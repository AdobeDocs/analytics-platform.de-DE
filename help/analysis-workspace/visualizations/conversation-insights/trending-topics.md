---
description: Verwenden Sie die Visualisierung von Trendthemen, um Trendthemen in Konversationen zu erkunden.
title: Trend-Themen
feature: Visualizations
role: User
hide: true
source-git-commit: 137dba69c8827f3b67d5656760d7715437c58b73
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 5%
---

# Trend-Themen

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

## Erstellen und konfigurieren

So erstellen und konfigurieren Sie eine Visualisierung von Trend-Themen:

1. Fügen Sie ![ Visualisierung ](/help/assets/icons/Feed.svg)Feed **[!UICONTROL Trendthemen]** hinzu. Weitere Informationen finden Sie unter [Hinzufügen einer Visualisierung in einem Bedienfeld](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. In den **[!UICONTROL Trending Topics]** Visualisierungskonfiguration:

   1. Wählen Sie eine **[!UICONTROL Rangfolgenmetrik]**. Beispiel: **[!UICONTROL Konversationen]**.
   1. Wählen Sie optional **[!UICONTROL Attribution festlegen]** und wählen Sie **[!UICONTROL Modell]**, **[!UICONTROL Container]** und **[!UICONTROL Lookback-Fenster]**.
   1. Wählen Sie eine Ebene für **[!UICONTROL Unterthemenebenen begrenzen]** aus. Der Standardwert ist **[!UICONTROL Stufe 5]**.

      >[!NOTE]
      >
      >Die **[!UICONTROL Unterthemenebene begrenzen]** definiert die maximale Anzahl von Ebenen, die für Themen in der Visualisierung aufgeschlüsselt werden. Wenn auf einer Ebene innerhalb dieser definierten maximalen Anzahl keine Themen mehr verfügbar sind, wird ![DataUnavailable](/help/assets/icons/DataUnavailable.svg) **[!UICONTROL No topics found]** angezeigt.

1. Wählen **[!UICONTROL Erstellen]**, um die Visualisierung zu erstellen. Wählen **[!UICONTROL Zurücksetzen]**, um die Konfigurationswerte auf die Standardwerte zurückzusetzen.

Um die Visualisierung der Trendthemen neu zu konfigurieren, wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) neben **[!UICONTROL Rangfolgenmetrik: _Rangfolgenmetrik_ | Unterthemenebenen: _x_]**.

## Verwenden

So verwenden Sie die Visualisierung:

* Um einen Drilldown durchzuführen und Trends von Unterthemen für ein Thema auf einer niedrigeren Ebene anzuzeigen, wählen Sie ein Thema auf einer bestimmten Ebene aus.

* Um Themen mit einem anderen Datumsbereich zu vergleichen, wählen Sie einen Datumsbereich von Vergleichen mit aus. So verwenden Sie einen benutzerdefinierten Datumsbereich:
  * Wählen Sie im Dropdown-Menü Benutzerdefinierter Datumsbereich aus und definieren und speichern Sie im Dialogfeld Neuer Datumsbereich einen benutzerdefinierten Datumsbereich.
  * Wählen Sie diesen benutzerdefinierten Datumsbereich aus.

* Um ein Liniendiagramm für die aktuelle Themenauswahl anzuzeigen, legen Sie eine [Linien](/help/analysis-workspace/visualizations/line.md)-Visualisierung in der **[!UICONTROL Trendthemen]**-Visualisierung ab. Die **[!UICONTROL Line]**-Visualisierung ist automatisch mit der **[!UICONTROL Trendthemen]**-Visualisierung verknüpft.

## Einstellungen

Die folgenden spezifischen [Visualisierungseinstellungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings) sind verfügbar.

| Einstellung | Beschreibung |
|---|---|
| **[!UICONTROL Tatsächlichen Wert anzeigen]** | Zeigt den tatsächlichen Wert für ein Thema an. |
| **[!UICONTROL Prozentsatz anzeigen]** | Zeigt den Prozentsatz für ein Thema an. |



