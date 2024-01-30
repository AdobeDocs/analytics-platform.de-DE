---
description: Konfigurieren des Cloud-Exportspeicherorts, an den Customer Journey Analytics-Daten gesendet werden können
keywords: Analysis Workspace
title: Konfigurieren von Cloud-Exportspeicherorten
feature: Components
exl-id: 93f1cca0-95da-41a0-a4f9-5ab620a5b9da
role: User, Admin
source-git-commit: e16d071df04d91ec6627efd250515fb2d54515bb
workflow-type: tm+mt
source-wordcount: '1635'
ht-degree: 4%

---

# Konfigurieren von Cloud-Exportspeicherorten

Bevor Sie Customer Journey Analytics-Berichte an ein Cloud-Ziel exportieren können, siehe [Customer Journey Analytics-Berichte in die Cloud exportieren](/help/analysis-workspace/export/export-cloud.md)müssen Sie den Ort hinzufügen und konfigurieren, an den die Daten gesendet werden sollen.

Dieser Prozess besteht aus dem Hinzufügen und Konfigurieren des Kontos (z. B. Amazon S3, Google Cloud Platform usw.), wie unter [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md)und dann den Speicherort innerhalb dieses Kontos (z. B. einen Ordner innerhalb des Kontos) hinzufügen und konfigurieren, wie in diesem Artikel beschrieben.

Informationen zum Verwalten vorhandener Standorte, einschließlich Anzeigen, Bearbeiten und Löschen von Standorten, finden Sie unter [Verwalten von Cloud-Exportspeicherorten und -konten](/help/components/exports/manage-export-locations.md).

## Erstellen eines Cloud-Export-Standorts

1. Sie müssen ein Konto hinzufügen, bevor Sie einen Ort hinzufügen können. Fügen Sie, falls noch nicht geschehen, ein Konto wie unter [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md).

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Standorte**] Registerkarte und wählen Sie [!UICONTROL **Ort hinzufügen**].

   ![Exportiert ein Fenster mit ausgewählter Registerkarte Standort , in dem die Schaltfläche Standort hinzufügen hervorgehoben wird](assets/location-add.png)

   Oder

   Wählen Sie die [!UICONTROL **Standortkonten**] Registerkarte das 3-Punkt-Symbol für ein vorhandenes Konto auswählen, dem Sie einen Ort hinzufügen möchten, und dann [!UICONTROL **Ort hinzufügen**].

   ![GCP-Konto und Ellipse-Dropdown-Menü mit ausgewähltem Standort hinzufügen](assets/add-location-existing-account.png)

   Das Dialogfeld Standort wird angezeigt.

1. Geben Sie die folgenden Informationen an: |Feld | Funktion | |—|—| | [!UICONTROL **Name**] | Der Name des Standorts.  | | [!UICONTROL **Beschreibung**] | Geben Sie eine kurze Beschreibung des Standorts ein, um ihn von anderen Positionen im Konto zu unterscheiden. | | [!UICONTROL **Standortkonto**] | Wählen Sie das Konto aus, in dem Sie den Standort erstellen möchten. Informationen zum Erstellen eines Kontos finden Sie unter [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md). |

1. Im [!UICONTROL **Standorteigenschaften**] Informationen zum Kontotyp Ihres Standortkontos angeben.

   Fahren Sie mit dem folgenden Abschnitt fort, der dem Kontotyp entspricht, den Sie in der [!UICONTROL **Standortkonto**] -Feld.

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

   * Auf der Seite &quot;Exporte&quot;, wie oben beschrieben, unter [Erstellen eines Cloud-Export-Standorts](#begin-creating-a-cloud-export-location)

   * Wann [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Im [!UICONTROL **Standorteigenschaften**] Abschnitt [!UICONTROL **Ort hinzufügen**] Geben Sie die folgenden Informationen an, um einen Adobe Experience Platform Data Landing Zone-Speicherort zu konfigurieren:

   <!-- still need to update; can't create AEP account -->

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Präfix**] | Der Ordner im Container, in den Sie die Daten ablegen möchten. Geben Sie einen Ordnernamen an und fügen Sie nach dem Namen einen Schrägstrich hinzu, um den Ordner zu erstellen. Beispiel: `folder_name/` |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. Sie können jetzt Daten aus Analysis Workspace in das Konto und den Speicherort exportieren, die Sie konfiguriert haben. Informationen zum Exportieren von Daten in die Cloud finden Sie unter [Exportieren von Projektdaten in die Cloud](/help/analysis-workspace/export/export-cloud.md).

1. Die einfachste Möglichkeit, auf Ihre Daten in der AEP Data Landing Zone zuzugreifen, besteht in der Verwendung des Microsoft Azure Storage Explorer. Dies ist dasselbe Tool, das in den Anweisungen zum Konfigurieren der [AEP Data Landing Zone-Konto](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone).

   1. Öffnen Sie die [Microsoft Azure Storage Explorer](https://azure.microsoft.com/en-us/products/storage/storage-explorer/).

   1. Navigieren Sie zu [!UICONTROL **Speicherkonten**] > [!UICONTROL **(Angehängte Container)**] > [!UICONTROL **Blob-Container**] > **[!UICONTROL cjaexport-_number_]**>*** your_container_name ***.

      >[!NOTE]
      >
      >Der Ordnername **[!UICONTROL cjaexport-_number_]**ist der Standardname, der von Azure Storage Explorer bereitgestellt wird. Wenn Sie nur eine Verbindung mit Ihrem SAS-URI haben (was normal ist), lautet der Name dieses Ordners **[!UICONTROL cjaexport-1]**.


      ![Auf Dateien in Azure Storage Explorer zugreifen](assets/azure-storage-explorer-access.png)

   1. Wählen Sie den Export aus, den Sie herunterladen möchten, und klicken Sie auf [!UICONTROL **Herunterladen**] herunterladen.

### Amazon S3 Role ARN

1. Beginnen Sie mit der Erstellung eines Cloud-Export-Standorts auf eine der folgenden Arten:

   * Auf der Seite &quot;Exporte&quot;, wie oben beschrieben, unter [Erstellen eines Cloud-Export-Standorts](#begin-creating-a-cloud-export-location)

   * Wann [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Im [!UICONTROL **Standorteigenschaften**] Abschnitt [!UICONTROL **Ort hinzufügen**] Geben Sie die folgenden Informationen an, um einen Amazon S3 Role ARN-Speicherort zu konfigurieren:

   <!-- still need to update; can't create S3 role ARN account -->

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Bucket**] | Der Behälter in Ihrem Amazon S3-Konto, an den Adobe Analytics-Daten gesendet werden sollen. Stellen Sie sicher, dass die von Adobe bereitgestellte Benutzer-ARN Zugriff auf das Hochladen von Dateien in diesen Bucket hat. |
   | [!UICONTROL **Präfix**] | Der Ordner im Behälter, in den Sie die Daten ablegen möchten. Geben Sie einen Ordnernamen an und fügen Sie nach dem Namen einen Schrägstrich hinzu, um den Ordner zu erstellen. Beispiel: folder_name/ |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. Sie können jetzt Daten aus Analysis Workspace in das Konto und den Speicherort exportieren, die Sie konfiguriert haben. Informationen zum Exportieren von Daten in die Cloud finden Sie unter [Exportieren von Projektdaten in die Cloud](/help/analysis-workspace/export/export-cloud.md).

### Google Cloud Platform

1. Beginnen Sie mit der Erstellung eines Cloud-Export-Standorts auf eine der folgenden Arten:

   * Auf der Seite &quot;Exporte&quot;, wie oben beschrieben, unter [Erstellen eines Cloud-Export-Standorts](#begin-creating-a-cloud-export-location)

   * Wann [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Im [!UICONTROL **Standorteigenschaften**] Abschnitt [!UICONTROL **Ort hinzufügen**] Geben Sie die folgenden Informationen an, um einen Google Cloud Platform-Speicherort zu konfigurieren:

   <!-- still need to update; can't create GCP account -->

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Bucket**] | Der Bucket in Ihrem GCP-Konto, an den Customer Journey Analytics-Daten gesendet werden sollen. Stellen Sie sicher, dass Sie dem von Adobe bereitgestellten Prinzipal die Berechtigung zum Hochladen von Dateien in diesen Bucket erteilt haben. (Der Prinzipal wird bereitgestellt, wenn [Konfigurieren des Google Cloud Platform-Kontos](/help/components/exports/cloud-export-accounts.md). Informationen zum Gewähren von Berechtigungen finden Sie unter [Einen Prinzipal zu einer Richtlinie auf Behälterebene hinzufügen](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) in der Dokumentation zu Google Cloud. |
   | [!UICONTROL **Präfix**] | Der Ordner im Behälter, in den Sie die Daten ablegen möchten. Geben Sie einen Ordnernamen an und fügen Sie nach dem Namen einen Schrägstrich hinzu, um den Ordner zu erstellen. Beispiel: folder_name/ |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. Sie können jetzt Daten aus Analysis Workspace in das Konto und den Speicherort exportieren, die Sie konfiguriert haben. Informationen zum Exportieren von Daten in die Cloud finden Sie unter [Exportieren von Projektdaten in die Cloud](/help/analysis-workspace/export/export-cloud.md).

### Azure SAS

1. Beginnen Sie mit der Erstellung eines Cloud-Export-Standorts auf eine der folgenden Arten:

   * Auf der Seite &quot;Exporte&quot;, wie oben beschrieben, unter [Erstellen eines Cloud-Export-Standorts](#begin-creating-a-cloud-export-location)

   * Wann [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Im [!UICONTROL **Standorteigenschaften**] Abschnitt [!UICONTROL **Ort hinzufügen**] Geben Sie die folgenden Informationen an, um einen Azure SAS-Speicherort zu konfigurieren:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Container name**] | Der Container innerhalb des von Ihnen angegebenen Kontos, an den Customer Journey Analytics-Daten gesendet werden sollen. |
   | [!UICONTROL **Präfix**] | Der Ordner im Container, in den Sie die Daten ablegen möchten. Geben Sie einen Ordnernamen an und fügen Sie nach dem Namen einen Schrägstrich hinzu, um den Ordner zu erstellen. Beispiel: `folder_name/` |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. Sie können jetzt Daten aus Analysis Workspace in das Konto und den Speicherort exportieren, die Sie konfiguriert haben. Informationen zum Exportieren von Daten in die Cloud finden Sie unter [Exportieren von Projektdaten in die Cloud](/help/analysis-workspace/export/export-cloud.md).

### Azure RBAC

1. Beginnen Sie mit der Erstellung eines Cloud-Export-Standorts auf eine der folgenden Arten:

   * Auf der Seite &quot;Exporte&quot;, wie oben beschrieben, unter [Erstellen eines Cloud-Export-Standorts](#begin-creating-a-cloud-export-location)

   * Wann [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Im [!UICONTROL **Standorteigenschaften**] Abschnitt [!UICONTROL **Ort hinzufügen**] Geben Sie die folgenden Informationen an, um einen Azure RBAC-Speicherort zu konfigurieren:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Container**] | Der Container innerhalb des von Ihnen angegebenen Kontos, an den Adobe Analytics-Daten gesendet werden sollen. Stellen Sie sicher, dass Sie Berechtigungen zum Hochladen von Dateien in die Azure-Anwendung erteilen, die Sie zuvor erstellt haben. |
   | [!UICONTROL **Präfix**] | Der Ordner im Container, in den Sie die Daten ablegen möchten. Geben Sie einen Ordnernamen an und fügen Sie nach dem Namen einen Schrägstrich hinzu, um den Ordner zu erstellen. Beispiel: `folder_name/` |
   | [!UICONTROL **Konto**] | Das Azure-Speicherkonto. |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. Sie können jetzt Daten aus Analysis Workspace in das Konto und den Speicherort exportieren, die Sie konfiguriert haben. Informationen zum Exportieren von Daten in die Cloud finden Sie unter [Exportieren von Projektdaten in die Cloud](/help/analysis-workspace/export/export-cloud.md).

### Snowflake

1. Beginnen Sie mit der Erstellung eines Cloud-Export-Standorts auf eine der folgenden Arten:

   * Auf der Seite &quot;Exporte&quot;, wie oben beschrieben, unter [Erstellen eines Cloud-Export-Standorts](#begin-creating-a-cloud-export-location)

   * Wann [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Im [!UICONTROL **Standorteigenschaften**] Abschnitt [!UICONTROL **Ort hinzufügen**] Geben Sie die folgenden Informationen an, um einen Snowflake-Speicherort zu konfigurieren:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **DB**] | Die angegebene Datenbank sollte eine bestehende Datenbank sein. Die von Ihnen erstellte Rolle muss über Berechtigungen für den Zugriff auf diese Datenbank verfügen.<p>Dies ist die Datenbank, die mit dem Staging-Namen verknüpft ist.</p><p>Sie können diese Rollenberechtigungen der Datenbank unter Snowflake mit dem folgenden Befehl gewähren: `GRANT USAGE ON DATABASE <your_database> TO ROLE <your_role>;`</p> <p>Weitere Informationen finden Sie unter [Seite &quot;Datenbank&quot;, &quot;Schema&quot;und &quot;Befehle freigeben&quot;in der Snowflake-Dokumentation](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **Schema**] | Das angegebene Schema sollte ein vorhandenes Schema sein. Die von Ihnen erstellte Rolle muss über Berechtigungen für den Zugriff auf dieses Schema verfügen.<p>Dies ist das Schema, das mit dem Staging-Namen verknüpft ist.<p>Mit dem folgenden Befehl können Sie dem Schema in Snowflake die Rolle zuweisen, die Sie für das Schema erstellt haben: `GRANT USAGE ON SCHEMA <your_database>.<your_schema> TO ROLE <your_role>;`</p><p>Weitere Informationen finden Sie unter [Seite &quot;Datenbank&quot;, &quot;Schema&quot;und &quot;Befehle freigeben&quot;in der Snowflake-Dokumentation](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **Staging-Name**] | Der Name der internen Phase, in der Datendateien im Snowflake gespeichert werden.<p>Stellen Sie sicher, dass die Rolle, die Sie im Konto angegeben haben, Lese- und Schreibzugriff auf diesen Staging-Namen hat. (Da Sie Lese- und Schreibzugriff gewähren, empfehlen wir die Verwendung einer Bühne, die nur von Adobe verwendet wird.)<p>Mit dem folgenden Befehl können Sie Lese- und Schreibzugriff auf den Staging-Namen im Snowflake gewähren: `GRANT READ, WRITE ON STAGE <your_database>.<your_schema>.<your_stage_name> TO ROLE <your_role>;`</p> <p>Informationen zum Gewähren von Berechtigungen für eine Rolle finden Sie unter [Gewähren von Berechtigungen in der Snowflake-Dokumentation](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege). <p>Weitere Informationen zum Namen der Bühne finden Sie unter [Auswählen einer internen Phase für lokale Dateien in der Snowflake-Dokumentation](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **Staging-Pfad**] | Der Pfad zum Speicherort, an dem Datendateien unter Snowflake gespeichert werden. <p>Weitere Informationen finden Sie unter [Auswählen einer internen Phase für lokale Dateien in der Snowflake-Dokumentation](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. Sie können jetzt Daten aus Analysis Workspace in das Konto und den Speicherort exportieren, die Sie konfiguriert haben. Informationen zum Exportieren von Daten in die Cloud finden Sie unter [Exportieren von Projektdaten in die Cloud](/help/analysis-workspace/export/export-cloud.md).
