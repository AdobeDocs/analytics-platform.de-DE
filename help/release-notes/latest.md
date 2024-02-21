---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: b8f70f38471e216c52a6c19b05fa259b9d2426ef
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 80%

---

# Aktuelle Versionshinweise zu Adobe Customer Journey Analytics (Februar 2024)

**Letzte Aktualisierung**: Mittwoch, 20. Februar 2024

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom 14. Februar 2024 bis zum 11. März 2024. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Zeitreihenprognosen** | [Prognosen](../analysis-workspace/c-forecast/forecasting.md) sind eine neue Funktion in Analysis Workspace, mit der eine standardmäßige oder berechnete Metrik mit beliebiger unterstützter Zeitgranularität (stündlich, täglich, wöchentlich, monatlich und jährlich) für Freiformtabellen und Liniendiagramme prognostiziert werden kann. | 31. Januar 2024 | 21. Februar 2024 |
| **Media Analytics-Berichte – Zielgruppendurchschnitt pro Minute (AMA)** | Das Bedienfeld „Zielgruppendurchschnitt pro Minute“ ist jetzt in CJA verfügbar. Media Analytics-Kundinnen und -Kunden können das Bedienfeld „Zielgruppendurchschnitt pro Minute“ verwenden, um die durchschnittliche Nutzung ihrer Inhalte besser zu verstehen. Der Zielgruppendurchschnitt pro Minute ermöglicht Vergleiche von Inhalten beliebiger Längen oder Genres. Darüber hinaus können Kunden diesen digitalen Zielgruppendurchschnitt pro Minute mit Metriken zum linearen TV-Durchschnitt pro Minute vergleichen oder ihn anhängen. Dieses Bedienfeld bietet mehr Flexibilität, um die durchschnittliche Zielgruppe für benutzerdefinierte Zeiträume sowie den Zeitpunkt zu ermitteln, an dem die Klassifizierung der Dauer nachträglich aktualisiert wurde.  |  | Februar 2024 |
| **Zeilenanzahl-Metriken für Lookup- und Profildaten** | Metriken zur Zeilenanzahl für Datensätze, die als Teil einer Verbindung konfiguriert sind, enthalten jetzt Datensätze, die hinzugefügt, übersprungen oder aus Profil- und Lookup-Datensätzen gelöscht werden. |  | Donnerstag, 14. Februar 2024 |
| **Experience Edge-Bot-Erkennung** | [Bot-Erkennung](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=de) ermöglicht es Ihnen, Ereignisse zu identifizieren, die vom Web SDK, Mobile SDK und Server API wie von bekannten Spiders und Bots generiert wurden. | | Dienstag, 29. April 2024 |
| **Nutzungsmetriken** | Die Nutzungsmetrik-Schnittstelle zeigt die Verwendung von erfassten und berichtspflichtigen Zeilen über alle Verbindungen hinweg an. Mit dieser Schnittstelle können Sie festlegen, ob Ihre Customer Journey Analytics-Nutzung den vertraglich vereinbarten Bedingungen entspricht. | 20. Februar 2024 | Anfang März 2024 |
| **Adobe Product Analytics: Für alle freigeben** | Ermöglicht die Freigabe eines schreibgeschützten Links zu Adobe Product Analytics-Projekten für Personen, die keinen Zugriff auf Product Analytics haben. |  | 21. Februar 2024 |
| **Adobe Product Analytics: Berechnete Metriken anwenden** | Sie können jetzt auf berechnete Metriken zugreifen, die in Analysis Workspace oder im Generator für berechnete Metriken in der Ansicht „Trends: Nutzung“ erstellt wurden. Damit können Sie Metriken im Zeitverlauf als Trend verfolgen und vergleichen. |  | 16. Februar 2024 |
| **Aktualisierte Links in den Benutzeroberflächen von Datenansichten und Verbindungen** | Anfang März plant Adobe, die folgenden Links in der Customer Journey Analytics-Produkt-Benutzeroberfläche zu aktualisieren. Bitte aktualisieren Sie Ihre Lesezeichen entsprechend.<ul><li>**Datenansichtsseite, Datenansichts-Manager**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [Neuer Link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**Neue Datenansicht erstellen**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [Neuer Link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**Datenansicht bearbeiten**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [Neuer Link](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**Connections Manager**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [Neuer Link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**Verbindungsinformationen**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Neuer Link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**Verbindung bearbeiten**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Neuer Link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**Neue Verbindung erstellen**: [Vorhandener Link](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [Neuer Link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |  | März 2024 |

{style="table-layout:auto"}

## Fehlerbehebungen in Customer Journey Analytics

AN-333172; AN-336887; AN-337402; AN-337593; AN-338482; AN-338684; AN-339883; AN-340200

## Wichtige Hinweise für Customer Journey Analytics-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| Adobe-API-Objektmitgliederergänzungen | 17. Januar 2024 | Adobe kann ohne Ankündigung oder Versionsänderung optionale Anforderungs- und Antwortmitglieder (Name/Wert-Paare) zu bestehenden API-Objekten hinzufügen. Solche Ergänzungen sollten für Ihre Implementierung keine einschneidenden Änderungen darstellen. Adobe empfiehlt, in der API-Dokumentation jedes Drittanbieter-Tools, das Sie in unsere API integrieren, nachzuschlagen, damit solche Ergänzungen bei der Verarbeitung ignoriert werden, wenn sie nicht verstanden werden. Adobe entfernt keine Parameter und fügt keine erforderlichen Parameter hinzu, ohne zuvor durch Versionshinweise eine Standardbenachrichtigung bereitzustellen. |

{style="table-layout:auto"}

## Verwandte Ressourcen

* [Frühere Versionshinweise für Customer Journey Analytics 2023](/help/release-notes/2023.md)
* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
* [Versionshinweise zu Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
