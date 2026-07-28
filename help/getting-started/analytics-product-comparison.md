---
title: Customer Journey Analytics - Produktvergleich
description: Kundenattribute von Reporting- und Export-Tools für Journey Analytics wie Analysis Workspace, Report Builder, Full Table Export, Daten-Feeds, APIs und MCP vergleichen.
keywords: Clickstream;Daten-Feed;Datenfeed;Produktvergleich;Analysis Workspace;Report Builder;vollständiger Tabellenexport
feature: Components
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: e686fca2c77a8f9739298ece01ccf0fa2fe87b3b
workflow-type: tm+mt
source-wordcount: 464
ht-degree: 44%

---


# Analytics-Produktvergleich

Auf dieser Seite können Sie die Berichts- und Exportwerkzeuge von Customer Journey Analytics in Bezug auf wichtige Attribute vergleichen, um das richtige Tool für Ihre Analyse- oder Datenexportanforderungen auszuwählen.

| Produktname und Hilfe-Link | [Analysis Workspace](/help/analysis-workspace/home.md) | [Report Builder](/help/report-builder/rb-overview.md) | [Vollständiger Tabellenexport](/help/analysis-workspace/export/export-cloud.md) | [Daten-Feeds](/help/components/exports/cja-data-feeds/data-feed-overview.md) | [APIs](https://developer.adobe.com/cja-apis/docs/) | MCP | BI-Erweiterung | Kollegin |
|---|---|---|---|---|---|---|---|---|
| **Zugriffsmethode** | Browser | Microsoft Excel | Browser | Über Browser einrichten | RESTful-API-Tools | MCP-kompatible Tools | BI-Tools | MCP-kompatible Tools |
| **Datengranularität** | Aggregiert | Aggregiert | Aggregiert | Ereignis | Aggregiert | Aggregiert | Aggregiert | Aggregiert |
| **Experience Cloud ID (ECID) verfügbar** | Nein | Nein | Nein | Ja | Nein | Nein | Nein | Nein |
| **Zeitstempel verfügbar** | Nein | Nein | Nein | Ja | Nein | Nein | Nein | Nein |
| **Verarbeitungsstufe** | Vollständig verarbeitet | Vollständig verarbeitet, mit separatem Echtzeitbericht | Vollständig verarbeitet | Vollständig verarbeitet | Vollständig verarbeitet | Vollständig verarbeitet | Vollständig verarbeitet | Vollständig verarbeitet |
| **Wo Bot-Filterung angewendet wird** | Innerhalb des [Datenstroms](https://experienceleague.adobe.com/de/docs/experience-platform/datastreams/bot-detection) und/oder innerhalb von [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | Innerhalb des [Datenstroms](https://experienceleague.adobe.com/de/docs/experience-platform/datastreams/bot-detection) und/oder innerhalb von [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | Innerhalb des [Datenstroms](https://experienceleague.adobe.com/de/docs/experience-platform/datastreams/bot-detection) und/oder innerhalb von [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | Innerhalb des [Datenstroms](https://experienceleague.adobe.com/de/docs/experience-platform/datastreams/bot-detection) und/oder innerhalb von [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) |  |  | Innerhalb des [Datenstroms](https://experienceleague.adobe.com/de/docs/experience-platform/datastreams/bot-detection) und/oder innerhalb von [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | |
| **Begrenzung der sichtbaren Zeilen (vor der Paginierung)** | 400 | 50,000 | Je nach Stufe ein Limit von 3 Millionen, 30 Millionen, 150 Millionen oder 300 Millionen | Abhängig von Stufe | 50,000 | 50,000 | 50,000 | 50,000 |
| **Mehrere Datenansichten** | Ja, ein Projekt kann Daten aus mehreren Datenansichten enthalten | Ja, ein Projekt kann Daten aus mehreren Datenansichten enthalten | Nein, ein Export kann nur Daten aus einer Datenansicht enthalten | Nein, ein Export kann nur Daten aus einer Datenansicht enthalten | Nein, jede Abfrage kann nur auf eine Datenansicht verweisen | Nein, jede Abfrage kann nur auf eine Datenansicht verweisen | Nein, jede Abfrage kann nur auf eine Datenansicht verweisen | Ja, wenn vom Benutzer dazu aufgefordert |
| **Anzahl der Dimensionsspalten** | Bis zu 5 | ? | Bis zu 10 | Unbegrenzt | Bis zu 5 | ? | ? | ? |
| **Anzahl der Metrikspalten** | ? | ? | Bis zu 10 | Unbegrenzt | ? | ? | ? | ? |
| **Segmentierung** <br> [Weitere Informationen](/help/components/segments/seg-overview.md) | Ja | Ja | Ja | Ja, mit [Einschränkungen](/help/components/exports/cja-data-feeds/df-segmentation.md) | Ja | Ja | Ja | Ja |
| **Berechnete Metriken** <br> [Weitere Informationen](/help/components/calc-metrics/calc-metr-overview.md) | Ja | Ja | Ja, mit [Einschränkungen](/help/analysis-workspace/export/export-cloud.md#calculated-metric-functions-support) | Nein | Ja | Ja | Ja | Ja |
| **Abgeleitete Felder** <br> [Weitere Informationen](/help/data-views/derived-fields/derived-fields.md) | Ja | Ja | Ja | Ja | Ja | Ja | Ja | Ja |
| **Attribution** <br> [Weitere Informationen](/help/analysis-workspace/attribution/overview.md) | Ja | Begrenzt | Ja, mit [Einschränkungen](/help/analysis-workspace/export/export-cloud.md#attribution-behavior) | Nein | Ja | Ja | Ja | Ja |
| **Geplanter Versand** | Ja | Ja | Ja | Ja | – | — | — | – |
| **Versandziele** | E-Mail | E-Mail | Amazon S3, Azure RBAC, Azure SAS, GCP | Amazon S3, Azure RBAC, Azure SAS, GCP | – | — | — | — |

{style="table-layout:auto"}
