---
description: Verwalten von Protokollen für bestehende Exporte
keywords: Analysis Workspace
title: Verwalten von Exportprotokollen
feature: Components
hide: true
hidefromtoc: true
source-git-commit: f070f998758cead3709f6c48412b22b29de00164
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 7%

---

# Verwalten von Exportprotokollen

{{select-package}}

Exportprotokolle enthalten Details zu jedem Export und werden jedes Mal generiert, wenn Analysis Workspace-Daten in die Cloud exportiert werden. (Informationen dazu, wie Daten in die Cloud exportiert werden können, finden Sie unter [Customer Journey Analytics-Daten in die Cloud exportieren](/help/analysis-workspace/export/export-cloud.md).

Bei geplanten Exporten spiegeln Protokolle die Exporteinstellungen so wider, wie sie zum Zeitpunkt des Protokollversands waren. Protokolle können nicht gelöscht werden.

## Filtern und Suchen nach Protokollen

Um die benötigten Informationen zu finden, können Sie entweder die Liste der Protokolle filtern oder nach einem Protokoll suchen.

### Liste der Protokolle filtern

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Protokoll**] Registerkarte.

1. Wählen Sie die **Filter** Symbol.

   ![Informationen filtern](assets/export-log-filters.png)

   Sie können nach folgenden Kriterien filtern:

   | Filter | Beschreibung |
   |---------|----------|
   | [!UICONTROL **Kontotyp**] | Der Kontotyp, mit dem das Protokoll verknüpft ist. Die folgenden Kontotypen sind verfügbar: <ul><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Snowflake**]</li><li>[!UICONTROL **Adobe Experience Manager**]</li></ul>. |
   | [!UICONTROL **Status**] | Der Status des Exports. Die folgenden Status sind verfügbar: <ul><li>[!UICONTROL **Ausstehend**]: Eine bestimmte Instanz eines Exports wurde gestartet, ist jedoch noch nicht abgeschlossen.<p>Wenn Sie einen Export mit dem Status Ausstehend erneut ausführen, wird der Exportvorgang verzögert.</p></li><li>[!UICONTROL **Abgeschlossen**]: Eine bestimmte Instanz eines Exports wurde fertig verarbeitet und ist im Exportkonto verfügbar.</li><li>[!UICONTROL **Fehlgeschlagen**]<p>Die folgenden Situationen können zu einem fehlgeschlagenen Export führen. Bewegen Sie den Mauszeiger über den Status Fehlgeschlagen , um Details zum Fehler anzuzeigen. <ul><li>Geplanter Exportablauf</li><li>Zeilenlimit für geplanten Export erreicht </li></ul> </p></li></ul> |

   {style="table-layout:auto"}

### Nach Protokollen suchen

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Protokoll**] Registerkarte.

1. Geben Sie auf der Registerkarte &quot;Suchen&quot;alle Informationen ein, die mit dem gesuchten Protokoll verknüpft sind. Sie können in einer beliebigen Spalte der Tabelle nach Daten suchen.

<!-- removed for MVP: Retry an export You can re-run the export associated with the selected log, using the data as it was on the day the log was originally exported. This is useful when selecting a log that show a failed export or when selecting a log that was accidentally deleted. 

Retrying an export that has a status of Pending will delay the export process.

This option is not available when selecting multiple logs. -->

<!-- 1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab, then select a log.

1. Select [!UICONTROL **Retry**]. -->

## Export bearbeiten

Sie können den mit einem bestimmten Protokoll verknüpften Export bearbeiten.

Diese Option ist nicht verfügbar, wenn mehrere Protokolle ausgewählt werden.

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Protokolle**] und wählen Sie ein Protokoll aus.

   <!-- add screenshot? -->

1. Wählen Sie [!UICONTROL **Bearbeiten**] aus.

## Spalten konfigurieren

Sie können Spalten zum [!UICONTROL Protokoll] um zu konfigurieren, welche Informationen angezeigt werden.

Wählen Sie eine Spaltenüberschrift aus, um die Protokolle nach dieser Spalte zu sortieren. Standardmäßig werden die Protokolle nach Datum und Uhrzeit des Beginns des Exports sortiert.

So konfigurieren Sie Spalten in der [!UICONTROL Protokoll] tab:

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Protokoll**] Registerkarte.

1. Wählen Sie die **Tabelle anpassen** icon ![Anpassbare Tabelle](assets/customize-table-icon.png) oben rechts im [!UICONTROL Protokoll] Seite.

   Die folgenden Spalten sind verfügbar:

   | Spalte verfügbar | Beschreibung |
   |---------|----------|
   | Exportname | Der Name des Exports. Benutzer geben Exporten einen Namen, wenn sie sie erstellen, wie in [Customer Journey Analytics-Daten in die Cloud exportieren](/help/analysis-workspace/export/export-cloud.md). |
   | Export-ID | Die beim Erstellen automatisch dem Export zugewiesene Kennung. <!-- True? --> |
   | Instanz-ID | Die ID der Customer Journey Analytics-Instanz. <!-- True? --> |
   | Name der Datenansicht | Der Name der mit dem Export verknüpften Datenansicht. Benutzer können die Datenansicht beim Erstellen des Exports auswählen, wie unter [Customer Journey Analytics-Daten in die Cloud exportieren](/help/analysis-workspace/export/export-cloud.md). |
   | Anzahl der Dateien | Die Anzahl der im Export enthaltenen Dateien. |
   | Größe | Die Größe des Exports.<p>Die Dateigröße wird mit einer Basis von 1024 berechnet, die manchmal als KIB und MIB dargestellt wird. Wenn Ihr Cloud-Anbieter die Größe mit einer Basis von 1000 berechnet, kann dies dazu führen, dass sich die in Ihrem Cloud-Anbieter angezeigte Größe geringfügig von der hier angezeigten Größe unterscheidet.</p> |
   | Standort | Der Speicherort auf dem Konto, auf dem die Daten exportiert wurden. |
   | Konto | Das Konto, in das die Daten exportiert wurden. |
   | Status | Der Status des Exports. Verfügbare Status sind [!UICONTROL Ausstehend], [!UICONTROL Zugestellt], und [!UICONTROL Fehlgeschlagen]. |
   | Gesendet am | Das Datum, an dem der Export erfolgte. |
   | Kontotyp | Der Typ des Cloud-Kontos, in das die Daten exportiert wurden. Verfügbare Kontotypen sind [!UICONTROL Amazon S3 Role ARN], [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL Azure RBAC], [!UICONTROL Snowflake], und [!UICONTROL Adobe Experience Platform]. |
   | Zeilenanzahl | Die Anzahl der in der exportierten Tabelle enthaltenen Zeilen. |

   {style="table-layout:auto"}

1. Stellen Sie sicher, dass alle Spalten ausgewählt sind, die angezeigt werden sollen. Die ausgewählten Spalten werden auf der [!UICONTROL Protokoll] und die relevanten Informationen anzeigen.

## Audit-Protokolle anzeigen

Volltabellenexporte werden auch im Abschnitt [Customer Journey Analytics-Auditprotokolle](/help/privacy/audit-log.md). <!-- Need to see what the Component Type for full-table export will be and add it here. Also, under "Event type captured by audit logs" there would be a new event type called "Full-table export". 4 actions would be "Create, Delete, Edit, Export" and "API_Request"? Also information about the locations. Probably have a different component for the location credentials.-->