---
description: Verwenden Sie die Visualisierung der Konversationszusammenfassungen , um Konversationen zusammenzufassen.
title: Konversationszusammenfassungen
feature: Visualizations
role: User
hide: true
source-git-commit: ccaa957e79fba24292316c7447be786f57f03493
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 8%
---
# Konversationszusammenfassungen {#conversation-summaries}

>[!CONTEXTUALHELP]
>id="workspace_conversationsummaries_button"
>title="Konversationszusammenfassungen"
>abstract="Erstellen Sie eine Visualisierung, die eine gefilterte Gruppe von Unterhaltungen zusammenfasst."

>[!CONTEXTUALHELP]
>id="workspace_conversationsummaries_panel"
>title="Konversationszusammenfassungen"
>abstract="Zusammenfassen einer gefilterten Gruppe von Unterhaltungen. Legen Sie die Länge der Zusammenfassung fest. Siehe repräsentative Anführungszeichen von Kunden zur Validierung der Genauigkeit der extrahierten Signale. Wählen Sie ein Angebot aus, um die vollständige Unterhaltungswiederholung zu öffnen."


Mit ![&#x200B; Visualisierung &#x200B;](/help/assets/icons/Summarize.svg)Zusammenfassen **[!UICONTROL Konversationszusammenfassungen]** können Sie eine gefilterte Gruppe von Konversationen zusammenfassen.

Die Visualisierung zeigt eine Zusammenfassung der ausgewählten Metrik (z. B. Konversationen) und zeigt Unterthemen oder wörtliche Kommentare an, wenn Sie die Visualisierung so konfiguriert haben, dass sie Unterthemen enthält.


## Erstellen und konfigurieren {#conversation-summaries-create-configure}

>[!CONTEXTUALHELP]
>id="workspace_conversationsummaries_attribution"
>title="Attribution von Konversationszusammenfassungen"
>abstract="Aktivieren Sie ein nicht standardmäßiges Attribution-Modell für die ausgewählte Metrik."

So erstellen und konfigurieren Sie eine **[!UICONTROL Konversationszusammenfassungen]** Visualisierung:

1. Fügen Sie eine Visualisierung ![Zusammenfassen](/help/assets/icons/Summarize.svg) **[!UICONTROL Konversationszusammenfassungen]** hinzu. Weitere Informationen finden Sie unter [Hinzufügen einer Visualisierung in einem Bedienfeld](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. In der **[!UICONTROL Konversationszusammenfassungen]** Visualisierungskonfiguration:

   1. Wählen Sie eine **[!UICONTROL Metrik]** aus. Beispiel: **[!UICONTROL Konversationen]**.
   1. Wenn Sie optional [Attribution) für die Metrik &#x200B;](/help/analysis-workspace/attribution/models.md) möchten, wählen Sie **[!UICONTROL Attribution festlegen]** und **[!UICONTROL Modell]**, **[!UICONTROL Container]** und **[!UICONTROL Lookback-Fenster]**.
   1. Optional können Sie ein Segment auf die Visualisierung anwenden. Wählen Sie ein Segment aus dem Dropdown **[!UICONTROL Menü]** Segmente“ aus.

1. Wählen **[!UICONTROL Erstellen]**, um die Visualisierung zu erstellen. Wählen **[!UICONTROL Zurücksetzen]**, um die Konfigurationswerte auf die Standardwerte zurückzusetzen. Wählen Sie **[!UICONTROL Abbrechen]**, um die Konfiguration abzubrechen.

Um die Visualisierung **[!UICONTROL Konversationszusammenfassungen]** neu zu konfigurieren, wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) neben **[!UICONTROL Metrik: _metric_]**&#x200B;oder **[!UICONTROL Metrik:_metric_]** | **[!UICONTROL Segmente: _segments_]**.

## Verwenden

So verwenden Sie die Visualisierung:

>[!BEGINTABS]

>[!TAB Unterthemen]

![Unterthemen](assets/conversation-summaries-subtopics.png)

>[!TAB Ausführliche Kommentare]

![Ausführliche Kommentare](assets/conversation-summaries-verbatimcomments.png)

>[!ENDTABS]

* Wenn Sie [Unterthemen eingebunden haben](#settings) wählen Sie **[!UICONTROL Unterthemen]**, um Unterthemen anzuzeigen, oder **[!UICONTROL Ausführliche Kommentare]**, um ausführliche Kommentare anzuzeigen.
* Wenn Sie &quot;**[!UICONTROL Kommentare]** ausgewählt haben, wählen Sie ![DateiSuchen](/help/assets/icons/FileSearch.svg), um eine neue Visualisierung [**[!UICONTROL Konversationsüberprüfung]**](./conversation-review.md) für die spezifische Konversation zu öffnen, zu der der wörtliche Kommentar gehört.

## Einstellungen

Die folgenden spezifischen [Visualisierungseinstellungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings) sind verfügbar.

| Einstellung | Beschreibung |
|---|---|
| **[!UICONTROL Zusammenfassungslänge]** | Geben Sie die Länge der Zusammenfassung an. Sie können zwischen &quot;**[!UICONTROL &quot;]** &quot;**[!UICONTROL &quot;]**. |
| **[!UICONTROL Unterthemen einschließen]** | Wählen **[!UICONTROL Unterthemen einschließen]** aus, um Unterthemen in der Visualisierung anzuzeigen. Verwenden Sie **[!UICONTROL Maximale Anzahl von Unterthemen]** um die maximale Anzahl von Unterthemen zu konfigurieren, die angezeigt werden sollen. |
