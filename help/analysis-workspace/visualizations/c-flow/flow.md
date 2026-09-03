---
description: Erfahren Sie, wie Sie die Flussvisualisierung in Analysis Workspace verwenden.
title: Flussübersicht
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
autotag-review: '2026-05-19T08:39:33.544Z'
TQID: 'https://experienceleague.adobe.com/X0VLZhluDR9Q-ax7TcTOHEcn4r0V5yu64spZlfc4fwU'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 349
ht-degree: 75%

---

# Flussübersicht {#flow}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_flow_button"
>title="Fluss"
>abstract="Erstellen Sie eine Visualisierung, um den Personenfluss von einem Checkpoint zum nächsten anzuzeigen."

>[!CONTEXTUALHELP]
>id="workspace_flow_panel"
>title="Fluss"
>abstract="Analysieren Sie den Besuchs- oder Besucherfluss von einem Touchpoint zum nächsten. Geben Sie eine Komponente (Metrik, Dimension oder Element) für den Beginn und für das Ende an. Optional können Sie erweiterte Einstellungen definieren, um die Visualisierung noch genauer zu konfigurieren."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_In diesem Artikel wird die Flussvisualisierung in_![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Siehe [Flow](https://experienceleague.adobe.com/de/docs/analytics/analyze/analysis-workspace/visualizations/flow/flow)_ für die ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** Version dieses Artikels._

>[!ENDSHADEBOX]


Die ![GraphPathing](/help/assets/icons/GraphPathing.svg) Visualisierung **[!UICONTROL Fluss]** zeigt Kundenpfade durch Ihre Websites und Programme an.

Mit der Visualisierung können Sie:

* Die Customer Journey durch Ihre Website oder Ihr Programm visualisieren.
* Analysieren, wohin Kundinnen und Kunden vor und nach festgelegten Checkpoints navigieren, wie zum Beispiel Einstieg, eine bestimmte Dimension oder Ausstieg.
* Erstellen Sie Segmente, indem Sie einen bestimmten Punkt in einem ausgewählten Pfad angeben.


>[!BEGINSHADEBOX]

Unter ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Erstellen einer Visualisierung „Fluss“](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/flow-visualization){target="_blank"} finden Sie ein Demovideo.

{{videoaa}}

>[!ENDSHADEBOX]


## Interdimensionale Flüsse

Sie können den [Fluss zwischen Dimensionen](/help/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md) anzeigen. So können Sie beispielsweise in einem Diagramm Seiten mit Abteilungen kombinieren. In diesem Fall geht der Fluss möglicherweise von der Startseite zur Seite „Männer“ und dann zur Abteilung „Schuhe“.

Jede Spalte kann eine andere Dimension aufweisen. Ziehen Sie einen Dimension per Drag-and-Drop in eine Dropzone, um diese Dimension zum Diagramm hinzuzufügen.

>[!MORELIKETHIS]
>
>[Konfigurieren einer Visualisierung „Fluss“](/help/analysis-workspace/visualizations/c-flow/create-flow.md).
>

## Wählen Sie zwischen den Visualisierungen „Fluss“, „Fallout“ oder „Journey-Arbeitsfläche“

Die Visualisierung „Fluss“ weist Ähnlichkeiten mit der Visualisierung [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) und der Visualisierung [Journey-Arbeitsflächen](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) auf, jedoch mit wichtigen Unterschieden.

### Informationen zu den Unterschieden

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### Wann „Fluss“ eingesetzt werden sollte

Visualisierungen vom Typ „Fluss“ eignen sich am besten für:

* Explorative Ad-hoc-Analysen für den unmittelbar nächsten Touchpoint auf dem Pfad. (Verwenden Sie die Journey-Arbeitsfläche für Journeys mit einer vordefinierten Seitensequenz oder für Seiten, die einen endgültigen Pfad verwenden.)

* Nichtlineare Journey mit mehreren Einstiegspunkten und Pfaden. (Verwenden Sie die Journey-Arbeitsfläche für Journeys mit einer vordefinierten Seitensequenz.)

Verwenden Sie [die Tabelle oben](#understand-the-differences), um die Unterschiede zwischen Fluss-, Fallout- und Journey-Arbeitsfläche zu verstehen.
