---
title: Mehrere Dimensionen in eine Freiformtabelle einschließen
description: Erfahren Sie, wie Sie mehrere Dimensionen in eine Freiformtabelle einschließen
feature: Visualizations
role: User
exl-id: 66ebb4fc-feb2-4fa7-a107-37508cca4748
source-git-commit: 14718476695dcf121c94ba4cb8b2c39e5874342d
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 2%

---

# Mehrere Dimensionsspalten in eine Freiformtabelle einschließen

{{release-limited-testing}}

Sie können bis zu 5 Dimensionsspalten in eine Freiformtabelle einbeziehen, sodass Sie mehrere Dimensionselemente nebeneinander anzeigen können. Jede Reihe von Dimensionselementen verhält sich wie ein einzelnes verkettetes Dimensionselement.

Sie können Filter, Sortierung, Aufschlüsselungen und mehr auf Freiformtabellen mit mehreren Dimensionsspalten anwenden, um eine tiefere und benutzerspezifischere Analyse zu erstellen.

## Verkettete Dimensionselemente

Wenn Sie [einer Freiformtabelle mehrere Dimensionsspalten hinzufügen](#add-multiple-dimension-columns) verhält sich jede Zeile mit Dimensionselementen wie ein einzelnes verkettetes Dimensionselement. Mit dieser Funktion können Sie Metrikdaten für bestimmte Kombinationen von Dimensionen anzeigen.

Nehmen wir zum Beispiel eine Freiformtabelle mit den Dimensionsspalten _Stadt_, _Gerätetyp_ und _Tag des Monats_ und der Metrik _Ereignisse_. Die 3 Dimensionselemente in der ersten Zeile dieser Tabelle werden zu einem einzigen verketteten Dimensionselement, das zeigt, dass am 30. Tag des Monats 2.056 Ereignisse in Mumbai von Mobiltelefonen aus stattfanden.

| Dimension: Stadt | Dimension: Gerätetyp | Dimension: Tag des Monats | Metrik: Ereignisse |
|---------|----------|---------|---------|
| Mumbai | Mobiltelefon | 30 | 2.056 |
| New York | Tablet | 31 | 1.761 |
| Bangalore | Desktop | 1 | 1.666 |
| Delhi | Mobiltelefon | 14 | 1.396 |

So wird diese Tabelle in Analysis Workspace angezeigt:

![Beispiel für mehrere Dimensionen](assets/multi-dim-example.png)

## Mehrere Dimensionsspalten hinzufügen

Sie können mehrere Dimensionsspalten gleichzeitig oder stapelweise hinzufügen.

1. Erstellen Sie in Analysis Workspace eine Freiformtabelle.

   Weitere Informationen finden Sie unter [Hinzufügen von Visualisierungen zu einem Bedienfeld](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) in [Übersicht über Visualisierungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Fügen Sie Dimensionen zur Freiformtabelle hinzu. Sie können Dimensionen einzeln hinzufügen oder mehrere Dimensionen gleichzeitig hinzufügen.

   * Ziehen Sie Dimensionen einzeln in die Freiformtabelle. Platzieren Sie zusätzliche Dimensionsspalten links oder rechts von vorhandenen Dimensionsspalten in der Tabelle. An der Stelle, an **[!UICONTROL die neue Spalte erstellt wird, wird eine blaue vertikale]** Hinzufügen“ angezeigt.

     ![Ziehen einzelner Dimensionen](assets/dimensions-add-individually.png)

   * Wählen Sie im Komponentenmenü bis zu 5 Dimensionen aus und ziehen Sie sie in die Freiformtabelle. Dimensionen werden der Tabelle von links nach rechts in der Reihenfolge hinzugefügt, in der Sie sie auswählen.

     Um mehrere Dimensionen auszuwählen, halten Sie die ***Befehlstaste*** (auf Mac) oder die ***Strg***-Taste (auf Windows) gedrückt.

     ![Ziehen mehrerer Dimensionen](assets/dimensions-add-multiple.png)

1. Zeigen Sie jede Tabellenzeile als einzelnes Dimensionselement an. Weitere Informationen finden Sie unter [Verkettete Dimensionselemente](#concatenated-dimension-items).

## Filtern und Sortieren von Tabellen

Sie können Filtern und Sortieren auf Spalten in einer Freiformtabelle anwenden. Sie können die Daten einer Freiformtabelle nach beliebigen Spalten sortieren, unabhängig davon, ob es sich um Dimensionen oder Metriken handelt. Sie können auch nach mehreren Spalten gleichzeitig sortieren.

Weitere Informationen finden Sie [Freiformtabellen filtern und sortieren](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

## Mehrere Dimensionsspalten und Aufschlüsselungen

Analysis Workspace bietet die folgenden Möglichkeiten, mehrere Dimensionen in einer Freiformtabelle hinzuzufügen:

* Mehrere Dimensionsspalten einschließen (wie in diesem Artikel beschrieben)

* [Aufschlüsselungen hinzufügen](/help/components/dimensions/t-breakdown-fa.md)

Mit beiden Methoden können Sie Dimensionen anhand anderer Dimensionen analysieren. Es gibt jedoch wichtige Unterschiede, und beide Methoden können in derselben Tabelle für eine noch tiefere Analyse verwendet werden.

### Unterschiede zwischen Dimensionsspalten und Aufschlüsselungen

Mehrere Dimensionsspalten ermöglichen Folgendes:

* Verketten von Dimensionselementen in separate Datenzeilen über mehrere Dimensionen hinweg.

* Dimensionselemente nur dann in verketteten Zeilen einbeziehen, wenn Dimensionselemente für jede Dimensionsspalte in der Tabelle gelten. Verwenden Sie dazu den Spaltenfilter, um die Auswahl der Einstellung &quot;**[!UICONTROL einschließen“]** jede Dimensionsspalte aufzuheben.

  Weitere Informationen finden Sie unter [Sortieren von Tabellen nach mehreren Spalten (erweiterte Sortierung)](#sort-tables-by-multiple-columns-advanced-sorting).

* Sortieren Sie Daten nach mehreren Dimensions- und Metrikspalten, um mehr benutzerdefinierte Daten anzuzeigen.

  Weitere Informationen finden Sie unter [Sortieren von Tabellen nach mehreren Spalten (erweiterte Sortierung)](#sort-tables-by-multiple-columns-advanced-sorting)

Aufschlüsselungen ermöglichen Folgendes:

* Aufschlüsseln eines Dimensionselements in der Freiformtabelle nach einer sekundären Dimension. Für die sekundäre Dimension können bis zu 400 Dimensionselemente angezeigt werden.

### Hinzufügen von Aufschlüsselungen zu einer Tabelle mit mehreren Dimensionsspalten

Wenn Sie einer Tabelle mit mehreren Dimensionsspalten eine Aufschlüsselung hinzufügen, gilt die Aufschlüsselung für das verkettete Dimensionselement (über alle Dimensionsspalten hinweg) in der Zeile, in der Sie es hinzufügen.

![Beispiel für eine Aufschlüsselung mit mehreren Sortierungen](assets/dimensions-multiple-sort-breakdown.png)

Darüber hinaus können Sie innerhalb einer Aufschlüsselung mehrere Dimensionsspalten hinzufügen. Jede Reihe von Dimensionselementen innerhalb der Aufschlüsselung verhält sich auch wie ein einzelnes verkettetes Dimensionselement.

<!-- Add a screenshot of a breakdown with multiple cllumns, then add this sentence: "For example, you can break down the first dimension item in this table by a new concatenated dimension item that shows..." -->

Weitere Informationen zum Hinzufügen einer Aufschlüsselung finden Sie unter [Dimensionen ](/help/components/dimensions/t-breakdown-fa.md).

## Erstellen eines Segments basierend auf einem Dimensionselement, das sich über mehrere Dimensionsspalten erstreckt

Wenn Sie ein Segment basierend auf einem Dimensionselement erstellen, das mehrere Dimensionsspalten umfasst, wird jedes Dimensionselement in die Segmentdefinition aufgenommen, wobei AND-Operatoren mit ihnen verknüpft werden.

Informationen zum Erstellen eines Segments finden Sie unter [Segmente erstellen](/help/components/segments/seg-create.md).

## Nicht unterstützte Dimensionen und Funktionen {#unsupported}

Die folgenden Dimensionskombinationen und -funktionen werden bei Verwendung mehrerer Dimensionsspalten nicht unterstützt und Analysis Workspace verbietet entweder deren Verwendung oder zeigt eine Fehlermeldung an:

* Mehrere Dimensionen, die aus Feldern stammen, die auf verschiedene [Arrays von Objekten](/help/use-cases/object-arrays.md) verweisen, die zusammen in derselben Freiformtabelle verwendet werden.

  Mehrere Dimensionen sind in derselben Freiformtabelle zulässig, wenn sie auf dasselbe Array von Objekten verweisen.

* [Statische Dimensionselemente](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md#static-dimension-items).
