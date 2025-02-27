---
title: Erstellen von Lookup-Datensätzen zum Klassifizieren von Daten in Customer Journey Analytics
description: Erfahren Sie, wie Sie Such-Datensätze erstellen, um Daten in Customer Journey Analytics zu klassifizieren
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f5443ddd-81d0-43cc-99cb-215e7ddf5acf
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 13%

---

# Erstellen von Lookup-Datensätzen zum Klassifizieren von Daten in Customer Journey Analytics {#upgrade-lookup-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-lookup-dataset-create"
>title="Erstellen eines Lookup-Datensatzes für jede Dimension mit Klassifizierungsdaten"
>abstract="Ähnlich wie Klassifizierungsdaten in Adobe Analytics sind Lookup-Datensätze die Methode zur Klassifizierung von Daten in Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Ähnlich wie Klassifizierungsdaten in Adobe Analytics sind Lookup-Datensätze die Methode zur Klassifizierung von Daten in Customer Journey Analytics.

Bei Verwendung des Analytics-Quell-Connectors werden einige Datensätze für die Standardsuche zum Zeitpunkt der Berichterstellung automatisch angewendet. Weitere Informationen finden Sie unter [Hinzufügen von Standardsuchen zu Ihren Datensätzen](/help/connections/standard-lookups.md).

Um Daten in Customer Journey Analytics bei Verwendung der Experience Platform Web SDK zu klassifizieren, müssen Sie ein benutzerdefiniertes Schema und einen Lookup-Datensatz für jede Dimension erstellen, die Daten enthält, die Sie klassifizieren möchten.

## Erstellen eines benutzerdefinierten Schemas zur Verwendung mit dem Lookup-Datensatz

Erstellen Sie ein neues benutzerdefiniertes Schema für jede Dimension, die Daten enthält, die Sie in Customer Journey Analytics klassifizieren möchten. Wenn Sie den Lookup-Datensatz in einem späteren Schritt erstellen, verweist er auf dieses Schema.

Wiederholen Sie diesen Vorgang für jede Dimension, die Daten enthält, die Sie klassifizieren möchten.

So erstellen Sie ein Schema zur Verwendung mit einem Lookup-Datensatz in Customer Journey Analytics:

1. Wählen Sie in Adobe Experience Platform **[!UICONTROL Schemata]** im Abschnitt **[!UICONTROL Daten-Management]** in der linken Leiste aus.

1. Wählen Sie **[!UICONTROL Schema erstellen]** aus.

   ![Schaltfläche „Schema erstellen“](assets/schema-create.png)

1. Wählen Sie **[!UICONTROL Manuell]** aus. Auf diese Weise können Sie Ihrem Schema manuell Felder und Feldergruppen hinzufügen. Wählen **[!UICONTROL Auswählen]**, um mit der nächsten Seite des Erstellungsassistenten fortzufahren.

1. Wählen Sie auf der **[!UICONTROL Schemadetails]** die Option **[!UICONTROL Sonstige]** und dann **[!UICONTROL Benutzerdefiniert]** aus.

   ![Benutzerdefiniert erstellen](assets/schema-custom.png)

1. Wählen Sie **[!UICONTROL Klasse erstellen]** aus.

   <!-- add screenshot -->

1. Geben **[!UICONTROL im Dialogfeld „Klasse erstellen]** einen Namen und eine Beschreibung für das Schema an, wählen Sie **[!UICONTROL Datensatz]** und dann **[!UICONTROL Erstellen]** aus.

1. Fahren Sie mit [Lookup-Datensatz erstellen](#create-a-lookup-dataset) fort.

## Erstellen eines Lookup-Datensatzes

Nachdem Sie [benutzerdefiniertes Schema erstellen](#create-a-custom-schema-to-use-with-the-lookup-dataset) um für einen Lookup-Datensatz zu verwenden, müssen Sie den Lookup-Datensatz erstellen und ihn Ihrem Schema zuordnen.

Wiederholen Sie diesen Vorgang für jede Dimension, die Daten enthält, die Sie klassifizieren möchten.

So erstellen Sie einen Lookup-Datensatz zur Verwendung mit einem Schema in Customer Journey Analytics:

>[!NOTE]
>
>Der folgende Prozess verwendet eine CSV-Datei, um den Datensatz zu erstellen. Sie können auch jede andere Methode verwenden, die für den Import von Daten in Experience Platform verfügbar ist, z. B. das Einrichten eines Datenstroms.

1. Wählen Sie in Adobe Experience Platform **[!UICONTROL Workflows]** in der linken Leiste aus.

   ![Benutzerdefiniert erstellen](assets/lookup-dataset-workflows.png)

1. Wählen Sie **[!UICONTROL CSV zu XDM-Schema zuordnen]** aus und klicken Sie dann auf **[!UICONTROL Starten]**.

1. Wählen **[!UICONTROL Abschnitt „Datensatzdetails]** die Option **[!UICONTROL Neuer Datensatz]** aus.

1. Geben Sie einen Namen und eine Beschreibung für Ihren Datensatz an.

1. Wählen Sie im Feld **[!UICONTROL Schema]** das Schema aus, das Sie für Lookup-Datensätze erstellt haben, wie in [Erstellen eines Schemas für Lookup-Datensätze](#create-a-schema-for-lookup-datasets) beschrieben.

1. Klicken Sie auf **[!UICONTROL Weiter]**.

1. Wählen Sie auf der Seite **[!UICONTROL CSV zu XDM-Schema zuordnen]** im Abschnitt **[!UICONTROL Dateien hochladen]** die Option **[!UICONTROL Dateien auswählen]** aus und durchsuchen Sie dann Ihr Dateisystem nach der Datei, die die Klassifizierungsinformationen für die Dimension enthält, für die Sie Klassifizierungsdaten anwenden möchten. Dies kann beispielsweise eine Tabelle sein, die die Feld-IDs und die entsprechenden Feldnamen auflistet. <!-- correct? How can I better explain what this file is?-->

   ![CSV-Datei zuordnen](assets/lookup-map-csv.png)

1. Wählen Sie **[!UICONTROL Weiter]**

1. Überprüfen Sie nach dem Hochladen der Datei die Zuordnungen, um sicherzustellen, dass sie korrekt sind. Die Spalten der CSV-Datei werden unter **[!UICONTROL Source-Daten]** und die zugehörigen XDM-Schemafelder unter &quot;**[!UICONTROL &quot;]**.

   Platform bietet automatisch intelligente Empfehlungen für automatisch zugeordnete Felder, die auf dem von Ihnen ausgewählten Zielschema oder Datensatz basieren. Sie können die Zuordnungsregeln manuell an Ihre Anwendungsfälle anpassen.

   Weitere Informationen zum Zuordnungsprozess finden Sie unter [Zuordnen einer CSV-Datei zu einem vorhandenen XDM-Schema](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema) in der Dokumentation zu Experience Platform.

1. Wählen Sie **[!UICONTROL Beenden]** aus.

1. Fahren Sie mit [Hinzufügen des Lookup-Datensatzes zu Ihrer Verbindung in Customer Journey Analytics](#add-the-lookup-dataset-to-your-connection-in-customer-journey-analytics) fort.

## Hinzufügen des Lookup-Datensatzes zu Ihrer Verbindung in Customer Journey Analytics

Nachdem Sie [ein benutzerdefiniertes Schema erstellt](#create-a-custom-schema-to-use-with-the-lookup-dataset) und [einen Lookup-Datensatz erstellt](#create-a-lookup-dataset) müssen Sie den Lookup-Datensatz zu Ihrer Verbindung in Customer Journey Analytics hinzufügen.

Wiederholen Sie diesen Vorgang für jede Dimension, die Daten enthält, die Sie klassifizieren möchten.

So fügen Sie den Lookup-Datensatz zu Ihrer Verbindung in Customer Journey Analytics hinzu:

1. Rufen Sie in Customer Journey Analytics die Registerkarte **[!UICONTROL Verbindungen]** auf.

1. Klicken Sie ![Mehr](assets/More.svg)Symbol neben der Verbindung, der Sie den Lookup-Datensatz hinzufügen möchten, und klicken Sie dann auf **[!UICONTROL Bearbeiten]**.

   <!-- add screenshot -->

1. Wählen Sie **[!UICONTROL Datensätze hinzufügen]** aus.

1. Wählen **[!UICONTROL Dialogfeld „Datensätze hinzufügen]** den von Ihnen erstellten Lookup-Datensatz aus und klicken Sie dann auf **[!UICONTROL Weiter]**.

1. Wählen Sie im Feld **[!UICONTROL Personen-ID]** eine Personen-ID aus den verfügbaren Identitäten aus, die in dem Datensatzschema definiert sind, das Sie in Experience Platform konfiguriert haben. <!-- fill out other fields? -->

1. Wählen Sie **[!UICONTROL Datensätze hinzufügen]** und dann **[!UICONTROL Speichern]** aus.

   <!-- is there a step right in between here where you select the dataset -->

1. Erstellen Sie mithilfe des Felds **[!UICONTROL Schlüssel]** und des Felds **[!UICONTROL Übereinstimmungsschlüssel]** eine Korrelation zwischen dem Feld in Ihrem Lookup-Datensatz und dem Feld in Ihrem Ereignis- oder Zusammenfassungsdatensatz.

1. Nachdem alle Lookup-Datensätze zu Ihrer Verbindung in Customer Journey Analytics hinzugefügt wurden, folgen Sie den [empfohlenen Upgrade-](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oder den [dynamisch generierten Upgrade-](https://gigazelle.github.io/cja-ttv/).

