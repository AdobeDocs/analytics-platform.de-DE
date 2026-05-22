---
title: Weitere Informationen zu Ihrer Adobe Analytics-Implementierung und deren Wirkung auf Ihr Customer Journey Analytics-Upgrade
description: Erfahren Sie mehr über den empfohlenen Pfad für das Upgrade von Adobe Analytics auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
autotag-review: '2026-05-19T08:10:04.372Z'
TQID: 'https://experienceleague.adobe.com/DYm1jOVvaGGgUpz51TEXYPNyqvJdMMY-clhvSEiEEyw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 994
ht-degree: 98%

---

# Weitere Informationen zu Ihrer Adobe Analytics-Implementierung und deren Wirkung auf Ihr Customer Journey Analytics-Upgrade {#implementation-affects-upgrade}

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
>id="cja-upgrade-appmeasurement-third-party"
>title="AppMeasurement unter Verwendung eines Drittanbieter-Tag-Management-Tools"
>abstract="Eine Implementierung, die ein Tag-Management-Tool eines Drittanbieters verwendet."

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
>abstract="Arbeiten Sie intern in Ihrem Unternehmen zusammen, um zu ermitteln, welchen Implementierungstyp Sie derzeit zum Senden von Daten an Adobe Analytics verwenden. Arbeiten Sie beim Upgrade auf Customer Journey Analytics mit der Person oder dem Team zusammen, die bzw. das über diese Informationen verfügt.<br><br>Nachdem Sie den Implementierungstyp ermittelt haben, den Ihr Unternehmen verwendet, ändern Sie Ihre Antwort im Aktualisierungshandbuch zu Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Es gibt verschiedene Möglichkeiten für die Implementierung von Adobe Analytics. Beim Upgrade auf Customer Journey Analytics sind nicht alle Upgrade-Pfade für alle Adobe Analytics-Implementierungen verfügbar. Der empfohlene Upgrade-Pfad ist jedoch unabhängig davon verfügbar, wie Adobe Analytics in Ihrer Organisation implementiert wird.

Verwenden Sie die folgenden Informationen, um mehr über Ihre aktuelle Adobe Analytics-Implementierung und die für Ihre Organisation verfügbaren Upgrade-Pfade zu erfahren.

Wenden Sie sich an den Adobe-Support, wenn Sie konkretere Ratschläge, Anleitungen oder Unterstützung benötigen.

| Vorhandene Adobe Analytics-Implementierung | Beschreibung | Verfügbare Upgrade-Pfade |
|---------|----------|----------|
| AppMeasurement | AppMeasurement für JavaScript ist seit jeher eine gängige Methode zur Implementierung von Adobe Analytics.<p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit AppMeasurement für JavaScript](https://experienceleague.adobe.com/de/docs/analytics/implementation/js/overview).</p> | <ul><li>[(Empfohlen) Neue Implementierung des Experience Platform Web SDK für die fortlaufende Datenerfassung; der Analytics-Quell-Connector für historische Daten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Neue Implementierung des Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>[Migrieren von Adobe Analytics zum Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Analytics-Quell-Connector](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Adobe Analytics-Erweiterung (Tags) | <p>Tags in Adobe Experience Platform ist eine Tag-Management-Lösung, mit der Sie Analytics-Code bereitstellen und weitere Tagging-Vorgaben erfüllen können. Adobe bietet Integrationen mit anderen Lösungen und Produkten und ermöglicht die Bereitstellung von benutzerdefiniertem Code. Alle diese Aufgaben können ausgeführt werden, ohne dass Entwicklungsteams in Ihrer Organisation Code auf Ihrer Website aktualisieren müssen.</p><p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit der Analytics-Erweiterung](https://experienceleague.adobe.com/de/docs/analytics/implementation/launch/overview).</p> | <ul><li>[(Empfohlen) Neue Implementierung des Experience Platform Web SDK für die fortlaufende Datenerfassung; der Analytics-Quell-Connector für historische Daten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Neue Implementierung des Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>[Migrieren von Adobe Analytics zum Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Analytics-Quell-Connector](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Experience Platform-Web-SDK (alloy.js) | Das Experience Platform Web-SDK ist die derzeit von Adobe empfohlene Methode zur Implementierung von Adobe Analytics. Mit dem Adobe Experience Platform Edge Network können Sie Daten, die für mehrere Produkte bestimmt sind, an einen zentralen Ort senden. <p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit dem Adobe Experience Platform Edge Network](https://experienceleague.adobe.com/de/docs/analytics/implementation/aep-edge/overview).</p> | <ul><li>[(Empfohlen) Neue Implementierung des Experience Platform Web SDK für die fortlaufende Datenerfassung; der Analytics-Quell-Connector für historische Daten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Neue Implementierung des Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>[Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Experience Platform-Web-SDK-Erweiterung (Tags) | Das Experience Platform-Web-SDK ist die derzeit von Adobe empfohlene Methode zur Implementierung von Adobe Analytics für Web-Daten. Mit dem Adobe Experience Platform Edge Network können Sie Daten, die für mehrere Produkte bestimmt sind, an einen zentralen Ort senden. <p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit dem Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/de/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[(Empfohlen) Neue Implementierung des Experience Platform Web SDK für die fortlaufende Datenerfassung; der Analytics-Quell-Connector für historische Daten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Neue Implementierung des Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>[Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Experience Platform Mobile SDK | Das Experience Platform Mobile SDK ist die derzeit von Adobe empfohlene Methode zur Implementierung von Adobe Analytics für mobile Daten. Mit dem Adobe Experience Platform Edge Network können Sie Daten, die für mehrere Produkte bestimmt sind, an einen zentralen Ort senden.<p>Der Adobe Experience Platform Mobile SDK unterstützt die CX Enterprise-Lösungen und -Services von Adobe in Ihren Mobile Apps. </p><p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit dem Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/de/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[(Empfohlen) Neue Implementierung des Experience Platform Web SDK für die fortlaufende Datenerfassung; der Analytics-Quell-Connector für historische Daten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Neue Implementierung des Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>[Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Bulk-Dateneinfüge-API | Die Bulk-Dateneinfüge-API (BDIA) ist eine Adobe Analytics-Funktion, mit der Sie Server-Aufrufdaten in Dateistapeln hochladen können, anstatt Client-seitige Bibliotheken wie AppMeasurement zu verwenden. </p><p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Bulk Data Insertion-API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).</p> | <ul><li>[(Empfohlen) Neue Implementierung des Experience Platform Web SDK für die fortlaufende Datenerfassung; der Analytics-Quell-Connector für historische Daten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Neue Implementierung des Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>[Adobe Experience Platform Edge Network Server API und Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}


