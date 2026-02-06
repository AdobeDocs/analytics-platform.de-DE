---
title: Experience Platform Query Service-Daten (Distiller) und Datensätze exportieren
description: Beschreibt die Verwendung des Abfrage-Service (Data Distiller) und des Datensatzexports zum Exportieren von Daten.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 14a90758-91eb-4610-8802-1edfdb8b9689
source-git-commit: 20ead546897ad517840f95a5ec4dcd7f830afe8c
workflow-type: tm+mt
source-wordcount: '2642'
ht-degree: 10%

---

# Abfrage-Service-Daten (Distiller) und Datensätze exportieren

In diesem Artikel wird beschrieben, wie die Kombination aus Experience Platform Query Service (Data Distiller) und Datensatzexport verwendet werden kann, um die folgenden [Anwendungsfälle für den Datenexport) zu ](overview.md):

- Datenvalidierung
- Data Lake, Data Warehouse der BI-Tools
- Bereitschaft für künstliches und maschinelles Lernen.


Adobe Analytics kann diese Anwendungsfälle mithilfe seiner [Daten-Feeds](https://experienceleague.adobe.com/de/docs/analytics/export/analytics-data-feed/data-feed-overview) implementieren. Daten-Feeds sind eine leistungsstarke Methode, Rohdaten aus Adobe Analytics abzurufen. In diesem Artikel wird beschrieben, wie Sie ähnliche Rohdaten aus Experience Platform abrufen können, damit Sie die oben genannten Anwendungsfälle implementieren können. Gegebenenfalls werden die in diesem Artikel beschriebenen Funktionen mit den Daten-Feeds von Adobe Analytics verglichen, um Unterschiede bei Daten und Prozessen zu verdeutlichen.

## Einführung

Der Datenexport mithilfe von Query Service (Data Distiller) und der Datensatzexport besteht aus:

- Definieren einer **geplanten Abfrage** die die Daten für Ihren Daten-Feed als Ausgabedatensatz (![) ](../assets/output-dataset.svg) mithilfe von **Query Service** generiert.
- Definieren eines **geplanten Datensatzexports** der den Ausgabedatensatz mithilfe eines Datensatzexports in ein Cloud-**exportiert**.

![Daten-Feed](../assets/queryservice-export-datasets.svg)


## Voraussetzungen

Stellen Sie sicher, dass Sie alle folgenden Anforderungen erfüllen, bevor Sie die in diesem Anwendungsfall beschriebenen Funktionen verwenden:

- Eine funktionierende Implementierung, die Daten im Data Lake von Experience Platform erfasst.
- Zugriff auf das Data Distiller-Add-on, um sicherzustellen, dass Sie berechtigt sind, Batch-Abfragen auszuführen. Weitere Informationen finden [ unter &quot;](https://experienceleague.adobe.com/en/docs/experience-platform/query/packaging) von Query Service“.
- Zugriff auf die Funktion zum Exportieren von Datensätzen, verfügbar, wenn Sie das Real-Time CDP Prime- oder Ultimate-Paket, Adobe Journey Optimizer oder Customer Journey Analytics erworben haben. Weitere [ finden Sie unter „Exportieren von Datensätzen ](https://experienceleague.adobe.com/de/docs/experience-platform/destinations/ui/activate/export-datasets) Cloud-Speicher-Ziele“.
- Ein oder mehrere konfigurierte Ziele (z. B. Amazon S3, Google Cloud Storage), an die Sie die Rohdaten Ihres Daten-Feeds exportieren können.


## Abfrage-Service

Mit Experience Platform Query Service können Sie einen beliebigen Datensatz im Data Lake von Experience Platform abfragen und verbinden, als ob es sich um eine Datenbanktabelle handelt. Anschließend können Sie die Ergebnisse als neuen Datensatz erfassen, der beim Reporting oder für den Export weiter verwendet werden kann.

Sie können den Abfrage-Service [Benutzeroberfläche](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/overview), einen [Client, der über das PostgresQL-](https://experienceleague.adobe.com/de/docs/experience-platform/query/clients/overview) verbunden ist, oder [RESTful-APIs](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started) verwenden, um Abfragen zu erstellen und zu planen, die die Daten für Ihren Daten-Feed erfassen.

### Abfrage erstellen

Sie können alle Funktionen von ANSI SQL für SELECT-Anweisungen und andere eingeschränkte Befehle verwenden, um Abfragen zu erstellen und auszuführen, die die Daten für Ihren Daten-Feed generieren. Siehe [SQL-](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/syntax) für weitere Informationen. Über diese SQL-Syntax hinaus unterstützt Adobe Folgendes:

- vordefinierte [Adobe-definierte ](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions) (ADF), die Sie bei der Durchführung gängiger geschäftsbezogener Aufgaben im Zusammenhang mit im Experience Platform Data Lake gespeicherten Ereignisdaten unterstützen, einschließlich Funktionen für [Sessionization](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing) und [Attribution](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/overview),
- mehrere integrierte [Spark SQL-](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions),
- [Metadaten PostgreSQL-](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/metadata),
- [Vorbereitete Anweisungen](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/prepared-statements).

#### Daten-Feed-Spalten

Die XDM-Felder, die Sie in Ihrer Abfrage verwenden können, hängen von der Schemadefinition ab, auf der Ihre Datensätze basieren. Stellen Sie sicher, dass Sie das dem Datensatz zugrunde liegende Schema verstehen. Weitere Informationen finden Sie im [Handbuch zur Datensatzbenutzeroberfläche](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/user-guide).

Informationen zum Definieren der Zuordnung zwischen den Daten-Feed-Spalten und XDM-Feldern finden Sie unter [Analytics-Feldzuordnung](https://experienceleague.adobe.com/de/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics). Weitere Informationen zum Verwalten von XDM-Ressourcen[ einschließlich Schemata, Klassen, Feldergruppen und Datentypen, finden Sie ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/overview#defining-xdm-fields) der Übersicht über die Schemas-Benutzeroberfläche .

Beispiel: Sie möchten *Seitenname* als Teil Ihres Daten-Feeds verwenden:

- In der Benutzeroberfläche von Adobe Analytics Daten-Feed wählen Sie **[!UICONTROL pagename]** als Spalte aus, die Sie Ihrer Daten-Feed-Definition hinzufügen möchten.
- In Query Service schließen Sie `web.webPageDetails.name` aus dem `sample_event_dataset_for_website_global_v1_1` Datensatz (basierend auf dem Erlebnisereignisschema **Sample Event Schema for Website (Global v1.1)** in Ihre Abfrage ein. Weitere Informationen finden [ in der Schemafeldgruppe ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/web-details)Web-Details“.


#### Identitäten

In Experience Platform sind verschiedene Identitäten verfügbar. Stellen Sie beim Erstellen Ihrer Abfragen sicher, dass Sie Identitäten korrekt abfragen.


Häufig finden Sie Identitäten in einer separaten Feldergruppe. In einer Implementierung kann ECID (`ecid`) als Teil einer Feldergruppe mit einem `core`-Objekt definiert werden, das selbst Teil eines `identification`-Objekts ist (zum Beispiel: `_sampleorg.identification.core.ecid`). Die ECIDs sind in Ihren Schemata möglicherweise unterschiedlich organisiert.

Alternativ können Sie `identityMap` verwenden, um Identitäten abzufragen. Der `identityMap` ist vom Typ `Map` und verwendet eine [verschachtelte Datenstruktur](#nested-data-structure).

Weitere [ zum Definieren von Identitätsfeldern in Experience Platform finden ](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/ui/fields/identity) unter „Definieren von Identitätsfeldern in der Benutzeroberfläche“.

Unter [Primäre Kennungen in Analytics-Daten](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics#primary-identifiers-in-analytics-data) erfahren Sie, wie Adobe Analytics-Identitäten bei Verwendung des Analytics-Quell-Connectors Experience Platform-Identitäten zugeordnet werden. Diese Zuordnung kann Ihnen bei der Einrichtung Ihrer Identitäten helfen, auch wenn Sie den Analytics-Quell-Connector nicht verwenden.


#### Daten und Identifizierung auf Trefferebene

Basierend auf der Implementierung werden Trefferdaten, die traditionell in Adobe Analytics erfasst werden, jetzt als Ereignisdaten mit Zeitstempel in Experience Platform gespeichert. Die folgende Tabelle wird aus der [Analytics-Feldzuordnung](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics#generated-mapping-fields) extrahiert und zeigt Beispiele für die Zuordnung trefferebenenspezifischer Adobe Analytics-Daten-Feed-Spalten zu den entsprechenden XDM-Feldern in Ihren Abfragen. Die Tabelle zeigt auch Beispiele dafür, wie Treffer, Besuche und Besucher mithilfe von XDM-Feldern identifiziert werden.

| Daten-Feed-Spalte | XDM-Feld | Typ | Beschreibung |
|---|---|---|---|
| `hitid_high` + `hitid_low` | `_id` | string | Eindeutige Kennung zur Identifizierung eines Treffers. |
| `hitid_low` | `_id` | string | Wird mit `hitid_high` verwendet, um einen Treffer eindeutig zu identifizieren. |
| `hitid_high` | `_id` | string | Wird mit `hitid_high` verwendet, um einen Treffer eindeutig zu identifizieren. |
| `hit_time_gmt` | `receivedTimestamp` | string | Der Zeitstempel des Treffers, basierend auf der UNIX®-Zeit. |
| `cust_hit_time_gmt` | `timestamp` | string | Dieser Zeitstempel wird nur in zeitstempelaktivierten Datensätzen verwendet. Dieser Zeitstempel wird mit dem Treffer gesendet, basierend auf der UNIX®-Zeit. |
| `visid_high` + `visid_low` | `identityMap` | Objekt | Eindeutige Kennung für einen Besuch. |
| `visid_high` + `visid_low` | `endUserIDs._experience.aaid.id` | string | Eindeutige Kennung für einen Besuch. |
| `visid_high` | `endUserIDs._experience.aaid.primary` | boolean | Wird mit `visid_low` verwendet, um einen Besuch eindeutig zu identifizieren. |
| `visid_high` | `endUserIDs._experience.aaid.namespace.code` | string | Wird mit `visid_low` verwendet, um einen Besuch eindeutig zu identifizieren. |
| `visid_low` | `identityMap` | Objekt | Wird mit `visid_high` verwendet, um einen Besuch eindeutig zu identifizieren. |
| `cust_visid` | `identityMap` | Objekt | Die Besucher-ID des Kunden. |
| `cust_visid` | `endUserIDs._experience.aacustomid.id` | Objekt | Die Besucher-ID des Kunden. |
| `cust_visid` | `endUserIDs._experience.aacustomid.primary` | boolean | Der Namespace-Code der Besucher-ID des Kunden. |
| `cust_visid` | `endUserIDs._experience.aacustomid.namespace.code` | string | Wird mit `visid_low` verwendet, um die Besucher-ID des Kunden eindeutig zu identifizieren. |
| `geo\_*` | `placeContext.geo.* ` | Zeichenfolge, Zahl | Geolokalisierungsdaten wie Land, Region, Stadt und andere |
| `event_list` | `commerce.purchases`, `commerce.productViews`, `commerce.productListOpens`, `commerce.checkouts`, `commerce.productListAdds`, `commerce.productListRemovals`, `commerce.productListViews`, `_experience.analytics.event101to200.*`, …, `_experience.analytics.event901_1000.*` | string | Beim Treffer ausgelöste Standard-Commerce- und benutzerdefinierte Ereignisse. |
| `page_event` | `web.webInteraction.type` | string | Die Art des in der Bildanforderung gesendeten Treffers (Standardtreffer, angeklickter Downloadlink, Exitlink oder benutzerspezifischer Link). |
| `page_event` | `web.webInteraction.linkClicks.value` | number | Die Art des in der Bildanforderung gesendeten Treffers (Standardtreffer, angeklickter Downloadlink, Exitlink oder benutzerspezifischer Link). |
| `page_event_var_1` | `web.webInteraction.URL` | string | Variable, die nur in Bildanforderungen zum Linktracking verwendet wird. Die Variable enthält die URL des angeklickten Downloadlinks, Exitlinks oder benutzerspezifischen Links. |
| `page_event_var_2` | `web.webInteraction.name` | string | Variable, die nur in Bildanforderungen zum Linktracking verwendet wird. Damit wird der benutzerdefinierte Name des Links aufgeführt, sofern angegeben. |
| `paid_search` | `search.isPaid` | boolean | Markierung, die gesetzt wird, wenn der Treffer mit der Paid Search-Erkennung übereinstimmt. |
| `ref_type` | `web.webReferrertype` | string | Eine numerische ID, die den Typ des Verweises für den Treffer darstellt. |

#### Spalten posten

Adobe Analytics-Daten-Feeds verwenden das Konzept der Spalten mit `post_` Präfix, d. h. Spalten, die Daten nach der Verarbeitung enthalten. Weitere Informationen finden Sie in den [häufig gestellten Fragen zu Daten-Feeds](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/df-faq#post).

Daten, die in Datensätzen über die Experience Platform Edge Network (Web SDK, Mobile SDK, Server-API) erfasst werden, haben kein Konzept von `post_`. Daher werden `post_` Daten-Feed-Spalten mit Präfixen *Nicht*`post_` Präfixen denselben XDM-Feldern zugeordnet. Beispielsweise werden sowohl `page_url`- als auch `post_page_url` Daten-Feed-Spalten demselben `web.webPageDetails.URL` XDM-Feld zugeordnet.

Einen [ über die Unterschiede bei der Datenverarbeitung finden Sie unter „Vergleich ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons) Datenverarbeitung in Adobe Analytics und Customer Journey Analytics&quot;.

Der Datentyp &quot;`post_`-Präfix-Spalte“ erfordert bei der Erfassung im Data Lake von Experience Platform jedoch erweiterte Umwandlungen, bevor er in einem Daten-Feed-Anwendungsfall erfolgreich verwendet werden kann. Die Durchführung dieser erweiterten Transformationen in Ihren Abfragen umfasst die Verwendung von [Adobe-definierten Funktionen](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions) für die Sitzungserstellung, Attribution und Deduplizierung. Siehe [Beispiele](#examples) zur Verwendung dieser Funktionen.

#### Lookups

Zum Nachschlagen von Daten aus anderen Datensätzen verwenden Sie standardmäßige SQL-Funktionen (`WHERE`, `INNER JOIN`, `OUTER JOIN` und andere).

#### Berechnungen

Um Berechnungen für Felder (Spalten) durchzuführen, verwenden Sie die standardmäßigen SQL-Funktionen (z. B. `COUNT(*)`) oder die [mathematischen und statistischen Operatoren und Funktionen](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#math), die Teil von Spark SQL sind. Außerdem unterstützen [Fensterfunktionen](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions#window-functions) die Aktualisierung von Aggregationen und geben einzelne Elemente für jede Zeile in einer sortierten Teilmenge zurück. Siehe [Beispiele](#examples) zur Verwendung dieser Funktionen.

#### Verschachtelte Datenstruktur

Die Schemata, auf denen die Datensätze basieren, enthalten oft komplexe Datentypen, einschließlich verschachtelter Datenstrukturen. Das zuvor erwähnte `identityMap` ist ein Beispiel für eine verschachtelte Datenstruktur. Ein Beispiel für `identityMap` Daten finden Sie unten.

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

Sie können die [`explode()` oder andere Array-Funktionen ](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#arrays) Spark SQL verwenden, um zu den Daten in einer verschachtelten Datenstruktur zu gelangen, z. B.:

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Alternativ können Sie mithilfe der Punktnotation auf einzelne Elemente verweisen. Zum Beispiel:

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Weitere Informationen finden Sie unter [Arbeiten mit verschachtelten Datenstrukturen im Abfrage-Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/nested-data-structures).


#### Beispiele

Für Abfragen:

- die Daten aus Datensätzen im Data Lake von Experience Platform verwenden,
- die zusätzlichen Funktionen von Adobe Defined Functions und/oder Spark SQL nutzen und
- die ähnliche Ergebnisse wie ein gleichwertiger Adobe Analytics-Daten-Feed liefern würde,

Siehe:

- [Abgebrochenes Durchsuchen](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/abandoned-browse)
- [Attributionsanalyse](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/attribution-analysis)
- [Bot-Filterung](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/bot-filtering)
- und andere [unterstützte Anwendungsfälle im Query Service-Handbuch](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/overview).

Im Folgenden finden Sie ein Beispiel für die ordnungsgemäße Anwendung der Attribution auf Sitzungen und es wird gezeigt, wie

- Verwenden Sie die letzten 90 Tage als Lookback,
- Fensterfunktionen wie Sitzungserstellung und/oder Attribution anwenden und
- schränken Sie die Ausgabe anhand der `ingest_time` ein.

  +++ Details

  Um dies zu tun, müssen Sie…

   - Verwenden Sie `checkpoint_log` eine Verarbeitungsstatustabelle, um den aktuellen Zeitpunkt im Vergleich zur letzten Aufnahme zu verfolgen. Weitere Informationen finden [ in ](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/incremental-load) Handbuch.
   - Deaktivieren Sie das Ablegen von Systemspalten, damit Sie `_acp_system_metadata.ingestTime` verwenden können.
   - Verwenden Sie eine innere `SELECT`, um die Felder zu erfassen, die Sie verwenden möchten, und beschränken Sie die Ereignisse auf Ihren Lookback-Zeitraum für Sitzungs- und/oder Attributionsberechnungen. Beispiel: 90 Tage.
   - Verwenden Sie eine `SELECT` der nächsten Ebene, um Ihre Sitzungs- und/oder Attributionsfensterfunktionen und andere Berechnungen anzuwenden.
   - Verwenden Sie `INSERT INTO` in Ihrer Ausgabetabelle, um den Lookback auf die Ereignisse zu beschränken, die seit der letzten Verarbeitungszeit eingetroffen sind. Hierfür filtern Sie nach der Zeit`_acp_system_metadata.ingestTime ` die zuletzt in Ihrer Verarbeitungsstatustabelle gespeichert wurde.

  **Beispiel für Fensterfunktionen des Sitzungsfensters**

  ```sql
  $$ BEGIN
     -- Disable dropping system columns
     set drop_system_columns=false; 
  
     -- Initialize variables
     SET @last_updated_timestamp = SELECT CURRENT_TIMESTAMP;
  
     -- Get the last processed batch ingestion time
     SET @from_batch_ingestion_time = SELECT coalesce(last_batch_ingestion_time, 'HEAD') 
        FROM checkpoint_log a 
        JOIN (
              SELECT MAX(process_timestamp) AS process_timestamp 
              FROM checkpoint_log
              WHERE process_name = 'data_feed' 
              AND process_status = 'SUCCESSFUL'
        ) b
        ON a.process_timestamp = b.process_timestamp;
  
     -- Get the last batch ingestion time
     SET @to_batch_ingestion_time = SELECT MAX(_acp_system_metadata.ingestTime) 
        FROM events_dataset;
  
     -- Sessionize the data and insert into data_feed.
     INSERT INTO data_feed
     SELECT *
     FROM (
        SELECT
              userIdentity,
              timestamp,
              SESS_TIMEOUT(timestamp, 60 * 30) OVER (
                 PARTITION BY userIdentity
                 ORDER BY timestamp
                 ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
              ) AS session_data,
              page_name,
              ingest_time
        FROM (
              SELECT
                 userIdentity,
                 timestamp,
                 web.webPageDetails.name AS page_name,
                 _acp_system_metadata.ingestTime AS ingest_time
              FROM events_dataset
              WHERE timestamp >= current_date - 90
        ) AS a
        ORDER BY userIdentity, timestamp ASC
     ) AS b
     WHERE b.ingest_time >= @from_batch_ingestion_time;
  
     -- Update the checkpoint_log table
     INSERT INTO checkpoint_log
     SELECT
        'data_feed' process_name,
        'SUCCESSFUL' process_status,
        cast(@to_batch_ingestion_time AS string) last_batch_ingestion_time,
        cast(@last_updated_timestamp AS TIMESTAMP) process_timestamp
  END
  $$;
  ```

  **Beispiel für Funktionen des Attributionsfensters**

  ```sql
  $$ BEGIN
   SET drop_system_columns=false;
  
  -- Initialize variables
   SET @last_updated_timestamp = SELECT CURRENT_TIMESTAMP;
  
  -- Get the last processed batch ingestion time 1718755872325
   SET @from_batch_ingestion_time =
       SELECT coalesce(last_snapshot_id, 'HEAD')
       FROM checkpoint_log a
       JOIN (
           SELECT MAX(process_timestamp) AS process_timestamp
           FROM checkpoint_log
           WHERE process_name = 'data_feed'
           AND process_status = 'SUCCESSFUL'
       ) b
       ON a.process_timestamp = b.process_timestamp;
  
   -- Get the last batch ingestion time 1718758687865
   SET @to_batch_ingestion_time =
       SELECT MAX(_acp_system_metadata.ingestTime)
       FROM demo_data_trey_mcintyre_midvalues;
  
   -- Sessionize the data and insert into new_sessionized_data
   INSERT INTO new_sessionized_data
   SELECT *
   FROM (
       SELECT
           _id,
           timestamp,
           struct(User_Identity,
           cast(SESS_TIMEOUT(timestamp, 60 * 30) OVER (
               PARTITION BY User_Identity
               ORDER BY timestamp
               ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
           ) as string) AS SessionData,
           to_timestamp(from_unixtime(ingest_time/1000, 'yyyy-MM-dd HH:mm:ss')) AS IngestTime,      
           PageName,
           first_url,
           first_channel_type
             ) as _demosystem5
       FROM (
           SELECT
               _id,
               ENDUSERIDS._EXPERIENCE.MCID.ID as User_Identity,
               timestamp,
               web.webPageDetails.name AS PageName,
              attribution_first_touch(timestamp, '', web.webReferrer.url) OVER (PARTITION BY ENDUSERIDS._EXPERIENCE.MCID.ID ORDER BY timestamp ASC ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING).value AS first_url,
              attribution_first_touch(timestamp, '',channel.typeAtSource) OVER (PARTITION BY ENDUSERIDS._EXPERIENCE.MCID.ID ORDER BY timestamp ASC ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING).value AS first_channel_type,
               _acp_system_metadata.ingestTime AS ingest_time
           FROM demo_data_trey_mcintyre_midvalues
           WHERE timestamp >= current_date - 90
       )
       ORDER BY User_Identity, timestamp ASC    
   )
   WHERE _demosystem5.IngestTime >= to_timestamp(from_unixtime(@from_batch_ingestion_time/1000, 'yyyy-MM-dd HH:mm:ss'));
  
  -- Update the checkpoint_log table
  INSERT INTO checkpoint_log
  SELECT
     'data_feed' as process_name,
     'SUCCESSFUL' as process_status,
     cast(@to_batch_ingestion_time AS string) as last_snapshot_id,
     cast(@last_updated_timestamp AS timestamp) as process_timestamp;
  
  END
  $$;
  ```

  +++


### Abfrage planen

Sie planen die Abfrage, um sicherzustellen, dass die Abfrage ausgeführt wird und die Ergebnisse in Ihrem bevorzugten Intervall generiert werden.

#### Verwenden des Abfrage-Editors

Sie können eine Abfrage mit dem Abfrage-Editor planen. Beim Planen der Abfrage definieren Sie einen Ausgabedatensatz. Weitere Informationen finden [ unter ](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/query-schedules) .


#### Verwenden der Abfrage-Service-API

Alternativ können Sie die RESTful-APIs verwenden, um eine Abfrage zu definieren und einen Zeitplan für die Abfrage festzulegen. Weitere Informationen finden Sie [ „Handbuch zur Abfrage](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started)Service-API“.
Stellen Sie sicher, dass Sie den Ausgabedatensatz als Teil der optionalen `ctasParameters`-Eigenschaft definieren, wenn Sie die Abfrage erstellen ([Abfrage erstellen](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery) oder wenn Sie den Zeitplan für eine Abfrage erstellen ([geplante Abfrage erstellen](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)).



## Exportieren von Datensätzen

Nachdem Sie Ihre Abfrage erstellt, geplant und die Ergebnisse überprüft haben, können Sie die Rohdatensätze in Cloud-Speicher-Ziele exportieren. Dieser Export wird in der Terminologie für Experience Platform-Ziele als Datensatzexportziele bezeichnet. Siehe [Exportieren von Datensätzen zu Cloud-Speicher](https://experienceleague.adobe.com/de/docs/experience-platform/destinations/ui/activate/export-datasets) für eine Übersicht.

Die folgenden Cloud-Speicherziele werden unterstützt:

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Data Landing Zone](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google Cloud Storage](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3)
- [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp)


### Experience Platform-Benutzeroberfläche

Sie können den Export Ihrer Ausgabedatensätze über die Experience Platform-Benutzeroberfläche exportieren und planen. In diesem Abschnitt werden die beteiligten Schritte beschrieben.

#### Ziel auswählen

Wenn Sie ermittelt haben, an welches Cloud-Speicher-Ziel Sie den Ausgabedatensatz exportieren möchten, wählen [ das Ziel ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). Wenn Sie noch kein Ziel für Ihren bevorzugten Cloud-Speicher konfiguriert haben, müssen Sie [eine neue Zielverbindung erstellen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination).

Beim Konfigurieren eines Ziels haben Sie folgende Möglichkeiten

- den Dateityp definieren (JSON oder Parquet),
- ob die resultierende Datei komprimiert werden soll oder nicht, und
- Ob eine Manifestdatei eingeschlossen werden soll oder nicht.


#### Datensatz auswählen

Wenn Sie das Ziel ausgewählt haben, müssen **[!UICONTROL nächsten Schritt]** Auswählen von Datensätzen“ Ihren Ausgabedatensatz aus der Liste der Datensätze auswählen. Wenn Sie mehrere geplante Abfragen erstellt haben und die Ausgabedatensätze an dasselbe Cloud-Speicher-Ziel senden sollen, können Sie die entsprechenden Ausgabedatensätze auswählen. Weitere [ finden Sie unter ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) auswählen .

#### Planen des Datensatzexports

Schließlich möchten Sie den Datensatzexport als Teil des Schritts „Planung ****. In diesem Schritt können Sie den Zeitplan definieren und festlegen, ob der Ausgabedatensatz-Export inkrementell erfolgen soll oder nicht. Weitere Informationen [ Sie unter „Planen ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) Datensatzexports“.


#### Letzte Schritte

[Überprüfen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review) Sie Ihre Auswahl und beginnen Sie, Ihren Ausgabedatensatz nach Bedarf an das Cloud-Speicher-Ziel zu exportieren.

Sie müssen [überprüfen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) einen erfolgreichen Datenexport durchführen. Beim Exportieren von Datensätzen erstellt Experience Platform eine oder mehrere `.json` oder `.parquet` Dateien an dem in Ihrem Ziel definierten Speicherort. Neue Dateien werden voraussichtlich entsprechend dem von Ihnen eingerichteten Exportzeitplan an Ihrem Speicherort abgelegt. Experience Platform erstellt eine Ordnerstruktur an dem Speicherort, den Sie als Teil des ausgewählten Ziels angegeben haben, und legt dort die exportierten Dateien ab. Für jeden Exportzeitpunkt wird ein neuer Ordner erstellt, der dem Muster folgt: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Der standardmäßige Dateiname wird nach dem Zufallsprinzip generiert, was sicherstellt, dass die Namen von exportierten Dateien eindeutig sind.

### Flow Service-API

Alternativ können Sie den Export von Ausgabedatensätzen mithilfe von APIs exportieren und planen. Die hierfür erforderlichen Schritte werden in [Exportieren von Datensätzen mithilfe der Flow Service-API](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets) dokumentiert.

#### Erste Schritte

Um Datensätze zu exportieren, stellen Sie sicher, dass Sie über die [erforderlichen Berechtigungen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions) verfügen. Überprüfen Sie außerdem, ob das Ziel, an das Sie Ihren Ausgabedatensatz senden möchten, das Exportieren von Datensätzen unterstützt. Anschließend müssen Sie [ Werte für erforderliche und optionale Kopfzeilen ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers), die Sie in den API-Aufrufen verwenden. Außerdem müssen Sie [die Verbindungsspezifikations- und Flussspezifikations-IDs des Ziels identifizieren](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) für das Sie Datensätze exportieren möchten.

#### Abrufen zulässiger Datensätze

Sie können [eine Liste von geeigneten Datensätzen abrufen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) um sie zu exportieren und mithilfe der [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets)-API zu überprüfen, ob Ihr Ausgabedatensatz Teil dieser Liste ist.


#### Quellverbindung erstellen

Als Nächstes müssen Sie [Quellverbindung erstellen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) für den Ausgabedatensatz unter Verwendung seiner eindeutigen ID, die Sie an das Cloud-Speicher-Ziel exportieren möchten. Sie verwenden die [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection)-API.

#### Beim Ziel authentifizieren (Basisverbindung erstellen)

Sie müssen jetzt [eine Basisverbindung erstellen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection) um die Anmeldeinformationen mithilfe der [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection)-API zu authentifizieren und sicher in Ihrem Cloud-Speicher-Ziel zu speichern.


#### Exportparameter angeben

Als Nächstes müssen Sie [eine zusätzliche Zielverbindung erstellen, die die Exportparameter speichert](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) für Ihren Ausgabedatensatz, indem Sie erneut die [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection)-API verwenden. Zu diesen Exportparametern gehören Speicherort, Dateiformat, Komprimierung und mehr.

#### Einrichten eines Datenflusses

Schließlich richten Sie [den Datenfluss) ein](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow) um sicherzustellen, dass Ihr Ausgabedatensatz mithilfe der [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow)-API in Ihr Cloud-Speicher-Ziel exportiert wird. In diesem Schritt können Sie den Zeitplan für den Export mithilfe des `scheduleParams` definieren.

#### Validieren eines Datenflusses

Um [erfolgreiche Ausführungen Ihres Datenflusses zu überprüfen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs) verwenden Sie die [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns)-API und geben Sie die Datenfluss-ID als Abfrageparameter an. Diese Datenfluss-ID ist eine Kennung, die beim Einrichten des Datenflusses zurückgegeben wird.

[Überprüfen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) einen erfolgreichen Datenexport. Beim Exportieren von Datensätzen erstellt Experience Platform eine oder mehrere `.json` oder `.parquet` Dateien an dem in Ihrem Ziel definierten Speicherort. Neue Dateien werden voraussichtlich entsprechend dem von Ihnen eingerichteten Exportzeitplan an Ihrem Speicherort abgelegt. Experience Platform erstellt eine Ordnerstruktur an dem Speicherort, den Sie als Teil des ausgewählten Ziels angegeben haben, und legt dort die exportierten Dateien ab. Für jeden Exportzeitpunkt wird ein neuer Ordner erstellt, der dem Muster folgt: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Der standardmäßige Dateiname wird nach dem Zufallsprinzip generiert, was sicherstellt, dass die Namen von exportierten Dateien eindeutig sind.

## Zusammenfassung

Kurz gesagt: Die Emulation der Adobe Analytics-Daten-Feed-Funktionalität erfordert das Einrichten geplanter Abfragen mithilfe des Abfrage-Service und die Verwendung der Ergebnisse dieser Abfragen in geplanten Datensatzexporten.

>[!IMPORTANT]
>
>In diesem Anwendungsfall sind zwei Planer involviert. Um ein ordnungsgemäßes Funktionieren der emulierten Daten-Feed-Funktionen zu gewährleisten, stellen Sie sicher, dass die im Abfrage-Service konfigurierten Zeitpläne und Datenexporte nicht stören.
