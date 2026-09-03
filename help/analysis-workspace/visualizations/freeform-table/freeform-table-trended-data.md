---
description: Erfahren Sie, wie Sie Trend-Daten für eine Freiformtabelle in Analysis Workspace anzeigen.
title: Anzeigen von Trend-Daten für eine Freiformtabelle
feature: Freeform Tables
role: User, Admin
exl-id: 57fc0a64-658f-4931-952e-ab8479ae61d1
autotag-review: '2026-05-19T08:43:04.024Z'
TQID: 'https://experienceleague.adobe.com/-WIC1VpPmJXOXAn3ltwvIRKY9iDbnKgxEJl3XF4VEBc'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 402
ht-degree: 0%

---

# Anzeigen von Trend-Daten für eine Freiformtabelle

Sie können den Trend der Daten anzeigen, die in einer Freiformtabelle enthalten sind. Diese Trend-Daten werden in Analysis Workspace in den folgenden Bereichen angezeigt:

* [Sparklines](#use-sparklines-to-view-trended-data)

* [Linienvisualisierungen](#use-line-visualizations-to-view-trended-data)

## Verwenden von Sparklines zum Anzeigen von Trend-Daten

Sparklines werden in der Metrik-Spaltenüberschrift von Freiformtabellen angezeigt.

![Sparkline in Freiformtabelle](assets/table-sparkline.png)

Sparklines umfassen immer:

* Trend-Daten für alle Daten in der Spalte

* Alle Suchfilterkriterien, die auf die Tabellendimension angewendet werden

  Weitere Informationen finden Sie unter [Filtern und Sortieren](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

## Verwenden von Linienvisualisierungen zum Anzeigen von Trenddaten

[Line](/help/analysis-workspace/visualizations/line.md)-Visualisierungen zeigen die Daten der Freiformtabelle an, mit der sie verbunden sind.

### Verbinden einer Linienvisualisierung mit einer Freiformtabelle

Je nachdem, wie und wann die Linienvisualisierung zum Projekt hinzugefügt wurde, ist sie möglicherweise bereits mit der gewünschten Freiformtabelle verbunden. Führen Sie die folgenden Schritte aus, um zu überprüfen oder manuell eine Verbindung herzustellen:

1. Hinzufügen einer Linienvisualisierung zu einem Analysis Workspace-Projekt.

1. Klicken Sie auf den Punkt neben dem Visualisierungsnamen, klicken Sie auf die Registerkarte **[!UICONTROL Datenquelle]** und wählen Sie dann den Namen der Freiformtabelle aus, mit der Sie die Linienvisualisierung verbinden möchten.

   ![Linienvisualisierung in Verbindung mit Freiformtabellen](assets/table-line-viz.png)

### Wählen Sie die in der Linienvisualisierung enthaltenen Daten aus

Die in der Visualisierung der verbundenen Zeilen enthaltenen Daten unterscheiden sich je nachdem, welche Zelle in der Freiformtabelle ausgewählt ist.

Um einen Trend aller Daten in der Freiformtabelle anzuzeigen, wählen Sie die Sparkline-Zelle in der Freiformtabelle aus.

Wenn die Sparkline-Zelle ausgewählt ist, wird die Zelle dunkelgrau angezeigt.

![Sparkline ausgewählt](assets/table-sparkline-selected.png)

Wenn die Sparkline-Zelle der verbundenen Tabelle ausgewählt ist, enthalten Linienvisualisierungen Folgendes:

* Trend-Daten für alle Daten in der Spalte

* Alle Suchfilterkriterien, die auf die Tabellendimension angewendet werden

  Weitere Informationen finden Sie unter [Filtern und Sortieren](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

Wenn die Sparkline der verbundenen Tabelle nicht ausgewählt ist, enthalten Linienvisualisierungen Folgendes:

* Daten für die Zeile, die in der verbundenen Tabelle ausgewählt ist. Wenn keine Zeile ausgewählt ist, werden nur Daten für die erste Dimension der verbundenen Tabelle angezeigt.

* Alle auf die Tabellendimension angewendeten Suchfilterkriterien werden ignoriert

  Weitere Informationen finden Sie unter [Filtern und Sortieren](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).


## Filterkriterien in verbundene Linienvisualisierungen einschließen

Informationen dazu, wann Filterkriterien in Visualisierungen mit verbundenen Linien enthalten sind, finden Sie unter [Filterkriterien in Trend-Daten in Sparklines und Linienvisualisierungen einschließen](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#include-filter-criteria-in-trended-data-in-sparklines-and-line-visualizations)
