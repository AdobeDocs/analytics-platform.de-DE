---
description: Erfahren Sie, wie Sie einem Projekt in Analysis Workspace Komponenten hinzufügen.
title: Verwenden von Komponenten in Analysis Workspace
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: 697503bba56f44159df7a2f6a0e60a0a4178266d
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 16%

---

# Verwenden von Komponenten in Analysis Workspace

Komponenten bilden die tatsächlichen Daten eines Projekts in Analysis Workspace. Komponenten bestehen aus Dimensionen, Metriken, Filtern und Datumsbereichen. Sie können einem Projekt Komponenten hinzufügen, indem Sie sie in Visualisierungen oder Bedienfelder ziehen.

Eine Übersicht über die Komponententypen, die Sie hinzufügen können, finden Sie unter [Komponentenübersicht](/help/components/overview.md).

>[!TIP]
>
>Informationen zu den einzelnen Komponenten erhalten Sie, wenn Sie in der linken Leiste von Analysis Workspace auf das Infosymbol neben dem Namen einer Komponente klicken.

## Hinzufügen von Komponenten zu einem Projekt beginnen

1. [Erstellen eines Projekts in Analysis Workspace](/help/analysis-workspace/build-workspace-project/create-projects.md) wenn Sie es noch nicht getan haben.

1. [Bedienfeld hinzufügen](/help/analysis-workspace/c-panels/panels.md) oder [Visualisierung hinzufügen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) zum Projekt in Analysis Workspace.

   Wenn Sie eine Komponente zu einem leeren Projekt hinzufügen, wird automatisch eine Freiformtabellenvisualisierung erstellt.

1. Wählen Sie in der linken Leiste das Symbol **[!UICONTROL Komponenten]** aus.

   ![](assets/build-components.png)

1. Scrollen Sie zu der Komponente, die Sie hinzufügen möchten, oder suchen Sie sie und ziehen Sie sie anschließend in ein Bedienfeld oder eine Visualisierung innerhalb Ihres Projekts.

1. (Optional) Ziehen Sie eine Komponente in die Dropzone Filter in einer Bedienfeldüberschrift.

   Filter gelten für alle Inhalte im Bereich.

   Informationen dazu, wie Sie die Filter-Dropzone in einem Bedienfeld zum Filtern Ihres Bedienfelds verwenden können, finden Sie unter [Dropzone](/help/analysis-workspace/c-panels/panels.md#drop-zone) in [Bedienfelder - Übersicht](/help/analysis-workspace/c-panels/panels.md).

   ![Filter im Ablegebereich ablegen](assets/filter-dropzone.png)

1. Weitere Informationen erhalten Sie in den folgenden Abschnitten, je nach Typ der Komponente, die Sie hinzufügen:

   * [Dimensionen zu einem Projekt hinzufügen](#add-dimensions-to-a-project)

   * [Hinzufügen von Metriken zu einem Projekt](#add-metrics-to-a-project)

   * [Filter zu einem Projekt hinzufügen](#add-filters-to-a-project)

   * [Hinzufügen von Datumsbereichen zu einem Projekt](#add-date-ranges-to-a-project)

## Dimensionen zu einem Projekt hinzufügen

[Dimensionen](/help/components/dimensions/overview.md) sind Variablen in Adobe Analytics, die normalerweise Zeichenfolgenwerte enthalten. Im Gegensatz dazu enthalten [Metriken](/help/components/calc-metrics/calc-metr-overview.md) numerische Werte, die mit einer Dimension verknüpft sind. Ein Basisbericht zeigt Zeilen mit Zeichenfolgenwerten (Dimension) gegen eine Spalte mit numerischen Werten (Metrik) an.

1. Beginnen Sie mit dem Hinzufügen einer Dimension zu Ihrem Projekt in Analysis Workspace, wie beschrieben in [Hinzufügen von Komponenten zu einem Projekt beginnen](#begin-adding-components-to-a-project).

1. Wählen Sie eine der folgenden Methoden, um Dimensionen hinzuzufügen und den Datentyp zu bestimmen, den Sie analysieren möchten:

   * Ziehen Sie eine Dimension in eine Visualisierung (z. B. eine Freiformtabelle) in Analysis Workspace.

     ![Dimensionen zu einem Projekt hinzufügen](assets/add-dimensions.png)

   * Ziehen Sie eine oder mehrere Dimensionen aus der linken Leiste in die Dropzone des Filters, um einen Ad-hoc-Filter zu erstellen, wie unter [Filter zu einem Projekt hinzufügen](#add-filters-to-a-project).

1. (Optional) Sie können Dimensionen und Dimensionselemente in Analysis Workspace mit anderen Komponenten aufschlüsseln.

   Weitere Informationen finden Sie unter [Aufschlüsseln von Dimensionen in Workspace](/help/components/dimensions/t-breakdown-fa.md).

Weitere Informationen zur Verwendung von Dimensionen in Analysis Workspace finden Sie unter [Dimensionen in der Vorschau anzeigen](/help/components/dimensions/view-dimensions.md), [Dimensionen aufschlüsseln](/help/components/dimensions/t-breakdown-fa.md), und [Dimensionen für die Zeitunterteilung](/help/components/dimensions/time-parting-dimensions.md).

## Hinzufügen von Metriken zu einem Projekt

Mit Metriken können Sie Datenpunkte in Analysis Workspace quantifizieren. Sie werden meist als Spalten in einer Visualisierung verwendet und sind an Dimensionen gebunden.

So fügen Sie einem Projekt in Analysis Workspace eine Metrik hinzu:

1. Beginnen Sie mit dem Hinzufügen einer Metrik zu Ihrem Projekt in Analysis Workspace, wie unter [Hinzufügen von Komponenten zu einem Projekt beginnen](#begin-adding-components-to-a-project).

1. Wählen Sie eine der folgenden Methoden, um eine Metrik in Analysis Workspace hinzuzufügen:

   * Ziehen Sie eine Metrik in den Ablagebereich der Metrik in einer leeren Freiformtabelle, um die Trendansicht dieser Metrik über den Datumsbereich des Projekts anzuzeigen.

     ![Hinzufügen einer Metrik zu einem Projekt](assets/add-metrics.png)

   * Ziehen Sie eine Metrik, wenn eine Dimension vorhanden ist, um diese Metrik mit jedem Dimensionselement zu vergleichen.

   * Ziehen Sie eine Metrik auf eine vorhandene Metrik-Kopfzeile, um sie zu ersetzen.

   * Ziehen Sie eine Metrik neben eine Kopfzeile, um beide Metriken nebeneinander anzuzeigen.

Weitere Informationen zu Metriken finden Sie unter [Übersicht über berechnete Metriken](/help/components/calc-metrics/calc-metr-overview.md).

## Filter zu einem Projekt hinzufügen

[Filter](/help/components/filters/filters-overview.md) ermöglichen es Ihnen, Besucheruntergruppen anhand von Merkmalen oder spezifischen Interaktionen zu identifizieren.

Sie können Filter in Analysis Workspace auf eine der folgenden Arten verwenden:

### Filter zu einem Bedienfeld hinzufügen

Wenn Sie einem Bereich Filter hinzufügen, werden die Filter auf alle Inhalte im Bereich angewendet.

Informationen dazu, wie Sie die Filter-Dropzone in einem Bedienfeld zum Filtern Ihres Bedienfelds verwenden können, finden Sie unter [Dropzone](/help/analysis-workspace/c-panels/panels.md#drop-zone) in [Bedienfelder - Übersicht](/help/analysis-workspace/c-panels/panels.md).

### Filter zu einer Spalte in einer Freiformtabelle hinzufügen

Wenn Sie einer Spalte in einer Freiformtabelle Filter hinzufügen, werden die Filter auf alle Inhalte in der Tabellenspalte angewendet.

### Filter bei der Erstellung berechneter Metriken verwenden

Im Generator für berechnete Metriken können Sie Filter innerhalb Ihrer Metrikdefinition anwenden.

Weitere Informationen finden Sie unter [Gefilterte Metriken](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md).

## Hinzufügen von Datumsbereichen zu einem Projekt

[Datumsbereiche](/help/components/date-ranges/custom-date-ranges.md) den Berichtszeitrahmen in Analysis Workspace bestimmen und auf einen oder mehrere Bereiche innerhalb eines Projekts angewendet werden können.

Jedes Bedienfeld enthält standardmäßig einen Datumsbereich. Es gibt mehrere Möglichkeiten, einen Datumsbereich für ein Bedienfeld zu aktualisieren. Eine Möglichkeit, einen Datumsbereich für ein Bedienfeld in Analysis Workspace zu aktualisieren, besteht darin, eine Datumsbereichskomponente aus der linken Leiste zu ziehen:

1. Beginnen Sie mit dem Hinzufügen eines Datumsbereichs zu Ihrem Projekt in Analysis Workspace, wie beschrieben in [Hinzufügen von Komponenten zu einem Projekt beginnen](#begin-adding-components-to-a-project).

1. Ziehen Sie einen Datumsbereich aus der linken Leiste in den aktuellen Datumsbereich oben rechts im Bedienfeld.

   ![Datumsbereich ablegen](assets/daterange-drop.png)

Weitere Informationen zur Verwendung von Kalendern und Datumsbereichen in Analysis Workspace finden Sie unter [Übersicht über Kalender und Datumsbereiche](/help/components/date-ranges/custom-date-ranges.md).
