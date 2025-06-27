---
description: Erfahren Sie, wie Sie die Touchpoints konfigurieren und angeben, um eine mehrdimensionale Fallout-Sequenz zu erstellen.
title: Fallout-Visualisierung konfigurieren
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 92%

---

# Fallout-Visualisierung konfigurieren {#configure-fallout-visualization}


Sie können die Touchpoints angeben, um eine mehrdimensionale Fallout-Sequenz zu erstellen. Ein Touchpoint ist im Allgemeinen eine Seite auf Ihrer Website. Touchpoints sind jedoch nicht auf Webseiten eingeschränkt. So können Sie zum Beispiel Ereignisse (wie Einheiten) sowie eindeutige Personen und erneute Besuche hinzufügen. Auch Dimensionen können Sie hinzufügen (wie Kategorie, Browsertyp oder interner Suchbegriff).

Sogar Segmente können Sie innerhalb eines Touchpoints hinzufügen. Vielleicht möchten Sie zum Beispiel Segmente vergleichen (wie etwa iOS- und Android™-Benutzende). Wenn Sie die gewünschten Segmente an die Oberseite des Trichters ziehen, werden Informationen über diese Segmente zum Fallout-Bericht hinzugefügt. Wenn Sie möchten, dass nur diese Segmente angezeigt werden, können Sie die Grundlinie „Alle Besuche“ entfernen.

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

   ![Die Touchpoints „Page:CamerRoll“ oder „Page: Camera“ sind hervorgehoben.](assets/fallout-or.png)

1. **Einzelne Touchpoints können nun auch auf das nächste Ereignis** (statt *am Ende*) im Pfad eingegrenzt werden. Unter jedem Touchpoint befinden sich die Auswahlmöglichkeiten **[!UICONTROL Endgültiger Pfad]** und **[!UICONTROL Nächstes Ereignis]**:

   ![Die Ansicht „Alle Besuche“ mit hervorgehobener Option „Endgültiger Pfad“. ](assets/fallout-nexthit.png)

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
| **[!UICONTROL Aufschlüsselung des Fallthroughs an diesem Touchpoint]** | Zeigt an, was Personen zwischen zwei Touchpoints (diesem und dem nächsten Touchpoint) getan haben, wenn sie sich zum nächsten Touchpoint fortbewegt haben. Diese Option erstellt eine Freiformtabelle, die Ihre Dimensionen enthält. Dimensionen und andere Elemente der Tabelle können Sie austauschen. |
| **[!UICONTROL Aufschlüsselung des Fallouts an diesem Touchpoint]** | Zeigt an, was Besuchende, die nicht im Trichter verblieben sind, unmittelbar nach dem ausgewählten Schritt getan haben. |
| **[!UICONTROL Erstellen von Segmenten aus Touchpoints]** | Erstellen Sie ein neues Segment aus dem ausgewählten Touchpoint. |

>[!MORELIKETHIS]
>
>[Hinzufügen einer Visualisierung in einem Bedienfeld](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[Visualisierungseinstellungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[Kontextmenü der Visualisierung](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

