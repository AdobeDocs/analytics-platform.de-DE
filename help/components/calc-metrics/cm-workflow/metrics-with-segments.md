---
description: Durch das Filtern einzelner Metriken können Sie Metriken innerhalb desselben Berichts vergleichen.
title: Gefilterte Metriken
feature: Calculated Metrics
exl-id: 37cc93df-9f51-42b3-918f-ed5864991621
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 1%

---

# Gefilterte Metriken

Im [Generator für berechnete Metriken](cm-build-metrics.md#definition-builder) können Sie Filter innerhalb Ihrer Metrikdefinition anwenden. Das Anwenden von Filtern ist hilfreich, wenn Sie Metriken für eine Teilmenge Ihrer Daten in Ihrer Analyse verwenden möchten.

>[!NOTE]
>
>Filterdefinitionen werden über den [Filter Builder](/help/components/filters/filter-builder.md) aktualisiert. Wenn Sie Änderungen an einem Filter vornehmen, wird der Filter automatisch überall dort aktualisiert, wo der Filter verwendet wird, auch wenn der Filter Teil einer Definition für berechnete Metriken ist.
>

Sie möchten Metriken für deutsche Personen, die mit Ihrer Marke interagieren, mit denen für Personen außerhalb Deutschlands vergleichen. Sie können also Fragen beantworten wie:

1. Wie viele Deutsche bzw. internationale Personen besuchen Ihre beliebtesten [Seiten](#popular-pages).
1. Wie viele Deutsche bzw. internationale Personen [total](#totals) haben in diesem Monat online mit Ihrer Marke interagiert.
1. Was sind [Prozent](#percentages) der Deutschen und internationalen Menschen, die Ihre beliebten Seiten besucht haben?

In den folgenden Abschnitten erfahren Sie, wie Sie mithilfe gefilterter Metriken diese Fragen beantworten können. Gegebenenfalls wird auf eine ausführlichere Dokumentation verwiesen.

## Beliebte Seiten

1. [Erstellen Sie eine berechnete ](cm-workflow.md) aus einem Workspace-Projekt namens `German people`.
1. Erstellen Sie im [Generator für berechnete ](cm-build-metrics.md)&quot; [Filter](/help/components/filters/filter-builder.md) mit dem Titel &quot;`Germany`&quot;, d. h. mithilfe des Felds „CRM-Land“ aus Ihren CRM-Daten, um zu bestimmen, woher eine Person kommt.

   >[!TIP]
   >
   >Im Generator für berechnete Metriken können Sie einen Filter direkt mithilfe des Bedienfelds Komponenten erstellen.
   >   

   Ihr Filter könnte wie folgt aussehen.

   ![Filter Deutschland](assets/filter-germany.png)

1. Zurück im Generator für berechnete Metriken verwenden Sie den Filter, um die berechnete Metrik zu aktualisieren.

   ![Berechnete Metrik Deutschland](assets/calculated-metric-germany.png)

Wiederholen Sie die obigen Schritte für die internationale Version Ihrer berechneten Metrik.

1. Erstellen Sie aus Ihrem Workspace-Projekt eine berechnete Metrik mit dem Titel `International people`.
1. Erstellen Sie im Generator für berechnete Metriken einen Filter mit dem Titel &quot;`Not Germany`&quot;, d. h. mithilfe des Felds „CRM-Land“ aus Ihren CRM-Daten, um zu bestimmen, woher eine Person kommt.

   Ihr Filter sollte wie folgt aussehen.

   ![Filter Deutschland](assets/filter-not-germany.png)

1. Zurück im Generator für berechnete Metriken verwenden Sie den Filter, um die berechnete Metrik zu aktualisieren.

   ![Berechnete Metrik Deutschland](assets/calculated-metric-notgermany.png)


1. Erstellen Sie ein Projekt in Analysis Workspace, in dem Sie sich die von deutschen und internationalen Personen besuchten Seiten ansehen.

   ![Workspace-Freiformtabellen-Visualisierung, die deutsche und internationale Personen zeigt](assets/workspace-german-vs-international.png)


## Gesamt

1. Erstellen Sie zwei neue Filter basierend auf der Gesamtsumme. Öffnen Sie jeden der zuvor erstellten Filter, benennen Sie den Filter um, legen Sie **[!UICONTROL Metriktyp]** für **[!UICONTROL Personen]** auf **[!UICONTROL Gesamtsumme]** fest und verwenden Sie **[!UICONTROL Speichern unter]**, um den Filter unter dem neuen Namen zu speichern. z. B.:

   ![Gesamtmetrik für Deutschland](assets/calculated-metric-germany-total.png)

1. Fügen Sie Ihrem Workspace-Projekt eine neue Freiformtabellen-Visualisierung hinzu, die die Gesamtseiten für diesen Monat anzeigt.

   ![Workspace-Freiformtabellen-Visualisierung, die Deutsche im Vergleich zu internationalen Personen zeigt](assets/workspace-german-vs-international-totals.png)


## Prozentsatz

1. Erstellen Sie zwei neue berechnete Metriken, die einen Prozentsatz aus den zuvor erstellten berechneten Metriken berechnen.

   ![Workspace-Freiformtabellen-Visualisierung, die den prozentualen Anteil deutscher vs. internationaler Personen anzeigt](assets/calculated-metric-germany-total-percentage.png)


1. Aktualisieren Sie Ihr Workspace-Projekt.

   ![Workspace-Freiformtabellen-Visualisierung, die Deutsche im Vergleich zu internationalen Personen zeigt](assets/workspace-german-vs-international-totals-percentage.png)



>[!BEGINSHADEBOX]

Siehe ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Verwenden einer gefilterten berechneten Metrik als implementierungslose Metrik](https://video.tv.adobe.com/v/25407?quality=12&learn=on){target="_blank"} für ein Demovideo.

{{videoaa}}

>[!ENDSHADEBOX]

