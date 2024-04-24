---
title: Aufbewahren historischer Daten bei der Migration auf Customer Journey Analytics
description: Erfahren Sie, wie Sie historische Daten bei der Migration zu Customer Journey Analytics beibehalten können.
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 2d35e49ca9afe37ed53d7c5da5aafd31dd2da632
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# Schritt 4: Verlaufsdaten bei der Migration beibehalten

+++ Erweitern Sie diesen Abschnitt, um zu sehen, wo die Informationen auf dieser Seite in den größeren Migrationsprozess passen. Stellen Sie sicher, dass alle vorherigen Migrationsschritte abgeschlossen sind.

Bevor Sie mit diesem Abschnitt fortfahren, stellen Sie zunächst sicher, dass Sie alle vorherigen Migrationsaufgaben abgeschlossen haben.

Die Informationen auf dieser Seite beziehen sich auf Schritt 4 der **Migration**, wie in der folgenden Tabelle hervorgehoben:

| Migrationsaufgabe | Details |
|---------|----------|
| **Schritt 1: [Erste Schritte mit der Migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Erfahren Sie mehr über die Vorteile der Migration zu Adobe Analytics und den grundlegenden Migrationsprozess. |
| **Schritt 2: [Migrationspfad auswählen](/help/getting-started/cja-migration/cja-migration-path.md)** | Für die Migration zum Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie je nach aktueller Adobe Analytics-Umgebung und langfristigen Zielen Ihres Unternehmens die für Ihr Unternehmen am besten geeignete Methode aus. |
| **Schritt 3: [Daten an Adobe Experience Platform senden](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Der Prozess zum Senden von Daten an Adobe Experience Platform hängt vom in Schritt 2 ausgewählten Migrationspfad ab. |
| <span class="preview">**Schritt 4: Verlaufsdaten beibehalten**</span> | <span class="preview">Die meisten Unternehmen müssen ihre historischen Adobe Analytics-Daten für einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung.</span> |
| **Schritt 5: [Zusätzliche Implementierungsaufgaben durchführen](/help/getting-started/cja-getting-started.md)** | An dieser Stelle im Migrationsprozess müssen Sie verschiedene Aufgaben ausführen, bevor Ihre Customer Journey Analytics-Umgebung einsatzbereit ist.<p>Diese zusätzlichen Aufgaben gelten für Migrationen von Adobe Analytics sowie für neue Customer Journey Analytics-Implementierungen.</p><p>Zu diesen Aufgaben gehören:</p><ul><li>Andere Daten in Experience Platform integrieren</li><li>Erstellen von Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics</li><li>Erstellen von Datenansichten</li><li>Portieren der Nutzung der Reporting-API</li><li>Abrechnung von Daten-Feeds und Data Warehouse</li><li>Migrieren von Projekten und Komponenten</li><li>Benutzerintegration planen</li></ul> <p>Weitere Informationen finden Sie unter [Customer Journey Analytics - Erste Schritte](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Wählen Sie eine der folgenden Optionen, um beim Wechsel von Adobe Analytics zu Customer Journey Analytics historische Daten beizubehalten:

>[!IMPORTANT]
>
>Wenden Sie sich bei der Wahl, wie Sie historische Daten speichern können, an Ihren Adobe-Kundenbetreuer, um die Preisgestaltung zu ermitteln.

## Verwenden des Analytics Source Connectors

Sie können die [Analytics Source Connector](/help/data-ingestion/analytics.md) , um historische Daten beizubehalten. Unabhängig vom ausgewählten Migrationspfad (auch wenn Sie mit dem Web SDK migrieren) können Sie den Analytics Source Connector verwenden, um historische Daten aus Ihrer Adobe Analytics-Umgebung beizubehalten.

Sie können den Analytics Source Connector verwenden, um historische Daten beizubehalten, indem Sie historische Daten an einen eigenen dedizierten Ort bringen, der von Ihren aktuellen Daten getrennt ist.

Der Analytics Source Connector muss solange funktionieren, wie Sie Zugriff auf die historischen Daten benötigen.

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## Vorhandene Adobe Analytics-Implementierung verwalten

Sie können Ihre vorhandene Adobe Analytics-Implementierung zusammen mit Ihrer neuen Customer Journey Analytics-Implementierung für einen bestimmten Zeitraum (z. B. 1 Jahr) verwalten. Beachten Sie bei der Auswahl dieser Option Folgendes:

* Daten wären nicht im Experience Platform verfügbar.

* Sie sollten planen, die Adobe Analytics-Implementierung zu deaktivieren, nachdem Sie über ausreichende Daten im Customer Journey Analytics verfügen.

## Als Nächstes führen Sie zusätzliche Implementierungsaufgaben durch

An dieser Stelle im Migrationsprozess müssen Sie verschiedene Implementierungsaufgaben ausführen, bevor Ihre Customer Journey Analytics-Umgebung verwendet werden kann.

Diese zusätzlichen Aufgaben gelten für Migrationen von Adobe Analytics sowie für neue Customer Journey Analytics-Implementierungen.

Zu diesen Aufgaben gehören:

* Andere Daten in Experience Platform integrieren

* Erstellen von Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics

* Erstellen von Datenansichten

* Portieren der Nutzung der Reporting-API

* Abrechnung von Daten-Feeds und Data Warehouse-Anwendungsfällen

* Migrieren von Projekten und Komponenten

* Benutzerintegration planen

Weitere Informationen finden Sie in Schritt 2 unter [Customer Journey Analytics - Erste Schritte](/help/getting-started/cja-getting-started.md).
