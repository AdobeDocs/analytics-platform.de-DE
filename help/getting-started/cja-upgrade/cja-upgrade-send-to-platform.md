---
title: Senden von Daten an Adobe Experience Platform bei der Migration auf Customer Journey Analytics
description: Senden von Daten an Adobe Experience Platform bei der Migration auf Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: c64f7a1676f4fd3712e618e26357f430e7d9f019
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 1%

---

# Schritt 3: Senden von Daten an Adobe Experience Platform beim Upgrade

+++ Erweitern Sie diesen Abschnitt, um zu sehen, wo die Informationen auf dieser Seite in den größeren Aktualisierungsprozess passen. Stellen Sie sicher, dass alle vorherigen Aktualisierungsschritte abgeschlossen sind.

Bevor Sie mit diesem Abschnitt fortfahren, stellen Sie zunächst sicher, dass Sie alle vorherigen Aktualisierungsaufgaben abgeschlossen haben.

Die Informationen auf dieser Seite decken Schritt 3 des Aktualisierungsprozesses ab, wie in der folgenden Tabelle hervorgehoben:

| Aktualisierungsaufgabe | Details |
|---------|----------|
| **Schritt 1: [Erste Schritte mit dem Upgrade](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Erfahren Sie mehr über die Vorteile der Aktualisierung auf Customer Journey Analytics und den grundlegenden Upgrade-Prozess. |
| **Schritt 2: [Aktualisierungspfad auswählen](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Für die Aktualisierung auf Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie je nach aktueller Adobe Analytics-Umgebung und langfristigen Zielen Ihres Unternehmens die für Ihr Unternehmen am besten geeignete Methode aus. |
| <span class="preview">**Schritt 3: Senden von Daten an Adobe Experience Platform**</span> | <span class="preview">Der Prozess zum Senden von Daten an Adobe Experience Platform hängt vom Aktualisierungspfad ab, den Sie in Schritt 2 ausgewählt haben.</span> |
| **Schritt 4: [Verlaufsdaten beibehalten](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | Die meisten Unternehmen müssen ihre historischen Adobe Analytics-Daten für einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung. |
| **Schritt 5: [Zusätzliche Implementierungsaufgaben durchführen](/help/getting-started/cja-getting-started.md)** | An dieser Stelle des Aktualisierungsprozesses müssen Sie verschiedene Aufgaben ausführen, bevor Ihre Customer Journey Analytics-Umgebung verwendet werden kann.<p>Diese zusätzlichen Aufgaben gelten für Aktualisierungen von Adobe Analytics sowie für neue Customer Journey Analytics-Implementierungen.</p><p>Zu diesen Aufgaben gehören:</p><ul><li>Andere Daten in Experience Platform integrieren</li><li>Erstellen von Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics</li><li>Erstellen von Datenansichten</li><li>Portieren der Nutzung der Reporting-API</li><li>Abrechnung von Daten-Feeds und Data Warehouse</li><li>Migrieren von Projekten und Komponenten</li><li>Benutzerintegration planen</li></ul> <p>Weitere Informationen finden Sie unter [Customer Journey Analytics - Erste Schritte](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++


Nach [Aktualisierungspfad auswählen](/help/getting-started/cja-upgrade/cja-upgrade-path.md) Wenn dies für Ihr Unternehmen am besten ist, können Sie mit dem Senden von Daten an Adobe Experience Platform beginnen, um sie in Customer Journey Analytics verfügbar zu machen.

Der Prozess zum Senden von Daten an Experience Platform für jeden Aktualisierungspfad ist unten dargestellt. Detaillierte Konfigurationsinformationen finden Sie unter den Links in der Tabelle.

| Aktualisierungspfad | Prozess zum Senden von Daten an Platform | Zusätzliche Informationen |
|---------|----------|----------|
| Neue Implementierung des Experience Platform Web SDK | <ol><li>Erstellen Sie ein XDM-Schema für Ihre Organisation.<p>Arbeiten Sie mit Ihrem Datenteam zusammen, um das ideale Schema für die Customer Journey Analytics zu ermitteln.</p></li><li>Implementieren Sie das Experience Platform Web SDK.</li><li>Senden von Daten an Platform.</li></ol><p>Detaillierte Informationen zu den einzelnen Schritten finden Sie unter [Daten über das Adobe Experience Platform Web SDK erfassen](/help/data-ingestion/aepwebsdk.md). | Da es sich um eine neue Implementierung des Experience Platform Web SDK handelt, ist keine Schemazuordnung erforderlich, da Sie das Schema als einen der ersten Schritte während der Implementierung erstellen müssen. |
| Migrieren der Adobe Analytics-Implementierung zur Verwendung des Web SDK | <ol><li>Verschieben Sie Ihre vorhandene Adobe Analytics-Implementierung in das Experience Platform Web SDK und überprüfen Sie dann, ob in Adobe Analytics alles funktioniert.<p>Verwenden Sie je nachdem, ob Ihre aktuelle Implementierung die Analytics-Tag-Erweiterung oder -AppMeasurement ist, die folgenden Ressourcen, um Informationen dazu zu erhalten:</p><ul><li>Wenn Sie die Analytics-Tag-Erweiterung verwenden, lesen Sie [Migration von der Adobe Analytics-Tag-Erweiterung zur Web SDK-Tag-Erweiterung](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</li><li>Wenn Sie AppMeasurement verwenden, lesen Sie [Migration von AppMeasurement zum Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)</li></ul><li>[Erstellen eines XDM-Schemas für Ihre Organisation](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Arbeiten Sie mit Ihrem Datenteam zusammen, um das ideale Schema für die Customer Journey Analytics zu ermitteln.</p></li><li>[Verwenden Sie die Datenvorbereitung, um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen.](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).</li><li>Senden von Daten an Platform durch [Einrichten eines Datenspeichers](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).</li></ol> |  |
| Konfigurieren der vorhandenen Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Customer Journey Analytics | <ol><li>Senden von Daten an Platform durch [Einrichten eines Datenspeichers](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).<p>Da Ihre Adobe Analytics-Implementierung bereits das Experience Platform Web SDK verwendet, können Sie die anderen Abschnitte unter [Daten über das Adobe Experience Platform Web SDK erfassen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk).</li><li>(Optional) [Erstellen eines XDM-Schemas für Ihre Organisation](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Arbeiten Sie mit Ihrem Datenteam zusammen, um das ideale Schema für die Customer Journey Analytics zu ermitteln.</p><p>Hinweis: Informationen zu den Vorteilen der Erstellung eines XDM-Schemas finden Sie unter [Schema auswählen](/help/getting-started/cja-upgrade/cja-upgrade-path.md#choose-your-schema).</li><li>(Bedingt) Wenn Sie ein XDM-Schema erstellt haben, [Verwenden Sie die Datenvorbereitung , um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen.](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).</li></ol> |
| Verwenden des Analytics Source Connectors | [Aufnehmen und Verwenden von Daten aus Adobe Analytics](/help/data-ingestion/analytics.md) | Adobe Analytics-Daten werden automatisch dem XDM-Schema zugeordnet, wenn Sie Analytics Source Connector verwenden. Es ist keine zusätzliche Zuordnung erforderlich. |

## Speichern Sie anschließend historische Daten.

Entscheiden Sie als Nächstes, wie Sie [historische Adobe Analytics-Daten beibehalten](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md).