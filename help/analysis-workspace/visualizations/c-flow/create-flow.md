---
description: Erfahren Sie, wie Sie die Flussvisualisierung in einem Workspace-Projekt verwenden.
title: Konfigurieren einer Flussvisualisierung
feature: Visualizations
exl-id: 7055cbc9-19b3-40f0-b8d4-52d241224827
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '1433'
ht-degree: 37%

---

# Konfigurieren einer Flussvisualisierung

Flussvisualisierungen helfen Ihnen dabei, die Journey zu verstehen, die von einem bestimmten Konversionsereignis auf Ihrer Website oder in Ihrer App stammt. Oder bis zu einem bestimmten Konversionsereignis. Die Visualisierung verfolgt einen Pfad durch Ihre Dimensionen (und Dimensionselemente) oder Metriken.

Sie können den Beginn oder das Ende des Pfads konfigurieren, an dem Sie interessiert sind. Oder analysieren Sie alle Pfade, die durch eine Dimension oder ein Dimensionselement fließen.

![Der Bildschirm für die Flusskonfiguration mit den Feldern &quot;Beginnt mit&quot;, &quot;Enthält&quot;und &quot;Endet mit&quot;](assets/new-flow.png).

## Verwenden Sie stattdessen 

1. Fügen Sie eine Visualisierung für ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Fluss]** hinzu. Siehe [Hinzufügen einer Visualisierung zu einem Bedienfeld](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Sie können Ihre Flussvisualisierung mithilfe einer der folgenden Optionen verankern:

   * [!UICONTROL **Beginnt mit**] (Metriken, Dimensionen oder Elemente) oder
   * [!UICONTROL **Enthält**] (Dimensionen oder Elemente) oder
   * [!UICONTROL **Endet mit**] (Metriken, Dimensionen oder Elemente)

   Jede dieser Kategorien wird auf dem Bildschirm als *Dropzone* angezeigt. Sie können den Ablagebereich auf drei Arten füllen:

   * Verwenden Sie das Dropdown-Menü, um Metriken oder Dimensionen auszuwählen.
   * Ziehen Sie Dimensionen oder Metriken aus dem linken Bereich.
   * Beginnen Sie mit der Eingabe des Namens einer Dimension oder Metrik und wählen Sie sie dann aus, wenn sie in der Dropdown-Liste angezeigt wird.

   >[!IMPORTANT]
   >
   >Berechnete Metriken können nicht in den Feldern **[!UICONTROL Beginnt mit]** oder **[!UICONTROL Endet mit]** verwendet werden.

1. Wenn Sie eine Metrik auswählen, müssen Sie auch eine [!UICONTROL **Pfade-Dimension**] bereitstellen, die als Pfad verwendet werden soll, der zu der ausgewählten Komponente führt oder von ihr stammt (siehe hier). Die Standardeinstellung ist [!UICONTROL **Seite**].

   ![Flusskonfiguration](assets/flow-configure.png)

1. (Optional) Wählen Sie **[!UICONTROL Erweiterte Einstellungen anzeigen]** aus, um eine der folgenden Optionen zu konfigurieren:


   | Einstellung | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Beschriftungen umbrechen]** | Die Bezeichnungen der Flusselemente werden üblicherweise aus Platzgründen auf dem Bildschirm abgeschnitten. Aktivieren Sie dieses Kontrollkästchen, um die gesamte Bezeichnung anzuzeigen.  Standard = deaktiviert. |
   | **[!UICONTROL Wiederholungsinstanzen einschließen]** | Flussvisualisierungen basieren auf Instanzen einer Dimension. Mit dieser Einstellung können Sie wiederholte Instanzen ein- oder ausschließen, z. B. Seitenneuladungen. Wiederholungen können jedoch nicht aus Flussvisualisierungen entfernt werden, die Dimensionen mit mehreren Werten enthalten, wie listVars, listProps, s.product, Merchandising-eVars usw. <p>Standardmäßig ist diese Option deaktiviert.</p> |
   | **[!UICONTROL Begrenzung auf erstes/letztes Auftreten]** | Begrenzen Sie Pfade auf Pfade, die mit dem ersten oder letzten Vorkommen einer Dimension, eines Elements oder einer Metrik beginnen oder enden. Eine detailliertere Erklärung finden Sie unter [Auf das erste/letzte Vorkommen beschränken](#example-scenario-for-limit-to-firstlast-occurrence) . |
   | **[!UICONTROL Anzahl der Spalten]** | Die Anzahl der Spalten, die Ihr Flussdiagramm enthalten soll. Sie können maximal 5 Spalten angeben. |
   | **[!UICONTROL Erweiterte Elemente pro Spalte]** | Die Anzahl der Elemente, die jede Spalte enthalten soll. Sie können pro Spalte maximal 10 erweiterte Elemente angeben. |
   | **[!UICONTROL Fluss-Container]** | Sie können zwischen **[!UICONTROL Sitzungen]** und **[!UICONTROL Person]** wechseln, um Pfade zu analysieren. Diese Einstellungen helfen Ihnen dabei, die Interaktion einer Person auf Personenebene (sitzungsübergreifend) zu verstehen oder die Analyse auf eine einzelne Sitzung zu beschränken. |

   >[!IMPORTANT]
   >
   >Die Kombination von **[!UICONTROL Anzahl der Spalten]** und **[!UICONTROL Erweiterte Elemente pro Spalte]** bestimmt die Anzahl der zugrunde liegenden Anfragen, die zum Erstellen der Flussvisualisierung erforderlich sind. Je höher diese Zahlen sind, desto länger dauert das Rendern einer Visualisierung.


1. Wählen Sie **[!UICONTROL Erstellen]** aus.


### Beispiel

Angenommen, Sie möchten den Pfad verfolgen, den Benutzer zu den beliebtesten Seiten Ihrer Site und von diesen aus eingeschlagen haben.

1. Erstellen Sie eine Flussvisualisierung wie oben beschrieben.
1. Ziehen Sie die Dimension [!UICONTROL **Seite**] in das Feld **[!UICONTROL Enthält]** und wählen Sie [!UICONTROL **Erstellen**] aus.
1. Die Flussvisualisierung wird erstellt, wobei die am häufigsten angezeigte Seite im Fokusknoten in der Mitte der Visualisierung angezeigt wird. Sie sehen auch die oberen Seiten, die zu dieser Seite führen (links neben dem Fokusknoten), sowie die oberen Seiten, die von dieser Seite weg führen (rechts neben dem Fokusknoten).
1. Analysieren Sie die Daten im Fluss, wie in [Konfigurieren](#configure) beschrieben.


## Konfigurieren

Eine Zusammenfassung der Flusskonfiguration wird oben in den Visualisierungen angezeigt. Die Pfade in dem Diagramm sind proportional. Pfade mit mehr Aktivität werden dicker dargestellt.

![Beispiel für eine Flussausgabe, in dem Ends with Visits, Pathing dimension: Page, and Flow container: Visitors.](assets/flow-output.png)

Um die Daten weiter zu untersuchen, haben Sie mehrere Möglichkeiten:

* Das Flussdiagramm ist interaktiv. Wenn Sie den Mauszeiger über das Diagramm halten, werden jeweils andere Details angezeigt.

* Wenn Sie einen Knoten in dem Diagramm auswählen, werden die zugehörigen Details zu diesem Knoten angezeigt. Wählen Sie den Knoten erneut aus, um ihn zu reduzieren.

  ![Beispiel für ein interaktives Flussdiagramm mit Knotendetails.](assets/node-details.png)

* Sie können eine Spalte so filtern, dass nur bestimmte Ergebnisse angezeigt werden, z. B. das Ein- und Ausschließen, die Angabe von Kriterien usw.

* Wählen Sie auf der linken oder rechten Seite ![Kreis hinzufügen](/help/assets/icons/AddCircle.svg) aus, um eine Spalte zu erweitern.

* Verwenden Sie zum Anpassen der Ausgabe die Optionen im [Kontextmenü](#context-menu) .

* Um den Fluss zu bearbeiten oder mit verschiedenen Optionen neu zu erstellen, wählen Sie neben der Konfigurationsübersicht die Option ![Bearbeiten](/help/assets/icons/Edit.svg) aus.

## Filter

Über jeder Spalte wird ein Filter ![Filter](/help/assets/icons/Filter.svg) angezeigt, wenn Sie den Mauszeiger darüber bewegen. Durch Auswahl des Filters erhalten Sie dasselbe Filterdialogfeld wie in der Freiformtabelle. Siehe [Filtern und Sortieren](freeform-table/../../freeform-table/filter-and-sort.md).

* Verwenden Sie **[!UICONTROL Erweitert anzeigen]** , um erweiterte Einstellungen so zu konfigurieren, dass bestimmte Kriterien mit einer Benutzerliste ein- oder ausgeschlossen werden. Weitere Informationen finden Sie unter [Filter und Sortieren](../freeform-table/filter-and-sort.md) .
* Nachdem Sie eine Spalte gefiltert haben, spiegelt diese Spalte die Filterung wider. Ein blauer ![Filter](/help/assets/icons/FilterColored.svg) gibt an, dass die Spalte gefiltert ist.  Der Filter reduziert die Spalte entweder, sodass nur das im Filter zulässige Element angezeigt wird. Alternativ werden alle Elemente entfernt, mit Ausnahme des Elements, das Sie im Filter verwenden möchten.
* Alle nachgelagerten und vorgelagerten Spalten bleiben bestehen, solange Daten in die verbleibenden Knoten fließen.
* Um einen Filter zu entfernen, wählen Sie ![Filter](/help/assets/icons/Filter.svg) aus, um das Filtermenü zu öffnen. Entfernen Sie alle angewendeten Filter und wählen Sie **[!UICONTROL Speichern]** aus. Der Fluss sollte zum vorherigen, ungefilterten Status zurückkehren.

## Kontextmenü

Verwenden Sie ein Kontextmenü für einen beliebigen Knoten in der Flussvisualisierung mit den folgenden Optionen:

| Option | Beschreibung |
|--- |--- |
| **[!UICONTROL Auf diesen Knoten fokussieren]** | Wechselt den Fokus auf den ausgewählten Knoten. Der Fokusknoten wird in der Mitte des Flussdiagramms angezeigt. |
| **[!UICONTROL Neu starten]** | Kehren Sie zum Freiform-Diagramm-Builder zurück, in dem Sie ein neues Flussdiagramm erstellen können. |
| **[!UICONTROL Erstellen eines Filters für diesen Pfad]** | Erstellen Sie einen Filter. Diese Auswahl führt Sie in den Filter-Builder, in dem Sie den neuen Filter konfigurieren können. |
| **[!UICONTROL Aufschlüsselung]** | Hiermit können Sie den Knoten nach verfügbaren Dimensionen, Metriken oder Zeiten aufschlüsseln. |
| **[!UICONTROL Spalte filtern]** | Dieselben Filteroptionen werden wie in der Freiformtabelle angezeigt. Weitere Informationen zu den verfügbaren Optionen finden Sie im Abschnitt &quot;Anwenden eines einfachen oder erweiterten Filters auf eine Tabelle&quot;unter [Filtern und Sortieren von Tabellen](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). |
| **[!UICONTROL Element ausschließen]** oder **[!UICONTROL Ausgeschlossene Elemente wiederherstellen]** | Entfernt einen bestimmten Knoten aus der Spalte und erstellt daraus automatisch einen Filter oben in der Spalte. Um das ausgeschlossene Element wiederherzustellen, wählen Sie im Kontextmenü die Option **[!UICONTROL Ausgeschlossenes Element wiederherstellen]** aus. Sie können den Filter auch oben in der Spalte öffnen und die Box mit dem Element entfernen, das Sie gerade ausgeschlossen haben. |
| **[!UICONTROL Trend]** | Mit dieser Option erstellen Sie ein Trenddiagramm für den Knoten. |
| **[!UICONTROL Nächste Spalte anzeigen]** / **[!UICONTROL Vorherige Spalte anzeigen]** | Zeigt die nächste (rechte) oder vorherige (linke) Spalte der Visualisierung an. |
| **[!UICONTROL Spalte ausblenden]**n | Blendet die ausgewählte Spalte aus der Visualisierung aus. |
| **[!UICONTROL Gesamte Spalte erweitern]** | Hiermit erweitern Sie eine Spalte so, dass alle Knoten angezeigt werden. In der Standardeinstellung werden nur die obersten fünf Knoten angezeigt. |
| **[!UICONTROL Erstellen einer Zielgruppe aus Auswahl]** | Erstellt eine Audience basierend auf der ausgewählten Spalte. |
| **[!UICONTROL Gesamte Spalte reduzieren]** | Diese Option blendet alle Knoten in einer Spalte aus. |

## Begrenzung auf erstes/letztes Auftreten

Beachten Sie bei Verwendung dieser Option Folgendes:

* **[!UICONTROL Auf das erste/letzte Vorkommen beschränken]** zählt nur das erste/letzte Vorkommen in der Reihe. Alle anderen Vorkommen der Kriterien **[!UICONTROL Beginnt mit]** oder **[!UICONTROL Endet mit]** werden verworfen.
* Bei Verwendung mit einem Fluss **[!UICONTROL Beginnt mit]** wird nur das erste Vorkommen berücksichtigt, das den Startkriterien entspricht.
Im folgenden Beispiel sind **alle** Vorkommen von *Zum Warenkorb hinzufügen* und *Produkt-Hauptkategorie* in jedem Schritt des Flusses enthalten.
  ![Keine Begrenzung, zuerst ](assets/limitofffirst.png)

  Im folgenden Beispiel werden nur die **ersten** Vorkommen von *Zum Warenkorb hinzufügen* und *Produkt-Hauptkategorie* in jedem Schritt des Flusses eingeschlossen.
  ![Lint, start](assets/limitonfirst.png)
* Bei Verwendung mit dem Fluss **[!UICONTROL Endet mit]** wird nur das letzte Vorkommen berücksichtigt, das den Endkriterien entspricht.
Im folgenden Beispiel sind **alle** Vorkommen von *Produkt-Hauptkategorie* und *Zum Warenkorb hinzufügen* in jedem Schritt des Flusses enthalten.
  ![Keine Begrenzung, zuerst ](assets/limitofflast.png)

  Im folgenden Beispiel werden nur die **letzten** Vorkommen von *Produkt-Hauptkategorie* und *Zum Warenkorb hinzufügen* in jedem Schritt des Flusses eingeschlossen.
  ![Lint, start](assets/limitonlast.png)
* Die verwendete Reihe unterscheidet sich je nach Container. Bei Verwendung des Containers **[!UICONTROL Person]** handelt es sich bei der Ereignisreihe um die Sitzung. Bei Verwendung des Containers **[!UICONTROL Sitzung]** sind die Ereignisreihen alle Ereignisse für einen bestimmten Benutzer im angegebenen Datumsbereich.
* Die Option **[!UICONTROL Auf das erste/letzte Vorkommen beschränken]** kann in den erweiterten Einstellungen konfiguriert werden, wenn ein Metrik- oder Dimension-Element in den Feldern **[!UICONTROL Beginnt mit]** oder **[!UICONTROL Endet mit]** verwendet wird.


>[!MORELIKETHIS]
>
>[Hinzufügen einer Visualisierung zu einem Bedienfeld](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualisierungseinstellungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Kontextmenü &quot;Visualisierung&quot;](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

