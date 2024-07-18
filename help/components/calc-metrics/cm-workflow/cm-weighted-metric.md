---
description: Enthält Beispiele für gefilterte und gewichtete Metriken.
title: Gefilterte und gewichtete Metriken
feature: Calculated Metrics
exl-id: 5e73ab52-627a-4064-bfb7-354c0ba1e4ee
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 76%

---

# Gefilterte und gewichtete Metriken

Enthält Beispiele für gefilterte und gewichtete Metriken.

## Gefilterte Absprungrate {#section_D42F2452E4464948934063EB6F2DAAB4}

Mit dieser einfachen Metrik wird die Absprungrate nur für die Seiten mit mehr als 100 Besuchen angezeigt:

![Zusammenfassungsfenster mit den Metriken, die auf Spalte 1 (Besuche) und Spalte 2 (100) angewendet werden, zusammen mit der Absprungrate. ](assets/cm_fbr.png)

Denken Sie daran, dass diese Formel von einem konsistenten Zeitraum abhängig ist. Wenn Sie einen Bericht für einen Tag ausführen, lohnt es sich, jede Seite mit mehr als 20 Besuchen zu betrachten. Wenn der Bericht für einen Monat ausgeführt wird, sollte der Filter mehr Besuche umfassen.

## Gefilterte Absprungrate mit Perzentil {#section_4F3E6D33A1FD438A932FA662B3510552}

Dieser Filter zeigt die Absprungrate für die oberen 30 Prozent der Seiten bei Sortierung nach Besuchen an.

![Wenn und filtern Sie dann die Absprungrate für die 30 % der wichtigsten Seiten, sortiert nach Besuchen.](assets/cm_wbr_2.png)

## Gewichtete Metrik {#section_F2D16B14569948289CF1310F9E6E3FC2}

Beispiel: Sie möchten nach Absprungrate im Allgemeinen sortieren, aber Seiten mit mehr Besuchen weiter oben in der Liste anzeigen. Dazu könnten Sie eine gewichtete Absprungrate erstellen, die in etwa wie folgt aussieht:

![Zusammenfassung mit Definition für Absprungratenzeiten bei Besuchen.](assets/cm_wbr.png)
