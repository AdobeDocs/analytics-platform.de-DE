---
title: Aktuelle Versionshinweise zu Customer Journey Analytics
description: Anzeigen der neuesten Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad333ea6-e90d-4c8f-8d61-9f8690784d6fid: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5cid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: c818dd36bc900b3945b87503afad8e944a3716a7
workflow-type: tm+mt
source-wordcount: 721
ht-degree: 100%

---

# Aktuelle Versionshinweise zu Customer Journey Analytics (Mai 2026)

**Letzte Aktualisierung:** 13. Mai 2026

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom Mai 2026. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion und Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| -----------|-----------|-----------|
| **CJA-API-Postman-Sammlungen** <br/>Eine herunterladbare Postman-Sammlung ist zum Aufrufen von CJA-API-Endpunkten verfügbar.<p>Weitere Informationen finden Sie im [analytics-cja-postman-collections GitHub-Repository](https://github.com/AdobeDocs/analytics-cja-postman-collections).  </p> | | &#x200B;1. Mai 2026 |
| **MCP-Server für Customer Journey Analytics** <br/>Die Analytics MCP-Server (Model Context Protocol) ermöglichen es Ihnen, einen unterstützten MCP-Client mit Adobe Customer Journey Analytics zu verbinden. Sobald die Verbindung hergestellt ist, kann Ihr MCP-Client produktspezifische Tools aufrufen, um Daten abzurufen, Abfragen auszuführen oder unterstützte Vorgänge als Teil eines LLM- oder Agent-basierten Workflows durchzuführen. Weitere Informationen finden Sie unter [Analytics-MCP-Server](https://developer.adobe.com/analytics-mcp/docs/).<p>Wenn Sie diese MCP-Server während der Beta-Phase verwendet haben, beachten Sie, dass es unterschiedliche URLs zwischen der Beta-Phase und den Produktionsendpunkten gibt. Stellen Sie sicher, dass alle während der Beta-Phase erstellten Agent-basierten Workflows vor dem 31. Mai so aktualisiert werden, dass sie die Produktions-Endpunkte verwenden.</p> | | &#x200B;5. Mai 2026 |
| **Content Analytics-Unterstützung für native App-Erlebnisse**<br/> Unternehmen können ihre Inhaltsleistungsanalyse auf iOS- und Android-Apps erweitern und Bild-Assets und granulare Erlebniselemente erfassen, um zu verstehen, welche In-App-Inhalte die Benutzerinteraktion und Geschäftsergebnisse fördern.<p> [Dokumentation](/help/content-analytics/content-analytics.md) wird aktualisiert, um die Funktionen und Konfigurationen des mobilen Kanals zu beschreiben. Informationen zur [Content Analytics Mobile SDK-Erweiterung](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) finden Sie auf [Adobe Developer](https://developer.adobe.com/).</p><p>Erkenntnisse sind für alle Kundinnen und Kunden von Adobe Content Analytics verfügbar.</p> | | &#x200B;6. Mai 2026 |
| **Verbesserungen der Journey-Arbeitsflächen** <br/> Die folgenden Verbesserungen sind in Journey-Arbeitsflächenvisualisierungen verfügbar: <ul><li>[Ausschließen von Knoten](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#exclude-nodes) aus einer Journey.</li><li>Verwenden Sie die Fallout-Daten eines Knotens, um [Segmente](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#create-a-segment-based-on-a-node-or-arrow), [Trends](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#view-trend-data), [Zielgruppen](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#create-an-audience) und [Aufschlüsselungen](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#apply-a-breakdown) zu erstellen.</li></ul> | | &#x200B;18. Mai 2026 |
| **Content Analytics: Miniaturen und Vorschauen für Linienvisualisierungen** <br/>[Miniaturen und Vorschauen](/help/content-analytics/report/report.md) sind jetzt für Assets und Erlebnisse in Linienvisualisierungen für Content Analytics verfügbar. |  | &#x200B;20. Mai 2026 |
| **Streaming-Mediendienste: Unterstützung von Zeitplandaten** <br/>Sie können jetzt Zeitplandaten von früheren Live-Inhalten von Streaming-Medien hochladen, um Zuschauerzahlen einfacher und genauer zu verfolgen.<p>Im Folgenden finden Sie Beispiele für Live-Inhalte, die mit dem Upload von Zeitplandaten unterstützt werden:</p><ul><li>FAST-Plattformen (Free Ad Supported TV)</li><li>Lokale Datenströme</li><li>Live-Sportübertragungen</li></ul><p>Durch das Hochladen von Zeitplandaten können Sie die Zuschauerzahlen für einzelne Programme verfolgen, die in dem von Ihnen in der Upload-Datei angegebenen Zeitraum gelaufen sind. Sie können sogar Zuschauerzahlen für bestimmte Themen oder Programmsegmente erfassen.</p><p>Diese Funktionen sind unabhängig davon verfügbar, wie Sie die Erfassung von Streaming-Medien implementiert haben.</p><p>Zuvor war es bei der Analyse von Live-Inhalten schwierig, eine bestimmte Sitzung genau mit bestimmten Programmen zu verknüpfen, und es war nicht möglich, eine bestimmte Sitzung mit einzelnen Themen oder Programmsegmenten zu verknüpfen.</p><p>Weitere Informationen finden Sie unter [Hochladen von Zeitplandaten zum Nachverfolgen von Live-Inhalten](https://experienceleague.adobe.com/de/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | &#x200B;29. Oktober 2025 | Erstes Halbjahr 2026<p>(Veröffentlichung ursprünglich für den 29. Oktober 2025 geplant)</p> |

{style="table-layout:auto"}


## Fehlerbehebungen in Customer Journey Analytics

**Analysis Workspace**: AN-446522, AN-445779, AN-445759, AN-444676, AN-442813, AN-441943, AN-441717, AN-441538, AN-441123, AN-440976, AN-440952, AN-440919, AN-439797, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Komponenten**:
**Verbindungen**: AN-449652, AN-444560, AN-442824, AN-440937, AN-440092, AN-439823, AN-429781
**Content Analytics**:
**Geführte Analyse**:
**Exporte**: AN-438953, AN-437115
**Datenansichten**: AN-442809
**Implementierung**:
**Report Builder**: AN-448697, AN-447128, AN-441148, AN-441136, AN-438147, AN-425150
**Reporting**: AN-445123, AN-442231, AN-442169, AN-441811, AN-441733, AN-440505, AN-440300, AN-434824, AN-434210, AN-424000, AN-423359, AN-406242
**Segmentierung**:
**Geplante Berichte**:
**Freigegebene Metriken und Dimensionen**:
**Sonstige**: AN-449159, AN-444661, AN-443900, AN-397985

## Verwandte Ressourcen

* [Frühere Versionshinweise für Customer Journey Analytics 2025](/help/release-notes/2025.md)
* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
* [Versionshinweise zur Streaming-Mediensammlung](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
* [Versionshinweise zu CX Enterprise](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
