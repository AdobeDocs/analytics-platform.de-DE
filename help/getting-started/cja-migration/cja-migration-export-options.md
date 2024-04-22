---
title: Ersetzen von Daten-Feeds und Data Warehouse bei der Migration zum Customer Journey Analytics
description: Migration von Adobe Analytics auf Customer Journey Analytics planen
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 3a99aed3-26b9-494f-aaf9-f8eaa2c2d88f
source-git-commit: 21d77f06595993172460b724dc7991cb9a5a02a8
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 4%

---

# Schritt 8: Ersetzen von Daten-Feeds und Data Warehouse bei der Migration zu Customer Journey Analytics

+++ Erweitern Sie diesen Abschnitt, um zu sehen, wo die Informationen auf dieser Seite in den größeren Migrationsprozess passen. Stellen Sie sicher, dass alle vorherigen Migrationsschritte abgeschlossen sind.

Bevor Sie mit diesem Abschnitt fortfahren, stellen Sie zunächst sicher, dass Sie alle vorherigen Migrationsaufgaben abgeschlossen haben.

Die Informationen auf dieser Seite beziehen sich auf Schritt 8, wie in der folgenden Tabelle hervorgehoben:

| Migrationsaufgabe | Details |
|---------|----------|
| **Schritt 1: [Erste Schritte mit der Migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Erfahren Sie mehr über die Vorteile der Migration zu Adobe Analytics und den grundlegenden Migrationsprozess. |
| **Schritt 2: [Migrationsmethode auswählen](/help/getting-started/cja-migration/cja-migration-method.md)** | Für die Migration zum Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie je nach aktueller Adobe Analytics-Umgebung und langfristigen Zielen Ihres Unternehmens die für Ihr Unternehmen am besten geeignete Methode aus. |
| **Schritt 3: [Daten an Adobe Experience Platform senden](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Der Prozess zum Senden von Daten an Adobe Experience Platform hängt von der in Schritt 1 ausgewählten Migrationsmethode ab. |
| **Schritt 4: [Zuordnen von Daten zum XDM-Schema](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM-Schemata](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) werden in Adobe Experience Platform verwendet, um die Datenstruktur konsistent und wiederverwendbar zu beschreiben. Durch die systemübergreifende einheitliche Definition von Daten wird es einfacher, deren Bedeutung beizubehalten und somit Wert aus Daten zu ziehen.<p>Die meisten Migrationsmethoden erfordern, dass Sie entweder ein neues XDM-Schema erstellen oder Ihr bestehendes Adobe Analytics-Schema mithilfe der Datastream-Zuordnung XDM zuordnen.</p> |
| **Schritt 5: [Verlaufsdaten beibehalten](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | Die meisten Unternehmen müssen ihre historischen Adobe Analytics-Daten für einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung. |
| **Schritt 6: [Benutzereinstieg planen](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Sie sollten Ihren Benutzern ausreichend Zeit (3 - 6 Monate) geben, um sich mit den wichtigsten Unterschieden von Analysis Workspace im Customer Journey Analytics vertraut zu machen. |
| **Schritt 7: [Portieren der Nutzung der Reporting-API](/help/getting-started/cja-migration/cja-migration-api.md)** | Die Customer Journey Analytics Reporting-API weist dasselbe Format auf, verwendet jedoch einen anderen Endpunkt. Portieren Sie die Nutzung der Reporting-API von der Adobe Analytics Reporting-API an die Customer Journey Analytics-Reporting-API. |
| <span class="preview">**Schritt 8: [Ersetzen von Daten-Feeds und Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)**</span> | <span class="preview">Entscheiden Sie, wie Sie die unter Customer Journey Analytics verfügbaren Exportoptionen verwenden werden, um die Daten-Feeds- und Data Warehouse-Funktionen zu ersetzen, die Sie in Adobe Analytics verwendet haben.</span> |
| **Schritt 9: [Migrieren von Projekten und Komponenten](/help/getting-started/cja-migration/cja-migration-projects.md)** | Im Bereich Komponentenmigration in Adobe Analytics können Sie Projekte und die zugehörigen Komponenten von Adobe Analytics auf Customer Journey Analytics migrieren. |
| **Schritt 10: [Ausführen von Aufgaben nach der Migration](/help/getting-started/cja-getting-started.md)** | Nachdem Sie die Migration abgeschlossen haben, müssen Sie verschiedene Aufgaben ausführen, darunter das Einbringen weiterer Daten in das Experience Platform, das Erstellen von Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics, das Erstellen von Datenansichten und das Erlernen des Berichts über kanalübergreifende Daten in Analysis Workspace. |

{style="table-layout:auto"}

+++

Wenn Sie derzeit Daten-Feeds oder Data Warehouse in Adobe Analytics verwenden, verwenden Sie die folgende Tabelle, um mehr über die verschiedenen Exportoptionen zu erfahren, die unter Customer Journey Analytics verfügbar sind:

| Adobe Analytics | Customer Journey Analytics |
|---------|----------|
| Daten-Feeds | Beurteilen Sie Ihre Data Feeds-Anwendungsfälle und verwenden Sie dann eine beliebige Kombination alternativer Exportmethoden, die unter Customer Journey Analytics verfügbar sind: <ul><li>So exportieren Sie Rohdatensätze [Exportieren von Datensätzen in Cloud-Speicher-Ziele](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets)&#x200B;</li><li>Für Exporte auf Zielgruppen- oder Ereignisebene mit Personen-ID oder Zeitstempel verwenden Sie [Vollständiger Tabellenexport](/help/analysis-workspace/export/export-cloud.md)&#x200B;</li><li>Für eine direkte Integration mit Power BI und Tableau verwenden Sie die [Customer Journey Analytics BI-Erweiterung](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension)&#x200B;</li><li>Verwenden Sie für den direkten SQL-Zugriff auf Daten in Adobe Experience Platform den [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/home).</li></ul> |
| Data Warehouse | Ändern der Adobe Analytics-Data Warehouse-Exporte zur Verwendung [Vollständiger Tabellenexport](/help/analysis-workspace/export/export-cloud.md) in Customer Journey Analytics.<p>Customer Journey Analytics Full Table Export ist die Entwicklung von Data Warehouse-Berichten in Adobe Analytics, mit vielen neuen, häufig angeforderten Funktionen, die heute nicht in Data Warehouse verfügbar sind.</p> |

{style="table-layout:auto"}

## Migrieren Sie anschließend Projekte und Komponenten.

Verwenden Sie den Komponentenmigrationsbereich in Adobe Analytics, um [Migrieren von Projekten und den zugehörigen Komponenten](/help/getting-started/cja-migration/cja-migration-projects.md) von Adobe Analytics zu Customer Journey Analytics.
