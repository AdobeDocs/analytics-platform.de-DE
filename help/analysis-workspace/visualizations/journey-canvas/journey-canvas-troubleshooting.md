---
description: Erfahren Sie, wie Sie Probleme beim Konfigurieren einer Journey-Arbeitsflächen-Visualisierung beheben können.
title: Fehlerbehebung bei der Journey-Arbeitsfläche
feature: Visualizations
role: User
exl-id: f0ac3752-9244-4d9e-807b-e6471e6aa55b
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '1290'
ht-degree: 1%

---

# Fehlerbehebung für die Journey-Arbeitsfläche

Die Journey-Arbeitsflächen-Visualisierung ermöglicht es Ihnen, die Journey zu analysieren und detaillierte Einblicke zu erhalten, die Sie Ihren Benutzenden und Kunden bieten.

Weitere Informationen zur Journey-Arbeitsfläche finden Sie unter [Übersicht über die Journey-Arbeitsfläche](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) und [Konfigurieren einer Journey-Arbeitsfläche](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

Die folgenden Informationen helfen Ihnen bei der Fehlerbehebung bei unbeabsichtigten Ergebnissen, z. B. bei Knoten, die später im Journey erscheinen und einen höheren Prozentsatz oder eine höhere Anzahl aufweisen als Knoten, die früher im Journey enthalten sind.

## Knoten mit einem höheren Prozentsatz oder Wert als frühere Knoten

Auf der Journey-Arbeitsfläche ist es für Knoten, die später auf der Journey erscheinen, möglich, einen höheren Prozentsatz oder eine höhere Anzahl anzuzeigen als Knoten, die früher auf der Journey erscheinen.

Anders ausgedrückt: Im Gegensatz zu Fallout-Visualisierungen, die immer funnel-förmig sind (wobei die Beteiligung mit jedem Schritt abnimmt), können Journey-Arbeitsflächen-Visualisierungen eine höhere Beteiligung in späteren Journey-Schritten aufweisen als in vorherigen Schritten.

Dies kann in den folgenden Szenarien auftreten:

* Wenn Sie eine andere primäre Metrik als Personen oder Sitzungen verwenden

* Wenn mehrere Pfade zu einem einzelnen Knoten konvergieren

### Der Journey verwendet eine andere primäre Metrik als „Personen“ oder „Sitzung“

Da Sie auf der Journey-Arbeitsfläche jede beliebige Metrik als primäre Metrik verwenden können, kann dies dazu führen, dass Knoten, die erst später auf der Journey erscheinen, einen höheren Prozentsatz oder eine höhere Anzahl anzeigen als Knoten, die früher auf der Journey erscheinen.

![Journey mit Knoten mit einem höheren Prozentsatz als der vorherige Knoten](assets/journey-canvas-higher-percentage.png)

Die in den folgenden Szenarien verwendete Journey wird mit diesen Einstellungen konfiguriert:

* **[!UICONTROL Person]** wird als Container festgelegt

* **[!UICONTROL Ereignis]** wird als primäre Metrik festgelegt

#### Szenario 1: Benutzer A folgt in der ersten Sitzung dem Journey-Pfad. In einer nachfolgenden Sitzung verfügt der Benutzer über ein Ereignis, das nur einem späteren Knoten entspricht.

Angenommen, Benutzer A besucht die Site und schließt die Journey ab (Knoten 1: „Site besuchen“ > Knoten 2: „Produkt A anzeigen“ > Knoten 3: „Auschecken„). Da Benutzer A über ein Ereignis verfügt, das mit jedem Knoten der Journey übereinstimmt, wird auf jedem Knoten der Journey ein Ereignis gezählt.

Nehmen wir nun an, dass Benutzer A die Website in einer späteren Sitzung erneut besucht. Da Anwender A den Journey bereits in einer vorherigen Sitzung durch Befolgen des Journey-Pfads abgeschlossen hat, bedeutet dies, dass jedes Mal, wenn Anwender A ein Ereignis hat, das mit einem beliebigen Knoten auf der Journey übereinstimmt - auch wenn Anwender A den Pfad der Journey in der aktuellen Sitzung nicht befolgt hat - ein Ereignis auf dem entsprechenden Knoten auf der Journey gezählt wird. Wenn Benutzer A beispielsweise auscheckt, wird ein Ereignis auf dem Knoten „Auschecken“ gezählt. Dies kann dazu führen, dass der Prozentsatz und die Zahl am Knoten „Auschecken“ höher sind als am vorherigen Knoten „Produkt A anzeigen“.

In diesem Beispiel spielt die Journey-Container-Einstellung „Person“ eine entscheidende Rolle bei der Bestimmung, dass das Ereignis auf dem dritten Knoten („Check Out„) in der nachfolgenden Sitzung gezählt wird.

Wäre die Container-Einstellung alternativ auf „Sitzung“ festgelegt worden, würde das Ereignis, das nur auf dem dritten Knoten beim nachfolgenden Besuch stattgefunden hat, auf der Journey nicht gezählt werden, da die auf der Journey angezeigten Statistiken auf eine einzige definierte Sitzung für eine bestimmte Person beschränkt wären. Weitere Informationen zur Container-Einstellung finden Sie unter [Erstellen einer Journey-Arbeitsflächen](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#begin-building-a-journey-canvas-visualization) im Artikel [Konfigurieren einer Journey-Arbeitsflächen-Visualisierung](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

<!-- The time allotted for users to move along the path is determined by the container setting. Because "Person" is selected as the container setting in this example, people who followed the journey's path in one session (moving from Node 1 to Node 2 and to Node 3) met the criteria of the journey. On any subsequent visits to the site, any event they have that matches any node on the journey is counted on that node. -->

#### Szenario 2: Benutzer B fällt aus dem Journey

Angenommen, Benutzer B besucht die Site und schließt die Journey nicht ab (besucht die Site, zeigt Produkt B an und checkt dann aus). In diesem Fall wird ein Ereignis für den Startknoten des Journey-Knotens „Site besuchen“ gezählt, aber ein Ereignis wird nicht für die verbleibenden Knoten gezählt, und Benutzende B fällt aus dem Journey. Obwohl Benutzer B ausgecheckt hat, wird ein Ereignis auf dem dritten Knoten nicht gezählt („Auschecken„), da Benutzer B die Journey nicht abgeschlossen hat, indem er sich Produkt A vor dem Auschecken angesehen hat.

Dies liegt daran, dass Ereignisse für jeden Knoten nur dann gezählt werden, wenn Personen dem „möglichen Pfad“ der Journey folgen. Das bedeutet, dass Ereignisse nur gezählt werden, wenn die Person letztendlich von einem Knoten zum anderen wechselt, unabhängig von Ereignissen, die zwischen den beiden Knoten auftreten.

### Der Journey hat mehrere Pfade, die zu einem einzigen Knoten konvergieren

Journey Canvas ermöglicht es Ihnen, mehrere Startknoten auf einer Journey zu speichern, was zu mehreren Pfaden führt. Diese Pfade können zu einem gemeinsamen Knoten zusammenlaufen, was dazu führen kann, dass Knoten, die später im Journey kommen, einen höheren Prozentsatz oder eine höhere Anzahl aufweisen als Knoten, die früher im Journey kommen.

![Ein Journey mit mehreren Pfaden, die zu einem einzigen Knoten konvergieren](assets/journey-canvas-percentage-converge.png)

<!--

The journey used in the following scenarios is configured with the following settings:

* **[!UICONTROL Person]** is set as the container

* **[!UICONTROL Event]** is set as the primary metric

#### Scenario 

When a journey contains multiple paths that converge into a single node, the two paths are combined into the single node using the OR operator. This can result in the

-->

### Journey-Prozentsätze

Die auf den einzelnen Knoten einer Journey angezeigten Zahlen bleiben unabhängig von der Auswahl im Feld **[!UICONTROL Prozentwert]** konstant.

Die folgenden Abschnitte zeigen, wie sich die Prozentsätze für denselben Journey ändern können, je nachdem, welche der folgenden Optionen im Feld **[!UICONTROL Prozentwert]** ausgewählt ist:

+++Prozentsatz des Startknotens

Die Knoten in diesem Journey enthalten die folgenden Statistiken, wenn das Feld **[!UICONTROL Prozentwert]** auf „Prozent **[!UICONTROL Startknotens“]** ist:

![Journey mit Knoten mit einem höheren Prozentsatz als der vorherige Knoten](assets/journey-canvas-higher-percentage.png)

| Knoten | Statistiken |
|---------|----------|
| Knoten 1: „Site besuchen“ | Auf dieser Journey gab es 354.147 Ereignisse auf der Website innerhalb des Datumsbereichs für die Berichterstellung, wie auf dem Startknoten der Journey „Site besuchen“ dargestellt. |
| Knoten 2: „Produkt A anzeigen“ | Von der Gesamtzahl der im Startknoten angezeigten Ereignisse entsprachen 14 % (48.394) den Kriterien des zweiten Journey-Knotens „Produkt A anzeigen“. |
| Knoten 3 - „Auschecken“ | Von der Gesamtzahl der im Startknoten angezeigten Ereignisse entsprachen 32 % (113.782) den Kriterien des dritten Journey-Knotens „Checkout“. |

+++

+++Prozentsatz des vorherigen Knotens

Die Knoten in diesem Journey enthalten die folgenden Statistiken, wenn das Feld **[!UICONTROL Prozentwert]** auf **[!UICONTROL Prozent des vorherigen Knotens eingestellt ist]**:

![Journey mit Knoten mit einem höheren Prozentsatz als der vorherige Knoten](assets/journey-canvas-percentage-previous.png)

| Knoten | Statistiken |
|---------|----------|
| Knoten 1: „Site besuchen“ | Auf dieser Journey gab es 354.147 Ereignisse auf der Website innerhalb des Datumsbereichs für die Berichterstellung, wie auf dem Startknoten der Journey „Site besuchen“ dargestellt. |
| Knoten 2: „Produkt A anzeigen“ | Von der Gesamtzahl der im vorherigen Knoten angezeigten Ereignisse entsprachen 14 % (48.394) den Kriterien des zweiten Journey-Knotens „Produkt A anzeigen“. |
| Knoten 3 - „Auschecken“ | Von der Gesamtzahl der im vorherigen Knoten angezeigten Ereignisse entsprachen mehr als 100 % (113.782) den Kriterien des dritten Journey-Knotens „Auschecken“. |

+++

+++Gesamtprozentsatz

Die Knoten in dieser Journey enthalten die folgenden Statistiken, wenn das Feld **[!UICONTROL Prozentwert]** auf **[!UICONTROL Prozent der Gesamtheit]** gesetzt ist:

![Journey mit Knoten mit einem höheren Prozentsatz als der vorherige Knoten](assets/journey-canvas-percentage-total.png)

| Knoten | Statistiken |
|---------|----------|
| Knoten 1: „Site besuchen“ | Auf dieser Journey gab es 354.147 Ereignisse auf der Website innerhalb des Datumsbereichs für die Berichterstellung, wie auf dem Startknoten der Journey „Site besuchen“ dargestellt. |
| Knoten 2: „Produkt A anzeigen“ | Von der Gesamtzahl der Ereignisse entsprachen weniger als 1 % (48.394) den Kriterien des zweiten Journey-Knotens „Produkt A anzeigen“. |
| Knoten 3 - „Auschecken“ | Von der Gesamtzahl der Ereignisse entsprachen 1 % (113.782) den Kriterien des dritten Journey-Knotens „Check out“. |

+++

## Kompatibilität zwischen der Container-Metrik und der primären Metrik

Sie können den Journey-Arbeitsflächen-Container als „Person“ (der die Metrik „Personen“ verwendet) oder „Sitzung“ (die die Metrik „Sitzungen“ verwendet) konfigurieren.

Stellen Sie sicher, dass Sie eine primäre Metrik auswählen, die mit der aktuell ausgewählten Container-Metrik kompatibel ist. Die meisten Metriken sind mit den verfügbaren Container-Metriken kompatibel. Einige Kombinationen aus Container-Metriken und primären Metriken sollten jedoch vermieden werden.

Die Verwendung von Person als Container mit Sitzung als primäre Metrik kann beispielsweise zu unbeabsichtigten Ergebnissen führen.

<!--

## Percentages that exceed 100%

The following configurations can result in nodes that show percentages that exceed 100%:

* When the **[!UICONTROL Percentage value]** field is set to **[!UICONTROL Percent of total]** or **[!UICONTROL Percent of start node]**, and a primary metric is selected that results in less data for the start node than on subsequent nodes.

  For example, if Revenue is selected as the primary metric, and no revenue is being realized on the primary metric, then on any node where revenue is being realized will show as exceeding 100%. 

-->
