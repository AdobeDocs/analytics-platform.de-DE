---
title: Mehrere Dimensionen in eine Freiformtabelle einschließen
description: Erfahren Sie, wie Sie mehrere Dimensionen in eine Freiformtabelle einschließen
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: ec07eb5dced013eac3d1088f2f49dcea23894395
workflow-type: tm+mt
source-wordcount: '1028'
ht-degree: 2%

---

# Mehrere Dimensionsspalten in eine Freiformtabelle einschließen

{{release-limited-testing}}

Sie können bis zu 5 Dimensionsspalten in eine Freiformtabelle einbeziehen, sodass Sie mehrere Dimensionselemente nebeneinander anzeigen können. Jede Reihe von Dimensionselementen fungiert als einzelnes verkettetes Element.

Sie können Filter, Sortierung, Aufschlüsselungen und mehr auf Freiformtabellen mit mehreren Dimensionsspalten anwenden, um eine vollständigere und benutzerdefinierter Analyse zu erstellen.

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

## Filtern von Tabellen

Sie können Filter auf eine oder mehrere Dimensionsspalten in einer Freiformtabelle anwenden.

Informationen zum Filtern von Tabellen finden Sie unter [Tabellen filtern](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#filter-tables) in [Tabellen filtern und sortieren](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

## Sortieren von Tabellen {#sort-tables}

<!--At GA, move this section into the "Filter and sort tables" article and replace the current "Sort tables" section. Change the "Filter tables" section above to "Filter and sort tables" and link to the other article. Also add row to Guardrails -->

Sie können die Daten einer Freiformtabelle nach beliebigen Spalten in Analysis Workspace sortieren, unabhängig davon, ob es sich um Dimensionen oder Metriken handelt.

Standardmäßig werden Dimensionen in aufsteigender Reihenfolge und Metriken in absteigender Reihenfolge sortiert.

### Sortieren von Tabellen nach einer Spalte

Wenn Sie Daten für eine einzelne Spalte sortieren, wie in diesem Abschnitt beschrieben, werden alle [erweiterten ](#sort-tables-by-multiple-columns-advanced-sorting)) entfernt, die auf die Tabelle angewendet werden.

So sortieren Sie Daten in Tabellen nach einer Spalte:

1. Bewegen Sie den Mauszeiger über die Kopfzeile der Spalte, die Sie sortieren möchten, und wählen Sie dann das **Sortieren**-Symbol ![Sortieren](/help/assets/icons/SortOrderDown.svg) aus, wenn es angezeigt wird.

   ![Dropdown-Menü „Sortieren“](assets/sort-dropdown-menu.png)

1. Wählen Sie **[!UICONTROL Aufsteigend]** oder **[!UICONTROL Absteigend]**.

   Das Sortiersymbol bleibt sichtbar, wenn die Sortierung auf die Spalte angewendet wird. Ein Pfeil gibt an, wie die Daten sortiert werden (![Sortieren](/help/assets/icons/SortOrderUp.svg) für aufsteigend oder ![Sortieren](/help/assets/icons/SortOrderDown.svg) für absteigend).

### Sortieren von Tabellen nach mehreren Spalten (erweiterte Sortierung)

{{release-limited-testing-section}}

#### Sortierung auf mehrere Spalten anwenden

So sortieren Sie Daten in Tabellen nach mehreren Spalten:

1. Bewegen Sie den Mauszeiger über die Kopfzeile einer Spalte, die Sie sortieren möchten, und wählen Sie dann das **Sortieren**-Symbol ![Sortieren](/help/assets/icons/SortOrderDown.svg) aus, wenn es angezeigt wird.

   ![Dropdown-Menü „Sortieren“](assets/sort-dropdown-menu.png)

1. Wählen Sie **[!UICONTROL Erweiterte Sortierung]** aus.

   ![Dialogfeld „Erweiterte Sortierung“](assets/sort-advanced-dialog.png)

1. Führen Sie im Dialogfeld Erweiterte Sortierung einen der folgenden Schritte aus:

   * Fügen Sie Spalten hinzu, die noch nicht sortiert werden, indem Sie die Schaltfläche **[!UICONTROL Sortierspalte hinzufügen]** auswählen.

   * Entfernen Sie Spalten, die Sie nicht mehr sortieren möchten, indem Sie das Symbol **Entfernen** (![) ](/help/assets/icons/Close.svg).

   * Ziehen Sie Spalten in der Liste nach oben oder unten, um die Sortierpriorität anzupassen.

     Weitere Informationen finden Sie unter [Priorität sortieren](#sort-priority).

   * Ändern Sie den Sortierwert, indem Sie **[!UICONTROL Aufsteigend]** oder **[!UICONTROL Absteigend]** im Dropdown-Menü auswählen.

   * Wählen Sie eine andere Spalte aus, indem Sie auf das Dropdown-Menü Spaltenname klicken.

1. Wählen Sie **[!UICONTROL Anwenden]** aus.

Das Symbol Sortierung bleibt sichtbar, wenn die Sortierung auf eine Spalte angewendet wird. Ein Pfeil gibt an, wie die Daten sortiert werden (![Sortieren](/help/assets/icons/SortOrderUp.svg) für aufsteigend oder ![Sortieren](/help/assets/icons/SortOrderDown.svg) für absteigend).

![Beispiel für Mehrfachsortierung](assets/dimensions-multiple-sort.png)

#### Sortierpriorität

Wenn Sie Daten für mehrere Spalten sortieren, werden die Daten nach der Priorität sortiert, die Sie jeder Spalte zuweisen. Die Prioritätsnummerierung wird neben dem Sortiersymbol (![-Symbol für Sortierpriorität](assets/sort-priority-icon.png) angezeigt.

Die Spalte mit der primären Priorität bestimmt die Hauptreihenfolge; die Spalte mit der sekundären Priorität bestimmt die Reihenfolge, wenn Zeilen in der primären Spalte denselben Wert haben; die Spalte mit der tertiären Priorität bestimmt die Reihenfolge, wenn Zeilen in der primären und sekundären Spalte denselben Wert haben; und so weiter.

Betrachten Sie beispielsweise eine Tabelle mit den folgenden Spalten:

* Tag des Monats (Dimension)

* Stunde des Tages (Dimension)

* Ereignisse (Metrik)

Sie können jeder Spalte wie folgt eine Sortierpriorität zuweisen:

| Name der Spalte (Komponente) | Typ der Komponente | Sortierpriorität |
|---------|----------|---------|
| Tag des Monats | Dimension | 1 |
| Stunde des Tages | Dimension | 2 |
| Ereignisse | Metrik | 3 |

Indem Sie jeder Spalte eine Sortierpriorität zuweisen, können Sie genau steuern, wie die Daten in der Tabelle angezeigt werden. In diesem Beispiel werden die Informationen zunächst nach Tag des Monats, dann nach Tageszeit und schließlich nach Ereignissen sortiert.

![Beispiel für Mehrfachsortierung](assets/dimensions-multiple-sort.png)

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

* Aufschlüsseln eines Dimensionselements in der Freiformtabelle nach einer sekundären Dimension. Für die sekundäre Dimension können bis zu 200 Dimensionselemente angezeigt werden.

### Hinzufügen von Aufschlüsselungen zu einer Tabelle mit mehreren Dimensionsspalten

Wenn Sie einer Tabelle mit mehreren Dimensionsspalten eine Aufschlüsselung hinzufügen, umfasst die Aufschlüsselung alle Dimensionselemente in der Zeile, in der Sie sie hinzufügen.

Sie können eine Aufschlüsselung hinzufügen, wie in [Dimensionen aufschlüsseln](/help/components/dimensions/t-breakdown-fa.md) beschrieben.

## Nicht unterstützte Dimensionen {#unsupported}

Die folgenden Dimensionskombinationen werden nicht unterstützt und Analysis Workspace verbietet entweder das Hinzufügen oder zeigt eine Fehlermeldung an, nachdem sie hinzugefügt wurden:

* Mehrere Dimensionen, die aus Feldern stammen, die auf verschiedene [Arrays von Objekten](/help/use-cases/object-arrays.md) verweisen, die zusammen in derselben Freiformtabelle verwendet werden.

  Mehrere Dimensionen sind in derselben Freiformtabelle zulässig, wenn sie auf dasselbe Array von Objekten verweisen.