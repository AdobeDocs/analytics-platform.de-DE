---
description: Beispiele beim Konfigurieren einer Journey-Arbeitsflächenvisualisierung
title: Beispiele für Journey-Arbeitsfläche
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: c79d1174d78c0bfb1c9b082eb93855bdab4283e4
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 1%

---

# Fehlerbehebung bei Journey Canvas

{{release-limited-testing}}

Mit der Journey-Arbeitsflächenvisualisierung können Sie tief greifende Einblicke in die Journey erhalten, die Sie Ihren Benutzern und Kunden zur Verfügung stellen.

Weitere Informationen zum Journey-Arbeitsbereich finden Sie unter [Journey-Arbeitsfläche - Übersicht](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) und [Journey-Arbeitsflächenvisualisierung konfigurieren](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).


## Kompatibilität zwischen der Container-Metrik und der primären Metrik

Sie können den Journey-Arbeitsflächencontainer so konfigurieren, dass er &quot;Person&quot;(die die Metrik für Personen verwendet) oder &quot;Sitzung&quot;(die die Metrik für Sitzungen verwendet) lautet.

Stellen Sie bei der Auswahl einer primären oder sekundären Metrik sicher, dass Sie eine Metrik auswählen, die mit der aktuell ausgewählten Behältermetrik kompatibel ist. Die meisten Metriken sind mit den verfügbaren Containermetriken kompatibel. Einige Kombinationen aus Containermetriken und primären oder sekundären Metriken sollten jedoch vermieden werden.

Wenn Sie beispielsweise Person als Container mit Sitzung als primäre oder sekundäre Metrik verwenden


| Container | Primäre oder sekundäre Metrik | Resultat |
|---------|----------|---------|
| Personen | Sitzung | Diese Kombination kann zu unbeabsichtigten Ergebnissen führen. Insbesondere kann das Ergebnis dieser Kombination |
| A2 | B2 | C2 |
| A3 | B3 | C3 |


## Prozentsätze über 100 %

Die folgenden Konfigurationen können zu Knoten führen, die Prozentsätze anzeigen, die 100 % überschreiten:

* Wenn das Feld **[!UICONTROL Prozentwert]** auf **[!UICONTROL Prozent des Gesamtwerts]** oder **[!UICONTROL Prozent des Startknotens]** gesetzt ist und eine primäre Metrik ausgewählt wird, die zu weniger Daten für den Startknoten als für die nachfolgenden Knoten führt.

  Wenn beispielsweise &quot;Umsatz&quot;als primäre Metrik ausgewählt ist und kein Umsatz für die primäre Metrik realisiert wird, wird für jeden Knoten, in dem der Umsatz realisiert wird, ein Umsatz von mehr als 100 % angezeigt.

## Knoten mit einem höheren Prozentsatz oder Wert als vorherige Knoten

## Knoten mit einem höheren Prozentsatz oder Wert als vorherige Knoten

## Knoten, die später im Journey auftreten, weisen einen höheren Prozentsatz oder Wert auf als die, die früher eingehen

## Ein Knoten mit einem höheren Prozentsatz oder Wert als Knoten, die ihm in der Journey vorangehen

## Knoten mit einem höheren Prozentsatz oder Wert als vorherige Knoten

## Knoten

## Ein höherer Prozentsatz oder Wert in nachfolgenden Knoten

## Eine Journey, die nicht trichter-förmig ist

Es ist möglich, in der Journey-Arbeitsfläche für Knoten, die später auf der Journey kommen, eine höhere Prozentzahl oder Anzahl anzuzeigen als Knoten, die früher auf der Journey auftreten.

Anders ausgedrückt: Anders als bei Fallout-Visualisierungen, die immer trichter-förmig sind (wobei der Beitrag bei jedem Schritt reduziert wird), können Journey-Canvas-Visualisierungen eine höhere Beteiligung an späteren Schritten des Journey haben.

Betrachten Sie eine Journey mit den folgenden Eigenschaften:

* Die Journey enthält 3 Knoten: Knoten A > Knoten B > Knoten C

* Das Feld **[!UICONTROL Prozentwert]** wird auf **[!UICONTROL Prozent des Gesamtwerts]** gesetzt

* **[!UICONTROL Person]** wird als Container festgelegt

* **[!UICONTROL Ereignis]** wird als primäre Metrik festgelegt

Angenommen, ein Besucher hat Knoten A, Knoten B und dann Knoten C besucht. Jeder dieser Besuche zählt für jeden Knoten als Einzelereignis, da er in der von der Journey definierten Reihenfolge besucht wurde.

Bei einem nachfolgenden Besuch der Site besucht der Besucher nur Knoten C, was zu einem zusätzlichen Ereignis in Knoten C führt.

In diesem Fall zeigen Knoten A und B jeweils 1 Ereignis und 100 %, während Knoten C 2 Ereignisse und 200 % anzeigt.

Wenn &quot;Sitzung&quot;als Container festgelegt wurde, zeigen die Knoten A, B und C jeweils 1 Ereignis und 100 % an, da der nachfolgende Besuch der Site, auf der der Besucher nur Knoten C besuchte, die Journey-Anforderungen nicht erfüllt hätte, da Knoten A und Knoten B vor dem Besuch von Knoten C nicht besucht wurden.
