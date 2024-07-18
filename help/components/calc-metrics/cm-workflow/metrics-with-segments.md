---
description: Durch Filterung einzelner Metriken können Sie Metrikvergleiche innerhalb desselben Berichts vornehmen.
title: Gefilterte Metriken
feature: Calculated Metrics
exl-id: 37cc93df-9f51-42b3-918f-ed5864991621
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 53%

---

# Gefilterte Metriken

Im Generator für berechnete Metriken können Sie Filter innerhalb Ihrer Metrikdefinition anwenden. Dies ist hilfreich, wenn Sie neue Metriken für Ihre Analyse ableiten möchten. Denken Sie daran, dass Filterdefinitionen über den Filter Builder aktualisiert werden können. Wenn Änderungen vorgenommen werden, wird der Filter automatisch überall dort aktualisiert, wo er angewendet wurde, auch wenn er Teil einer Definition für berechnete Metriken ist.

![Zusammenfassung und Definition von Filtern für Länder = Deutschland und Unique Visitors](assets/german-visitors.png)

## Erstellen einer gefilterten Metrik {#create}

Beispiel: Sie möchten verschiedene Aspekte des Filters „Deutsche Besucher“ mit denen des Filters „Internationale Besucher“ vergleichen. Dazu können Sie Metriken erstellen, die Einblick in Folgendes ermöglichen:

* Wie sieht das Browsingverhalten im Vergleich zwischen den beiden Gruppen aus? (Ein weiteres Beispiel wäre: Wie sieht die Konversionsrate im Vergleich zwischen den beiden Filtern aus?)
* Wie viele deutsche Personen durchsuchen bestimmte Seiten im Vergleich zu internationalen Personen in Prozent?
* Wo liegen die größten Unterschiede in Bezug darauf, welcher Inhalt von den verschiedenen Filtern aufgerufen wird?

Erstellen und speichern Sie eine Metrik namens &quot;Deutsche Besucher&quot;und eine Metrik namens &quot;Internationale Besucher&quot;:

1. Erstellen Sie im Generator für berechnete Metriken einen Ad-hoc-Filter namens &quot;Deutsche Besucher&quot;, bei dem &quot;Länder&quot;gleich &quot;Deutschland&quot;ist. Ziehen Sie die Dimension Länder in die Arbeitsfläche Definition und wählen Sie als Wert [!UICONTROL **Deutschland**] aus:

   ![Ad-hoc-Filter, der Länder gleich Deutschland anzeigt](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >Sie können dies auch im [Filtergenerator](/help/components/filters/create-filters.md) tun, aber wir haben den Workflow vereinfacht, indem Dimensionen im Generator für berechnete Metriken verfügbar gemacht werden. &quot;Ad Hoc&quot;bedeutet, dass der Filter in der Liste **[!UICONTROL Filter]** in der linken Leiste nicht sichtbar ist. Sie können es aber auch veröffentlichen, indem Sie über das „i“ daneben fahren und auf **[!UICONTROL Als öffentlich einstellen klicken]**.

1. Ziehen Sie den Filter Deutschland in die Arbeitsfläche Definition und ziehen Sie die Metrik Unique Visitors darin:

   ![Zusammenfassung und Definition von Ländern gleich Deutschland und Unique Visitors](assets/german-visitors.png)

1. Wählen Sie [!UICONTROL **Speichern**] aus, um die berechnete Metrik zu speichern.

1. Erstellen Sie im Generator für berechnete Metriken einen Ad-hoc-Filter namens &quot;internationale Besucher&quot;, bei dem &quot;Länder&quot;nicht mit &quot;Deutschland&quot;übereinstimmt.

   Ziehen Sie die Dimension &quot;Länder&quot;in die Arbeitsfläche &quot;Definition&quot;, wählen Sie [!UICONTROL **Deutschland**] als Wert aus und wählen Sie dann [!UICONTROL **nicht gleich**] als Operator.

1. Ziehen Sie die Metrik Unique Visitors hinzu.

1. Wählen Sie [!UICONTROL **Speichern**] aus, um die berechnete Metrik zu speichern.

1. Ziehen Sie in Analysis Workspace die Dimension **[!UICONTROL Seite]** in eine Freiform-Tabelle und dann die zwei neuen berechneten Metriken nebeneinander oben in die Tabelle:

   ![Freiformtabelle mit der Dimension &quot;Seite&quot;für deutsche und internationale Besucher](assets/workspace-pages.png)

Im Folgenden finden Sie eine Videoübersicht:

>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

## Prozent der Gesamtmetriken {#percent-total}

Sie können das obige Beispiel fortentwickeln, indem Sie Ihren Filter mit der Gesamtbevölkerung vergleichen. Erstellen Sie dazu zwei neue Metriken: „% aller deutschen Besucher“ und „% der Gesamtzahl internationaler Besucher“:

1. Ziehen Sie den Filter „Deutsche Besucher“ (oder „Internationale Besucher“) auf die Arbeitsfläche.
1. Legen Sie darunter einen weiteren Filter „Deutsche Besucher“ (oder „Internationale Besucher“) ab. Klicken Sie dieses Mal aber auf das zugehörige Konfigurationssymbol (Zahnrad), um den Metriktyp „Gesamt“ auszuwählen. Das Format sollte „Prozent“ lauten. Der Operator sollte „Geteilt durch“ lauten. Dadurch erhalten Sie die folgende Metrikdefinition:

   ![Länder gleich Deutschland und Gesamtanzahl Unique Visitors](assets/cm_metric_total.png)

1. Wenden Sie diese Metrik auf das Projekt an:

   ![Freiformtabelle mit Seite und % aller deutschen Besucher insgesamt](assets/cm_percent_total.png)
