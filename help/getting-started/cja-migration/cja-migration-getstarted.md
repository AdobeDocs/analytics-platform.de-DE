---
title: Erste Schritte mit der Migration auf Customer Journey Analytics
description: Migration von Adobe Analytics auf Customer Journey Analytics planen
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: 21d77f06595993172460b724dc7991cb9a5a02a8
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 10%

---

# Schritt 1: Erste Schritte mit der Migration zum Customer Journey Analytics

Customer Journey Analytics ist die nächste Analysegeneration. Sie ermöglicht die kanalübergreifende Datenerfassung (sowohl Online- als auch Offline-Daten) in Verbindung mit einer leistungsstarken Berichtszeitverarbeitungsfunktion (durch Definition von Komponenten und abgeleiteten Feldern in Datenansichten).

Bevor Sie mit der Migration von Adobe Analytics zu Customer Journey Analytics beginnen, sollten Sie die Vorteile von Customer Journey Analytics sowie die Schritte kennen, die für eine erfolgreiche Migration erforderlich sind.

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

## Informationen zum Migrationsprozess

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
Diese Seite stellt Schritt 1 der Migration dar, wie in der folgenden Tabelle dargestellt. Führen Sie alle Schritte in dieser Tabelle aus, um von Adobe Analytics zu Customer Journey Analytics zu migrieren.

| Aufgabe | Details |
|---------|----------|
| **Schritt 1: [Erste Schritte mit der Migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Erfahren Sie mehr über die Vorteile der Migration zu Adobe Analytics und den grundlegenden Migrationsprozess. |
| **Schritt 2: [Migrationsmethode auswählen](/help/getting-started/cja-migration/cja-migration-method.md)** | Für die Migration zum Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie unter Berücksichtigung der aktuellen Adobe Analytics-Umgebung Ihres Unternehmens und Ihrer langfristigen Ziele die für Ihr Unternehmen am besten geeignete Methode aus. |
| **Schritt 3: [Daten an Adobe Experience Platform senden](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Der Prozess zum Senden von Daten an Adobe Experience Platform hängt von der in Schritt 1 ausgewählten Migrationsmethode ab. |
| **Schritt 4: [Zuordnen von Daten zum XDM-Schema](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM-Schemata](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) werden in Adobe Experience Platform verwendet, um die Datenstruktur konsistent und wiederverwendbar zu beschreiben. Durch die systemübergreifende einheitliche Definition von Daten wird es einfacher, deren Bedeutung beizubehalten und somit Wert aus Daten zu ziehen.<p>Die meisten Migrationsmethoden erfordern, dass Sie entweder ein neues XDM-Schema erstellen oder Ihr bestehendes Adobe Analytics-Schema mithilfe der Datastream-Zuordnung XDM zuordnen.</p> |
| **Schritt 5: [Verlaufsdaten beibehalten](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | Die meisten Unternehmen müssen ihre historischen Adobe Analytics-Daten für einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung. |
| **Schritt 6: [Benutzereinstieg planen](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Sie sollten Ihren Benutzern ausreichend Zeit (3 - 6 Monate) geben, um sich mit den wichtigsten Unterschieden von Analysis Workspace im Customer Journey Analytics vertraut zu machen. |
| **Schritt 7: [Portieren der Nutzung der Reporting-API](/help/getting-started/cja-migration/cja-migration-api.md)** | Die Customer Journey Analytics Reporting-API weist dasselbe Format auf, verwendet jedoch einen anderen Endpunkt. Portieren Sie die Nutzung der Reporting-API von der Adobe Analytics Reporting-API an die Customer Journey Analytics-Reporting-API. |
| **Schritt 8: [Ersetzen von Daten-Feeds und Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Entscheiden Sie, wie Sie die unter Customer Journey Analytics verfügbaren Exportoptionen verwenden werden, um die Daten-Feeds- und Data Warehouse-Funktionen zu ersetzen, die Sie in Adobe Analytics verwendet haben. |
| **Schritt 9: [Migrieren von Projekten und Komponenten](/help/getting-started/cja-migration/cja-migration-projects.md)** | Im Bereich Komponentenmigration in Adobe Analytics können Sie Projekte und die zugehörigen Komponenten von Adobe Analytics auf Customer Journey Analytics migrieren. |
| **Schritt 10: [Ausführen von Aufgaben nach der Migration](/help/getting-started/cja-getting-started.md)** | Nachdem Sie die Migration abgeschlossen haben, müssen Sie verschiedene Aufgaben ausführen, darunter das Einbringen weiterer Daten in das Experience Platform, das Erstellen von Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics, das Erstellen von Datenansichten und das Erlernen des Berichts über kanalübergreifende Daten in Analysis Workspace. |

{style="table-layout:auto"}

## Wählen Sie zuerst die Migrationsmethode aus.

Für die Migration zum Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. [Wählen Sie die für Ihre Organisation am besten geeignete Methode aus.](/help/getting-started/cja-migration/cja-migration-method.md).

Die von Ihnen gewählte Migrationsmethode hängt von der aktuellen Adobe Analytics-Umgebung und den langfristigen Zielen Ihres Unternehmens ab.
