---
title: Weitere Informationen zu Optionen für die Web-SDK-Implementierung beim Upgrade auf Customer Journey Analytics
description: Erfahren Sie mehr über die Optionen für die Web-SDK-Implementierung beim Upgrade auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 94a2bf2f-ad84-4f35-af8f-b8a5d9e5c607
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '350'
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

* [NPM](https://experienceleague.adobe.com/de/docs/experience-platform/web-sdk/install/npm): Installieren Sie das Web-SDK mithilfe des NPM-Package Managers auf Ihrer Website.

Weitere Informationen finden Sie unter [Überblick über die Web-SDK-Installation ](https://experienceleague.adobe.com/de/docs/experience-platform/web-sdk/install/overview) im Web SDK-Handbuch in Experience Platform.
