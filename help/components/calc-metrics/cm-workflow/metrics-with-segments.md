---
description: Durch die Segmentierung einzelner Metriken können Sie Metriken innerhalb desselben Berichts vergleichen.
title: Segmentierte Metriken
feature: Calculated Metrics
exl-id: 37cc93df-9f51-42b3-918f-ed5864991621
source-git-commit: b3c7ceedec7b3f6a916e97bab38fd55f1d6c7f51
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 1%

---

# Segmentierte Metriken

Im [Generator für berechnete Metriken](cm-build-metrics.md#definition-builder) können Sie Segmente innerhalb Ihrer Metrikdefinition anwenden. Das Anwenden von Segmenten ist hilfreich, wenn Sie Metriken für eine Teilmenge Ihrer Daten in Ihrer Analyse verwenden möchten.

>[!NOTE]
>
>Segmentdefinitionen werden über den [Segment Builder](/help/components/segments/seg-builder.md) aktualisiert. Wenn Sie eine Änderung an einem Segment vornehmen, wird das Segment automatisch aktualisiert, wo immer es verwendet wird, auch wenn das Segment Teil einer Definition für berechnete Metriken ist.
>

Sie möchten Metriken für deutsche Personen, die mit Ihrer Marke interagieren, mit denen für Personen außerhalb Deutschlands vergleichen. Sie können also Fragen beantworten wie:

1. Wie viele Deutsche bzw. internationale Personen besuchen Ihre beliebtesten [Seiten](#popular-pages).
1. Wie viele Deutsche bzw. internationale Personen [total](#totals) haben in diesem Monat online mit Ihrer Marke interagiert.
1. Was sind [Prozent](#percentages) der Deutschen und internationalen Menschen, die Ihre beliebten Seiten besucht haben?

In den folgenden Abschnitten erfahren Sie, wie Sie mithilfe segmentierter Metriken diese Fragen beantworten können. Gegebenenfalls wird auf eine ausführlichere Dokumentation verwiesen.

## Beliebte Seiten

1. [Erstellen Sie eine berechnete ](cm-workflow.md) aus einem Workspace-Projekt namens `German people`.
1. Erstellen Sie im [Generator für berechnete ](cm-build-metrics.md) [ ein Segment](/help/components/segments/seg-builder.md) mit dem Titel &quot;`Germany`&quot;, d. h. mithilfe des Felds „CRM-Land“ aus Ihren CRM-Daten, um zu bestimmen, woher eine Person kommt.

   >[!TIP]
   >
   >Im Generator für berechnete Metriken können Sie ein Segment direkt mithilfe des Bedienfelds Komponenten erstellen.
   >   

   Ihr Segment könnte wie folgt aussehen.

   ![Segment Deutschland](assets/filter-germany.png)

1. Zurück im Generator für berechnete Metriken verwenden Sie das Segment , um die berechnete Metrik zu aktualisieren.

   ![Berechnete Metrik Deutschland](assets/calculated-metric-germany.png)

Wiederholen Sie die obigen Schritte für die internationale Version Ihrer berechneten Metrik.

1. Erstellen Sie aus Ihrem Workspace-Projekt eine berechnete Metrik mit dem Titel `International people`.
1. Erstellen Sie im Generator für berechnete Metriken ein Segment mit dem Titel &quot;`Not Germany`&quot;, das das Feld „CRM-Land“ aus Ihren CRM-Daten verwendet, um zu bestimmen, woher eine Person kommt.

   Ihr Segment sollte wie folgt aussehen.

   ![Segment Deutschland](assets/filter-not-germany.png)

1. Zurück im Generator für berechnete Metriken verwenden Sie das Segment , um die berechnete Metrik zu aktualisieren.

   ![Berechnete Metrik Deutschland](assets/calculated-metric-notgermany.png)


1. Erstellen Sie ein Projekt in Analysis Workspace, in dem Sie sich die von deutschen und internationalen Personen besuchten Seiten ansehen.

   ![Workspace-Freiformtabellen-Visualisierung, die deutsche und internationale Personen zeigt](assets/workspace-german-vs-international.png)


## Gesamt

1. Erstellen Sie zwei neue berechnete Metriken basierend auf der Gesamtsumme. Öffnen Sie jedes der zuvor erstellten Segmente, benennen Sie das Segment um, legen Sie **[!UICONTROL Metriktyp]** für **[!UICONTROL Personen]** auf **[!UICONTROL Gesamtsumme]** fest und verwenden Sie **[!UICONTROL Speichern unter]**, um das Segment unter dem neuen Namen zu speichern. Zum Beispiel:

   ![Gesamtmetrik für Deutschland](assets/calculated-metric-germany-total.png)

1. Fügen Sie Ihrem Workspace-Projekt eine neue Freiformtabellen-Visualisierung hinzu, die die Gesamtseiten für diesen Monat anzeigt.

   ![Workspace-Freiformtabellen-Visualisierung, die Deutsche im Vergleich zu internationalen Personen zeigt](assets/workspace-german-vs-international-totals.png)


## Prozentsatz

1. Erstellen Sie zwei neue berechnete Metriken, die einen Prozentsatz aus den zuvor erstellten berechneten Metriken berechnen.

   ![Workspace-Freiformtabellen-Visualisierung, die den prozentualen Anteil deutscher vs. internationaler Personen anzeigt](assets/calculated-metric-germany-total-percentage.png)


1. Aktualisieren Sie Ihr Workspace-Projekt.

   ![Workspace-Freiformtabellen-Visualisierung, die Deutsche im Vergleich zu internationalen Personen zeigt](assets/workspace-german-vs-international-totals-percentage.png)



>[!BEGINSHADEBOX]

Siehe ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Verwenden einer segmentierten berechneten Metrik als implementierungslose Metrik](https://video.tv.adobe.com/v/37931?quality=12&learn=on&captions=ger){target="_blank"} für ein Demovideo.

{{videoaa}}

>[!ENDSHADEBOX]

