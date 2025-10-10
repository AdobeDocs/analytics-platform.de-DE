---
title: Customer Journey Analytics-Datensätze exportieren
description: Beschreibt die Verwendung der Exportdatensätze zum Sichern Ihrer Daten.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: b861f765-b18d-4be2-b4c7-c66186d37d99
source-git-commit: 9fef1fddbb4b51efb9282e3ef13501bd498a4546
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 7%

---

# Exportieren von Datensätzen

In diesem Artikel wird beschrieben, wie die [!DNL Customer Journey Analytics Export datasets] zur Implementierung des folgenden [Anwendungsfalls für den Datenexport“ verwendet &#x200B;](overview.md) kann:

- Datensicherung

## Einführung

Durch den Export von Daten mit [!DNL Experience Platform Export datasets] können Sie Daten aus Ihren Customer Journey Analytics-Datenansichten in ein beliebiges Cloud-Speicher-Ziel exportieren.

![BI-Erweiterung](../assets/export-datasets.svg)

## Weitere Informationen

Sie können Rohdatensätze aus dem Data Lake in Experience Platform in Cloud-Speicher-Ziele exportieren. Dieser Export wird in der Terminologie für Experience Platform-Ziele als Datensatzexportziele bezeichnet. Siehe [Exportieren von Datensätzen zu Cloud-Speicher](https://experienceleague.adobe.com/de/docs/experience-platform/destinations/ui/activate/export-datasets) für eine Übersicht.

Die folgenden Cloud-Speicherziele werden unterstützt:

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Data Landing Zone](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google Cloud Storage](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3#changelog)
- [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob#changelog)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp#changelog)


### Experience Platform-Benutzeroberfläche

Sie können den Export Ihrer Datensätze über die Experience Platform-Benutzeroberfläche exportieren und planen. In diesem Abschnitt werden die beteiligten Schritte beschrieben.

#### Ziel auswählen

Wenn Sie das Cloud-Speicher-Ziel bestimmt haben, an das Sie den Datensatz exportieren möchten, [&#x200B; Sie das Ziel &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). Wenn Sie noch kein Ziel für Ihren bevorzugten Cloud-Speicher konfiguriert haben, müssen Sie [eine neue Zielverbindung erstellen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination).

Beim Konfigurieren eines Ziels können Sie Folgendes definieren:

- Dateityp (JSON oder Parquet),
- ob die resultierende Datei komprimiert werden soll oder nicht, und
- Ob eine Manifestdatei eingeschlossen werden soll oder nicht.


#### Datensatz auswählen

Wenn Sie das Ziel ausgewählt haben, müssen **[!UICONTROL im nächsten Schritt]** Auswählen von Datensätzen“ Ihren Datensatz aus der Liste der Datensätze auswählen. Wenn Sie mehrere geplante Abfragen erstellt haben und die Datensätze an dasselbe Cloud-Speicher-Ziel senden sollen, können Sie die entsprechenden Datensätze auswählen. Weitere [&#x200B; finden Sie unter &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) auswählen .

#### Planen des Datensatzexports

Schließlich möchten Sie den Datensatzexport als Teil des Schritts „Planung **&#x200B;**. In diesem Schritt können Sie den Zeitplan definieren und festlegen, ob der Datensatzexport inkrementell erfolgen soll oder nicht. Weitere Informationen [&#x200B; Sie unter „Planen &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) Datensatzexports“.


#### Letzte Schritte

[Überprüfen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review) Sie Ihre Auswahl und beginnen Sie, Ihren Datensatz an das Cloud-Speicher-Ziel zu exportieren.

Zunächst müssen Sie [&#x200B; erfolgreichen &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) überprüfen. Beim Exportieren von Datensätzen erstellt Experience Platform eine oder mehrere `.json` oder `.parquet` Dateien an dem in Ihrem Ziel definierten Speicherort. Neue Dateien werden voraussichtlich entsprechend dem von Ihnen eingerichteten Exportzeitplan an Ihrem Speicherort abgelegt. Experience Platform erstellt eine Ordnerstruktur an dem Speicherort, den Sie als Teil des ausgewählten Ziels angegeben haben, und legt dort die exportierten Dateien ab. Für jeden Exportzeitpunkt wird ein neuer Ordner erstellt, der dem Muster folgt: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Der standardmäßige Dateiname wird nach dem Zufallsprinzip generiert, was sicherstellt, dass die Namen von exportierten Dateien eindeutig sind.

### Flow Service-API

Alternativ können Sie den Export von Datensätzen mithilfe von APIs exportieren und planen. Die hierfür erforderlichen Schritte werden in [Exportieren von Datensätzen mithilfe der Flow Service-API](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets) dokumentiert.

#### Erste Schritte

Um Datensätze zu exportieren, stellen Sie sicher, dass Sie über die [erforderlichen Berechtigungen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions) verfügen. Überprüfen Sie außerdem, ob das Ziel, an das Sie Ihren Datensatz senden möchten, das Exportieren von Datensätzen unterstützt. Anschließend müssen Sie [&#x200B; Werte für erforderliche und optionale Kopfzeilen &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers), die Sie in den API-Aufrufen verwenden. Außerdem müssen Sie [die Verbindungsspezifikations- und Flussspezifikations-IDs des Ziels identifizieren](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) für das Sie Datensätze exportieren möchten.

#### Abrufen zulässiger Datensätze

Sie können [eine Liste der geeigneten Datensätze abrufen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) um sie zu exportieren und mithilfe der [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets)-API zu überprüfen, ob Ihr Datensatz Teil dieser Liste ist.


#### Quellverbindung erstellen

Als Nächstes müssen Sie [Quellverbindung erstellen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) für den Datensatz unter Verwendung seiner eindeutigen ID, die Sie an das Cloud-Speicher-Ziel exportieren möchten. Sie verwenden die [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection)-API.

#### Beim Ziel authentifizieren (Basisverbindung erstellen)

Sie müssen jetzt [eine Basisverbindung erstellen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection) um die Anmeldeinformationen mithilfe der [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection)-API zu authentifizieren und sicher in Ihrem Cloud-Speicher-Ziel zu speichern.


#### Exportparameter angeben

Als Nächstes müssen Sie [eine zusätzliche Zielverbindung erstellen, die die Exportparameter speichert](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) für Ihren Datensatz, indem Sie erneut die [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection)-API verwenden. Zu diesen Exportparametern gehören Speicherort, Dateiformat, Komprimierung und mehr.

#### Einrichten eines Datenflusses

Schließlich richten Sie [den Datenfluss) ein](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow) um sicherzustellen, dass Ihr Datensatz mithilfe der [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow)-API in Ihr Cloud-Speicher-Ziel exportiert wird. In diesem Schritt können Sie den Zeitplan für den Export mithilfe des `scheduleParams` definieren.

#### Validieren eines Datenflusses

Um [erfolgreiche Ausführungen Ihres Datenflusses zu überprüfen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs) verwenden Sie die [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns)-API und geben Sie die Datenfluss-ID als Abfrageparameter an. Diese Datenfluss-ID ist eine Kennung, die beim Einrichten des Datenflusses zurückgegeben wird.

[Überprüfen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) einen erfolgreichen Datenexport. Beim Exportieren von Datensätzen erstellt Experience Platform eine oder mehrere `.json` oder `.parquet` Dateien an dem in Ihrem Ziel definierten Speicherort. Neue Dateien werden voraussichtlich entsprechend dem von Ihnen eingerichteten Exportzeitplan an Ihrem Speicherort abgelegt. Experience Platform erstellt eine Ordnerstruktur an dem Speicherort, den Sie als Teil des ausgewählten Ziels angegeben haben, und legt dort die exportierten Dateien ab. Für jeden Exportzeitpunkt wird ein neuer Ordner erstellt, der dem Muster folgt: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Der standardmäßige Dateiname wird nach dem Zufallsprinzip generiert, was sicherstellt, dass die Namen von exportierten Dateien eindeutig sind.
