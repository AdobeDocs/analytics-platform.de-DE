---
title: Customer Journey Analytics-Leitplanken
description: Informationen zu den Schutzmechanismen für Customer Journey Analytics
solution: Customer Journey Analytics
feature: Administration
role: Admin
exl-id: f093ac54-7d31-449b-a441-a65856a1d535
source-git-commit: 2dd215b0fe689c9370e9f5867fd1bd5fdee83d42
workflow-type: tm+mt
source-wordcount: '1760'
ht-degree: 10%

---

# Customer Journey Analytics-Leitplanken

Dieses Dokument enthält Grenzwerte für verschiedene Komponenten von Customer Journey Analytics. Informationen zu Leitplanken, Bereichsparametern und Berechtigungen finden Sie unter [Produktbeschreibung für Customer Journey Analytics](https://helpx.adobe.com/de/legal/product-descriptions/customer-journey-analytics.html) oder [Produktbeschreibung für Adobe Analytics-Add-on: Customer Journey Analytics](https://helpx.adobe.com/de/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html).

## Arten von Beschränkungen

In diesem Dokument gibt es zwei Arten von Standardbeschränkungen:

| Art der Leitplanke | Beschreibung |
|----------|---------|
| **Leistungs-Leitplanken (weiches Limit)** | Leistungs-Leitplanken sind Nutzungsbeschränkungen, die sich auf den Umfang Ihrer Anwendungsfälle beziehen. Beim Überschreiten der Leistungsleitplanken kann es zu Leistungseinbußen und Latenzzeiten kommen. Adobe ist nicht für eine solche Leistungsbeeinträchtigung verantwortlich. Kunden, die eine Leistungsschutzmaßnahme durchgängig überschreiten, können sich dafür entscheiden, zusätzliche Kapazität zu lizenzieren, um eine Leistungsbeeinträchtigung zu vermeiden. |
| **Vom System erzwungene Leitplanken (feste Grenze)** | Systemerzwungene Leitplanken werden von der Customer Journey Analytics-Benutzeroberfläche oder der API erzwungen. Dies sind Beschränkungen, die Sie nicht überschreiten können, da die Benutzeroberfläche und die API Sie daran hindern oder einen Fehler zurückgeben. |

{style="table-layout:auto"}

Einige der Funktionen und ihr Wert für das Limit hängen vom Customer Journey Analytics-Paket ab, zu dem Sie berechtigt sind.

>[!NOTE]
>
>Die in diesem Dokument beschriebenen Werte können sich aufgrund kontinuierlicher Verbesserungen am Produkt ändern. Suchen Sie regelmäßig nach Updates. Wenn Sie mehr über benutzerdefinierte Limits erfahren möchten, wenden Sie sich an Ihren Kundenbetreuer.

## Ad-hoc-SQL-Abfragen

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Maximale Wartezeit erneut versuchen | 90 | Vom System erzwungene Leitplanke | Die maximale Anzahl von Sekunden, bevor die Reporting-Engine antwortet, dass die Anfrage zu lange dauert, bis Ergebnisse zurückgegeben werden (möglicherweise aufgrund anderer gleichzeitiger anderer Anfragen). Es ist möglich, erneut eine Anfrage auszuführen. |
| Zeitüberschreitung nicht erneut versuchen | 600 | Vom System erzwungene Leitplanke | Maximale Anzahl von Sekunden bis zum Timeout von Ad-hoc-SQL-Abfragen. Andernfalls gibt die maximale Anzahl von Sekunden vor der Berichterstellungs-Engine an, dass es zu lange gedauert hat, bis die Anfrage Ergebnisse zurückgibt. Daher sollte dies nicht erneut versucht werden. Die Anfrage gibt höchstwahrscheinlich nie Ergebnisse aufgrund von Problemen im Hintergrundprozess zurück. |
| Metriken | 150 | Vom System erzwungene Leitplanke | Maximale Anzahl von Metriken in einer Anfrage. |
| Interaktive Abfrageausgabezeilen | 50.000 | Vom System erzwungene Leitplanke | Standardanzahl der zurückgegebenen Zeilen, sofern nicht anders angegeben. |

{style="table-layout:auto"}

## Analysis Workspace-Projekte

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Sichtbare Zeilen pro Tabelle | 400 | Vom System erzwungene Leitplanke | Maximale Anzahl sichtbarer Zeilen in einer beliebigen Freiformtabelle in einem Analysis Workspace-Projekt. |
| Exportierbare Zeilen pro Tabelle | 50.000 | Vom System erzwungene Leitplanke | Maximale Anzahl von Zeilen, die pro Dimension exportiert werden können. |
| Bedienfelder pro Projekt | 15 | Vom System erzwungene Leitplanke | Maximale Anzahl von [Bedienfeldern](../analysis-workspace/home.md#panels) pro Projekt. |
| Visualisierungen pro Bedienfeld | 25 | Vom System erzwungene Leitplanke | Maximale Anzahl von [Visualisierungen](../analysis-workspace/home.md#visualizations) pro Bedienfeld. |
| Abgeleitete Felder pro Freiformtabelle | 5 | Vom System erzwungene Leitplanke | Maximale Anzahl verschiedener abgeleiteter Felder in einer einzelnen Freiformtabelle. |

{style="table-layout:auto"}

<!--
## Attribution AI

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Attribution AI models | 35 | Maximum number of Attribution AI Model per year to analyze the impact of up to an average of 60 independent touchpoints on a specified conversion event.  | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Region based iterations | 10 | Maximum number of region-based iterations of each Attribution AI model. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Export Insights batches | 12 | Maximum number of export batches times the number of authorized Attribution AI Insights per year. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 

{style="table-layout:auto"}
-->

## Zielgruppen

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Zielgruppenfilter | 20 | Vom System erzwungene Leitplanke | Maximale Anzahl von [Filtern](../components/filters/filters-overview.md) pro Zielgruppe |
| Anzahl der Zielgruppenidentitäten | 20 Million | Vom System erzwungene Leitplanke | Maximale Anzahl von Identitäten pro Zielgruppe. |
| Häufigkeit der Zielgruppenaktualisierung | 4 | Vom System erzwungene Leitplanke | Die maximale Häufigkeit in Stunden, in [ eine ](../components/audiences/audiences-overview.md) aktualisiert werden kann. |
| Lookback-Fenster zur Zielgruppenaktualisierung | 90 | Vom System erzwungene Leitplanke | Maximale Anzahl von Tagen für das Aktualisierungs-Lookback-Fenster |
| Ablaufdatum der Zielgruppe aktualisieren | 13 | Vom System erzwungene Leitplanke | Die maximale Anzahl von Monaten, die die Zielgruppe ab dem Erstellungsdatum nicht mehr aktualisiert wird. Kunden können dies um weitere 13 Monate verlängern. |
| Anzahl der aktualisierten Zielgruppen | 75 150 | Vom System erzwungene Leitplanke | Maximale Anzahl an Zielgruppen, die aktualisiert werden. Der Wert variiert je nach Customer Journey Analytics-Paket (siehe Produktbeschreibung). |

{style="table-layout:auto"}

Siehe auch Experience Platform von [Real-time Customer Data Platform-Schutzmechanismen](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html?lang=de).


## Automatisierte Datensatzgültigkeit

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|:---:|
| Arbeitsaufträge | 20 | Vom System erzwungene Leitplanke | Maximale Anzahl an automatisierten Arbeitsaufträgen zur Datensatzgültigkeit pro Monat. |

{style="table-layout:auto"}



## Verbindungen, Datenansichten, Projekte

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Projekte | 50.000 | Vom System erzwungene Leitplanke | Maximale Anzahl von Projekten für eine Organisation. |
| Datenansichten | 2.000 | Vom System erzwungene Leitplanke | Maximale Anzahl [Datenansichten](../data-views/data-views.md) für eine Organisation. |
| Datenansichten | 500-1000 | Vom System erzwungene Leitplanke | Maximale Anzahl von Datenansichten für eine Verbindung. Der Wert variiert je nach Customer Journey Analytics-Paket (siehe Produktbeschreibung). |
| Datensätze | 100 | Vom System erzwungene Leitplanke | Maximale Anzahl [Datensätze](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=de) pro Verbindung |
| Verbindungen | 1000 | Vom System erzwungene Leitplanke | Maximale Anzahl von [Verbindungen](../connections/overview.md) für eine Organisation. |
| Connection Title | 500 | Vom System erzwungene Leitplanke | Maximale Zeichenanzahl für einen Verbindungstitel. |
| Metriken | 5.000 | Vom System erzwungene Leitplanke | Maximale Anzahl von Metriken in einer Datenansicht. |
| Dimensionen | 5.000 | Vom System erzwungene Leitplanke | Maximale Anzahl von Dimensionen in einer Datenansicht. |
| Titel der Anmerkung | 100 | Vom System erzwungene Leitplanke | Maximale Zeichenanzahl für einen Anmerkungstitel. |
| Beschreibung der Anmerkung | 250 | Vom System erzwungene Leitplanke | Maximale Zeichenanzahl für eine Anmerkungsbeschreibung |
| Schemafelder | 10 | Vom System erzwungene Leitplanke | Maximale Anzahl von Schemafeldern (ohne Standardfelder) beim Definieren von Regeln für ein ([ Feld](../data-views/derived-fields/derived-fields.md). |
| Lookup-/Profilfelder | 3 | Vom System erzwungene Leitplanke | Maximale Anzahl von Lookup- oder Profilschemafeldern innerhalb der maximalen Anzahl von Schemafeldern (ohne Standardfelder) beim Definieren von Regeln für ein abgeleitetes Feld. |
| Abgeleitete Felder | 100 - 500 | Vom System erzwungene Leitplanke | Maximale Anzahl abgeleiteter Felder pro Verbindung Der Wert variiert je nach Customer Journey Analytics-Paket (siehe Produktbeschreibung). |

{style="table-layout:auto"}


## Grenzwerte für die Datenübertragung

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Felder | 10.000 | Vom System erzwungene Leitplanke | Maximale Anzahl von Eigenschaften oder Feldern pro Zeile in einem Datensatz. |
| Eindeutige Zeichenfolgen | 10 Million | Vom System erzwungene Leitplanke | Maximale Anzahl eindeutiger Schlüssel pro Lookup-Datensatz. |
| Zeilen | 1 Million | Vom System erzwungene Leitplanke | Maximale Anzahl von Zeilen pro eindeutiger Personen-ID in einem bestimmten Monat innerhalb einer Verbindung. |
| Zeilengröße | 2 | Leistungs-Schutzmaßnahme/Vom System erzwungene Schutzmaßnahme | Durchschnittliche Größe in Kilobyte pro Datenzeile, die in Customer Journey Analytics aufgenommen wird (weiche Grenze). Eine statische Begrenzung für die Zeilengröße wird durch Leitplanken für die Datenaufnahme im Experience Platform bestimmt. |

{style="table-layout:auto"}

Siehe auch Experience Platform [Schutzmaßnahmen bei der Datenaufnahme](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html).


## Zieldatenexport

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Datenexport | Insgesamt autorisierter Data-Lake-Speicher | Leistungs-Schutzmaßnahme | Der Kunde kann den Export von Zieldatensätzen verwenden, um Kundendaten im Data Lake bis zur insgesamt autorisierten Data Lake-Datenspeicherung zu exportieren. |
| Verfügbare Datensätze | Profil und Ereignis | Erzwungene Schutzmaßnahme des Systems | Ereignis-, Profil- oder Lookup-Datensätze, die in der Experience Platform-Benutzeroberfläche nach der Aufnahme oder Erfassung von Daten über Quellen, Web SDK, Mobile SDK, Analytics Data Connector und Audience Manager erstellt wurden. |

{style="table-layout:auto"}

Siehe auch Experience Platform [Leitplanken für den Datensatzexport](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/guardrails#dataset-exports)


## Data Landing Zone

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Data Landing Zone pro Sandbox | 1 | Vom System erzwungene Leitplanke | Maximale Anzahl von Data Landing Zones pro Sandbox. |
| Datenspeicherung | 7 | Vom System erzwungene Leitplanke | Maximale Anzahl von Tagen, an denen Daten in der Data Landing Zone gespeichert werden, bevor sie gelöscht werden. |

{style="table-layout:auto"}


## Feldbasiertes Stitching

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Zusammengefügte Datensätze | 5-50 | Vom System erzwungene Leitplanke | Maximale Anzahl an zugeordneten Datensätzen pro Kunde. Der Wert variiert je nach Customer Journey Analytics-Paket (siehe Produktbeschreibung). |
| Aufstockungslänge | 6-25 | Vom System erzwungene Leitplanke | Maximale Anzahl von Monaten für die Aufstockung von Daten. Der Wert variiert je nach Customer Journey Analytics-Paket (siehe Produktbeschreibung). |
| Lookback-Fenster/Wiederholungshäufigkeit | 1/1 - 30/7 | Vom System erzwungene Leitplanke | Maximales Lookback-Fenster in Tagen/Wiederholungshäufigkeit. Der Wert variiert je nach Customer Journey Analytics-Paket (siehe Produktbeschreibung). |

{style="table-layout:auto"}


## Grafikbasierte Zuordnung

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Zusammengefügte Datensätze | 10 - 50 | Vom System erzwungene Leitplanke | Maximale Anzahl an zugeordneten Datensätzen pro Kunde. Der Wert variiert je nach Customer Journey Analytics-Paket (siehe Produktbeschreibung). |
| Aufstockungslänge | 13 - 25 | Vom System erzwungene Leitplanke | Maximale Anzahl von Monaten für die Aufstockung von Daten. Der Wert variiert je nach Customer Journey Analytics-Paket (siehe Produktbeschreibung). |
| Lookback-Fenster/Wiederholungshäufigkeit | 1/1 - 30/7 | Vom System erzwungene Leitplanke | Maximales Lookback-Fenster in Tagen/Wiederholungshäufigkeit. Der Wert variiert je nach Customer Journey Analytics-Paket (siehe Produktbeschreibung). |


## Filter und berechnete Metriken

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Container pro Filter | 50 | Vom System erzwungene Leitplanke | Maximale Anzahl an Containern pro Filter. |
| Metriken pro berechneter Metrik | 25 | Vom System erzwungene Leitplanke | Maximale Anzahl von Metriken pro berechneter Metrik. |
| Metriken und Dimensionen pro Filter | 25 | Vom System erzwungene Leitplanke | Maximale Anzahl eindeutiger Metriken und Dimensionen pro Filter. |
| Verschachtelte Container pro Filter | 10 | Vom System erzwungene Leitplanke | Maximale Anzahl verschachtelter Container pro Filter. |
| Regeln pro Filter | 100 | Vom System erzwungene Leitplanke | Maximale Anzahl von Regeln pro Filter. |
| Zeichenfolgenvergleiche pro Dimension und Filter | 100 | Vom System erzwungene Leitplanke | Maximale Anzahl von Zeichenfolgenvergleichen pro Dimension pro Filter. |
| Berechnete Metriken | 6.000 | Vom System erzwungene Leitplanke | Maximale Anzahl berechneter Metriken für eine Organisation. |
| Filter | 50.000 | Vom System erzwungene Leitplanke | Maximale Anzahl von Filtern, die Sie für eine Organisation definieren können. |
| API-Aufrufe | 120 | Vom System erzwungene Leitplanke | API-Anfragen pro Minute (12 Anfragen alle 6 Sekunden). |

{style="table-layout:auto"}


## Mobile App

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Kacheln | 16 | Vom System erzwungene Leitplanke | Maximale Anzahl an Kacheln pro Scorecard |
| Filter | 10 | Vom System erzwungene Leitplanke | Maximale Anzahl an Filtern pro Scorecard. |
| Dimensionen | 10 | Vom System erzwungene Leitplanke | Maximale Anzahl von Dimensionen pro Scorecard. |

{style="table-layout:auto"}

## Report Builder

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Größe der Arbeitsmappen-Datei | 5 | Vom System erzwungene Leitplanke | Maximale Dateigröße in MB einer geplanten Arbeitsmappe. |
| Datenblöcke | 1000 | Vom System erzwungene Leitplanke | Maximale Anzahl von [Datenblöcken](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=de) pro Arbeitsmappe. |
| Metriken | 20 | Vom System erzwungene Leitplanke | Maximale Anzahl von Metriken pro Datenblock. |
| Datumsbereich | 13 | Vom System erzwungene Leitplanke | Maximale Anzahl von Monaten, die ein Datumsbereich pro Datenblock umfassen kann. |
| Zeilen | 50.000 | Vom System erzwungene Leitplanke | Maximale Zeilenanzahl pro Datenblock. |

{style="table-layout:auto"}


## Vollständiger Tabellenexport

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Zeilen pro Bericht | 3 Millionen - 300 Millionen | Vom System erzwungene Leitplanke | Maximale Anzahl an Berichtszeilen pro Bericht. Der Wert variiert je nach Customer Journey Analytics-Paket (siehe Produktbeschreibung). |
| Aufschlüsselungen nach Tabelle | 5 | Vom System erzwungene Leitplanke | Maximale Anzahl von Aufschlüsselungen pro Tabelle. |
| Metriken pro Tabelle | 5 | Vom System erzwungene Leitplanke | Maximale Anzahl von Metriken pro Tabelle. |
| Zeitplanfrequenz | 1 | Vom System erzwungene Leitplanke | Exporte können einmal (1) täglich oder nach einem längeren Zeitplan geplant werden (z. B. alle 2 Tage oder wöchentlich). |

{style="table-layout:auto"}

## Latenzen

>[!NOTE]
>
>Die folgenden Verarbeitungszeiten sind Leitplanken, keine vertraglichen Service Level Agreements (SLAs). Die Latenz variiert je nach Kundenkonfiguration, Datenvolumen und Kundenanwendungen. Häufig sind die tatsächlichen Verarbeitungszeiten schneller. Lesen Sie Ihren Customer Journey Analytics-Vertrag für Ihre spezifischen Vertragsbedingungen und SLAs. Experience Platform Weitere Informationen finden Sie unter [ (](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html) für die Datenaufnahme).

| Datenfluss | Erwartete Latenz |
|---|---|
| Adobe Analytics zu Adobe Analytics Source Connector (A4T-fähig) | &lt; 30 Minuten |
| Adobe Analytics Source Connector für Echtzeit-Kundenprofil (A4T nicht aktiviert) | &lt; 2 Minuten |
| Adobe Analytics Source Connector für Echtzeit-Kundenprofil (A4T aktiviert) | &lt; 30 Minuten |
| Datenaufnahme in den Data Lake aus der Edge Network- oder Streaming-Aufnahme | &lt; 60 Minuten |
| Datenaufnahme in den Data Lake vom Adobe Analytics Source-Connector | &lt; 2,25 Stunden |
| Datenaufnahme in Customer Journey Analytics aus dem Data Lake | &lt; 90 Minuten |
| Stitching (optionale Funktion; weitere Informationen [Stitching-Übersicht](../stitching/overview.md)) | 4 Stunden |
| Adobe Analytics Source Connector-Aufstockung von weniger als 10 Milliarden Ereignissen (maximal 13 Monate historischer Daten) | &lt; 4 Wochen |
| Zielgruppenveröffentlichung im Echtzeit-Kundenprofil, einschließlich der automatischen Erstellung des Streaming-Segments, sodass das Segment bereit für den Empfang der Daten ist. | ≈ 60 Minuten |
| Aktualisierungshäufigkeit für Zielgruppen | Einmalige Aktualisierung: Latenz von weniger als 5 Minuten.<br/>Aktualisierung alle 4 Stunden, täglich, wöchentlich, monatlich (die Latenz wird mit der Aktualisierungsrate in Verbindung gebracht). |

{style="table-layout:auto"}
