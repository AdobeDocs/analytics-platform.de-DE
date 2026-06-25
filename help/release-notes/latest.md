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
source-git-commit: 8cdfe0db0aabba05fbebe7d9215182e0fca31d66
workflow-type: tm+mt
source-wordcount: 615
ht-degree: 44%

---

# Aktuelle Versionshinweise zu Customer Journey Analytics (Juni 2026)

**Letzte Aktualisierung**: 25. Juni 2026

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom Juni 2026. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion und Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| -----------|-----------|-----------|
| **Data Mirror** <br/>[Data Mirror](/help/data-mirror/data-mirror.md) ist eine Experience Platform-Funktion, die die Änderungsaufnahme (Change Data Capture) auf Zeilenebene von externen Data Warehouse-Lösungen ([!DNL Snowflake], [!DNL Azure Databricks] und [!DNL Google BigQuery]) in Customer Journey Analytics mithilfe relationaler Schemata ermöglicht. Sie behält Datenbeziehungen bei, erzwingt Eindeutigkeit und unterstützt die Versionierung, ohne dass ETL-Prozesse (Upstream Extract, Transform, Load) erforderlich sind. | &#x200B;25. März 2026 | &#x200B;17. Juni 2026 |
| **Überprüfen Ihrer Daten im KI** Assistenten<br/>Sie können den KI-Assistenten verwenden, um [die Datenqualität Ihrer Adobe Experience Platform-Datensätze zu überprüfen](https://experienceleague.adobe.com/de/docs/experience-cloud-ai/experience-cloud-ai/agents/data-validation). Basierend auf Agent Orchestrator kann die Datenvalidierungsfunktion statistische und semantische Validierungen für Datensätze durchführen, Datensatzfelder analysieren, Datenqualitätsprobleme identifizieren und Zusammenfassungen natürlicher Sprachen mit umsetzbaren Einblicken zurückgeben. | | &#x200B;22. Juni 2026 |

### Fehlerbehebungen in Customer Journey Analytics

**Analysis Workspace**: AN-456858, AN-455865, AN-455706, AN-455592, AN-455484, AN-455180, AN-454999, AN-454170, AN-454145, AN-453793, AN-452921, AN-451643, AN-451600, AN-451525, AN-452009, AN-451477, AN-451262, AN-451958, AN-451161, AN-450772, AN-443594, AN-AN-434416, AN-AN-ALL, AN-AN-US
**Komponenten**:
**Verbindungen**: AN-457065, AN-453705
**Content Analytics**: AN-451203, AN-447596
**Geführte Analyse**:
**Exporte**: AN-452006, AN-451989, AN-440567
**Datenansichten**: AN-451198
**Implementierung**:
**Report Builder**: AN-440912, AN-457586, AN-457533, AN-455713, AN-455623, AN-455063, AN-454512, AN-454053, AN-453977, AN-453781, AN-453683, AN-451731, AN-451190, AN-449813, AN-451974, AN-447173, AN-447139, AN-451735, AN-446184, AN-445794, AN-445354, AN-AN-442819, AN-AN-ALL, AN-AN-US
**Reporting**: AN-454589, AN-454517, AN-453982, AN-451822, AN-451497, AN-451463, AN-451259, AN-451215, AN-450661, AN-447699, AN-448375, AN-447692
**Segmentierung**:
**Terminierte Berichte**: AN-451980, AN-451882, AN-450715
**Freigegebene Metriken und Dimensionen**:
**Zielgruppenanalyse**: AN-449656, AN-450400
**Sonstige**: AN-457063, AN-454140, AN-453937, AN-453825, AN-452959, AN-452934, AN-452296, AN-451781, AN-450974

## Zurückgestellte Funktionen

| Funktion und Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| -----------|-----------|-----------|
| **Streaming-Mediendienste: Unterstützung von Zeitplandaten** <br/>Sie können jetzt Zeitplandaten von früheren Live-Inhalten von Streaming-Medien hochladen, um Zuschauerzahlen einfacher und genauer zu verfolgen.<p>Im Folgenden finden Sie Beispiele für Live-Inhalte, die mit dem Upload von Zeitplandaten unterstützt werden:</p><ul><li>FAST-Plattformen (Free Ad Supported TV)</li><li>Lokale Datenströme</li><li>Live-Sportübertragungen</li></ul><p>Durch das Hochladen von Zeitplandaten können Sie die Zuschauerzahlen für einzelne Programme verfolgen, die in dem von Ihnen in der Upload-Datei angegebenen Zeitraum gelaufen sind. Sie können sogar Zuschauerzahlen für bestimmte Themen oder Programmsegmente erfassen.</p><p>Diese Funktionen sind unabhängig davon verfügbar, wie Sie die Erfassung von Streaming-Medien implementiert haben.</p><p>Zuvor war es bei der Analyse von Live-Inhalten schwierig, eine bestimmte Sitzung genau mit bestimmten Programmen zu verknüpfen, und es war nicht möglich, eine bestimmte Sitzung mit einzelnen Themen oder Programmsegmenten zu verknüpfen.</p><p>Weitere Informationen finden Sie unter [Hochladen von Zeitplandaten zum Nachverfolgen von Live-Inhalten](https://experienceleague.adobe.com/de/docs/media-analytics/using/media-use-cases/track-schedule-data) | &#x200B;29. Oktober 2025 | TBD<p>(Ursprünglich für den 29. Oktober 2025 geplant)</p> |

>[!MORELIKETHIS]
>
>* [Frühere Versionshinweise zu Customer Journey Analytics für 2026](/help/release-notes/2026.md)
>* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
>* [Versionshinweise zur Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
>* [CX Enterprise - Versionshinweise](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
>* [Aktualisierungen der Dokumentation zu Customer Journey Analytics](/help/release-notes/doc-changes.md)
