---
description: Erfahren Sie mehr über die Flow-Funktion, die Kundenpfade durch Ihre Websites und Programme zeigt.
title: Flussübersicht
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 46%

---

# Fluss {#flow}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_flow_button"
>title="Fluss"
>abstract="Erstellen Sie eine Visualisierung, um den Personenfluss von einem Checkpoint zum nächsten anzuzeigen."

>[!CONTEXTUALHELP]
>id="workspace_flow_panel"
>title="Fluss"
>abstract="Analysieren Sie den Besuchs- oder Besucherfluss von einem Touchpoint zum nächsten.<br/><br/>**Parameter **<br/>**Beginnt mit**: Fügen Sie eine Dimension, ein Dimensionselement oder eine Metrik hinzu, um die am häufigsten auftretenden Touchpoints nach dem Auftreten der ausgewählten Komponente anzuzeigen.<br/>**Enthält**: Fügen Sie eine Dimension oder ein Dimensionselement hinzu, um die am häufigsten auftretenden Touchpoints vor und nach dem Auftreten der ausgewählten Komponente anzuzeigen.<br/>**Endet mit**: Fügen Sie eine Dimension, ein Dimensionselement oder eine Metrik hinzu, um die am häufigsten auftretenden Touchpoints vor dem Auftreten der ausgewählten Komponente anzuzeigen.<br/>**Pfaddimension**: Fügen Sie eine Dimension hinzu, die als Pfad verwendet werden soll, der zu der ausgewählten Komponente führt oder von dieser weg führt."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_In diesem Artikel wird die Flussvisualisierung in {_}![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Siehe [Fluss](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/flow/flow) für die_![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**-Version dieses Artikels._

>[!ENDSHADEBOX]


Die Visualisierung ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Flow]** zeigt Kundenpfade durch Ihre Websites und Programme.

Mit der Visualisierung können Sie:

* Visualisieren Sie die Kunden-Journey über Ihre Website oder Ihr Programm.
* Analysieren, wo Kunden vor und nach bestimmten Checkpoints wie Eintritt, bestimmter Dimension oder Austritt navigieren.
* Erstellen Sie Filter, indem Sie einen bestimmten Punkt in einem ausgewählten Pfad angeben.


>[!BEGINSHADEBOX]

Siehe ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Erstellen einer Flussvisualisierung](https://video.tv.adobe.com/v/346063/?quality=12&learn=on){target="_blank"} für ein Demovideo.

{{videoaa}}

>[!ENDSHADEBOX]


## Interdimensionale Flüsse

Sie können den [Fluss zwischen Dimensionen](/help/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md) anzeigen. So können Sie beispielsweise in einem Diagramm Seiten mit Abteilungen kombinieren. In diesem Fall würde der Fluss von der Startseite zur Seite „Männer“ und dann zur Abteilung „Schuhe“ verlaufen.

Jede Spalte könnte eine andere Dimension anzeigen. Ziehen Sie einen Dimension per Drag-and-Drop in eine Dropzone, um diese Dimension zum Diagramm hinzuzufügen.

>[!MORELIKETHIS]
>
>[Flussvisualisierung konfigurieren](/help/analysis-workspace/visualizations/c-flow/create-flow.md).
>

## Wählen Sie zwischen Flow-, Fallout- oder Journey-Arbeitsflächen-Visualisierungen

Die Flussvisualisierung weist Ähnlichkeiten mit der [Fallout-Visualisierung](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) und der [Journey-](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) auf, jedoch mit wichtigen Unterschieden.

### Unterschiede verstehen

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### Verwendung von Flow

Flussvisualisierungen eignen sich am besten für:

* Explorative Ad-hoc-Analyse für den unmittelbar nächsten Touchpoint auf dem Pfad. (Verwenden Sie die Journey-Arbeitsfläche für Journeys mit einer vordefinierten Seitensequenz oder für Seiten, die einen eventuellen Pfad verwenden.)

* Nichtlineare Journey mit mehreren Einstiegspunkten und Pfaden. (Verwenden Sie die Journey-Arbeitsfläche für Journey mit einer vordefinierten Seitensequenz.)

Verwenden Sie [Tabelle oben](#understand-the-differences) um die Unterschiede zwischen Fluss-, Fallout- und Journey-Arbeitsfläche zu verstehen.
