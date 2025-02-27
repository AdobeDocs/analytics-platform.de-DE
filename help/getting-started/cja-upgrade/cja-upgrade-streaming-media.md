---
title: Einrichten der Streaming-Mediensammlung für Customer Journey Analytics
description: Erfahren Sie, wie Sie die Streaming Media Collection für Customer Journey Analytics einrichten
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 68ce73ddf805ec377fdb2c539683507f191c9249
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 2%

---

# Einrichten der Streaming-Mediensammlung für Customer Journey Analytics {#streaming-media-setup}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-media-edge"
>title="Einrichten und Implementieren von Media Edge"
>abstract="Sie können die Adobe Streaming Media Collection so konfigurieren, dass Daten mit Experience Platform Edge in Customer Journey Analytics verfügbar gemacht werden."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Die Schritte zum Implementieren der Streaming-Mediensammlung in Customer Journey Analytics unterscheiden sich je nach Ihrer aktuellen Implementierung der Streaming-Mediensammlung in Adobe Analytics.

Die Streaming-Mediensammlung kann auf eine der folgenden Arten in Adobe Analytics implementiert werden:

* [Edge Network-Implementierungen für die Streaming-Mediensammlung](#edge-network-implementations)

+++ Infografik anzeigen

  ![Implementierung von Streaming-Medien in Edge](assets/streaming-media-edge.png)

+++

* [Nur Adobe Analytics-Implementierungen für die Streaming-Mediensammlung](#adobe-analytics-only-implementations)

+++ Infografik anzeigen

  ![Nur Analytics-Implementierung](assets/analytics-implementation.png)

+++

Weitere Informationen zu den Unterschieden zwischen diesen Implementierungsmethoden finden Sie unter [Implementieren der Streaming Media Collection](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview) im Handbuch zur Streaming Media Collection.

## Edge Network-Implementierungen für die Streaming-Mediensammlung

Wenn die Streaming-Mediensammlung mithilfe [ Edge Network in Ihrer Adobe Analytics-Implementierung implementiert wird](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#edge-implementation-methods) bedeutet dies, dass einige Schritte, die zum Aktualisieren der Streaming-Mediensammlung auf Customer Journey Analytics erforderlich sind, im Rahmen Ihrer Adobe Analytics-Implementierung bereits abgeschlossen wurden. Im Folgenden finden Sie die abgeschlossenen Schritte:

* [Einrichten des Schemas in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)

* [Erstellen eines Datensatzes in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#create-a-dataset-in-adobe-experience-platform)

* [Konfigurieren eines Datenstroms in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)

Die folgenden zusätzlichen Schritte müssen im Rahmen des Upgrades auf Customer Journey Analytics ausgeführt werden:

>[!NOTE]
>
>Wenn Sie die Customer Journey Analytics-Upgrade-Schritte abgeschlossen haben, stellen Sie sicher, dass Sie das Schema, den Datensatz und den Datenstrom aus Ihrer Implementierung der Streaming-Mediensammlung in Adobe Analytics verwenden.

* [Erstellen einer Verbindung in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)

* [Erstellen einer Datenansicht in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)


## Nur Adobe Analytics-Implementierungen für die Streaming-Mediensammlung

Wenn die Streaming[Mediensammlung mithilfe einer Adobe Analytics-Implementierung in Ihrer Adobe Analytics-Umgebung implementiert ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#adobe-analytics-only-implementation-methods), bedeutet dies, dass Streaming-Mediendaten noch nicht an Edge Network übermittelt werden.

Wenn Sie das Schema, den Datensatz, den Datenstrom, die Verbindung und die Datenansicht im Rahmen Ihrer Aktualisierung von Adobe Analytics auf Customer Journey Analytics erstellen, treffen Sie die folgenden Auswahlen, um die Daten der Streaming-Mediensammlung zu berücksichtigen:

* Schließen Sie beim Erstellen des Schemas für Customer Journey Analytics die `MediaAnalytics Interaction Details` Feldergruppe ein.

  Weitere Informationen zum Hinzufügen dieser Feldergruppe finden Sie unter [Einrichten des Schemas in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) im Handbuch zur Streaming-Mediensammlung.

  Informationen zum Erstellen des Schemas finden Sie unter [Erstellen eines benutzerdefinierten Schemas zur Verwendung mit Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

* Aktivieren Sie beim Konfigurieren des Datenstroms für Customer Journey Analytics Media Analytics.

  Weitere Informationen zur Aktivierung dieser Option finden Sie unter [Konfigurieren eines Datenstroms in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) im Handbuch zur Streaming-Mediensammlung.

  Weitere Informationen zum Erstellen des Datenstroms finden Sie unter [Erstellen eines Datenstroms zur Verwendung mit Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

* Schließen Sie beim Erstellen einer Datenansicht für Customer Journey Analytics die erforderlichen Schemafelder für die Streaming-Mediensammlung ein.

  Stellen Sie sicher, dass Sie diese Schemafelder den richtigen Werten im XDM-Objekt zuordnen.

  Weitere Informationen zu den erforderlichen Feldern finden Sie unter [Erstellen einer Datenansicht in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) im Handbuch zur Streaming-Mediensammlung.

  Weitere Informationen zum Erstellen der Datenansicht finden Sie unter [Erstellen einer Datenansicht in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).


