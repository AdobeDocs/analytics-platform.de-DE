---
title: Aktuelle Versionshinweise zu Customer Journey Analytics
description: Anzeigen der neuesten Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: df8a10c674ed64d0341209fbe0a700a5c94b3b75
workflow-type: tm+mt
source-wordcount: '1093'
ht-degree: 36%

---

# Aktuelle Versionshinweise zu Adobe Customer Journey Analytics (Mai 2025)

**Letzte Aktualisierung:**: Freitag, 22. Mai 2025


Diese Versionshinweise decken den Veröffentlichungszeitraum vom 22. April bis zum 18. Juni 2025 ab. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **XDM-Felder zum Erfassen von Streaming-Mediendaten in Adobe Experience Platform wurden aktualisiert** | Beim Erfassen von Streaming-Mediendaten in Adobe Experience Platform sollten die XDM-Feldpfade, die unter der Überschrift „XDM-Feldpfad“ der Dokumentation zu Streaming-Medienparametern angezeigt werden, nicht mehr verwendet werden. Diese Feldpfade befinden sich auf den folgenden Seiten und sind als „Veraltet“ gekennzeichnet: [Audio- und Videoparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Anzeigenparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/ad-parameters), [Kapitelparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/chapter-parameters), [Player-](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/player-state-parameters) und [Qualitätsparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/quality-parameters). <p>Stattdessen sollten Kunden zu den `mediaReporting` Feldpfaden migrieren, wie sie unter der Überschrift „XDM-Feldpfad für Berichterstellung“ in der Dokumentation zu Streaming-Medienparametern oben beschrieben sind.<p>Während einer Übergangszeit von drei Monaten wird die Datenaufnahme in den veralteten XDM-Feldpfaden fortgesetzt. Ende Juli 2025 werden veraltete Feldpfade jedoch vollständig entfernt und nicht mehr in der Adobe Experience Platform-Schema-Benutzeroberfläche angezeigt. Daten werden nur unter Verwendung der `mediaReporting` Feldpfade gesendet.<p>Kunden, die den Analytics-Quell-Connector implementiert haben, um Streaming-Mediendaten vor dem 22. April 2025 in Platform zu erfassen, müssen ihre vorhandenen Konfigurationen migrieren, um die neuen Feldpfade zu verwenden. Diese Migration muss bis Ende Juli 2025 abgeschlossen sein. Wenden Sie sich an Ihren Adobe Consulting-Dienst oder Ihr Kontoteam, um Unterstützung bei der Migration zu erhalten. Für Kundinnen und Kunden, die den Analytics-Quell-Connector nach dem 22. April 2025 implementieren, ist keine Aktion erforderlich.</p> |  | 22. April 2025 |
| **Zuordnung: Abrufen persistenter und vorübergehender IDs aus XDM IdentityMap** | Diese Funktion bietet Unterstützung für die Verwendung von Identitäten im Zuordnungsprozess, die in der XDM identityMap gespeichert sind. Die identityMap kann für die persistente oder die vorübergehende ID für die feldbasierte Zuordnung und für die persistente ID für die diagrammbasierte Zuordnung verwendet werden.  Sie können entweder einen bestimmten Namespace oder eine primäre Identität aus der identityMap verwenden. Weitere Informationen sind [hier](https://experienceleague.adobe.com/de/docs/analytics-platform/using/stitching/fbs#identitymap) und [hier](https://experienceleague.adobe.com/de/docs/analytics-platform/using/stitching/gbs#identitymap) verfügbar |  | Dienstag, 28. April 2025 |
| **Freigegebene Metriken und Dimensionen in allen Datenansichten** | Ermöglichen die Anwendung von Dimensions- und Metrikeinstellungen auf mehrere Datenansichten. Änderungen an einer freigegebenen Dimension oder Metrik gelten für alle Instanzen dieser Dimension oder Metrik in allen anwendbaren Datenansichten. Diese Benutzeroberfläche ermöglicht es Customer Journey Analytics-Admins, Komponenten einfacher zu verwalten, wenn viele Datenansichten verwendet werden. [Weitere Informationen](/help/data-views/shared-metrics-dimensions/smd-overview.md) |  | 30. April 2025 |
| **Erhöhung der vollständigen Tabellenexportbeschränkungen** | Adobe hat die Anzahl der Spalten, die Sie mit dem [vollständigen Tabellenexport) verwenden können, ](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/export/export-cloud#comparison-of-full-table-export-in-customer-journey-analytics-to-data-warehouse-in-adobe-analytics) von 5 Dimensionen und 5 Metriken auf 10 Dimensionen und 10 Metriken erhöht. Dies gilt für alle Customer Journey Analytics-Ebenen. Die Berechtigungen für die Anzahl der Zeilen, die exportiert werden können, ändern sich nicht. |  | 30. April 2025 |
| **Dimension „Ereignistiefe“** | Eine neue [Dimension Ereignistiefe](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/component-reference#required-standard-components) wurde zur Liste der erforderlichen Standardkomponenten für eine Datenansicht hinzugefügt. |  | Freitag, 8. Mai 2025 |
| **Deaktivieren der Manifestdatei beim Exportieren vollständiger Tabellen** | Damit können Sie die Manifestdatei deaktivieren, die standardmäßig enthalten ist, wenn Sie vollständige Tabellen aus Analysis Workspace exportieren. [Weitere Informationen](/help/analysis-workspace/export/export-cloud.md) |  | Mittwoch, 20. Mai 2025 |
| **Data Insights Agent** | Data Insights Agent, Teil des KI-Assistenten in Customer Journey Analytics, ist ein generativer KI-Gesprächsagent. Sie verwendet Komponenten aus Ihrer Datenansicht und Ihren tatsächlichen Daten, um datenorientierte Fragen schnell und effizient zu beantworten, indem relevante Visualisierungen in Analysis Workspace erstellt werden. [Weitere Informationen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai) |  | Donnerstag, 28. Mai 2025 |
| Das Format **Dimension ist für Dimensionen vom Typ „Double“ standardmäßig auf 2 festgelegt** | Für Schemata mit dem Datentyp Double beträgt das Dimensionsformat jetzt standardmäßig 2 Dezimalstellen. Sie können diese Zahl in 0 bis 5 Dezimalstellen ändern.<p>Zuvor war das Format standardmäßig auf 0 Dezimalstellen festgelegt.</p><p>Das bedeutet, dass bei Verwendung von Dimensionen vom Typ „Double“ in Analysis Workspace-Berichten standardmäßig keine Dezimalstellen angezeigt wurden. Dieselben Berichte zeigen jetzt 2 Dezimalstellen an.</p><p>Weitere Informationen zum Aktualisieren der Anzahl der Dezimalstellen, die für Dimensionen vom Typ „Double“ angezeigt werden, finden Sie unter [Formatieren von Komponenteneinstellungen](/help/data-views/component-settings/format.md).</p> | | &#x200B;29. Mai 2025 |
| **Das linke Panel in Analysis Workspace wird beim Bewegen des Mauszeigers nicht mehr geöffnet und geschlossen** | Das linke Panel in Analysis Workspace wird verwendet, um Ihrem Projekt Elemente wie Komponenten, Panels und Visualisierungen hinzuzufügen. Die Option zum vorübergehenden Öffnen des linken Panels durch Bewegen des Mauszeigers über eines der Symbole ganz links ist nicht mehr verfügbar. Klicken Sie stattdessen einfach auf eines dieser Symbole, um das Panel geöffnet zu lassen, und klicken Sie dann auf dasselbe Symbol, um es zu schließen. |  | Dienstag, 2. Juni 2025 <p>(Ursprünglich geplant für die Veröffentlichung am 29. Mai 2025)</p> |
| **Customer Journey Analytics B2B edition** | Customer Journey Analytics B2B edition unterstützt B2B-Unternehmen bei der Abstimmung ihrer Marketing-, Vertriebs- und Produkt-Teams, indem es umsetzbare Account Insights bereitstellt, die das Umsatzwachstum fördern. Wenn der Account in den Mittelpunkt des Datenmodells gestellt wird, konzentriert sich die gesamte Analyse auf die Account-Journey. Durch das Hinzufügen einer neuen Ebene von Entitäten (Konten, Opportunities und Einkaufsgruppen) zusätzlich zu Personen- und zeitbasierten Ereignissen erhalten Sie ein vollständiges Bild vom Lebenszyklus des B2B-Marketings und des Umsatzes. [Weitere Informationen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | Donnerstag, 18. Juni 2025 |
| **Hinzufügen und Anzeigen von Kommentaren in Analysis Workspace-Projekten** | Eine neue [Kommentierungsfunktion](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) in Analysis Workspace ermöglicht es Ihnen, Einblicke zu teilen und Fragen im Kontext eines Analysis Workspace-Projekts zu stellen. Dadurch können Diskussionen über die Daten gestrafft werden, sodass Gespräche im Kontext der Daten geführt werden, die besprochen werden. Sie können <ul><li>Kommentieren Sie jedes Analysis Workspace-Projekt, auf das Sie Zugriff haben</li><li>Kommentieren Sie einen bestimmten Punkt in einer Visualisierung oder geben Sie allgemeine Kommentare zu einem Projekt ab</li><li>Taggen Sie andere Benutzer, um sie über Ihre Kommentare zu informieren</li><li>Verwalten vorhandener Kommentare (Bearbeiten, Einfügen, Auflösen usw.)</li></ul>Customer Journey Analytics-Administratoren können [Kommentieren auf Unternehmensebene deaktivieren](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences). Projektbesitzer können [Kommentare auf Projektebene deaktivieren](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects). |  | Donnerstag, 25. Juni 2025 <p>(Ursprünglich geplant für die Veröffentlichung am 29. Mai 2025)</p> |

## Fehlerbehebungen in Customer Journey Analytics

**Analysis Workspace**: AN-361874; AN-371360; AN-373079; AN-374382; AN-374447; AN-375277; AN-375680
**Audiences**: AN-372343
**Auditprotokoll**: AN-378168
**VERBINDUNGEN**: AN-373121; AN-372996
**Datenlöschung**: AN-375450
**Abgeleitete Felder**: AN-373689; AN-377852
**Exportspeicherorte**: AN-374167
**Journey-Arbeitsfläche**: AN-373319
**Report Builder**: AN-369786
**Reporting**: AN-377326; AN-378051
**Reporting Activity Manager**: AN-377148


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
