---
description: Konfigurieren des Cloud-Exportspeicherorts, an den Customer Journey Analytics-Daten gesendet werden können
keywords: Analysis Workspace
title: Konfigurieren von Cloud-Exportspeicherorten
feature: Components
exl-id: 93f1cca0-95da-41a0-a4f9-5ab620a5b9da
role: User, Admin
source-git-commit: 1bf36f60b0b3aec04bb1452e5f63f97051d9bb50
workflow-type: tm+mt
source-wordcount: '1932'
ht-degree: 21%

---

# Konfigurieren von Cloud-Exportspeicherorten

Bevor Sie Customer Journey Analytics-Berichte an ein Cloud-Ziel exportieren können, wie unter [Customer Journey Analytics-Berichte in die Cloud exportieren](/help/analysis-workspace/export/export-cloud.md) beschrieben, müssen Sie den Speicherort hinzufügen und konfigurieren, an dem die Daten gesendet werden sollen.

Dieser Prozess besteht aus dem Hinzufügen und Konfigurieren des Kontos (z. B. Amazon S3, Google Cloud Platform usw.), wie unter [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md) beschrieben, und anschließendem Hinzufügen und Konfigurieren des Speicherorts innerhalb dieses Kontos (z. B. eines Ordners innerhalb des Kontos), wie in diesem Artikel beschrieben.

Informationen zum Verwalten vorhandener Speicherorte, einschließlich Anzeigen, Bearbeiten und Löschen von Standorten, finden Sie unter [Verwalten von Cloud-Exportspeicherorten und -Konten](/help/components/exports/manage-export-locations.md).

## Erstellen eines Cloud-Export-Standorts

1. Sie müssen ein Konto hinzufügen, bevor Sie einen Ort hinzufügen können. Fügen Sie, falls noch nicht geschehen, ein Konto hinzu, wie unter [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md) beschrieben.

1. Wählen Sie unter Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Wählen Sie die Registerkarte [!UICONTROL **Standorte**] und dann [!UICONTROL **Ort hinzufügen**] aus.

   ![Exportiert das Fenster mit ausgewählter Registerkarte &quot;Position&quot;, um die Schaltfläche &quot;Position hinzufügen&quot;hervorzuheben](assets/location-add.png)

   Oder

   Wählen Sie die Registerkarte [!UICONTROL **Standortkonten**], wählen Sie das 3-Punkt-Symbol für ein vorhandenes Konto aus, dem Sie einen Ort hinzufügen möchten, und wählen Sie dann [!UICONTROL **Ort hinzufügen**] aus.

   ![GCP-Konto und Ellipse-Dropdown-Menü mit ausgewähltem Standort hinzufügen](assets/add-location-existing-account.png)

   Das Dialogfeld Standort wird angezeigt.

1. Geben Sie die folgenden Informationen an:
|Feld | Funktion |
|—|—|
| [!UICONTROL **Name**] | Der Name des Standorts.  |
| [!UICONTROL **Beschreibung**] | Geben Sie eine kurze Beschreibung des Standorts ein, um ihn von anderen Positionen im Konto zu unterscheiden. |
| [!UICONTROL **Stellen Sie den Standort allen Benutzern in Ihrer Organisation zur Verfügung**] | **Hinweis:** Diese Funktion befindet sich in der eingeschränkten Testphase der Veröffentlichung und ist möglicherweise noch nicht in Ihrer Umgebung verfügbar. Diese Anmerkung wird entfernt, wenn die Funktion allgemein verfügbar ist. Informationen zum Analytics-Veröffentlichungsprozess finden Sie unter [Veröffentlichung von Funktionen für Customer Journey Analytics](/help/release-notes/releases.md). <p>Aktivieren Sie diese Option, damit andere Benutzer in Ihrer Organisation den Standort verwenden können.</p> <p>Beachten Sie beim Freigeben von Orten Folgendes:</p><ul><li>Die Freigabe von freigegebenen Speicherorten kann nicht aufgehoben werden.</li><li>Freigegebene Standorte können nur vom Eigentümer des Standorts bearbeitet werden.</li><li>Standorte können nur freigegeben werden, wenn auch das Konto, mit dem der Ort verknüpft ist, freigegeben wurde.</li></ul> |
| [!UICONTROL **Standortkonto**] | Wählen Sie das Konto aus, in dem Sie den Standort erstellen möchten. Informationen zum Erstellen eines Kontos finden Sie unter [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md). |

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
>Achten Sie beim Exportieren von Customer Journey Analytics-Berichten in die Adobe Experience Platform Data Landing Zone darauf, die Daten innerhalb von 7 Tagen herunterzuladen und sie dann aus der AEP Data Landing Zone zu löschen. Nach 7 Tagen werden die Daten automatisch aus der AEP Data Landing Zone gelöscht.

1. Beginnen Sie mit der Erstellung eines Cloud-Export-Standorts auf eine der folgenden Arten:

   * Beginnen Sie auf der Seite &quot;Exporte&quot;wie oben beschrieben in [Erstellen eines Cloud-Exportspeicherorts beginnen](#begin-creating-a-cloud-export-location)

   * Beim [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Geben Sie im Abschnitt [!UICONTROL **Standorteigenschaften**] des Dialogfelds [!UICONTROL **Ort hinzufügen**] die folgenden Informationen an, um einen Adobe Experience Platform-Einstiegszonen-Speicherort zu konfigurieren:

   <!-- still need to update; can't create AEP account -->

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Präfix**] | Der Ordner im Container, in dem Sie die Daten ablegen möchten. Geben Sie einen Ordnernamen an und fügen Sie nach dem Namen einen Schrägstrich hinzu, um den Ordner zu erstellen. Beispiel: `folder_name/` |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. Sie können jetzt Daten aus Analysis Workspace in das Konto und den Speicherort exportieren, die Sie konfiguriert haben. Informationen zum Exportieren von Daten in die Cloud finden Sie unter [Exportieren von Projektdaten in die Cloud](/help/analysis-workspace/export/export-cloud.md).

1. Die einfachste Möglichkeit, auf Ihre Daten in der AEP Data Landing Zone zuzugreifen, besteht in der Verwendung des Microsoft Azure Storage Explorer. Dies ist dasselbe Tool, das in den Anweisungen zum Konfigurieren des [AEP Data Landing Zone-Kontos](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone) verwendet wird.

   1. Öffnen Sie den [Microsoft Azure Storage Explorer](https://azure.microsoft.com/en-us/products/storage/storage-explorer/).

   1. Navigieren Sie zu [!UICONTROL **Speicherkonten**] > [!UICONTROL **(Attached Containers)**] > [!UICONTROL **Blob Containers**] > **[!UICONTROL cjaexport-_number_]**>*** Ihr_Containername ***.

      >[!NOTE]
      >
      >Der Ordnername **[!UICONTROL cjaexport-_number_]**ist der Standardname, der von Azure Storage Explorer bereitgestellt wird. Wenn Sie nur eine Verbindung mit Ihrem SAS-URI haben (was normal ist), lautet der Name dieses Ordners **[!UICONTROL cjaexport-1]**.


      ![Zugreifen auf Dateien im Azure Storage Explorer](assets/azure-storage-explorer-access.png)

   1. Wählen Sie den Export aus, den Sie herunterladen möchten, und klicken Sie dann zum Herunterladen auf [!UICONTROL **Herunterladen**] .

### Amazon S3 Role ARN

1. Beginnen Sie mit der Erstellung eines Cloud-Export-Standorts auf eine der folgenden Arten:

   * Beginnen Sie auf der Seite &quot;Exporte&quot;wie oben beschrieben in [Erstellen eines Cloud-Exportspeicherorts beginnen](#begin-creating-a-cloud-export-location)

   * Beim [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Geben Sie im Abschnitt [!UICONTROL **Location properties**] des Dialogfelds [!UICONTROL **Add location**] die folgenden Informationen an, um einen Amazon S3 Role ARN-Speicherort zu konfigurieren:

   <!-- still need to update; can't create S3 role ARN account -->

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Behälter**] | Der Behälter in Ihrem Amazon S3-Konto, an den Customer Journey Analytics-Daten gesendet werden sollen. <p>Stellen Sie sicher, dass die von Adobe bereitgestellte Benutzer-ARN über die Berechtigung `S3:PutObject` verfügt, um Dateien in diesen Behälter hochzuladen. </p><p>Bucket-Namen müssen bestimmten Benennungsregeln entsprechen. Bucket-Namen müssen etwa zwischen 3 und 63 Zeichen lang sein, dürfen nur aus Kleinbuchstaben, Zahlen, Punkten (.) und Bindestrichen (-) bestehen und müssen mit einem Buchstaben oder einer Zahl beginnen und enden. [Eine vollständige Liste der Benennungsregeln finden Sie in der AWS-Dokumentation.](https://docs.aws.amazon.com/de_de/AmazonS3/latest/userguide/bucketnamingrules.html). </p> |
   | [!UICONTROL **Präfix**] | Der Ordner im Bucket, in den Sie die Daten ablegen möchten. Geben Sie einen Ordnernamen an und fügen Sie nach dem Namen einen Schrägstrich hinzu, um den Ordner zu erstellen. (Beispiel: Ordnername/) |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. Sie können jetzt Daten aus Analysis Workspace in das Konto und den Speicherort exportieren, die Sie konfiguriert haben. Informationen zum Exportieren von Daten in die Cloud finden Sie unter [Exportieren von Projektdaten in die Cloud](/help/analysis-workspace/export/export-cloud.md).

### Google Cloud Platform

1. Beginnen Sie mit der Erstellung eines Cloud-Export-Standorts auf eine der folgenden Arten:

   * Beginnen Sie auf der Seite &quot;Exporte&quot;wie oben beschrieben in [Erstellen eines Cloud-Exportspeicherorts beginnen](#begin-creating-a-cloud-export-location)

   * Beim [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Geben Sie im Abschnitt [!UICONTROL **Standorteigenschaften**] des Dialogfelds [!UICONTROL **Speicherort hinzufügen**] die folgenden Informationen an, um einen Google Cloud Platform-Speicherort zu konfigurieren:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Behälter**] | Der Bucket in Ihrem GCP-Konto, an den Customer Journey Analytics-Daten gesendet werden sollen. <p>Vergewissern Sie sich, dass Sie dem durch Adobe bereitgestellten Prinzipal die Berechtigung `roles/storage.objectCreator` erteilt haben. (Der Prinzipal wird beim [Konfigurieren des Google Cloud Platform-Kontos](/help/components/exports/cloud-export-accounts.md) bereitgestellt.) <p>Informationen zum Gewähren von Berechtigungen finden Sie in der Google Cloud-Dokumentation unter [Hauptkonto zu einer Richtlinie auf Bucket-Ebene hinzufügen](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add).</p><p>Wenn Ihre Organisation [Organisationsrichtlinieneinschränkungen](https://cloud.google.com/storage/docs/org-policy-constraints) verwendet, um nur das Google Cloud Platform-Konto in Ihrer Zulassungsliste zuzulassen, benötigen Sie die folgende Adobe-eigene Organisations-ID für Google Cloud Platform: <ul><li>`DISPLAY_NAME`: `adobe.com`</li><li>`ID`: `178012854243`</li><li>`DIRECTORY_CUSTOMER_ID`: `C02jo8puj`</li></ul> </p> |
   | [!UICONTROL **Präfix**] | Der Ordner im Bucket, in den Sie die Daten ablegen möchten. Geben Sie einen Ordnernamen an und fügen Sie nach dem Namen einen Schrägstrich hinzu, um den Ordner zu erstellen. (Beispiel: Ordnername/) |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. Sie können jetzt Daten aus Analysis Workspace in das Konto und den Speicherort exportieren, die Sie konfiguriert haben. Informationen zum Exportieren von Daten in die Cloud finden Sie unter [Exportieren von Projektdaten in die Cloud](/help/analysis-workspace/export/export-cloud.md).

### Azure SAS

1. Beginnen Sie mit der Erstellung eines Cloud-Export-Standorts auf eine der folgenden Arten:

   * Beginnen Sie auf der Seite &quot;Exporte&quot;wie oben beschrieben in [Erstellen eines Cloud-Exportspeicherorts beginnen](#begin-creating-a-cloud-export-location)

   * Beim [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Geben Sie im Abschnitt [!UICONTROL **Location properties**] des Dialogfelds [!UICONTROL **Add location**] die folgenden Informationen an, um einen Azure SAS-Speicherort zu konfigurieren:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Container-Name**] | Der Container innerhalb des von Ihnen angegebenen Kontos, an den Customer Journey Analytics-Daten gesendet werden sollen. |
   | [!UICONTROL **Präfix**] | Der Ordner im Container, in dem Sie die Daten ablegen möchten. Geben Sie einen Ordnernamen an und fügen Sie nach dem Namen einen Schrägstrich hinzu, um den Ordner zu erstellen. Beispiel: `folder_name/`<p>Stellen Sie sicher, dass der SAS-Token-Speicher, den Sie bei der Konfiguration des Azure SAS-Kontos im Feld „Key Vault-Geheimnisname“ angegeben haben, über die `Write`-Berechtigung verfügt. Dadurch kann das SAS-Token Dateien in Ihrem Azure-Container erstellen. <p>Wenn Sie möchten, dass das SAS-Token auch Dateien überschreibt, stellen Sie sicher, dass der SAS-Token-Speicher die `Delete`-Berechtigung besitzt.</p><p>Weitere Informationen finden Sie in der Azure Blob Storage-Dokumentation unter [Blob Storage-Ressourcen](https://learn.microsoft.com/de-de/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources).</p> |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. Sie können jetzt Daten aus Analysis Workspace in das Konto und den Speicherort exportieren, die Sie konfiguriert haben. Informationen zum Exportieren von Daten in die Cloud finden Sie unter [Exportieren von Projektdaten in die Cloud](/help/analysis-workspace/export/export-cloud.md).

### Azure RBAC

1. Beginnen Sie mit der Erstellung eines Cloud-Export-Standorts auf eine der folgenden Arten:

   * Beginnen Sie auf der Seite &quot;Exporte&quot;wie oben beschrieben in [Erstellen eines Cloud-Exportspeicherorts beginnen](#begin-creating-a-cloud-export-location)

   * Beim [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Geben Sie im Abschnitt [!UICONTROL **Location properties**] des Dialogfelds [!UICONTROL **Add location**] die folgenden Informationen an, um einen Azure RBAC-Speicherort zu konfigurieren:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Container**] | Der Container innerhalb des von Ihnen angegebenen Kontos, an den Customer Journey Analytics-Daten gesendet werden sollen. Stellen Sie sicher, dass Sie Berechtigungen zum Hochladen von Dateien in die Azure-Anwendung erteilen, die Sie zuvor erstellt haben. |
   | [!UICONTROL **Präfix**] | Der Ordner im Container, in dem Sie die Daten ablegen möchten. Geben Sie einen Ordnernamen an und fügen Sie nach dem Namen einen Schrägstrich hinzu, um den Ordner zu erstellen. Beispiel: `folder_name/`<p>Stellen Sie sicher, dass die Anwendungs-ID, die Sie beim Konfigurieren des Azure RBAC-Kontos angegeben haben, der Rolle `Storage Blob Data Contributor` zugeteilt wurde, damit der Zugriff auf den Container (Ordner) möglich ist.</p> <p>Weitere Informationen finden Sie unter [Integrierte Azure-Rollen](https://learn.microsoft.com/de-de/azure/role-based-access-control/built-in-roles).</p> |
   | [!UICONTROL **Konto**] | Das Azure-Speicherkonto. |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. Sie können jetzt Daten aus Analysis Workspace in das Konto und den Speicherort exportieren, die Sie konfiguriert haben. Informationen zum Exportieren von Daten in die Cloud finden Sie unter [Exportieren von Projektdaten in die Cloud](/help/analysis-workspace/export/export-cloud.md).

### Snowflake

1. Beginnen Sie mit der Erstellung eines Cloud-Export-Standorts auf eine der folgenden Arten:

   * Beginnen Sie auf der Seite &quot;Exporte&quot;wie oben beschrieben in [Erstellen eines Cloud-Exportspeicherorts beginnen](#begin-creating-a-cloud-export-location)

   * Beim [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Geben Sie im Abschnitt [!UICONTROL **Positionseigenschaften**] des Dialogfelds [!UICONTROL **Speicherort hinzufügen**] die folgenden Informationen an, um einen Snowflake-Speicherort zu konfigurieren:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **DB**] | Die angegebene Datenbank sollte eine bestehende Datenbank sein. Die von Ihnen erstellte Rolle muss über Berechtigungen für den Zugriff auf diese Datenbank verfügen.<p>Dies ist die Datenbank, die mit dem Staging-Namen verknüpft ist.</p><p>Sie können diese Rollenberechtigungen der Datenbank unter Snowflake mit dem folgenden Befehl erteilen: `GRANT USAGE ON DATABASE <your_database> TO ROLE <your_role>;`</p> <p>Weitere Informationen finden Sie auf der Seite [Datenbank-, Schema- und Freigabebefehle in der Snowflake-Dokumentation](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **Schema**] | Das angegebene Schema sollte ein vorhandenes Schema sein. Die von Ihnen erstellte Rolle muss über Berechtigungen für den Zugriff auf dieses Schema verfügen.<p>Dies ist das Schema, das mit dem Staging-Namen verknüpft ist.<p>Mit dem folgenden Befehl können Sie dem Schema in Snowflake die Rolle zuweisen, die Sie für das Schema erstellt haben: `GRANT USAGE ON SCHEMA <your_database>.<your_schema> TO ROLE <your_role>;`</p><p>Weitere Informationen finden Sie auf der Seite [Datenbank-, Schema- und Freigabebefehle in der Snowflake-Dokumentation](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **Name der Bühne**] | Der Name der internen Phase, in der Datendateien im Snowflake gespeichert werden.<p>Stellen Sie sicher, dass die Rolle, die Sie im Konto angegeben haben, Lese- und Schreibzugriff auf diesen Staging-Namen hat. (Da Sie Lese- und Schreibzugriff gewähren, empfehlen wir die Verwendung einer Bühne, die nur von Adobe verwendet wird.)<p>Mit dem folgenden Befehl können Sie Lese- und Schreibzugriff auf den Staging-Namen im Snowflake gewähren: `GRANT READ, WRITE ON STAGE <your_database>.<your_schema>.<your_stage_name> TO ROLE <your_role>;`</p> <p>Informationen zum Gewähren von Berechtigungen für eine Rolle finden Sie unter [Gewähren von Berechtigungen in der Snowflake-Dokumentation](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege). <p>Weitere Informationen zum Staging-Namen finden Sie auf der Seite &quot;[Auswählen einer internen Stage für lokale Dateien&quot;in der Snowflake-Dokumentation](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage)&quot;.</p> |
   | [!UICONTROL **Staging-Pfad**] | Der Pfad zum Speicherort, an dem Datendateien unter Snowflake gespeichert werden. <p>Weitere Informationen finden Sie auf der Seite &quot;[Auswählen einer internen Phase für lokale Dateien&quot;in der Snowflake-Dokumentation](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. Sie können jetzt Daten aus Analysis Workspace in das Konto und den Speicherort exportieren, die Sie konfiguriert haben. Informationen zum Exportieren von Daten in die Cloud finden Sie unter [Exportieren von Projektdaten in die Cloud](/help/analysis-workspace/export/export-cloud.md).
