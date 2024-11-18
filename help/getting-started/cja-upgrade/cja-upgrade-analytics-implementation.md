---
title: Grundlegendes zu Ihrer Adobe Analytics-Implementierung und wie sie sich auf Ihre Aktualisierung auf Customer Journey Analytics auswirkt
description: Erfahren Sie mehr über den empfohlenen Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: 5ce69400a01566728f374d68ac08a981adfd8b6e
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 19%

---

# Grundlegendes zu Ihrer Adobe Analytics-Implementierung und wie sie sich auf Ihre Aktualisierung auf Customer Journey Analytics auswirkt

>[!NOTE]
> 
>Verwenden Sie die Informationen auf dieser Seite, wenn Sie Fragen in der Checkliste für das [Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/) beantworten.

Es gibt verschiedene Möglichkeiten, Adobe Analytics zu implementieren. Beim Upgrade auf Customer Journey Analytics sind nicht alle Aktualisierungspfade für alle Adobe Analytics-Implementierungen verfügbar. Der empfohlene Aktualisierungspfad ist jedoch unabhängig von der Implementierung von Adobe Analytics in Ihrem Unternehmen verfügbar.

Verwenden Sie die folgenden Informationen, um mehr über Ihre aktuelle Adobe Analytics-Implementierung zu erfahren und zu erfahren, welche Aktualisierungspfade für Ihr Unternehmen verfügbar sind.

Wenden Sie sich an den Adobe-Support, wenn Sie konkretere Ratschläge, Anleitungen oder Unterstützung benötigen.

| Vorhandene Adobe Analytics-Implementierung | Beschreibung | Verfügbare Aktualisierungswege |
|---------|----------|----------|
| AppMeasurement | AppMeasurement für JavaScript ist seit jeher eine gängige Methode zur Implementierung von Adobe Analytics.<p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit AppMeasurement für JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview)</p> | <ul><li>(Empfohlen) Neue Implementierung des Experience Platform Web SDK mit dem Analytics Source Connector</li><li>Neue Implementierung des Experience Platform Web SDK</li><li>Migrieren von Adobe Analytics zum Web SDK</li><li>Analytics-Quell-Connector</li></ul> |
| Adobe Analytics-Erweiterung (Tags) | <p>Tags in Adobe Experience Platform ist eine Tag-Management-Lösung, mit der Sie Analytics-Code bereitstellen und weitere Tagging-Vorgaben erfüllen können. Adobe bietet Integrationen mit anderen Lösungen und Produkten und ermöglicht die Bereitstellung von benutzerdefiniertem Code. Alle diese Aufgaben können ausgeführt werden, ohne dass Entwicklungsteams in Ihrer Organisation Code auf Ihrer Website aktualisieren müssen.</p><p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit der Analytics-Erweiterung](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview)</p> | <ul><li>(Empfohlen) Neue Implementierung des Experience Platform Web SDK mit dem Analytics Source Connector</li><li>Neue Implementierung des Experience Platform Web SDK</li><li>Migrieren von Adobe Analytics zum Web SDK</li><li>Analytics-Quell-Connector</li></ul> |
| Experience Platform Web SDK (legierte.js) | Das Experience Platform Web SDK ist die derzeit empfohlene Adobe zur Implementierung von Adobe Analytics. Mit dem Adobe Experience Platform-Edge Network können Sie Daten an mehrere Produkte an einen zentralen Ort senden. <p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit dem Adobe Experience Platform-Edge Network](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)</p> | <ul><li>(Empfohlen) Neue Implementierung des Experience Platform Web SDK mit dem Analytics Source Connector</li><li>Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Platform</li></ul> |
| Experience Platform Web SDK-Erweiterung (Tags) | Das Experience Platform Web SDK ist die derzeit empfohlene Adobe zur Implementierung von Adobe Analytics für Webdaten. Mit dem Adobe Experience Platform-Edge Network können Sie Daten an mehrere Produkte an einen zentralen Ort senden. <p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit dem Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>(Empfohlen) Neue Implementierung des Experience Platform Web SDK mit dem Analytics Source Connector</li><li>Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Platform</li></ul> |
| Experience Platform Mobile SDK | Das Experience Platform Mobile SDK ist die derzeit empfohlene Adobe zur Implementierung von Adobe Analytics für Mobildaten. Mit dem Adobe Experience Platform-Edge Network können Sie Daten an mehrere Produkte an einen zentralen Ort senden.<p>Mit dem Adobe Experience Platform Mobile SDK können Sie Adobe Experience Cloud-Lösungen und -Dienste in Ihren mobilen Apps nutzen. </p><p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit dem Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>(Empfohlen) Neue Implementierung des Experience Platform Web SDK mit dem Analytics Source Connector</li><li>Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Platform</li></ul> |

{style="table-layout:auto"}
