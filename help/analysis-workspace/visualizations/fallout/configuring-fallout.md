---
description: Erfahren Sie, wie Sie die Touchpoints konfigurieren und angeben, um eine mehrdimensionale Fallout-Sequenz zu erstellen.
title: Fallout-Visualisierung konfigurieren
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
role: User
source-git-commit: d91e6aaebd14bc02f53b28820dd6013350e36d36
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 71%

---

# Fallout-Visualisierung konfigurieren {#configure-fallout-visualization}


Sie können die Touchpoints angeben, um eine mehrdimensionale Fallout-Sequenz zu erstellen. Normalerweise ist ein Touchpoint eine Seite auf Ihrer Site. Touchpoints sind jedoch nicht auf Seiten beschränkt. So können Sie zum Beispiel Ereignisse (wie Einheiten) sowie eindeutige Personen und erneute Besuche hinzufügen. Sie können auch Dimensionen hinzufügen, z. B. eine Kategorie, einen Browser-Typ oder einen internen Suchbegriff.

Sie können sogar Segmente innerhalb eines Touchpoints hinzufügen. Vielleicht möchten Sie zum Beispiel Segmente vergleichen (wie etwa iOS- und Android™-Benutzende). Wenn Sie die gewünschten Segmente an die Oberseite des Trichters ziehen, werden Informationen über diese Segmente zum Fallout-Bericht hinzugefügt. Wenn Sie möchten, dass nur diese Segmente angezeigt werden, können Sie die Grundlinie „Alle Besuche“ entfernen.

Es gibt keine Einschränkungen bezüglich der Anzahl der Schritte, die hinzugefügt werden können, oder der Dimensionen, die verwendet werden können.

Sie können Pfade für Dimensionen, Metriken und Segmente erstellen. Beispiel: Angenommen, jemand sucht auf der einen Seite nach „Schuhe, Shirt“ und auf der nächsten Seite nach „Schuhe, Socken“. Der nächste Produktflussbericht von Schuhe wird „Shirt und Socken“ lauten, NICHT „Shirt“.

## Verwenden

1. Fügen Sie eine Visualisierung des Typs ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL Fallout]** hinzu. Weitere Informationen finden Sie unter [Hinzufügen einer Visualisierung in einem Bedienfeld](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Ziehen Sie eine Seite, z. B. die Startseite, aus der Dimension Seite in das Dropdown *Menü* Touchpoint hinzufügen“.

   ![Die Startseite aus der Dimension „Seite“, die in das Feld „Touchpoint hinzufügen“ gezogen wurde.](assets/fallout-drag.png)

   Bewegen Sie den Mauszeiger über einen Touchpoint, um den Fallout und andere Informationen zu dieser Ebene anzuzeigen, wie z. B. den Namen des Touchpoints und die Anzahl der Personen zu diesem Zeitpunkt. Zeigen Sie die Erfolgsrate für diesen Touchpoint an (und vergleichen Sie die Erfolgsrate mit anderen Touchpoints).

   Die umkreisten Zahlen im grauen Abschnitt der Leiste zeigen den Fallout zwischen Touchpoints an (nicht den gesamten Fallout bis zu diesem Punkt). **[!UICONTROL Touchpoint %]** zeigt den erfolgreichen Fallthrough vom vorherigen Schritt zum aktuellen Schritt im Fallout-Bericht an.

   Sie können auch eine einzelne Seite anstatt der gesamten Dimension zum Fallout-Bericht hinzufügen. Klicken Sie auf den rechten Pfeil ![ChevronRight](/help/assets/icons/ChevronRight.svg) auf der Dimension „Seite“, um die Seite auszuwählen, die Sie zum Fallout-Bericht hinzufügen möchten.

1. Fügen Sie weitere Touchpoints hinzu, bis Ihre Sequenz vollständig ist.

   Sie können **mehrere Touchpoints kombinieren**, indem Sie mindestens eine weitere Komponente auf einen Touchpoint ziehen. 

   >[!NOTE]
   >
   >Hinweis: Mehrere Segmente werden mit AND verbunden, mehrere Elemente wie Dimensionselemente und Metriken hingegen mit OR.

   ![Die Seite:CamerRoll oder Seite: Kamera-Touchpoints hervorgehoben.](assets/fallout-or.png)

1. **Einzelne Touchpoints können nun auch auf das nächste Ereignis** (statt *am Ende*) im Pfad eingegrenzt werden. Unter jedem Touchpoint befinden sich die Auswahlmöglichkeiten **[!UICONTROL Endgültiger Pfad]** und **[!UICONTROL Nächstes Ereignis]**:

   ![Die Ansicht „Alle Besuche“ mit hervorgehobener Option „Endgültiger Pfad“. &#x200B;](assets/fallout-nexthit.png)

   | Option | Beschreibung |
   |---|---|
   | **[!UICONTROL Endgültiger Pfad]** (Standard) | Es werden die Besuchenden gezählt, die *am Ende* auf der nächsten Seite im Pfad, aber nicht notwendigerweise beim nächsten Ereignis landen. |
   | **[!UICONTROL Nächstes Ereignis]** | Personen werden gezählt, die beim nächsten Ereignis auf der nächsten Seite im Pfad landen. |


## Einstellungen {#settings}

>[!CONTEXTUALHELP]
>id="workspace_fallout_container"
>title="Fallout-Container"
>abstract="Wählen Sie einen Container aus, um den Pfad zu analysieren. Diese Auswahl hilft Ihnen, Interaktionen zu verstehen, und schränkt die Analyse auf den ausgewählten Container ein."

Im Rahmen der Visualisierung sind bestimmte Einstellungen verfügbar.

| Fallout-Container | Beschreibung |
|--- |--- |
| **[!UICONTROL Sitzung]** oder **[!UICONTROL Person]** | Sie können bei der Analyse der Personenpfade zwischen [!UICONTROL Sitzung] und [!UICONTROL Person] wechseln. Die Standardeinstellung ist [!UICONTROL Person]. Diese Einstellungen helfen Ihnen, das Engagement von Personen auf Personenebene (über Sitzungen hinweg) zu verstehen, oder die Analyse auf eine einzelne Sitzung zu beschränken. |


## Kontextmenü

Im Rahmen der Visualisierung sind bestimmte Kontextmenüoptionen verfügbar.

![Fallout-Optionen](assets/fallout-options.png)

| Option | Beschreibung |
|--- |--- |
| **[!UICONTROL Trend-Touchpoint]** | Zeigt Trend-Daten für einen Touchpoint in einem Liniendiagramm mit einigen vorab definierten Anomalieerkennungsdaten an. |
| **[!UICONTROL Trend-Touchpoint (%)]** | Trend für den gesamten Fallout-Prozentsatz. |
| **[!UICONTROL Trend aller Touchpoints (%)]** | Trend für alle Touchpoint-Prozentsätze im Fallout (außer **[!UICONTROL Alle Personen]**, falls vorhanden) im selben Diagramm |
| **[!UICONTROL Aufschlüsselung des Fallthroughs an diesem Touchpoint]** | Zeigt an, was Personen zwischen zwei Touchpoints (diesem und dem nächsten Touchpoint) getan haben, wenn sie sich zum nächsten Touchpoint fortbewegt haben. Diese Option erstellt eine Freiformtabelle, die Ihre Dimensionen enthält. Sie können Dimensionen und andere Elemente der Tabelle ersetzen. Beispiel: eine Tabelle mit der Beschriftung **[!UICONTROL Durchlauf: Alle Personen > Seite ist gleich einer der Startseiten]** und **[!UICONTROL Seite]** als Dimension und **[!UICONTROL Personen]** segmentiert durch das [Nur-Projekt-Schnellsegment](/help/components/segments/seg-quick.md)**[!UICONTROL Durchlauf: Alle Personen > Seite ist gleich einer der]**. Überprüfen Sie das Segment, um zu verstehen, wie das Fallthrough-Segment bestimmt wird. |
| **[!UICONTROL Aufschlüsselung des Fallouts an diesem Touchpoint]** | Zeigt an, was Benutzer, die es nicht über die funnel geschafft haben, unmittelbar nach dem ausgewählten Schritt getan haben. Diese Option erstellt eine Freiformtabelle, die Ihre Dimensionen enthält. Sie können Dimensionen und andere Elemente der Tabelle ersetzen. Beispiel: Eine Tabelle mit der Beschriftung **[!UICONTROL Fallout: Personen > Seite entspricht einer der]** und **[!UICONTROL Seite]** als Dimension und **[!UICONTROL Personen]** segmentiert durch das [Nur-Projekt-Schnellsegment](/help/components/segments/seg-quick.md)**[!UICONTROL Fallthrough: Alle Besucher > Seite entspricht einer der]** Segmente als Metrik enthält. Überprüfen Sie das Segment, um zu verstehen, wie das Fallout-Segment bestimmt wird. |
| **[!UICONTROL Erstellen von Segmenten aus Touchpoints]** | Erstellen Sie ein neues Segment aus dem ausgewählten Touchpoint. |

>[!MORELIKETHIS]
>
>[Hinzufügen einer Visualisierung in einem Bedienfeld](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[Visualisierungseinstellungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[Kontextmenü der Visualisierung](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

