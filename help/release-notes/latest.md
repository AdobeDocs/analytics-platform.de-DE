---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 1534b628841a5b4588379b944822073f3288d710
workflow-type: tm+mt
source-wordcount: '1129'
ht-degree: 79%

---

# Aktuelle Versionshinweise zu Adobe Customer Journey Analytics (Juni 2024)

**Letzte Aktualisierung**: Mittwoch, 18. Juni 2024

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom 6. Juni 2024 bis Juli 2024. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **KI-Assistent für Customer Journey Analytics** | Sie können in der Customer Journey Analytics-Benutzeroberfläche Fragen in natürlicher Sprache stellen und erhalten Antworten auf Grundlage der Customer Journey Analytics-Dokumentation. [Weitere Informationen](/help/ai-assistant.md) | | 6. Juni 2024 |
| **Diagrammbasiertes Stitching** | Durch eine grafikbasierte Zuordnung können Sie das Identitätsdiagramm aus dem Experience Platform Identity-Dienst verwenden, um eine bessere Ansicht der Journey des Kunden zu erhalten, indem Sie:<ul><li>Datensätze mit verschiedenen Kennungen verknüpfen, ohne zusätzliche Daten extrahieren, transformieren und laden zu müssen, um eine einzelne Kennung widerzuspiegeln.</li><li>Die Abdeckung der bevorzugten oder goldenen Identität für einen einzelnen Datensatz durch die gemeinsame Nutzung von Identitäten über Datensätze hinweg verbessern.</li><li>Die in Real-time Customer Data Platform und Journey Optimizer erstellten Profile mit Personen in Customer Journey Analytics abstimmen.</li></ul>[Weitere Informationen](/help/stitching/overview.md) |  | 28. Juni 2024 |
| **B2B-Schematransformation – Person zu Konto** | Um personenbasierte Suchen nach B2B-Daten (einschließlich Konten, Gelegenheiten, Marketing-Listen und Kampagnen) zu unterstützen, können Sie B2B-Lookup-Datensätze transformieren. Diese Transformation ist nur für Datensätzen mit Daten für B2B-Suchschemata verfügbar, die auf den folgenden Klassen basieren:<ul><li>XDM Business Account Person Relation</li><li>XDM Business Opportunity Person Relation</li><li>XDM Business Marketing List Members</li><li>XDM Business Campaign Members</li></ul>[Weitere Informationen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-connections/transform-datasets-b2b-lookups) |  | 5. Juni 2024 |
| **Abgeleitete Felder – Math-Funktion** | Sie können einfache mathematische Operatoren in Datenansichten ausführen, um Fragen zu Ihren Benutzenden zu beantworten. Sie können beispielsweise Produkt-, Garantie- und Versandumsätze kombinieren. [Weitere Informationen](/help/data-views/derived-fields/derived-fields.md#math)</p> | | 5. Juni 2024 |
| **Abgeleitete Felder: Nächste oder vorherige Funktion** | Hiermit können Sie den nächsten oder vorherigen Wert anzeigen. Mit welchen vorherigen Marketing-Kanälen hat beispielsweise jemand vor dem ausgewählten Marketing-Kanal interagiert? Oder mit welchen Seiten haben Benutzende vor oder nach der ausgewählten Seite interagiert? Mit welchen Kanälen interagieren die beliebtesten Benutzer, bevor sie in den Speicher gehen? [Weitere Informationen](/help/data-views/derived-fields/derived-fields.md#next-or-previous)</p> | | 12. Juni 2024 |
| **Abgeleitete Felder - Zusammenfassungsfunktion** | Bietet die Möglichkeit, auf Ereignis-, Sitzungs- und Benutzerebene Aggregationstypfunktionen auf Metriken oder Dimensionen anzuwenden. [Weitere Informationen](/help/data-views/derived-fields/derived-fields.md#summarize) | | 26. Juni 2024 |
| **Abgeleitete Felder – Deduplizierungsfunktion** | Hilft, die wiederholte Zählung eines Werts zu verhindern. Kann auf Benutzer- oder Sitzungsebene oder basierend auf dem eindeutigen Wert einer Dimension angewendet werden. (Link zur Dokumentation folgt) |  | Donnerstag, 10. Juli 2024 |
| **Aufnahmepriorität und Latenz** | Sie können Ihre Ereignisdaten jetzt innerhalb von 90 Minuten (SLT) in Customer Journey Analytics aufnehmen, unabhängig davon, ob die Daten 24 Stunden, 48 Stunden oder 7 Tage alt sind. Beachten Sie, dass sich diese Funktion je nach dem von Ihrem Unternehmen erworbenen SKU-Paket unterscheidet:<ul><li>CJA Priority Ingestion Basic: 24 Stunden alte Daten werden innerhalb von 90 Minuten mit SLT verarbeitet (verfügbar für CJA Foundation und CJA Select)</li><li>CJA Priority Ingestion Intermediate: 72 Stunden alte Daten werden innerhalb von 90 Minuten mit SLT verarbeitet (verfügbar für CJA Prime)</li><li>CJA Priority Ingestion Advanced: 1 Woche alte Daten innerhalb von 90 Minuten mit SLT verarbeitet (verfügbar für CJA Ultimate)</li></ul> |  | 12. Juni 2024 |
| **Freigeben von Konten und Speicherorten, die für den Export und Import verwendet werden** | Benutzende können nun die von ihnen erstellten Konten und Speicherorte allen Benutzenden in ihrer Organisation zur Verfügung stellen. Nur die Personen, denen Konten bzw. Speicherorte gehören, und System-Admins können Konten und Speicherorte bearbeiten und löschen. Zuvor konnten Konten und Speicherorte nur von der Person verwendet werden, die sie erstellt hat. Diese Einstellungen sind verfügbar, wenn Benutzende [Cloud-Exportkonten konfigurieren](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts) und [Cloud-Exportspeicherorte konfigurieren](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-components/exports/cloud-export-locations). | 12. Juni 2024 | Mitte Juli 2024 |
| **Auswählen mehrerer Felder in einem Dropdown-Filter** | Wenn einem Dropdown-Filter mehrere Felder hinzugefügt wurden, können Benutzende jetzt mehrere Felder gleichzeitig auswählen. Das Panel wird gefiltert, um alle ausgewählten Felder einzuschließen. <p>Zuvor konnten Benutzende in einem Dropdown-Filter jeweils nur ein Feld auswählen.</p><p>Die Option, eine Auswahl in einem Dropdown-Filter erforderlich zu machen, wurde beim Rechtsklick auf einen Dropdown-Filter in das Menü verschoben.</p><p>Zuvor konnten Benutzer im Dropdown-Menü neben der Option Kein Filter auf (x) klicken.</p><p>Weitere Informationen finden Sie unter [Statische Dropdown-Filter](/help/analysis-workspace/c-panels/panels.md#static-drop-down-filters) in [Bedienfelder - Übersicht](/help/analysis-workspace/c-panels/panels.md).</p><p>[Videodemonstration zu dieser Funktion anzeigen](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/navigating-workspace-projects/use-multi-select-drop-down-filters).</p> |  | 19. Juni 2024 |
| **Inhaltsverzeichnis für Workspace-Projekte** | Für Projekte ist jetzt ein neues Inhaltsverzeichnis verfügbar. Das Inhaltsverzeichnis enthält Links, über die Benutzer schnell zwischen Bedienfeldern und Visualisierungen innerhalb des Projekts wechseln können. <p>Das Inhaltsverzeichnis ist in allen Projekten in der linken Leiste verfügbar.</p><p>Weitere Informationen finden Sie unter [Projektinhaltsverzeichnis](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md).</p><p>[Videodemonstration zu dieser Funktion anzeigen](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/navigating-workspace-projects/create-a-toc-in-analysis-workspace).</p> |  | 19. Juni 2024 |
| **Erstellen von Hyperlinks für Dimensionselemente in einer Freiformtabelle** | Sie können Hyperlinks für ein oder mehrere Dimensionselemente erstellen, damit sie in einer Freiformtabelle in Analysis Workspace angeklickt werden können. <p>Sie können Hyperlinks für Dimensionselemente erstellen, die URL-Werte aufweisen, oder Sie können benutzerdefinierte URLs für Dimensionselemente erstellen, die Nicht-URL-Werte haben.</p><p>Sie können dynamische benutzerdefinierte URLs für mehrere Dimensionselemente mithilfe von Variablen erstellen. Variablen können auf den Wert eines Dimensionselements oder auf die Aufschlüsselungsdimension verweisen.</p><p>Weitere Informationen finden Sie unter [Erstellen von Hyperlinks für Dimensionen in einer Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md).</p><p>[Videodemonstration zu dieser Funktion anzeigen](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/tips-and-tricks/create-hyperlinks-in-freeform-tables).</p> |  | 19. Juni 2024 |
| **Verwenden Ihrer Customer Journey Analytics-Datenansicht mit Adobe Journey Optimizer** | Eine neue Konfigurationsoption in Customer Journey Analytics ermöglicht es Ihnen, eine Customer Journey Analytics-Datenansicht zu bestimmen, die mit Adobe Journey Optimizer verwendet werden kann, ohne dass eine manuelle Konfiguration erforderlich ist. <p>Informationen zum Aktivieren dieser Konfigurationsoption finden Sie unter [Kompatibilität](/help/data-views/create-dataview.md#compatibility) Abschnitt in [Datenansicht erstellen oder bearbeiten](/help/data-views/create-dataview.md).</p><p>Zuvor mussten Sie beim Anzeigen von Journey Optimizer-Daten unter Customer Journey Analytics manuell eine Verbindung und Datenansichten konfigurieren.</p> |  | 19. Juni 2024 |
| **Veröffentlichung von Zielgruppen in einem neuen Abschnitt „Zielgruppen“ in Experience Platform** | Von Customer Journey Analytics veröffentlichte Zielgruppen sind jetzt im neuen Abschnitt „Zielgruppen“ in Adobe Experience Platform verfügbar.<p>Bislang waren über Customer Journey Analytics veröffentlichte Zielgruppen in Experience Platform im Abschnitt „Segmente“ verfügbar.</p><p>Diese Verbesserung bietet folgende Vorteile:</p><ul><li>Zielgruppen werden nicht mehr mit 1 Stunde Verzögerung in Experience Platform angezeigt. Sie stehen vielmehr Sekunden nach ihrer Veröffentlichung zur Verfügung.</li><li>Zielgruppen können in Experience Platform mithilfe der Spalte „Herkunft“ sortiert werden, in der die Anwendung angezeigt wird, von der aus die Zielgruppe ursprünglich veröffentlicht wurde.</li><li>Mit den Filter- und Sortieroptionen in Experience Platform können Sie die relevanten Zielgruppen schneller finden.</li></ul> <p>(Link zur Dokumentation folgt)</p> |  | 14. Juli 2024 |

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
* [Versionshinweise zum Streaming-Mediensammlungs-Add-on](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
