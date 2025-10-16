---
description: Erfahren Sie, welche statistischen Verfahren zum Erkennen von Anomalien verwendet werden.
title: In der Anomalieerkennung verwendete statistische Verfahren
feature: Anomaly Detection
exl-id: 7165e7a1-a04f-450e-bffd-e329adac6903
role: User
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 33%

---

# Statistische Verfahren

Die Anomalieerkennung in Analysis Workspace setzt eine Reihe statistischer Verfahren ein, um festzustellen, ob eine Beobachtung als anormal anzusehen ist oder nicht.

Je nach der im Bericht verwendeten Datumsgranularität werden 3 verschiedene statistische Verfahren eingesetzt – für stündliche, tägliche, wöchentliche/monatliche Anomalieerkennung. Die statistischen Verfahren werden nachfolgend beschrieben.

## Anomalieerkennung für Granularität „Täglich“ 

Für Berichte mit täglicher Granularität berücksichtigt der Algorithmus verschiedene wichtige Faktoren, um Ergebnisse mit höchstmöglicher Genauigkeit bereitzustellen. Zunächst bestimmt der Algorithmus anhand der verfügbaren Daten, welche Modellart angewendet werden soll, und wählt dabei eine von zwei Klassen aus: ein zeitreihenbasiertes Modell oder ein Modell zur Erkennung von Ausreißern (funktionale Segmentierung genannt).

Die Entscheidung für das zeitreihenbasierte Modell beruht auf den folgenden Kombinationen für den Typ ETS (Error, Trend and Seasonality = Fehler, Trend und Saisonabhängigkeit), wie von [Hyndman und Kollegen (2008)](https://idp.springer.com/authorize?response_type=cookie&client_id=springerlink&redirect_uri=https%3A%2F%2Flink.springer.com%2Fbook%2F10.1007%2F978-3-540-71918-2). Insbesondere versucht der Algorithmus die folgenden Kombinationen:

1. ANA (additiver Fehler, kein Trend, additive Saisonabhängigkeit)
1. AAA (additiver Fehler, additiver Trend, additive Saisonabhängigkeit)
1. MNM (multiplikativer Fehler, kein Trend, multiplikative Saisonabhängigkeit)
1. MNA (multiplikativer Fehler, kein Trend, additive Saisonabhängigkeit)
1. AAN (additiver Fehler, additiver Trend, keine Saisonabhängigkeit)

Der Algorithmus testet die Eignung jeder dieser Kombinationen, indem er die Kombination mit dem besten mittleren absoluten Prozentfehler (MAPE) auswählt. Wenn der Zuordnungssatz des besten Zeitreihenmodells jedoch größer als 15 % ist, wird eine funktionale Segmentierung angewendet. In der Regel passen Daten mit einem hohen Wiederholungsgrad (z. B. Woche über Woche oder Monat über Monat) am besten zu einem Zeitreihenmodell.

Nach der Modellauswahl passt der Algorithmus die Ergebnisse dann an Feiertagen und der Saisonabhängigkeit von einem Jahr zum anderen an. Für Feiertage prüft der Algorithmus, ob einer der folgenden Feiertage im Datumsbereich des Berichts vorhanden ist:

* Gedenktag
* &#x200B;4. Juli
* Erntedankfest
* Black Friday
* Cyber Monday
* &#x200B;24. bis 26. Dezember
* &#x200B;1. Januar
* &#x200B;31. Dezember

Diese Feiertage wurden anhand umfangreicher statistischer Analysen einer großen Anzahl von Datenpunkten ausgewählt, um die Feiertage zu ermitteln, die den größten Einfluss in den meisten Kunden-Trends gezeigt haben. Während die Liste sicherlich nicht für alle Kunden oder Geschäftszyklen vollständig ist, verbessert die Anwendung von Feiertagen die Leistung des Algorithmus insgesamt für fast alle Datensätze von Kunden erheblich.

Nach Auswahl des Modells und der Identifizierung der im Berichtszeitraum befindlichen Feiertage fährt der Algorithmus wie folgt fort:

1. Konstruiert den Referenzzeitraum der Anomalie. Dieser Anomalie-Referenzzeitraum umfasst bis zu 35 Tage vor dem Berichtsdatumsbereich und einen entsprechenden Datumsbereich 1 Jahr davor. Falls erforderlich, Schalttage berücksichtigen und alle anwendbaren Feiertage berücksichtigen, die an einem anderen Kalendertag im Vorjahr aufgetreten sein könnten.
1. Er testet, ob im aktuellen Zeitraum (außer dem Vorjahr) Feiertage vorhanden sind, die laut den aktuellsten Daten eine Anomalität darstellen.
1. Wenn der Feiertag im aktuellen Datumsbereich als anormal betrachtet wird, passt der Algorithmus den erwarteten Wert und das Konfidenzintervall des aktuellen Feiertags an die Werte des Feiertags aus dem vergangenen Jahr an (unter Betrachtung von zwei Tagen vorher und nachher). Die Korrektur für den aktuellen Feiertag basiert auf dem niedrigsten absoluten Mittelwert des Fehlers in Prozent von:

   1. Additive Wirkungen
   1. Multiplikative Effekte
   1. Differenz gegenüber dem Vorjahr

Beachten Sie im folgenden Beispiel die deutliche Verbesserung der Performance an Weihnachten und Neujahr:

![Zwei Liniendiagramme, die Leistungsänderungen mit und ohne Feiertagsleistung zeigen.](assets/anomaly_statistics.png)

## Anomalieerkennung für Granularität „Stündlich“ 

Stündliche Daten basieren auf demselben Zeitreihen-Algorithmus wie der tägliche Granularitätsalgorithmus. Sie beruht jedoch stark auf zwei Trendmustern: dem 24-Stunden-Zyklus sowie dem Wochenende-/Wochentagszyklus. Um diese beiden saisonalen Effekte zu erfassen, erstellt der stündliche Algorithmus mithilfe des oben beschriebenen Ansatzes zwei separate Modelle für ein Wochenende und einen Wochentag.

Die Schulungsfenster für stündliche Trends basieren auf einem 336-Stunden-Lookback-Fenster.

## Anomalieerkennung für die Granularitäten „Wöchentlich“ und „Monatlich“ 

Wöchentliche und monatliche Trends weisen nicht dieselben wöchentlichen oder täglichen Trends auf, die bei täglichen oder stündlichen Granularitäten gefunden werden, sodass ein solcher separater Algorithmus verwendet wird. Bei wöchentlichen und monatlichen Tests wird ein zweistufiger Ansatz zur Erkennung von Ausreißern als Generalized Extreme Studentized Deviate (GESD) Test bezeichnet. Dieser Test berücksichtigt die maximale Anzahl erwarteter Anomalien in Kombination mit dem angepassten Boxplot-Plot-Ansatz (eine nicht parametrische Methode zur Ausreißererkennung), um die maximale Anzahl von Ausreißern zu bestimmen. Die beiden Schritte sind:

1. Angepasste Boxplot-Plot-Funktion: Diese Funktion bestimmt die maximale Anzahl von Anomalien bei den Eingabedaten.
1. GESD-Funktion: wird auf die Eingabedaten mit der Ausgabe aus Schritt 1 angewendet.

Der Schritt zur Anomalieerkennung für Feiertag und Jahreszeit zieht dann die Daten des letzten Jahres von den diesjährigen Daten ab. Anschließend werden die Daten erneut mithilfe des oben beschriebenen zweistufigen Prozesses iteriert, um zu überprüfen, ob Anomalien saisonal relevant sind. Jede dieser Datumsgranularitäten verwendet ein 15 Zeiträume zurückliegendes Zeitfenster, in dem der für den Bericht ausgewählte Datumsbereich liegt (entweder 15 Monate oder 15 Wochen), sowie einen entsprechenden Datumsbereich, der 1 Jahr vor dem Trainingszeitraum liegt.
