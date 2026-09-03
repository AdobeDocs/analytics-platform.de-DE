---
title: Segmentierung in Daten-Feeds
description: Erfahren Sie, wie Sie Segmente auf Customer Journey Analytics-Daten-Feeds anwenden und verstehen, wie Datumsbereichssegmente mit dem Berichtsfenster des Feeds interagieren.
keywords: Clickstream;Daten-Feed;Daten-Feed;Segmentierung;Segmente;Datumsbereich
feature: Components
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: c7fc5df2a0fd7393b48bfe6bdfa7dccdfffde46c
workflow-type: tm+mt
source-wordcount: 357
ht-degree: 0%

---


# Segmentierung in Daten-Feeds

{{release-limited-testing}}

Daten-Feeds in Customer Journey Analytics unterstützen die Segmentierung, sodass Sie filtern können, welche Zeilen in jedem Feed-Versand enthalten sind. Sie können Segmente auf Datenansichtsebene, Feed-Ebene oder auf beides anwenden.

## Wo Segmente angewendet werden

Segmente können an zwei Stellen auf einen Daten-Feed angewendet werden:

- **Datenansicht**: Ein in der Datenansicht konfiguriertes Segment, das für alle Feeds gilt, die diese Datenansicht verwenden.
- **Datenfeed**: Ein Segment, das zusätzlich zu einem Datenansichtssegment direkt auf einen einzelnen Feed angewendet wird.

Wenn beide konfiguriert sind, kombiniert Customer Journey Analytics sie - nur Zeilen, die beide Segmente erfüllen, werden in die Feed-Ausgabe aufgenommen.

## Segmente, die einen Datumsbereich enthalten

Sie können Segmente verwenden, die Datumsbereiche in einem Daten-Feed enthalten. Das Reporting-Fenster wird jedoch immer durch den geplanten Versand des Feeds definiert (stündlich oder täglich). Wenn ein Segment einen Datumsbereich enthält, filtert es Zeilen innerhalb des Daten-Feed-Fensters, ohne das Fenster selbst zu verschieben oder zu erweitern.

Dies unterscheidet sich von Analysis Workspace, wo die Anwendung eines Segments, das einen Datumsbereich enthält, das aktive Reporting-Fenster so ändert, dass es mit dem Datumsbereich des Segments übereinstimmt.

## Segmentqualifikation und der Lookback-Datumsbereich

Für Segmente, die einen Personen- oder Sitzungs-Container verwenden, wird die Qualifizierung durch die Einstellung **Lookback-**) bestimmt, nicht nur durch das Versandfenster. Wenn sich eine Person für den Lookback-Datumsbereich qualifiziert, werden alle Ereignisse dieser Person im Versandfenster einbezogen. Die Container-Einstellung bestimmt den Umfang:

- **Ereignis-Container**: Nur Ereignisse, die den Segmentkriterien im Versandfenster entsprechen, werden einbezogen.
- **Sitzungs-Container**: Alle Ereignisse in qualifizierten Sitzungen im Versandfenster sind enthalten, wobei die Sitzungsqualifizierung über den Lookback-Datumsbereich ausgewertet wird.
- **Personen-Container**: Alle Ereignisse im Versandfenster sind für jede Person enthalten, die sich während des Lookback-Datumsbereichs qualifiziert.

Weitere Informationen zum Lookback-Datumsbereich und dessen Auswirkungen auf die Segmentqualifikation finden Sie unter [Erstellen eines Daten-Feeds](/help/components/exports/cja-data-feeds/create-feed.md).

