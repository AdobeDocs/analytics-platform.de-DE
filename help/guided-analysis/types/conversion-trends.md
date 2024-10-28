---
title: Analyse von Konversionstrends
description: Verfolgen Sie Änderungen der Konversionsrate im Zeitverlauf.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
exl-id: 75501e77-a172-48b4-9c91-b12d39e93c37
role: User
source-git-commit: d492220eaf12242a870f3826b31edd3d1ea99a3b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!UICONTROL Konversionstrends] Analyse {#conversion-trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_guidedanalysis_conversiontrends_button"
>title="Konversions-Trends"
>abstract="Verfolgen Sie ie dVeränderungen der Konversionsraten im Laufe der Zeit."

<!-- markdownlint-enable MD034 -->


Die Analyse ![Konversionstrends](/help/assets/icons/ConversionTrends.svg) **[!UICONTROL Konversionstrends]** bietet eine Trend-Visualisierung der Konversionsraten im Zeitverlauf. Die horizontale Achse ist ein Zeitintervall, während die vertikale Achse die Konversionsrate darstellt.


>[!VIDEO](https://video.tv.adobe.com/v/3421662/?learn=on)


## Anwendungsbeispiele

Anwendungsbeispiele für diese Analyse sind:

* **Optimierungsbemühungen verfolgen**: Nachdem Sie die wichtigsten Engpässe identifiziert haben, die Sie mithilfe der [Trichteranalyse](funnel.md) verbessern möchten, können Sie mit dieser Analyse verfolgen, wie sich diese Optimierungen im Laufe der Zeit auf die Konversionsrate auswirken.
* **A/B-Test-Evaluierung**: Bewerten Sie die Effektivität von A/B-Tests oder -Experimenten, die im Kontext eines Trichters durchgeführt werden. Durch den Vergleich von Konversionsraten zwischen verschiedenen Varianten können Sie einfach feststellen, welche Tests höhere Konversionsraten bieten, was zu datengesteuerten Entscheidungen führt, um welche Varianten dauerhaft implementiert werden sollen.
* **Kampagnenbewertung im Zeitverlauf**: Messen Sie die Effektivität von Marketing-Kampagnen im Zeitverlauf. Sie können ein Segment erstellen, das sich auf Benutzer konzentriert, die eine bestimmte Kampagne berührt haben, und ihre Konversionsraten mit anderen Kampagnen vergleichen. Sie können auch die aktuellen Konversionsraten mit ähnlichen Kampagnen vergleichen, die in der Vergangenheit ausgeführt wurden.

## Benutzeroberfläche

Eine Übersicht über die Benutzeroberfläche der geführten Analyse finden Sie unter [Schnittstelle](../overview.md#interface) . Die folgenden Einstellungen beziehen sich auf diese Analyse:

### Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Wechseln Sie zwischen dieser Analyse und [Trichter](funnel.md).
* **[!UICONTROL Schritte]**: Die Ereignis-Touchpoints, die Sie verfolgen möchten. Jede Leiste im Diagramm stellt einen Schritt dar. Sie können bis zu zehn Schritte einbeziehen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll. Zu den Optionen gehören [!UICONTROL Benutzer] und [!UICONTROL Sitzungen].
* **[!UICONTROL Segmente]**: Die Segmente, über die Sie den Trichter vergleichen möchten. Jedes ausgewählte Segment teilt jeden Schritt in mehrere Balken auf. Jede Farbe stellt ein anderes Segment dar. Sie können bis zu drei Segmente einbeziehen.

### Diagrammeinstellungen

Die Analyse [!UICONTROL Konversionstrends] bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Typ der Visualisierung, die Sie verwenden möchten. Zu den Optionen gehören [!UICONTROL Linie].
* **[!UICONTROL Konvertierung von]**: Bestimmt die Berechnung des Prozentsatzes von Schritt zu Schritt. Zu den Optionen gehören die Berechnung der Konvertierung aus dem [!UICONTROL ersten Schritt] oder dem [!UICONTROL vorherigen Schritt].

>[!NOTE]
>
>Die Spalte **Durchschnitt** in der Tabelle zur Analyse von Konversionstrends unterscheidet sich von der Spalte **Gesamt** in der Tabelle [Trichteranalyse](funnel.md). Erstere ist der Durchschnitt der Intervallspalten (z. B. der Durchschnitt der täglichen Konversionsraten), während Letztere eine aggregierte Berechnung über den gesamten Datumsbereich hinweg ist.

### Zeitvergleich

{{apply-time-comparison}}


### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Trenddaten angezeigt werden sollen. Gültige Optionen sind &quot;Stündlich&quot;, &quot;Täglich&quot;, &quot;Wöchentlich&quot;, &quot;Monatlich&quot;und &quot;Quartal&quot;. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Wenn Sie beispielsweise eine Analyse betrachten, die sich auf drei Tage mit täglicher Granularität erstreckt, werden nur drei Datenpunkte angezeigt, während eine Analyse, die drei Tage mit stündlicher Granularität umfasst, 72 Datenpunkte anzeigen würde.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.

<!--
## Example

See below for an example of the analysis.

![Conversion trends time compare](../assets/conversion-trends-compare.png)

-->
