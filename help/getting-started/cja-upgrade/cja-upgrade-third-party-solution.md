---
title: Upgrade von der Analyselösung eines Drittanbieters auf Customer Journey Analytics
description: Erfahren Sie, wie Sie von einer Analyselösung eines Drittanbieters auf Customer Journey Analytics aktualisieren
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: 87df2fb92f238ce051ac5f6cc90e218737279471
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 20%

---

# Upgrade von der Analyselösung eines Drittanbieters auf Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Analyseprodukt eines Drittanbieters"
>abstract="Eine Implementierung, die Daten für das Analyseprodukt eines Drittanbieters erfasst, z. B. Google Analytics. Durch Auswahl dieser Option werden mehrere Optionen im Fragebogen deaktiviert, die beim Upgrade auf Customer Journey Analytics vom Analyseprodukt eines Drittanbieters nicht zutreffen."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Verwenden Sie die Informationen auf dieser Seite bei der Beantwortung von Fragen in der Checkliste für das [Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/).

Das empfohlene Verfahren für das Upgrade von einer Analyselösung eines Drittanbieters auf Customer Journey Analytics ist eine neue Implementierung des Experience Platform Web SDK, der bevorzugten Datenerfassungsmethode für Customer Journey Analytics. In Verbindung mit dem Web SDK empfiehlt Adobe auch die Aufnahme historischer Daten aus der Analyselösung eines Drittanbieters in Adobe Experience Platform.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Verwenden Sie den folgenden Prozess, wenn Sie von einer Analyselösung eines Drittanbieters, wie z. B. Google Analytics, zum Customer Journey Analytics wechseln:

1. ...


Wenden Sie sich an den Adobe-Support, wenn Sie konkretere Ratschläge, Anleitungen oder Unterstützung benötigen.

| Vorhandene Analyselösung | Beschreibung | Verfügbare Aktualisierungspfade |
|---------|----------|----------|
| AppMeasurement | AppMeasurement für JavaScript ist seit jeher eine gängige Methode zur Implementierung von Adobe Analytics.<p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit AppMeasurement für JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview).</p> | <ul><li>[(Empfohlen) Neue Implementierung von Experience Platform Web SDK für die fortlaufende Datenerfassung, der Analytics Source Connector für Verlaufsdaten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Neue Implementierung der Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migrieren von Adobe Analytics zum Web SDK</li><li>[Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Adobe Analytics-Erweiterung (Tags) | <p>Tags in Adobe Experience Platform ist eine Tag-Management-Lösung, mit der Sie Analytics-Code bereitstellen und weitere Tagging-Vorgaben erfüllen können. Adobe bietet Integrationen mit anderen Lösungen und Produkten und ermöglicht die Bereitstellung von benutzerdefiniertem Code. Alle diese Aufgaben können ausgeführt werden, ohne dass Entwicklungsteams in Ihrer Organisation Code auf Ihrer Website aktualisieren müssen.</p><p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mithilfe der Analytics-Erweiterung](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview).</p> | <ul><li>[(Empfohlen) Neue Implementierung von Experience Platform Web SDK für die fortlaufende Datenerfassung, der Analytics Source Connector für Verlaufsdaten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Neue Implementierung der Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migrieren von Adobe Analytics zum Web SDK</li><li>[Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Experience Platform Web SDK (alloy.js) | Die Experience Platform Web SDK ist die derzeit empfohlene Adobe-Methode zur Implementierung von Adobe Analytics. Mit dem Adobe Experience Platform-Edge Network können Sie Daten, die für mehrere Produkte bestimmt sind, an einen zentralen Ort senden. <p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit dem Adobe Experience Platform-Edge Network ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview).</p> | <ul><li>[(Empfohlen) Neue Implementierung von Experience Platform Web SDK für die fortlaufende Datenerfassung, der Analytics Source Connector für Verlaufsdaten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Neue Implementierung der Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Platform</li></ul> |
| Experience Platform Web SDK-Erweiterung (Tags) | Die Experience Platform Web SDK ist die derzeit empfohlene Methode zur Implementierung von Adobe Analytics für Web-Daten auf Adobe. Mit dem Adobe Experience Platform-Edge Network können Sie Daten, die für mehrere Produkte bestimmt sind, an einen zentralen Ort senden. <p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit der Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[(Empfohlen) Neue Implementierung von Experience Platform Web SDK für die fortlaufende Datenerfassung, der Analytics Source Connector für Verlaufsdaten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Neue Implementierung der Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Platform</li></ul> |
| Experience Platform Mobile SDK | Die Experience Platform Mobile SDK ist die derzeit empfohlene Methode zur Implementierung von Adobe Analytics für mobile Daten auf der Adobe. Mit dem Adobe Experience Platform-Edge Network können Sie Daten, die für mehrere Produkte bestimmt sind, an einen zentralen Ort senden.<p>Mit der Adobe Experience Platform Mobile SDK können Sie Adobe-Experience Cloud-Lösungen und -Services in Ihren Apps nutzen. </p><p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit der Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[(Empfohlen) Neue Implementierung von Experience Platform Web SDK für die fortlaufende Datenerfassung, der Analytics Source Connector für Verlaufsdaten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Neue Implementierung der Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Platform</li></ul> |
| Bulk-Dateneinfüge-API | Die Bulk Data Insertion-API (BDIA) ist eine Adobe Analytics-Funktion, mit der Sie Server-Aufrufdaten in Dateistapeln hochladen können, anstatt Client-seitige Bibliotheken wie AppMeasurement zu verwenden. </p><p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Bulk Data Insertion-API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).</p> | <ul><li>[(Empfohlen) Neue Implementierung von Experience Platform Web SDK für die fortlaufende Datenerfassung, der Analytics Source Connector für Verlaufsdaten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Neue Implementierung der Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>[Adobe Experience Platform Edge Network Server-API und -Edge Network ](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}
