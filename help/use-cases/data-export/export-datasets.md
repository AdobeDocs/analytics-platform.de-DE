---
title: Customer Journey Analytics Exportieren von Datensätzen
description: Beschreibt, wie Sie mit den Datensätzen exportieren Ihre Daten sichern.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 19018e31bb2a46e88a27643fe10c388b40de243e
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 6%

---


# Exportieren von Datensätzen

In diesem Artikel wird erläutert, wie die [!DNL Customer Journey Analytics Export datasets] kann zur Implementierung der folgenden [Anwendungsfall für den Datenexport](overview.md):

- Datensicherung

## Einführung

Exportieren von Daten mithilfe von [!DNL Experience Platform Export datasets] ermöglicht Ihnen den Export von Daten aus Ihren Customer Journey Analytics-Datenansichten in ein beliebiges Cloud-Speicher-Ziel.

![BI-Erweiterung](../assets/export-datasets.svg)

## Weitere Informationen

Sie können Rohdatensätze vom Data Lake in Experience Platform zu Cloud-Speicher-Zielen exportieren. Dieser Export erfolgt in der Experience Platform Destinations-Terminologie, die als Datensatzexport-Ziele bezeichnet wird. Siehe [Exportieren von Datensätzen in Cloud-Speicher-Ziele](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) für einen Überblick.

Die folgenden Cloud-Speicher-Ziele werden unterstützt:

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Data Landing Zone](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google Cloud Storage](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3#changelog)
- [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob#changelog)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp#changelog)


### Experience Platform-Benutzeroberfläche

Sie können den Export Ihrer Datensätze über die Experience Platform-Benutzeroberfläche planen. In diesem Abschnitt werden die erforderlichen Schritte beschrieben.

#### Ziel auswählen

Wenn Sie das Cloud-Speicher-Ziel an den Speicherort festgelegt haben, an den Sie den Datensatz exportieren möchten, [Ziel auswählen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). Wenn Sie noch kein Ziel für Ihren bevorzugten Cloud-Speicher konfiguriert haben, müssen Sie [Erstellen einer neuen Zielverbindung](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination).

Im Zuge der Konfiguration eines Ziels können Sie Folgendes definieren:

- Dateityp (JSON oder Parquet),
- ob die resultierende Datei komprimiert werden soll oder nicht und
- ob eine Manifestdatei enthalten sein soll oder nicht.


#### Datensatz auswählen

Wenn Sie das Ziel ausgewählt haben, klicken Sie im nächsten **[!UICONTROL Auswählen von Datensätzen]** Schritt müssen Sie Ihren Datensatz aus der Liste der Datensätze auswählen. Wenn Sie mehrere geplante Abfragen erstellen und möchten, dass die Datensätze an dasselbe Cloud-Speicher-Ziel gesendet werden, können Sie die entsprechenden Datensätze auswählen. Siehe [Auswählen Ihrer Datensätze](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) für weitere Informationen.

#### Planen des Datensatzexports

Schließlich möchten Sie Ihren Datensatzexport als Teil der **[!UICONTROL Planung]** Schritt. In diesem Schritt können Sie den Zeitplan definieren und festlegen, ob der Datensatzexport inkrementell sein soll oder nicht. Siehe [Datensatz-Export planen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) für weitere Informationen.


#### Abgeschlossene Schritte

[Überprüfen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review) Ihre Auswahl fest und starten Sie den Export Ihres Datensatzes in das Cloud-Speicher-Ziel, falls zutreffend.

Zunächst müssen Sie [verify](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) einen erfolgreichen Datenexport. Beim Exportieren von Datensätzen erstellt Experience Platform eine oder mehrere `.json` oder `.parquet` -Dateien am Speicherort, der in Ihrem Ziel definiert ist. Erwarten Sie, dass neue Dateien entsprechend dem von Ihnen eingerichteten Exportplan an Ihrem Speicherort abgelegt werden. Experience Platform erstellt eine Ordnerstruktur am Speicherort, den Sie als Teil des ausgewählten Ziels angegeben haben, wo die exportierten Dateien abgelegt werden. Für jeden Exportzeitpunkt wird ein neuer Ordner nach folgendem Muster erstellt: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Der standardmäßige Dateiname wird nach dem Zufallsprinzip generiert, was sicherstellt, dass die Namen von exportierten Dateien eindeutig sind.

### Flussdienst-API

Alternativ können Sie den Export von Datensätzen mithilfe von APIs exportieren und planen. Die erforderlichen Schritte werden im Abschnitt [Exportieren von Datensätzen mithilfe der Flow Service-API](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets).

#### Erste Schritte

Um Datensätze zu exportieren, stellen Sie sicher, dass Sie über die [erforderliche Berechtigungen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions). Überprüfen Sie außerdem, ob das Ziel, an das Sie Ihren Datensatz senden möchten, den Export von Datensätzen unterstützt. Sie müssen [Werte für erforderliche und optionale Kopfzeilen erfassen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) , die Sie in den API-Aufrufen verwenden. Sie müssen auch [Identifizieren der Verbindungsspezifikations- und Flussspezifikations-IDs des Ziels](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) Sie beabsichtigen, Datensätze in zu exportieren.

#### Abrufen zulässiger Datensätze

Sie können [Liste der zulässigen Datensätze abrufen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) zum Exportieren und überprüfen Sie anhand der [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API.


#### Erstellen der Quellverbindung

Als Nächstes müssen Sie [Quellverbindung erstellen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) für den Datensatz, den Sie mithilfe seiner eindeutigen ID an das Cloud-Speicher-Ziel exportieren möchten. Sie verwenden die [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API.

#### Authentifizierung am Ziel (Basisverbindung erstellen)

Sie müssen jetzt [Basisverbindung erstellen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection) , um die Anmeldeinformationen zu authentifizieren und sicher in Ihrem Cloud-Speicher-Ziel zu speichern, indem Sie die [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API.


#### Exportparameter angeben

Als Nächstes müssen Sie [eine zusätzliche Zielverbindung erstellen, in der die Exportparameter gespeichert werden](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) für Ihren Datensatz verwenden, indem Sie erneut die Variable [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API. Zu diesen Exportparametern gehören Speicherort, Dateiformat, Komprimierung und mehr.

#### Einrichten des Datenflusses

Schließlich haben Sie [Datenfluss einrichten](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow) , um sicherzustellen, dass Ihr Datensatz mit dem [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API. In diesem Schritt können Sie den Zeitplan für den Export mithilfe der Variablen `scheduleParams` -Parameter.

#### Validieren des Datenflusses

nach [Überprüfen erfolgreicher Ausführungen Ihres Datenflusses](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs), verwenden Sie die [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API, die die Datenfluss-ID als Abfrageparameter angibt. Diese Datenfluss-ID ist eine Kennung, die beim Einrichten des Datenflusses zurückgegeben wird.

[Überprüfen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) einen erfolgreichen Datenexport. Beim Exportieren von Datensätzen erstellt Experience Platform eine oder mehrere `.json` oder `.parquet` -Dateien am Speicherort, der in Ihrem Ziel definiert ist. Erwarten Sie, dass neue Dateien entsprechend dem von Ihnen eingerichteten Exportplan an Ihrem Speicherort abgelegt werden. Experience Platform erstellt eine Ordnerstruktur am Speicherort, den Sie als Teil des ausgewählten Ziels angegeben haben, wo die exportierten Dateien abgelegt werden. Für jeden Exportzeitpunkt wird ein neuer Ordner nach folgendem Muster erstellt: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Der standardmäßige Dateiname wird nach dem Zufallsprinzip generiert, was sicherstellt, dass die Namen von exportierten Dateien eindeutig sind.
