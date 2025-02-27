---
title: Weitere Informationen zu Web SDK-Implementierungsoptionen beim Upgrade auf Customer Journey Analytics
description: Erfahren Sie mehr über die Implementierungsoptionen von Web SDK beim Upgrade auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 43%

---

# Weitere Informationen zu Web SDK-Implementierungsoptionen beim Upgrade auf Customer Journey Analytics {#web-sdk-implementation-options}

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
>abstract="(Empfohlen) Wenn Sie noch keine Tags verwenden, installieren Sie den Tag-Loader auf Ihrer Site. Wenn Sie bereits Tags verwenden, können Sie die Web SDK-Erweiterung zu Ihrer Tag-Eigenschaft hinzufügen. Diese Option umfasst Implementierungen, bei denen Tags in der Datenerfassung von Adobe Experience Platform und in Tag-Management-Systemen von Drittanbietern verwendet werden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="NPM-Paket"
>abstract="Verwenden Sie die Datenerfassungs-API, um Daten direkt an einen Datenstrom zu senden. Es werden sowohl nicht authentifizierte (Client-zu-Server) als auch authentifizierte (Server-zu-Server) Typen unterstützt."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Der empfohlene Upgrade-Prozess von Adobe Analytics auf Customer Journey Analytics ist eine neue Implementierung der Experience Platform Web SDK, der bevorzugten Datenerfassungsmethode für Customer Journey Analytics.

Es gibt drei unterstützte Möglichkeiten, Adobe Experience Platform Web SDK zu verwenden:

* [Web-SDK-Tag](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension)Erweiterung: Adobe empfiehlt die Verwendung dieser Methode. Installieren Sie einen Tag-Loader auf Ihrer Site und konfigurieren Sie dann Ihre Implementierung über die Datenerfassungs-Benutzeroberfläche von Adobe Experience Platform.

* [Web SDK JavaScript-Bibliothek](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library): Verweisen Sie auf eine CDN-gehostete Bibliotheksdatei oder hosten Sie die Bibliotheksdatei mithilfe Ihrer eigenen Infrastruktur. Aufrufe an die -Bibliothek im Code auf Ihrer Site.

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm): Installieren Sie Web SDK mithilfe des NPM-Package Managers auf Ihrer Site.

SDK Weitere Informationen finden Sie unter [Übersicht über die Installation von Web ](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview) im Experience Platform Web SDK-Handbuch.



