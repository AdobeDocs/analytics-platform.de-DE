---
description: Dokumentation, in der beschrieben wird, wie Tabellen in Analysis Workspace gefiltert und sortiert werden.
title: Filtern und Sortieren von Tabellen
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
role: User
source-git-commit: 772fa17f013ef0543027a7f60be780e9cf8f634a
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 69%

---


# Filtern und Sortieren von Freiformtabellen

Freiformtabellen in Analysis Workspace bilden die Grundlage für die interaktive Datenanalyse. Daher können sie Tausende von Informationszeilen enthalten. Das Filtern und Sortieren der Daten kann ein wichtiger Teil der effizienten Aufdeckung der wichtigsten Informationen sein.

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## Filtern von Tabellen

Mit Filtern in Analysis Workspace können Sie die wichtigsten Informationen aufdecken.

>[!NOTE]
>
> Nur dynamische Dimensionselemente können wie in diesem Abschnitt beschrieben gefiltert werden. Statische Dimensionselemente können nicht gefiltert werden. Weitere Informationen finden Sie unter [Dynamische und statische Dimensionselemente in Freiformtabellen](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

## Freiformtabellenzeilen filtern

Sie können mehrere Methoden verwenden, um Zeilen aus einer Freiformtabelle zu filtern. 

- Klicken Sie auf das X in der Zeile
- Rechtsklick > Ausgewählte Zeilen gelöscht
- Tabellenfilter
- Segmentierung

Lesen Sie unbedingt, wie sich die einzelnen Methoden auf [Gesamtwerte der Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md).

### Schnelles Ausschließen bestimmter Zeilen aus einer Tabelle

Sie können bestimmte Zeilen schnell aus der Tabelle ausschließen, ohne das Dialogfeld Filter öffnen zu müssen.

>[!NOTE]
>
>Wenn Sie Zeilen ausschließen, wie in diesem Abschnitt beschrieben, wird ein [!UICONTROL **Ausschließen von Elementen**] im Dialogfeld für erweiterte Filter automatisch angewendet wird. (Sie können die angewendete Regel anzeigen, indem Sie das Filtersymbol auswählen und dann [**[!UICONTROL Erweitert anzeigen]**](#apply-a-simple-or-advanced-filter-to-a-table).

So schließen Sie bestimmte Zeilen schnell aus einer Freiformtabelle aus:

1. Bewegen Sie den Mauszeiger über die Zeile, die Sie ausschließen möchten, und wählen Sie dann das Symbol x aus.

   Halten Sie die Umschalttaste gedrückt, um einen Zeilenbereich auszuwählen, oder halten Sie die Befehlstaste (Mac) oder die Strg-Taste (Windows) gedrückt, um mehrere Zeilen auszuwählen.

<!--### Right-click > Delete selected rows

Note: this option does not seem to work. AN-338422

1. Select 1 or more rows. 
1. Right-click and select **[!UICONTROL Delete Selected Rows]**. 

   This action will remove the rows from the table and apply a table filter.-->


### Einfache oder erweiterte Filter auf Tabellen anwenden

So filtern Sie Daten in Freiformtabellen:

1. Bewegen Sie den Mauszeiger über die Spalte, die die zu filternden Daten enthält. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Wählen Sie das **Filtersymbol** aus, wenn es angezeigt wird.

   ![Freiformtabelle, die das Symbol Filter hervorhebt.](assets/table-filter-icon.png)

   Die folgenden Optionen sind verfügbar:

   | Option | Funktion |
   |---------|----------|
   | [!UICONTROL **Suchbegriff oder -satz**] | Geben Sie ein Wort oder eine Wortgruppe an, nach dem/der Sie filtern möchten. Es werden nur Zeilen angezeigt, die das Wort oder die exakte Phrase enthalten. |
   | [!UICONTROL **Nicht spezifizierte einschließen (keine)**] | Aktivieren Sie diese Option, um Daten in der Tabelle anzuzeigen, die nicht zu einer Dimension der Tabelle gehören. <!--what is this?--> |

1. (Optional) Um nach verschiedenen Kriterien oder nach mehreren Kriterien zu filtern, wählen Sie [!UICONTROL **Erweiterte Einstellungen anzeigen**] aus.

   Die folgenden erweiterten Filteroptionen sind verfügbar:

   | Option | Funktion |
   |---------|----------|
   | [!UICONTROL **Nicht spezifizierte einschließen (keine)**] | Aktivieren Sie diese Option, um Daten in der Tabelle anzuzeigen, die nicht zu einer Dimension der Tabelle gehören. <!--what is this?--> |
   | [!UICONTROL **Übereinstimmung**] | <p>Wählen Sie [!UICONTROL **Wenn alle Kriterien erfüllt sind**] aus, um nur Daten anzuzeigen, die alle angegebenen Kriterien erfüllen. Diese Option führt normalerweise zu verfeinerten Daten.</p> <p>Wählen Sie [!UICONTROL **Wenn ein Kriterium erfüllt ist**] aus, um Daten anzuzeigen, die eines der angegebenen Filterkriterien erfüllen. Diese Option führt normalerweise zu weniger verfeinerten Daten.</p> |
   | [!UICONTROL **Kriterien**] | <p>Treffen Sie eine Auswahl aus den folgenden Filteroptionen:</p><p>(Wählen Sie [!UICONTROL **Zeile hinzufügen**] aus, um mehrere Filterkriterien hinzuzufügen. Die Option, die Sie im Abschnitt [!UICONTROL **Übereinstimmung**] auswählen, bestimmt, ob alle oder eines der hinzugefügten Kriterien erfüllt sein müssen.)</p><ul><li><p>[!UICONTROL **Enthält die Phrase**]: Nur Daten, die die von Ihnen angegebene Phrase enthalten, werden in die gefilterten Ergebnisse aufgenommen. Die Wörter müssen in der Reihenfolge vorliegen, die im Feld [!UICONTROL **Nach Wort oder Phrase suchen**] angegeben ist.<p>Dies ist die Standardeinstellung bei einer einfachen Suche.</p></p></li><li><p>[!UICONTROL **Enthält einen der Begriffe**]: Nur Daten, die ein oder mehrere Wörter aus der angegebenen Phrase enthalten, werden in die gefilterten Ergebnisse aufgenommen. </p></li><li><p>[!UICONTROL **Enthält alle Begriffe**]: Nur Daten, die alle Wörter aus der angegebenen Phrase enthalten, werden in die gefilterten Ergebnisse aufgenommen. Die Wörter müssen nicht in der gleichen Reihenfolge wie im Feld [!UICONTROL **Nach Wort oder Phrase suchen**] vorliegen.</p></li><li><p>[!UICONTROL **Enthält keinen der Begriffe**]: Nur Daten, die keines der Wörter aus der angegebenen Phrase enthalten, werden in die gefilterten Ergebnisse aufgenommen. </p></li><li><p>[!UICONTROL **Enthält nicht die Phrase**]: Nur Daten, die nicht genau die angegebene Phrase enthalten, werden in die gefilterten Ergebnisse aufgenommen. Die Wörter müssen in der Reihenfolge vorliegen, die im Feld [!UICONTROL **Nach Wort oder Phrase suchen**] angegeben ist.</p></li><li><p>[!UICONTROL **Gleich**]: Nur Daten, die genau mit der angegebenen Phrase übereinstimmen, werden in die gefilterten Ergebnisse aufgenommen. </p></li><li><p>[!UICONTROL **Ist nicht gleich**]: Nur Daten, die nicht genau mit der angegebenen Phrase übereinstimmen, werden in die gefilterten Ergebnisse aufgenommen. </p></li><li><p>[!UICONTROL **Beginnt mit**]: Nur Daten, die mit dem angegebenen Wort oder der angegebenen Phrase beginnen, werden in die gefilterten Ergebnisse aufgenommen. </p></li><li><p>[!UICONTROL **Endet mit**]: Nur Daten, die mit dem angegebenen Wort oder der angegebenen Phrase enden, werden in die gefilterten Ergebnisse aufgenommen. </p></li></ul> |
   | [!UICONTROL **Elemente immer ausschließen**] | Geben Sie den Namen aller Elemente an, die Sie aus den gefilterten Daten ausschließen möchten. |

1. Wählen Sie [!UICONTROL **Anwenden**] aus, um die Daten zu filtern.

   Das **Filtersymbol** ![Blaues Filtersymbol zur Filterung der Tabelle](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) wird angezeigt, wenn ein Filter auf die Tabelle angewendet wird.

### Filter

Siehe unsere [Filterdokumentation](/help/components/filters/filters-overview.md) für weitere Details.

## Sortieren von Tabellen

Sie können die Daten einer Freiformtabelle nach jeder Spalte in Analysis Workspace sortieren, die entweder eine Dimension oder eine Metrik ist.

Ein Pfeil-nach-unten-Symbol ![Pfeil nach unten zur Sortierung einer Tabellenspalte](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) ist in der Kopfzeile der Spalte sichtbar, nach der die Daten derzeit sortiert werden.

1. Klicken Sie in einer beliebigen Freiformtabelle in Analysis Workspace auf den Pfeil neben dem Namen der Dimension oder Metrik.

   Beachten Sie beim Sortieren Folgendes:

   - Der Nach-unten-Pfeil sortiert in absteigender Reihenfolge und der Nach-oben-Pfeil (Standard) in aufsteigender Reihenfolge.
   - Sie können Dimensionen alphabetisch oder numerisch sortieren. Beispielsweise können Sie in einem Workflow nummerierte Schritte verwenden und nach der Schrittnummer sortieren. Eine datumsbezogene Dimension kann nach Datum sortiert werden. Oder Sie können, wie in der folgenden Abbildung, Datenquellen alphabetisch sortieren.

   ![Data Sources-Ansicht, die das Sortiersymbol hervorhebt.](assets/sort-dimensions.png)


