---
title: Senden von Daten an Adobe Experience Platform beim Migrieren zu Customer Journey Analytics
description: Senden von Daten an Adobe Experience Platform beim Migrieren zu Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '897'
ht-degree: 100%

---

# Schritt 3: Senden von Daten an Adobe Experience Platform beim Upgrade

+++Erweitern Sie diesen Abschnitt, um zu sehen, wo die Informationen auf dieser Seite in den allgemeinen Upgrade-Prozess einzuordnen sind. Stellen Sie sicher, dass alle vorherigen Upgrade-Schritte abgeschlossen sind.

Bevor Sie mit diesem Abschnitt fortfahren, stellen Sie zunächst sicher, dass Sie alle vorherigen Upgrade-Aufgaben abgeschlossen haben.

Die Informationen auf dieser Seite beziehen sich auf Schritt 3 des Upgrades, wie in der folgenden Tabelle hervorgehoben:

| Upgrade-Aufgabe | Details |
|---------|----------|
| **Schritt 1: [Erste Schritte beim Upgrade](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Erfahren Sie mehr über die Vorteile des Upgrades auf Customer Journey Analytics und den grundlegenden Upgrade-Prozess. |
| **Schritt 2: [Auswählen des Upgrade-Pfads](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Für das Upgrade auf Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie je nach aktueller Adobe Analytics-Umgebung und den langfristigen Zielen Ihrer Organisation die für Ihre Organisation am besten geeignete Methode aus. |
| <span class="preview">**Schritt 3: Senden von Daten an Adobe Experience Platform**</span> | <span class="preview">Der Prozess zum Senden von Daten an Adobe Experience Platform richtet sich nach dem in Schritt 2 ausgewählten Upgrade-Pfad.</span> |
| **Schritt 4: [Beibehalten historischer Daten](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | Die meisten Organisationen müssen ihre historischen Adobe Analytics-Daten über einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung. |
| **Schritt 5: [Durchführen zusätzlicher Implementierungsaufgaben](/help/getting-started/cja-getting-started.md)** | An dieser Stelle im Upgrade-Prozess müssen Sie verschiedene Aufgaben ausführen, bevor Ihre Customer Journey Analytics-Umgebung einsatzbereit ist.<p>Diese zusätzlichen Aufgaben gelten für Upgrades von Adobe Analytics sowie für neue Customer Journey Analytics-Implementierungen.</p><p>Zu diesen Aufgaben zählen:</p><ul><li>Erfassen von Daten in Experience Platform</li><li>Erstellen von Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics</li><li>Erstellen von Datenansichten</li><li>Portieren der Reporting-API-Nutzung</li><li>Abrechnung für Daten-Feeds und Data Warehouse</li><li>Migrieren von Projekten und Komponenten</li><li>Planen des Benutzer-Onboardings</li></ul> <p>Weitere Informationen finden Sie unter [Customer Journey Analytics – Erste Schritte](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>Die Informationen auf dieser Seite werden durch die folgenden, umfassenderen Upgrade-Informationen ersetzt: <ul><li>**Empfohlene Upgrade-Schritte**<p>Weitere Informationen finden Sie unter [Empfohlener Pfad für das Upgrade von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Leitfaden für das Upgrade auf Customer Journey Analytics**<p>Es ist ein neuer Upgrade-Leitfaden verfügbar, in dem dynamisch Upgrade-Schritte generiert werden, die auf Ihre Organisation und Ihre individuellen Bedingungen zugeschnitten sind.</p><p>Um über Customer Journey Analytics auf den Leitfaden zuzugreifen, wählen Sie die Registerkarte **[!UICONTROL Arbeitsbereich]** und dann im linken Panel die Option **[!UICONTROL Upgrade auf Customer Journey Analytics]** aus. Befolgen Sie die Anweisungen auf dem Bildschirm.</p></li></ul>

Nach [Auswahl des Upgrade-Pfads](/help/getting-started/cja-upgrade/cja-upgrade-path.md), der für Ihre Organisation am besten geeignet ist, können Sie Daten an Adobe Experience Platform senden, um sie in Customer Journey Analytics verfügbar zu machen.

Der Prozess zum Senden von Daten an Experience Platform für jeden Upgrade-Pfad ist unten dargestellt. Ausführliche Konfigurationsinformationen finden Sie über die Links in der Tabelle.

| Upgrade-Pfad | Prozess zum Senden von Daten an Platform | Zusätzliche Informationen |
|---------|----------|----------|
| Neue Implementierung des Experience Platform Web SDK | <ol><li>Erstellen Sie ein XDM-Schema für Ihre Organisation.<p>Arbeiten Sie mit Ihrem Daten-Team zusammen, um das ideale Customer Journey Analytics-Schema-Design für Ihre Organisation zu bestimmen.</p></li><li>Implementieren Sie das Experience Platform Web SDK.</li><li>Senden Sie Daten an Platform.</li></ol><p>Ausführliche Informationen zu den einzelnen Schritten finden Sie unter [Aufnehmen von Daten über das Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md). | Da es sich um eine neue Experience Platform Web SDK-Implementierung handelt, ist keine Schemazuordnung erforderlich, da Sie das Schema als einen der ersten Schritte während der Implementierung erstellen müssen. |
| Migrieren der Adobe Analytics-Implementierung zur Web SDK-Verwendung | <ol><li>Verschieben Sie Ihre vorhandene Adobe Analytics-Implementierung in das Experience Platform Web SDK und überprüfen Sie dann, ob alles in Adobe Analytics funktioniert.<p>Informationen dazu erhalten Sie je nach aktueller Implementierung (Analytics-Tag-Erweiterung oder AppMeasurement) wie folgt:</p><ul><li>Wenn Sie die Analytics-Tag-Erweiterung verwenden, lesen Sie [Migrieren von der Adobe Analytics-Tag-Erweiterung zur Web SDK-Tag-Erweiterung](https://experienceleague.adobe.com/de/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</li><li>Wenn Sie AppMeasurement verwenden, lesen Sie [Migrieren von AppMeasurement zum Web SDK](https://experienceleague.adobe.com/de/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)</li></ul><li>[Erstellen Sie ein XDM-Schema für Ihre Organisation](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Arbeiten Sie mit Ihrem Daten-Team zusammen, um das ideale Customer Journey Analytics-Schema-Design für Ihre Organisation zu bestimmen.</p></li><li>[Verwenden Sie die Datenvorbereitung, um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen](https://experienceleague.adobe.com/de/docs/experience-platform/data-prep/home).</li><li>Senden Sie Daten an Platform, indem Sie einen [Datastream einrichten](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).</li></ol> |  |
| Konfigurieren der vorhandenen Adobe Analytics Web-SDK-Implementierung zum Senden von Daten an Platform | <ol><li>Senden Sie Daten an Platform, indem Sie einen [Datastream einrichten](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream).<p>Da Ihre Adobe Analytics-Implementierung bereits das Experience Platform Web SDK verwendet, können Sie die anderen Abschnitte unter [Aufnehmen von Daten über das Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) ignorieren.</p><p>Wenn Sie bereits Daten mit Ihrer Adobe Analytics-Implementierung an Platform senden, ist dieser Schritt nicht erforderlich. Sie müssen lediglich eine Verbindung zwischen Platform-Datensätzen und Customer Journey Analytics herstellen, wie weiter unten in diesem Prozess beschrieben.</p></li><li>(Optional) [Erstellen Sie ein XDM-Schema für Ihre Organisation](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Arbeiten Sie mit Ihrem Daten-Team zusammen, um das ideale Customer Journey Analytics-Schema-Design für Ihre Organisation zu bestimmen.</p><p>Hinweis: Informationen zu den Vorteilen, die mit der Erstellung eines XDM-Schemas verbunden sind, finden Sie unter [Auswählen Ihres Schemas](/help/getting-started/cja-upgrade/cja-upgrade-path.md#choose-your-schema).</li><li>(Bedingt) Wenn Sie ein XDM-Schema erstellt haben, [verwenden Sie die Datenvorbereitung, um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen](https://experienceleague.adobe.com/de/docs/experience-platform/data-prep/home).</li></ol> |  |
| Verwenden des Analytics-Quell-Connectors | [Aufnehmen und Verwenden von Daten aus Adobe Analytics](/help/data-ingestion/analytics.md) | Adobe Analytics-Daten werden automatisch dem XDM-Schema zugeordnet, wenn Sie den Analytics-Quell-Connector verwenden. Es ist keine weitere Zuordnung erforderlich. |

## Der nächste Schritt – Beibehalten historischer Daten

Legen Sie als Nächstes fest, wie Sie [historische Adobe Analytics-Daten beibehalten](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md).
