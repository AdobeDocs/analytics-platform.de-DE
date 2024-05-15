---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4ad92a72f0ced81f84198da744fef9fe4c0a6b0b
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 37%

---

# Aktuelle Adobe Customer Journey Analytics-Versionshinweise (Mai 2024)

**Letzte Aktualisierung:**: Donnerstag, 15. Mai 2024

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom 15. Mai 2024 bis Juni 2024. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **BI-Erweiterung** | Die BI-Erweiterung ermöglicht SQL-Zugriff auf die Datenansichten, die Sie unter Customer Journey Analytics definiert haben. [Weitere Informationen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension) | | Donnerstag, 15. Mai 2024 |
| **Veröffentlichung von Zielgruppen in einem neuen Abschnitt „Zielgruppen“ in Experience Platform** | Von Customer Journey Analytics veröffentlichte Zielgruppen sind jetzt im neuen Abschnitt „Zielgruppen“ in Adobe Experience Platform verfügbar.<p>Bislang waren über Customer Journey Analytics veröffentlichte Zielgruppen in Experience Platform im Abschnitt „Segmente“ verfügbar.</p><p>Diese Verbesserung bietet folgende Vorteile:</p><ul><li>Zielgruppen werden nicht mehr mit 1 Stunde Verzögerung in Experience Platform angezeigt. Sie stehen vielmehr Sekunden nach ihrer Veröffentlichung zur Verfügung.</li><li>Zielgruppen können in Experience Platform mithilfe der Spalte „Herkunft“ sortiert werden, in der die Anwendung angezeigt wird, von der aus die Zielgruppe ursprünglich veröffentlicht wurde.</li><li>Mit den Filter- und Sortieroptionen in Experience Platform können Sie die relevanten Zielgruppen schneller finden.</li></ul> [Weitere Informationen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-components/audiences/publish) |  | Donnerstag, 15. Mai 2024 |
| **KI-Assistent für Customer Journey Analytics** | Ermöglicht Ihnen, Fragen in natürlicher Sprache in der Customer Journey Analytics-Benutzeroberfläche zu stellen und Antworten auf der Grundlage der Customer Journey Analytics-Dokumentation zu erhalten. (Link zur Dokumentation folgt) | | Freitag, 30. Mai 2024 |
| **Streaming-Medien: Senden von Webdaten mit dem Web SDK an das Adobe Experience Platform-Edge Network** | Sie können jetzt das Adobe Experience Platform Web SDK verwenden, um Webdaten zu Streaming-Medien an Adobe Experience Platform-Edge Network zu senden, sodass Sie personalisiertere Kampagnen erstellen und personalisiertere Inhalte bereitstellen können, sodass mehr Tracking-Daten für Berichte zur Verfügung stehen.<p>Diese Verbesserung bietet eine einheitliche Erfassungsmethode für Webimplementierungen in allen Plattformlösungen, z. B. Customer Journey Analytics, RT-CDP, AJO und Ereignisweiterleitung. Zuvor bestand die einzige Möglichkeit, Web-Daten für Streaming-Medien an Edge Network zu senden, in der Verwendung der Media Edge-API. [Weitere Informationen](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge) | | 31. Mai 2024 |
| **Abgeleitete Felder - Math-Funktion** | Ermöglicht Ihnen, einfache mathematische Operatoren in Datenansichten auszuführen, um Fragen zu Ihren Benutzern zu beantworten. Sie können beispielsweise Produkt-, Garantie- und Versandumsätze kombinieren. (Link zur Dokumentation folgt) | | Donnerstag, 5. Juni 2024 |
| **Abgeleitete Felder - Nächste oder Vorherige Funktion** | Hiermit können Sie den nächsten oder vorherigen Wert anzeigen. Mit welchen vorherigen Marketing-Kanälen hat beispielsweise jemand vor dem ausgewählten Marketing-Kanal interagiert? Oder mit welchen Seiten die Benutzer vor oder nach der ausgewählten Seite interagiert haben? Mit welchen Kanälen interagieren die beliebtesten Benutzer, bevor sie in den Speicher gehen?  (Link zur Dokumentation folgt) | | Donnerstag, 12. Juni 2024 |
| **Neue Dokumentation für die Aktualisierung von Adobe Analytics auf Customer Journey Analytics** | Für Unternehmen, die von Adobe Analytics auf Customer Journey Analytics aktualisieren, gibt es mehrere Upgrade-Optionen und viele Überlegungen, die basierend auf der aktuellen Adobe Analytics-Implementierung und den langfristigen Zielen eines Unternehmens zu beachten sind. Es stehen nun neue Dokumentationsressourcen zur Verfügung, die Ihnen helfen, Folgendes besser zu verstehen:<ul><li>Die verschiedenen vorhandenen Aktualisierungspfade</li><li>Welche Aktualisierungspfade sind basierend auf der aktuellen Adobe Analytics-Implementierung eines Unternehmens verfügbar?</li><li>Die Vor- und Nachteile jedes Aktualisierungspfads</li><li>Schrittweise Anleitung für jeden Aktualisierungspfad</li><li>Überlegungen zum Umgang mit historischen Daten</li></ul>[Erste Schritte mit dem Upgrade auf Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | Jetzt verfügbar |
| **Neue Dokumentation zu [Anwendungsfälle für Datenexport](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/data-export/overview)** | In diesem neuen Abschnitt werden Anwendungsfälle für den Datenexport beschrieben, z. B.<ul><li>Datensicherung</li><li>Datenvalidierung</li><li>Data Lake-, Data Warehouse- oder BI-Tools</li><li>Bereitschaft für KI/ML</li></ul> und wie sie mithilfe von Experience Platform- und Customer Journey Analytics-Funktionen implementiert werden. | | Jetzt verfügbar |

{style="table-layout:auto"}

## Fehlerbehebungen in Customer Journey Analytics

AN-342309; AN-342312; AN-345267; AN-345909; AN-346016; AN-346049; AN-346052; AN 346287; AN-346624; AN-347919

## Wichtige Hinweise für Customer Journey Analytics-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| Nicht angegeben | | |

{style="table-layout:auto"}

## Verwandte Ressourcen

* [Frühere Versionshinweise für Customer Journey Analytics 2024](/help/release-notes/2024.md)
* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
* [Versionshinweise zu Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
