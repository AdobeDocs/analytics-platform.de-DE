---
title: Aufbewahren historischer Daten bei der Migration auf Customer Journey Analytics
description: Erfahren Sie, wie Sie historische Daten bei der Migration zu Customer Journey Analytics beibehalten können.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: da71e96749093821b49806c5a1bfd2f82ca85dd4
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 2%

---

# Schritt 5: Speichern von historischen Daten bei der Migration zu Customer Journey Analytics

+++ Die Informationen auf dieser Seite sind Teil eines größeren Migrationsprozesses. Erweitern Sie diesen Abschnitt, um zu sehen, wo diese Informationen zum Migrationsprozess passen. </br></br>Sie müssen alle vorherigen Migrationsschritte ausführen, bevor Sie mit den Informationen auf dieser Seite fortfahren.

Bevor Sie mit diesem Abschnitt fortfahren, stellen Sie zunächst sicher, dass Sie alle vorherigen Migrationsaufgaben abgeschlossen haben.

Die Informationen auf dieser Seite beziehen sich auf Schritt 5, wie in der folgenden Tabelle hervorgehoben:

| Migrationsaufgabe | Details |
|---------|----------|
| **Schritt 1: [Erste Schritte mit der Migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Erfahren Sie mehr über die Vorteile der Migration zu Adobe Analytics und den grundlegenden Migrationsprozess. |
| **Schritt 2: [Migrationsmethode auswählen](/help/getting-started/cja-migration/cja-migration-method.md)** | Für die Migration zum Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie je nach aktueller Adobe Analytics-Umgebung und langfristigen Zielen Ihres Unternehmens die für Ihr Unternehmen am besten geeignete Methode aus. |
| **Schritt 3: [Daten an Adobe Experience Platform senden](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Der Prozess zum Senden von Daten an Adobe Experience Platform hängt von der in Schritt 1 ausgewählten Migrationsmethode ab. |
| **Schritt 4: [Planen der Datenzuordnung zum XDM-Schema](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM-Schemata](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) werden in Adobe Experience Platform verwendet, um die Datenstruktur konsistent und wiederverwendbar zu beschreiben. Durch die systemübergreifende einheitliche Definition von Daten wird es einfacher, deren Bedeutung beizubehalten und somit Wert aus Daten zu ziehen.<p>Die meisten Migrationsmethoden erfordern, dass Sie entweder ein neues XDM-Schema erstellen oder Ihr bestehendes Adobe Analytics-Schema mithilfe der Datastream-Zuordnung XDM zuordnen.</p> |
| <span class="preview">**Schritt 5: [Verlaufsdaten beibehalten](/help/getting-started/cja-migration/cja-migration-historical-data.md)**</span> | <span class="preview">Die meisten Unternehmen müssen ihre historischen Adobe Analytics-Daten für einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung.</span> |
| **Schritt 6: [Benutzereinstieg planen](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Sie sollten Ihren Benutzern ausreichend Zeit (3 - 6 Monate) geben, um sich mit den wichtigsten Unterschieden von Analysis Workspace im Customer Journey Analytics vertraut zu machen. |
| **Schritt 7: [Portieren der Nutzung der Reporting-API](/help/getting-started/cja-migration/cja-migration-api.md)** | Die Customer Journey Analytics Reporting-API weist dasselbe Format auf, verwendet jedoch einen anderen Endpunkt. Portieren Sie die Nutzung der Reporting-API von der Adobe Analytics Reporting-API an die Customer Journey Analytics-Reporting-API. |
| **Schritt 8: [Ersetzen von Daten-Feeds und Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Entscheiden Sie, wie Sie die unter Customer Journey Analytics verfügbaren Exportoptionen verwenden werden, um die Daten-Feeds- und Data Warehouse-Funktionen zu ersetzen, die Sie in Adobe Analytics verwendet haben. |
| **Schritt 9: [Migrieren von Projekten und Komponenten](/help/getting-started/cja-migration/cja-migration-projects.md)** | Im Bereich Komponentenmigration in Adobe Analytics können Sie Projekte und die zugehörigen Komponenten von Adobe Analytics auf Customer Journey Analytics migrieren. |

{style="table-layout:auto"}

+++

Wählen Sie eine der folgenden Optionen, um beim Wechsel von Adobe Analytics zu Customer Journey Analytics historische Daten beizubehalten:

## Analytics Source Connector verwenden

Sie können die [Analytics Source Connector](/help/data-ingestion/analytics.md) , um historische Daten beizubehalten. Unabhängig von der gewählten Migrationsmethode (auch wenn Sie mit dem Web SDK migrieren) können Sie den Analytics Source Connector verwenden, um historische Daten aus Ihrer Adobe Analytics-Umgebung beizubehalten.

Mit dem Analytics Source Connector können Sie historische Daten auf folgende Weise speichern:

* Bringen Sie historische Daten an eine eigene dedizierte Stelle, die von Ihren aktuellen Daten getrennt ist.

* Ordnen Sie historische Daten so zu, dass Sie sie mit Ihren neuen Daten verknüpfen können. <!-- Possible? Explain -->

## Vorhandene Adobe Analytics-Implementierung verwalten

Sie können Ihre vorhandene Adobe Analytics-Implementierung zusammen mit Ihrer neuen Customer Journey Analytics-Implementierung für einen bestimmten Zeitraum (z. B. 1 Jahr) verwalten. Wenn Sie diese Option wählen, müssen Sie planen, die Adobe Analytics-Implementierung zu deaktivieren, nachdem Sie über ausreichende Daten im Customer Journey Analytics verfügen.

Wenden Sie sich an Ihren Adobe-Kundenbetreuer, um die Preise für diese Option zu ermitteln.

## Planen Sie als Nächstes das Onboarding von Benutzern.

[Benutzereinstieg auf Customer Journey Analytics planen](/help/getting-started/cja-migration/cja-migration-onboarding.md). Sie sollten Ihren Benutzern ausreichend Zeit (3 - 6 Monate) geben, um sich mit den wichtigsten Unterschieden von Analysis Workspace im Customer Journey Analytics vertraut zu machen.
