---
title: Customer Journey Analytics – Erste Schritte
description: Machen Sie sich mit den Voraussetzungen und dem Workflow vertraut, die für die Implementierung von Customer Journey Analytics erforderlich sind.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 7bc4425f11980780ab64a201029cd63e4bd7849c
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 51%

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
| **Schritt 1: Migrieren von Adobe Analytics zu Customer Journey Analytics: Wählen Sie einen Migrationspfad aus und senden Sie Daten an Adobe Experience Platform** | Für die Migration von Adobe Analytics zu Customer Journey Analytics stehen verschiedene Pfade zur Verfügung. Jeder mögliche Migrationspfad hat seine eigenen Vor- und Nachteile, und ein Pfad, der für eine Organisation richtig ist, ist für eine andere Organisation möglicherweise nicht sinnvoll. <p>Informationen zum Starten der Migration von Adobe Analytics zu Customer Journey Analytics finden Sie unter [Erste Schritte mit der Migration auf Customer Journey Analytics](/help/getting-started/cja-migration/cja-migration-getstarted.md). <!-- [Utilizing Adobe Analytics report suite data in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md) --> </p> |
| **Schritt 2: Importien von weiteren Daten in Adobe Experience Platform** | Dieser Schritt, der in Adobe Experience Platform ausgeführt wird, umfasst mehrere Unterschritte:<ul><li>**Schritt 2a: Bereiten Sie Ihr Datenschema vor**: Verwenden Sie das [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=de), um Kundenerlebnisdaten zu [standardisieren und um Schemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=de) für das Customer Experience Management zu definieren.</li><li>**Schritt 2b: Erstellen eines Datensatzes basierend auf dem Schema**: Daten in Platform bestehen aus Datensätzen wie E-Mail-Datensätzen, CRM-Datensätzen, POS-Datensätzen, dem Adobe Analytics-Datensatz usw. Jeder Datensatz umfasst ein Schema und Daten-Batches. Sie können [einen Datensatz in Experience Platform erstellen](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=de).</li><li>**Schritt 2c: Aufnehmen von Daten in Experience Platform**: Hier haben Sie mehrere Möglichkeiten.</li></ul> |
| **Schritt 3: Erstellen Sie Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics** | Mithilfe einer Verbindung können Sie Datensätze aus Adobe Experience Platform in Arbeitsbereich integrieren. Um über Experience Platform-Datensätze zu berichten, müssen Sie zunächst eine Verbindung zwischen den Datensätzen in Experience Platform und Arbeitsbereich herstellen.<br>Siehe [Erstellen oder Bearbeiten einer Verbindung](/help/connections/create-connection.md). |
| **Schritt 4: Erstellen Sie Datenansichten** | Eine Datenansicht ist eine „gefilterte“ Ansicht der Daten. Sie können verschiedene Datenansichten für dieselbe Verbindung mit unterschiedlichen Einstellungen für Besuchs-Timeout, Attribution usw. erstellen. Sie können für einen Datensatz mehrere Datenansichten erstellen.<br>Siehe [Datenansicht erstellen](/help/data-views/create-dataview.md). |
| **Schritt 5: Portieren der Nutzung der Reporting-API**</br> Gilt nur bei der Migration von Adobe Analytics | Die Customer Journey Analytics Reporting-API weist dasselbe Format auf, verwendet jedoch einen anderen Endpunkt. Portieren Sie die Nutzung der Reporting-API von der Adobe Analytics Reporting-API an die Customer Journey Analytics-Reporting-API. |
| **Schritt 6: Berücksichtigen Sie Datenfeeds und Data Warehouse-Anwendungsfälle.**</br> Gilt nur bei der Migration von Adobe Analytics | Entscheiden Sie, wie Sie die in Customer Journey Analytics verfügbaren Exportoptionen verwenden werden, um die Daten-Feeds und Data Warehouse-Funktionen, die Sie in Adobe Analytics verwendet haben, am besten zu replizieren. <!-- link to docs Rob is creating --> |
| **Schritt 7: Migrieren von Projekten und Komponenten**</br> Gilt nur bei der Migration von Adobe Analytics | Im Bereich Komponentenmigration in Adobe Analytics können Sie Projekte und die zugehörigen Komponenten von Adobe Analytics auf Customer Journey Analytics migrieren.<p>Informationen zum Replizieren Ihrer Adobe Analytics-Projekte in Customer Journey Analytics sowie zum Zuordnen von Projektkomponenten von einer Adobe Analytics Report Suite zu einer Customer Journey Analytics-Datenansicht finden Sie unter [Migrieren von Komponenten und Projekten von Adobe Analytics zum Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration.html?lang=de).</p> |
| **Schritt 8: BenutzerOnboarding planen** | Wie in Adobe Analytics ist Analysis Workspace das wichtigste Tool für die Benutzer im Customer Journey Analytics. Es gibt jedoch einige wesentliche Unterschiede bei der Verwendung von Analysis Workspace in Customer Journey Analytics, die die Benutzer kennen müssen.<p>Sie sollten Ihren Benutzern ausreichend Zeit (3 - 6 Monate) geben, um sich mit den wichtigsten Unterschieden von Analysis Workspace im Customer Journey Analytics vertraut zu machen.</p><p>Informationen zu einigen der wichtigsten Unterschiede zwischen Adobe Analytics und Customer Journey Analytics finden Sie unter [Benutzerhandbuch für Adobe Analytics-Benutzer](/help/getting-started/aa-to-cja-user.md).</p> |
| **Schritt 9: Erstellen Sie Berichte über kanalübergreifende Daten im Arbeitsbereich** | Nachdem Sie Verbindungen und Datenansichten erstellt haben, nutzen Sie die leistungsstarken und flexiblen Funktionen von Analysis Workspace, um Ihre erfassten Daten zu analysieren.<br>Siehe [Einfache Analyse durchführen](/help/analysis-workspace/perform-basic-analysis.md) und [Erweiterte Analyse durchführen](/help/analysis-workspace/perform-adv-analysis.md). |

## Schnellstartanleitungen

Der Abschnitt [Datenaufnahme](../data-ingestion/data-ingestion.md) enthält Schnellstartanleitungen zum obigen Workflow. Diese Schnellstartanleitungen veranschaulichen, wie Daten aus verschiedenen Quellen (einschließlich Adobe Analytics) in Adobe Experience Platform aufgenommen und dann in Customer Journey Analytics verwendet werden.
