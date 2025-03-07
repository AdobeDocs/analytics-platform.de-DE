---
title: Senden von Daten an Adobe Experience Platform beim Migrieren zu Customer Journey Analytics
description: Senden von Daten an Adobe Experience Platform beim Migrieren zu Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 765b6863cdafa06b54b76fbf0983afb4c14c21d4
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 58%

---

# Schritt 3: Senden von Daten an Adobe Experience Platform beim Upgrade

+++Erweitern Sie diesen Abschnitt, um zu sehen, wo die Informationen auf dieser Seite in den größeren Aktualisierungsprozess passen. Stellen Sie sicher, dass alle vorherigen Upgrade-Schritte abgeschlossen sind.

Bevor Sie mit diesem Abschnitt fortfahren, vergewissern Sie sich zunächst, dass Sie alle vorherigen Upgrade-Aufgaben abgeschlossen haben.

Die Informationen auf dieser Seite decken Schritt 3 des Upgrade-Prozesses ab, wie in der folgenden Tabelle hervorgehoben:

| Upgrade-Aufgabe | Details |
|---------|----------|
| **Schritt 1: [Erste Schritte mit dem Upgrade](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Erfahren Sie mehr über die Vorteile eines Upgrades auf Customer Journey Analytics und den grundlegenden Upgrade-Prozess. |
| **Schritt 2: [Wählen Sie den Aktualisierungspfad](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Beim Upgrade auf Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie je nach aktueller Adobe Analytics-Umgebung und den langfristigen Zielen Ihrer Organisation die für Ihre Organisation am besten geeignete Methode aus. |
| <span class="preview">**Schritt 3: Senden von Daten an Adobe Experience Platform**</span> | <span class="preview">Der Prozess zum Senden von Daten an Adobe Experience Platform unterscheidet sich je nach dem in Schritt 2 ausgewählten Aktualisierungspfad.</span> |
| **Schritt 4: [Beibehalten historischer Daten](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | Die meisten Organisationen müssen ihre historischen Adobe Analytics-Daten über einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung. |
| **Schritt 5: [Durchführen zusätzlicher Implementierungsaufgaben](/help/getting-started/cja-getting-started.md)** | An dieser Stelle des Upgrade-Prozesses müssen Sie verschiedene Aufgaben ausführen, bevor Ihre Customer Journey Analytics-Umgebung einsatzbereit ist.<p>Diese zusätzlichen Aufgaben gelten für Upgrades von Adobe Analytics sowie neue Customer Journey Analytics-Implementierungen.</p><p>Zu diesen Aufgaben zählen:</p><ul><li>Erfassen von Daten in Experience Platform</li><li>Erstellen von Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics</li><li>Erstellen von Datenansichten</li><li>Portieren der Reporting-API-Nutzung</li><li>Abrechnung für Daten-Feeds und Data Warehouse</li><li>Migrieren von Projekten und Komponenten</li><li>Planen des Benutzer-Onboardings</li></ul> <p>Weitere Informationen finden Sie unter [Customer Journey Analytics – Erste Schritte](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>Die Informationen auf dieser Seite werden durch die folgenden umfassenderen Upgrade-Informationen ersetzt: <ul><li>**Empfohlene Upgrade-Schritte**<p>Detaillierte Informationen finden Sie unter [Empfohlener Pfad beim Upgrade von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Customer Journey Analytics-Aktualisierungshandbuch**<p>Es ist ein neues Upgrade-Handbuch verfügbar, in dem dynamisch Upgrade-Schritte generiert werden, die für Ihr Unternehmen und Ihre individuellen Bedingungen maßgeschneidert sind.</p><p>Um über Customer Journey Analytics auf das Handbuch zuzugreifen, wählen Sie die Registerkarte **[!UICONTROL Workspace]** und dann **[!UICONTROL Upgrade auf Customer Journey Analytics]** im linken Bereich aus. Befolgen Sie die Anweisungen auf dem Bildschirm.</p></li></ul>

Nachdem Sie [den für Ihr ](/help/getting-started/cja-upgrade/cja-upgrade-path.md) optimalen Aktualisierungspfad ausgewählt haben), können Sie mit dem Senden von Daten an Adobe Experience Platform beginnen, um sie in Customer Journey Analytics verfügbar zu machen.

Der Prozess zum Senden von Daten an Experience Platform für jeden Aktualisierungspfad wird unten angezeigt. Ausführliche Konfigurationsinformationen finden Sie über die Links in der Tabelle.

| Aktualisierungspfad | Prozess zum Senden von Daten an Platform | Zusätzliche Informationen |
|---------|----------|----------|
| Neue Implementierung des Experience Platform Web SDK | <ol><li>Erstellen Sie ein XDM-Schema für Ihre Organisation.<p>Arbeiten Sie mit Ihrem Daten-Team zusammen, um das ideale Customer Journey Analytics-Schema-Design für Ihre Organisation zu bestimmen.</p></li><li>Implementieren Sie das Experience Platform Web SDK.</li><li>Senden Sie Daten an Platform.</li></ol><p>Ausführliche Informationen zu den einzelnen Schritten finden Sie unter [Aufnehmen von Daten über das Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md). | Da es sich um eine neue Experience Platform Web SDK-Implementierung handelt, ist keine Schemazuordnung erforderlich, da Sie das Schema als einen der ersten Schritte während der Implementierung erstellen müssen. |
| Migrieren der Adobe Analytics-Implementierung zur Web SDK-Verwendung | <ol><li>Verschieben Sie Ihre vorhandene Adobe Analytics-Implementierung in das Experience Platform Web SDK und überprüfen Sie dann, ob alles in Adobe Analytics funktioniert.<p>Informationen dazu erhalten Sie je nach aktueller Implementierung (Analytics-Tag-Erweiterung oder AppMeasurement) wie folgt:</p><ul><li>Wenn Sie die Analytics-Tag-Erweiterung verwenden, lesen Sie [Migrieren von der Adobe Analytics-Tag-Erweiterung zur Web SDK-Tag-Erweiterung](https://experienceleague.adobe.com/de/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</li><li>Wenn Sie AppMeasurement verwenden, lesen Sie [Migrieren von AppMeasurement zum Web SDK](https://experienceleague.adobe.com/de/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)</li></ul><li>[Erstellen Sie ein XDM-Schema für Ihre Organisation](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Arbeiten Sie mit Ihrem Daten-Team zusammen, um das ideale Customer Journey Analytics-Schema-Design für Ihre Organisation zu bestimmen.</p></li><li>[Verwenden Sie die Datenvorbereitung, um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen](https://experienceleague.adobe.com/de/docs/experience-platform/data-prep/home).</li><li>Senden Sie Daten an Platform, indem Sie einen [Datastream einrichten](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).</li></ol> |  |
| Konfigurieren Sie Ihre bestehende Adobe Analytics Web SDK-Implementierung, um Daten an Platform zu senden | <ol><li>Senden Sie Daten an Platform, indem Sie einen [Datastream einrichten](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream).<p>Da Ihre Adobe Analytics-Implementierung bereits das Experience Platform Web SDK verwendet, können Sie die anderen Abschnitte unter [Aufnehmen von Daten über das Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) ignorieren.</p><p>Wenn Sie bereits Daten mit Ihrer Adobe Analytics-Implementierung an Platform senden, ist dieser Schritt nicht erforderlich. Sie müssen lediglich eine Verbindung zwischen Platform-Datensätzen und Customer Journey Analytics herstellen, wie weiter unten in diesem Prozess beschrieben.</p></li><li>(Optional) [Erstellen Sie ein XDM-Schema für Ihre Organisation](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Arbeiten Sie mit Ihrem Daten-Team zusammen, um das ideale Customer Journey Analytics-Schema-Design für Ihre Organisation zu bestimmen.</p><p>Hinweis: Informationen zu den Vorteilen, die mit der Erstellung eines XDM-Schemas verbunden sind, finden Sie unter [Auswählen Ihres Schemas](/help/getting-started/cja-upgrade/cja-upgrade-path.md#choose-your-schema).</li><li>(Bedingt) Wenn Sie ein XDM-Schema erstellt haben, [verwenden Sie die Datenvorbereitung, um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen](https://experienceleague.adobe.com/de/docs/experience-platform/data-prep/home).</li></ol> |  |
| Verwenden des Analytics-Quell-Connectors | [Aufnehmen und Verwenden von Daten aus Adobe Analytics](/help/data-ingestion/analytics.md) | Adobe Analytics-Daten werden bei Verwendung des Analytics-Quell-Connectors automatisch dem XDM-Schema zugeordnet. Es ist keine weitere Zuordnung erforderlich. |

## Der nächste Schritt – Beibehalten historischer Daten

Legen Sie als Nächstes fest, wie Sie [historische Adobe Analytics-Daten beibehalten](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md).
