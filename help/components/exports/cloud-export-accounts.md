---
description: Konfigurieren des Cloud-Exportkontos, an das Customer Journey Analytics-Daten gesendet werden können
keywords: Analysis Workspace
title: Konfigurieren von Cloud-Exportkonten
feature: Components
exl-id: 7c9d100f-0dbd-4dd2-b20b-d2ee117f1b7a
role: User, Admin
source-git-commit: 9a0e6ed66a20eac1fa5f94efd378842a579826c0
workflow-type: tm+mt
source-wordcount: '2009'
ht-degree: 29%

---

# Konfigurieren von Cloud-Exportkonten

Bevor Sie Customer Journey Analytics-Berichte an ein Cloud-Ziel exportieren können, siehe [Customer Journey Analytics-Berichte in die Cloud exportieren](/help/analysis-workspace/export/export-cloud.md)hinzugefügt und konfiguriert werden, an die die Daten gesendet werden sollen.

Dieser Prozess besteht aus dem Hinzufügen und Konfigurieren des Kontos (z. B. Amazon S3, Google Cloud Platform usw.), wie in diesem Artikel beschrieben, und anschließendem Hinzufügen und Konfigurieren des Speicherorts innerhalb dieses Kontos (z. B. eines Ordners innerhalb des Kontos), wie in [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md).

Informationen zum Verwalten vorhandener Konten, einschließlich Anzeigen, Bearbeiten und Löschen von Konten, finden Sie unter [Verwalten von Cloud-Exportspeicherorten und -konten](/help/components/exports/manage-export-locations.md).

## Erstellen eines Cloud-Exportkontos beginnen

1. Vergewissern Sie sich, dass Sie die [Mindestanforderungen](/help/analysis-workspace/export/export-cloud.md#minimum-requirements) zum Exportieren von Berichten in die Cloud.
1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].
1. Im [!UICONTROL Exporte] Seite, wählen Sie die [!UICONTROL **Standortkonten**] Registerkarte.

   ![Exportiert Seitenoptionen mit Anzeige Weitere Konten hinzufügen](assets/account-add.png)

1. Auswählen [!UICONTROL **Konto hinzufügen**].

   Das Dialogfeld Konto hinzufügen wird angezeigt.

1. Im [!UICONTROL **Name des Standortkontos**] -Feld einen Namen für das Standortkonto angeben. Dieser Name wird beim Erstellen eines Standorts angezeigt.

1. Im [!UICONTROL **Beschreibung des Standortkontos**] geben Sie eine kurze Beschreibung des Kontos ein, um es von anderen Konten desselben Kontotyps zu unterscheiden.

1. Aktivieren Sie die Option zum [!UICONTROL **Konto für alle Benutzer in Ihrer Organisation verfügbar machen**] , wenn Sie anderen Benutzern in Ihrer Organisation die Verwendung des Kontos erlauben möchten.

   Beachten Sie beim Freigeben von Konten Folgendes:

   * Die Freigabe von Konten, die Sie freigeben, kann nicht aufgehoben werden.

   * Freigegebene Konten können nur vom Eigentümer des Kontos bearbeitet werden.

   * Jeder kann einen Speicherort für das freigegebene Konto erstellen.

   **Hinweis:** Diese Funktion befindet sich in der eingeschränkten Testphase der Veröffentlichung und ist möglicherweise noch nicht in Ihrer Umgebung verfügbar. Diese Anmerkung wird entfernt, wenn die Funktion allgemein verfügbar ist. Informationen zum Analytics-Veröffentlichungsprozess finden Sie unter [Veröffentlichung von Funktionen für Customer Journey Analytics](/help/release-notes/releases.md).

1. Im [!UICONTROL **Kontotyp**] auswählen, wählen Sie den Typ des Cloud-Kontos aus, in das Sie exportieren. Verfügbare Kontotypen sind Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake und AEP Data Landing Zone.

1. Fahren Sie mit dem folgenden Abschnitt fort, der dem [!UICONTROL **Kontotyp**] ausgewählt haben.

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

1. Beginnen Sie mit der Erstellung eines Cloud-Export-Kontos auf eine der folgenden Arten:

   * Auf der Seite &quot;Exporte&quot;, wie oben beschrieben, unter [Erstellen eines Cloud-Exportkontos beginnen](#begin-creating-a-cloud-export-account)

   * Wann [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Wählen Sie [!UICONTROL **Speichern**] aus.

   Die [!UICONTROL **Konto exportieren erstellt**] angezeigt.

   ![Dialogfeld &quot;Konto exportieren&quot;AEP Data Landing Zone](assets/export-account-aep.png)

1. Kopieren Sie den Inhalt der [!UICONTROL **SAS-URI**] in die Zwischenablage. Mit diesem SAS-URI greifen Sie auf die Daten zu, die aus Analysis Workspace aus der AEP Data Landing Zone exportiert werden.

   Wenn dieses Feld leer ist, müssen Sie eine Zugriffsberechtigung für Adobe Experience Platform erhalten.

1. Konfigurieren Sie in Adobe Experience Platform Ihren Dateneinstiegszonen-Container, um den von Ihnen kopierten SAS-URI zu verwenden.

   >[!NOTE]
   >
   >Da das AEP Data Landing Zone-Konto auf Azure basiert, können Sie am einfachsten auf Berichte zugreifen, die Sie in die AEP Data Landing Zone exportieren, indem Sie den Azure Storage Explorer verwenden. Die folgenden Schritte verwenden diese Methode.

   1. Laden Sie die [Microsoft Azure Storage Explorer](https://azure.microsoft.com/en-us/products/storage/storage-explorer/).

   1. Führen Sie in der Adobe Experience Platform-Dokumentation die Schritte aus, die unter [Verbinden Sie Ihren Dateneinstiegszonen-Container mit Azure Storage Explorer.](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#connect-your-data-landing-zone-container-to-azure-storage-explorer).

      Sie können die in den Abschnitten beschriebenen Aufgaben überspringen. [Abrufen der Anmeldeinformationen für Ihre Dateneinstiegszone](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#retrieve-dlz-credentials) und [Aktualisieren der Landingzone-Anmeldedaten für Daten](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#update-dlz-credentials), da der von Ihnen kopierte URI diese Anmeldeinformationen enthält.

   1. Wenn Sie die Adobe Experience Platform-Dokumentation befolgen und zur [!UICONTROL **Blob-Container SAS-URL**] Fügen Sie den SAS-URI ein, den Sie in Schritt 3 kopiert haben.

      >[!NOTE]
      >
      >Sie müssen diese Aktion alle 7 Tage ausführen, da der SAS-URI 7 Tage nach seiner Erstellung abläuft. Sie können ein Skript erstellen, um diesen Prozess zu automatisieren.


      ![Fenster &quot;Verbindungsinformationen&quot;mit SAS-URL-Feld öffnen](assets/blob-container-sas-uri.png)

   1. Auswählen [!UICONTROL **Nächste**] > [!UICONTROL **Verbinden**].

1. In Customer Journey Analytics im [!UICONTROL **Konto exportieren erstellt**] Dialogfeld auswählen [!UICONTROL **OK**].

   ![Dialogfeld &quot;Konto exportieren&quot;AEP Data Landing Zone](assets/export-account-aep.png)

1. Fahren Sie mit [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md).

### Amazon S3 Role ARN

1. Beginnen Sie mit der Erstellung eines Cloud-Export-Kontos auf eine der folgenden Arten:

   * Auf der Seite &quot;Exporte&quot;, wie oben beschrieben, unter [Erstellen eines Cloud-Exportkontos beginnen](#begin-creating-a-cloud-export-account)

   * Wann [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Im [!UICONTROL **Kontoeigenschaften**] Abschnitt [!UICONTROL **Konto hinzufügen**] Geben Sie die folgenden Informationen an:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Rollen-ARN**] | Sie müssen einen Rollen-ARN (Amazon Resource Name) bereitstellen, den Adobe verwenden kann, um Zugriff auf das Amazon S3-Konto zu erhalten. Erstellen Sie hierfür eine IAM-Berechtigungsrichtlinie für das Quellkonto, hängen Sie die Richtlinie an eine Benutzerin oder einen Benutzer an und erstellen Sie dann eine Rolle für das Zielkonto. Spezifische Informationen finden Sie in [dieser AWS-Dokumentation](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

   Die [!UICONTROL **Konto exportieren erstellt**] angezeigt.

   ![Dialogfeld &quot;Konto exportieren&quot;Amazon S3 Rolle ARN](assets/export-account-amazons3.png)

1. Kopieren Sie den Inhalt der [!UICONTROL **Benutzer-ARN**] in die Zwischenablage. Der Benutzer-ARN (Amazon Resource Name) wird von Adobe bereitgestellt. Sie müssen diesen Benutzer an die Richtlinie anhängen, die Sie in Amazon S3 Role ARN erstellt haben.

1. Auswählen [!UICONTROL **OK**].

1. Fahren Sie mit [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md).

### Google Cloud Platform

1. Beginnen Sie mit der Erstellung eines Cloud-Export-Kontos auf eine der folgenden Arten:

   * Auf der Seite &quot;Exporte&quot;, wie oben beschrieben, unter [Erstellen eines Cloud-Exportkontos beginnen](#begin-creating-a-cloud-export-account)

   * Wann [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Im [!UICONTROL **Kontoeigenschaften**] Abschnitt [!UICONTROL **Konto hinzufügen**] Geben Sie die folgenden Informationen an:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Projekt-ID**] | Ihre Google Cloud-Projekt-ID, die Sie aus Ihrem Google Cloud-Konto kopieren. Siehe [Dokumentation zu Google Cloud zum Abrufen einer Projekt-ID](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

   Die [!UICONTROL **Konto exportieren erstellt**] angezeigt.

   ![Dialogfeld &quot;Konto erstellen&quot;exportieren](assets/export-account-gcp.png)

1. Kopieren Sie den Inhalt der [!UICONTROL **Principal**] in die Zwischenablage ein, und stellen Sie sicher, dass Sie dem Prinzipal Berechtigungen zum Hochladen von Dateien in diesen Behälter in Google Cloud Platform erteilen. <!-- add link to Google Cloud docs on how to do this -->

1. Auswählen [!UICONTROL **OK**].

1. Fahren Sie mit [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md).

### Azure SAS

1. Beginnen Sie mit der Erstellung eines Cloud-Export-Kontos auf eine der folgenden Arten:

   * Auf der Seite &quot;Exporte&quot;, wie oben beschrieben, unter [Erstellen eines Cloud-Exportkontos beginnen](#begin-creating-a-cloud-export-account)

   * Wann [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Im [!UICONTROL **Kontoeigenschaften**] Abschnitt [!UICONTROL **Konto hinzufügen**] Geben Sie die folgenden Informationen an:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Anwendungs-ID**] | Kopieren Sie diese ID aus der von Ihnen erstellten Azure-Anwendung. In Microsoft Azure befinden sich diese Informationen auf der Registerkarte **Übersicht** in Ihrer Anwendung. Weitere Informationen finden Sie in der [Microsoft Azure-Dokumentation zur Registrierung einer Anwendung bei der Microsoft Identity Platform](https://learn.microsoft.com/de-de/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Mandanten-ID**] | Kopieren Sie diese ID aus der von Ihnen erstellten Azure-Anwendung. In Microsoft Azure befinden sich diese Informationen auf der Registerkarte **Übersicht** in Ihrer Anwendung. Weitere Informationen finden Sie in der [Microsoft Azure-Dokumentation zur Registrierung einer Anwendung bei der Microsoft Identity Platform](https://learn.microsoft.com/de-de/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Key Vault-URI**] | <p>Der Pfad zum SAS-Token im Azure Key Vault. Um Azure SAS zu konfigurieren, müssen Sie einen SAS-URI mithilfe des Azure Key Vault als Geheimnis speichern. Weitere Informationen finden Sie in der [Microsoft Azure-Dokumentation zum Einrichten und Abrufen eines Geheimnisses aus Azure Key Vault](https://learn.microsoft.com/de-de/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Nachdem die Key Vault-URI erstellt wurde:<ul><li>Fügen Sie im Key Vault eine Zugriffsrichtlinie hinzu, um der von Ihnen erstellten Azure-Anwendung Berechtigungen zu erteilen.</li><li>Stellen Sie sicher, dass der Anwendungs-ID die `Key Vault Certificate User` integrierte Rolle für den Zugriff auf den URI des Key Vault zugewiesen wurde.</br><p>Weitere Informationen finden Sie unter [Integrierte Azure-Rollen](https://learn.microsoft.com/de-de/azure/role-based-access-control/built-in-roles).</p></li></ul><p>Weitere Informationen finden Sie unter [Microsoft Azure-Dokumentation für die Zuweisung einer Key Vault-Zugriffsrichtlinie](https://learn.microsoft.com/de-de/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **Key Vault-Geheimnisname**] | Der Geheimnisname, den Sie beim Hinzufügen des Geheimnisses zum Azure Key Vault erstellt haben. In Microsoft Azure befinden sich diese Informationen im von Ihnen erstellten Key Vault auf den **Key Vault**-Einstellungsseiten. Weitere Informationen finden Sie unter [Microsoft Azure-Dokumentation zum Einrichten und Abrufen eines Geheimnisses aus Azure Key Vault](https://learn.microsoft.com/de-de/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **Geheimnis des Speicherkontos**] | Kopieren Sie das Geheimnis aus der von Ihnen erstellten Azure-Anwendung. In Microsoft Azure befinden sich diese Informationen auf der Registerkarte **Zertifikate und Geheimnisse** in Ihrer Anwendung. Weitere Informationen finden Sie unter [Microsoft Azure-Dokumentation zur Registrierung einer Anwendung bei der Microsoft-Identitätsplattform](https://learn.microsoft.com/de-de/azure/active-directory/develop/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

   Die [!UICONTROL **Konto exportieren erstellt**] angezeigt.

   ![Dialogfeld &quot;Konto erstellen&quot;exportieren](assets/export-account-azure.png)

1. Wenn Sie dies noch nicht getan haben, stellen Sie sicher, dass Sie dem Behälter in Azure SAS Berechtigungen erteilen. <!-- add link to Google Cloud docs on how to do this -->

1. Auswählen [!UICONTROL **OK**].

1. Fahren Sie mit [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md).

### Azure RBAC

1. Beginnen Sie mit der Erstellung eines Cloud-Export-Kontos auf eine der folgenden Arten:

   * Auf der Seite &quot;Exporte&quot;, wie oben beschrieben, unter [Erstellen eines Cloud-Exportkontos beginnen](#begin-creating-a-cloud-export-account)

   * Wann [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Im [!UICONTROL **Kontoeigenschaften**] Abschnitt [!UICONTROL **Konto hinzufügen**] Geben Sie die folgenden Informationen an:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Anwendungs-ID**] | Kopieren Sie diese ID aus der von Ihnen erstellten Azure-Anwendung. In Microsoft Azure befinden sich diese Informationen auf der Registerkarte **Übersicht** in Ihrer Anwendung. Weitere Informationen finden Sie in der [Microsoft Azure-Dokumentation zur Registrierung einer Anwendung bei der Microsoft Identity Platform](https://learn.microsoft.com/de-de/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Mandanten-ID**] | Kopieren Sie diese ID aus der von Ihnen erstellten Azure-Anwendung. In Microsoft Azure befinden sich diese Informationen auf der Registerkarte **Übersicht** in Ihrer Anwendung. Weitere Informationen finden Sie in der [Microsoft Azure-Dokumentation zur Registrierung einer Anwendung bei der Microsoft Identity Platform](https://learn.microsoft.com/de-de/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Geheimnis des Speicherkontos**] | Kopieren Sie das Geheimnis aus der von Ihnen erstellten Azure-Anwendung. In Microsoft Azure befinden sich diese Informationen auf der Registerkarte **Zertifikate und Geheimnisse** in Ihrer Anwendung. Weitere Informationen finden Sie in der [Microsoft Azure-Dokumentation zur Registrierung einer Anwendung bei der Microsoft Identity Platform](https://learn.microsoft.com/de-de/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

   Die [!UICONTROL **Konto exportieren erstellt**] angezeigt.

   ![Dialogfeld &quot;Konto erstellen&quot;exportieren](assets/export-account-azure.png)

1. Wenn Sie dies noch nicht getan haben, stellen Sie sicher, dass Sie dem Bucket in Azure RBAC Berechtigungen erteilen. <!-- add link to Google Cloud docs on how to do this -->

1. Auswählen [!UICONTROL **OK**].

1. Fahren Sie mit [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md).

### Snowflake

1. Beginnen Sie mit der Erstellung eines Cloud-Export-Kontos auf eine der folgenden Arten:

   * Auf der Seite &quot;Exporte&quot;, wie oben beschrieben, unter [Erstellen eines Cloud-Exportkontos beginnen](#begin-creating-a-cloud-export-account)

   * Wann [Exportieren vollständiger Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Im [!UICONTROL **Kontoeigenschaften**] Abschnitt [!UICONTROL **Konto hinzufügen**] Geben Sie die folgenden Informationen an:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Kontokennung**] | Identifiziert eindeutig ein Snowflake-Konto innerhalb Ihres Unternehmens sowie im gesamten globalen Netzwerk von Snowflake-unterstützten Cloud-Plattformen und Cloud-Regionen. <p>Sie müssen die Kontokennung von Ihrem Snowflake-Konto abrufen und die Informationen hier einfügen.</p><p>Informationen darüber, wo Sie diese Informationen erhalten, finden Sie unter [Seite &quot;Konto-IDs&quot;in der Snowflake-Dokumentation](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> |
   | [!UICONTROL **Benutzer**] | Der Anmeldename des Benutzers, der für die Verbindung verwendet wird. Es wird empfohlen, einen neuen Benutzer zu erstellen, der speziell für das Adobe verwendet wird. Geben Sie hier den Namen an und erstellen Sie dann einen Benutzer im Snowflake mit demselben Namen. Sie können einen Benutzer in Snowflake mithilfe der `CREATE USER` Befehl.  <p>Weitere Informationen finden Sie unter [Befehle für Benutzer, Rolle und Berechtigungen](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |
   | [!UICONTROL **Rolle**] | Die Rolle, die dem Benutzer zugewiesen wird. Es wird empfohlen, eine neue Rolle zu erstellen, die speziell für das Adobe verwendet wird. Geben Sie hier die Rolle an, erstellen Sie dann eine Rolle im Snowflake mit demselben Namen und weisen Sie dem Benutzer die Rolle zu. Sie können eine Rolle beim Snowflake mithilfe der `CREATE ROLE` Befehl. <p>Weitere Informationen finden Sie unter [Befehle für Benutzer, Rolle und Berechtigungen](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus.

   Die [!UICONTROL **Konto exportieren erstellt**] angezeigt.

   ![Dialogfeld &quot;Konto erstellen&quot;exportieren](assets/export-account-snowflake.png)

1. Kopieren Sie den Inhalt der [!UICONTROL **Öffentlicher Schlüssel**] in die Zwischenablage. Der öffentliche Schlüssel wird von Adobe bereitgestellt.

   Verwenden Sie den öffentlichen Schlüssel im Snowflake, um eine Verbindung zu Ihrem Snowflake-Konto herzustellen. Sie müssen den von Ihnen erstellten Benutzer mit diesem öffentlichen Schlüssel verknüpfen.

   Geben Sie beispielsweise unter Snowflake den folgenden Befehl an:

   ```
   CREATE USER <your_adobe_user> RSA_PUBLIC_KEY = '<your_public_key>';
   ```

   Weitere Informationen finden Sie unter [Seite &quot;Schlüsselpaarauthentifizierung und Schlüsselpaar-Rotation&quot;in der Snowflake-Dokumentation](https://docs.snowflake.com/en/user-guide/key-pair-auth).

1. Auswählen [!UICONTROL **OK**].

1. Fahren Sie mit [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md).
