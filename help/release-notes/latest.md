---
title: Aktuelle Versionshinweise zu Customer Journey Analytics
description: Anzeigen der neuesten Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4cea79a6ba26a2e4f06bfc9c60fdfc03341a7d60
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 93%

---

# Aktuelle Versionshinweise zu Customer Journey Analytics (September 2025)

**Letzte Aktualisierung**: 23. September 2025


Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum von September bis Anfang Oktober 2025. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Aktualisierungen der Benutzeroberfläche** | Die [Benutzeroberfläche](/help/connections/manage-connections.md#usage) enthält jetzt Informationen zum Kerndatenvolumen und zur durchschnittlichen Zeilengröße.<p>Weitere Informationen finden Sie unter [Verwalten von Verbindungen](/help/connections/manage-connections.md#usage).</p> | | &#x200B;4. September 2025 |
| **Verbesserungen beim Migrieren von Projekten und Komponenten zu Customer Journey Analytics** | Die folgenden Verbesserungen sind jetzt beim Migrieren von Projekten und Komponenten von Adobe Analytics zu Customer Journey Analytics verfügbar:<ul><li>Gleichzeitige Migration mehrerer Projekte.<br/>Sie können bis zu 20 Projekte gleichzeitig migrieren.<br/>Zuvor konnten Sie jeweils nur ein Projekt migrieren.</li><li>Aktualisieren Sie Zuordnungen für Dimensionen und Metriken, die bereits einer vorherigen Projektmigration zugeordnet waren.<br/>Sie können diese Zuordnungen jetzt jedes Mal aktualisieren, wenn Sie ein Projekt migrieren, auch wenn dieselben Dimensionen und Metriken vormals einer vorherigen Migration zugeordnet waren.<br/>Zuvor waren alle ausgewählten Zuordnungen dauerhaft für alle zukünftigen Projektmigrationen.</li><li>Verbesserte Leistung für Organisationen mit hoher Projektanzahl.</li></ul><p>Diese Funktion ist über die Benutzeroberfläche von Adobe Analytics verfügbar. Weitere Informationen finden Sie unter [Migrieren von Komponenten und Projekten von Adobe Analytics zu Customer Journey Analytics](https://experienceleague.adobe.com/de/docs/analytics/admin/admin-tools/component-migration/component-migration).</p> | &#x200B;15. September 2025 | &#x200B;18. September 2025 |
| **Limit für Lookup-Schlüssel wurde auf bis zu 1 Milliarde erhöht** | Die maximale Anzahl eindeutiger Schlüssel für einen Lookup-Datensatz beträgt jetzt je nach Customer Journey Analytics-Berechtigung bis zu 1 Milliarde. <p>Zuvor war die maximale Anzahl für alle Berechtigungen 10 Millionen.<p>Weitere Informationen finden Sie unter [Leitlinien](/help/technotes/guardrails.md).</p> | | &#x200B;25. September 2025 |
| **Unterstützung für Ad-hoc- und modellbasierte Schemata** | [Ad-hoc](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/tutorials/ad-hoc) und modellbasierte Schemata werden in Datenaufnahme- und Datenspiegelungs-Workflows für Experience Platform verwendet. |  | &#x200B;23. September 2025 (Veröffentlichung ursprünglich für den 28. August 2025 geplant) |
| **Echtzeit-Reporting** | Echtzeitberichte in Customer Journey Analytics zeigen Daten und Visualisierungen in einem oder mehreren Bedienfeldern in Analysis Workspace in Echtzeit an und aktualisieren diese.<br/><br/>(Link zur Dokumentation folgt.) | 18. September 2025 (Veröffentlichung ursprünglich für den 15. August 2025 geplant) | Dienstag, 27. Oktober 2025 |
| **Unterstützung für Datenspiegelung** | Durch die Unterstützung modellbasierter Schemata und der Funktion zur Änderungsdatenerfassung (Change Data Capture, CDC) für bestimmte Quell-Connectoren in Experience Platform kann Customer Journey Analytics die Datenspiegelungsfunktion von Data-Warehouse-Lösungen wie [!DNL Snowflake], [!DNL Azure Databrick] und [!DNL Google BigQuery] unterstützen.<p>Wenden Sie sich an Ihr Adobe-Accountteam, um Zugriff auf die Beta-Version anzufordern.</p><p>(Link zur Dokumentation folgt.)</p> | Beta-Version ab 24. September 2025 | TBD |
| **Streaming-Mediendienste: Unterstützung von Zeitplandaten** | Sie können jetzt geplante Daten vergangener Live-Streaming-Medieninhalte hochladen, um die Zuschauerzahlen einfacher und genauer verfolgen zu können.<p>Im Folgenden finden Sie Beispiele für Live-Inhalte, die mit dem Upload von Zeitplandaten unterstützt werden:</p><ul><li>FAST-Plattformen (Free Ad Supported TV)</li><li>Lokale Datenströme</li><li>Live-Sportübertragungen</li></ul><p>Durch das Hochladen von Zeitplandaten können Sie die Zuschauerzahlen für einzelne Programme verfolgen, die in dem von Ihnen in der Upload-Datei angegebenen Zeitraum gelaufen sind. Sie können sogar Zuschauerzahlen zu bestimmten Themen oder Programmsegmenten erfassen.</p><p>Diese Funktionen sind unabhängig davon verfügbar, wie Sie die Erfassung von Streaming-Medien implementiert haben.</p><p>Zuvor war es bei der Analyse von Live-Inhalten schwierig, eine bestimmte Sitzung genau mit bestimmten Programmen zu verknüpfen, und es war nicht möglich, eine bestimmte Sitzung mit einzelnen Themen oder Programmsegmenten zu verknüpfen.</p><p>(Link zur Dokumentation folgt.)<!--For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)--></p> |  | Donnerstag, 29. Oktober 2025 |
| **Streaming-Medien: Aktualisierte XDM-Felder zum Sammeln von Streaming-Mediendaten in Adobe Experience Platform** | Beim Erfassen von Streaming-Mediendaten in Adobe Experience Platform sollten die XDM-Feldpfade unter der Überschrift „XDM-Feldpfad“ in der Dokumentation zu den Streaming-Medienparametern nicht mehr verwendet werden. Stattdessen müssen Kundinnen und Kunden, die den Analytics-Quell-Connector vor dem 9. Mai 2025 implementiert haben, um Streaming-Mediendaten in Platform zu erfassen, ihre vorhandenen Konfigurationen in die mediaReporting-Feldpfade migrieren, wie unter der Überschrift „XDM-Feldpfad für Berichterstellung“ der Dokumentation zu Streaming-Medienparametern gezeigt.<p> Diese Feldpfade befinden sich auf den folgenden Seiten und sind als „veraltet“ gekennzeichnet: [Audio- und Videoparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Anzeigenparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/ad-parameters), [Kapitelparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/chapter-parameters), [Player-Statusparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/player-state-parameters) und [Qualitätsparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/quality-parameters). (Bei Kundinnen und Kunden, die den Analytics-Quell-Connector nach dem 9. Mai 2025 implementiert haben und bereits nur XDM-Pfade für mediaReporting verwenden, ist keine Aktion erforderlich.)</p><p>Die Datenaufnahme über die veralteten XDM-Feldpfade wird noch bis Ende Oktober 2025 fortgesetzt. Danach werden die veralteten Felder vollständig entfernt und nicht mehr in der Schema-Benutzeroberfläche von Adobe Experience Platform angezeigt. Daten werden nur mithilfe der mediaReporting-Feldpfade gesendet.</p><p>Weitere Informationen finden Sie unter [Migrieren einer Analytics-Quell-Connector-Implementierung zu aktualisierten XDM-Streaming-Medien-Feldern](https://experienceleague.adobe.com/de/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Wenden Sie sich an Ihren Adobe Consulting-Dienst oder Ihr Konto-Team, um Unterstützung bei der Migration zu erhalten. </p> |  | Oktober 2025 |
| **Zuordnung von Verbindungen** | Vereinfacht die Zuordnung in Customer Journey Analytics. Statt einen Datensatz zu duplizieren und eine Zuordnung zum duplizierten Datensatz vorzunehmen, wird die Zuordnung jetzt bei der Aufnahme von Daten in Customer Journey Analytics durchgeführt. Dadurch entfällt die Anforderung duplizierter Datensätze und Schemata. <p>Darüber hinaus können Sie jetzt die Zuordnung selbst über eine aktualisierte Verbindungs-Benutzeroberfläche starten, anstatt die Zuordnung über den Kunden-Support anfordern zu müssen.</p><p> *Die zuvor mitgeteilten Veröffentlichungstermine müssen aufgrund zusätzlicher erforderlicher Arbeiten verschoben werden. Da sich die neuen Veröffentlichungstermine mit der Urlaubssaison überschneiden, gibt es zusätzliche Einschränkungen bei der Veröffentlichung. Um Stabilität zu gewährleisten und Störungen während der Feiertage zu minimieren, ist nun ein schrittweises Rollout geplant.*</p> <p>(Link zur Dokumentation folgt.)</p> | Ende Oktober 2025 | Ende Januar 2026 |

## Fehlerbehebungen in Customer Journey Analytics

**Analysis Workspace**: AN-391719, AN-380838, AN-389402, AN-389373, AN-390851, AN-391593, AN-391404, AN-393064, AN-379337
**Komponenten**: AN-393810
**Content Analytics**:
**Geführte Analyse**:
**Plattform**:
**Report Builder**: AN-387741, AN-386777, AN-388720, AN-389343
**Reporting**: AN-391439, AN-391228, AN-393620, AN-393640, AN-391334, AN-393304
**Segmentierung**:
**Terminierte Berichte**: AN-391150, AN-390474
**Freigegebene Metriken und Dimensionen**:
**Sonstige**: AN-387858


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
