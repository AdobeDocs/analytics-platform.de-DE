---
title: Erste Schritte mit dem Upgrade auf Customer Journey Analytics
description: Upgrade von Adobe Analytics auf Customer Journey Analytics planen
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: c64f7a1676f4fd3712e618e26357f430e7d9f019
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 63%

---

# Schritt 1: Erste Schritte mit dem Upgrade auf Customer Journey Analytics

Customer Journey Analytics ist das Analyseprodukt der nächsten Generation. Es ermöglicht eine kanalübergreifende Datenerfassung (von Online- und Offline-Daten) in Verbindung mit der leistungsstarken Funktion „Berichtszeitverarbeitung“ (durch Definition von Komponenten und abgeleiteten Feldern in Datenansichten).

Bevor Sie mit der Aktualisierung von Adobe Analytics auf Customer Journey Analytics beginnen, sollten Sie die Vorteile von Customer Journey Analytics sowie die Schritte kennen, die für eine erfolgreiche Aktualisierung erforderlich sind.

## Die Vorteile von Customer Journey Analytics

Im Folgenden werden einige der wichtigsten Vorteile vorgestellt. (Eine umfassende Liste sowie weitere Informationen zu den einzelnen Schlüsselfunktionen finden Sie unter [Nur in Customer Journey Analytics verfügbare Funktionen](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics).)

* [Multi-Channel-Reporting](/help/getting-started/aa-to-cja-user.md#changes-to-data-architecture)

  Customer Journey Analytics ist mit der Fähigkeit von Experience Platform kombiniert, alle Arten von Datenschemata und -typen zu speichern. Erfassen Sie Daten aus mehreren Kanälen, z. B. digitalen Kanälen (Web), Point-of-Sale-Systemen, Mobile, CRM-Systemen usw. und erstellen Sie darüber entsprechende Berichte.

* [Berichtszeittransformationen in Datenansichten](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

  Datenansichten in Customer Journey Analytics ermöglichen eine weiter gehende Interpretation von Daten aus einer Verbindung. Sie können Daten ändern oder entfernen, ohne Ihre Implementierung zu ändern, Teilzeichenfolgen verwenden, um Dimensionen zu bearbeiten, Metriken aus beliebigen Werten erstellen, Teilereignisse filtern oder abgeleitete Felder nutzen. Alle diese Transformationen erfolgen zerstörungsfrei. 

* [Transformationen für historische und neue Daten](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)

  Änderungen der Datenansicht können auf zerstörungsfreie Weise auf historische und neue Daten angewendet werden.

* [Abgeleitete Felder](/help/data-views/derived-fields/derived-fields.md)

  Abgeleitete Felder ermöglichen die Umwandlung zum Zeitpunkt der Berichtserstattung Ihren Daten. Daten können dynamisch kombiniert, korrigiert oder erstellt werden und gelten rückwirkend für alle Berichte.

* [Datenansichten statt Virtual Report Suites](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-virtual-report-suites)

  Datenansichten übernehmen das Konzept der heutigen Virtual Report Suites und erweitern es, sodass die über die Verbindungen verfügbar gemachten Daten besser kontrolliert werden können. Durch diese Änderungen können allgemeine Einstellungen wie Zeitzonen und Sitzungs-Timeout-Intervalle konfiguriert werden und diese Konfigurationen gelten auch rückwirkend. 

* [Unbegrenzte Kundendimensionen und -metriken](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-evars-and-props)

  Werte können Zahlen, Text, Objekte, Listen oder ein Mix dieser Elemente sein. Dimensionen können verschachtelt oder hierarchisch aufgebaut sein.

## Informationen zum Upgrade-Prozess

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
Die Informationen auf dieser Seite beziehen sich auf Schritt 1 des Aktualisierungsprozesses, wie in der folgenden Tabelle hervorgehoben. Führen Sie alle Schritte in dieser Tabelle aus, um von Adobe Analytics auf Customer Journey Analytics zu aktualisieren.

| Aktualisierungsaufgabe | Details |
|---------|----------|
| <span class="preview">**Schritt 1: Erste Schritte mit dem Upgrade**</span> | <span class="preview">Erfahren Sie mehr über die Vorteile der Aktualisierung auf Customer Journey Analytics und den grundlegenden Aktualisierungsprozess.</span> |
| **Schritt 2: [Aktualisierungspfad auswählen](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Für die Aktualisierung auf Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie je nach aktueller Adobe Analytics-Umgebung und den langfristigen Zielen Ihrer Organisation die für Ihre Organisation am besten geeignete Methode aus. |
| **Schritt 3: [Senden von Daten an Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Der Prozess zum Senden von Daten an Adobe Experience Platform hängt vom Aktualisierungspfad ab, den Sie in Schritt 2 ausgewählt haben. |
| **Schritt 4: [Beibehalten historischer Daten](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | Die meisten Organisationen müssen ihre historischen Adobe Analytics-Daten über einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung. |
| **Schritt 5: [Durchführen zusätzlicher Implementierungsaufgaben](/help/getting-started/cja-getting-started.md)** | An dieser Stelle des Aktualisierungsprozesses müssen Sie verschiedene Aufgaben ausführen, bevor Ihre Customer Journey Analytics-Umgebung verwendet werden kann.<p>Diese zusätzlichen Aufgaben gelten für Aktualisierungen von Adobe Analytics sowie für neue Customer Journey Analytics-Implementierungen.</p><p>Zu diesen Aufgaben zählen:</p><ul><li>Erfassen von Daten in Experience Platform</li><li>Erstellen von Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics</li><li>Erstellen von Datenansichten</li><li>Portieren der Reporting-API-Nutzung</li><li>Abrechnung für Daten-Feeds und Data Warehouse</li><li>Migrieren von Projekten und Komponenten</li><li>Planen des Benutzer-Onboardings</li></ul> <p>Weitere Informationen finden Sie unter [Customer Journey Analytics – Erste Schritte](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

## Wählen Sie zunächst den Aktualisierungspfad aus.

Für die Aktualisierung auf Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. [Wählen Sie die für Ihre Organisation am besten geeignete Methode aus](/help/getting-started/cja-upgrade/cja-upgrade-path.md).

Der von Ihnen ausgewählte Aktualisierungspfad hängt von der aktuellen Adobe Analytics-Umgebung und den langfristigen Zielen Ihres Unternehmens ab.
