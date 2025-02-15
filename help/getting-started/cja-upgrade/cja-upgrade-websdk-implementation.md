---
title: Grundlegendes zu den Implementierungsoptionen von Web SDK beim Upgrade auf Customer Journey Analytics
description: Erfahren Sie mehr über die Implementierungsoptionen von Web SDK beim Upgrade auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 971600fcc7d8a5aac4ad39812ab4a7af69d45ccc
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 1%

---

# Grundlegendes zu den Implementierungsoptionen von Web SDK beim Upgrade auf Customer Journey Analytics {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="Web SDK JavaScript-Bibliothek (alloy.js)"
>abstract="Fügen Sie die Web SDK-Bibliothek (alloy.js) auf jeder Seite Ihrer Site ein."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="Web SDK-Tag-Erweiterung"
>abstract="(Empfohlen) Wenn Sie Tags noch nicht verwenden, installieren Sie den Tag-Loader auf Ihrer Site. Wenn Sie bereits Tags verwenden, können Sie die Web SDK-Erweiterung zu Ihrer Tag-Eigenschaft hinzufügen. Diese Option umfasst Implementierungen, bei denen Tags in der Datenerfassung von Adobe Experience Platform und in Tag-Management-Systemen von Drittanbietern verwendet werden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="NPM-Paket"
>abstract="Verwenden Sie die Datenerfassungs-API, um Daten direkt an einen Datenstrom zu senden. Es werden sowohl nicht authentifizierte (Client-zu-Server) als auch authentifizierte (Server-zu-Server) Typen unterstützt."

<!-- markdownlint-enable MD034 -->

Das empfohlene Upgrade von Adobe Analytics auf Customer Journey Analytics ist eine neue Implementierung des Experience Platform Web SDK, der bevorzugten Datenerfassungsmethode für Customer Journey Analytics.

Es gibt drei unterstützte Möglichkeiten, Adobe Experience Platform Web SDK zu verwenden:

* [Web SDK-Tag-Erweiterung](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension): Adobe empfiehlt die Verwendung dieser Methode. Installieren Sie einen Tag-Loader auf Ihrer Site und konfigurieren Sie dann Ihre Implementierung über die Datenerfassungs-Benutzeroberfläche von Adobe Experience Platform.

* [Web SDK JavaScript-Bibliothek](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library): Verweisen Sie auf eine CDN-gehostete Bibliotheksdatei oder hosten Sie die Bibliotheksdatei mithilfe Ihrer eigenen Infrastruktur. Aufrufe an die -Bibliothek im Code auf Ihrer Site.

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm): Installieren Sie Web SDK mithilfe des NPM-Package Managers auf Ihrer Site.

Weitere Informationen finden Sie unter [Web SDK-](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview)) im Experience Platform Web SDK-Handbuch.



