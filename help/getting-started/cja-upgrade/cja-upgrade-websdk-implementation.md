---
title: Weitere Informationen zu Optionen für die Web-SDK-Implementierung beim Upgrade auf Customer Journey Analytics
description: Erfahren Sie mehr über die Optionen für die Web-SDK-Implementierung beim Upgrade auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 94a2bf2f-ad84-4f35-af8f-b8a5d9e5c607
autotag-review: '2026-05-19T08:21:32.040Z'
TQID: 'https://experienceleague.adobe.com/5mjQHmjaBfxAusSR3EuDykYxJzgaR6P9jiL3HH09Bns'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 394
ht-degree: 100%

---

# Weitere Informationen zu Optionen für die Web-SDK-Implementierung beim Upgrade auf Customer Journey Analytics {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="Web-SDK-JavaScript-Bibliothek (alloy.js)"
>abstract="Fügen Sie die Web-SDK-Bibliothek (alloy.js) auf jeder Seite Ihrer Website ein."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="Web SDK-Tag-Erweiterung"
>abstract="(Empfohlen) Wenn Sie noch keine Tags verwenden, installieren Sie den Tag Loader auf Ihrer Website. Wenn Sie bereits Tags verwenden, können Sie die Web-SDK-Erweiterung zu Ihrer Tag-Eigenschaft hinzufügen. Diese Option umfasst Implementierungen, bei denen Tags in der Datenerfassung von Adobe Experience Platform und in Tag-Management-Systemen von Drittanbietern verwendet werden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="NPM-Paket"
>abstract="Verwenden Sie die Datenerfassungs-API, um Daten direkt an einen Datenstrom zu senden. Es werden sowohl nicht authentifizierte (Client-zu-Server) als auch authentifizierte (Server-zu-Server) Typen unterstützt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-no-selection"
>title="Implementieren der Web-SDK für die angegebene Eigenschaft"
>abstract="Wählen Sie im Aktualisierungshandbuch den gewünschten Implementierungstyp aus, um detailliertere Anweisungen zu erhalten."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-third-party"
>title="Hinzufügen der Web SDK-Bibliothek zu einem Drittanbieter-Tag-Management-System"
>abstract="Arbeiten Sie mit den Admins für Ihr Tag-Management-System zusammen daran, die Web SDK-Bibliothek zu Ihrer Site hinzuzufügen.<br><br>Die Zeit bis zum Abschluss dieser Aufgabe hängt stark von der Reaktionsfähigkeit der für Ihr Tag-Management-System verantwortlichen Person ab. Das Hinzufügen der Web-SDK-Bibliothek kann mit der zugehörigen Implementierungslogik gebündelt und im Zuge der standardmäßigen Versionszyklen Ihres Unternehmens bereitgestellt werden."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Der empfohlene Prozess für das Upgrade von Adobe Analytics auf Customer Journey Analytics ist eine neue Implementierung des Experience Platform-Web-SDK, der bevorzugten Datenerfassungsmethode für Customer Journey Analytics.

Es werden drei Möglichkeiten unterstützte, um das Adobe Experience Platform-Web-SDK zu verwenden:

* [Web-SDK-Tag-Erweiterung](https://experienceleague.adobe.com/de/docs/experience-platform/web-sdk/install/extension): Adobe empfiehlt, diese Methode zu verwenden. Installieren Sie einen Tag Loader auf Ihrer Website und konfigurieren Sie dann Ihre Implementierung über die Datenerfassungs-Benutzeroberfläche von Adobe Experience Platform.

* [Web-SDK-JavaScript-Bibliothek](https://experienceleague.adobe.com/de/docs/experience-platform/web-sdk/install/library): Verweisen Sie auf eine vom CDN gehostete Bibliotheksdatei oder hosten Sie die Bibliotheksdatei mithilfe Ihrer eigenen Infrastruktur. Rufen Sie die Bibliothek im Code auf Ihrer Site auf.

* [NPM](https://experienceleague.adobe.com/de/docs/experience-platform/web-sdk/install/npm): Installieren Sie das Web-SDK mithilfe des NPM-Paket-Managers auf Ihrer Website.

Weitere Informationen finden Sie unter [Überblick über die Web-SDK-Installation ](https://experienceleague.adobe.com/de/docs/experience-platform/web-sdk/install/overview) im Web SDK-Handbuch in Experience Platform.
