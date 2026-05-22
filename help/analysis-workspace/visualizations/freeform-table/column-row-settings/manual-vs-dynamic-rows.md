---
title: Dynamische und statische Dimension-Elemente
description: Erfahren Sie, wie Sie dynamische und statische Dimensionselemente in Freiformtabellen in Analysis Workspace verwenden.
feature: Visualizations
exl-id: 7806f535-15c7-40f4-955a-724d9752969d
role: User
TQID: https://experienceleague.adobe.com/q9X-MNr4r3Xrs16gAgH6-F3yrRDJP73xfXdd8BcFg84
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 549
ht-degree: 77%

---

# Dynamische und statische Dimensionselemente

In Freiformtabellen können die Zeilen und Spalten verschiedene Komponentenwerte enthalten. Diese Werte können abhängig von der Analyse, die Sie erstellen möchten, dynamisch (zeitabhängig) oder statisch (nicht zeitabhängig) sein.

## Dynamische Dimensionselemente

Dynamische Dimensionselemente ändern sich mit der Zeit und hängen von der Metrik ab, nach der in der Freiformtabelle sortiert wird. Dynamische Dimensionselemente werden bevorzugt, wenn Sie die obersten Elemente für einen bestimmten Zeitraum analysieren möchten.

Wenn Sie eine Dimension in eine Freiform-Tabelle ablegen, werden dynamische Zeilen zurückgegeben. Dynamische Zeilen stellen die obersten Elemente dar, die der Dimension für eine bestimmte Metrik und einen bestimmten Zeitraum entsprechen. Sie können eine Dimension auch in Freiform-Tabellenspalten ablegen, und die Dimension wird automatisch in die fünf obersten Dimensionselemente erweitert.

Wenn Sie beispielsweise die Dimension „Browsertyp“ in die Tabelle ziehen, werden die Dimensionselemente für den oberen Browser-Typ (z. B. Microsoft, Apple, Google usw.) Dynamische Rückkehr zu den Tabellenzeilen. Wenn sie in eine Spalte abgelegt wurde, werden die obersten 5 Dimensionselemente des Browser-Typs dynamisch zurückgegeben.

Dynamische Dimensionselemente verfügen über die Zeilenfilteroption ![Filter](/help/assets/icons/Filter.svg) und ein ![Schließen](/help/assets/icons/Close.svg) und **nicht** eine Sperre ![LockClosed](/help/assets/icons/LockClosed.svg). <!--do they have the lock icon? --> Wenn Sie ![Schließen](/help/assets/icons/Close.svg) neben einem dynamischen Dimensionselement klicken, wird automatisch ein Filter angewendet. Weitere Informationen zum Anwenden von Filtern auf Tabellen finden Sie unter [Filtern und Sortieren von Tabellen](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).


![Eine Freiformtabelle mit hervorgehobenem Filtersymbol.](assets/dynamic-items.png)

## Statische Dimensionselemente

Statische Dimensionselemente ändern sich nicht mit der Zeit. Es handelt sich dabei um feste Komponenten, die immer in einer Freiform-Tabelle zurückgegeben werden. Statische Dimensionselemente werden bevorzugt, wenn Sie immer dasselbe Element analysieren möchten, unabhängig davon, ob es sich um bestimmte Kampagnen oder bestimmte Wochentage handelt.

Jedes Mal, wenn Sie bestimmte Komponentenwerte (Dimension, Metrik, Segment, Datumsbereich) manuell in eine Tabelle auswählen und dort ablegen, ist das Ergebnis eine statische Liste von Zeilen oder Spalten.

Wenn Sie beispielsweise über bestimmte Browser-Typ-Elemente wie „Microsoft“ und „Apple“ ziehen, werden diese beiden Elemente immer in die Tabelle gezogen.

Statische Dimensionselemente können auch erstellt werden, wenn Sie **[!UICONTROL Nur ausgewählte Zeilen anzeigen]** aus dem Kontextmenü für ausgewählte Zeilen auswählen.

Statische Dimensionselemente verfügen **nicht** über die Zeilenfilteroption. Stattdessen sind für jedes Element ![LockClosed](/help/assets/icons/LockClosed.svg) und ![Close](/help/assets/icons/Close.svg) vorhanden. Wählen Sie ![Close](/help/assets/icons/Close.svg) aus, um dieses Dimensionselement aus der Tabelle zu entfernen.

![Eine Freiformtabelle mit dem Browser-Typ und der Microsoft-Zeile mit einem Sperrsymbol. Hinweis: Dieses Dimensionselement ist statisch und ändert sich nicht mit der Zeit.](assets/static-items.png)

## Gemischte Dimensionselemente

Dimensionselemente aus verschiedenen Dimensionen können derselben Tabelle hinzugefügt werden. In diesen Fällen steht in der Kopfzeile der Zeile **[!UICONTROL Gemischte Dimensionen]**. Diese Dimensionselemente sind statisch. Fügen Sie beispielsweise bestimmte Dimensionselemente aus der Dimension „Browser-Gruppe“ und andere Dimensionselemente aus der Dimension „Browser-Name“ hinzu.

![Eine Freiformtabelle mit hervorgehobener Spalte mit den gemischten Dimensionen.](assets/mixed-dimensions.png)

## Freiform-Gesamtzeilen

Dynamische und statische Zeilen verhalten sich in der Freiform-Gesamtzeile unterschiedlich. Standardmäßig:

* Dynamische Zeilen werden Server-seitig summiert und deduplizieren Metriken wie „Sitzungen“ oder „Personen“.
* Statische Zeilen werden Client-seitig summiert und deduplizieren **keine** Metriken. Um die Gesamtzeile Server-seitig zu berechnen, ändern Sie die Zeileneinstellung auf **Gesamtsumme anzeigen**. [Weitere Informationen](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md)
