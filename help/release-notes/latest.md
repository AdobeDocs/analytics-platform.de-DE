---
title: Aktuelle Versionshinweise zu Customer Journey Analytics
description: Sehen Sie sich die neuesten Customer Journey Analytics-Versionshinweise an, einschließlich neuer Funktionen, behobener Probleme und verschobener Versionen für den aktuellen Zeitraum.
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: 'https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
    internal-label: Templates
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
    internal-label: Content Analytics
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
    internal-label: Filters
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
    internal-label: Audiences
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
    internal-label: Connections
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
    internal-label: Freeform tables
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
  - id: a8e39571-4463-4aa3-8b3f-4e2341ecf3b3
    internal-label: Release notes
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 0a83f4d08806b4d9b97265989f9d687011b232c3
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 28%
---
# Aktuelle Customer Journey Analytics-Versionshinweise (Oktober 2026)

**Letzte Aktualisierung**: 7. Oktober 2026

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom Oktober 2026. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion und Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| -----------|-----------|-----------|
| **Schreibgeschützte Berechtigung für den Customer Journey Analytics MCP-Server**<br/> Administratoren können Benutzenden jetzt schreibgeschützten Zugriff auf den Customer Journey Analytics MCP-Server gewähren. Das neue [!UICONTROL MCP Read Only]-Berechtigungselement bietet Benutzern Zugriff auf alle schreibgeschützten Tools, ohne dass sie Projekte, Segmente oder berechnete Metriken erstellen können.<p>Das vorhandene [!UICONTROL MCP-]-Berechtigungselement wird in &quot;[!UICONTROL -Vollzugriff“ ]. Benutzende mit dieser Berechtigung behalten Zugriff auf alle Tools, einschließlich Tools zum Erstellen, Ändern oder Löschen von Komponenten.</p><p>Weitere Informationen finden Sie unter [Customer Journey Analytics MCP-Server](https://developer.adobe.com/analytics-mcp/docs/cja/).</p> | | &#x200B;6. Oktober 2026 |
| **Analysieren von LLM-Kundenerlebnissen in Analysis Workspace mit Conversation Insights**<br/> Customer Journey Analytics bringt jetzt unstrukturierte Chat-Daten in Analysis Workspace ein, sodass Sie Berichte über LLM-gestützte Browser- und Kauferlebnisse in Ihren Properties erstellen können.<p>Mit dieser Funktion können Sie:</p><ul><li>Sammeln Sie Eingabeaufforderungen, Antworten und Agentenmetadaten von Gesprächsagenten (entweder den benutzerdefinierten Agenten Ihres Unternehmens oder Adobe Brand Concierge) über Web SDK.</li><li>Analysieren Sie Absicht, Tonfall und Sentiment, damit Sie verstehen können, was Kunden fragen, wie Ihr Agent reagiert und wie Ihre Kunden über ihre Interaktionen denken.</li><li>Analysieren Sie im benötigten Umfang anhand Ihres vorhandenen Schemas, Ihrer Datensätze und Datenansichten und nutzen Sie dann die Gelegenheit, Einblicke in Analysis Workspace zu gewinnen.</li><li>Verknüpfen Sie Konversationen mit Ergebnissen, indem Sie Agenteninteraktionen mit Ihren allgemeinen Journey-Kunden verknüpfen, damit Sie echte Auswirkungen auf Konversion, Interaktion und mehr messen können.</li></ul><p>Zuvor waren LLM-gestützte Erlebnisse schwer zu messen und es war nahezu unmöglich, eine Verbindung zu den Journey-Systemen Ihrer bestehenden Kunden herzustellen.</p><p>Weitere Informationen finden Sie unter [Konversationseinblicke](/help/conversation-insights/overview.md).</p> | | &#x200B;8. Oktober 2026<p>(Ursprünglich für den 22. September 2026 geplant)</p> |
| **Komponentenbeschreibungen automatisch generieren** <br/>Sie können jetzt automatisch Beschreibungen für Dimensionen, Metriken, berechnete Metriken, Segmente und Datumsbereiche generieren. Auf diese Weise können Workspace-Benutzende verstehen, welche Komponenten verwendet werden sollen, insbesondere in Organisationen mit großen Komponentenbibliotheken. <p>Sie können für eine einzelne Komponente eine Beschreibung oder für viele Komponenten gleichzeitig Beschreibungen erstellen.</p> <p>(Link zur Dokumentation folgt.)<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | &#x200B;28. Oktober 2026 |
| **Adobe Brand Visibility-Integration**<br/> Verbinden Sie Adobe Brand Visibility mit den Customer Journey Analytics-Daten Ihres Unternehmens, damit Sie messen können, wie sich die KI-gesteuerte Erkennung in echte Website-Interaktion und Geschäftsergebnisse niederschlägt.<p>(Link zur Dokumentation folgt.)</p> | | Oktober 2026 |


### Fehlerbehebungen in Customer Journey Analytics

**Analysis Workspace**: AN-495340, AN-494789, AN-493307, AN-468900
**Komponenten**: AN-492523
**Verbindungen**: AN-492236
**Content Analytics**:
**Geführte Analyse**: AN-495592
**EXPORTE**: AN-495077, AN-494337, AN-486563, AN-469919, AN-462560, AN-462372
**Datenansichten**: AN-492093, AN-467770, AN-455367, AN-444467
**Datenaufnahme**: AN-496439, AN-495339, AN-493456, AN-491984, AN-490515, AN-490479, AN-470065
**Implementierung**:
**Report Builder**: AN-496602, AN-494224, AN-493737, AN-493508, AN-493505, AN-492806, AN-468981, AN-454376
**Reporting**: AN-495661, AN-493562, AN-487058, AN-478768
**Segmentierung**:
**Terminierte Berichte**: AN-491103, AN-468049
**Freigegebene Metriken und Dimensionen**: AN-493722
**Zielgruppenanalyse**: AN-469101
**Sonstige**: AN-493865

## Zurückgestellte Funktionen

| Funktion und Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| -----------|-----------|-----------|
| **Berichte zur Gesamtpopulation**<br/> Sie können jetzt in Profil- und Lookup-Datensätzen definierte Entitäten analysieren und Berichte dazu erstellen, die in einer Customer Journey Analytics-Verbindung vorhanden sind. Diese Analyse und das Reporting gehen über zeitbasierte Ereignisreihen aus Ereignisdatensätzen hinaus. <p>Diese Funktion ermöglicht neue Klassen von Abfragen, Metriken und Zielgruppendefinitionen, die den gesamten Umfang des Kundenstamms eines Unternehmens widerspiegeln.</p><p>(Link zur Dokumentation folgt.)</p> | | TBD<p>(Ursprünglich für den 22. September 2026 geplant)</p> |
| **Streaming-Mediendienste: Unterstützung von Zeitplandaten** <br/>Sie können jetzt Zeitplandaten von früheren Live-Inhalten von Streaming-Medien hochladen, um Zuschauerzahlen einfacher und genauer zu verfolgen.<p>Im Folgenden finden Sie Beispiele für Live-Inhalte, die beim Hochladen von Zeitplandaten unterstützt werden:</p><ul><li>FAST-Plattformen (Free Ad-Supported TV)</li><li>Lokale Datenströme</li><li>Live-Sportübertragungen</li></ul><p>Durch das Hochladen von Zeitplandaten können Sie die Zuschauerzahlen für einzelne Programme verfolgen, die in dem von Ihnen in der Upload-Datei angegebenen Zeitraum gelaufen sind. Sie können sogar Zuschauerzahlen für bestimmte Themen oder Programmsegmente erfassen.</p><p>Diese Funktionen sind unabhängig davon verfügbar, wie Sie die Erfassung von Streaming-Medien implementiert haben.</p><p>Zuvor war es bei der Analyse von Live-Inhalten schwierig, eine bestimmte Sitzung genau mit bestimmten Programmen zu verknüpfen, und es war nicht möglich, eine bestimmte Sitzung mit einzelnen Themen oder Programmsegmenten zu verknüpfen.</p><p>Weitere Informationen finden Sie unter [Hochladen von Zeitplandaten zur Verfolgung von Live-Inhalten](https://experienceleague.adobe.com/de/docs/media-analytics/using/media-use-cases/track-schedule-data).</p> | &#x200B;29. Oktober 2025 | TBD<p>(Ursprünglich für den 29. Oktober 2025 geplant)</p> |

>[!MORELIKETHIS]
>
>* [Frühere Versionshinweise zu Customer Journey Analytics für 2026](/help/release-notes/2026.md)
>* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
>* [Versionshinweise zur Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
>* [Versionshinweise zu CX Enterprise](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
>* [Aktualisierungen der Dokumentation zu Customer Journey Analytics](/help/release-notes/doc-changes.md)

