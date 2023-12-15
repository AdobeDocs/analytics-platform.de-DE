---
title: Customer Journey Analytics Guardrails
description: Erfahren Sie mehr über die Limits für Customer Journey Analytics
solution: Customer Journey Analytics
feature: Administration
role: Admin
source-git-commit: 37cb4cc9ecb58f31fdcd53deaadbd124bf6e894c
workflow-type: tm+mt
source-wordcount: '1467'
ht-degree: 14%

---


# Customer Journey Analytics Guardrails

Dieses Dokument bietet Einschränkungen für verschiedene Komponenten von Customer Journey Analytics. Limits, Scoping-Parameter und Berechtigungen finden Sie in der [Produktbeschreibung für Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html) oder [Produktbeschreibung für Adobe Analytics Add-on: Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html).

## Arten von Beschränkungen

In diesem Dokument gibt es zwei Arten von Standardbeschränkungen:

| Schutztyp | Beschreibung |
|----------|---------|
| **Leistungsgarantien (weiche Begrenzung)** | Leistungsgarantien sind Nutzungsbeschränkungen, die sich auf das Scoping Ihrer Anwendungsfälle beziehen. Wenn Sie die Leistungsgarantien überschreiten, kann es zu Leistungseinbußen und Latenzzeiten kommen. Adobe ist nicht für eine solche Leistungsbeeinträchtigung verantwortlich. Kunden, die eine Leistungsgarantie konsequent überschreiten, können zusätzliche Kapazität lizenzieren, um Leistungsbeeinträchtigungen zu vermeiden. |
| **Systemerzwungene Limits (harte Grenze)** | Systemerzwungene Limits werden durch die Customer Journey Analytics-Benutzeroberfläche oder -API erzwungen. Dies sind Beschränkungen, die Sie nicht überschreiten können, da die Benutzeroberfläche und API Sie daran hindert, dies zu tun oder einen Fehler zurückzugeben. |

{style="table-layout:auto"}

Einige der Funktionen und der zugehörige Wert für die Begrenzung hängen vom Customer Journey Analytics-Package ab, für das Sie berechtigt sind.

>[!NOTE]
>
>Die in diesem Dokument beschriebenen Werte können sich aufgrund kontinuierlicher Verbesserungen des Produkts ändern. Suchen Sie regelmäßig nach Updates. Wenden Sie sich an Ihren Kundenbetreuer, wenn Sie mehr über benutzerdefinierte Beschränkungen erfahren möchten.

## Ad-hoc-SQL-Abfragen

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Wiederholtes Timeout ausprobieren | 90 | Systemerzwungene Limits | Maximale Anzahl von Sekunden, bevor die Reporting-Engine zurückgibt, dass die Anfrage zu lange dauert, bis Ergebnisse zurückgegeben werden (möglicherweise aufgrund anderer gleichzeitiger Anfragen). Eine erneute Anforderung ist möglich. | |
| Wiederholtes Timeout nicht wiederholen | 600 | Systemerzwungene Limits | Maximale Anzahl von Sekunden vor Zeitüberschreitung bei Ad Hoc SQL-Abfragen. Andernfalls wird angegeben, dass die maximale Anzahl von Sekunden, bevor Reporting-Engines melden, zurückgibt, dass die Anfrage zu lange gedauert hat, um Ergebnisse zurückzugeben, und nicht erneut versucht werden sollte. Die Anfrage liefert höchstwahrscheinlich nie Ergebnisse aufgrund von Problemen im Hintergrund-Prozess. |
| Metriken | 150 | Systemerzwungene Limits | Maximale Anzahl an Metriken in einer Anforderung. | | |
| Ausgabezeilen interaktiver Abfragen | 50.000 | Systemerzwungene Limits | Standardanzahl der zurückgegebenen Zeilen, sofern nicht anders angegeben. | |

{style="table-layout:auto"}

## Analysis Workspace-Projekte

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Sichtbare Zeilen pro Tabelle | 400 | Systemerzwungene Limits | Maximale Anzahl sichtbarer Zeilen in einer Freiformtabelle in einem Analysis Workspace-Projekt. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |
| Exportierbare Zeilen pro Tabelle | 50.000 | Systemerzwungene Limits | Maximale Anzahl von Zeilen, die pro Dimension exportiert werden können. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |
| Bedienfelder pro Projekt | 15 | Systemerzwungene Limits | Maximale Anzahl an [Bedienfelder](../analysis-workspace/home.md#panels) pro Projekt. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |
| Visualisierungen pro Bereich | 25 | Systemerzwungene Limits | Maximale Anzahl an [Visualisierungen](../analysis-workspace/home.md#visualizations) pro Bedienfeld. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |

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
| Zielgruppenfilter | 20 | Systemerzwungene Limits | Maximale Anzahl an [Filter](../components/filters/filters-overview.md) pro Zielgruppe. |
| Anzahl der Zielgruppenidentitäten | 20 Million | Systemerzwungene Limits | Maximale Anzahl von Identitäten pro Zielgruppe. |
| Aktualisierungshäufigkeit der Zielgruppe | 4 | Systemerzwungene Limits | Maximale Häufigkeit in Stunden und [audience](../components/audiences/audiences-overview.md) aktualisiert werden. | |
| Lookback-Fenster für Zielgruppenaktualisierung | 90 | Systemerzwungene Limits | Maximale Anzahl von Tagen für das Lookback-Fenster &quot;Aktualisieren&quot;. |
| Aktualisieren des Zielgruppenablaufdatums | 13 | Systemerzwungene Limits | Die maximale Anzahl von Monaten für die Audience wird ab dem Erstellungsdatum nicht mehr aktualisiert. Kunden können dies um weitere 13 Monate verlängern. |
| Anzahl der aktualisierten Zielgruppen | 75, 100, 150 | Systemerzwungene Limits | Maximale Anzahl aktualisierter Zielgruppen, der Wert variiert je nach Package. |

{style="table-layout:auto"}

Siehe auch Experience Platform [Limits in Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html?lang=en).


## Automatischer Ablauf von Datensätzen

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|:---:|
| Arbeitsaufträge | 20 | Systemerzwungene Limits | Maximale Anzahl automatisierter Arbeitsaufträge zum Ablauf von Datensätzen pro Monat. |

{style="table-layout:auto"}



## Verbindungen, Datenansichten, Projekte

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Projekte | 2.000 | Systemerzwungene Limits | Maximale Anzahl der Projekte für eine Organisation. |
| Datenansichten | 2.000 | Systemerzwungene Limits | Maximale Anzahl an [Datenansichten](../data-views/data-views.md) für eine Organisation. |
| Datenansichten | 50 | Systemerzwungene Limits | Maximale Anzahl von Datenansichten für eine Verbindung |
| Datensätze | 100 | Systemerzwungene Limits | Maximale Anzahl an [Datensätze](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=en) pro Verbindung. |
| Verbindungen | 1000 | Systemerzwungene Limits | Maximale Anzahl an [Verbindungen](../connections/overview.md) für eine Organisation. |
| Verbindungstitel | 500 | Systemerzwungene Limits | Maximale Zeichenanzahl für einen Verbindungstitel. |
| Metriken | 5.000 | Systemerzwungene Limits | Maximale Anzahl an Metriken in einer Datenansicht. |
| Dimensionen | 5.000 | Systemerzwungene Limits | Maximale Anzahl von Dimensionen in einer Datenansicht. | |
| Anmerkungstitel | 100 | Systemerzwungene Limits | Maximale Zeichenanzahl für einen Anmerkungstitel. |
| Anmerkungsbeschreibung | 250 | Systemerzwungene Limits | Maximale Zeichenanzahl für eine Anmerkung. | |
| Schemafelder | 10 | Systemerzwungene Limits | Maximale Anzahl von Schemafeldern (ohne Standardfelder) bei der Definition von Regeln für eine [abgeleitetes Feld](../data-views/derived-fields/derived-fields.md). |
| Such-/Profilfelder | 3 | Systemerzwungene Limits | Maximale Anzahl von Lookup- oder Profilschemafeldern innerhalb der maximalen Anzahl von Schemafeldern (ohne Standardfelder) bei der Definition von Regeln für ein abgeleitetes Feld. |
| Abgeleitete Felder | 100 | Systemerzwungene Limits | Maximale Anzahl abgeleiteter Felder pro Verbindung. |

{style="table-layout:auto"}


## Datenübertragungsbeschränkungen

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Felder | 10.000 | Systemerzwungene Limits | Maximale Anzahl von Eigenschaften oder Feldern pro Zeile in einem Datensatz. | | |
| Eindeutige Zeichenfolgen | 10 Million | Systemerzwungene Limits | Maximale Anzahl eindeutiger Schlüssel pro Lookup-Datensatz. |
| Zeilen | 1 Million | Systemerzwungene Limits | Maximale Anzahl von Zeilen pro eindeutiger Personen-ID innerhalb einer Verbindung. |
| Zeilengröße | 2 | Leistungsgarantie/systemerzwungene Limits | Durchschnittliche Größe in Kilobyte pro Datenzeile, die in Customer Journey Analytics erfasst wird (weiche Begrenzung). Eine statische Grenze für die Zeilengröße wird durch Limits für die Datenerfassung in Experience Platform bestimmt. |

{style="table-layout:auto"}

Siehe auch Experience Platform [Limits für die Datenerfassung](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html?lang=en).


## Daten-Landingzone

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Daten-Landingzone pro Sandbox | 1 | Systemerzwungene Limits | Maximale Anzahl der Daten-Landingzonen pro Sandbox. |
| Datenspeicherung | 7 | Systemerzwungene Limits | Maximale Anzahl von Tagen wird vor dem Löschen in der Daten-Landingzone gespeichert. |

{style="table-layout:auto"}


## Feldbasiertes Stitching

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Zugeordnete Datensätze | 10 | Systemerzwungene Limits | Maximale Anzahl von zugeordneten Datensätzen pro Kunde, abhängig vom Paket. |
| Daten aufstocken | 60 | Systemerzwungene Limits | Maximale Anzahl von Tagen für Aufstockungsdaten. |

{style="table-layout:auto"}


## Filter und berechnete Metriken

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Container pro Filter | 50 | Systemerzwungene Limits | Maximale Anzahl von Containern pro Filter. |
| Metriken pro berechneter Metrik | 25 | Systemerzwungene Limits | Maximale Anzahl an Metriken pro berechneter Metrik. |
| Metriken und Dimensionen pro Filter | 25 | Systemerzwungene Limits | Maximale Anzahl eindeutiger Metriken und Dimensionen pro Filter. |
| Verschachtelte Container pro Filter | 10 | Systemerzwungene Limits | Maximale Anzahl verschachtelter Container pro Filter. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |
| Regeln pro Filter | 100 | Systemerzwungene Limits | Maximale Regelanzahl pro Filter. |
| Zeichenfolge vergleicht pro Dimension und Filter | 100 | Systemerzwungene Limits | Maximale Anzahl von Zeichenfolgenvergleichen pro Dimension und Filter. |
| Berechnete Metriken  | 6.000 | Systemerzwungene Limits | Maximale Anzahl berechneter Metriken für eine Organisation. | |
| Filter | 50.000 | Systemerzwungene Limits | Maximale Anzahl von Filtern, die Sie für eine Organisation definieren können. |

{style="table-layout:auto"}


## Mobile App

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Kacheln | 16 | Systemerzwungene Limits | Maximale Anzahl von Kacheln pro Scorecard. |
| Filter | 10 | Systemerzwungene Limits | Maximale Anzahl von Filtern pro Scorecard. |
| Dimensionen | 10 | Systemerzwungene Limits | Maximale Anzahl von Dimensionen pro Scorecard. |

{style="table-layout:auto"}

## Report Builder

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Größe der Arbeitsmappen-Datei | 5 | Systemerzwungene Limits | Maximale Dateigröße einer geplanten Arbeitsmappe in MB. |
| Datenblöcke | 1000 | Systemerzwungene Limits | Maximale Anzahl an [Datenblöcke](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=en) pro Arbeitsmappe. |
| Metriken | 20 | Systemerzwungene Limits | Maximale Anzahl an Metriken pro Datenblock. |
| Datumsbereich | 13 | Systemerzwungene Limits | Maximale Anzahl von Monaten, die ein Datumsbereich pro Datenblock umfassen kann. |  |
| Zeilen | 50.000 | Systemerzwungene Limits | Maximale Zeilenanzahl pro Datenblock. |

{style="table-layout:auto"}


## Vollständiger Tabellenexport

| Name | Wert | Art von Limit | Beschreibung |
|---|--:|---|---|
| Zeilen pro Bericht | 3 Millionen - 150 Millionen | Systemerzwungene Limits | Maximale Anzahl an Berichtszeilen pro Bericht; Wert basierend auf dem lizenzierten Paket. |
| Aufschlüsselung nach Tabelle | 5 | Systemerzwungene Limits | Maximale Anzahl an Aufschlüsselungen pro Tabelle. |
| Metriken pro Tabelle | 5 | Systemerzwungene Limits | Maximale Anzahl an Metriken pro Tabelle. |
| Planfrequenz | 1 | Systemerzwungene Limits | Die Exporte können einmal (1) täglich oder länger geplant werden (z. B. einmal alle 2 Tage oder wöchentlich). |

{style="table-layout:auto"}

## Latenzen

>[!NOTE]
>
>Die folgenden Verarbeitungszeiten sind Limits, nicht vertragliche Service Level Agreements (SLAs). Die Latenz variiert je nach Kundenkonfiguration, Datenvolumen und Verbraucheranwendungen. Echte Verarbeitungszeiten sind oft schneller. Ihre spezifischen Vertragsbedingungen und SLAs finden Sie in Ihrem Customer Journey Analytics-Vertrag. Siehe Experience Platform [Limits für die Datenerfassung](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html?lang=en) für weitere Informationen.

| Datenfluss | Erwartete Latenz |
|---|---|
| Quell-Connector von Adobe Analytics nach Adobe Analytics (A4T aktiviert) | &lt; 30 Minuten |
| Adobe Analytics-Quell-Connector zum Echtzeit-Kundenprofil (A4T nicht aktiviert) | &lt; 2 Minuten |
| Adobe Analytics-Quell-Connector zum Echtzeit-Kundenprofil (A4T aktiviert) | &lt; 30 Minuten |
| Datenerfassung in den Data Lake von Edge Network oder Streaming-Erfassung | &lt; 60 Minuten |
| Datenerfassung in den Data Lake über den Quell-Connector von Adobe Analytics | &lt; 90 Minuten |
| Datenerfassung in Customer Journey Analytics aus dem Data Lake | &lt; 90 Minuten |
| Aufstockung des Adobe Analytics-Quell-Connectors bei weniger als 10 Milliarden Ereignissen (maximal 13 Monate historischer Daten) | &lt; 4 Wochen |
| Zielgruppenveröffentlichung im Echtzeit-Kundenprofil, einschließlich der automatischen Erstellung des Streaming-Segments, sodass das Segment bereit für den Empfang der Daten ist. | ~ 60 Minuten |
| Aktualisierungshäufigkeit für Zielgruppen | Einmalige Aktualisierung: Latenz von weniger als 5 Minuten.<br/>Aktualisieren Sie alle 4 Stunden, täglich, wöchentlich, monatlich (die Latenz geht mit der Aktualisierungsrate einher). |

{style="table-layout:auto"}

