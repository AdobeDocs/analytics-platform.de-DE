---
title: Beim Aktualisieren auf Customer Journey Analytics historische Daten beibehalten
description: Erfahren Sie, wie Sie beim Upgrade auf Customer Journey Analytics historische Daten beibehalten können.
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: c64f7a1676f4fd3712e618e26357f430e7d9f019
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 55%

---

# Schritt 4: Beibehalten von historischen Daten beim Upgrade

+++ Erweitern Sie diesen Abschnitt, um zu sehen, wo die Informationen auf dieser Seite in den größeren Aktualisierungsprozess passen. Stellen Sie sicher, dass alle vorherigen Aktualisierungsschritte abgeschlossen sind.

Bevor Sie mit diesem Abschnitt fortfahren, stellen Sie zunächst sicher, dass Sie alle vorherigen Aktualisierungsaufgaben abgeschlossen haben.

Die Informationen auf dieser Seite decken Schritt 4 des Aktualisierungsprozesses ab, wie in der folgenden Tabelle hervorgehoben:

| Aktualisierungsaufgabe | Details |
|---------|----------|
| **Schritt 1: [Erste Schritte mit dem Upgrade](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Erfahren Sie mehr über die Vorteile der Aktualisierung auf Customer Journey Analytics und den grundlegenden Upgrade-Prozess. |
| **Schritt 2: [Aktualisierungspfad auswählen](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Für die Aktualisierung auf Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie je nach aktueller Adobe Analytics-Umgebung und den langfristigen Zielen Ihrer Organisation die für Ihre Organisation am besten geeignete Methode aus. |
| **Schritt 3: [Senden von Daten an Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Der Prozess zum Senden von Daten an Adobe Experience Platform hängt vom Aktualisierungspfad ab, den Sie in Schritt 2 ausgewählt haben. |
| <span class="preview">**Schritt 4: Beibehalten historischer Daten**</span> | <span class="preview">Die meisten Organisationen müssen ihre historischen Adobe Analytics-Daten über einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung.</span> |
| **Schritt 5: [Durchführen zusätzlicher Implementierungsaufgaben](/help/getting-started/cja-getting-started.md)** | An dieser Stelle des Aktualisierungsprozesses müssen Sie verschiedene Aufgaben ausführen, bevor Ihre Customer Journey Analytics-Umgebung verwendet werden kann.<p>Diese zusätzlichen Aufgaben gelten für Aktualisierungen von Adobe Analytics sowie für neue Customer Journey Analytics-Implementierungen.</p><p>Zu diesen Aufgaben zählen:</p><ul><li>Erfassen von Daten in Experience Platform</li><li>Erstellen von Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics</li><li>Erstellen von Datenansichten</li><li>Portieren der Reporting-API-Nutzung</li><li>Abrechnung für Daten-Feeds und Data Warehouse</li><li>Migrieren von Projekten und Komponenten</li><li>Planen des Benutzer-Onboardings</li></ul> <p>Weitere Informationen finden Sie unter [Customer Journey Analytics – Erste Schritte](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Wählen Sie eine der folgenden Optionen, um beim Wechsel von Adobe Analytics zu Customer Journey Analytics historische Daten beizubehalten.

>[!IMPORTANT]
>
>Wenden Sie sich an die Adobe-Kundenbetreuung, wenn Sie über die Methode entscheiden, wie historische Daten beibehalten werden sollen, um entsprechende Preisinformationen zu erhalten.

## Verwenden des Analytics-Quell-Connectors

Sie können den [Analytics-Quell-Connector](/help/data-ingestion/analytics.md) verwenden, um historische Daten beizubehalten. Unabhängig vom ausgewählten Aktualisierungspfad (auch wenn Sie ein Upgrade mit dem Web SDK durchführen) können Sie mit dem Analytics Source Connector historische Daten aus Ihrer Adobe Analytics-Umgebung speichern.

Dabei werden die historischen Daten an einem eigenen dedizierten, von Ihren aktuellen Daten getrennten Speicherort abgelegt.

Der Analytics-Quell-Connector muss so lange funktionieren, wie Sie Zugriff auf die historischen Daten benötigen.

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## Beibehalten der vorhandenen Adobe Analytics-Implementierung

Sie können Ihre vorhandene Adobe Analytics-Implementierung neben Ihrer neuen Customer Journey Analytics-Implementierung für einen bestimmten Zeitraum (z. B. 1 Jahr) beibehalten. Bei dieser Option ist Folgendes zu beachten:

* Daten stehen nicht in Experience Platform zur Verfügung.

* Sie sollten planen, die Adobe Analytics-Implementierung außer Betrieb zu setzen, wenn genügend Daten in Customer Journey Analytics vorhanden sind.

## Der nächste Schritt – Durchführen zusätzlicher Implementierungsaufgaben

An dieser Stelle im Aktualisierungsprozess müssen Sie verschiedene Implementierungsaufgaben ausführen, bevor Ihre Customer Journey Analytics-Umgebung verwendet werden kann.

Diese zusätzlichen Aufgaben gelten für Aktualisierungen von Adobe Analytics sowie für neue Customer Journey Analytics-Implementierungen.

Zu diesen Aufgaben zählen:

* Erfassen von Daten in Experience Platform

* Erstellen von Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics

* Erstellen von Datenansichten

* Portieren der Reporting-API-Nutzung

* Abrechnen für Daten-Feeds und Data Warehouse-Anwendungsfälle

* Migrieren von Projekten und Komponenten

* Planen des Benutzer-Onboardings

Weitere Informationen finden Sie in Schritt 2 unter [Customer Journey Analytics – Erste Schritte](/help/getting-started/cja-getting-started.md).
