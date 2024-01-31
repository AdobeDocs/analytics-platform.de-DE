---
description: Verwenden Sie die Linienvisualisierung, um Trend-Datensätze (zeitbasiert) darzustellen.
title: Linie
feature: Visualizations
exl-id: b68aa8dc-2c96-4c49-8d3c-d94804aab479
role: User
source-git-commit: 30f3e24533ab0e03ee7f819c7f94592776603764
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 81%

---

# Linie

>[!NOTE]
>
>Die Linienvisualisierung wird in Kürze verfügbar sein [intelligente Beschriftungen](/help/analysis-workspace/visualizations/intelligent-captions.md).

Die Linienvisualisierung stellt Metriken anhand einer Linie dar, die den Wertverlauf über einen bestimmten Zeitraum hinweg zeigt. Ein Liniendiagramm kann nur verwendet werden, wenn die Zeit als Dimension verwendet wird.

![Linienvisualisierung](assets/line-viz.png)

Symbol Einstellungen auswählen ![Einstellungen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) in der Symbolleiste der Linienvisualisierung, um auf [Visualisierungseinstellungen](freeform-analysis-visualizations.md) verfügbar. Die Einstellungen sind in folgende Kategorien unterteilt:

<img src="./assets/viz-settings-line.png" alt="Visualisierungseinstellungen" width="50%" />

* **Allgemein**: Einstellungen, die für verschiedene Visualisierungstypen gelten
* **Achse**: Einstellungen, die sich auf die x- oder y-Achse der Linienvisualisierung auswirken
* **Überlagerungen**: Optionen zum Hinzufügen von zusätzlichem Kontext zu den in Ihrer Linienvisualisierung angezeigten Serien.


## Granularität ändern

In den [Visualisierungseinstellungen](freeform-analysis-visualizations.md) können Sie über ein Dropdown-Menü für die Granularität eine Trend-Visualisierung (z. B. Linie, Balken) von täglich zu wöchentlich zu monatlich usw. ändern. Die Granularität wird auch in der Datenquellentabelle aktualisiert.

## Min. oder Max. anzeigen

Unter **[!UICONTROL Visualisierungseinstellungen]** > **[!UICONTROL Überlagerungen]** > **[!UICONTROL Min/Max anzeigen]** können Sie eine Beschriftung für Minimal- und Maximalwerte überlagern, um die Spitzen und Täler schnell in einer Metrik hervorzuheben. Hinweis: Die Minimal bzw. Maximalwerte werden aus den sichtbaren Datenpunkten in der Visualisierung abgeleitet, nicht aus dem vollständigen Satz von Werten innerhalb einer Dimension.

![Eine Überlagerung mit der minimalen und maximalen Wertebeschriftung.](assets/min-max-labels.png)

## Trendzeilenüberlagerung anzeigen

Unter **[!UICONTROL Visualisierungseinstellungen]** > **[!UICONTROL Überlagerungen]** > **[!UICONTROL Trendlinie anzeigen]** können Sie Ihrer Linienserie eine Regressionstrendlinie hinzufügen oder die Durchschnittstrendlinie in Ihre Linienserie verschieben. Trendlinien helfen, ein Muster in den Daten besser darzustellen.

>[!TIP]
>
>Es wird empfohlen, Trendlinien auf Daten anzuwenden, die weder das aktuelle Datum (partielle Daten) noch zukünftige Datumsangaben enthalten, da diese die Trendlinie verfälschen. Wenn Sie jedoch zukünftige Datumsangaben einbeziehen müssen, entfernen Sie Nullen aus den Daten, um eine Verfälschung für diese Tage zu vermeiden. Gehen Sie dazu zur Datenquellenabelle der Visualisierung, wählen Sie Ihre Metrikspalte aus und aktivieren Sie dann **[!UICONTROL Spalteneinstellungen]** > **[!UICONTROL Null als keinen Wert interpretieren]**.

![Lineare Trendlinie](assets/show-linear-trendline.png)

Alle Trendlinien des Regressionsmodells werden über die reguläre Kleinstquadrat-Methode angepasst:

| Modell | Beschreibung |
| --- | --- |
| Linear | Erstellt eine am besten passende gerade Linie für einfache lineare Datensätze und ist nützlich, wenn die Daten stetig zunehmen oder abnehmen. Gleichung: `y = a + b * x` |
| Logarithmisch | Erstellt eine am besten passende gekrümmte Linie und ist nützlich, wenn die Änderungsrate der Daten schnell zunimmt oder abnimmt und dann abflacht. Eine logarithmische Trendlinie kann negative und positive Werte verwenden. Gleichung: `y = a + b * log(x)` |
| Exponentiell | Erstellt eine gekrümmte Linie und ist nützlich, wenn Daten mit ständig steigenden Raten steigen oder fallen. Diese Option sollte nicht verwendet werden, wenn Ihre Daten Null oder negative Werte enthalten. Gleichung: `y = a + e^(b * x)` |
| Potenzfunktion | Erstellt eine gekrümmte Linie und ist nützlich für Datensätze, die Messungen vergleichen, die mit einer bestimmten Rate zunehmen. Diese Option sollte nicht verwendet werden, wenn Ihre Daten Null oder negative Werte enthalten. Gleichung: `y = a * x^b` |
| Quadratisch | Findet die beste Anpassung für einen Datensatz, der wie eine Parabel geformt ist (konkav nach oben oder unten). Gleichung: `y = a + b * x + c * x^2` |
| Gleitender Mittelwert | Erstellt eine glatte Trendlinie basierend auf einer Reihe von Durchschnittswerten. Ein gleitender Durchschnittswert, der auch als rollierender Durchschnitt bezeichnet wird, nutzt eine bestimmte Anzahl von Datenpunkten (bestimmt durch Auswahl eines Zeitraums), errechnet einen Durchschnittswert und verwendet den Durchschnittswert als Punkt auf der Linie. Beispiele sind der gleitende Durchschnitt für 7 Tage oder der gleitende Durchschnitt für 4 Wochen. |
