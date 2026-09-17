---
title: Vollständige Customer Journey Analytics-Exporttabelle
description: Beschreibt, wie Sie die Funktion „Vollständige Tabelle exportieren“ verwenden können, um Ihre Daten zu validieren oder Ihre Daten für KI/ML zu verwenden.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: ee004948-3025-434b-a90b-8aa185800820
autotag-review: '2026-05-19T09:39:35.989Z'
TQID: 'https://experienceleague.adobe.com/5lP3PKpCpxkeyH34327gieZ48KFkEai4DF2SC0H4E2U'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
  - id: f24857a4-4b64-4b25-b237-d43026362144
    internal-label: BI extension
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 4%
---
# Exportieren einer vollständigen Tabelle

In diesem Artikel wird beschrieben, wie die [!DNL Export full table]-Funktion verwendet werden kann, um den folgenden [Anwendungsfall für den Datenexport“ zu &#x200B;](overview.md):

* Datenvalidierung
* Bereitschaft für KI/ML

## Einführung

Durch den Export von Daten mit [!DNL Customer Journey Analytics Full Table Export] können Sie Daten aus Ihren Freiformtabellen in Customer Journey Analytics Analysis Workspace exportieren.

![BI-Erweiterung](../assets/export-full-table.png)

## Weitere Informationen

Um den gesamten Inhalt einer Freiformtabelle, die Sie in Analysis Workspace erstellen, direkt in bestimmte Cloud-Ziele zu exportieren, verwenden Sie die Funktion „Vollständige Tabelle exportieren“.

Die vollständige Exporttabelle unterstützt bis zu 10 Dimensionen und 10 Metriken pro Bericht und enthält berechnete Metriken und die Segmentierung. Abhängig von Ihrer Lizenzstufe können Sie pro Export 3 Millionen, 30 Millionen, 150 Millionen oder 300 Millionen Zeilen exportieren, was das Limit von 50.000 Zeilen anderer Exportmethoden überschreitet. Zu den unterstützten Zielen gehören Adobe Experience Platform Data Landing Zone, Google Cloud Platform, Microsoft Azure, Amazon S3 und Snowflake. Weitere [&#x200B; finden Sie unter „Vorteile &#x200B;](/help/analysis-workspace/export/export-cloud.md#advantages) Tabellenexports“.

Weitere Informationen finden Sie in der ausführlichen Dokumentation unter [Exportieren von Customer Journey Analytics-Berichten in die Cloud](/help/analysis-workspace/export/export-cloud.md).
