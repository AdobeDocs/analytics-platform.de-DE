---
title: Grundlegende Funktionen
description: Erfahren Sie mehr über die grundlegenden Funktionen berechneter Metriken.
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: 211f0411d0bf70288cbd46bb219fce7ae99fe03d
workflow-type: tm+mt
source-wordcount: '3599'
ht-degree: 48%

---

# Grundlegende Funktionen


Mit dem [Generator für berechnete Metriken](cm-workflow/cm-build-metrics.md) können Sie statistische und mathematische Funktionen anwenden. In diesem Artikel werden die Funktionen und ihre Definitionen alphabetisch aufgelistet.

>[!NOTE]
>
>Wenn [!DNL metric] als Argument in einer Funktion angegeben ist, sind auch andere Ausdrücke von Metriken zulässig. Beispielsweise ermöglicht [COLUMN MAXIMUM(Metriken)](#column-maximum) auch [COLUMN MAXIMUM(PageViews + Sessions)](#column-maximum).



## Vergleich zwischen Tabellenfunktionen und Zeilenfunktionen

Eine Tabellenfunktion ist eine Funktion, bei der die Ausgabe für jede Zeile der Tabelle gleich ist. Eine Zeilenfunktion ist eine Funktion, bei der die Ausgabe für jede Zeile der Tabelle unterschiedlich ist.

Gegebenenfalls wird einer Funktion eine Anmerkung mit dem Typ der Funktion hinzugefügt: [!BADGE Tabelle]{type="Neutral"} oder [!BADGE Zeile]{type="Neutral"}.

## Was bedeutet der Parameter „include-zeros“?

Damit wird angegeben, ob Nullen in die Berechnung einbezogen werden sollen. In manchen Fällen bedeutet eine Null *nichts*, in anderen Fällen kann sie aber auch wichtig sein.

Beispiel: Wenn Sie mit einer Umsatzmetrik arbeiten und dem Bericht dann eine Seitenansichtsmetrik hinzufügen, gibt es plötzlich mehr Zeilen für den Umsatz, die alle Nullwerte enthalten. Sie möchten wahrscheinlich nicht, dass sich diese zusätzliche Metrik auf Berechnungen wie **[ARITHMETISCHES MITTEL](cm-functions.md#mean)**, **[ZEILENMINIMUM](cm-functions.md#row-min)**, **[QUARTIL](cm-functions.md#quartile)** usw. auswirkt, die sich in der Umsatzspalte befinden. In diesem Fall müssen Sie den Parameter `include-zeros` aktivieren.

Ein alternatives Szenario besteht darin, dass Sie zwei Metriken von Interesse haben und eine Metrik einen höheren Durchschnitt oder ein höheres Minimum aufweist, da einige der Zeilen Nullen sind.   In diesem Fall können Sie festlegen, dass der Parameter nicht auf Nullen überprüft werden soll.



## Absolutwert {#absolute-value}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-abs"
>title="Absolutwert"
>abstract="Gibt den absoluten Wert einer Zahl zurück. Der absolute Wert einer Zahl ist die Zahl mit einem positiven Wert."

<!-- markdownlint-enable MD034 -->


![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL ABSOLUTE VALUE(metric)]**

[!BADGE Zeile]{type="Neutral"} Gibt den absoluten Wert einer Zahl zurück. Der absolute Wert einer Zahl ist die Zahl mit einem positiven Wert.

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die der absolute Wert berechnet werden soll. |

**Anwendungsfall** Stellen Sie sicher, dass alle Ergebnisse positiv sind, wenn Sie Metriken analysieren, die möglicherweise negative Werte ergeben, z. B. Umsatzdeltas oder prozentuale Änderungen. Dies hilft, sich auf das Ausmaß der Veränderung ohne Rücksicht auf die Richtung zu konzentrieren.

**Im Generator für berechnete Metriken**: Schließen Sie Ihre Metrik oder Ihren Ausdruck in die Funktion **Absoluter Wert** ein, z. B.: **Absoluter Wert**(Aktueller Umsatz - Vorheriger Umsatz). Dadurch werden alle negativen Differenzen in positive Werte umgewandelt.

>[!TIP]
>
>Verwenden Sie diese Option, um absolute Unterschiede zwischen zwei Zeiträumen oder Segmenten zu messen, unabhängig davon, ob die Leistung gestiegen oder gesunken ist.
>

## Spaltenmaximum {#column-maximum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-max"
>title="Spaltenmaximum"
>abstract="Gibt den größten Wert in einem Satz aus Dimensionselementen für eine Metrikspalte zurück. MAXV wird vertikal innerhalb einer einzelnen Spalte (Metrik) über Dimensionselemente hinweg ausgewertet."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MAXIMUM(metric, include_zeros)]**

Gibt den größten Wert in einem Satz aus Dimensionselementen für eine Metrikspalte zurück. MAXV wird vertikal innerhalb einer einzelnen Spalte (Metrik) über Dimensionselemente hinweg ausgewertet.

| Argument | Beschreibung |
|---|---|
| metric | Erfordert mindestens eine Metrik, kann jedoch eine beliebige Anzahl von Metriken als Parameter verwenden. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht. |

**Anwendungsfall**: Identifizieren Sie den höchsten Wert innerhalb einer Aufschlüsselung, z. B. den Tag mit den meisten Besuchen oder das Produkt mit dem höchsten Umsatz. Auf diese Weise wird die Spitzenleistung kategorieübergreifend hervorgehoben.

**Im Generator für berechnete Metriken**: Wenden Sie **Spaltenmaximum** auf eine Metrik wie *Umsatz* oder *Sitzungen* an, wenn Sie nach *Tag* oder *Produkt* aufschlüsseln. Die Funktion gibt für jede Zeile den größten Wert in dieser Spalte zurück.

>[!TIP]
>
>Verwenden Sie eine [IF](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-adv-functions#if)-Anweisung wie **IF**(*Revenue* = **Column Maximum***(Revenue*), 1, 0), um das Element in Ihrer Aufschlüsselung hervorzuheben, das die beste Leistung erzielt.
>

## Spaltenminimum {#column-minimum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-min"
>title="Spaltenminimum"
>abstract="Gibt den kleinsten Wert in einem Satz aus Dimensionselementen für eine Metrikspalte zurück. MINV wird vertikal innerhalb einer einzelnen Spalte (Metrik) über Dimensionselemente hinweg ausgewertet."

<!-- markdownlint-enable MD034 -->


![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MINIMUM(metric, include_zeros)]**

Gibt den kleinsten Wert in einem Satz aus Dimensionselementen für eine Metrikspalte zurück. MINV wird vertikal innerhalb einer einzelnen Spalte (Metrik) über Dimensionselemente hinweg ausgewertet.

| Argument | Beschreibung |
|---|---|
| metric | Erfordert mindestens eine Metrik, kann jedoch eine beliebige Anzahl von Metriken als Parameter verwenden. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht. |

**Anwendungsfall**: Identifizieren Sie den Wert mit der niedrigsten Leistung innerhalb einer Aufschlüsselung, z. B. die Kampagne mit den geringsten Konversionen oder den Tag mit dem geringsten Umsatz. Dies hilft beim schnellen Aufdecken von leistungsschwachen Segmenten.

**Im Generator für berechnete Metriken**: Wenden Sie **Spaltenminimum** auf eine Metrik wie *Umsatz* oder *Konversionsrate* an, wenn Sie nach *Kampagne* oder *Tag* aufschlüsseln. Die Funktion gibt für jede Zeile den kleinsten Wert in dieser Spalte zurück.

>[!TIP]
>
>Verwenden Sie eine [IF](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-adv-functions#if)-Anweisung wie **IF**(*Revenue* = **Column Minimum***(Revenue*), 1, 0), um das Element in Ihrer Aufschlüsselung mit der niedrigsten Leistung hervorzuheben.
>


## Spaltensumme {#column-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-sum"
>title="Spaltensumme"
>abstract="Addiert alle numerischen Werte für eine Metrik innerhalb einer Spalte (über die Elemente einer Dimension hinweg)."

<!-- markdownlint-enable MD034 -->


![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN SUM(metric)]**

Addiert alle numerischen Werte für eine Metrik innerhalb einer Spalte (über die Elemente einer Dimension hinweg).

| Argument | Beschreibung |
|---|---|
| metric | Erfordert mindestens eine Metrik, kann jedoch eine beliebige Anzahl von Metriken als Parameter verwenden. |

**Anwendungsfall**: Berechnung der Summe aller Werte in einer Aufschlüsselung, z. B. Gesamtumsatz über alle Produkte oder Gesamtbesuche über alle Tage hinweg. Dies ist hilfreich, wenn Sie eine Gesamtsumme benötigen, um sie mit den einzelnen Zeilenwerten zu vergleichen.

**Im Generator für berechnete Metriken**: Wenden Sie **Spaltensumme** auf eine Metrik wie *Umsatz* oder *Sitzungen* an, während Sie nach *Produkt* oder *Tag* aufschlüsseln. Die Funktion gibt die Summe aller Werte in dieser Spalte für jede Zeile zurück.

>[!TIP]
>
>Verwenden Sie diese Option, wenn Sie einen Verweis auf die Gesamtsumme benötigen, um Anteile oder Prozentsätze der Gesamtleistung zu berechnen.
>


## Anzahl {#count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count"
>title="Anzahl"
>abstract="Gibt die Zahl oder Anzahl der Werte ungleich null für eine Metrik innerhalb einer Spalte zurück (die Anzahl der eindeutigen Elemente innerhalb einer Dimension)."

<!-- markdownlint-enable MD034 -->


![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL COUNT(metric)]**

[!BADGE Tabelle]{type="Neutral"} Gibt die Anzahl der Werte für eine Metrik innerhalb einer Spalte zurück, die ungleich null sind (die Anzahl erfasster eindeutiger Elemente innerhalb einer Dimension).

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, die gezählt werden soll. |

**Anwendungsfall**: Zählen der Anzahl der in einer Berechnung enthaltenen Datenpunkte, z. B. die Anzahl der Tage in einem Datumsbereich oder die Anzahl der Produkte in einer Aufschlüsselung. Dies ist hilfreich, wenn Sie wissen müssen, wie viele Elemente zu einem aggregierten Wert beitragen.

**Im Generator für berechnete Metriken**: Wenden Sie **count** auf eine Metrik wie *Sitzungen* oder *Umsatz* an, um die Gesamtzahl der Zeilen (oder Datenpunkte) zurückzugeben, die in der aktuellen Aufschlüsselung oder im Datumsbereich enthalten sind.

>[!TIP]
>
>Verwenden Sie zusammen mit **Spaltensumme** um Durchschnittswerte manuell zu berechnen (z. B. **Spaltensumme**(*Umsatz*) / **Anzahl**(Umsatz)).
>

## Exponent {#exponent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-exp"
>title="Exponent"
>abstract="Gibt e potenziert mit einer gegebenen Zahl zurück. Die Konstante e entspricht 2,71828182845904, der Basis des natürlichen Logarithmus. EXPONENT ist die Umkehrung von LN, dem natürlichen Logarithmus einer Zahl."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENT(metric)]**

[!BADGE Row]{type="Neutral"} Gibt *e* erhöht um die Potenz einer bestimmten Zahl zurück. Die Konstante *e* entspricht 2,71828182845904, der Basis des natürlichen Logarithmus. EXPONENT ist die Umkehrung von LN, dem natürlichen Logarithmus einer Zahl.

| Argument | Beschreibung |
|---|---|
| metric | Der auf die Basis angewendete Exponent *e*. |

**Anwendungsfall**: Hebt *e* auf die Potenz einer bestimmten Zahl oder Metrik auf. Dies ist nützlich bei der Modellierung von Wachstumstrends oder der exponentiellen Skalierung einer Metrik.

**Im Generator für berechnete Metriken**: Verwenden Sie **Exponent** mit einer Metrik. Beispiel: **Exponent**(*Sessions*) hebt *e* auf die Metrik *Sessions* an.

>[!TIP]
>
>Kombinieren Sie mit **Logarithmus** für erweiterte Modellierung oder zur Glättung von hochvariablen Daten beim Vergleich von Wachstumsmustern.
>


## Arithmetisches Mittel {#mean}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-mean"
>title="Arithmetisches Mittel"
>abstract="Gibt das arithmetische Mittel (d. h. den Durchschnitt) für eine Metrik in einer Spalte zurück."

<!-- markdownlint-enable MD034 -->


![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL MEAN(metric, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"} Gibt das arithmetische Mittel (oder den Durchschnitt) für eine Metrik in einer Spalte zurück.

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die der Durchschnitt berechnet werden soll. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht. |

**Anwendungsfall**: Berechnet den arithmetischen Durchschnitt einer Reihe von Werten, wie z. B. den durchschnittlichen täglichen Umsatz oder die durchschnittliche Anzahl der Besuche pro Kampagne. Dies hilft bei der Festlegung einer Baseline für den Vergleich einzelner Werte in einem Datensatz.

**Im Generator für berechnete Metriken**: Wenden Sie **Mittel** auf eine Metrik wie *Umsatz* oder *Sitzungen* an, um den Durchschnittswert für alle Datenpunkte in der ausgewählten Aufschlüsselung oder im Datumsbereich zurückzugeben.

>[!TIP]
>
>Verwenden Sie diese Option, um die allgemeinen Leistungstrends zu verstehen, oder kombinieren Sie sie mit **Standardabweichung**, um die Konsistenz um den Durchschnitt herum zu messen.
>

## Median {#median}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-median"
>title="Median"
>abstract="Gibt den Medianwert für eine Metrik in einer Spalte zurück. Der Median ist die Zahl in der Mitte einer Zahlenreihe. Das heißt, die Hälfte der Zahlen weist Werte auf, die größer oder gleich dem Median sind, und die Hälfte ist kleiner oder gleich dem Median."

<!-- markdownlint-enable MD034 -->


![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIAN(metric, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"} Gibt den Medianwert für eine Metrik in einer Spalte zurück. Der Median ist die Zahl in der Mitte einer Zahlenreihe. Das heißt, die Hälfte der Zahlen weist Werte auf, die größer oder gleich dem Median sind, und die Hälfte ist kleiner oder gleich dem Median.

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die der Median berechnet werden soll. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht. |

**Anwendungsfall**: Identifizieren Sie den Mittelwert in einem Datensatz, z. B. den Median des täglichen Umsatzes oder den Median der Seitenansichten pro Besuch. Dies ist hilfreich, wenn Sie die Auswirkungen von Ausreißern reduzieren und die zentrale Tendenz Ihrer Daten erkennen möchten.

**Im Generator für berechnete Metriken**: Wenden Sie den Median auf eine Metrik wie Umsatz oder Seitenansichten an, um den Mittelpunktwert für alle Datenpunkte in der ausgewählten Aufschlüsselung oder im Datumsbereich zurückzugeben.

>[!TIP]
>
>Verwenden Sie anstelle von **Mittel**, wenn Ihre Daten extreme Höhen oder Tiefen enthalten, die den Durchschnitt verfälschen könnten.
>


## Modulo {#modulo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-modulo"
>title="Modulo"
>abstract="Gibt den Rest bei der euklidischen Division von x durch y zurück. "

<!-- markdownlint-enable MD034 -->


![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL MODULO(metric_X, metric_Y)]**

Gibt den Rest bei der euklidischen Division von x durch y zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Die erste Metrik, die geteilt werden soll. |
| metric_Y | Die zweite Metrik, die geteilt werden soll. |

**Anwendungsfall**: Gibt den Rest zurück, nachdem eine Zahl durch eine andere geteilt wurde. Dies kann für zyklische oder sich wiederholende Muster nützlich sein, z. B. die Identifizierung jedes n-ten Tages oder einer Kampagne in einer Sequenz.

**Im Generator für berechnete Metriken**: Verwenden Sie **Modulo** mit zwei numerischen Eingaben. Beispiel: **Modulo**(*Tageszahl*, 7) gibt den Rest zurück, nachdem die Tageszahl durch sieben geteilt wurde, was dazu beitragen kann, Daten nach Woche zu gruppieren.

>[!TIP]
>
>Kombinieren Sie mit bedingter Logik, um wiederkehrende Intervalle zu markieren oder Daten basierend auf sich wiederholenden Zyklen zu segmentieren.
>

### Weitere Beispiele

Der Rückgabewert hat dasselbe Vorzeichen wie die Eingabe (oder ist null).

```
MODULO(4,3) = 1
MODULO(-4,3) = -1
MODULO(-3,3) = 0
```

Um sicherzustellen, dass Sie immer eine positive Zahl zu erhalten, verwenden Sie

```
MODULO(MODULO(x,y)+y,y)
```

## Perzentil {#percentile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-percentile"
>title="Perzentil"
>abstract="Gibt das n-te Perzentil zurück, das einen Wert zwischen 0 und 100 darstellt. Wenn n &lt; 0 ist, verwendet die Funktion null. Wenn n > 100 ist, gibt die Funktion 100 zurück."

<!-- markdownlint-enable MD034 -->


![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL PERCENTILE(metric, k, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"} Gibt das n-te Perzentil zurück, das einen Wert zwischen 0 und 100 darstellt. Wenn n &lt; 0 ist, verwendet die Funktion null. Wenn n > 100 ist, gibt die Funktion 100 zurück.

| Argument | Beschreibung |
|---|---|
| metric | Der Perzentilwert im Bereich von 0 bis 100 (einschließlich). |
| k | Die Metrikspalte, die die relative Position definiert. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht. |

**Anwendungsfall**: Identifizieren Sie den Wert, unter den ein bestimmter Prozentsatz von Datenpunkten fällt, z. B. das 90. Perzentil des täglichen Umsatzes oder die Seitenansichten. Dies hilft bei der Messung der Verteilung und der Erkennung von Ausreißern mit hoher Leistung.

**Im Generator für berechnete Metriken**: Wenden Sie **Perzentil** auf eine Metrik wie *Umsatz* oder *Sitzungen* an und geben Sie den gewünschten Perzentilwert an (z. B. **Perzentil**(*Umsatz*, 90)). Das Ergebnis zeigt den Schwellenwert an, unter den 90 % der Datenpunkte fallen.

>[!TIP]
>
>Verwenden Sie , um Leistungsbenchmarks festzulegen oder nach leistungsstärksten Tagen, Kampagnen oder Produkten zu filtern.
>

## Potenzierungsoperator {#power-operator}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-pow"
>title="Potenzierungsoperator"
>abstract="Gibt die y-te Potenz von x zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL POWER OPERATOR(metric_X, metrix_Y)]**

Gibt die y-te Potenz von x zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Die Metrik, die zur Potenz metric_Y erhoben werden soll. |
| metric_Y | Die Potenz, zu der metric_X erhoben werden soll. |

**Anwendungsfall**: Erhöhen Sie eine Zahl oder Metrik auf die Stärke einer anderen, z. B. durch Quadrieren eines Werts oder Anwenden einer exponentiellen Gewichtung. Dies ist hilfreich bei der Modellierung von Wachstum, der Skalierung von Werten oder der Durchführung erweiterter mathematischer Transformationen.

**Im Generator für berechnete**: Verwenden Sie **Power Operator** zwischen zwei numerischen Werten oder Metriken. Beispiel: *Umsatz* ^ 2 hebt den *Umsatz*-Wert auf die zweite Potenz.

>[!TIP]
>
>Ähnlich wie die **Exponent**-Funktion, jedoch ausgedrückt als mathematischer Operator, wodurch innerhalb berechneter Metriken kompaktere Formeln ermöglicht werden.
>

## Quartil {#quartile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-quartile"
>title="Quartil"
>abstract="Gibt das Quartil der Werte für eine Metrik zurück. Quartile können beispielsweise verwendet werden, um die oberen 25 % der Produkte zu finden, die den höchsten Umsatz erzielen."

<!-- markdownlint-enable MD034 -->


![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL QUARTILE(metric, quartile, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"} Gibt das Quartil der Werte für eine Metrik zurück. Anhand von Quartilen können Sie beispielsweise die oberen 25 % der Produkte finden, die den meisten Umsatz generieren. [COLUMN MINIMUM](#column-minimum), [MEDIAN](#median) und [COLUMN MAXIMUM](#column-maximum) geben jeweils denselben Wert zurück wie [QUARTILE](#quartile), wenn „Quartil“ `0` (null), `2` bzw. `4` entspricht.

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die der Quartilwert berechnet werden soll. |
| Quartil | Gibt an, welcher Quartilwert zurückgegeben werden soll. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht. |

**Anwendungsfall**: Teilen Sie einen Datensatz in vier gleiche Teile auf, um zu verstehen, wie Werte verteilt werden, z. B. die Identifizierung der obersten 25 % der Tage nach Umsatz oder Besuchen. Dies hilft, die Leistung in Ranggruppen zu unterteilen, um einen tieferen Vergleich zu ermöglichen.

**Im Generator für berechnete Metriken**: Wenden Sie **Quartil** auf eine Metrik wie *Umsatz* oder *Sitzungen* an und geben Sie an, welches Quartil zurückgegeben werden soll (z. B. **Quartil**(*Umsatz*, 3), um den Schwellenwert für das dritte Quartil oder die obersten 25 % zu finden).

>[!TIP]
>
>Verwenden Sie , um Werte in Leistungsstufen wie Kampagnen oder Produkte mit niedriger, mittlerer und hoher Leistung zu gruppieren.
>

## Runden {#round}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-round"
>title="Runden"
>abstract="Das Runden ohne den Parameter *number* hat den gleichen Effekt wie das Runden mit dem Parameter *number* von 0, also die Rundung auf die nächste Ganzzahl. Mit einem Parameter *number* gibt ROUND die auf *number* Ziffern rechts vom Dezimalzeichen gerundete Zahl zurück. Wenn *number* negativ ist, werden entsprechend viele Nullen links neben dem Dezimalzeichen zurückgegeben."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL ROUND(metric, number)]**

Das Runden ohne den Parameter *number* hat den gleichen Effekt wie das Runden mit dem Parameter *number* von 0, also die Rundung auf die nächste Ganzzahl. Mit einem Parameter *number* gibt ROUND die auf *number* Ziffern rechts vom Dezimalzeichen gerundete Zahl zurück. Wenn *number* negativ ist, werden entsprechend viele Nullen links neben dem Dezimalzeichen zurückgegeben.

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, die gerundet werden soll. |
| number | Gibt an, wie viele Stellen rechts neben dem Dezimalzeichen zurückgegeben werden sollen. (Falls negativ, werden Nullen links neben dem Dezimalzeichen zurückgegeben.) |

**Anwendungsfall**: Vereinfachen Sie numerische Ergebnisse, indem Sie sie auf eine bestimmte Anzahl von Dezimalstellen runden. Dies ist hilfreich, um klarere Visualisierungen zu erstellen oder die Lesbarkeit berechneter Metriken in Berichten zu vereinfachen.

**Im Generator für berechnete**: Wenden Sie **Round** auf eine Metrik oder einen Ausdruck an und geben Sie die Anzahl der Dezimalstellen an. Beispiel: **round**(*Konversionsrate*, 2) rundet den Wert auf zwei Dezimalstellen.

>[!TIP]
>
>Wird verwendet, um die Formatierung von Metriken in Berichten zu standardisieren, insbesondere bei der Anzeige von Prozentsätzen oder Währungswerten.
>

### Weitere Beispiele

```
ROUND( 314.15, 0) = 314
ROUND( 314.15, 1) = 314.1
ROUND( 314.15, -1) = 310
ROUND( 314.15, -2) = 300
```

## Zeilenanzahl {#row-count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count-rows"
>title="Zeilenanzahl"
>abstract="Gibt die Anzahl der Zeilen in einer bestimmten Spalte zurück (die Anzahl der innerhalb einer Dimension berichteten eindeutigen Elemente). *Individuelle Werte überschritten* wird als 1 gezählt."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL ROW COUNT()]**

Gibt die Anzahl der Zeilen in einer bestimmten Spalte zurück (die Anzahl der innerhalb einer Dimension berichteten eindeutigen Elemente). *Individuelle Werte überschritten* wird als 1 gezählt.

**Anwendungsfall** Zählen Sie die Gesamtzahl der in einer Aufschlüsselung oder einem Datensatz zurückgegebenen Zeilen, z. B. die Anzahl der Tage, Kampagnen oder Produkte, die in einem Bericht enthalten sind. Auf diese Weise lässt sich erkennen, wie viele Elemente zu Ihrer Analyse beitragen.

**Im Generator für berechnete Metriken**: Wenden Sie **Zeilenanzahl** an, um die Gesamtzahl der Zeilen in der aktuellen Aufschlüsselung oder im aktuellen Segment zurückzugeben. Wenn Sie beispielsweise „Umsatz ** nach *Produkt*, **Zeilenanzahl** anzeigen, wird die Anzahl der angezeigten Produkte zurückgegeben.

>[!TIP]
>
>Verwenden Sie mit anderen Funktionen wie **Spaltensumme**, um Durchschnittswerte manuell zu berechnen (z. B. **Spaltensumme**(*Umsatz*) / **Zeilenanzahl**())).
>

## Zeilenmaximum {#row-max}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-max"
>title="Zeilenmaximum"
>abstract="Das Maximum der Spalten in jeder Zeile."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MAX(metric, include_zeros)]**

Das Maximum der Spalten in jeder Zeile.

| Argument | Beschreibung |
|---|---|
| metric | Erfordert mindestens eine Metrik, kann jedoch eine beliebige Anzahl von Metriken als Parameter verwenden. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht. |

**Anwendungsfall**: Identifizieren Sie den höchsten Wert für alle Metriken in einer einzigen Zeile, z. B. welche Metrik (z. B. *Umsatz*, *Bestellungen* oder *Sitzungen*) den größten Wert für einen bestimmten Tag oder ein bestimmtes Segment hat. Auf diese Weise kann hervorgehoben werden, welche Metrik in jeder Datenzeile zu Leads führt.

**Im Generator für berechnete Metriken**: Wenden Sie **Zeilenmaximum** an, wenn mehrere Metriken in einer berechneten Metrik enthalten sind. Beispiel: **Row Maximum**(*Umsatz*, *Bestellungen*, *Sitzungen*) gibt den größten Wert unter diesen Metriken für jede Zeile zurück.

>[!TIP]
>
>Verwenden Sie , um verwandte Metriken nebeneinander zu vergleichen und zu ermitteln, welcher in jeder Zeile am meisten zur Leistung beiträgt.
>

## Zeilenminimum {#row-min}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-min"
>title="Zeilenminimum"
>abstract="Das Minimum der Spalten in jeder Zeile."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MIN(metric, include_zeros)]**

Das Minimum der Spalten in jeder Zeile.

| Argument | Beschreibung |
|---|---|
| metric | Erfordert mindestens eine Metrik, kann jedoch eine beliebige Anzahl von Metriken als Parameter verwenden. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht. |

**Anwendungsfall**: Identifizieren Sie den niedrigsten Wert für alle Metriken in einer einzigen Zeile, z. B. welche Metrik (z. B. *Umsatz*, *Bestellungen* oder *Sitzungen*) den kleinsten Wert für einen bestimmten Tag oder ein bestimmtes Segment hat. Auf diese Weise können Sie die Metrik mit der schwächsten Performance in jeder Datenzeile identifizieren.

**Im Generator für berechnete Metriken**: Wenden Sie **Zeilenminimum“ an** wenn Sie mehrere Metriken vergleichen. Beispiel: **Mindestzeile**(*Umsatz*, *Bestellungen*, *Sitzungen*) gibt den kleinsten Wert unter diesen Metriken für jede Zeile zurück.

>[!TIP]
>
>Kombinieren Sie mit dem Zeilenmaximum, um Leistungsbereiche zu berechnen oder unterdurchschnittliche Metriken in einem Vergleich nebeneinander hervorzuheben.
>

## Zeilensumme {#row-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-sum"
>title="Zeilensumme"
>abstract="Die Summe der Spalten in jeder Zeile."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL ROW SUM(metric, include_zeros)]**

Die Summe der Spalten in jeder Zeile.

| Argument | Beschreibung |
|---|---|
| metric | Erfordert mindestens eine Metrik, kann jedoch eine beliebige Anzahl von Metriken als Parameter verwenden. |

**Anwendungsfall**: Addieren Sie die Werte mehrerer Metriken in einer einzigen Zeile, z. B. Summe *Umsatz* und *Steuer*, um den Gesamttransaktionswert zu berechnen oder *Sitzungen* aus verschiedenen Quellen zu kombinieren. Dies hilft, verwandte Metriken in einer Summe zu konsolidieren.

**Im Generator für berechnete Metriken**: Wenden Sie **Zeilensumme** an, um mehrere Metriken zu kombinieren. Beispiel: **Zeilensumme**(*Umsatz*, *Steuer*) fügt diese beiden Metriken für jede Zeile in Ihrer Aufschlüsselung hinzu.

>[!TIP]
>
>Verwenden Sie , um kombinierte Summen zu erstellen oder verwandte Leistungsindikatoren in einer einzigen berechneten Metrik zu gruppieren.
>

## Quadratwurzel {#square-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sqrt"
>title="Quadratwurzel"
>abstract="Gibt die positive Quadratwurzel einer Zahl zurück. Die Quadratwurzel einer Zahl ist der Wert, wenn diese Zahl zur Potenz 1/2 erhoben wird."

<!-- markdownlint-enable MD034 -->


![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL SQUARE ROOT(metric, include_zeros)]**

[!BADGE Zeile]{type="Neutral"} Gibt die positive Quadratwurzel einer Zahl zurück. Die Quadratwurzel einer Zahl ist der Wert, wenn diese Zahl zur Potenz 1/2 erhoben wird.

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die die Quadratwurzel berechnet werden soll. |

**Anwendungsfall**: Gibt die Quadratwurzel einer Zahl oder Metrik zurück, z. B. das Auffinden der Varianzwurzel bei der Berechnung der Standardabweichung oder der Normalisierung von Werten in einem Datensatz. Dies ist für erweiterte statistische Berechnungen oder Datenumwandlungsberechnungen nützlich.

**Im Generator für berechnete Metriken**: Anwenden **Quadratwurzel** auf eine Metrik oder einen Ausdruck. Beispiel: **Quadratwurzel**(Varianz(*Umsatz*)) gibt die Standardabweichung von &quot;*&quot;*.

>[!TIP]
>
>Wird verwendet, wenn Sie Metriken proportional skalieren müssen oder um andere statistische Funktionen zu unterstützen, die auf Stammwerten basieren.
>

## Standardabweichung {#standard-deviation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-stdev"
>title="Standardabweichung"
>abstract="Gibt die Standardabweichung (oder die Quadratwurzel der Schwankung) basierend auf einer Beispieldatenpopulation zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL STANDARD DEVIATION(metric, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"} Gibt die Standardabweichung (d. h. die Quadratwurzel der Varianz) basierend auf einer Stichprobenpopulation von Daten zurück.

| Argument | Beschreibung |
|---|---|
| | Die Metrik, für die die Standardabweichung berechnet werden soll. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht. |

**Anwendungsfall**: Messen Sie, wie viele Werte vom Durchschnitt abweichen, z. B. wie konsistent der tägliche Umsatz oder die Besuche im Laufe der Zeit sind. Dies hilft bei der Identifizierung von Volatilität, Stabilität oder ungewöhnlichen Leistungsschwankungen.

**Im Generator für berechnete Metriken**: Wenden Sie **Standardabweichung** auf eine Metrik wie *Umsatz* oder *Sitzungen* an, um den Spread der Werte innerhalb der ausgewählten Aufschlüsselung oder des Datumsbereichs zu berechnen. Beispiel: **Standardabweichung**(*Umsatz*) zeigt an, wie stark der tägliche Umsatz vom Mittelwert abweicht.

>[!TIP]
>
>Verwenden Sie with *Mean*, um Anomalien zu erkennen oder die Konsistenz der Leistung über Kampagnen, Produkte oder Segmente hinweg zu vergleichen.
>

## Varianz {#variance}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-variance"
>title="Varianz"
>abstract="Gibt die Schwankung basierend auf einer Beispieldatenpopulation zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANCE(metric, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"} Gibt die Schwankung basierend auf einer Beispieldatenpopulation zurück.

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die die Varianz berechnet werden soll. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht. |

**Anwendungsfall**: Messen Sie, wie weit sich die Werte in einem Datensatz vom Mittelwert entfernen, z. B. indem Sie analysieren, wie stark sich der tägliche Umsatz oder die Sitzungsdauer im Laufe der Zeit verändert. Dies hilft bei der Quantifizierung des Grads der Konsistenz oder der Schwankung der Leistung.

**Im Generator für berechnete Metriken**: Wenden Sie **Varianz** auf eine Metrik wie *Umsatz* oder *Besuchszeit pro Besuch* an, um die durchschnittliche quadratische Abweichung vom Mittelwert zu berechnen. Beispiel: **Variance**(*Umsatz*) zeigt, wie stark sich die Umsatzwerte vom Durchschnitt im ausgewählten Bereich unterscheiden.

>[!TIP]
>
>Verwenden Sie mit **Standardabweichung** um die Datenvariabilität besser zu verstehen und Bereiche mit unvorhersehbarer Leistung zu identifizieren.
>

Die Gleichung für VARIANCE lautet:

![](assets/variance_eq.png){width="100"}

Dabei ist *x* der Mittelwert der Stichprobe, [MEAN(*metric*)](#mean), und *n* ist der Stichprobenumfang.


Zur Berechnung einer Varianz wird eine gesamte Spalte von Zahlen betrachtet. Aus dieser Liste von Zahlen berechnen Sie zunächst den Durchschnitt. Sobald Sie den Durchschnitt ermittelt haben, sehen Sie sich jeden Eintrag an und gehen wie folgt vor:

1. Ziehen Sie den Durchschnitt von der Zahl ab.

1. Quadrieren Sie das Ergebnis.

1. Fügen Sie diesen Wert zum Gesamtergebnis hinzu.

Sobald Sie die gesamte Spalte durchlaufen haben, erhalten Sie ein einziges Gesamtergebnis. Dieser Gesamtbetrag wird dann durch die Anzahl der Elemente in der Spalte geteilt. Diese Zahl ist die Varianz für die Spalte. Es ist eine einzelne Zahl. Sie wird jedoch als Zahlenspalte angezeigt.

Im Beispiel der folgenden Spalte mit drei Elementen:

| Spalte |
|:---:|
| 1 |
| 2 |
| 3 |

Der Durchschnitt dieser Spalte ist 2. Die Varianz für die Spalte ist ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3) = 2/3.

<!--

## Absolute Value (Row)

Returns the absolute value of a number. The absolute value of a number is the number with a positive value.

```
ABS(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the absolute value.  |

## Column Maximum

Returns the largest value in a set of dimension elements for a metric column. MAXV evaluates vertically within a single column (metric) across dimension elements.

```
MAXV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Minimum 

Returns the smallest value in a set of dimension elements for a metric column. MINV evaluates vertically within a single column (metric) across dimension elements.

```
MINV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Sum 

Adds all of the numeric values for a metric within a column (across the elements of a dimension).

```
SUM(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the total value or sum.  |

## Count (Table) 

Returns the number, or count, of non-zero values for a metric within a column (the number of unique elements reported within a dimension).

```
COUNT(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric that you want to count.  |

## Exponent (Row) 

Returns *e* raised to the power of a given number. The constant *e* equals 2.71828182845904, the base of the natural logarithm. EXP is the inverse of LN, the natural logarithm of a number.

```
EXP(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The exponent applied to the base *e*.  |

## Exponentiation 

Power Operator


pow(x,y) = x<sup>y</sup> = x*x*x*… (y times)


## Mean (Table) 

Returns the arithmetic mean, or average, for a metric in a column.

```
MEAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the average.  |

## Median (Table) 

Returns the median for a metric in a column. The median is the number in the middle of a set of numbers-that is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

```
MEDIAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the median.  |

## Modulo 

The remainder of col1 / col2, using Euclidean division.

Returns the remainder after dividing x by y.

```
x = floor(x/y) + modulo(x,y)
```

The return value has the same sign as the input (or is zero).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

To always get a positive number, use 

```
modulo(modulo(x,y)+y,y)
```

## Percentile (Table) 

Returns the k-th percentile of values for a metric. You can use this function to establish a threshold of acceptance. For example, you can decide to examine dimension elements who score above the 90  percentile.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric column that defines relative standing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> The percentile value in the range 0 to 100, inclusive. </td> 
  </tr> 
 </tbody> 
</table>

## Quartile (Table) 

Returns the quartile of values for a metric. For example, quartiles can be used to find the top 25% of products driving the most revenue. MINV, MEDIAN, and MAXV return the same value as QUARTILE when quart is equal to 0 (zero), 2, and 4, respectively.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric for which you want the quartile value. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> Indicates which *value to return. </td> 
  </tr> 
 </tbody> 
</table>

&#42;If *quart* = 0, QUARTILE returns the minimum value. If *quart* = 1, QUARTILE returns the first quartile (25 percentile). If *quart* = 2, QUARTILE returns the first quartile (50 percentile). If *quart* = 3, QUARTILE returns the first quartile (75 percentile). If *quart* = 4, QUARTILE returns the maximum value.

## Round 

Returns the nearest integer for a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula Round( *Revenue*) to round revenue to the nearest dollar, or $569. A product reporting $569.51 will be round to the nearest dollar, or $570.

```
ROUND(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric you want to round.  |

Round without a digits parameter is the same as round with a digits parameter of 0, namely round to the nearest integer. With a digits parameter it returns that many digits to the right of the decimal. If digits is negative, it returns 0's to the left of the decimal.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Row Count 

Returns the count of rows for a given column (the number of unique elements reported within a dimension). "Uniques exceeded" is counted as 1.

## Row Max 

The maximum of the columns in each row.

## Row Min 

The minimum of the columns in each row.

## Row Sum

The sum of the columns of each row.

## Square Root (Row) 

Returns the positive square root of a number. The square root of a number is the value of that number raised to the power of 1/2.

```
SQRT(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric for which you want the square root.  |

## Standard Deviation (Table) 

Returns the standard deviation, or square root of the variance, based on a sample population of data.

The equation for STDEV is:

![](assets/std_dev.png)

where x is the sample mean (*metric*) and *n* is the sample size.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argument</b> </td> 
   <td> <b> Description</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> metric</i> </b> </td> 
   <td> <p> The metric for which you want for standard deviation. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variance (Table) 

Returns the variance based on a sample population of data.

The equation for VARIANCE is:

![](assets/variance_eq.png)

where x is the sample mean, MEAN(*metric*), and *n* is the sample size.

```
VARIANCE(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the variance.  |

In order to calculate a variance you look at an entire column of numbers. From that list of numbers you first calculate the average. Once you have the average you go through each entry and do the following:

1. Subtract the average from the number.

2. Square the result.

3. Add that to the total.

Once you have iterated over the entire column you have a single total. You then divide that total by the number of items in the column. That number is the variance for the column. It is a single number. It is, however, displayed as a column of numbers.

In case of a three-item column:

1

2

3

The average of this column is 2. The variance for the column will be ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3 = 2/3.

-->