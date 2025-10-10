---
description: Erfahren Sie, wie Sie Komponenten in einem Projekt in Analysis Workspace verwenden.
title: Verwenden von Komponenten in einem Projekt
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 100%

---

# Verwenden von Komponenten in einem Projekt

Komponenten bilden die eigentlichen Daten eines jeden Projekts in Analysis Workspace. Komponenten bestehen aus Dimensionen, Metriken, Segmenten und Datumsbereichen. Sie können Komponenten zu einem Projekt hinzufügen, indem Sie sie in Visualisierungen oder Panels ziehen.

Weitere Informationen zu den Typen von Komponenten, die Sie hinzufügen können, finden Sie unter [Komponentenübersicht](/help/components/overview.md).

>[!TIP]
>
>Um Informationen zu den einzelnen Komponenten abzurufen, verwenden Sie ![Information](/help/assets/icons/InfoOutline.svg). Weitere Informationen finden Sie unter [Informationen zu Komponenten](#component-info).

## Hinzufügen von Komponenten zu einem Projekt

1. [Erstellen Sie ein Projekt in Analysis Workspace](/help/analysis-workspace/build-workspace-project/create-projects.md).

1. Fügen Sie [ein Panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel) oder [eine Visualisierung](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) zum Projekt in Analysis Workspace hinzu. Wenn Sie einem leeren Projekt eine Komponente hinzufügen, wird bereits eine Visualisierung vom Typ „Freiformtabelle“ für Sie erstellt.

1. Wählen Sie ![Kuratieren](/help/assets/icons/Curate.svg) **[!UICONTROL Komponenten]** im Schaltflächen-Panel aus. Im linken Panel werden alle verfügbaren Komponenten angezeigt. Weitere Informationen finden Sie unter [Benutzeroberfläche](/help/analysis-workspace/home.md#interface).

1. Scrollen Sie zu oder suchen Sie nach der Komponente, die hinzugefügt werden soll, und ziehen Sie sie anschließend in ein Panel oder eine Visualisierung innerhalb Ihres Projekts.

1. Sie können eine Komponente auch in den Segment-Ablegebereich in der Kopfzeile eines Panels ziehen. Dieser Drag-and-Drop-Vorgang definiert die Komponente als Segment und wendet das Segment auf alle Inhalte im Panel an.
Informationen zum Verwenden des Segment-Ablegebereichs in einem Panel, um das Panel zu segmentieren, finden Sie im [Überblick über Panels](/help/analysis-workspace/c-panels/panels.md) unter [Ablegebereich](/help/analysis-workspace/c-panels/panels.md#drop-zone).

1. Weitere Informationen finden Sie in den folgenden Abschnitten:

   * [Hinzufügen von Dimensionen zu einem Projekt](#add-dimensions-to-a-project)

   * [Hinzufügen von Metriken zu einem Projekt](#add-metrics-to-a-project)

   * [Hinzufügen von Segmenten zu einem Projekt](#add-segments-to-a-project)

   * [Hinzufügen von Datumsbereichen zu einem Projekt](#add-date-ranges-to-a-project)

### Hinzufügen von Dimensionen zu einem Projekt

[Dimensionen](/help/components/dimensions/overview.md) sind Variablen in Customer Journey Analytics, die normalerweise Zeichenfolgenwerte enthalten. Im Gegensatz dazu enthalten [Metriken](/help/components/calc-metrics/calc-metr-overview.md) numerische Werte, die mit einer Dimension verknüpft sind. Ein Basisbericht zeigt Zeilen mit Zeichenfolgenwerten (Dimension) gegen eine Spalte mit numerischen Werten (Metrik) an.

1. Fügen Sie zunächst eine Dimension zu Ihrem Projekt in Analysis Workspace hinzu, wie unter [Hinzufügen von Komponenten zu einem Projekt](#add-components-to-a-project) beschrieben. 

1. Wählen Sie eine der folgenden Methoden, um Dimensionen hinzuzufügen, und bestimmen Sie den Datentyp, der analysiert werden soll:

   ![Hinzufügen einer Dimension](/help/components/assets/add-dimension.gif)

   * Ziehen Sie eine Dimension in eine Visualisierung (z. B. eine Freiformtabelle) in Analysis Workspace.

   * Ziehen Sie eine oder mehrere Dimensionen aus dem linken Panel in den Segment-Ablegebereich, um ein Schnellsegment zu erstellen, wie unter [Hinzufügen von Segmenten zu einem Projekt](#add-filters-to-a-project) beschrieben.

1. Sie können Dimensionen und Dimensionselemente in Analysis Workspace optional mit anderen Komponenten aufschlüsseln. Weitere Informationen finden Sie unter [Aufschlüsseln von Dimensionen in Workspace](/help/components/dimensions/t-breakdown-fa.md).

Weitere Informationen zum Verwenden von Dimensionen in Analysis Workspace finden Sie unter [Vorschau von Dimensionen](/help/components/dimensions/view-dimensions.md), [Aufschlüsseln von Dimensionen](/help/components/dimensions/t-breakdown-fa.md) und [Zeitteilungsdimensionen](/help/components/dimensions/time-parting-dimensions.md).

### Hinzufügen von Metriken zu einem Projekt

Mit Metriken können Sie Datenpunkte in Analysis Workspace quantifizieren. Sie werden meist als Spalten in einer Visualisierung verwendet und sind an Dimensionen gebunden.

So fügen Sie einem Projekt in Analysis Workspace eine Metrik hinzu:

1. Fügen Sie zunächst eine Metrik zu Ihrem Projekt in Analysis Workspace hinzu, wie unter [Hinzufügen von Komponenten zu einem Projekt](#add-components-to-a-project) beschrieben. 



1. Wählen Sie eine der folgenden Methoden, um eine Metrik in Analysis Workspace hinzuzufügen:

   ![Hinzufügen einer Metrik](/help/components/assets/add-metric.gif)

   * Ziehen Sie eine Metrik in den Metrik-Ablegebereich einer leeren Freiformtabelle, um die Trend-Ansicht dieser Metrik über den Datumsbereich des Projekts anzuzeigen.

   * Ziehen Sie eine Metrik, wenn eine Dimension vorhanden ist, um diese Metrik für jedes Dimensionselement anzuzeigen.

   * Ziehen Sie eine Metrik auf eine vorhandene Metrik-Kopfzeile, um sie zu ersetzen.

   * Ziehen Sie eine Metrik neben die linke oder rechte Seite einer vorhandenen Metrik-Kopfzeile, um die neue Metrik hinzuzufügen.

   * Ziehen Sie eine Metrik über oder unter eine vorhandene Metrik-Kopfzeile, um eine Metrik-Überschneidung zu erstellen.


Weitere Informationen zu Metriken finden Sie unter [Metriken](/help/components/apply-create-metrics.md).

### Hinzufügen von Segmenten zu einem Projekt

Mit [Segmenten](/help/components/segments/seg-overview.md) können Sie Teilmengen von Personen, Sitzungen oder Ereignissen anhand von Merkmalen oder bestimmten Interaktionen identifizieren.

Sie können Segmente in Analysis Workspace auf eine der folgenden Arten verwenden:

* Segmente zu einem Panel hinzufügen
Wenn Sie Segmente zu einem Panel hinzufügen, gelten die Segmente für alle Inhalte im Panel.
Informationen zum Verwenden des Segment-Ablegebereichs in einem Panel, um das Panel zu segmentieren, finden Sie im [Überblick über Panels](/help/analysis-workspace/c-panels/panels.md) unter [Ablegebereich](/help/analysis-workspace/c-panels/panels.md#drop-zone).

* Segmente zu einer Visualisierung hinzufügen
Wenn Sie einer Spalte in einer Freiformtabelle Segmente hinzufügen, werden die Segmente auf alle Inhalte in der Tabellenspalte angewendet. Sie können Segmente auch als Teil einer Fallout-Visualisierung hinzufügen.

* Segmente in Komponenten verwenden
Wenn Sie Komponenten wie [berechnete Metriken](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md), [Anmerkungen](/help/components/annotations/create-annotations.md#annotation-builder) oder sogar [Segmente](/help/components/segments/seg-builder.md) definieren, können Sie Segmente als Teil der Definition verwenden.


### Hinzufügen von Datumsbereichen zu einem Projekt

[Datumsbereiche](/help/components/date-ranges/overview.md) bestimmen den Reporting-Zeitrahmen in Analysis Workspace und können auf ein oder mehrere Panels innerhalb eines Projekts sowie auf einige Visualisierungen (wie die Freiformtabelle) angewendet werden.

Jedes Panel enthält standardmäßig einen Datumsbereich. Es gibt mehrere Möglichkeiten, einen Datumsbereich für ein Panel zu aktualisieren. Eine Möglichkeit zum Aktualisieren eines Datumsbereichs für ein Panel in Analysis Workspace besteht darin, eine Datumsbereichskomponente aus dem linken Panel zu ziehen:

1. Fügen Sie optional Panels zu Ihrem Projekt in Analysis Workspace hinzu, wie unter [Hinzufügen von Komponenten zu einem Projekt](#add-components-to-a-project) beschrieben. 

1. Ziehen Sie einen Datumsbereich per Drag-and-Drop aus dem linken Panel auf:

   * Den aktuellen Datumsbereich, um den Datumsbereich für das Panel zu ändern.

     ![Abelgen eines Datumsbereichs](assets/add-date-range.gif)

   * Eine Metrik oder Dimension in einer Visualisierung vom Typ „Freiformtabelle“. Weitere Informationen finden Sie unter [Verwenden von Datumsbereichen](/help/components/date-ranges/overview.md#use-date-ranges).

Weitere Informationen zum Verwenden und Verwalten von Datumsbereichen in Analysis Workspace finden Sie unter [Übersicht über Datumsbereiche](/help/components/date-ranges/overview.md).

## Informationen zu Komponenten

Sie können den Mauszeiger über eine beliebige Komponente bewegen, um ![weitere Informationen](/help/assets/icons/InfoOutline.svg) anzuzeigen. Wenn diese Option ausgewählt ist, wird ein Popup mit zusätzlichen Informationen über die Komponente angezeigt.

![Informationen zu Komponenten](assets/component-info.png)

Je nach Zugriffssteuerung haben Sie folgende Möglichkeiten:

* Aufrufen der ![Lesezeichen](/help/assets/icons/Bookmark.svg) [!UICONTROL Datenwörterbuch]-Definition für die Komponente.
* Aufrufen des ![Bearbeiten](/help/assets/icons/Edit.svg) Komponenten-Builders oder der Datenansicht, in der die Komponente definiert ist.
