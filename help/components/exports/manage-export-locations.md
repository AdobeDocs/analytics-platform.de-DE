---
description: Verwalten des Cloud-Exportspeicherorts, an den Customer Journey Analytics-Daten gesendet werden können
keywords: Analysis Workspace
title: Verwalten von Cloud-Exportspeicherorten und -konten
feature: Components
exl-id: 8e82fe6f-99df-4360-8693-99692aac002b
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 6%

---

# Verwalten von Cloud-Exportspeicherorten und -konten

Sie können Cloud-Exportspeicherorte anzeigen, bearbeiten und löschen.

Informationen zum Erstellen eines neuen Standorts finden Sie unter [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md).

## Filtern und Suchen von Standorten

Um benötigte Informationen zu finden, können Sie entweder die Liste der Standorte filtern oder nach einem Ort suchen.

### Filtern der Ortsliste

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Standorte**] Registerkarte.

1. Wählen Sie die **Filter** Symbol.

   <!-- add screenshot -->

   Sie können nach folgenden Kriterien filtern:

   | Filter | Beschreibung |
   |---------|----------|
   | [!UICONTROL **Standorttyp**]<!--should this be changed to Account type?--> | Der Kontotyp, mit dem der Ort verknüpft ist. Die folgenden Kontotypen können verfügbar sein: <ul><li>[!UICONTROL **AEP Data Landing Zone**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul> |
   | [!UICONTROL **Konto**] | Der Name des Kontos, mit dem der Standort verknüpft ist. |
   | [!UICONTROL **Erstellt von**] | Die E-Mail-Adresse des Benutzers, der den Standort erstellt hat. |

   {style="table-layout:auto"}

### Suchen nach Orten

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Standorte**] Registerkarte.

1. Geben Sie im Suchfeld alle Informationen ein, die mit dem gesuchten Ort verknüpft sind. Sie können in einer beliebigen Spalte der Tabelle nach Daten suchen.

## Bearbeitungsorte

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Standorte**] und wählen Sie dann den Ort aus, den Sie bearbeiten möchten.

   ![Exportiert das Fenster mit der Registerkarte Standorte und der Liste der Standorte.](assets/locations-edit.png)

1. Wählen Sie [!UICONTROL **Bearbeiten**] aus.

1. Nehmen Sie die gewünschten Änderungen vor und wählen Sie dann [!UICONTROL **Speichern**].

## Speicherorte löschen

Wenn Sie einen Speicherort löschen, werden auch alle Exporte gelöscht, die diesen Speicherort verwenden. Prüfen Sie beim Löschen das Bestätigungsdialogfeld, um sicherzustellen, dass dem Speicherort keine Exporte zugeordnet sind.

So löschen Sie einen Speicherort:

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Standorte**] und wählen Sie einen oder mehrere Speicherorte aus, die Sie löschen möchten.

   ![Exportiert das Fenster mit der Registerkarte Standorte und der Liste der Standorte](assets/locations-edit.png)

1. Wählen Sie [!UICONTROL **Löschen**] aus.

   Das Dialogfeld Speicherort löschen wird angezeigt.

1. Stellen Sie im Dialogfeld Speicherort löschen sicher, dass der Speicherort keinem Export zugeordnet ist, bevor Sie den Löschvorgang bestätigen.

   ![Dialogfeld &quot;Speicherstandbestätigung&quot;](assets/delete-location-confirmation-dialog.png)

1. Auswählen [!UICONTROL **Löschen**] erneut zu bestätigen.

## Konten bearbeiten

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Standortkonten**] Registerkarte.

   ![Exportfenster mit der Registerkarte Standortkonten](assets/account-add.png)

1. Auswählen [!UICONTROL **Details anzeigen**] auf dem Konto, das Sie bearbeiten möchten.

1. Nehmen Sie die gewünschten Änderungen vor und wählen Sie dann [!UICONTROL **Speichern**].

## Kontoschlüssel anzeigen

Nachdem Sie ein Konto erstellt haben, können Sie alle zugehörigen Kontoschlüssel für dieses Konto anzeigen. Möglicherweise müssen Sie diese Informationen einsehen, wenn Sie die Konfiguration des Kontos für Ihren Cloud-Anbieter nicht abgeschlossen haben [bei der ursprünglichen Konfiguration des Kontos](/help/components/exports/cloud-export-accounts.md).

So zeigen Sie Schlüssel an, die mit einem Exportkonto verknüpft sind:

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Standortkonten**] Registerkarte.

   ![Exportfenster mit der Registerkarte Standortkonten](assets/account-add.png)

1. Wählen Sie das 3-Punkt-Symbol für das Konto aus, das Sie bearbeiten möchten, und wählen Sie dann [!UICONTROL **Kontoschlüssel**].

## Löschen von Konten

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Standortkonten**] Registerkarte.

   ![Exportfenster mit der Registerkarte Standortkonten](assets/account-add.png)

1. Wählen Sie das 3-Punkt-Symbol für das Konto aus, das Sie bearbeiten möchten, und wählen Sie dann [!UICONTROL **Konto löschen**].

1. Auswählen [!UICONTROL **Löschen**] erneut im Bestätigungsdialogfeld angezeigt.
