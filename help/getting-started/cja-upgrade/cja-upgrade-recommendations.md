---
title: Empfohlener Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 4%

---

# Upgrade von Adobe Analytics auf Customer Journey Analytics

Bevor Sie mit der Aktualisierung von Adobe Analytics auf Customer Journey Analytics beginnen, sollten Sie zunächst die empfohlenen Aktualisierungsschritte verstehen.

Abhängig von verschiedenen Faktoren, wie Timeline- und Ressourcenbeschränkungen, sind die empfohlenen Aktualisierungsschritte für Ihr Unternehmen möglicherweise nicht praktikabel. Nachdem Sie die empfohlenen Aktualisierungsschritte verstanden haben, füllen Sie den Fragebogen aus, um dynamisch Aktualisierungsschritte zu generieren, die auf die individuellen Umstände Ihres Unternehmens zugeschnitten sind.

## 1. Machen Sie sich mit den empfohlenen Aktualisierungsschritten vertraut

>[!NOTE]
>
>Die in diesem Abschnitt beschriebenen Aktualisierungsschritte sind die empfohlenen Aktualisierungsschritte, die jedes Unternehmen für eine erfolgreiche Aktualisierung von Adobe Analytics auf Customer Journey Analytics verwenden kann.
>
>Je nach verschiedenen Faktoren, wie Timeline- und Ressourcenbeschränkungen, sind die empfohlenen Aktualisierungsschritte jedoch möglicherweise nicht für Ihr Unternehmen praktisch. Nachdem Sie die empfohlenen Aktualisierungsschritte verstanden haben, füllen Sie den Fragebogen [Adobe Analytics to Customer Journey Analytics Upgrade](https://gigazelle.github.io/cja-ttv/) aus, um dynamisch Aktualisierungsschritte zu generieren, die auf die individuellen Gegebenheiten Ihres Unternehmens zugeschnitten sind.

Die empfohlenen Schritte bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics sind eine neue Implementierung des Experience Platform Web SDK, der bevorzugten Datenerfassungsmethode für Customer Journey Analytics. In Verbindung mit dem Web SDK empfiehlt Adobe außerdem die Verwendung des Analytics-Quell-Connectors, um historische Adobe Analytics-Daten beizubehalten und einen parallelen Datenvergleich durchzuführen.

Nach der vollständigen Umstellung auf Customer Journey Analytics kann der Analytics-Quell-Connector deaktiviert und das Experience Platform Web SDK exklusiv verwendet werden.

1. **Implementieren des Experience Platform Web SDK**

   Eine neue Implementierung des Experience Platform Web SDK ist die beste Methode, Daten für Customer Journey Analytics zu erfassen. Es bietet die beste Grundlage, um Customer Journey Analytics optimal zu nutzen, da es die leistungsfähigste, einfachste und zukunftssichere Methode zur Implementierung von Customer Journey Analytics ist.

   * Leistungsstarke Berichterstellung und Datenverfügbarkeit, da Adobe Experience Platform für Anwendungsfälle der Echtzeit-Personalisierung entwickelt wurde

   * Sie können die Implementierung für die Adobe Experience Cloud-Datenerfassung zwischen anderen Experience Cloud-Produkten (AJO, RTCDP usw.) konsolidieren.

   * Es besteht keine Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar, Ereignis usw.).

1. **Einrichten des Adobe Analytics-Quell-Connectors**

   Um einen reibungslosen Übergang zur Verwendung des Experience Platform Web SDK mit Customer Journey Analytics zu erleichtern, empfiehlt Adobe auch die Verwendung des Adobe Analytics-Quell-Connectors. Auf diese Weise können Sie historische Daten speichern und Daten aus Ihrer bestehenden Adobe Analytics-Implementierung in Customer Journey Analytics zusammen mit den Daten aus Ihrer neuen Experience Platform Web SDK-Implementierung anzeigen.

   Der Analytics-Quell-Connector bietet Ihnen folgende Möglichkeiten:

   * Bringen Sie Ihre historischen Adobe Analytics Report Suite-Daten in Adobe Experience Platform und Customer Journey Analytics.

     Sie können den Analytics-Quell-Connector so lange ausführen lassen, wie Sie die historischen Adobe Analytics-Daten beibehalten müssen.

   * Zeigen Sie die Daten an, die mit Ihrer ursprünglichen Adobe Analytics-Implementierung (entweder AppMeasurement, der Analytics-Erweiterung oder der Web SDK-Erweiterung) innerhalb von Customer Journey Analytics erfasst wurden. Sie können diese Daten nebeneinander mit denen Ihrer neuen Web SDK-Implementierung vergleichen.

     Sie können den Analytics-Quell-Connector so lange laufen lassen, bis Sie mit den Unterschieden vertraut und zufrieden sind. <!--elaborate on what those differences are? -->

   Der Analytics-Quell-Connector als eigenständige Implementierung ist keine empfohlene langfristige Methode zur Verwendung von Customer Journey Analytics. Dies liegt an einer hohen Latenz, übersichtlichen und komplexen Schemata, der Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar usw.) und der Schwierigkeit, schließlich vom Quell-Connector zur empfohlenen Web SDK-Implementierung zu wechseln.

## 2. Dynamisches Generieren von Aktualisierungsschritten für Ihre Organisation

Abhängig von verschiedenen Faktoren, wie Timeline- und Ressourcenbeschränkungen, sind die unter [Die empfohlenen Aktualisierungsschritte verstehen](#1-understand-the-recommended-upgrade-steps) beschriebenen empfohlenen Aktualisierungsschritte für Ihr Unternehmen möglicherweise nicht praktisch.

So zeigen Sie die dynamisch generierten Aktualisierungsschritte für die individuellen Umstände Ihres Unternehmens an:

1. Füllen Sie den Fragebogen [Adobe Analytics zum Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/) aus.

   Nach Abschluss dieses Fragebogens erhalten Sie schrittweise Anweisungen, in denen die optimalen, für Ihr Unternehmen einzigartigen Upgrade-Schritte beschrieben werden. Dies sind die Aktualisierungsschritte, die am besten mit Ihrer bestehenden Adobe Analytics-Umgebung und Ihren Customer Journey Analytics-Zielen übereinstimmen.

1. Folgen Sie den generierten schrittweisen Anweisungen zum Aktualisieren auf Customer Journey Analytics.

<!--

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 



When upgrading from Adobe Analytics to Customer Journey Analytics, no single set of upgrade steps exist that are optimal for every organization.

Adobe recommends using the dynamically generated upgrade steps that are unique to your organization. These upgrade steps are generated after you complete an upgrade questionnaire, which helps you understand the best way for your organization to upgrade to Customer Journey Analytics. 

Generic upgrade steps are also available.

1. **Implement the Experience Platform Web SDK**

   A new implementation of the Experience Platform Web SDK provides the best foundation to get the most out of Customer Journey Analytics. 
   
   It is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics:

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector**

   The Analytics source connector is a recommended part of the piece when upgrading to Customer Journey Analytics. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the Web SDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new Web SDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->

<!--

   When you no longer need the Analytics source connector because you have enough historical data from your new implementation and you are familiar with the reporting differences in Customer Journey Analytics, you should turn off the Analytics source connector. With the Experience Platform Web SDK implementation, the Analytics source connector is not needed.  
   
   The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended Web SDK implementation. 
   
-->









