---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: abaa747934ff2cdd0a3dab867165afb46fbc71db
workflow-type: tm+mt
source-wordcount: '945'
ht-degree: 44%

---

# Aktuelle Adobe Customer Journey Analytics-Versionshinweise (April 2024)

**Letzte Aktualisierung**: Donnerstag, 17. April 2024

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom 10. April 2024 bis Mai 2024. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Streaming-Medien: Senden von Roku-Daten an Adobe Experience Platform Edge** | Jetzt [Installieren von Media Analytics mit Experience Platform Edge](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge)können Sie das Adobe Experience Platform Roku-SDK verwenden, um Streaming-Medien-Daten an Adobe Experience Platform zu senden. |  | 12. April 2024 |
| **Verfügbare monatliche Berichte im Reporting Activity Manager** | Beim Anzeigen der Berichtsaktivität für alle Verbindungen im Reporting Activity Manager ist jetzt ein Diagramm verfügbar, das die [monatliche Berichte/Anforderungen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/reporting-activity-manager/reporting-activity#view-all-report-suites) die auf der IMS-Org-Ebene sowohl für den aktuellen als auch für den vorherigen Monat ausgeführt wurden.<p>**Hinweis:** Daten sind ab März 2024 verfügbar. | | Dienstag, 15. April 2024 |
| **Intelligente Beschriftungen in mobilen Scorecards** | [Intelligente Beschriftungen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions) können Personen ohne Analysekenntnisse dabei helfen, ihre Daten ohne die Hilfe von Analystinnen und Analysten besser zu verstehen. Sie sind jetzt in Customer Journey Analytics-Scorecards verfügbar. |  | 17. April 2024 |
| **Verbesserung der Berechtigungen für &quot;Nur Projekt&quot; [!UICONTROL Arbeitsbereich] Komponenten** | Wenn ein Benutzer (Benutzer A) zuvor ein Projekt für einen anderen Benutzer (Benutzer B) freigegeben und Benutzer B Bearbeitungszugriff auf das Projekt gewährt hat, konnte Benutzer B das Projekt bearbeiten. Benutzer B kann jedoch nicht [!UICONTROL Schnellsegmente] eingebettet in das Projekt. Diese Einschränkung wurde entfernt - Benutzer B kann bearbeiten [!UICONTROL Schnellsegmente] und anderen Projektkomponenten, die in das freigegebene Projekt eingebettet sind. |  | 17. April 2024 |
| **Administrierende können alle Standorte in ihrer Organisation verwalten** | Eine neue Option für [Standortseite](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) ermöglicht es Administratoren, alle Standorte in der Organisation anzuzeigen und zu verwalten. Zuvor konnten Administrierende nur die von ihnen erstellten Standorte anzeigen und verwalten. |  | 17. April 2024 |
| **Adobe Product Analytics: Funktionsmatrix** | Entscheiden Sie für die Investition, indem Sie verstehen, was Ihr Kern, Ihre Macht, Ihre einmaligen und fragwürdigen Merkmale sind. [!UICONTROL Funktionsmatrix] misst Ereignisse nach Häufigkeit der Anwendung im Vergleich zu % aktiven Anwendern und vergleicht die mediane Anwendung. | 17. April 2024 | 30. April 2024 |
| **Adobe Product Analytics: Erweiterte Einblicke in Trichter** | Im [Friktion](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/funnel/friction) -Ansicht wurden die schriftlichen Einblicke um Kategorien, Deltas und Beschreibungen erweitert, um ein besseres Verständnis der Grafik und Tabelle zu ermöglichen. | 17. April 2024 | Samstag, 26. April 2024 |
| **Adobe Product Analytics: Erweiterte Ansicht zur Aufbewahrung** | Mehrere Funktionen wurden zum [Treue](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/retention/retention-rates) Ratenansicht, um tiefere und anpassbare Einblicke in die Treue zu erhalten:<ul><li>Verknüpfung von Start- und Rückkehrereignissen trennen</li><li>Vergleichen mehrerer Rückkehrereignisse in einer Ansicht</li><li>Anpassen des Aufbewahrungsmodells, das mit einem oder nach (unbegrenzt) auf jede (begrenzte) und in Klammern eingestellte Einstellung angewendet wird</li><li>Anzeigen und Ausblenden einzelner Kohortenzeilen in der Grafik</li></ul> | Donnerstag, 24. April 2024 | Donnerstag, 8. Mai 2024 |
| **Adobe Product Analytics: Vergleichen von Ereignissen innerhalb eines einzelnen Trichterschritts** | Sie können jetzt Ereignisse in einem einzelnen Trichterschritt im [Friktion](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/funnel/friction) anzeigen. Dies ist besonders nützlich, wenn Ihre Journey Schrittoptionen oder einen Schritt aufweist, bei dem ein A/B-Experiment durchgeführt wird. | Mittwoch, 23. April 2024 | Samstag, 3. Mai 2024 |
| **B2B-Schematransformation – Person zu Konto** | Ermöglicht Ihnen die Transformation von Datensätzen, um personenbasierte Suchvorgänge in Customer Journey Analytics-B2B-Berichtsszenarien besser zu unterstützen. Diese Funktion ist bei Datensätzen für B2B-Schemata verfügbar, die auf den folgenden Klassen basieren:<ul><li>XDM Business Account Person Relation</li><li>XDM Business Opportunity Person Relation</li><li>XDM Business Marketing List Members</li><li>XDM Business Campaign Members</li></ul> | | Donnerstag, 1. Mai 2024 |
| **Bot-Erkennung bei Experience Edge** | [Bot-Erkennung](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=de) ermöglicht es Ihnen, Ereignisse zu identifizieren, die vom Web SDK, Mobile SDK und der Server-API und nicht von bekannten Spiders und Bots generiert wurden. | | Donnerstag, 1. Mai 2024 |
| **Abgeleitete Felder: Funktion &quot;Weiter&quot;oder &quot;Zurück&quot;** | Mit diesen neuen Funktionen können Sie ein Feld als Eingabe nehmen und dann den n-vorherigen oder n-nächsten Wert identifizieren, um eine bessere Ansicht der Benutzer-Journey zu erhalten. Diese Funktion kann auch mit anderen Funktionen in [!UICONTROL Abgeleitete Felder], beispielsweise [!UICONTROL Verketten], um neue Dimensionen zu erstellen. |  | Donnerstag, 1. Mai 2024 |
| **Veröffentlichung von Zielgruppen in einem neuen Abschnitt „Zielgruppen“ in Experience Platform** | Zielgruppen, die über Customer Journey Analytics veröffentlicht werden, sind jetzt im neuen Abschnitt &quot;Zielgruppen&quot;in Adobe Experience Platform verfügbar.<p>Zuvor waren Audiences, die über Customer Journey Analytics veröffentlicht wurden, im Experience Platform unter dem Abschnitt &quot;Segmente&quot;verfügbar.</p><p>Diese Verbesserung bietet folgende Vorteile:</p><ul><li>Zielgruppen haben keine Verzögerung von mehr 1 Stunde, bevor sie auf dem Experience Platform erscheinen. Sie sind Sekunden nach ihrer Veröffentlichung verfügbar.</li><li>Zielgruppen können mithilfe der Spalte &quot;Ursprung&quot;in der Experience Platform sortiert werden, in der die Anwendung angezeigt wird, von der aus die Zielgruppe ursprünglich veröffentlicht wurde.</li><li>Mithilfe der Filter- und Sortieroptionen in Experience Platform können Sie die relevanten Zielgruppen schneller finden.</li></ul> |  | Mai 2024 |

{style="table-layout:auto"}

## Fehlerbehebungen in Customer Journey Analytics

AN-319662; AN-337894; AN-338469; AN-340147; AN-340200; AN-340443; AN-341594; AN 342442; AN-342976; AN-343020; AN-343469; AN-343703; AN-343938; AN-344614; AN-3 44677

## Wichtige Hinweise für Customer Journey Analytics-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| **Aktualisierte Links in den Benutzeroberflächen von Datenansichten und Verbindungen** | 15. Februar | Anfang März plant Adobe, die folgenden Links in der Customer Journey Analytics-Produkt-Benutzeroberfläche zu aktualisieren. Bitte aktualisieren Sie Ihre Lesezeichen entsprechend.<ul><li>**Datenansichtsseite, Datenansichts-Manager**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [Neuer Link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**Erstellen einer neuen Datenansicht**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [Neuer Link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**Bearbeiten der Datenansicht**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [Neuer Link](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**Verbindungs-Manager**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [Neuer Link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**Verbindungsinformationen**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Neuer Link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**Bearbeiten einer Verbindung**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Neuer Link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**Erstellen einer neuen Verbindung**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [Neuer Link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |

{style="table-layout:auto"}

## Verwandte Ressourcen

* [Frühere Versionshinweise für Customer Journey Analytics 2024](/help/release-notes/2024.md)
* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
* [Versionshinweise zu Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
