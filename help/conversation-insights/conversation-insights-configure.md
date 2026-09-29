---
title: Erstellen oder Bearbeiten einer Conversation Insights-Konfiguration
description: Erfahren Sie, wie Sie Conversation Insights-Konfigurationen konfigurieren.
solution: Customer Journey Analytics
feature: AI Tools
role: Admin, User
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: ae3aff40-b2f6-4df1-8c01-0b0720d1510f
    internal-label: AI Tools
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 4eaf8820fd847426ba6a471e1bfbc7b397283905
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 7%
---
# Erstellen oder Bearbeiten von Konfigurationen

Mit Conversation Insights können Sie Konversationen aus den Agentenerlebnissen analysieren, die Sie Ihren Kunden anbieten. Diese Agentenerlebnisse können auf großen Sprachmodellen (LLM) oder auf menschlichen Konversationen basieren. Beispielsweise ein Chatbot, der mit einem Kunden oder einem Callcenter interagiert.
Mithilfe von Conversation Insights sind Sie in der Lage, die Auswirkungen von Repräsentanten auf tatsächliche Benutzerergebnisse zu verstehen.

Über die Konfigurationsoberfläche für Conversation Insights können Sie schnell eine Konfiguration und die zugehörigen Artefakte (Verbindung, Datenansichten usw.) erstellen oder bearbeiten.

Wenn Sie eine Conversation Insights-Konfiguration erstellen oder bearbeiten, geben Sie die Sandbox und die Ereignis-Datensätze an, die Eingabeaufforderungen, Antworten und Feedback-Daten enthalten. Sie können auch die Customer Journey Analytics-Verbindung auswählen, der Sie diese Datensätze hinzufügen möchten. Und die Datenansicht, der Sie die Metriken und Dimensionen von Conversation Insights hinzufügen möchten.

Nur Systemadministratoren können Conversation Insights-Konfigurationen erstellen oder bearbeiten.

Sie können Konfigurationen über die Benutzeroberfläche „Conversation Insights[Konfigurationen“ erstellen oder &#x200B;](./conversation-insights-manage.md).

## Fehlenden kombinierten Datensatz wiederherstellen

Wenn Sie eine Konfiguration bearbeiten und der für die Konfiguration generierte gemischte Datensatz nicht mehr vorhanden ist, wählen Sie **[!UICONTROL Wiederherstellen]** aus, um den gemischten Datensatz neu zu generieren.


## Konfigurationsschritte

Für jede Konfiguration:

1. Geben **[!UICONTROL im Abschnitt]** die folgenden Informationen an:

   ![Details zu Conversation Insights](assets/conversation-insights-configuration-details.png)

   | Feld | Beschreibung |
   |---------|----------|
   | **[!UICONTROL Name]** | Geben Sie einen Namen für die Konfiguration an. |
   | **[!UICONTROL Sandbox]** | Wählen Sie die Experience Platform-Sandbox aus, die die Eingabeaufforderungen, Antworten und Feedback-Ereignis-Datensätze enthält, die Sie Ihrer Verbindung hinzufügen möchten. |

1. Geben **[!UICONTROL im Abschnitt]** die folgenden Informationen an:

   ![Conversation Insights-Datensätze](assets/conversation-insights-configuration-datasets.png)

   | Feld | Beschreibung |
   |---------|----------|
   | **[!UICONTROL Eingabeaufforderung für Ereignisdatensatz]** | Wählen Sie den Datensatz aus, der die Eingabeaufforderungsereignisdaten enthält. |
   | **[!UICONTROL Datensatz für Antwortereignisse]** | Wählen Sie den Datensatz aus, der die Ereignisdaten für Antworten enthält. |
   | **[!UICONTROL Feedback-Ereignisdatensatz]** | Wählen Sie den Datensatz aus, der die Feedback-Ereignisdaten enthält. |

1. Wenn im Abschnitt **[!UICONTROL Verbindung]** bereits keine Verbindung konfiguriert ist, wählen Sie mit **[!UICONTROL Verbindung auswählen]** eine Verbindung aus.

   ![Conversation Insights-Verbindung](assets/conversation-insights-configuration-connection.png)

   Wenn eine Verbindung bereits konfiguriert ist, wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]** aus, um eine andere Verbindung auszuwählen.

   ![Conversation Insights - Verbindung bearbeiten](assets/conversation-insights-configuration-edit-connection.png)

   Im Dialogfeld **[!UICONTROL Verbindung auswählen]**:

   ![Conversation Insights - Verbindung auswählen](assets/conversation-insights-configuration-select-connection.png)

   1. Aktivieren Sie das Kontrollkästchen neben der Verbindung, der Sie die Datensätze für Eingabeaufforderungen, Antworten und Feedback-Ereignisse hinzufügen möchten.
   1. Wählen **[!UICONTROL Verbindung verwenden]**.

   * Um in der Liste der auszuwählenden Verbindungen zu suchen, verwenden Sie das Feld ![Suche](/help/assets/icons/Search.svg).
   * Um zu definieren, welche Spalten in der Tabelle angezeigt werden sollen, wählen Sie ![Spalteneinstellungen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) aus. Wählen **[!UICONTROL Dialogfeld „Tabelle anpassen]** die anzuzeigenden Spalten aus. Wählen Sie dann **[!UICONTROL Übernehmen]** aus.

1. Wenn **[!UICONTROL Datenansichten bereits konfiguriert]**, wählen Sie **[!UICONTROL Datenansichten auswählen]** aus, um Datenansichten auszuwählen.

   Wenn Datenansichten bereits konfiguriert sind, wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Datenansichtsauswahl bearbeiten]** aus, um die Auswahl der Datenansichten neu zu konfigurieren.

   Im Dialogfeld **[!UICONTROL Mehrere Datenansichten auswählen]**:

   ![Conversation Insights - Datenansichten auswählen](assets/conversation-insights-configuration-select-data-views.png)

   1. Wählen Sie eine oder mehrere Datenansichten aus, die Sie für die Conversation Insights-Konfiguration verwenden möchten.

   1. Wählen **[!UICONTROL Verwenden von Datenansichten]** aus, um die Datenansichten zu verwenden. Wählen Sie zum Abbrechen die Option „Abbrechen“ aus.

   * Um in der Liste der auszuwählenden Datenansichten zu suchen, verwenden Sie das Feld ![Suche](/help/assets/icons/Search.svg).
   * Um zu definieren, welche Spalten in der Tabelle angezeigt werden sollen, wählen Sie ![Spalteneinstellungen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) aus. Wählen **[!UICONTROL Dialogfeld „Tabelle anpassen]** die anzuzeigenden Spalten aus. Wählen Sie dann **[!UICONTROL Übernehmen]** aus.

1. So beenden Sie die Konfiguration:

   * Wählen Sie **[!UICONTROL Verwerfen]** für eine neue Konfiguration aus, die nicht erstellt wird.

   * Wählen Sie **[!UICONTROL Für später speichern]** für eine neue Konfiguration aus, die Sie speichern möchten, für die Sie jedoch kein Artefakt erstellen möchten (z. B. Aktualisierungen an Datenansichten). Sie können die Konfiguration später erneut aufrufen und die tatsächliche Erstellung der Konfiguration abschließen.

   * Wählen **[!UICONTROL Erstellen]** aus, um die neue Konfiguration zu erstellen.

   * Klicken Sie **[!UICONTROL Speichern]**, um die geänderte Konfiguration zu speichern.

   * Wählen Sie **[!UICONTROL Wiederherstellen]** aus, um die Konfiguration wiederherzustellen und einen neuen gemischten Datensatz für die Konfiguration neu zu generieren.

   * Wählen Sie **[!UICONTROL Beenden]** aus, um alle Änderungen an der Konfiguration zu ignorieren.


## Verifizierung der Datenansicht

(Beschreiben Sie die Metriken und Dimensionen, die Sie in den entsprechenden Datensätzen sehen.)


<!--

1. In the Data views dialog, select the checkbox next to one or more data views that you want to use when analyzing Experience Platform audience data within Analysis Workspace. These data views are automatically configured with Experience Platform audience data for reporting.

1. Select **[!UICONTROL Use data views]**.

1. Select **[!UICONTROL Create]** to create the configuration.

   >[!IMPORTANT]
   >
   >Because the profile dataset is updated once per day, audiences are available in Customer Journey Analytics data views on the day after you create the audience analysis configuration.


1. After 24 hours, [view audience dimensions in the data view](#view-audience-dimensions-in-the-data-view) to verify that the audience dimensions are available in the data views that you selected. 


 
## View audience dimensions in the data view

After you [create an audience analysis configuration](#create-an-audience-analysis-configuration), you can verify that audience dimensions were added to the data views that you selected during the configuration.

To view audience dimensions in the data view, you must be a product profile administrator for the product profile that the data view is assigned to. For more information, see [Access control](/help/technotes/access-control.md).

To view the audience analysis dimensions in the data view:

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Data views]**.

1. In the **[!UICONTROL Dimensions]** section, the following dimensions should now be available:

   * **[!UICONTROL Audience Name]**

   * **[!UICONTROL Audience Origin]**

   * **[!UICONTROL Exited Audience Origin]**

   * **[!UICONTROL Exited Audience Name]**

   Note that each of these dimensions was added to the profile dataset that is associated with the merge policy that you selected during the audience analysis configuration, and each was added to the new lookup dataset that was created.

   ![Audience dimensions available in the data view](assets/audience-analysis-dataview-dataset.png)

1. Use the audience analysis dimensions in Analysis Workspace. 

   Users who have access to use the data view in Analysis Workspace can now see the new dimensions and use them in their analyses. For information about how to use the audience analysis dimensions in Analysis Workspace, see [Analyze Experience Platform audiences in Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).

-->