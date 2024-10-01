---
description: Erfahren Sie, wie Sie einem Projekt in Analysis Workspace Komponenten hinzufügen.
title: Verwenden von Komponenten in Analysis Workspace
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 7%

---

# Verwenden von Komponenten in Analysis Workspace

Komponenten bilden die tatsächlichen Daten eines Projekts in Analysis Workspace. Komponenten bestehen aus Dimensionen, Metriken, Filtern und Datumsbereichen. Sie können einem Projekt Komponenten hinzufügen, indem Sie sie in Visualisierungen oder Bedienfelder ziehen.

Weitere Informationen zu den Komponententypen, die Sie hinzufügen können, finden Sie in der [Komponentenübersicht](/help/components/overview.md) .

>[!TIP]
>
>Wählen Sie für Informationen zu den einzelnen Komponenten das Symbol ![InfoOutline](/help/assets/icons/InfoOutline.svg) neben dem Namen der Komponente aus.

## Komponenten zu einem Projekt hinzufügen

1. [Erstellen Sie ein Projekt in Analysis Workspace](/help/analysis-workspace/build-workspace-project/create-projects.md).

1. [Fügen Sie dem Projekt in Analysis Workspace ein Bedienfeld ](/help/analysis-workspace/c-panels/panels.md#create-a-panel) oder [ hinzu, um eine Visualisierung](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) hinzuzufügen. Wenn Sie eine Komponente zu einem leeren Projekt hinzufügen, wurde bereits eine Freiformtabellenvisualisierung erstellt.

1. Wählen Sie ![Kuratieren](/help/assets/icons/Curate.svg) **[!UICONTROL Komponenten]** aus dem Schaltflächenbedienfeld. Im linken Bereich werden alle verfügbaren Komponenten angezeigt. Weitere Informationen finden Sie unter [Schnittstelle](/help/analysis-workspace/home.md#interface) .

1. Scrollen Sie zu der Komponente, die Sie hinzufügen möchten, oder suchen Sie sie und ziehen Sie sie in ein Bedienfeld oder eine Visualisierung innerhalb Ihres Projekts.

1. Sie können eine Komponente optional in die Dropzone des Filters in eine Bedienfeldüberschrift ziehen. Durch diese Drag &amp; Drop-Funktion wird die Komponente als Filter definiert und der Filter auf alle Inhalte im Bereich angewendet.
Informationen dazu, wie Sie die Filter-Dropzone in einem Bedienfeld verwenden können, um Ihr Bedienfeld zu filtern, finden Sie unter [Dropzone](/help/analysis-workspace/c-panels/panels.md#drop-zone) in [Übersicht über Bedienfelder](/help/analysis-workspace/c-panels/panels.md).

1. Weitere Informationen finden Sie in den folgenden Abschnitten:

   * [Dimensionen zu einem Projekt hinzufügen](#add-dimensions-to-a-project)

   * [Hinzufügen von Metriken zu einem Projekt](#add-metrics-to-a-project)

   * [Filter zu einem Projekt hinzufügen](#add-filters-to-a-project)

   * [Hinzufügen von Datumsbereichen zu einem Projekt](#add-date-ranges-to-a-project)

### Dimensionen zu einem Projekt hinzufügen

[Dimensionen](/help/components/dimensions/overview.md) sind Variablen im Customer Journey Analytics, die normalerweise Zeichenfolgenwerte enthalten. Im Gegensatz dazu enthalten [Metriken](/help/components/calc-metrics/calc-metr-overview.md) numerische Werte, die mit einer Dimension verknüpft sind. Ein Basisbericht zeigt Zeilen mit Zeichenfolgenwerten (Dimension) gegen eine Spalte mit numerischen Werten (Metrik) an.

1. Beginnen Sie mit dem Hinzufügen einer Dimension zu Ihrem Projekt in Analysis Workspace, wie unter [Hinzufügen von Komponenten zu einem Projekt](#add-components-to-a-project) beschrieben.

1. Wählen Sie eine der folgenden Methoden, um Dimensionen hinzuzufügen und den Datentyp zu bestimmen, den Sie analysieren möchten:

   ![Dimension hinzufügen](/help/components/assets/add-dimension.gif)

   * Ziehen Sie eine Dimension in eine Visualisierung (z. B. eine Freiformtabelle) in Analysis Workspace.

   * Ziehen Sie eine oder mehrere Dimensionen aus dem linken Bereich in die Dropzone des Filters, um einen Schnellfilter zu erstellen, wie unter [Filter zu einem Projekt hinzufügen](#add-filters-to-a-project) beschrieben.

1. Sie können Dimensionen und Dimensionselemente in Analysis Workspace optional mit anderen Komponenten aufschlüsseln. Weitere Informationen finden Sie unter [Aufschlüsseln von Dimensionen in Workspace](/help/components/dimensions/t-breakdown-fa.md).

Weitere Informationen zur Verwendung von Dimensionen in Analysis Workspace finden Sie unter [Dimensionen in der Vorschau anzeigen](/help/components/dimensions/view-dimensions.md), [Dimensionen aufschlüsseln](/help/components/dimensions/t-breakdown-fa.md) und [Dimensionen für die Zeitunterteilung](/help/components/dimensions/time-parting-dimensions.md).

### Hinzufügen von Metriken zu einem Projekt

Mit Metriken können Sie Datenpunkte in Analysis Workspace quantifizieren. Sie werden meist als Spalten in einer Visualisierung verwendet und sind an Dimensionen gebunden.

So fügen Sie einem Projekt in Analysis Workspace eine Metrik hinzu:

1. Beginnen Sie mit dem Hinzufügen einer Metrik zu Ihrem Projekt in Analysis Workspace, wie unter [Komponenten zu einem Projekt hinzufügen](#add-components-to-a-project) beschrieben.



1. Wählen Sie eine der folgenden Methoden, um eine Metrik in Analysis Workspace hinzuzufügen:

   ![Hinzufügen einer Metrik](/help/components/assets/add-metric.gif)

   * Ziehen Sie eine Metrik in den Ablagebereich der Metrik in einer leeren Freiformtabelle, um die Trendansicht dieser Metrik über den Datumsbereich des Projekts anzuzeigen.

   * Ziehen Sie eine Metrik, wenn eine Dimension vorhanden ist, um diese Metrik für jedes Dimensionselement anzuzeigen.

   * Ziehen Sie eine Metrik auf eine vorhandene Metrik-Kopfzeile, um sie zu ersetzen.

   * Ziehen Sie eine Metrik neben die rechte Seite einer vorhandenen Metrik-Kopfzeile, um die neue Metrik hinzuzufügen.

   * Ziehen Sie eine Metrik über oder unter eine vorhandene Metrik-Kopfzeile, um eine Metriküberlappung zu erstellen.


Weitere Informationen zu Metriken finden Sie unter [Metriken](/help/components/apply-create-metrics.md).

### Filter zu einem Projekt hinzufügen

[Filter](/help/components/filters/filters-overview.md) ermöglichen es Ihnen, Untergruppen von Personen, Sitzungen oder Ereignissen anhand von Merkmalen oder spezifischen Interaktionen zu identifizieren.

Sie können Filter in Analysis Workspace auf eine der folgenden Arten verwenden:

* Filter zu einem Bedienfeld hinzufügen
Wenn Sie einem Bereich Filter hinzufügen, werden die Filter auf alle Inhalte im Bereich angewendet.
Informationen dazu, wie Sie die Filter-Dropzone in einem Bedienfeld verwenden können, um Ihr Bedienfeld zu filtern, finden Sie unter [Dropzone](/help/analysis-workspace/c-panels/panels.md#drop-zone) in [Übersicht über Bedienfelder](/help/analysis-workspace/c-panels/panels.md).

* Filter zu einer Visualisierung hinzufügen
Wenn Sie einer Spalte in einer Freiformtabelle Filter hinzufügen, werden die Filter auf alle Inhalte in der Tabellenspalte angewendet. Sie können Filter auch als Teil einer Fallout-Visualisierung hinzufügen.

* Verwenden von Filtern in Komponenten
Wenn Sie Komponenten wie [berechnete Metriken](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md), [Anmerkungen](/help/components/annotations/create-annotations.md#annotation-builder) oder sogar [Filter](/help/components/filters/filter-builder.md) definieren, können Sie Filter als Teil der Definition verwenden.


### Hinzufügen von Datumsbereichen zu einem Projekt

[Datumsbereiche](/help/components/date-ranges/overview.md) bestimmen den Berichtszeitrahmen in Analysis Workspace und können auf einen oder mehrere Bereiche innerhalb eines Projekts sowie auf einige Visualisierungen (wie die Freiformtabelle) angewendet werden.

Jedes Bedienfeld enthält standardmäßig einen Datumsbereich. Es gibt mehrere Möglichkeiten, einen Datumsbereich für ein Bedienfeld zu aktualisieren. Eine Möglichkeit, einen Datumsbereich für ein Bedienfeld in Analysis Workspace zu aktualisieren, besteht darin, eine Datumsbereichskomponente aus dem linken Bedienfeld zu ziehen:

1. Fügen Sie optional einen Datumsbereich zu Ihrem Projekt in Analysis Workspace hinzu, wie unter [Komponenten zu einem Projekt hinzufügen](#add-components-to-a-project) beschrieben.

1. Ziehen Sie einen Datumsbereich aus dem linken Bereich in den Bereich:

   * Der aktuelle Datumsbereich, um den Datumsbereich für das Bedienfeld zu ändern.

     ![Einen Datumsbereich ablegen](assets/add-date-range.gif)

   * Eine Metrik oder Dimension in einer Freiformtabellenvisualisierung. Weitere Informationen finden Sie unter [Verwenden von Datenbereichen](/help/components/date-ranges/overview.md#use-date-ranges) .

Weitere Informationen zur Verwendung und Verwaltung von Datumsbereichen in Analysis Workspace finden Sie unter [Übersicht über Datumsbereiche](/help/components/date-ranges/overview.md).

## Komponenteninformationen

Sie können den Mauszeiger über eine beliebige Komponente bewegen, um ![Mehr Infos](/help/assets/icons/InfoOutline.svg) anzuzeigen. Wenn diese Option aktiviert ist, wird ein Popup mit zusätzlichen Informationen zur Komponente angezeigt.

![Komponenteninfo](assets/component-info.png)

Je nach Zugriffssteuerung haben Sie folgende Möglichkeiten:

* Rufen Sie die Definition ![Lesezeichen](/help/assets/icons/Bookmark.svg) [!UICONTROL Datenwörterbuch] für die Komponente auf.
* Rufen Sie den Komponenten-Builder ![Bearbeiten](/help/assets/icons/Edit.svg) oder die Datenansicht auf, in der die Komponente definiert ist.
