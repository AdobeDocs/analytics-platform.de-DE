---
description: die für den Export aus Analysis Workspace verfügbaren Methoden verstehen.
keywords: Analysis Workspace
title: Exportieren von Projektdaten
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 1%

---

# Exportübersicht

Sie können Customer Journey Analytics-Berichte aus Analysis Workspace exportieren. Der Export von Customer Journey Analytics-Berichten kann verschiedene Gründe haben, z. B. die Verwendung in Drittanbieter-Tools oder die Kombination mit externen Daten.

In den folgenden Abschnitten werden die unterstützten Dateitypen, die verschiedenen für den Export verfügbaren Methoden und die Vorteile jeder Methode beschrieben.

## Unterstützte Dateitypen

Sie können Customer Journey Analytics-Berichte als PDF-, CSV- oder JSON-Datei exportieren.

* **PDF:** Bietet eine einfache Möglichkeit, visuelle Daten für Stakeholder freizugeben. PDF-Dateien enthalten alle angezeigten (sichtbaren) Tabellen und Visualisierungen im Projekt.

* **CSV:** Ermöglicht die Anzeige von Rohdaten in einer Tabellenkalkulationsanwendung wie Excel. CSV-Dateien enthalten Daten im Klartext.

* **JSON:** Bietet ein offenes Standarddateiformat für die Datenfreigabe.

## Exportmethoden

Beim Exportieren aus Analysis Workspace stehen verschiedene Methoden zur Verfügung. Überlegen Sie bei der Auswahl einer Exportmethode, was Sie exportieren möchten und wer darauf zugreifen muss.

| Exportmethode | Vorteile |
|---------|----------|
| [Auf Workstation herunterladen](/help/analysis-workspace/export/download-send.md) | Verwenden Sie diese Methode, wenn Sie: <ul><li>Projekte auf Ihre persönliche Workstation herunterladen.</li><li>Downloads sind nur ad hoc (können nicht geplant werden).</li> <li>Insgesamt 50.000 Zeilen herunterladen.</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [An andere Benutzer senden](/help/analysis-workspace/export/t-schedule-report.md) | Verwenden Sie diese Methode, wenn Sie: <ul><li>Exportierte Customer Journey Analytics-Daten per E-Mail an andere Benutzende in Ihrem Unternehmen senden.</li><li>Kann ad hoc oder nach einem Zeitplan sein.</li> <li>Schließen Sie insgesamt 50.000 Zeilen ein.</li> <!--true?--> |
| [An eine Cloud-Anwendung senden](/help/analysis-workspace/export/export-cloud.md) | Verwenden Sie diese Methode, wenn Sie: <ul><li>Exportieren Sie an einen freigegebenen Speicherort, z. B. Adobe Experience Platform Data Landing Zone, Google Cloud Platform, Microsoft Azure, Amazon S3 oder Snowflake.</li><li>Kann ad hoc oder nach einem Zeitplan sein.</li><li>Speichern Sie größere Mengen an Customer Journey Analytics-Daten.</li><li>Exportieren Sie vollständige Tabellen, die Tausende oder Millionen von Zeilen enthalten.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
