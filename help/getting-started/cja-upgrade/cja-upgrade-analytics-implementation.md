---
title: Machen Sie sich mit Ihrer Adobe Analytics-Implementierung vertraut und erfahren Sie, wie sich dies auf Ihr Customer Journey Analytics-Upgrade auswirkt
description: Erfahren Sie mehr über den empfohlenen Pfad beim Upgrade von Adobe Analytics auf Customer Journey Analytics
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

# Machen Sie sich mit Ihrer Adobe Analytics-Implementierung vertraut und erfahren Sie, wie sich dies auf Ihr Customer Journey Analytics-Upgrade auswirkt

>[!NOTE]
> 
>Verwenden Sie die Informationen auf dieser Seite bei der Beantwortung von Fragen in der Checkliste für das [Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/).

Es gibt verschiedene Möglichkeiten, Adobe Analytics zu implementieren. Beim Upgrade auf Customer Journey Analytics stehen nicht alle Upgrade-Pfade für alle Adobe Analytics-Implementierungen zur Verfügung. Der empfohlene Aktualisierungspfad ist jedoch unabhängig davon verfügbar, wie Adobe Analytics in Ihrem Unternehmen implementiert ist.

Verwenden Sie die folgenden Informationen, um mehr über Ihre aktuelle Adobe Analytics-Implementierung und die für Ihr Unternehmen verfügbaren Aktualisierungspfade zu erfahren.

Wenden Sie sich an den Adobe-Support, wenn Sie konkretere Ratschläge, Anleitungen oder Unterstützung benötigen.

| Vorhandene Adobe Analytics-Implementierung | Beschreibung | Verfügbare Aktualisierungspfade |
|---------|----------|----------|
| AppMeasurement | AppMeasurement für JavaScript ist seit jeher eine gängige Methode zur Implementierung von Adobe Analytics.<p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit AppMeasurement für JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview)</p> | <ul><li>(Empfohlen) Neue Implementierung von Experience Platform Web SDK mit dem Analytics Source Connector</li><li>Neue Implementierung des Experience Platform Web SDK</li><li>Migrieren von Adobe Analytics zum Web SDK</li><li>Analytics-Quell-Connector</li></ul> |
| Adobe Analytics-Erweiterung (Tags) | <p>Tags in Adobe Experience Platform ist eine Tag-Management-Lösung, mit der Sie Analytics-Code bereitstellen und weitere Tagging-Vorgaben erfüllen können. Adobe bietet Integrationen mit anderen Lösungen und Produkten und ermöglicht die Bereitstellung von benutzerdefiniertem Code. Alle diese Aufgaben können ausgeführt werden, ohne dass Entwicklungsteams in Ihrer Organisation Code auf Ihrer Website aktualisieren müssen.</p><p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mithilfe der Analytics-Erweiterung](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview)</p> | <ul><li>(Empfohlen) Neue Implementierung von Experience Platform Web SDK mit dem Analytics Source Connector</li><li>Neue Implementierung des Experience Platform Web SDK</li><li>Migrieren von Adobe Analytics zum Web SDK</li><li>Analytics-Quell-Connector</li></ul> |
| Experience Platform Web SDK (alloy.js) | Die Experience Platform Web SDK ist die derzeit empfohlene Adobe-Methode zur Implementierung von Adobe Analytics. Mit dem Adobe Experience Platform-Edge Network können Sie Daten, die für mehrere Produkte bestimmt sind, an einen zentralen Ort senden. <p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit dem Adobe Experience Platform-Edge Network ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)</p> | <ul><li>(Empfohlen) Neue Implementierung von Experience Platform Web SDK mit dem Analytics Source Connector</li><li>Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Platform</li></ul> |
| Experience Platform Web SDK-Erweiterung (Tags) | Die Experience Platform Web SDK ist die derzeit empfohlene Methode zur Implementierung von Adobe Analytics für Web-Daten auf Adobe. Mit dem Adobe Experience Platform-Edge Network können Sie Daten, die für mehrere Produkte bestimmt sind, an einen zentralen Ort senden. <p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit der Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>(Empfohlen) Neue Implementierung von Experience Platform Web SDK mit dem Analytics Source Connector</li><li>Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Platform</li></ul> |
| Experience Platform Mobile SDK | Die Experience Platform Mobile SDK ist die derzeit empfohlene Methode zur Implementierung von Adobe Analytics für mobile Daten auf der Adobe. Mit dem Adobe Experience Platform-Edge Network können Sie Daten, die für mehrere Produkte bestimmt sind, an einen zentralen Ort senden.<p>Mit der Adobe Experience Platform Mobile SDK können Sie Adobe-Experience Cloud-Lösungen und -Services in Ihren Apps nutzen. </p><p>Weitere Informationen zu diesem Implementierungstyp finden Sie unter [Implementieren von Adobe Analytics mit der Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>(Empfohlen) Neue Implementierung von Experience Platform Web SDK mit dem Analytics Source Connector</li><li>Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Platform</li></ul> |

{style="table-layout:auto"}
