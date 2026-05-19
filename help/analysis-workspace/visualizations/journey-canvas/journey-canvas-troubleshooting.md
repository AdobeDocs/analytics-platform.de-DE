---
description: Erfahren Sie, wie Sie die Journey-Arbeitsflächen-Visualisierung in Analysis Workspace verwenden, um Benutzer-Journey, Fallout und Multi-Path-Konversionen zu analysieren.
title: Fehlerbehebung für die Journey-Arbeitsfläche
feature: Visualizations
role: User
exl-id: f0ac3752-9244-4d9e-807b-e6471e6aa55b
autotag-review: '2026-05-19T08:43:53.628Z'
TQID: 'https://experienceleague.adobe.com/E0LdSu06SM3c1ZBnOcIz352mqIkTN7dXfH9qC1BM-4g'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 1303
ht-degree: 93%

---

# Fehlerbehebung für die Journey-Arbeitsfläche

Die Journey-Arbeitsflächenvisualisierung hilft Ihnen, die Journey zu analysieren und tiefgreifende Erkenntnisse zu gewinnen, die Sie Ihren Benutzenden sowie Kundinnen und Kunden bereitstellen können.

Weitere Informationen zur Journey-Arbeitsfläche finden Sie unter [Journey-Arbeitsfläche – Überblick](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) und unter [Konfigurieren einer Journey-Arbeitsflächenvisualisierung](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

Die folgenden Informationen helfen Ihnen bei der Fehlerbehebung bei unbeabsichtigten Ergebnissen, z. B. bei Knoten, die später in der Journey auftreten und einen höheren Prozentsatz oder eine höhere Anzahl aufweisen als Knoten, die früher in der Journey auftreten sind.

## Knoten mit einem höheren Prozentsatz oder Wert als frühere Knoten

In der Journey-Arbeitsfläche ist es möglich, dass Knoten, die später in der Journey auftreten, einen höheren Prozentsatz oder eine höhere Anzahl aufweisen als Knoten, die früher in der Journey auftreten.

Anders ausgedrückt: Im Gegensatz zu Fallout-Visualisierungen, die immer trichterförmig sind (wobei der Beitrag mit jedem Schritt abnimmt), können Journey-Arbeitsflächenvisualisierungen in späteren Journey-Schritten einen höheren Beitrag aufweisen als in vorherigen Schritten.

Dies kann in den folgenden Szenarien auftreten:

* Wenn Sie eine andere primäre Metrik als „Personen“ oder „Sitzungen“ verwenden

* Wenn mehrere Pfade zu einem einzelnen Knoten konvergieren

### Der Journey verwendet eine andere primäre Metrik als „Personen“ oder „Sitzungen“

Da Sie in der Journey-Arbeitsfläche jede beliebige Metrik als primäre Metrik verwenden können, kann dies dazu führen, dass Knoten, die erst später in der Journey auftreten, einen höheren Prozentsatz oder eine höhere Anzahl aufweisen als Knoten, die früher in der Journey auftreten.

![Journey mit Knoten mit einem höheren Prozentsatz als der vorherige Knoten](assets/journey-canvas-higher-percentage.png)

Die in den folgenden Szenarien verwendete Journey wird mit diesen Einstellungen konfiguriert:

* **[!UICONTROL Person]** wird als Container festgelegt

* **[!UICONTROL Ereignis]** wird als primäre Metrik festgelegt

#### Szenario 1: Person A folgt in der ersten Sitzung dem Journey-Pfad. In einer nachfolgenden Sitzung verfügt die Person über ein Ereignis, das erst einem späteren Knoten entspricht.

Angenommen, Person A besucht die Website und schließt die Journey ab (Knoten 1: „Website besuchen“ > Knoten 2: „Produkt A anzeigen“ > Knoten 3: „Checkout“). Da Person A über ein Ereignis verfügt, das mit jedem Knoten der Journey übereinstimmt, wird auf jedem Knoten der Journey ein Ereignis gezählt.

Nehmen wir nun an, dass Person A die Website in einer späteren Sitzung erneut besucht. Da Person A dem Journey-Pfad bereits in einer vorherigen Sitzung gefolgt ist und die Journey abgeschlossen hat, bedeutet dies, dass jedes Mal, wenn Person A ein Ereignis hat, das mit einem beliebigen Knoten auf der Journey übereinstimmt – auch wenn Person A dem Pfad der Journey in der aktuellen Sitzung nicht gefolgt ist – ein Ereignis auf dem entsprechenden Knoten in der Journey gezählt wird. Wenn Person A beispielsweise auscheckt, wird ein Ereignis auf dem Knoten „Checkout“ gezählt. Dies kann dazu führen, dass der Prozentsatz und die Zahl am Knoten „Checkout“ höher sind als am vorherigen Knoten „Produkt A anzeigen“.

In diesem Beispiel spielt die Journey-Container-Einstellung „Person“ eine entscheidende Rolle bei der Bestimmung, dass das Ereignis auf dem dritten Knoten („Checkout“) in der nachfolgenden Sitzung gezählt wird.

Wäre die Container-Einstellung alternativ auf „Sitzung“ festgelegt worden, würde das Ereignis, das nur auf dem dritten Knoten beim nachfolgenden Besuch stattgefunden hat, in der Journey nicht gezählt werden, da die in der Journey angezeigten Statistiken auf eine einzige definierte Sitzung für eine bestimmte Person beschränkt wären. Weitere Informationen zur Container-Einstellung finden Sie unter [Erstellen einer Journey-Arbeitsflächen](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#begin-building-a-journey-canvas-visualization) im Artikel [Konfigurieren einer Journey-Arbeitsflächen-Visualisierung](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

<!-- The time allotted for users to move along the path is determined by the container setting. Because "Person" is selected as the container setting in this example, people who followed the journey's path in one session (moving from Node 1 to Node 2 and to Node 3) met the criteria of the journey. On any subsequent visits to the site, any event they have that matches any node on the journey is counted on that node. -->

#### Szenario 2: Person B fällt aus der Journey

Angenommen, Person B besucht die Website und schließt die Journey nicht ab (besucht die Website, zeigt Produkt B an und checkt dann aus). In diesem Fall wird ein Ereignis für den Journey-Startknoten „Website besuchen“ gezählt, aber für die verbleibenden Knoten wird kein Ereignis gezählt und Person B fällt aus der Journey. Obwohl Person B ausgecheckt hat, wird kein Ereignis auf dem dritten Knoten („Checkout“) gezählt, da Person B die Journey nicht abgeschlossen hat, indem er sich Produkt A vor dem Auschecken angesehen hat.

Dies liegt daran, dass Ereignisse für jeden Knoten nur dann gezählt werden, wenn Personen dem „endgültigen Pfad“ der Journey folgen. Das bedeutet, dass Ereignisse nur gezählt werden, wenn die Person letztendlich von einem Knoten zum anderen wechselt, unabhängig von Ereignissen, die zwischen den beiden Knoten auftreten.

### Die Journey hat mehrere Pfade, die zu einem einzigen Knoten konvergieren

Die Journey-Arbeitsfläche ermöglicht es Ihnen, mehrere Startknoten in einer Journey zu speichern, was zu mehreren Pfaden führt. Diese Pfade können zu einem gemeinsamen Knoten zusammenlaufen, was dazu führen kann, dass Knoten, die später in der Journey auftreten, einen höheren Prozentsatz oder eine höhere Anzahl aufweisen als Knoten, die früher in der Journey auftreten.

![Eine Journey mit mehreren Pfaden, die zu einem einzigen Knoten konvergieren](assets/journey-canvas-percentage-converge.png)

<!--

The journey used in the following scenarios is configured with the following settings:

* **[!UICONTROL Person]** is set as the container

* **[!UICONTROL Event]** is set as the primary metric

#### Scenario 

When a journey contains multiple paths that converge into a single node, the two paths are combined into the single node using the OR operator. This can result in the

-->

### Journey-Prozentsätze

Die auf den einzelnen Knoten einer Journey angezeigten Zahlen bleiben unabhängig von der Auswahl im Feld **[!UICONTROL Prozentwert]** konstant.

Die folgenden Abschnitte zeigen, wie sich die Prozentsätze für dieselbe Journey ändern können, je nachdem, welche der folgenden Optionen im Feld **[!UICONTROL Prozentwert]** ausgewählt ist:

+++Prozentsatz des Startknotens

Die Knoten in dieser Journey enthalten die folgenden Statistiken, wenn das Feld **[!UICONTROL Prozentwert]** auf **[!UICONTROL Prozentsatz des Startknotens]** festgelegt ist:

![Journey mit Knoten mit einem höheren Prozentsatz als der vorherige Knoten](assets/journey-canvas-higher-percentage.png)

| Knoten | Statistiken |
|---------|----------|
| Knoten 1: „Website besuchen“ | In dieser Journey gab es 354.147 Ereignisse auf der Website innerhalb des Datumsbereichs für die Berichterstellung, wie auf dem Startknoten der Journey „Website besuchen“ dargestellt. |
| Knoten 2: „Produkt A anzeigen“ | Von der Gesamtzahl der im Startknoten angezeigten Ereignisse entsprachen 14 % (48.394) den Kriterien des zweiten Journey-Knotens „Produkt A anzeigen“. |
| Knoten 3 - „Checkout“ | Von der Gesamtzahl der im Startknoten angezeigten Ereignisse entsprachen 32 % (113.782) den Kriterien des dritten Journey-Knotens „Checkout“. |

+++

+++Prozentsatz des vorherigen Knotens

Die Knoten in dieser Journey enthalten die folgenden Statistiken, wenn das Feld **[!UICONTROL Prozentwert]** auf **[!UICONTROL Prozentsatz des vorherigen Knotens]** festgelegt ist:

![Journey mit Knoten mit einem höheren Prozentsatz als der vorherige Knoten](assets/journey-canvas-percentage-previous.png)

| Knoten | Statistiken |
|---------|----------|
| Knoten 1: „Website besuchen“ | In dieser Journey gab es 354.147 Ereignisse auf der Website innerhalb des Datumsbereichs für die Berichterstellung, wie auf dem Startknoten der Journey „Website besuchen“ dargestellt. |
| Knoten 2: „Produkt A anzeigen“ | Von der Gesamtzahl der im vorherigen Knoten angezeigten Ereignisse entsprachen 14 % (48.394) den Kriterien des zweiten Journey-Knotens „Produkt A anzeigen“. |
| Knoten 3 - „Checkout“ | Von der Gesamtzahl der im vorherigen Knoten angezeigten Ereignisse entsprachen mehr als 100 % (113.782) den Kriterien des dritten Journey-Knotens „Checkout“. |

+++

+++Gesamtprozentsatz

Die Knoten in dieser Journey enthalten die folgenden Statistiken, wenn das Feld **[!UICONTROL Prozentwert]** auf **[!UICONTROL Gesamtprozentsatz]** festgelegt ist:

![Journey mit Knoten mit einem höheren Prozentsatz als der vorherige Knoten](assets/journey-canvas-percentage-total.png)

| Knoten | Statistiken |
|---------|----------|
| Knoten 1: „Website besuchen“ | In dieser Journey gab es 354.147 Ereignisse auf der Website innerhalb des Datumsbereichs für die Berichterstellung, wie auf dem Startknoten der Journey „Website besuchen“ dargestellt. |
| Knoten 2: „Produkt A anzeigen“ | Von der Gesamtzahl der Ereignisse entsprachen weniger als 1 % (48.394) den Kriterien des zweiten Journey-Knotens „Produkt A anzeigen“. |
| Knoten 3 - „Checkout“ | Von der Gesamtzahl der Ereignisse entsprachen 1 % (113.782) den Kriterien des dritten Journey-Knotens „Checkout“. |

+++

## Kompatibilität zwischen der Container-Metrik und der primären Metrik

Sie können den Journey-Arbeitsflächen-Container als „Person“ (verwendet die Metrik „Personen“) oder „Sitzung“ (verwendet die Metrik „Sitzungen“) konfigurieren.

Stellen Sie sicher, dass Sie eine primäre Metrik auswählen, die mit der aktuell ausgewählten Container-Metrik kompatibel ist. Die meisten Metriken sind mit den verfügbaren Container-Metriken kompatibel. Einige Kombinationen aus Container-Metriken und primären Metriken sollten jedoch vermieden werden.

Die Verwendung von „Person“ als Container mit „Sitzung“ als primäre Metrik kann beispielsweise zu unbeabsichtigten Ergebnissen führen.

<!--

## Percentages that exceed 100%

The following configurations can result in nodes that show percentages that exceed 100%:

* When the **[!UICONTROL Percentage value]** field is set to **[!UICONTROL Percent of total]** or **[!UICONTROL Percent of start node]**, and a primary metric is selected that results in less data for the start node than on subsequent nodes.

  For example, if Revenue is selected as the primary metric, and no revenue is being realized on the primary metric, then on any node where revenue is being realized will show as exceeding 100%. 

-->
