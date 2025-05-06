---
title: Customer Journey Analytics B2B-Schnellstartanleitung
description: Schnellstartanleitung für die B2B edition von Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B edition"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
source-git-commit: 326a82e93c0c8d57db224023ed5f3a7ab94a8997
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 22%

---


# B2B edition-Schnellstartanleitung

{{draft-b2b}}

Um Customer Journey Analytics B2B edition zu implementieren, müssen Sie zunächst die B2B-spezifischen Konzepte und Funktionen verstehen. Außerdem sollten Sie mit dem herkömmlichen Workflow zur Implementierung von Customer Journey Analytics vertraut sein.

Dieses Dokument konzentriert sich auf den Workflow, der für die Implementierung von Customer Journey Analytics spezifisch ist.

## Voraussetzungen

Für die Implementierung von Customer Journey Analytics B2B edition gelten die folgenden Voraussetzungen:

* Sie verfügen nicht über die erforderlichen [Zugriffssteuerungs- und ](/help/technotes/access-control.md)), um Verwaltungsaufgaben in Customer Journey Analytics bereitzustellen.
* Sie haben das Add-on-Paket für Customer Journey Analytics B2B edition erworben.


## Workflow

| Aufgabe | Details |
| --- | --- |
| **Schritt 1: Importieren Sie B2B-Daten in Experience Platform** | Dieser Schritt, der in Experience Platform ausgeführt wird, umfasst mehrere Unterschritte:<ul><li>**Schritt 1a: Bereiten Sie Ihr Datenschema vor**: Verwenden Sie das [Adobe Experience-Datenmodell (XDM)](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/home), um B2B-Daten zu standardisieren und [Schemas zu definieren](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/schemas/b2b) für Ihre B2B-Daten.</li><li>**Schritt 1b: Erstellen Sie einen Datensatz basierend auf dem Schema**: Daten in Platform bestehen aus Datensätzen wie Kontodaten, Opportunity-Daten, Einkaufsgruppendaten, Kampagnendaten, Marketing-Listendaten, E-Mail-Datensätzen, CRM-Datensätzen, POS-Datensätzen und mehr. Jeder Datensatz umfasst ein Schema und Daten-Batches. Sie können [einen Datensatz in Experience Platform erstellen](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=de).</li><li>**Schritt 1c: Nehmen Sie Daten in Experience Platform auf**: Sie haben [mehrere Optionen](https://experienceleague.adobe.com/de/docs/experience-platform/ingestion/home).</li></ul> |
| **Schritt 2: Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics herstellen** | Mithilfe einer Verbindung können Sie Datensätze aus Adobe Experience Platform in Arbeitsbereich integrieren. Um über Experience Platform-Datensätze zu berichten, müssen Sie zunächst eine Verbindung zwischen den Datensätzen in Experience Platform und Workspace herstellen. Beim Konfigurieren einer Verbindung mit der B2B edition stehen Ihnen zusätzliche Optionen zur Verfügung. <br>Siehe [Erstellen oder Bearbeiten einer Verbindung](/help/connections/create-connection.md). |
| **Schritt 3: Datenansichten erstellen** | Eine Datenansicht ist eine *gefilterte* Ansicht der Daten. Sie können verschiedene Datenansichten für dieselbe Verbindung mit unterschiedlichen Einstellungen für Besuchs-Timeout, Attribution usw. erstellen. Sie können für einen Datensatz mehrere Datenansichten erstellen. Sie haben zusätzliche Optionen, wenn Sie eine Datenansicht konfigurieren, wenn Sie die B2B edition haben.<br>Siehe [Datenansicht erstellen](/help/data-views/create-dataview.md). |
| **Schritt 4: Berichte über kanalübergreifende Daten in Arbeitsbereich erstellen** | Nachdem Sie Verbindungen und Datenansichten erstellt haben, analysieren Sie die eingebrachten B2B-Daten mithilfe der Leistungsfähigkeit und Flexibilität von Analysis Workspace.<br>Siehe [Einfache Analyse durchführen](/help/analysis-workspace/perform-basic-analysis.md) und [Erweiterte Analyse durchführen](/help/analysis-workspace/perform-adv-analysis.md). |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->