---
title: Dynamische und statische Dimensionselemente im Vergleich
description: Interaktion mit dynamischen und statischen Dimensionselementen in Tabellen
feature: Visualizations
exl-id: 7806f535-15c7-40f4-955a-724d9752969d
role: User
source-git-commit: 4942c83e34b129e3718084601d5a733bcebf4de9
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 44%

---

# Dynamische und statische Dimensionselemente

In Freiform-Tabellen können die Zeilen und Spalten verschiedene Komponentenwerte enthalten. Diese Werte können dynamisch (Änderung im Zeitverlauf) oder statisch (keine Änderung im Zeitverlauf) sein, je nach der Analyse, die Sie erstellen möchten.

## Dynamische Dimensionselemente

Dynamische Dimensionselemente ändern sich im Laufe der Zeit und sind von der Metrik abhängig, nach der in der Freiformtabelle sortiert wird. Dynamische Dimensionselemente werden bevorzugt, wenn Sie die obersten Elemente für einen bestimmten Zeitraum analysieren möchten.

Wenn Sie eine Dimension in eine Freiform-Tabelle ablegen, werden dynamische Zeilen zurückgegeben. Dynamische Zeilen stellen die obersten Elemente dar, die der Dimension für eine bestimmte Metrik und einen bestimmten Zeitraum entsprechen. Sie können eine Dimension auch in Freiform-Tabellenspalten ablegen und die Dimension wird automatisch in die fünf obersten Dimensionselemente erweitert.

Wenn Sie beispielsweise die Dimension „Browser-Typ“ in die Tabelle ziehen, kehren die oberen Dimensionselemente des Browser-Typs (z. B. Microsoft, Apple, Google usw.) dynamisch zu den Tabellenzeilen zurück. Wenn sie in eine Spalte abgelegt wurde, werden die obersten 5 Browsertyp-Dimensionselemente dynamisch zurückgegeben.

Dynamische Dimensionselemente verfügen über die Zeilenfilteroption ![Filter](/help/assets/icons/Filter.svg) und ein ![Schließen](/help/assets/icons/Close.svg) und **nicht** eine Sperre ![LockClosed](/help/assets/icons/LockClosed.svg). <!--do they have the lock icon? --> Wenn Sie neben ![ dynamischen Dimensionselement ](/help/assets/icons/Close.svg)Schließen“ klicken, wird automatisch ein Filter angewendet. Weitere Informationen zum Anwenden von Filtern auf Tabellen finden Sie unter [Tabellen filtern und sortieren](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).


![Eine Freiformtabelle mit hervorgehobenem Filtersymbol.](assets/dynamic-items.png)

## Statische Dimensionselemente

Statische Dimensionselemente ändern sich nicht mit der Zeit. Es handelt sich dabei um feste Komponenten, die immer in einer Freiform-Tabelle zurückgegeben werden. Statische Dimensionselemente werden bevorzugt, wenn Sie immer dasselbe Element analysieren möchten, unabhängig davon, ob es sich um bestimmte Kampagnen oder bestimmte Wochentage handelt.

Jedes Mal, wenn Sie bestimmte Komponentenwerte (Dimension, Metrik, Filter, Datumsbereich) manuell in eine Tabelle auswählen und dort ablegen, ist das Ergebnis eine statische Liste von Zeilen oder Spalten.

Wenn Sie beispielsweise über bestimmte Browser-Typ-Elemente wie Microsoft und Apple ziehen, werden diese beiden Elemente immer in die Tabelle gezogen.

Statische Dimensionselemente können auch erstellt werden, wenn Sie **[!UICONTROL Nur ausgewählte Zeilen anzeigen]** aus dem Kontextmenü für ausgewählte Zeilen auswählen.

Statische Dimensionselemente verfügen **nicht** über die Zeilenfilteroption. Stattdessen sind ![LockClosed](/help/assets/icons/LockClosed.svg) und ![Close](/help/assets/icons/Close.svg) für jedes Element vorhanden. Wählen Sie ![Schließen](/help/assets/icons/Close.svg) aus, um dieses Dimensionselement aus der Tabelle zu entfernen.

![Eine Freiformtabelle, die den Browser-Typ und die Microsoft-Zeile mit einem Sperrsymbol anzeigt Hinweis: Dieses Dimensionselement ist statisch und ändert sich nicht mit der Zeit.](assets/static-items.png)

## Gemischte Dimensionselemente

Dimensionselemente aus verschiedenen Dimensionen können derselben Tabelle hinzugefügt werden. Die Zeilenüberschrift lautet **[!UICONTROL Gemischte Dimensionen]** in diesen Fällen. Diese Dimensionselemente sind statisch. Beispielsweise das Hinzufügen bestimmter Dimensionselemente aus der Dimension „Browser-Gruppe“ und anderer Dimensionselemente aus der Dimension „Browser-Name“.

![Eine Freiformtabelle, in der die Spalte mit den gemischten Dimensionen hervorgehoben ist.](assets/mixed-dimensions.png)

## Freiform-Gesamtzeilen

Dynamische und statische Zeilen verhalten sich in der Freiform-Gesamtzeile unterschiedlich. Standardmäßig:

* Dynamische Zeilen werden Server-seitig zusammengefasst und Metriken wie Sitzungen oder Personen dedupliziert.
* Statische Zeilen werden Client-seitig summiert und deduplizieren **keine** Metriken. Um die Gesamtzeile Server-seitig zu berechnen, ändern Sie die Zeileneinstellung auf **Gesamtsumme anzeigen**. [Weitere Infos](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md)
