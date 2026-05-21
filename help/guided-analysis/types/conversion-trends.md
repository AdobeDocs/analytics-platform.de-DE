---
title: Analyse „Konversions-Trends“
description: Verfolgen Sie die Veränderungen der Konversionsrate im Zeitverlauf.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
exl-id: 75501e77-a172-48b4-9c91-b12d39e93c37
role: User
TQID: https://experienceleague.adobe.com/jqpqcNM8eOP0Te1t6-l0Mt5HvxhGzB8xMBxb1I-5GPM
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 550
ht-degree: 97%

---

# Analyse [!UICONTROL Konversions-Trends] {#conversion-trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_conversiontrends_button"
>title="Konversions-Trends"
>abstract="Verfolgen Sie ie dVeränderungen der Konversionsraten im Laufe der Zeit."

<!-- markdownlint-enable MD034 -->


Die ![Konversionstrends](/help/assets/icons/ConversionTrends.svg) Analyse **[!UICONTROL Konversions-Trends]** bietet eine Trend-Visualisierung der Konversionsraten im Zeitverlauf. Die horizontale Achse ist ein Zeitintervall, die vertikale Achse stellt die Konversionsrate dar.


>[!VIDEO](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/conversion-trends)


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
* **[!UICONTROL Schritte]**: Die Ereignis-Touchpoints, die Sie verfolgen möchten. Jeder Balken im Diagramm stellt einen Schritt dar. Sie können bis zu zehn Schritte einschließen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll. Zu den Optionen gehören [!UICONTROL Benutzende] und [!UICONTROL Sitzungen].
* **[!UICONTROL Segmente]**: Die Segmente, über die Sie den Trichter vergleichen möchten. Jedes ausgewählte Segment teilt jeden Schritt in mehrere Balken auf. Jede Farbe stellt ein anderes Segment dar. Sie können bis zu drei Segmente einschließen.

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
