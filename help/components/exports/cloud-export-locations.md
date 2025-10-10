---
description: Konfigurieren Sie den Cloud-Exportspeicherort, an den Customer Journey Analytics-Daten gesendet werden können
keywords: Analysis Workspace
title: Konfigurieren von Cloud-Exportspeicherorten
feature: Components
exl-id: 93f1cca0-95da-41a0-a4f9-5ab620a5b9da
role: User, Admin
source-git-commit: 5adcab1df932f5c8af1f140fb6707f2d56726ae3
workflow-type: tm+mt
source-wordcount: '2030'
ht-degree: 19%

---

# Konfigurieren von Cloud-Exportspeicherorten {#configure-cloud-export-locations}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-prefix"
>title="Präfix"
>abstract="Der Stammordner innerhalb des Containers, in den Sie die Daten einfügen möchten. Geben Sie einen statischen Ordnernamen an und fügen Sie dann nach dem Namen einen Schrägstrich hinzu, um den Ordner zu erstellen. Beispiel: `folder_name/`"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-file-name"
>title="Dateiname und Pfad"
>abstract="Geben Sie einen dynamischen benutzerdefinierten Dateinamen an, der für automatisierte Exporte verwendet werden soll, die an diesen Speicherort gesendet werden. Sie können dem Dateinamen auch einen dynamischen benutzerdefinierten Dateipfad voranstellen. &lt;br\>Verwenden Sie Variablen im Dateinamen und im Pfad, um sie dynamisch zu machen. &lt;br\>Wenn Sie beispielsweise `${yyyy}/${mm}/${dd}/my-report-${instance_id}-${idx}` angeben, hätte ein Export, der am 15. Januar 2026 automatisch an dieses Ziel gesendet wird, folgenden Dateipfad und -namen: `[prefix_folder_name]/2026/01/15/my-report-[UUID]-1.csv` &lt;br\>Klicken Sie auf den Link unten, um eine Liste der verfügbaren Variablen zu erhalten."

<!-- markdownlint-enable MD034 -->

Bevor Sie Customer Journey Analytics-Berichte in ein Cloud-Ziel exportieren können (entweder aus Analysis Workspace, wie unter [Exportieren von Customer Journey Analytics-Berichten in die Cloud](/help/analysis-workspace/export/export-cloud.md) beschrieben, oder aus Report Builder, wie [Exportieren von Berichten aus Report Builder](/help/report-builder/report-builder-export.md)), wie [Exportieren von Customer Journey Analytics-Berichten in die Cloud](/help/analysis-workspace/export/export-cloud.md) beschrieben, müssen Sie den Speicherort hinzufügen und konfigurieren, an den die Daten gesendet werden sollen.

Dieser Prozess besteht aus dem Hinzufügen und Konfigurieren des Kontos (z. B. Amazon S3, Google Cloud Platform usw.), wie unter [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md) beschrieben, und dem Hinzufügen und Konfigurieren des Speicherorts innerhalb dieses Kontos (z. B. eines Ordners innerhalb des Kontos), wie in diesem Artikel beschrieben.

Informationen zum Verwalten vorhandener Speicherorte, einschließlich Anzeigen, Bearbeiten und Löschen von Speicherorten, finden Sie unter [Verwalten von Speicherorten und Konten für Cloud-](/help/components/exports/manage-export-locations.md).

## Erstellen eines Cloud-Exportspeicherorts

1. Sie müssen ein Konto hinzufügen, bevor Sie einen Speicherort hinzufügen können. Falls noch nicht geschehen, fügen Sie ein Konto hinzu, wie in [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md) beschrieben.

1. Wählen Sie in Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Wählen Sie die Registerkarte [!UICONTROL **Standorte**] und dann [!UICONTROL **Standort hinzufügen**] aus.

   ![Exportiert das Fenster mit ausgewählter Registerkarte „Standort“ und hervorgehobener Schaltfläche „Standort hinzufügen“](assets/location-add.png)

   Oder

   Wählen Sie die Registerkarte [!UICONTROL **Standortkonten**], klicken Sie auf das Dreipunkt-Symbol in einem vorhandenen Konto, dem Sie einen Standort hinzufügen möchten, und klicken Sie dann auf [!UICONTROL **Standort hinzufügen**].

   ![Dropdown-Menü GCP-Konto und Auslassungspunkte mit der Option Standort hinzufügen ](assets/add-location-existing-account.png)

   Das Dialogfeld Standort wird angezeigt.

1. Geben Sie die folgenden Informationen an:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Name**] | Der Name des Speicherorts. |
   | [!UICONTROL **Beschreibung**] | Geben Sie eine kurze Beschreibung des Speicherorts ein, um ihn von anderen Speicherorten im Konto zu unterscheiden. |
   | [!UICONTROL **Den Speicherort für alle Benutzer in Ihrer Organisation verfügbar machen**] | Aktivieren Sie diese Option, damit andere Benutzer in Ihrem Unternehmen den Speicherort verwenden können. <p>Beachten Sie beim Freigeben von Speicherorten Folgendes:</p><ul><li>Die Freigabe von Speicherorten, die Sie freigeben, kann nicht aufgehoben werden.</li><li>Freigegebene Speicherorte können nur vom Eigentümer des Speicherorts bearbeitet werden.</li><li>Standorte können nur freigegeben werden, wenn das Konto, mit dem der Standort verknüpft ist, auch freigegeben ist.</li></ul> |
   | [!UICONTROL **Standortkonto**] | Wählen Sie das Konto aus, in dem Sie den Speicherort erstellen möchten. Informationen zum Erstellen eines Kontos finden Sie unter [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md). |

1. Geben Sie im Abschnitt [!UICONTROL **Speicherorteigenschaften**] spezifische Informationen zum Kontotyp Ihres Speicherortkontos an.

   Fahren Sie mit dem folgenden Abschnitt fort, der dem Kontotyp entspricht, den Sie im Feld [!UICONTROL **Standortkonto**] ausgewählt haben.

   * [AEP Data Landing Zone](#aep-data-landing-zone)
   * [Amazon S3 Role ARN](#amazon-s3-role-arn)
   * [Google Cloud Platform](#google-cloud-platform)
   * [Azure SAS](#azure-sas)
   * [Azure RBAC](#azure-rbac)
   * [Snowflake](#snowflake)

### AEP Data Landing Zone

>[!IMPORTANT]
>
>Stellen Sie beim Exportieren von Customer Journey Analytics-Berichten in die Data Landing Zone von Adobe Experience Platform sicher, dass Sie die Daten innerhalb von 7 Tagen herunterladen und dann aus der Data Landing Zone von AEP löschen. Nach 7 Tagen werden die Daten automatisch aus der Data Landing Zone von AEP gelöscht.

1. Beginnen Sie mit der Erstellung eines Cloud-Exportspeicherorts auf eine der folgenden Arten:

   * Klicken Sie auf der Seite „Exporte“ wie oben beschrieben unter [Erstellen eines Cloud-Exportspeicherorts](#begin-creating-a-cloud-export-location)

   * Beim [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Geben Sie [!UICONTROL **Abschnitt**] des Dialogfelds [!UICONTROL **Speicherort hinzufügen**] die folgenden Informationen an, um einen Speicherort für die Data Landing Zone in Adobe Experience Platform zu konfigurieren:

   <!-- still need to update; can't create AEP account -->

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Präfix**] | Der Ordner im Container, in dem Sie die Daten ablegen möchten. Geben Sie einen Ordnernamen an und fügen Sie dann nach dem Namen einen Schrägstrich hinzu, um den Ordner zu erstellen. Beispiel: `folder_name/` |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. Sie können jetzt Daten aus Analysis Workspace an das -Konto und den Speicherort exportieren, die Sie konfiguriert haben. Informationen zum Exportieren von Daten in die Cloud finden Sie unter [Exportieren von Projektdaten in die Cloud](/help/analysis-workspace/export/export-cloud.md).

1. Der einfachste Weg, auf Ihre Daten in der AEP Data Landing Zone zuzugreifen, ist die Verwendung des Microsoft Azure Storage Explorers. Dies ist dasselbe Tool, das in den Anweisungen zum Konfigurieren des [AEP Data Landing Zone-Kontos verwendet ](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone).

   1. Öffnen Sie den [Microsoft Azure Storage Explorer](https://azure.microsoft.com/en-us/products/storage/storage-explorer/).

   1. Navigieren Sie [!UICONTROL **Speicherkonten**] > [!UICONTROL **(angehängte Container)**] > [!UICONTROL **Blob-Container**] > **[!UICONTROL cjaexport-_number_]**>*** your_container_name ***.

      >[!NOTE]
      >
      >Der Ordnername **[!UICONTROL cjaexport-_number_]**ist der Standardname, der vom Azure Storage Explorer bereitgestellt wird. Wenn Ihrem SAS-URI nur eine einzige Verbindung zugeordnet ist (was normal ist), lautet der Name dieses Ordners **[!UICONTROL cjaexport-1]**.


      ![Zugreifen auf Dateien im Azure-Speicher-Explorer](assets/azure-storage-explorer-access.png)

   1. Wählen Sie den Export aus, den Sie herunterladen möchten, und wählen Sie dann [!UICONTROL **Herunterladen**] aus, um ihn herunterzuladen.

### Amazon S3 Role ARN

1. Beginnen Sie mit der Erstellung eines Cloud-Exportspeicherorts auf eine der folgenden Arten:

   * Klicken Sie auf der Seite „Exporte“ wie oben beschrieben unter [Erstellen eines Cloud-Exportspeicherorts](#begin-creating-a-cloud-export-location)

   * Beim [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Geben Sie [!UICONTROL **Abschnitt**] des Dialogfelds [!UICONTROL **Speicherort hinzufügen**] die folgenden Informationen an, um einen ARN-Speicherort für die Amazon S3-Rolle zu konfigurieren:

   <!-- still need to update; can't create S3 role ARN account -->

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Bucket**] | Der Bucket in Ihrem Amazon S3-Konto, an den Customer Journey Analytics-Daten gesendet werden sollen. <p>Stellen Sie sicher, dass der von Adobe bereitgestellte Benutzer-ARN über die Berechtigung `S3:PutObject` verfügt, um Dateien in diesen Bucket hochzuladen. </p><p>Bucket-Namen müssen bestimmten Benennungsregeln entsprechen. Bucket-Namen müssen etwa zwischen 3 und 63 Zeichen lang sein, dürfen nur aus Kleinbuchstaben, Zahlen, Punkten (.) und Bindestrichen (-) bestehen und müssen mit einem Buchstaben oder einer Zahl beginnen und enden. [Eine vollständige Liste der Benennungsregeln finden Sie in der AWS-Dokumentation.](https://docs.aws.amazon.com/de_de/AmazonS3/latest/userguide/bucketnamingrules.html). </p> |
   | [!UICONTROL **Präfix**] | Der Ordner im Bucket, in den Sie die Daten ablegen möchten. Geben Sie einen Ordnernamen an und fügen Sie dann nach dem Namen einen Schrägstrich hinzu, um den Ordner zu erstellen. (Beispiel: Ordnername/) |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. Sie können jetzt Daten aus Analysis Workspace an das -Konto und den Speicherort exportieren, die Sie konfiguriert haben. Informationen zum Exportieren von Daten in die Cloud finden Sie unter [Exportieren von Projektdaten in die Cloud](/help/analysis-workspace/export/export-cloud.md).

### Google Cloud Platform

1. Beginnen Sie mit der Erstellung eines Cloud-Exportspeicherorts auf eine der folgenden Arten:

   * Klicken Sie auf der Seite „Exporte“ wie oben beschrieben unter [Erstellen eines Cloud-Exportspeicherorts](#begin-creating-a-cloud-export-location)

   * Beim [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Geben Sie [!UICONTROL **Abschnitt**] des Dialogfelds [!UICONTROL **Speicherort hinzufügen**] die folgenden Informationen an, um einen Speicherort in Google Cloud Platform zu konfigurieren:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Bucket**] | Der Bucket in Ihrem GCP-Konto, an den Customer Journey Analytics-Daten gesendet werden sollen. <p>Stellen Sie sicher, dass Sie dem von Adobe bereitgestellten Prinzipal die `roles/storage.objectCreator`-Berechtigung erteilt haben. (Der Prinzipal wird beim Konfigurieren [ Google Cloud Platform-Kontos ](/help/components/exports/cloud-export-accounts.md).) <p>Informationen zum Gewähren von Berechtigungen finden Sie in der Google Cloud-Dokumentation unter [Hauptkonto zu einer Richtlinie auf Bucket-Ebene hinzufügen](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add).</p><p>Wenn Ihre Organisation [Organisationsrichtlinieneinschränkungen](https://cloud.google.com/storage/docs/org-policy-constraints) verwendet, um nur das Google Cloud Platform-Konto in Ihrer Zulassungsliste zuzulassen, benötigen Sie die folgende Adobe-eigene Organisations-ID für Google Cloud Platform: <ul><li>`DISPLAY_NAME`: `adobe.com`</li><li>`ID`: `178012854243`</li><li>`DIRECTORY_CUSTOMER_ID`: `C02jo8puj`</li></ul> </p> |
   | [!UICONTROL **Präfix**] | Der Ordner im Bucket, in den Sie die Daten ablegen möchten. Geben Sie einen Ordnernamen an und fügen Sie dann nach dem Namen einen Schrägstrich hinzu, um den Ordner zu erstellen. (Beispiel: Ordnername/) |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. Sie können jetzt Daten aus Analysis Workspace an das -Konto und den Speicherort exportieren, die Sie konfiguriert haben. Informationen zum Exportieren von Daten in die Cloud finden Sie unter [Exportieren von Projektdaten in die Cloud](/help/analysis-workspace/export/export-cloud.md).

### Azure SAS

1. Beginnen Sie mit der Erstellung eines Cloud-Exportspeicherorts auf eine der folgenden Arten:

   * Klicken Sie auf der Seite „Exporte“ wie oben beschrieben unter [Erstellen eines Cloud-Exportspeicherorts](#begin-creating-a-cloud-export-location)

   * Beim [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Geben Sie [!UICONTROL **Abschnitt**] des Dialogfelds [!UICONTROL **Speicherort hinzufügen**] die folgenden Informationen an, um einen Azure SAS-Speicherort zu konfigurieren:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Container-Name**] | Der Container innerhalb des von Ihnen angegebenen Kontos, an den Customer Journey Analytics-Daten gesendet werden sollen. |
   | [!UICONTROL **Präfix**] | Der Ordner im Container, in dem Sie die Daten ablegen möchten. Geben Sie einen Ordnernamen an und fügen Sie dann nach dem Namen einen Schrägstrich hinzu, um den Ordner zu erstellen. Beispiel: `folder_name/`<p>Stellen Sie sicher, dass der SAS-Token-Speicher, den Sie bei der Konfiguration des Azure SAS-Kontos im Feld „Key Vault-Geheimnisname“ angegeben haben, über die `Write`-Berechtigung verfügt. Dadurch kann das SAS-Token Dateien in Ihrem Azure-Container erstellen. <p>Wenn Sie möchten, dass das SAS-Token auch Dateien überschreibt, stellen Sie sicher, dass der SAS-Token-Speicher die `Delete`-Berechtigung besitzt.</p><p>Weitere Informationen finden Sie in der Azure Blob Storage-Dokumentation unter [Blob Storage-Ressourcen](https://learn.microsoft.com/de-de/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources).</p> |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. Sie können jetzt Daten aus Analysis Workspace an das -Konto und den Speicherort exportieren, die Sie konfiguriert haben. Informationen zum Exportieren von Daten in die Cloud finden Sie unter [Exportieren von Projektdaten in die Cloud](/help/analysis-workspace/export/export-cloud.md).

### Azure RBAC

1. Beginnen Sie mit der Erstellung eines Cloud-Exportspeicherorts auf eine der folgenden Arten:

   * Klicken Sie auf der Seite „Exporte“ wie oben beschrieben unter [Erstellen eines Cloud-Exportspeicherorts](#begin-creating-a-cloud-export-location)

   * Beim [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Geben Sie [!UICONTROL **Abschnitt**] des Dialogfelds [!UICONTROL **Speicherort hinzufügen**] die folgenden Informationen an, um einen Azure RBAC-Speicherort zu konfigurieren:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Container**] | Der Container innerhalb des von Ihnen angegebenen Kontos, an den Customer Journey Analytics-Daten gesendet werden sollen. Stellen Sie sicher, dass Sie Berechtigungen zum Hochladen von Dateien in die Azure-Anwendung erteilen, die Sie zuvor erstellt haben. |
   | [!UICONTROL **Präfix**] | Der Ordner im Container, in dem Sie die Daten ablegen möchten. Geben Sie einen Ordnernamen an und fügen Sie dann nach dem Namen einen Schrägstrich hinzu, um den Ordner zu erstellen. Beispiel: `folder_name/`<p>Stellen Sie sicher, dass die Anwendungs-ID, die Sie beim Konfigurieren des Azure RBAC-Kontos angegeben haben, der Rolle `Storage Blob Data Contributor` zugeteilt wurde, damit der Zugriff auf den Container (Ordner) möglich ist.</p> <p>Weitere Informationen finden Sie unter [Integrierte Azure-Rollen](https://learn.microsoft.com/de-de/azure/role-based-access-control/built-in-roles).</p> |
   | [!UICONTROL **Konto**] | Das Azure-Speicherkonto. |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. Sie können jetzt Daten aus Analysis Workspace an das -Konto und den Speicherort exportieren, die Sie konfiguriert haben. Informationen zum Exportieren von Daten in die Cloud finden Sie unter [Exportieren von Projektdaten in die Cloud](/help/analysis-workspace/export/export-cloud.md).

### Snowflake

1. Beginnen Sie mit der Erstellung eines Cloud-Exportspeicherorts auf eine der folgenden Arten:

   * Klicken Sie auf der Seite „Exporte“ wie oben beschrieben unter [Erstellen eines Cloud-Exportspeicherorts](#begin-creating-a-cloud-export-location)

   * Beim [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Geben Sie [!UICONTROL **Abschnitt**] des Dialogfelds [!UICONTROL **Speicherort hinzufügen**] die folgenden Informationen an, um einen Snowflake-Speicherort zu konfigurieren:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **DB**] | Die angegebene Datenbank sollte eine vorhandene Datenbank sein. Die von Ihnen erstellte Rolle muss über Berechtigungen für den Zugriff auf diese Datenbank verfügen.<p>Dies ist die Datenbank, die mit dem Namen des Stadiums verknüpft ist.</p><p>Sie können diese Rollenberechtigungen der Datenbank in Snowflake mit dem folgenden Befehl gewähren: `GRANT USAGE ON DATABASE <your_database> TO ROLE <your_role>;`</p> <p>Weitere Informationen finden Sie auf der Seite [Befehle für Datenbank, Schema und Freigabe“ in der Snowflake-Dokumentation](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **Schema**] | Das angegebene Schema sollte ein vorhandenes Schema sein. Die von Ihnen erstellte Rolle muss über Berechtigungen für den Zugriff auf dieses Schema verfügen.<p>Dies ist das Schema, das mit dem Namen des Stadiums verknüpft ist.<p>Sie können die von Ihnen erstellte Rolle dem Schema in Snowflake mit dem folgenden Befehl zuweisen: `GRANT USAGE ON SCHEMA <your_database>.<your_schema> TO ROLE <your_role>;`</p><p>Weitere Informationen finden Sie auf der Seite [Befehle für Datenbank, Schema und Freigabe“ in der Snowflake-Dokumentation](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **Name des Stadiums**] | Der Name des internen Schritts, in dem Datendateien in Snowflake gespeichert werden.<p>Stellen Sie sicher, dass die für das Konto angegebene Rolle Lese- und Schreibzugriff auf diesen Phasennamen hat. (Da Sie Lese- und Schreibzugriff gewähren, empfehlen wir die Verwendung eines Schritts, der nur von Adobe verwendet wird.)<p>Sie können mit dem folgenden Befehl Lese- und Schreibzugriff auf den Namen des Stadiums in Snowflake gewähren: `GRANT READ, WRITE ON STAGE <your_database>.<your_schema>.<your_stage_name> TO ROLE <your_role>;`</p> <p>Informationen zum Gewähren von Berechtigungen für eine Rolle finden Sie unter [Gewähren von Berechtigungen in der Dokumentation zu Snowflake](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege). <p>Weitere Informationen zum Namen des Stadiums finden Sie auf der Seite [Auswählen eines internen Stadiums für lokale Dateien“ in der Dokumentation zu Snowflake](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **Staging-**] | Der Pfad zu dem Speicherort, an dem Datendateien in Snowflake gespeichert werden. <p>Weitere Informationen finden Sie auf der Seite [Auswahl eines internen Schritts für lokale Dateien“ in der Dokumentation zu Snowflake](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. Sie können jetzt Daten aus Analysis Workspace an das -Konto und den Speicherort exportieren, die Sie konfiguriert haben. Informationen zum Exportieren von Daten in die Cloud finden Sie unter [Exportieren von Projektdaten in die Cloud](/help/analysis-workspace/export/export-cloud.md).
