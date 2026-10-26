---
description: Verwenden Sie die Visualisierung von Trendthemen, um Trendthemen in Konversationen zu erkunden.
title: Trend-Themen
feature: Visualizations
role: User
hide: true
source-git-commit: 85311bf19368560ef54a3361edf2e7c13590929c
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 8%
---
# Trend-Themen {#trending-topics}

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_button"
>title="Trend-Themen"
>abstract="Erstellen Sie eine Visualisierung, die eine hierarchische Aufschlüsselung der Trend-Themen mit Vorkommen und Prozentsätzen zeigt, damit Sie wichtige Themen in Konversationen identifizieren können."

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_panel"
>title="Trend-Themen"
>abstract="Analyse von Trend-Themen basierend auf der ausgewählten Rangfolgenmetrik Wählen Sie Themen aus, um einen Drilldown in bis zu fünf Ebenen durchzuführen. Suchen Sie nach bestimmten Themen und vergleichen Sie Themen mit anderen Datumsbereichen."

Die ![Feed](/help/assets/icons/Feed.svg)**[!UICONTROL Trendthemen]**-Visualisierung ermöglicht es Ihnen, die Trendthemen im Rahmen von Conversation Insights zu untersuchen und zu analysieren.

Sie können nach bestimmten Themen suchen und die Anzahl und den Prozentsatz für jedes Thema auf jeder Ebene mit anderen Datenbereichen vergleichen.

## Erstellen und konfigurieren {#trendimg-topics-create-and-configure}

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_usenondefaultattributionmodel"
>title="Nicht standardmäßiges Attribution-Modell verwenden"
>abstract="Aktivieren Sie ein nicht standardmäßiges Attributionsmodell für diese Metrik."

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_usenondefaultattributionmodel_disabled"
>title="Nicht standardmäßiges Attribution-Modell verwenden"
>abstract="Nicht-Standard-Attributionsmodelle sind für diese Metrik nicht verfügbar."

So erstellen und konfigurieren Sie eine **[!UICONTROL Trendthemen]**-Visualisierung:

1. Fügen Sie ![ Visualisierung ](/help/assets/icons/Feed.svg)Feed **[!UICONTROL Trendthemen]** hinzu. Weitere Informationen finden Sie unter [Hinzufügen einer Visualisierung in einem Bedienfeld](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. In den **[!UICONTROL Trending Topics]** Visualisierungskonfiguration:

   1. Wählen Sie eine **[!UICONTROL Rangfolgenmetrik]**. Beispiel: **[!UICONTROL Konversationen]**.
   1. Wenn Sie optional ein nicht standardmäßiges [Attribution](/help/analysis-workspace/attribution/models.md)-Modell für die Metrik verwenden möchten, wählen Sie **[!UICONTROL Nicht standardmäßiges Attributionsmodell verwenden]** und **[!UICONTROL Modell]**, **[!UICONTROL Container]** und **[!UICONTROL Lookback-Fenster]**.
1. Wählen **[!UICONTROL Erstellen]**, um die Visualisierung zu erstellen. Wählen **[!UICONTROL Zurücksetzen]**, um die Konfigurationswerte auf die Standardwerte zurückzusetzen.

Um die Visualisierung der Trendthemen neu zu konfigurieren, wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) neben **[!UICONTROL Rangfolgenmetrik: _Rangfolgenmetrik_ | Unterthemenebenen: _x_]**.

## Verwenden

So verwenden Sie die Visualisierung:

![Verwenden der Visualisierung für Trendthemen](assets/trending-topics.png)

* Bewegen Sie den Mauszeiger über ein Thema, um ein Popup mit weiteren Details anzuzeigen. ➊

* Um Trend-Unterthemen für ein Thema auf einer niedrigeren Ebene anzuzeigen, wählen Sie ein Thema auf einer bestimmten Ebene aus. Wenn auf einer Unterebene keine Themen verfügbar sind, sehen Sie ![DataRemove](/help/assets/icons/DataRemove.svg) **[!UICONTROL Keine Unterthemen gefunden für _topic > Unterthema > …]**.

* Verwenden Sie ![Suche](/help/assets/icons/Search.svg) **[!UICONTROL _Suchthemen_]**, um schnell nach Themen zu suchen. ➋

* Um Themen mit einem anderen Datumsbereich zu vergleichen, wählen Sie einen Datumsbereich aus **[!UICONTROL Vergleichen mit]**. ➌

  So verwenden Sie einen benutzerdefinierten Datumsbereich:

  * Wählen Sie **[!UICONTROL Benutzerdefinierter Datumsbereich]** aus dem Dropdown-Menü aus und definieren und speichern Sie **[!UICONTROL Dialogfeld „Neuer]**&quot; einen benutzerdefinierten Datumsbereich.
  * Wählen Sie diesen benutzerdefinierten Datumsbereich aus.

* Um ein Liniendiagramm für die aktuelle Themenauswahl anzuzeigen, legen Sie eine [Linien](/help/analysis-workspace/visualizations/line.md)-Visualisierung in der **[!UICONTROL Trendthemen]**-Visualisierung ab. Die **[!UICONTROL Linie]**-Visualisierung wird automatisch mit der **[!UICONTROL Trendthemen]**-Visualisierung verknüpft und zeigt eine Linie für das ausgewählte Thema an.

  ![Trending Topic Line Visualization](assets/trending-topics-line-viz.png)

## Einstellungen

Die folgenden spezifischen [Visualisierungseinstellungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings) sind verfügbar.

| Einstellung | Beschreibung |
|---|---|
| **[!UICONTROL Tatsächlichen Wert anzeigen]** | Zeigt den tatsächlichen Wert für ein Thema an. |
| **[!UICONTROL Prozentsatz anzeigen]** | Zeigt den Prozentsatz für ein Thema an. |
