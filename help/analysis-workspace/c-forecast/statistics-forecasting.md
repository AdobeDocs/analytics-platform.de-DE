---
description: Die Prognosen in Analysis Workspace verwenden eine Reihe fortschrittlicher statistischer Verfahren zur Bestimmung der Prognosewerte.
title: In der Prognose verwendete statistische Verfahren
feature: Visualizations
role: User
exl-id: f042a6dd-6af5-4bdd-afc9-07546d8ded6e
source-git-commit: accd7300c2dd6224e4d154cb6e3889f564e07a1a
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 6%

---

# Im Prognosedienst verwendete statistische Verfahren

Der Prognosedienst unterstützt derzeit Prophet und funktioniert für die meisten Daten effizient und zuverlässig. Prophet ist ein von Meta entwickeltes Open-Source-Prognospaket. Sie dekomprimiert Daten in Komponenten für Trends, saisonale Effekte und Ereignisse. Das Prophet-Modell ist effizient und skaliert gut auf viele Prognoseanwendungen. Außerdem funktioniert das Modell robust gegen Ausreißer und fehlende Daten.

In Zukunft werden Modelle auf der Basis von Heuristik ausgewählt, z. B. Online Approximate Gaussian Process für Streaming-Daten oder NeuralProphet , wenn Benutzer die beste Vorhersagegenauigkeit angeben und längere Wartezeiten tolerieren können.

Der Dienst skaliert Daten automatisch herunter, wenn zu viele Datenpunkte vorhanden sind, um die Reaktionszeit sicherzustellen. Die Zielantwortzeit beträgt ca. 3 Sekunden. Wenn die Anzahl der Datenpunkte derzeit 5500 überschreitet, werden die Zeitreihendaten je nach Datenlänge adaptiv nach unten gesampelt. Die Ausgabe wird wieder in die ursprüngliche Datenfrequenz konvertiert, sodass der adaptive Sampling-Prozess keine Auswirkungen auf Benutzererlebnisse hat.

Die Auswirkungen auf die Ferien werden berücksichtigt, wenn Daten aus mehreren Jahren verfügbar sind. Derzeit ist die Liste der fraglichen Feiertage:

* Martin Luther King Day
* Präsident Day
* Memorial Day (nur USA)
* 4. Juli
* Thanksgiving (nur USA)
* Black Friday (nur USA)
* Cyber Monday (nur USA)
* Weihnachten

Der Dienst kann auch eine einfache Anomalie (Ausreißer) entfernen, z. B. indem Datenpunkte entfernt werden, die außerhalb des sechs Sigma-Bereichs liegen. Dies ist standardmäßig nicht aktiviert, da davon ausgegangen wird, dass alle Datenpunkte gültig sind. Anomalien können sich negativ auf die Modellqualität auswirken, auch wenn das Eigenschaftsmodell gegenüber Ausreißern im Allgemeinen widerstandsfähig ist.

Der Dienst akzeptiert benutzerdefinierte saisonale Einstellungen, z. B. tägliche und wöchentliche Saisonabhängigkeit. Andernfalls wählt das Modell automatisch die Saisonabhängigkeit aus. Für unterschiedliche Datengranularität verwendet der Dienst verschiedene Längen historischer Daten, um Prognosemodelle zu erstellen. Beispielsweise ruft er für tägliche Daten mehr als ein Jahr Daten ab (sofern verfügbar). Für stündliche Daten werden Daten aus acht Wochen abgerufen (sofern verfügbar). Das Abrufen von Daten kann zeitaufwendig sein und manchmal zu längerer Wartezeit führen.

Die historischen Daten, die für eine andere Zeitgranularität erforderlich sind:

| Granularität | Erforderliche historische Daten |
|---|--:|
| Minute | 3 Tage |
| Stunde | 2 Wochen |
| Tag | 8 Wochen |
| Woche | 2 Jahre |
| Monat | 2 Jahre |
| Quartal | 8 Quartale |
| Jahr | 8 Jahre |


Das Prognosergebnis für jede angegebene Zeit enthält ein Prognoseintervall (definiert durch die untere und obere Grenze), das den künftigen beobachteten Wert von 95 % der Zeit enthalten soll, der häufig als Konfidenzintervall bezeichnet wird. Es gibt keine Grenze, wie weit der Dienst in die Zukunft vorhersagen kann. Die Unsicherheit bei den Prognosen steigt jedoch mit den Daten weiter in die Zukunft, was durch ein breiteres Prognoseintervall im Laufe der Zeit widergespiegelt wird.

Der Dienst stellt keine Annahmen über Benutzerdaten auf. Beispielsweise geht der Dienst nicht davon aus, dass die Daten nicht negativ sind. Dies bedeutet, dass die Prognosen und/oder ihre Grenzen negativ sein können, wenn die Daten einen starken Abwärtstrend aufweisen, auch wenn alle beobachteten Datenpunkte nicht negativ sind.


## Verweise

1. Taylor, Sean J. und Benjamin Letham: *Vorhersagen im Maßstab.* Der amerikanische Statistiker 72.1 (2018): 37-45.
1. Triebe, Oskar, et al.: *Neuralprophet: Erklärbare Vorhersagen im Maßstab.* arXiv preprint arXiv:2111.15397(2021).
1. Zhang und Arbor: *Anomalieerkennung für Zeitreihen.* US-Patentanmeldung #18/057883.
