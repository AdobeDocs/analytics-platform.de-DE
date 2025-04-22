---
title: Aktuelle Versionshinweise zu Customer Journey Analytics
description: Anzeigen der neuesten Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 5a4d9ad92de69c91d4cf8f4f400ede37470c3baa
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 47%

---

# Aktuelle Versionshinweise zu Adobe Customer Journey Analytics (April 2025)

**Letzte Aktualisierung**: Donnerstag, 16. April 2025

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom 27. März bis zum Freitag, 15. Mai 2025. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Aktualisierungen des Zeileneintrags „Kein Wert“ in numerischen Dimensionen** | Bei numerischen Dimensionen ermöglicht diese Aktualisierung Folgendes:<ul><li>Verwenden Sie das Dimensionselement „Kein Wert“ in einem Segment.</li><li>Aufschlüsselung des Zeileneintrags „Kein Wert“ in einem Bericht.</li></ul> [Weitere Informationen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/no-value-options#numeric) | 27. März 2025 |
| **Adobe Content Analytics** | Mit Adobe Content Analytics können Sie schnell und einfach große Mengen von Inhaltsdaten untersuchen, um Trends aufzudecken, Anomalien zu erkennen, Content-Ermüdung zu identifizieren und Erkenntnisse aus der Bereitstellung von Inhalten zu gewinnen.<p>Standardmäßig können Sie mit vordefinierten Berichtsvorlagen und neuen Funktionen wie Asset Inspector Zeit sparen. Mit dieser Funktion können Sie das Asset nicht nur inline mit Ihren Daten visualisieren, sondern auch jedes einzelne Asset öffnen, um zusammengefasste Details wie Leistung, Platzierungen, Attribute und mehr zu erhalten.<p>Sie können diesen neuen Satz von Inhaltsdaten im Kontext der vollständigen Customer Journey untersuchen, um wichtige geschäftliche Fragen zu beantworten, die Content-Performance zu bewerten, die Segmentierung zu verbessern, Optimierungsmöglichkeiten zu identifizieren und neue Zielgruppen für die Aktivierung zu definieren.<p>Content Analytics ist ein Add-on für Customer Journey Analytics. [Weitere Informationen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/content-analytics/content-analytics) |  | 27. März 2025 |
| **Mediensammlung: Adobe Source Connector-Aktualisierungen für neues Berichterstellungs-XDM** | Der Analytics Source Connector ordnet Streaming-Mediendaten in Adobe Analytics automatisch den Feldern zu, die vom Web SDK verwendet werden. Zuvor wurden die Daten sowohl den alten als auch den neuen Speicherorten zugeordnet, in Zukunft wird jedoch nur der neue Speicherort verwendet. [Weitere Informationen](https://experienceleague.adobe.com/de/docs/analytics/implementation/aep-edge/xdm-var-mapping) |  | 31. März 2025 |
| **XDM-Felder zum Erfassen von Streaming-Mediendaten in Adobe Experience Platform wurden aktualisiert** | Beim Erfassen von Streaming Media-Daten in Adobe Experience Platform sollte die `media.mediaTimed` Feldergruppe nicht mehr verwendet werden. Stattdessen sollten Kunden zur `mediaReporting` Feldergruppe migrieren.<p>Während einer Übergangszeit von drei Monaten wird die Datenaufnahme in `media.mediaTimed` Feldern fortgesetzt. Ende Juli 2025 werden jedoch `the media.mediaTimed` Felder vollständig veraltet sein und nicht mehr in der Adobe Experience Platform-Schema-Benutzeroberfläche angezeigt. Daten werden nur mithilfe der `mediaReporting` Felder gesendet.<p>Kunden, die den Analytics-Quell-Connector implementiert haben, um Streaming-Mediendaten vor dem 22. April 2025 in Platform zu erfassen, müssen ihre vorhandenen Konfigurationen migrieren, um die neue Feldergruppe zu verwenden. Diese Migration muss bis Ende Juli 2025 abgeschlossen sein. Wenden Sie sich an Ihren Adobe Consulting-Service oder Ihr Account-Team, um Unterstützung bei der Migration zu erhalten. Für Kunden, die den Analytics-Quell-Connector nach dem 22. April 2025 implementieren, ist keine Aktion erforderlich. |  | Mittwoch, 22. April 2025 |
| **Terminologieänderung: „Filter“ zu „Segmenten“** | Zuvor bezeichnete Adobe Customer Journey Analytics Segmente als „Filter“. Diese Terminologie wurde nun an Adobe Analytics angepasst. „Filter“ werden jetzt als „Segmente“ bezeichnet. (Natürlich werden Suchfilter weiterhin als „Filter“ bezeichnet.) Die Benutzeroberfläche wurde aktualisiert, und die Dokumentation wird derzeit aktualisiert. |  | Donnerstag, 16. April 2025 |
| **Zusammenfügen: Abrufen persistenter und vorübergehender IDs aus XDM IdentityMap** | Diese Funktion bietet Unterstützung für die Verwendung von Identitäten, die in der XDM IdentityMap gespeichert sind, im Stitching-Prozess. Die identityMap kann für die persistente oder vorübergehende ID für feldbasiertes Stitching und für die persistente ID für diagrammbasiertes Stitching verwendet werden.  Sie können entweder einen bestimmten Namespace oder eine primäre Identität aus der identityMap verwenden. (Link zur Dokumentation folgt) |  | Samstag, 25. April 2025 |
| **Freigegebene Metriken und Dimensionen in allen Datenansichten** | Ermöglicht die Anwendung von Dimensions- und Metrikeinstellungen auf mehrere Datenansichten. Änderungen an einer freigegebenen Dimension oder Metrik gelten für alle Instanzen dieser Dimension oder Metrik in allen anwendbaren Datenansichten. Diese Benutzeroberfläche ermöglicht es Customer Journey Analytics-Admins, Komponenten einfacher zu verwalten, wenn viele Datenansichten verwendet werden. (Link zur Dokumentation folgt) |  | Donnerstag, 30. April 2025 |


## Fehlerbehebungen in Customer Journey Analytics

**Admin Console**: AN-370228
**Analysis Workspace**: AN-371933; AN- 371933; AN-371979
**Audiences**: AN-373032
**Komponenteneinstellungen**: AN-367400
**Abgeleitete Felder**: AN-370614; AN-370959
**Exportspeicherorte**: AN-371670
**Vollständiger Tabellenexport** AN-360492; AN-369204; AN-370755; AN-372294; AN-372363; AN-372754; AN-373040; AN-373081; AN-373168
**Journey-Arbeitsfläche**: AN-373294
**Mobile App**: AN-363169; AN-368496; AN-371766
**Produktnutzung**: AN-369501
**Reporting**: AN-369085; AN-371094; AN-372580


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
