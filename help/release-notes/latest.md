---
title: Aktuelle Versionshinweise zu Customer Journey Analytics
description: Anzeigen der neuesten Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a16043f1bb15deba1332ed39438214597647b9b4
workflow-type: ht
source-wordcount: '956'
ht-degree: 100%

---

# Aktuelle Versionshinweise zu Customer Journey Analytics (Oktober 2025)

**Letztes Update**: 14. Oktober 2025

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum von Oktober bis Anfang November 2025. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **In Linienvisualisierungen und Sparklines enthaltene Filterkriterien** | Alle Suchfilterkriterien, die Sie auf einen Freiformtabellenfilter anwenden, sind jetzt immer in Sparklines enthalten. Darüber hinaus können Sie Suchfilterkriterien in jede verbundene Linienvisualisierung einbeziehen.<p>Sie können Linienvisualisierungen so konfigurieren, dass Suchfilterkriterien einbezogen werden, indem Sie die Sparkline in der Spaltenüberschrift der Metrik in der verbundenen Tabelle auswählen.</p><p>Zuvor waren Suchfilterkriterien nicht in Sparklines oder verbundenen Linienvisualisierungen enthalten.</p><p>Weitere Informationen finden Sie unter [Anzeigen von Trend-Daten für eine Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md).</p> | | &#x200B;15. Oktober 2025 |
| **Daten-Storytelling: Generieren von Folienpräsentationen aus Workspace-Berichten** | Sie können jetzt automatisch eine Folienpräsentation (im .pptx-Format) generieren, die auf einem Analysis Workspace-Bericht basiert. Workspace identifiziert wichtige Erkenntnisse in Ihrem Bericht und erstellt aus diesen für Stakeholder geeignete Folien.<p>Diese Funktion reduziert den Zeit- und Arbeitsaufwand für das Auffinden von Ergebnissen, das Erstellen von Zusammenfassungen für Führungskräfte und die Kommunikation der geschäftlichen Auswirkungen.</p><p>(Link zur Dokumentation folgt.)</p> | &#x200B;22. Oktober 2025 | Januar 2026 |
| **Echtzeit-Reporting** | Echtzeitberichte in Customer Journey Analytics zeigen Daten und Visualisierungen in einem oder mehreren Bedienfeldern in Analysis Workspace in Echtzeit an und aktualisieren diese.<br/><br/>(Link zur Dokumentation folgt.) | 18. September 2025 (Veröffentlichung ursprünglich für den 15. August 2025 geplant) | &#x200B;27. Oktober 2025 |
| **Unterstützung für Datenspiegelung** | Durch die Unterstützung modellbasierter Schemata und der Funktion zur Änderungsdatenerfassung (Change Data Capture, CDC) für bestimmte Quell-Connectoren in Experience Platform kann Customer Journey Analytics die Datenspiegelungsfunktion von Data-Warehouse-Lösungen wie [!DNL Snowflake], [!DNL Azure Databricks] und [!DNL Google BigQuery] unterstützen.<p>Wenden Sie sich an Ihr Adobe-Accountteam, um Zugriff auf die Beta-Version anzufordern.</p><p>(Link zur Dokumentation folgt.)</p> | Beta-Version: 24. September 2025 | TBD |
| **Zuordnung von Verbindungen** | Vereinfacht die Zuordnung in Customer Journey Analytics. Statt einen Datensatz zu duplizieren und eine Zuordnung zum duplizierten Datensatz vorzunehmen, wird die Zuordnung jetzt bei der Aufnahme von Daten in Customer Journey Analytics durchgeführt. Dadurch entfällt die Anforderung duplizierter Datensätze und Schemata. <p>Darüber hinaus können Sie jetzt die Zuordnung selbst über eine aktualisierte Verbindungs-Benutzeroberfläche starten, anstatt die Zuordnung über den Kunden-Support anfordern zu müssen.</p><p> *Die zuvor mitgeteilten Veröffentlichungstermine müssen aufgrund zusätzlicher erforderlicher Arbeiten verschoben werden. Da sich die neuen Veröffentlichungstermine mit der Urlaubssaison überschneiden, gibt es zusätzliche Einschränkungen bei der Veröffentlichung. Um Stabilität zu gewährleisten und Störungen während der Feiertage zu minimieren, ist nun ein schrittweises Rollout geplant.*</p> <p>(Link zur Dokumentation folgt.)</p> | &#x200B;28. Oktober 2025 | &#x200B;30. April 2026 |
| **Streaming-Mediendienste: Unterstützung von Zeitplandaten** | Sie können jetzt Zeitplandaten von früheren Live-Inhalten von Streaming-Medien hochladen, um die Zuschauerzahlen einfacher und genauer zu verfolgen.<p>Im Folgenden finden Sie Beispiele für Live-Inhalte, die mit dem Upload von Zeitplandaten unterstützt werden:</p><ul><li>FAST-Plattformen (Free Ad Supported TV)</li><li>Lokale Datenströme</li><li>Live-Sportübertragungen</li></ul><p>Durch das Hochladen von Zeitplandaten können Sie die Zuschauerzahlen für einzelne Programme verfolgen, die in dem von Ihnen in der Upload-Datei angegebenen Zeitraum gelaufen sind. Sie können sogar Zuschauerzahlen für bestimmte Themen oder Programmsegmente erfassen.</p><p>Diese Funktionen sind unabhängig davon verfügbar, wie Sie die Erfassung von Streaming-Medien implementiert haben.</p><p>Zuvor war es bei der Analyse von Live-Inhalten schwierig, eine bestimmte Sitzung genau mit bestimmten Programmen zu verknüpfen, und es war nicht möglich, eine bestimmte Sitzung mit einzelnen Themen oder Programmsegmenten zu verknüpfen.</p><p>(Link zur Dokumentation folgt.)<!--For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)--></p> |  | &#x200B;29. Oktober 2025 |
| **Analytics-Quell-Connector: Suchen von Report Suites in Experience Platform** | Kundinnen und Kunden mit vielen Report Suites können jetzt im Datenfluss-Workflow des Analytics-Quell-Connectors nach der Report Suite suchen, mit der sie eine Verbindung herstellen möchten. <p>Zuvor mussten Kundinnen und Kunden eine potenziell lange Liste von Report Suites durchsuchen.</p><p>(Link zur Dokumentation folgt.) | | &#x200B;30. Oktober 2025 |
| **Streaming-Medien: Aktualisierte XDM-Felder zum Sammeln von Streaming-Mediendaten in Adobe Experience Platform** | Beim Erfassen von Streaming-Mediendaten in Adobe Experience Platform sollten die XDM-Feldpfade unter der Überschrift „XDM-Feldpfad“ in der Dokumentation zu den Streaming-Medienparametern nicht mehr verwendet werden. Stattdessen müssen Kundinnen und Kunden, die den Analytics-Quell-Connector vor dem 9. Mai 2025 implementiert haben, um Streaming-Mediendaten in Platform zu erfassen, ihre vorhandenen Konfigurationen in die mediaReporting-Feldpfade migrieren, wie unter der Überschrift „XDM-Feldpfad für Berichterstellung“ der Dokumentation zu Streaming-Medienparametern gezeigt.<p> Diese Feldpfade befinden sich auf den folgenden Seiten und sind als „veraltet“ gekennzeichnet: [Audio- und Videoparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Anzeigenparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/ad-parameters), [Kapitelparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/chapter-parameters), [Player-Statusparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/player-state-parameters) und [Qualitätsparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/quality-parameters). (Bei Kundinnen und Kunden, die den Analytics-Quell-Connector nach dem 9. Mai 2025 implementiert haben und bereits nur XDM-Pfade für mediaReporting verwenden, ist keine Aktion erforderlich.)</p><p>Die Datenaufnahme über die veralteten XDM-Feldpfade wird noch bis Ende Oktober 2025 fortgesetzt. Danach werden die veralteten Felder vollständig entfernt und nicht mehr in der Schema-Benutzeroberfläche von Adobe Experience Platform angezeigt. Daten werden nur mithilfe der mediaReporting-Feldpfade gesendet.</p><p>Weitere Informationen finden Sie unter [Migrieren einer Analytics-Quell-Connector-Implementierung zu aktualisierten XDM-Streaming-Medien-Feldern](https://experienceleague.adobe.com/de/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Wenden Sie sich an Ihren Adobe Consulting-Dienst oder Ihr Konto-Team, um Unterstützung bei der Migration zu erhalten. </p> |  | Oktober 2025 |

## Fehlerbehebungen in Customer Journey Analytics

**Analysis Workspace**: AN-400507, AN-400265, AN-399209, AN-397146, AN-394992, AN-390795
**Komponenten**:
**Inhaltsanalyse**:
**Exporte**: AN-399012, AN-388578
**Geführte Analyse**:
**Implementierung**: AN-397551, AN-397550, AN-397190, AN-396127
**Report Builder**: AN-401127, AN-400618, AN-392971, AN-391692
**Reporting**:
**Segmentierung**:
**Geplante Berichte**:
**Freigegebene Metriken und Dimensionen**:
**Sonstiges**:


## Wichtige Hinweise für Customer Journey Analytics-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| k. A. | | |

## Verwandte Ressourcen

* [Frühere Versionshinweise für Customer Journey Analytics 2025](/help/release-notes/2025.md)
* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
* [Versionshinweise zur Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
