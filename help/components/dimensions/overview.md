---
title: Dimensionen – Übersicht
description: Erfahren Sie, welche Dimensionen und wie sie beim Customer Journey Analytics verwendet werden.
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: d37734ae415722fc609715868c37a36f2becdbf6
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 36%

---

# Dimensionen – Übersicht

Dimensionen sind ein Komponententyp in Customer Journey Analytics, der zur Datenanalyse verwendet wird. Sie verwenden beispielsweise Dimensionen, wenn Sie Berichte in [Analysis Workspace](/help/analysis-workspace/home.md) oder in [Report Builder](/help/report-builder/report-buider-overview.md) erstellen.

Customer Journey Analytics-Dimensionen sind unbegrenzt; Werte können numerisch, Text, Objekte, Listen oder Mischungen von allen sein.

Ein grundlegender Bericht unter Customer Journey Analytics zeigt Dimensionen-Zeilen (häufig Zeichenfolgenwerte) in Bezug auf eine Metrikspalte (häufig numerische Werte) an.

Wenn Sie beispielsweise die Dimension Seite mit der Metrik für Personen kombinieren, erhalten Sie einen Rangbericht, der Ihre am häufigsten besuchten Seiten nach Personen anzeigt:

| Seite | Personen |
| --- | ---: |
| Startseite | 800 |
| Produktseite | 500 |
| Kaufseite | 100 |

{style="table-layout:fixed"}

Jede Dimension stellt einen anderen Teil oder eine andere Facette Ihrer Site dar. Sie können eine oder mehrere dieser Dimensionen mit einer oder mehreren Metriken kombinieren, um einen gewünschten Bericht zu erstellen.


## Dimensionen erstellen

Customer Journey Analytics-Administratoren können [Dimensionen in einer Datenansicht erstellen](/help/data-views/create-dataview.md#components).

## Standarddimensionen

Wenn Sie eine Datenansicht erstellen, werden die folgenden zeitbasierten Komponenten standardmäßig als Dimensionen zu Ihrer Datenansicht hinzugefügt:

- 15 Minuten
- 30 Minuten
- 5 Minuten
- Tag
- Tag des Monats
- Wochentag
- Tag des Jahres
- Stunde
- Stunde des Tages
- Minute
- Minute der Stunde
- Monat
- Monat des Jahres
- Quartal
- Quartal des Jahres
- Zweite/r
- Woche des Jahres
- Jahr

## Hinzufügen von Dimensionsbeschreibungen

Customer Journey Analytics-Administratoren können Beschreibungen für Dimensionen und andere Komponenten entweder in der Datenansicht oder direkt in Analysis Workspace hinzufügen. Informationen zum Hinzufügen von Beschreibungen zu Dimensionen finden Sie unter [Hinzufügen von Komponentenbeschreibungen](/help/components/add-component-descriptions.md).
