---
title: Aktuelle Versionshinweise zu Customer Journey Analytics
description: Anzeigen der neuesten Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 795fbac85fbd57fa503bd1f56fe6dc325201f733
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 44%

---

# Aktuelle Versionshinweise zu Customer Journey Analytics (Januar 2026)

**Letzte Aktualisierung:** Dienstag, 2. Februar 2026

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom Januar 2026. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Überschreibungen der Kopfzeile** | In Content Analytics können Sie den Kopfzeilennamen und den geheimen Kopfzeilenwert angeben.  Dieser [Header überschreibt die Konfiguration](/help/content-analytics/config/guided.md#header-overrides) stellt sicher, dass Content Analytics benutzerdefinierte HTTP-Header sendet, um alle implementierten Bot-Erkennungs- oder Gate-Traffic-Technologien zu umgehen. |  | Dienstag, 2. Februar 2026 |
| **Analysieren von Zielgruppen aus Experience Platform-Profildatensätzen in Customer Journey Analytics** | Sie können jetzt Zielgruppenzugehörigkeitsdaten aus Experience Platform-Profildatensätzen in eine Customer Journey Analytics-Verbindung aufnehmen. Zielgruppen werden als neue Dimensionen zur Verwendung in Analysis Workspace verfügbar.<p>Dies wird durch eine neue Funktion in Customer Journey Analytics ermöglicht, mit der XDM-Objektzuordnungen aufgenommen werden können, wodurch es möglich wird, Profil-Zielgruppen-IDs aufzunehmen.</p><p>Zuvor konnten nur einfache XDM-Zuordnungen in Customer Journey Analytics aufgenommen werden.</p><p>Neben der Möglichkeit, Zielgruppendaten als Dimensionen zu jedem Projekt in Analysis Workspace hinzuzufügen, sind auch die folgenden neuen Workspace-Vorlagen verfügbar:</p><ul><li>Übersicht über Audience Analytics</li><li>Übersicht über die Einverständnisrichtlinie</li></ul><p>Weitere Informationen finden Sie unter [Übersicht über die Zielgruppenanalyse](/help/connections/audience-analysis/audience-analysis-overview.md).</p> | &#x200B;22. Oktober 2025 | Freitag, 22. Januar 2026 |
| **Daten-Storytelling: Generieren von Folienpräsentationen aus Workspace-Berichten** | Sie können jetzt automatisch eine Folienpräsentation (im .pptx-Format) generieren, die auf einem Analysis Workspace-Bericht basiert. Workspace identifiziert wichtige Erkenntnisse in Ihrem Bericht und erstellt aus diesen für Stakeholder geeignete Folien.<p>Diese Funktion reduziert den Zeit- und Arbeitsaufwand für das Auffinden von Ergebnissen, das Erstellen von Zusammenfassungen für Führungskräfte und die Kommunikation der geschäftlichen Auswirkungen.</p><p>Weitere Informationen finden Sie unter [Daten-Storytelling: Generieren von Folien-Präsentationen aus Workspace-Berichten](/help/analysis-workspace/curate-share/generate-slides.md).</p> | &#x200B;22. Oktober 2025 | Donnerstag, 28. Januar 2026 |
| **Mehrere Dimensionsspalten in eine Freiformtabelle einbeziehen** | Sie können jetzt bis zu 5 Dimensionsspalten in eine Freiformtabelle einbeziehen, sodass Sie mehrere Dimensionselemente nebeneinander anzeigen können. Jede Reihe von Dimensionselementen verhält sich wie ein einzelnes verkettetes Dimensionselement.<p>Sie können Filter, Sortierung, Aufschlüsselungen und mehr auf Freiformtabellen mit mehreren Dimensionsspalten anwenden, um eine tiefere und benutzerspezifischere Analyse zu erstellen.</p><p>Zuvor konnten Sie nur eine Dimensionsspalte in eine Freiformtabelle einbeziehen.</p><p>Weitere Informationen finden Sie unter [Mehrere Dimensionsspalten in eine Freiformtabelle einbeziehen](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md).</p> | Donnerstag, 28. Januar 2026 | Donnerstag, 18. Februar 2026 |
| **Sortieren von Tabellen nach mehreren Spalten** | Sie können jetzt die Daten einer Freiformtabelle in Analysis Workspace nach mehreren Spalten sortieren, unabhängig davon, ob es sich um Dimensionen oder Metriken handelt.<p>Wenn Sie Daten für mehrere Spalten sortieren, werden die Daten nach der Priorität sortiert, die Sie jeder Spalte zuweisen. Die Prioritätsnummerierung wird neben dem Sortiersymbol angezeigt.</p><p>Weitere Informationen finden Sie unter [Freiformtabellen filtern und sortieren](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).</p> | Donnerstag, 28. Januar 2026 | Donnerstag, 18. Februar 2026 |
| **Kombinieren Sie Datenquellen aus mehreren IMS-Organisationen** | Sie können jetzt den Analytics Source Connector verwenden, um mehrere Datenquellen aus mehreren IMS-Organisationen zu kombinieren. Auf diese Weise können Unternehmen eine kombinierte Ansicht ihrer Kundendaten erhalten, selbst wenn diese Kundendaten über mehrere IMS-Organisationen verteilt sind. <p>**Hinweis:** Diese Konfiguration ist nur verfügbar, wenn Sie eine Anfrage an die Adobe-Kundenunterstützung senden.</p>  <p>(Link zur Dokumentation folgt.)</p> |  | Samstag, 30. Januar 2026 |
| **Zuordnung von Verbindungen** | Der Zuordnungsprozess in Customer Journey Analytics ist jetzt einfacher. Statt einen Datensatz zu duplizieren und eine Zuordnung zum duplizierten Datensatz vorzunehmen, wird die Zuordnung jetzt bei der Aufnahme von Daten in Customer Journey Analytics durchgeführt. Dadurch entfällt die Anforderung duplizierter Datensätze und Schemata. <p>Darüber hinaus [&#x200B; Sie das Zusammenfügen über eine aktualisierte Verbindungsschnittstelle initiieren](/help/stitching/use-stitching-ui.md) anstatt das Zusammenfügen über die Adobe-Kundenunterstützung anfordern zu müssen. | &#x200B;28. Oktober 2025 | Samstag, 30. Januar 2026 |
| **Unterstützung für Datenspiegelung** | Durch die Unterstützung modellbasierter Schemata und der Funktion zur Änderungsdatenerfassung (Change Data Capture, CDC) für bestimmte Quell-Connectoren in Experience Platform kann Customer Journey Analytics die [Datenspiegelungsfunktion](/help/data-mirror/data-mirror.md) von Data-Warehouse-Lösungen wie [!DNL Snowflake], [!DNL Azure Databricks] und [!DNL Google BigQuery] unterstützen.<p>Wenden Sie sich an Ihr Adobe-Accountteam, um Zugriff auf die Beta-Version anzufordern.</p> | Beta-Version: 24. September 2025 | TBD |
| **Streaming-Mediendienste: Unterstützung von Zeitplandaten** | Sie können jetzt Zeitplandaten von früheren Live-Inhalten von Streaming-Medien hochladen, um die Zuschauerzahlen einfacher und genauer zu verfolgen.<p>Im Folgenden finden Sie Beispiele für Live-Inhalte, die mit dem Upload von Zeitplandaten unterstützt werden:</p><ul><li>FAST-Plattformen (Free Ad Supported TV)</li><li>Lokale Datenströme</li><li>Live-Sportübertragungen</li></ul><p>Durch das Hochladen von Zeitplandaten können Sie die Zuschauerzahlen für einzelne Programme verfolgen, die in dem von Ihnen in der Upload-Datei angegebenen Zeitraum gelaufen sind. Sie können sogar Zuschauerzahlen für bestimmte Themen oder Programmsegmente erfassen.</p><p>Diese Funktionen sind unabhängig davon verfügbar, wie Sie die Erfassung von Streaming-Medien implementiert haben.</p><p>Zuvor war es bei der Analyse von Live-Inhalten schwierig, eine bestimmte Sitzung genau mit bestimmten Programmen zu verknüpfen, und es war nicht möglich, eine bestimmte Sitzung mit einzelnen Themen oder Programmsegmenten zu verknüpfen.</p><p>Weitere Informationen finden Sie unter [Hochladen von Zeitplandaten zum Nachverfolgen von Live-Inhalten](https://experienceleague.adobe.com/de/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | &#x200B;29. Oktober 2025 | Erstes Halbjahr 2026<p>(Veröffentlichung ursprünglich für den 29. Oktober 2025 geplant)</p> |

## Fehlerbehebungen in Customer Journey Analytics

**Analysis Workspace**: AN-423389, AN-423316, AN-422636, AN-422482, AN-422121, AN-422116, AN-422027, AN-421134, AN-420187, AN-406271, AN-406188, AN-404893, AN-405997, AN-405983, AN-404871, AN-404842, AN-405796, AN-405033, AN-404713, AN-404502, AN-404353, AN-404352, AN-404048, AN-403241, AN-402523, AN-400795, AN-396149, AN-390990, AN-390646 383484 376980 371729 347570 404835
**Komponenten**:
**Content Analytics**:
**Geführte Analyse**: AN-421274
**Exporte**:
**Datenansichten**: AN-421891, AN-404627
**Implementierung**:
**Report Builder**: AN-422120, AN-421937, AN-406296, AN-402951, AN-399748
**Reporting**:
**Segmentierung**:
**Terminierte Berichte**: AN-423087, AN-422686
**Freigegebene Metriken und Dimensionen**:
**Sonstige**: AN-422946, AN-422775, AN-422273, AN-422100, AN-420045, AN-404891, AN-390912


## Wichtige Hinweise für Customer Journey Analytics-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| k. A. |  |  |

## Verwandte Ressourcen

* [Frühere Versionshinweise für Customer Journey Analytics 2025](/help/release-notes/2025.md)
* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
* [Versionshinweise zur Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
