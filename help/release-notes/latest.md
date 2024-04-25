---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: abaa747934ff2cdd0a3dab867165afb46fbc71db
workflow-type: ht
source-wordcount: '945'
ht-degree: 100%

---

# Aktuelle Versionshinweise zu Adobe Customer Journey Analytics (April 2024)

**Letzte Aktualisierung**: 17. April 2024

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom 10. April 2024 bis Mai 2024. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Streaming-Medien: Senden von Roku-Daten an Adobe Experience Platform Edge** | Bei der [Installation von Media Analytics mit Experience Platform Edge](https://experienceleague.adobe.com/de/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge) können Sie jetzt das Adobe Experience Platform Roku SDK verwenden, um Streaming-Medien-Daten an Adobe Experience Platform zu senden. |  | 12. April 2024 |
| **Verfügbare monatliche Berichte im Reporting Activity Manager** | Beim Anzeigen der Berichtsaktivität für alle Verbindungen im Reporting Activity Manager ist jetzt ein Diagramm verfügbar, das die [monatlichen Berichte/Anfragen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/reporting-activity-manager/reporting-activity#view-all-report-suites) zeigt, die auf der IMS-Org-Ebene sowohl für den aktuellen als auch für den vorherigen Monat ausgeführt wurden.<p>**Hinweis:** Die Daten werden seit März 2024 zur Verfügung gestellt. | | 15. April 2024 |
| **Intelligente Beschriftungen in mobilen Scorecards** | [Intelligente Beschriftungen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions) können Personen ohne Analysekenntnisse dabei helfen, ihre Daten ohne die Hilfe von Analystinnen und Analysten besser zu verstehen. Sie sind jetzt in Customer Journey Analytics-Scorecards verfügbar. |  | 17. April 2024 |
| **Erweiterung der Berechtigungen für projektspezifische [!UICONTROL Arbeitsbereich]-Komponenten** | Wenn eine Benutzerin oder ein Benutzer (Person A) zuvor ein Projekt für eine andere Benutzerin bzw. einen anderen Benutzer (Person B) freigegeben und Person B Bearbeitungszugriff auf das Projekt gewährt hat, konnte Person B das Projekt bearbeiten. Person B war jedoch nicht in der Lage, die im Projekt eingebetteten [!UICONTROL Schnellsegmente] zu bearbeiten. Diese Einschränkung ist nun aufgehoben - Person B kann nun [!UICONTROL Schnellsegmente] und andere projektspezifische Komponenten bearbeiten, die in das freigegebene Projekt eingebettet sind. |  | 17. April 2024 |
| **Admins können alle Standorte in ihrer Organisation verwalten** | Eine neue Option auf der Seite [Speicherorte](https://experienceleague.adobe.com/de/docs/analytics/components/locations/locations-manager) ermöglicht es Admins, alle Speicherorte in der Organisation anzuzeigen und zu verwalten. Zuvor konnten Admins nur die von ihnen erstellten Standorte anzeigen und verwalten. |  | 17. April 2024 |
| **Adobe Product Analytics: Funktionsmatrix** | Fördern Sie Investitionsentscheidungen mit dem Wissen, was Ihre wichtigsten, leistungsfähigsten, einmaligen und fragwürdigen Funktionen sind. Die [!UICONTROL Funktionsmatrix] misst Ereignisse nach Nutzungshäufigkeit gegenüber den aktiven Benutzenden in % und vergleicht sie mit der durchschnittlichen Nutzung. | 17. April 2024 | 30. April 2024 |
| **Adobe Product Analytics: Erweiterte Erkenntnisse im Trichter** | In der Ansicht [Reibung](https://experienceleague.adobe.com/de/docs/analytics-platform/using/guided-analysis/funnel/friction) wurden die schriftlichen Einblicke um Kategorien, Deltas und Beschreibungen erweitert, um ein besseres Verständnis des Diagramms und der Tabelle zu ermöglichen. | 17. April 2024 | 26. April 2024 |
| **Adobe Product Analytics: Erweiterte Ansicht zur Kundenbindung** | Mehrere Funktionen wurden zur Ansicht [Bindungsraten](https://experienceleague.adobe.com/de/docs/analytics-platform/using/guided-analysis/retention/retention-rates) hinzugefügt, um tiefere und anpassbare Erkenntnisse zur Kundenbindung zu erhalten:<ul><li>Trennen der Verknüpfung von Start- und Rückkehrereignissen</li><li>Vergleichen mehrerer Rückkehrereignisse in einer Ansicht</li><li>Anpassen des angewandten Bindungsmodells mit den Einstellungen „bei oder nach“ (unbegrenzt), „bei jedem“ (begrenzt) und „in Klammern“</li><li>Anzeigen und Ausblenden einzelner Kohortenzeilen im Diagramm</li></ul> | 24. April 2024 | 8. Mai 2024 |
| **Adobe Product Analytics: Vergleichen von Ereignissen innerhalb eines einzelnen Trichterschritts** | Sie können jetzt Ereignisse in einem einzelnen Trichterschritt in der Ansicht [Reibung](https://experienceleague.adobe.com/de/docs/analytics-platform/using/guided-analysis/funnel/friction) anzeigen. Dies ist besonders nützlich, wenn Ihre Journey Schrittoptionen oder einen Schritt aufweist, bei dem ein A/B-Experiment durchgeführt wird. | 23. April 2024 | 3. Mai 2024 |
| **B2B-Schematransformation – Person zu Konto** | Ermöglicht Ihnen die Transformation von Datensätzen, um personenbasierte Suchvorgänge in Customer Journey Analytics-B2B-Berichtsszenarien besser zu unterstützen. Diese Funktion ist bei Datensätzen für B2B-Schemata verfügbar, die auf den folgenden Klassen basieren:<ul><li>XDM Business Account Person Relation</li><li>XDM Business Opportunity Person Relation</li><li>XDM Business Marketing List Members</li><li>XDM Business Campaign Members</li></ul> | | 1. Mai 2024 |
| **Bot-Erkennung bei Experience Edge** | [Bot-Erkennung](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=de) ermöglicht es Ihnen, Ereignisse zu identifizieren, die vom Web SDK, Mobile SDK und der Server-API und nicht von bekannten Spiders und Bots generiert wurden. | | 1. Mai 2024 |
| **Abgeleitete Felder: Nächste oder vorherige Funktion** | Mit diesen neuen Funktionen können Sie ein Feld als Eingabe nehmen und dann den n.-vorherigen oder n.-nächsten Wert identifizieren, um eine bessere Ansicht der Benutzer-Journey zu erhalten. Diese Funktionalität kann auch mit anderen Funktionen in [!UICONTROL Abgeleitete Felder], wie [!UICONTROL Verkettung], kombiniert werden, um neue Dimensionen zu erstellen. |  | 1. Mai 2024 |
| **Veröffentlichung von Zielgruppen in einem neuen Abschnitt „Zielgruppen“ in Experience Platform** | Von Customer Journey Analytics veröffentlichte Zielgruppen sind jetzt im neuen Abschnitt „Zielgruppen“ in Adobe Experience Platform verfügbar.<p>Bislang waren über Customer Journey Analytics veröffentlichte Zielgruppen in Experience Platform im Abschnitt „Segmente“ verfügbar.</p><p>Diese Verbesserung bietet folgende Vorteile:</p><ul><li>Zielgruppen werden nicht mehr mit 1 Stunde Verzögerung in Experience Platform angezeigt. Sie stehen vielmehr Sekunden nach ihrer Veröffentlichung zur Verfügung.</li><li>Zielgruppen können in Experience Platform mithilfe der Spalte „Herkunft“ sortiert werden, in der die Anwendung angezeigt wird, von der aus die Zielgruppe ursprünglich veröffentlicht wurde.</li><li>Mit den Filter- und Sortieroptionen in Experience Platform können Sie die relevanten Zielgruppen schneller finden.</li></ul> |  | Mai 2024 |

{style="table-layout:auto"}

## Fehlerbehebungen in Customer Journey Analytics

AN-319662; AN-337894; AN-338469; AN-340147; AN-340200; AN-340443; AN-341594; AN-342442; AN-342976; AN-343020; AN-343469; AN-343703; AN-343938; AN-344614; AN-344677;

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
