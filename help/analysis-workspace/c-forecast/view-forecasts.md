---
description: Erfahren Sie, wie Sie Prognosen in einer Tabelle oder einem Liniendiagramm anzeigen können.
title: So zeigen Sie Prognosen in Analysis Workspace an
feature: Visualizations
role: User
exl-id: 4a8b602c-e6aa-4a46-bba9-642387e6af88
source-git-commit: fea1b12a594a820ab2e55f850ca95c5a373184f0
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 2%

---

# Anzeigen von Prognosen in Analysis Workspace

Sie können Prognosen in einer Freiformtabelle oder in einem Liniendiagramm anzeigen.

## Anzeigen von Prognosen in einer Tabelle

Sie können Prognosen in einer Zeitreihen-Freiformtabelle anzeigen. Wenn [!UICONTROL Prognose anzeigen] für die Freiformtabelle in [Benutzereinstellungen](../user-preferences.md) aktiviert ist, wird automatisch eine Prognose für die erste Metrikspalte angezeigt, die der Tabelle hinzugefügt wurde. Für jede zusätzliche Spalte:

1. Wählen Sie das Symbol für die Spalteneinstellungen ![Spalteneinstellungen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) in der Spaltenüberschrift aus und stellen Sie sicher, dass **[!UICONTROL Prognose anzeigen]** in der Optionsliste ausgewählt ist. Weitere Informationen finden Sie unter [Spalteneinstellungen](../visualizations/freeform-table/column-row-settings/column-settings.md).

1. Klicken Sie außerhalb des Menüs **[!UICONTROL Spalteneinstellungen]**, um die Einstellung zu speichern und die aktualisierte Tabelle anzuzeigen.

Die Prognosen sind in der Tabelle wie folgt dargestellt:

![Prognose in Tabelle anzeigen](assets/show-forecast-table.png)

* Der Prognosewert und der Prozentsatz für jede Zelle werden in **dunkelgrau** angezeigt.
* Um einen Prognosewert anzugeben, ein Prognosesymbol <img src="./assets/forecast.svg" alt="Prognosesymbol" width="20" /> wird in der oberen rechten Ecke der Zelle angezeigt.


## Anzeigen von Prognosen in einem Liniendiagramm

Ein Liniendiagramm ist die einzige Visualisierung, mit der Sie Prognosen anzeigen können.

1. Wählen Sie das Einstellungssymbol ![Spalteneinstellungen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) in der Visualisierungskopfzeile aus und stellen Sie sicher, dass **[!UICONTROL Prognose anzeigen]** in der Optionsliste ausgewählt ist.

1. (Optional) Damit die Prognosen das Diagramm ordnungsgemäß skalieren können, wählen Sie **[!UICONTROL Prognose auf Y-Achse skalieren lassen]** aus. Diese Option ist standardmäßig nicht aktiviert, da dadurch unter Umständen ein Diagramm weniger gut lesbar wird.

1. Klicken Sie außerhalb des **[!UICONTROL Einstellungen]**, um das aktualisierte Liniendiagramm anzuzeigen.

Die Prognosen werden im Liniendiagramm wie folgt angezeigt:

![Prognose im Liniendiagramm anzeigen](assets/show-forecast-linechart.png)

* Die aktuellen Werte für die Metriken im Liniendiagramm werden durch einen vertikalen Balken angezeigt. Wenn Sie den Mauszeiger über diese vertikale Linie bewegen, wird ein Popup mit dem letzten aktuellen Datum angezeigt.
* Prognostizierte Werte für eine oder mehrere Metriken werden direkt über den vertikalen Balken mit gepunkteten Linien angezeigt. Sie können den Mauszeiger über einen beliebigen Datenpunkt für eine Metrik bewegen. Dadurch wird ein Popup angezeigt mit:
   * Datum der Prognose
   * Prognostizierter Wert für die Metrik
   * Obere Grenze des prognostizierten Werts für die Metrik
   * Untergrenze des prognostizierten Werts für die Metrik
* Der schattierte Bereich zeigt das Konfidenzband der Prognose an.
