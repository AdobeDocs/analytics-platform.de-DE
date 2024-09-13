---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7b368f81c4036a3992fdfc34b983f344a61dc2fb
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 52%

---

# Aktuelle Versionshinweise zu Adobe Customer Journey Analytics (September 2024)

**Letzte Aktualisierung**: Donnerstag, 11. September 2024

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom 11. September 2024 bis Anfang Oktober. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Zusätzliche Informationen in der Spalte &quot;Verwendet in&quot;im Manager für berechnete Metriken und im Filter-Manager** | Die Spalte „Verwendet in“ im Manager für berechnete Metriken und im Filter-Manager enthält die folgenden neuen Reporting-Bereiche:<ul><li>**Report Builder**: Zeigt die Anzahl der berechneten Metriken oder Filter an, die im Report Builder verwendet werden.</li><li>**Ad-hoc-Komponenten**: Zeigt die Anzahl der berechneten Ad-hoc-Metriken oder Ad-hoc-Filter an, die in Projekten verwendet werden. Diese berechneten Ad-hoc-Metriken und -Filter (auch als „schnell berechnete Metriken“ und „Schnellfilter“ bezeichnet) können nur in dem Projekt verwendet werden, in dem sie erstellt wurden. Daher werden sie getrennt vom Reporting-Bereich „Projekt“ in der Spalte „Verwendet in“ aufgeführt.</li></ul>Weitere Informationen finden Sie unter [Manager für berechnete Metriken](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager) und [Filter-Manager](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-filters/manage-filters). |  | 11. September 2024 |
| **Intelligente Warnhinweise** | Intelligente Warnhinweise in Customer Journey Analytics ermöglichen es, dass Sie sofort benachrichtigt werden, wenn in Ihren Daten anormale Ereignisse auftreten.<p>Sie können festlegen, dass Warnhinweise auf der Grundlage von Schwellenwerten für Anomalien, geänderten Prozentsätzen oder spezifischen Datenpunkten ausgelöst werden. Warnhinweise bieten granulare Steuerelemente, die in die Anomalieerkennung integriert werden und ausgelöst werden, wenn Sie sie am dringendsten benötigenen.</p><p>Die Verwendung intelligenter Warnhinweise in Customer Journey Analytics ist fast identisch mit der Verwendung intelligenter Warnhinweise in Adobe Analytics. Ein wichtiger Unterschied besteht darin, dass in Customer Journey Analytics keine stündlichen Warnhinweise verfügbar sind. Dieser Unterschied liegt daran, dass die Datenerfassung für die verschiedenen Arten von Ereignisdaten, die erfasst werden können, erst nach einer Verzögerung abgeschlossen ist, in der Regel zwischen 3 und 9 Stunden nach der Datenereigniszeit. [Weitere Informationen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/c-intelligent-alerts/intellligent-alerts) |  | Mitte September 2024 |
| **Aktualisierungen des Adobe Analytics-Quell-Connectors** | Auf der Seite Datensatzaktivität werden keine Informationen zu Batches angezeigt, da der Analytics Source Connector vollständig von Adobe verwaltet wird. Sie können überwachen, dass Daten fließen, indem Sie sich die Metriken um die erfassten Datensätze ansehen. Weitere Informationen finden Sie im Handbuch zum [Erstellen einer Quellverbindung für Analytics-Daten](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) . |  | Jetzt verfügbar |
| **Nutzungsanalyse** | Erfahren Sie, wie Ihr Unternehmen Customer Journey Analytics verwendet. Durch Aktivierung dieser Funktion wird ein Datensatz in Adobe Experience Platform erstellt, der Daten erfasst, wenn ein anderer Mitarbeiter Ihres Unternehmens Analysis Workspace verwendet. Eine Verbindung und eine Datenansicht werden ebenfalls automatisch erstellt, sodass Sie auf Dimensionen wie Top-Projekttypen, die aktivsten Benutzer und die beliebtesten in Projekten verwendeten Komponenten zugreifen können. (Link zur Dokumentation folgt) |  | 18. Sept. 2024 |
| **Geführte Analyse: Einbetten in Workspace** | Kombinieren mehrerer geführter Analysen zu einer Ansicht in Analysis Workspace. (Link zur Dokumentation folgt) | Montag, 22. September 2024 | Donnerstag, 2. Oktober 2024 |


## Fehlerbehebungen in Customer Journey Analytics

AN-352461; AN-355446: AN-355665

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
