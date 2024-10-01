---
description: Erfahren Sie, wie Sie die Touchpoints angeben, um eine mehrdimensionale Fallout-Sequenz zu erstellen.
title: Fallout-Visualisierung konfigurieren
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
role: User
source-git-commit: 664756b796e8915a701ccabfb5f250e777701b60
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 36%

---

# Fallout-Visualisierung konfigurieren

Sie können die Touchpoints angeben, um eine mehrdimensionale Fallout-Sequenz zu erstellen. Ein Touchpoint ist im Allgemeinen eine Seite auf Ihrer Website. Touchpoints sind jedoch nicht auf Webseiten eingeschränkt. Sie können beispielsweise Ereignisse wie Einheiten sowie Unique Users und Wiederkehrbesuche hinzufügen. Auch Dimensionen können Sie hinzufügen (wie Kategorie, Browsertyp oder interner Suchbegriff).

Sie können sogar Filter innerhalb eines Touchpoints hinzufügen. Sie können beispielsweise Filter vergleichen, z. B. Benutzer von iOS und Android™. Wenn Sie die gewünschten Filter per Drag-and-Drop an den oberen Rand des Fallouts ziehen, werden Informationen über diese Filter zum Fallout-Bericht hinzugefügt. Wenn Sie nur diese Filter anzeigen möchten, können Sie die Grundlinie Alle Besuche entfernen.

Die Anzahl der Schritte, die Sie hinzufügen können, und die Anzahl der verwendeten Dimensionen sind nicht beschränkt.

Sie können Pfade für Dimensionen, Metriken und Filter erstellen. Angenommen, jemand sucht auf einer Seite nach Schuhe, Hemd und auf der nächsten Seite nach Hemd, Socken. Der nächste Produktflussbericht von Schuhe wird „Shirt und Socken“ lauten, NICHT „Shirt“.

## Verwenden Sie stattdessen 

1. Fügen Sie eine Visualisierung für ![ConversionTrichter](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL Fallout]** hinzu. Siehe [Hinzufügen einer Visualisierung zu einem Bedienfeld](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Ziehen Sie eine Seite, z. B. die Startseite, aus der Dimension Seite in das Dropdown-Menü *Touchpoint hinzufügen* .

   ![Die Startseite aus der Dimension &quot;Startseite&quot;wurde in das Feld &quot;Touchpoint hinzufügen&quot;gezogen.](assets/fallout-drag.png)

   Bewegen Sie den Mauszeiger über einen Touchpoint, um den Fallout und andere Informationen zu dieser Ebene anzuzeigen, z. B. den Namen des Touchpoints und die Personenanzahl an diesem Punkt. Sehen Sie sich die Erfolgsrate für diesen Touchpoint an (und vergleichen Sie die Erfolgsrate mit anderen Touchpoints).

   Die umkreisten Zahlen im grauen Abschnitt der Leiste zeigen den Fallout zwischen Touchpoints an (nicht den gesamten Fallout bis zu diesem Punkt). Der **[!UICONTROL Touchpoint %]** zeigt den erfolgreichen Durchbruch vom vorherigen Schritt zum aktuellen Schritt im Fallout-Bericht an.

   Sie können auch eine einzelne Seite anstatt der gesamten Dimension zum Fallout-Bericht hinzufügen. Klicken Sie auf den Pfeil ![ChevronRight](/help/assets/icons/ChevronRight.svg) auf der Seitendimension, um eine bestimmte Seite auszuwählen, die dem Fallout-Bericht hinzugefügt werden soll.

1. Fügen Sie weitere Touchpoints hinzu, bis Ihre Sequenz vollständig ist.

   Sie können **mehrere Touchpoints kombinieren** , indem Sie eine oder mehrere zusätzliche Komponenten auf einen Touchpoint ziehen.

   >[!NOTE]
   >
   >Hinweis: Mehrere Segmente werden mit AND verbunden, mehrere Elemente wie Dimensionselemente und Metriken hingegen mit OR.

   ![Die Seiten:CamerRoll oder Seite: Kamera-Touchpoints hervorgehoben.](assets/fallout-or.png)

1. Sie können einzelne Touchpoints auch auf das nächste Ereignis **(im Gegensatz zu *letztendlich*) im Pfad beschränken.** Unter jedem Touchpoint befindet sich ein Selektor mit den Optionen **[!UICONTROL Eventual path]** und **[!UICONTROL Next event]**, wie hier dargestellt:

   ![Die Ansicht &quot;Alle Besuche&quot;mit der Option &quot;Pfad am Ende&quot;wurde hervorgehoben. ](assets/fallout-nexthit.png)

   | Option | Beschreibung |
   |---|---|
   | **[!UICONTROL Eventual path]** (Standard) | Personen werden gezählt, die *schließlich* auf der nächsten Seite im Pfad landen, aber nicht notwendigerweise beim nächsten Ereignis. |
   | **[!UICONTROL Nächstes Ereignis]** | werden gezählt, die auf der nächsten Seite im Pfad des nächsten Ereignisses landen. |


## Einstellungen

Im Rahmen der Visualisierung sind spezifische Einstellungen verfügbar.

| Fallout-Container | Beschreibung |
|--- |--- |
| **[!UICONTROL Sitzung]** oder **[!UICONTROL Person]** | Wechseln Sie zwischen [!UICONTROL Sitzung] und [!UICONTROL Person], um die Personenpfade zu analysieren. Der Standardwert ist [!UICONTROL Person]. Diese Einstellungen helfen Ihnen, das Engagement von Personen auf Personenebene (über Sitzungen hinweg) zu verstehen, oder die Analyse auf eine einzelne Sitzung zu beschränken. |


## Kontextmenü

Im Rahmen der Visualisierung sind spezifische Kontextmenüoptionen verfügbar.

![Fallout-Optionen](assets/fallout-options.png)

| Option | Beschreibung |
|--- |--- |
| **[!UICONTROL Trend-Touchpoint]** | Zeigt Trenddaten für einen Touchpoint in einem Kantengraphen mit einigen vorab definierten Anomalieerkennungsdaten an. |
| **[!UICONTROL Trend-Touchpoint (%)]** | Trends für den gesamten Fallout-Prozentsatz. |
| **[!UICONTROL Trend für alle Touchpoints (%)]** | Zeigt die Trends für alle Touchpoint-Prozentsätze im Fallout (außer **[!UICONTROL Alle Personen]**, sofern vorhanden) im selben Diagramm an. |
| **[!UICONTROL Aufschlüsseln des Fallthrough an diesem Touchpoint]** | Sehen Sie sich an, welche Personen zwischen zwei Touchpoints (diesem Touchpoint und dem nächsten Touchpoint) ausgeführt haben, wenn sie zum nächsten Touchpoint übergegangen sind. Diese Option erstellt eine Freiformtabelle, die Ihre Dimensionen enthält. Dimensionen und andere Elemente der Tabelle können Sie austauschen. |
| **[!UICONTROL Trichteranalyse an diesem Touchpoint aufschlüsseln]** | Zeigt an, was Besucher, die nicht im Trichter verblieben sind, unmittelbar nach dem ausgewählten Schritt getan haben. |
| **[!UICONTROL Filter aus Touchpoint erstellen]** | Erstellen Sie einen neuen Filter aus dem ausgewählten Touchpoint. |

>[!MORELIKETHIS]
>
>[Hinzufügen einer Visualisierung zu einem Bedienfeld](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualisierungseinstellungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Kontextmenü &quot;Visualisierung&quot;](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

