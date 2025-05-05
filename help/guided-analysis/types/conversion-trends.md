---
title: Analyse „Konversions-Trends“
description: Verfolgen Sie die Veränderungen der Konversionsrate im Zeitverlauf.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
exl-id: 75501e77-a172-48b4-9c91-b12d39e93c37
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: ht
source-wordcount: '536'
ht-degree: 100%

---

# Analyse [!UICONTROL Konversions-Trends] {#conversion-trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_conversiontrends_button"
>title="Konversions-Trends"
>abstract="Verfolgen Sie ie dVeränderungen der Konversionsraten im Laufe der Zeit."

<!-- markdownlint-enable MD034 -->


Die ![Konversionstrends](/help/assets/icons/ConversionTrends.svg) Analyse **[!UICONTROL Konversions-Trends]** bietet eine Trend-Visualisierung der Konversionsraten im Zeitverlauf. Die horizontale Achse ist ein Zeitintervall, die vertikale Achse stellt die Konversionsrate dar.


>[!VIDEO](https://video.tv.adobe.com/v/3423487/?quality=12&learn=on&captions=ger)


## Anwendungsfälle

Zu den Anwendungsfällen für diese Analyse gehören:

* **Optimierungsmaßnahmen verfolgen**: Nachdem Sie mithilfe der Analyse [Trichter](funnel.md) wichtige Engpässe identifiziert haben, die verbessert werden sollen, können Sie anhand dieser Analyse verfolgen, wie sich diese Optimierungen im Zeitverlauf auf die Konversionsrate auswirken.
* **A/B-Tests bewerten** Bewerten Sie die Effektivität von A/B-Tests oder Experimenten, die im Kontext eines Trichters durchgeführt werden. Durch den Vergleich der Konversionsraten zwischen verschiedenen Varianten können Sie einfach feststellen, welche Tests höhere Konversionsraten liefern. Dies führt zu datengesteuerten Entscheidungen, welche Varianten dauerhaft implementiert werden sollen.
* **Kampagnen im Zeitverlauf bewerten**: Messen Sie die Effektivität von Marketing-Kampagnen im Zeitverlauf. Sie können ein Segment erstellen, das sich auf Benutzende mit einem Touchpoint zu einer bestimmten Kampagne konzentriert, und ihre Konversionsraten mit anderen Kampagnen vergleichen. Sie können auch aktuelle Konversionsraten mit ähnlichen Kampagnen vergleichen, die in der Vergangenheit durchgeführt wurden.

## Benutzeroberfläche

Einen Überblick über die Benutzeroberfläche für die geführte Analyse erhalten Sie unter [Benutzeroberfläche](../overview.md#interface). Die folgenden Einstellungen sind für diese Analyse spezifisch:

### Abfrageleiste

Mit der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Wechseln Sie zwischen dieser Analyse und [Trichter](funnel.md).
* **[!UICONTROL Schritte]**: Die Ereignis-Touchpoints, die verfolgt werden sollen. Jeder Balken im Diagramm stellt einen Schritt dar. Sie können bis zu zehn Schritte einschließen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll. Zu den Optionen gehören [!UICONTROL Benutzende] und [!UICONTROL Sitzungen].
* **[!UICONTROL Segmente]**: Die Segmente, über die der Trichter verglichen werden soll. Jedes ausgewählte Segment teilt jeden Schritt in mehrere Balken auf. Jede Farbe stellt ein anderes Segment dar. Sie können bis zu drei Segmente einschließen.

### Diagrammeinstellungen

Die Analyse [!UICONTROL Konversions-Trends] bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, der verwendet werden soll. Zu den Optionen gehört [!UICONTROL Linie].
* **[!UICONTROL Konversion in]**: Bestimmt die prozentuale Berechnung von Schritt zu Schritt. Zu den Optionen gehören die Berechnung der Konversion aus dem [!UICONTROL ersten Schritt] oder [!UICONTROL vorherigen Schritt].

>[!NOTE]
>
>Die Spalte **Durchschnitt** der Analysetabelle „Konversions-Trends“ unterscheidet sich von der Spalte **Gesamt** der Tabelle [Trichteranalyse](funnel.md). Bei der ersten Spalte handelt es sich um einen Durchschnitt der Intervallspalten (z. B. den Durchschnitt der täglichen Konversionsraten), bei der zweiten um eine aggregierte Berechnung über den gesamten Datumsbereich.

### Zeitvergleich

{{apply-time-comparison}}


### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trend-Daten angezeigt werden sollen. Gültige Optionen sind „Stündlich“, „Täglich“, „Wöchentlich“, „Monatlich“ und „Quartalsweise“. Derselbe Datumsbereich kann unterschiedliche Intervalle aufweisen, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Bei einer Analyse über drei Tage mit täglicher Granularität werden beispielsweise nur drei Datenpunkte angezeigt, während eine Analyse über drei Tage mit stündlicher Granularität 72 Datenpunkte ergibt.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Ihnen stehen rollierende Datumsbereichsvorgaben und zuvor gespeicherte benutzerdefinierte Bereiche zur Verfügung. Sie können auch die Kalenderauswahl verwenden, um einen festen Datumsbereich zu definieren.

<!--
## Example

See below for an example of the analysis.

![Conversion trends time compare](../assets/conversion-trends-compare.png)

-->
