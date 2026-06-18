---
title: Schnellstartanleitung für Customer Journey Analytics B2B
description: Schnellstartanleitung für die B2B Edition von Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
TQID: https://experienceleague.adobe.com/SjixkRCOmeUYuhZCVO7-7tLHalpnXO6QCVE1BiG9h2E
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: a67cb189-a535-41f6-afa2-448f39c4759f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 9c87ce4fb30c7d1d66ce88174443369ef44a7377
workflow-type: tm+mt
source-wordcount: 499
ht-degree: 77%

---

# Schnellstartanleitung für B2B Edition

Um die Customer Journey Analytics B2B Edition zu implementieren, müssen Sie zunächst die B2B-spezifischen Konzepte und Funktionen verstehen. Außerdem sollten Sie mit dem herkömmlichen Workflow zur Implementierung von Customer Journey Analytics vertraut sein.

Dieses Dokument konzentriert sich auf den Workflow, der für die Implementierung von Customer Journey Analytics spezifisch ist.

## Voraussetzungen

Für die Implementierung der Customer Journey Analytics B2B Edition gelten die folgenden Voraussetzungen:

* Sie verfügen über die erforderliche(n) [Zugriffssteuerung und Berechtigungen](/help/technotes/access-control.md), um Verwaltungsaufgaben in Customer Journey Analytics bereitzustellen.
* Sie haben das Add-on-Paket für die Customer Journey Analytics B2B Edition erworben.


## Workflow

| Aufgabe | Details |
| --- | --- |
| **Schritt 1: B2B-Daten in Experience Platform importieren** | Dieser Schritt, der in Experience Platform ausgeführt wird, umfasst mehrere Unterschritte:<ul><li>**Schritt 1a: Datenschema vorbereiten**: Verwenden Sie das [Adobe Experience-Datenmodell (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=de), um B2B-Daten zu standardisieren und um für Ihre B2B-Daten [Schemata zu definieren](https://experienceleague.adobe.com/de/docs/experience-platform/rtcdp/schemas/b2b).<br/>Sie können Ihre Schemata auf den [Standardklassen basieren, die in Real-Time CDP B2B edition bereitgestellt werden](https://experienceleague.adobe.com/de/docs/experience-platform/rtcdp/schemas/b2b) oder Sie können Ihre eigenen benutzerdefinierten Klassen und Schemata verwenden. Die [Anwendungsfälle](/help/use-cases/b2b/b2b-edition/use-cases-overview.md)-Artikel verwenden Real-Time CDP B2B edition-Klassen und -Schemata. Eine Real-Time CDP B2B edition-Lizenz ist jedoch nicht erforderlich, um die Standardklassen und -schemata zu verwenden.</li><li>**Schritt 1b: Einen Datensatz basierend auf dem Schema erstellen**: Daten in Platform bestehen aus Datensätzen wie Kontodaten, Opportunity-Daten, Käufergruppendaten, Kampagnendaten, Daten zu Marketing-Listen, E-Mail-Datensätzen, CRM-Datensätzen, POS-Datensätzen und mehr. Jeder Datensatz umfasst ein Schema und Daten-Batches. Sie können [einen Datensatz in Experience Platform erstellen](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=de).</li><li>**Schritt 1c: Daten in Experience Platform aufnehmen**: Hier haben Sie [mehrere Möglichkeiten](https://experienceleague.adobe.com/de/docs/experience-platform/ingestion/home).</li></ul> |
| **Schritt 2: Erstellen Sie Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics** | Mithilfe einer Verbindung können Sie Datensätze aus Adobe Experience Platform in Arbeitsbereich integrieren. Um über Experience Platform-Datensätze zu berichten, müssen Sie zunächst eine Verbindung zwischen den Datensätzen in Experience Platform und Workspace herstellen. Beim Konfigurieren einer Verbindung mit der B2B Eedition stehen Ihnen zusätzliche Optionen zur Verfügung. <br>Siehe [Erstellen oder Bearbeiten einer Verbindung](/help/connections/create-connection.md). |
| **Schritt 3: Erstellen Sie Datenansichten** | Eine Datenansicht ist eine *gefilterte* Ansicht der Daten. Sie können verschiedene Datenansichten für dieselbe Verbindung mit unterschiedlichen Einstellungen für Besuchs-Timeout, Attribution und mehr erstellen. Sie können für einen Datensatz mehrere Datenansichten erstellen. Wenn Sie eine Datenansicht konfigurieren, verfügen Sie über zusätzliche Optionen, wenn Sie die B2B edition verwenden<br>Siehe [Erstellen einer Datenansicht](/help/data-views/create-dataview.md). |
| **Schritt 4: Erstellen von Berichten über kanalübergreifende Daten im Arbeitsbereich** | Nachdem Sie Verbindungen und Datenansichten erstellt haben, nutzen Sie die leistungsstarken und flexiblen Funktionen von Analysis Workspace, um die eingebrachten B2B-Daten zu analysieren.<br>Siehe [Durchführen grundlegender &#x200B;](/help/analysis-workspace/perform-basic-analysis.md) und [Durchführen erweiterter &#x200B;](/help/analysis-workspace/perform-adv-analysis.md). |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->