---
title: Customer Journey Analytics-Datensätze exportieren
description: Beschreibt die Verwendung der Exportdatensätze zum Sichern Ihrer Daten.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: b861f765-b18d-4be2-b4c7-c66186d37d99
autotag-review: '2026-05-19T09:38:40.111Z'
TQID: 'https://experienceleague.adobe.com/az0B0Gzzu0pbb0TbpiZjW0Y-GysEptIETtg2bBFl-Uw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bf2b169f-d8b2-488a-97b9-f3bc9532e35c
    internal-label: Use cases, Use cases (CJA)
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '1185'
ht-degree: 6%
---
# Exportieren von Datensätzen

In diesem Artikel wird beschrieben, wie die [!DNL Customer Journey Analytics Export datasets] zur Implementierung des folgenden [Anwendungsfalls für den Datenexport“ verwendet ](overview.md) kann:

- Datensicherung

## Einführung

Durch den Export von Daten mit [!DNL Experience Platform Export datasets] können Sie Daten aus Ihren Customer Journey Analytics-Datenansichten in ein beliebiges Cloud-Speicher-Ziel exportieren.

Im Gegensatz zu anderen Exportmethoden gibt es für Datensätze im Export keine feste Zeilenbegrenzung. Die Kapazität Ihres Cloud-Speicher-Ziels begrenzt die Exportgröße. Daher ist dies die bevorzugte Funktion, wenn Sie eine vollständige Rohkopie Ihrer Daten benötigen.

![BI-Erweiterung](../assets/export-datasets.png)

## Weitere Informationen

Verwenden Sie Cloud-Speicherziele, um Rohdatensätze aus dem Data Lake in Experience Platform zu exportieren. Dieser Export wird in der Terminologie von Experience Platform-Zielen als Datensatzexportziele bezeichnet. Eine Übersicht finden Sie unter [Exportieren von Datensätzen zu Cloud-Speicher-Zielen](https://experienceleague.adobe.com/de/docs/experience-platform/destinations/ui/activate/export-datasets).

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

Wenn Sie das Cloud-Speicher-Ziel ermittelt haben, an das Sie den Datensatz exportieren möchten, [ Sie das Ziel ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). Wenn Sie noch kein Ziel für Ihren bevorzugten Cloud-Speicher konfiguriert haben, müssen Sie [eine neue Zielverbindung erstellen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination).

Beim Konfigurieren eines Ziels können Sie Folgendes definieren:

- Dateityp (JSON oder Parquet),
- ob die resultierende Datei komprimiert werden soll oder nicht, und
- Ob eine Manifestdatei eingeschlossen werden soll oder nicht.


#### Datensatz auswählen

Wenn Sie das Ziel ausgewählt haben, müssen **[!UICONTROL im nächsten Schritt]** Auswählen von Datensätzen“ Ihren Datensatz aus der Liste der Datensätze auswählen. Wenn Sie mehrere geplante Abfragen erstellt haben und die Datensätze an dasselbe Cloud-Speicher-Ziel gesendet werden sollen, können Sie die entsprechenden Datensätze auswählen. Weitere [ finden Sie unter ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) auswählen .

#### Planen des Datensatzexports

Planen Sie abschließend den Datensatzexport im Rahmen des Schritts **[!UICONTROL Planung]**. Definieren Sie in diesem Schritt den Zeitplan und ob der Datensatzexport inkrementell ist. Weitere Informationen [ Sie unter „Planen ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) Datensatzexports“.


#### Letzte Schritte

[Überprüfen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review) Sie Ihre Auswahl und beginnen Sie, Ihren Datensatz an das Cloud-Speicher-Ziel zu exportieren.

Zunächst müssen Sie [ erfolgreichen ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) überprüfen. Beim Exportieren von Datensätzen erstellt Experience Platform eine oder mehrere `.json` oder `.parquet` Dateien am Speicherort Ihres Ziels. Neue Dateien werden voraussichtlich entsprechend dem von Ihnen eingerichteten Exportzeitplan an Ihrem Speicherort abgelegt. Experience Platform erstellt eine Ordnerstruktur an dem Speicherort, den Sie als Teil des ausgewählten Ziels angegeben haben, und legt dort die exportierten Dateien ab. Für jeden Exportzeitpunkt wird ein neuer Ordner erstellt, der dem Muster folgt: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Der standardmäßige Dateiname wird nach dem Zufallsprinzip generiert, was sicherstellt, dass die Namen von exportierten Dateien eindeutig sind.

### Flow Service-API

Alternativ können Sie den Export von Datensätzen mithilfe von APIs exportieren und planen. Die hierfür erforderlichen Schritte werden in [Exportieren von Datensätzen mithilfe der Flow Service-API](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets) dokumentiert.

#### Erste Schritte

Um Datensätze zu exportieren, stellen Sie sicher, dass Sie über die [erforderlichen Berechtigungen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions) verfügen. Stellen Sie außerdem sicher, dass das Ziel den Export von Datensätzen unterstützt. Sie können Ihren Datensatz an dieses Ziel senden. Anschließend müssen Sie [ Werte für erforderliche und optionale Kopfzeilen ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers), die Sie in den API-Aufrufen verwenden. Außerdem müssen Sie [die Verbindungsspezifikations- und Flussspezifikations-IDs des Ziels identifizieren](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) für das Sie Datensätze exportieren möchten.

#### Abrufen zulässiger Datensätze

Sie können [eine Liste der geeigneten Datensätze abrufen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) um sie zu exportieren und mithilfe der [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/getDatasets)-API zu überprüfen, ob Ihr Datensatz Teil dieser Liste ist.


#### Quellverbindung erstellen

Als Nächstes müssen Sie [Quellverbindung erstellen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) für den Datensatz unter Verwendung seiner eindeutigen ID, die Sie an das Cloud-Speicher-Ziel exportieren möchten. Sie verwenden die [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/postSourceConnection)-API.

#### Beim Ziel authentifizieren (Basisverbindung erstellen)

Um Anmeldeinformationen für Ihr Cloud-Speicher-Ziel zu authentifizieren und sicher zu speichern[ erstellen Sie eine Basisverbindung ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection) der [`POST /targetConnection`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/postTargetConnection)-API.


#### Exportparameter angeben

Als Nächstes müssen Sie [eine zusätzliche Zielverbindung erstellen, die die Exportparameter speichert](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) für Ihren Datensatz mithilfe der [`POST /targetConnection`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/postTargetConnection)-API. Zu diesen Exportparametern gehören Speicherort, Dateiformat, Komprimierung und mehr.

#### Einrichten eines Datenflusses

Um sicherzustellen, dass Ihr Datensatz in Ihr Cloud-Speicher-Ziel exportiert wird, [richten Sie den Datenfluss ein](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow) indem Sie die [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/postFlow) API verwenden. In diesem Schritt können Sie den Zeitplan für den Export mithilfe des `scheduleParams` definieren.

#### Validieren eines Datenflusses

Um [erfolgreiche Ausführungen Ihres Datenflusses zu überprüfen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs) verwenden Sie die [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/getFlowRuns)-API und geben Sie die Datenfluss-ID als Abfrageparameter an. Diese Datenfluss-ID ist eine Kennung, die beim Einrichten des Datenflusses zurückgegeben wird.

[Überprüfen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) einen erfolgreichen Datenexport. Beim Exportieren von Datensätzen erstellt Experience Platform eine oder mehrere `.json` oder `.parquet` Dateien am Speicherort Ihres Ziels. Neue Dateien werden voraussichtlich entsprechend dem von Ihnen eingerichteten Exportzeitplan an Ihrem Speicherort abgelegt. Experience Platform erstellt eine Ordnerstruktur an dem Speicherort, den Sie als Teil des ausgewählten Ziels angegeben haben, und legt dort die exportierten Dateien ab. Für jeden Exportzeitpunkt wird ein neuer Ordner erstellt, der dem Muster folgt: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Der standardmäßige Dateiname wird nach dem Zufallsprinzip generiert, was sicherstellt, dass die Namen von exportierten Dateien eindeutig sind.
