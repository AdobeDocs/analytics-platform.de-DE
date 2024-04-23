---
title: Senden von Daten an Adobe Experience Platform bei der Migration auf Customer Journey Analytics
description: Senden von Daten an Adobe Experience Platform bei der Migration auf Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 3e362a62d2ffd6d15e3028706e3704264df80222
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 3%

---

# Schritt 3: Senden von Daten an Adobe Experience Platform bei der Migration zu Customer Journey Analytics

+++ Erweitern Sie diesen Abschnitt, um zu sehen, wo die Informationen auf dieser Seite in den größeren Migrationsprozess passen. Stellen Sie sicher, dass alle vorherigen Migrationsschritte abgeschlossen sind.

Bevor Sie mit diesem Abschnitt fortfahren, stellen Sie zunächst sicher, dass Sie alle vorherigen Migrationsaufgaben abgeschlossen haben.

Die Informationen auf dieser Seite beziehen sich auf Schritt 3, wie in der folgenden Tabelle hervorgehoben:

| Migrationsaufgabe | Details |
|---------|----------|
| **Schritt 1: [Erste Schritte mit der Migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Erfahren Sie mehr über die Vorteile der Migration zu Adobe Analytics und den grundlegenden Migrationsprozess. |
| **Schritt 2: [Migrationsmethode auswählen](/help/getting-started/cja-migration/cja-migration-method.md)** | Für die Migration zum Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie je nach aktueller Adobe Analytics-Umgebung und langfristigen Zielen Ihres Unternehmens die für Ihr Unternehmen am besten geeignete Methode aus. |
| <span class="preview">**Schritt 3: [Daten an Adobe Experience Platform senden](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)**</span> | <span class="preview">Der Prozess zum Senden von Daten an Adobe Experience Platform hängt von der in Schritt 1 ausgewählten Migrationsmethode ab.</span> |
| **Schritt 4: [Zuordnen von Daten zum XDM-Schema](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM-Schemata](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) werden in Adobe Experience Platform verwendet, um die Datenstruktur konsistent und wiederverwendbar zu beschreiben. Durch die systemübergreifende einheitliche Definition von Daten wird es einfacher, deren Bedeutung beizubehalten und somit Wert aus Daten zu ziehen.<p>Die meisten Migrationsmethoden erfordern, dass Sie entweder ein neues XDM-Schema erstellen oder Ihr bestehendes Adobe Analytics-Schema mithilfe der Datastream-Zuordnung XDM zuordnen.</p> |
| **Schritt 5: [Verlaufsdaten beibehalten](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | Die meisten Unternehmen müssen ihre historischen Adobe Analytics-Daten für einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung. |
| **Schritt 6: [Benutzereinstieg planen](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Sie sollten Ihren Benutzern ausreichend Zeit (3 - 6 Monate) geben, um sich mit den wichtigsten Unterschieden von Analysis Workspace im Customer Journey Analytics vertraut zu machen. |
| **Schritt 7: [Portieren der Nutzung der Reporting-API](/help/getting-started/cja-migration/cja-migration-api.md)** | Die Customer Journey Analytics Reporting-API weist dasselbe Format auf, verwendet jedoch einen anderen Endpunkt. Portieren Sie die Nutzung der Reporting-API von der Adobe Analytics Reporting-API an die Customer Journey Analytics-Reporting-API. |
| **Schritt 8: [Ersetzen von Daten-Feeds und Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Entscheiden Sie, wie Sie die unter Customer Journey Analytics verfügbaren Exportoptionen verwenden werden, um die Daten-Feeds- und Data Warehouse-Funktionen zu ersetzen, die Sie in Adobe Analytics verwendet haben. |
| **Schritt 9: [Migrieren von Projekten und Komponenten](/help/getting-started/cja-migration/cja-migration-projects.md)** | Im Bereich Komponentenmigration in Adobe Analytics können Sie Projekte und die zugehörigen Komponenten von Adobe Analytics auf Customer Journey Analytics migrieren. |

{style="table-layout:auto"}

+++


Nach [Migrationsmethode auswählen](#step-2-choose-your-customer-journey-analytics-migration-method) Wenn dies für Ihr Unternehmen am besten ist, können Sie mit dem Senden von Daten an Adobe Experience Platform beginnen, um sie in Customer Journey Analytics verfügbar zu machen.

Der Prozess zum Senden von Daten an Experience Platform für jede Migrationsmethode ist unten dargestellt. Weitere Informationen finden Sie unter den unten stehenden Links.

| Migrationsmethode | Prozess zum Senden von Daten an Platform |
|---------|----------|
| Neue Implementierung des Web SDK | Da es sich um eine neue Implementierung des Web SDK handelt, müssen Sie alle Schritte ausführen, die unter [Daten über das Adobe Experience Platform Web SDK erfassen](/help/data-ingestion/aepwebsdk.md). |
| Migrieren der Adobe Analytics-Implementierung zur Verwendung des Web SDK | Die Schritte für die Migration zum Adobe Analytics Web SDK unterscheiden sich je nachdem, ob Ihre aktuelle Implementierung die Analytics-Erweiterung oder AppMeasurement ist. <p>Wenn Sie die Analytics-Tag-Erweiterung verwenden: [Migration von der Adobe Analytics-Tag-Erweiterung zur Web SDK-Tag-Erweiterung](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</p><p>Oder</p><p>Wenn Sie AppMeasurement verwenden: [Migration von AppMeasurement zum Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk) |
| Konfigurieren der vorhandenen Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Customer Journey Analytics | Da Ihre Adobe Analytics-Implementierung bereits das Web-SDK verwendet, müssen Sie nur [Einrichten eines Datenspeichers](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream). Sie können den anderen Abschnitt in [Daten über das Adobe Experience Platform Web SDK erfassen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk). |
| Analytics Source Connector | [Aufnehmen und Verwenden von Daten aus Adobe Analytics](/help/data-ingestion/analytics.md) |

## Zuordnen von Daten zum XDM-Schema

Nachdem Sie Daten durch Befolgen der Links in der obigen Tabelle an Experience Platform gesendet haben, müssen Sie möglicherweise [Zuordnen von Daten zum XDM-Schema](/help/getting-started/cja-migration/cja-migration-xdm.md), abhängig von der gewählten Implementierungsmethode.

Für die folgenden Implementierungsmethoden müssen Sie Daten dem XDM-Schema zuordnen:

* Migration von der Adobe Analytics-Tag-Erweiterung zur Web SDK-Tag-Erweiterung

* Konfigurieren der vorhandenen Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Customer Journey Analytics

Wenn Sie sich für eine neue Implementierung des Web SDK entschieden haben, ist auch keine Zuordnung erforderlich, da Sie bereits [Einrichten eines neuen XDM-Schemas](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) als Teil der neuen Implementierung.

Wenn Sie sich dafür entschieden haben, Analytics Source Connector für Ihre Migration zu verwenden, ist keine Zuordnung erforderlich, da der Analytics Source Connector Ihr vorhandenes Adobe Analytics-Schema anstelle des XDM-Schemas verwendet.
