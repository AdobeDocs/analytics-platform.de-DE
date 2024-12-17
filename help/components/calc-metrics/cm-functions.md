---
title: Grundlegende Funktionen
description: Mit dem Generator für berechnete Metriken können Sie statistische und mathematische Funktionen anwenden, um erweiterte berechnete Metriken zu erstellen.
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: 1804f3dc4126007c1ff553f844d691c80623bb90
workflow-type: tm+mt
source-wordcount: '1636'
ht-degree: 93%

---

# Grundlegende Funktionen


Mit dem [Generator für berechnete Metriken](cm-workflow/cm-build-metrics.md) können Sie statistische und mathematische Funktionen anwenden. In diesem Artikel werden die Funktionen und ihre Definitionen alphabetisch aufgelistet.

>[!NOTE]
>
>Wenn [!DNL metric] als Argument in einer Funktion angegeben ist, sind auch andere Ausdrücke von Metriken zulässig. Beispiel: [COLUMN MAXIMUM(metrics)](#column-maximum) ermöglicht auch [COLUMN MAXIMUM(PageViews + Visits)](#column-maximum).



## Vergleich zwischen Tabellenfunktionen und Zeilenfunktionen

Bei einer Tabellenfunktion ist die Ausgabe für jede Tabellenzeile gleich. Bei einer Zeilenfunktion ist die Ausgabe für jede Tabellenzeile unterschiedlich.

Gegebenenfalls wird einer Funktion eine Anmerkung mit dem Typ der Funktion hinzugefügt: [!BADGE Tabelle]{type="Neutral"}[!BADGE Zeile]{type="Neutral"}

## Was bedeutet der Parameter „include-zeros“? 

Damit wird angegeben, ob Nullen in die Berechnung einbezogen werden sollen. In manchen Fällen bedeutet eine Null *nichts*, in anderen Fällen kann sie aber auch wichtig sein.

Beispiel: Wenn Sie mit einer Umsatzmetrik arbeiten und dem Bericht dann eine Seitenansichtsmetrik hinzufügen, gibt es plötzlich mehr Zeilen für den Umsatz, die alle Nullwerte enthalten. Sie möchten wahrscheinlich nicht, dass sich diese zusätzliche Metrik auf Berechnungen wie **[ARITHMETISCHES MITTEL](cm-functions.md#mean)**, **[ZEILENMINIMUM](cm-functions.md#row-min)**, **[QUARTIL](cm-functions.md#quartile)** usw. auswirkt, die sich in der Umsatzspalte befinden. In diesem Fall müssen Sie den Parameter `include-zeros` aktivieren.

Ein alternatives Szenario besteht darin, dass Sie zwei Metriken von Interesse haben und eine Metrik einen höheren Durchschnitt oder ein höheres Minimum aufweist, da einige der Zeilen Nullen sind.   In diesem Fall können Sie festlegen, dass der Parameter nicht auf Nullen überprüft werden soll.



## Absolutwert {#absolute-value}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_absolute_value"
>title="Absolutwert"
>abstract="Gibt den Absolutwert einer Zahl zurück. Der Absolutwert einer Zahl ist die Zahl mit einem positiven Wert."

<!-- markdownlint-enable MD034 -->


![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL ABSOLUTE VALUE(metric)]**

[!BADGE Zeile]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die der absolute Wert berechnet werden soll. |


## Spaltenmaximum {#column-maximum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_column_maximum"
>title="Spaltenmaximum"
>abstract="Gibt den größten Wert in einem Satz aus Dimensionselementen für eine Metrikspalte zurück. MAXV wird vertikal innerhalb einer einzelnen Spalte (Metrik) über Dimensionselemente hinweg ausgewertet."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MAXIMUM(metric, include_zeros)]**

Gibt den größten Wert in einem Satz aus Dimensionselementen für eine Metrikspalte zurück. MAXV wird vertikal innerhalb einer einzelnen Spalte (Metrik) über Dimensionselemente hinweg ausgewertet.

| Argument | Beschreibung |
|---|---|
| metric | Erfordert mindestens eine Metrik, kann jedoch eine beliebige Anzahl von Metriken als Parameter verwenden. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht. |


## Spaltenminimum {#column-minimum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_column_minimum"
>title="Spaltenminimum"
>abstract="Gibt den kleinsten Wert in einem Satz aus Dimensionselementen für eine Metrikspalte zurück. MINV wird vertikal innerhalb einer einzelnen Spalte (Metrik) über Dimensionselemente hinweg ausgewertet."

<!-- markdownlint-enable MD034 -->


![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MINIMUM(metric, include_zeros)]**

Gibt den kleinsten Wert in einem Satz aus Dimensionselementen für eine Metrikspalte zurück. MINV wird vertikal innerhalb einer einzelnen Spalte (Metrik) über Dimensionselemente hinweg ausgewertet.

| Argument | Beschreibung |
|---|---|
| metric | Erfordert mindestens eine Metrik, kann jedoch eine beliebige Anzahl von Metriken als Parameter verwenden. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht. |


## Spaltensumme {#column-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_column_sum"
>title="Spaltensumme"
>abstract="Addiert alle numerischen Werte für eine Metrik innerhalb einer Spalte (über die Elemente einer Dimension hinweg)."

<!-- markdownlint-enable MD034 -->


![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN SUM(metric)]**

Addiert alle numerischen Werte für eine Metrik innerhalb einer Spalte (über die Elemente einer Dimension hinweg).

| Argument | Beschreibung |
|---|---|
| metric | Erfordert mindestens eine Metrik, kann jedoch eine beliebige Anzahl von Metriken als Parameter verwenden. |


## Anzahl {#count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_count"
>title="Anzahl"
>abstract="Gibt die Zahl oder Anzahl der Werte ungleich null für eine Metrik innerhalb einer Spalte zurück (die Anzahl der eindeutigen Elemente innerhalb einer Dimension)."

<!-- markdownlint-enable MD034 -->


![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL COUNT(metric)]**

[!BADGE Tabelle]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, die gezählt werden soll. |


## Exponent {#exponent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_exponent"
>title="Exponent"
>abstract="Gibt e hoch eine angegebene Zahl zurück. Die Konstante e ist gleich 2,71828182845904 (der Basis des natürlichen Logarithmus). EXPONENT ist die Umkehrung von LN, der natürliche Logarithmus einer Zahl."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENT(metric)]**

[!BADGE Zeile ]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric | Die Exponentialfunktion mit Basis „e“. |


## Arithmetisches Mittel {#mean}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_mean"
>title="Arithmetisches Mittel"
>abstract="Gibt das arithmetische Mittel (bzw. den Durchschnitt) einer Metrik in einer Spalte zurück."

<!-- markdownlint-enable MD034 -->


![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL MEAN(metric, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die der Durchschnitt berechnet werden soll. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht. |


## Median {#median}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_median"
>title="Median"
>abstract="Gibt den Medianwert für eine Metrik in einer Spalte zurück. Der Median ist die Zahl in der Mitte einer Zahlenfolge. Das heißt, die Hälfte der Zahlen hat Werte, die größer oder gleich dem Median sind, und die Hälfte ist kleiner oder gleich dem Median."

<!-- markdownlint-enable MD034 -->


![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIAN(metric, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die der Median berechnet werden soll. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht. |


## Modulo {#modulo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_modulo"
>title="Modulo"
>abstract="Gibt den Rest bei der euklidischen Division von x durch y zurück. "

<!-- markdownlint-enable MD034 -->


![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL MODULO(metric_X, metric_Y)]**

Gibt den Rest bei der euklidischen Division von x durch y zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Die erste Metrik, die geteilt werden soll. |
| metric_Y | Die zweite Metrik, die geteilt werden soll. |

### Beispiele

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
>id="calcmetrics_function_percentile"
>title="Perzentil"
>abstract="Gibt das n-te Perzentil zurück, das einen Wert zwischen 0 und 100 darstellt. Wenn n &lt; 0 ist, verwendet die Funktion null. Wenn n > 100 ist, gibt die Funktion 100 zurück."

<!-- markdownlint-enable MD034 -->


![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL PERCENTILE(metric, k, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric | Der Perzentilwert im Bereich von 0 bis 100 (einschließlich). |
| k | Die Metrikspalte, die die relative Position definiert. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht. |



## Potenzierungsoperator {#power-operator}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_power_operator"
>title="Potenzierungsoperator"
>abstract="Gibt die y-te Potenz von x zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL POWER OPERATOR(metric_X, metrix_Y)]**

Gibt die y-te Potenz von x zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Die Metrik, die zur Potenz metric_Y erhoben werden soll. |
| metric_Y | Die Potenz, zu der metric_X erhoben werden soll. |


## Quartil {#quartile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_quartile"
>title="Quartil"
>abstract="Gibt das Quartil der Werte für eine Metrik zurück. Beispielsweise können Quartile verwendet werden, um die 25 % der Produkte zu finden, die den höchsten Umsatz erzielen."

<!-- markdownlint-enable MD034 -->


![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL QUARTILE(metric, quartile, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"}[COLUMN MINIMUM](#column-minimum), [MEDIAN](#median) und [COLUMN MAXIMUM](#column-maximum) geben jeweils denselben Wert zurück wie [QUARTILE](#quartile), wenn „Quartil“ `0` (null), `2` bzw. `4` entspricht.

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die der Quartilwert berechnet werden soll. |
| Quartil | Gibt an, welcher Quartilwert zurückgegeben werden soll. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht. |


## Runden {#round}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_round"
>title="Runden"
>abstract="Das Runden ohne den Parameter *number* hat den gleichen Effekt wie das Runden mit dem Parameter *number* von 0, also die Rundung auf die nächste Ganzzahl. Mit einem Parameter *number* gibt ROUND die auf *number* Ziffern rechts vom Dezimalzeichen gerundete Zahl zurück. Wenn *number* negativ ist, werden entsprechend viele Nullen links neben dem Dezimalzeichen zurückgegeben."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL ROUND(metric, number)]**

Das Runden ohne den Parameter *number* hat den gleichen Effekt wie das Runden mit dem Parameter *number* von 0, also die Rundung auf die nächste Ganzzahl. Mit einem Parameter *number* gibt ROUND die auf *number* Ziffern rechts vom Dezimalzeichen gerundete Zahl zurück. Wenn *number* negativ ist, werden entsprechend viele Nullen links neben dem Dezimalzeichen zurückgegeben.

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, die gerundet werden soll. |
| number | Gibt an, wie viele Stellen rechts neben dem Dezimalzeichen zurückgegeben werden sollen. (Falls negativ, werden Nullen links neben dem Dezimalzeichen zurückgegeben.) |

### Beispiele

```
ROUND( 314.15, 0) = 314
ROUND( 314.15, 1) = 314.1
ROUND( 314.15, -1) = 310
ROUND( 314.15, -2) = 300
```

## Zeilenanzahl {#row-count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_row_count"
>title="Zeilenanzahl"
>abstract="Gibt die Anzahl der Zeilen in einer bestimmten Spalte zurück (die Anzahl der innerhalb einer Dimension berichteten eindeutigen Elemente). *Individuelle Werte überschritten* wird als 1 gezählt."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL ROW COUNT()]**

Gibt die Anzahl der Zeilen in einer bestimmten Spalte zurück (die Anzahl der innerhalb einer Dimension berichteten eindeutigen Elemente). *Individuelle Werte überschritten* wird als 1 gezählt.


## Zeilenmaximum {#row-max}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_row_max"
>title="Zeilenmaximum"
>abstract="Das Maximum der Spalten in jeder Zeile."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MAX(metric, include_zeros)]**

Das Maximum der Spalten in jeder Zeile.

| Argument | Beschreibung |
|---|---|
| metric | Erfordert mindestens eine Metrik, kann jedoch eine beliebige Anzahl von Metriken als Parameter verwenden. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht. |


## Zeilenminimum {#row-min}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_row_min"
>title="Zeilenminimum"
>abstract="Das Minimum der Spalten in jeder Zeile."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MIN(metric, include_zeros)]**

Das Minimum der Spalten in jeder Zeile.

| Argument | Beschreibung |
|---|---|
| metric | Erfordert mindestens eine Metrik, kann jedoch eine beliebige Anzahl von Metriken als Parameter verwenden. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht. |



## Zeilensumme {#row-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_row_sum"
>title="Zeilensumme"
>abstract="Die Summe der Spalten in jeder Zeile."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL ROW SUM(metric, include_zeros)]**

Die Summe der Spalten in jeder Zeile.

| Argument | Beschreibung |
|---|---|
| metric | Erfordert mindestens eine Metrik, kann jedoch eine beliebige Anzahl von Metriken als Parameter verwenden. |


## Quadratwurzel {#square-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_square_root"
>title="Quadratwurzel"
>abstract="Gibt die positive Quadratwurzel einer Zahl zurück. Die Quadratwurzel einer Zahl ist der Wert dieser Zahl hoch 1/2."

<!-- markdownlint-enable MD034 -->


![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL SQUARE ROOT(metric, include_zeros)]**

[!BADGE Zeile]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die die Quadratwurzel berechnet werden soll. |


## Standardabweichung {#standard-deviation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_standard_deviation"
>title="Standardabweichung"
>abstract="Gibt die Standardabweichung (oder die Quadratwurzel der Schwankung) basierend auf einer Beispieldatenpopulation zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL STANDARD DEVIATION(metric, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| | Die Metrik, für die die Standardabweichung berechnet werden soll. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht. |


## Varianz {#variance}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_variance"
>title="Varianz"
>abstract="Gibt die Schwankung basierend auf einer Beispieldatenpopulation zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANCE(metric, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die die Varianz berechnet werden soll. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht. |


Die Gleichung für VARIANCE lautet:

![](assets/variance_eq.png){width="100"}

Dabei ist *x* der Mittelwert der Stichprobe, [MEAN(*metric*)](#mean), und *n* ist der Stichprobenumfang.


Zur Berechnung einer Varianz wird eine gesamte Spalte von Zahlen betrachtet. Aus dieser Liste von Zahlen berechnen Sie zunächst den Durchschnitt. Sobald Sie den Durchschnitt ermittelt haben, sehen Sie sich jeden Eintrag an und gehen wie folgt vor:

1. Ziehen Sie den Durchschnitt von der Zahl ab.

1. Quadrieren Sie das Ergebnis.

1. Fügen Sie diesen Wert zum Gesamtergebnis hinzu.

Sobald Sie die gesamte Spalte durchlaufen haben, erhalten Sie ein einziges Gesamtergebnis. Teilen Sie dann dieses Gesamtergebnis durch die Anzahl der Elemente in der Spalte. Die resultierende Zahl ist die Varianz für die Spalte. Es handelt sich dabei um eine einzige Zahl. Allerdings wird der Wert in Form einer Spalte mit Zahlen angezeigt.

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

Returns the median for a metric in a column. The median is the number in the middle of a set of numbers—that is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

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