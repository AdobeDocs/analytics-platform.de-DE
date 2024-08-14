---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 835be84fd5f1398b88e265a21fe6f9665c758dce
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 79%

---

# Aktuelle Versionshinweise zu Adobe Customer Journey Analytics (August 2024)

**Letzte Aktualisierung**: Donnerstag, 14. August 2024

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom 14. August 2024 bis September 2024. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Datenquellen auf Zusammenfassungsebene** | Ermöglicht das Einbinden von Zeitreihendaten ohne Personen-ID. Diese Zeitreihendaten können zur Unterstützung verschiedener Anwendungsfälle verwendet werden, z. B.:<ul><li>Darstellung von Leistungsindikatoren auf hoher Ebene als Teil von oder neben Daten auf Ereignisebene. Dies kann so einfach sein wie ein Datum und ein einzelner Metrikwert, aber auch mehrere Dimensionen und Metriken umfassen, wie z. B. Werbeimpressionen, E-Mail-Öffnungen, Werbeausgaben, Kosten für verkaufte Waren und mehr.</li><li>Hochladen von Zielen oder Zielen auf stündlicher oder täglicher Basis und anschließendes Positionieren dieser Ziele oder Ziele gegenüber Metriken auf Ereignisebene. Auf diese Weise können Sie die Trends von Metriken in Bezug auf die Ziele oder Ziele in der Organisation visualisieren.</li></ul><p>Weitere Informationen finden Sie unter [Zusammenfassungsdaten](/help/data-views/summary-data.md)</p> |  | Mittwoch, 13. August 2024 |
| **Veröffentlichung von Zielgruppen in einem neuen Abschnitt „Zielgruppen“ in Experience Platform** | Von Customer Journey Analytics veröffentlichte Zielgruppen sind jetzt im neuen Abschnitt „Zielgruppen“ in Adobe Experience Platform verfügbar.<p>Bislang waren über Customer Journey Analytics veröffentlichte Zielgruppen in Experience Platform im Abschnitt „Segmente“ verfügbar.</p><p>Diese Verbesserung bietet folgende Vorteile:</p><ul><li>Zielgruppen werden nicht mehr mit 1 Stunde Verzögerung in Experience Platform angezeigt. Sie stehen vielmehr Sekunden nach ihrer Veröffentlichung zur Verfügung.</li><li>Zielgruppen können in Experience Platform mithilfe der Spalte „Herkunft“ sortiert werden, in der die Anwendung angezeigt wird, von der aus die Zielgruppe ursprünglich veröffentlicht wurde.</li><li>Mit den Filter- und Sortieroptionen in Experience Platform können die relevanten Zielgruppen schneller gefunden werden.</li></ul> <p>Weitere Informationen finden Sie unter [Verwenden von Customer Journey Analytics-Zielgruppen in Experience Platform](/help/components/audiences/publish.md#use-customer-journey-analytics-audiences-in-experience-platform) im Artikel, [Erstellen und Veröffentlichen von Zielgruppen](/help/components/audiences/publish.md).</p> | Donnerstag, 14. August 2024 | Freitag, 22. August 2024 |
| **Intelligente Warnhinweise** | Intelligente Warnhinweise in Customer Journey Analytics ermöglichen es Ihnen, sofort benachrichtigt zu werden, wenn in Ihren Daten abnormale Ereignisse auftreten.<p>Sie können festlegen, dass Warnhinweise auf der Grundlage von Schwellenwerten für Anomalien, geänderten Prozentsätzen oder spezifischen Datenpunkten ausgelöst werden. Warnhinweise bieten granulare Steuerelemente, die in die Anomalieerkennung integriert werden und ausgelöst werden, wenn Sie sie am dringendsten benötigenen.</p><p>Die Verwendung intelligenter Warnhinweise in Customer Journey Analytics ist fast identisch mit der Verwendung intelligenter Warnhinweise in Adobe Analytics. Ein wichtiger Unterschied besteht darin, dass in Customer Journey Analytics keine stündlichen Warnhinweise verfügbar sind. Dieser Unterschied ist darauf zurückzuführen, dass die Datenaufnahme für die verschiedenen Arten von Ereignisdaten, die aufgenommen werden können, erst mit einer Verzögerung abgeschlossen ist, die in der Regel zwischen 3 und 9 Stunden nach dem Zeitpunkt des Datenereignisses liegt.</p><p>(Links zur aktualisierten Dokumentation folgen)</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | TBD |

{style="table-layout:auto"}

## Fehlerbehebungen in Customer Journey Analytics

AN-354359; AN-351646; AN-346873; AN-352504; AN-353755; AN-354199; AN-354268; AN 354791; AN-354598; AN-354462; AN-354547;

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
