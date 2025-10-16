---
title: Zuordnung verwenden
description: Verwendung von Stitching
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
hide: true
hidefromtoc: true
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: c4aea74807be15af56413522d9e6fbf5f18a37a0
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 1%

---

# Zuordnung verwenden

Sie können das Zusammenfügen mit einem oder mehreren Ereignisdatensätzen aktivieren, die Sie im Rahmen Ihrer Verbindung konfiguriert haben. Die Anzahl der Ereignis-Datensätze, die Sie für das Zusammenfügen aktivieren können, wird durch das lizenzierte Customer Journey Analytics-Paket bestimmt.

Sie können das Zusammenfügen als Teil der [Datensatzeinstellungen](/help/connections/create-connection.md#dataset-settings) für einen Ereignisdatensatz aktivieren, wenn Sie [Verbindung erstellen](/help/connections/create-connection.md) oder [Verbindung bearbeiten](/help/connections/manage-connections.md#edit-a-connection).

Um das Zusammenfügen zu aktivieren, gehen Sie im Abschnitt Ereignisdatensatz des Dialogfelds **[!UICONTROL Datensätze hinzufügen]** oder **[!UICONTROL Datensatz bearbeiten]** folgendermaßen vor:

![Optionen für die Identitätszuordnung beim Aktivieren der Identitätszuordnung](assets/identity-stitching-ui.png)

1. Wählen Sie **[!UICONTROL Identitätszusammenfügung aktivieren]** aus.

   Wenn Sie die Zuordnung für einen vorhandenen Ereignisdatensatz aktivieren, zeigt das Dialogfeld **[!UICONTROL Personen-ID ändern]** die Auswirkungen einer Änderung der Personen-ID aufgrund der Verwendung der Zuordnung an. Wählen Sie **[!UICONTROL Weiter]** aus, um fortzufahren.

   Das **[!UICONTROL „Identitätszuordnung aktivieren]** fasst die Auswirkungen des Zuordnens von Identitäten zusammen. Wählen Sie **[!UICONTROL Weiter]** aus, um fortzufahren.

1. Wählen Sie eine persistente ID aus **[!UICONTROL Dropdown-Menü]** Persistente ID“ aus.

   Wenn Sie **[!UICONTROL Identitätszuordnung]** für die persistente ID auswählen, müssen Sie einen Namespace auswählen. Sie haben zwei Möglichkeiten:

   * Aktivieren Sie **[!UICONTROL Primären Identity-Namespace verwenden]**, um den primären Identity-Namespace zu verwenden.
   * Wählen Sie einen Namespace aus dem **[!UICONTROL Namespace]** Dropdown-Menü aus.

1. Wählen Sie eine Personen-ID aus **[!UICONTROL Dropdown]** Menü „Personen-ID“ aus.

   Wenn Sie **[!UICONTROL Identitätszuordnung]** für die Personen-ID auswählen, müssen Sie einen Namespace auswählen. Sie haben zwei Möglichkeiten:

   * Aktivieren Sie **[!UICONTROL Primären Identity-Namespace verwenden]**, um den primären Identity-Namespace zu verwenden.
   * Wählen Sie einen Namespace aus dem **[!UICONTROL Namespace]** Dropdown-Menü aus.


   Wenn Sie **[!UICONTROL Identitätsdiagramm]** für die Personen-ID auswählen, müssen Sie einen Namespace auswählen.

   >[!NOTE]
   >
   >Sie müssen berechtigt sein, das Identitätsdiagramm zu verwenden.
   >

   Zuvor wird ein Dialogfeld **[!UICONTROL Änderung am Identitätsdiagramm]** angezeigt, um sicherzustellen, dass Sie [die Einrichtung des Identitätsdiagramms für den Datensatz abgeschlossen haben](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) bevor Sie das Identitätsdiagramm zum Zusammenfügen verwenden. Wählen Sie **[!UICONTROL Weiter]** aus, um fortzufahren.

   * Wählen Sie einen Namespace aus dem **[!UICONTROL Namespace]** Dropdown-Menü aus.


1. Wählen Sie ein Lookback-Fenster aus **[!UICONTROL Dropdown-Menü]** Lookback-Fenster“. Die verfügbaren Optionen hängen vom Customer Journey Analytics-Paket ab, zu dem Sie berechtigt sind.

Nachdem Sie eine Verbindung gespeichert haben, die Datensätze enthält, die für die Identitätszuordnung aktiviert sind, beginnt der Zuordnungsprozess für jeden Datensatz, wenn die Aufnahme von Daten für diesen Datensatz beginnt.