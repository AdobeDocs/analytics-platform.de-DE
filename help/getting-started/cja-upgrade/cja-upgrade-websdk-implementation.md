---
title: Weitere Informationen zu Web SDK-Implementierungsoptionen beim Upgrade auf Customer Journey Analytics
description: Erfahren Sie mehr über die Implementierungsoptionen von Web SDK beim Upgrade auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 94a2bf2f-ad84-4f35-af8f-b8a5d9e5c607
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 58%

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

Der empfohlene Upgrade-Prozess von Adobe Analytics auf Customer Journey Analytics ist eine neue Implementierung der Experience Platform Web SDK, der bevorzugten Datenerfassungsmethode für Customer Journey Analytics.

Es gibt drei unterstützte Möglichkeiten, Adobe Experience Platform Web SDK zu verwenden:

* [Web-SDK-Tag](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension)Erweiterung: Adobe empfiehlt die Verwendung dieser Methode. Installieren Sie einen Tag-Loader auf Ihrer Site und konfigurieren Sie dann Ihre Implementierung über die Datenerfassungs-Benutzeroberfläche von Adobe Experience Platform.

* [Web SDK JavaScript-Bibliothek](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library): Verweisen Sie auf eine CDN-gehostete Bibliotheksdatei oder hosten Sie die Bibliotheksdatei mithilfe Ihrer eigenen Infrastruktur. Aufrufe an die -Bibliothek im Code auf Ihrer Site.

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm): Installieren Sie Web SDK mithilfe des NPM-Package Managers auf Ihrer Site.

SDK Weitere Informationen finden Sie unter [Übersicht über die Installation von Web ](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview) im Experience Platform Web SDK-Handbuch.
