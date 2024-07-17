---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a2673763fce0766b732ac7ab557d3a0a193173fd
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 42%

---

# Aktuelle Versionshinweise zu Adobe Customer Journey Analytics (Juli 2024)

**Letzte Aktualisierung**: Donnerstag, 17. Juli 2024

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom 17. Juli 2024 bis August 2024. Adobe Customer Journey Analytics-Versionen basieren auf einem [kontinuierlichen Bereitstellungsmodell](releases.md), das einen skalierbareren, schrittweisen Ansatz für die Bereitstellung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Intelligente Warnhinweise** | Intelligente Warnhinweise sind jetzt im Customer Journey Analytics verfügbar, sodass Sie sofort benachrichtigt werden können, wenn in Ihren Daten anormale Ereignisse auftreten.<p>Sie können Warnungen festlegen, die auf Anomalieschwellen, geänderten Prozentsätzen oder spezifischen Datenpunkten ausgelöst werden. Warnhinweise bieten granulare Steuerelemente, die mit der Anomalieerkennung integriert werden und ausgelöst werden, wenn Sie sie am dringendsten benötigen.</p><p>Die Verwendung intelligenter Warnhinweise auf dem Customer Journey Analytics ist fast identisch mit der Verwendung intelligenter Warnhinweise in Adobe Analytics. Ein wichtiger Unterschied besteht darin, dass stündliche Warnhinweise nicht im Customer Journey Analytics verfügbar sind. Dieser Unterschied liegt daran, dass die Datenerfassung für die verschiedenen Arten von Ereignisdaten, die erfasst werden können, erst nach einer Verzögerung abgeschlossen ist, in der Regel zwischen 3 und 9 Stunden nach der Datenereigniszeit.</p><p>(Nachfolgende Links der Dokumentation wurden aktualisiert)</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | Samstag, 26. Juli 2024 |
| **Administrator-Einstellungen zum Steuern der Konten und Speicherorte, die beim Exportieren von Berichten in die Cloud verwendet werden** | Eine neue Registerkarte &quot;[&quot;Admin-Einstellungen&quot;im Locations Manager](/help/components/exports/manage-export-locations.md#configure-company-wide-settings-administrators-only) gibt Administratoren die Kontrolle darüber, ob Benutzer Konten und Standorte erstellen und bearbeiten können.<p>Diese Einstellungen gelten, wenn Benutzer [Cloud-Exportkonten konfigurieren](/help/components/exports/cloud-export-accounts.md) und [Cloud-Exportspeicherorte konfigurieren](/help/components/exports/cloud-export-locations.md).</p><p>Administratoren können auch die Kontotypen einschränken, die Benutzer erstellen und verwenden können. Zu den Kontotypen gehören Google Cloud Platform, Azure RBAC, Amazon S3, AEP Data Landing Zone, Snowflake usw.</p><p>Zuvor konnten alle Benutzenden Konten und Speicherorte für beliebige Kontotypen erstellen, bearbeiten und verwenden.</p> | Freitag, 11. Juli 2024 | Samstag, 19. Juli 2024 |
| **Datenquellen auf Zusammenfassungsebene** | Ermöglicht den Einstieg in Zeitreihendaten ohne Personen-ID. Diese Zeitreihendaten können zur Unterstützung verschiedener Anwendungsfälle verwendet werden, z. B.:<ul><li>Darstellung von Leistungsindikatoren auf hoher Ebene als Teil von oder neben Daten auf Ereignisebene. Dies kann so einfach sein wie ein Datum und einen einzelnen Metrikwert oder mehrere Dimensionen und Metriken umfassen, wie z. B. Werbeimpressionen, E-Mail-Öffnungen, Werbeausgaben, Kosten für gut verkauft und mehr.</li><li>Hochladen von Zielen oder Zielen täglich, wöchentlich, monatlich oder vierteljährlich und Positionieren dieser Ziele oder Ziele anhand von Metriken auf Ereignisebene, um die Trends von Metriken im Vergleich zu den Zielgruppen oder Zielen der Organisation visualisieren zu können.</li></ul><p>(Nachfolgende Links der Dokumentation wurden aktualisiert)</p> |  | Donnerstag, 31. Juli 2024 |
| **Abgeleitete Felder - Funktion &quot;Deduplizieren&quot;** | Mit der Funktion Deduplizieren in abgeleiteten Feldern können Sie verhindern, dass ein Wert mehrmals gezählt wird.<p>(Link zur Dokumentation folgt)</p> |  | Mittwoch, 16. Juli 2024 |
| **Geführte Analysebereitstellung für CJA-Kunden** | Geführte Analysen ermöglichen es Benutzern, durch geführte Workflows, die auf kanalübergreifenden Daten von Customer Journey Analytics aufbauen, hochwertige Daten und Einblicke über die Journey zu den Kunden selbst bereitzustellen. <p>Funktionsübergreifende Teams, vom Marketing bis zum Produkt, können in Echtzeit eine Verbindung herstellen, um diese Berichte zu verwenden und zu verstehen.</p><p>In CJA-Paketen sind jetzt bis zu 11 geführte Analyseansichten verfügbar. [Weitere Informationen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/overview)</p> |  | Donnerstag, 17. Juli 2024 |
| **Freigeben von Konten und Speicherorten, die für den Export und Import verwendet werden** | Benutzende können nun die von ihnen erstellten Konten und Speicherorte allen Benutzenden in ihrer Organisation zur Verfügung stellen. Nur die Personen, denen Konten bzw. Speicherorte gehören, und System-Admins können Konten und Speicherorte bearbeiten und löschen. Zuvor konnten Konten und Speicherorte nur von der Person verwendet werden, die sie erstellt hat. Diese Einstellungen sind verfügbar, wenn Benutzende [Cloud-Exportkonten konfigurieren](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts) und [Cloud-Exportspeicherorte konfigurieren](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-components/exports/cloud-export-locations). | 12. Juni 2024 | Mitte Juli 2024 |
| **Veröffentlichung von Zielgruppen in einem neuen Abschnitt „Zielgruppen“ in Experience Platform** | Von Customer Journey Analytics veröffentlichte Zielgruppen sind jetzt im neuen Abschnitt „Zielgruppen“ in Adobe Experience Platform verfügbar.<p>Bislang waren über Customer Journey Analytics veröffentlichte Zielgruppen in Experience Platform im Abschnitt „Segmente“ verfügbar.</p><p>Diese Verbesserung bietet folgende Vorteile:</p><ul><li>Zielgruppen werden nicht mehr mit 1 Stunde Verzögerung in Experience Platform angezeigt. Sie stehen vielmehr Sekunden nach ihrer Veröffentlichung zur Verfügung.</li><li>Zielgruppen können in Experience Platform mithilfe der Spalte „Herkunft“ sortiert werden, in der die Anwendung angezeigt wird, von der aus die Zielgruppe ursprünglich veröffentlicht wurde.</li><li>Mithilfe der Filter- und Sortieroptionen in Experience Platform können Sie die relevanten Audiences schneller finden.</li></ul> <p>(Link zur Dokumentation folgt)</p> |  | TBD |

{style="table-layout:auto"}

## Fehlerbehebungen in Customer Journey Analytics

AN-306000; AN-288748; AN-351547; AN-351110

## Wichtige Hinweise für Customer Journey Analytics-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| -/- | | |

{style="table-layout:auto"}

## Verwandte Ressourcen

* [Frühere Versionshinweise für Customer Journey Analytics 2024](/help/release-notes/2024.md)
* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
* [Versionshinweise zum Add-on für Streaming-Mediensammlungen](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
