---
title: Datenfeed-Funktion emulieren
description: Erfahren Sie, wie Sie Adobe Analytics-Daten-Feeds mit Daten im Experience Platform emulieren können.
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
role: Admin
exl-id: 71dd9e4e-1d71-424b-b984-492a3e39af5f
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '2402'
ht-degree: 10%

---

# Datenfeed-Funktion emulieren

Adobe Analytics-Daten-Feeds sind eine leistungsstarke Methode, Rohdaten aus Adobe Analytics abzurufen. In diesem Anwendungsbeispiel wird beschrieben, wie Sie ähnliche Rohdaten aus der Experience Platform abrufen können, damit Sie die Daten auf anderen Plattformen, außerhalb von Adobe und nach Ermessen Ihres Unternehmens verwenden können.

## Einführung

Die Emulation eines Adobe Analytics-Daten-Feeds umfasst:

* Definieren einer **Geplante Abfrage** , das die Daten für Ihren Daten-Feed als Ausgabedatensatz generiert ![Ausgabedatensatz](assets/output-dataset.svg)verwendet **Query Service**.
* Definieren einer **geplanter Datensatzexport** , der den Ausgabedatensatz in ein Cloud-Speicher-Ziel exportiert, mithilfe von **Datensatzexport**.

![Daten-Feed](assets/data-feed.svg)


## Voraussetzungen

Stellen Sie sicher, dass Sie alle folgenden Anforderungen erfüllen, bevor Sie die in diesem Anwendungsbeispiel beschriebene Funktion verwenden:

* Eine funktionierende Implementierung, die Daten in den Experience Platform Data Lake sammelt.
* Zugriff auf das Data Distiller-Add-on, um sicherzustellen, dass Sie berechtigt sind, Batch-Abfragen auszuführen. Siehe [Query Service-Verpackung](https://experienceleague.adobe.com/docs/experience-platform/query/packaging.html) für weitere Informationen.
* Zugriff auf die Funktion zum Exportieren von Datensätzen , die beim Kauf des Real-Time CDP Prime- oder Ultimate-Packages, Adobe Journey Optimizer oder Customer Journey Analytics verfügbar ist. Siehe [Exportieren von Datensätzen in Cloud-Speicher-Ziele](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=de) für weitere Informationen.
* Ein oder mehrere Ziele (z. B. Amazon S3, Google Cloud-Speicher), die für den Export der Rohdaten Ihres Daten-Feeds konfiguriert sind.


## Abfrage-Service

Mit dem Experience Platform Query Service können Sie einen beliebigen Datensatz in Experience Platform Data Lake abfragen und verbinden, als wäre es eine Datenbanktabelle. Anschließend können Sie die Ergebnisse als neuen Datensatz für die weitere Verwendung in Berichten oder für den Export erfassen.

Sie verwenden den Query Service [Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/query/ui/overview.html?lang=de), a [Client, der über das PostgresQL-Protokoll verbunden ist](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html)oder [RESTful-APIs](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=de) , um Abfragen zu erstellen und zu planen, die die Daten für Ihren Daten-Feed erfassen.

### Abfrage erstellen

Sie können alle Funktionen von Standard-ANSI SQL für SELECT-Anweisungen und andere eingeschränkte Befehle verwenden, um Abfragen zu erstellen und auszuführen, die die Daten für Ihren Daten-Feed generieren. Siehe [SQL-Syntax](https://experienceleague.adobe.com/docs/experience-platform/query/sql/syntax.html) für weitere Informationen. Neben dieser SQL-Syntax unterstützt Adobe Folgendes:

* vorkonfiguriert [Adobe-definierte Funktionen (ADF)](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html) , mit denen häufig geschäftsbezogene Aufgaben für Ereignisdaten durchgeführt werden können, die im Experience Platform Data Lake gespeichert sind, einschließlich Funktionen für [Sessionization](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing.html) und [Attribution](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=de),
* mehrere integrierte [Spark SQL-Funktionen](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html),
* [metadata PostgreSQL-Befehle](https://experienceleague.adobe.com/docs/experience-platform/query/sql/metadata.html),
* [vorbereitete Anweisungen](https://experienceleague.adobe.com/docs/experience-platform/query/sql/prepared-statements.html).

#### Daten-Feed-Spalten

Die XDM-Felder, die Sie in Ihrer Abfrage verwenden können, hängen von der Schemadefinition ab, auf der Ihre Datensätze basieren. Vergewissern Sie sich, dass Sie das dem Datensatz zugrunde liegende Schema verstehen. Siehe [Handbuch zur Benutzeroberfläche von Datensätzen](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=de) für weitere Informationen.

Informationen zum Definieren der Zuordnung zwischen den Daten-Feed-Spalten und XDM-Feldern finden Sie unter [Analytics-Feldzuordnung](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=de). Siehe auch [Übersicht über die Benutzeroberfläche von Schemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html#defining-xdm-fields) für weitere Informationen zum Verwalten von XDM-Ressourcen, einschließlich Schemas, Klassen, Feldergruppen und Datentypen.

Beispiel: falls Sie *Seitenname* als Teil Ihres Daten-Feeds:

* In der Benutzeroberfläche des Adobe Analytics-Daten-Feeds wählen Sie **[!UICONTROL pagename]** als die Spalte, die zu Ihrer Datenfeed-Definition hinzugefügt werden soll.
* In Query Service fügen Sie `web.webPageDetails.name` aus dem `sample_event_dataset_for_website_global_v1_1` Datensatz (basierend auf der **Beispielereignisschema für Website (Global v1.1)** Erlebnisereignisschema) in Ihrer Abfrage. Siehe [Feldgruppe &quot;Webdetails-Schema&quot;](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/web-details.html) für weitere Informationen.

<!--
To understand the mapping between Adobe Analytics data feed columns and XDM fields in your experience event dataset and underlying schema, see [Analytics fields mapping](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html) and [Adobe Analytics ExperienceEvent Full Extension schema field group](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html) for more information.

Furthermore, the [automatically collected information by the Experience Platform Web SDK (out of the box)](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html) might be relevant to identify columns for your query.
-->

#### Identitäten

Unter Experience Platform sind verschiedene Identitäten verfügbar. Stellen Sie bei der Erstellung Ihrer Abfragen sicher, dass Sie Identitäten richtig abfragen.


Oft finden Sie Identitäten in einer separaten Feldergruppe. In einer Implementierung ECID (`ecid`) kann als Teil einer Feldergruppe mit einer `core` -Objekt, das selbst Teil eines `identification` -Objekt (z. B.: `_sampleorg.identification.core.ecid`). Die ECIDs können in Ihren Schemas unterschiedlich organisiert sein.

Alternativ können Sie `identityMap` , um Identitäten abzufragen. Dieses Objekt ist vom Typ `Map` und verwendet eine [verschachtelte Datenstruktur](#nested-data-structure).

Siehe [Identitätsfelder in der Benutzeroberfläche definieren](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html) für weitere Informationen zur Definition von Identitätsfeldern in Experience Platform.

Siehe Abschnitt [Primäre IDs in Analytics-Daten](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html#primary-identifiers-in-analytics-data) für ein Verständnis, wie Adobe Analytics-Identitäten bei Verwendung des Analytics-Quell-Connectors Experience Platform-Identitäten zugeordnet werden. Dies kann als Anleitung zum Einrichten Ihrer Identitäten dienen, auch wenn Sie den Analytics-Quell-Connector nicht verwenden.


#### Daten und Identifizierung auf Trefferebene

Basierend auf der Implementierung werden traditionell in Adobe Analytics erfasste Trefferebenenddaten jetzt als Ereignisdaten mit Zeitstempel in Experience Platform gespeichert. Die folgende Tabelle wurde aus [Analytics-Feldzuordnung](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html#generated-mapping-fields) und zeigt Beispiele, wie Sie Trefferebenenspezifische Adobe Analytics Data Feed-Spalten mit entsprechenden XDM-Feldern in Ihren Abfragen zuordnen. Die Tabelle zeigt außerdem Beispiele dafür, wie Treffer, Besuche und Besucher mithilfe von XDM-Feldern identifiziert werden.

| Daten-Feed-Spalte | XDM-Feld | Typ | Beschreibung |
|---|---|---|---|
| `hitid_high` + `hitid_low` | `_id` | string | Eindeutige Kennung zur Identifizierung eines Treffers. |
| `hitid_low` | `_id` | string | Verwendet mit `hitid_high` zur eindeutigen Identifizierung eines Treffers. |
| `hitid_high` | `_id` | string | Verwendet mit `hitid_high` zur eindeutigen Identifizierung eines Treffers. |
| `hit_time_gmt` | `receivedTimestamp` | string | Der Zeitstempel des Treffers basierend auf der UNIX®-Zeit. |
| `cust_hit_time_gmt` | `timestamp` | string | Dieser Wert wird nur in für Zeitstempel aktivierten Datensätzen verwendet. Dies ist der Zeitstempel, der mit dem Treffer gesendet wird, basierend auf der UNIX®-Zeit. |
| `visid_high` + `visid_low` | `identityMap` | Objekt | Eindeutige Kennung für einen Besuch. |
| `visid_high` + `visid_low` | `endUserIDs._experience.aaid.id` | string | Eindeutige Kennung für einen Besuch. |
| `visid_high` | `endUserIDs._experience.aaid.primary` | boolean | Verwendet mit `visid_low` zur eindeutigen Identifizierung eines Besuchs. |
| `visid_high` | `endUserIDs._experience.aaid.namespace.code` | string | Verwendet mit `visid_low` zur eindeutigen Identifizierung eines Besuchs. |
| `visid_low` | `identityMap` | Objekt | Verwendet mit `visid_high` zur eindeutigen Identifizierung eines Besuchs. |
| `cust_visid` | `identityMap` | Objekt | Die Besucher-ID des Kunden. |
| `cust_visid` | `endUserIDs._experience.aacustomid.id` | Objekt | Die Besucher-ID des Kunden. |
| `cust_visid` | `endUserIDs._experience.aacustomid.primary` | boolean | Der Namespace-Code der Besucher-ID des Kunden. |
| `cust_visid` | `endUserIDs._experience.aacustomid.namespace.code` | string | Verwendet mit `visid_low` zur eindeutigen Identifizierung der Kunden-Besucher-ID. |
| `geo\_*` | `placeContext.geo.* ` | Zeichenfolge, Zahl | Geolocation-Daten wie Land, Region, Stadt und andere |
| `event_list` | `commerce.purchases`, `commerce.productViews`, `commerce.productListOpens`, `commerce.checkouts`, `commerce.productListAdds`, `commerce.productListRemovals`, `commerce.productListViews`, `_experience.analytics.event101to200.*`, ... `_experience.analytics.event901_1000.*` | string | Standardmäßige Commerce- und benutzerspezifische Ereignisse, die beim Treffer ausgelöst werden. |
| `page_event` | `web.webInteraction.type` | string | Die Art des in der Bildanforderung gesendeten Treffers (Standardtreffer, angeklickter Downloadlink, Exitlink oder benutzerspezifischer Link). |
| `page_event` | `web.webInteraction.linkClicks.value` | number | Die Art des in der Bildanforderung gesendeten Treffers (Standardtreffer, angeklickter Downloadlink, Exitlink oder benutzerspezifischer Link). |
| `page_event_var_1` | `web.webInteraction.URL` | string | Variable, die nur in Bildanforderungen zum Linktracking verwendet wird. Die Variable enthält die URL des angeklickten Downloadlinks, Exitlinks oder benutzerspezifischen Links. |
| `page_event_var_2` | `web.webInteraction.name` | string | Variable, die nur in Bildanforderungen zum Linktracking verwendet wird. Damit wird der benutzerdefinierte Name des Links aufgeführt, sofern angegeben. |
| `paid_search` | `search.isPaid` | boolean | Markierung, die gesetzt wird, wenn der Treffer mit der Paid Search-Erkennung übereinstimmt. |
| `ref_type` | `web.webReferrertype` | string | Eine numerische ID, die den Typ des Verweises für den Treffer darstellt. |

#### Post-Spalten

Adobe Analytics Data Feeds verwenden das Spaltenkonzept mit einer `post_` -Präfix, d. h. Spalten, die nach der Verarbeitung Daten enthalten. Weitere Informationen finden Sie in den [häufig gestellten Fragen zu Daten-Feeds](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/df-faq.html#post).

Daten, die in Datensätzen über das Experience Platform Edge Network (Web SDK, Mobile SDK, Server API) erfasst werden, haben kein Konzept von `post_` -Felder. Daher `post_` Präfix und *non*-`post_` Präfixe Daten-Feed-Spalten werden denselben XDM-Feldern zugeordnet. Beispielsweise können beide `page_url` und `post_page_url` Daten-Feed-Spalten werden demselben `web.webPageDetails.URL` XDM-Feld.

Siehe [Datenverarbeitung in Adobe Analytics und Customer Journey Analytics vergleichen](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons.html) für einen Überblick über die Unterschiede bei der Datenverarbeitung.

Die `post_` -Präfix-Spaltentyp von Daten, die im Experience Platform Data Lake erfasst werden, erfordert jedoch erweiterte Transformationen, bevor sie in einem Daten-Feed-Anwendungsfall erfolgreich verwendet werden können. Die Durchführung dieser erweiterten Umwandlungen in Abfragen erfordert die Verwendung von [Adobe-definierte Funktionen](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html) für die Sitzungserstellung, Attribution und Deduplizierung. Siehe [Beispiele](#examples) zur Verwendung dieser Funktionen.

#### Suchen

Zum Nachschlagen von Daten aus anderen Datensätzen verwenden Sie die SQL-Standardfunktion (`WHERE` -Klausel, `INNER JOIN`, `OUTER JOIN`und andere).

#### Berechnungen

Verwenden Sie die SQL-Standardfunktionen (z. B. `COUNT(*)`) oder der [mathematische und statistische Operatoren und Funktionen](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html#math) Teil von Spark SQL. Außerdem [Fensterfunktionen](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html#window-functions) unterstützen die Aktualisierung von Aggregationen und die Rückgabe einzelner Elemente für jede Zeile in einer sortierten Teilmenge. Siehe [Beispiele](#examples) zur Verwendung dieser Funktionen.

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

Sie können die [`explode()` oder anderen Arrays-Funktionen](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html#arrays) von Spark SQL, um zu den Daten in einer verschachtelten Datenstruktur zu gelangen, z. B.:

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Alternativ können Sie einzelne Elemente mit Punktnotation referenzieren. Zum Beispiel:

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Weitere Informationen finden Sie unter [Arbeiten mit verschachtelten Datenstrukturen im Abfrage-Service](https://experienceleague.adobe.com/docs/experience-platform/query/key-concepts/nested-data-structures.html).


#### Beispiele

Abfragen, die Daten aus Datensätzen im Experience Platform Data Lake verwenden, nutzen die zusätzlichen Funktionen von Adobe Defined Functions und/oder Spark SQL und liefern ähnliche Ergebnisse wie ein äquivalenter Adobe Analytics-Daten-Feed, siehe

* [abgebrochener Browser](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/abandoned-browse.html)
* [Attributionsanalyse](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/attribution-analysis.html)
* [Bot-Filterung](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/bot-filtering.html)
* und anderen Beispielanwendungsfällen im Query Service-Handbuch.


### Planen der Abfrage

Sie planen die Abfrage, um sicherzustellen, dass die Abfrage ausgeführt und die Ergebnisse in Ihrem gewünschten Intervall generiert werden.

#### Verwenden des Abfrage-Editors

Sie können eine Abfrage mit dem Abfrage-Editor planen. Bei der Planung der Abfrage definieren Sie einen Ausgabedatensatz. Siehe [Abfragepläne](https://experienceleague.adobe.com/docs/experience-platform/query/ui/query-schedules.html) für weitere Informationen.


#### Verwenden der Query Service-API

Alternativ können Sie die RESTful-APIs verwenden, um eine Abfrage und einen Zeitplan für die Abfrage zu definieren. Siehe [Handbuch zur Query Service-API](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=de) für weitere Informationen.
Stellen Sie sicher, dass Sie den Ausgabedatensatz als Teil des optionalen `ctasParameters` -Eigenschaft beim Erstellen der Abfrage ([Abfragen erstellen](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)) oder beim Erstellen des Zeitplans für eine Abfrage ([Geplante Abfrage erstellen](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)).



## Datensatzexport

Nachdem Sie Ihre Abfrage erstellt und geplant und überprüft haben, ob die Ergebnisse in den Ausgabedatensätzen Ihren Anforderungen entsprechen, können Sie die Rohdatensätze dann in Cloud-Speicher-Ziele exportieren. Dieser Export erfolgt in der Experience Platform Destinations-Terminologie, die als Datensatzexport-Ziele bezeichnet wird. Siehe [Exportieren von Datensätzen in Cloud-Speicher-Ziele](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=de) für einen Überblick.

Die folgenden Cloud-Speicher-Ziele werden unterstützt:

* [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2.html?lang=de)
* [Data Landing Zone](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=de)
* [Google Cloud Storage](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage.html?lang=de)
* [Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3.html#changelog)
* [Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob.html#changelog)
* [SFTP](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/sftp.html#changelog)


### Experience Platform-Benutzeroberfläche

Sie können den Export Ihrer Ausgabedatensätze über die Experience Platform-Benutzeroberfläche exportieren und planen. In diesem Abschnitt werden die erforderlichen Schritte beschrieben.

#### Ziel auswählen

Wenn Sie ermittelt haben, zu welchem Cloud-Speicher-Ziel Sie den Ausgabedatensatz exportieren möchten, [Ziel auswählen](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html#select-destination). Wenn Sie noch kein Ziel für Ihren bevorzugten Cloud-Speicher konfiguriert haben, müssen Sie [Erstellen einer neuen Zielverbindung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/connect-destination.html?lang=de).

Im Rahmen der Konfiguration eines Ziels können Sie den Dateityp (JSON oder Parquet) definieren, ob die resultierende Datei komprimiert werden soll oder nicht und ob eine Manifestdatei enthalten sein soll oder nicht.


#### Datensatz auswählen

Wenn Sie das Ziel ausgewählt haben, klicken Sie im nächsten **[!UICONTROL Auswählen von Datensätzen]** Schritt müssen Sie Ihren Ausgabedatensatz aus der Liste der Datensätze auswählen. Wenn Sie mehrere geplante Abfragen erstellen und möchten, dass die Ausgabedatensätze an dasselbe Cloud-Speicher-Ziel gesendet werden, können Sie die entsprechenden Ausgabedatensätze auswählen. Siehe [Auswählen Ihrer Datensätze](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html#select-datasets) für weitere Informationen.

#### Planen des Datensatzexports

Schließlich möchten Sie Ihren Datensatzexport als Teil der **[!UICONTROL Planung]** Schritt. In diesem Schritt können Sie den Zeitplan definieren und festlegen, ob der Export des Ausgabedatensatzes inkrementell erfolgen soll oder nicht. Siehe [Datensatz-Export planen](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html#scheduling) für weitere Informationen.


#### Abgeschlossene Schritte

[Überprüfen](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html#review) Ihre Auswahl und wenn Sie den Export Ihres Ausgabedatasets in das Cloud-Speicher-Ziel ordnungsgemäß starten.

Sie müssen [verify](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=de#verify) einen erfolgreichen Datenexport. Beim Exportieren von Datensätzen erstellt Experience Platform eine oder mehrere `.json` oder `.parquet` -Dateien am Speicherort, der in Ihrem Ziel definiert ist. Erwarten Sie, dass neue Dateien entsprechend dem von Ihnen eingerichteten Exportplan an Ihrem Speicherort abgelegt werden. Experience Platform erstellt eine Ordnerstruktur am Speicherort, den Sie als Teil des ausgewählten Ziels angegeben haben, wo die exportierten Dateien abgelegt werden. Für jeden Exportzeitpunkt wird ein neuer Ordner nach folgendem Muster erstellt: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Der standardmäßige Dateiname wird nach dem Zufallsprinzip generiert, was sicherstellt, dass die Namen von exportierten Dateien eindeutig sind.

### Flussdienst-API

Alternativ können Sie den Export von Ausgabedatensets mithilfe von APIs exportieren und planen. Die erforderlichen Schritte werden im Abschnitt [Exportieren von Datensätzen mithilfe der Flow Service-API](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html).

#### Erste Schritte

Um Datensätze zu exportieren, stellen Sie sicher, dass Sie über die [erforderliche Berechtigungen](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#permissions). Überprüfen Sie außerdem, ob das Ziel, an das Sie Ihren Ausgabedatensatz senden möchten, den Export von Datensätzen unterstützt. Sie müssen [Werte für erforderliche und optionale Kopfzeilen erfassen](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-values-headers) , die Sie in den API-Aufrufen verwenden. Sie müssen auch [Identifizieren der Verbindungsspezifikations- und Flussspezifikations-IDs des Ziels](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-connection-spec-flow-spec) Sie beabsichtigen, Datensätze in zu exportieren.

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

[Überprüfen](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=de#verify) einen erfolgreichen Datenexport. Beim Exportieren von Datensätzen erstellt Experience Platform eine oder mehrere `.json` oder `.parquet` -Dateien am Speicherort, der in Ihrem Ziel definiert ist. Erwarten Sie, dass neue Dateien entsprechend dem von Ihnen eingerichteten Exportplan an Ihrem Speicherort abgelegt werden. Experience Platform erstellt eine Ordnerstruktur am Speicherort, den Sie als Teil des ausgewählten Ziels angegeben haben, wo die exportierten Dateien abgelegt werden. Für jeden Exportzeitpunkt wird ein neuer Ordner nach folgendem Muster erstellt: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Der standardmäßige Dateiname wird nach dem Zufallsprinzip generiert, was sicherstellt, dass die Namen von exportierten Dateien eindeutig sind.

## Zusammenfassung

Kurz gesagt, das Emulieren der Adobe Analytics-Daten-Feed-Funktion erfordert die Einrichtung geplanter Abfragen mit Query Service und die Verwendung der Ergebnisse dieser Abfragen in geplanten Datensatzexporten.

>[!IMPORTANT]
>
>An diesem Anwendungsfall sind zwei Planer beteiligt. Um eine ordnungsgemäße Funktionsweise der emulierten Daten-Feed-Funktion zu gewährleisten, stellen Sie sicher, dass die in Query Service konfigurierten Zeitpläne und Datenexporte nicht stören.
