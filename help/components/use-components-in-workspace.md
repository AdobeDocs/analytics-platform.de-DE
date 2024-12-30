---
description: Erfahren Sie, wie Sie in Analysis Workspace Komponenten zu einem Projekt hinzufügen
title: Verwenden von Komponenten in Analysis Workspace
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: c56c77079aa21fb740fda6bec333731a1f82a48f
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 7%

---

# Verwenden von Komponenten in Analysis Workspace

Komponenten bilden die tatsächlichen Daten eines beliebigen Projekts in Analysis Workspace. Komponenten bestehen aus Dimensionen, Metriken, Filtern und Datumsbereichen. Sie können Komponenten zu einem Projekt hinzufügen, indem Sie sie in Visualisierungen oder Bedienfelder ziehen.

Weitere Informationen zu den [ Komponenten, ](/help/components/overview.md) Sie hinzufügen können, finden Sie unter „Komponentenübersicht“ .

>[!TIP]
>
>Informationen zu den einzelnen Komponenten finden Sie unter ![InfoOutline](/help/assets/icons/InfoOutline.svg). Siehe [Komponenteninformationen](#component-info) für weitere Informationen

## Hinzufügen von Komponenten zu einem Projekt

1. [Erstellen eines Projekts in Analysis Workspace](/help/analysis-workspace/build-workspace-project/create-projects.md).

1. [Bedienfeld hinzufügen](/help/analysis-workspace/c-panels/panels.md#create-a-panel) oder [Visualisierung hinzufügen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) zum Projekt in Analysis Workspace hinzufügen. Wenn Sie einem leeren Projekt eine Komponente hinzufügen, wird bereits eine Freiformtabellen-Visualisierung für Sie erstellt.

1. Wählen ![Kuratieren](/help/assets/icons/Curate.svg) **[!UICONTROL Komponenten]** im Schaltflächenbereich aus. Im linken Bereich werden alle verfügbaren Komponenten angezeigt. Weitere Informationen finden [ unter ](/help/analysis-workspace/home.md#interface)Benutzeroberfläche“.

1. Scrollen Sie nach der Komponente, die Sie hinzufügen möchten, oder suchen Sie sie, und ziehen Sie sie dann in ein Bedienfeld oder eine Visualisierung innerhalb Ihres Projekts.

1. Optional können Sie eine Komponente in die Ablagefläche des Filters in einer Bedienfeldkopfzeile ziehen. Diese Drag-and-Drop-Funktion definiert die Komponente als Filter und wendet den Filter auf alle Inhalte im Bedienfeld an.
Informationen dazu, wie Sie den Ablagebereich für Filter in einem Bedienfeld zum Filtern Ihres Bedienfelds verwenden können, finden Sie unter [Ablagebereich](/help/analysis-workspace/c-panels/panels.md#drop-zone) in [Bedienfelder - Übersicht](/help/analysis-workspace/c-panels/panels.md).

1. Weitere Informationen finden Sie in den folgenden Abschnitten:

   * [Hinzufügen von Dimensionen zu einem Projekt](#add-dimensions-to-a-project)

   * [Hinzufügen von Metriken zu einem Projekt](#add-metrics-to-a-project)

   * [Hinzufügen von Filtern zu einem Projekt](#add-filters-to-a-project)

   * [Hinzufügen von Datumsbereichen zu einem Projekt](#add-date-ranges-to-a-project)

### Hinzufügen von Dimensionen zu einem Projekt

[Dimensionen ](/help/components/dimensions/overview.md) sind Variablen im Customer Journey Analytics, die normalerweise Zeichenfolgenwerte enthalten. Im Gegensatz dazu enthalten [Metriken](/help/components/calc-metrics/calc-metr-overview.md) numerische Werte, die mit einer Dimension verknüpft sind. Ein Basisbericht zeigt Zeilen mit Zeichenfolgenwerten (Dimension) gegen eine Spalte mit numerischen Werten (Metrik) an.

1. Beginnen Sie, Ihrem Projekt in Analysis Workspace eine Dimension hinzuzufügen, wie in [Hinzufügen von Komponenten zu einem Projekt](#add-components-to-a-project) beschrieben.

1. Wählen Sie eine der folgenden Methoden, um Dimensionen hinzuzufügen, und bestimmen Sie den Datentyp, den Sie analysieren möchten:

   ![Dimension hinzufügen](/help/components/assets/add-dimension.gif)

   * Ziehen einer Dimension in eine Visualisierung (z. B. eine Freiformtabelle) in Analysis Workspace.

   * Ziehen Sie eine oder mehrere Dimensionen aus dem linken Bedienfeld auf den Ablagebereich für Filter, um einen Schnellfilter zu erstellen, wie in [Hinzufügen von Filtern zu einem Projekt](#add-filters-to-a-project) beschrieben.

1. Sie können Dimensionen und Dimensionselemente in Analysis Workspace optional mit anderen Komponenten aufschlüsseln. Weitere Informationen finden Sie unter [Dimensionen in Workspace aufschlüsseln](/help/components/dimensions/t-breakdown-fa.md).

Weitere Informationen zur Verwendung von Dimensionen in Analysis Workspace finden Sie unter [Vorschau von Dimensionen](/help/components/dimensions/view-dimensions.md), [Dimensionen aufschlüsseln](/help/components/dimensions/t-breakdown-fa.md) und [Dimensionen für die Zeitunterteilung](/help/components/dimensions/time-parting-dimensions.md).

### Hinzufügen von Metriken zu einem Projekt

Mit Metriken können Sie Datenpunkte in Analysis Workspace quantifizieren. Sie werden meist als Spalten in einer Visualisierung verwendet und sind an Dimensionen gebunden.

So fügen Sie einem Projekt in Analysis Workspace eine Metrik hinzu:

1. Beginnen Sie mit dem Hinzufügen einer Metrik zu Ihrem Projekt in Analysis Workspace, wie unter [Hinzufügen von Komponenten zu einem Projekt](#add-components-to-a-project) beschrieben.



1. Wählen Sie eine der folgenden Methoden, um eine Metrik in Analysis Workspace hinzuzufügen:

   ![Metrik hinzufügen](/help/components/assets/add-metric.gif)

   * Ziehen Sie eine Metrik in die Metrik-Ablagezone in einer leeren Freiformtabelle, um die Entwicklung dieser Metrik über den Datumsbereich des Projekts anzuzeigen.

   * Ziehen Sie eine Metrik, wenn eine Dimension vorhanden ist, um diese Metrik für jedes Dimensionselement anzuzeigen.

   * Ziehen Sie eine Metrik auf eine vorhandene Metrik-Kopfzeile, um sie zu ersetzen.

   * Ziehen Sie eine Metrik neben die linke oder rechte Seite einer vorhandenen Metrik-Kopfzeile, um die neue Metrik hinzuzufügen.

   * Ziehen Sie eine Metrik über oder unter eine vorhandene Metrikkopfzeile, um eine Metriküberschneidung zu erstellen.


Weitere Informationen zu Metriken finden Sie unter [Metriken](/help/components/apply-create-metrics.md).

### Hinzufügen von Filtern zu einem Projekt

[Filter](/help/components/filters/filters-overview.md) ermöglichen es Ihnen, Untergruppen von Personen, Sitzungen oder Ereignissen anhand von Merkmalen oder bestimmten Interaktionen zu identifizieren.

Sie können Filter in Analysis Workspace auf eine der folgenden Arten verwenden:

* Hinzufügen von Filtern zu einem Bedienfeld
Wenn Sie einem Bedienfeld Filter hinzufügen, gelten die Filter für alle Inhalte im Bedienfeld.
Informationen dazu, wie Sie den Ablagebereich für Filter in einem Bedienfeld zum Filtern Ihres Bedienfelds verwenden können, finden Sie unter [Ablagebereich](/help/analysis-workspace/c-panels/panels.md#drop-zone) in [Bedienfelder - Übersicht](/help/analysis-workspace/c-panels/panels.md).

* Hinzufügen von Filtern zu einer Visualisierung
Wenn Sie einer Spalte in einer Freiformtabelle Filter hinzufügen, werden die Filter auf alle Inhalte in der Tabellenspalte angewendet. Sie können auch Filter als Teil einer Fallout-Visualisierung hinzufügen.

* Verwenden von Filtern in Komponenten
Wenn Sie Komponenten wie [berechnete Metriken](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md), [Anmerkungen](/help/components/annotations/create-annotations.md#annotation-builder) oder sogar [Filter) definieren](/help/components/filters/filter-builder.md) können Sie Filter als Teil der Definition verwenden.


### Hinzufügen von Datumsbereichen zu einem Projekt

[Datumsbereiche](/help/components/date-ranges/overview.md) bestimmen den Berichtszeitrahmen in Analysis Workspace und können auf ein oder mehrere Bedienfelder innerhalb eines Projekts sowie auf einige Visualisierungen (wie die Freiformtabelle) angewendet werden.

Jedes Bedienfeld enthält standardmäßig einen Datumsbereich. Es gibt mehrere Möglichkeiten, einen Datumsbereich für ein Bedienfeld zu aktualisieren. Eine Möglichkeit, einen Datumsbereich für ein Bedienfeld in Analysis Workspace zu aktualisieren, besteht darin, eine Datumsbereichskomponente aus dem linken Bedienfeld zu ziehen:

1. Optional können Sie einen Datumsbereich zu Ihrem Projekt in Analysis Workspace hinzufügen, wie unter [Hinzufügen von Komponenten zu einem Projekt](#add-components-to-a-project) beschrieben.

1. Ziehen Sie per Drag-and-Drop einen Datumsbereich aus dem linken Panel auf:

   * Der aktuelle Datumsbereich, um den Datumsbereich für das Bedienfeld zu ändern.

     ![Einen Datumsbereich ablegen](assets/add-date-range.gif)

   * Eine Metrik oder Dimension in einer Freiformtabellenvisualisierung. Weitere Informationen [ Sie unter ](/help/components/date-ranges/overview.md#use-date-ranges) von Datumsbereichen .

Weitere Informationen zur Verwendung und Verwaltung von Datumsbereichen in Analysis Workspace finden Sie unter [Datumsbereiche - Übersicht](/help/components/date-ranges/overview.md).

## Komponenteninformationen

Sie können den Mauszeiger über eine beliebige Komponente bewegen, um &quot;![ Informationen“ ](/help/assets/icons/InfoOutline.svg). Wenn diese Option ausgewählt ist, wird ein Popup mit zusätzlichen Informationen über die Komponente angezeigt.

![Komponenteninformationen](assets/component-info.png)

Je nach Zugriffssteuerung haben Sie folgende Möglichkeiten:

* Rufen Sie die ![Lesezeichen](/help/assets/icons/Bookmark.svg)[!UICONTROL  Datenwörterbuch]-Definition für die Komponente auf.
* Greifen Sie auf ![ Komponenten](/help/assets/icons/Edit.svg)Builder oder die Datenansicht zu, in der die Komponente definiert ist.
