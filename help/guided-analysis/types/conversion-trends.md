---
title: Analyse der Konversionstrends
description: Verfolgen Sie Veränderungen der Konversionsrate im Zeitverlauf.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
exl-id: 75501e77-a172-48b4-9c91-b12d39e93c37
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 7%

---

# Analyse [!UICONTROL Konversions-Trends] {#conversion-trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_conversiontrends_button"
>title="Konversions-Trends"
>abstract="Verfolgen Sie ie dVeränderungen der Konversionsraten im Laufe der Zeit."

<!-- markdownlint-enable MD034 -->


Die ![Konversionstrends](/help/assets/icons/ConversionTrends.svg)**[!UICONTROL Konversionstrends]** bietet eine Trend-Visualisierung der Konversionsraten im Zeitverlauf. Die horizontale Achse ist ein Zeitintervall, während die vertikale Achse die Konversionsrate darstellt.


>[!VIDEO](https://video.tv.adobe.com/v/3421662/?quality=12&learn=on)


## Anwendungsfälle

Anwendungsfälle für diese Analyse sind:

* **Optimierungsbemühungen verfolgen**: Nachdem Sie mithilfe der [Trichter](funnel.md)-Analyse wichtige Engpässe identifiziert haben, die Sie verbessern möchten, können Sie diese Analyse verwenden, um zu verfolgen, wie sich diese Optimierungen im Laufe der Zeit auf die Konversionsrate auswirken.
* **A/B-Test-Evaluierung** Bewerten Sie die Effektivität von A/B-Tests oder Experimenten, die im Kontext eines Trichters durchgeführt werden. Durch den Vergleich der Konversionsraten zwischen verschiedenen Varianten können Sie einfach feststellen, welche Tests höhere Konversionsraten liefern, was zu datengesteuerten Entscheidungen darüber führt, welche Varianten dauerhaft implementiert werden sollen.
* **Kampagnenauswertung im Zeitverlauf**: Messen der Effektivität von Marketing-Kampagnen im Zeitverlauf. Sie können ein Segment erstellen, das sich auf Benutzer konzentriert, die eine bestimmte Kampagne berührt haben, und ihre Konversionsraten mit anderen Kampagnen vergleichen. Sie können auch aktuelle Konversionsraten mit ähnlichen Kampagnen vergleichen, die in der Vergangenheit ausgeführt wurden.

## Benutzeroberfläche

Siehe [Schnittstelle](../overview.md#interface) für einen Überblick über die Oberfläche der geführten Analyse. Die folgenden Einstellungen sind für diese Analyse spezifisch:

### Abfrageleiste

Mit der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Wechseln Sie zwischen dieser Analyse und [Trichter](funnel.md).
* **[!UICONTROL Schritte]**: Die Ereignis-Touchpoints, die Sie verfolgen möchten. Jeder Balken im Diagramm stellt einen Schritt dar. Sie können bis zu zehn Schritte umfassen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll.  Die Optionen umfassen [!UICONTROL Benutzer] und [!UICONTROL Sitzungen].
* **[!UICONTROL Segmente]**: Die Segmente, über die Sie den Trichter vergleichen möchten. Jedes ausgewählte Segment teilt jeden Schritt in mehrere Balken auf. Jede Farbe stellt ein anderes Segment dar. Sie können bis zu drei Segmente einschließen.

### Diagrammeinstellungen

Die [!UICONTROL Konversionstrends]-Analyse bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, den Sie verwenden möchten. Die Optionen umfassen [!UICONTROL Line].
* **[!UICONTROL Konversion von]**: Bestimmt die prozentuale Berechnung von Schritt zu Schritt. Zu den Optionen gehören die Berechnung der Konvertierung aus dem [!UICONTROL ersten Schritt] oder [!UICONTROL vorherigen Schritt].

>[!NOTE]
>
>Die Spalte **Durchschnitt** in der Analysetabelle für Konversionstrends unterscheidet sich von der Spalte **Summe** in der Tabelle [Trichteranalyse](funnel.md). Bei der ersten Spalte handelt es sich um einen Durchschnitt der Intervallspalten (z. B. den Durchschnitt der täglichen Konversionsraten), bei der zweiten um eine aggregierte Berechnung über den gesamten Datumsbereich.

### Zeitvergleich

{{apply-time-comparison}}


### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trend-Daten angezeigt werden sollen. Gültige Optionen sind stündlich, täglich, wöchentlich, monatlich und vierteljährlich. Derselbe Datumsbereich kann unterschiedliche Intervalle aufweisen, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Wenn Sie beispielsweise eine Analyse mit dreitägiger Granularität anzeigen, werden nur drei Datenpunkte angezeigt, während eine Analyse mit dreitägiger Granularität 72 Datenpunkte ergibt.
* **[!UICONTROL Date]**: Das Start- und Enddatum. Rollierende Datumsbereichsvorgaben und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Sie können auch den Kalenderselektor verwenden, um einen festen Datumsbereich auszuwählen.

<!--
## Example

See below for an example of the analysis.

![Conversion trends time compare](../assets/conversion-trends-compare.png)

-->
