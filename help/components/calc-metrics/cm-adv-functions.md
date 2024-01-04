---
title: Referenz – Erweiterte Funktionen
description: Greifen Sie auf diese Funktionen zu, indem Sie in der Dropdown-Liste „Funktionen“ die Option „Erweitert anzeigen“ auswählen.
feature: Calculated Metrics
exl-id: 3689a499-817d-4a59-8a1f-5f7bda297268
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '3062'
ht-degree: 98%

---

# Referenz – Erweiterte Funktionen

Greifen Sie auf diese Funktionen zu, indem Sie in der Dropdown-Liste **[!UICONTROL Funktionen]** die Option **[!UICONTROL Erweitert anzeigen]** wählen.

## Vergleich zwischen Tabellenfunktionen und Zeilenfunktionen

Bei einer Tabellenfunktion ist die Ausgabe für jede Tabellenzeile gleich. Bei einer Zeilenfunktion ist die Ausgabe für jede Tabellenzeile unterschiedlich.

## Was bedeutet der Parameter „Include-Zeros“?

Damit wird angegeben, ob Nullen in die Berechnung einbezogen werden sollen. In manchen Fällen bedeutet eine Null „nichts“, in anderen Fällen kann sie aber auch wichtig sein.

Beispiel: Wenn Sie mit einer Umsatzmetrik arbeiten und dem Bericht dann eine Seitenansichtsmetrik hinzufügen, gibt es plötzlich mehr Zeilen für den Umsatz, die alle Nullwerte enthalten. Dies soll sich sicherlich nicht auf Berechnungen für arithmetisches MEAN, MIN, QUARTILE usw. auswirken, die Sie für die Umsatzspalte eingerichtet haben. In diesem Fall würden Sie den include-zeros-Parameter aktivieren.

Wenn Sie allerdings an zwei Metriken interessiert sind, soll vielleicht nicht eine Metrik einen höheren Durchschnitt oder Mindestwert erhalten, weil einige seiner Zeilen Null waren. Daher würden Sie den Parameter zum Einbeziehen der Nullwerte nicht aktivieren.

## AND

Gibt den Wert des zugehörigen Arguments zurück. Mit „NOT“ können Sie sicherstellen, dass ein Wert nicht mit einem bestimmten Wert übereinstimmt.

>[!NOTE]
>
>0 (null) bedeutet „Falsch“ und jeder andere Wert „Wahr“.

```
AND(logical_test1,[logical_test2],...)
```

| Argument | Beschreibung |
|---|---|
| *logical_test1* | Erforderlich. Jeder Wert oder Ausdruck, der als TRUE oder FALSE ausgewertet werden kann. |
| *logical_test2* | Optional. Zusätzliche Bedingungen, die als TRUE oder FALSE ausgewertet werden sollen. |

## Ungefährer Distinct Count (Dimension)

Gibt den ungefähren Distinct Count für die Elemente der ausgewählten Dimension zurück. Diese Funktion verwendet die HyperLogLog (HLL)-Methode zur ungefähren Bestimmung des Distinct Count. Sie ist entsprechend eingestellt, um zu garantieren, dass der Wert zu 95 % der Zeit 5 % des tatsächlichen Werts beträgt.

```
Approximate Count Distinct (dimension)
```

| Argument |  |
|---|---|
| *Dimension* | Die Dimension, für die Sie den ungefähren Distinct Count für Elemente ermitteln möchten. |

## Beispielanwendungsfall

Ungefährer Distinct Count (Kunden-ID-eVar) ist ein typischer Anwendungsfall für diese Funktion.

Definition für eine neue berechnete „Ungefähre Kunden“-Metrik:

![Ungefähre Definition einer neuen Dimension für das Land, die die Kunden-ID anzeigt (eVar 1)](assets/approx-count-distinct.png)

So könnte die „Ungefähre Kunden“-Metrik für Berichte verwendet werden:

![Freiformtabelle mit Unique Visitors und Ungefähren Kunden ](assets/approx-customers.png)

## Individuelle Werte überschritten

Ebenso wie Count() und RowCount() unterliegt Ungefährer Distinct Count() [„Uniques überschritten“-Beschränkungen](https://experienceleague.adobe.com/docs/analytics/technotes/low-traffic.html?lang=de). Wird für eine Dimension in einem bestimmten Monat die „Uniques überschritten“-Beschränkung erreicht, wird der Wert als 1 Dimensionselement gezählt.

## Vergleich von Count-Funktionen

Ungefährer Distinct Count() ist eine Verbesserung im Vergleich zu Count()- und RowCount()-Funktionen, da die dadurch erstellte Metrik in allen Dimensionsberichten verwendet werden kann, um eine ungefähre Elementanzahl für eine separate Dimension zu rendern. Beispielsweise wird eine Anzahl an Kunden-IDs in einem Bericht zu Mobilgerätetypen verwendet.

Diese Funktion ist etwas weniger genau als Count() und RowCount(), da die HLL-Methode verwendet wird. Bei Count() und RowCount() hingegen handelt es sich um genaue Anzahlen.

## Arkuskosinus (Zeile)

Gibt den Arkuskosinus (oder umgekehrten Kosinus) einer Metrik zurück. Der Arkuskosinus ist der Winkel, dessen Kosinus die Zahl ist. Der zurückgegebene Winkel wird in Radianten im Bereich zwischen 0 (null) und Pi angegeben. Wenn Sie das Ergebnis von Radianten in Grad umrechnen möchten, multiplizieren Sie es mit 180/PI( ).

```
ACOS(metric)
```

| Argument |  |
|---|---|
| *metric* | Der Kosinus des gewünschten Winkels von -1 bis 1. |

## Arkussinus (Zeile)

Gibt den Arkussinus (oder umgekehrten Sinus) einer Zahl zurück. Der Arkussinus ist der Winkel, dessen Sinus die Zahl ist. Der zurückgegebene Winkel wird in Radianten im Bereich zwischen -Pi/2 und Pi/2 angegeben. Um den Arkussinus in Grad auszudrücken, multiplizieren Sie das Ergebnis mit 180/PI( ).

```
ASIN(metric)
```

| Argument |  |
|---|---|
| *metric* | Der Kosinus des gewünschten Winkels von -1 bis 1. |

## Arkustangens (Zeile)

Gibt den Arkustangens (oder umgekehrten Tangens) einer Zahl zurück. Der Arkustangens ist der Winkel, dessen Tangens die Zahl ist. Der zurückgegebene Winkel wird in Radianten im Bereich zwischen -Pi/2 und Pi/2 angegeben. Um den Arkustangens in Grad auszudrücken, multiplizieren Sie das Ergebnis mit 180/PI( ).

```
ATAN(metric)
```

| Argument |  |
|---|---|
| *metric* | Der Kosinus des gewünschten Winkels von -1 bis 1. |

## Exponentielle Regression: Vorhersage für Y (Zeile)

Berechnet die prognostizierten y-Werte (metric_Y) anhand der bekannten x-Werte (metric_X) mittels der Methode der kleinsten Quadrate für die Berechnung der Ausgleichsgeraden basierend auf.

```
ESTIMATE.EXP(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Cdf-T

Gibt den Prozentsatz von Werten in studentischer t-Verteilung mit n Freiheitsgraden zurück, die einen z-Wert unter x aufweisen.

```
cdf_t( -∞, n ) = 0
cdf_t(  ∞, n ) = 1
cdf_t( 3, 5 ) ? 0.99865
cdf_t( -2, 7 ) ? 0.0227501
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

Gibt den Prozentsatz von Werten in einer normalen Verteilung zurück, die einen z-Wert unter x aufweisen.

```
cdf_z( -∞ ) = 0
cdf_z( ∞ ) = 1
cdf_z( 0 ) = 0.5
cdf_z( 2 ) ? 0.97725
cdf_z( -3 ) ? 0.0013499
```

## Nächsthöhere ganze Zahl (Ceiling) (Zeile)

Gibt die kleinste Ganzzahl zurück, die nicht kleiner als ein angegebener Wert ist. Beispiel: Wenn Sie keine Währungsdezimalzahlen für den Umsatz in Berichte aufnehmen möchten und ein Produkt einen Umsatz von 569,34 US-Dollar aufweist, können Sie mit der Formel CEILING(*Revenue*) den Umsatz bis zum nächsten Dollar aufrunden (in diesem Fall 570 US-Dollar).

```
CEILING(metric)
```

| Argument | Beschreibung |
|---|---|
| *metric* | Die Metrik, die gerundet werden soll. |

## Konfidenz

[!UICONTROL Konfidenz] ist ein Maß dafür, wie hoch die Wahrscheinlichkeit ist, dass eine bestimmte Variante mit der Kontrollvariante identisch ist. Bei einer höheren Konfidenz deutet weniger darauf hin, dass die Annahme stimmt, dass die Kontroll- und Nicht-Kontrollvariante die gleiche Performance aufweisen.

```
fx Confidence (normalizing-container, success-metric, control, significance-threshold)
```

| Argument | Beschreibung |
| --- | --- |
| Normalisierungs-Container | Die Grundlage (Personen, Sitzungen oder Ereignisse) für die Ausführung eines Tests. |
| Erfolgskennzahl | Die Kennzahl(en), die ein(e) Benutzende(r) verwendet, um Varianten zu vergleichen. |
| Kontrollvariante | Die Variante, mit der alle anderen Varianten im Experiment verglichen werden. Geben Sie den Namen des Dimensionselements der Kontrollvariante ein. |
| Signifikanzschwelle | Der Schwellenwert in dieser Funktion ist auf den Standardwert 95 % eingestellt. |

{style="table-layout:auto"}

## Kosinus (Zeile)

Gibt den Kosinus des angegebenen Winkels zurück. Wenn der Winkel in Grad vorliegt, multiplizieren Sie ihn mit PI( )/180.

```
COS(metric)
```

| Argument | Beschreibung |
|---|---|
| *metric* | Der Winkel in Radianten, für den Sie den Kosinus ermitteln möchten. |

## Kubikwurzel

Gibt die positive Kubikwurzel einer Zahl zurück. Die Kubikwurzel einer Zahl ist der Wert dieser Zahl hoch 1/3.

```
CBRT(metric)
```

| Argument | Beschreibung |
|---|---|
| *metric* | Die Metrik, für die Sie die Kubikwurzel abrufen möchten. |

## Kumulativ

Gibt die Summe von x für die letzten N Zeilen zurück (angeordnet nach Dimension mit Hashwerten für zeichenfolgenbasierte Felder).

Wenn N &lt;= 0 ist, werden alle vorherigen Zeilen verwendet. Da die Anordnung nach Dimensionen erfolgt, ist dies nur bei Dimensionen mit einer natürlichen Reihenfolge nützlich, wie Datum oder Pfadlänge.

```
| Date | Rev  | cumul(0,Rev) | cumul(2,Rev) |
|------+------+--------------+--------------|
| May  | $500 | $500         | $500         |
| June | $200 | $700         | $700         |
| July | $400 | $1100        | $600         |
```

## Kumulativer Durchschnitt

Gibt den Durchschnitt der letzten N Zeilen zurück.

Wenn N &lt;= 0 ist, werden alle vorherigen Zeilen verwendet. Da die Anordnung nach Dimensionen erfolgt, ist dies nur bei Dimensionen mit einer natürlichen Reihenfolge nützlich, wie Datum oder Pfadlänge.

>[!NOTE]
>
>Mit Quotenmetriken wie Umsatz/Person funktioniert dies nicht so, wie Sie es vielleicht erwarten: Es wird der Quotendurchschnitt ermittelt, anstatt dass der Umsatz über die letzten N summiert und Personen über die letzten N summiert und anschließend geteilt werden. Verwenden Sie stattdessen

```
cumul(revenue)/cumul(person)
```

## Gleich

Gibt Elemente mit einer exakten Entsprechung für numerische oder Zeichenfolgenwerte wieder.

## Exponentielle Regression: Korrelationskoeffizient (Tabelle)

Gibt den Korrelationskoeffizienten *r* zwischen zwei Metrikspalten (*metric_A* und *metric_B*) für die Regressionsgleichung zurück.

```
CORREL.EXP(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Die Metrik, die mit *metric_Y* korreliert werden soll. |
| *metric_Y* | Die Metrik, die mit *metric_X* korreliert werden soll. |

## Exponentielle Regression: Konstante (Tabelle)

Gibt die Konstante *b* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) zurück für

```
INTERCEPT.EXP(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Exponentielle Regression: Steigung (Tabelle)

Gibt die Steigung *a* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) zurück für

```
SLOPE.EXP(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Nächstniedrigere ganze Zahl (Floor) (Zeile)

Gibt die größte Ganzzahl zurück, die nicht größer als ein angegebener Wert ist. Beispiel: Wenn Sie keine Währungsdezimalzahlen für den Umsatz in Berichte aufnehmen möchten und ein Produkt einen Umsatz von 569,34 US-Dollar aufweist, können Sie mit der Formel FLOOR(*Revenue*) den Umsatz bis zum nächsten Dollar abrunden (in diesem Fall 569 US-Dollar).

```
FLOOR(metric)
```

| Argument | Beschreibung |
|---|---|
| *metric* | Die Metrik, die gerundet werden soll. |

## Größer als

Gibt Elemente zurück, deren numerische Anzahl größer als der eingegebene Wert ist.

## Größer gleich

Gibt Elemente zurück, deren numerische Anzahl größer als der eingegebene Wert ist oder damit übereinstimmt.

## Hyperbelkosinus (Zeile)

Gibt den Hyperbelkosinus einer Zahl zurück.

```
COSH(metric)
```

| Argument | Beschreibung |
|---|---|
| *metric* | Der Winkel in Radianten, für den Sie den Hyperbelkosinus ermitteln möchten. |

## Hyperbelsinus (Zeile)

Gibt den Hyperbelsinus einer Zahl zurück.

```
SINH(metric)
```

| Argument | Beschreibung |
|---|---|
| *metric* | Der Winkel in Radianten, für den Sie den Hyperbelsinus ermitteln möchten. |

## Hyperbeltangens (Zeile)

Gibt den Hyperbeltangens einer Zahl zurück.

```
TANH(metric)
```

| Argument | Beschreibung |
|---|---|
| *metric* | Der Winkel in Radianten, für den Sie den Hyperbeltangens ermitteln möchten. |

## IF (Zeile)

Die IF-Funktion gibt einen Wert zurück, wenn eine angegebene Bedingung TRUE ergibt, und einen anderen Wert, wenn diese Bedingung FALSE ergibt.

```
IF(logical_test, [value_if_true], [value_if_false])
```

| Argument | Beschreibung |
|---|---|
| *logical_test* | Erforderlich. Jeder Wert oder Ausdruck, der als TRUE oder FALSE ausgewertet werden kann. |
| *[value_if_true]* | Der Wert, der zurückgegeben soll, wenn das Argument *logical_test* TRUE ergibt. (Für dieses Argument wird standardmäßig 0 verwendet, wenn es nicht angegeben wird.) |
| *[value_if_false]* | Der Wert, der zurückgegeben soll, wenn das Argument *logical_test* FALSE ergibt. (Für dieses Argument wird standardmäßig 0 verwendet, wenn es nicht angegeben wird.) |

## Kleiner als

Gibt Elemente zurück, deren numerische Anzahl kleiner als der eingegebene Wert ist.

## Kleiner gleich

Gibt Elemente zurück, deren numerische Anzahl kleiner als der eingegebene Wert ist oder damit übereinstimmt.

## Anstieg

Gibt den Anstieg zurück, den eine bestimmte Variante bei Konversionen gegenüber einer Kontrollvariante verzeichnete. Dies ist der Performance-Unterschied zwischen einer bestimmten Variante und der Baseline, geteilt durch die Performance der Baseline und ausgedrückt in Prozent.

```
fx Lift (normalizing-container, success-metric, control)
```

| Argument | Beschreibung |
| --- | --- |
| Normalisierungs-Container | Die Grundlage (Personen, Sitzungen oder Ereignisse) für die Ausführung eines Tests. |
| Erfolgskennzahl | Die Kennzahl(en), die ein(e) Benutzende(r) verwendet, um Varianten zu vergleichen. |
| Kontrollvariante | Die Variante, mit der alle anderen Varianten im Experiment verglichen werden. Geben Sie den Namen des Dimensionselements der Kontrollvariante ein. |

{style="table-layout:auto"}

## Lineare Regression: Korrelationskoeffizient

Y = a X + b. Gibt den Korrelationskoeffizienten zurück.

## Lineare Regression: Konstante

Y = a X + b. Gibt b zurück.

## Lineare Regression: Vorhersage für Y

Y = a X + b. Gibt Y zurück.

## Lineare Regression: Steigung

Y = a X + b. Gibt a zurück.

## Logarithmus zur Basis 10 (Zeile)

Gibt den Logarithmus zur Basis 10 einer Zahl zurück.

```
LOG10(metric)
```

| Argument | Beschreibung |
|---|---|
| *metric* | Die positive reale Zahl, dessen Logarithmus zur Basis 10 gewünscht ist. |

## Logistische Regression: Korrelationskoeffizient (Tabelle)

Gibt den Korrelationskoeffizienten *r* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für die Regressionsgleichung [!DNL Y = a ln(X) + b] zurück. Dies wird mit der Gleichung CORREL berechnet.

```
CORREL.LOG(metric_X,metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Die Metrik, die mit *metric_Y* korreliert werden soll. |
| *metric_Y* | Die Metrik, die mit *metric_X* korreliert werden soll. |

## Logistische Regression: Konstante (Tabelle)

Gibt die Konstante *b* als die Regression der kleinsten Quadrate zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für die Regressionsgleichung [!DNL Y = a ln(X) + b] zurück. Dies wird mit der Gleichung INTERCEPT berechnet.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Logistische Regression: Vorhersage für Y (Zeile)

Berechnet die prognostizierten [!DNL y]-Werte (metric_Y) anhand der bekannten [!DNL x]-Werte (metric_X) mittels der Methode der kleinsten Quadrate für die Berechnung der Ausgleichsgeraden mit [!DNL Y = a ln(X) + b]. Dies wird mit der Gleichung ESTIMATE berechnet.

In der Regressionsanalyse berechnet diese Funktion die prognostizierten [!DNL y]-Werte (*metric_Y*) anhand der bekannten [!DNL x]-Werte (*metric_X*) mithilfe des Logarithmus zur Berechnung der Ausgleichsgraden für die Regressionsgleichung [!DNL Y = a ln(X) + b]. Die [!DNL a]-Werte entsprechen den jeweiligen x-Werten und [!DNL b] ist eine Konstante.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Logistische Regression: Steigung (Tabelle)

Gibt die Steigung *a* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für die Regressionsgleichung [!DNL Y = a ln(X) + b] zurück. Dies wird mit der Gleichung SLOPE berechnet.

```
SLOPE.LOG(metric_A, metric_B)
```

| Argument | Beschreibung |
|---|---|
| *metric_A* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_B* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Natürlicher Logarithmus

Gibt den natürlichen Logarithmus einer Zahl zurück. Natürliche Logarithmen basieren auf der Konstante *e* (2,71828182845904). LN ist die Umkehrung der Exponentialfunktion.

```
LN(metric)
```

| Argument | Beschreibung |
|---|---|
| *metric* | Die positive reale Zahl, deren natürlicher Logarithmus gewünscht ist. |

## NOT

Gibt 1 zurück, wenn die Zahl 0 ist, oder gibt 0 zurück, wenn es eine andere Zahl ist.

```
NOT(logical)
```

| Argument | Beschreibung |
|---|---|
| *logisch* | Erforderlich. Ein Wert oder Ausdruck, der als TRUE oder FALSE ausgewertet werden kann. |

Bei Verwendung von NOT müssen Sie wissen, ob die Ausdrücke (&lt;, >, =, &lt;> usw.) 0- oder 1-Werte zurückgeben.

## Ungleich

Gibt alle Elemente zurück, die keine exakte Übereinstimmung mit dem eingegebenen Wert enthalten.

## Oder (Zeile)

Gibt TRUE zurück, wenn ein Argument TRUE ist, oder FALSE, wenn alle Argumente FALSE sind.

>[!NOTE]
>
>0 (null) bedeutet „Falsch“ und jeder andere Wert „Wahr“.

```
OR(logical_test1,[logical_test2],...)
```

| Argument | Beschreibung |
|---|---|
| *logical_test1* | Erforderlich. Jeder Wert oder Ausdruck, der als TRUE oder FALSE ausgewertet werden kann. |
| *logical_test2* | Optional. Zusätzliche Bedingungen, die als TRUE oder FALSE ausgewertet werden sollen. |

## Pi

Gibt die Konstante PI (3,14159265358979) mit 15 Stellen zurück.

```
PI()
```

Die Funktion [!DNL PI] weist keine Argumente auf.

## Potenzregression: Korrelationskoeffizient (Tabelle)

Gibt den Korrelationskoeffizienten *r* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für [!DNL Y = b*X] zurück.

```
CORREL.POWER(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Die Metrik, die mit *metric_Y* korreliert werden soll. |
| *metric_Y* | Die Metrik, die mit *metric_X* korreliert werden soll. |

## Potenzregression: Konstante (Tabelle)

Gibt die Konstante *b* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für [!DNL Y = b*X] zurück.

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Potenzregression: Vorhersage für Y (Zeile)

Berechnet die prognostizierten [!DNL y]-Werte ([!DNL metric_Y]) anhand der bekannten [!DNL x]-Werte ([!DNL metric_X]) mittels der Methode der kleinsten Quadrate für die Berechnung der Ausgleichsgeraden für [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Potenzregression: Steigung (Tabelle)

Gibt die Steigung *a* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für [!DNL Y = b*X] a zurück.

```
SLOPE.POWER(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Quadratische Regression: Korrelationskoeffizient (Tabelle)

Gibt den Korrelationskoeffizienten *r* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für [!DNL Y=(a*X+b)]**** zurück.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Die Metrik, die mit *metric_Y* korreliert werden soll. |
| *metric_Y* | Die Metrik, die mit *metric_X* korreliert werden soll. |

## Quadratische Regression: Konstante (Tabelle)

Gibt die Konstante *b* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für [!DNL Y=(a*X+b)]**** zurück.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Quadratische Regression: Vorhersage für Y (Zeile)

Berechnet die prognostizierten [!DNL y]-Werte (metric_Y) anhand der bekannten [!DNL x]-Werte (metric_X) mittels der Methode der kleinsten Quadrate für die Berechnung der Ausgleichsgeraden mit [!DNL Y=(a*X+b)]****.

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

| Argument | Beschreibung |
|---|---|
| *metric_A* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_B* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |

## Quadratische Regression: Steigung (Tabelle)

Gibt die Steigung *a* zwischen zwei Metrikspalten (*metric_X* und metric_Y) für [!DNL Y=(a*X+b)]**** zurück.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Reziproke Regression: Korrelationskoeffizient (Tabelle)

Gibt den Korrelationskoeffizienten *r* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für [!DNL Y = a/X+b] zurück.

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Die Metrik, die mit *metric_Y* korreliert werden soll. |
| *metric_Y* | Die Metrik, die mit *metric_X* korreliert werden soll. |

## Reziproke Regression: Konstante (Tabelle)

Gibt die Konstante *b* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für [!DNL Y = a/X+b] zurück.

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Reziproke Regression: Vorhersage für Y (Zeile)

Berechnet die prognostizierten [!DNL y]-Werte (metric_Y) anhand der bekannten [!DNL x]-Werte (metric_X) mittels der Methode der kleinsten Quadrate für die Berechnung der Ausgleichsgeraden mit [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Reziproke Regression: Steigung (Tabelle)

Gibt die Steigung *a* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für [!DNL Y = a/X+b] a zurück.

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Sinus (Zeile)

Gibt den Sinus des angegebenen Winkels zurück. Wenn der Winkel in Grad vorliegt, multiplizieren Sie ihn mit PI( )/180.

```
SIN(metric)
```

| Argument | Beschreibung |
|---|---|
| *metric* | Der Winkel in Radianten, für den Sie den Sinus ermitteln möchten. |

## t-Transformation

Alias für z-Transformation, also die Abweichung vom arithmetischen Mittel geteilt durch die Standardabweichung.

## t-Test

Führt einen m-seitigen t-Test mit einem t-Wert von Spalte und n Freiheitsgraden durch.

Die Signatur lautet `t_test( x, n, m )`. Darunter wird einfach `m*cdf_t(-abs(x),n)` aufgerufen. (Dies entspricht der z-Test-Funktion, die wie folgt lautet `m*cdf_z(-abs(x))`.

Hier gibt `m` die Anzahl der Seiten und `n` die Freiheitsgrade an. Hierbei sollte es sich um Ziffern handeln (im gesamten Bericht konstant, d. h. die Werte sollten nicht von Zeile zu Zeile variieren).

`X` ist die t-Test-Statistik. Hierbei handelt es sich häufig um eine auf einer Metrik basierende Formel (z. B. z-Wert), die in jeder Zeile bewertet wird.

Der Rückgabewert ist die Wahrscheinlichkeit, die Teststatistik x zu erhalten, bei gegebenen Freiheitsgraden und der Anzahl an Seiten.

**Beispiele:**

1. Verwenden Sie ihn zum Auffinden von Ausreißern:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Kombinieren Sie ihn mit `if`, um sehr hohe oder niedrige Absprungraten zu ignorieren und alle weiteren Besuche zu zählen:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangens

Gibt den Tangens des angegebenen Winkels zurück. Wenn der Winkel in Grad vorliegt, multiplizieren Sie ihn mit PI( )/180.

```
TAN (metric)
```

| Argument | Beschreibung |
|---|---|
| *metric* | Der Winkel in Radianten, für den Sie den Tangens ermitteln möchten. |

## z-Transformation (Zeile)

Gibt die z-Transformation oder Normaltransformation basierend auf einer normalen Verteilung zurück. Die z-Transformation ist die Anzahl der Standardabweichungen, die eine Beobachtung vom arithmetischen Mittel darstellt. Eine z-Transformation von 0 (null) gibt an, dass die Transformation mit dem arithmetischen Mittel identisch ist. Eine z-Transformation kann positiv oder negativ sein, abhängig davon, ob sie über oder unter dem arithmetischen Mittel liegt und um wie viele Standardabweichungen es sich handelt.

Die Gleichung für z-Transformation lautet:

![](assets/z_score.png)

wobei [!DNL x] der Rohwert, [!DNL μ] das arithmetische Mittel der Population und [!DNL σ] die Standardabweichung der Population ist.

>[!NOTE]
>
>[!DNL μ] (Mu) und [!DNL σ] (Sigma) werden automatisch aus der Metrik berechnet.

z-Transformation (Metrik)

<table id="table_AEA3622A58F54EA495468A9402651E1B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Argument </th>
   <th colname="col2" class="entry"> Beschreibung </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <i>metric</i> </td>
   <td colname="col2"> <p> Gibt den Wert des ersten Arguments ungleich null zurück. </p> </td>
  </tr>
 </tbody>
</table>

## z-Test

Führt einen n-seitigen z-Test mit einem z-Wert von A durch.

Gibt zurück, wie wahrscheinlich es ist, dass die aktuelle Zeile zufällig in der Spalte gesehen wird.

>[!NOTE]
>
>Dabei wird von einer Normalverteilung der Werte ausgegangen.
