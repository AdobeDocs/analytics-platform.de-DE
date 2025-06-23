---
title: Aktuelle Versionshinweise zu Customer Journey Analytics
description: Anzeigen der neuesten Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 5722b858e173e9704ec51afe1f0a694cf04a301f
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 78%

---

# Aktuelle Versionshinweise zu Adobe Customer Journey Analytics (Juni 2025)

**Letzte Aktualisierung**: 18. Juni 2025


Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom Dienstag, 2. Juni 2025 bis zum Mittwoch, 15. Juli 2025. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Das linke Panel in Analysis Workspace wird beim Bewegen des Mauszeigers nicht mehr geöffnet und geschlossen** | Das linke Panel in Analysis Workspace wird verwendet, um Ihrem Projekt Elemente wie Komponenten, Panels und Visualisierungen hinzuzufügen. Die Option zum vorübergehenden Öffnen des linken Panels durch Bewegen des Mauszeigers über eines der Symbole ganz links ist nicht mehr verfügbar. Klicken Sie stattdessen einfach auf eines dieser Symbole, damit das Panel geöffnet bleibt, und klicken Sie dann auf dasselbe Symbol, um es zu schließen. |  | &#x200B;2. Juni 2025 <p>(Veröffentlichung ursprünglich für den 29. Mai 2025 geplant)</p> |
| **Customer Journey Analytics B2B Edition** | Customer Journey Analytics B2B Edition unterstützt B2B-Unternehmen dabei, ihre Marketing-, Vertriebs- und Produkt-Teams aufeinander abzustimmen, indem es verwertbare Kontoerkenntnisse bereitstellt, die das Umsatzwachstum fördern. Wenn das Konto in den Mittelpunkt des Datenmodells gestellt wird, konzentriert sich die gesamte Analyse auf die Konto-Journey. Durch das Hinzufügen einer neuen Ebene von Entitäten (Konten, Opportunities und Käufergruppen) zu Personen- und zeitbasierten Ereignissen erhalten Sie ein vollständiges Bild vom Lebenszyklus des B2B-Marketings und Umsatzes. [Weitere Informationen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 18. Juni 2025 |
| **Unterstützung für sichere Cloud-Ziele in Report Builder** | Sie können jetzt Berichte aus Report Builder in die folgenden Cloud-Speicher-Ziele exportieren:<ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul><p>Zuvor konnten Sie Arbeitsmappen per E-Mail für andere Benutzende freigeben, aber keine Berichte aus Report Builder in Cloud-Ziele exportieren.</p><p>Weitere Informationen finden Sie unter &quot;[ von Arbeitsmappen durch Exportieren in Cloud-Ziele](/help/report-builder/report-builder-export.md).</p> |  | &#x200B;19. Juni 2025 (ursprünglich 18. Juni 2025) |
| **Neues Vorschauerlebnis** | Das Panel „Vorschau“, das zur Vorschau von Segmenten, berechneten Metriken und mehr verwendet wird, nutzt jetzt eine Darstellung mit horizontalen Balken anstelle einer Darstellung mit Ringdiagrammen. |  | 18. Juni 2025 |
| **Geändertes Dialogfeld für Attributionsmodelle** | Sie können nun den Container und den Zeitraum separat im Dialogfeld für Attributionsmodelle definieren. |  | 18. Juni 2025 |
| **Verbindungszuordnung** | Eine neue [Verbindungszuordnungs-Schnittstelle](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-connections/create-connection#connection-map) ist verfügbar, um Ihre Verbindungskonfiguration visuell anzuzeigen. |  | 18. Juni 2025 |
| **Hinzufügen und Anzeigen von Kommentaren in Analysis Workspace-Projekten** | Eine neue [Kommentarfunktion](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) in Analysis Workspace ermöglicht es Ihnen, im Rahmen eines Analysis Workspace-Projekts Erkenntnisse zu teilen und Fragen zu stellen. Dadurch können Diskussionen über die Daten optimiert werden, sodass Gespräche im Kontext der diskutierten Daten geführt werden. Sie können <ul><li>jedes Analysis Workspace-Projekt kommentieren, auf das Sie Zugriff haben,</li><li>einen bestimmten Punkt in einer Visualisierung kommentieren oder allgemeine Kommentare zu einem Projekt abgeben,</li><li>andere Benutzende taggen, um sie über Ihre Kommentare zu informieren,</li><li>vorhandene Kommentare verwalten (bearbeiten, anheften, schließen usw.).</li></ul>Customer Journey Analytics-Admins können die [Kommentarfunktion auf Organisationsebene deaktivieren](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences). Projektverantwortliche können die [Kommentarfunktion auf Projektebene deaktivieren](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects). | &#x200B;25. Juni 2025 | Samstag, 11. Juli 2025 <p>(Veröffentlichung ursprünglich für den 29. Mai 2025 geplant)</p> |
| **Unterstützung für das Chrome-Vorab-Rendering** | Steuern Sie, wie sich Datenerfassungsbibliotheken verhalten, wenn Chrome eine Seite vorab rendert. (Link zur Dokumentation folgt) |  | 30. Juni 2025 |

## Fehlerbehebungen in Customer Journey Analytics

**Warnhinweise**: AN-379554
**Analysis Workspace**: AN-339607; AN-379222; AN-381138; AN-383291
**B2B**: AN-376028
**BI-Erweiterung für Tableau**: AN-377488
**Komponenten**: AN-376174
**Datenansichten**: AN-379011
**Exportspeicherorte**: AN-382191
**Vollständiger Tabellenexport**: AN-375646; AN-376986; AN-380355; AN-381310
**Journey-Arbeitsfläche**: AN-375865; AN-378011
**Report Builder**: AN-369786; AN-371395; AN-372809
**Reporting**: AN-372615; AN-378578;


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
