---
title: Customer Journey Analytics – Erste Schritte
description: Machen Sie sich mit den Voraussetzungen und dem Workflow vertraut, die für die Implementierung von Customer Journey Analytics erforderlich sind.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: c64f7a1676f4fd3712e618e26357f430e7d9f019
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 100%

---

# Customer Journey Analytics – Erste Schritte

Befolgen Sie diesen Workflow, um Customer Journey Analytics zu implementieren. Einige erste Aufgaben werden in Adobe Experience Platform und einige in Customer Journey Analytics ausgeführt.

## Voraussetzungen

Customer Journey Analytics ist für Kunden verfügbar, die

* für [Adobe Experience Platform](https://www.adobe.com/de/experience-platform.html) bereitgestellt werden und
* die Customer Journey Analytics-SKU erworben haben.

## Workflow

| Aufgabe | Details |
| --- | --- |
| **Schritt 1: Wenn Sie ein Upgrade von Adobe Analytics auf Customer Journey Analytics durchführen: Wählen Sie einen Aktualisierungspfad und senden Sie Daten an Adobe Experience Platform** | Für die Aktualisierung von Adobe Analytics zu Customer Journey Analytics stehen verschiedene Pfade zur Verfügung. Jeder mögliche Aktualisierungspfad hat seine eigenen Vor- und Nachteile, und ein Pfad, der für eine Organisation richtig ist, ist für eine andere Organisation möglicherweise nicht sinnvoll. <p>Weitere Informationen zum Upgrade von Adobe Analytics auf Customer Journey Analytics finden Sie unter [Upgrade auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md). <!-- [Utilizing Adobe Analytics report suite data in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md) --> </p> |
| **Schritt 2: Importien von weiteren Daten in Adobe Experience Platform** | Dieser Schritt, der in Adobe Experience Platform ausgeführt wird, umfasst mehrere Unterschritte:<ul><li>**Schritt 2a: Bereiten Sie Ihr Datenschema vor**: Verwenden Sie das [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=de), um Kundenerlebnisdaten zu [standardisieren und um Schemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=de) für das Customer Experience Management zu definieren.</li><li>**Schritt 2b: Erstellen eines Datensatzes basierend auf dem Schema**: Daten in Platform bestehen aus Datensätzen wie E-Mail-Datensätzen, CRM-Datensätzen, POS-Datensätzen, dem Adobe Analytics-Datensatz usw. Jeder Datensatz umfasst ein Schema und Daten-Batches. Sie können [einen Datensatz in Experience Platform erstellen](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=de).</li><li>**Schritt 2c: Aufnehmen von Daten in Experience Platform**: Hier haben Sie mehrere Möglichkeiten.</li></ul> |
| **Schritt 3: Erstellen Sie Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics** | Mithilfe einer Verbindung können Sie Datensätze aus Adobe Experience Platform in Arbeitsbereich integrieren. Um über Experience Platform-Datensätze zu berichten, müssen Sie zunächst eine Verbindung zwischen den Datensätzen in Experience Platform und Arbeitsbereich herstellen.<br>Siehe [Erstellen oder Bearbeiten einer Verbindung](/help/connections/create-connection.md). |
| **Schritt 4: Erstellen Sie Datenansichten** | Eine Datenansicht ist eine „gefilterte“ Ansicht der Daten. Sie können verschiedene Datenansichten für dieselbe Verbindung mit unterschiedlichen Einstellungen für Besuchs-Timeout, Attribution usw. erstellen. Sie können für einen Datensatz mehrere Datenansichten erstellen.<br>Siehe [Datenansicht erstellen](/help/data-views/create-dataview.md). |
| **Schritt 5: Portieren der Nutzung der Reporting-API**</br> Gilt nur bei der Migration von Adobe Analytics | Die Customer Journey Analytics-Reporting-API weist dasselbe Format auf, verwendet jedoch einen anderen Endpunkt. Portieren Sie die Verwendung der Reporting-API von der Adobe Analytics Reporting-API auf die Customer Journey Analytics Reporting-API. |
| **Schritt 6: Konto für Daten-Feeds- und Data Warehouse-Anwendungsfälle**</br> Gilt nur bei der Migration von Adobe Analytics | Entscheiden Sie, wie Sie die in Customer Journey Analytics verfügbaren Exportoptionen nutzen, um die in Adobe Analytics verwendeten Daten-Feeds- und Data-Warehouse-Funktionen bestmöglich zu replizieren. <!-- link to docs Rob is creating --> |
| **Schritt 7: Migrieren von Projekten und Komponenten**</br> Gilt nur bei der Migration von Adobe Analytics | Der Bereich Komponentenmigration in Adobe Analytics ermöglicht die Migration von Projekten und den zugehörigen Komponenten von Adobe Analytics zu Customer Journey Analytics.<p>Der Migrationsvorgang umfasst:</p><ul><li>Neuerstellung von Adobe Analytics-Projekten in Customer Journey Analytics.</li><li>Zuordnung von Dimensionen und Metriken aus Adobe Analytics-Report Suites zu Dimensionen und Metriken in Customer Journey Analytics-Datenansichten.</li></ul><p>Bevor Sie mit der Migration beginnen, sollten Sie zunächst die [Migration von Komponenten und Projekten von Adobe Analytics zu Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=de) vorbereiten.</p><p>Nachdem Sie alle notwendigen Vorbereitungen getroffen haben, können Sie [Komponenten und Projekte von Adobe Analytics zu Customer Journey Analytics migrieren](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html?lang=de).</p> |
| **Schritt 8: Planen des Onboardings für Benutzende** | Wie in Adobe Analytics ist auch in Customer Journey Analytics der Analysis Workspace das wichtigste Werkzeug für die Benutzenden. Es gibt jedoch einige wesentliche Unterschiede bei der Verwendung von Analysis Workspace in Customer Journey Analytics, die die Benutzenden kennen sollten.<p>Sie sollten Ihren Benutzenden ausreichend Zeit (3–6 Monate) geben, um sich mit den wichtigsten Unterschieden von Analysis Workspace in Customer Journey Analytics vertraut zu machen.</p><p>Informationen zu einigen der wichtigsten Unterschiede zwischen Adobe Analytics und Customer Journey Analytics finden Sie im [Benutzerhandbuch für Adobe Analytics-Benutzende](/help/getting-started/aa-to-cja-user.md).</p> |
| **Schritt 9: Erstellen von Berichten über kanalübergreifende Daten im Arbeitsbereich** | Nachdem Sie Verbindungen und Datenansichten erstellt haben, nutzen Sie die leistungsstarken und flexiblen Funktionen von Analysis Workspace, um Ihre erfassten Daten zu analysieren.<br>Siehe [Einfache Analyse durchführen](/help/analysis-workspace/perform-basic-analysis.md) und [Erweiterte Analyse durchführen](/help/analysis-workspace/perform-adv-analysis.md). |

## Schnellstartanleitungen

Der Abschnitt [Datenaufnahme](../data-ingestion/data-ingestion.md) enthält Schnellstartanleitungen zum obigen Workflow. Diese Schnellstartanleitungen veranschaulichen, wie Daten aus verschiedenen Quellen (einschließlich Adobe Analytics) in Adobe Experience Platform aufgenommen und dann in Customer Journey Analytics verwendet werden.
