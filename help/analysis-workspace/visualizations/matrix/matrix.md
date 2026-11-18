---
title: Übersicht über die Matrixvisualisierung in Analysis Workspace
description: Erfahren Sie mehr über die Matrixvisualisierung in Customer Journey Analytics Analysis Workspace, einschließlich dessen, was sie zeigt, wann sie verwendet wird und wie sie mit anderen Visualisierungen verglichen wird.
feature: Visualizations
role: User
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 3199a70eee577f4e283208e2c5089c05fe20ed0d
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 2%
---

# Matrix-Übersicht {#matrix-overview}

Mit der Matrixvisualisierung in Analysis Workspace können Sie sehen, wie sich Dimensionselemente aus zwei Dimensionen überschneiden oder miteinander korrelieren.

Dimension-Elemente für eine Dimension werden als Zeilen (entlang der Y-Achse) angezeigt, während Dimensionselemente für die andere Dimension als Spalten (entlang der X-Achse) angezeigt werden. Jede sich schneidende Zelle zeigt entweder die Überschneidungs- oder Korrelationsdaten an, die auf der von Ihnen gewählten Metrik basieren.

Beispielsweise zeigt die folgende Matrix-Visualisierung die Überschneidungsanzahl von Ereignissen für Gerätenamen nach Länder-Code.

* Dimension 1 (Zeilendimension): Gerätename

* Dimension 2 (Spaltendimension): Ländercode

* Metrik: Ereignisse

![Matrix-Übersicht](assets/matrix-overview.png)

## Wichtigste Funktionen

* **Zwei verschiedene Dimensionen vergleichen**: Sehen Sie, wie sich Elemente in einer Dimension auf Elemente in einer anderen Dimension beziehen.

* **Dimension mit sich selbst vergleichen**: Hier erfahren Sie, wie Elemente in derselben Dimension zusammenhängen.

* **Überschneidung**: Zeigt die Überschneidung von Dimensionselementen an.

* **Korrelation**: Zeigt an, wie stark sich Dimensionselemente zusammen entwickeln, auf einer Skala von -1 (Bewegung immer in verschiedene Richtungen) bis +1 (Bewegung immer zusammen).

* **Heatmap-Farben**: Die Zellfarbe gibt an, ob die Überlappung hoch oder niedrig ist, oder ob die Korrelation positiv oder negativ ist und wie stark sie ist. Überlappung und Korrelation haben separate Farbpaletten.

## Potenzielle Erkenntnisse

* Finden Sie Muster und Lücken in zwei Dimensionen. Sie können beispielsweise Fragen wie die folgenden beantworten:

  * Welche Kampagnen funktionieren in einigen Regionen gut, in anderen nicht?

  * Welche Inhaltstypen schneiden bei jedem Gerätetyp am besten ab?

* Ermitteln Sie, wie sich Dimensionselemente zueinander verhalten. Sie können beispielsweise Fragen wie die folgenden beantworten:

  * Welche Marketing-Kanäle entwickeln sich im Laufe der Zeit zusammen, welche bewegen sich unabhängig voneinander und welche bewegen sich in entgegengesetzte Richtungen?

  * Welche Seiten haben Traffic, der gemeinsam steigt und fällt?

* Vergleichen einer Dimension mit sich selbst. Sie können beispielsweise Fragen wie die folgenden beantworten:

  * Welche Produkte werden oft von denselben Leuten gekauft?

  * Welche Geräte verwenden dieselben Menschen zusammen, z. B. Mobiltelefone und Tablets?

## Wählen Sie zwischen Matrix-, Freiformtabellen-, Venn- oder Streuvisualisierungen

Die Matrix-Visualisierung weist Ähnlichkeiten mit [Verwendung mehrerer Dimensionsspalten in einer Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md) der [Venn-](/help/analysis-workspace/visualizations/venn.md) und der [Streuvisualisierung](/help/analysis-workspace/visualizations/scatterplot.md) auf. Jede Visualisierung zeigt, wie Komponenten miteinander in Beziehung stehen, aber sie unterscheiden sich in den von ihnen verwendeten Komponenten und der Anzeige der Ergebnisse.

### Verwendung der einzelnen Visualisierungen

Wählen Sie die Visualisierung aus, die am besten zu Ihrer Analyse passt:

* **Matrix:** Sehen Sie für eine bestimmte Metrik, wie sich jedes Dimensionselement in einer Dimension auf jedes Dimensionselement in einer anderen Dimension bezieht, einschließlich Lücken und Dimensionselemente, die zusammen einen Trend aufweisen.

* **Freiformtabelle mit mehreren Dimensionsspalten:** Sie einer Freiformtabelle bis zu 5 Dimensionen als separate Spalten hinzufügen. Dimension-Elemente, die in derselben Tabellenzeile angezeigt werden, werden verkettet. Fügen Sie der Tabelle eine beliebige Anzahl von Metriken hinzu, um Metrikdaten für jedes verkettete Dimensionselement anzuzeigen. Filtern, Sortieren und Hinzufügen von Aufschlüsselungen zu verketteten Dimensionselementen.

* **Venn:** Zeigen Sie für eine einzelne Metrik die Überschneidung von bis zu drei Segmenten an.

* **Streuung** Dimensionselemente über zwei oder drei Metriken hinweg vergleichen, um Muster und Ausreißer zu finden.

### Informationen zu den Unterschieden

<!-- SME CHECK: Confirm the Matrix cells: segments can't be used as rows or columns. Container row: confirm what each Matrix container means for overlap, and that freeform combinations are based on the dimension items that apply to each event. -->

| Funktion | Matrix | Mehrere Dimensionsspalten in einer Freiformtabelle | Venn | Streuung |
| --- | --- | --- | --- | --- |
| **Verwendete Komponenten** | 2 Dimensionen; 1 Metrik<p>Vergleicht Dimensionselemente aus zwei Dimensionen oder aus einer Dimension mit sich selbst.</p> | Bis zu 5 Dimensionen; beliebig viele Metriken<p>Dimension-Elemente, die in derselben Zeile angezeigt werden, sind verkettet und verhalten sich wie ein einzelnes Dimensionselement. Verkettete Zeilen werden anhand ihrer Metrikwerte verglichen.</p> | Bis zu 3 Segmente; 1 Metrik<p>Vergleicht die Überschneidung zwischen Segmenten.</p> | 1 Dimension; bis zu 3 Metriken<p>Vergleicht Dimensionselemente über Metriken hinweg.</p> |
| **Container** | In der Visualisierung festgelegt: Person (Standard), Sitzung oder Ereignis<p>Legt fest, ob die Überschneidung Dimensionselemente zählt, die für dieselbe Person, in derselben Sitzung oder im selben Ereignis auftreten.</p> | Keine Container-Einstellung<p>Jede Zeile kombiniert die Dimensionselemente, die für dasselbe Ereignis gelten. Die ausgewählte Metrik, z. B. Personen oder Sitzungen, bestimmt, was gezählt wird.</p> | In jedem Segment festlegen<p>Jedes Segment verwendet einen eigenen [Container](/help/components/segments/seg-overview.md#containers) (Person, Sitzung oder Ereignis). Die Metrik bestimmt, was in jeder Überschneidung gezählt wird.</p> | Keine Container-Einstellung<p>Die von Ihnen gewählten Metriken bestimmen, was gezählt wird.</p> |
| **Layout** | Raster, ähnlich wie eine Pivot-Tabelle<p>Dimension-Elemente aus einer Dimension sind Zeilen, und Dimensionselemente aus der anderen Dimension sind Spalten.</p> | Liste<p>Jede Zeile kombiniert ein Dimensionselement aus jeder Dimensionsspalte.</p> | Überlappende Kreise | Punkte auf einer X- und Y-Achse |
| **Zeigt Überschneidungen an** | Ja<p>Zeigt die Überschneidung zwischen jedem Dimensionselement in den Zeilen und jedem Dimensionselement in den Spalten.</p><p>Verwenden Sie die Ansicht **[!UICONTROL Überschneidungsanzahl]**.</p> | Ja<p>Zeigt die Metrik für jede Kombination von Dimensionselementen, eine Kombination pro Zeile.</p> | Ja<p>Zeigt die Überschneidung zwischen Segmenten an.</p> | Nein |
| **Zeigt Korrelation an** | Ja, zwischen Dimensionselementen<p>Zeigt, wie stark sich Dimensionselemente im Zeitverlauf gemeinsam entwickeln, auf einer Skala von -1 (entgegengesetzte Richtungen) bis +1 (zusammen).</p><p>Verwenden Sie die Ansicht **[!UICONTROL Korrelationsstärke]**.</p> | Nein | Nein | Ja, zwischen Metriken<p>Zeigt, wie Metriken miteinander in Beziehung stehen. Jeder Punkt ist ein Dimensionselement, das durch bis zu drei Metriken dargestellt wird.</p> |

{style="table-layout:auto"}

