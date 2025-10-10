---
description: Verwalten von Protokollen für vorhandene Exporte
keywords: Analysis Workspace
title: Verwalten von Exportprotokollen
feature: Components
exl-id: 6d676a0a-b117-421e-9a90-8c550f08d474
role: User
source-git-commit: ad43b199d4174894f0e428bcaf1748ca80bddb45
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 8%

---

# Verwalten von Exportprotokollen

Exportprotokolle enthalten Details zu jedem Export und werden jedes Mal generiert, wenn Analysis Workspace-Daten in die Cloud exportiert werden. (Informationen zum Exportieren von Daten in die Cloud finden Sie unter [Exportieren von Customer Journey Analytics-Berichten in die Cloud](/help/analysis-workspace/export/export-cloud.md).)

Für geplante Exporte spiegeln die Protokolle die Exporteinstellungen wider, die zum Zeitpunkt des Versands des Protokolls galten. Protokolle können nicht gelöscht werden.

## Exportprotokolle anzeigen

1. Wählen Sie in Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Wählen Sie die Registerkarte [!UICONTROL **Protokolle**] aus.

   ![Exportfenster mit der Registerkarte „Protokolle“](assets/export-logs-tab.png)

   Details zu jedem Protokoll werden in den verfügbaren Spalten angezeigt.

1. Führen Sie einen der folgenden Schritte aus:

   * [Anpassen der &#x200B;](#configure-columns) Spalten“.

   * Wählen Sie das **Informationssymbol**![&#x200B; Informationssymbol](assets/information-icon.png) neben dem Protokollnamen aus, um den mit dem Protokoll verknüpften Export anzuzeigen.

   * Wählen Sie das Symbol **Export bearbeiten** ![Informationssymbol](assets/edit-export-icon.png) neben dem Protokollnamen aus, um den mit dem Protokoll verknüpften Export zu bearbeiten.

     Weitere Informationen zum Bearbeiten eines Exports finden Sie unter [Exportieren von Customer Journey Analytics-Berichten in die Cloud](/help/analysis-workspace/export/export-cloud.md).

## Filtern und Suchen nach Protokollen

Um die benötigten Informationen zu finden, können Sie entweder die Liste der Protokolle filtern oder nach einem Protokoll suchen.

### Filtern der Protokollliste

1. Wählen Sie in Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Wählen Sie die Registerkarte [!UICONTROL **Protokolle**] aus.

1. Wählen Sie das Symbol **Filter** aus.

   ![Exportfenster mit Filterliste nach Kontotyp](assets/export-log-filters.png)

   Sie können nach den folgenden Kriterien filtern:

   | Filter | Beschreibung |
   |---------|----------|
   | [!UICONTROL **Export-ID**] | Geben Sie die Export-ID des Exportprotokolls an, das Sie anzeigen möchten. |
   | [!UICONTROL **Kontotyp**] | Der Kontotyp, mit dem das Protokoll verknüpft ist. Die folgenden Kontotypen sind verfügbar: <ul><li>[!UICONTROL **AEP Data Landing Zone**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul>. |
   | [!UICONTROL **Status**] | Der Status des Exports Die folgenden Status sind verfügbar: <ul><li>[!UICONTROL **Ausstehend**]: Eine bestimmte Instanz eines Exports wurde gestartet, ist jedoch noch nicht abgeschlossen.<p>Das erneute Ausführen eines Exports mit dem Status Ausstehend verzögert den Exportvorgang.</p></li><li>[!UICONTROL **Abgeschlossen**]: Eine bestimmte Instanz eines Exports wurde fertig verarbeitet und ist im Exportkonto verfügbar.</li><li>[!UICONTROL **Fehlgeschlagen**]<p>Verschiedene Situationen können zu einem fehlgeschlagenen Export führen. Bewegen Sie den Mauszeiger über den Status Fehlgeschlagen , um Details zum Fehler anzuzeigen.<p>Weitere Informationen zu möglichen Fehlerursachen finden Sie unter [Fehlerbehebung bei fehlgeschlagenen &#x200B;](/help/components/exports/troubleshoot-exports.md)).</p> |

   {style="table-layout:auto"}

### Nach Protokollen suchen

1. Wählen Sie in Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Wählen Sie die Registerkarte [!UICONTROL **Protokolle**] aus.

1. Beginnen Sie im Suchfeld mit der Eingabe von Informationen, die mit dem gesuchten Protokoll verknüpft sind. Sie können nach Daten aus jeder in der Tabelle verfügbaren Spalte suchen.

<!-- removed for MVP: Retry an export You can re-run the export associated with the selected log, using the data as it was on the day the log was originally exported. This is useful when selecting a log that show a failed export or when selecting a log that was accidentally deleted. 

Retrying an export that has a status of Pending will delay the export process.

This option is not available when selecting multiple logs. -->

<!-- 1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab, then select a log.

1. Select [!UICONTROL **Retry**]. -->

## Bearbeiten eines Exports

Sie können den mit einem bestimmten Protokoll verknüpften Export bearbeiten.

Diese Option ist nicht verfügbar, wenn mehrere Protokolle ausgewählt werden.

1. Wählen Sie in Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Wählen Sie die Registerkarte [!UICONTROL **Protokolle**] aus.

1. Suchen Sie das Protokoll, das mit dem Export verknüpft ist, den Sie bearbeiten möchten.

1. Wählen Sie das **Export bearbeiten**-Symbol ![Export-](assets/export-icon.png)-Symbol) neben dem Protokollnamen aus.

   Oder

   Aktivieren Sie das Kontrollkästchen neben dem Protokoll und klicken Sie dann auf [!UICONTROL **Export bearbeiten**].

## Konfigurieren von Spalten

Sie können Spalten auf der Registerkarte [!UICONTROL Protokolle] hinzufügen oder entfernen, um zu konfigurieren, welche Informationen angezeigt werden.

Spaltenüberschrift auswählen, um die Protokolle nach dieser Spalte zu sortieren. Standardmäßig werden die Protokolle nach Datum und Uhrzeit des Starts des Exports sortiert.

So konfigurieren Sie Spalten auf der Registerkarte [!UICONTROL Protokolle]:

1. Wählen Sie in Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Wählen Sie die Registerkarte [!UICONTROL **Protokolle**] aus.

1. Wählen Sie **Symbol** Tabelle anpassen![&#x200B; &#x200B;](assets/customize-table-icon.png) oben rechts auf der Seite [!UICONTROL Protokolle] aus.

   Die folgenden Spalten sind verfügbar:

   | Verfügbare Spalte | Beschreibung |
   |---------|----------|
   | Exportname | Der Name des Exports Benutzer geben Exporten bei ihrer Erstellung einen Namen, wie unter [Exportieren von Customer Journey Analytics-Berichten in die Cloud](/help/analysis-workspace/export/export-cloud.md) beschrieben. |
   | Export-ID | Die ID, die dem Export bei seiner Erstellung automatisch zugewiesen wird. <!-- True? --> |
   | Instanz-ID | Die ID der Customer Journey Analytics-Instanz. <!-- True? --> |
   | Name der Datenansicht | Der Name der dem Export zugeordneten Datenansicht. Benutzerinnen und Benutzer können die Datenansicht auswählen, wenn sie den Export erstellen, wie unter [Exportieren von Customer Journey Analytics-Berichten in die Cloud](/help/analysis-workspace/export/export-cloud.md) beschrieben. |
   | Anzahl der Dateien | Die Anzahl der im Export enthaltenen Dateien. |
   | Größe | Die Größe des Exports.<p>Die Dateigröße wird mit einem Basiswert von 1024 berechnet, der manchmal als KIB und MIB dargestellt wird. Wenn Ihr Cloud-Anbieter die Größe mit einer Basis von 1.000 berechnet, kann dies dazu führen, dass die in Ihrem Cloud-Anbieter angezeigte Größe geringfügig von der hier angezeigten Größe abweicht.</p> |
   | Standort | Der Speicherort des Kontos, in das die Daten exportiert wurden. |
   | Konto | Das Konto, in das die Daten exportiert wurden. |
   | Status | Der Status des Exports Verfügbare Status [!UICONTROL &#x200B; &quot;]&quot;, [!UICONTROL Zugestellt] und [!UICONTROL Fehlgeschlagen]. |
   | Gesendet am | Das Datum, an dem der Export stattfand. |
   | Kontotyp | Der Typ des Cloud-Kontos, in das die Daten exportiert wurden. Verfügbare Kontotypen sind [!UICONTROL Amazon S3 Role ARN], [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL Azure RBAC], [!UICONTROL Snowflake] und [!UICONTROL Adobe Experience Platform]. |
   | Anzahl Zeilen | Die Anzahl der in der exportierten Tabelle enthaltenen Zeilen. |

   {style="table-layout:auto"}

1. Stellen Sie sicher, dass alle Spalten, die angezeigt werden sollen, ausgewählt sind. Ausgewählte Spalten werden auf der Seite [!UICONTROL Protokolle] angezeigt und enthalten die entsprechenden Informationen.

## Audit-Protokolle anzeigen

Vollständige Tabellenexporte werden auch in den [Customer Journey Analytics-Auditprotokollen](/help/privacy/audit-log.md) verfolgt. <!-- Need to see what the Component Type for full-table export will be and add it here. Also, under "Event type captured by audit logs" there would be a new event type called "Full-table export". 4 actions would be "Create, Delete, Edit, Export" and "API_Request"? Also information about the locations. Probably have a different component for the location credentials.-->
