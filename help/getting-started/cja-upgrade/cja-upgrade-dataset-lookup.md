---
title: Erstellen von Lookup-Datensätzen zum Klassifizieren von Daten in Customer Journey Analytics
description: Erfahren Sie, wie Sie Lookup-Datensätze erstellen, um Daten in Customer Journey Analytics zu klassifizieren
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f5443ddd-81d0-43cc-99cb-215e7ddf5acf
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 96%

---

# Erstellen von Lookup-Datensätzen zum Klassifizieren von Daten in Customer Journey Analytics {#upgrade-lookup-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-lookup-dataset-create"
>title="Erstellen eines Lookup-Datensatzes für jede Dimension mit Klassifizierungsdaten"
>abstract="Ähnlich wie Klassifizierungsdaten in Adobe Analytics sind Lookup-Datensätze die Methode zum Klassifizieren von Daten in Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Ähnlich wie Klassifizierungsdaten in Adobe Analytics sind Lookup-Datensätze die Methode zum Klassifizieren von Daten in Customer Journey Analytics.

Bei Verwendung des Analytics-Quell-Connectors werden einige standardmäßige Lookup-Datensätze zum Zeitpunkt der Berichterstellung automatisch angewendet. Weitere Informationen finden Sie unter [Hinzufügen von Standardsuchen zu Ihren Datensätzen](/help/connections/standard-lookups.md).

Um Daten in Customer Journey Analytics bei Verwendung des Experience Platform Web SDK zu klassifizieren, müssen Sie ein benutzerdefiniertes Schema und einen Lookup-Datensatz für jede Dimension erstellen, die zu klassifizierende Daten enthält.

## Erstellen eines benutzerdefinierten Schemas für den Lookup-Datensatz

Erstellen Sie ein neues benutzerdefiniertes Schema für jede Dimension, die Daten enthält, die in Customer Journey Analytics klassifiziert werden sollen. Wenn Sie den Lookup-Datensatz in einem späteren Schritt erstellen, verweist er auf dieses Schema.

Wiederholen Sie diesen Vorgang für jede Dimension, die zu klassifizierende Daten enthält.

So erstellen Sie ein Schema für einen Lookup-Datensatz in Customer Journey Analytics:

1. Wählen Sie in Adobe Experience Platform im Abschnitt **[!UICONTROL Daten-Management]** in der linken Leiste die Option **[!UICONTROL Schemata]** aus.

1. Wählen Sie **[!UICONTROL Schema erstellen]** aus.

   ![Schaltfläche Schema erstellen](assets/schema-create.png)

1. Wählen Sie **[!UICONTROL Manuell]** aus. Dadurch können Sie Ihrem Schema manuell Felder und Feldergruppen hinzufügen. Wählen Sie **[!UICONTROL Auswählen]**, um mit der nächsten Seite des Erstellungsassistenten fortzufahren.

1. Wählen Sie auf der Seite **[!UICONTROL Schemadetails]** die Option **[!UICONTROL Sonstige]** und dann **[!UICONTROL Benutzerdefiniert]** aus.

   ![Benutzerdefinierte Erstellung](assets/schema-custom.png)

1. Wählen Sie **[!UICONTROL Klasse erstellen]** aus.

   <!-- add screenshot -->

1. Geben Sie im Dialogfeld **[!UICONTROL Klasse erstellen]** einen Namen und eine Beschreibung für das Schema an. Wählen Sie **[!UICONTROL Eintrag]** und dann **[!UICONTROL Erstellen]** aus.

1. Fahren Sie mit [Erstellen eines Lookup-Datensatzes](#create-a-lookup-dataset) fort.

## Erstellen eines Lookup-Datensatzes

Nach der [Erstellung eines benutzerdefiniertes Schemas](#create-a-custom-schema-to-use-with-the-lookup-dataset) für einen Lookup-Datensatz müssen Sie den Lookup-Datensatz erstellen und Ihrem Schema zuordnen.

Wiederholen Sie diesen Vorgang für jede Dimension, die zu klassifizierende Daten enthält.

So erstellen Sie einen Lookup-Datensatz für ein Schema in Customer Journey Analytics:

>[!NOTE]
>
>Beim folgenden Prozess wird eine CSV-Datei verwendet, um den Datensatz zu erstellen. Sie können auch eine andere Methode verwenden, die für den Import von Daten in Experience Platform verfügbar ist, z. B. die Einrichtung eines Datenstroms.

1. Wählen Sie in Adobe Experience Platform die Option **[!UICONTROL Workflows]** in der linken Leiste aus.

   ![Benutzerdefinierte Erstellung](assets/lookup-dataset-workflows.png)

1. Wählen Sie **[!UICONTROL CSV-Datei einem XDM-Schema zuordnen]** und dann **[!UICONTROL Starten]** aus.

1. Wählen Sie im Abschnitt **[!UICONTROL Datensatz-Details]** die Option **[!UICONTROL Neuer Datensatz]** aus.

1. Geben Sie einen Namen und eine Beschreibung für den Datensatz an.

1. Wählen Sie im Feld **[!UICONTROL Schema]** das Schema aus, das Sie für Lookup-Datensätze erstellt haben, wie unter [Erstellen eines Schemas für Lookup-Datensätze](#create-a-schema-for-lookup-datasets) beschrieben.

1. Klicken Sie auf **[!UICONTROL Weiter]**.

1. Wählen Sie auf der Seite **[!UICONTROL CSV-Datei einem XDM-Schema zuordnen]** im Abschnitt **[!UICONTROL Dateien hochladen]** die Option **[!UICONTROL Dateien auswählen]** aus und durchsuchen Sie dann Ihr Dateisystem nach der Datei mit den Klassifizierungsinformationen für die Dimension, für die Klassifizierungsdaten angewendet werden sollen. Dies kann beispielsweise eine Tabelle sein, in der die Feld-IDs und die entsprechenden Feldnamen aufgelistet sind. <!-- correct? How can I better explain what this file is?-->

   ![Zuordnen der CSV-Datei](assets/lookup-map-csv.png)

1. Wählen Sie **[!UICONTROL Weiter]** aus

1. Überprüfen Sie nach dem Datei-Upload die Zuordnungen, um sicherzustellen, dass sie korrekt sind. Die Spalten der CSV-Datei werden unter **[!UICONTROL Quelldaten]** aufgeführt, die entsprechenden XDM-Schemafelder unter **[!UICONTROL Zielfeld]**.

   Platform bietet automatisch intelligente Empfehlungen für automatisch zugeordnete Felder, die auf dem von Ihnen ausgewählten Zielschema oder Datensatz basieren. Sie können die Zuordnungsregeln manuell an Ihre Anwendungsfälle anpassen.

   Weitere Informationen zum Zuordnungsprozess finden Sie unter [Zuordnen einer CSV-Datei zu einem vorhandenen XDM-Schema](https://experienceleague.adobe.com/de/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema) in der Dokumentation zu Experience Platform.

1. Wählen Sie **[!UICONTROL Beenden]** aus.

1. Fahren Sie mit [Hinzufügen des Lookup-Datensatzes zu Ihrer Verbindung in Customer Journey Analytics](#add-the-lookup-dataset-to-your-connection-in-customer-journey-analytics) fort.

## Hinzufügen des Lookup-Datensatzes zu Ihrer Verbindung in Customer Journey Analytics

Nachdem Sie [ein benutzerdefiniertes Schema erstellt](#create-a-custom-schema-to-use-with-the-lookup-dataset) und [einen Lookup-Datensatz erstellt](#create-a-lookup-dataset) haben, müssen Sie den Lookup-Datensatz zu Ihrer Verbindung in Customer Journey Analytics hinzufügen.

Wiederholen Sie diesen Vorgang für jede Dimension, die zu klassifizierende Daten enthält.

So fügen Sie den Lookup-Datensatz zu Ihrer Verbindung in Customer Journey Analytics hinzu:

1. Wählen Sie in Customer Journey Analytics **[!UICONTROL Verbindungen]**, optional unter **[!UICONTROL Datenverwaltung]** im oberen Menü aus.

1. Wählen Sie ![Mehr-Symbol](assets/More.svg) neben der Verbindung, der Sie den Lookup-Datensatz hinzufügen möchten, und klicken Sie dann auf **[!UICONTROL Bearbeiten]**.

   <!-- add screenshot -->

1. Wählen Sie **[!UICONTROL Datensätze hinzufügen]** aus.

1. Wählen Sie im Dialogfeld **[!UICONTROL Datensätze hinzufügen]** den von Ihnen erstellten Lookup-Datensatz hinzu und wählen Sie dann **[!UICONTROL Weiter]**.

1. Wählen Sie im Feld **[!UICONTROL Personen-ID]** eine Personen-ID aus den verfügbaren Identitäten aus, die in dem Datensatzschema definiert sind, das Sie in Experience Platform konfiguriert haben. <!-- fill out other fields? -->

1. Wählen Sie **[!UICONTROL Datensätze hinzufügen]** und dann **[!UICONTROL Speichern]** aus.

   <!-- is there a step right in between here where you select the dataset -->

1. Erstellen Sie mithilfe des Felds **[!UICONTROL Schlüssel]** und des Felds **[!UICONTROL Passender Schlüssel]** eine Korrelation zwischen dem Feld in Ihrem Lookup-Datensatz und dem Feld in Ihrem Ereignis- oder Zusammenfassungsdatensatz.

1. Wiederholen Sie diesen Vorgang, bis alle Lookup-Datensätze zu Ihrer Verbindung in Customer Journey Analytics hinzugefügt werden.

{{upgrade-final-step}}

