---
title: Aktuelle Versionshinweise zu Customer Journey Analytics
description: Anzeigen der neuesten Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 58224cf1a0b3527669bad17494fe2582ea95f3b1
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 66%

---

# Aktuelle Versionshinweise zu Customer Journey Analytics (April 2026)

**Letzte Aktualisierung**: 22. April 2026

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom April 2026. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion und Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| -----------|-----------|-----------|
| **Sprachunterstützung für Italienisch**<br/> Das italienische Gebietsschema (it-IT) wird jetzt in Analysis Workspace in Customer Journey Analytics unterstützt. <p>Customer Journey Analytics unterstützt alle Sprachen, die in der Experience Platform-Benutzeroberfläche unterstützt werden, wie unter [Browser- und Sprachunterstützung für die Experience Platform-Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/experience-platform/landing/platform-ui/browser-language-support#language-support) beschrieben.</p><p>Sie haben in Experience Platform die Möglichkeit, Ihre [Standardsprache zu ändern](https://experienceleague.adobe.com/de/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language).</p> | | &#x200B;8. April 2026 |
| **Datenvalidierung in Adobe Engineering Agent** <br/>Neue Datenvalidierungsfunktionen sind in Data Engineering Agent verfügbar. Diese Funktionen helfen Teams dabei, die Datenqualität direkt in Adobe Experience Platform schnell zu bewerten, bevor die Daten in Customer Journey Analytics analysiert werden. <p>Datenvalidierungsfunktionen ermöglichen die Validierung nach Bedarf sowie auf Feld- und Datensatzebene, wobei statistische Zusammenfassungen mit der intelligenten Erkennung ungültiger oder anomaler Werte kombiniert werden. </p><p>Die Verwendung von Datenvalidierungsfunktionen reduziert den Aufwand einer manuellen Qualitätssicherung und beschleunigt die zuverlässige Eingliederung und Umwandlung von Daten in allen Daten-Engineering-Workflows.</p><p>(Link zur Dokumentation folgt.)<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | Mai 2026 <p>(Veröffentlichung ursprünglich für den 31. März 2026 geplant)</p> |
| **MCP-Server für Customer Journey Analytics** <br/>Die Analytics MCP-Server (Model Context Protocol) ermöglichen es Ihnen, einen unterstützten MCP-Client mit Adobe Customer Journey Analytics zu verbinden. Sobald die Verbindung hergestellt ist, kann Ihr MCP-Client produktspezifische Tools aufrufen, um Daten abzurufen, Abfragen auszuführen oder unterstützte Vorgänge als Teil eines LLM- oder Agent-Workflows durchzuführen. Weitere Informationen finden Sie unter [Analytics-MCP-Server](https://developer.adobe.com/analytics-mcp/docs/).<p>Wenn Sie diese MCP-Server während der Beta-Phase verwendet haben, beachten Sie, dass es unterschiedliche URLs zwischen der Beta-Phase und den Produktionsendpunkten gibt. Stellen Sie sicher, dass alle während der Beta-Phase erstellten Agent-Workflows so aktualisiert werden, dass sie die Produktions-Endpunkte vor dem 31. Mai verwenden.</p> | | &#x200B;5. Mai 2026 |
| **Content Analytics-Unterstützung für native Mobile-App-Erlebnisse**<br/> Unternehmen können ihre Inhaltsleistungsanalyse auf iOS- und Android-Apps erweitern und Bild-Assets und granulare Erlebniselemente erfassen, um zu verstehen, welche In-App-Inhalte die Benutzerinteraktion und Geschäftsergebnisse fördern.<p>Einblicke sind für alle Adobe Content Analytics-Kunden verfügbar.</p> | &#x200B;6. Mai 2026 | TBD |
| **Streaming-Mediendienste: Unterstützung von Zeitplandaten** <br/>Sie können jetzt Zeitplandaten von früheren Live-Inhalten von Streaming-Medien hochladen, um Zuschauerzahlen einfacher und genauer zu verfolgen.<p>Im Folgenden finden Sie Beispiele für Live-Inhalte, die mit dem Upload von Zeitplandaten unterstützt werden:</p><ul><li>FAST-Plattformen (Free Ad Supported TV)</li><li>Lokale Datenströme</li><li>Live-Sportübertragungen</li></ul><p>Durch das Hochladen von Zeitplandaten können Sie die Zuschauerzahlen für einzelne Programme verfolgen, die in dem von Ihnen in der Upload-Datei angegebenen Zeitraum gelaufen sind. Sie können sogar Zuschauerzahlen für bestimmte Themen oder Programmsegmente erfassen.</p><p>Diese Funktionen sind unabhängig davon verfügbar, wie Sie die Erfassung von Streaming-Medien implementiert haben.</p><p>Zuvor war es bei der Analyse von Live-Inhalten schwierig, eine bestimmte Sitzung genau mit bestimmten Programmen zu verknüpfen, und es war nicht möglich, eine bestimmte Sitzung mit einzelnen Themen oder Programmsegmenten zu verknüpfen.</p><p>Weitere Informationen finden Sie unter [Hochladen von Zeitplandaten zum Nachverfolgen von Live-Inhalten](https://experienceleague.adobe.com/de/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | &#x200B;29. Oktober 2025 | Erstes Halbjahr 2026<p>(Veröffentlichung ursprünglich für den 29. Oktober 2025 geplant)</p> |
| **Reporting-API für mehrere Dimensionen**<br/> Erstellen Sie Berichte für mehrere Dimensionen in einer einzigen API-Anfrage und führen Sie Suchvorgänge auf Dimensionsebene durch. [Weitere Informationen](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim) | | März 2026 |
| **Mehrspaltige API-Sortierung**<br/> Sortieren Sie mehrere Dimensions- und Metrikobjekte in einer API-Anfrage. Kombinieren Sie Dimensionen und Metriken in derselben Sortierdefinition. [Weitere Informationen](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim#multi-column-sorting) | | März 2026 |

## Fehlerbehebungen in Customer Journey Analytics

**Analysis Workspace**: AN-442813, AN-442410, AN-442231, AN-441943, AN-441717, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Komponenten**:
**VERBINDUNGEN**: AN-442824, AN-440937, AN-440092, AN-429781
**Content Analytics**:
**Geführte**:
**Exporte**:
**Datenansichten**: AN-442809, AN-434824, AN-434210, AN-424000
**Implementierung**:
**Report Builder**: AN-441136, AN-438147, AN-425150
**Reporting**: AN-443900, AN-441811, AN-441506, AN-440919, AN-440545, AN-440505, AN-440300
**Segmentierung**:
**Terminierte Berichte**:
**Freigegebene Metriken und Dimensionen**:
**Sonstige**: AN-423359, AN-406242, AN-397985

## Verwandte Ressourcen

* [Frühere Versionshinweise für Customer Journey Analytics 2025](/help/release-notes/2025.md)
* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
* [Versionshinweise zur Streaming-Mediensammlung](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
