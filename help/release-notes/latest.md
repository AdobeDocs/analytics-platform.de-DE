---
title: Aktuelle Versionshinweise zu Customer Journey Analytics
description: Anzeigen der neuesten Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: f09937e6babca5549b9b78e9c90462673750a4b3
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 96%

---

# Aktuelle Versionshinweise zu Adobe Customer Journey Analytics (August 2025)

**Letzte Aktualisierung**: Freitag, 4. September 2025


Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom 13. August bis zum 16. September 2025. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Aktualisierungen der Benutzeroberfläche von** | Die [Nutzungsschnittstelle](/help/connections/manage-connections.md#usage) fügt jetzt Informationen zum Kerndatenvolumen und zur durchschnittlichen Zeilengröße hinzu. | | Freitag, 4. September 2025 |
| **Kartenvisualisierung** | Die Kartenvisualisierung ist eine Visualisierung in Analysis Workspace, mit der Sie eine visuelle Karte für jede beliebige Metrik (einschließlich berechneter Metriken) erstellen können. Sie ist hilfreich bei der Erfassung und dem Vergleich von Metrikdaten über verschiedene geographische Regionen hinweg.<p>Zuvor war die Kartenvisualisierung nur in Adobe Analytics verfügbar.</p><p>Die Kartenvisualisierung in Customer Journey Analytics enthält die folgenden Verbesserungen gegenüber der Kartenvisualisierung in Adobe Analytics:</p><ul><li>Verwendung eines beliebigen Segments aus Ihrer Datenansicht als Datenquelle.</li><li>Genauigkeit von bis zu einem Meter durch Konfigurieren der Dimension in Ihrer Datenansicht.</li><li>Mit dem neuen Auswahlwerkzeug können Sie ein Segment, eine Zielgruppe, einen Trend oder eine Aufschlüsselung aus einem beliebigen Bereich in der Visualisierung erstellen.</li></ul><p>Weitere Informationen finden Sie unter [Karte](/help/analysis-workspace/visualizations/map.md).</p> | Donnerstag, 13. August 2025 | 25. August 2025 |
| **B2B-Vorlagen** | Wenn Sie die Lizenz für Customer Journey Analytics B2B Edition erwerben, sind jetzt die folgenden zusätzlichen B2B-Vorlagen in der Benutzeroberfläche der Adobe-Vorlagen verfügbar: <ul><li>Überblick über B2B-Konteninteraktion</li><li>Überblick über B2B-Opportunity-Interaktion</li><li>Aktivität der B2B-Käufergruppe</li></ul><p>Weitere Informationen finden Sie in [Verwenden von Vorlagen](/help/analysis-workspace/templates/use-templates.md) unter [B2B-Vorlagen](/help/analysis-workspace/templates/use-templates.md#b2b-templates).</p> |  | Samstag, 15. August 2025 |
| **Als PDF heruntergeladene Projekte werden auf Ihre Workstation heruntergeladen** | Beim Herunterladen eines Projekts als PDF wird die PDF-Datei in den Ordner „Downloads“ auf Ihrer Workstation heruntergeladen. <p>Bisher wurde die PDF-Datei in einem neuen Browser-Tab mit einer eindeutigen URL geöffnet, wenn Sie ein Projekt als PDF heruntergeladen haben.</p><p>Weitere Informationen finden Sie unter [Herunterladen von Projekten und Daten](/help/analysis-workspace/export/download-send.md).</p> |  | 25. August 2025 |
| **Unterstützung für Ad-hoc-Schemata** | [Ad-hoc-Schemata](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/tutorials/ad-hoc) werden in verschiedenen Datenaufnahme-Workflows für Experience Platform verwendet, einschließlich der Aufnahme von CSV-Dateien und der Erstellung bestimmter Arten von Quellverbindungen. <p>Diese Funktion ermöglicht die Unterstützung für die Verwendung von Ad-hoc-Schemata in Customer Journey Analytics. Als Teil der Definition einer Verbindung können Sie jetzt einen Datensatz basierend auf einem Ad-hoc-Schema auswählen und die Daten in Ihren Datenansichts- und Workspace-Projekten verwenden.</p> <p>(Link zur Dokumentation folgt.)</p> |  | &#x200B;18. September 2025 (ursprünglich geplant für die Veröffentlichung am 28. August 2025) |
| **Erweitern des Lookup-Schlüssel-Limits** | Je nach Customer Journey Analytics-Paket können Sie jetzt bis zu 1 Milliarde eindeutige Schlüssel in einem Lookup-Datensatz haben. <p>Weitere Informationen finden Sie unter [Datenübertragungslimits](/help/technotes/guardrails.md#data-transfer-limits) in der [Leitlinien](/help/technotes/guardrails.md)-Dokumentation zu Customer Journey Analytics.</p> |  | Samstag, 29. August 2025 |
| **Erstellen von Metriken und Dimensionen basierend auf benutzerdefinierten Zuordnungsfeldern aus dem Platform-Schema** | Benutzerdefinierte Zuordnungsfelder, die Sie in Ihrem Experience Platform-Schema definieren, sind jetzt für die Verwendung in Customer Journey Analytics verfügbar.<p>Beim Erstellen von Metriken und Dimensionen in Customer Journey Analytics können Sie die folgenden Zuordnungsfelder verwenden:</p><ul><li>Zeichenfolge zu Zeichenfolge</li><li>Zeichenfolge zu Ganzzahl</li></ul><p>Weitere Informationen finden Sie unter [Komponenteneinstellungen](/help/data-views/component-settings/overview.md).</p><p>Weitere Informationen zu Zuordnungsfeldern in Experience Platform finden Sie unter [Definieren von Zuordnungsfeldern in der Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/ui/fields/map).</p> |  | Ende August 2025 |
| **Gelöschte Projekte sind per URL sofort nicht mehr verfügbar und werden aus terminierten Bereitstellungen entfernt** | Gelöschte Projekte werden sofort aus den geplanten Bereitstellungen entfernt und sind über ihre URL nicht mehr zugänglich.<p>Zuvor waren Projekte in geplante Bereitstellungen eingeschlossen und konnten nach dem Löschen 60 Tage lang über die URL aufgerufen werden.</p><p>Weitere Informationen zum Löschen von Projekten finden Sie unter [Projekte – Übersicht](/help/analysis-workspace/build-workspace-project/freeform-overview.md).</p> | | Ende August 2025 |
| **Echtzeit-Reporting** | Echtzeitberichte in Customer Journey Analytics zeigen Daten und Visualisierungen in einem oder mehreren Bedienfeldern in Analysis Workspace in Echtzeit an und aktualisieren diese.<br/><br/>(Link zur Dokumentation folgt.) | | &#x200B;18. September 2025 (ursprünglich geplant für die Veröffentlichung am 15. August 2025) |
| **Streaming-Medien: Aktualisierte XDM-Felder zum Sammeln von Streaming-Mediendaten in Adobe Experience Platform** | Beim Erfassen von Streaming-Mediendaten in Adobe Experience Platform sollten die XDM-Feldpfade unter der Überschrift „XDM-Feldpfad“ in der Dokumentation zu den Streaming-Medienparametern nicht mehr verwendet werden. Stattdessen müssen Kundinnen und Kunden, die den Analytics-Quell-Connector vor dem 9. Mai 2025 implementiert haben, um Streaming-Mediendaten in Platform zu erfassen, ihre vorhandenen Konfigurationen in die mediaReporting-Feldpfade migrieren, wie unter der Überschrift „XDM-Feldpfad für Berichterstellung“ der Dokumentation zu Streaming-Medienparametern gezeigt.<p> Diese Feldpfade befinden sich auf den folgenden Seiten und sind als „veraltet“ gekennzeichnet: [Audio- und Videoparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Anzeigenparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/ad-parameters), [Kapitelparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/chapter-parameters), [Player-Statusparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/player-state-parameters) und [Qualitätsparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/quality-parameters). (Bei Kundinnen und Kunden, die den Analytics-Quell-Connector nach dem 9. Mai 2025 implementiert haben und bereits nur XDM-Pfade für mediaReporting verwenden, ist keine Aktion erforderlich.)</p><p>Die Datenaufnahme über die veralteten XDM-Feldpfade wird noch bis Ende Oktober 2025 fortgesetzt. Danach werden die veralteten Felder vollständig entfernt und nicht mehr in der Schema-Benutzeroberfläche von Adobe Experience Platform angezeigt. Daten werden nur mithilfe der mediaReporting-Feldpfade gesendet.</p><p>Weitere Informationen finden Sie unter [Migrieren einer Analytics-Quell-Connector-Implementierung zu aktualisierten XDM-Streaming-Medien-Feldern](https://experienceleague.adobe.com/de/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Wenden Sie sich an Ihren Adobe Consulting-Dienst oder Ihr Konto-Team, um Unterstützung bei der Migration zu erhalten. </p> |  | Oktober 2025 |
| **Zuordnung von Verbindungen** | Vereinfacht die Zuordnung in Customer Journey Analytics. Statt einen Datensatz zu duplizieren und eine Zuordnung zum duplizierten Datensatz vorzunehmen, wird die Zuordnung jetzt bei der Aufnahme von Daten in Customer Journey Analytics durchgeführt. Dadurch entfällt die Anforderung duplizierter Datensätze und Schemata. <p>Darüber hinaus können Sie jetzt die Zuordnung selbst über eine aktualisierte Verbindungs-Benutzeroberfläche starten, anstatt die Zuordnung über den Kunden-Support anfordern zu müssen.</p><p> *Die zuvor mitgeteilten Veröffentlichungstermine müssen aufgrund zusätzlicher erforderlicher Arbeiten verschoben werden. Da sich die neuen Veröffentlichungstermine mit der Urlaubssaison überschneiden, gibt es zusätzliche Einschränkungen bei der Veröffentlichung. Um Stabilität zu gewährleisten und Störungen während der Feiertage zu minimieren, ist nun ein schrittweises Rollout geplant.*</p> | Ende Oktober 2025 | Ende Januar 2026 |

## Fehlerbehebungen in Customer Journey Analytics

**Analysis Workspace**: AN-389683; AN-389534; AN-389207; AN-389066; AN-388687; AN-388478; AN-387089; AN-384865; AN-384560; AN-383486; AN-365768; AN-351639
**Komponenten**:
**Inhaltsanalyse**:
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
