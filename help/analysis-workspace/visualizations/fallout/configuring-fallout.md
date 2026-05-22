---
description: Erfahren Sie, wie Sie die Touchpoints konfigurieren und angeben, um eine mehrdimensionale Fallout-Sequenz zu erstellen.
title: Fallout-Visualisierung konfigurieren
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
role: User
TQID: https://experienceleague.adobe.com/Oyt-8i7vBYjTxBk4mX3dN3GeohZvzH0dh10kBS6UBx4
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: bc7a5a86-1a70-451f-985c-037b65f091d1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 921
ht-degree: 40%

---

# Fallout-Visualisierung konfigurieren {#configure-fallout-visualization}


Sie können **Touchpoints** angeben, um eine mehrdimensionale Fallout-Sequenz zu erstellen. In vielen Fällen ist ein Touchpoint eine Seite Ihrer Website. Touchpoints sind jedoch nicht auf Seiten beschränkt. So können Sie zum Beispiel Ereignisse (wie Einheiten) sowie eindeutige Personen und erneute Besuche hinzufügen. Sie können auch Dimensionen hinzufügen, z. B. eine Kategorie, einen Browser-Typ oder einen internen Suchbegriff.

Sie können sogar Segmente innerhalb eines Touchpoints hinzufügen. Vielleicht möchten Sie zum Beispiel Segmente vergleichen, z. B. Benutzer von iOS und Android. Wenn Sie die gewünschten Segmente an die Oberseite des Trichters ziehen, werden Informationen über diese Segmente zum Fallout-Bericht hinzugefügt. Wenn Sie nur diese Segmente anzeigen möchten, können Sie die Baseline „Alle Personen“ entfernen.

Fallout-Visualisierungen haben keine Beschränkung hinsichtlich der Anzahl der Touchpoints, die Sie hinzufügen können, oder der Anzahl der Komponenten, die Sie verwenden können.

Sie können Pfade für Dimensionen, Metriken und Segmente erstellen. Nehmen wir zum Beispiel an, dass jemand `shoes, shirt` auf einer Seite betrachtet, und auf der nächsten Seite `shirt, socks`. Der nächste Produktflussbericht von Schuhe wird „Shirt und Socken“ lauten, NICHT „Shirt“.

## Verwenden

1. Fügen Sie eine Visualisierung des Typs ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL Fallout]** hinzu. Weitere Informationen finden Sie unter [Hinzufügen einer Visualisierung in einem Bedienfeld](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Ziehen Sie eine Komponente in das **[!UICONTROL Touchpoint hinzufügen]** Dropdown-Menü.

   >[!TIP]
   >
   >Sie können dem Fallout-Bericht eine einzelne Seite statt der gesamten Dimension hinzufügen. Klicken Sie auf den Pfeil nach rechts ![ChevronRight](/help/assets/icons/ChevronRight.svg) auf der Seitendimension, um eine bestimmte Seite auszuwählen, z. B **[!UICONTROL &quot;]**&quot;, die dem Fallout-Bericht hinzugefügt werden soll.

   ![Die Startseite aus der Dimension „Seite“, die in das Feld „Touchpoint hinzufügen“ gezogen wurde.](assets/fallout-drag.png)

1. Fügen Sie weitere Touchpoints hinzu, bis Ihre Sequenz vollständig ist.

   Die umkreisten Zahlen im grauen Abschnitt der Leiste zeigen den Fallout zwischen Touchpoints an (nicht den gesamten Fallout bis zu diesem Punkt). Die eingekreisten Zahlen im grünen Bereich des Balkens zeigen den erfolgreichen Durchfall vom vorherigen Touchpoint zum aktuellen Touchpoint.

   ![Fallout-Visualisierung](assets/fallout-visualization.png)

   Beim Hinzufügen von Touchpoints haben Sie folgende Möglichkeiten:

   * Kombinieren Sie mehrere Komponenten, indem Sie eine oder mehrere zusätzliche Komponenten auf einen einzelnen Touchpoint ziehen.

     >[!NOTE]
     >
     >Hinweis: Mehrere Segmente werden mit AND verbunden, mehrere Elemente wie Dimensionselemente und Metriken hingegen mit OR.

   * Ordnen Sie Touchpoints neu an, indem Sie sie in der Fallout-Hierarchie auf eine andere Ebene ziehen.

   * Kombinieren Sie zwei Touchpoints, indem Sie einen Touchpoint auf einen anderen ziehen. Touchpoint ablegen, wenn das Wort &quot;**[!UICONTROL &quot;]**.

   * Einschränken einzelner Touchpoints auf das nächste Ereignis (im Gegensatz zu *letztendlich*) im Pfad. Unter jedem Touchpoint gibt es einen Selektor mit den Optionen **[!UICONTROL Eventueller Pfad]** und **[!UICONTROL Nächstes Ereignis]**, wie hier gezeigt:

     | Option | Beschreibung |
     |---|---|
     | **[!UICONTROL Endgültiger Pfad]** (Standard) | Es werden die Besuchenden gezählt, die *am Ende* auf der nächsten Seite im Pfad, aber nicht notwendigerweise beim nächsten Ereignis landen. |
     | **[!UICONTROL Nächstes Ereignis]** | Personen werden gezählt, die beim nächsten Ereignis auf der nächsten Seite im Pfad landen. |

   * Bewegen Sie den Mauszeiger über einen Touchpoint, um den Fallout und andere Informationen zu dieser Ebene anzuzeigen. Zu den Informationen gehören der Name des Touchpoints, die Anzahl der Personen und die Erfolgsrate. Sie können die Erfolgsrate auch mit anderen Touchpoints vergleichen.

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

### Zugriff auf das Kontextmenü

Sie können auf eine der folgenden Arten auf das Kontextmenü zugreifen:

* Bewegen Sie den Mauszeiger über einen Touchpoint in der Visualisierung und wählen Sie dann **[!UICONTROL Zum Analysieren klicken]** aus.

  ![Zugriff auf das Kontextmenü über den Mauszeiger](assets/fallout-tooltip-analyze.png)

* Klicken Sie mit der rechten Maustaste auf einen Touchpoint in der Visualisierung.

  ![Fallout-Optionen](assets/fallout-options.png)

### Optionen des Kontextmenüs

Die folgenden Optionen des Kontextmenüs sind verfügbar:

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
>[Hinzufügen einer Visualisierung zu einem Bedienfeld](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Einstellungen der Visualisierung](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Kontextmenü der Visualisierung](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

