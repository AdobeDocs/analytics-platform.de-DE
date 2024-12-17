---
title: Erweiterte Funktionen
description: Greifen Sie auf diese Funktionen zu, indem Sie in der Dropdown-Liste „Funktionen“ die Option „Erweitert anzeigen“ auswählen.
feature: Calculated Metrics
exl-id: 3689a499-817d-4a59-8a1f-5f7bda297268
role: User
source-git-commit: 1804f3dc4126007c1ff553f844d691c80623bb90
workflow-type: tm+mt
source-wordcount: '4438'
ht-degree: 29%

---

# Erweiterte Funktionen

Mit dem [Generator für berechnete Metriken](cm-workflow/cm-build-metrics.md) können Sie statistische und mathematische Funktionen anwenden. Dieser Artikel dokumentiert eine alphabetische Liste der erweiterten Funktionen und ihrer Definitionen.

Greifen Sie auf diese Funktionen zu, indem **[!UICONTROL Alle anzeigen]** unter ![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL Funktionen]** im Bedienfeld „Komponenten“ auswählen. Scrollen Sie nach unten, um die Liste der **[!UICONTROL Erweiterten Funktionen]** anzuzeigen.

## Vergleich zwischen Tabellenfunktionen und Zeilenfunktionen

Bei einer Tabellenfunktion ist die Ausgabe für jede Tabellenzeile gleich. Bei einer Zeilenfunktion ist die Ausgabe für jede Tabellenzeile unterschiedlich.

Gegebenenfalls wird einer Funktion eine Anmerkung mit dem Typ der Funktion hinzugefügt: [!BADGE Tabelle]{type="Neutral"}[!BADGE Zeile]{type="Neutral"}

## Was bedeutet der Parameter „include-zeros“? 

Damit wird angegeben, ob Nullen in die Berechnung einbezogen werden sollen. In manchen Fällen bedeutet eine Null *nichts*, in anderen Fällen kann sie aber auch wichtig sein.

Beispiel: Wenn Sie mit einer Umsatzmetrik arbeiten und dem Bericht dann eine Seitenansichtsmetrik hinzufügen, gibt es plötzlich mehr Zeilen für den Umsatz, die alle Nullwerte enthalten. Sie möchten wahrscheinlich nicht, dass sich diese zusätzliche Metrik auf Berechnungen wie **[ARITHMETISCHES MITTEL](cm-functions.md#mean)**, **[ZEILENMINIMUM](cm-functions.md#row-min)**, **[QUARTIL](cm-functions.md#quartile)** usw. auswirkt, die sich in der Umsatzspalte befinden. In diesem Fall müssen Sie den Parameter `include-zeros` aktivieren.

Ein alternatives Szenario besteht darin, dass Sie zwei Metriken von Interesse haben und eine Metrik einen höheren Durchschnitt oder ein höheres Minimum aufweist, da einige der Zeilen Nullen sind.   In diesem Fall können Sie festlegen, dass der Parameter keine Nullen enthält.


## Und {#and}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_and"
>title="Und"
>abstract="Verbindung. Wenn ungleich null ist, gilt dies als „true“ und wenn gleich null ist, wird dies als „false“ betrachtet. Die Ausgabe ist entweder 0 (false) oder 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL AND(logical_test)]**

Verbindung. Wenn ungleich null ist, gilt dies als „true“ und wenn gleich null ist, wird dies als „false“ betrachtet. Die Ausgabe ist entweder 0 (false) oder 1 (true).

| Argument | Beschreibung |
|---|---|
| Logical_test | Erfordert mindestens einen Parameter, kann jedoch eine beliebige Anzahl Parameter annehmen. Jeder Wert oder Ausdruck, der als TRUE oder FALSE ausgewertet werden kann |


## Ungefähres Erfassen bestimmter {#approximate_count_distinct}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_approximate_count_distinct"
>title="Ungefähres Erfassen bestimmter"
>abstract="Gibt die ungefähre Anzahl von Dimensionselementen für die ausgewählte Dimension zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL ANNÄHERNDE ANZAHL DISTINCT(Dimension)]**


Gibt die ungefähre Anzahl von Dimensionselementen für die ausgewählte Dimension zurück.


| Argument | Beschreibung |
|---|---|
| Dimension | Die Dimension, für die Sie die ungefähre Anzahl der einzelnen Elemente berechnen möchten |

### Beispiel

Ein gängiger Anwendungsfall für diese Funktion ist, wenn Sie eine ungefähre Anzahl von Kunden erhalten möchten.



## Arkuskosinus {#arc-cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_arc_cosine"
>title="Arkuskosinus"
>abstract="Gibt den Arkuskosinus (oder umgekehrten Kosinus) einer Metrik zurück. Der Arkuskosinus ist der Winkel, dessen Kosinus die Zahl ist. Der zurückgegebene Winkel wird in Radianten im Bereich zwischen 0 (null) und Pi angegeben. Wenn Sie das Ergebnis von Radiant in Grad umrechnen möchten, multiplizieren Sie es mit 180/PI()."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL BOGEN KOSINUS(metrisch)]**


[!BADGE Zeile]{type="Neutral"}


| Argument | Beschreibung |
|---|---|
| metric | Der Kosinus des gewünschten Winkels von -1 bis 1 |



## Kreisbogensinus {#arc-sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_arc_sine"
>title="Kreisbogensinus"
>abstract="Gibt den Arkussinus (oder umgekehrten Sinus) einer Zahl zurück. Der Arkussinus ist der Winkel, dessen Sinus eine Zahl ist. Der zurückgegebene Winkel wird in Radianten im Bereich zwischen -Pi/2 und Pi/2 angegeben. Um den Arkussinus in Grad auszudrücken, multiplizieren Sie das Ergebnis mit 180/PI()"

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL BOGEN SINUS(metrisch)]**


[!BADGE Zeile]{type="Neutral"}


| Argument | Beschreibung |
|---|---|
| metric | Der Sinus des gewünschten Winkels von -1 bis 1 |



## Arkustangens {#arc-tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_arc_tangent"
>title="Arkustangens"
>abstract="Gibt den Arkustangens (oder umgekehrten Tangens) einer Zahl zurück. Der Bogen ist der Winkel, dessen Tangente eine Zahl ist. Der zurückgegebene Winkel wird in Radianten im Bereich zwischen -Pi/2 und Pi/2 angegeben. Um den Arktangens in Grad auszudrücken, multiplizieren Sie das Ergebnis mit 180/PI()."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL BOGENTANGENTE(metrisch)]**


[!BADGE Zeile]{type="Neutral"}


| Argument | Beschreibung |
|---|---|
| metric | Der Tangens des gewünschten Winkels von -1 bis 1 |



## Cdf-T {#cdf-t}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_cdf_t"
>title="Cdf-T"
>abstract="Gibt die Wahrscheinlichkeit dafür zurück, dass eine Zufallsvariable mit studentischer t-Verteilung mit n Freiheitsgraden einen z-Wert hat, der unter dem Spaltenwert liegt."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-T(Metrik, Zahl)]**

Gibt die Wahrscheinlichkeit dafür zurück, dass eine Zufallsvariable mit studentischer t-Verteilung mit n Freiheitsgraden einen z-Wert hat, der unter dem Spaltenwert liegt.

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die die Kumulative Verteilungsfunktion der studentischen t-Verteilung angezeigt werden soll |
| number | Die Freiheitsgrade für die Kumulative Verteilungsfunktion der studentischen t-Verteilung |

### Beispiel

```
CDF-T(-∞, n) = 0
CDF-T(∞, n) = 1
CDF-T(3, 5) ? 0.99865
CDF-T(-2, 7) ? 0.0227501
CDF-T(x, ∞) ? cdf_z(x)
```


## Cdf-Z {#cdf-z}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_cdf_z"
>title="Cdf-Z"
>abstract="Gibt die Wahrscheinlichkeit dafür zurück, dass eine Zufallsvariable normaler Verteilung einen z-Wert hat, der unter dem Spaltenwert liegt."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-Z(Metrik, Zahl)]**

Gibt die Wahrscheinlichkeit dafür zurück, dass eine Zufallsvariable normaler Verteilung einen z-Wert hat, der unter dem Spaltenwert liegt.

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die die Kumulative Verteilungsfunktion der Standardnormalverteilung verwendet werden soll |

### Beispiele

```
CDF-Z(-∞) = 0
CDF-Z(∞) = 1
CDF-Z(0) = 0.5
CDF-Z(2) ? 0.97725
CDF-Z(-3) ? 0.0013499
```

## Ceiling (Obergrenze) {#ceiling}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_ceiling"
>title="Ceiling (Obergrenze)"
>abstract="Gibt die kleinste Ganzzahl zurück, die nicht kleiner als ein angegebener Wert ist. Beispiel: Wenn Sie keine Währungsdezimalzahlen für den Umsatz in Berichte aufnehmen möchten und ein Produkt einen Umsatz von 569,34 US-Dollar aufweist, können Sie mit der Formel CEILING(Umsatz) den Umsatz bis zum nächsten Dollar aufrunden (in diesem Fall 570 US-Dollar)."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CEILING(metrisch)]**

[!BADGE Zeile]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, die Sie runden möchten |


## Konfidenz {#confidence}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_confidence"
>title="Konfidenz"
>abstract="Berechnen Sie die jederzeit gültige Konfidenz mithilfe der WASKR-Methode, wie in [Zeiteinheitliche zentrale Grenztheorie und asymptotische Konfidenzsequenzen](https://arxiv.org/pdf/2103.06476) beschrieben."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg)**[!UICONTROL KONFIDENZ(Normalisierungs-Container, Erfolgsmetrik, Kontrolle, Signifikanz-Schwellenwert)]**

Berechnen Sie die jederzeit gültige Konfidenz mithilfe der WASKR-Methode, wie in [Zeiteinheitliche zentrale Grenztheorie und asymptotische Konfidenzsequenzen](https://arxiv.org/pdf/2103.06476) beschrieben.

Konfidenz ist ein Maß dafür, wie hoch die Wahrscheinlichkeit ist, dass eine bestimmte Variante mit der Kontrollvariante identisch ist. Bei einer höheren Konfidenz deutet weniger darauf hin, dass die Annahme stimmt, dass die Kontroll- und Nicht-Kontrollvariante die gleiche Performance aufweisen.

| Argument | Beschreibung |
| --- | --- |
| Normalisierungs-Container | Die Grundlage (Personen, Sitzungen oder Ereignisse) für die Ausführung eines Tests. |
| Erfolgsmetrik | Die Kennzahl(en), die ein(e) Benutzende(r) verwendet, um Varianten zu vergleichen. |
| Kontrolle | Die Variante, mit der alle anderen Varianten im Experiment verglichen werden. Geben Sie den Namen des Dimensionselements der Kontrollvariante ein. |
| Signifikanzschwelle | Der Schwellenwert in dieser Funktion ist auf den Standardwert 95 % eingestellt. |


## Konfidenz (untere Grenze) {#confidence-lower}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_confidence_lower"
>title="Konfidenz (untere Grenze)"
>abstract="Berechnen Sie die jederzeit gültige Konfidenz **niedriger** mithilfe der WASKR-Methode, wie in [Zeiteinheitliche zentrale Grenztheorie und asymptotische Konfidenzsequenzen](https://arxiv.org/pdf/2103.06476) beschrieben."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg)**[!UICONTROL KONFIDENZ(Normalisierungs-Container, Erfolgsmetrik, Kontrolle, Signifikanz-Schwellenwert)]**

Berechnen Sie die jederzeit gültige Konfidenz **niedriger** mithilfe der WASKR-Methode, wie in [Zeiteinheitliche zentrale Grenztheorie und asymptotische Konfidenzsequenzen](https://arxiv.org/pdf/2103.06476) beschrieben.

Konfidenz ist ein Maß dafür, wie hoch die Wahrscheinlichkeit ist, dass eine bestimmte Variante mit der Kontrollvariante identisch ist. Bei einer höheren Konfidenz deutet weniger darauf hin, dass die Annahme stimmt, dass die Kontroll- und Nicht-Kontrollvariante die gleiche Performance aufweisen.

| Argument | Beschreibung |
| --- | --- |
| Normalisierungs-Container | Die Grundlage (Personen, Sitzungen oder Ereignisse) für die Ausführung eines Tests. |
| Erfolgsmetrik | Die Kennzahl(en), die ein(e) Benutzende(r) verwendet, um Varianten zu vergleichen. |
| Kontrolle | Die Variante, mit der alle anderen Varianten im Experiment verglichen werden. Geben Sie den Namen des Dimensionselements der Kontrollvariante ein. |
| Signifikanzschwelle | Der Schwellenwert in dieser Funktion ist auf den Standardwert 95 % eingestellt. |

## Konfidenz (obere Grenze) {#confidence-upper}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_confidence_upper"
>title="Konfidenz (obere Grenze)"
>abstract="Berechnen Sie die jederzeit gültige Konfidenz **upper** mithilfe der WASKR-Methode, wie in [Zeiteinheitliche zentrale Grenztheorie und asymptotische Konfidenzsequenzen](https://arxiv.org/pdf/2103.06476) beschrieben."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg)**[!UICONTROL KONFIDENZ(Normalisierungs-Container, Erfolgsmetrik, Kontrolle, Signifikanz-Schwellenwert)]**

Berechnen Sie die jederzeit gültige Konfidenz **upper** mithilfe der WASKR-Methode, wie in [Zeiteinheitliche zentrale Grenztheorie und asymptotische Konfidenzsequenzen](https://arxiv.org/pdf/2103.06476) beschrieben.

Konfidenz ist ein Maß dafür, wie hoch die Wahrscheinlichkeit ist, dass eine bestimmte Variante mit der Kontrollvariante identisch ist. Bei einer höheren Konfidenz deutet weniger darauf hin, dass die Annahme stimmt, dass die Kontroll- und Nicht-Kontrollvariante die gleiche Performance aufweisen.

| Argument | Beschreibung |
| --- | --- |
| Normalisierungs-Container | Die Grundlage (Personen, Sitzungen oder Ereignisse) für die Ausführung eines Tests. |
| Erfolgsmetrik | Die Kennzahl(en), die ein(e) Benutzende(r) verwendet, um Varianten zu vergleichen. |
| Kontrolle | Die Variante, mit der alle anderen Varianten im Experiment verglichen werden. Geben Sie den Namen des Dimensionselements der Kontrollvariante ein. |
| Signifikanzschwelle | Der Schwellenwert in dieser Funktion ist auf den Standardwert 95 % eingestellt. |


## Kosinus {#cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_cosine"
>title="Kosinus"
>abstract="Gibt den Kosinus des angegebenen Winkels zurück. Wenn der Winkel in Grad angegeben ist, multiplizieren Sie den Winkel mit PI()/180."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL KOSINUS(metrisch)]**

[!BADGE Zeile]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric | Der Winkel im Bogenmaß, für den der Kosinus verwendet werden soll |


## Kubikwurzel {#cube-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_cube_root"
>title="Kubikwurzel"
>abstract="Gibt die positive Kubikwurzel einer Zahl zurück. Die Kubikwurzel einer Zahl ist der Wert dieser Zahl hoch 1/3."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CUBE ROOT(metric)]**


Gibt die positive Kubikwurzel einer Zahl zurück. Die Kubikwurzel einer Zahl ist der Wert dieser Zahl hoch 1/3.


| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die Sie die Kubikwurzel berechnen möchten |



## Kumulativ {#cumulative}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_cumulative"
>title="Kumulativ"
>abstract="Gibt die Summe der letzten n Elemente der Spalte x zurück. Wenn n > 0 ist, werden die letzten n Elemente oder x addiert. Wenn n &lt; 0 ist, werden die vorangehenden Elemente addiert."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE(number, metric)]**

Gibt die Summe der letzten n Elemente der Spalte x zurück. Wenn n > 0 ist, werden die letzten n Elemente oder x addiert. Wenn n &lt; 0 ist, werden die vorangehenden Elemente addiert.

| Argument | Beschreibung |
| --- | --- |
| number | Die letzte Anzahl N von Zeilen, für die die Summe zurückgegeben werden soll. Wenn N &lt;= 0 ist, werden alle vorherigen Zeilen verwendet. |
| metric | Die Metrik, für die die kumulative Summe angezeigt werden soll. |

### Beispiele

| Datum | Umsatz | KUMULATIV(0, Umsatz) | KUMULATIV(2, Einnahmen) |
|------|------:|--------------:|--------------:|
| Mai | 500 $ | 500 $ | 500 $ |
| Juni | 200 $ | 700 $ | 700 $ |
| Juli | 400$ | 1 100 $ | 600 $ |


## Kumulativ (Durchschnitt) {#cumulative-average}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_cumulative_average"
>title="Kumulativ (Durchschnitt)"
>abstract="Gibt den Durchschnitt der letzten n Elemente der Spalte x zurück. Wenn n > 0 ist, werden die letzten n Elemente oder x addiert. Wenn n &lt; 0 ist, werden die vorangehenden Elemente addiert."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL KUMULATIVER DURCHSCHNITT(Zahl, Metrik)]**

Gibt den Durchschnitt der letzten n Elemente der Spalte x zurück. Wenn n > 0 ist, werden die letzten n Elemente oder x addiert. Wenn n &lt; 0 ist, werden die vorangehenden Elemente addiert.

| Argument | Beschreibung |
| --- | --- |
| number | Die letzte Anzahl N von Zeilen, für die der Durchschnitt zurückgegeben wird. Wenn N &lt;= 0 ist, werden alle vorherigen Zeilen verwendet. |
| metric | Die Metrik, für die der kumulative Durchschnitt angezeigt werden soll. |

>[!NOTE]
>
>Diese Funktion funktioniert nicht mit Tarifmetriken wie Umsatz pro Person. Die Funktion ermittelt den Durchschnitt der Sätze, anstatt den Umsatz der letzten N zu summieren und die Personen der letzten N zu summieren und dann zu teilen. <br/>Verwenden Sie stattdessen [**[!UICONTROL CUMULATIVE(Revenue)]**](#cumulative) ![Divide](/help/assets/icons/Divide.svg) [**[!UICONTROL CUMULATIVE(person)]**](#cumulative).
>


## Gleich {#equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_equal"
>title="Gleich"
>abstract="Gleich. Die Ausgabe ist entweder 0 (false) oder 1 (true)."

<!-- markdownlint-enable MD034 -->

![EFFECT](/help/assets/icons/Effect.svg) **[!UICONTROL EQUAL()]**

Gleich. Die Ausgabe ist entweder 0 (false) oder 1 (true).


| Argument | Beschreibung |
|---|---|
| metric_X | |
| metric_Y | |

### Beispiel

`Metric 1 = Metric 2`


## Exponentielle Regression: Korrelationskoeffizient {#exponential-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_exponential_regression_correlation_coefficient"
>title="Exponentielle Regression: Korrelationskoeffizient"
>abstract="Exponentielle Regression: Y = a exp(X) + b. Gibt den Korrelationskoeffizienten zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIELLE REGRESSION: KORRELATIONSKOEFFIZIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabelle]{type="Neutral"}


| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die Sie mit metric_Y korrelieren möchten |
| metric_Y | Eine Metrik, die Sie mit metric_X korrelieren möchten |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |

## Exponentielle Regression: Prognostiziert Y {#exponential-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_exponential_regression_predicted_y"
>title="Exponentielle Regression: Prognostiziert Y"
>abstract="Exponentielle Regression: Y = a exp(X) + b. Gibt Y zurück."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zero)]**


[!BADGE Zeile]{type="Neutral"}


| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |
| metric_Y | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |


## Exponentielle Regression: Intercept {#exponential-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_exponential_regression_intercept"
>title="Exponentielle Regression: Intercept"
>abstract="Exponentielle Regression: Y = a exp(X) + b. Gibt b zurück."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: INTERCEPT(metric_X, metric_Y, include_zero)]**


[!BADGE Tabelle]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, der abhängige Daten zugewiesen werden sollen |
| metric_Y | Eine Metrik, die als unabhängige Daten gekennzeichnet werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |


## Exponentielle Regression: Steigung {#exponential-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_exponential_regression_slope"
>title="Exponentielle Regression: Steigung"
>abstract="Exponentielle Regression: Y = a exp(X) + b. Gibt a zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIELLE REGRESSION: SLOPE(metric_X, metric_Y, include_zero)]**


[!BADGE Tabelle]{type="Neutral"}


| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, der abhängige Daten zugewiesen werden sollen |
| metric_Y | Eine Metrik, die als unabhängige Daten gekennzeichnet werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |


## Untergrenze {#floor}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_floor"
>title="Untergrenze"
>abstract="Gibt die größte Ganzzahl zurück, die nicht größer als ein angegebener Wert ist. Beispiel: Wenn Sie keine Währungsdezimalzahlen für den Umsatz in Berichte aufnehmen möchten und ein Produkt einen Umsatz von 569,34 US-Dollar aufweist, können Sie mit der Formel FLOOR(Umsatz) den Umsatz bis zum nächsten Dollar abrunden (in diesem Fall 569 US-Dollar)."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL FLOOR(metric_X, metric_Y, include_zero)]**

[!BADGE Zeile]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, die gerundet werden soll. |


## Größer als {#greather-than}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_greater_than"
>title="Größer als"
>abstract="Die Ausgabe ist entweder 0 (false) oder 1 (true)."

<!-- markdownlint-enable MD034 -->

![EFFECT](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER THAN()]**

Die Ausgabe ist entweder 0 (false) oder 1 (true).

| Argument | Beschreibung |
|---|---|
| metric_X | |
| metric_Y | |

### Beispiel

`Metric 1 > Metric 2`


## Größer gleich {#greater-than-or-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_greater_than_or_equal"
>title="Größer gleich"
>abstract="Größer als oder gleich. Die Ausgabe ist entweder 0 (false) oder 1 (true)."

<!-- markdownlint-enable MD034 -->

![EFFECT](/help/assets/icons/Effect.svg) **[!UICONTROL GRÖSSER ODER GLEICH()]**

Größer als oder gleich. Die Ausgabe ist entweder 0 (false) oder 1 (true).

| Argument | Beschreibung |
|---|---|
| metric_X |  |
| metric_Y |  |

### Beispiel

`Metric 1 >= Metric 2`



## Kosinus hyperbolicus {#hyperbolic-cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_hyperbolic_cosine"
>title="Kosinus hyperbolicus"
>abstract="Gibt den Hyperbelkosinus einer Zahl zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLISCHER KOSINUS(metrisch)]**


[!BADGE Zeile]{type="Neutral"}


| Argument | Beschreibung |
|---|---|
| metric | Der Winkel im Bogenmaß, für den Sie den hyperbolischen Kosinus finden möchten |



## Sinus hyperbolicus {#hyperbolic-sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_hyperbolic_sine"
>title="Sinus hyperbolicus"
>abstract="Gibt den Hyperbelsinus einer Zahl zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLISCHER SINUS(metrisch)]**

[!BADGE Zeile]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric | Der Winkel im Bogenmaß, für den der hyperbolische Sinus gefunden werden soll |


## Tangente Hyperbolicus {#hyperbolic-tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_hyperbolic_tangent"
>title="Tangente Hyperbolicus"
>abstract="Gibt den Hyperbeltangens einer Zahl zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLISCHER TANGENS(metrisch)]**

[!BADGE Zeile]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric | Der Winkel im Bogenmaß, für den die hyperbolische Tangente gefunden werden soll |


## Wenn {#if}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_if"
>title="Wenn"
>abstract="Wenn der Wert des Bedingungsparameters ungleich null (true) ist, ist das Ergebnis der Wert des Parameters value_if_true. Andernfalls ist dies der Wert des Parameters value_if_false."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL IF(logical_test, value_if_true, value_if_false)]**


[!BADGE Zeile]{type="Neutral"}


| Argument | Beschreibung |
|---|---|
| Logical_test | Erforderlich. Jeder Wert oder Ausdruck, der als TRUE oder FALSE ausgewertet werden kann |
| value_if_true | Der Wert, der ausgegeben werden soll, wenn das Argument des Logiktests also TRUE ausgewertet wird. (Dieses Argument wird automatisch auf 0 gesetzt, wenn es nicht eingesetzt wurde.) |
| value_if_false | Der Wert, der ausgegeben werden soll, wenn das logical_test-Argument als FALSE ausgewertet wird. (Dieses Argument wird automatisch auf 0 gesetzt, wenn es nicht eingesetzt wurde.) |


## Kleiner als {#less-than}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_less_than"
>title="Kleiner als"
>abstract="Die Ausgabe ist entweder 0 (false) oder 1 (true)."

<!-- markdownlint-enable MD034 -->

![EFFECT](/help/assets/icons/Effect.svg) **[!UICONTROL LESS THAN()]**

Die Ausgabe ist entweder 0 (false) oder 1 (true).

| Argument | Beschreibung |
|---|---|
| metric_X | |
| metric_Y | |

### Beispiel

`Metric 1 < Metric 2`


## Kleiner gleich {#less-than-or-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_less_than_or_equal"
>title="Kleiner gleich"
>abstract="Kleiner oder gleich. Die Ausgabe ist entweder 0 (false) oder 1 (true)."

<!-- markdownlint-enable MD034 -->

![EFFECT](/help/assets/icons/Effect.svg) **[!UICONTROL LESS THAN OR EQUAL()]**

Kleiner oder gleich. Die Ausgabe ist entweder 0 (false) oder 1 (true).

| Argument | Beschreibung |
|---|---|
| metric_X | |
| metric_Y | |

### Beispiel

`Metric 1 <= Metric 2`



## #lift

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_lift"
>title="Anstieg"
>abstract="Der Anstieg des Verhältnisses im Vergleich zum Kontrollwert."

<!-- markdownlint-enable MD034 -->

| Argument | Beschreibung |
| --- | --- |
| Normalisierungs-Container | Die Grundlage (Personen, Sitzungen oder Ereignisse) für die Ausführung eines Tests. |
| Erfolgsmetrik | Die Kennzahl(en), die ein(e) Benutzende(r) verwendet, um Varianten zu vergleichen. |
| Kontrolle | Die Variante, mit der alle anderen Varianten im Experiment verglichen werden. Geben Sie den Namen des Dimensionselements der Kontrollvariante ein. |



## Lineare Regression: Korrelationskoeffizient {#linear-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_linear_regression_correlation_coefficient"
>title="Lineare Regression: Korrelationskoeffizient"
>abstract="Lineare Regression: Y = a X + b. Gibt den Korrelationskoeffizienten zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LINEARE REGRESSION: KORRELATIONSKOEFFIZIENT(metric_X, metric_Y, include_zero)]**


[!BADGE Tabelle]{type="Neutral"}


| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die Sie mit metric_Y korrelieren möchten |
| metric_Y | Eine Metrik, die Sie mit metric_X korrelieren möchten |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |



## Lineare Regression: Intercept {#linear-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_linear_regression_intercept"
>title="Lineare Regression: Intercept"
>abstract="Lineare Regression: Y = a X + b. Gibt b zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LINEARE REGRESSION: INTERCEPT(metric_X, metric_Y, include_zero)]**


[!BADGE Tabelle]{type="Neutral"}


| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, der abhängige Daten zugewiesen werden sollen |
| metric_Y | Eine Metrik, die als unabhängige Daten gekennzeichnet werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |



## Lineare Regression: Prognostiziertes Y {#linear-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_linear_regression_predicted_y"
>title="Lineare Regression: Prognostiziertes Y"
>abstract="Lineare Regression: Y = a X + b. Gibt Y zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LINEARE REGRESSION: PRODICTED Y(metric_X, metric_Y, include_zero)]**


[!BADGE Zeile]{type="Neutral"}


| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, der abhängige Daten zugewiesen werden sollen |
| metric_Y | Eine Metrik, die als unabhängige Daten gekennzeichnet werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |



## Lineare Regression: Steigung {#linear-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_linear_regression_slope"
>title="Lineare Regression: Steigung"
>abstract="Lineare Regression: Y = a X + b. Gibt a zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LINEARE REGRESSION: SLOPE(metric_X, metric_Y, include_zero)]**

[!BADGE Tabelle]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, der abhängige Daten zugewiesen werden sollen |
| metric_Y | Eine Metrik, die als unabhängige Daten gekennzeichnet werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |


## Protokoll-Basis 10 {#log-base-ten}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_log_base_ten"
>title="Protokoll-Basis 10"
>abstract="Gibt den Logarithmus zur Basis 10 einer Zahl zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LOG BASE 10(metrisch)]**


[!BADGE Zeile]{type="Neutral"}


| Argument | Beschreibung |
|---|---|
| metric | Die positive reelle Zahl, für die der Logarithmus der Basis 10 verwendet werden soll |


## Log-Regression: Korrelationskoeffizient {#log-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_log_regression_coefficient"
>title="Log-Regression: Korrelationskoeffizient"
>abstract="Logistische Regression: Y = a ln(X) + b. Gibt den Korrelationskoeffizienten zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: KORRELATIONSKOEFFIZIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die Sie mit metric_Y korrelieren möchten |
| metric_Y | Eine Metrik, die Sie mit metric_X korrelieren möchten |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |


## Log-Regression: Intercept {#log-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_log_regression_intercept"
>title="Log-Regression: Intercept"
>abstract="Log-Regression: Y = a ln(X) + b. Gibt b zurück."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, der abhängige Daten zugewiesen werden sollen |
| metric_Y | Eine Metrik, die als unabhängige Daten gekennzeichnet werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |



## Protokollregression: Prognostiziertes Y {#log-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_log_regression_predicted_y"
>title="Protokollregression: Prognostiziertes Y"
>abstract="Log-Regression: Y = a ln(X) + b. Gibt Y zurück."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zero)]**

[!BADGE Zeile]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, der abhängige Daten zugewiesen werden sollen |
| metric_Y | Eine Metrik, die als unabhängige Daten gekennzeichnet werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |



## Log-Regression: Steigung {#log-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_log_regression_slope"
>title="Log-Regression: Steigung"
>abstract="Log-Regression: Y = a ln(X) + b. Gibt a zurück."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: SLOPE(metric_X, metric_Y, include_zero)]**

[!BADGE Tabelle]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, der abhängige Daten zugewiesen werden sollen |
| metric_Y | Eine Metrik, die als unabhängige Daten gekennzeichnet werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |



## Natürlicher Logarithmus {#natural-log}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_natural_log"
>title="Natürlicher Logarithmus"
>abstract="Gibt den natürlichen Logarithmus einer Zahl zurück. Natürliche Logarithmen basieren auf der Konstante e (2,71828182845904). LN ist die Umkehrung der Exponentialfunktion."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL NATÜRLICHES LOG(metrisch)]**

Gibt den natürlichen Logarithmus einer Zahl zurück. Natürliche Logarithmen basieren auf der Konstante e (2,71828182845904). LN ist die Umkehrung der Exponentialfunktion.

| Argument | Beschreibung |
|---|---|
| metric | Die positive reelle Zahl, für die der natürliche Logarithmus angezeigt werden soll |



## Nicht {#not}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_not"
>title="Nicht"
>abstract="Negation als boolescher Wert. Die Ausgabe ist entweder 0 (false) oder 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL NICHT(logisch)]**

Negation als boolescher Wert. Die Ausgabe ist entweder 0 (false) oder 1 (true).

| Argument | Beschreibung |
|---|---|
| logisch | Erforderlich. Ein Wert oder Ausdruck, der als TRUE oder FALSE ausgewertet werden kann |



## Ungleich {#not-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_not_equal"
>title="Ungleich"
>abstract="Ungleich. Die Ausgabe ist entweder 0 (false) oder 1 (true)."

<!-- markdownlint-enable MD034 -->

![EFFECT](/help/assets/icons/Effect.svg) **[!UICONTROL NOT EQUAL()]**


Ungleich. Die Ausgabe ist entweder 0 (false) oder 1 (true).


| Argument | Beschreibung |
|---|---|
| metric_X | |
| metric_Y | |

### Beispiel

`Metric 1 != Metric 2`


## Oder {#or}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_or"
>title="Oder"
>abstract="Trennung. Wenn ungleich null ist, gilt dies als „true“ und wenn gleich null ist, wird dies als „false“ betrachtet. Die Ausgabe ist entweder 0 (false) oder 1 (true)."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL OR(logical_test)]**


[!BADGE Zeile]{type="Neutral"}


| Argument | Beschreibung |
|---|---|
| Logical_test | Erfordert mindestens einen Parameter, kann jedoch eine beliebige Anzahl Parameter annehmen. Jeder Wert oder Ausdruck, der als TRUE oder FALSE ausgewertet werden kann |


>[!NOTE]
>
>0 (null) bedeutet „Falsch“ und jeder andere Wert „Wahr“.


## Pi {#pi}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_pi"
>title="Pi"
>abstract="Gibt PI zurück: 3,14159…"

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL PI()]**

Gibt PI zurück: 3,14159…


## Potenzregression: Korrelationskoeffizient {#power-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_power_regression_correlation_coefficient"
>title="Potenzregression: Korrelationskoeffizient"
>abstract="Potenzregression: Y = b X ^ a. Gibt den Korrelationskoeffizienten zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: KORRELATIONSKOEFFIZIENT(metric_X, metric_Y, include_zero)]**

[!BADGE Tabelle]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die Sie mit metric_Y korrelieren möchten |
| metric_Y | Eine Metrik, die Sie mit metric_X korrelieren möchten |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |



## Potenzregression: Intercept {#power-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_power_regression_intercept"
>title="Potenzregression: Intercept"
>abstract="Potenzregression: Y = b X ^ a. Gibt b zurück."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: INTERCEPT(metric_X, metric_Y, include_zero)]**


[!BADGE Tabelle]{type="Neutral"}


| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, der abhängige Daten zugewiesen werden sollen |
| metric_Y | Eine Metrik, die als unabhängige Daten gekennzeichnet werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |


## Potenzregression: Prognostiziertes Y {#power-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_power_regression_predicted_y"
>title="Potenzregression: Prognostiziertes Y"
>abstract="Potenzregression: Y = b X ^ a. Gibt Y zurück."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zero)]**

[!BADGE Zeile]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, der abhängige Daten zugewiesen werden sollen |
| metric_Y | Eine Metrik, die als unabhängige Daten gekennzeichnet werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |



## Leistungsregression: Steigung {#power-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_power_regression_slope"
>title="Leistungsregression: Steigung"
>abstract="Potenzregression: Y = b X ^ a. Gibt a zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: SLOPE(metric_X, metric_Y, include_zero)]**

[!BADGE Tabelle]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, der abhängige Daten zugewiesen werden sollen |
| metric_Y | Eine Metrik, die als unabhängige Daten gekennzeichnet werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |



## Quadratische Regression: Korrelationskoeffizient {#quadratic-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_quadratic_regression_correlation_coefficient"
>title="Quadratische Regression: Korrelationskoeffizient"
>abstract="Quadratische Regression: Y = (a + bX) ^ 2. Gibt den Korrelationskoeffizienten zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATISCHE REGRESSION: KORRELATIONSKOEFFIZIENT(metric_X, metric_Y, include_zero)]**

[!BADGE Tabelle]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die Sie mit metric_Y korrelieren möchten |
| metric_Y | Eine Metrik, die Sie mit metric_X korrelieren möchten |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |

## Quadratische Regression: Intercept {#quadratic-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_quadratic_regression_intercept"
>title="Quadratische Regression: Intercept"
>abstract="Quadratische Regression: Y = (a + bX) ^ 2. Gibt a zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATISCHE REGRESSION: INTERCEPT(metric_X, metric_Y, include_zero)]**

[!BADGE Tabelle]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, der abhängige Daten zugewiesen werden sollen |
| metric_Y | Eine Metrik, die als unabhängige Daten gekennzeichnet werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |


## Quadratische Regression: Vorhergesagtes Y {#quadratic-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_quadratic_regression_predicted_y"
>title="Quadratische Regression: Vorhergesagtes Y"
>abstract="Quadratische Regression: Y = (a + bX) ^ 2. Gibt Y zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATISCHE REGRESSION: PROGNOSTIZIERTES Y(metric_X, metric_Y, include_zero)]**

[!BADGE Zeile]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, der abhängige Daten zugewiesen werden sollen |
| metric_Y | Eine Metrik, die als unabhängige Daten gekennzeichnet werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |


## Quadratische Regression: Steigung {#quadratic-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_quadratic_regression_slope"
>title="Quadratische Regression: Steigung"
>abstract="Quadratische Regression: Y = (a + bX) ^ 2. Gibt b zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATISCHE REGRESSION: SLOPE(metric_X, metric_Y, include_zero)]**

[!BADGE Tabelle]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, der abhängige Daten zugewiesen werden sollen |
| metric_Y | Eine Metrik, die als unabhängige Daten gekennzeichnet werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |



## Reziproke Regression: Korrelationskoeffizient {#reciprocal-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_reciprocal_regression_correlation_coefficient"
>title="Reziproke Regression: Korrelationskoeffizient"
>abstract="Reziproke Regression: Y = a + b X ^ -1. Gibt den Korrelationskoeffizienten zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL REZIPROKE REGRESSION: KORRELATIONSKOEFFIZIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die Sie mit metric_Y korrelieren möchten |
| metric_Y | Eine Metrik, die Sie mit metric_X korrelieren möchten |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |


## Reziproke Regression: Intercept {#reciprocal-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_reciprocal_regression_intercept"
>title="Reziproke Regression: Intercept"
>abstract="Reziproke Regression: Y = a + b X ^ -1. Gibt ein -Objekt zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL REZIPROKE REGRESSION: INTERCEPT(metric_X, metric_Y, include_zero)]**

[!BADGE Tabelle]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, der abhängige Daten zugewiesen werden sollen |
| metric_Y | Eine Metrik, die als unabhängige Daten gekennzeichnet werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |


## Reziproke Regression: Prognostiziertes Y {#reciprocal-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_reciprocal_regression_predicted_y"
>title="Reziproke Regression: Prognostiziertes Y"
>abstract="Reziproke Regression: Y = a + b X ^ -1. Gibt Y zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL REZIPROKE REGRESSION: PROGNOSTIZIERTES Y(metric_X, metric_Y, include_zero)]**

[!BADGE Zeile]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, der abhängige Daten zugewiesen werden sollen |
| metric_Y | Eine Metrik, die als unabhängige Daten gekennzeichnet werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |


## Reziproke Regression: Steigung {#reciprocal-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_reciprocal_regression_slope"
>title="Reziproke Regression: Steigung"
>abstract="Reziproke Regression: Y = a + b X ^ -1. Gibt b zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL REZIPROKE REGRESSION: SLOPE(metric_X, metric_Y, include_zero)]**

[!BADGE Tabelle]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, der abhängige Daten zugewiesen werden sollen |
| metric_Y | Eine Metrik, die als unabhängige Daten gekennzeichnet werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |




## Sinus {#sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_sine"
>title="Sinus"
>abstract="Gibt den Sinus des angegebenen Winkels zurück. Wenn der Winkel in Grad angegeben ist, multiplizieren Sie den Winkel mit PI()/180."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL SINUS(metrisch)]**


[!BADGE Zeile]{type="Neutral"}


| Argument | Beschreibung |
|---|---|
| metric | Der Winkel im Bogenmaß, für den der Sinus verwendet werden soll |




## t-Transformation {#t-score}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_t_score"
>title="t-Transformation"
>abstract="Die Abweichung vom [MITTELWERT](cm-functions.md#mean) geteilt durch die Standardabweichung. Alias für [Z-Score](#z-score)."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL T-SCORE(metric, include_zeros)]**

Die Abweichung vom [MITTELWERT](cm-functions.md#mean) geteilt durch die Standardabweichung. Alias für [Z-Score](#z-score).

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die der T-Score erstellt werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |


## t-Test {#t-test}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_t_test"
>title="t-Test"
>abstract="Führt einen m-seitigen t-Test mit einem t-Wert von x und n Freiheitsgraden durch."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL T-TEST(metrisch, Grad, Schwanz)]**

Führt einen m-seitigen t-Test mit einem t-Wert von x und n Freiheitsgraden durch.

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die Sie einen Test durchführen möchten |
| degrees | Die Freiheitsgrade |
| Schwänze | Die Länge des für die Durchführung des T-Tests zu verwendenden Schwanzes |

### Details

Die Signatur ist T-TEST (Metrik, Grad, Zahl). Darunter ruft es einfach ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-T(-ABSOLUTE VALUE(tails), degrees)]](#cdf-t)**. Diese Funktion ähnelt der **[Z-TEST](#z-test)**-Funktion, die ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-Z(-ABSOLUTE VALUE(tails))]](#cdf-z)** ausführt.

- ***m*** ist die Anzahl der Schwänze.
- ***n*** ist der Freiheitsgrad und sollte eine konstante Zahl für den gesamten Bericht sein, d. h., sie ändert sich nicht Zeile für Zeile.
- ***x*** ist die Statistik des T-Tests und wäre häufig eine Formel (z. B. **[Z-SCORE](#z-score)**), die auf einer Metrik basiert und in jeder Zeile ausgewertet wird.

Der Rückgabewert ist die Wahrscheinlichkeit, die Teststatistik x zu erhalten, bei gegebenen Freiheitsgraden und der Anzahl an Seiten.

### Beispiele

1. Verwenden Sie die -Funktion, um Ausreißer zu finden:

   ```
   T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2)
   ```

1. Kombinieren Sie die Funktion mit **[IF](#if)**, um sehr hohe oder niedrige Absprungraten zu ignorieren und Sitzungen auf alles andere zu zählen:

   ```
   IF(T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2) < 0.01, 0, sessions )
   ```



## Tangens {#tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_tangent"
>title="Tangens"
>abstract="Gibt den Tangens des angegebenen Winkels zurück. Wenn der Winkel in Grad angegeben ist, multiplizieren Sie den Winkel mit PI()/180."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL TANGENS(metrisch)]**

Gibt den Tangens des angegebenen Winkels zurück. Wenn der Winkel in Grad angegeben ist, multiplizieren Sie den Winkel mit PI()/180.

| Argument | Beschreibung |
|---|---|
| metric | Der Winkel in Bogenmaß, für den die Tangente bestimmt werden soll |



## z-score {#z-score}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_z_score"
>title="z-score"
>abstract="Die Abweichung vom Mittelwert dividiert durch die Standardabweichung."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL Z-SCORE(metric, include_zeros)]**

[!BADGE Zeile]{type="Neutral"}

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die der Z-Wert gewünscht wird |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen |

Ein Z-Score von 0 (Null) bedeutet, dass der Score dem Mittelwert entspricht. Eine z-Transformation kann positiv oder negativ sein, abhängig davon, ob sie über oder unter dem arithmetischen Mittel liegt und um wie viele Standardabweichungen es sich handelt.

Die Gleichung für z-Transformation lautet:

![](assets/z_score.png)

Dabei ist ***[!DNL x]*** der Rohwert, ***[!DNL μ]*** der Mittelwert der Population und ***[!DNL σ]*** die Standardabweichung der Population.

>[!NOTE]
>
>***[!DNL μ]*** (Mu) und ***[!DNL σ]*** (Sigma) werden automatisch aus der Metrik berechnet.



## z-Test {#z-test}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="calcmetrics_function_z_test"
>title="z-Test"
>abstract="Führt einen n-seitigen z-Test mit einem z-Wert von x durch."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL Z-TEST(metric_tails)]**

Führt einen n-seitigen z-Test mit einem z-Wert von x durch.

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die ein Z-Test durchgeführt werden soll |
| Schwänze | Die Länge des für die Durchführung des Z-Tests zu verwendenden Schwanzes |

>[!NOTE]
>
>Dabei wird von einer Normalverteilung der Werte ausgegangen.




<!--



## AND

Returns the value of its argument. Use NOT to make sure that a value is not equal to one particular value.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
AND(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Approximate Count Distinct (dimension)

Returns the approximated distinct count of dimension items for the selected dimension. The function uses the HyperLogLog (HLL) method of approximating distinct counts.&nbsp; It is configured to guarantee the value is within 5% of the actual value 95% of the time.

```
Approximate Count Distinct (dimension)
```

|  Argument  |  |
|---|---|
|  *dimension* | The dimension for which you want the approximate distinct item count.  |

### Example Use Case

Approximate Count Distinct (customer ID eVar) is a common use case for this function.

Definition for a new 'Approximate Customers' calculated metric:

![Approximate county distinct new dimension definition showing Customer ID (eVar1)](assets/approx-count-distinct.png)

This is how the "Approximate Customers" metric could be used in reporting:

![Freeform Table showing Unique Visitors and Approximate Customers ](assets/approx-customers.png)

### Comparing Count Functions

Approximate Count Distinct() is an improvement over Count() and RowCount() functions because the metric created can be used in any dimensional report to render an approximated count of items for a separate dimension. For example, a count of customer IDs used in a Mobile Device Type report.

This function will be marginally less accurate than Count() and RowCount() because it uses the HLL method, whereas Count() and RowCount() are exact counts.

## Arc Cosine (Row)

Returns the arccosine, or inverse of the cosine, of a metric. The arccosine is the angle whose cosine is number. The returned angle is given in radians in the range 0 (zero) to pi. If you want to convert the result from radians to degrees, multiply it by 180/PI( ).

```
ACOS(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Sine (Row)

Returns the arcsine, or inverse sine, of a number. The arcsine is the angle whose sine is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arcsine in degrees, multiply the result by 180/PI( ).

```
ASIN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Tangent (Row)

Returns the arctangent, or inverse tangent, of a number. The arctangent is the angle whose tangent is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arctangent in degrees, multiply the result by 180/PI( ).

```
ATAN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Exponential Regression: Predicted Y (Row)

Calculates the predicted y-values (metric_Y), given the known x-values (metric_X) using the "least squares" method for calculating the line of best fit based on .

```
ESTIMATE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Cdf-T

Returns the percentage of values in a student's t-distribution with n degrees of freedom that have a z-score less than x.

```
cdf_t( -∞, n ) = 0
cdf_t(  ∞, n ) = 1
cdf_t( 3, 5 ) ? 0.99865
cdf_t( -2, 7 ) ? 0.0227501
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

Returns the percentage of values in a normal distribution that have a z-score less than x.

```
cdf_z( -∞ ) = 0
cdf_z( ∞ ) = 1
cdf_z( 0 ) = 0.5
cdf_z( 2 ) ? 0.97725
cdf_z( -3 ) ? 0.0013499

```

## Exponential Regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns ( *metric_X* and *metric_Y*) for

```
INTERCEPT.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Exponential Regression: Slope (Table)

Returns the slope, *a*, between two metric columns ( *metric_X* and *metric_Y*) for .

```
SLOPE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Floor (Row)

Returns the largest integer not greater than a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula FLOOR( *Revenue*) to round revenue down to the nearest dollar, or $569.

```
FLOOR(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric you want to round.  |

## Greater Than

Returns items whose numeric count is greater than the value entered.

## Greater Than or Equal

Returns items whose numeric count is greater than or equal to the value entered.

## Hyperbolic Cosine (Row)

Returns the hyperbolic cosine of a number.

```
COSH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic cosine.  |

## Hyperbolic Sine (Row)

Returns the hyperbolic sine of a number.

```
SINH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic sine.  |

## Hyperbolic Tangent (Row)

Returns the hyperbolic tangent of a number.

```
TANH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic tanget.  |

## IF (Row)

The IF function returns one value if a condition you specify evaluates to TRUE, and another value if that condition evaluates to FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

|  Argument  | Description  |
|---|---|
|  *logical_test* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *[value_if_true]* | The value that you want to be returned if the *logical_test* argument evaluates to TRUE. (This argument defaults to 0 if not included.)  |
|  *[value_if_false]* | The value that you want to be returned if the *logical_test* argument evaluates to FALSE. (This argument defaults to 0 if not included.)  |

## Less Than

Returns items whose numeric count is less than the value entered.

## Less Than or Equal

Returns items whose numeric count is less than or equal to the value entered.

## Lift

Returns the Lift a particular variant had in conversions over a control variant. It is the difference in performance between a given variant and the baseline, divided by the performance of the baseline, expressed as a percentage. 

```
fx Lift (normalizing-container, success-metric, control)
```

| Argument | Description |
| --- | --- |
| Normalizing Container | The basis (People, Sessions, or Events) on which a test will be run. |
| Success Metric | The metric or metrics that a user is comparing variants with. |
| Control | The variant that all other variants in the experiment are being compared with. Enter the name of the control variant dimension item. |

{style="table-layout:auto"}

## Linear regression_ Correlation Coefficient

Y = a X + b. Returns the correlation coefficient

## Linear regression_ Intercept

Y = a X + b. Returns b.

## Linear regression_ Predicted Y

Y = a X + b. Returns Y.

## Linear regression_ Slope

Y = a X + b. Returns a.

## Log Base 10 (Row)

Returns the base-10 logarithm of a number.

```
LOG10(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the base-10 logarithm.  |

## Log regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the CORREL equation.

```
CORREL.LOG(metric_X,metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Log regression: Intercept (Table)

Returns the intercept *b* as the least squares regression between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the INTERCEPT equation.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log Regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the "least squares" method for calculating the line of best fit based on [!DNL Y = a ln(X) + b]. It is calculated using the ESTIMATE equation.

In regression analysis, this function calculates the predicted [!DNL y] values (*metric_Y*), given the known [!DNL x] values (*metric_X*) using the logarithm for calculating the line of best fit for the regression equation [!DNL Y = a ln(X) + b]. The [!DNL a] values correspond to each x value, and [!DNL b] is a constant value.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the SLOPE equation.

```
SLOPE.LOG(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the independent data.  |

## Natural Log

Returns the natural logarithm of a number. Natural logarithms are based on the constant *e* (2.71828182845904). LN is the inverse of the EXP function.

```
LN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the natural logarithm.  |

## NOT

Returns 1 if the number is 0 or returns 0 if another number.

```
NOT(logical)
```

|  Argument  | Description  |
|---|---|
|  *logical* | Required. A value or expression that can be evaluated to TRUE or FALSE.  |

Using NOT requires knowing if the expressions (<, >, =, <> , etc.) return 0 or 1 values.

## Not equal

Returns all items that do not contain the exact match of the value entered.

## Or (Row)

Returns TRUE if any argument is TRUE, or returns FALSE if all arguments are FALSE.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
OR(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Pi

Returns the constant PI, 3.14159265358979, accurate to 15 digits.

```
PI()
```

The [!DNL PI]function has no arguments.

## Power regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Power regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values ( [!DNL metric_Y]), given the known [!DNL x] values ( [!DNL metric_X]) using the "least squares" method for calculating the line of best fit for [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Quadratic regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y=(a*X+b)]**** .

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the dependent data.  |

## Quadratic regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and metric_Y) for [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X)* and *metric_Y*) for [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Reciprocal regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Sine (Row)

Returns the sine of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
SIN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the sine.  |

## T-Score

Alias for Z-Score, namely the deviation from the mean divided by the standard deviation

## T-Test

Performs an m-tailed t-test with t-score of col and n degrees of freedom.

The signature is `t_test( x, n, m )`. Underneath, it simply calls `m*cdf_t(-abs(x),n)`. (This is similar to the z-test function which runs `m*cdf_z(-abs(x))`.

Here, `m` is the number of tails, and `n` is the degrees of freedom. These should be numbers (constant for the whole report, i.e. not changing on a row by row basis).

`X` is the t-test statistic, and would often be a formula (e.g. zscore) based on a metric and will be evaluated on every row.

The return value is the probability of seeing the test statistic x given the degrees of freedom and number of tails.

**Examples:**

1. Use it to find outliers:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combine it with `if` to ignore very high or low bounce rates, and count visits on everything else:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangent

Returns the tangent of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
TAN (metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the tangent.  |

## Z-Score (Row)

Returns the Z-score, or normal score, based upon a normal distribution. The Z-score is the number of standard deviations an observation is from the mean. A Z-score of 0 (zero) means the score is the same as the mean. A Z-score can be positive or negative, indicating whether it is above or below the mean and by how many standard deviations.

The equation for Z-score is:

![](assets/z_score.png)

where [!DNL x] is the raw score, [!DNL μ] is the mean of the population, and [!DNL σ] is the standard deviation of the population.

>[!NOTE]
>
>[!DNL μ] (mu) and[!DNL σ] (sigma) are automatically calculated from the metric.

Z-score(metric)

<table id="table_AEA3622A58F54EA495468A9402651E1B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Argument </th>
   <th colname="col2" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <i>metric</i> </td>
   <td colname="col2"> <p> Returns the value of its first non-zero argument. </p> </td>
  </tr>
 </tbody>
</table>

## Z-Test

Performs an n-tailed Z-test with Z-score of A.

Returns the probability that the current row could be seen by chance in the column.

>[!NOTE]
>
>Assumes that the values are normally distributed.

-->