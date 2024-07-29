---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: fa6f549c83f8b91907f1bb174f061cbe32aeb13c
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 100%

---

# Aktuelle Versionshinweise zu Adobe Customer Journey Analytics (Juli 2024)

**Letzte Aktualisierung**: Donnerstag, 24. Juli 2024

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom 17. Juli 2024 bis zum August 2024. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Intelligente Warnhinweise** | Intelligente Warnhinweise sind jetzt in Customer Journey Analytics verfügbar, sodass Sie sofort benachrichtigt werden können, wenn in Ihren Daten anormale Ereignisse auftreten.<p>Sie können festlegen, dass Warnhinweise auf der Grundlage von Schwellenwerten für Anomalien, geänderten Prozentsätzen oder spezifischen Datenpunkten ausgelöst werden. Warnhinweise bieten granulare Steuerelemente, die in die Anomalieerkennung integriert werden und ausgelöst werden, wenn Sie sie am dringendsten benötigenen.</p><p>Die Verwendung intelligenter Warnhinweise in Customer Journey Analytics ist fast identisch mit der Verwendung intelligenter Warnhinweise in Adobe Analytics. Ein wichtiger Unterschied besteht darin, dass in Customer Journey Analytics keine stündlichen Warnhinweise verfügbar sind. Dieser Unterschied ist darauf zurückzuführen, dass die Datenaufnahme für die verschiedenen Arten von Ereignisdaten, die aufgenommen werden können, erst mit einer Verzögerung abgeschlossen ist, die in der Regel zwischen 3 und 9 Stunden nach dem Zeitpunkt des Datenereignisses liegt.</p><p>(Links zur aktualisierten Dokumentation folgen)</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | TBD |
| **Administratoreinstellungen zum Steuern der Konten und Speicherorte, die beim Exportieren von Berichten in die Cloud verwendet werden** | Eine neue [Registerkarte „Admin-Einstellungen“ im Speicherorte-Manager](/help/components/exports/manage-export-locations.md#configure-company-wide-settings-administrators-only) gibt Admins die Kontrolle darüber, ob Benutzende Konten und Speicherorte erstellen und bearbeiten können.<p>Diese Einstellungen gelten, wenn Benutzende [Cloud-Exportkonten konfigurieren](/help/components/exports/cloud-export-accounts.md) und [Cloud-Exportspeicherorte konfigurieren](/help/components/exports/cloud-export-locations.md).</p><p>Admins können auch die Kontotypen einschränken, die Benutzende erstellen und verwenden können. Zu den Kontotypen gehören Google Cloud Platform, Azure RBAC, Amazon S3, AEP Data Landing Zone, Snowflake usw.</p><p>Zuvor konnten alle Benutzenden Konten und Speicherorte für beliebige Kontotypen erstellen, bearbeiten und verwenden.</p> | 11. Juli 2024 | 19. Juli 2024 |
| **Datenquellen auf Zusammenfassungsebene** | Ermöglicht das Einbinden von Zeitreihendaten ohne Personen-ID. Diese Zeitreihendaten können zur Unterstützung verschiedener Anwendungsfälle verwendet werden, z. B.:<ul><li>Darstellung von Leistungsindikatoren auf hoher Ebene als Teil von oder neben Daten auf Ereignisebene. Dies kann so einfach sein wie ein Datum und ein einzelner Metrikwert, aber auch mehrere Dimensionen und Metriken umfassen, wie z. B. Werbeimpressionen, E-Mail-Öffnungen, Werbeausgaben, Kosten für verkaufte Waren und mehr.</li><li>Hochladen von Zielen oder Zielvorgaben täglich, wöchentlich, monatlich oder vierteljährlich und Positionieren dieser Ziele oder Zielvorgaben anhand von Metriken auf Ereignisebene, um die Trends von Metriken im Vergleich zu den Zielgruppen oder Zielen der Organisation visualisieren zu können.</li></ul><p>(Links zur aktualisierten Dokumentation folgen)</p> |  | 31. Juli 2024 |
| **Abgeleitete Felder – Deduplizierungsfunktion** | Mit der Funktion [Deduplizieren](/help/data-views/derived-fields/derived-fields.md#deduplicate) in abgeleiteten Feldern können Sie verhindern, dass ein Wert mehrmals gezählt wird. |  | 17. Juli 2024 |
| **Bereitstellung der geführten Analyse für CJA-Kundinnen und -Kunden** | Mit geführten Analysen können Benutzende hochwertige Daten und Erkenntnisse zur Customer Journey mithilfe geführter Workflows selbst bereitstellen, die auf den kanalübergreifenden Daten von Customer Journey Analytics basieren. <p>Funktionsübergreifende Teams, vom Marketing bis zum Produkt, können in Echtzeit eine Verbindung herstellen, um diese Berichte zu verwenden und zu verstehen.</p><p>In CJA-Paketen sind jetzt bis zu 11 geführte Analyseansichten verfügbar. [Weitere Informationen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/guided-analysis/overview)</p> |  | 17. Juli 2024 |
| **Freigeben von Konten und Speicherorten, die für den Export und Import verwendet werden** | Benutzende können nun die von ihnen erstellten Konten und Speicherorte allen Benutzenden in ihrer Organisation zur Verfügung stellen. Nur die Personen, denen Konten bzw. Speicherorte gehören, und System-Admins können Konten und Speicherorte bearbeiten und löschen. Zuvor konnten Konten und Speicherorte nur von der Person verwendet werden, die sie erstellt hat. Diese Einstellungen sind verfügbar, wenn Benutzende [Cloud-Exportkonten konfigurieren](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts) und [Cloud-Exportspeicherorte konfigurieren](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-components/exports/cloud-export-locations). | 12. Juni 2024 | Mitte Juli 2024 |
| **Veröffentlichung von Zielgruppen in einem neuen Abschnitt „Zielgruppen“ in Experience Platform** | Von Customer Journey Analytics veröffentlichte Zielgruppen sind jetzt im neuen Abschnitt „Zielgruppen“ in Adobe Experience Platform verfügbar.<p>Bislang waren über Customer Journey Analytics veröffentlichte Zielgruppen in Experience Platform im Abschnitt „Segmente“ verfügbar.</p><p>Diese Verbesserung bietet folgende Vorteile:</p><ul><li>Zielgruppen werden nicht mehr mit 1 Stunde Verzögerung in Experience Platform angezeigt. Sie stehen vielmehr Sekunden nach ihrer Veröffentlichung zur Verfügung.</li><li>Zielgruppen können in Experience Platform mithilfe der Spalte „Herkunft“ sortiert werden, in der die Anwendung angezeigt wird, von der aus die Zielgruppe ursprünglich veröffentlicht wurde.</li><li>Mit den Filter- und Sortieroptionen in Experience Platform können die relevanten Zielgruppen schneller gefunden werden.</li></ul> <p>(Link zur Dokumentation folgt)</p> |  | TBD |

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
