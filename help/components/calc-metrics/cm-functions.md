---
title: Referenz – Grundfunktionen
description: Mit dem Generator für berechnete Metriken können Sie statistische und mathematische Funktionen anwenden, um erweiterte berechnete Metriken zu erstellen.
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: ht
source-wordcount: '1078'
ht-degree: 100%

---

# Referenz – Grundfunktionen

Mit dem Generator für berechnete Metriken können Sie statistische und mathematische Funktionen anwenden, um erweiterte berechnete Metriken zu erstellen.

Im Folgenden werden die Funktionen und ihre Definitionen alphabetisch aufgelistet.

>[!NOTE]
>
>Wenn [!DNL metric] als Argument in einer Funktion angegeben ist, sind auch andere Ausdrücke von Metriken zulässig. Beispiel: [!DNL MAXV(metrics)] ermöglicht auch [!DNL MAXV(PageViews + Visits).]

## Vergleich zwischen Tabellenfunktionen und Zeilenfunktionen

Bei einer Tabellenfunktion ist die Ausgabe für jede Tabellenzeile gleich. Bei einer Zeilenfunktion ist die Ausgabe für jede Tabellenzeile unterschiedlich.

## Absolutwert (Zeile)

Gibt den Absolutwert einer Zahl zurück. Der Absolutwert einer Zahl ist die Zahl mit einem positiven Wert.

```
ABS(metric)
```

| Argument | Beschreibung |
|---|---|
| *metric* | Die Metrik, für die Sie den Absolutwert abrufen möchten. |

## Spaltenmaximum

Gibt den größten Wert in einem Satz aus Dimensionselementen für eine Metrikspalte zurück. MAXV wird vertikal innerhalb einer einzelnen Spalte (Metrik) über Dimensionselemente hinweg ausgewertet.

```
MAXV(metric)
```

| Argument | Beschreibung |
|---|---|
| *metric* | Die Metrik, die Sie auswerten möchten. |

## Spaltenminimum

Gibt den kleinsten Wert in einem Satz aus Dimensionselementen für eine Metrikspalte zurück. MINV wird vertikal innerhalb einer einzelnen Spalte (Metrik) über Dimensionselemente hinweg ausgewertet.

```
MINV(metric)
```

| Argument | Beschreibung |
|---|---|
| *metric* | Die Metrik, die Sie auswerten möchten. |

## Spaltensumme

Addiert alle numerischen Werte für eine Metrik innerhalb einer Spalte (über die Elemente einer Dimension hinweg).

```
SUM(metric)
```

| Argument | Beschreibung |
|---|---|
| *metric* | Die Metrik, für die Sie den Gesamtwert oder die Summe ermitteln möchten. |

## Anzahl (Tabelle)

Gibt die Zahl oder Anzahl der Werte ungleich null für eine Metrik innerhalb einer Spalte zurück (die Anzahl der eindeutigen Elemente innerhalb einer Dimension).

```
COUNT(metric)
```

| Argument | Beschreibung |
|---|---|
| *metric* | Die Metrik, die gezählt werden soll. |

## Exponent (Zeile)

Gibt *e* hoch eine angegebene Zahl zurück. Die Konstante *e* ist gleich 2,71828182845904 (der Basis des natürlichen Logarithmus). EXP ist die Umkehrung von LN, des natürlichen Logarithmus einer Zahl.

```
EXP(metric)
```

| Argument | Beschreibung |
|---|---|
| *metric* | Der Exponent, der auf Basis *e* angewendet wird. |

## Potenzierung

Potenzierungsoperator

<pre>
pow(x,y) = x<sup>y</sup> = x*x*x*… (y-mal)
</pre>

## Arithmetisches Mittel (Tabelle)

Gibt das arithmetische Mittel (oder den Durchschnitt) für eine Metrik in einer Spalte zurück.

```
MEAN(metric)
```

| Argument | Beschreibung |
|---|---|
| *metric* | Die Metrik, für die Sie den Durchschnitt ermitteln möchten. |

## Medianwert (Tabelle)

Gibt den Medianwert für eine Metrik in einer Spalte zurück. Der Medianwert ist die Zahl in der Mitte eines Zahlensatzes, d. h. die Hälfte der Zahlen hat Werte größer oder gleich dem Medianwert und die Hälfte ist kleiner oder gleich dem Medianwert.

```
MEDIAN(metric)
```

| Argument | Beschreibung |
|---|---|
| *metric* | Die Metrik, für die Sie den Medianwert ermitteln möchten. |

## Modulo

Der Rest von col1/col2 mit euklidischer Division.

Gibt den Rest zurück, nachdem x durch y geteilt wurde.

```
x = floor(x/y) + modulo(x,y)
```

Der Rückgabewert hat dasselbe Vorzeichen wie die Eingabe (oder ist null).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

Um immer eine positive Zahl zu erhalten, verwenden Sie

```
modulo(modulo(x,y)+y,y)
```

## Perzentil (Tabelle)

Gibt das k. Perzentil der Werte für eine Metrik zurück. Mit dieser Funktion können Sie einen Akzeptanzschwellenwert einrichten. Sie können beispielsweise Dimensionselemente untersuchen, die über dem 90. Perzentil liegen.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> Die Metrikspalte, die die relative Position definiert. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> Der Perzentilwert im Bereich von 0 bis 100 (einschließlich). </td> 
  </tr> 
 </tbody> 
</table>

## Quartil (Tabelle)

Gibt das Quartil der Werte für eine Metrik zurück. Anhand von Quartilen können Sie beispielsweise die oberen 25 % der Produkte finden, die den meisten Umsatz generieren. MINV, MEDIAN und MAXV geben denselben Wert wie QUARTILE zurück, wenn Quartil 0 (null), 2 bzw. 4 entspricht.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> Die Metrik, für die Sie den Quartilwert abrufen möchten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> Gibt an, welcher *-Wert zurückgegeben werden soll. </td> 
  </tr> 
 </tbody> 
</table>

&#42;Wenn *quart* = 0 ist, gibt QUARTILE den Mindestwert zurück. Wenn *quart* = 1 ist, gibt QUARTILE das zweite Quartil (25. Perzentil) zurück. Wenn *quart* = 2 ist, gibt QUARTILE das zweite Quartil (50. Perzentil) zurück. Wenn *quart* = 3 ist, gibt QUARTILE das zweite Quartil (75. Perzentil) zurück. Wenn *quart* = 4 ist, gibt QUARTILE den Höchstwert zurück.

## Rund

Gibt die nächste Ganzzahl für einen Wert zurück. Beispiel: Wenn Sie keine Währungsdezimalzahlen für den Umsatz in Berichte aufnehmen möchten und ein Produkt einen Umsatz von 569,34 US-Dollar aufweist, können Sie mit der Formel Round(*Revenue*) den Umsatz bis zum nächsten Dollar runden (in diesem Fall 569 US-Dollar). Ein Produkt mit einem Umsatz von 569,51 US-Dollar wird zum nächsten Dollarbetrag (570 US-Dollar) gerundet.

```
ROUND(metric)
```

| Argument | Beschreibung |
|---|---|
| *number* | Die Metrik, die gerundet werden soll. |

Das Runden ohne Stellenparameter ist mit dem Runden mit dem Stellenparameter 0 identisch, also der Rundung zur nächsten Ganzzahl. Wenn Sie einen Stellenparameter angeben, wird die angegebene Anzahl an Stellen rechts neben dem Dezimalzeichen zurückgegeben. Wenn der Stellenparameter negativ ist, werden Nullen links neben dem Dezimalzeichen zurückgegeben.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Zeilenanzahl

Gibt die Anzahl der Zeilen in einer bestimmten Spalte zurück (die Anzahl berichteter eindeutiger Elemente innerhalb einer Dimension). „Individuelle Werte überschritten“ wird als 1 gezählt.

## Zeilenmaximum

Das Maximum der Spalten in jeder Zeile.

## Zeilenminimum

Das Minimum der Spalten in jeder Zeile.

## Zeilensumme

Die Summe der Spalten in jeder Zeile.

## Quadratwurzel (Zeile)

Gibt die positive Quadratwurzel einer Zahl zurück. Die Quadratwurzel einer Zahl ist der Wert dieser Zahl hoch 1/2.

```
SQRT(metric)
```

| Argument | Beschreibung |
|---|---|
| *number* | Die Metrik, für die Sie die Quadratwurzel abrufen möchten. |

## Standardabweichung (Tabelle)

Gibt die Standardabweichung (oder die Quadratwurzel der Schwankung) basierend auf einer Beispieldatenpopulation zurück.

Die Gleichung für STDEV lautet:

![](assets/std_dev.png)

wobei x das arithmetische Beispielmittel (*metric*) und *n* die Beispielgröße ist.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argument</b> </td> 
   <td> <b> Beschreibung</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> metric</i> </b> </td> 
   <td> <p> Die Metrik, deren Standardabweichung gewünscht ist. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Varianz (Tabelle)

Gibt die Schwankung basierend auf einer Beispieldatenpopulation zurück.

Die Gleichung für VARIANCE lautet:

![](assets/variance_eq.png)

wobei x das arithmetische Beispielmittel MEAN(*metric*) und *n* die Beispielgröße ist.

```
VARIANCE(metric)
```

| Argument | Beschreibung |
|---|---|
| *metric* | Die Metrik, für die Sie die Schwankung ermitteln möchten. |

Zur Berechnung einer Varianz sehen Sie sich eine gesamte Spalte von Zahlen an. Aus dieser Liste von Zahlen berechnen Sie zunächst den Durchschnitt. Sobald Sie den Durchschnitt ermittelt haben, sehen Sie sich jeden Eintrag an und tun Folgendes:

1. Ziehen Sie den Durchschnitt von der Zahl ab.

2. Quadrieren Sie das Ergebnis.

3. Fügen Sie diesen Wert zum Gesamtergebnis hinzu.

Sobald Sie die gesamte Spalte durchlaufen haben, haben Sie ein einziges Gesamtergebnis. Teilen Sie dann dieses Gesamtergebnis durch die Anzahl der Elemente in der Spalte. Die resultierende Zahl ist die Varianz für die Spalte. Es handelt sich dabei um eine einzige Zahl. Allerdings wird der Wert in Form einer Spalte mit Zahlen angezeigt.

Beispiel: Sie haben eine Spalte mit drei Elementen:

1

2

3

Der Durchschnitt dieser Spalte ist 2. Die Varianz für die Spalte ist ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3 = 2/3.
