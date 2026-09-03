---
description: Erfahren Sie mehr über die für den Export aus Analysis Workspace verfügbaren Methoden.
keywords: Analysis Workspace
title: Exportieren von Projektdaten
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
autotag-review: '2026-05-19T08:26:15.356Z'
TQID: 'https://experienceleague.adobe.com/9pyrzsluOss-Dz4yrDJAmVqxjjeiEYTNILIz4llAMPA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 299
ht-degree: 96%

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
| [Auf Ihre Workstation herunterladen](/help/analysis-workspace/export/download-send.md) | <li>Projekte auf Ihre persönliche Workstation herunterladen.</li><li>Nur ungeplant Daten herunterladen.</li> <li>Maximal 50.000 Zeilen herunterladen.</li> <!--true? Are there 2 different options to download to your workstation? is this emailing it? --> |
| [An andere Benutzende senden](/help/analysis-workspace/export/t-schedule-report.md) | <li>Exportierte Customer Journey Analytics-Daten per E-Mail an andere Benutzende in Ihrer Organisation senden.</li><li>Die E-Mail ungeplant oder geplant senden.</li> <li>Binden Sie maximal 400 Zeilen in die E-Mail ein.</li> <!--true?--> |
| [Exportieren in einen Cloud-Speicherort](/help/analysis-workspace/export/export-cloud.md) | <li>In einen Cloud-Speicherort exportieren, z. B. <ul><li>Adobe Experience Platform Data Landing Zone</li><li>Google Cloud Platform</li><li>Microsoft Azure</li><li>Amazon S3</li><li>Snowflake</li></ul></li><li>Daten ungeplant oder geplant exportieren.</li><li>Größere Mengen an Customer Journey Analytics-Daten speichern.</li><li>Vollständige Tabellen exportieren, die Tausende oder Millionen von Zeilen enthalten.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
