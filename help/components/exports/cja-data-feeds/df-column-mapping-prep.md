---
description: Erfahren Sie, wie Sie die Zuordnung von Daten-Feed-Spalten von Adobe Analytics zu Customer Journey Analytics vorbereiten.
keywords: Clickstream;Daten-Feed;Daten-Feed;Data Feed
title: Vorbereiten der Zuordnung von Daten-Feed-Spalten von Adobe Analytics zu Customer Journey Analytics
feature: Components
hide: true
exl-id: d0a9e697-1e48-4cfb-8613-2f932bf5015b
autotag-review: '2026-05-19T08:44:51.994Z'
TQID: 'https://experienceleague.adobe.com/0KbYVZ87QL4qh-5FfSRxpuEF4-xsqBTLwLCvKa-u9Mw'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 1092
ht-degree: 3%

---

# Vorbereiten der Zuordnung von Daten-Feed-Spalten von Adobe Analytics zu Customer Journey Analytics

Customer Journey Analytics bietet eine flexiblere Architektur als Adobe Analytics, um die Spalten zu bestimmen, die für die Aufnahme in einen Daten-Feed verfügbar sind. Die meisten Unternehmen sollten damit rechnen, andere Daten-Feed-Spalten aus Customer Journey Analytics zu exportieren als aus Adobe Analytics. Diese Unterschiede sind auf die folgenden Faktoren zurückzuführen:

* **[Architektur des Daten-Feed](#schema-architecture)**: Daten-Feed-Spalten von Adobe Analytics werden von Analytics-Variablen abgeleitet, während Daten-Feed-Spalten von Customer Journey Analytics von der Datenansichtskonfiguration abgeleitet werden.

* **[Datenverarbeitung](#data-processing)**: Zwischen Adobe Analytics und Customer Journey Analytics bestehen grundlegende Unterschiede bei der Datenverarbeitung, insbesondere das Vorhandensein sowohl vorab verarbeiteter als auch nachbearbeiteter Spalten für viele Adobe Analytics-Spalten.

* **[Nicht verwendete Spalten](#unused-columns)**: Adobe Analytics enthält mehr als 1.100 Daten-Feed-Spalten. Die meisten Unternehmen verwenden nicht die Daten aus allen Spalten, die exportiert werden.

* **[Kanalübergreifende Spalten](#cross-channel-columns)**: Customer Journey Analytics unterstützt kanalübergreifende Daten (z. B. Callcenter-Daten), die in Adobe Analytics nicht verfügbar sind.

Bevor Sie mit der Zuordnung von Daten-Feed-Spalten in Adobe Analytics zu Daten-Feed-Spalten in Customer Journey Analytics beginnen, lesen Sie die folgenden Abschnitte, um diese Schlüsselfaktoren, die die Zuordnung beeinflussen, besser zu verstehen.

Nachdem Sie diese Informationen geprüft haben, befolgen Sie die Zuordnungsanweisungen für jede Adobe Analytics-Daten-Feed-Spalte, die Sie in Customer Journey Analytics beibehalten möchten, wie in [Datenspaltenreferenz](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md) beschrieben.

## Architektur des Daten-Feed-Schemas

Customer Journey Analytics bietet eine flexiblere Architektur als Adobe Analytics, um zu bestimmen, welche Spalten in einen Daten-Feed aufgenommen werden können:

### Adobe Analytics-Architektur

Es steht eine vordefinierte statische Liste von Variablen zur Verfügung, die als Daten-Feed-Spalten einbezogen werden können.

Es ist einfach, alle Spalten einzubeziehen, und viele Kunden tun dies, auch wenn die in diesen Spalten enthaltenen Daten nicht im gesamten Unternehmen verwendet werden.

### Customer Journey Analytics-Architektur

Alle Komponenten, die in der Datenansichtskonfiguration enthalten sind, können als Daten-Feed-Spalten einbezogen werden. Detaillierte Informationen zu diesem Prozess für jede potenzielle Adobe Analytics-Daten-Feed-Spalte finden Sie [Datenspaltenreferenz](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

Komponenten werden auf eine der in der folgenden Tabelle beschriebenen Arten in die Datenansichtskonfiguration eingeschlossen:

| Methode zur Aufnahme in die Datenansichtskonfiguration | Zusätzliche Informationen |
|---------|----------|
| XDM-Schemafelder werden in der Datenansicht als Komponenten kuratiert | Felder, die in Ihrem XDM-Schema vorhanden sind, werden Teil der Datenansichtskonfiguration in Customer Journey Analytics, nachdem sie als Komponenten in der Datenansicht kuratiert wurden. <p>Die Anzahl der Felder, die standardmäßig in Ihrem Customer Journey Analytics-XDM-Schema verfügbar sind, kann je nachdem, wie Daten für Ihre Customer Journey Analytics-Implementierung erfasst werden, unterschiedlich sein:</p><ul><li>**Neue Web SDK-Implementierungen**: Wenn Ihre Customer Journey Analytics-Implementierung ein benutzerdefiniertes Schema verwendet, sind viele Spalten, die in Adobe Analytics-Daten-Feeds vorhanden sind, wahrscheinlich nicht in Customer Journey Analytics vorhanden. Ebenso kann Customer Journey Analytics Felder enthalten, die nicht in Adobe Analytics-Daten-Feeds vorhanden sind.<p>Wenden Sie sich nach Möglichkeit an das Team oder die Einzelperson, die das XDM-Schema für die Customer Journey Analytics-Implementierung Ihres Unternehmens entwickelt hat. Viele der Entscheidungen darüber, welche Adobe Analytics-Felder in Customer Journey Analytics benötigt werden, wurden bei der Erstellung des XDM-Schemas getroffen. Weitere Informationen finden Sie unter [Planen Ihres Schemas zur Verwendung mit Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).</p></li><li>**Analytics Source Connector-Implementierungen**: Standardmäßig sind für viele Daten-Feed-Spalten Eins-zu-eins-Feldzuordnungen vorhanden, da der Analytics Source Connector die Analytics Experience Event -Feldergruppe im XDM-Schema verwendet. Informationen dazu, welche Adobe Analytics-Felder den Feldern in dieser Feldergruppe zugeordnet sind, finden Sie unter [Analytics-](https://experienceleague.adobe.com/de/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics)) in der Experience Platform-Dokumentation.</li></ul> |
| Komponenten werden innerhalb der Datenansicht mithilfe abgeleiteter Felder erstellt | Sie können Komponenten direkt in einer Datenansicht erstellen und so Daten-Feed-Spalten erstellen, die im XDM-Schema nicht verfügbar sind. |

## Datenverarbeitung

Unterschiede bei der Datenverarbeitung zwischen Adobe Analytics und Customer Journey Analytics beeinflussen, welche Daten-Feed-Spalten exportiert werden können:

* **Adobe Analytics**: Viele Daten-Feed-Felder werden als zwei separate Spalten exportiert: eine mit vorverarbeiteten Daten und eine andere mit nachverarbeiteten Daten. (Nachverarbeitete Daten umfassen Server-seitige Logik, Verarbeitungsregeln, VISTA-Regeln, Regeln für die Dimensionspersistenz usw.)

  Da Adobe Analytics Daten für einige Felder in zwei separaten Spalten exportiert (eine für vorverarbeitete Daten und eine für nachverarbeitete Daten), enthält Adobe Analytics mehr Daten-Feed-Spalten als Customer Journey Analytics. Beachten Sie dies beim Zuordnen von Feldern.

* **Customer Journey Analytics**: Felder sind für Daten-Feeds verfügbar, nachdem sie in der Datenansicht erstellt wurden. Normalerweise enthalten Felder in Customer Journey Analytics-Datenansichten nur nachverarbeitete Daten. Sie können jedoch für gewöhnlich einen Näherungswert für die vorverarbeitete Adobe Analytics-Version eines Felds erhalten, indem Sie in der Customer Journey Analytics-Datenansicht eine zweite Version des Felds erstellen und so konfigurieren, dass es bei einem Treffer abläuft.

## Nicht verwendete Spalten

In Adobe Analytics stehen über 1.100 Daten-Feed-Spalten für den Export zur Verfügung. Von diesen Spalten werden nicht alle in Ihren Customer Journey Analytics-Daten-Feeds verwendet. Diese Diskrepanz ist kein Hinweis darauf, dass Ihre Customer Journey Analytics-Daten-Feed-Spalten unzureichend sind.

Ermitteln Sie, welche der Daten-Feed-Spalten von Adobe Analytics Ihr Unternehmen verwendet. Dadurch wird darüber informiert, welche Spalten in Ihren Customer Journey Analytics-Daten-Feeds benötigt werden. So bestimmen Sie, welche Spalten verwendet werden sollen:

* **Felder identifizieren, die nur für Adobe Analytics gelten**: Bestimmte Spalten in Adobe Analytics-Daten-Feeds sind spezifisch für die Datenverarbeitungs-Engine für Adobe Analytics und gelten daher nicht für Customer Journey Analytics. Beispiele für solche Spalten sind `exclude_hit` und `hit_source`.

* **Identifizieren Sie Felder, die für Ihr Unternehmen gelten**: Obwohl nicht alle Adobe Analytics-Kunden alle verfügbaren Spalten exportieren, exportieren viele Kunden mehr als sie tatsächlich verwenden.

  Bevor Sie mit dem Export von Daten-Feeds aus Customer Journey Analytics beginnen, sollten Sie zunächst ermitteln, welche Adobe Analytics-Daten-Feed-Spalten Ihr Unternehmen derzeit verwendet, und dann sicherstellen, dass diese Komponenten in Ihrer Customer Journey Analytics-Datenansichtskonfiguration vorhanden sind. Um diese Informationen zu erfassen, wenden Sie sich an die Teams oder Einzelpersonen in Ihrem Unternehmen, die Daten-Feed-Inhalte für Adobe Analytics verwenden.

## Kanalübergreifende Spalten

Customer Journey Analytics unterstützt kanalübergreifende Daten (z. B. Callcenter-Daten), die in Adobe Analytics nicht verfügbar sind. Diese kanalübergreifenden Felder sind Beispiele für neue Spalten, die in Customer Journey Analytics-Daten-Feeds enthalten sein können, welche in Adobe Analytics nicht unterstützt werden.

<!--

1. View the data views throughout your organization to make sure that corresponding dimensions are available. If a corresponding dimension does not exist in the data view, create it.

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view.

   

1. For each Adobe Analytics data feed field that is being used, ensure that a similar field exists in the XDM schema.

1. Verify that and that corresponding dimensions are available in the data view. If not, you need to create them. 

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 

## Map data feed columns from Adobe Analytics to Customer Journey Analytics

### Step 1 - Map the default columns included in Customer Journey Analytics

There are roughly 20 default fields included in all WebSDK implementations. 

Before you can map these default columns, make sure that your Customer Journey Analytics environment meets the following prerequisites:

* It uses a WebSDK implementation.

* The appropriate field groups that contain the default WebSDK fields are added to your XDM schema.If the field is not added to your schema, it is included in the payload, but ultimately dropped.

* Each default field must be curated as a component in a Customer Journey Analytics data view.

* The component settings in the data view must be equivalent to how Analytics treats it (Visit persistence or hit-level persistence).

To map the default dimensions:

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that are included by default

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

### Step 2: Discover which additional data feed columns your consumers use

There are over 1,100 data feed columns available to be exported in Adobe Analytics. While not all Adobe Analytics customers export all of the available columns, many customers export more than they actually use. 

Before you begin mapping data feed columns, you should first:

1. Contact the teams or individuals who consume data feed content and determine which data feed columns they use.

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 


### Step 3 - Map each additional column

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that could be mapped if they are included in your schema and data views

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

Notes below here. Ignore:

Do we group these columns by if you're using the WebSDK, or if you're using specific field groups.

Here's what is in Analytics, and here's what it maps to in CJA. Customers want us to "give them the mappings."

Some of these fields there is probably something like it that you could get in WebSDK. There will be some fields that aren't. Or some that are in AEP that aren't in here (like call center data).

We have an XDM field mappings to Analytics variables. "Adobe analytics XDM Var - first hit on Google." If you set your XDM payload to the given field on the left, it will automatically be associated to the Analytics variable on the right. But we're looking for a reverse mapping of this. 









If you're using ADC, you'll have the AA column name in there. We also have an ADC mapping doc page. (Analytics field mappings doc page maps the fields)



Make a table (or a section) that talks about fields that are new to CJA, like cross-channel fields (call center, etc.) 

The number of AA columns that they can map is not going to be that big (maybe 100). The number of columns that don't map will be huge.

## Data feed column reference

### Adobe Analytics data feed columns that are included by default in Customer Journey Analytics WebSDK implementations

### Adobe Analytics data feed columns that can be included in Customer Journey Analytics data feed

### Adobe Analytics data feed columns that don't apply to Customer Journey Analytics


### Columns, descriptions, and data types

Use this section to learn what data is contained in each column. Most implementations don't use every column, so this section can be referenced when determining which columns to include in a data feed export.

-->
