---
title: Schnellstartanleitung für Customer Journey Analytics B2B
description: Schnellstartanleitung für die B2B Edition von Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
source-git-commit: 326a82e93c0c8d57db224023ed5f3a7ab94a8997
workflow-type: ht
source-wordcount: '396'
ht-degree: 100%

---


# Schnellstartanleitung für B2B Edition

{{draft-b2b}}

Um die Customer Journey Analytics B2B Edition zu implementieren, müssen Sie zunächst die B2B-spezifischen Konzepte und Funktionen verstehen. Außerdem sollten Sie mit dem herkömmlichen Workflow zur Implementierung von Customer Journey Analytics vertraut sein.

Dieses Dokument konzentriert sich auf den Workflow, der für die Implementierung von Customer Journey Analytics spezifisch ist.

## Voraussetzungen

Für die Implementierung der Customer Journey Analytics B2B Edition gelten die folgenden Voraussetzungen:

* Sie verfügen über die erforderliche(n) [Zugriffssteuerung und Berechtigungen](/help/technotes/access-control.md), um Verwaltungsaufgaben in Customer Journey Analytics bereitzustellen.
* Sie haben das Add-on-Paket für die Customer Journey Analytics B2B Edition erworben.


## Workflow

| Aufgabe | Details |
| --- | --- |
| **Schritt 1: B2B-Daten in Experience Platform importieren** | Dieser Schritt, der in Experience Platform ausgeführt wird, umfasst mehrere Unterschritte:<ul><li>**Schritt 1a: Datenschema vorbereiten**: Verwenden Sie das [Adobe Experience-Datenmodell (XDM)](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/home), um B2B-Daten zu standardisieren und um für Ihre B2B-Daten [Schemata zu definieren](https://experienceleague.adobe.com/de/docs/experience-platform/rtcdp/schemas/b2b).</li><li>**Schritt 1b: Einen Datensatz basierend auf dem Schema erstellen**: Daten in Platform bestehen aus Datensätzen wie Kontodaten, Opportunity-Daten, Käufergruppendaten, Kampagnendaten, Daten zu Marketing-Listen, E-Mail-Datensätzen, CRM-Datensätzen, POS-Datensätzen und mehr. Jeder Datensatz umfasst ein Schema und Daten-Batches. Sie können [einen Datensatz in Experience Platform erstellen](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=de).</li><li>**Schritt 1c: Daten in Experience Platform aufnehmen**: Hier haben Sie [mehrere Möglichkeiten](https://experienceleague.adobe.com/de/docs/experience-platform/ingestion/home).</li></ul> |
| **Schritt 2: Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics herstellen** | Mithilfe einer Verbindung können Sie Datensätze aus Adobe Experience Platform in Arbeitsbereich integrieren. Um über Experience Platform-Datensätze zu berichten, müssen Sie zunächst eine Verbindung zwischen den Datensätzen in Experience Platform und Workspace herstellen. Beim Konfigurieren einer Verbindung mit der B2B Eedition stehen Ihnen zusätzliche Optionen zur Verfügung. <br>Siehe [Erstellen oder Bearbeiten einer Verbindung](/help/connections/create-connection.md). |
| **Schritt 3: Datenansichten erstellen** | Eine Datenansicht ist eine *gefilterte* Ansicht der Daten. Sie können verschiedene Datenansichten für dieselbe Verbindung mit unterschiedlichen Einstellungen für Besuchs-Timeout, Attribution und mehr erstellen. Sie können für einen Datensatz mehrere Datenansichten erstellen. Beim Konfigurieren einer Datenansicht mit der B2B Eedition stehen Ihnen zusätzliche Optionen zur Verfügung. <br>Siehe [Datenansicht erstellen](/help/data-views/create-dataview.md). |
| **Schritt 4: Berichte über kanalübergreifende Daten in Arbeitsbereich erstellen** | Nachdem Sie Verbindungen und Datenansichten erstellt haben, nutzen Sie die leistungsstarken und flexiblen Funktionen von Analysis Workspace, um Ihre erfassten B2B-Daten zu analysieren.<br>Siehe [Durchführen einer grundlegenden Analyse](/help/analysis-workspace/perform-basic-analysis.md) und [Durchführen einer erweiterten Analyse](/help/analysis-workspace/perform-adv-analysis.md). |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->