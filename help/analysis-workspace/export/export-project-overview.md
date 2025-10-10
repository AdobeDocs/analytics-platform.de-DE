---
description: Erfahren Sie mehr über die für den Export aus Analysis Workspace verfügbaren Methoden.
keywords: Analysis Workspace
title: Exportieren von Projektdaten
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 100%

---

# Exportübersicht

Sie können Customer Journey Analytics-Projekte (oder Teile von ihnen) aus Analysis Workspace exportieren. Der Export von Customer Journey Analytics-Berichten kann verschiedene Gründe haben, z. B. die Verwendung in Drittanbieter-Tools oder die Kombination mit externen Daten.

In den folgenden Abschnitten werden die unterstützten Dateitypen, die verschiedenen, für den Export verfügbaren Methoden und die Vorteile jeder Methode beschrieben.

## Unterstützte Dateitypen:

Sie können Customer Journey Analytics-Berichte als PDF-, CSV- oder JSON-Datei exportieren.

* **PDF:** Bietet eine einfache Möglichkeit, visuelle Daten für Stakeholder freizugeben. Die PDF-Datei enthält alle angezeigten (sichtbaren) Tabellen und Visualisierungen im Projekt.

* **CSV:** Ermöglicht die Anzeige von Rohdaten in einer Tabellenanwendung wie Excel. CSV-Dateien enthalten Daten in Textform.

* **JSON:** Bietet ein offenes Standarddateiformat für die Datenfreigabe.

## Exportmethoden

Für den Export aus Analysis Workspace stehen Ihnen verschiedene Methoden zur Verfügung. Überlegen Sie bei der Auswahl einer Exportmethode, was Sie exportieren möchten und wer auf die exportierten Daten zugreifen muss.

| Exportmethode | Verwenden Sie diese Methode, wenn Sie … |
|---------|----------|
| [Auf Ihre Workstation herunterladen](/help/analysis-workspace/export/download-send.md) | <li>Projekte auf Ihre persönliche Workstation herunterladen.</li><li>Nur ungeplant Daten herunterladen.</li> <li>Maximal 50.000 Zeilen herunterladen.</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [An andere Benutzende senden](/help/analysis-workspace/export/t-schedule-report.md) | <li>Exportierte Customer Journey Analytics-Daten per E-Mail an andere Benutzende in Ihrer Organisation senden.</li><li>Die E-Mail ungeplant oder geplant senden.</li> <li>Die E-Mail maximal 50.000 Zeilen enthält.</li> <!--true?--> |
| [Exportieren in einen Cloud-Speicherort](/help/analysis-workspace/export/export-cloud.md) | <li>In einen Cloud-Speicherort exportieren, z. B. <ul><li>Adobe Experience Platform Data Landing Zone</li><li>Google Cloud Platform</li><li>Microsoft Azure</li><li>Amazon S3</li><li>Snowflake</li></ul></li><li>Daten ungeplant oder geplant exportieren.</li><li>Größere Mengen an Customer Journey Analytics-Daten speichern.</li><li>Vollständige Tabellen exportieren, die Tausende oder Millionen von Zeilen enthalten.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
