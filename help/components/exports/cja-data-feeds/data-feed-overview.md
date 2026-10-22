---
description: Erfahren Sie, wie Sie mit Daten-Feeds Rohdaten auf Ereignisebene aus Customer Journey Analytics exportieren, die Voraussetzungen überprüfen und die Artikel finden, die Sie für die ersten Schritte benötigen.
keywords: Clickstream;Daten-Feed;Daten-Feed;Data Feed
title: Übersicht über Customer Journey Analytics-Daten-Feeds
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
autotag-review: '2026-05-19T08:45:11.428Z'
TQID: 'https://experienceleague.adobe.com/TO8lEW8-GE-sIGj3vmm0X1zCgpg-0VpS1wjs0-HQjg8'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 34959e37a7040bcd861a506968895ad6f051b686
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 1%
---
# Übersicht über Daten-Feeds

{{release-limited-testing}}

Daten-Feeds exportieren Rohdaten auf Ereignisebene von Customer Journey Analytics in ein Cloud-Ziel. Sie können diese Daten auf anderen Plattformen außerhalb von Adobe verwenden, z. B. in einem Data Warehouse.

Daten-Feeds werden aus den Komponenten in einer Datenansicht erstellt. Jede Dimension und Metrik, die Sie einbeziehen, wird zu einer Spalte im Daten-Feed, und Einstellungen der Datenansicht wie Persistenz, abgeleitete Felder und Segmente werden auf die Daten angewendet. Die Dateien werden im Parquet-Format bereitgestellt.

Sie können die folgenden Arten von Daten-Feeds erstellen:

* **Live-Feeds**: Exportieren Sie aktuelle und zukünftige Daten stündlich oder täglich. Jeder Versand wird nach der Stunde oder dem Tag gesendet, an dem die Verarbeitungsverzögerung abgelaufen ist.

* **Aufstockungs-Feeds**: Exportieren Sie historische Daten für einen früheren Datumsbereich.

Einen Vergleich der Daten-Feeds mit anderen Customer Journey Analytics-Exportmethoden, z. B. dem vollständigen Tabellenexport, finden Sie unter [Analytics-Produktvergleich](/help/getting-started/analytics-product-comparison.md).

## Voraussetzungen

Stellen Sie sicher, dass Sie alle folgenden Anforderungen erfüllen, bevor Sie Daten-Feeds verwenden:

* Daten werden in Customer Journey Analytics aufgenommen und eine Verbindung und [Datenansicht](/help/data-views/create-dataview.md) sind konfiguriert. <!-- For more information, see Data ingestion overview - add link -->

* Ihr Konto ist ein Customer Journey Analytics-Produktadministrator oder gehört zu einem Produktprofil mit der Berechtigung [!UICONTROL **Daten-Feeds**] (in der Kategorie [!UICONTROL **Datenansichts-Tools**]) für die Datenansicht, die Sie verwenden möchten. Weitere Informationen finden Sie unter [Zugriffssteuerung](/help/technotes/access-control.md). <!--Add a Data Feeds row to the Data View Tools permissions table in access-control.md.-->

* Ein Cloud-Exportkonto und ein Speicherort sind für [!DNL Amazon S3], [!DNL Google Cloud Platform], [!DNL Azure RBAC] oder [!DNL Azure SAS] konfiguriert. Weitere Informationen finden Sie unter [Konfigurieren von Cloud](/help/components/exports/cloud-export-accounts.md)Exportkonten und [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md).

>[!TIP]
>
>Da Änderungen an Komponenten in einer Datenansicht jeden Daten-Feed betreffen, der sie verwendet, sollten Sie eine Datenansicht erstellen, die nur für Daten-Feeds verwendet wird.
>
>* **Vorteil**: Verringert das Risiko, dass Änderungen, die für Analysis Workspace-Berichte vorgenommen werden, unerwartet die Daten-Feed-Ausgabe ändern.
>
>* **Nachteil**: Sie müssen die zusätzliche Datenansicht neben Ihren anderen Datenansichten beibehalten.

## Erste Schritte

Verwenden Sie die folgenden Artikel, um Ihre Daten-Feeds zu planen, zu migrieren und zu erstellen.

### Planen von Daten-Feeds

* [Vergleichen von Daten-Feeds in Customer Journey Analytics und Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md): Verstehen Sie Unterschiede bei Funktionen und Konzepten, wenn Sie zuvor Adobe Analytics-Daten-Feeds verwendet haben.

* [Datendiskrepanzen zwischen Daten-Feeds und Analysis Workspace verstehen](/help/components/exports/cja-data-feeds/df-comparison-workspace.md): Erfahren Sie, warum die Daten-Feed-Ausgabe möglicherweise nicht mit Berichten in Analysis Workspace übereinstimmt.

* [Komponentenverfügbarkeit in Daten-Feeds](/help/components/exports/cja-data-feeds/df-components.md): Erfahren Sie, welche Dimensionen und Metriken in Daten-Feeds erforderlich, nicht unterstützt oder eingeschränkt sind.

### Migrieren von Adobe Analytics-Daten-Feeds

1. [Vorbereiten der Zuordnung von Daten-Feed-Spalten](/help/components/exports/cja-data-feeds/df-column-mapping-prep.md): Verstehen Sie die Faktoren, die die Zuordnung von Adobe Analytics-Spalten zu Customer Journey Analytics beeinflussen.

1. [Zuordnen von Adobe Analytics-Daten-Feed-Spalten zu Customer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md): Suchen Sie das Customer Journey Analytics-Äquivalent jeder Adobe Analytics-Spalte, die Sie beibehalten möchten.

### Erstellen und Konfigurieren von Daten-Feeds

* [Erstellen eines Daten-Feeds](/help/components/exports/cja-data-feeds/create-feed.md): Wählen Sie Komponenten aus, konfigurieren Sie den Zeitplan und richten Sie den Versand ein.

* [Segmentierung in Daten-Feeds](/help/components/exports/cja-data-feeds/df-segmentation.md): Anwenden von Segmenten zum Filtern der Daten in einem Daten-Feed.

* [Datenumwandlungen anwenden](/help/components/exports/cja-data-feeds/df-data-transformations.md): Umwandeln von Daten mithilfe von Komponenteneinstellungen, abgeleiteten Feldern oder SQL.

* [Komponenten von Unterereignissen in Daten-Feeds](/help/components/exports/cja-data-feeds/df-sub-event.md): Erfahren Sie, wie Komponenten aus Arrays und Zuordnungen exportiert werden und wie Sie sie abfragen können.

