---
title: Aktuelle Versionshinweise zu Customer Journey Analytics
description: Anzeigen der neuesten Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7fc7475001505749cf59aa82a62e5abb7e81ea97
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 41%

---

# Aktuelle Customer Journey Analytics-Versionshinweise (April 2026)

**Letzte Aktualisierung**: 9. April 2026

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom April 2026. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion und Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| -----------|-----------|-----------|
| **Italienische Sprachunterstützung**<br/> Das italienische Gebietsschema (it-it) wird jetzt in Analysis Workspace in Customer Journey Analytics unterstützt. <p>Customer Journey Analytics unterstützt alle Sprachen, die in der Experience Platform-Benutzeroberfläche unterstützt werden, wie unter [Browser- und Sprachunterstützung für die Experience Platform-Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/experience-platform/landing/platform-ui/browser-language-support#language-support) beschrieben.</p><p>Sie können [Standardsprache ändern](https://experienceleague.adobe.com/de/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language) in Experience Platform.</p> | | Donnerstag, 8. April 2026 |
| **Datenvalidierung im Adobe Engineering Agent** <br/>Neue Datenvalidierungsfähigkeiten sind in Data Engineering Agent verfügbar. Diese Fähigkeiten helfen Teams dabei, die Datenqualität direkt in Adobe Experience Platform schnell zu bewerten, bevor die Daten in Customer Journey Analytics analysiert werden. <p>Datenvalidierungsfähigkeiten ermöglichen die Validierung auf Anforderungs-, Feld- und Datensatzebene, wobei statistische Zusammenfassungen mit der intelligenten Erkennung ungültiger oder anomaler Werte kombiniert werden. </p><p>Die Verwendung von Datenvalidierungsfähigkeiten reduziert den manuellen QA-Aufwand und beschleunigt das Onboarding und die Transformationen vertrauenswürdiger Daten in allen Data Engineering Workflows.</p><p>(Link zur Dokumentation folgt.)<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/de/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | Ende April 2026 <p>(Veröffentlichung ursprünglich für den Mittwoch, 31. März 2026 geplant)</p> |
| **MCP-Server für** <br/>Sie können Customer Journey Analytics jetzt mithilfe von MCP (Model Context Protocol) in Ihre bestehenden Agent-Workflows einbinden. Sie können Berichte und Einblicke in natürlicher Sprache anfordern.<p>(Link zur Dokumentation folgt.)</p> | | Ende April 2026 |
| **Streaming-Medien-Services: Unterstützen von Zeitplandaten** <br/>Sie können jetzt Zeitplandaten vergangener Live-Streaming-Medien-Inhalte hochladen, um die Zuschauerzahlen einfacher und genauer zu verfolgen.<p>Im Folgenden finden Sie Beispiele für Live-Inhalte, die mit dem Upload von Zeitplandaten unterstützt werden:</p><ul><li>FAST-Plattformen (Free Ad Supported TV)</li><li>Lokale Datenströme</li><li>Live-Sportübertragungen</li></ul><p>Durch das Hochladen von Zeitplandaten können Sie die Zuschauerzahlen für einzelne Programme verfolgen, die in dem von Ihnen in der Upload-Datei angegebenen Zeitraum gelaufen sind. Sie können sogar Zuschauerzahlen für bestimmte Themen oder Programmsegmente erfassen.</p><p>Diese Funktionen sind unabhängig davon verfügbar, wie Sie die Erfassung von Streaming-Medien implementiert haben.</p><p>Zuvor war es bei der Analyse von Live-Inhalten schwierig, eine bestimmte Sitzung genau mit bestimmten Programmen zu verknüpfen, und es war nicht möglich, eine bestimmte Sitzung mit einzelnen Themen oder Programmsegmenten zu verknüpfen.</p><p>Weitere Informationen finden Sie unter [Hochladen von Zeitplandaten zum Nachverfolgen von Live-Inhalten](https://experienceleague.adobe.com/de/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | &#x200B;29. Oktober 2025 | Erstes Halbjahr 2026<p>(Veröffentlichung ursprünglich für den 29. Oktober 2025 geplant)</p> |
| **Berichte für**<br/>-APIs mit mehreren Dimensionen in einer einzigen API-Anfrage ausgeben und Suchen auf Dimensionsebene durchführen. [Weitere Informationen](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim) | | März 2026 |
| **Mehrspaltige API-Sortierung**<br/> Sortieren mehrerer Dimensions- und Metrikobjekte in einer API-Anfrage. Dimensionen und Metriken in derselben Sortierdefinition mischen. [Weitere Informationen](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim#multi-column-sorting) | | März 2026 |

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
* [Versionshinweise zur Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
