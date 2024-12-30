---
description: Dokumentation, in der beschrieben wird, wie Tabellen in Analysis Workspace gefiltert und sortiert werden.
title: Filtern und Sortieren von Tabellen
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
role: User
source-git-commit: 590a3ddbe988d27341fe96a3fa866960d1641e24
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 42%

---

# Filtern und Sortieren von Freiformtabellen

Freiformtabellen in Analysis Workspace bilden die Grundlage für die interaktive Datenanalyse. Daher können sie Tausende von Informationszeilen enthalten. Das Filtern und Sortieren der Daten kann ein wichtiger Teil der effizienten Aufdeckung der wichtigsten Informationen sein.

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## Filtern von Tabellen

Mit Filtern in Analysis Workspace können Sie die wichtigsten Informationen aufdecken.

>[!NOTE]
>
> Nur dynamische Dimensionselemente können gefiltert werden, wie in diesem Abschnitt beschrieben. Statische Dimensionselemente können nicht gefiltert werden. Weitere Informationen finden Sie unter [Dynamische und statische Dimensionselemente in Freiformtabellen](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

Sie können mehrere Methoden verwenden, um Zeilen aus einer Freiformtabelle zu filtern.

- Ausschließen bestimmter Zeilen aus einer Tabelle
- Anwenden von Filtern auf Tabellen
- Zielgruppenfilter verwenden

Sehen Sie sich unbedingt an, wie sich die einzelnen Methoden auf [Gesamtwerte von Freiformtabellen](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md) auswirken.

### Ausschließen bestimmter Zeilen aus einer Tabelle

Sie können bestimmte Zeilen schnell aus der Tabelle ausschließen, ohne dass Sie &quot;![&quot; ](/help/assets/icons/Filter.svg) &quot;**[!UICONTROL &quot;]** müssen.

>[!NOTE]
>
>Wenn Sie Zeilen ausschließen, wie in diesem Abschnitt beschrieben[!UICONTROL  wird im Filterdialogfeld [!UICONTROL Erweitert] automatisch eine Regel „Elemente immer ausschließen] hinzugefügt. Sie können die angewendete Regel anzeigen, indem Sie auf das Symbol ![Filter](/help/assets/icons/Filter.svg) Filter und dann auf [**[!UICONTROL Erweitert anzeigen]**](#apply-a-simple-or-advanced-filter-to-a-table) klicken.

So schließen Sie bestimmte Zeilen aus einer Freiformtabelle aus:

1. Bewegen Sie den Mauszeiger über die Zeile, die Sie ausschließen möchten, und klicken Sie dann auf ![Schließen](/help/assets/icons/Close.svg).

   Halten Sie die ***Umschalt*** gedrückt, um einen Zeilenbereich auszuwählen, oder halten Sie die ***cmd***-Taste (in Mac) oder die ***Strg***-Taste (in Windows) gedrückt, um mehrere Zeilen auszuwählen.

<!--### Right-click > Delete selected rows

Note: this option does not seem to work. AN-338422

1. Select 1 or more rows. 
1. Right-click and select **[!UICONTROL Delete Selected Rows]**. 

   This action will remove the rows from the table and apply a table filter.-->


### Anwenden eines einfachen oder erweiterten Filters auf eine Tabelle

So filtern Sie Daten in Freiformtabellen:

1. Bewegen Sie den Mauszeiger über die Spalte, die die Daten enthält, die Sie filtern möchten. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Wählen Sie ![Filter](/help/assets/icons/Filter.svg) **Filter** aus, wenn es angezeigt wird.

   ![Freiformtabelle mit hervorgehobenem Filtersymbol.](assets/table-filter-icon.png)

   Die folgenden Optionen sind im Dialogfeld **[!UICONTROL Suche]** verfügbar:

   ![Einfach filtern](assets/filter-simple.png){width="500"}

   | Option | Funktion |
   |---------|----------|
   | [!UICONTROL **Einschließen von „Kein Wert“**] | Wählen Sie diese Option aus, um eine Zeile **[!UICONTROL Kein Wert]** in der Tabelle für Daten anzuzeigen, die für die ausgewählte Dimension keinen Wert hat. Deaktivieren Sie diese Option, um die Zeile **[!UICONTROL Kein Wert]** auszublenden. |
   | [!UICONTROL **Nach Wort oder Phrase suchen**] | Geben Sie ein Wort oder eine Phrase an, nach dem bzw. der Sie filtern möchten. Es werden nur Zeilen angezeigt, die das Wort oder die exakte Phrase enthalten. |


1. (Optional) Um nach verschiedenen Kriterien oder nach mehreren Kriterien zu filtern, wählen Sie [!UICONTROL **Erweiterte Einstellungen anzeigen**] aus.

   Die folgenden erweiterten Filteroptionen sind verfügbar:

   ![Filter einfach](assets/filter-advanced.png){width=500}

   | Option | Funktion |
   |---------|----------|
   | [!UICONTROL **Einschließen von „Kein Wert“**] | Wählen Sie diese Option aus, um eine Zeile **[!UICONTROL Kein Wert]** in der Tabelle für Daten anzuzeigen, die für die ausgewählte Dimension keinen Wert hat. Deaktivieren Sie diese Option, um die Zeile **[!UICONTROL Kein Wert]** auszublenden. |
   | [!UICONTROL **Übereinstimmung**] | Wählen Sie [!UICONTROL **Wenn alle Kriterien erfüllt sind**] aus, um nur Daten anzuzeigen, die alle angegebenen Kriterien erfüllen. Diese Option führt normalerweise zu verfeinerten Daten.<br/><br/>Wählen Sie [!UICONTROL **Wenn ein Kriterium erfüllt ist**] aus, um Daten anzuzeigen, die eines der angegebenen Filterkriterien erfüllen. Diese Option führt normalerweise zu weniger verfeinerten Daten. |
   | [!UICONTROL **Kriterien**] | Wählen Sie aus den folgenden Filteroptionen aus:<br/><ul><li>[!UICONTROL **Enthält die Phrase**] (Standard): Nur Daten, die die angegebene Phrase enthalten, werden in die gefilterten Ergebnisse aufgenommen. Die Wörter müssen in der Reihenfolge vorliegen, die im Feld [!UICONTROL **Nach Wort oder Phrase suchen**] angegeben ist.</li><li>[!UICONTROL **Enthält einen der Begriffe**]: Nur Daten, die ein oder mehrere Wörter aus der angegebenen Phrase enthalten, werden in die gefilterten Ergebnisse aufgenommen. </li><li>[!UICONTROL **Enthält alle Begriffe**]: Nur Daten, die alle Wörter aus der angegebenen Phrase enthalten, werden in die gefilterten Ergebnisse aufgenommen. Die Wörter müssen nicht in der gleichen Reihenfolge wie im Feld [!UICONTROL **Nach Wort oder Phrase suchen**] vorliegen.</li><li>[!UICONTROL **Enthält keinen der Begriffe**]: Nur Daten, die keines der Wörter aus der angegebenen Phrase enthalten, werden in die gefilterten Ergebnisse aufgenommen. </li><li>[!UICONTROL **Enthält nicht die Phrase**]: Nur Daten, die nicht genau die angegebene Phrase enthalten, werden in die gefilterten Ergebnisse aufgenommen. Die Wörter müssen in der Reihenfolge vorliegen, die im Feld [!UICONTROL **Nach Wort oder Phrase suchen**] angegeben ist.</li><li>[!UICONTROL **Gleich**]: Nur Daten, die genau mit der angegebenen Phrase übereinstimmen, werden in die gefilterten Ergebnisse aufgenommen. </li><li>[!UICONTROL **Ist nicht gleich**]: Nur Daten, die nicht genau mit der angegebenen Phrase übereinstimmen, werden in die gefilterten Ergebnisse aufgenommen. </li><li>[!UICONTROL **Beginnt mit**]: Nur Daten, die mit dem angegebenen Wort oder der angegebenen Phrase beginnen, werden in die gefilterten Ergebnisse aufgenommen. </li><li>[!UICONTROL **Endet mit**]: Nur Daten, die mit dem angegebenen Wort oder der angegebenen Phrase enden, werden in die gefilterten Ergebnisse aufgenommen. </li></ul>Wählen Sie ![Hinzufügen](/help/assets/icons/Add.svg) [!UICONTROL **Zeile hinzufügen**] aus, um mehrere Filterkriterien hinzuzufügen. Die Option, die Sie für [!UICONTROL **Übereinstimmung**] auswählen, bestimmt **[!UICONTROL Wenn alle Kriterien erfüllt sind]** oder **[!UICONTROL Wenn beliebige Kriterien erfüllt sind]**. |
   | [!UICONTROL **Elemente immer ausschließen**] | Geben Sie den Namen aller Elemente an, die Sie aus den gefilterten Daten ausschließen möchten. |

1. Wählen **[!UICONTROL Anwenden]**, um die Daten zu filtern. Wählen Sie **[!UICONTROL Löschen]**, um alle Eingaben zu löschen. Wählen Sie **[!UICONTROL Abbrechen]**, um den Vorgang abzubrechen und das Dialogfeld zu schließen. <br/>Ein farbiges Symbol ![Filter](/help/assets/icons/FilterColored.svg) **Filter** zeigt Details an, wenn ein Filter auf die Tabelle angewendet wird.

### Zielgruppenfilter verwenden

Siehe [Filter - Übersicht](/help/components/filters/filters-overview.md) für weitere Details.

## Sortieren von Tabellen

Sie können die Daten einer Freiformtabelle nach einer beliebigen Spalte in Analysis Workspace sortieren, die entweder eine Dimension oder eine Metrik ist. Ein Pfeil gibt an, wie die Daten sortiert werden (**↓** für absteigend oder **↑** für aufsteigend).

![Sortieren](assets/sorting.gif)
