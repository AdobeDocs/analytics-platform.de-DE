---
title: Segmentierung in Customer Journey Analytics-Daten-Feeds
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
source-git-commit: f36723dab5500f728dd9ec267d97305aff604149
workflow-type: tm+mt
source-wordcount: 659
ht-degree: 2%

---


# Segmentierung in Daten-Feeds

{{release-limited-testing}}

Daten-Feeds in Customer Journey Analytics unterstützen die Segmentierung, sodass Sie filtern können, welche Zeilen in jedem Feed-Versand enthalten sind. Sie können Segmente auf Datenansichtsebene, Feed-Ebene oder auf beides anwenden.

## Wo Segmente angewendet werden

Segmente können an zwei Stellen auf einen Daten-Feed angewendet werden:

- **Datenansicht**: Ein in der Datenansicht konfiguriertes Segment, das für alle Feeds gilt, die diese Datenansicht verwenden.
- **Datenfeed**: Ein Segment, das zusätzlich zu einem Datenansichtssegment direkt auf einen einzelnen Feed angewendet wird.

Wenn beide konfiguriert sind, kombiniert Customer Journey Analytics sie - nur Zeilen, die beide Segmente erfüllen, werden in die Feed-Ausgabe aufgenommen.

## Datumsbereichssegmente

Segmente, die auf Datumsbereiche verweisen, werden in Daten-Feeds unterstützt. Das Verhalten unterscheidet sich jedoch wesentlich von Analysis Workspace: **Datumsbereichsbedingungen in einem Segment überschreiben nicht den Berichtsdatumsbereich des Feeds.**

Wenn Sie in Analysis Workspace ein Datumsbereichssegment anwenden, wird das aktive Berichtsfenster so geändert, dass es mit dem Datumsbereich des Segments übereinstimmt. In Daten-Feeds wird das Reporting-Fenster immer durch den geplanten Versand des Feeds definiert (stündlich oder täglich). Ein Segment mit einer Bedingung für den Datumsbereich filtert Zeilen innerhalb dieses Fensters - es verschiebt oder erweitert das Fenster selbst nicht.

Dieses Design ist beabsichtigt. Wenn Sie zulassen, dass Datumsbereichssegmente das Berichtsfenster überschreiben, könnte ein stündlicher Feed ein viel größeres Datenfenster als erwartet bereitstellen, was zu Datenduplizierung oder übermäßigem Ausgabevolumen führen könnte.

### Beispiele

**Beispiel 1 - Segment, das Ereignisse von einem bestimmten Datum enthält**

Angenommen, Sie wenden ein Segment an, das nur Ereignisse ab dem 1. Juli zurückgibt und den Feed für den 22. Juli ausführt:

- Das Feed-Bereitstellungsfenster bleibt der 22. Juli.
- Das Segment filtert alle Zeilen heraus, da keine Ereignisse innerhalb des Fensters vom 22. Juli den Kriterien vom 1. Juli entsprechen. Der Feed wird ausgeführt, liefert jedoch keine Zeilen.
- Wenn Sie eine Aufstockung für den 1. Juli ausführen, verhält sich das Segment wie erwartet - es werden nur Ereignisse einbezogen, die den Kriterien für den 1. Juli entsprechen.

**Beispiel 2 - Segment, das Ereignisse von einem bestimmten Datum ausschließt**

Angenommen, Sie wenden ein Segment an, das alle Ereignisse mit einer Bestellung vom 1. Juli ausschließt, und führen den Feed für den 22. Juli aus:

- Das Segment gilt für die Daten vom 22. Juli. Da im Fenster vom 22. Juli keine Ereignisse vom 1. Juli vorhanden sind, wird nichts ausgeschlossen und alle Zeilen werden bereitgestellt.
- Wenn Sie eine Aufstockung für den 1. Juli ausführen, schließt das Segment die relevanten Zeilen erwartungsgemäß aus.

## Segmente mit mehreren Bedingungen

Für Segmente, die Datumsbereichsbedingungen mit anderen Kriterien kombinieren, wertet Customer Journey Analytics den Datumsbereichsteil nur als Zeilenfilter aus - nicht als Überschreibung des Berichtsfensters. Alle Bedingungen im Segment werden innerhalb des Versandfensters des Feeds berücksichtigt.

## Segmentqualifikation und der Lookback-Datumsbereich

Für Segmente, die einen Personen- oder Sitzungs-Container verwenden, wird die Qualifizierung durch die Einstellung **Lookback-**) bestimmt, nicht nur durch das Versandfenster. Wenn sich eine Person für den Lookback-Datumsbereich qualifiziert, werden alle Ereignisse dieser Person im Versandfenster einbezogen. Die Container-Einstellung bestimmt den Umfang:

- **Ereignis-Container**: Nur Ereignisse, die den Segmentkriterien im Versandfenster entsprechen, werden einbezogen.
- **Sitzungs-Container**: Alle Ereignisse in qualifizierten Sitzungen im Versandfenster sind enthalten, wobei die Sitzungsqualifizierung über den Lookback-Datumsbereich ausgewertet wird.
- **Personen-Container**: Alle Ereignisse im Versandfenster sind für jede Person enthalten, die sich während des Lookback-Datumsbereichs qualifiziert.

Weitere Informationen zum Lookback-Datumsbereich und dessen Auswirkungen auf die Segmentqualifikation finden Sie unter [Erstellen eines Daten-Feeds](/help/components/exports/cja-data-feeds/create-feed.md).

## Vergleich mit Analysis Workspace

| Verhalten | Analysis Workspace | Daten-Feeds |
|---|---|---|
| Berichtsfenster für Datumsbereich-Segmentüberschreibungen | Ja | Nein |
| Segmentfilter in Zeilen im Reporting-Fenster | Ja | Ja |
| Datenansichtssegment gilt | Ja | Ja |
| Zusätzliches Segment, das direkt auf den Versand angewendet wird | Nein | Ja |

{style="table-layout:auto"}
