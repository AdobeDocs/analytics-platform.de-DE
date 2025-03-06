---
title: Weitere Informationen zu Web SDK-Implementierungsoptionen beim Upgrade auf Customer Journey Analytics
description: Erfahren Sie mehr über die Implementierungsoptionen von Web SDK beim Upgrade auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 1ac7059e76797b14c00993a2a46aa51b1ebfe6a2
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 38%

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
>title="Web-SDK für die angegebene Eigenschaft implementieren"
>abstract="Wählen Sie den gewünschten Implementierungstyp im Fragebogen aus, um detailliertere Anweisungen zu erhalten."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-third-party"
>title="Web-SDK-Bibliothek zum Tag-Management-System eines Drittanbieters hinzufügen"
>abstract="Arbeiten Sie mit dem Administrator über Ihr Tag-Management-System zusammen, um die Web SDK-Bibliothek zu Ihrer Site hinzuzufügen.<br><br>Die Zeit bis zum Abschluss dieser Aufgabe hängt stark von der Reaktionsfähigkeit des für Ihr Tag-Management-System verantwortlichen Benutzers ab. Das Hinzufügen der Web-SDK-Bibliothek kann mit der zugehörigen Implementierungslogik gebündelt und während der standardmäßigen Versionszyklen Ihres Unternehmens bereitgestellt werden."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Der empfohlene Upgrade-Prozess von Adobe Analytics auf Customer Journey Analytics ist eine neue Implementierung der Experience Platform Web SDK, der bevorzugten Datenerfassungsmethode für Customer Journey Analytics.

Es gibt drei unterstützte Möglichkeiten, Adobe Experience Platform Web SDK zu verwenden:

* [Web-SDK-Tag](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension)Erweiterung: Adobe empfiehlt die Verwendung dieser Methode. Installieren Sie einen Tag-Loader auf Ihrer Site und konfigurieren Sie dann Ihre Implementierung über die Datenerfassungs-Benutzeroberfläche von Adobe Experience Platform.

* [Web SDK JavaScript-Bibliothek](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library): Verweisen Sie auf eine CDN-gehostete Bibliotheksdatei oder hosten Sie die Bibliotheksdatei mithilfe Ihrer eigenen Infrastruktur. Aufrufe an die -Bibliothek im Code auf Ihrer Site.

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm): Installieren Sie Web SDK mithilfe des NPM-Package Managers auf Ihrer Site.

SDK Weitere Informationen finden Sie unter [Übersicht über die Installation von Web ](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview) im Experience Platform Web SDK-Handbuch.



