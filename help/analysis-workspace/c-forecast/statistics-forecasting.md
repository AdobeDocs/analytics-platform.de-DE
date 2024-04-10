---
description: Für Prognosen in Analysis Workspace werden eine Reihe fortschrittlicher statistischer Verfahren verwendet, um Prognosewerte zu bestimmen.
title: Für Prognosen verwendete statistische Verfahren
feature: Visualizations
role: User
source-git-commit: 1bd24ee1163e4615bf5626c51aec9f167352f2f6
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 5%

---


# Im Prognosedienst verwendete statistische Verfahren

Der Prognoseservice unterstützt derzeit Prophet und hat sich bei den meisten Daten als effizient und zuverlässig erwiesen. Prophet ist ein weit verbreitetes Open-Source-Prognosen-Paket, das von Meta entwickelt wurde. Sie zerlegt Daten in Komponenten für Trends, Saisonalen und Ereignisse. Das Prophet-Modell ist effizient und skaliert gut für viele Prognoseanwendungen. Außerdem arbeitet das Modell zuverlässig gegen Ausreißer und fehlende Daten.

In Zukunft gibt es Pläne, Modelle auszuwählen, die auf Heuristiken basieren, z. B. wählen Sie Online Approximate Gauß Process für Streaming-Daten oder NeuralProphet, wenn Benutzer die beste Prognosegenauigkeit angeben und längere Wartezeiten tolerieren können.

Der Service skaliert Daten automatisch herunter, wenn zu viele Datenpunkte vorhanden sind, um die Reaktionszeit sicherzustellen. Die Ziel-Antwortzeit ist auf ca. 3 Sekunden eingestellt. Wenn die Anzahl der Datenpunkte 5.500 überschreitet, werden die Zeitreihendaten derzeit adaptiv heruntergerechnet, je nach Länge der Daten. Die Ausgabe wird wieder in die ursprüngliche Datenfrequenz konvertiert, sodass der adaptive Sampling-Prozess keine Auswirkungen auf das Benutzererlebnis hat.

Die Auswirkungen auf die Feiertage werden berücksichtigt, wenn mehrjährige Daten verfügbar sind. Derzeit sind die folgenden Feiertage in Betracht zu ziehen:

* Martin Luther King Day
* Tag der Präsidenten
* Memorial Day (nur USA)
* 4. Juli
* Thanksgiving (nur USA)
* Black Friday (nur USA)
* Cyber Monday (nur USA)
* Weihnachten

Der Service kann auch eine einfache Anomalie (Ausreißer) entfernen, z. B. durch Entfernen von Datenpunkten, die außerhalb des Sechs-Sigma-Bereichs liegen. Dies ist nicht standardmäßig aktiviert, da davon ausgegangen wird, dass alle Datenpunkte gültig sind. Anomalien können sich negativ auf die Modellqualität auswirken, auch wenn das Prophet-Modell im Allgemeinen gegenüber Ausreißern widerstandsfähig ist.

Der Service akzeptiert benutzerspezifische Saisoneinstellungen, z. B. die tägliche und die wöchentliche Saisonalität. Andernfalls wählt das Modell automatisch die Saisonalität aus. Für unterschiedliche Datengranularität verwendet der Service verschiedene Längen historischer Daten, um Prognosemodelle zu erstellen. Bei täglichen Daten ruft sie beispielsweise Daten aus mehr als einem Jahr ab (falls verfügbar). Für stündliche Daten werden acht Wochen Daten abgerufen (falls verfügbar). Das Abrufen von Daten kann zeitaufwendig sein und manchmal zu längerer Wartezeit führen.

Die für unterschiedliche Zeitgranularität erforderlichen historischen Daten:

| Granularität | Historische Daten erforderlich |
|---|--:|
| Minute | 3 Tage |
| Stunde | 2 Wochen |
| Tag | 8 Wochen |
| Woche | 2 Jahre |
| Monat | 2 Jahre |
| Quartal | 8 Quartale |
| Jahr | 8 Jahre |


Das Prognoseergebnis für jeden angegebenen Zeitpunkt enthält ein Prognoseintervall (definiert durch die untere und obere Grenze), das den zukünftigen beobachteten Wert zu 95 % der Zeit enthält, häufig als Konfidenzintervall bezeichnet. Es gibt keine Begrenzung dafür, wie weit der Service in die Zukunft vorhersagen kann. Allerdings nimmt die Unsicherheit bei Prognosen mit Daten, die weiter in die Zukunft reichen, zu, was sich in einem längeren Prognoseintervall im Zeitverlauf widerspiegelt.

Der Service geht in Bezug auf Benutzerdaten von keiner Annahme aus. Beispielsweise geht der Service nicht davon aus, dass die Daten nicht negativ sind. Dies bedeutet, dass die Prognosen und/oder deren Grenzen negativ sein können, wenn die Daten einen starken Abwärtstrend aufweisen, obwohl alle beobachteten Datenpunkte nicht negativ sind.


## Verweise

1. Taylor, Sean J. und Benjamin Letham: *Prognose in großem Maßstab.* In: The American Statistician 72.1 (2018), S. 37-45.
1. Triebe, Oskar u. a.: *Neuralprophet: Erklärbare Vorhersagen in großem Maßstab.* arXiv-Vorabdruck arXiv:2111.(2021).
1. Zhang und Arbor: *Anomalieerkennung in Zeitreihen.* In: US Patent Application #18/057883.

