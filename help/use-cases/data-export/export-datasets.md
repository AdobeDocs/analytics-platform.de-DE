---
title: Customer Journey Analytics Exportieren von Datensätzen
description: Beschreibt, wie Sie mit den Datensätzen exportieren Ihre Daten sichern.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: b861f765-b18d-4be2-b4c7-c66186d37d99
source-git-commit: 9fef1fddbb4b51efb9282e3ef13501bd498a4546
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 6%

---

# Exportieren von Datensätzen

In diesem Artikel wird beschrieben, wie der [!DNL Customer Journey Analytics Export datasets] verwendet werden kann, um den folgenden [Anwendungsfall für den Datenexport](overview.md) zu implementieren:

- Datensicherung

## Einführung

Durch den Export von Daten mit [!DNL Experience Platform Export datasets] können Sie Daten aus Ihren Customer Journey Analytics-Datenansichten an ein beliebiges Cloud-Speicher-Ziel exportieren.

![BI-Erweiterung](../assets/export-datasets.svg)

## Weitere Informationen

Sie können Rohdatensätze vom Data Lake in Experience Platform zu Cloud-Speicher-Zielen exportieren. Dieser Export erfolgt in der Experience Platform Destinations-Terminologie, die als Datensatzexport-Ziele bezeichnet wird. Eine Übersicht finden Sie unter [Exportieren von Datensätzen in Cloud-Speicher-Ziele](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) .

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

Wenn Sie das Cloud-Speicher-Ziel ermittelt haben, an das Sie den Datensatz exportieren möchten, wählen Sie [das Ziel ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination) aus. Wenn Sie noch kein Ziel für Ihren bevorzugten Cloud-Speicher konfiguriert haben, müssen Sie [eine neue Zielverbindung erstellen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination).

Im Zuge der Konfiguration eines Ziels können Sie Folgendes definieren:

- Dateityp (JSON oder Parquet),
- ob die resultierende Datei komprimiert werden soll oder nicht und
- ob eine Manifestdatei enthalten sein soll oder nicht.


#### Datensatz auswählen

Wenn Sie das Ziel ausgewählt haben, müssen Sie im nächsten Schritt **[!UICONTROL Datensätze auswählen]** Ihren Datensatz aus der Liste der Datensätze auswählen. Wenn Sie mehrere geplante Abfragen erstellen und möchten, dass die Datensätze an dasselbe Cloud-Speicher-Ziel gesendet werden, können Sie die entsprechenden Datensätze auswählen. Weitere Informationen finden Sie unter [Auswählen Ihrer Datensätze](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) .

#### Planen des Datensatzexports

Schließlich möchten Sie den Export Ihres Datensatzes im Rahmen des Schritts **[!UICONTROL Planung]** planen. In diesem Schritt können Sie den Zeitplan definieren und festlegen, ob der Datensatzexport inkrementell sein soll oder nicht. Weitere Informationen finden Sie unter [Planen des Datensatzexports](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) .


#### Abgeschlossene Schritte

[Überprüfen Sie Ihre Auswahl](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review) und starten Sie den Export Ihres Datensatzes in das Cloud-Speicher-Ziel, wenn dies korrekt ist.

Zunächst müssen Sie [verifizieren](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify), dass der Datenexport erfolgreich war. Beim Exportieren von Datensätzen erstellt Experience Platform eine oder mehrere `.json` - oder `.parquet` -Dateien am Speicherort, der in Ihrem Ziel definiert ist. Erwarten Sie, dass neue Dateien entsprechend dem von Ihnen eingerichteten Exportplan an Ihrem Speicherort abgelegt werden. Experience Platform erstellt eine Ordnerstruktur am Speicherort, den Sie als Teil des ausgewählten Ziels angegeben haben, wo die exportierten Dateien abgelegt werden. Für jeden Exportzeitpunkt wird ein neuer Ordner nach folgendem Muster erstellt: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Der standardmäßige Dateiname wird nach dem Zufallsprinzip generiert, was sicherstellt, dass die Namen von exportierten Dateien eindeutig sind.

### Flussdienst-API

Alternativ können Sie den Export von Datensätzen mithilfe von APIs exportieren und planen. Die erforderlichen Schritte werden in [Exportieren von Datensätzen mithilfe der Flow Service-API](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets) dokumentiert.

#### Erste Schritte

Um Datensätze zu exportieren, stellen Sie sicher, dass Sie über die [erforderlichen Berechtigungen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions) verfügen. Überprüfen Sie außerdem, ob das Ziel, an das Sie Ihren Datensatz senden möchten, den Export von Datensätzen unterstützt. Anschließend müssen Sie [ die Werte für erforderliche und optionale Kopfzeilen ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) erfassen, die Sie in den API-Aufrufen verwenden. Außerdem müssen Sie [die Verbindungsspezifikations- und Flussspezifikations-IDs des Ziels](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) identifizieren, an das Sie Datensätze exportieren möchten.

#### Abrufen zulässiger Datensätze

Sie können [ eine Liste der für den Export infrage kommenden Datensätze abrufen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) und mithilfe der API [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) überprüfen, ob Ihr Datensatz Teil dieser Liste ist.


#### Erstellen der Quellverbindung

Als Nächstes müssen Sie [eine Quellverbindung ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) für den Datensatz mit seiner eindeutigen ID erstellen, die Sie an das Cloud-Speicher-Ziel exportieren möchten. Sie verwenden die [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) -API.

#### Authentifizierung am Ziel (Basisverbindung erstellen)

Sie müssen jetzt [eine Basisverbindung erstellen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection), um die Anmeldeinformationen mithilfe der API [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) für Ihr Cloud-Speicher-Ziel zu authentifizieren und sicher zu speichern.


#### Exportparameter angeben

Als Nächstes müssen Sie [eine zusätzliche Zielverbindung erstellen, in der die Exportparameter](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) für Ihren Datensatz gespeichert werden, indem Sie die API [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) erneut verwenden. Zu diesen Exportparametern gehören Speicherort, Dateiformat, Komprimierung und mehr.

#### Einrichten des Datenflusses

Richten Sie abschließend den Datenfluss ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow) ein, um sicherzustellen, dass Ihr Datensatz mit der API [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) an Ihr Cloud-Speicher-Ziel exportiert wird. [ In diesem Schritt können Sie den Zeitplan für den Export mithilfe des Parameters `scheduleParams` definieren.

#### Validieren des Datenflusses

Um [die erfolgreichen Ausführungen Ihres Datenflusses](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs) zu überprüfen, verwenden Sie die API [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) und geben Sie die Datenfluss-ID als Abfrageparameter an. Diese Datenfluss-ID ist eine Kennung, die beim Einrichten des Datenflusses zurückgegeben wird.

[Überprüfen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) Sie einen erfolgreichen Datenexport. Beim Exportieren von Datensätzen erstellt Experience Platform eine oder mehrere `.json` - oder `.parquet` -Dateien am Speicherort, der in Ihrem Ziel definiert ist. Erwarten Sie, dass neue Dateien entsprechend dem von Ihnen eingerichteten Exportplan an Ihrem Speicherort abgelegt werden. Experience Platform erstellt eine Ordnerstruktur am Speicherort, den Sie als Teil des ausgewählten Ziels angegeben haben, wo die exportierten Dateien abgelegt werden. Für jeden Exportzeitpunkt wird ein neuer Ordner nach folgendem Muster erstellt: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Der standardmäßige Dateiname wird nach dem Zufallsprinzip generiert, was sicherstellt, dass die Namen von exportierten Dateien eindeutig sind.
