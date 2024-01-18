---
title: Customer Journey Analytics – Erste Schritte
description: Machen Sie sich mit den Voraussetzungen und dem Workflow vertraut, die für die Implementierung von Customer Journey Analytics erforderlich sind.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: bfaf76fa5f225e9aa3153fc4ee10c5be8f3164e7
workflow-type: ht
source-wordcount: '459'
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
| **Schritt 1: Wenn Sie Ihre Daten von Adobe Analytics zu Customer Journey Analytics migrieren, migrieren Sie Ihre Daten und replizieren Ihre Projekte.** | Informationen zur Datenmigration von Adobe Analytics zu Customer Journey Analytics finden Sie unter: <ul><li>[Verwenden von Daten aus Report Suites in Adobe Analytics in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md)</li><li>[Aufnehmen und Verwenden von Daten aus Adobe Analytics](../data-ingestion/analytics.md)</li></ul><p>Informationen zum Replizieren Ihrer Adobe Analytics-Projekte in Customer Journey Analytics sowie zum Zuordnen von Projektkomponenten aus einer Report Suite in Adobe Analytics zu einer Datenansicht von Customer Journey Analytics finden Sie unter:</p><ul><li>[Migrieren von Komponenten und Projekten von Adobe Analytics zu Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration.html?lang=de)</li></ul> |
| **Schritt 2: Importien von weiteren Daten in Adobe Experience Platform** | Dieser Schritt, der in Adobe Experience Platform ausgeführt wird, umfasst mehrere Unterschritte:<ul><li>**Schritt 2a: Bereiten Sie Ihr Datenschema vor**: Verwenden Sie das [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=de), um Kundenerlebnisdaten zu [standardisieren und um Schemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=de) für das Customer Experience Management zu definieren.</li><li>**Schritt 2b: Erstellen eines Datensatzes basierend auf dem Schema**: Daten in Platform bestehen aus Datensätzen wie E-Mail-Datensätzen, CRM-Datensätzen, POS-Datensätzen, dem Adobe Analytics-Datensatz usw. Jeder Datensatz umfasst ein Schema und Daten-Batches. Sie können [einen Datensatz in Experience Platform erstellen](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=de).</li><li>**Schritt 2c: Aufnehmen von Daten in Experience Platform**: Hier haben Sie mehrere Möglichkeiten.</li></ul> |
| **Schritt 3: Erstellen Sie Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics** | Mithilfe einer Verbindung können Sie Datensätze aus Adobe Experience Platform in Arbeitsbereich integrieren. Um über Experience Platform-Datensätze zu berichten, müssen Sie zunächst eine Verbindung zwischen den Datensätzen in Experience Platform und Arbeitsbereich herstellen.<br>Siehe [Erstellen oder Bearbeiten einer Verbindung](/help/connections/create-connection.md). |
| **Schritt 4: Erstellen Sie Datenansichten** | Eine Datenansicht ist eine „gefilterte“ Ansicht der Daten. Sie können verschiedene Datenansichten für dieselbe Verbindung mit unterschiedlichen Einstellungen für Besuchs-Timeout, Attribution usw. erstellen. Sie können für einen Datensatz mehrere Datenansichten erstellen.<br>Siehe [Datenansicht erstellen](/help/data-views/create-dataview.md). |
| **Schritt 5: Erstellen Sie Berichte über kanalübergreifende Daten im Arbeitsbereich** | Nachdem Sie Verbindungen und Datenansichten erstellt haben, nutzen Sie die leistungsstarken und flexiblen Funktionen von Analysis Workspace, um Ihre erfassten Daten zu analysieren.<br>Siehe [Einfache Analyse durchführen](/help/analysis-workspace/perform-basic-analysis.md) und [Erweiterte Analyse durchführen](/help/analysis-workspace/perform-adv-analysis.md). |

## Schnellstartanleitungen

Der Abschnitt [Datenaufnahme](../data-ingestion/data-ingestion.md) enthält Schnellstartanleitungen zum obigen Workflow. Diese Schnellstartanleitungen veranschaulichen, wie Daten aus verschiedenen Quellen (einschließlich Adobe Analytics) in Adobe Experience Platform aufgenommen und dann in Customer Journey Analytics verwendet werden.
