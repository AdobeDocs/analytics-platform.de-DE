---
title: Konfiguration von Conversation Insights verwalten
description: Erfahren Sie, wie Sie Conversation Insights-Konfigurationen verwalten.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: b29ee2f04a1775dca6a8fd93c3ac3050b67f0ceb
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 6%
---
# Konfigurationen verwalten

Nachdem Sie [Conversation Insights-Konfigurationen erstellt haben](/help/conversation-insights/conversation-insights-configure.md) können Sie diese Konfigurationen anzeigen, bearbeiten oder löschen.

Nur Systemadministratoren können Conversation Insights-Konfigurationen verwalten.

Weitere Informationen zu Conversation Insights finden Sie unter [Conversation Insights - Übersicht](/help/conversation-insights/conversation-insights-overview.md).

## Anzeigen und Filtern vorhandener Konfigurationen

So zeigen Sie Ihre vorhandenen Conversation Insights-Konfigurationen an:

1. Wählen Sie in Customer Journey Analytics **[!UICONTROL Daten-Management]** > **[!UICONTROL Konversationseinblicke-Konfiguration]** aus.

   ![Übersicht über Conversation Insights-Konfigurationen](assets/conversation-insights-configurations.png)

   Die folgenden Informationsspalten sind zu jeder Konfiguration verfügbar:

   * **[!UICONTROL Name]**: Der Name der Conversation Insights-Konfiguration.
   * **[!UICONTROL Erstellt von]**: Der Benutzer, der die Konfiguration erstellt hat.

   * **[!UICONTROL Sandbox]**: Die Experience Platform-Sandbox mit dem Profildatensatz, den Sie Ihrer Verbindung hinzugefügt haben.

   * **[!UICONTROL Verbindung]**: Die Verbindung, die Sie Ihrer Konfiguration hinzugefügt haben.

   * **[!UICONTROL Erstellungsdatum]**: Datum und Uhrzeit der Erstellung der Konfiguration.

   * **[!UICONTROL Zuletzt geändert]**: Das Datum, an dem die Konfiguration zuletzt geändert wurde.

   * **[!UICONTROL Status]**: Der Status der Konfiguration. Mögliche Werte sind:
     ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Complete]**, ![StatusBlue](/help/assets/icons/StatusBlue.svg) **[!UICONTROL Pending]** oder ![](/help/assets/icons/StatusRed.svg) StatusRed **[!UICONTROL Failed]**.

   Um zu konfigurieren, welche Spalten in der Tabelle angezeigt werden sollen, wählen Sie ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) aus. Wählen **[!UICONTROL Dialogfeld „Tabelle anpassen]** die anzuzeigenden Spalten aus. Wählen Sie dann **[!UICONTROL Übernehmen]** aus.

1. (Optional) Um die Liste der Konfigurationen zu filtern, wählen ![Filtern](/help/assets/icons/Filter.svg) und dann nach einem der folgenden Kriterien filtern:

   * **[!UICONTROL Verbindung]**

   * **[!UICONTROL Erstellt von]**

   * **[!UICONTROL Sandbox]**

   * **[!UICONTROL Status]**

## Erstellen einer Konfiguration

So erstellen Sie eine neue Konfiguration für Conversation Insights:

1. Wählen Sie **[!UICONTROL Konfiguration erstellen]** aus.
1. Verwenden Sie das Dialogfeld [**[!UICONTROL Konfiguration erstellen]**](./conversation-insights-configure.md), um Konversationseinblicke zu konfigurieren.

## Bearbeiten einer Konfiguration

So bearbeiten Sie eine vorhandene Conversation Insights-Konfiguration:

1. Führen Sie einen der folgenden Schritte aus:

   * Wählen Sie den Namen der Konfiguration aus, die Sie bearbeiten möchten.
   * Aktivieren Sie das Kontrollkästchen neben der Konfiguration, die Sie bearbeiten möchten, und wählen Sie dann ![ blaue Aktionsleiste ](/help/assets/icons/Edit.svg)Bearbeiten **[!UICONTROL Bearbeiten]** aus.
   * Wählen Sie ![Mehr](/help/assets/icons/More.svg) für die Konfiguration aus, die Sie bearbeiten möchten. Wählen Sie im Kontextmenü die Option ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]** aus.

1. Verwenden Sie das [**[!UICONTROL Konfiguration / _Name der Konfiguration_]**](./conversation-insights-configure.md), um Konversationseinblicke zu konfigurieren.

## Löschen einer Konfiguration

So löschen Sie eine vorhandene Conversation Insights-Konfiguration:

1. Führen Sie einen der folgenden Schritte aus:

   * Aktivieren Sie das Kontrollkästchen neben der Konfiguration, die Sie löschen möchten, und wählen Sie dann ![ blaue Aktionsleiste ](/help/assets/icons/Delete.svg)Löschen **** aus.
   * Wählen Sie ![Mehr](/help/assets/icons/More.svg) für die Konfiguration aus, die Sie bearbeiten möchten. Wählen Sie im Kontextmenü die Option ![Löschen](/help/assets/icons/Delete.svg) **[!UICONTROL Löschen]** aus.

1. Wählen Sie im Dialogfeld **[!UICONTROL Konfiguration löschen]** die Option **[!UICONTROL Löschen]** aus, um die Konfiguration zu löschen. Wählen Sie zum Abbrechen **[!UICONTROL Abbrechen]** aus.
