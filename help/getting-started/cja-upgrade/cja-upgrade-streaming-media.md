---
title: Einrichten der Streaming-Mediensammlung für Customer Journey Analytics
description: Erfahren Sie, wie Sie die Streaming Media Collection für Customer Journey Analytics einrichten
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: b807099d-a61d-48f9-9fec-94ecc6b76213
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 20%

---

# Einrichten der Streaming-Mediensammlung für Customer Journey Analytics {#streaming-media-setup}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-media-edge"
>title="Einrichten und Implementieren von Media Edge"
>abstract="Wenn Sie die Streaming-Mediensammlung mit Customer Journey Analytics verwenden möchten, müssen Sie an bestimmten Stellen des Aktualisierungsprozesses bestimmte Auswahlen treffen. Sie müssen beispielsweise die Feldergruppe „Details zu Medienanalyse-Interaktionen“ zu Ihrem Schema hinzufügen, die Medienanalyse im Datenstrom aktivieren und vieles mehr."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Wie in Adobe Analytics kann die Streaming Media Collection verwendet werden, um Streaming-Mediendaten zur Verwendung in Customer Journey Analytics zu erfassen. Wenn Sie die Streaming-Mediensammlung mit Adobe Analytics verwenden, sollten Sie sie in Ihre Aktualisierungspläne für Customer Journey Analytics aufnehmen.

Wenn Sie mit der Aktualisierung von Adobe Analytics auf Customer Journey Analytics beginnen, wählen Sie die folgenden Elemente aus, um die Daten der Streaming-Mediensammlung zu berücksichtigen:

* Schließen Sie beim Erstellen des Schemas für Customer Journey Analytics die `MediaAnalytics Interaction Details` Feldergruppe ein.

  Weitere Informationen zum Hinzufügen dieser Feldergruppe finden Sie unter [Einrichten des Schemas in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) im Handbuch zur Streaming-Mediensammlung.

  Informationen zum Erstellen des Schemas finden Sie unter [Erstellen eines benutzerdefinierten Schemas zur Verwendung mit Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

* Aktivieren Sie beim Konfigurieren des Datenstroms für Customer Journey Analytics Media Analytics.

  Weitere Informationen zur Aktivierung dieser Option finden Sie unter [Konfigurieren eines Datenstroms in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) im Handbuch zur Streaming-Mediensammlung.

  Weitere Informationen zum Erstellen des Datenstroms finden Sie unter [Erstellen eines Datenstroms zur Verwendung mit Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

  >[!NOTE]
  >
  >Wenn Ihre Adobe Analytics-Implementierung bereits die Experience Platform Web SDK verwendet, ist dieser Schritt nicht erforderlich.

* Schließen Sie beim Erstellen einer Datenansicht für Customer Journey Analytics die erforderlichen Schemafelder für die Streaming-Mediensammlung ein.

  Stellen Sie sicher, dass Sie diese Schemafelder den richtigen Werten im XDM-Objekt zuordnen.

  Weitere Informationen zu den erforderlichen Feldern finden Sie unter [Erstellen einer Datenansicht in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) im Handbuch zur Streaming-Mediensammlung.

  Weitere Informationen zum Erstellen der Datenansicht finden Sie unter [Erstellen einer Datenansicht in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

<!--

------------------

The steps for implementing the Streaming Media Collection in Customer Journey Analytics differ depending on your current Streaming Media Collection implementation in Adobe Analytics. 

Streaming Media Collection can be implemented in Adobe Analytics in either of the following ways:

* [Edge Network implementations for the Streaming Media Collection](#edge-network-implementations)

* [Adobe Analytics-only implementations for the Streaming Media Collection](#adobe-analytics-only-implementations)

For more information about the differences between these implementation methods, see [Implement the Streaming Media Collection](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview) in the Streaming Media Collection Guide.

## Edge Network implementations for the Streaming Media Collection

If the Streaming Media Collection is [implemented using the Edge Network in your Adobe Analytics implementation](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#edge-implementation-methods), this means that some steps that are required to upgrade the Streaming Media Collection to Customer Journey Analytics have already been completed as part of your Adobe Analytics implementation. Following are the completed steps:

* [Set up the schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)

* [Create a dataset in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#create-a-dataset-in-adobe-experience-platform)

* [Configure a datastream in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)

The following additional steps need to be completed as part of the upgrade to Customer Journey Analytics:

>[!NOTE]
>
>As you complete the Customer Journey Analytics upgrade steps, make sure you use the schema, dataset, and datastream from your Streaming Media Collection implementation in Adobe Analytics.

* [Create a connection in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)

* [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)


## Adobe Analytics-only implementations for the Streaming Media Collection

If the Streaming Media Collection is [implemented using an Adobe Analytics-only implementation in your Adobe Analytics environment](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#adobe-analytics-only-implementation-methods), this means that Streaming Media data is not yet going to Edge Network. 

As you create the schema, dataset, datastream, connection, and data view as part of your upgrade from Adobe Analytics to Customer Journey Analytics, make the following selections to account for Streaming Media Collection data:

* When creating the schema for Customer Journey Analytics, include the `MediaAnalytics Interaction Details` field group.

  For more information about adding this field group, see [Set up the schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) in the Streaming Media Collection Guide.

  For information about creating the schema, see [Create a custom schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

* When configuring the datastream for Customer Journey Analytics, enable Media Analytics. 

  For more information about enabling this option, see [Configure a datastream in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) in the Streaming Media Collection Guide.

  For information about creating the datastream, see [Create a datastream to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

* When creating a data view for Customer Journey Analytics, include the required schema fields for the Streaming Media Collection.

  Make sure you map these schema fieldds to the correct values in the XDM object.

  For more information about the required fields, see [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) in the Streaming Media Collection Guide.

  For information about creating the data view, see [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

  -->
