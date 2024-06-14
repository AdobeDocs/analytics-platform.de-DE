---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 484ec8c32a8da4c33bb3236b9c7a8e1de83ead76
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 38%

---

# Aktuelle Adobe Customer Journey Analytics-Versionshinweise (Juni 2024)

**Letzte Aktualisierung**: Donnerstag, 12. Juni 2024

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom 6. Juni 2024 bis Juli 2024. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **KI-Assistent für Customer Journey Analytics** | Sie können in der Customer Journey Analytics-Benutzeroberfläche Fragen in natürlicher Sprache stellen und erhalten Antworten auf Grundlage der Customer Journey Analytics-Dokumentation. [Weitere Informationen](/help/ai-assistant.md) | | 6. Juni 2024 |
| **Diagrammbasierte Zuordnung: Zuordnung mithilfe des UIS-Diagrammexports** | Durch die grafikbasierte Zuordnung können Sie das Identitätsdiagramm verwenden, um eine bessere Ansicht der Journey des Kunden zu erhalten, indem Sie:<ul><li>Datensätze mit verschiedenen Kennungen verknüpfen, ohne zusätzliche Daten extrahieren, transformieren und laden zu müssen, um eine einzelne Kennung widerzuspiegeln.</li><li>Verbessern der Abdeckung der bevorzugten oder goldenen Identität für einen einzelnen Datensatz durch die gemeinsame Nutzung von Identitäten über Datensätze hinweg.</li><li>Abstimmung von in Real-time Customer Data Platform und Journey Optimizer erstellten Profilen mit Personen im Customer Journey Analytics.</li></ul>(Link zur Dokumentation folgt) |  | Samstag, 28. Juni 2024 |
| **B2B-Schematransformation – Person zu Konto** | Um personenbasierte Suchen nach B2B-Daten (einschließlich Konten, Chancen, Marketinglisten und Kampagnen) zu unterstützen, können Sie B2B-Lookup-Datensätze transformieren. Diese Umwandlung ist nur für Datensätze mit Daten für B2B-Lookup-Schemas verfügbar, die auf den folgenden Klassen basieren:<ul><li>XDM Business Account Person Relation</li><li>XDM Business Opportunity Person Relation</li><li>XDM Business Marketing List Members</li><li>XDM Business Campaign Members</li></ul>[Weitere Informationen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/transform-datasets-b2b-lookups) |  | 5. Juni 2024 |
| **Abgeleitete Felder – Math-Funktion** | Sie können einfache mathematische Operatoren in Datenansichten ausführen, um Fragen zu Ihren Benutzenden zu beantworten. Sie können beispielsweise Produkt-, Garantie- und Versandumsätze kombinieren. <p>[Weitere Informationen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#math)</p> | | 5. Juni 2024 |
| **Abgeleitete Felder - Nächste oder Vorherige Funktion** | Hiermit können Sie den nächsten oder vorherigen Wert anzeigen. Mit welchen vorherigen Marketing-Kanälen hat beispielsweise jemand vor dem ausgewählten Marketing-Kanal interagiert? Oder mit welchen Seiten die Benutzer vor oder nach der ausgewählten Seite interagiert haben? Mit welchen Kanälen interagieren die beliebtesten Benutzer, bevor sie in den Speicher gehen? <p>[Weitere Informationen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#next-or-previous)</p> | | 12. Juni 2024 |
| **Abgeleitete Felder - Zusammenfassungsfunktion** | Bietet die Möglichkeit, auf Ereignis-, Sitzungs- und Benutzerebene Aggregatfunktionen auf Metriken oder Dimensionen anzuwenden. (Link zur Dokumentation folgt) | | Donnerstag, 26. Juni 2024 |
| **Abgeleitete Felder - Deduplizierungsfunktion** | Hilft, die wiederholte Zählung eines Werts zu verhindern. Kann auf Benutzer- oder Sitzungsebene oder basierend auf dem eindeutigen Wert einer Dimension angewendet werden. (Link zur Dokumentation folgt) |  | Donnerstag, 26. Juni 2024 |
| **Aufnahmepriorität und Latenz** | Sie können Ihre Ereignisdaten jetzt innerhalb von 90 Minuten (SLT) in Customer Journey Analytics erfassen, unabhängig davon, ob die Daten 24 Stunden, 48 Stunden oder 7 Tage alt sind. Beachten Sie, dass sich diese Funktion je nach dem von Ihrem Unternehmen erworbenen SKU-Paket unterscheidet:<ul><li>CJA Priority Ingestion Standard: 24-Stunden-Daten innerhalb einer 90-minütigen SLT-Verarbeitung (verfügbar für CJA Foundation und CJA Select)</li><li>CJA Priority Ingestion Intermediate: 72 Stunden alte Daten innerhalb einer 90-minütigen SLT-Verarbeitung (verfügbar für CJA Prime)</li><li>CJA Priority Ingestion Erweitert: 1 Woche alte Daten innerhalb einer 90-minütigen SLT-Verarbeitung (verfügbar für CJA Ultimate)</li></ul> |  | 12. Juni 2024 |
| **Freigeben von Konten und Speicherorten, die für den Export und Import verwendet werden** | Benutzende können nun die von ihnen erstellten Konten und Speicherorte allen Benutzenden in ihrer Organisation zur Verfügung stellen. Nur Konto- und Standorteigner und Systemadministratoren können Konten und Standorte bearbeiten und löschen. Zuvor konnten Konten und Standorte nur von dem Benutzer verwendet werden, der sie erstellt hat. Diese Einstellungen sind verfügbar, wenn Benutzer [Konfigurieren von Cloud-Exportkonten](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts) und [Cloud-Exportspeicherorte konfigurieren](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-locations). | 12. Juni 2024 | Mittwoch, 18. Juni 2024 |
| **Auswählen mehrerer Felder in einem Dropdown-Filter** | Wenn einem Dropdown-Filter mehrere Felder hinzugefügt wurden, können Benutzer jetzt mehrere Felder gleichzeitig auswählen. Das Bedienfeld wird gefiltert, um eines der ausgewählten Felder einzuschließen. <p>Zuvor konnten Benutzer in einem Dropdown-Filter jeweils nur ein Feld auswählen.</p><p>(Der Dokumentationslink folgt.)</p> |  | Donnerstag, 19. Juni 2024 |
| **Inhaltsverzeichnis für Workspace-Projekte** | Für Projekte ist jetzt ein neues Inhaltsverzeichnis verfügbar. Das Inhaltsverzeichnis enthält Links, über die Benutzer schnell zu Bereichen und Visualisierungen innerhalb des Projekts springen können. <p>Das Inhaltsverzeichnis kann für einzelne Projekte oder für alle Projekte eines bestimmten Benutzers aktiviert werden.</p><p>(Der Dokumentationslink folgt.)<!--For more information, see "Display the project table of contents" in "Create projects".--> |  | Donnerstag, 19. Juni 2024 |
| **Erstellen von Hyperlinks für Dimensionselemente in einer Freiformtabelle** | Sie können Hyperlinks für ein oder mehrere Dimensionselemente erstellen, damit sie in einer Freiformtabelle in Analysis Workspace angeklickt werden können. <p>Sie können Hyperlinks für Dimensionselemente erstellen, die URL-Werte aufweisen, oder Sie können benutzerdefinierte URLs für Dimensionselemente erstellen, die Nicht-URL-Werte haben.</p><p>Sie können dynamische benutzerdefinierte URLs für mehrere Dimensionselemente mithilfe von Variablen erstellen. Variablen können auf den Wert eines Dimensionselements verweisen oder auf die Aufschlüsselungsdimension verweisen.</p><p>(Der Dokumentationslink folgt.)<!--For more information, see "Add hyperlinks to dimensions in a freeform table."--></p> |  | Donnerstag, 19. Juni 2024 |
| **Veröffentlichung von Zielgruppen in einem neuen Abschnitt „Zielgruppen“ in Experience Platform** | Von Customer Journey Analytics veröffentlichte Zielgruppen sind jetzt im neuen Abschnitt „Zielgruppen“ in Adobe Experience Platform verfügbar.<p>Bislang waren über Customer Journey Analytics veröffentlichte Zielgruppen in Experience Platform im Abschnitt „Segmente“ verfügbar.</p><p>Diese Verbesserung bietet folgende Vorteile:</p><ul><li>Zielgruppen werden nicht mehr mit 1 Stunde Verzögerung in Experience Platform angezeigt. Sie stehen vielmehr Sekunden nach ihrer Veröffentlichung zur Verfügung.</li><li>Zielgruppen können in Experience Platform mithilfe der Spalte „Herkunft“ sortiert werden, in der die Anwendung angezeigt wird, von der aus die Zielgruppe ursprünglich veröffentlicht wurde.</li><li>Mit den Filter- und Sortieroptionen in Experience Platform können Sie die relevanten Zielgruppen schneller finden.</li></ul> <p>(Link zur Dokumentation folgt)</p> |  | Montag, 14. Juli 2024 |

{style="table-layout:auto"}

## Fehlerbehebungen in Customer Journey Analytics

AN-345454; AN-349816; AN-349905; AN-350617

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
