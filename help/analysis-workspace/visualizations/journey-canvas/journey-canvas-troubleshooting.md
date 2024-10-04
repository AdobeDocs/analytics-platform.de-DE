---
description: Beispiele beim Konfigurieren einer Journey-Arbeitsflächenvisualisierung
title: Beispiele für Journey-Arbeitsfläche
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: 82f8ba3fb04b50e352b76fd1ce866c0615971335
workflow-type: tm+mt
source-wordcount: '1248'
ht-degree: 0%

---

# Fehlerbehebung bei Journey Canvas

{{release-limited-testing}}

Mit der Journey-Arbeitsflächenvisualisierung können Sie tief greifende Einblicke in die Journey erhalten, die Sie Ihren Benutzern und Kunden zur Verfügung stellen.

Weitere Informationen zum Journey-Arbeitsbereich finden Sie unter [Journey-Arbeitsfläche - Übersicht](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) und [Journey-Arbeitsflächenvisualisierung konfigurieren](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

Die folgenden Informationen helfen Ihnen bei der Fehlerbehebung bei unbeabsichtigten Ergebnissen, die Ihnen möglicherweise angezeigt werden, z. B. Knoten, die später auf der Journey erscheinen und eine höhere Prozentzahl oder Anzahl aufweisen als Knoten, die früher auf der Journey erscheinen.

## Knoten mit einem höheren Prozentsatz oder Wert als vorherige Knoten

Es ist möglich, in der Journey-Arbeitsfläche für Knoten, die später auf der Journey kommen, eine höhere Prozentzahl oder Anzahl anzuzeigen als Knoten, die früher auf der Journey auftreten.

Anders ausgedrückt: Anders als bei Fallout-Visualisierungen, die immer trichter-förmig sind (wobei der Beitrag bei jedem Schritt reduziert wird), können Journey-Canvas-Visualisierungen in späteren Schritten des Journey eine höhere Beteiligung haben als in vorherigen Schritten.

Dies kann in den folgenden Szenarien eintreten:

* Bei Verwendung einer anderen primären Metrik als &quot;Personen oder Sitzungen&quot;

* Wenn mehrere Pfade in einen einzelnen Knoten konvertieren

### Die Journey verwendet eine andere primäre Metrik als Personen oder Sitzung

Da die Journey-Arbeitsfläche es Ihnen ermöglicht, eine beliebige Metrik als primäre Metrik zu verwenden, kann dies dazu führen, dass Knoten, die später im Journey erscheinen, eine höhere Prozentzahl oder eine höhere Anzahl von Knoten anzeigen als Knoten, die früher auf der Journey erscheinen.

![Journey mit Knoten mit einem höheren Prozentsatz als der vorherige Knoten](assets/journey-canvas-higher-percentage.png)

Die in den folgenden Szenarien verwendete Journey wird mit den folgenden Einstellungen konfiguriert:

* **[!UICONTROL Person]** wird als Container festgelegt

* **[!UICONTROL Ereignis]** wird als primäre Metrik festgelegt

#### Szenario 1: Benutzer A folgt dem Journey-Pfad in der ersten Sitzung, dann nur späteren Knoten in einer nachfolgenden Sitzung

Angenommen, Benutzer A besucht die Site und folgt dem Pfad der Journey (Knoten 1: Site besuchen > Knoten 2: Produkt A anzeigen > Knoten 3: Auschecken). In diesem Szenario wird ein Ereignis für jeden Knoten der Journey gezählt.

Nehmen wir nun an, dass Benutzer A die Site in einer späteren Sitzung erneut besucht. Da Benutzer A die Anforderungen des Journey bereits erfüllt hat, indem er in einer vorherigen Sitzung dem Journey-Pfad folgte, bedeutet dies, dass jedes Mal, wenn Benutzer A auscheckt - auch wenn Benutzer A den Pfad der Journey in der aktuellen Sitzung nicht gefolgt ist - ein Ereignis auf dem dritten Journey-Knoten &quot;Auschecken&quot;gezählt wird. Dies führt zu einem höheren Prozentsatz und einer höheren Zahl auf dem Knoten &quot;Checkout&quot;als auf dem vorherigen Knoten &quot;Produkt A anzeigen&quot;.

In diesem Beispiel spielt die Einstellung Journey-Container eine wichtige Rolle bei der Bestimmung, ob das Ereignis auf dem dritten Knoten (&quot;Checkout&quot;) in der nachfolgenden Sitzung gezählt wird.

Wenn &quot;Sitzung&quot;als Container (anstelle von &quot;Person&quot;) festgelegt worden wäre, hätte das Ereignis, das nur auf dem dritten Knoten des nachfolgenden Besuchs stattfand, nicht auf der Journey gezählt, da die auf der Journey angezeigten Statistiken auf eine einzelne definierte Sitzung für eine bestimmte Person beschränkt wären. Weitere Informationen zur Containereinstellung finden Sie unter [Erstellen einer Journey-Arbeitsflächenvisualisierung beginnen](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#begin-building-a-journey-canvas-visualization) im Artikel [Konfigurieren einer Visualisierung der Journey-Arbeitsfläche](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) .

<!-- The time allotted for users to move along the path is determined by the container setting. Because "Person" is selected as the container setting in this example, people who followed the journey's path in one session (moving from Node 1 to Node 2 and to Node 3) met the criteria of the journey. On any subsequent visits to the site, any event they have that matches any node on the journey is counted on that node. -->

#### Szenario 2 - Benutzer B fällt aus der Journey

Angenommen, Benutzer B besucht die Site und folgt nicht dem Pfad der Journey (besucht die Site, zeigt Produkt B an und checkt dann aus), ein Ereignis wird für den Journey Start-Knoten &quot;Besuchssite&quot;gezählt, aber ein Ereignis wird für die verbleibenden Knoten nicht gezählt und Benutzer B verlässt die Journey. Obwohl Benutzer B ausgecheckt ist, wird ein Ereignis nicht auf dem dritten Knoten &quot;Checkout&quot;gezählt, da Benutzer B nicht dem Pfad der Journey gefolgt ist, indem er Produkt A anzeigte.

Dies liegt daran, dass Ereignisse nur dann für jeden Knoten gezählt werden, wenn Benutzer dem Journey &quot;Endlicher Pfad&quot;folgen. Das bedeutet, dass Ereignisse gezählt werden, solange die Person schließlich von einem Knoten zum anderen wechselte, unabhängig von Ereignissen, die zwischen den beiden Knoten auftraten.

### Die Journey hat mehrere Pfade, die zu einem einzelnen Knoten konvertieren

Mit der Journey-Arbeitsfläche können Sie mehrere Startknoten in eine Journey einschließen, was zu mehreren Pfaden führt. Diese Pfade können in einen gemeinsamen Knoten konvertieren, was dazu führt, dass Knoten, die später im Journey auftreten, eine höhere Prozentzahl oder Anzahl aufweisen als Knoten, die früher auf der Journey erscheinen.

![Eine Journey mit mehreren Pfaden, die in einen einzelnen Knoten konvertieren](assets/journey-canvas-percentage-converge.png)

<!--

The journey used in the following scenarios is configured with the following settings:

* **[!UICONTROL Person]** is set as the container

* **[!UICONTROL Event]** is set as the primary metric

#### Scenario 

When a journey contains multiple paths that converge into a single node, the two paths are combined into the single node using the OR operator. This can result in the

-->

### Journey-Prozentsätze

Während die auf jedem Knoten einer Journey angezeigten Zahlen unabhängig davon, was im Feld **[!UICONTROL Prozentwert]** ausgewählt ist, konstant bleiben, können sich die Prozentsätze selbst ändern.

Die folgenden Abschnitte zeigen, wie sich die Prozentsätze für dieselbe Journey ändern können, je nachdem, welche der folgenden Optionen im Feld **[!UICONTROL Prozentwert]** ausgewählt ist:

+++Prozentsatz des Startknotens

Die Knoten in diesem Journey enthalten die folgenden Statistiken, wenn das Feld **[!UICONTROL Prozentwert]** auf **[!UICONTROL Prozent des Startknotens]** festgelegt ist:

![Journey mit Knoten mit einem höheren Prozentsatz als der vorherige Knoten](assets/journey-canvas-higher-percentage.png)

| Knoten | Statistik |
|---------|----------|
| 1. Knoten - &quot;Besuchsite&quot; | In dieser Journey gab es 354.147 Ereignisse auf der Site innerhalb des Datumsbereichs der Berichterstellung, wie im Journey-Startknoten &quot;Site besuchen&quot;dargestellt. |
| Knoten 2: &quot;Produkt A anzeigen&quot; | Von der Gesamtzahl der im Startknoten angezeigten Ereignisse entsprachen 14 % (48.394) der Ereignisse den Kriterien des zweiten Journey, &quot;Produkt A anzeigen&quot;. |
| 3. Schritt - &quot;Auschecken&quot; | Von der Gesamtzahl der im Startknoten angezeigten Ereignisse entsprachen 32 % (113.782) der Ereignisse den Kriterien des dritten Journey-Knotens, &quot;Checkout&quot;. |

+++

+++Prozentsatz des vorherigen Knotens

Die Knoten in diesem Journey enthalten die folgenden Statistiken, wenn das Feld **[!UICONTROL Prozentwert]** auf **[!UICONTROL Prozent des vorherigen Knotens]** festgelegt ist:

![Journey mit Knoten mit einem höheren Prozentsatz als der vorherige Knoten](assets/journey-canvas-percentage-previous.png)

| Knoten | Statistik |
|---------|----------|
| 1. Knoten - &quot;Besuchsite&quot; | In dieser Journey gab es 354.147 Ereignisse auf der Site innerhalb des Datumsbereichs der Berichterstellung, wie im Journey-Startknoten &quot;Site besuchen&quot;dargestellt. |
| Knoten 2: &quot;Produkt A anzeigen&quot; | Von der Gesamtzahl der im vorherigen Knoten angezeigten Ereignisse entsprachen 14 % (48.394) der Ereignisse den Kriterien des zweiten Journey, &quot;Produkt A anzeigen&quot;. |
| 3. Schritt - &quot;Auschecken&quot; | Von der Gesamtzahl der im vorherigen Knoten angezeigten Ereignisse entsprachen mehr als 100 % (113.782) der Ereignisse den Kriterien des dritten Journey-Knotens &quot;Checkout&quot;. |

+++

+++ % der Gesamtsumme

Die Knoten in diesem Journey enthalten die folgenden Statistiken, wenn das Feld **[!UICONTROL Prozentwert]** auf **[!UICONTROL Prozent des Gesamtwerts]** festgelegt ist:

![Journey mit Knoten mit einem höheren Prozentsatz als der vorherige Knoten](assets/journey-canvas-percentage-total.png)

| Knoten | Statistik |
|---------|----------|
| 1. Knoten - &quot;Besuchsite&quot; | In dieser Journey gab es 354.147 Ereignisse auf der Site innerhalb des Datumsbereichs der Berichterstellung, wie im Journey-Startknoten &quot;Site besuchen&quot;dargestellt. |
| Knoten 2: &quot;Produkt A anzeigen&quot; | Von der Gesamtzahl der Ereignisse entsprachen weniger als 1 % (48 394) den Kriterien des zweiten Journey-Knotens &quot;Produkt A anzeigen&quot;. |
| 3. Schritt - &quot;Auschecken&quot; | Von der Gesamtzahl der Ereignisse entsprachen 1% (113.782) den Kriterien des dritten Journey. &quot;Checkout&quot; |

+++

## Kompatibilität zwischen der Container-Metrik und der primären Metrik

Sie können den Journey-Arbeitsflächencontainer so konfigurieren, dass er &quot;Person&quot;(die die Metrik für Personen verwendet) oder &quot;Sitzung&quot;(die die Metrik für Sitzungen verwendet) lautet.

Stellen Sie sicher, dass Sie eine primäre Metrik auswählen, die mit der aktuell ausgewählten Container-Metrik kompatibel ist. Die meisten Metriken sind mit den verfügbaren Containermetriken kompatibel. Einige Kombinationen aus Containermetriken und primären Metriken sollten jedoch vermieden werden.

Beispielsweise kann die Verwendung von Person als Container mit Sitzung als primäre Metrik zu unbeabsichtigten Ergebnissen führen.

<!--

## Percentages that exceed 100%

The following configurations can result in nodes that show percentages that exceed 100%:

* When the **[!UICONTROL Percentage value]** field is set to **[!UICONTROL Percent of total]** or **[!UICONTROL Percent of start node]**, and a primary metric is selected that results in less data for the start node than on subsequent nodes.

  For example, if Revenue is selected as the primary metric, and no revenue is being realized on the primary metric, then on any node where revenue is being realized will show as exceeding 100%. 

-->
