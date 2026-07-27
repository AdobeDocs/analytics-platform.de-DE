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
source-git-commit: d5ecbbc28bc3892a2114de2c73df3287f22cf1a0
workflow-type: tm+mt
source-wordcount: 345
ht-degree: 59%

---


# Analytics-Produktvergleich

Auf dieser Seite können Sie die Berichts- und Exportwerkzeuge von Customer Journey Analytics in Bezug auf wichtige Attribute vergleichen, um das richtige Tool für Ihre Analyse- oder Datenexportanforderungen auszuwählen.

| Produktname und Hilfe-Link | [Analysis Workspace](/help/analysis-workspace/home.md) | [Report Builder](/help/report-builder/rb-overview.md) | [Vollständiger Tabellenexport](/help/analysis-workspace/export/export-cloud.md) | [Daten-Feeds](/help/components/exports/cja-data-feeds/data-feed-overview.md) | [APIs](https://developer.adobe.com/cja-apis/docs/) | MCP |
|---|---|---|---|---|---|---|
| **Zugriffsmethode** | Browser | Microsoft Excel | Browser | Über Browser einrichten | RESTful-API-Tools | MCP-kompatible Tools |
| **Datengranularität** | Aggregiert | Aggregiert | Aggregiert | Ereignis | Aggregiert | Aggregiert |
| **Experience Cloud ID (ECID) verfügbar** | Nein | Nein | Ja | Ja | Nein | Nein |
| **Zeitstempel verfügbar** | Nein | Nein | Nein | Ja | Nein | Nein |
| **Verarbeitungsstufe** | Vollständig verarbeitet | Vollständig verarbeitet | Vollständig verarbeitet | Vollständig verarbeitet | Vollständig verarbeitet | Vollständig verarbeitet |
| **Enthaltene Bot-Filterdaten** | Nein | Nein | Nein | Nein | Nein | Nein |
| **Geringer Traffic (Individuelle Werte überschritten) wird angezeigt** <br> [Weitere Informationen](/help/components/dimensions/high-cardinality.md) | Ja | Ja | Nein | Nein | Ja | Ja |
| **Begrenzung der sichtbaren Zeilen (vor der Paginierung)** | 400 | 50,000 | Unbegrenzt | Unbegrenzt | 50,000 | 50,000 |
| **Mehrere Datenansichten** | Ja | Ja | Nein | Nein | Ja | Ja |
| **Anzahl der Aufschlüsselungen** | Unbegrenzt | Bis zu 2 | Unbegrenzt | Unbegrenzt | Unbegrenzt, über mehrere Abfragen ausführen | Unbegrenzt |
| **Segmentierung** <br> [Weitere Informationen](/help/components/segments/seg-overview.md) | Ja | Ja | Ja | Ja, mit [Einschränkungen](/help/components/exports/cja-data-feeds/df-segmentation.md) | Ja | Ja |
| **Berechnete Metriken** <br> [Weitere Infos](/help/components/calc-metrics/calc-metr-overview.md) | Ja, mit [Attribution](/help/analysis-workspace/attribution/overview.md) | Ja, mit Attribution | Nein | Nein | Ja, mit Attribution | Ja, mit Attribution |
| **Abgeleitete Felder** <br> [Weitere Informationen](/help/data-views/derived-fields/derived-fields.md) | Ja | Ja | Ja | Ja | Ja | Ja |
| **Kohortenanalyse** | [Ja](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Nein | Nein | Nein | Nein | Nein |
| **Attribution** <br> [Weitere Informationen](/help/analysis-workspace/attribution/overview.md) | Ja | Begrenzt | Nein | Nein | Ja | Ja |
| **Kuratierung** <br> [Weitere Infos](/help/analysis-workspace/curate-share/curate.md) | Ja, mit in Projekten und Datenansichten | Nein | Nein | Ja, in der Datenansicht | Ja, in der Datenansicht | Ja, in der Datenansicht |
| **Projektfreigabe** <br> [Weitere Infos](/help/analysis-workspace/curate-share/share-projects.md) | Ja, mit Projektrollen | Nein | Nein | Nein | Nein | Nein |
| **Geplanter Versand** | Ja | Ja | Ja | Ja | Nein | Nein |
| **Versandziele** | E-Mail | E-Mail | Amazon S3, Azure RBAC, Azure SAS, GCP | Amazon S3, Azure RBAC, Azure SAS, GCP | – | – |
| **Datenansicht - Verarbeitung zur Berichtszeit** <br> [Weitere Informationen](/help/data-views/data-views.md) | Ja | Ja | Nein | Nein | Ja | Ja |

{style="table-layout:auto"}
