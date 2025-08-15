---
title: Aktuelle Versionshinweise zu Customer Journey Analytics
description: Anzeigen der neuesten Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: f959ac6c12280f745a986237c39d7fb1e7af5aa7
workflow-type: tm+mt
source-wordcount: '1032'
ht-degree: 19%

---

# Aktuelle Versionshinweise zu Adobe Customer Journey Analytics (August 2025)

**Letzte Aktualisierung**: Freitag, 14. August 2025


Diese Versionshinweise decken den Veröffentlichungszeitraum vom 13. August bis zum 16. September 2025 ab. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Kartenvisualisierung** | Die Zuordnungsvisualisierung ist eine Visualisierung in Analysis Workspace, mit der Sie eine visuelle Zuordnung einer beliebigen Metrik (einschließlich berechneter Metriken) erstellen können. Dies ist nützlich, um Metrikdaten über verschiedene geografische Regionen hinweg zu identifizieren und zu vergleichen.<p>Zuvor war die Kartenvisualisierung nur in Adobe Analytics verfügbar.</p><p>Die Kartenvisualisierung in Customer Journey Analytics enthält die folgenden Verbesserungen gegenüber der Kartenvisualisierung in Adobe Analytics:</p><ul><li>Verwenden Sie ein beliebiges Segment aus Ihrer Datenansicht als Datenquelle.</li><li>Genauigkeit von bis zu einem Meter durch Konfigurieren der Dimension in Ihrer Datenansicht.</li><li>Mit dem neuen Auswahlwerkzeug können Sie ein Segment, eine Zielgruppe, einen Trend oder eine Aufschlüsselung aus einem beliebigen Bereich in der Visualisierung erstellen.</li></ul><p>Weitere Informationen finden Sie unter [Map](/help/analysis-workspace/visualizations/map.md).</p> | Donnerstag, 13. August 2025 | Dienstag, 25. August 2025 |
| **Echtzeit-Reporting** | Echtzeitberichte in Customer Journey Analytics zeigen Daten und Visualisierungen in einem oder mehreren Bedienfeldern in Analysis Workspace in Echtzeit an und aktualisieren diese. | | Samstag, 15. August 2025 |
| **B2B-Vorlagen** | Wenn Sie die Lizenz für Customer Journey Analytics B2B edition erwerben, sind jetzt die folgenden zusätzlichen B2B-Vorlagen in der Benutzeroberfläche der Adobe-Vorlagen verfügbar: <ul><li>Überblick über B2B-Konteninteraktion</li><li>Überblick über B2B-Opportunity-Interaktion</li><li>Aktivität der B2B-Käufergruppe</li></ul><p>(Link zur Dokumentation folgt.)</p> |  | Samstag, 15. August 2025 |
| **Als PDF heruntergeladene Projekte werden auf Ihre Workstation heruntergeladen** | Beim Herunterladen eines Projekts als PDF wird die PDF in den Ordner „Downloads“ auf Ihrer Workstation heruntergeladen. <p>Beim Herunterladen eines Projekts als PDF wurde PDF zuvor in einer neuen Browser-Registerkarte mit einer eindeutigen URL gestartet.</p><p>Weitere Informationen finden Sie unter [Herunterladen von Projekten und Daten](/help/analysis-workspace/export/download-send.md).</p> |  | Dienstag, 25. August 2025 |
| **Unterstützung für Ad-hoc-Schemata** | [Ad-hoc-Schemata](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/tutorials/ad-hoc) werden in verschiedenen Datenaufnahme-Workflows für Experience Platform verwendet, einschließlich der Aufnahme von CSV-Dateien und der Erstellung bestimmter Arten von Quellverbindungen. <p>Diese Funktion ermöglicht die Unterstützung für die Verwendung von Ad-hoc-Schemata in Customer Journey Analytics. Als Teil der Definition einer Verbindung können Sie jetzt einen Datensatz basierend auf einem Ad-hoc-Schema auswählen und die Daten in Ihren Datenansichts- und Arbeitsbereich-Projekten verwenden.</p> <p>(Link zur Dokumentation folgt.)</p> |  | Freitag, 28. August 2025 |
| **Zusammenfügen von Verbindungen** | Vereinfacht das Zusammenfügen mit Customer Journey Analytics. Anstatt einen Datensatz zu duplizieren und eine Zuordnung zum duplizierten Datensatz anzuwenden, erfolgt die Zuordnung jetzt bei der Aufnahme von Daten in Customer Journey Analytics, wodurch die Anforderung duplizierter Datensätze und Schemata entfällt. <p>Darüber hinaus können Sie jetzt die Zuordnung selbst über eine aktualisierte Verbindungs-Benutzeroberfläche starten, anstatt die Zuordnung über den Kunden-Support anfordern zu müssen.</p><p> *Die zuvor kommunizierten Veröffentlichungstermine werden aufgrund zusätzlicher erforderlicher Anstrengungen verschoben. Die neuen Veröffentlichungstermine überschneiden sich mit der Urlaubssaison, was zusätzliche Veröffentlichungsbeschränkungen mit sich bringt. Es ist jetzt ein schrittweiser Rollout geplant, um Stabilität zu gewährleisten und Unterbrechungen während der Feiertage zu minimieren.*</p> | Ende Oktober 2025 | Ende Januar 2026 |
| **Suchschlüssellimit erweitern** | Je nach Customer Journey Analytics-Paket können Sie jetzt bis zu 1 Milliarde eindeutige Schlüssel in einem Lookup-Datensatz haben. <p>Customer Journey Analytics Weitere Informationen finden Sie unter [Datenübertragungsbeschränkungen](/help/technotes/guardrails.md#data-transfer-limits) in der Dokumentation zu [ (](/help/technotes/guardrails.md)).</p> |  | Samstag, 29. August 2025 |
| **Erstellen Sie Metriken und Dimensionen basierend auf benutzerdefinierten Zuordnungsfeldern aus dem Platform-Schema** | Benutzerdefinierte Zuordnungsfelder, die Sie in Ihrem Experience Platform-Schema definieren, sind jetzt für die Verwendung in Customer Journey Analytics verfügbar.<p>Beim Erstellen von Metriken und Dimensionen in Customer Journey Analytics können Sie die folgenden Zuordnungsfelder verwenden:</p><ul><li>Zeichenfolge zu Zeichenfolge</li><li>Zeichenfolge zu Ganzzahl</li></ul><p>(Link zur Dokumentation folgt.)</p><p>Weitere Informationen zu Zuordnungsfeldern in Experience Platform finden Sie unter [Definieren von Zuordnungsfeldern in der Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/ui/fields/map).</p> |  | Ende August 2025 |
| **Gelöschte Projekte sind per URL sofort nicht mehr verfügbar und werden aus terminierten Sendungen gelöscht** | Gelöschte Projekte werden sofort aus den geplanten Sendungen gelöscht und sind über ihre URL nicht mehr zugänglich.<p>Zuvor waren Projekte in geplante Sendungen eingeschlossen und konnten nach dem Löschen 60 Tage lang über die URL aufgerufen werden.</p><p>Weitere Informationen zum Löschen von Projekten finden Sie unter [Projekte - Übersicht](/help/analysis-workspace/build-workspace-project/freeform-overview.md).</p> | | Ende August 2025 |
| **Streaming-Medien: Aktualisierte XDM-Felder zum Erfassen von Streaming-Mediendaten in Adobe Experience Platform** | Beim Erfassen von Streaming-Mediendaten in Adobe Experience Platform sollten die XDM-Feldpfade unter der Überschrift „XDM-Feldpfad“ in der Dokumentation zu den Streaming-Medienparametern nicht mehr verwendet werden. Stattdessen müssen Kundinnen und Kunden, die den Analytics-Quell-Connector implementiert haben, um Streaming-Mediendaten in Platform vor dem 9. Mai 2025 zu erfassen, ihre vorhandenen Konfigurationen in die mediaReporting-Feldpfade migrieren, wie unter der Überschrift „XDM-Feldpfad für Berichterstellung“ der Dokumentation zu Streaming-Medienparametern gezeigt.<p> Diese Feldpfade befinden sich auf den folgenden Seiten und sind als „Veraltet“ gekennzeichnet: [Audio- und Videoparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Anzeigenparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/ad-parameters), [Kapitelparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/chapter-parameters), [Player-](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/player-state-parameters) und [Qualitätsparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/quality-parameters). (Für Kunden, die den Analytics-Quell-Connector nach dem 9. Mai 2025 implementieren und bereits nur XDM-Pfade für mediaReporting verwenden, ist keine Aktion erforderlich.)</p><p>Die Datenaufnahme in den veralteten XDM-Feldpfaden wird bis Ende Oktober 2025 fortgesetzt. Nach diesem Zeitpunkt werden veraltete Feldpfade vollständig entfernt und nicht mehr in der Adobe Experience Platform-Schema-Benutzeroberfläche angezeigt. Daten werden nur noch über die MediaReporting-Feldpfade gesendet.</p><p>Weitere Informationen finden Sie unter [ einer Analytics Source Connector-Implementierung in aktualisierte XDM Streaming Media-Felder](https://experienceleague.adobe.com/de/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Wenden Sie sich an Ihren Adobe Consulting-Service oder Ihr Account-Team, um Unterstützung bei der Migration zu erhalten. </p> |  | Oktober 2025 |

## Fehlerbehebungen in Customer Journey Analytics

**Analysis Workspace**: AN-389683; AN-389534; AN-389207; AN-389066; AN-388687; AN-388478; AN-387089; AN-384865; AN-384560; AN-383486; AN-365768; AN-351639
**Komponenten**:
**Content Analytics**:
**Geführte Analyse**: AN-384426
**Platform**: AN-384410
**Report Builder**: AN-389336; AN-382775
**Reporting**:
**Segmentierung**:
**Freigegebene Metriken und Dimensionen**:
**Sonstige**: AN-388222; AN-384898; AN-387169


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
