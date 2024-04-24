---
title: Portieren Sie die Nutzung der Reporting-API bei der Migration auf Customer Journey Analytics.
description: Erfahren Sie, wie Sie die API-Nutzung von Adobe Analytics auf Customer Journey Analytics portieren
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d26a6956-870f-44f2-9c32-f732bff17737
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# Schritt 7: Portieren Sie die Verwendung der Reporting-API bei der Migration auf Customer Journey Analytics.

+++ Erweitern Sie diesen Abschnitt, um zu sehen, wo die Informationen auf dieser Seite in den größeren Migrationsprozess passen. Stellen Sie sicher, dass alle vorherigen Migrationsschritte abgeschlossen sind.

Bevor Sie mit diesem Abschnitt fortfahren, stellen Sie zunächst sicher, dass Sie alle vorherigen Migrationsaufgaben abgeschlossen haben.

Die Informationen auf dieser Seite beziehen sich auf Schritt 7, wie in der folgenden Tabelle hervorgehoben:

| Migrationsaufgabe | Details |
|---------|----------|
| **Schritt 1: [Erste Schritte mit der Migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Erfahren Sie mehr über die Vorteile der Migration zu Adobe Analytics und den grundlegenden Migrationsprozess. |
| **Schritt 2: [Migrationspfad auswählen](/help/getting-started/cja-migration/cja-migration-path.md)** | Für die Migration zum Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie je nach aktueller Adobe Analytics-Umgebung und langfristigen Zielen Ihres Unternehmens die für Ihr Unternehmen am besten geeignete Methode aus. |
| **Schritt 3: [Daten an Adobe Experience Platform senden](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Der Prozess zum Senden von Daten an Adobe Experience Platform hängt vom in Schritt 2 ausgewählten Migrationspfad ab. |
| **Schritt 4: [Verlaufsdaten beibehalten](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | Die meisten Unternehmen müssen ihre historischen Adobe Analytics-Daten für einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung. |
| **Schritt 5: [Zusätzliche Implementierungsaufgaben durchführen](/help/getting-started/cja-getting-started.md)** | An dieser Stelle im Migrationsprozess müssen Sie verschiedene Aufgaben ausführen, bevor Ihre Customer Journey Analytics-Umgebung einsatzbereit ist.<p>Diese zusätzlichen Aufgaben gelten für Migrationen von Adobe Analytics sowie für neue Customer Journey Analytics-Implementierungen.</p><p>Zu diesen Aufgaben gehören:</p><ul><li>Andere Daten in Experience Platform integrieren</li><li>Erstellen von Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics</li><li>Erstellen von Datenansichten</li><li>Portieren der Nutzung der Reporting-API</li><li>Abrechnung von Daten-Feeds und Data Warehouse</li><li>Migrieren von Projekten und Komponenten</li><li>Benutzerintegration planen</li></ul> <p>Weitere Informationen finden Sie unter [Customer Journey Analytics - Erste Schritte](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Portieren Sie die Nutzung der Reporting-API von der Adobe Analytics Reporting-API an die Customer Journey Analytics-Reporting-API.

Die Customer Journey Analytics Reporting-API weist dasselbe Format auf, verwendet jedoch eine andere Subdomäne.

Weitere Informationen finden Sie im Endpunkthandbuch für Adobe Analytics und Customer Journey Analytics.

Die meisten API-Aufrufe können einfach von Adobe Analytics in Customer Journey Analytics übersetzt werden.

Fügen Sie die Customer Journey Analytics-API ihrem API-Projekt hinzu.

Fügen Sie die IMS-Organisations-ID zur Kopfzeile ihrer API-Aufrufe hinzu.

cja.adobe.io vs. analytics.adobe.io

Zusätzliche Header

## Ersetzen Sie anschließend Daten-Feeds und Data Warehouse

Legen Sie fest, wie Sie die unter Customer Journey Analytics verfügbaren Exportoptionen verwenden werden, um [Ersetzen der Daten-Feeds- und Data Warehouse-Funktionen](/help/getting-started/cja-migration/cja-migration-export-options.md) Sie in Adobe Analytics verwendet haben.
