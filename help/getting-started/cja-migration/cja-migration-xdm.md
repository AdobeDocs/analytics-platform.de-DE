---
title: Daten beim Migrieren zu Customer Journey Analytics dem XDM-Schema zuordnen
description: Erfahren Sie, wie Sie beim Migrieren zu Customer Journey Analytics Daten dem XDM-Schema zuordnen
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: da71e96749093821b49806c5a1bfd2f82ca85dd4
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 4%

---

# Schritt 4: Zuordnen von Daten zum XDM-Schema bei der Migration zu Customer Journey Analytics

+++ Die Informationen auf dieser Seite sind Teil eines größeren Migrationsprozesses. Erweitern Sie diesen Abschnitt, um zu sehen, wo diese Informationen zum Migrationsprozess passen. </br></br>Sie müssen alle vorherigen Migrationsschritte ausführen, bevor Sie mit den Informationen auf dieser Seite fortfahren.

Bevor Sie mit diesem Abschnitt fortfahren, stellen Sie zunächst sicher, dass Sie alle vorherigen Migrationsaufgaben abgeschlossen haben.

Die Informationen auf dieser Seite beziehen sich auf Schritt 4, wie in der folgenden Tabelle hervorgehoben:

| Migrationsaufgabe | Details |
|---------|----------|
| **Schritt 1: [Erste Schritte mit der Migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Erfahren Sie mehr über die Vorteile der Migration zu Adobe Analytics und den grundlegenden Migrationsprozess. |
| **Schritt 2: [Migrationsmethode auswählen](/help/getting-started/cja-migration/cja-migration-method.md)** | Für die Migration zum Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie je nach aktueller Adobe Analytics-Umgebung und langfristigen Zielen Ihres Unternehmens die für Ihr Unternehmen am besten geeignete Methode aus. |
| **Schritt 3: [Daten an Adobe Experience Platform senden](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Der Prozess zum Senden von Daten an Adobe Experience Platform hängt von der in Schritt 1 ausgewählten Migrationsmethode ab. |
| <span class="preview">**Schritt 4: [Planen der Datenzuordnung zum XDM-Schema](/help/getting-started/cja-migration/cja-migration-xdm.md)**</span> | <span class="preview">[XDM-Schemata](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) werden in Adobe Experience Platform verwendet, um die Datenstruktur konsistent und wiederverwendbar zu beschreiben. Durch die systemübergreifende einheitliche Definition von Daten wird es einfacher, deren Bedeutung beizubehalten und somit Wert aus Daten zu ziehen.<p>Die meisten Migrationsmethoden erfordern, dass Sie entweder ein neues XDM-Schema erstellen oder Ihr bestehendes Adobe Analytics-Schema mithilfe der Datastream-Zuordnung XDM zuordnen.</p></span> |
| **Schritt 5: [Verlaufsdaten beibehalten](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | Die meisten Unternehmen müssen ihre historischen Adobe Analytics-Daten für einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung. |
| **Schritt 6: [Benutzereinstieg planen](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Sie sollten Ihren Benutzern ausreichend Zeit (3 - 6 Monate) geben, um sich mit den wichtigsten Unterschieden von Analysis Workspace im Customer Journey Analytics vertraut zu machen. |
| **Schritt 7: [Portieren der Nutzung der Reporting-API](/help/getting-started/cja-migration/cja-migration-api.md)** | Die Customer Journey Analytics Reporting-API weist dasselbe Format auf, verwendet jedoch einen anderen Endpunkt. Portieren Sie die Nutzung der Reporting-API von der Adobe Analytics Reporting-API an die Customer Journey Analytics-Reporting-API. |
| **Schritt 8: [Ersetzen von Daten-Feeds und Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Entscheiden Sie, wie Sie die unter Customer Journey Analytics verfügbaren Exportoptionen verwenden werden, um die Daten-Feeds- und Data Warehouse-Funktionen zu ersetzen, die Sie in Adobe Analytics verwendet haben. |
| **Schritt 9: [Migrieren von Projekten und Komponenten](/help/getting-started/cja-migration/cja-migration-projects.md)** | Im Bereich Komponentenmigration in Adobe Analytics können Sie Projekte und die zugehörigen Komponenten von Adobe Analytics auf Customer Journey Analytics migrieren. |

{style="table-layout:auto"}

+++

Die folgende Tabelle zeigt Implementierungsmethoden, die erfordern, dass Sie Daten dem XDM-Schema zuordnen:


| Migrationsmethode | XDM-Zuordnung erforderlich? | Weitere Informationen |
|---------|----------|---------|
| **Neue Implementierung des Web SDK**<p>Die grundlegenden Schritte sind:</p><ol><li>Erstellen eines XDM-Schemas für Ihre Organisation</li><li>Implementieren des Web SDK</li><li>Daten an Platform senden</li></ol> | Nein | Eine Zuordnung ist nicht erforderlich, da Sie bereits [Einrichten eines neuen XDM-Schemas](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) als Teil der neuen Implementierung. |
| **Migrieren der Adobe Analytics-Implementierung zur Verwendung des Web SDK**<p>Die grundlegenden Schritte sind:</p><ol><li>Verschieben Sie Ihre vorhandene Adobe Analytics-Implementierung in das Web SDK und überprüfen Sie, ob dort alles funktioniert.</li><li>Erstellen Sie ein XDM-Schema für Ihre Organisation so, wie Sie Zeit haben.</li><li>Verwenden Sie die Datenstream-Zuordnung, um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen.</li><li>Daten an Platform senden</li></ol> | Ja | Ermitteln Sie in Zusammenarbeit mit Ihrem Datenteam das ideale Schema Ihres Unternehmens für die Customer Journey Analytics und legen Sie fest, wie Sie eVars und Props XDM zuordnen.</br>[Verwenden Sie die Datenvorbereitung, um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen.](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **Konfigurieren der vorhandenen Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Customer Journey Analytics**<p>Die grundlegenden Schritte sind:</p><ol><li>Senden Sie Daten an Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Optional) Erstellen Sie ein XDM-Schema für Ihre Organisation, da Sie Zeit haben.</li><li>Verwenden Sie die Datenstream-Zuordnung, um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen.</li></ol> | Ja | Ermitteln Sie in Zusammenarbeit mit Ihrem Datenteam das ideale Schema Ihres Unternehmens für die Customer Journey Analytics und legen Sie fest, wie Sie eVars und Props XDM zuordnen.</br>[Verwenden Sie die Datenvorbereitung, um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen.](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **Analytics Source Connector**</br> Wenn Ihre Adobe Analytics-Implementierung AppMeasurement oder die Analytics-Erweiterung ist, können Sie mit dem Senden von Daten an eine Datenansicht in Customer Journey Analytics beginnen.<p>Dies ist der einfachste Weg, Daten an Customer Journey Analytics zu übertragen, aber langfristig ist dies die am wenigsten praktikable Methode.</p> | Nein | Eine Zuordnung ist nicht erforderlich, da der Analytics Source Connector dasselbe Adobe Analytics-Schema anstelle des XDM-Schemas verwendet. |

{style="table-layout:auto"}

<!-- Does it benefit the customer to do this all at the same time if they're using multiple AEP apps? If so, have multiple sections like this. Or can they do CJA first and AJO later?

### Plan data mapping for Customer Journey Analytics


### Plan data mapping for Customer Journey analytics and other Adobe Experience platform applications

-->

## Speichern Sie anschließend historische Daten.

Wählen Sie als Nächstes die Methode aus, die Sie verwenden werden, um [historische Adobe Analytics-Daten beibehalten](/help/getting-started/cja-migration/cja-migration-historical-data.md).