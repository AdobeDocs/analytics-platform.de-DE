---
description: Verwenden Sie die Linienvisualisierung, um Trend-Datensätze (zeitbasiert) darzustellen.
title: Linie
feature: Visualizations
exl-id: b68aa8dc-2c96-4c49-8d3c-d94804aab479
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 18%

---

# Linie {#line}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_line_button"
>title="Linie"
>abstract="Erstellen Sie eine Linienvisualisierung, die anzeigt, wie sich Werte über einen bestimmten Zeitraum ändern. Eine Linienvisualisierung kann nur verwendet werden, wenn die Zeit als Dimension verwendet wird."

<!-- markdownlint-enable MD034 -->


Die Visualisierung ![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL Linie]** stellt Metriken anhand einer Zeile dar, die angibt, wie sich Werte über einen bestimmten Zeitraum ändern. Eine Linienvisualisierung kann nur verwendet werden, wenn die Zeit als Dimension verwendet wird.

<!--
>[!NOTE]
>
>The Line visualization soon feature [intelligent captions](/help/analysis-workspace/visualizations/intelligent-captions.md).

The Line visualization represents metrics using a line to show how values change over a period of time. A line chart can be used only when time is used as a dimension.
-->

![Linienvisualisierung](assets/line-viz.png)


## Einstellungen

Im Rahmen der [Visualisierungseinstellungen](freeform-analysis-visualizations.md#settings) sind spezifische Einstellungen für die Linienvisualisierung verfügbar.

| Einstellung | Beschreibung |
|---|---|
| **[!UICONTROL Granularität]** | Wählen Sie aus der Dropdown-Liste Granularität aus, um eine Trend-Visualisierung von täglich zu wöchentlich zu monatlich usw. zu ändern. Die Granularität wird auch in der Datenquellentabelle aktualisiert. |
| **[!UICONTROL Min. anzeigen]** <br/>**[!UICONTROL Max.]**anzeigen | Sie können eine Mindest- und Höchstwertebeschriftung überlagern, um die Mindest- und Höchstwerte in einer Metrik hervorzuheben. Die Mindest-/Höchstwerte werden aus den sichtbaren Datenpunkten in der Visualisierung abgeleitet, nicht aus dem vollständigen Satz von Werten innerhalb einer Dimension.<br/>![Eine Überlagerung mit der minimalen und maximalen Wertebeschriftung.](assets/min-max-labels.png) |
| **[!UICONTROL Trendlinie anzeigen]** | Sie können eine Regression oder eine sich bewegende durchschnittliche Trendlinie zu Ihrer Linienserie hinzufügen. Trendlinien helfen bei der Darstellung eines klareren Musters in den Daten. Wenn diese Option aktiviert ist, wählen Sie ein Modell aus der Liste aus. Eine Übersicht und Beschreibung der verfügbaren Modelle finden Sie unter [Modelle](#models) .<br/>![Lineare Trendlinie](assets/show-linear-trendline.png). |

>[!TIP]
>
>Es wird empfohlen, Trendlinien auf Daten anzuwenden, die weder heute noch zukünftige Daten enthalten. Die heutigen oder künftigen Datumsangaben verfälschen die Trendlinie. Wenn Sie jedoch zukünftige Datumsangaben einbeziehen müssen, entfernen Sie Nullen aus den Daten, um eine Verfälschung für diese Tage zu vermeiden. Wechseln Sie zur Datenquellentabelle der Visualisierung, wählen Sie Ihre Metrikspalte aus und aktivieren Sie dann **[!UICONTROL Spalteneinstellungen]** > **[!UICONTROL Null als keinen Wert auffassen]**.



### Modelle

Alle Trendlinien des Regressionsmodells werden über die reguläre Kleinstquadrat-Methode angepasst:

| Modell | Beschreibung |
| --- | --- |
| **[!UICONTROL Linear]** | Erstellen Sie eine am besten passende gerade Linie für einfache lineare Datensätze und ist nützlich, wenn die Daten stetig zunehmen oder abnehmen. Gleichung: `y = a + b * x` |
| **[!UICONTROL Logarithmisch]** | Erstellen Sie eine am besten passende gekrümmte Linie und ist nützlich, wenn die Änderungsrate in den Daten schnell zunimmt oder abnimmt und dann abflacht. Eine logarithmische Trendlinie kann negative und positive Werte verwenden. Gleichung: `y = a + b * log(x)` |
| **[!UICONTROL Exponentiell]** | Erstellen Sie eine gekrümmte Linie und ist nützlich, wenn Daten mit ständig steigenden Raten steigen oder fallen. Diese Option sollte nicht verwendet werden, wenn Ihre Daten Null oder negative Werte enthalten. Gleichung: `y = a + e^(b * x)` |
| **[!UICONTROL Power]** | Erstellen Sie eine gekrümmte Linie und ist nützlich für Datensätze, die Messungen vergleichen, die mit einer bestimmten Rate zunehmen. Diese Option sollte nicht verwendet werden, wenn Ihre Daten Null oder negative Werte enthalten. Gleichung: `y = a * x^b` |
| **[!UICONTROL Quadratisch]** | Findet die beste Anpassung für einen Datensatz, der wie eine Parabel geformt ist (konkav nach oben oder unten). Gleichung: `y = a + b * x + c * x^2` |
| **[!UICONTROL Beweglicher Durchschnitt]** | Erstellen Sie eine glatte Trendlinie basierend auf einer Reihe von Durchschnittswerten. Ein anpassbarer Durchschnittswert, der auch als rollierender Durchschnitt bezeichnet wird, verwendet eine bestimmte Anzahl von Datenpunkten (bestimmt durch Ihre Auswahl von [!UICONTROL Granularität] ), errechnet einen Durchschnittswert und verwendet den Durchschnittswert als Punkt in der Zeile. Beispiele sind ein anpassbarer Durchschnittswert von sieben Tagen oder ein anpassbarer Durchschnittswert von vier Wochen. |

>[!MORELIKETHIS]
>
>[Hinzufügen einer Visualisierung zu einem Bedienfeld](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualisierungseinstellungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Kontextmenü &quot;Visualisierung&quot;](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

