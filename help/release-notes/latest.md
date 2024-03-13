---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 1b39449fa58157fb61d619de82235cba326ffe2c
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 57%

---

# Aktuelle Adobe Customer Journey Analytics-Versionshinweise (März 2024)

**Zuletzt aktualisiert**: Samstag, 8. März 2024

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum von Ende des 13. März 2024 bis April 2024. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Auf der Landingpage &quot;Projekte&quot;verfügbare neue Spalte** | Die **[!UICONTROL Zuletzt verwendet]** ist jetzt bei Ansicht der Registerkarte Projekte auf der [Customer Journey Analytics-Landingpage](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html). Anhand dieser Informationen können Sie feststellen, ob ein Projekt für Benutzer in Ihrer Organisation nützlich ist, indem Sie das Datum und die Uhrzeit des letzten Öffnens des Projekts anzeigen. Zuvor wurde die Variable **[!UICONTROL Zuletzt verwendet]** -Spalte war nur im Manager für berechnete Metriken, im Segment-Manager und im Warnhinweismanager verfügbar. |  | Donnerstag, 13. März 2024 |
| **Nutzungsmetriken** | Die Nutzungsmetrik-Schnittstelle zeigt die Verwendung von erfassten und berichtspflichtigen Zeilen über alle Verbindungen hinweg an. Mit dieser Schnittstelle können Sie festlegen, ob Ihre Customer Journey Analytics-Nutzung den vertraglich vereinbarten Bedingungen entspricht. |  | Donnerstag, 13. März 2024 |
| **Media Analytics-Berichte – Zielgruppendurchschnitt pro Minute (AMA)** | Das Bedienfeld „Zielgruppendurchschnitt pro Minute“ ist jetzt in CJA verfügbar. Media Analytics-Kundinnen und -Kunden können das Bedienfeld „Zielgruppendurchschnitt pro Minute“ verwenden, um die durchschnittliche Nutzung ihrer Inhalte besser zu verstehen. Der Zielgruppendurchschnitt pro Minute ermöglicht Vergleiche von Inhalten beliebiger Längen oder Genres. Darüber hinaus können Kunden diesen digitalen Zielgruppendurchschnitt pro Minute mit Metriken zum linearen TV-Durchschnitt pro Minute vergleichen oder ihn anhängen. Dieses Bedienfeld bietet mehr Flexibilität, um die durchschnittliche Zielgruppe für benutzerdefinierte Zeiträume sowie den Zeitpunkt zu ermitteln, an dem die Klassifizierung der Dauer nachträglich aktualisiert wurde.  |  | 12. März 2024 |
| **B2B-Schema-Umwandlung für Person zu Konto** | Ermöglicht Ihnen die Transformation von Datensätzen zur besseren Unterstützung personalbasierter Suchen in Customer Journey Analytics-B2B-Berichtsszenarien. Diese Funktion ist für Datensätze für B2B-Schemas verfügbar, die auf den folgenden Klassen basieren:<ul><li>XDM Business Account Person Relation</li><li>XDM Business Opportunity Person Relation</li><li>XDM Business Marketing List Members</li><li>XDM Business Campaign Members</li></ul> | | Mittwoch, 26. März 2024 |
| **Adobe Product Analytics: Vergleichen von Ereignissen innerhalb eines einzelnen Trichterschritts** | In der Ansicht &quot;Trichter: Fehler&quot;können Sie jetzt Ereignisse innerhalb eines einzelnen Trichterschritts vergleichen. Dies ist besonders nützlich, wenn Ihre Journey Schrittoptionen hat oder wenn ein A/B-Experiment durchgeführt wird. | Samstag, 29. März 2024 | Samstag, 12. April 2024 |
| **Administratoren können alle Standorte in ihrer Organisation verwalten** | Eine neue Option auf der Seite Standorte ermöglicht es Administratoren, alle Standorte in der Organisation anzuzeigen und zu verwalten. Zuvor konnten Administratoren nur die von ihnen erstellten Standorte anzeigen und verwalten. | | April 2024 |
| **Zielgruppen werden in einem neuen Abschnitt &quot;Zielgruppen&quot;unter Experience Platform veröffentlicht** | Audiences, die von Customer Journey Analytics veröffentlicht werden, sind jetzt im neuen Bereich &quot;Audiences&quot;unter Experience Platform verfügbar. Zuvor waren Zielgruppen, die über Customer Journey Analytics veröffentlicht wurden, in Platform im Bereich &quot;Segmente&quot;verfügbar. Diese Verbesserung bietet die folgenden Vorteile:<ul><li>Zielgruppen haben keine Verzögerung von mehr 1 Stunde, bevor sie in Platform angezeigt werden. Sie stehen Sekunden nach ihrer Veröffentlichung zur Verfügung.</li><li>Zielgruppen können in Platform mithilfe der Spalte &quot;Ursprung&quot;sortiert werden, in der die Anwendung angezeigt wird, von der aus die Zielgruppe ursprünglich veröffentlicht wurde.</li><li>Mit den Filter- und Sortieroptionen in Platform können Sie die relevanten Zielgruppen schneller finden.</li></ul>Weitere Informationen finden Sie im Abschnitt . [Verwenden von Customer Journey Analytics-Zielgruppen in Experience Platform](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=en#audiences-aep). |  | April 2024 |
| **Bot-Erkennung bei Experience Edge** | [Bot-Erkennung](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=de) ermöglicht es Ihnen, Ereignisse zu identifizieren, die vom Web SDK, Mobile SDK und der Server-API und nicht von bekannten Spiders und Bots generiert wurden. | | 29. April 2024 |

{style="table-layout:auto"}

## Fehlerbehebungen in Customer Journey Analytics

AN-340429; AN-341544; AN-341974; AN-342176; AN-342391

## Wichtige Hinweise für Customer Journey Analytics-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| **Aktualisierte Links in den Benutzeroberflächen von Datenansichten und Verbindungen** | Februar 15 | Anfang März plant Adobe, die folgenden Links in der Customer Journey Analytics-Produkt-Benutzeroberfläche zu aktualisieren. Bitte aktualisieren Sie Ihre Lesezeichen entsprechend.<ul><li>**Datenansichtsseite, Datenansichts-Manager**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [Neuer Link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**Erstellen einer neuen Datenansicht**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [Neuer Link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**Bearbeiten der Datenansicht**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [Neuer Link](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**Verbindungs-Manager**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [Neuer Link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**Verbindungsinformationen**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Neuer Link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**Bearbeiten einer Verbindung**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Neuer Link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**Erstellen einer neuen Verbindung**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [Neuer Link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |
| Adobe-API-Objektmitgliederergänzungen | 17. Januar 2024 | Adobe kann ohne Ankündigung oder Versionsänderung optionale Anforderungs- und Antwortmitglieder (Name/Wert-Paare) zu bestehenden API-Objekten hinzufügen. Solche Ergänzungen sollten für Ihre Implementierung keine einschneidenden Änderungen darstellen. Adobe empfiehlt, in der API-Dokumentation jedes Drittanbieter-Tools, das Sie in unsere API integrieren, nachzuschlagen, damit solche Ergänzungen bei der Verarbeitung ignoriert werden, wenn sie nicht verstanden werden. Adobe entfernt keine Parameter und fügt keine erforderlichen Parameter hinzu, ohne zuvor durch Versionshinweise eine Standardbenachrichtigung bereitzustellen. |

{style="table-layout:auto"}

## Verwandte Ressourcen

* [Frühere Versionshinweise für Customer Journey Analytics 2023](/help/release-notes/2023.md)
* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
* [Versionshinweise zu Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
