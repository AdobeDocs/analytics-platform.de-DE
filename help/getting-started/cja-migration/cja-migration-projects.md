---
title: Migrieren von Projekten und Komponenten zum Customer Journey Analytics
description: Erfahren Sie mehr über die Komponentenmigration für die Migration von Projekten und Komponenten zu Customer Journey Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 6e5c3ecf-6eba-4dfa-8bf2-e43d56cfc65f
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 14%

---

# Schritt 9: Migrieren von Projekten und Komponenten zum Customer Journey Analytics

+++ Erweitern Sie diesen Abschnitt, um zu sehen, wo die Informationen auf dieser Seite in den größeren Migrationsprozess passen. Stellen Sie sicher, dass alle vorherigen Migrationsschritte abgeschlossen sind.

Bevor Sie mit diesem Abschnitt fortfahren, stellen Sie zunächst sicher, dass Sie alle vorherigen Migrationsaufgaben abgeschlossen haben.

Die Informationen auf dieser Seite beziehen sich auf Schritt 9, wie in der folgenden Tabelle hervorgehoben:

| Migrationsaufgabe | Details |
|---------|----------|
| **Schritt 1: [Erste Schritte mit der Migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Erfahren Sie mehr über die Vorteile der Migration zu Adobe Analytics und den grundlegenden Migrationsprozess. |
| **Schritt 2: [Migrationspfad auswählen](/help/getting-started/cja-migration/cja-migration-path.md)** | Für die Migration zum Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie je nach aktueller Adobe Analytics-Umgebung und langfristigen Zielen Ihres Unternehmens die für Ihr Unternehmen am besten geeignete Methode aus. |
| **Schritt 3: [Zuordnen von Daten zum XDM-Schema](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM-Schemata](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) werden in Adobe Experience Platform verwendet, um die Datenstruktur konsistent und wiederverwendbar zu beschreiben. Durch die systemübergreifende einheitliche Definition von Daten wird es einfacher, deren Bedeutung beizubehalten und somit Wert aus Daten zu ziehen.<p>Die meisten Migrationspfade erfordern, dass Sie entweder ein neues XDM-Schema erstellen oder Ihr vorhandenes Adobe Analytics-Schema mithilfe der Datastream-Zuordnung XDM zuordnen.</p> |
| **Schritt 4: [Daten an Adobe Experience Platform senden](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Der Prozess zum Senden von Daten an Adobe Experience Platform hängt vom in Schritt 2 ausgewählten Migrationspfad ab. |
| **Schritt 5: [Verlaufsdaten beibehalten](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | Die meisten Unternehmen müssen ihre historischen Adobe Analytics-Daten für einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung. |
| **Schritt 6: [Benutzereinstieg planen](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Sie sollten Ihren Benutzern ausreichend Zeit (3 - 6 Monate) geben, um sich mit den wichtigsten Unterschieden von Analysis Workspace im Customer Journey Analytics vertraut zu machen. |
| **Schritt 7: [Portieren der Nutzung der Reporting-API](/help/getting-started/cja-migration/cja-migration-api.md)** | Die Customer Journey Analytics Reporting-API weist dasselbe Format auf, verwendet jedoch einen anderen Endpunkt. Portieren Sie die Nutzung der Reporting-API von der Adobe Analytics Reporting-API an die Customer Journey Analytics-Reporting-API. |
| **Schritt 8: [Ersetzen von Daten-Feeds und Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Entscheiden Sie, wie Sie die unter Customer Journey Analytics verfügbaren Exportoptionen verwenden werden, um die Daten-Feeds- und Data Warehouse-Funktionen zu ersetzen, die Sie in Adobe Analytics verwendet haben. |
| <span class="preview">**Schritt 9: [Migrieren von Projekten und Komponenten](/help/getting-started/cja-migration/cja-migration-projects.md)**</span> | <span class="preview">Im Bereich Komponentenmigration in Adobe Analytics können Sie Projekte und die zugehörigen Komponenten von Adobe Analytics auf Customer Journey Analytics migrieren.</span> |
| **Schritt 10: [Ausführen von Aufgaben nach der Migration](/help/getting-started/cja-getting-started.md)** | Nachdem Sie die Migration abgeschlossen haben, müssen Sie verschiedene Aufgaben ausführen, darunter das Einbringen weiterer Daten in das Experience Platform, das Erstellen von Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics, das Erstellen von Datenansichten und das Erlernen des Berichts über kanalübergreifende Daten in Analysis Workspace. |

{style="table-layout:auto"}

+++

Im Bereich Komponentenmigration in Adobe Analytics können Sie Projekte und die zugehörigen Komponenten von Adobe Analytics auf Customer Journey Analytics migrieren.

Der Migrationsvorgang umfasst:

* Neuerstellung von Adobe Analytics-Projekten in Customer Journey Analytics.

* Zuordnung von Dimensionen und Metriken aus Adobe Analytics-Report Suites zu Dimensionen und Metriken in Customer Journey Analytics-Datenansichten.

Bevor Sie mit der Migration beginnen, sollten Sie zunächst die [Migration von Komponenten und Projekten von Adobe Analytics zu Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=de) vorbereiten.

Nachdem Sie alle notwendigen Vorbereitungen getroffen haben, können Sie [Komponenten und Projekte von Adobe Analytics zu Customer Journey Analytics migrieren](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html?lang=de).

## Führen Sie als Nächstes nach der Migration Aufgaben aus.

Nach [Migrieren von Komponenten und Projekten von Adobe Analytics zum Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html?lang=de)müssen Sie verschiedene Aufgaben ausführen, um die Einrichtung Ihrer Customer Journey Analytics-Umgebung abzuschließen. Dazu gehören das Einbringen anderer Daten in das Experience Platform, das Erstellen von Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics, das Erstellen von Datenansichten und das Erlernen der Berichterstellung über kanalübergreifende Daten in Analysis Workspace.

Weitere Informationen zu diesen Migrationsaufgaben finden Sie unter [Customer Journey Analytics - Erste Schritte](/help/getting-started/cja-getting-started.md).
