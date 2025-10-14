---
description: Erfahren Sie, wie Sie Freiformtabellen in Analysis Workspace filtern und sortieren.
title: Filtern und Sortieren
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
role: User
source-git-commit: a16043f1bb15deba1332ed39438214597647b9b4
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 71%

---

# Filtern und Sortieren

Freiformtabellen in Analysis Workspace bilden die Grundlage für die interaktive Datenanalyse. Daher können sie Tausende von Informationszeilen enthalten. Das Filtern und Sortieren der Daten kann ein wichtiger Teil der effizienten Aufdeckung der wichtigsten Informationen sein.

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## Filtern von Tabellen

Mit Filtern in Analysis Workspace können Sie die wichtigsten Informationen aufdecken.

>[!NOTE]
>
> Es können nur dynamische Dimensionselemente gefiltert werden, wie in diesem Abschnitt beschrieben. Statische Dimensionselemente können nicht gefiltert werden. Weitere Informationen finden Sie unter [Dynamische und statische Dimensionselemente in Freiformtabellen](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

Sie können mehrere Methoden verwenden, um Zeilen aus einer Freiformtabelle zu filtern.

* Ausschließen bestimmter Zeilen aus einer Tabelle
* Anwenden von Filtern auf eine Tabelle
* Verwenden von Zielgruppensegmenten

Sehen Sie sich unbedingt an, wie sich die einzelnen Methoden auf die [Gesamtwerte von Freiformtabellen](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md) auswirken.

### Ausschließen bestimmter Zeilen aus einer Tabelle

Sie können bestimmte Zeilen schnell aus der Tabelle ausschließen, ohne ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** verwenden zu müssen.

>[!NOTE]
>
>Wenn Sie Zeilen ausschließen, wie in diesem Abschnitt beschrieben, wird im Filterdialogfeld [!UICONTROL Erweitert] automatisch eine Regel [!UICONTROL Elemente immer ausschließen] hinzugefügt. Sie können die angewendete Regel anzeigen, indem Sie auf das Filtersymbol ![Filter](/help/assets/icons/Filter.svg) und dann auf [**[!UICONTROL Erweiterte Optionen anzeigen]**](#apply-a-simple-or-advanced-filter-to-a-table) klicken.

So schließen Sie bestimmte Zeilen aus einer Freiformtabelle aus:

1. Bewegen Sie den Mauszeiger über die Zeile, die Sie ausschließen möchten, und wählen Sie dann ![Schließen](/help/assets/icons/Close.svg) aus.

   Halten Sie die ***Umschalttaste*** gedrückt, um einen Zeilenbereich auszuwählen, oder halten Sie die Taste ***cmd*** (Mac) oder die Taste ***Strg*** (Windows) gedrückt, um mehrere Zeilen auszuwählen.

<!--### Right-click > Delete selected rows

Note: this option does not seem to work. AN-338422

1. Select 1 or more rows. 
1. Right-click and select **[!UICONTROL Delete Selected Rows]**. 

   This action will remove the rows from the table and apply a table filter.-->


### Anwenden eines einfachen oder erweiterten Filters auf eine Tabelle

So filtern Sie Daten in Freiformtabellen:

1. Bewegen Sie den Mauszeiger über die Spalte mit den Daten, die Sie filtern möchten. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Wählen Sie ![Filter](/help/assets/icons/Filter.svg) **Filter** aus, wenn die Option angezeigt wird.

   ![Freiformtabelle mit hervorgehobenem Filtersymbol.](assets/table-filter-icon.png)

   Die folgenden Optionen sind im Dialogfeld **[!UICONTROL Durchsuchen]** verfügbar:

   ![Filter simple](assets/filter-simple.png){width="500"}

   | Option | Funktion |
   |---------|----------|
   | [!UICONTROL **„Kein Wert“ einschließen**] | Wählen Sie diese Option, um eine Zeile **[!UICONTROL Kein Wert]** in der Tabelle für Daten anzuzeigen, die für die ausgewählte Dimension keinen Wert hat. Heben Sie die Auswahl für diese Option auf, um die Zeile **[!UICONTROL Kein Wert]** auszublenden. |
   | [!UICONTROL **Suchbegriff**] | Geben Sie ein Wort oder eine Wortgruppe an, nach dem bzw. der Sie filtern möchten. Es werden nur Zeilen angezeigt, die das Wort oder die exakte Phrase enthalten. |


1. (Optional) Um nach verschiedenen Kriterien oder nach mehreren Kriterien zu filtern, wählen Sie [!UICONTROL **Erweiterte Einstellungen anzeigen**] aus.

   Die folgenden erweiterten Filteroptionen sind verfügbar:

   ![Filter simple](assets/filter-advanced.png){width=500}

   | Option | Funktion |
   |---------|----------|
   | [!UICONTROL **„Kein Wert“ einschließen**] | Wählen Sie diese Option, um eine Zeile **[!UICONTROL Kein Wert]** in der Tabelle für Daten anzuzeigen, die für die ausgewählte Dimension keinen Wert hat. Heben Sie die Auswahl für diese Option auf, um die Zeile **[!UICONTROL Kein Wert]** auszublenden. |
   | [!UICONTROL **Übereinstimmung**] | Wählen Sie [!UICONTROL **Wenn alle Kriterien erfüllt sind**] aus, um nur Daten anzuzeigen, die alle angegebenen Kriterien erfüllen. Diese Option führt normalerweise zu verfeinerten Daten.<br/><br/>Wählen Sie [!UICONTROL **Wenn ein beliebiges Kriterium erfüllt ist**] aus, um Daten anzuzeigen, die eines der von Ihnen angegebenen Filterkriterien erfüllen. Diese Option führt normalerweise zu weniger verfeinerten Daten. |
   | [!UICONTROL **Kriterien**] | Treffen Sie eine Auswahl aus den folgenden Filteroptionen:<br/><ul><li>[!UICONTROL **Enthält die Wortgruppe**] (Standard): Es werden nur Daten in die gefilterten Ergebnisse aufgenommen, die die von Ihnen angegebene Wortgruppe enthalten. Die Wörter müssen in der Reihenfolge vorliegen, die im Feld [!UICONTROL **Nach Wort oder Phrase suchen**] angegeben ist.</li><li>[!UICONTROL **Enthält einen der Begriffe**]: Nur Daten, die ein oder mehrere Wörter aus der angegebenen Phrase enthalten, werden in die gefilterten Ergebnisse aufgenommen. </li><li>[!UICONTROL **Enthält alle Begriffe**]: Nur Daten, die alle Wörter aus der angegebenen Phrase enthalten, werden in die gefilterten Ergebnisse aufgenommen. Die Wörter müssen nicht in der gleichen Reihenfolge wie im Feld [!UICONTROL **Nach Wort oder Phrase suchen**] vorliegen.</li><li>[!UICONTROL **Enthält keinen der Begriffe**]: Nur Daten, die keines der Wörter aus der angegebenen Phrase enthalten, werden in die gefilterten Ergebnisse aufgenommen. </li><li>[!UICONTROL **Enthält nicht die Phrase**]: Nur Daten, die nicht genau die angegebene Phrase enthalten, werden in die gefilterten Ergebnisse aufgenommen. Die Wörter müssen in der Reihenfolge vorliegen, die im Feld [!UICONTROL **Nach Wort oder Phrase suchen**] angegeben ist.</li><li>[!UICONTROL **Gleich**]: Es werden nur Daten in die gefilterten Ergebnisse aufgenommen, die genau mit der von Ihnen angegebenen Wortgruppe übereinstimmen. </li><li>[!UICONTROL **Ist nicht gleich**]: Nur Daten, die nicht genau mit der angegebenen Phrase übereinstimmen, werden in die gefilterten Ergebnisse aufgenommen. </li><li>[!UICONTROL **Beginnt mit**]: Nur Daten, die mit dem angegebenen Wort oder der angegebenen Phrase beginnen, werden in die gefilterten Ergebnisse aufgenommen. </li><li>[!UICONTROL **Endet mit**]: Nur Daten, die mit dem angegebenen Wort oder der angegebenen Phrase enden, werden in die gefilterten Ergebnisse aufgenommen. </li></ul>Wählen Sie ![Add](/help/assets/icons/Add.svg) [!UICONTROL **Zeile hinzufügen**] aus, um mehrere Filterkriterien hinzuzufügen. Die Option, die Sie für [!UICONTROL **Übereinstimmung**] auswählen, bestimmt **[!UICONTROL Wenn alle Kriterien erfüllt sind]** oder **[!UICONTROL Wenn ein beliebiges Kriterium erfüllt ist]**. |
   | [!UICONTROL **Elemente immer ausschließen**] | Geben Sie den Namen aller Elemente an, die Sie aus den gefilterten Daten ausschließen möchten. |

1. Wählen Sie **[!UICONTROL Anwenden]** aus, um die Daten zu filtern. Wählen Sie **[!UICONTROL Löschen]** aus, um alle Eingaben zu löschen. Wählen Sie **[!UICONTROL Abbrechen]** aus, um den Vorgang abzubrechen und das Dialogfeld zu schließen. <br/>Ein farbiges ![Filter](/help/assets/icons/FilterColored.svg) **Filtersymbol** weist auf Details hin und zeigt diese an, wenn ein Filter auf die Tabelle angewendet wird.

### Filterkriterien in Trend-Daten in Sparklines und Linienvisualisierungen einschließen {#include-filter-criteria}

Alle Suchfilterkriterien, die auf die Tabellendimension auf eine Freiformtabelle angewendet werden, sind immer in Sparklines enthalten.

Zusätzlich zu Sparklines können Sie Filterkriterien konfigurieren, die in Visualisierungen verbundener Zeilen enthalten sind. (Filterkriterien sind standardmäßig nicht in Linienvisualisierungen enthalten. Linienvisualisierungen zeigen Daten für die Zeile an, die in der verbundenen Tabelle ausgewählt ist. Wenn keine Zeile ausgewählt ist, werden nur Daten für die erste Dimension der verbundenen Tabelle angezeigt.)

Weitere Informationen zu Sparklines und Linienvisualisierungen finden Sie unter [Anzeigen von Trend-Daten für eine Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md).

#### Konfigurieren von Linienvisualisierungen, um Filterkriterien einzuschließen

1. Wählen Sie die Sparkline in der Spaltenüberschrift Metrik aus.

   Wenn die Sparkline-Zelle ausgewählt ist, wird sie dunkelgrau angezeigt. Dies zeigt an, dass Filterkriterien in der Visualisierung der verbundenen Linien enthalten sind. Die Filterkriterien werden als Segment auf die Spalte angewendet. <!--show how to see it? Show what the segment looks like when it's applied? -->

   ![Sparkline ausgewählt](assets/table-sparkline-selected.png)

#### Verstehen, wann Spaltensummen möglicherweise ungenau sind

Spaltensummen sind in den folgenden Szenarien möglicherweise nicht exakt:

* Wenn statische Komponenten in der linken Spalte verwendet werden und [Spaltensummen als Summe der Zeilen berechnet werden](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)

  Wenn Zeilenelemente in diesem Szenario überlappende Daten enthalten, sind die Spaltensummen ungenau.

  Wenn Sie beispielsweise der linken Spalte statische Segmente hinzufügen und in der rechten Spalte Benutzer als Metrik hinzufügen, können einige dieser Benutzer Teil von mehr als einem der statischen Segmente sein. In diesem Fall dedupliziert Workspace die Benutzenden nicht für jedes statische Segment. Dies kann zu einer höheren Anzahl an Gesamtbenutzenden führen, da einige Benutzende möglicherweise mehrmals gezählt werden.

* Bei Verwendung von Dimensionen mit mehreren Werten

>[!NOTE]
>
>Das Sparkline- und Liniendiagramm spiegelt weiterhin die genauen Gesamtwerte in diesen Szenarien wider.

### Verwenden von Zielgruppensegmenten

Weitere Informationen finden [ unter ](/help/components/segments/seg-overview.md)Segmentierung - Übersicht“.

## Sortieren von Tabellen

Sie können die Daten einer Freiformtabelle nach jeder Spalte in Analysis Workspace sortieren, die entweder eine Dimension oder eine Metrik ist. Ein Pfeil gibt an, wie die Daten sortiert werden (**↓** für absteigend oder **↑** für aufsteigend).

![Sortieren](assets/sorting.gif)
