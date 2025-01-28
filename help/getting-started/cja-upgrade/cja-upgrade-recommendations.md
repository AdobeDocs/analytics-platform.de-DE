---
title: Empfohlener Pfad beim Upgrade von Adobe Analytics auf Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad beim Upgrade von Adobe Analytics auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: 2d9475c4aa3ca9ba92856182e8c93f59180d833a
workflow-type: tm+mt
source-wordcount: '1587'
ht-degree: 7%

---

# Upgrade von Adobe Analytics auf Customer Journey Analytics

Beim Upgrade von Adobe Analytics auf Customer Journey Analytics folgen Sie den [empfohlenen Upgrade-Schritten](#recommended-upgrade-steps-for-most-organizations). Alternativ können Sie [Upgrade-Schritte dynamisch generieren](#dynamically-generate-upgrade-steps-for-your-organization) für die einzigartigen Umstände Ihres Unternehmens.

## Empfohlene Upgrade-Schritte für die meisten Unternehmen {#upgrade-process}

Das empfohlene Upgrade von Adobe Analytics auf Customer Journey Analytics ist eine neue Implementierung des Experience Platform Web SDK, der bevorzugten Datenerfassungsmethode für Customer Journey Analytics. In Verbindung mit dem Web SDK empfiehlt Adobe außerdem die Verwendung des Analytics-Quell-Connectors, um Sie beim Übergang zum Customer Journey Analytics zu unterstützen. Verwenden Sie den Analytics-Quell-Connector, um historische Adobe Analytics-Daten beizubehalten und einen direkten Datenvergleich durchzuführen.

Nachdem Sie über genügend historische Daten mit der Experience Platform Web SDK verfügen und vollständig zum Customer Journey Analytics übergegangen sind, kann der Analytics-Quell-Connector deaktiviert und die Web SDK ausschließlich verwendet werden.

>[!NOTE]
>
>Wenn die in diesem Abschnitt beschriebenen Upgrade-Schritte für Ihr Unternehmen nicht sinnvoll sind, verwenden Sie den [Adobe Analytics-to-Customer Journey Analytics-Upgrade-Fragebogen](https://gigazelle.github.io/cja-ttv/), um Upgrade-Schritte dynamisch zu generieren, die auf die individuellen Umstände Ihres Unternehmens zugeschnitten sind.

### Empfohlener Upgrade-Prozess auf hoher Ebene {#high-level-upgade-process}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-historical-data"
>title="Historische Daten aus Adobe Analytics"
>abstract="Übertragen Sie Ihre historischen Adobe Analytics Report Suite-Daten in Adobe Experience Platform und Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

1. **Implementieren von Experience Platform Web SDK (für die fortlaufende Datenerfassung)**

   Eine neue Implementierung der Experience Platform Web SDK ist die beste Möglichkeit, Daten für das Customer Journey Analytics zu erfassen. Es bietet die beste Grundlage, um Customer Journey Analytics optimal zu nutzen, da es die leistungsfähigste, unkomplizierteste und zukunftssicherste Methode zur Implementierung von Customer Journey Analytics ist.

   * Leistungsstarkes Reporting und hohe Datenverfügbarkeit, da Adobe Experience Platform für Anwendungsfälle der Echtzeit-Personalisierung entwickelt wurde

   * Sie können die Implementierung für die Adobe Experience Cloud-Datenerfassung zwischen anderen Experience Cloud-Produkten (AJO, RTCDP usw.) konsolidieren.

   * Es besteht keine Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar, Ereignis usw.).

1. **Einrichten des Adobe Analytics-Quell-Connectors (zum Übermitteln historischer Daten)**

   Um einen reibungslosen Übergang zur Verwendung von Experience Platform Web SDK mit Customer Journey Analytics zu erleichtern, empfiehlt Adobe auch die Verwendung des Adobe Analytics-Quell-Connectors. Auf diese Weise können Sie historische Daten beibehalten und Daten aus Ihrer bestehenden Adobe Analytics-Implementierung in Customer Journey Analytics zusammen mit den Daten aus Ihrer neuen Experience Platform Web SDK-Implementierung anzeigen.

   Mit dem Analytics-Quell-Connector können Sie:

   * Übertragen Sie Ihre historischen Adobe Analytics Report Suite-Daten in Adobe Experience Platform und Customer Journey Analytics.

     Sie können den Analytics-Quell-Connector so lange ausführen, wie Sie die historischen Adobe Analytics-Daten beibehalten müssen.

   * Zeigen Sie die Daten an, die mit Ihrer ursprünglichen Adobe Analytics-Implementierung (entweder AppMeasurement, Analytics-Erweiterung oder Web SDK-Erweiterung) in Customer Journey Analytics erfasst wurden. Sie können diese Daten nebeneinander mit denen Ihrer neuen Web SDK-Implementierung vergleichen.

     Sie können den Analytics-Quell-Connector so lange ausführen, bis Sie mit den Unterschieden vertraut sind und sich damit vertraut machen. <!--elaborate on what those differences are? -->

   Der Analytics-Quell-Connector als eigenständige Implementierung ist keine empfohlene langfristige Methode zur Verwendung von Customer Journey Analytics. Dies liegt an der hohen Latenz, überladenen und komplexen Schemata, der Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar usw.) und der Schwierigkeit, schließlich vom Analytics-Quell-Connector zur empfohlenen Web SDK-Implementierung zu wechseln.

### Detaillierte empfohlene Upgrade-Schritte

Die folgenden Schritte beschreiben den empfohlenen Prozess für die Aktualisierung von Adobe Analytics auf Customer Journey Analytics.

Jeder Schritt bietet eine allgemeine Erklärung eines detaillierteren Prozesses. Folgen Sie dem Link für jeden Schritt und führen Sie die zugehörigen Aufgaben aus, kehren Sie dann zu dieser Seite zurück und fahren Sie mit dem nächsten Schritt im Prozess fort.

1. [Planen Sie Ihre XDM-Schemaarchitektur](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Erstellen Sie das gewünschte benutzerdefinierte Schema in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   Beachten Sie beim Erstellen Ihres Schemas die folgenden Optionen:

   * Wenn Sie Customer Journey Analytics mit RTCDP integrieren möchten, müssen Sie die Option **[!UICONTROL Profile]** für Ihr Schema aktivieren, wie in [Erstellen eines XDM-Schemas zur Verwendung mit Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) beschrieben. Wenn diese Option aktiviert ist, werden Daten, die auf Grundlage dieses Schemas in Datensätze aufgenommen werden, mit dem Echtzeit-Kundenprofil zusammengeführt.

   * Wenn Sie Streaming-Mediendaten einbeziehen möchten, müssen Sie [Ihr Schema für die Aufnahme und Verwendung von Streaming-Daten konfigurieren](/help/data-ingestion/streaming.md).

1. [Erstellen eines Datensatzes in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. (Optional) Wenn Sie Klassifizierungsdaten in Adobe Analytics verwenden, können Sie Ihrem Datensatz Klassifizierungsdaten auf Customer Journey Analytics hinzufügen.

   Erstellen Sie dazu [für jede Dimension, die Klassifizierungsdaten enthält, einen ](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Bei Adobe Analytics-Implementierungen mit AppMeasurement oder der Analytics-Erweiterung (Tags) [Erstellen eines Datenstroms in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   Bei Adobe Analytics-Implementierungen mit der Web-SDK ist bereits ein Datenstrom vorhanden.

1. [Fügen Sie Adobe Experience Platform als Service zu Ihrem Datenstrom hinzu](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md).

1. (Optional) Wenn Sie Customer Journey Analytics mit Adobe Journey Optimizer integrieren möchten, verwenden Sie das Personalisierungsobjekt in Ihrer Implementierung zur Verwendung in Adobe Journey Optimizer.

1. Erweitern Sie den Abschnitt, in dem beschrieben wird, wie Sie Experience Platform Web SDK für Ihre Customer Journey Analytics-Implementierung implementieren möchten, und führen Sie dann die entsprechenden Schritte aus:

   +++Manuelle Implementierung (JS-Datei)

   1. [Fügen Sie alloy.js zu Ihrer Site hinzu](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

   1. Füllen Sie ein XDM-Objekt und senden Sie es an den Datenstrom.

+++

   +++Tags

   1. [Erstellen Sie eine Tag-Eigenschaft und fügen Sie die Adobe Experience Platform Web SDK-Erweiterung hinzu](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md).

   1. [Hinzufügen der Adobe Experience Platform Web SDK-Erweiterung zu Ihrer Tag-Eigenschaft](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)

   1. [Implementieren Sie das Lader-Tag auf Ihrer Site](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md).

   1. [Fügen Sie Ihrem Tag eine XDM-Datenerfassungslogik hinzu](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md).

+++

+++ API

   1. Verwenden Sie die Edge Network-API, um Daten an den gewünschten Datenstrom zu senden.

+++

1. [Überprüfen Sie, ob Ihre Web SDK-Implementierung Daten an einen Datensatz sendet](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md).

1. [Erstellen einer Verbindung in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. (Optional) Binden Sie Web-Daten mit Daten aus anderen Kanälen wie Callcenter-Daten.

   Sie erreichen dies, indem Sie zusätzliche Datensätze zu Ihrer Customer Journey Analytics-Verbindung hinzufügen, wie in [Callcenter- und Web-Daten importieren](/help/use-cases/cross-channel/call-center.md) beschrieben.

1. [Erstellen einer Datenansicht auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [Überprüfen Sie, ob Daten auf Customer Journey Analytics in die Datenansicht fließen](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. [Migrieren von Projekten und ](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. (Optional) Wenn Sie Marketing-Kanäle in Adobe Analytics verwenden, können Sie [ein abgeleitetes Feld für den Marketing-Kanal in Customer Journey Analytics erstellen](/help/data-views/derived-fields/derived-fields.md#marketing-channels).

   Abgeleitete Felder sind ein wichtiger Aspekt des Echtzeit-Reportings in Customer Journey Analytics. Mit einem abgeleiteten Feld können Sie mithilfe eines anpassbaren Regel-Builders spontan (häufig komplexe) Datenmanipulationen definieren.

   Eine Verwendung für abgeleitete Felder besteht darin, ein abgeleitetes Marketing-Kanal-Feld zu definieren, das den richtigen Marketing-Kanal basierend auf einer oder mehreren Bedingungen (z. B. URL-Parameter, Seiten-URL oder Seitenname) bestimmt.

   Verwenden Sie [Funktionsvorlage Marketing-Kanäle](/help/data-views/derived-fields/derived-fields.md#marketing-channels) in abgeleiteten Feldern, um schnell ein abgeleitetes Feld für Marketing-Kanäle zu erstellen.

1. Vergleichen Sie Daten in Adobe Analytics aus Ihrer alten Implementierung mit Daten in Customer Journey Analytics aus Ihrer neuen Implementierung und stellen Sie sicher, dass Sie die Unterschiede und ihre Ursachen verstehen. <!-- Expound on this. Link to somewhere? There will be a lot of differences. -->

1. Übertragen von historischen Daten aus Adobe Analytics mithilfe des Analytics-Quell-Connectors:

   >[!NOTE]
   >
   >Führen Sie die folgenden Schritte aus, wenn Sie zuvor noch keinen Analytics-Quell-Connector erstellt haben.
   >
   >Wenn Sie bereits den Analytics-Quell-Connector mit Customer Journey Analytics verwenden, führen Sie die Schritte unter [Übergang vom Analytics-Quell-Connector zum Web SDK für Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md) aus.

   1. [Erstellen eines XDM-Schemas für den Analytics-Quell-Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

   1. Wenn Sie noch keinen Analytics-Quell-Connector haben, erstellen [ den Analytics-Quell-Connector und ordnen Sie Felder Ihrem XDM-Schema zu](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

      Oder

      Wenn Sie bereits über einen Analytics-Quell-Connector verfügen[ ordnen Sie (Felder aus dem Quell-Connector Ihrem XDM-Schema zu](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

   1. [Fügen Sie den Analytics-Quell-Connector-Datensatz zur Verbindung hinzu](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. Onboarding von Benutzern planen.

   Wie in Adobe Analytics ist auch in Customer Journey Analytics der Analysis Workspace das wichtigste Werkzeug für die Benutzenden. Es gibt jedoch einige wesentliche Unterschiede bei der Verwendung von Analysis Workspace in Customer Journey Analytics, die die Benutzenden kennen sollten.

   Sie sollten Ihren Benutzenden ausreichend Zeit (3–6 Monate) geben, um sich mit den wichtigsten Unterschieden von Analysis Workspace in Customer Journey Analytics vertraut zu machen.

   Informationen zu einigen der wichtigsten Unterschiede zwischen Adobe Analytics und Customer Journey Analytics finden Sie im [Benutzerhandbuch für Adobe Analytics-Benutzende](/help/getting-started/aa-to-cja-user.md).

1. Erfahren Sie mehr über [Funktionsunterstützung in Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md). Die meisten Adobe Analytics-Funktionen werden im Customer Journey Analytics unterstützt, und viele zusätzliche Funktionen sind im Customer Journey Analytics verfügbar.

1. [Deaktivieren der AppMeasurement-Datenerfassung](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md) wenn Ihre Web SDK-Implementierung abgeschlossen ist und Sie mit den erfassten Daten vertraut sind.

1. Deaktivieren Sie den Analytics-Quell-Connector , nachdem alle Analytics-Quell-Connector-Daten aus Ihrer Datenaufbewahrungsdauer entfernt wurden.

   Bei der Implementierung von Experience Platform Web SDK wird der Analytics-Quell-Connector nur für historische Adobe Analytics-Daten benötigt und um Daten aus Ihrer ursprünglichen Implementierung mit denen Ihrer neuen Implementierung zu vergleichen.

   Wenn Sie über genügend historische Daten aus Ihrer neuen Implementierung verfügen und mit den Berichtsunterschieden beim Customer Journey Analytics vertraut sind, sollten Sie den Analytics-Quell-Connector deaktivieren.

## Dynamische Generierung von Upgrade-Schritten für Ihre Organisation

Abhängig von verschiedenen Faktoren, wie z. B. Timeline- und Ressourcenbeschränkungen, sind die empfohlenen Upgrade-Schritte, die unter [Grundlegendes zu den empfohlenen Upgrade-Schritten](#1-understand-the-recommended-upgrade-steps) beschrieben werden, möglicherweise für Ihr Unternehmen nicht praktikabel.

So generieren Sie Upgrade-Schritte dynamisch für die individuellen Bedingungen in Ihrem Unternehmen:

1. Füllen Sie den Fragebogen zum Upgrade von [Adobe Analytics auf Customer Journey Analytics aus](https://gigazelle.github.io/cja-ttv/).

   Nach dem Ausfüllen dieses Fragebogens erhalten Sie schrittweise Anleitungen, die die optimalen Upgrade-Schritte für Ihre Unternehmensanforderungen beschreiben. Dies sind die Upgrade-Schritte, die am besten zu Ihrer bestehenden Adobe Analytics-Umgebung und Ihren Customer Journey Analytics-Zielen passen.

1. Folgen Sie den generierten schrittweisen Anweisungen, um das Upgrade auf Customer Journey Analytics durchzuführen.

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
