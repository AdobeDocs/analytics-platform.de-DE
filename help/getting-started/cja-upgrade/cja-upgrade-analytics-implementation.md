---
title: Weiter Informationen zu Ihrer Adobe Analytics-Implementierung und deren Wirkung auf Ihr Customer Journey Analytics-Upgrade
description: Erfahren Sie mehr über den empfohlenen Pfad beim Upgrade von Adobe Analytics auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '923'
ht-degree: 36%

---

# Weiter Informationen zu Ihrer Adobe Analytics-Implementierung und deren Wirkung auf Ihr Customer Journey Analytics-Upgrade {#implementation-affects-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement"
>title="AppMeasurement (manuelle JS-Datei)"
>abstract="Eine JavaScript-Implementierung, die AppMeasurement.js auf einer Seite lädt und Daten mithilfe des s-Objekts (z. B. s.eVar1) an Adobe sendet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-analyticsextension"
>title="Adobe Analytics-Erweiterung (Tags)"
>abstract="Eine Tags-Implementierung, die die Adobe Experience Platform-Datenerfassung (früher als Launch bekannt) lädt. Für das Tag ist die Adobe Analytics-Erweiterung installiert."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk"
>title="Web SDK (alloy.js)"
>abstract="Eine JavaScript-Implementierung, die die Web SDK-Bibliothek (alloy.js) auf einer Seite lädt und Daten mithilfe einer JSON-Payload an Adobe sendet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdkextension"
>title="Web SDK-Erweiterung (Tag)"
>abstract="Eine Tags-Implementierung, die die Adobe Experience Platform-Datenerfassung (früher als Launch bekannt) lädt. Für das Tag ist die Web SDK-Erweiterung installiert."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-api"
>title="Dateneinfüge-API"
>abstract="Eine Implementierung, die die App zum Einfügen von Daten oder die App zum Einfügen von Massendaten verwendet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-mobilesdk"
>title="Mobile SDK"
>abstract="Eine Implementierung, die das Adobe Experience Platform Mobile SDK verwendet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-unknown"
>title="Unbekannte Implementierung"
>abstract="Wenn Sie nicht die Person sind, die Ihre Implementierung verwaltet, können Sie diese Option vorübergehend auswählen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-determine-implementation"
>title="Bestimmen des vorhandenen Implementierungstyps"
>abstract="Arbeiten Sie intern in Ihrem Unternehmen zusammen, um zu ermitteln, welchen Implementierungstyp Sie derzeit zum Senden von Daten an Adobe Analytics verwenden. Es ist wahrscheinlich, dass Sie mit der Person oder dem Team zusammenarbeiten, die bzw. das diese Informationen kennt, wenn Sie bereit sind, zu Customer Journey Analytics zu migrieren.<br><br>Nachdem Sie den Implementierungstyp ermittelt haben, den Ihr Unternehmen verwendet, ändern Sie Ihre Antwort im Fragebogen."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Es gibt verschiedene Möglichkeiten, Adobe Analytics zu implementieren. Beim Upgrade auf Customer Journey Analytics sind nicht alle Upgrade-Pfade für alle Adobe Analytics-Implementierungen verfügbar. Der empfohlene Aktualisierungspfad ist jedoch unabhängig davon verfügbar, wie Adobe Analytics in Ihrem Unternehmen implementiert ist.

Verwenden Sie die folgenden Informationen, um mehr über Ihre aktuelle Adobe Analytics-Implementierung und die für Ihr Unternehmen verfügbaren Aktualisierungspfade zu erfahren.

Wenden Sie sich an den Adobe-Support, wenn Sie konkretere Ratschläge, Anleitungen oder Unterstützung benötigen.

| Vorhandene Adobe Analytics-Implementierung | Beschreibung | Verfügbare Aktualisierungspfade |
|---------|----------|----------|
| AppMeasurement | AppMeasurement für JavaScript ist seit jeher eine gängige Methode zur Implementierung von Adobe Analytics.<p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit AppMeasurement für JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview).</p> | <ul><li>[(Empfohlen) Neue Implementierung von Experience Platform Web SDK für die fortlaufende Datenerfassung, der Analytics Source Connector für Verlaufsdaten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Neue Implementierung der Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migrieren von Adobe Analytics zum Web SDK</li><li>[Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Adobe Analytics-Erweiterung (Tags) | <p>Tags in Adobe Experience Platform ist eine Tag-Management-Lösung, mit der Sie Analytics-Code bereitstellen und weitere Tagging-Vorgaben erfüllen können. Adobe bietet Integrationen mit anderen Lösungen und Produkten und ermöglicht die Bereitstellung von benutzerdefiniertem Code. Alle diese Aufgaben können ausgeführt werden, ohne dass Entwicklungsteams in Ihrer Organisation Code auf Ihrer Website aktualisieren müssen.</p><p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mithilfe der Analytics-Erweiterung](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview).</p> | <ul><li>[(Empfohlen) Neue Implementierung von Experience Platform Web SDK für die fortlaufende Datenerfassung, der Analytics Source Connector für Verlaufsdaten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Neue Implementierung der Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migrieren von Adobe Analytics zum Web SDK</li><li>[Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Experience Platform Web SDK (alloy.js) | Experience Platform Web SDK ist die derzeit von Adobe empfohlene Methode zur Implementierung von Adobe Analytics. Mit Adobe Experience Platform Edge Network können Sie Daten, die für mehrere Produkte bestimmt sind, an einen zentralen Ort senden. <p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit Adobe Experience Platform Edge Network](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview).</p> | <ul><li>[(Empfohlen) Neue Implementierung von Experience Platform Web SDK für die fortlaufende Datenerfassung, der Analytics Source Connector für Verlaufsdaten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Neue Implementierung der Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Platform</li></ul> |
| Experience Platform Web SDK-Erweiterung (Tags) | Experience Platform Web SDK ist die derzeit von Adobe empfohlene Methode zur Implementierung von Adobe Analytics für Web-Daten. Mit Adobe Experience Platform Edge Network können Sie Daten, die für mehrere Produkte bestimmt sind, an einen zentralen Ort senden. <p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit der Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[(Empfohlen) Neue Implementierung von Experience Platform Web SDK für die fortlaufende Datenerfassung, der Analytics Source Connector für Verlaufsdaten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Neue Implementierung der Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Platform</li></ul> |
| Experience Platform Mobile SDK | Die Experience Platform Mobile SDK ist die derzeit von Adobe empfohlene Methode zur Implementierung von Adobe Analytics für Mobilgeräte. Mit Adobe Experience Platform Edge Network können Sie Daten, die für mehrere Produkte bestimmt sind, an einen zentralen Ort senden.<p>Mit der Adobe Experience Platform Mobile SDK können Sie die Experience Cloud-Lösungen und -Services von Adobe in Ihren Mobile Apps nutzen. </p><p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit der Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[(Empfohlen) Neue Implementierung von Experience Platform Web SDK für die fortlaufende Datenerfassung, der Analytics Source Connector für Verlaufsdaten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Neue Implementierung der Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Platform</li></ul> |
| Bulk-Dateneinfüge-API | Die Bulk Data Insertion-API (BDIA) ist eine Adobe Analytics-Funktion, mit der Sie Server-Aufrufdaten in Dateistapeln hochladen können, anstatt Client-seitige Bibliotheken wie AppMeasurement zu verwenden. </p><p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Bulk Data Insertion-API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).</p> | <ul><li>[(Empfohlen) Neue Implementierung von Experience Platform Web SDK für die fortlaufende Datenerfassung, der Analytics Source Connector für Verlaufsdaten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Neue Implementierung der Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>[Adobe Experience Platform Edge Network Server-API und Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}
