---
title: Konfigurieren einer Matrixvisualisierung in Analysis Workspace
description: Erfahren Sie, wie Sie die Matrixvisualisierung in Customer Journey Analytics Analysis Workspace konfigurieren, einschließlich der Komponenten, Anzeigeoptionen und Einstellungen.
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
source-wordcount: '1323'
ht-degree: 4%
---

# Konfigurieren einer Matrix-Visualisierung

Die Matrixvisualisierung ist ein Raster von Werten, die zeigen, wie Dimensionselemente aus zwei Dimensionen sich überschneiden oder miteinander korrelieren. Jede Zelle zeigt die Schnittmenge des Dimensionselements der Zeile mit der des Dimensionselements der Spalte an.

![Matrix-Visualisierung](assets/matrix-overview.png)

## Matrix-Übersicht

Weitere [&#x200B; zur &#x200B;](/help/analysis-workspace/visualizations/matrix/matrix.md) finden Sie unter „Matrix-Übersicht“, einschließlich:

* Wichtigste Funktionen

* Potenzielle Erkenntnisse

* Unterschiede zwischen Matrix-, Freiformtabellen-, Venn- und Streuvisualisierungen

## Erstellen einer Matrix-Visualisierung

1. Fügen Sie Ihrem Projekt ein leeres Bedienfeld hinzu, wählen Sie in der linken Leiste das [!UICONTROL **Visualisierungen**]-Symbol aus und ziehen Sie dann die [!UICONTROL **Matrix**]-Visualisierung in das Bedienfeld. <!-- FOLLOW-UP: add the Matrix icon before the name when it's available in help/assets/icons. -->

   Oder

   Fügen Sie eine Matrix-Visualisierung auf eine der Arten hinzu, die im Abschnitt [Hinzufügen von Visualisierungen zu einem Bedienfeld](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) in [Visualisierungsübersicht](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) beschrieben werden.

   <!-- add screenshot of the Matrix configuration fields -->

1. Geben Sie die folgenden Informationen an, um die Matrixvisualisierung zu konfigurieren:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Zeilendimension**] | Die Dimension, deren Elemente als Zeilen in der Matrix angezeigt werden. |
   | [!UICONTROL **Spaltendimension**] | Die Dimension, deren Elemente als Spalten in der Matrix angezeigt werden. <p>Wenn Sie dieselbe Dimension sowohl für die Zeilendimension als auch für die Spaltendimension auswählen, vergleicht die Matrixvisualisierung die Dimensionselemente miteinander. Wenn beispielsweise beide Dimensionen _Gerätetyp_ sind, zeigt jede Zelle die Überschneidung oder Korrelation zwischen zwei Gerätetypen an, z. B _„Mobiltelefon_ und _Tablet_. Die Werte über und unter der Diagonale spiegeln sich gegenseitig.</p> |
   | [!UICONTROL **Metrik**] | Die Metrik, die jede Zelle für die Kombination ihres Zeilen- und Spaltendimensionselements anzeigt. |
   | [!UICONTROL **Container**] | Der Container, der den Umfang der Überschneidung zwischen Zeilen- und Spaltendimensionselementen bestimmt. (Wenn sich Ihre Container-Namen von den unten gezeigten Standardnamen unterscheiden, wurden sie in Ihrer Datenansicht angepasst.)<ul><li>**Person:** (Standard) Ein Zeilendimensionselement und ein Spaltendimensionselement überschneiden sich, wenn sie für dieselbe Person über eine beliebige Anzahl von Sitzungen hinweg auftreten.</li><li>**Sitzung** Ein Zeilendimensionselement und ein Spaltendimensionselement überschneiden sich, wenn sie in derselben Sitzung auftreten.</li><li>**Ereignis** Ein Zeilendimensionselement und ein Spaltendimensionselement überschneiden sich, wenn sie im selben Ereignis auftreten.</li></ul><!-- SME CHECK: confirm how each container defines overlap. --> |

1. (Optional) Ändern Sie eine der folgenden Einstellungen:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Zeilenbegrenzung**] | Die maximale Anzahl von Zeilen, die die Matrix-Visualisierung anzeigt. Der Standardwert lautet 10. <!-- SME CHECK: Which items are shown (top items by the metric?)? Does the limit also apply to columns? What's the maximum? --> |
   | [!UICONTROL **Überlappungspalette**] | Die Farbskala für Zellen, wenn die Matrix [Überlappungszahlen](#view-overlap-count-or-correlation-strength) anzeigt. |
   | [!UICONTROL **Korrelationspalette**] | Die Farbskala für Zellen, wenn die Matrix &quot;[&quot; &#x200B;](#view-overlap-count-or-correlation-strength). Negative und positive Korrelationen verwenden unterschiedliche Farben. |
   | [!UICONTROL **Korrelationsgranularität**] | Die Zeitgranularität, die zur Berechnung [Korrelationsstärke“ verwendet wird](#view-overlap-count-or-correlation-strength) z. B. **[!UICONTROL Tag]**. Dieser Wert wird automatisch auf der Grundlage des Datumsbereichs des Bedienfelds festgelegt. Du kannst es nicht ändern. <p>Die folgenden Granularitäten werden je nach Datumsbereich des Bedienfelds ausgewählt:</p><ul><li>[!UICONTROL **Stunde**]: Für Datumsbereiche von 7 Tagen oder weniger ausgewählt</li><li>[!UICONTROL **Tag**]: Für Datumsbereiche von mehr als 7 Tagen bis zu 3 Monaten ausgewählt</li><li>[!UICONTROL **Woche**]: Für Datumsbereiche von mehr als 3 Monaten bis zu 1 Jahr ausgewählt</li><li>[!UICONTROL **Monat**]: Für Datumsbereiche von mehr als 1 Jahr ausgewählt</li></ul><!-- SME CHECK: The granularities and date range thresholds in this list are a best guess. Confirm which granularities are used for which date ranges. --> |
   | [!UICONTROL **Diagonale Zellenwerte**] | Die Matrix-Visualisierung zeigt Zellen, wo ein Dimensionselement auf sich selbst trifft. Diese Einstellung ist nur verfügbar, wenn die Zeilendimension und die Spaltendimension identisch sind.<ul><li>**[!UICONTROL Anzeigen]:** Zeigt den Wert an.</li><li>**[!UICONTROL Dash]:** Zeigt einen Bindestrich anstelle des Werts an.</li><li>**[!UICONTROL Leer]:** Lässt die Zelle leer.</li></ul> |

1. Wählen Sie [!UICONTROL **Erstellen**] aus.

   <!-- add screenshot -->

1. Fahren Sie mit dem folgenden Abschnitt fort[Anzeigen der Überschneidungsanzahl oder Korrelationsstärke](#view-overlap-count-or-correlation-strength).

## Anzahl der Überschneidungen oder Korrelationsstärke anzeigen

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_matrix_overlap_correlation"
>title="Anzahl der Überschneidungen vs. Korrelationsstärke"
>abstract="<p>**Überschneidungsanzahl** ist der Wert der ausgewählten Metrik, bei dem sich ein Zeilendimensionselement und ein Spaltendimensionselement überschneiden.</p><p>**Korrelationsstärke** ist eine lineare Korrelation von -1 bis +1, die angibt, wie stark sich die Metrik für die beiden Dimensionselemente im Zeitverlauf zusammen bewegt. Ein Wert von +1 bedeutet, dass sie gemeinsam aufsteigen und fallen, 0 bedeutet, dass es keine Beziehung gibt, und -1 bedeutet, dass sie sich in entgegengesetzte Richtungen bewegen. Die Korrelationsstärke wird getrennt von der Überschneidung berechnet, sodass Dimensionselemente mit geringer Überschneidung weiterhin eine starke Korrelation aufweisen können.</p>"

<!-- markdownlint-enable MD034 -->

Sie können die Matrixvisualisierung umschalten, um die Überschneidungsanzahl oder Korrelationsstärke anzuzeigen. Die Überschneidungsanzahl wird standardmäßig angezeigt.

1. Öffnen Sie in Analysis Workspace eine Matrix-Visualisierung oder [&#x200B; Sie eine neue &#x200B;](#build-a-matrix-visualization).

1. Wählen Sie in der linken oberen Ecke der Matrixvisualisierung eine der folgenden Optionen aus:

   * [!UICONTROL **Überschneidungsanzahl**]: Zeigt an, wie viele Überschneidungen für jedes Zeilendimensionselement mit jedem Spaltendimensionselement vorhanden sind. Jede Zelle zeigt den Wert der ausgewählten Metrik für die Personen, Sitzungen oder Ereignisse (je nach Container) an, in denen beide Dimensionselemente auftreten.

   * [!UICONTROL **Korrelationsstärke**]: Zeigt an, wie genau sich die ausgewählte Metrik für jedes Zeilendimensionselement und jedes Spaltendimensionselement über den Datumsbereich des Bedienfelds zusammenbewegt, als lineare Korrelation von -1 bis +1. Ein Wert von +1 bedeutet, dass die beiden Dimensionselemente immer ansteigen und zusammenfallen, 0 bedeutet, dass es keine Beziehung gibt, und -1 bedeutet, dass sie sich immer in entgegengesetzte Richtungen bewegen. Die Korrelationsstärke wird getrennt von der Überschneidung berechnet, sodass Dimensionselemente mit geringer Überschneidung weiterhin eine starke Korrelation aufweisen können. Die Korrelation wird zu dem Zeitpunkt berechnet, an dem die Granularität in der Einstellung [!UICONTROL **Korrelationsgranularität**] angezeigt wird. <!-- SME CHECK: Confirm that the linear correlation is Pearson. -->

   Eine Legende in der oberen rechten Ecke der Matrixvisualisierung zeigt die Farbskala für die aktuelle Ansicht: niedrig zu hoch für die Überlappungsanzahl oder negativ (-1) zu positiv (+1) für die Korrelationsstärke.

## Anzeigen von Einblicken

<!-- FOLLOW-UP: Draft based on a prototype screenshot. Add a screenshot of the insight card. -->

Eine insight-Karte am unteren Rand der Matrixvisualisierung beschreibt bemerkenswerte Muster in den Matrixdaten.

<!-- SME CHECK: How are insights generated (AI)? What does the label on the card (such as ABSOLUTE) mean, and what other labels are there? Do the insights differ between the Overlap count and Correlation strength views? Are they updated when you change the settings or the panel date range? Can you hide the card? Are any permissions, entitlements, or AI settings required? -->

So zeigen Sie Erkenntnisse an:

1. In einer Matrix-Visualisierung sehen Sie sich die insight-Karte unten in der Visualisierung an.

1. Verwenden Sie die Pfeile auf der insight-Karte, um durch die verfügbaren Einblicke zu blättern.

## Bearbeiten der Matrix-Einstellungen

Nachdem Sie eine Matrixvisualisierung erstellt haben, können Sie deren Einstellungen ändern, z. B. die Dimensionen, die Metrik oder den Container.

So bearbeiten Sie die Matrix-Einstellungen:

1. Wählen Sie in einer ![-Visualisierung &#x200B;](/help/assets/icons/Edit.svg)Bearbeiten) neben dem Untertitel oben in der Visualisierung aus. Der Untertitel fasst die aktuellen Einstellungen wie die Metrik und die Dimensionen zusammen.

1. Ändern Sie alle Einstellungen, die unter &quot;[&#x200B; einer Matrixvisualisierung“ beschrieben &#x200B;](#build-a-matrix-visualization).

1. Wählen Sie [!UICONTROL **Erstellen**] aus.

<!-- SME CHECK: Confirm that the Edit icon reopens the build settings. Does the Matrix keep the Overlap count or Correlation strength view after you rebuild it? -->

## Anzeigen von Trend-Daten

Sie können die Trenddaten für eine Zelle in einer [-Visualisierung &#x200B;](/help/analysis-workspace/visualizations/line.md). Die Linienvisualisierung zeigt, wie sich die ausgewählte Metrik über den Datumsbereich des Bedienfelds ändert. Die angezeigten Linien hängen davon ab, ob die Matrix [Überlappungsanzahl oder Korrelationsstärke](#view-overlap-count-or-correlation-strength) anzeigt.

So zeigen Sie Trenddaten an:

1. Klicken Sie in einer Matrix-Visualisierung mit der rechten Maustaste auf die Zelle, für die Sie Trenddaten anzeigen möchten.

1. Wählen Sie [!UICONTROL **Trend**] aus.

   Dem Bedienfeld wird eine Linienvisualisierung über der Matrixvisualisierung hinzugefügt:

   * [!UICONTROL **Überschneidungsanzahl**]: Eine einzelne Zeile zeigt die ausgewählte Metrik an, gefiltert nach dem Zeilendimensionselement und dem Spaltendimensionselement.

   * [!UICONTROL **Korrelationsstärke**]: Zwei Zeilen zeigen die ausgewählte Metrik an, eine für das Dimensionselement Zeile und eine für das Dimensionselement Spalte. Vergleichen Sie die Linien, um zu sehen, wie eng die beiden Dimensionselemente zusammen tendieren.

   <!-- SME CHECK: Does the overlap count filter use the Matrix container? Is the time granularity the panel default or the Correlation granularity? Can you select multiple cells? Is the option available for diagonal cells? -->

## Überschneidung in einer Venn-Visualisierung anzeigen

Sie können die Überschneidung zwischen dem Zeilendimensionselement und dem Spaltendimensionselement für eine Zelle in einer (Venn[Visualisierung &#x200B;](/help/analysis-workspace/visualizations/venn.md).

Weitere Informationen dazu, wann eine Matrix- oder Venn-Visualisierung verwendet wird, finden Sie unter [Auswahl zwischen Matrix-, Freiformtabellen-, Venn- oder Streuvisualisierungen](/help/analysis-workspace/visualizations/matrix/matrix.md#choose-between-matrix-freeform-table-venn-or-scatter-visualizations) in [Matrix-Übersicht](/help/analysis-workspace/visualizations/matrix/matrix.md).

So zeigen Sie die Überschneidung in einer Venn-Visualisierung an:

1. Klicken Sie in einer Matrix-Visualisierung mit der rechten Maustaste auf die Zelle, deren Überschneidung angezeigt werden soll.

1. Wählen Sie [!UICONTROL **In Venn anzeigen**] aus.

   Dem Bedienfeld wird eine Venn-Visualisierung hinzugefügt. Ein Kreis stellt das Zeilendimensionselement dar, und der andere Kreis stellt das Spaltendimensionselement dar. Die Venn -Visualisierung verwendet dieselbe Metrik wie die Matrixvisualisierung. <!-- SME CHECK: Where is the Venn visualization added? Are segments created for each dimension item, and do they use the Matrix container? Is the option available for diagonal cells and in the Correlation strength view? -->

## Anwenden einer Aufschlüsselung

Sie können die Daten für eine Zelle nach einer anderen Dimension aufschlüsseln, um zu sehen, welche Dimensionselemente zum Zellwert beitragen.

So wenden Sie eine Aufschlüsselung an:

1. Klicken Sie in einer Matrix-Visualisierung mit der rechten Maustaste auf die Zelle, für die Sie eine Aufschlüsselung anwenden möchten.

1. Wählen Sie [!UICONTROL **Aufschlüsselung**] aus.

1. Wählen Sie die Dimension aus, die Sie für die Aufschlüsselung verwenden möchten.

   Die obersten Dimensionselemente für die Aufschlüsselungsdimension werden in einer neuen Freiformtabelle angezeigt. <!-- SME CHECK: Where is the table added? Does the breakdown use the Matrix metric and container? Can you select multiple cells? Is the option available for diagonal cells and in the Correlation strength view? -->


