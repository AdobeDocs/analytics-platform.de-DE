---
title: Aufnehmen und Verwenden von Experience Platform-Zielgruppen
description: Hier erfahren Sie, wie Sie Experience Platform-Zielgruppen in Customer Journey Analytics aufnehmen und für weitere Analysen verwenden.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
role: Admin
source-git-commit: fc62e87c3a69302c4084bf8c0f6c16520e65d60d
workflow-type: tm+mt
source-wordcount: '1570'
ht-degree: 11%

---

# Aufnehmen und Verwenden von Experience Platform-Zielgruppen

In diesem Anwendungsbeispiel wird eine Zwischenlösung zur Aufnahme von Experience Platform-Zielgruppen in Customer Journey Analytics untersucht. Diese Zielgruppen wurden möglicherweise in Experience Platform Segment Builder, Adobe Audience Manager oder anderen Tools erstellt und sind im Echtzeit-Kundenprofil gespeichert. Die Zielgruppen bestehen aus einer Reihe von Profil-IDs sowie den entsprechenden Attributen, Ereignissen und mehr. Sie diese Zielgruppendaten zur weiteren Analyse in Customer Journey Analytics importieren möchten.

## Voraussetzungen

* Zugriff auf [Experience Platform](https://experienceleague.adobe.com/de/docs/experience-platform/access-control/home), insbesondere das Echtzeit-Kundenprofil.
* Zugriff auf das Erstellen und Verwalten von Experience Platform [Schemata](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/home) und [Datensätzen](https://experienceleague.adobe.com/de/docs/experience-platform/catalog/datasets/overview).
* Zugriff auf den [Experience Platform Query Service](https://experienceleague.adobe.com/de/docs/experience-platform/query/home) (und die Möglichkeit, SQL zu schreiben).
* Zugriff auf ein Tool, mit dem einige Datenumwandlungen durchgeführt werden können.
* Zugriff auf Customer Journey Analytics. Sie müssen [Customer Journey Analytics-Produktadministrator sein](/help/technotes/access-control.md) um Customer Journey Analytics-Verbindungen und -Datenansichten erstellen und ändern zu können.
* [Authentifizierung und Zugriff auf Experience Platform-APIs (Catalog Service-API und Segmentierungs-Service-API)](https://experienceleague.adobe.com/de/docs/experience-platform/landing/platform-apis/api-authentication). Sie müssen ein Projekt in der Entwicklerkonsole der Organisation und Sandbox erstellen und sicherstellen, dass Sie über die Informationen verfügen, die zum erfolgreichen Senden von API-Aufrufen erforderlich sind.

## Schritte

Die Zwischenlösung umfasst die folgenden Schritte:

1. [Audiences auswählen (Experience Platform-Benutzeroberfläche)](#select-audiences).
1. [Erstellen eines profilaktivierten Datensatzes (Experience Platform-API)](#create-a-profile-enabled-dataset).
1. [Exportieren von Zielgruppen (Experience Platform-API)](#export-audiences).
1. [Transformieren der Ausgabe (Experience Platform-Benutzeroberfläche und mehr)](#transform-the-output).
1. [Erstellen eines Schemas und eines Datensatzes (Experience Platform-Benutzeroberfläche)](#create-a-schema-and-dataset).
1. [Hinzufügen oder Bearbeiten einer Verbindung (Customer Journey Analytics-Benutzeroberfläche)](#add-or-edit-a-connection).
1. [Konfigurieren einer Datenansicht (Customer Journey Analytics-Benutzeroberfläche)](#configure-a-data-view).
1. [Reporting und Analyse (Customer Journey Analytics-Benutzeroberfläche)](#report-and-analyze).


### Audiences auswählen

Die Lösung beginnt mit der Identifizierung der Zielgruppen, die Sie in Customer Journey Analytics aufnehmen möchten.

+++ Identifizieren von Audiences

In der Experience Platform-Benutzeroberfläche:

1. Wählen Sie **[!UICONTROL Kunde]** > ![SegmentAudience](/help/assets/icons2/SegmentAudience.svg) **[!UICONTROL Audiences]**.
1. Wählen Sie **[!UICONTROL Durchsuchen]** und suchen Sie nach den Zielgruppen, die Sie in Customer Journey Analytics aufnehmen und verwenden möchten. Notieren Sie **[!UICONTROL Zielgruppen-ID]** für jede der Zielgruppen für die spätere Verwendung.

   ![Zielgruppen](assets/audiences.png)

+++

### Erstellen eines profilaktivierten Datensatzes

Sie müssen einen Datensatz basierend auf dem kernbasierten Schema **[!UICONTROL XDM Individual Profile]** erstellen. Sie können dieses auf dem Kern basierende individuelle XDM-Profil nicht als Schema auswählen, wenn Sie einen Datensatz in der Experience Platform-Benutzeroberfläche erstellen. Verwenden Sie stattdessen die [Catalog Service-API, um einen Datensatz ](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/create#create-a-dataset) Grundlage des `_xdm.context.profile__union`-Schemas zu erstellen.

+++ Erstellen einer Datensatzanfrage

#### Anfrage

```shell
curl -X POST \
  'https://platform.adobe.io/data/foundation/catalog/dataSets?requestDataSource=true' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'Content-Type: application/json' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {ORG_ID}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '{
   "name": "{DATASET_NAME}",
   "schemaRef": {
      "id": "_xdm.context.profile__union",
      "contentType": "application/vnd.adobe.xed+json;version=1"
   },
   "fileDescription": {
      "persistet": true,
      "containerFormat": "parquet",
      "format": "parquet"
   }
}'
```

Dabei gilt:

* `DATASET_NAME` ist der Anzeigename des Datensatzes. Zum Beispiel `Segment Export Job Dataset for CJA`.

#### Antwort

```json
["@/dataSets/{DATASET_ID}"]
```

Dabei gilt:

* `DATASET_ID` ist die Datensatzkennung für den erstellten Datensatz.

+++

### Audiences exportieren

Exportieren Sie die ausgewählten Zielgruppen in den soeben erstellten Datensatz. Verwenden Sie die [Segmentierungs-Service-API, um einen Exportvorgang zu erstellen](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/api/export-jobs#create) der die Zielgruppen an den Datensatz sendet.

+++ Vorgangsanfrage exportieren

```shell
curl -X POST https://platform.adobe.io/data/core/ups/export/jobs \
 -H 'Authorization: Bearer {ACCESS_TOKEN}' \
 -H 'Content-Type: application/json' \
 -H 'x-gw-ims-org-id: {ORG_ID}' \
 -H 'x-api-key: {API_KEY}' \
 -H 'x-sandbox-name: {SANDBOX_NAME}' \
 -d '{
    "fields": "{COMMA_SEPARATED_LIST_OF_FULLY_QUALIFIED_FIELD_NAMES}",
    "filter": {
        "segments": [
            {
                "segmentId": "{AUDIENCE_ID_1}",
                "segmentNs": "ups",
                "status": [
                    "realized"
                ],
                "segmentId": "{AUDIENCE_ID_2}",
                "segmentNs": "ups",
                "status": [
                    "realized"
                ],
                "segmentId": "{AUDIENCE_ID_3}",
                "segmentNs": "ups",
                "status": [
                    "realized"
                ]             
             }
        ]
    },
    "destination":{
        "datasetId": "{DATASET_ID}",
        "segmentPerBatch": false
    },
    "schema":{
        "name": "_xdm.context.profile"
    }
}'
```

Dabei wird

* `COMMA_SEPARATED_LIST_OF_FULLY_QUALIFIED_FIELD_NAMES` könnte so etwas wie `_demoemea.identification.core.ecid, _demoemea.identification.core.email, _demoemea.identification.core.phoneNumber, person.gender, person.name.firstName, person.name.lastName` sein. Stellen Sie sicher, dass Sie mindestens die relevanten Felder (z. B. die Personen-ID (E-Mail)) einbeziehen, die Sie in Ihrer Kunden-Journey-Analyse verwenden möchten.
* `AUDIENCE_ID_x` sind die Zielgruppenkennungen der Zielgruppen, die Sie exportieren möchten.
* `DATASET_ID` ist der von Ihnen erstellte Datensatz.


### Antwort

```json
{
  "..."
  "id": "{EXPORT_JOB_ID}",
  "..."
}
```

Dabei wird

* `EXPORT_JOB_ID` ist die Kennung des Exportvorgangs.


+++

Verwenden Sie die [Segmentierungs-Service-API, um den Status des Exportvorgangs zu ](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/api/export-jobs#get).

+++ Abrufen einer bestimmten Exportvorgangsanfrage

#### Anfrage

```shell
curl -X GET https://platform.adobe.io/data/core/ups/export/jobs/{EXPORT_JOB_ID} \
 -H 'Authorization: Bearer {ACCESS_TOKEN}' \
 -H 'x-gw-ims-org-id: {ORG_ID}' \
 -H 'x-api-key: {API_KEY}' \
 -H 'x-sandbox-name: {SANDBOX_NAME}'
```

#### Antwort

```json
{
  "..."
  "id": "{EXPORT_JOB_ID}",
  "..."
  "status": "SUCCEEDED",
  "..."
}
```

+++

Nachdem der Exportvorgang erfolgreich abgeschlossen wurde, überprüfen Sie, ob der Datensatz erfolgreich aufgenommene Batches enthält.

+++ Überprüfen des Aufnahmestatus

In der Experience Platform-Benutzeroberfläche:

1. Wählen Sie **[!UICONTROL Daten-Management]** > ![Daten](/help/assets/icons2/Data.svg) **[!UICONTROL Datensätze]**.
1. Wählen Sie den von Ihnen erstellten Datensatz aus, zum Beispiel: **[!UICONTROL Segmentexportvorgangs-Datensatz für CJA]**.

   ![Datensatzaktivität](assets/dataset-activity.png)

1. Überprüfen Sie die aufgenommenen Batches. Wenn der Datensatz fehlgeschlagene Batches enthält, verwenden Sie **[!UICONTROL Daten-Management]** > ![Monitoring](/help/assets/icons2/Monitoring.svg) **[!UICONTROL Monitoring]**, um den Grund anzuzeigen. Sie haben beispielsweise einen Feldnamen verwendet, der im Schema nicht vorhanden ist.
1. Kopieren Sie den **[!UICONTROL Tabellennamen]** des Datensatzes. Beispiel: **[!UICONTROL segment_export_job_dataset_for_cja]**.  Sie verwenden diesen Namen im nächsten Schritt.

+++


### Transformieren der Ausgabe

Die Daten im Datensatz haben nicht das richtige Format für Customer Journey Analytics. Um die Daten zu transformieren, verwenden Sie den Abfrage-Service von Experience Platform, um die Daten abzurufen.

+++ SQL zum Abrufen exportierter Zielgruppendaten

Verwenden Sie einen PSQL-Client, der eine Verbindung zum Abfrage-Service von Experience Platform herstellt.

In der Experience Platform-Benutzeroberfläche:

1. Wählen Sie **[!UICONTROL Daten-Management]** > ![DataSearch](/help/assets/icons2/DataSearch.svg) **[!UICONTROL Queries]**.
1. Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Credentials]** aus.

Verwenden Sie die Anmeldeinformationen, um Ihren PSQL-Client für die Verbindung mit dem Abfrage-Service von Customer Journey Analytics zu konfigurieren.

#### Abfrage

```sql
SELECT ROW_NUMBER() OVER (ORDER BY key)::text as _id, personID, key as audienceMembershipId
FROM (
   SELECT {IDENTITY_TO_USE_AS_PERSON_ID} AS personID, explode(segmentMembership.ups)
   FROM {DATASET_TABLE_NAME}
)
WHERE value.status = 'realized' AND (key = '{AUDIENCE_ID_1}' OR key = 'AUDIENCE_ID_2' OR key = 'AUDIENCE_ID_3')
```

Dabei gilt:

* `IDENTITY_TO_USE_AS_PERSON_ID` ist eines der Felder, die Sie als Teil des Exportvorgangs definiert haben. Beispiel: `_demoemea.identification.core.email`.
* `AUDIENCE_ID_x` sind die Zielgruppen, die Sie als Teil des Exportvorgangs definiert haben. Sie müssen diese Zielgruppen erneut angeben, da die Spezifikation im Exportvorgang ein Filter auf Zeilenebene ist. Dieser Filter auf Zeilenebene gibt Profile für die angegebenen Segmente mit allen Segmentzugehörigkeiten für jedes der Profile zurück.


#### Ergebnisse

Das Ergebnis der Abfrage im JSON-Format sollte wie folgt aussehen:

```json
[
   {
      "_id": "1",
      "personID": "{PERSON_ID_x}",
      "audienceMembershipId": "{AUDIENCE_ID_x}"
   },
   {
      "_id": "2",
      "personID": "PERSON_ID_y",
      "audienceMembershipId": "{AUDIENCE_ID_x}"
   }

]
```

Dabei gilt:

* `PERSON_ID_x` sind die Kennungswerte für die Kennung, die Sie als Personen-ID verwenden möchten. `john.doe@gmail.com` beispielsweise bei der Verwendung von E-Mails.
* `AUDIENCE_ID_x` sind die Zielgruppenkennungen.

+++

Sie müssen diese JSON-Daten transformieren, um den Mandantennamen der Umgebung hinzuzufügen und einen benutzerfreundlicheren Namen für die Zielgruppe bereitzustellen.

+++ JSON transformieren

Das endgültige JSON sollte wie folgt aussehen:

```json
[
   {
      "_id": "1",
      "personID": "{PERSON_ID_x}",
      "{TENANT_NAME}": {
         "audienceMembershipId": "{AUDIENCE_ID_x}",
         "audienceMembershipName": "{AUDIENCE_FRIENDLY_NAME_x}"
      }
  },
  {
      "_id": "2",
      "personID": "{PERSON_ID_y}",
      "{TENANT_NAME}": {
         "audienceMembershipId": "{AUDIENCE_ID_y}",
         "audienceMembershipName": "{AUDIENCE_FRIENDLY_NAME_y}"
      }
    }
  }

]
```

Dabei gilt:

* `TENANT_NAME` ist der Name des Mandanten. Beispiel: `_demoemea`.
* `PERSON_ID_x` sind die Kennungswerte für die Kennung, die Sie als Personen-ID verwenden möchten. `john.doe@gmail.com` beispielsweise bei der Verwendung von E-Mails.
* `AUDIENCE_ID_x` sind die Zielgruppenkennungen.
* `AUDIENCE_FRIENDLY_NAME_x` sind Anzeigenamen für die Zielgruppen-IDs. Beispiel: `Luma - Blue+ Members`.

Verwenden Sie Ihr bevorzugtes Tool, um die ursprüngliche JSON in dieses Format umzuwandeln.

+++


### Erstellen eines Schemas und Datensatzes

Um das umgewandelte JSON als exportierte Zielgruppendaten in Customer Journey Analytics zu verwenden, müssen Sie ein dediziertes Schema erstellen.

+++ Schema erstellen

So erstellen Sie das Schema:

In der Experience Platform-Benutzeroberfläche:

1. Wählen Sie **[!UICONTROL Daten-Management]** > ![Schema](/help/assets/icons2/Schema.svg) **[!UICONTROL Schemas]** aus.
1. Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Schema erstellen]**. Wählen **[!UICONTROL Standard]** aus dem Dropdown-Menü aus.
1. Wählen Sie **[!UICONTROL Dialogfeld]** Schema erstellen **[!UICONTROL die Option „Manuell]** aus und verwenden Sie **[!UICONTROL Auswählen]**, um fortzufahren.
1. Gehen Sie im **[!UICONTROL Schema erstellen]** im Schritt **[!UICONTROL Klasse auswählen]** folgendermaßen vor:
   1. Wählen Sie **[!UICONTROL Individuelles Profil]** aus.
   1. Klicken Sie auf **[!UICONTROL Weiter]**.
1. Im Assistenten **[!UICONTROL Schema erstellen]** im Schritt **[!UICONTROL Name und Überprüfung]**:
   1. Geben Sie einen **[!UICONTROL Anzeigenamen des Schemas]** ein. Beispiel: `Audience Export for CJA Schema`.
   1. (Optional) Geben Sie eine &quot;**[!UICONTROL &quot;]**.
   1. Wählen Sie **[!UICONTROL Beenden]** aus.
1. Richten Sie Ihr Schema so ein, dass es eine benutzerdefinierte Feldergruppe (mit dem Namen **[!UICONTROL Zielgruppenmitgliedschaft]**) enthält, die zwei Felder mit dem Namen **[!UICONTROL audienceMembershipId]** und **[!UICONTROL audienceMembershipName]** enthält.
1. Stellen Sie sicher **[!UICONTROL dass das Feld]** personID) eine **[!UICONTROL Identität]** **[!UICONTROL Primäre Identität]** ist und **[!UICONTROL email]** als I**[!UICONTROL identity-Namespace]** hat.

   ![Segment für den Export](assets/segment-for-export.png)

1. **[!UICONTROL Übernehmen]** alle Änderungen. Klicken Sie auf **[!UICONTROL Speichern]**, um das Schema zu speichern.

+++

Erstellen Sie einen Datensatz und verwenden Sie diesen Datensatz, um die umgewandelten JSON-Daten aufzunehmen.

+++ Datensatz erstellen und Daten aufnehmen

In der Experience Platform-Benutzeroberfläche:

1. Wählen Sie **[!UICONTROL Daten-Management]** > ![Schema](/help/assets/icons2/Schema.svg) **[!UICONTROL Datensätze]**.
1. Wählen Sie ![Kreis hinzufügen](/help/assets/icons/AddCircle.svg) **[!UICONTROL Datensatz erstellen]**.
1. Wählen Sie **[!UICONTROL Erstellen eines Datensatzes aus einem Schema]** aus.
1. Im Assistenten **[!UICONTROL Datensatz aus Schema erstellen]** im Schritt **[!UICONTROL Schema auswählen]**:
   1. Wählen Sie das soeben erstellte Schema aus. Beispiel: **[!UICONTROL Zielgruppenexport für CJA-Schema]**.
   1. Klicken Sie auf **[!UICONTROL Weiter]**.
1. Im Assistenten **[!UICONTROL Erstellen eines Datensatzes aus]**) im Schritt **[!UICONTROL Konfigurieren]** Datensatzes:
   1. Geben Sie einen **[!UICONTROL Namen]** für den Datensatz ein.
   1. (Optional) Geben Sie eine **[!UICONTROL Beschreibung]** für den Datensatz ein.
   1. Wählen Sie **[!UICONTROL Beenden]** aus.
1. Ziehen Sie unter **[!UICONTROL Datensätze]** > **[!UICONTROL _Name des Datensatzes_]** die umgewandelte JSON-Datendatei und legen Sie die Datei auf **[!UICONTROL Dateien per Drag-and-Drop]**. Diese Aktion startet die Aufnahme der exportierten JSON-Daten in den Datensatz.
1. Überprüfen Sie die aufgenommenen Batches. Wenn der Datensatz fehlgeschlagene Batches enthält, verwenden Sie **[!UICONTROL Daten-Management]** > ![Monitoring](/help/assets/icons2/Monitoring.svg) **[!UICONTROL Monitoring]**, um den Grund anzuzeigen. Sie haben beispielsweise einen Feldnamen in der JSON definiert, der im Schema nicht vorhanden ist.


+++

### Hinzufügen oder Bearbeiten einer Verbindung

Nachdem die umgewandelten JSON-Daten, die die Zielgruppendaten aus Experience Platform enthalten, erfolgreich aufgenommen wurden, können Sie den Datensatz in Customer Journey Analytics zu einer neuen oder vorhandenen Verbindung hinzufügen.

+++ Datensatz zur Verbindung hinzufügen

In der Customer Journey Analytics-Benutzeroberfläche:

1. Wählen **[!UICONTROL Daten-Management]** > **[!UICONTROL Verbindungen]** aus.
1. Erstellen einer neuen Verbindung/Definieren **[!UICONTROL Verbindungseinstellungen]** und **[!UICONTROL Dateneinstellungen]**. Oder wählen Sie eine vorhandene Verbindung aus und verwenden Sie ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Verbindung bearbeiten]**, um die Verbindung zu bearbeiten.
1. Wählen Sie ![DataAdd](/help/assets/icons/DataAdd.svg) **[!UICONTROL Datensätze hinzufügen]** aus.
1. Wählen Sie den von Ihnen erstellten Datensatz aus, in den Sie die umgewandelten JSON-Daten aufgenommen haben.
1. Konfigurieren Sie den Datensatz. Zum Beispiel:

   ![Verbindung - Datensatz mit exportierten Zielgruppendaten](assets/connection-add-dataset.png)

1. **[!UICONTROL Speichern]** der Verbindung.

+++

### Erstellen einer Datenansicht

Konfigurieren Sie eine Datenansicht für die Verbindung, die Sie gerade erstellt oder bearbeitet haben.

+++ Definieren von Zielgruppenkomponenten

1. Wählen **[!UICONTROL Daten-Management]** > **[!UICONTROL Datenansichten]** aus.
1. Bearbeiten Sie eine vorhandene Datenansicht oder erstellen Sie eine neue Datenansicht.
1. Stellen **[!UICONTROL auf der Registerkarte]** Komponenten“ der Datenansicht sicher, **[!UICONTROL Zielgruppenzugehörigkeits-ID]** und **[!UICONTROL Zielgruppenzugehörigkeits-]**) als Dimensionskomponenten hinzugefügt werden.

   ![Datenansichtskomponenten](assets/dataview-components.png)

1. Wählen Sie **[!UICONTROL Speichern und fortfahren]**, um die Datenansicht zu speichern.

+++

### Berichte und Analysen

Verwenden Sie abschließend Analysis Workspace, um Berichte zu Experience Platform-Zielgruppendaten in einem oder mehreren Bedienfeldern zu erstellen, die die Datenansicht mit den Zielgruppenzugehörigkeitskomponenten wie `audienceMembershipId`, `audienceMembershipIdName` und `personID` verwenden.



<!--

## Step 1: Select audiences in Real-time Customer Profile {#audience}

Experience Platform [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html) lets you see a holistic view of each individual customer by combining data from multiple channels, including online, offline, CRM, and third party. 

You likely already have audiences in RTCP that may have come from various sources. Select one or more audiences to ingest into Customer Journey Analytics. For example, WKND Fly Platinum and Gold Fly Club Members.




## Step 2: Create a Profile Union dataset for the export

In order to export the audience to a dataset that you can ingest in Customer Journey Analytics as profiles, create a dataset whose schema is a Profile [Union schema](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html#understanding-union-schemas).

Union schemas are composed of multiple schemas that share the same class and have been enabled for Profile. The union schema enables you to see an amalgamation of all of the fields contained within schemas sharing the same class. Real-time Customer Profile uses the union schema to create a holistic view of each individual customer.

## Step 3: Export an audience to the Profile Union dataset via API call {#export}

Before you can bring an audience into Customer Journey Analytics, you need to export it to an Adobe Experience Platform dataset. This can only be done using the Segmentation API, and specifically the [Export Jobs API Endpoint](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html). 

You can create an export job using the audience ID of your choice, and put the results in the Profile Union Adobe Experience Platform dataset you created in Step 2. Although you can export various attributes/events for the audience, you only need to export the specific profile ID field that matches the person ID field used in the Customer Journey Analytics connection you will be leveraging (see below in Step 5).

## Step 4: Edit the export output 

The results of the export job need to be transformed into a separate Profile dataset in order to be ingested into Customer Journey Analytics.  This transformation can be done with [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html), or another transformation tool of your choice. We only need the Profile ID (that will match the Person ID in Customer Journey Analytics) and one or more audience ID(s) to do the reporting in Customer Journey Analytics.

The standard export job, however, contains more data and so we need to edit this output to remove extraneous data, as well as move some things around.  Also, you need to create a schema/dataset first before you add the transformed data to it.

Here is an example of the export output in the Profile union dataset, **before** any editing:

![Unedited output](../assets/export-unedited.png)

Note the following:

* The audience ID is contained under `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* The status has to be "realized", or "entered", but not "exited".

This is the format of the Profile dataset that you can send into Customer Journey Analytics.

![Edited output](../assets/export-edited.png)

Here are the data elements that need to be present:

* `_aresprodvalidation` string field: Refers to your Organization ID. Yours will be different.
* `personID` string field: This is the standard XDM schema field on Profile datasets to identity the person. Use the Profile ID from the export.
* `audienceMembershipId` string field: The audience ID from the export.  NOTE: This field can be named whatever you want (from your own schema).
* Add a friendly name for the audience (`audienceMembershipIdName`), such as

   ![Friendly audience name](../assets/audience-name.png)
   
* Add other audience metadata if you desire.

## Step 5: Add this Profile dataset to an existing connection in Customer Journey Analytics

You could [create a new connection](/help/connections/create-connection.md), but most customers will want to add the Profile dataset to an existing connection. The audience IDs "enrich" the existing data in Customer Journey Analytics.

## Step 6: Modify existing (or create new) Customer Journey Analytics data view

Add `audienceMembershipId`, `audienceMembershipIdName` and `personID` to the data view.

## Step 7: Report in Workspace

You can now report on `audienceMembershipId`, `audienceMembershipIdName` and `personID` in Workspace.

-->


## Weitere Hinweise

* Sie sollten diesen Prozess regelmäßig durchführen, damit die Zielgruppendaten in Customer Journey Analytics ständig aktualisiert werden.
* Sie können mehrere Zielgruppen in eine Customer Journey Analytics-Verbindung importieren. Dies erhöht zwar die Komplexität des Prozesses, es ist jedoch möglich. Damit dies funktioniert, müssen Sie einige Änderungen am obigen Prozess vornehmen:
   1. Führen Sie diesen Prozess für jede gewünschte Zielgruppe in Ihrer Zielgruppensammlung innerhalb des Echtzeit-Kundenprofis aus.
   1. Customer Journey Analytics unterstützt Arrays/Objekt-Arrays in Profildatensätzen. Es [ sich, für die ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/complex-data/object-arrays.html?lang=de) oder `audienceMembershipId` ein `audienceMembershipIdName`Array von Objekten“ zu verwenden.
   1. Erstellen Sie in Ihrer Datenansicht eine neue Dimension mithilfe der Teilzeichenfolgenumwandlung des `audienceMembershipId`-Felds, um die Zeichenfolge mit kommagetrennten Werten in ein Array zu konvertieren. HINWEIS: Derzeit besteht für das Array eine Beschränkung von 10 Werten.
   1. Jetzt können Sie in Customer Journey Analytics Workspace Berichte zu diesem neuen `audienceMembershipIds` erstellen.
