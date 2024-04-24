---
title: Benutzereinstieg bei der Migration auf Customer Journey Analytics planen
description: Benutzereinstieg bei der Migration auf Customer Journey Analytics planen
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 34ccab37-a37f-4d69-aa96-ae1047b1f195
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 3%

---

# Schritt 6: Planen des Onboarding von Benutzern bei der Migration zum Customer Journey Analytics

+++ Erweitern Sie diesen Abschnitt, um zu sehen, wo die Informationen auf dieser Seite in den größeren Migrationsprozess passen. Stellen Sie sicher, dass alle vorherigen Migrationsschritte abgeschlossen sind.

Bevor Sie mit diesem Abschnitt fortfahren, stellen Sie zunächst sicher, dass Sie alle vorherigen Migrationsaufgaben abgeschlossen haben.

Die Informationen auf dieser Seite beziehen sich auf Schritt 6, wie in der folgenden Tabelle hervorgehoben:

| Migrationsaufgabe | Details |
|---------|----------|
| **Schritt 1: [Erste Schritte mit der Migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Erfahren Sie mehr über die Vorteile der Migration zu Adobe Analytics und den grundlegenden Migrationsprozess. |
| **Schritt 2: [Migrationspfad auswählen](/help/getting-started/cja-migration/cja-migration-path.md)** | Für die Migration zum Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie je nach aktueller Adobe Analytics-Umgebung und langfristigen Zielen Ihres Unternehmens die für Ihr Unternehmen am besten geeignete Methode aus. |
| **Schritt 3: [Zuordnen von Daten zum XDM-Schema](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM-Schemata](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) werden in Adobe Experience Platform verwendet, um die Datenstruktur konsistent und wiederverwendbar zu beschreiben. Durch die systemübergreifende einheitliche Definition von Daten wird es einfacher, deren Bedeutung beizubehalten und somit Wert aus Daten zu ziehen.<p>Die meisten Migrationspfade erfordern, dass Sie entweder ein neues XDM-Schema erstellen oder Ihr vorhandenes Adobe Analytics-Schema mithilfe der Datastream-Zuordnung XDM zuordnen.</p> |
| **Schritt 4: [Daten an Adobe Experience Platform senden](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Der Prozess zum Senden von Daten an Adobe Experience Platform hängt vom in Schritt 2 ausgewählten Migrationspfad ab. |
| **Schritt 5: [Verlaufsdaten beibehalten](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | Die meisten Unternehmen müssen ihre historischen Adobe Analytics-Daten für einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung. |
| <span class="preview">**Schritt 6: [Benutzereinstieg planen](/help/getting-started/cja-migration/cja-migration-onboarding.md)**</span> | <span class="preview">Sie sollten Ihren Benutzern ausreichend Zeit (3 - 6 Monate) geben, um sich mit den wichtigsten Unterschieden von Analysis Workspace im Customer Journey Analytics vertraut zu machen.</span> |
| **Schritt 7: [Portieren der Nutzung der Reporting-API](/help/getting-started/cja-migration/cja-migration-api.md)** | Die Customer Journey Analytics Reporting-API weist dasselbe Format auf, verwendet jedoch einen anderen Endpunkt. Portieren Sie die Nutzung der Reporting-API von der Adobe Analytics Reporting-API an die Customer Journey Analytics-Reporting-API. |
| **Schritt 8: [Ersetzen von Daten-Feeds und Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Entscheiden Sie, wie Sie die unter Customer Journey Analytics verfügbaren Exportoptionen verwenden werden, um die Daten-Feeds- und Data Warehouse-Funktionen zu ersetzen, die Sie in Adobe Analytics verwendet haben. |
| **Schritt 9: [Migrieren von Projekten und Komponenten](/help/getting-started/cja-migration/cja-migration-projects.md)** | Im Bereich Komponentenmigration in Adobe Analytics können Sie Projekte und die zugehörigen Komponenten von Adobe Analytics auf Customer Journey Analytics migrieren. |

{style="table-layout:auto"}

+++

Es gibt einige wesentliche Unterschiede zwischen Customer Journey Analytics und Adobe Analytics, die die Benutzer kennen müssen.

Wie in Adobe Analytics ist Analysis Workspace das wichtigste Tool für die Benutzer im Customer Journey Analytics. Es gibt jedoch einige wesentliche Unterschiede bei der Verwendung von Analysis Workspace in Customer Journey Analytics, die die Benutzer kennen müssen.

Sie sollten Ihren Benutzern ausreichend Zeit (3 - 6 Monate) geben, um sich mit den wichtigsten Unterschieden von Analysis Workspace im Customer Journey Analytics vertraut zu machen.

Informationen zu einigen der wichtigsten Unterschiede zwischen Adobe Analytics und Customer Journey Analytics finden Sie unter [Benutzerhandbuch für Adobe Analytics-Benutzer](/help/getting-started/aa-to-cja-user.md).

## Als Nächstes portieren Sie die Nutzung der Reporting-API.

Die Customer Journey Analytics Reporting-API weist dasselbe Format auf, verwendet jedoch einen anderen Endpunkt. [Portieren der Nutzung der Reporting-API](/help/getting-started/cja-migration/cja-migration-api.md) von der Adobe Analytics Reporting-API zur Customer Journey Analytics-Reporting-API.
