---
description: Durch Filterung einzelner Metriken können Sie Metrikvergleiche innerhalb desselben Berichts vornehmen.
title: Gefilterte Metriken
feature: Calculated Metrics
exl-id: 37cc93df-9f51-42b3-918f-ed5864991621
source-git-commit: 65eafd65358d9370b452338ce1036e59b3c69d1a
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 1%

---

# Gefilterte Metriken

Im [Generator für berechnete Metriken](cm-build-metrics.md#definition-builder) können Sie Filter innerhalb Ihrer Metrikdefinition anwenden. Das Anwenden von Filtern ist hilfreich, wenn Sie Metriken für eine Untergruppe Ihrer Daten in Ihrer Analyse verwenden möchten.

>[!NOTE]
>
>Filterdefinitionen werden über den [Filter-Builder](/help/components/filters/filter-builder.md) aktualisiert. Wenn Sie an einem Filter Änderungen vornehmen, wird der Filter automatisch überall dort aktualisiert, wo der Filter verwendet wird, auch wenn der Filter Teil einer Definition für berechnete Metriken ist.
>

Sie möchten Metriken für deutsche Personen vergleichen, die mit Ihrer Marke interagieren, und für Personen außerhalb Deutschlands. So können Sie Fragen beantworten wie:

1. Wie viele Deutsche und internationale Besucher Ihre beliebtesten [Seiten](#popular-pages) besuchen.
1. Wie viele deutsche und internationale Personen insgesamt [insgesamt](#totals) haben in diesem Monat mit Ihrer Marke online interagiert.
1. Wie hoch sind die [Prozentsätze](#percentages) der Deutschen und internationalen Menschen, die Ihre beliebten Seiten besucht haben?

In den folgenden Abschnitten erfahren Sie, wie Ihnen gefilterte Metriken bei der Beantwortung dieser Fragen helfen können. Gegebenenfalls wird auf ausführlichere Unterlagen verwiesen.

## Beliebte Seiten

1. [Erstellen Sie eine berechnete Metrik](cm-workflow.md) aus einem Workspace-Projekt mit dem Namen `German people`.
1. Erstellen Sie im [Generator für berechnete Metriken](cm-build-metrics.md) [einen Filter mit dem Namen ](/help/components/filters/filter-builder.md) mit dem Namen `Germany`, der das Feld CRM-Land aus Ihren CRM-Daten verwendet, um zu ermitteln, woher eine Person stammt.

   >[!TIP]
   >
   >Im Generator für berechnete Metriken können Sie direkt über den Bereich Komponenten einen Filter erstellen.
   >   

   Ihr Filter könnte so aussehen.

   ![Deutschland filtern](assets/filter-germany.png)

1. Verwenden Sie im Generator für berechnete Metriken den Filter, um die berechnete Metrik zu aktualisieren.

   ![Berechnete Metrik Deutschland](assets/calculated-metric-germany.png)

Wiederholen Sie die obigen Schritte für die internationale Version Ihrer berechneten Metrik.

1. Erstellen Sie eine berechnete Metrik aus Ihrem Workspace-Projekt mit dem Titel `International people`.
1. Erstellen Sie im Generator für berechnete Metriken einen Filter mit der Bezeichnung `Not Germany`, der das Feld CRM-Land aus Ihren CRM-Daten verwendet, um zu bestimmen, woher eine Person stammt.

   Ihr Filter sollte so aussehen.

   ![Deutschland filtern](assets/filter-not-germany.png)

1. Verwenden Sie im Generator für berechnete Metriken den Filter, um die berechnete Metrik zu aktualisieren.

   ![Berechnete Metrik Deutschland](assets/calculated-metric-notgermany.png)


1. Erstellen Sie ein Projekt in Analysis Workspace, in dem Sie sich die Seiten ansehen, die von deutschen und internationalen Besuchern besucht werden.

   ![Visualisierung der Workspace-Freiformtabelle mit deutschsprachigen und internationalen Personen](assets/workspace-german-vs-international.png)


## Gesamt

1. Erstellen Sie zwei neue Filter basierend auf der Gesamtsumme. Öffnen Sie jeden zuvor erstellten Filter, benennen Sie den Filter um, setzen Sie den Metriktyp **[!UICONTROL für**[!UICONTROL  Personen ]**auf**[!UICONTROL  Gesamtsumme ]**und verwenden Sie**[!UICONTROL  Speichern unter ]**, um den Filter unter dem neuen Namen zu speichern.]** Zum Beispiel:

   ![Gesamtmetrik für Deutschland](assets/calculated-metric-germany-total.png)

1. Fügen Sie Ihrem Workspace-Projekt eine neue Freiformtabellen-Visualisierung hinzu, die die Gesamtseiten für diesen Monat anzeigt.

   ![Visualisierung der Workspace-Freiformtabelle mit deutscher und internationaler Gesamtzahl](assets/workspace-german-vs-international-totals.png)


## Prozentsatz

1. Erstellen Sie zwei neue berechnete Metriken, die einen Prozentsatz aus den zuvor erstellten berechneten Metriken berechnen.

   ![Visualisierung der Workspace-Freiformtabelle mit deutschem und internationalem Gesamt-Personenprozentsatz](assets/calculated-metric-germany-total-percentage.png)


1. Aktualisieren Sie Ihr Workspace-Projekt.

   ![Visualisierung der Workspace-Freiformtabelle mit deutscher und internationaler Gesamtzahl](assets/workspace-german-vs-international-totals-percentage.png)


+++ In diesem Video wird gezeigt, wie eine gefilterte berechnete Metrik als implementierungslose Metrik verwendet wird.

>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

{{videoaa}}

+++
