---
title: Empfohlener Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: 5ce69400a01566728f374d68ac08a981adfd8b6e
workflow-type: tm+mt
source-wordcount: '1545'
ht-degree: 7%

---

# Upgrade von Adobe Analytics auf Customer Journey Analytics

Beim Upgrade von Adobe Analytics auf Customer Journey Analytics empfiehlt Adobe eine neue Implementierung des Experience Platform Web SDK in Verbindung mit dem Analytics-Quell-Connector, wie unter [Empfohlene Aktualisierungsschritte für die meisten Unternehmen](#recommended-upgrade-steps-for-most-organizations) beschrieben.

Abhängig von verschiedenen Faktoren, wie Timeline- und Ressourcenbeschränkungen, sind die empfohlenen Aktualisierungsschritte für Ihr Unternehmen möglicherweise nicht praktikabel. Verwenden Sie in diesem Fall den Fragebogen [Adobe Analytics to Customer Journey Analytics Upgrade](https://gigazelle.github.io/cja-ttv/) , um dynamisch Aktualisierungsschritte zu generieren, die auf die individuellen Gegebenheiten Ihres Unternehmens zugeschnitten sind.

## Empfohlene Upgrade-Schritte für die meisten Unternehmen

>[!NOTE]
>
>Die in diesem Abschnitt beschriebenen Aktualisierungsschritte sind die empfohlenen Aktualisierungsschritte, die jedes Unternehmen für eine erfolgreiche Aktualisierung von Adobe Analytics auf Customer Journey Analytics verwenden kann.
>
>Je nach verschiedenen Faktoren, wie Timeline- und Ressourcenbeschränkungen, sind die empfohlenen Aktualisierungsschritte jedoch möglicherweise nicht für Ihr Unternehmen praktisch. Verwenden Sie in diesem Fall den Fragebogen [Adobe Analytics to Customer Journey Analytics Upgrade](https://gigazelle.github.io/cja-ttv/) , um dynamisch Aktualisierungsschritte zu generieren, die auf die individuellen Gegebenheiten Ihres Unternehmens zugeschnitten sind.

Die empfohlene Aktualisierung von Adobe Analytics auf Customer Journey Analytics ist eine neue Implementierung des Experience Platform Web SDK, der bevorzugten Datenerfassungsmethode für Customer Journey Analytics. In Verbindung mit dem Web SDK empfiehlt Adobe außerdem die Verwendung des Analytics-Quell-Connectors, um Ihnen bei der Umstellung auf Customer Journey Analytics zu helfen. Verwenden Sie den Analytics-Quell-Connector, um historische Adobe Analytics-Daten beizubehalten und einen parallelen Datenvergleich durchzuführen.

Nach der vollständigen Umstellung auf Customer Journey Analytics kann der Analytics-Quell-Connector deaktiviert und das Experience Platform Web SDK exklusiv verwendet werden.

### Von hoher Ebene empfohlener Aktualisierungsprozess

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

### Detaillierte empfohlene Aktualisierungsschritte

Die folgenden Schritte beschreiben den empfohlenen Prozess für die Aktualisierung von Adobe Analytics auf Customer Journey Analytics.

Jeder Schritt bietet eine allgemeine Erläuterung eines detaillierteren Prozesses. Folgen Sie dem Link für jeden Schritt und führen Sie die zugehörigen Aufgaben aus. Kehren Sie dann zu dieser Seite zurück und fahren Sie mit dem nächsten Schritt im Prozess fort.

1. [Planen Sie Ihre XDM-Schemaarchitektur](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Erstellen Sie das gewünschte benutzerdefinierte Schema in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   Beachten Sie beim Erstellen Ihres Schemas die folgenden Optionen:

   * Wenn Sie Customer Journey Analytics in RTCDP integrieren möchten, müssen Sie die Option **[!UICONTROL Profil]** in Ihrem Schema aktivieren, wie unter [Erstellen eines XDM-Schemas zur Verwendung mit Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) beschrieben. Wenn diese Option aktiviert ist, werden diese Daten bei der Erfassung von Daten in Datensätzen, die auf diesem Schema basieren, mit dem Echtzeit-Kundenprofil zusammengeführt.

   * Wenn Sie Streaming-Mediendaten einbeziehen möchten, müssen Sie [Ihr Schema so konfigurieren, dass Streaming-Daten erfasst und verwendet werden](/help/data-ingestion/streaming.md).

1. [Erstellen Sie einen Datensatz in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. (Optional) Wenn Sie Klassifizierungsdaten in Adobe Analytics verwenden, können Sie Ihrem Datensatz unter Customer Journey Analytics Klassifizierungsdaten hinzufügen.

   Erstellen Sie dazu einen Lookup-Datensatz für jede Dimension mit Classification-Daten](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).[

1. Erstellen Sie bei Adobe Analytics-Implementierungen mit AppMeasurement oder der Analytics-Erweiterung (Tags) [einen Datastream in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md) <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->.

   Bei Adobe Analytics-Implementierungen mit dem Web SDK ist bereits ein Datenspeicher vorhanden.

1. [Fügen Sie Adobe Experience Platform als Dienst zu Ihrem Datastream hinzu](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md).

1. (Optional) Wenn Sie Customer Journey Analytics in Adobe Journey Optimizer integrieren möchten, verwenden Sie das Personalisierungsobjekt in Ihrer Implementierung zur Verwendung in Adobe Journey Optimizer.

1. Erweitern Sie den Abschnitt, der beschreibt, wie Sie das Experience Platform Web SDK für Ihre Customer Journey Analytics-Implementierung implementieren möchten, und führen Sie dann die zugehörigen Schritte aus:

   + + + Manuelle Implementierung (JS-Datei)

   1. [Fügen Sie Ihrer Site &quot;legate.js&quot;hinzu.](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22)

   1. Füllen Sie ein XDM-Objekt und senden Sie es an den Datastream.

+++

   +++Tags

   1. [Implementieren Sie das Lader-Tag auf Ihrer Site](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md).

   1. [Erstellen Sie eine Tag-Eigenschaft und fügen Sie die Adobe Experience Platform Web SDK-Erweiterung hinzu](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md).

   1. [Fügen Sie dem Tag ](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md) die XDM-Datenerfassungslogik hinzu.

+++

+++ API

   1. Verwenden Sie die Edge Network-API, um Daten an den gewünschten Datastream zu senden.

+++

1. Überprüfen Sie, ob Ihre Web SDK-Implementierung Daten an einen Datensatz sendet.

1. [Erstellen Sie eine Verbindung in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. (Optional) Verknüpfen Sie Webdaten mit Daten aus anderen Kanälen, z. B. Callcenter-Daten.

   Dies erreichen Sie durch Hinzufügen zusätzlicher Datensätze zu Ihrer Customer Journey Analytics-Verbindung.

1. [Erstellen Sie eine Datenansicht in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [Überprüfen Sie, ob die Daten in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md) fließen.

1. (Optional) Importieren Sie historische Daten aus Adobe Analytics mithilfe des Analytics-Quell-Connectors:

   >[!NOTE]
   >
   >Führen Sie die folgenden Schritte aus, wenn Sie noch keinen Analytics-Quell-Connector erstellt haben.
   >
   >Wenn Sie den Analytics-Quell-Connector bereits mit Customer Journey Analytics verwenden, führen Sie die unter [Wechsel vom Analytics-Quell-Connector zum Web SDK für Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md) beschriebenen Schritte aus.

   1. [Erstellen Sie ein XDM-Schema für den Analytics-Quell-Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

   1. [Erstellen Sie die Analytics-Quell-Connector- und Zuordnungsfelder](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   1. [Fügen Sie den Datensatz des Analytics-Quell-Connectors zur Verbindung hinzu](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. [Migrieren von Projekten und Komponenten](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).

1. (Optional) Wenn Sie Marketingkanäle in Adobe Analytics verwenden, können Sie [ein abgeleitetes Marketingkanalfeld in Customer Journey Analytics](/help/data-views/derived-fields/derived-fields.md#marketing-channels) erstellen.

   Abgeleitete Felder sind ein wichtiger Aspekt der Echtzeitberichterstellung in Customer Journey Analytics. Mit einem abgeleiteten Feld können Sie mithilfe eines anpassbaren Regel-Builders (Regel-Builder) spontan (häufig komplexe) Datenmanipulationen definieren.

   Eine Verwendung für abgeleitete Felder besteht darin, ein abgeleitetes Marketing-Kanal-Feld zu definieren, das den korrekten Marketing-Kanal anhand einer oder mehrerer Bedingungen bestimmt (z. B. URL-Parameter, Seiten-URL, Seitenname).

   Verwenden Sie [die Vorlage der Marketing-Kanal-Funktion](/help/data-views/derived-fields/derived-fields.md#marketing-channels) in abgeleiteten Feldern, um schnell ein abgeleitetes Feld für Marketing-Kanäle zu erstellen.

1. Vergleichen Sie Daten aus Ihrer alten Implementierung mit Daten aus Ihrer neuen Implementierung und stellen Sie sicher, dass Sie alle Unterschiede und deren Existenz verstehen.

1. Erfahren Sie mehr über die Unterstützung von [Funktionen in Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md). Die meisten Adobe Analytics-Funktionen werden im Customer Journey Analytics unterstützt und viele zusätzliche Funktionen sind im Customer Journey Analytics verfügbar.

1. Planen Sie das Onboarding von Benutzern.

   Wie in Adobe Analytics ist auch in Customer Journey Analytics der Analysis Workspace das wichtigste Werkzeug für die Benutzenden. Es gibt jedoch einige wesentliche Unterschiede bei der Verwendung von Analysis Workspace in Customer Journey Analytics, die die Benutzenden kennen sollten.

   Sie sollten Ihren Benutzenden ausreichend Zeit (3–6 Monate) geben, um sich mit den wichtigsten Unterschieden von Analysis Workspace in Customer Journey Analytics vertraut zu machen.

   Informationen zu einigen der wichtigsten Unterschiede zwischen Adobe Analytics und Customer Journey Analytics finden Sie im [Benutzerhandbuch für Adobe Analytics-Benutzende](/help/getting-started/aa-to-cja-user.md).

1. Deaktivieren Sie die AppMeasurement-Datenerfassung.

1. Deaktivieren Sie den Analytics-Quell-Connector.

   Mit der Experience Platform Web SDK-Implementierung ist der Analytics-Quell-Connector nur für Adobe Analytics-Verlaufsdaten und zum Vergleich von Daten aus Ihrer ursprünglichen Implementierung mit denen Ihrer neuen Implementierung erforderlich.

   Wenn Sie über ausreichend historische Daten aus Ihrer neuen Implementierung verfügen und mit den Unterschieden bei der Customer Journey Analytics in der Berichterstellung vertraut sind, sollten Sie den Analytics-Quell-Connector deaktivieren.

## Dynamisches Generieren von Aktualisierungsschritten für Ihre Organisation

Abhängig von verschiedenen Faktoren, wie Timeline- und Ressourcenbeschränkungen, sind die unter [Die empfohlenen Aktualisierungsschritte verstehen](#1-understand-the-recommended-upgrade-steps) beschriebenen empfohlenen Aktualisierungsschritte für Ihr Unternehmen möglicherweise nicht praktisch.

So generieren Sie dynamisch Aktualisierungsschritte für die individuellen Umstände Ihres Unternehmens:

1. Füllen Sie den Fragebogen [Adobe Analytics zum Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/) aus.

   Nach dem Ausfüllen dieses Fragebogens erhalten Sie schrittweise Anweisungen, in denen die optimalen, für Ihre Unternehmensanforderungen einzigartigen Upgrade-Schritte beschrieben werden. Dies sind die Aktualisierungsschritte, die am besten mit Ihrer bestehenden Adobe Analytics-Umgebung und Ihren Customer Journey Analytics-Zielen übereinstimmen.

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
