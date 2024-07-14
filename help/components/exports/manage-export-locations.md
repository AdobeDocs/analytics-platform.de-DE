---
description: Verwalten des Cloud-Exportspeicherorts, an den Customer Journey Analytics-Daten gesendet werden können
keywords: Analysis Workspace
title: Verwalten von Cloud-Exportspeicherorten und -konten
feature: Components
exl-id: 8e82fe6f-99df-4360-8693-99692aac002b
role: User, Admin
source-git-commit: 9f3182ed33fc5ad537b05e9effbdd25caf4e87d7
workflow-type: tm+mt
source-wordcount: '1370'
ht-degree: 1%

---

# Verwalten von Cloud-Exportspeicherorten und -konten

Sie können Cloud-Exportspeicherorte anzeigen, bearbeiten und löschen.

Informationen zum Erstellen eines neuen Speicherorts finden Sie unter [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md).

## Filtern und Suchen von Standorten

Um benötigte Informationen zu finden, können Sie entweder die Liste der Standorte filtern oder nach einem Ort suchen.

### Filtern der Ortsliste

1. Wählen Sie unter Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Wählen Sie die Registerkarte [!UICONTROL **Standorte**] aus.

1. Wählen Sie das Symbol **Filter** aus.

   <!-- add screenshot -->

   Sie können nach folgenden Kriterien filtern:

   | Filter | Beschreibung |
   |---------|----------|
   | [!UICONTROL **Positionstyp**]<!--should this be changed to Account type?--> | Der Kontotyp, mit dem der Ort verknüpft ist. Die folgenden Kontotypen können verfügbar sein: <ul><li>[!UICONTROL **AEP Data Landing Zone**]</li><li>[!UICONTROL **Amazon S3-Rolle ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul> |
   | [!UICONTROL **Konto**] | Der Name des Kontos, mit dem der Standort verknüpft ist. |
   | [!UICONTROL **Erstellt von**] | Die E-Mail-Adresse des Benutzers, der den Standort erstellt hat. |

   {style="table-layout:auto"}

### Suchen nach Orten

1. Wählen Sie unter Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Wählen Sie die Registerkarte [!UICONTROL **Standorte**] aus.

1. (Bedingt) Wenn Sie Systemadministrator sind, können Sie die Option [!UICONTROL **Standorte für alle Benutzer anzeigen**] aktivieren, um von allen Benutzern in Ihrer Organisation erstellte Standorte anzuzeigen.

1. Geben Sie im Suchfeld alle Informationen ein, die mit dem gesuchten Ort verknüpft sind. Sie können in einer beliebigen Spalte der Tabelle nach Daten suchen.

## Bearbeitungsorte

Ein Speicherort kann nur von dem Benutzer, der ihn erstellt hat, oder von einem Systemadministrator bearbeitet werden.

So bearbeiten Sie einen Speicherort:

1. Wählen Sie unter Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Wählen Sie die Registerkarte [!UICONTROL **Standorte**] aus.

1. (Bedingt) Wenn Sie Systemadministrator sind, können Sie die Option [!UICONTROL **Standorte für alle Benutzer anzeigen**] aktivieren, um von allen Benutzern in Ihrer Organisation erstellte Standorte anzuzeigen.

1. Wählen Sie den Speicherort aus, den Sie bearbeiten möchten.

   ![Fenster &quot;Exporte&quot;mit der Registerkarte &quot;Standorte&quot;und der Liste der Standorte.](assets/locations-edit.png)

1. Wählen Sie [!UICONTROL **Bearbeiten**] aus.

1. Nehmen Sie die gewünschten Änderungen vor und wählen Sie dann [!UICONTROL **Speichern**] aus.

## Speicherorte löschen

Wenn Sie einen Speicherort löschen, werden auch alle Exporte gelöscht, die diesen Speicherort verwenden. Prüfen Sie beim Löschen das Bestätigungsdialogfeld, um sicherzustellen, dass dem Speicherort keine Exporte zugeordnet sind.

So löschen Sie einen Speicherort:

1. Wählen Sie unter Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Wählen Sie die Registerkarte [!UICONTROL **Standorte**] aus.

1. (Bedingt) Wenn Sie Systemadministrator sind, können Sie die Option [!UICONTROL **Standorte für alle Benutzer anzeigen**] aktivieren, um von allen Benutzern in Ihrer Organisation erstellte Standorte anzuzeigen.

1. Wählen Sie einen oder mehrere Speicherorte aus, die Sie löschen möchten.

   ![Fenster &quot;Exporte&quot;mit der Registerkarte &quot;Standorte&quot;und der Liste der Standorte](assets/locations-edit.png)

1. Wählen Sie [!UICONTROL **Löschen**] aus.

   Das Dialogfeld Speicherort löschen wird angezeigt.

1. Stellen Sie im Dialogfeld Speicherort löschen sicher, dass der Speicherort keinem Export zugeordnet ist, bevor Sie den Löschvorgang bestätigen.

   ![Dialogfeld &quot;Speicherortbestätigung&quot;löschen](assets/delete-location-confirmation-dialog.png)

1. Wählen Sie zur Bestätigung erneut [!UICONTROL **Löschen**] aus.

## Konten bearbeiten

Ein Konto kann nur von dem Benutzer, der es erstellt hat, oder von einem Systemadministrator bearbeitet werden.

So bearbeiten Sie ein Konto:

1. Wählen Sie unter Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Wählen Sie die Registerkarte [!UICONTROL **Standortkonten**] aus.

   ![Fenster &quot;Exporte&quot;mit der Registerkarte &quot;Standortkonten&quot;](assets/account-add.png)

1. (Bedingt) Wenn Sie Systemadministrator sind, können Sie die Option [!UICONTROL **Konten für alle Benutzer anzeigen**] aktivieren, um die von allen Benutzern in Ihrer Organisation erstellten Speicherorte anzuzeigen.

1. Wählen Sie [!UICONTROL **Details anzeigen**] für das Konto aus, das Sie bearbeiten möchten.

1. Nehmen Sie die gewünschten Änderungen vor und wählen Sie dann [!UICONTROL **Speichern**] aus.

## Kontoschlüssel anzeigen

Nachdem Sie ein Konto erstellt haben, können Sie alle zugehörigen Kontoschlüssel für dieses Konto anzeigen. Möglicherweise müssen Sie diese Informationen einsehen, wenn Sie die Konfiguration des Kontos mit Ihrem Cloud-Anbieter [bei der ursprünglichen Konfiguration des Kontos](/help/components/exports/cloud-export-accounts.md) nicht abgeschlossen haben.

So zeigen Sie Schlüssel an, die mit einem Exportkonto verknüpft sind:

1. Wählen Sie unter Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Wählen Sie die Registerkarte [!UICONTROL **Standortkonten**] aus.

   ![Fenster &quot;Exporte&quot;mit der Registerkarte &quot;Standortkonten&quot;](assets/account-add.png)

1. (Bedingt) Wenn Sie Systemadministrator sind, können Sie die Option [!UICONTROL **Konten für alle Benutzer anzeigen**] aktivieren, um die von allen Benutzern in Ihrer Organisation erstellten Speicherorte anzuzeigen.

1. Wählen Sie das 3-Punkt-Symbol für das Konto aus, das Sie bearbeiten möchten, und wählen Sie dann [!UICONTROL **Kontoschlüssel**] aus.

## Löschen von Konten

1. Wählen Sie unter Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Wählen Sie die Registerkarte [!UICONTROL **Standortkonten**] aus.

   ![Fenster &quot;Exporte&quot;mit der Registerkarte &quot;Standortkonten&quot;](assets/account-add.png)

1. (Bedingt) Wenn Sie Systemadministrator sind, können Sie die Option [!UICONTROL **Konten für alle Benutzer anzeigen**] aktivieren, um die von allen Benutzern in Ihrer Organisation erstellten Speicherorte anzuzeigen.

1. Wählen Sie das 3-Punkt-Symbol für das Konto aus, das Sie bearbeiten möchten, und wählen Sie dann [!UICONTROL **Konto löschen**] aus.

1. Wählen Sie im Bestätigungsdialogfeld erneut [!UICONTROL **Löschen**] aus.

## unternehmensweite Einstellungen konfigurieren (nur Administratoren)

{{release-limited-testing-section}}

Systemadministratoren können Benutzer daran hindern, Konten und Standorte zu erstellen, oder sie können die Arten von Konten einschränken, die Benutzer erstellen und verwenden können.

![Registerkarte &quot;Admin-Einstellungen&quot;](assets/locations-admin-settings.png)

### Konfigurieren, ob Benutzer Konten erstellen und bearbeiten können

Standardmäßig können alle Benutzer des Unternehmens Konten erstellen und Konten bearbeiten, die sie in Ihrer Customer Journey Analytics-Umgebung erstellen, wie in [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md) beschrieben.

Sie können Benutzer daran hindern, Konten zu erstellen. Wenn Sie dies tun, können Benutzer weiterhin alle Konten verwenden, die sie bereits erstellt haben, sie können sie jedoch nicht mehr bearbeiten. Sie können von Benutzern erstellte Konten löschen, wie unter [Konto löschen](#delete-an-account) beschrieben.

So beschränken Sie das Erstellen und Bearbeiten von Konten für alle Benutzer:

1. Wählen Sie unter Customer Journey Analytics die Option **[!UICONTROL Komponenten]** > **[!UICONTROL Exporte]** und dann die Registerkarte [!UICONTROL **Admin-Einstellungen**] aus.

1. Deaktivieren Sie im Abschnitt [!UICONTROL **Standortenkonten**] die Option [!UICONTROL **Benutzern erlauben, Standortkonten zu erstellen und zu verwalten**].

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. (Optional) Löschen Sie alle Konten, die Benutzer erstellt haben und die Sie nicht mehr verwenden möchten, wie unter [Konto löschen](#delete-an-account) beschrieben.

### Konfigurieren, ob Benutzer Standorte erstellen und bearbeiten können

Standardmäßig können alle Benutzer des Unternehmens Orte erstellen und Orte bearbeiten, die sie in Ihrer Customer Journey Analytics-Umgebung erstellen, wie unter [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md) beschrieben.

Sie können Benutzer daran hindern, Orte zu erstellen. Wenn Sie dies tun, können Benutzer weiterhin alle Orte verwenden, die sie bereits erstellt haben, sie können sie jedoch nicht mehr bearbeiten. Sie können von Benutzern erstellte Speicherorte löschen, wie unter [Speicherorte löschen](#delete-a-location) beschrieben.

So beschränken Sie die Erstellung und Bearbeitung von Standorten für alle Benutzer:

1. Wählen Sie unter Customer Journey Analytics die Option **[!UICONTROL Komponenten]** > **[!UICONTROL Berichte]** und dann die Registerkarte [!UICONTROL **Admin-Einstellungen**] aus.

1. Deaktivieren Sie im Abschnitt [!UICONTROL **Standorte**] die Option [!UICONTROL **Benutzern erlauben, Standorte zu erstellen und zu verwalten**].

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. (Optional) Löschen Sie alle Orte, die Benutzer erstellt haben und die Sie nicht mehr verwenden möchten, wie unter [Löschen eines Standorts](#delete-a-location) beschrieben.

### Beschränken, welche Kontotypen Benutzer erstellen und verwenden können

Sie können die Kontotypen einschränken, die Benutzern in den folgenden Fällen angezeigt werden:

* Beim Erstellen neuer Konten [ ](/help/components/exports/cloud-export-accounts.md).
* Bei der Auswahl der Konten, die beim Exportieren von Dateien mit dem [vollständigen Tabellenexport](/help/analysis-workspace/export/export-cloud.md) verwendet werden sollen.

Wenn Sie die in diesem Abschnitt beschriebenen Kontotypen einschränken, sind Konten des Typs, den Sie einschränken, für Benutzer nicht mehr sichtbar. Dies bedeutet, dass keine neuen Konten dieses Typs erstellt werden können und vorhandene Konten dieses Typs nicht beim Export von Dateien mit vollständigem Tabellenexport verwendet werden können.

Vorhandene Konten, die für geplante Exporte konfiguriert sind, müssen jedoch gelöscht werden, wenn Sie sie von der Verwendung beschränken möchten.

#### Stellen Sie sicher, dass Konten nicht für geplante Exporte verwendet werden

Wenn Sie die Kontotypen einschränken, werden vorhandene Konten ausgeblendet und nicht gelöscht.

Wenn Zeitpläne bereits so konfiguriert sind, dass Daten an ein Konto gesendet werden, das dem von Ihnen begrenzten Typ entspricht, werden die Zeitpläne auch nach der Begrenzung des Kontotyps weiter ausgeführt und die Daten werden weiterhin an das Konto gesendet. Wenn beispielsweise ein vollständiger Tabellenexport geplant ist, um Daten an einen von Ihnen beschränkten Kontotyp zu senden, wird der Zeitplan weiterhin ausgeführt.

Wenn Sie sicherstellen müssen, dass Konten eines bestimmten Typs nicht in geplanten Exporten verwendet werden, können Sie die Konten löschen, bevor Sie [die Kontotypen einschränken](#limit-the-account-types-that-are-available-to-users).

So löschen Sie Konten:

1. Suchen Sie die Konten des Kontotyps, den Sie begrenzen möchten, die für geplante Exporte verwendet werden.

1. Löschen Sie die Konten, wie unter [Konto löschen](#delete-an-account) beschrieben.

1. Fahren Sie mit dem folgenden Abschnitt fort: [Beschränken Sie die für Benutzer verfügbaren Kontotypen](#limit-the-account-types-that-are-available-to-users).

#### Beschränken der für Benutzer verfügbaren Kontotypen

So beschränken Sie die Kontotypen, die Benutzern beim Erstellen und Verwenden von Konten zur Verfügung stehen:

1. Wählen Sie unter Customer Journey Analytics die Option **[!UICONTROL Komponenten]** > **[!UICONTROL Exporte]** und dann die Registerkarte [!UICONTROL **Admin-Einstellungen**] aus.

1. Suchen Sie den Abschnitt [!UICONTROL **Zulässige Kontotypen**] .

   Die folgenden Kontotypen sind standardmäßig für Benutzer verfügbar. Heben Sie die Auswahl dieser Kontotypen auf, die Sie die Verwendung von Benutzern beschränken möchten.

   * [!UICONTROL **AEP Data Landing Zone**]

   * [!UICONTROL **Amazon S3-Rolle ARN**]

   * [!UICONTROL **Google Cloud Platform**]

   * [!UICONTROL **Azure SAS**]

   * [!UICONTROL **Azure RBAC**]

   * [!UICONTROL **Snowflake**]

1. Wählen Sie [!UICONTROL **Speichern**] aus.
