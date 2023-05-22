---
title: Attributions-Komponenteneinstellungen
description: Hier können Sie die Standardattribution für eine Metrik festlegen.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '1782'
ht-degree: 41%

---

# Attributions-Komponenteneinstellungen

Mit Attribution können Sie anpassen, wie Erfolgsereignisse Dimensionselementen zugeschrieben werden. Zum Beispiel:

1. Ein Besucher Ihrer Site klickt auf einen Paid-Search-Link zu einer Ihrer Produktseiten. Das Produkt wird zum Warenkorb hinzugefügt, aber nicht gekauft.
2. Am nächsten Tag sehen sie einen Social-Media-Beitrag von einem ihrer Freunde. Er klickt auf den Link und schließt dann den Kauf ab.

In einigen Berichten möchten Sie die Bestellung eventuell Paid Search zuordnen. In anderen Berichten möchten Sie die Bestellung eventuell Social Media zuordnen. Mithilfe von Attribution können Sie diesen Aspekt der Berichterstattung steuern.

Mit dieser Komponenteneinstellung für die Datenansicht können Sie ein standardmäßiges Attributionsmodell für eine Metrik festlegen. Sie können das Attributionsmodell einer bestimmten Metrik überschreiben, während Sie in Analysis Workspace arbeiten.

![Attribution](../assets/attribution-settings.png)

Wenn Ihre Organisation erfordert, dass eine Metrik über mehrere Attributionseinstellungen verfügt, können Sie eine der folgenden Aktionen durchführen:

* Kopieren Sie die Metrik in der Datenansicht mit jeder gewünschten Attributionseinstellung. Sie können dieselbe Metrik mehrmals in eine Datenansicht einbeziehen, wodurch jede Metrik eine andere Einstellung erhält. Stellen Sie sicher, dass Sie jede Metrik entsprechend benennen, damit Analysten den Unterschied zwischen diesen Metriken bei der Berichterstellung verstehen.
* Überschreiben Sie die Metrik in Analysis Workspace. In einer Metrik [Spalteneinstellungen](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)auswählen **[!UICONTROL Nicht standardmäßiges Attributionsmodell verwenden]** , um das Attributionsmodell der Metrik und das Lookback-Fenster für diesen Bericht zu ändern.

## Attributionsmodelle

Ein Attributionsmodell bestimmt, welchen Dimensionselementen eine Metrik zugeschrieben wird, wenn innerhalb des Lookback-Fensters einer Metrik mehrere Werte angezeigt werden. Attributionsmodelle gelten nur, wenn im Lookback-Fenster mehrere Dimensionselemente festgelegt sind. Wenn nur ein einzelnes Dimensionselement festgelegt ist, wird diesem Dimensionselement unabhängig vom verwendeten Attributionsmodell 100 % zugeschrieben.

| Symbol | Attributionsmodell | Definition |
| :---: | :--- | --- |
| ![Letztkontakt](../assets/attribution-models/last_touch1.png) | Letztkontakt | 100 % werden dem Touchpoint zugeschrieben, der zuletzt vor der Konversion aufgetreten ist. Dieses Attributionsmodell ist normalerweise der Standardwert für jede Metrik, bei der kein Attributionsmodell anderweitig angegeben ist. Unternehmen verwenden in der Regel dieses Modell, bei dem die Konvertierungszeit relativ kurz ist, z. B. bei der Analyse interner Suchbegriffe. |
| ![Erstkontakt](../assets/attribution-models/first_touch.png) | Erstkontakt | 100 % werden dem Touchpoint zugeschrieben, der zuerst im Attributions-Lookback-Fenster angezeigt wird. Unternehmen verwenden dieses Modell in der Regel, um das Markenbewusstsein oder die Kundenakquise zu verstehen. |
| ![Linear](../assets/attribution-models/linear.png) | Linear | Ermöglicht dieselbe Gewichtung für jeden Touchpoint, der vor einer Konversion erfolgte. Dies ist nützlich, wenn Konversionszyklen länger sind oder eine häufigere Kundeninteraktion erfordern. Unternehmen verwenden in der Regel dieses Attributionsmodell zur Messung der Benachrichtigungseffektivität mobiler Apps oder mit abonnementbasierten Produkten. |
| ![Beitrag](../assets/attribution-models/participation.png) | Beitrag | 100 % Gewichtung für alle eindeutigen Touchpoints. Da jedem Touchpoint 100 % zugeschrieben werden, ergeben sich für Metrikdaten in der Regel mehr als 100 %. Wenn ein Dimensionselement mehrmals vor einer Konversion separat angezeigt wird, werden die Werte auf 100 % dedupliziert. Dieses Attributionsmodell eignet sich ideal für Situationen, in denen Sie verstehen möchten, welche Touchpoints Kunden am häufigsten angezeigt werden. Medienunternehmen verwenden dieses Modell normalerweise zur Berechnung der Content Velocity. Einzelhandelsunternehmen verwenden dieses Modell normalerweise, um zu verstehen, welche Teile ihrer Site für die Konversion von entscheidender Bedeutung sind. |
| ![Selber Kontakt](../assets/attribution-models/same_touch.png) | Selber Kontakt | 100 % werden demselben Ereignis zugeschrieben, bei dem die Konversion erfolgte. Wenn bei demselben Ereignis wie einer Konversion kein Touchpoint auftritt, wird er unter &quot;Keine&quot;zusammengefasst. Dieses Attributionsmodell ist manchmal mit dem Attributionsmodell gleichgesetzt, das überhaupt nicht vorhanden ist. Dies ist in Szenarien nützlich, in denen Sie keine Werte aus anderen Ereignissen wünschen, die sich auf die Art und Weise auswirken, in der eine Metrik Dimensionselementen zugeschrieben wird. Produkt- oder Designteams können dieses Modell verwenden, um die Effektivität einer Seite zu bewerten, auf der eine Konversion stattfindet. |
| ![U-Form](../assets/attribution-models/u_shaped.png) | U-Form | Der ersten Interaktion werden 40 % zugeschrieben, der letzten Interaktion 40 %. Die verbleibenden 20 % werden auf alle dazwischen liegenden Touchpoints aufgeteilt. Bei Konversionen mit einem einzigen Touchpoint werden diesem 100 % zugeschrieben. Bei Konversionen mit zwei Touchpoints werden jedem 50 % zugeschrieben. Dieses Attributionsmodell eignet sich am besten in Szenarien, in denen Sie die erste und letzte Interaktion am häufigsten bewerten, aber keine zusätzlichen Interaktionen dazwischen vollständig verwerfen möchten. |
| ![J-Kurve](../assets/attribution-models/j_shaped.png) | J-Kurve | Der letzten Interaktion werden 60 % zugeschrieben, der ersten Interaktion werden 20 % zugeschrieben. Die restlichen 20 % werden auf alle dazwischen liegenden Touchpoints aufgeteilt. Bei Konversionen mit einem einzigen Touchpoint werden diesem 100 % zugeschrieben. Bei Konversionen mit zwei Touchpoints der letzten Interaktion 75 % zu geschrieben und der ersten 25 %. Ähnlich wie U-förmig bevorzugt dieses Attributionsmodell die ersten und letzten Interaktionen, bevorzugt jedoch die letzte Interaktion. |
| ![Umgekehrtes J](../assets/attribution-models/inverse_j.png) | Umgekehrtes J | Der ersten Interaktion werden 60 % zugeschrieben, der letzten Interaktion 20 %. Die verbleibenden 20 % werden auf alle dazwischen liegenden Touchpoints aufgeteilt. Bei Konversionen mit einem einzigen Touchpoint werden diesem 100 % zugeschrieben. Bei Konversionen mit zwei Touchpoints der ersten Interaktion 75 % zu geschrieben und der letzten 25 %. Ähnlich wie J-förmig bevorzugt dieses Attributionsmodell die ersten und letzten Interaktionen, bevorzugt jedoch die erste Interaktion. |
| ![Zeitverfall](../assets/attribution-models/time_decay.png) | Zeitverfall | Folgt einem exponentiellen Abfall mit einem benutzerdefinierten Parameter für die Halbwertszeit, wobei der Standardwert 7 Tage ist. Die Gewichtung der einzelnen Kanäle hängt von der Zeit ab, die zwischen dem Beginn des Touchpoints und der letztendlichen Konversion verstrichen ist. Die Formel, die zur Bestimmung der Gewichtung verwendet wird, lautet `2^(-t/halflife)`, wobei `t` die Zeit zwischen einem Touchpoint und einer Konversion ist. Alle Touchpoints werden dann auf 100 % normalisiert. Ideal für Szenarien, in denen Sie die Attribution mit einem bestimmten und wichtigen Ereignis messen möchten. Je länger eine Konversion nach diesem Ereignis erfolgt, desto weniger Gewichtung wird gewährt. |
| ![Benutzerspezifisch](../assets/attribution-models/custom.png) | Anpassen | Ermöglicht die Angabe der Gewichtungen, die Sie für den Erstkontakt-Punkt, den Letztkontakt-Punkt und alle dazwischen liegenden Touchpoints festlegen möchten. Die angegebenen Werte werden auf 100 % normalisiert, selbst wenn die eingegebenen benutzerdefinierten Zahlen zusammen nicht 100 ergeben. Bei Konversionen mit einem einzigen Touchpoint werden diesem 100 % zugeschrieben. Bei Interaktionen mit zwei Touchpoints wird der mittlere Parameter ignoriert. Die ersten und letzten Touchpoints werden dann auf 100 % normalisiert und die Gewichtung wird entsprechend zugeschrieben. Dieses Modell eignet sich ideal für Analysten, die vollständige Kontrolle über ihr Attributionsmodell wünschen und spezielle Anforderungen haben, die andere Attributionsmodelle nicht erfüllen. |
| ![Algorithmisch](../assets/attribution-models/algorithmic.png) | Algorithmisch | Verwendet statistische Verfahren, um die optimale Zuordnung für die ausgewählte Metrik dynamisch zu bestimmen. Der für die Zuordnung verwendete Algorithmus basiert auf der Harsanyi-Dividende aus der kooperativen Spieltheorie. Die Harsanyi-Dividende ist eine Verallgemeinerung der Shapley-Wertlösung (die nach Lloyd Shapley, einem Nobelpreisträger für Ökonomie, benannt wurde) zur Verteilung von Gutschriften unter den Spielern in einem Spiel mit ungleichen Beiträgen zum Ergebnis.<br>Auf hoher Ebene wird die Attribution als eine Koalition von Akteuren berechnet, auf die ein Überschuss gleichmäßig verteilt werden muss. Die Überschusshöhe jeder Koalition wird nach dem Überschuss bestimmt, der zuvor von jeder Unterkoalition (oder zuvor teilnehmenden Dimensionselementen) rekursiv erzeugt wurde. Weitere Informationen finden Sie in den Originalpapieren von John Harsanyi und Lloyd Shapley:<br>Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.<br>Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220. |

{style="table-layout:auto"}

## Lookback-Fenster

Ein Lookback-Fenster ist der Zeitraum, der für eine Konversion rückblickend bei der Erfassung von Touchpoints berücksichtigt werden sollte. Wenn ein Dimensionselement außerhalb des Lookback-Fensters festgelegt wird, wird der Wert nicht in Attributionsberechnungen einbezogen.

* **14 Tage**: Blickt bis zu 14 Tage nach der Konvertierung zurück.
* **30 Tage**: Blickt bis zu 30 Tage nach der Konvertierung zurück.
* **60 Tage**: Blickt bis zu 60 Tage nach der Konvertierung zurück.
* **90 Tage**: Blickt bis zu 90 Tage nach der Konvertierung zurück.
* **Sitzung**: Blickt bis zum Anfang der Sitzung zurück, in der eine Konversion stattgefunden hat. Sitzungs-Lookback-Fenster berücksichtigen die geänderte [Sitzungs-Timeout](../create-dataview.md#session-settings).
* **Person (Berichtsfenster)**: Betrachtet alle Besuche bis zum ersten des Monats des aktuellen Datumsbereichs. Wenn der Datumsbereich des Berichts beispielsweise zwischen dem 15. September und dem 30. September liegt, liegt der Besucher-Lookback-Datumsbereich zwischen dem 1. September und dem 30. September. Wenn Sie dieses Lookback-Fenster verwenden, können Sie gelegentlich sehen, dass Dimensionselemente Datumsangaben außerhalb Ihres Berichtsfensters zugeordnet werden.
* **Benutzerdefinierte Zeit:** Ermöglicht Ihnen das Festlegen eines benutzerdefinierten Lookback-Fensters ab dem Zeitpunkt der Konvertierung. Sie können die Anzahl der Minuten, Stunden, Tage, Wochen, Monate oder Quartale festlegen. Wenn beispielsweise am 20. Februar eine Konversion stattfand, würde ein Lookback-Fenster von fünf Tagen alle Dimensionskontaktpunkte vom 15. Februar bis 20. Februar im Attributionsmodell auswerten.

## Beispiel

Siehe folgendes Beispiel:

1. Am 15. September gelangt ein Besucher über Paid Search zu Ihrer Site und verlässt sie dann.
2. Am 18. September gelangt der Besucher erneut über einen Link in sozialen Medien zu Ihrer Site, den er von einem Freund erhalten hat. Er fügt mehrere Artikel zum Warenkorb hinzu, erwirbt aber nichts.
3. Am 24. September sendet Ihr Marketing-Team eine E-Mail mit einem Coupon für einige der Artikel im Warenkorb. Der Coupon wird angewendet, der Besucher ruft aber mehrere andere Websites auf, um zu sehen, ob andere Coupons verfügbar sind. Er findet einen weiteren über eine Display-Anzeige und kauft dann letztendlich für 50 Euro ein.

Je nach Lookback-Fenster und Attributionsmodell erhalten Kanäle eine unterschiedliche Gewichtung. Im Folgenden finden Sie einige interessante Beispiele:

* Verwenden **Erstkontakt** und **Sitzungs-Lookback-Fenster**, betrachtet die Attribution nur den dritten Besuch. E-Mail kam vor Display-Anzeige, sodass E-Mail 100 % des Kaufs von 50 Euro zugeschrieben werden.
* Verwenden **Erstkontakt** und **Personen-Lookback-Fenster**, betrachtet die Attribution alle drei Besuche. Paid Search kam zuerst, sodass Paid Search 100 % des Kaufs von 50 Euro zugeschrieben werden.
* Verwenden **linear** und **Sitzungs-Lookback-Fenster**, wird die Gewichtung zwischen E-Mail und Anzeige aufgeteilt. Beiden Kanälen werden jeweils 25 Euro zugeschrieben.
* Verwenden **linear** und **Personen-Lookback-Fenster**, wird die Gewichtung zwischen Paid Search, Social Media, E-Mail und Display-Anzeige aufgeteilt. Jedem Kanal werden für diesen Kauf 12,50 Euro zugeschrieben.
* Verwenden **J-förmig** und **Personen-Lookback-Fenster**, wird die Gewichtung zwischen Paid Search, Social Media, E-Mail und Display-Anzeige aufgeteilt.
   * Der Display-Anzeige werden 60 %, also 30 Euro, zugeschrieben.
   * Paid Search werden 20 %, also 10 Euro, zugeschrieben.
   * Die restlichen 20 % werden zwischen Social Media und E-Mail aufgeteilt (jeweils 5 Euro).
* Verwenden **Zeitverfall** und **Personen-Lookback-Fenster**, wird die Gewichtung zwischen Paid Search, Social Media, E-Mail und Display-Anzeige aufgeteilt. Verwendung der standardmäßigen 7-Tage-Halbwertszeit:
   * Abstand von null Tagen zwischen Display-Touchpoint und Konversion. `2^(-0/7) = 1`
   * Abstand von null Tagen zwischen E-Mail-Touchpoint und Konversion. `2^(-0/7) = 1`
   * Abstand von sechs Tagen zwischen Social-Media-Touchpoint und Konversion. `2^(-6/7) = 0.552`
   * Abstand von neun Tagen zwischen Paid-Search-Touchpoint und Konversion. `2^(-9/7) = 0.41`
   * Die Normalisierung dieser Werte führt zu Folgendem:
      * Display-Anzeige: 33,8 %, 16,88 Euro
      * E-Mail: 33,8 %, 16,88 Euro
      * Social Media: 18,6 %, 9,32 Euro
      * Paid Search: 13,8 %, 6,92 Euro

Konversionsereignisse, die normalerweise ganze Zahlen aufweisen, werden aufgeteilt, wenn die Gewichtung für mehrere Kanäle erfolgt. Wenn beispielsweise zwei Kanäle mit einem linearen Attributionsmodell zu einer Bestellung beitragen, erhalten beide Kanäle 0,5 dieser Reihenfolge. Diese partiellen Metriken werden über alle Personen summiert und dann zur Berichterstellung auf die nächste Ganzzahl gerundet.
