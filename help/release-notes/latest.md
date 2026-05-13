---
title: Aktuelle Versionshinweise zu Customer Journey Analytics
description: Anzeigen der neuesten Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: d7802b43351f5aa4777f32d8c736d5137860dd44
workflow-type: tm+mt
source-wordcount: 891
ht-degree: 41%

---

# Aktuelle Versionshinweise zu Customer Journey Analytics (Mai 2026)

**Letzte Aktualisierung**: 13. Mai 2026

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom Mai 2026. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion und Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| -----------|-----------|-----------|
| **CJA-API-Postman** Sammlungen<br/> (Eine herunterladbare Postman-Sammlung ist zum Aufrufen von CJA-API-Endpunkten verfügbar.<p>Weitere Informationen finden Sie unter [analytics-cja-postman-collections GitHub-Repository](https://github.com/AdobeDocs/analytics-cja-postman-collections).  </p> | | &#x200B;1. Mai 2026 |
| **MCP-Server für Customer Journey Analytics** <br/>Die Analytics MCP-Server (Model Context Protocol) ermöglichen es Ihnen, einen unterstützten MCP-Client mit Adobe Customer Journey Analytics zu verbinden. Sobald die Verbindung hergestellt ist, kann Ihr MCP-Client produktspezifische Tools aufrufen, um Daten abzurufen, Abfragen auszuführen oder unterstützte Vorgänge als Teil eines LLM- oder Agent-Workflows durchzuführen. Weitere Informationen finden Sie unter [Analytics-MCP-Server](https://developer.adobe.com/analytics-mcp/docs/).<p>Wenn Sie diese MCP-Server während der Beta-Phase verwendet haben, beachten Sie, dass es unterschiedliche URLs zwischen der Beta-Phase und den Produktionsendpunkten gibt. Stellen Sie sicher, dass alle während der Beta-Phase erstellten Agent-Workflows so aktualisiert werden, dass sie die Produktions-Endpunkte vor dem 31. Mai verwenden.</p> | | &#x200B;5. Mai 2026 |
| **Content Analytics-Unterstützung für native Mobile-App-Erlebnisse**<br/> Unternehmen können ihre Inhaltsleistungsanalyse auf iOS- und Android-Apps erweitern und Bild-Assets und granulare Erlebniselemente erfassen, um zu verstehen, welche In-App-Inhalte die Benutzerinteraktion und Geschäftsergebnisse fördern.<p> [Dokumentation](/help/content-analytics/content-analytics.md) wird aktualisiert, um die Funktionen und Konfigurationen des mobilen Kanals zu beschreiben. Informationen zur [Content Analytics Mobile SDK-](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) finden Sie unter [Adobe Developer](https://developer.adobe.com/).</p><p>Einblicke sind für alle Adobe Content Analytics-Kunden verfügbar.</p> | | &#x200B;6. Mai 2026 |
| **Datenvalidierung in Adobe Engineering Agent** <br/>Neue Datenvalidierungsfunktionen sind in Data Engineering Agent verfügbar. Diese Funktionen helfen Teams dabei, die Datenqualität direkt in Adobe Experience Platform schnell zu bewerten, bevor die Daten in Customer Journey Analytics analysiert werden. <p>Datenvalidierungsfunktionen ermöglichen die Validierung nach Bedarf sowie auf Feld- und Datensatzebene, wobei statistische Zusammenfassungen mit der intelligenten Erkennung ungültiger oder anomaler Werte kombiniert werden. </p><p>Die Verwendung von Datenvalidierungsfunktionen reduziert den Aufwand einer manuellen Qualitätssicherung und beschleunigt die zuverlässige Eingliederung und Umwandlung von Daten in allen Daten-Engineering-Workflows.</p><p>(Link zur Dokumentation folgt.)<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/de/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | &#x200B;19. Mai 2026 <p>(Veröffentlichung ursprünglich für den 31. März 2026 geplant)</p> |
| **Content Analytics: Miniaturansichten und Vorschauen** Linienvisualisierungen <br/>[Miniaturansichten und Vorschauen](/help/content-analytics/report/report.md) sind jetzt für Assets und Erlebnisse in Linienvisualisierungen für Content Analytics verfügbar. |  | &#x200B;20. Mai 2026 |
| **Data Insights Agent auf Agent Orchestrator** <br/> Data Insights Agent ist nicht nur in der rechten Leiste in Customer Journey Analytics verfügbar, sondern auch als Teil von Agent Orchestrator. Dies bedeutet, dass Sie jetzt Einblicke erhalten können, die auf Daten und Funktionen von Customer Journey Analytics basieren, während Sie in anderen Experience Platform-Apps arbeiten, z. B. in Journey Optimizer.<p>In Customer Journey Analytics umfasst Data Insights Agent die folgenden Verbesserungen:</p><ul><li>Ein konsistenteres Benutzererlebnis mit Agent Orchestrator</li><li>Erläuternde zusammenfassende Absätze</li><li>Antworten auf „Warum“-Fragen durch Ursachenanalyse</li><li>Inline-Tabellen</li><li>Und vieles mehr!&lt;/l></ul><p>(Link zur Dokumentation folgt.)</p> | | Ende Mai 2026 |
| **Streaming-Mediendienste: Unterstützung von Zeitplandaten** <br/>Sie können jetzt Zeitplandaten von früheren Live-Inhalten von Streaming-Medien hochladen, um Zuschauerzahlen einfacher und genauer zu verfolgen.<p>Im Folgenden finden Sie Beispiele für Live-Inhalte, die mit dem Upload von Zeitplandaten unterstützt werden:</p><ul><li>FAST-Plattformen (Free Ad Supported TV)</li><li>Lokale Datenströme</li><li>Live-Sportübertragungen</li></ul><p>Durch das Hochladen von Zeitplandaten können Sie die Zuschauerzahlen für einzelne Programme verfolgen, die in dem von Ihnen in der Upload-Datei angegebenen Zeitraum gelaufen sind. Sie können sogar Zuschauerzahlen für bestimmte Themen oder Programmsegmente erfassen.</p><p>Diese Funktionen sind unabhängig davon verfügbar, wie Sie die Erfassung von Streaming-Medien implementiert haben.</p><p>Zuvor war es bei der Analyse von Live-Inhalten schwierig, eine bestimmte Sitzung genau mit bestimmten Programmen zu verknüpfen, und es war nicht möglich, eine bestimmte Sitzung mit einzelnen Themen oder Programmsegmenten zu verknüpfen.</p><p>Weitere Informationen finden Sie unter [Hochladen von Zeitplandaten zum Nachverfolgen von Live-Inhalten](https://experienceleague.adobe.com/de/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | &#x200B;29. Oktober 2025 | Erstes Halbjahr 2026<p>(Veröffentlichung ursprünglich für den 29. Oktober 2025 geplant)</p> |

{style="table-layout:auto"}


## Fehlerbehebungen in Customer Journey Analytics

**Analysis Workspace**: AN-446522, AN-445779, AN-445759, AN-444676, AN-442813, AN-441943, AN-441717, AN-441538, AN-441123, AN-440976, AN-440919, AN-439797, AN-434855, AN-429777, AN-440952, AN-429048, AN-428892, AN-428189, AN-425215
**Komponenten**:
**VERBINDUNGEN**: AN-449652, AN-444560, AN-442824, AN-440937, AN-440092, AN-439823, AN-429781
**Content Analytics**:
**Geführte**:
**Exporte**: AN-438953, AN-437115
**Datenansichten**: AN-442809
**Implementierung**:
**Report Builder**: AN-448697, AN-447128, AN-441148, AN-441136, AN-438147, AN-425150
**Reporting**: AN-445123, AN-442231, AN-442169, AN-441811, AN-441733, AN-440505, AN-440300, AN-434824, AN-434210, AN-424000, AN-423359, AN-406242
**Segmentierung**:
**Terminierte Berichte**:
**Freigegebene Metriken und Dimensionen**:
**Sonstige**: AN-449159, AN-444661, AN-443900, AN-397985

## Verwandte Ressourcen

* [Frühere Versionshinweise für Customer Journey Analytics 2025](/help/release-notes/2025.md)
* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
* [Versionshinweise zur Streaming-Mediensammlung](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
