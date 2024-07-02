---
title: Customer Journey Analytics Guardrails
description: Erfahren Sie mehr über die Limits für Customer Journey Analytics
solution: Customer Journey Analytics
feature: Administration
role: Admin
exl-id: f093ac54-7d31-449b-a441-a65856a1d535
source-git-commit: a0124ee6c4534cbaf607367ee3ae79f1cbfc239c
workflow-type: tm+mt
source-wordcount: '1747'
ht-degree: 10%

---

# Customer Journey Analytics Guardrails

Dieses Dokument bietet Einschränkungen für verschiedene Komponenten von Customer Journey Analytics. Informationen zu Limits, Scoping-Parametern und Berechtigungen finden Sie in der [Produktbeschreibung für Customer Journey Analytics](https://helpx.adobe.com/de/legal/product-descriptions/customer-journey-analytics.html) oder [Produktbeschreibung für Adobe Analytics Add-on: Customer Journey Analytics](https://helpx.adobe.com/de/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html).

## Arten von Beschränkungen

In diesem Dokument gibt es zwei Arten von Standardbeschränkungen:

| Schutztyp | Beschreibung |
|----------|---------|
| **Leistungsgarantien (weiche Begrenzung)** | Performance-Limits sind Nutzungsbeschränkungen, die sich auf das Scoping Ihrer Anwendungsfälle beziehen. Bei Überschreitung der Leistungs-Limits kann es zu Leistungsbeeinträchtigungen und Latenzzeiten kommen. Adobe ist nicht für eine solche Leistungsbeeinträchtigung verantwortlich. Kunden, die eine Performance-Limits durchgängig überschreiten, können zusätzliche Kapazität lizenzieren, um Leistungsbeeinträchtigungen zu vermeiden. |
| **Systemerzwungene Limits (harte Grenze)** | Systemerzwungene Schutzmechanismen werden durch die Customer Journey Analytics-Benutzeroberfläche oder -API erzwungen. Dies sind Beschränkungen, die Sie nicht überschreiten können, da die Benutzeroberfläche und API Sie daran hindert, dies zu tun oder einen Fehler zurückzugeben. |

{style="table-layout:auto"}

Einige der Funktionen und der zugehörige Wert für die Beschränkung hängen vom Customer Journey Analytics-Package ab, für das Sie berechtigt sind.

>[!NOTE]
>
>Die in diesem Dokument beschriebenen Werte können sich aufgrund kontinuierlicher Verbesserungen des Produkts ändern. Suchen Sie regelmäßig nach Updates. Wenden Sie sich an Ihren Kundenbetreuer, wenn Sie mehr über benutzerdefinierte Beschränkungen erfahren möchten.

## Ad-hoc-SQL-Abfragen

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Wiederholtes Timeout versuchen | 90 | Systemdurchsetztes Schutzschild | Maximale Anzahl von Sekunden, bevor die Reporting-Engine zurückgibt, dass die Anfrage zu lange dauert, bis Ergebnisse zurückgegeben werden (möglicherweise aufgrund anderer gleichzeitiger Anfragen). Eine erneute Anforderung ist möglich. |
| Nicht erneut versuchen - Zeitüberschreitung | 600 | Systemdurchsetztes Schutzschild | Maximale Anzahl von Sekunden vor Zeitüberschreitung bei Ad Hoc SQL-Abfragen. Andernfalls wird angegeben, dass die maximale Anzahl von Sekunden, bevor Reporting-Engines melden, zurückgibt, dass die Anfrage zu lange gedauert hat, um Ergebnisse zurückzugeben, und nicht erneut versucht werden sollte. Die Anfrage liefert höchstwahrscheinlich nie Ergebnisse aufgrund von Problemen im Hintergrund-Prozess. |
| Metriken | 150 | Systemdurchsetztes Schutzschild | Maximale Anzahl an Metriken in einer Anforderung. |
| Ausgabezeilen interaktiver Abfragen | 50.000 | Systemdurchsetztes Schutzschild | Standardanzahl der zurückgegebenen Zeilen, sofern nicht anders angegeben. |

{style="table-layout:auto"}

## Analysis Workspace-Projekte

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Sichtbare Zeilen pro Tabelle | 400 | Systemdurchsetztes Schutzschild | Maximale Anzahl sichtbarer Zeilen in einer Freiformtabelle in einem Analysis Workspace-Projekt. |
| Exportierbare Zeilen pro Tabelle | 50.000 | Systemdurchsetztes Schutzschild | Maximale Anzahl von Zeilen, die pro Dimension exportiert werden können. |
| Bedienfelder pro Projekt | 15 | Systemdurchsetztes Schutzschild | Maximale Anzahl an [Bedienfelder](../analysis-workspace/home.md#panels) pro Projekt. |
| Visualisierungen pro Bedienfeld | 25 | Systemdurchsetztes Schutzschild | Maximale Anzahl an [Visualisierungen](../analysis-workspace/home.md#visualizations) pro Bedienfeld. |
| Abgeleitete Felder pro Freiformtabelle | 5 | Systemdurchsetztes Schutzschild | Maximale Anzahl verschiedener abgeleiteter Felder in einer einzelnen Freiformtabelle. |

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
| Zielgruppenfilter | 20 | Systemdurchsetztes Schutzschild | Maximale Anzahl an [Filter](../components/filters/filters-overview.md) pro Zielgruppe. |
| Anzahl der Zielgruppenidentitäten | 20 Million | Systemdurchsetztes Schutzschild | Maximale Anzahl von Identitäten pro Zielgruppe. |
| Häufigkeit der Zielgruppenaktualisierung | 4 | Systemdurchsetztes Schutzschild | Maximale Häufigkeit in Stunden und [audience](../components/audiences/audiences-overview.md) aktualisiert werden. |
| Lookback-Fenster für Zielgruppenaktualisierung | 90 | Systemdurchsetztes Schutzschild | Maximale Anzahl von Tagen für das Lookback-Fenster &quot;Aktualisieren&quot;. |
| Aktualisieren des Zielgruppenablaufdatums | 13 | Systemdurchsetztes Schutzschild | Die maximale Anzahl von Monaten für die Audience wird ab dem Erstellungsdatum nicht mehr aktualisiert. Kunden können dies um weitere 13 Monate verlängern. |
| Anzahl der aktualisierten Zielgruppen | 75.150 | Systemdurchsetztes Schutzschild | Maximale Anzahl aktualisierter Zielgruppen; der Wert variiert je nach Customer Journey Analytics-Package (siehe Produktbeschreibung). |

{style="table-layout:auto"}

Siehe auch Experience Platform [Real-time Customer Data Platform-Schutzmechanismen](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html?lang=de).


## Automatischer Ablauf von Datensätzen

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|:---:|
| Arbeitsaufträge | 20 | Systemdurchsetztes Schutzschild | Maximale Anzahl automatisierter Arbeitsaufträge zum Ablauf von Datensätzen pro Monat. |

{style="table-layout:auto"}



## Verbindungen, Datenansichten, Projekte

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Projekte | 50.000 | Systemdurchsetztes Schutzschild | Maximale Anzahl der Projekte für eine Organisation. |
| Datenansichten | 2.000 | Systemdurchsetztes Schutzschild | Maximale Anzahl an [Datenansichten](../data-views/data-views.md) für eine Organisation. |
| Datenansichten | 50 | Systemdurchsetztes Schutzschild | Maximale Anzahl von Datenansichten für eine Verbindung |
| Datensätze | 100 | Systemdurchsetztes Schutzschild | Maximale Anzahl an [Datensätze](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=de) pro Verbindung. |
| Verbindungen | 1000 | Systemdurchsetztes Schutzschild | Maximale Anzahl an [Verbindungen](../connections/overview.md) für eine Organisation. |
| Verbindungstitel | 500 | Systemdurchsetztes Schutzschild | Maximale Zeichenanzahl für einen Verbindungstitel. |
| Metriken | 5.000 | Systemdurchsetztes Schutzschild | Maximale Anzahl an Metriken in einer Datenansicht. |
| Dimensionen | 5.000 | Systemdurchsetztes Schutzschild | Maximale Anzahl von Dimensionen in einer Datenansicht. |
| Anmerkungstitel | 100 | Systemdurchsetztes Schutzschild | Maximale Zeichenanzahl für einen Anmerkungstitel. |
| Anmerkungsbeschreibung | 250 | Systemdurchsetztes Schutzschild | Maximale Zeichenanzahl für eine Anmerkung. |
| Schemafelder | 10 | Systemdurchsetztes Schutzschild | Maximale Anzahl von Schemafeldern (ohne Standardfelder) bei der Definition von Regeln für eine [abgeleitetes Feld](../data-views/derived-fields/derived-fields.md). |
| Such-/Profilfelder | 3 | Systemdurchsetztes Schutzschild | Maximale Anzahl von Lookup- oder Profilschemafeldern innerhalb der maximalen Anzahl von Schemafeldern (ohne Standardfelder) bei der Definition von Regeln für ein abgeleitetes Feld. |
| Abgeleitete Felder | 100-500 | Systemdurchsetztes Schutzschild | Maximale Anzahl abgeleiteter Felder pro Verbindung. Der Wert variiert je nach Customer Journey Analytics-Package (siehe Produktbeschreibung). |

{style="table-layout:auto"}


## Datenübertragungsbeschränkungen

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Felder | 10.000 | Systemdurchsetztes Schutzschild | Maximale Anzahl von Eigenschaften oder Feldern pro Zeile in einem Datensatz. |
| Eindeutige Zeichenfolgen | 10 Million | Systemdurchsetztes Schutzschild | Maximale Anzahl eindeutiger Schlüssel pro Lookup-Datensatz. |
| Zeilen | 1 Million | Systemdurchsetztes Schutzschild | Maximale Anzahl von Zeilen pro eindeutiger Personen-ID in einem bestimmten Monat innerhalb einer Verbindung. |
| Zeilengröße | 2 | Leistungsgarantie/systemerzwungene Schutzmechanismen | Durchschnittliche Größe in Kilobyte pro Datenzeile, die in Customer Journey Analytics erfasst wird (weiche Begrenzung). Eine statische Grenze für die Zeilengröße wird durch Limits für die Datenerfassung in Experience Platform bestimmt. |

{style="table-layout:auto"}

Siehe auch Experience Platform [Limits für die Datenerfassung](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html).


## Zieldatenexport

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Datenexport | Gesamter autorisierter Data Lake-Speicher | Leistungsgarantie | Der Kunde kann den Zieldatensatzexport verwenden, um Kundendaten bis zum zulässigen Gesamtdatenspeicherplatz im Data Lake im Data Lake zu exportieren. |
| Verfügbare Datensätze | Profil und Ereignis | Systemgesteuerte Schutzmechanismen | Ereignis-, Profil- oder Lookup-Datensätze, die in der Experience Platform-Benutzeroberfläche erstellt wurden, nachdem Daten über Quellen, Web SDK, Mobile SDK, Analytics Data Connector und Audience Manager erfasst oder erfasst wurden. |

{style="table-layout:auto"}

Siehe auch Experience Platform [Limits für den Datenexport](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/guardrails#dataset-exports)


## Daten-Landingzone

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Data Landing Zone per Sandbox | 1 | Systemdurchsetztes Schutzschild | Maximale Anzahl der Daten-Landingzonen pro Sandbox. |
| Datenspeicherung | 7 | Systemdurchsetztes Schutzschild | Maximale Anzahl von Tagen wird vor dem Löschen in der Daten-Landingzone gespeichert. |

{style="table-layout:auto"}


## Feldbasiertes Stitching

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Zusammengefügte Datensätze | 5 - 50 | Systemdurchsetztes Schutzschild | Maximale Anzahl von zugeordneten Datensätzen pro Kunde; der Wert variiert je nach Customer Journey Analytics-Package (siehe Produktbeschreibung). |
| Aufstockungsdauer | 6 - 25 | Systemdurchsetztes Schutzschild | Maximale Anzahl an Monaten für Aufstockungsdaten; der Wert variiert je nach Customer Journey Analytics-Package (siehe Produktbeschreibung). |
| Lookback-Fenster/Wiederholungshäufigkeit | 1.01.2017 - 30.07 | Systemdurchsetztes Schutzschild | Maximales Lookback-Fenster in Tagen/Wiederholungshäufigkeit; der Wert variiert je nach Customer Journey Analytics-Package (siehe Produktbeschreibung). |

{style="table-layout:auto"}


## Diagrammbasiertes Stitching

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Zusammengefügte Datensätze | 10-50 | Systemdurchsetztes Schutzschild | Maximale Anzahl von zugeordneten Datensätzen pro Kunde; der Wert variiert je nach Customer Journey Analytics-Package (siehe Produktbeschreibung). |
| Aufstockungsdauer | 13-25 | Systemdurchsetztes Schutzschild | Maximale Anzahl an Monaten für Aufstockungsdaten; der Wert variiert je nach Customer Journey Analytics-Package (siehe Produktbeschreibung). |
| Lookback-Fenster/Wiederholungshäufigkeit | 1.01.2017 - 30.07 | Systemdurchsetztes Schutzschild | Maximales Lookback-Fenster in Tagen/Wiederholungshäufigkeit; der Wert variiert je nach Customer Journey Analytics-Package (siehe Produktbeschreibung). |


## Filter und berechnete Metriken

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Container pro Filter | 50 | Systemdurchsetztes Schutzschild | Maximale Anzahl von Containern pro Filter. |
| Metriken pro berechneter Metrik | 25 | Systemdurchsetztes Schutzschild | Maximale Anzahl an Metriken pro berechneter Metrik. |
| Metriken und Dimensionen pro Filter | 25 | Systemdurchsetztes Schutzschild | Maximale Anzahl eindeutiger Metriken und Dimensionen pro Filter. |
| Verschachtelte Container pro Filter | 10 | Systemdurchsetztes Schutzschild | Maximale Anzahl verschachtelter Container pro Filter. |
| Regeln pro Filter | 100 | Systemdurchsetztes Schutzschild | Maximale Regelanzahl pro Filter. |
| Zeichenfolge Vergleicht pro Dimension nach Filter | 100 | Systemdurchsetztes Schutzschild | Maximale Anzahl von Zeichenfolgenvergleichen pro Dimension und Filter. |
| Berechnete Metriken  | 6.000 | Systemdurchsetztes Schutzschild | Maximale Anzahl berechneter Metriken für eine Organisation. |
| Filter | 50.000 | Systemdurchsetztes Schutzschild | Maximale Anzahl von Filtern, die Sie für eine Organisation definieren können. |
| API-Aufrufe | 120 | Systemdurchsetztes Schutzschild | API-Anfragen pro Minute (12 Anfragen alle 6 Sekunden). |

{style="table-layout:auto"}


## Mobile App

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Kacheln | 16 | Systemdurchsetztes Schutzschild | Maximale Anzahl von Kacheln pro Scorecard. |
| Filter | 10 | Systemdurchsetztes Schutzschild | Maximale Anzahl von Filtern pro Scorecard. |
| Dimensionen | 10 | Systemdurchsetztes Schutzschild | Maximale Anzahl von Dimensionen pro Scorecard. |

{style="table-layout:auto"}

## Report Builder

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Größe der Arbeitsmappen-Datei | 5 | Systemdurchsetztes Schutzschild | Maximale Dateigröße einer geplanten Arbeitsmappe in MB. |
| Datenblöcke | 1000 | Systemdurchsetztes Schutzschild | Maximale Anzahl an [Datenblöcke](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=de) pro Arbeitsmappe. |
| Metriken | 20 | Systemdurchsetztes Schutzschild | Maximale Anzahl an Metriken pro Datenblock. |
| Datumsbereich-Bereich | 13 | Systemdurchsetztes Schutzschild | Maximale Anzahl von Monaten, die ein Datumsbereich pro Datenblock umfassen kann. |
| Zeilen | 50.000 | Systemdurchsetztes Schutzschild | Maximale Zeilenanzahl pro Datenblock. |

{style="table-layout:auto"}


## Vollständiger Tabellenexport

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Zeilen pro Bericht | 3 Millionen - 300 Millionen | Systemdurchsetztes Schutzschild | Maximale Anzahl an Berichtszeilen pro Bericht. Der Wert variiert je nach Customer Journey Analytics-Package (siehe Produktbeschreibung). |
| Aufschlüsselung nach Tabelle | 5 | Systemdurchsetztes Schutzschild | Maximale Anzahl an Aufschlüsselungen pro Tabelle. |
| Metriken pro Tabelle | 5 | Systemdurchsetztes Schutzschild | Maximale Anzahl an Metriken pro Tabelle. |
| Planfrequenz | 1 | Systemdurchsetztes Schutzschild | Die Exporte können einmal (1) täglich oder länger geplant werden (z. B. einmal alle 2 Tage oder wöchentlich). |

{style="table-layout:auto"}

## Latenzen

>[!NOTE]
>
>Die folgenden Verarbeitungszeiten sind Limits, nicht vertragliche Service Level Agreements (SLAs). Die Latenz variiert je nach Kundenkonfiguration, Datenvolumen und Verbraucheranwendungen. Echte Verarbeitungszeiten sind oft schneller. Ihre spezifischen Vertragsbedingungen und SLAs finden Sie in Ihrem Customer Journey Analytics-Vertrag. Siehe Experience Platform [Limits für die Datenerfassung](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html) für weitere Informationen.

| Datenfluss | Erwartete Latenz |
|---|---|
| Adobe Analytics to Adobe Analytics Source Connector (A4T aktiviert) | &lt; 30 Minuten |
| Adobe Analytics Source Connector zum Echtzeit-Kundenprofil (A4T nicht aktiviert) | &lt; 2 Minuten |
| Adobe Analytics Source Connector zum Echtzeit-Kundenprofil (A4T aktiviert) | &lt; 30 Minuten |
| Datenaufnahme aus der Edge Network- oder Streaming-Erfassung in den Data Lake | &lt; 60 Minuten |
| Datenerfassung in den Data Lake über Adobe Analytics Source Connector | &lt; 2,25 Stunden |
| Datenerfassung in Customer Journey Analytics vom Data Lake | &lt; 90 Minuten |
| Stitching (optionale Funktion; siehe [Stitching-Übersicht](../stitching/overview.md) für weitere Informationen) | &lt; 3,25 Stunden |
| Aufstockung von Adobe Analytics Source Connector für weniger als 10 Milliarden Ereignisse (maximal 13 Monate historischer Daten) | &lt; 4 Wochen |
| Zielgruppe Veröffentlichen in Echtzeit-Kundenprofil, einschließlich der automatischen Erstellung des Streaming-Segments, sodass das Segment für den Empfang der Daten bereit ist. | ~ 60 Minuten |
| Aktualisierungshäufigkeit für Zielgruppen | Einmalige Aktualisierung: Latenz von weniger als 5 Minuten.<br/>Aktualisieren Sie alle 4 Stunden, täglich, wöchentlich, monatlich (die Latenz geht mit der Aktualisierungsrate einher). |

{style="table-layout:auto"}
