---
title: Aktuelle Versionshinweise zu Customer Journey Analytics
description: Anzeigen der neuesten Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: df8a10c674ed64d0341209fbe0a700a5c94b3b75
workflow-type: ht
source-wordcount: '1093'
ht-degree: 100%

---

# Aktuelle Versionshinweise zu Adobe Customer Journey Analytics (Mai 2025)

**Letzte Aktualisierung:**: 22. Mai 2025


Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom 22. April bis zum 18. Juni 2025. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **AktualisierteXDM-Felder zum Erfassen von Streaming-Mediendaten in Adobe Experience Platform** | Beim Erfassen von Streaming-Mediendaten in Adobe Experience Platform sollten die XDM-Feldpfade unter der Überschrift „XDM-Feldpfad“ in der Dokumentation zu den Streaming-Medienparametern nicht mehr verwendet werden. Diese Feldpfade befinden sich auf den folgenden Seiten und sind als „veraltet“ gekennzeichnet: [Audio- und Videoparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Anzeigenparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/ad-parameters), [Kapitelparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/chapter-parameters), [Player-Statusparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/player-state-parameters) und [Qualitätsparameter](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/variables/quality-parameters). <p>Stattdessen sollten Kundinnen und Kunden zu den `mediaReporting`-Feldpfaden migrieren, wie unter der Überschrift „XDM-Feldpfad für Berichterstellung“ in der oben angegebenen Dokumentation zu Streaming-Medienparametern beschrieben.<p>Während einer Übergangszeit von drei Monaten wird die Datenaufnahme über die veralteten XDM-Feldpfade fortgesetzt. Ende Juli 2025 werden die veralteten Felder jedoch vollständig entfernt und nicht mehr in der Adobe Experience Platform-Schema-Benutzeroberfläche angezeigt. Daten werden nur mithilfe der `mediaReporting`-Feldpfade gesendet.<p>Kundinnen und Kunden, die den Analytics-Quell-Connector zum Erfassen von Streaming-Mediendaten vor dem 22. April 2025 in Platform implementiert haben, müssen ihre vorhandenen Konfigurationen migrieren, um die neuen Feldpfade verwenden zu können. Diese Migration muss bis Ende Juli 2025 abgeschlossen sein. Wenden Sie sich an Ihren Adobe Consulting-Dienst oder Ihr Kontoteam, um Unterstützung bei der Migration zu erhalten. Für Kundinnen und Kunden, die den Analytics-Quell-Connector nach dem 22. April 2025 implementieren, ist keine Aktion erforderlich.</p> |  | 22. April 2025 |
| **Zuordnung: Abrufen persistenter und vorübergehender IDs aus XDM IdentityMap** | Diese Funktion bietet Unterstützung für die Verwendung von Identitäten im Zuordnungsprozess, die in der XDM identityMap gespeichert sind. Die identityMap kann für die persistente oder die vorübergehende ID für die feldbasierte Zuordnung und für die persistente ID für die diagrammbasierte Zuordnung verwendet werden.  Sie können entweder einen bestimmten Namespace oder eine primäre Identität aus der identityMap verwenden. Weitere Informationen sind [hier](https://experienceleague.adobe.com/de/docs/analytics-platform/using/stitching/fbs#identitymap) und [hier](https://experienceleague.adobe.com/de/docs/analytics-platform/using/stitching/gbs#identitymap) verfügbar |  | 28. April 2025 |
| **Freigegebene Metriken und Dimensionen in allen Datenansichten** | Ermöglichen die Anwendung von Dimensions- und Metrikeinstellungen auf mehrere Datenansichten. Änderungen an einer freigegebenen Dimension oder Metrik gelten für alle Instanzen dieser Dimension oder Metrik in allen anwendbaren Datenansichten. Diese Benutzeroberfläche ermöglicht es Customer Journey Analytics-Admins, Komponenten einfacher zu verwalten, wenn viele Datenansichten verwendet werden. [Weitere Informationen](/help/data-views/shared-metrics-dimensions/smd-overview.md) |  | 30. April 2025 |
| **Höhere Limits für vollständige Tabellenexporte** | Adobe hat die Anzahl der Spalten, die Ihnen für [vollständige Tabellenexporte](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/export/export-cloud#comparison-of-full-table-export-in-customer-journey-analytics-to-data-warehouse-in-adobe-analytics) zur Verfügung stehen, von 5 Dimensionen und 5 Metriken auf 10 Dimensionen und 10 Metriken erhöht. Dies gilt für alle Customer Journey Analytics-Ebenen. Die Berechtigungen für die Anzahl der Zeilen, die exportiert werden können, ändern sich nicht. |  | 30. April 2025 |
| **Dimension „Ereignistiefe“** | Der Liste der erforderlichen Standardkomponenten für eine Datenansicht wurde eine neue [Dimension „Ereignistiefe“](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/component-reference#required-standard-components) hinzugefügt. |  | 8. Mai 2025 |
| **Deaktivieren der Manifestdatei bei vollständigen Tabellenexporten** | Damit können Sie die Manifestdatei deaktivieren, die bei vollständigen Tabellenexporten aus Analysis Workspace standardmäßig enthalten ist. [Weitere Informationen](/help/analysis-workspace/export/export-cloud.md) |  | &#x200B;20. Mai 2025 |
| **Data Insights Agent** | Der Data Insights Agent, Teil des KI-Assistenten in Customer Journey Analytics, ist ein auf generativer KI basierender Konversationsagent. Er nutzt Komponenten aus Ihrer Datenansicht und Ihren tatsächlichen Daten, um datenorientierte Fragen schnell und effizient zu beantworten, indem er relevante Visualisierungen in Analysis Workspace erstellt. [Weitere Informationen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai) |  | 28. Mai 2025 |
| **Das Dimensionsformat für Dimensionen vom Typ „Duplikat“ ist standardmäßig auf 2 festgelegt** | Für Schemata mit dem Datentyp „Duplikat“ sind für das Dimensionsformat jetzt standardmäßig 2 Dezimalstellen festgelegt. Sie können diese Anzahl in 0 bis 5 Dezimalstellen ändern.<p>Zuvor war das Format standardmäßig auf 0 Dezimalstellen festgelegt.</p><p>Das bedeutet, dass bei Verwendung von Dimensionen vom Typ „Duplikat“ in Analysis Workspace-Berichten standardmäßig keine Dezimalstellen angezeigt wurden. Dieselben Berichte zeigen jetzt 2 Dezimalstellen an.</p><p>Weitere Informationen zum Aktualisieren der Anzahl der Dezimalstellen, die für Dimensionen vom Typ „Duplikat“ angezeigt werden, finden Sie unter [Formatieren von Komponenteneinstellungen](/help/data-views/component-settings/format.md).</p> | | 29. Mai 2025 |
| **Linkes Panel in Analysis Workspace wird beim Bewegen des Mauszeigers nicht mehr geöffnet und geschlossen** | Das linke Panel in Analysis Workspace wird verwendet, um Ihrem Projekt Elemente wie Komponenten, Panels und Visualisierungen hinzuzufügen. Die Option zum vorübergehenden Öffnen des linken Panels durch Bewegen des Mauszeigers über eines der Symbole ganz links ist nicht mehr verfügbar. Klicken Sie stattdessen einfach auf eines dieser Symbole, damit das Panel geöffnet bleibt, und klicken Sie dann auf dasselbe Symbol, um es zu schließen. |  | &#x200B;2. Juni 2025 <p>(Veröffentlichung ursprünglich für den 29. Mai 2025 geplant)</p> |
| **Customer Journey Analytics B2B Edition** | Customer Journey Analytics B2B Edition unterstützt B2B-Unternehmen dabei, ihre Marketing-, Vertriebs- und Produkt-Teams aufeinander abzustimmen, indem es verwertbare Kontoerkenntnisse bereitstellt, die das Umsatzwachstum fördern. Wenn das Konto in den Mittelpunkt des Datenmodells gestellt wird, konzentriert sich die gesamte Analyse auf die Konto-Journey. Durch das Hinzufügen einer neuen Ebene von Entitäten (Konten, Opportunities und Käufergruppen) zu Personen- und zeitbasierten Ereignissen erhalten Sie ein vollständiges Bild vom Lebenszyklus des B2B-Marketings und Umsatzes. [Weitere Informationen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 18. Juni 2025 |
| **Hinzufügen und Anzeigen von Kommentaren in Analysis Workspace-Projekten** | Eine neue [Kommentarfunktion](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) in Analysis Workspace ermöglicht es Ihnen, im Rahmen eines Analysis Workspace-Projekts Erkenntnisse zu teilen und Fragen zu stellen. Dadurch können Diskussionen über die Daten optimiert werden, sodass Gespräche im Kontext der diskutierten Daten geführt werden. Sie können <ul><li>jedes Analysis Workspace-Projekt kommentieren, auf das Sie Zugriff haben,</li><li>einen bestimmten Punkt in einer Visualisierung kommentieren oder allgemeine Kommentare zu einem Projekt abgeben,</li><li>andere Benutzende taggen, um sie über Ihre Kommentare zu informieren,</li><li>vorhandene Kommentare verwalten (bearbeiten, anheften, schließen usw.).</li></ul>Customer Journey Analytics-Admins können die [Kommentarfunktion auf Organisationsebene deaktivieren](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences). Projektverantwortliche können die [Kommentarfunktion auf Projektebene deaktivieren](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects). |  | &#x200B;25. Juni 2025 <p>(Veröffentlichung ursprünglich für den 29. Mai 2025 geplant)</p> |

## Fehlerbehebungen in Customer Journey Analytics

**Analysis Workspace**: AN-361874; AN-371360; AN-373079; AN-374382; AN-374447; AN-375277; AN-375680
**Zielgruppen**: AN-372343
**Auditprotokoll**: AN-378168
**Verbindungen**: AN-373121; AN-372996
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
