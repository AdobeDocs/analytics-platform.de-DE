---
title: Aktuelle Versionshinweise zu Customer Journey Analytics
description: Anzeigen der neuesten Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: ea699bcacd985d9da1e3895f7770290dc77da537
workflow-type: tm+mt
source-wordcount: '951'
ht-degree: 48%

---

# Aktuelle Customer Journey Analytics Versionshinweise (Januar 2026)

**Letzte Aktualisierung:** Donnerstag, 14. Januar 2026

Diese Versionshinweise gelten für den Veröffentlichungszeitraum Januar 2026. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysieren Sie Zielgruppen aus Experience Platform Profile-Datensätzen in Customer Journey Analytics** | Sie können jetzt Zielgruppe Abonnement Daten aus Experience Platform Profile-Datensätzen in eine Customer Journey Analytics Verbindung aufnehmen. Audiences stehen als neue Dimensionen zur Verwendung in Analysis Workspace zur Verfügung.<p>Möglich wird dies durch eine neue Funktion in Customer Journey Analytics, XDM Objektkarten zu erfassen, die es ermöglicht, Profil-AudienceIDs aufzunehmen.</p><p>Zuvor konnten nur einfache XDM Karten in Customer Journey Analytics aufgenommen werden.</p><p>Neben der Möglichkeit, Zielgruppe Daten als Dimensionen zu einem beliebigen Projekt in Analysis Workspace hinzuzufügen, sind auch die folgenden neuen Arbeitsbereich Vorlagen verfügbar:</p><ul><li>Übersicht über Audience Analytics</li><li>Übersicht über die Einwilligungsrichtlinie</li><p><!--For more information, see "Audience analysis overview" (https://experienceleague.corp.adobe.com/docs/analytics-platform/using/cja-dataviews/audience-analysis/audience-analysis-overview.html).-->(Link zur Dokumentation folgt.)</p> | &#x200B;22. Oktober 2025 | Freitag, 22. Januar 2026 |
| **Daten-Storytelling: Generieren von Folienpräsentationen aus Workspace-Berichten** | Sie können jetzt automatisch eine Folienpräsentation (im .pptx-Format) generieren, die auf einem Analysis Workspace-Bericht basiert. Workspace identifiziert wichtige Erkenntnisse in Ihrem Bericht und erstellt aus diesen für Stakeholder geeignete Folien.<p>Diese Funktion reduziert den Zeit- und Arbeitsaufwand für das Auffinden von Ergebnissen, das Erstellen von Zusammenfassungen für Führungskräfte und die Kommunikation der geschäftlichen Auswirkungen.</p><p>(Link zur Dokumentation folgt.)<!--For more information, see [Data storytelling: Generate slide presentations from Workspace reports](/help/analysis-workspace/curate-share/generate-slides.md).--></p> | &#x200B;22. Oktober 2025 | Donnerstag, 28. Januar 2026 |
| **Mehrere Dimension Spalten in eine Freiformtabelle einbeziehen** | Sie können jetzt bis zu 5 Dimension Spalten in eine Freiformtabelle einbeziehen, sodass Sie mehrere Dimension Elemente nebeneinander Ansicht können. Jede Zeile Dimension Elements verhält sich liken ein einzelnes verkettetes Dimension Element.<p>Sie können Filter, Sortierung, Aufschlüsselungen und mehr auf Freiformtabellen mit mehreren Dimension Spalten anwenden, um eine tiefere und benutzerdefiniertere Analyse zu erstellen.</p><p>Früher konnten Sie nur 1 Dimension Spalte in eine Freiformtabelle einfügen.</p><p><!-- For more information, see [Include multiple dimension columns in a freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md).--> (Link zur Dokumentation folgt.)</p> | Donnerstag, 28. Januar 2026 | Donnerstag, 18. Februar 2026 |
| **Sortieren von Tabellen nach mehreren Spalten** | Sie können nun die Daten einer Freiformtabelle nach mehreren Spalten in Analysis Workspace sortieren, unabhängig davon, ob es sich um Dimensionen oder Metriken handelt.<p>Wenn Sie Daten für mehrere Spalten sortieren, werden die Daten entsprechend der Priorität sortiert, die Sie den einzelnen Spalten zuweisen. Priorität Nummerierung wird neben dem Sortiersymbol angezeigt.</p><p>(Link zur Dokumentation folgt.)<!-- For more information, see "Filter and sort freeform tables". (need to move info to this article from "Include multiple dimension columns in a freeform table") --></p> | Donnerstag, 28. Januar 2026 | Donnerstag, 18. Februar 2026 |
| **Datenquellen aus mehreren IMS-Organisationen kombinieren** | Mit dem Analytics Quelle Connector können Sie jetzt mehrere Datenquellen aus mehreren IMS-Organisationen kombinieren. Auf diese Weise können Organisationen über eine kombinierte Ansicht ihrer Kundendaten verfügen, Linear, wenn diese Kundendaten auf mehrere IMS-Organisationen verteilt sind. <p>**Hinweis:** Diese Konfiguration ist nur verfügbar, wenn Sie eine Anfrage an Adobe Systems Kundenunterstützung senden.</p>  <p>(Link zur Dokumentation folgt.)</p> |  | Samstag, 30. Januar 2026 |
| **Zuordnung von Verbindungen** | Der Stitching-Prozess in Customer Journey Analytics ist jetzt einfacher. Statt einen Datensatz zu duplizieren und eine Zuordnung zum duplizierten Datensatz vorzunehmen, wird die Zuordnung jetzt bei der Aufnahme von Daten in Customer Journey Analytics durchgeführt. Dadurch entfällt die Anforderung duplizierter Datensätze und Schemata. <p>Darüber hinaus können Sie das Stitching jetzt [selbst über eine aktualisierte Connections-Oberfläche](/help/stitching/use-stitching-ui.md) initiieren, anstatt das Stitching über Adobe Systems Kundenunterstützung Anfrage zu müssen.</p><p> *Die zuvor kommunizierten Veröffentlichungstermine wurden aufgrund des zusätzlichen Aufwands und der Weihnachtszeit verschoben. Um Stabilität zu gewährleisten und Störungen während der Feiertage zu minimieren, ist nun ein schrittweises Rollout geplant.*</p> | &#x200B;28. Oktober 2025 | Samstag, 30. Januar 2026 |
| **Unterstützung für Datenspiegelung** | Durch die Unterstützung modellbasierter Schemata und der Funktion zur Änderungsdatenerfassung (Change Data Capture, CDC) für bestimmte Quell-Connectoren in Experience Platform kann Customer Journey Analytics die [Datenspiegelungsfunktion](/help/data-mirror/data-mirror.md) von Data-Warehouse-Lösungen wie [!DNL Snowflake], [!DNL Azure Databricks] und [!DNL Google BigQuery] unterstützen.<p>Wenden Sie sich an Ihr Adobe-Accountteam, um Zugriff auf die Beta-Version anzufordern.</p> | Beta-Version: 24. September 2025 | TBD |
| **Streaming-Mediendienste: Unterstützung von Zeitplandaten** | Sie können jetzt Zeitplandaten von früheren Live-Inhalten von Streaming-Medien hochladen, um die Zuschauerzahlen einfacher und genauer zu verfolgen.<p>Im Folgenden finden Sie Beispiele für Live-Inhalte, die mit dem Upload von Zeitplandaten unterstützt werden:</p><ul><li>FAST-Plattformen (Free Ad Supported TV)</li><li>Lokale Datenströme</li><li>Live-Sportübertragungen</li></ul><p>Durch das Hochladen von Zeitplandaten können Sie die Zuschauerzahlen für einzelne Programme verfolgen, die in dem von Ihnen in der Upload-Datei angegebenen Zeitraum gelaufen sind. Sie können sogar Zuschauerzahlen für bestimmte Themen oder Programmsegmente erfassen.</p><p>Diese Funktionen sind unabhängig davon verfügbar, wie Sie die Erfassung von Streaming-Medien implementiert haben.</p><p>Zuvor war es bei der Analyse von Live-Inhalten schwierig, eine bestimmte Sitzung genau mit bestimmten Programmen zu verknüpfen, und es war nicht möglich, eine bestimmte Sitzung mit einzelnen Themen oder Programmsegmenten zu verknüpfen.</p><p>Weitere Informationen finden Sie unter [Hochladen von Zeitplandaten zum Nachverfolgen von Live-Inhalten](https://experienceleague.adobe.com/de/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | &#x200B;29. Oktober 2025 | Erstes Halbjahr 2026<p>(Veröffentlichung ursprünglich für den 29. Oktober 2025 geplant)</p> |

## Fehlerbehebungen in Customer Journey Analytics

**Analysis Workspace**: AN-423389, AN-423316, AN-422636, AN-422482, AN-422121, AN-422116, AN-422027, AN-421134, AN-420187, AN-406271, AN-406188, AN-405997, AN-405983, AN-405796, AN-405033, AN-404893, AN-40487 1, AN-404842, AN-404713, AN-404502, AN-404353, AN-404352, AN-404048, AN-403241, AN-402523, AN-400795, AN-396149, AN-390990, AN-390646, AN-383484, AN-376980, AN-371729, AN-347570, AN-404835
**Komponenten**:
**Inhalt Analytics**:
**Geführter Analyse**: AN-421274
**Exporte**:
**Daten Ansichten**: AN-421891, AN-404627
**Umsetzung**:
**Report Builder**: AN-422120, AN-421937, AN-406296, AN-402951, AN-399748
**Berichterstattung**:
**Segmentierung**:
**Geplante Berichte**: AN-423087, AN-422686
**Freigegebene Metriken und Dimensionen**:
**Andere**: AN-422946, AN-422775, AN-422273, AN-422100, AN-420045, AN-404891, AN-390912


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
