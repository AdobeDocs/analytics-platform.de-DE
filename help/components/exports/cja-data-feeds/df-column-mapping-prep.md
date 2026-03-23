---
description: Erfahren Sie, wie Sie die Zuordnung von Daten-Feed-Spalten von Adobe Analytics zu Customer Journey Analytics vorbereiten.
keywords: Clickstream;Daten-Feed;Daten-Feed;Data Feed
title: Vorbereiten der Zuordnung von Daten-Feed-Spalten von Adobe Analytics zu Customer Journey Analytics
feature: Components
hide: true
hidefromtoc: true
source-git-commit: 5dada1744a479cd4736c9fb7f3c807471e8da226
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 2%

---

# Vorbereiten der Zuordnung von Daten-Feed-Spalten von Adobe Analytics zu Customer Journey Analytics

Bei der Umstellung von Adobe Analytics-Daten-Feeds auf Customer Journey Analytics-Daten-Feeds ist es normal, jede Adobe Analytics-Daten-Feed-Spalte einer Daten-Feed-Spalte in Customer Journey Analytics zuzuordnen.

Bei der Zuordnung von Daten-Feed-Spalten von Adobe Analytics zu Customer Journey Analytics handelt es sich jedoch selten um eine Eins-zu-eins-Zuordnung. Dies ist auf die folgenden Faktoren zurückzuführen:

* **[Schemaarchitektur](#schema-architecture)**: Adobe Analytics-Daten-Feed-Spalten werden von Analytics-Variablen abgeleitet, während Customer Journey Analytics-Daten-Feed-Spalten von XDM-Schemafeldern in Experience Platform und Datenansichtskomponenten in Customer Journey Analytics abgeleitet werden.

* **[Implementierungstyp](#implementation-type)**: Adobe Analytics und Customer Journey Analytics unterstützen jeweils mehrere Implementierungskonfigurationen. Die Schritte, die zum Zuordnen einzelner Felder erforderlich sind, hängen von diesen Implementierungen ab.

* **[Datenverarbeitung](#data-processing)**: Zwischen Adobe Analytics und Customer Journey Analytics bestehen grundlegende Unterschiede bei der Datenverarbeitung.

* **[Nicht verwendete Spalten](#unused-columns)**: Adobe Analytics enthält mehr als 1.100 Daten-Feed-Spalten. Ermitteln Sie, welche dieser Spalten Ihr Unternehmen verwendet, damit Sie nur die erforderlichen Spalten zuordnen können.

Bevor Sie mit der Zuordnung von Daten-Feed-Spalten in Adobe Analytics zu Daten-Feed-Spalten in Customer Journey Analytics beginnen, lesen Sie die folgenden Abschnitte, um diese Schlüsselfaktoren, die die Zuordnung beeinflussen, besser zu verstehen.

Nachdem Sie diese Informationen geprüft haben, befolgen Sie die Zuordnungsanweisungen für jede Adobe Analytics-Daten-Feed-Spalte, die Sie in Customer Journey Analytics beibehalten möchten, wie in [Datenspaltenreferenz](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md) beschrieben.

## Schemaarchitektur

Das Experience-Datenmodell (XDM)-Schema ist zusammen mit den in Customer Journey Analytics verwendeten Datenansichten flexibler als das Adobe Analytics-Variablenmodell. Daher enthält das XDM-Schema Ihrer Organisation wahrscheinlich keine Felder, die in Eins-zu-eins-Daten-Feed-Spaltenzuordnungen übersetzt werden können.

Beachten Sie die folgenden Punkte zur Schemaarchitektur:

* Das Fehlen von Eins-zu-eins-Spaltenzuordnungen bedeutet nicht, dass Ihr Customer Journey Analytics-XDM-Schema unzureichend ist. Stattdessen müssen Sie zunächst ermitteln, welche Adobe Analytics-Daten-Feed-Spalten Sie derzeit verwenden, und dann nur diese Spalten Customer Journey Analytics-Daten-Feeds zuordnen.

* Das Customer Journey Analytics-XDM-Schema unterstützt kanalübergreifende Daten (z. B. Callcenter-Daten), die in Adobe Analytics nicht verfügbar sind. Diese kanalübergreifenden Felder sind Beispiele für neue Spalten, die in Customer Journey Analytics-Daten-Feeds enthalten sein können, die in Adobe Analytics nicht unterstützt werden.

* Felder können erst in einen Customer Journey Analytics-Daten-Feed aufgenommen werden, nachdem sie in Experience Platform in das XDM-Schema aufgenommen und dann für die Verwendung in der Datenansicht in Customer Journey Analytics kuratiert wurden.

  Detaillierte Informationen zu diesem Prozess für jede potenzielle Adobe Analytics-Daten-Feed-Spalte finden Sie [Datenspaltenreferenz](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

>[!TIP]
>
>Wenden Sie sich nach Möglichkeit an das Team oder die Einzelperson, die das XDM-Schema für die Customer Journey Analytics-Implementierung Ihres Unternehmens entwickelt hat. Viele der Entscheidungen darüber, welche Adobe Analytics-Felder in Customer Journey Analytics benötigt werden, wurden bei der Erstellung des XDM-Schemas getroffen. Weitere Informationen finden Sie unter [Planen Ihres Schemas zur Verwendung mit Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

## Implementierungstyp

<!--  tons of different AA implementations + tons of different CJA schemas -->

Die Anzahl der Felder, die Ihrem Customer Journey Analytics-XDM-Schema zugeordnet werden können, kann je nachdem, wie Daten für Ihre Customer Journey Analytics-Implementierung erfasst werden, unterschiedlich sein:

* **Neue Web SDK-Implementierungen**: Wenn Ihre Customer Journey Analytics-Implementierung ein benutzerdefiniertes Schema verwendet, sind viele Spalten, die in Adobe Analytics-Daten-Feeds vorhanden sind, wahrscheinlich nicht in Customer Journey Analytics vorhanden. Ebenso kann Customer Journey Analytics Felder enthalten, die nicht in Adobe Analytics-Daten-Feeds vorhanden sind.

* **Analytics Source Connector-Implementierungen**: Standardmäßig sind für viele Daten-Feed-Spalten Eins-zu-eins-Feldzuordnungen vorhanden, da der Analytics Source Connector die Analytics Experience Event -Feldergruppe im XDM-Schema verwendet. Informationen dazu, welche Adobe Analytics-Felder den Feldern in dieser Feldergruppe zugeordnet sind, finden Sie unter [Analytics-](https://experienceleague.adobe.com/de/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics)) in der Experience Platform-Dokumentation.

<!-- **Data layer**: ??? -->

## Datenverarbeitung

Die Datenverarbeitung unterscheidet sich zwischen Adobe Analytics und Customer Journey Analytics wie folgt:

**Adobe Analytics**: Viele Daten-Feed-Felder werden als zwei separate Spalten exportiert: eine mit vorverarbeiteten Daten und eine andere mit nachverarbeiteten Daten. (Nachverarbeitete Daten umfassen Server-seitige Logik, Verarbeitungsregeln, VISTA-Regeln, Regeln für die Dimensionspersistenz usw.)

Da Adobe Analytics Daten für einige Felder in zwei separaten Spalten exportiert (eine für vorverarbeitete Daten und eine für nachverarbeitete Daten), enthält Adobe Analytics mehr Daten-Feed-Spalten als Customer Journey Analytics. Beachten Sie dies beim Zuordnen von Feldern.

**Customer Journey Analytics**: Felder sind für Daten-Feeds verfügbar, nachdem sie in der Datenansicht erstellt wurden. Normalerweise enthalten Felder in Customer Journey Analytics-Datenansichten nur nachverarbeitete Daten. Sie können jedoch für gewöhnlich einen Näherungswert für die vorverarbeitete Adobe Analytics-Version eines Felds erhalten, indem Sie in der Customer Journey Analytics-Datenansicht eine zweite Version des Felds erstellen und so konfigurieren, dass es bei einem Treffer abläuft.

## Nicht verwendete Spalten

In Adobe Analytics stehen über 1.100 Daten-Feed-Spalten für den Export zur Verfügung. Von diesen Spalten werden nicht alle in Ihren Customer Journey Analytics-Daten-Feeds verwendet.

So bestimmen Sie, welche Spalten verwendet werden sollen:

* **Felder identifizieren, die nur für Adobe Analytics gelten**: Bestimmte Spalten in Adobe Analytics-Daten-Feeds sind spezifisch für die Datenverarbeitungs-Engine für Adobe Analytics und gelten daher nicht für Customer Journey Analytics. Beispiele für solche Spalten sind `exclude_hit` und `hit_source`.

* **Identifizieren Sie Felder, die für Ihr Unternehmen gelten**: Obwohl nicht alle Adobe Analytics-Kunden alle verfügbaren Spalten exportieren, exportieren viele Kunden mehr als sie tatsächlich verwenden.

  Bevor Sie mit der Zuordnung von Daten-Feed-Spalten beginnen, identifizieren Sie, welche Felder in Ihrer gesamten Organisation tatsächlich verwendet werden. Um diese Informationen zu erfassen, wenden Sie sich an die Teams oder Einzelpersonen, die Daten-Feed-Inhalte für Adobe Analytics verwenden.



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
