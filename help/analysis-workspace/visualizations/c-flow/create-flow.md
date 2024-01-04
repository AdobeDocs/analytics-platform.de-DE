---
description: Erfahren Sie, wie Sie die Flussvisualisierung in einem Workspace-Projekt verwenden.
title: Konfigurieren einer Flussvisualisierung
feature: Visualizations
exl-id: 7055cbc9-19b3-40f0-b8d4-52d241224827
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1595'
ht-degree: 56%

---

# Flussvisualisierung konfigurieren

Flussvisualisierungen helfen Ihnen dabei, die Journey zu verstehen, die von einem bestimmten Konversionsereignis auf Ihrer Website oder in Ihrer App ausgehen oder dazu führen. Sie verfolgt einen Pfad durch Ihre Dimensionen (und Dimensionselemente) oder Metriken.

Mit Flussvisualisierungen können Sie den Anfang oder das Ende des Pfads, an dem Sie interessiert sind, konfigurieren oder alle Pfade analysieren, die durch eine Dimension oder ein Dimensionselement fließen.

![Im Konfigurationsbildschirm &quot;Fluss&quot;werden die Felder &quot;Beginnt mit&quot;, &quot;Enthält&quot;und &quot;Endet mit&quot;angezeigt.](assets/new-flow.png)

## Erstellen einer Flussvisualisierung {#configure}

1. Fügen Sie ein leeres Bedienfeld zu Ihrem Projekt hinzu, wählen Sie in der linken Leiste das Symbol Visualisierungen aus und ziehen Sie dann die [!UICONTROL **Fluss**] Visualisierung in das Bedienfeld ein.

   Oder

   Fügen Sie eine Visualisierung auf eine der im Abschnitt &quot;Visualisierungen zu einem Bedienfeld hinzufügen&quot;unter [Visualisierungen - Übersicht](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Die Flussvisualisierung können Sie mit einer der folgenden Optionen verankern:

   * [!UICONTROL **Beginnt mit**] (Metriken, Dimensionen oder Elemente) oder
   * [!UICONTROL **Enthält**] (Dimensionen oder Elemente) oder
   * [!UICONTROL **Endet mit**] (Metriken, Dimensionen oder Elemente)

   Jede dieser Kategorien wird auf dem Bildschirm als ein Ablagebereich angezeigt. Sie können den Ablagebereich auf drei Arten füllen:

   * Verwenden Sie das Dropdown-Menü, um Metriken oder Dimensionen auszuwählen.
   * Ziehen Sie Dimensionen oder Metriken aus der linken Leiste.
   * Beginnen Sie mit der Eingabe des Namens einer Dimension oder Metrik und wählen Sie sie dann aus, wenn sie in der Dropdown-Liste angezeigt wird.

   >[!IMPORTANT]
   >
   >Berechnete Metriken können nicht im  **[!UICONTROL Beginnt mit]** oder **[!UICONTROL Endet in]** -Felder.

1. Wenn Sie eine Metrik auswählen, müssen Sie auch eine [!UICONTROL **Pathing-Dimension**] , um als Pfad zu verwenden, der zu Ihrer ausgewählten Komponente führt oder von dieser weg führt, wie hier dargestellt. Die Standardeinstellung ist [!UICONTROL **Seite**].

   ![Die Pfaddimension.](assets/pathing-dim.png)

1. (Optional) Wählen Sie **[!UICONTROL Erweiterte Einstellungen anzeigen]** um eine der folgenden Optionen zu konfigurieren:

   ![Erweiterte Einstellungen mit Anzeigeoptionen, Anzahl der Spalten und Fluss-Container.](assets/adv-settings.png)

   | Einstellung | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Beschriftungen umbrechen]** | Die Bezeichnungen der Flusselemente werden üblicherweise aus Platzgründen auf dem Bildschirm abgeschnitten. Aktivieren Sie dieses Kontrollkästchen, um die gesamte Bezeichnung anzuzeigen.  Standard = deaktiviert. |
   | **[!UICONTROL Wiederholungsinstanzen einschließen]** | Flussvisualisierungen basieren auf Instanzen einer Dimension. Diese Einstellung gibt Ihnen die Möglichkeit, wiederholte Instanzen ein- oder auszuschließen, z. B. Seitenneuladungen. Wiederholungen können jedoch nicht aus Flussvisualisierungen entfernt werden, die Dimensionen mit mehreren Werten enthalten, wie listVars, listProps, s.product, Merchandising-eVars usw. <p>Standardmäßig ist diese Option deaktiviert.</p> |
   | **[!UICONTROL Begrenzung auf erstes/letztes Auftreten]** | Begrenzen Sie Pfade auf jene, die mit dem ersten/letzten Vorkommen einer Dimension/eines Elements/einer Metrik beginnen/enden. Siehe den Abschnitt unten. [Beispielszenario für &quot;Beschränkung auf das erste/letzte Vorkommen&quot;](#example-scenario-for-limit-to-firstlast-occurrence), um eine ausführlichere Erläuterung zu erhalten. |
   | **[!UICONTROL Anzahl der Spalten]** | Die Anzahl der Spalten, die in Ihrem Flussdiagramm angezeigt werden sollen. Sie können maximal 5 Spalten angeben. |
   | **[!UICONTROL Elemente pro Spalte erweitert]** | Die Anzahl der Elemente, die in jeder Spalte angezeigt werden sollen. Sie können pro Spalte maximal 10 erweiterte Elemente angeben. |
   | **[!UICONTROL Flussbehälter]** | <ul><li>Besuch</li><li>Besucher.</li></ul> Hiermit können Sie bei der Analyse der Besucherpfade zwischen Besuch und Besucher wechseln. Mithilfe dieser Einstellungen können Sie Einblicke in Besucheraktivitäten auf der Besucherebene (besuchsübergreifend) erhalten oder die Analyse auf einen einzelnen Besuch einschränken. |

   >[!IMPORTANT]
   >
   >Die Kombination **[!UICONTROL Anzahl der Spalten]** und **[!UICONTROL Elemente pro Spalte erweitert]** bestimmen die Anzahl der zugrunde liegenden Anforderungen, die zum Erstellen der Flussvisualisierung erforderlich sind. Je höher diese Zahlen sind, desto länger dauert das Rendern einer Visualisierung.


1. Auswählen **[!UICONTROL Build]**.

>[!INFO]
>
>**Beispiel:** Angenommen, Sie möchten den Pfad verfolgen, den Benutzer zu den beliebtesten Seiten Ihrer Site und von diesen aus eingeschlagen haben.
>
>Dazu würden Sie
>
>1. Erstellen Sie eine Flussvisualisierung wie oben beschrieben.
>1. Ziehen Sie die [!UICONTROL **Seite**] Dimension in die **[!UICONTROL Enthält]** und wählen Sie [!UICONTROL **Build**].
>1. Die Flussvisualisierung wird mit der am häufigsten angezeigten Seite erstellt, die im Fokusknoten in der Mitte der Visualisierung angezeigt wird. Sie sehen auch die obersten Seiten, die zu dieser Seite führen (links neben dem Fokusknoten), sowie die obersten Seiten, die aus dieser Fokusseite führen (rechts neben dem Fokusknoten).
>1. Daten im Fluss analysieren, wie unter [Flussausgabe anzeigen und ändern](#view-and-change-the-flow-output).

## Flussausgabe anzeigen und ändern {#output}

![Beispiel für die Flussausgabe mit Ends with Visits, Pathing dimension: Page, and Flow container: Visitors.](assets/flow-output.png)

Eine Zusammenfassung der Flusskonfiguration wird oben im Diagramm angezeigt. Die Pfade in dem Diagramm sind proportional. Pfade mit mehr Aktivität werden dicker dargestellt.

Um die Daten weiter zu untersuchen, haben Sie mehrere Möglichkeiten:

* Das Flussdiagramm ist interaktiv. Wenn Sie den Mauszeiger über das Diagramm halten, werden jeweils andere Details angezeigt.

* Wenn Sie auf einen Knoten in dem Diagramm klicken, werden die zugehörigen Details zu diesem Knoten angezeigt. Klicken Sie erneut auf den Knoten, um ihn wieder zu reduzieren.

  ![Interaktives Flussdiagramm mit Knotendetails.](assets/node-details.png)

* Sie können eine Spalte so filtern, dass nur bestimmte Ergebnisse angezeigt werden, z. B. das Ein- und Ausschließen, die Angabe von Kriterien usw.

* Klicken Sie links auf das Pluszeichen (+), um eine Spalte zu erweitern.

* Verwenden Sie die unten erläuterten Rechtsklickoptionen, um die Ausgabe weiter anzupassen.

* Klicken Sie auf das Stiftsymbol neben der Konfigurationsübersicht, um den Fluss weiter zu bearbeiten oder ihn mit verschiedenen Optionen neu zu erstellen.

* Sie können Ihr Flussdiagramm als Teil der .CSV-Datei eines Projekts auch exportieren und weiter analysieren, indem Sie **[!UICONTROL Projekt]** > **[!UICONTROL CSV herunterladen]** aufrufen.

## Filtern

Über jeder Spalte wird ein Filter angezeigt, wenn Sie den Mauszeiger darüber bewegen. Wenn Sie auf den Filter klicken, sehen Sie dasselbe Filterdialogfeld, das heute auch in der Freiformtabelle vorhanden ist. Dieser Filter funktioniert genauso wie in der Freiformtabelle.

* Verwenden Sie die erweiterten Einstellungen, um bestimmte Kriterien in die Benutzerliste aufzunehmen oder auszuschließen.
* Nachdem Sie ein Element aus der Liste gefiltert haben, spiegelt diese Spalte die Filterung wider. (Der Filter reduziert sie entweder, um nur das im Filter zulässige Element anzuzeigen, oder er entfernt alle Elemente mit Ausnahme des Elements, das Sie im Filter verwenden möchten.
* Alle nachgelagerten und vorgelagerten Spalten sollten beibehalten werden, solange Daten in die verbleibenden Knoten fließen.
* Nach der Anwendung wird das Filtersymbol in Blau über der Spalte angezeigt, die gefiltert wird.
* Um einen Filter zu entfernen, klicken Sie auf das Filtersymbol, um das Filtermenü zu öffnen. Entfernen Sie alle angewendeten Filter und klicken Sie dann auf **[!UICONTROL Speichern]**. Der Fluss sollte zum vorherigen, ungefilterten Status zurückkehren.

## Rechtsklick-Optionen {#right-click}

| Option | Beschreibung |
|--- |--- |
| [!UICONTROL Auf diesen Knoten fokussieren] | Wechselt den Fokus auf den ausgewählten Knoten. Der Fokusknoten wird in der Mitte des Flussdiagramms angezeigt. |
| [!UICONTROL Neu beginnen] | Bringt Sie wieder zurück in den Freiform-Diagramm-Builder, in dem Sie ein neues Flussdiagramm erstellen können. |
| [!UICONTROL Filter für diesen Pfad erstellen] | Erstellen Sie einen Filter. Dadurch gelangen Sie zum Filtergenerator, in dem Sie den neuen Filter konfigurieren können. |
| [!UICONTROL Aufschlüsselung] | Hiermit können Sie den Knoten nach verfügbaren Dimensionen, Metriken oder Zeiten aufschlüsseln. |
| [!UICONTROL Filterspalte] | Dieselben Filteroptionen werden wie in der Freiformtabelle angezeigt. Weitere Informationen zu den verfügbaren Optionen finden Sie im Abschnitt &quot;Anwenden eines einfachen oder erweiterten Filters auf eine Tabelle&quot;unter [Tabellen filtern und sortieren](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). |
| [!UICONTROL Element ausschließen]/[!UICONTROL Ausgeschlossene Elemente wiederherstellen] | Entfernt einen bestimmten Knoten aus der Spalte und erstellt daraus automatisch einen Filter oben in der Spalte. Um das ausgeschlossene Element wiederherzustellen, klicken Sie erneut mit der rechten Maustaste und wählen Sie **[!UICONTROL Ausgeschlossenes Element wiederherstellen]**. Sie können den Filter auch oben in der Spalte öffnen und die Box mit dem Element entfernen, das Sie gerade ausgeschlossen haben. |
| [!UICONTROL Trend] | Mit dieser Option erstellen Sie ein Trenddiagramm für den Knoten. |
| Nächste Spalte anzeigen/Vorherige Spalte anzeigen | Zeigt die nächste (rechte) oder vorherige (linke) Spalte der Visualisierung an. |
| Spalte ausblenden | Blendet die ausgewählte Spalte aus der Visualisierung aus. |
| [!UICONTROL Gesamte Spalte erweitern] | Hiermit erweitern Sie eine Spalte so, dass alle Knoten angezeigt werden. In der Standardeinstellung werden nur die obersten fünf Knoten angezeigt. |
| Zielgruppe aus Auswahl erstellen | Erstellt eine Audience basierend auf der ausgewählten Spalte. |
| [!UICONTROL Gesamte Spalte reduzieren] | Diese Option blendet alle Knoten in einer Spalte aus. |

## Beispielszenario für „Beschränkung auf das erste/letzte Vorkommen“

Beachten Sie bei Verwendung dieser Option Folgendes:

* **[!UICONTROL Auf das erste/letzte Vorkommen beschränken]** zählt nur das erste/letzte Vorkommen in der Reihe. Alle anderen Vorkommen der Kriterien **[!UICONTROL Beginnt mit]** oder **[!UICONTROL Endet mit]** werden verworfen.
* Bei Verwendung mit einem Fluss des Typs **[!UICONTROL Beginnt mit]** wird nur das erste Vorkommen einbezogen, das den Startkriterien entspricht.
* Bei Verwendung mit einem Fluss des Typs **[!UICONTROL Endet mit]** wird nur das letzte Vorkommen einbezogen, das den Endkriterien entspricht.
* Die verwendete Reihe unterscheidet sich je nach Container. Wenn Sie die **[!UICONTROL Besuch]** -Container, wird die Ereignisreihe die Sitzung sein. Wenn Sie die **[!UICONTROL Besucher]** -Container enthalten, sind alle Ereignisse aus der Ereignisreihe für einen bestimmten Benutzer im angegebenen Datumsbereich.
* Die Option **[!UICONTROL Begrenzung auf erstes/letztes Auftreten]** kann in den erweiterten Einstellungen konfiguriert werden, wenn ein Metrik- oder Dimensionselement in den Feldern „Beginnt mit“ oder „Endet mit“ verwendet wird.

Beispielserie von Ereignissen:

Startseite > Produkte > Zum Warenkorb hinzufügen > Produkte > Zum Warenkorb hinzufügen > Rechnungsstellung > Bestellbestätigung

### Betrachten Sie eine Flussanalyse mit den folgenden Einstellungen:

* Beginn mit [!UICONTROL Zum Warenkorb hinzufügen] (Dimensionselement)
* Pfaddimension [!UICONTROL Seite]
* Container [!UICONTROL Besuch]

Wenn &quot;Auf das erste/letzte Vorkommen beschränken&quot;deaktiviert ist, würde diese einzelne Ereignisreihe zwei Vorkommen von &quot;Zum Warenkorb hinzufügen&quot;zählen.
Erwartete Flussausgabe: 
„Zum Warenkorb hinzufügen“ (2) —> „Produkte“ (1)
-> „Rechnungsstellung“ (1)

Wenn jedoch &quot;Auf das erste/letzte Vorkommen begrenzen&quot;aktiviert ist, wird nur das erste Vorkommen von &quot;Zum Warenkorb hinzufügen&quot;in die Analyse aufgenommen.
Erwartete Flussausgabe:
„Zum Warenkorb hinzufügen“ (1) —> „Produkte“ (1)

### Betrachten Sie die gleiche Reihe von Ereignissen mit den folgenden Einstellungen:

* Endet mit [!UICONTROL Zum Warenkorb hinzufügen] (Dimensionselement)
* Pfaddimension [!UICONTROL Seite]
* Container [!UICONTROL Besuch]

Wenn **[!UICONTROL Auf das erste/letzte Vorkommen beschränken]** is *disabled*, würde diese einzelne Ereignisreihe zwei Vorkommen von &quot;Zum Warenkorb hinzufügen&quot;zählen.
Erwartete Flussausgabe: 
„Produkte“ (2) &lt;— „Zum Warenkorb hinzufügen“ (2)

Wenn jedoch **[!UICONTROL Begrenzung auf erstes/letztes Auftreten]** *aktiviert* ist, würde nur das letzte Auftreten von [!UICONTROL Zum Warenkorb hinzufügen] in die Analyse einbezogen.
Erwartete Flussausgabe: 
„Produkte“ (1) &lt;— „Zum Warenkorb hinzufügen“ (1)
