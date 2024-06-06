---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 6ac57240b9c74b83cadcb26a5fd55913bc28c01f
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 91%

---

# Aktuelle Versionshinweise zu Adobe Customer Journey Analytics (Mai 2024)

**Letzte Aktualisierung**: Freitag, 6. Juni 2024

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom 15. Mai 2024 bis Juni 2024. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **KI-Assistent für Customer Journey Analytics** | Sie können in der Customer Journey Analytics-Benutzeroberfläche Fragen in natürlicher Sprache stellen und erhalten Antworten auf Grundlage der Customer Journey Analytics-Dokumentation. [Weitere Informationen](/help/ai-assistant.md) | | Freitag, 6. Juni 2024 |
| **Umwandlung von B2B-Lookup-Datensätzen** | Sie können jetzt [B2B-Lookup-Datensätze transformieren](/help/connections/transform-datasets-b2b-lookups.md) beim Definieren einer Verbindung. Diese Umwandlung ermöglicht die Unterstützung personalbasierter Suchen nach B2B-Daten. | | Freitag, 6. Juni 2024 |
| **BI-Erweiterung** | Die BI-Erweiterung ermöglicht SQL-Zugriff auf Datenansichten, die Sie in Customer Journey Analytics definiert haben. [Weitere Informationen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/bi-extension) | | 15. Mai 2024 |
| **Veröffentlichung von Zielgruppen in einem neuen Abschnitt „Zielgruppen“ in Experience Platform** | Von Customer Journey Analytics veröffentlichte Zielgruppen sind jetzt im neuen Abschnitt „Zielgruppen“ in Adobe Experience Platform verfügbar.<p>Bislang waren über Customer Journey Analytics veröffentlichte Zielgruppen in Experience Platform im Abschnitt „Segmente“ verfügbar.</p><p>Diese Verbesserung bietet folgende Vorteile:</p><ul><li>Zielgruppen werden nicht mehr mit 1 Stunde Verzögerung in Experience Platform angezeigt. Sie stehen vielmehr Sekunden nach ihrer Veröffentlichung zur Verfügung.</li><li>Zielgruppen können in Experience Platform mithilfe der Spalte „Herkunft“ sortiert werden, in der die Anwendung angezeigt wird, von der aus die Zielgruppe ursprünglich veröffentlicht wurde.</li><li>Mit den Filter- und Sortieroptionen in Experience Platform können Sie die relevanten Zielgruppen schneller finden.</li></ul> <p>(Link zur aktualisierten Dokumentation folgt)</p> |  | Ende Mai bis Anfang Juni 2024 |
| **Streaming-Medien: Senden von Web-Daten mit dem Web SDK an Adobe Experience Platform Edge Network** | Sie können nun das Adobe Experience Platform Web SDK verwenden, um Web-Daten zu Streaming-Medien an das Adobe Experience Platform Edge Network zu senden, sodass Sie stärker personalisierte Kampagnen erstellen sowie stärker personalisierte Inhalte bereitstellen können und dadurch mehr Tracking-Daten für Berichte zur Verfügung stehen.<p>Diese Erweiterung bietet eine einheitliche Erfassungsmethode für Web-Implementierungen über alle Plattformlösungen hinweg, z. B. Customer Journey Analytics, RT-CDP, AJO und Ereignisweiterleitung. Zuvor bestand die einzige Möglichkeit, Web-Daten zu Streaming-Medien an Edge Network zu senden, in der Verwendung des Media Edge-API. <p>[Weitere Informationen](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/edge-web-sdk)</p> | | 29. Mai 2024 |
| **Abgeleitete Felder - Neue Funktionen und Funktionsvorlagen** | Zusätzliche abgeleitete Feldfunktionen ([Mathematisch](/help/data-views/derived-fields/derived-fields.md#math), [Nächste oder Vorherige](/help/data-views/derived-fields/derived-fields.md#next-or-previous)) und [Funktionsvorlagen](/help/data-views/derived-fields/derived-fields.md#function-templates). | | 5. Juni 2024 |
| **Freigeben von Konten und Speicherorten, die für den Export und Import verwendet werden** | Benutzende können nun die von ihnen erstellten Konten und Speicherorte allen Benutzenden in ihrer Organisation zur Verfügung stellen. Nur die Personen, denen Konten bzw. Speicherorte gehören, und System-Admins können Konten und Speicherorte bearbeiten und löschen.<p>Zuvor konnten Konten und Speicherorte nur von der Person verwendet werden, die sie erstellt hat.</p><p>Diese Einstellungen sind verfügbar, wenn Benutzende Cloud-Exportkonten und Cloud-Exportspeicherorte konfigurieren.</p> <p>(Link zur aktualisierten Dokumentation folgt)</p> | 12. Juni 2024 | 30. Juni 2024 |
| **Neue Dokumentation für die Aktualisierung von Adobe Analytics auf Customer Journey Analytics** | Für Organisationen, die von Adobe Analytics auf Customer Journey Analytics umsteigen möchten, gibt es mehrere Aktualisierungsoptionen und viele Überlegungen, die abhängig von der aktuellen Adobe Analytics-Implementierung und den langfristigen Zielen der Organisation berücksichtigt werden sollten. Es stehen nun neue Dokumentationsressourcen zur Verfügung, die Ihnen helfen, Folgendes besser zu verstehen:<ul><li>Die verschiedenen vorhandenen Aktualisierungspfade</li><li>Welche Aktualisierungspfade auf der Grundlage der aktuellen Adobe Analytics-Implementierung einer Organisation verfügbar sind</li><li>Die Vor- und Nachteile jedes Aktualisierungspfads</li><li>Eine schrittweise Anleitung für jeden Aktualisierungspfad</li><li>Überlegungen zum Umgang mit historischen Daten</li></ul>[Erste Schritte mit dem Upgrade auf Customer Journey Analytics](https://experienceleague.adobe.com/de/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | Jetzt verfügbar |
| **Neue Dokumentation zu Anwendungsfällen für Datenexport** | In diesem neuen Abschnitt werden [Anwendungsfälle für den Datenexport](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-usecases/data-export/overview) wie<ul><li>Daten-Backup</li><li>Datenvalidierung</li><li>Data Lake-, Data Warehouse- oder BI-Tools</li><li>Bereitschaft für KI/ML</li></ul> Außerdem erfahren Sie, wie die Anwendungsfälle mithilfe von Experience Platform- und Customer Journey Analytics-Funktionen implementiert werden. | | Jetzt verfügbar |

{style="table-layout:auto"}

## Fehlerbehebungen in Customer Journey Analytics

AN-342309; AN-342312; AN-345267; AN-345909; AN-346016; AN-346049; AN-346052; AN-346287; AN-346624; AN-347919

## Wichtige Hinweise für Customer Journey Analytics-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| -/- | | |

{style="table-layout:auto"}

## Verwandte Ressourcen

* [Frühere Versionshinweise für Customer Journey Analytics 2024](/help/release-notes/2024.md)
* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
* [Versionshinweise zu Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
