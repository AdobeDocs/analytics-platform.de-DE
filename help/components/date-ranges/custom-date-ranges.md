---
description: Beispiel für benutzerdefinierte Datumsbereiche in Analysis Workspace.
keywords: Analysis Workspace
title: Beispiel für benutzerdefinierte Datumsbereiche
feature: Calendar
exl-id: 1a7df63a-bf18-4c38-b7e2-e83c2d278544
role: User
source-git-commit: 90d1c51c11f0ab4d7d61b8e115efa8257a985446
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 4%

---

# Beispiel für benutzerdefinierte Datumsbereiche

Dieser Artikel zeigt weitere Beispiele für benutzerdefinierte Datumsbereiche



## Letzte vor zwei Monaten

+++ Details

Sie möchten einen benutzerdefinierten Datumsbereich definieren, der vor zwei Monaten definiert wurde. Sie verwenden eine der Vorgaben.

![Letzte 2 Monate her](assets/date-range-example-simple.png)

+++


## Rollierend bis Ende letzter Woche

+++ Details

Sie möchten einen Datumsbereich definieren, der den Zeitraum zwischen dem aktuellen Tag vor einer Woche und dem Ende derselben letzten Woche definiert. Wenn heute beispielsweise Mittwoch, der 11. September 2024 ist. Sie möchten einen Datumsbereich von Mittwoch, 4. September 2024 bis Samstag, 7. September 2024. September

![Beispiel für einen Datumsbereich](assets/date-range-example.png)

+++

<!--
## Example: Use a 7-day rolling date range

You can create a date range that specifies a 7-day rolling window that ends one week ago:

![](assets/create_date_range.png)

Use *`rolling daily`*.

* The Start settings would be *`current day minus 6 days`*.

* The End settings would be *`current day minus 7 days`*.

This date range can be a component that you drag onto any freeform table.
-->