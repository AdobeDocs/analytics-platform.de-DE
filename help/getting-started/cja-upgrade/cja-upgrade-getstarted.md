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
ht-degree: 10%

---

# Schritt 1: Erste Schritte mit dem Upgrade auf Customer Journey Analytics

Customer Journey Analytics ist die nächste Analysegeneration. Sie ermöglicht die kanalübergreifende Datenerfassung (sowohl Online- als auch Offline-Daten) in Verbindung mit einer leistungsstarken Berichtszeitverarbeitungsfunktion (durch Definition von Komponenten und abgeleiteten Feldern in Datenansichten).

Bevor Sie mit der Aktualisierung von Adobe Analytics auf Customer Journey Analytics beginnen, sollten Sie die Vorteile von Customer Journey Analytics sowie die Schritte kennen, die für eine erfolgreiche Aktualisierung erforderlich sind.

## Die Vorteile von Customer Journey Analytics

Im Folgenden finden Sie einige der wichtigsten Vorteile: (Eine umfassende Liste sowie weitere Informationen zu den einzelnen wichtigen Funktionen finden Sie unter [Nur auf Customer Journey Analytics verfügbare Funktionen](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics).

* [Multi-Channel-Reporting](/help/getting-started/aa-to-cja-user.md#changes-to-data-architecture)

  Customer Journey Analytics wird mit der Fähigkeit von Experience Platform kombiniert, alle Arten von Datenschemata und -typen zu speichern. Erfassen und Berichten von Daten aus mehreren Kanälen, z. B. digitalen (Web), Point-of-Sale-Systemen, mobilen Systemen, CRM-Systemen und mehr.

* [Berichtszeittransformationen in Datenansichten](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

  Datenansichten in Customer Journey Analytics ermöglichen eine weiter gehende Interpretation von Daten aus einer Verbindung. Sie können Daten ändern oder entfernen, ohne Ihre Implementierung zu ändern, Unterzeichenfolgen verwenden, um Dimensionen zu bearbeiten, Metriken aus einem beliebigen Wert zu erstellen, Unterereignisse zu filtern oder abgeleitete Felder zu verwenden. Alle diese Umwandlungen sind zerstörungsfrei.

* [Umwandlungen gelten für historische und neue Daten](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)

  Die Manipulation von Datenansichten kann zerstörungsfrei sowohl auf historische als auch auf neue Daten angewendet werden.

* [Abgeleitete Felder](/help/data-views/derived-fields/derived-fields.md)

  Abgeleitete Felder ermöglichen die Umwandlung zum Zeitpunkt der Berichtserstattung Ihren Daten. Daten können dynamisch kombiniert, korrigiert oder erstellt werden und gelten rückwirkend für alle Berichte.

* [Datenansichten ersetzen Virtual Report Suites](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-virtual-report-suites)

  Datenansichten nehmen das Konzept der Virtual Report Suites an, wie sie heute existieren, und erweitern es, um zusätzliche Steuerelemente für die Daten zu ermöglichen, die über Verbindungen bereitgestellt werden. Diese Änderungen machen allgemeine Einstellungen wie Zeitzonen- und Sitzungs-Timeout-Intervalle konfigurierbar und rückwirkend.

* [Unbegrenzte Kundendimensionen und -metriken](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-evars-and-props)

  Werte können numerisch, Text, Objekte, Listen oder Mischungen von allen sein. Dimensionen können verschachtelt oder hierarchisch aufgebaut sein.

## Informationen zum Upgrade-Prozess

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
Die Informationen auf dieser Seite beziehen sich auf Schritt 1 des Aktualisierungsprozesses, wie in der folgenden Tabelle hervorgehoben. Führen Sie alle Schritte in dieser Tabelle aus, um von Adobe Analytics auf Customer Journey Analytics zu aktualisieren.

| Aktualisierungsaufgabe | Details |
|---------|----------|
| <span class="preview">**Schritt 1: Erste Schritte mit dem Upgrade**</span> | <span class="preview">Erfahren Sie mehr über die Vorteile der Aktualisierung auf Customer Journey Analytics und den grundlegenden Upgrade-Prozess.</span> |
| **Schritt 2: [Aktualisierungspfad auswählen](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Für die Aktualisierung auf Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie je nach aktueller Adobe Analytics-Umgebung und langfristigen Zielen Ihres Unternehmens die für Ihr Unternehmen am besten geeignete Methode aus. |
| **Schritt 3: [Daten an Adobe Experience Platform senden](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Der Prozess zum Senden von Daten an Adobe Experience Platform hängt vom Aktualisierungspfad ab, den Sie in Schritt 2 ausgewählt haben. |
| **Schritt 4: [Verlaufsdaten beibehalten](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | Die meisten Unternehmen müssen ihre historischen Adobe Analytics-Daten für einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung. |
| **Schritt 5: [Zusätzliche Implementierungsaufgaben durchführen](/help/getting-started/cja-getting-started.md)** | An dieser Stelle des Aktualisierungsprozesses müssen Sie verschiedene Aufgaben ausführen, bevor Ihre Customer Journey Analytics-Umgebung verwendet werden kann.<p>Diese zusätzlichen Aufgaben gelten für Aktualisierungen von Adobe Analytics sowie für neue Customer Journey Analytics-Implementierungen.</p><p>Zu diesen Aufgaben gehören:</p><ul><li>Andere Daten in Experience Platform integrieren</li><li>Erstellen von Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics</li><li>Erstellen von Datenansichten</li><li>Portieren der Nutzung der Reporting-API</li><li>Abrechnung von Daten-Feeds und Data Warehouse</li><li>Migrieren von Projekten und Komponenten</li><li>Benutzerintegration planen</li></ul> <p>Weitere Informationen finden Sie unter [Customer Journey Analytics - Erste Schritte](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

## Wählen Sie zunächst den Aktualisierungspfad aus.

Für die Aktualisierung auf Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. [Wählen Sie die für Ihre Organisation am besten geeignete Methode aus.](/help/getting-started/cja-upgrade/cja-upgrade-path.md).

Der von Ihnen ausgewählte Aktualisierungspfad hängt von der aktuellen Adobe Analytics-Umgebung und den langfristigen Zielen Ihres Unternehmens ab.