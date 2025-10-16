---
description: Erfahren Sie, wie Prognosen in Analysis Workspace eine Reihe fortschrittlicher statistischer Verfahren verwenden, um Prognosewerte zu bestimmen.
title: Statistische Verfahren
feature: Visualizations
role: User
exl-id: f042a6dd-6af5-4bdd-afc9-07546d8ded6e
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 4%

---

# Statistische Verfahren

Der Prognoseservice unterstützt derzeit Prophet und hat sich bei den meisten Daten als effizient und zuverlässig erwiesen. Prophet ist ein weit verbreitetes Open-Source-Prognosepaket, das von Meta entwickelt wurde. Sie zerlegt Daten in Komponenten für Trends, Saisonalen Ereignisse und Ereignisse. Das Prophet-Modell ist effizient und lässt sich gut auf viele Prognoseanwendungen skalieren. Außerdem arbeitet das Modell zuverlässig gegen Ausreißer und fehlende Daten.

In Zukunft gibt es Pläne, Modelle auszuwählen, die auf Heuristiken basieren, zum Beispiel wählen Sie Online Approximate Gauß Process für Streaming-Daten oder NeuralProphet, wenn Benutzer die beste Prognosegenauigkeit angeben und längere Wartezeiten tolerieren können.

Der Service skaliert Daten automatisch herunter, wenn zu viele Datenpunkte vorhanden sind, um die Reaktionszeit sicherzustellen. Die Ziel-Reaktionszeit ist auf ca. 3 Sekunden eingestellt. Wenn die Anzahl der Datenpunkte 5.500 überschreitet, werden die Zeitreihendaten derzeit adaptiv heruntergerechnet, je nach Länge der Daten. Die Ausgabe wird wieder in die ursprüngliche Datenfrequenz konvertiert, sodass der adaptive Sampling-Prozess keine Auswirkungen auf das Benutzererlebnis hat.

Die Auswirkungen auf die Feiertage werden berücksichtigt, wenn mehrjährige Daten verfügbar sind. Derzeit sind folgende Feiertage in Betracht zu ziehen:

* Martin Luther King Day
* Tag der Präsidenten
* Gedenktag
* 4. Juli
* Erntedankfest
* Black Friday
* Cyber Monday
* Weihnachten

Der Service kann auch eine einfache Anomalie (Ausreißer) entfernen, z. B. durch Entfernen von Datenpunkten, die außerhalb des Sechs-Sigma-Bereichs liegen. Dies ist nicht standardmäßig aktiviert, da davon ausgegangen wird, dass alle Datenpunkte gültig sind. Anomalien können sich negativ auf die Modellqualität auswirken, auch wenn das Prophet-Modell im Allgemeinen gegenüber Ausreißern widerstandsfähig ist.

Der Service akzeptiert benutzerspezifische Saisoneinstellungen, z. B. die tägliche und die wöchentliche Saisonalität. Andernfalls wählt das Modell automatisch die Saisonabhängigkeit aus. Für unterschiedliche Datengranularität verwendet der Service verschiedene Längen historischer Daten zum Erstellen von Prognosemodellen. Bei täglichen Daten ruft sie beispielsweise Daten aus mehr als einem Jahr ab (falls verfügbar). Für stündliche Daten werden Daten aus acht Wochen abgerufen (falls verfügbar). Das Abrufen von Daten kann zeitaufwendig sein und manchmal zu längerer Wartezeit führen.

Die für eine andere Zeitgranularität erforderlichen historischen Daten:

| Granularität | Historische Daten erforderlich |
|---|--:|
| Minute | 3 Tage |
| Stunde | 2 Wochen |
| Tag | 8 Wochen |
| Woche | 2 Jahre |
| Monat | 2 Jahre |
| Quartal | 8 Quartale |
| Jahr | 8 Jahre |


Das Prognoseergebnis für jeden angegebenen Zeitpunkt umfasst ein Prognoseintervall (definiert durch die untere und obere Grenze), das den zukünftigen beobachteten Wert zu 95 % der Zeit enthalten soll, häufig als Konfidenzintervall bezeichnet. Es gibt keine Begrenzung dafür, wie weit der Service in die Zukunft vorhersagen kann. Allerdings nimmt die Unsicherheit bei Prognosen mit Daten, die weiter in die Zukunft reichen, zu, was sich in einem größeren Prognoseintervall im Zeitverlauf widerspiegelt.

Der Service geht in Bezug auf Benutzerdaten von keiner Annahme aus. Beispielsweise geht der Service nicht davon aus, dass die Daten nicht negativ sind. Dies bedeutet, dass die Prognosen und/oder deren Grenzen negativ sein können, wenn die Daten einen starken Abwärtstrend aufweisen, obwohl alle beobachteten Datenpunkte nicht negativ sind.


## Verweise

1. Taylor, Sean J. und Benjamin Letham: *Forecasting at scale.* The American Statistician 72.1 (2018): 37-45.
1. Triebe, Oskar u. a.: *Neuralprophet: Erklärbare Vorhersagen in großem Maßstab.* arXiv-Vorabdruck arXiv:2111.15397(2021).
1. Zhang and Arbor: *Zeitreihen-Anomalieerkennung.* US-#18/057883.
