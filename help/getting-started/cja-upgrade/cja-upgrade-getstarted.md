---
title: Erste Schritte mit dem Upgrade auf Customer Journey Analytics
description: Planen des Upgrades von Adobe Analytics auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: 765b6863cdafa06b54b76fbf0983afb4c14c21d4
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 56%

---

# Schritt 1: Erste Schritte mit dem Upgrade auf Customer Journey Analytics

>[!AVAILABILITY]
>
>Die Informationen auf dieser Seite werden durch die folgenden umfassenderen Upgrade-Informationen ersetzt: <ul><li>**Empfohlene Upgrade-Schritte**<p>Detaillierte Informationen finden Sie unter [Empfohlener Pfad beim Upgrade von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Customer Journey Analytics-Aktualisierungshandbuch**<p>Es ist ein neues Upgrade-Handbuch verfügbar, in dem dynamisch Upgrade-Schritte generiert werden, die für Ihr Unternehmen und Ihre individuellen Bedingungen maßgeschneidert sind.</p><p>Um über Customer Journey Analytics auf das Handbuch zuzugreifen, wählen Sie die Registerkarte **[!UICONTROL Workspace]** und dann **[!UICONTROL Upgrade auf Customer Journey Analytics]** im linken Bereich aus. Befolgen Sie die Anweisungen auf dem Bildschirm.</p></li></ul>

Customer Journey Analytics ist das Analyseprodukt der nächsten Generation. Es ermöglicht eine kanalübergreifende Datenerfassung (von Online- und Offline-Daten) in Verbindung mit der leistungsstarken Funktion „Berichtszeitverarbeitung“ (durch Definition von Komponenten und abgeleiteten Feldern in Datenansichten).

Bevor Sie mit dem Upgrade von Adobe Analytics auf Customer Journey Analytics beginnen, sollten Sie die Vorteile von Customer Journey Analytics sowie die für ein erfolgreiches Upgrade erforderlichen Schritte kennen.

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

## Grundlegendes zum Upgrade-Prozess

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
Die Informationen auf dieser Seite decken Schritt 1 des Upgrade-Prozesses ab, wie in der folgenden Tabelle hervorgehoben. Führen Sie alle Schritte in dieser Tabelle aus, um von Adobe Analytics auf Customer Journey Analytics zu aktualisieren.

| Upgrade-Aufgabe | Details |
|---------|----------|
| <span class="preview">**Schritt 1: Erste Schritte mit dem Upgrade**</span> | <span class="preview">Erfahren Sie mehr über die Vorteile eines Upgrades auf Customer Journey Analytics und den grundlegenden Upgrade-Prozess.</span> |
| **Schritt 2: [Wählen Sie den Aktualisierungspfad](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Beim Upgrade auf Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie je nach aktueller Adobe Analytics-Umgebung und den langfristigen Zielen Ihrer Organisation die für Ihre Organisation am besten geeignete Methode aus. |
| **Schritt 3: [Senden von Daten an Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Der Prozess zum Senden von Daten an Adobe Experience Platform unterscheidet sich je nach Upgrade-Pfad, den Sie in Schritt 2 ausgewählt haben. |
| **Schritt 4: [Beibehalten historischer Daten](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | Die meisten Organisationen müssen ihre historischen Adobe Analytics-Daten über einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung. |
| **Schritt 5: [Durchführen zusätzlicher Implementierungsaufgaben](/help/getting-started/cja-getting-started.md)** | An dieser Stelle des Upgrade-Prozesses müssen Sie verschiedene Aufgaben ausführen, bevor Ihre Customer Journey Analytics-Umgebung einsatzbereit ist.<p>Diese zusätzlichen Aufgaben gelten für Upgrades von Adobe Analytics sowie neue Customer Journey Analytics-Implementierungen.</p><p>Zu diesen Aufgaben zählen:</p><ul><li>Erfassen von Daten in Experience Platform</li><li>Erstellen von Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics</li><li>Erstellen von Datenansichten</li><li>Portieren der Reporting-API-Nutzung</li><li>Abrechnung für Daten-Feeds und Data Warehouse</li><li>Migrieren von Projekten und Komponenten</li><li>Planen des Benutzer-Onboardings</li></ul> <p>Weitere Informationen finden Sie unter [Customer Journey Analytics – Erste Schritte](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

## Wählen Sie zunächst den Aktualisierungspfad aus

Beim Upgrade auf Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. [Wählen Sie die für Ihre Organisation am besten geeignete Methode aus](/help/getting-started/cja-upgrade/cja-upgrade-path.md).

Der von Ihnen gewählte Aktualisierungspfad hängt von der aktuellen Adobe Analytics-Umgebung Ihres Unternehmens und seinen langfristigen Zielen ab.
