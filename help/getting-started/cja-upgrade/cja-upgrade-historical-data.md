---
title: Beibehalten historischer Daten beim Upgrade auf Customer Journey Analytics
description: Erfahren Sie, wie Sie historische Daten beim Upgrade auf Customer Journey Analytics beibehalten können
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 73%

---

# Schritt 4: Beibehalten historischer Daten beim Upgrade

+++Erweitern Sie diesen Abschnitt, um zu sehen, wo die Informationen auf dieser Seite in den allgemeinen Upgrade-Prozess einzuordnen sind. Stellen Sie sicher, dass alle vorherigen Upgrade-Schritte abgeschlossen sind.

Bevor Sie mit diesem Abschnitt fortfahren, stellen Sie zunächst sicher, dass Sie alle vorherigen Upgrade-Aufgaben abgeschlossen haben.

Die Informationen auf dieser Seite beziehen sich auf Schritt 4 des Upgrades, wie in der folgenden Tabelle hervorgehoben:

| Upgrade-Aufgabe | Details |
|---------|----------|
| **Schritt 1: [Erste Schritte beim Upgrade](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Erfahren Sie mehr über die Vorteile des Upgrades auf Customer Journey Analytics und den grundlegenden Upgrade-Prozess. |
| **Schritt 2: [Auswählen des Upgrade-Pfads](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Für das Upgrade auf Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie je nach aktueller Adobe Analytics-Umgebung und den langfristigen Zielen Ihrer Organisation die für Ihre Organisation am besten geeignete Methode aus. |
| **Schritt 3: [Senden von Daten an Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Der Prozess zum Senden von Daten an Adobe Experience Platform richtet sich nach dem in Schritt 2 ausgewählten Upgrade-Pfad. |
| <span class="preview">**Schritt 4: Beibehalten historischer Daten**</span> | <span class="preview">Die meisten Organisationen müssen ihre historischen Adobe Analytics-Daten über einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung.</span> |
| **Schritt 5: [Durchführen zusätzlicher Implementierungsaufgaben](/help/getting-started/cja-getting-started.md)** | An dieser Stelle im Upgrade-Prozess müssen Sie verschiedene Aufgaben ausführen, bevor Ihre Customer Journey Analytics-Umgebung einsatzbereit ist.<p>Diese zusätzlichen Aufgaben gelten für Upgrades von Adobe Analytics sowie für neue Customer Journey Analytics-Implementierungen.</p><p>Zu diesen Aufgaben zählen:</p><ul><li>Erfassen von Daten in Experience Platform</li><li>Erstellen von Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics</li><li>Erstellen von Datenansichten</li><li>Portieren der Reporting-API-Nutzung</li><li>Abrechnung für Daten-Feeds und Data Warehouse</li><li>Migrieren von Projekten und Komponenten</li><li>Planen des Benutzer-Onboardings</li></ul> <p>Weitere Informationen finden Sie unter [Customer Journey Analytics – Erste Schritte](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>Die Informationen auf dieser Seite werden durch die folgenden umfassenderen Upgrade-Informationen ersetzt: <ul><li>**Empfohlene Upgrade-Schritte**<p>Detaillierte Informationen finden Sie unter [Empfohlener Pfad beim Upgrade von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Customer Journey Analytics-Aktualisierungshandbuch**<p>Es ist ein neues Upgrade-Handbuch verfügbar, in dem dynamisch Upgrade-Schritte generiert werden, die für Ihr Unternehmen und Ihre individuellen Bedingungen maßgeschneidert sind.</p><p>Um über Customer Journey Analytics auf das Handbuch zuzugreifen, wählen Sie die Registerkarte **[!UICONTROL Workspace]** und dann **[!UICONTROL Upgrade auf Customer Journey Analytics]** im linken Bereich aus. Befolgen Sie die Anweisungen auf dem Bildschirm.</p></li></ul>

Wählen Sie eine der folgenden Optionen, um beim Wechsel von Adobe Analytics zu Customer Journey Analytics historische Daten beizubehalten

>[!IMPORTANT]
>
>Wenden Sie sich an die Adobe-Kundenbetreuung, wenn Sie über die Methode entscheiden, wie historische Daten beibehalten werden sollen, um entsprechende Preisinformationen zu erhalten.

## Verwenden des Analytics-Quell-Connectors

Sie können den [Analytics-Quell-Connector](/help/data-ingestion/analytics.md) verwenden, um historische Daten beizubehalten. Unabhängig vom ausgewählten Aktualisierungspfad (selbst wenn Sie das Upgrade mit der Web-SDK durchführen) können Sie den Analytics-Quell-Connector verwenden, um historische Daten aus Ihrer Adobe Analytics-Umgebung beizubehalten.

Sie können den Analytics-Quell-Connector verwenden, um historische Daten beizubehalten, indem Sie historische Daten an einem eigenen dedizierten Speicherort getrennt von Ihren aktuellen Daten abrufen.

Der Analytics-Quell-Connector muss so lange funktionieren, wie Sie Zugriff auf die Verlaufsdaten benötigen.

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## Beibehalten der vorhandenen Adobe Analytics-Implementierung

Sie können Ihre vorhandene Adobe Analytics-Implementierung neben Ihrer neuen Customer Journey Analytics-Implementierung für einen bestimmten Zeitraum (z. B. 1 Jahr) beibehalten. Bei dieser Option ist Folgendes zu beachten:

* Daten stehen nicht in Experience Platform zur Verfügung.

* Sie sollten planen, die Adobe Analytics-Implementierung außer Betrieb zu setzen, wenn genügend Daten in Customer Journey Analytics vorhanden sind.

## Der nächste Schritt – Durchführen zusätzlicher Implementierungsaufgaben

An dieser Stelle im Upgrade-Prozess müssen Sie verschiedene Implementierungsaufgaben durchführen, damit Sie Ihre Customer Journey Analytics-Umgebung verwenden können.

Diese zusätzlichen Aufgaben gelten für Upgrades von Adobe Analytics sowie für neue Customer Journey Analytics-Implementierungen.

Zu diesen Aufgaben zählen:

* Erfassen von Daten in Experience Platform

* Erstellen von Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics

* Erstellen von Datenansichten

* Portieren der Reporting-API-Nutzung

* Abrechnen für Daten-Feeds und Data Warehouse-Anwendungsfälle

* Migrieren von Projekten und Komponenten

* Planen des Benutzer-Onboardings

Weitere Informationen finden Sie in Schritt 2 unter [Customer Journey Analytics – Erste Schritte](/help/getting-started/cja-getting-started.md).
