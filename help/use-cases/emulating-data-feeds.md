---
title: Datenfeed-Funktion emulieren
description: Erfahren Sie, wie Sie Adobe Analytics-Daten-Feeds mit Daten im Experience Platform emulieren können.
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: a4d9272b1e813a34f11e4b42c3369129b57c6ef0
workflow-type: tm+mt
source-wordcount: '2107'
ht-degree: 4%

---

# Datenfeed-Funktion emulieren

Adobe Analytics-Daten-Feeds sind eine leistungsstarke Methode, Rohdaten aus Adobe Analytics abzurufen. In diesem Anwendungsbeispiel wird beschrieben, wie Sie ähnliche Rohdaten aus der Experience Platform abrufen, sie auf anderen Plattformen außerhalb von Adobe verwenden und nach Ermessen Ihres Unternehmens verwenden können.

## Voraussetzungen

Stellen Sie sicher, dass Sie alle folgenden Anforderungen erfüllen, bevor Sie die in diesem Anwendungsbeispiel beschriebene Funktion verwenden:

* Eine funktionierende Implementierung, die Online- und Offline-Daten an Experience Platform Data Lake sendet.
* Zugriff auf Query Service, der als Teil von plattformbasierten Anwendungen oder dem Data Distiller-Add-on gepackt wird. Siehe [Query Service-Verpackung](https://experienceleague.adobe.com/docs/experience-platform/query/packaging.html?lang=en) für weitere Informationen.
* Zugriff auf die Funktion zum Exportieren von Datensätzen , die für Kunden verfügbar ist, die das Real-Time CDP Prime- oder Ultimate-Paket, Adobe Journey Optimizer oder Customer Journey Analytics erworben haben. Siehe [Exportieren von Datensätzen in Cloud-Speicher-Ziele](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=de) für weitere Informationen.
* Ein oder mehrere Ziele (z. B. Amazon S3, Google Cloud-Speicher), die für den Export der Rohdaten Ihres Daten-Feeds konfiguriert sind.

## Einführung

Die Emulation eines Adobe Analytics-Daten-Feeds umfasst:

* Definieren einer **Geplante Abfrage** , das die Daten für Ihren Daten-Feed als Ausgabedatensatz generiert, indem **Query Service**.
* Definieren einer **geplanter Datensatzexport** , der den Ausgabedatensatz in ein Cloud-Speicher-Ziel exportiert, mithilfe von **Datensatzexport**.


![Daten-Feed](assets/data-feed.svg)


## Abfrage-Service

Mit dem Experience Platform Query Service können Sie einen beliebigen Datensatz in Experience Platform Data Lake abfragen und verbinden, als wäre es eine Datenbanktabelle. Anschließend können Sie die Ergebnisse als neuen Datensatz für die weitere Verwendung in Berichten oder für den Export erfassen.

Sie verwenden den Query Service [Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/query/ui/overview.html?lang=en), a [Client, der über das PostgresSQL-Protokoll verbunden ist](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=de)oder [RESTful-APIs](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) , um Abfragen zu erstellen und zu planen, die die Daten für Ihren Daten-Feed erfassen.

### Abfrage erstellen

Sie können alle Funktionen von Standard-ANSI SQL für SELECT-Anweisungen und andere eingeschränkte Befehle verwenden, um die Abfragen zu erstellen und auszuführen, die die Daten für Ihren Daten-Feed generieren. Siehe [SQL-Syntax](https://experienceleague.adobe.com/docs/experience-platform/query/sql/syntax.html?lang=en) für weitere Informationen. Neben dieser SQL-Syntax unterstützt Adobe Folgendes:

* vorkonfiguriert [Adobe-definierte Funktionen (ADF)](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) , mit denen häufig geschäftsbezogene Aufgaben für Ereignisdaten durchgeführt werden können, die im Experience Platform Data Lake gespeichert sind, einschließlich Funktionen für [Sessionization](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing.html?lang=de) und [Attribution](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=de),
* mehrere integrierte [Spark SQL-Funktionen](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en),
* [metadata PostgreSQL-Befehle](https://experienceleague.adobe.com/docs/experience-platform/query/sql/metadata.html?lang=en),
* [vorbereitete Anweisungen](https://experienceleague.adobe.com/docs/experience-platform/query/sql/prepared-statements.html?lang=en).


#### Beispiele

Nachfolgend finden Sie einige Beispiele für Abfragen, die Daten für Ihre Daten-Feeds erfassen. Diese Beispiele verwenden `demo_system_event_dataset_for_website_global_v1_1` als Beispiel-Erlebnisereignis-Datensatz mit Daten, die von Kunden erfasst wurden, die mit der Website interagieren.

+++ Die fünf beliebtesten Produkte

*Welches sind die fünf am häufigsten angezeigten Produkte auf der Website?*

```sql
select productListItems.name, count(*)
from   demo_system_event_dataset_for_website_global_v1_1
where  eventType = 'commerce.productViews'
group  by productListItems.name
order  by 2 desc
limit 5;
```

+++

+++Produktinteraktionstrichter

*Welche Produktinteraktionen gibt es auf der gesamten Website?*

```sql
select eventType, count(*)
from   demo_system_event_dataset_for_website_global_v1_1
where  eventType is not null
and    eventType <> ''
group  by eventType;
```

+++

+++ Was machen Personen?

*Was machen Personen auf der Site, bevor sie als dritte Seite in einer Sitzung die Seite &quot;Abbrechen-Dienst&quot;aufrufen?*

Diese Abfrage verwendet die Adobe Definierte Funktionen `SESS_TIMEOUT` und `NEXT`.

* Der `SESS_TIMEOUT()` reproduziert die in Adobe Analytics gefundenen Besuchergruppen. Er führt eine ähnliche zeitbasierte Gruppierung durch, jedoch mit anpassbaren Parametern.
* `NEXT()` und `PREVIOUS()` hilft Ihnen zu verstehen, wie Kunden durch Ihre Site navigieren.

```sql
SELECT
  webPage,
  webPage_2,
  webPage_3,
  webPage_4,
  count(*) journeys
FROM
  (
      SELECT
        webPage,
        NEXT(webPage, 1, true)
          OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_2,
        NEXT(webPage, 2, true)
          OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_3,
        NEXT(webPage, 3, true)
           OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_4,
        session.depth AS SessionPageDepth
      FROM (
            select a._sampleorg.identification.core.ecid as ecid,
                   a.timestamp,
                   web.webPageDetails.name as webPage,
                    SESS_TIMEOUT(timestamp, 60 * 30)
                       OVER (PARTITION BY a._sampleorg.identification.core.ecid
                             ORDER BY timestamp
                             ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW)
                  AS session
            from   demo_system_event_dataset_for_website_global_v1_1 a
            where  a._sampleorg.identification.core.ecid in (
                select b._sampleorg.identification.core.ecid
                from   demo_system_event_dataset_for_website_global_v1_1 b
                where  b.web.webPageDetails.name = 'Cancel Service'
            )
        )
)
WHERE SessionPageDepth=1
and   webpage_3 = 'Cancel Service'
GROUP BY webPage, webPage_2, webPage_3, webPage_4
ORDER BY journeys DESC
LIMIT 10;
```

+++

+++Wie viel Zeit

*Wie viel Zeit haben Sie, bevor ein Besucher das Callcenter aufruft, nachdem Sie die Seite &quot;Dienst abbrechen&quot;besucht haben?*

Für diese Art von Abfrage verwenden Sie die `TIME_BETWEEN_NEXT_MATCH()` Adobe definierte Funktion. Die Zeit zwischen vorherigen oder nächsten Übereinstimmungsfunktionen bietet eine neue Dimension, die die seit einem bestimmten Vorfall verstrichene Zeit misst.

```sql
select * from (
       select _sampleorg.identification.core.ecid as ecid,
              web.webPageDetails.name as webPage,
              TIME_BETWEEN_NEXT_MATCH(timestamp, web.webPageDetails.name='Call Start', 'seconds')
              OVER(PARTITION BY _sampleorg.identification.core.ecid
                  ORDER BY timestamp
                  ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING)
              AS contact_callcenter_after_seconds
       from   demo_system_event_dataset_for_website_global_v1_1
       where  web.webPageDetails.name in ('Cancel Service', 'Call Start')
) r
where r.webPage = 'Cancel Service'
limit 15;
```

+++

+++Was ist das Ergebnis?

*Wie lautet das Ergebnis eines Anrufs durch die Kunden?*

Für diese Abfrage wird die Variable `demo_system_event_dataset_for_website_global_v1_1` Datensatz wird mit einem Beispiel verknüpft `demo_system_event_dataset_for_call_center_global_v1_1` Datensatz mit Callcenter-Interaktionen.

```sql
select distinct r.*,
       c._sampleorg.interactionDetails.core.callCenterAgent.callFeeling,
       c._sampleorg.interactionDetails.core.callCenterAgent.callTopic,
       c._sampleorg.interactionDetails.core.callCenterAgent.callContractCancelled
from (
       select _sampleorg.identification.core.ecid ecid,
              web.webPageDetails.name as webPage,
              TIME_BETWEEN_NEXT_MATCH(timestamp, web.webPageDetails.name='Call Start', 'seconds')
              OVER(PARTITION BY _sampleorg.identification.core.ecid
                  ORDER BY timestamp
                  ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING)
              AS contact_callcenter_after_seconds
       from   demo_system_event_dataset_for_website_global_v1_1
       where  web.webPageDetails.name in ('Cancel Service', 'Call Start')
) r
, demo_system_event_dataset_for_call_center_global_v1_1 c
where r.ecid = c._sampleorg.identification.core.ecid
and r.webPage = 'Cancel Service'
and c._sampleorg.interactionDetails.core.callCenterAgent.callContractCancelled IN (true,false)
and c._sampleorg.interactionDetails.core.callCenterAgent.callTopic IN ('contract', 'invoice','complaint','wifi')
limit 15;
```

+++

+++Marketingkanal-Interaktion (Adobe Analytics-Daten)

*Was ist die Interaktion über Marketingkanäle für den auf Italien fokussierten Web-Traffic?*

In diesem Beispiel wird der Datensatz verwendet, der automatisch vom Adobe Analytics-Quell-Connector erstellt wurde. Beispiel: `demo_data_sample_org_midvalues`.

```sql
select 
    channel.typeAtSource, count(*) 
from 
    demo_data_sample_org_midvalues 
where 
    (channel.typeAtSource IS NOT NULL
and
    web.webPageDetails.URL LIKE '%/it/it/%')
group by 
    channel.typeAtSource
order by 2 desc;
```

+++

Weitere (erweiterte) Beispielabfragen finden Sie unter [abgebrochener Browser](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/abandoned-browse.html?lang=en), [Attributionsanalyse](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/attribution-analysis.html?lang=en), [Bot-Filterung](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/bot-filtering.html?lang=en)und andere Beispiele im Query Service-Handbuch.


#### Identitäten

Unter Experience Platform sind verschiedene Identitäten verfügbar. Stellen Sie sicher, dass Sie Identitäten richtig abfragen. In den obigen Beispielen wird ECID als Teil eines Kernobjekts definiert, das selbst Teil eines Identifizierungsobjekts ist. Beide werden dem Schema mit einer Experience Event Core-Feldergruppe hinzugefügt (z. B.: `_sampleorg.identification.core.ecid`). Die ECIDs können in Ihren Schemas unterschiedlich organisiert sein.

Alternativ können Sie `identityMap` , um Identitäten abzufragen. Dieses Objekt ist vom Typ `Map` und verwendet eine [verschachtelte Datenstruktur](#nested-data-structure).

Für Daten, die mit dem Adobe Analytics-Quell-Connector erfasst werden, stehen möglicherweise mehrere Identitäten zur Verfügung. Die primäre Kennung hängt davon ab, ob eine ECID oder eine AAID vorhanden ist. Siehe [Primäre IDs in Adobe Analytics-Daten](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en#how-the-analytics-source-treats-identities) und [AAID, ECID, AACUSTOMID und der Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=de) für weitere Informationen

#### Daten-Feed-Spalten

Welche Felder (Spalten) Sie in Ihrer Abfrage verwenden können, hängt von der Schemadefinition ab, auf der Ihre Datensätze basieren. Vergewissern Sie sich, dass Sie das dem Datensatz zugrunde liegende Schema verstehen.

Beispiel: In einigen [Beispielabfragen](#examples) Sie haben nach *Seitenname*.

* In der Benutzeroberfläche des Adobe Analytics-Daten-Feeds wählen Sie **[!UICONTROL pagename]** als die Spalte, die zu Ihrer Datenfeed-Definition hinzugefügt werden soll.
* In Query Service fügen Sie `web.webPageDetails.name` aus dem `demo_system_event_dataset_for_website_global_v1_1` Datensatz (basierend auf der **Demosystem - Ereignisschema für Website (Global v1.1)** Erlebnisereignisschema) in Ihrer Abfrage. Siehe [Feldgruppe &quot;Webdetails-Schema&quot;](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/web-details.html?lang=en) für weitere Informationen.

Informationen zur Zuordnung zwischen früheren Adobe Analytics-Datenspalten und XDM-Feldern in Ihrem Erlebnisereignis-Datensatz und dem zugrunde liegenden Schema finden Sie unter [Zuordnung von Analytics-Feldern](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=de) und [Feldergruppe Adobe Analytics ExperienceEvent Full Extension](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) für weitere Informationen.

Darüber hinaus können die automatisch vom Experience Platform Web SDK erfassten Informationen (vorkonfiguriert) auch zur Identifizierung von Spalten für Ihre Abfrage relevant sein. Siehe [Automatisch erfasste Informationen](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html?lang=en) für weitere Informationen.


#### Suchen

Zum Nachschlagen von Daten aus anderen Datensätzen verwenden Sie die SQL-Standardfunktionalität (WHERE-Klausel, INNER JOIN, OUTER JOIN und andere). Siehe [Was ist das Ergebnis?](#examples) in den Beispielen.

#### Berechnungen

Um Berechnungen für Felder (Spalten) durchzuführen, verwenden Sie einfach die SQL-Standardfunktionen (z. B. `COUNT(*)` im [Produktinteraktionstrichter](#examples) -Abfrage in den Beispielen) oder der [mathematische und statistische Operatoren und Funktionen](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#math) Teil von Spark SQL.

#### Verschachtelte Datenstruktur

Die Schemas, auf denen die Datensätze basieren, enthalten häufig komplexe Datentypen, einschließlich verschachtelter Datenstrukturen. Zuvor erwähnt `identityMap` ist ein Beispiel für eine verschachtelte Datenstruktur. Nachfolgend finden Sie ein Beispiel für `identityMap` Daten.

```json
{
   "identityMap":{
      "FPID":[
         {
            "id":"55613368189701342632255821452918751312",
            "authenticatedState":"ambiguous"
         }
      ],
      "CRM":[
         {
            "id":"2394509340-30453470347",
            "authenticatedState":"authenticated"
         }
      ]
   }
}
```

Sie können die [`explode()` oder anderen Arrays-Funktionen](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#arrays) von Spark SQL, um zu den Daten in einer verschachtelten Datenstruktur zu gelangen.

Zum Beispiel:

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Alternativ können Sie einzelne Elemente mit Punktnotation referenzieren. Zum Beispiel:

```sql
select identityMap,ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Weitere Informationen finden Sie unter [Arbeiten mit verschachtelten Datenstrukturen im Abfrage-Service](https://experienceleague.adobe.com/docs/experience-platform/query/key-concepts/nested-data-structures.html?lang=en).

### Planen der Abfrage

Sie planen die Abfrage, um sicherzustellen, dass die Abfrage ausgeführt und die Ergebnisse in Ihrem gewünschten Intervall generiert werden. Bei der Planung der Abfrage definieren Sie einen Ausgabedatensatz.

#### Verwenden des Abfrage-Editors

Sie können eine Abfrage mit dem Abfrage-Editor planen. Beim Definieren eines Zeitplans für eine Abfrage können Sie den Ausgabedatensatz definieren. Siehe [Abfragepläne](https://experienceleague.adobe.com/docs/experience-platform/query/ui/query-schedules.html?lang=en) für weitere Informationen.


#### Verwenden der Query Service-API

Alternativ können Sie die RESTful-APIs verwenden, um eine Abfrage und einen Zeitplan für die Abfrage zu definieren. Siehe [Handbuch zur Query Service-API](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en_) für weitere Informationen.
Stellen Sie sicher, dass Sie den Ausgabedatensatz als Teil des optionalen `ctasParameters` -Eigenschaft beim Erstellen der Abfrage ([Abfragen erstellen](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)) oder beim Erstellen des Zeitplans für eine Abfrage ([Geplante Abfrage erstellen](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)).



## Datensatzexport

Nachdem Sie Ihre Abfrage erstellt und geplant und überprüft haben, ob die Ergebnisse in den Ausgabedatensätzen Ihren Anforderungen entsprechen, können Sie die Rohdatensätze dann in Cloud-Speicher-Ziele exportieren. Dieser Export erfolgt in der Experience Platform Destinations-Terminologie, die als Datensatzexport-Ziele bezeichnet wird. Siehe [Exportieren von Datensätzen in Cloud-Speicher-Ziele](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=de) für einen Überblick.

Die folgenden Cloud-Speicher-Ziele werden unterstützt:

* [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2.html?lang=en)
* [Data Landing Zone](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=en)
* [Google Cloud Storage](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage.html?lang=en)
* [Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3.html?lang=en#changelog)
* [Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob.html?lang=en#changelog)
* [SFTP](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/sftp.html?lang=en#changelog)


### Experience Platform-Benutzeroberfläche

Sie können den Export Ihrer Ausgabedatensätze über die Experience Platform-Benutzeroberfläche exportieren und planen. In diesem Abschnitt werden die erforderlichen Schritte beschrieben.

#### Ziel auswählen

Wenn Sie ermittelt haben, zu welchem Cloud-Speicher-Ziel Sie den Ausgabedatensatz exportieren möchten, [Ziel auswählen](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-destination). Wenn Sie noch kein Ziel für Ihren bevorzugten Cloud-Speicher konfiguriert haben, müssen Sie [Erstellen einer neuen Zielverbindung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/connect-destination.html?lang=de).

Im Rahmen der Konfiguration eines Ziels können Sie den Dateityp (JSON oder Parquet) definieren, ob die resultierende Datei komprimiert werden soll oder nicht und ob eine Manifestdatei enthalten sein soll oder nicht.


#### Datensatz auswählen

Wenn Sie das Ziel ausgewählt haben, klicken Sie im nächsten **[!UICONTROL Auswählen von Datensätzen]** Schritt müssen Sie Ihren Ausgabedatensatz aus der Liste der Datensätze auswählen. Wenn Sie mehrere geplante Abfragen erstellen und möchten, dass die Ausgabedatensätze an dasselbe Cloud-Speicher-Ziel gesendet werden, können Sie die entsprechenden Ausgabedatensätze auswählen. Siehe [Auswählen Ihrer Datensätze](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-datasets) für weitere Informationen.

#### Planen des Datensatzexports

Schließlich möchten Sie Ihren Datensatzexport als Teil der **[!UICONTROL Planung]** Schritt. In diesem Schritt können Sie den Zeitplan definieren und festlegen, ob der Export des Ausgabedatensatzes inkrementell erfolgen soll oder nicht. Siehe [Datensatz-Export planen](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#scheduling) für weitere Informationen.


#### Abgeschlossene Schritte

[Überprüfen](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#review) Ihre Auswahl und wenn Sie den Export Ihres Ausgabedatasets in das Cloud-Speicher-Ziel ordnungsgemäß starten.

Sie müssen [verify](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) einen erfolgreichen Datenexport. Beim Exportieren von Datensätzen erstellt Experience Platform eine oder mehrere `.json` oder `.parquet` -Dateien am Speicherort, der in Ihrem Ziel definiert ist. Erwarten Sie, dass neue Dateien entsprechend dem von Ihnen eingerichteten Exportplan an Ihrem Speicherort abgelegt werden. Experience Platform erstellt eine Ordnerstruktur am Speicherort, den Sie als Teil des ausgewählten Ziels angegeben haben, wo die exportierten Dateien abgelegt werden. Für jeden Exportzeitpunkt wird ein neuer Ordner nach folgendem Muster erstellt: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Der standardmäßige Dateiname wird nach dem Zufallsprinzip generiert, was sicherstellt, dass die Namen von exportierten Dateien eindeutig sind.

### Flussdienst-API

Alternativ können Sie den Export von Ausgabedatensets mithilfe von APIs exportieren und planen. Die erforderlichen Schritte werden im Abschnitt [Exportieren von Datensätzen mithilfe der Flow Service-API](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html).

#### Erste Schritte

Vergewissern Sie sich, dass [erforderliche Berechtigungen](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#permissions) , um Datensätze zu exportieren, und dass das Ziel, an das Sie Ihren Ausgabedatensatz senden möchten, den Export von Datensätzen unterstützt. Sie müssen [Werte für erforderliche und optionale Kopfzeilen erfassen](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-values-headers) Sie verwenden in den API-Aufrufen sowie [Identifizieren der Verbindungsspezifikations- und Flussspezifikations-IDs des Ziels](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-connection-spec-flow-spec) Sie beabsichtigen, Datensätze in zu exportieren.

#### Abrufen zulässiger Datensätze

Sie können [Liste der zulässigen Datensätze abrufen](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#retrieve-list-of-available-datasets) zum Exportieren und überprüfen Sie, ob Ihr Ausgabedatensatz mithilfe der [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API.


#### Erstellen der Quellverbindung

Als Nächstes müssen Sie [Quellverbindung erstellen](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-source-connection) für den Ausgabedatensatz, den Sie mit seiner eindeutigen ID an das Cloud-Speicher-Ziel exportieren möchten. Sie verwenden die [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API.

#### Authentifizierung am Ziel (Basisverbindung erstellen)

Sie müssen jetzt [Basisverbindung erstellen](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-base-connection) , um die Anmeldeinformationen ordnungsgemäß zu authentifizieren und sicher in Ihrem Cloud-Speicher-Ziel zu speichern, indem Sie die [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API.


#### Exportparameter angeben

Als Nächstes müssen Sie [eine zusätzliche Zielverbindung erstellen, in der die Exportparameter gespeichert werden](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-target-connection) für Ihren Ausgabedatensatz verwenden, indem Sie erneut die [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API. Zu diesen Exportparametern gehören Speicherort, Dateiformat, Komprimierung und mehr.

#### Einrichten des Datenflusses

Schließlich haben Sie [Datenfluss einrichten](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-dataflow) , um sicherzustellen, dass Ihr Ausgabedatensatz mit dem [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API. In diesem Schritt können Sie den Zeitplan für den Export mithilfe der Variablen `scheduleParams` -Parameter.

#### Validieren des Datenflusses

nach [Überprüfen erfolgreicher Ausführungen Ihres Datenflusses](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#get-dataflow-runs), verwenden Sie die [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API, die die Datenfluss-ID als Abfrageparameter angibt. Diese Datenfluss-ID ist eine Kennung, die beim Einrichten des Datenflusses zurückgegeben wird.

[Überprüfen](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) einen erfolgreichen Datenexport. Beim Exportieren von Datensätzen erstellt Experience Platform eine oder mehrere `.json` oder `.parquet` -Dateien am Speicherort, der in Ihrem Ziel definiert ist. Erwarten Sie, dass neue Dateien entsprechend dem von Ihnen eingerichteten Exportplan an Ihrem Speicherort abgelegt werden. Experience Platform erstellt eine Ordnerstruktur am Speicherort, den Sie als Teil des ausgewählten Ziels angegeben haben, wo die exportierten Dateien abgelegt werden. Für jeden Exportzeitpunkt wird ein neuer Ordner nach folgendem Muster erstellt: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Der standardmäßige Dateiname wird nach dem Zufallsprinzip generiert, was sicherstellt, dass die Namen von exportierten Dateien eindeutig sind.

## Zusammenfassung

Kurz gesagt, das Emulieren der Adobe Analytics-Daten-Feed-Funktion erfordert die Einrichtung geplanter Abfragen mit Query Service und die Verwendung der Ergebnisse dieser Abfragen in geplanten Datensatzexporten.

>[!IMPORTANT]
>
>An diesem Anwendungsfall sind zwei Planer beteiligt. Um eine ordnungsgemäße Funktionsweise der emulierten Daten-Feed-Funktion zu gewährleisten, stellen Sie sicher, dass die in Query Service konfigurierten Zeitpläne und Datenexporte nicht stören.

