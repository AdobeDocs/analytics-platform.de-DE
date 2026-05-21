---
description: Erfahren Sie, wie Sie Prognosen in einer Tabelle oder einem Liniendiagramm anzeigen können.
title: Prognosen anzeigen
feature: Visualizations
role: User
exl-id: 4a8b602c-e6aa-4a46-bba9-642387e6af88
TQID: https://experienceleague.adobe.com/fihJQOI-CyvGccQsB0VxvwR-iV0OkJSMENaiciYrgFc
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: d13dba12-733d-4914-8d92-d643658bbe5d
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 372
ht-degree: 5%

---

# Anzeigen von Prognosen

Sie können Prognosen in einer Freiformtabelle oder in einem Liniendiagramm anzeigen.

## Anzeigen von Prognosen in einer Tabelle

Sie können Prognosen in einer Zeitreihen-Freiformtabelle anzeigen. Wenn [!UICONTROL Prognose anzeigen] für die Freiformtabelle in [Benutzereinstellungen](../user-preferences.md) aktiviert ist, wird automatisch eine Prognose für die erste Metrikspalte angezeigt, die der Tabelle hinzugefügt wurde. Für jede zusätzliche Spalte:

1. Wählen Sie das Symbol für die Spalteneinstellungen ![Spalteneinstellungen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) in der Spaltenüberschrift aus und stellen Sie sicher, dass **[!UICONTROL Prognose anzeigen]** in der Optionsliste ausgewählt ist. Weitere Informationen finden Sie unter [Spalteneinstellungen](../visualizations/freeform-table/column-row-settings/column-settings.md).

1. Klicken Sie außerhalb des Menüs **[!UICONTROL Spalteneinstellungen]**, um die Einstellung zu speichern und die aktualisierte Tabelle anzuzeigen.

Die Prognosen sind in der Tabelle wie folgt dargestellt:

![Prognose in Tabelle anzeigen](assets/show-forecast-table.png)

* Der Prognosewert und der Prozentsatz für jede Zelle werden in **dunkelgrau** angezeigt.
* Um einen Prognosewert anzugeben, wird ein Prognosesymbol ![ForecastAnalytics](/help/assets/icons/ForecastAnalytics.svg) oben rechts in der Zelle angezeigt.


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
