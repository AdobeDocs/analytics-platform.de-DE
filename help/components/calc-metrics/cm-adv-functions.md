---
title: Erweiterte Funktionen
description: Greifen Sie auf diese Funktionen zu, indem Sie im Dropdown-Menü Funktionen die Option Erweitert anzeigen auswählen.
feature: Calculated Metrics
exl-id: 3689a499-817d-4a59-8a1f-5f7bda297268
role: User
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '5247'
ht-degree: 89%

---

# Erweiterte Funktionen

Mit dem [Generator für berechnete Metriken](cm-workflow/cm-build-metrics.md) können Sie statistische und mathematische Funktionen anwenden. In diesem Artikel werden die erweiterten Funktionen und ihre Definitionen alphabetisch aufgelistet.

Sie können auf diese Funktionen zugreifen, indem Sie die Option **[!UICONTROL Alle anzeigen]** unter der Liste ![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL Funktionen]** im Panel „Komponenten“ auswählen. Scrollen Sie nach unten, um die Liste der **[!UICONTROL Erweiterten Funktionen]** anzuzeigen.

## Vergleich zwischen Tabellenfunktionen und Zeilenfunktionen

Bei einer Tabellenfunktion ist die Ausgabe für jede Tabellenzeile gleich. Bei einer Zeilenfunktion ist die Ausgabe für jede Tabellenzeile unterschiedlich.

Sofern zutreffend und relevant, wird eine Funktion mit dem Typ der Funktion kommentiert: [!BADGE Tabelle]{type="Neutral"} oder [!BADGE Zeile]{type="Neutral"}

## Was bedeutet der Parameter „include-zeros“?

Damit wird angegeben, ob Nullen in die Berechnung einbezogen werden sollen. In manchen Fällen bedeutet eine Null *nichts*, in anderen Fällen kann sie aber auch wichtig sein.

Beispiel: Wenn Sie mit einer Umsatzmetrik arbeiten und dem Bericht dann eine Seitenansichtsmetrik hinzufügen, gibt es plötzlich mehr Zeilen für den Umsatz, die alle Nullwerte enthalten. Sie möchten wahrscheinlich nicht, dass sich diese zusätzliche Metrik auf Berechnungen wie **[ARITHMETISCHES MITTEL](cm-functions.md#mean)**, **[ZEILENMINIMUM](cm-functions.md#row-min)**, **[QUARTIL](cm-functions.md#quartile)** usw. auswirkt, die sich in der Umsatzspalte befinden. In diesem Fall müssen Sie den Parameter `include-zeros` aktivieren.

Ein alternatives Szenario besteht darin, dass Sie zwei Metriken von Interesse haben und eine Metrik einen höheren Durchschnitt oder ein höheres Minimum aufweist, da einige der Zeilen Nullen sind.  In diesem Fall können Sie festlegen, dass der Parameter nicht auf Nullen überprüft werden soll.


## Und {#and}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-and"
>title="Und"
>abstract="Verbindung. „Ungleich null“ gilt als „True“ und „Gleich null“ gilt als „False“. Die Ausgabe ist entweder 0 (False) oder 1 (True)."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL AND(logical_test)]**

Verbindung. „Ungleich null“ gilt als „True“ und „Gleich null“ gilt als „False“. Die Ausgabe ist entweder 0 (False) oder 1 (True).

| Argument | Beschreibung |
|---|---|
| logical_test | Erfordert mindestens einen Parameter, kann jedoch eine beliebige Anzahl von Parametern verwenden. Jeder Wert oder Ausdruck, der als TRUE oder FALSE ausgewertet werden kann |


## Ungefähre Zählung Verschiedener {#approximate_count_distinct}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count-distinct-metric"
>title="Ungefähre Zählung Verschiedener"
>abstract="Gibt die ungefähre Anzahl von Dimensionselementen für die ausgewählte Dimension zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL APPROXIMATE COUNT DISTINCT(dimension)]**


Gibt die ungefähre Anzahl von Dimensionselementen für die ausgewählte Dimension zurück.


| Argument | Beschreibung |
|---|---|
| Dimension | Die Dimension, für die die ungefähre Anzahl verschiedener Elemente ermittelt werden soll |

### Beispiel

Ein gängiger Anwendungsfall für diese Funktion ist, wenn Sie eine ungefähre Anzahl von Kundinnen und Kunden erhalten möchten.



## Arcuscosinus {#arc-cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-acos"
>title="Arcuscosinus"
>abstract="Gibt den Arcuscosinus (d. h. die Umkehrung des Cosinus) einer Metrik zurück. Der Arcuscosinus ist der Winkel, dessen Cosinus eine gegebene Zahl ist. Der zurückgegebene Winkel wird in Radiant im Bereich von 0 (Null) bis pi angegeben. Wenn Sie das Ergebnis von Radianten in Grad umrechnen möchten, multiplizieren Sie es mit 180/PI()."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL ARC COSINE(metric)]**


[!BADGE Zeile]{type="Neutral"} Gibt den Arkuskosinus (oder das Inverse des Kosinus) einer Metrik zurück. Der Arcuscosinus ist der Winkel, dessen Cosinus eine gegebene Zahl ist. Der zurückgegebene Winkel wird in Radiant im Bereich von 0 (Null) bis pi angegeben. Wenn Sie das Ergebnis von Radianten in Grad umrechnen möchten, multiplizieren Sie es mit 180/PI().


| Argument | Beschreibung |
|---|---|
| metric | Der Kosinus des gewünschten Winkels von -1 bis 1 |



## Arcussinus {#arc-sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-asin"
>title="Arcussinus"
>abstract="Gibt den Arcussinus (die Umkehrung des Sinus) einer Zahl zurück. Der Arcussinus ist der Winkel, dessen Sinus eine gegebene Zahl ist. Der zurückgegebene Winkel wird in Radiant im Bereich -pi/2 bis pi/2 angegeben. Um den Arcussinus in Grad auszudrücken, multiplizieren Sie das Ergebnis mit 180/PI()"

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL ARC SINE(metric)]**


[!BADGE Row]{type="Neutral"} Gibt den Arkussinus (den umgekehrten Sinus) einer Zahl zurück. Der Arcussinus ist der Winkel, dessen Sinus eine gegebene Zahl ist. Der zurückgegebene Winkel wird in Radiant im Bereich -pi/2 bis pi/2 angegeben. Um den Arkussinus in Grad auszudrücken, multiplizieren Sie das Ergebnis mit 180/PI().


| Argument | Beschreibung |
|---|---|
| metric | Der Sinus des gewünschten Winkels von -1 bis 1 |



## Arkustangens {#arc-tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-atan"
>title="Arkustangens"
>abstract="Gibt den Arkustangens, d. h. die Umkehrung des Tangens, einer Zahl zurück. Der Arkustangens ist der Winkel, dessen Tangens eine gegebene Zahl ist. Der zurückgegebene Winkel wird in Radiant im Bereich -pi/2 bis pi/2 angegeben. Um den Arkustangens in Grad auszudrücken, multiplizieren Sie das Ergebnis mit 180/PI()."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL ARC TANGENT(metric)]**


[!BADGE Zeile]{type="Neutral"} Gibt den Arkustangens oder umgekehrten Tangens einer Zahl zurück. Der Arkustangens ist der Winkel, dessen Tangens eine gegebene Zahl ist. Der zurückgegebene Winkel wird in Radiant im Bereich -pi/2 bis pi/2 angegeben. Um den Arkustangens in Grad auszudrücken, multiplizieren Sie das Ergebnis mit 180/PI().


| Argument | Beschreibung |
|---|---|
| metric | Die Tangente des gewünschten Winkels von -1 bis 1 |



## Cdf-T {#cdf-t}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cdf-t"
>title="Cdf-T"
>abstract="Gibt die Wahrscheinlichkeit dafür zurück, dass eine Zufallsvariable mit studentscher t-Verteilung mit n Freiheitsgraden einen z-Wert hat, der unter dem Spaltenwert liegt."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-T(metric, number)]**

Gibt die Wahrscheinlichkeit dafür zurück, dass eine Zufallsvariable mit studentscher t-Verteilung mit n Freiheitsgraden einen z-Wert hat, der unter dem Spaltenwert liegt.

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die die kumulative Verteilungsfunktion der studentischen t-Verteilung angezeigt werden soll |
| number | Die Freiheitsgrade für die kumulative Verteilungsfunktion der studentischen t-Verteilung |

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
>id="functions-cdf-z"
>title="Cdf-Z"
>abstract="Gibt die Wahrscheinlichkeit dafür zurück, dass eine Zufallsvariable mit einer normalen Verteilung einen z-Wert hat, der unter dem Spaltenwert liegt."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-Z(metric, number)]**

Gibt die Wahrscheinlichkeit dafür zurück, dass eine Zufallsvariable mit einer normalen Verteilung einen z-Wert hat, der unter dem Spaltenwert liegt.

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die die kumulative Verteilungsfunktion der Standardnormalverteilung verwendet werden soll |

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
>id="functions-ceil"
>title="Ceiling (Obergrenze)"
>abstract="Gibt die kleinste Ganzzahl zurück, die nicht kleiner als ein angegebener Wert ist. Beispiel: Wenn Sie für den Umsatz keine Währungsdezimalzahlen in Berichte aufnehmen möchten und ein Produkt einen Umsatz von 569,34 US-Dollar aufweist, können Sie mit der Formel CEILING(Umsatz) den Umsatz auf den nächsten Dollar aufrunden (in diesem Fall 570 US-Dollar)."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CEILING(metric)]**

[!BADGE Zeile]{type="Neutral"} Gibt die kleinste Ganzzahl zurück, die mindestens einem angegebenen Wert entspricht. Beispiel: Wenn Sie für den Umsatz keine Währungsdezimalzahlen in Berichte aufnehmen möchten und ein Produkt einen Umsatz von 569,34 US-Dollar aufweist, können Sie mit der Formel CEILING(Umsatz) den Umsatz auf den nächsten Dollar aufrunden (in diesem Fall 570 US-Dollar).

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, die gerundet werden soll |


## Konfidenz {#confidence}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-confidence"
>title="Konfidenz"
>abstract="Berechnet die jederzeit gültige Konfidenz mithilfe der WASKR-Methode, wie in [Zeiteinheitlicher zentraler Grenzwertsatz und asymptotische Konfidenzintervalle (Time-uniform central limit theory and asymptotic confidence sequences)](https://arxiv.org/pdf/2103.06476) beschrieben."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

Berechnet die jederzeit gültige Konfidenz mithilfe der WASKR-Methode, wie in [Zeiteinheitlicher zentraler Grenzwertsatz und asymptotische Konfidenzintervalle (Time-uniform central limit theory and asymptotic confidence sequences)](https://arxiv.org/pdf/2103.06476) beschrieben.

Konfidenz ist ein Maß dafür, wie hoch die Wahrscheinlichkeit ist, dass eine bestimmte Variante mit der Kontrollvariante identisch ist. Bei einer höheren Konfidenz deutet weniger darauf hin, dass die Annahme stimmt, dass die Kontroll- und Nicht-Kontrollvariante die gleiche Performance aufweisen.

| Argument | Beschreibung |
| --- | --- |
| normalizing-container | Die Grundlage (Personen, Sitzungen oder Ereignisse) für die Ausführung eines Tests. |
| success-metric | Die Metrik oder Metriken, die eine Benutzerin bzw. ein Benutzer verwendet. |
| control | Die Variante, mit der alle anderen Varianten im Experiment verglichen werden. Geben Sie den Namen des Dimensionselements der Kontrollvariante ein. |
| significance-threshold | Der Schwellenwert in dieser Funktion ist auf den Standardwert 95 % eingestellt. |


## Confidence (Lower) {#confidence-lower}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-confidence-interval-lower"
>title="Confidence (Lower)"
>abstract="Berechnet die jederzeit gültige **niedrigere** Konfidenz mithilfe der WASKR-Methode, wie in [Zeiteinheitlicher zentraler Grenzwertsatz und asymptotische Konfidenzintervalle (Time-uniform central limit theory and asymptotic confidence sequences)](https://arxiv.org/pdf/2103.06476) beschrieben."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

Berechnet die jederzeit gültige **niedrigere** Konfidenz mithilfe der WASKR-Methode, wie in [Zeiteinheitlicher zentraler Grenzwertsatz und asymptotische Konfidenzintervalle (Time-uniform central limit theory and asymptotic confidence sequences)](https://arxiv.org/pdf/2103.06476) beschrieben.

Konfidenz ist ein Maß dafür, wie hoch die Wahrscheinlichkeit ist, dass eine bestimmte Variante mit der Kontrollvariante identisch ist. Bei einer höheren Konfidenz deutet weniger darauf hin, dass die Annahme stimmt, dass die Kontroll- und Nicht-Kontrollvariante die gleiche Performance aufweisen.

| Argument | Beschreibung |
| --- | --- |
| normalizing-container | Die Grundlage (Personen, Sitzungen oder Ereignisse) für die Ausführung eines Tests. |
| success-metric | Die Metrik oder Metriken, die eine Benutzerin bzw. ein Benutzer verwendet. |
| control | Die Variante, mit der alle anderen Varianten im Experiment verglichen werden. Geben Sie den Namen des Dimensionselements der Kontrollvariante ein. |
| significance-threshold | Der Schwellenwert in dieser Funktion ist auf den Standardwert 95 % eingestellt. |

## Confidence (Upper) {#confidence-upper}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-confidence-interval-upper"
>title="Confidence (Upper)"
>abstract="Berechnet die jederzeit gültige **höhere** Konfidenz mithilfe der WASKR-Methode, wie in [Zeiteinheitlicher zentraler Grenzwertsatz und asymptotische Konfidenzintervalle (Time-uniform central limit theory and asymptotic confidence sequences)](https://arxiv.org/pdf/2103.06476) beschrieben."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

Berechnet die jederzeit gültige **höhere** Konfidenz mithilfe der WASKR-Methode, wie in [Zeiteinheitlicher zentraler Grenzwertsatz und asymptotische Konfidenzintervalle (Time-uniform central limit theory and asymptotic confidence sequences)](https://arxiv.org/pdf/2103.06476) beschrieben.

Konfidenz ist ein Maß dafür, wie hoch die Wahrscheinlichkeit ist, dass eine bestimmte Variante mit der Kontrollvariante identisch ist. Bei einer höheren Konfidenz deutet weniger darauf hin, dass die Annahme stimmt, dass die Kontroll- und Nicht-Kontrollvariante die gleiche Performance aufweisen.

| Argument | Beschreibung |
| --- | --- |
| normalizing-container | Die Grundlage (Personen, Sitzungen oder Ereignisse) für die Ausführung eines Tests. |
| success-metric | Die Metrik oder Metriken, die eine Benutzerin bzw. ein Benutzer verwendet. |
| control | Die Variante, mit der alle anderen Varianten im Experiment verglichen werden. Geben Sie den Namen des Dimensionselements der Kontrollvariante ein. |
| significance-threshold | Der Schwellenwert in dieser Funktion ist auf den Standardwert 95 % eingestellt. |


## Cosine {#cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cos"
>title="Cosine"
>abstract="Gibt den Cosinus des gegebenen Winkels zurück. Wenn der Winkel in Grad angegeben ist, multiplizieren Sie den Winkel mit PI()/180."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL COSINE(metric)]**

[!BADGE Zeile]{type="Neutral"} Gibt den Kosinus des gegebenen Winkels zurück. Wenn der Winkel in Grad angegeben ist, multiplizieren Sie den Winkel mit PI()/180.

| Argument | Beschreibung |
|---|---|
| metric | Der Winkel in Radianten, für den der Kosinus ermittelt werden soll |


## Kubikwurzel {#cube-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cube-root"
>title="Kubikwurzel"
>abstract="Gibt die positive Kubikwurzel einer Zahl zurück. Die Kubikwurzel einer Zahl ist der Wert, wenn diese Zahl zur Potenz 1/3 erhoben wird."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CUBE ROOT(metric)]**


Gibt die positive Kubikwurzel einer Zahl zurück. Die Kubikwurzel einer Zahl ist der Wert, wenn diese Zahl zur Potenz 1/3 erhoben wird.


| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die die Kubikwurzel berechnet werden soll |



## Kumulativ {#cumulative}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cumul"
>title="Kumulativ"
>abstract="Gibt die Summe der letzten n Elemente der Spalte x zurück. Wenn n > 0 ist, werden die letzten n Elemente von x addiert. Wenn n &lt; 0 ist, werden die n vorangehenden Elemente addiert."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE(number, metric)]**

Gibt die Summe der letzten n Elemente der Spalte x zurück. Wenn n > 0 ist, werden die letzten n Elemente von x addiert. Wenn n &lt; 0 ist, werden die n vorangehenden Elemente addiert.

| Argument | Beschreibung |
| --- | --- |
| number | Die letzte Anzahl N von Zeilen, für die die Summe zurückgegeben werden soll. Wenn N &lt;= 0 ist, werden alle vorherigen Zeilen verwendet. |
| metric | Die Metrik, für die die kumulative Summe angezeigt werden soll. |

### Beispiele

| Datum | Umsatz | CUMULATIVE(0, Revenue) | CUMULATIVE(2, Revenue) |
|------|------:|--------------:|--------------:|
| Mai | 500 $ | 500 $ | 500 $ |
| Juni | 200 $ | 700 $ | 700 $ |
| Juli | 400$ | 1100 $ | 600 $ |


## Cumulative (Average) {#cumulative-average}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cumul-avg"
>title="Cumulative (Average)"
>abstract="Gibt den Durchschnitt der letzten n Elemente der Spalte x zurück. Wenn n > 0 ist, werden die letzten n Elemente von x addiert. Wenn n &lt; 0 ist, werden die vorangehenden Elemente n addiert."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE AVERAGE(number, metric)]**

Gibt den Durchschnitt der letzten n Elemente der Spalte x zurück. Wenn n > 0 ist, werden die letzten n Elemente von x addiert. Wenn n &lt; 0 ist, werden die vorangehenden Elemente n addiert.

| Argument | Beschreibung |
| --- | --- |
| number | Die letzte Anzahl N von Zeilen, für die der Durchschnitt zurückgegeben werden soll. Wenn N &lt;= 0 ist, werden alle vorherigen Zeilen verwendet. |
| metric | Die Metrik, für die der kumulative Durchschnitt ermittelt werden soll. |

>[!NOTE]
>
>Diese Funktion funktioniert nicht mit Satzmetriken wie Umsatz pro Person. Die Funktion ermittelt den Durchschnitt der Sätze, anstatt den Umsatz der letzten N zu summieren und die Personen der letzten N zu summieren und dann zu teilen. <br/>Verwenden Sie stattdessen [**[!UICONTROL CUMULATIVE(Revenue)]**](#cumulative) ![Divide](/help/assets/icons/Divide.svg) [**[!UICONTROL CUMULATIVE(person)]**](#cumulative).
>


## Gleich {#equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-eq"
>title="Gleich"
>abstract="Gleich. Die Ausgabe ist entweder 0 (False) oder 1 (True)."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL EQUAL()]**

Gleich. Die Ausgabe ist entweder 0 (False) oder 1 (True).


| Argument | Beschreibung |
|---|---|
| metric_X | Die Metrik, die Sie vergleichen möchten. |
| metric_Y | Die Metrik, mit der verglichen werden soll. |

### Beispiel

`Metric 1 = Metric 2`


## Exponentielle Regression: Korrelationskoeffizient {#exponential-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-exp"
>title="Exponentielle Regression: Korrelationskoeffizient"
>abstract="Exponentielle Regression: Y = a exp(X) + b. Gibt den Korrelationskoeffizienten zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabelle]{type="Neutral"} Exponentielle Regression: Y = a exp(X) + b. Gibt den Korrelationskoeffizienten zurück.


| Argument | Beschreibung |
|---|---|
| metric_X | Die Metrik, die mit metric_Y korreliert werden soll |
| metric_Y | Die Metrik, die mit metric_X korreliert werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |

## Exponentielle Regression: Vorhersage für Y {#exponential-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-exp"
>title="Exponentielle Regression: Vorhersage für Y"
>abstract="Exponentielle Regression: Y = a exp(X) + b. Gibt Y zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Zeile]{type="Neutral"} Exponentielle Regression: Y = a exp(X) + b. Gibt Y zurück.


| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |
| metric_Y | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |


## Exponentielle Regression: Schnittpunkt {#exponential-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-exp"
>title="Exponentielle Regression: Schnittpunkt"
>abstract="Exponentielle Regression: Y = a exp(X) + b. Gibt b zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabelle]{type="Neutral"} Exponentielle Regression: Y = a exp(X) + b. Gibt b zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die als abhängiges Datenelement zugewiesen werden soll |
| metric_Y | Die Metrik, die als unabhängiges Datenelement zugewiesen werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |


## Exponentielle Regression: Steigung {#exponential-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-exp"
>title="Exponentielle Regression: Steigung"
>abstract="Exponentielle Regression: Y = a exp(X) + b. Gibt a zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabelle]{type="Neutral"} Exponentielle Regression: Y = a exp(X) + b. Gibt a zurück.


| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die als abhängiges Datenelement zugewiesen werden soll |
| metric_Y | Die Metrik, die als unabhängiges Datenelement zugewiesen werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |


## Floor {#floor}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-floor"
>title="Floor"
>abstract="Gibt die größte Ganzzahl zurück, die nicht größer als ein angegebener Wert ist. Beispiel: Wenn Sie für den Umsatz keine Währungsdezimalzahlen in Berichte aufnehmen möchten und ein Produkt einen Umsatz von 569,34 US-Dollar aufweist, können Sie mit der Formel FLOOR(Umsatz) den Umsatz auf den nächsten Dollar abrunden (in diesem Fall 569 US-Dollar)."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL FLOOR(metric_X, metric_Y, include_zeros)]**

[!BADGE Zeile]{type="Neutral"} Gibt die größte Ganzzahl zurück, die nicht größer als ein gegebener Wert ist. Beispiel: Wenn Sie für den Umsatz keine Währungsdezimalzahlen in Berichte aufnehmen möchten und ein Produkt einen Umsatz von 569,34 US-Dollar aufweist, können Sie mit der Formel FLOOR(Umsatz) den Umsatz auf den nächsten Dollar abrunden (in diesem Fall 569 US-Dollar).

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, die gerundet werden soll. |


## Größer als {#greather-than}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-gt"
>title="Größer als"
>abstract="Die Ausgabe ist entweder 0 (False) oder 1 (True)."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER THAN()]**

Die Ausgabe ist entweder 0 (False) oder 1 (True).

| Argument | Beschreibung |
|---|---|
| metric_X | Die Basismetrik, die Sie zum Vergleich verwenden möchten. |
| metric_Y | Die Metrik, mit der verglichen werden soll. |

### Beispiel

`Metric 1 > Metric 2`


## Größer als oder gleich {#greater-than-or-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ge"
>title="Größer als oder gleich"
>abstract="Größer als oder gleich. Die Ausgabe ist entweder 0 (False) oder 1 (True)."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER THAN OR EQUAL()]**

Größer als oder gleich. Die Ausgabe ist entweder 0 (False) oder 1 (True).

| Argument | Beschreibung |
|---|---|
| metric_X | Die Basismetrik, die Sie zum Vergleich verwenden möchten. |
| metric_Y | Die Metrik, mit der verglichen werden soll. |

### Beispiel

`Metric 1 >= Metric 2`



## Hyperbolic Cosine {#hyperbolic-cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cosh"
>title="Hyperbolic Cosine"
>abstract="Gibt den Cosinus hyperbolicus einer Zahl zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC COSINE(metric)]**


[!BADGE Zeile]{type="Neutral"} Gibt den hyperbolischen Kosinus einer Zahl zurück.


| Argument | Beschreibung |
|---|---|
| metric | Der Winkel in Radianten, für den Sie den Hyperbelkosinus ermitteln möchten |



## Hyperbolic Sine {#hyperbolic-sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sinh"
>title="Hyperbolic Sine"
>abstract="Gibt den Sinus hyperbolicus einer Zahl zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC SINE(metric)]**

[!BADGE Zeile]{type="Neutral"} Gibt den hyperbolischen Sinus einer Zahl zurück.

| Argument | Beschreibung |
|---|---|
| metric | Der Winkel in Radianten, für den Sie den Hyperbelsinus ermitteln möchten |


## Hyperbolic Tangent {#hyperbolic-tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-tanh"
>title="Hyperbolic Tangent"
>abstract="Gibt den Tangens hyperbolicus einer Zahl zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC TANGENT(metric)]**

[!BADGE Zeile]{type="Neutral"} Gibt den hyperbolischen Tangens einer Zahl zurück.

| Argument | Beschreibung |
|---|---|
| metric | Der Winkel in Radianten, dessen hyperbolischer Tangens berechnet werden soll |


## Wenn {#if}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-if"
>title="Wenn"
>abstract="Wenn der Bedingungsparameter einen Wert ungleich null (true) aufweist, ist das Ergebnis der Wert des Parameters „value_if_true“. Andernfalls ist es der Wert des Parameters „value_if_false“."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL IF(logical_test, value_if_true, value_if_false)]**


[!BADGE Zeile]{type="Neutral"} Wenn der Wert des Bedingungsparameters ungleich null (true) ist, ist das Ergebnis der Wert des Parameters value_if_true. Andernfalls ist es der Wert des Parameters „value_if_false“.


| Argument | Beschreibung |
|---|---|
| logical_test | Erforderlich. Wert, der als TRUE oder FALSE ausgewertet werden kann. |
| value_if_true | Der Wert, der ausgegeben werden soll, wenn das Argument des Logiktests also TRUE ausgewertet wird. (Dieses Argument wird automatisch auf 0 gesetzt, wenn es nicht eingesetzt wurde.) |
| value_if_false | Der Wert, der ausgegeben werden soll, wenn das logical_test-Argument als FALSE ausgewertet wird. (Dieses Argument wird automatisch auf 0 gesetzt, wenn es nicht eingesetzt wurde.) |


## Weniger als {#less-than}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-lt"
>title="Weniger als"
>abstract="Die Ausgabe ist entweder 0 (False) oder 1 (True)."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LESS THAN()]**

Die Ausgabe ist entweder 0 (False) oder 1 (True).

| Argument | Beschreibung |
|---|---|
| metric_X | Die Metrik, die Sie vergleichen möchten. |
| metric_Y | Die Metrik, mit der verglichen werden soll. |

### Beispiel

`Metric 1 < Metric 2`


## Kleiner als oder gleich {#less-than-or-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-le"
>title="Kleiner als oder gleich"
>abstract="Kleiner als oder gleich. Die Ausgabe ist entweder 0 (False) oder 1 (True)."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LESS THAN OR EQUAL()]**

Kleiner als oder gleich. Die Ausgabe ist entweder 0 (False) oder 1 (True).

| Argument | Beschreibung |
|---|---|
| metric_X | Die Metrik, die Sie vergleichen möchten. |
| metric_Y | Die Metrik, mit der verglichen werden soll. |

### Beispiel

`Metric 1 <= Metric 2`



## Anstieg {#lift}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-lift"
>title="Anstieg"
>abstract="Der Anstieg des Verhältnisses im Vergleich zum Kontrollwert."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LIFT(Normalisierungs-Container, Erfolgsmetrik, Kontrolle)]**

Der Anstieg des Verhältnisses im Vergleich zum Kontrollwert.

| Argument | Beschreibung |
| --- | --- |
| normalizing-container | Die Grundlage (Personen, Sitzungen oder Ereignisse) für die Ausführung eines Tests. |
| success-metric | Die Metrik oder Metriken, die eine Benutzerin bzw. ein Benutzer verwendet. |
| control | Die Variante, mit der alle anderen Varianten im Experiment verglichen werden. Geben Sie den Namen des Dimensionselements der Kontrollvariante ein. |



## Lineare Regression: Korrelationskoeffizient {#linear-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-linear"
>title="Lineare Regression: Korrelationskoeffizient"
>abstract="Lineare Regression: Y = a X + b.  Gibt den Korrelationskoeffizienten zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabelle]{type="Neutral"} Lineare Regression: Y = a X + b. Gibt den Korrelationskoeffizienten zurück.


| Argument | Beschreibung |
|---|---|
| metric_X | Die Metrik, die mit metric_Y korreliert werden soll |
| metric_Y | Die Metrik, die mit metric_X korreliert werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |



## Lineare Regression: Schnittpunkt {#linear-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-linear"
>title="Lineare Regression: Schnittpunkt"
>abstract="Lineare Regression: Y = a X + b. Gibt b zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabelle]{type="Neutral"} Lineare Regression: Y = a X + b. Gibt b zurück.


| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die als abhängiges Datenelement zugewiesen werden soll |
| metric_Y | Die Metrik, die als unabhängiges Datenelement zugewiesen werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |



## Lineare Regression: Vorhersage für Y {#linear-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-linear"
>title="Lineare Regression: Vorhersage für Y"
>abstract="Lineare Regression: Y = a X + b. Gibt Y zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Zeile]{type="Neutral"} Lineare Regression: Y = a X + b. Gibt Y zurück.


| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die als abhängiges Datenelement zugewiesen werden soll |
| metric_Y | Die Metrik, die als unabhängiges Datenelement zugewiesen werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |



## Lineare Regression: Steigung {#linear-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-linear"
>title="Lineare Regression: Steigung"
>abstract="Lineare Regression: Y = a X + b. Gibt a zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"} Lineare Regression: Y = a X + b. Gibt a zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die als abhängiges Datenelement zugewiesen werden soll |
| metric_Y | Die Metrik, die als unabhängiges Datenelement zugewiesen werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |


## Log Base 10 {#log-base-ten}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-log10"
>title="Log Base 10"
>abstract="Gibt den Logarithmus einer Zahl zur Basis 10 zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LOG BASE 10(metric)]**


[!BADGE Zeile]{type="Neutral"} Gibt den Logarithmus zur Basis 10 einer Zahl zurück.


| Argument | Beschreibung |
|---|---|
| metric | Die positive reale Zahl, deren Logarithmus zur Basis 10 gewünscht ist |


## Logarithmische Regression: Korrelationskoeffizient {#log-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-log"
>title="Logarithmische Regression: Korrelationskoeffizient"
>abstract="Logarithmische Regression: Y = a ln(X) + b. Gibt den Korrelationskoeffizienten zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"} Log-Regression: Y = a ln(X) + b. Gibt den Korrelationskoeffizienten zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Die Metrik, die mit metric_Y korreliert werden soll |
| metric_Y | Die Metrik, die mit metric_X korreliert werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |


## Logarithmische Regression: Schnittpunkt {#log-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-log"
>title="Logarithmische Regression: Schnittpunkt"
>abstract="Logarithmische Regression: Y = a ln(X) + b. Gibt b zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"} Log-Regression: Y = a ln(X) + b. Gibt b zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die als abhängiges Datenelement zugewiesen werden soll |
| metric_Y | Die Metrik, die als unabhängiges Datenelement zugewiesen werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |



## Logarithmische Regression: Vorhersage für Y {#log-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-log"
>title="Logarithmische Regression: Vorhersage für Y"
>abstract="Logarithmische Regression: Y = a ln(X) + b. Gibt Y zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Zeile]{type="Neutral"} Protokollregression: Y = a ln(X) + b. Gibt Y zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die als abhängiges Datenelement zugewiesen werden soll |
| metric_Y | Die Metrik, die als unabhängiges Datenelement zugewiesen werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |



## Logistische Regression: Steigung {#log-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-log"
>title="Logistische Regression: Steigung"
>abstract="Logarithmische Regression: Y = a ln(X) + b. Gibt a zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"} Log-Regression: Y = a ln(X) + b. Gibt a zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die als abhängiges Datenelement zugewiesen werden soll |
| metric_Y | Die Metrik, die als unabhängiges Datenelement zugewiesen werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |



## Natürlicher Logarithmus {#natural-log}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-log"
>title="Natürlicher Logarithmus"
>abstract="Gibt den natürlichen Logarithmus einer Zahl zurück. Natürliche Logarithmen basieren auf der Konstanten e (2.71828182845904). LN ist die Umkehrung der EXP-Funktion."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL NATURAL LOG(metric)]**

Gibt den natürlichen Logarithmus einer Zahl zurück. Natürliche Logarithmen basieren auf der Konstanten e (2.71828182845904). LN ist die Umkehrung der EXP-Funktion.

| Argument | Beschreibung |
|---|---|
| metric | Die positive reale Zahl, deren natürlicher Logarithmus gewünscht ist |



## Nicht {#not}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-not"
>title="Nicht"
>abstract="Negation als boolescher Wert. Die Ausgabe ist entweder 0 (False) oder 1 (True)."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL NOT(logical)]**

Negation als boolescher Wert. Die Ausgabe ist entweder 0 (False) oder 1 (True).

| Argument | Beschreibung |
|---|---|
| logical | Erforderlich. Ein Wert oder Ausdruck, der als TRUE oder FALSE ausgewertet werden kann. |



## Not Equal {#not-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ne"
>title="Not Equal"
>abstract="Ungleich. Die Ausgabe ist entweder 0 (False) oder 1 (True)."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL NOT EQUAL()]**


Ungleich. Die Ausgabe ist entweder 0 (False) oder 1 (True).


| Argument | Beschreibung |
|---|---|
| metric_X | Die Metrik, die Sie vergleichen möchten. |
| metric_Y | Die Metrik, mit der verglichen werden soll. |

### Beispiel

`Metric 1 != Metric 2`


## Oder {#or}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-or"
>title="Oder"
>abstract="ODER-Verknüpfung. „Ungleich null“ gilt als „True“ und „Gleich null“ gilt als „False“. Die Ausgabe ist entweder 0 (False) oder 1 (True)."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL OR(logical_test)]**


[!BADGE Zeile]{type="Neutral"} Trennung. „Ungleich null“ gilt als „True“ und „Gleich null“ gilt als „False“. Die Ausgabe ist entweder 0 (False) oder 1 (True).


| Argument | Beschreibung |
|---|---|
| logical_test | Erfordert mindestens einen Parameter, kann jedoch eine beliebige Anzahl von Parametern annehmen. Jeder Wert oder Ausdruck, der als TRUE oder FALSE ausgewertet werden kann. |


>[!NOTE]
>
>0 (null) bedeutet „Falsch“ und jeder andere Wert „Wahr“.


## Pi {#pi}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-pi"
>title="Pi"
>abstract="Gibt Pi zurück: 3,14159..."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL PI()]**

Gibt Pi zurück: 3,14159...


## Potenzregression: Korrelationskoeffizient {#power-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-power"
>title="Potenzregression: Korrelationskoeffizient"
>abstract="Potenzregression: Y = b X ^ a. Gibt den Korrelationskoeffizienten zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"} Potenzregression: Y = b X ^ a. Gibt den Korrelationskoeffizienten zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Die Metrik, die mit metric_Y korreliert werden soll |
| metric_Y | Die Metrik, die mit metric_X korreliert werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |



## Potenzregression: Schnittpunkt {#power-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-power"
>title="Potenzregression: Schnittpunkt"
>abstract="Potenzregression: Y = b X ^ a. Gibt b zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabelle]{type="Neutral"} Potenzregression: Y = b X ^ a. Gibt b zurück.


| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die als abhängiges Datenelement zugewiesen werden soll |
| metric_Y | Die Metrik, die als unabhängiges Datenelement zugewiesen werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |


## Potenzregression: Vorhersage für Y {#power-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-power"
>title="Potenzregression: Vorhersage für Y"
>abstract="Potenzregression: Y = b X ^ a. Gibt Y zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Zeile]{type="Neutral"} Potenzregression: Y = b X ^ a. Gibt Y zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die als abhängiges Datenelement zugewiesen werden soll |
| metric_Y | Die Metrik, die als unabhängiges Datenelement zugewiesen werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |



## Potenzregression: Steigung {#power-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-power"
>title="Potenzregression: Steigung"
>abstract="Potenzregression: Y = b X ^ a. Gibt a zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"} Potenzregression: Y = b X ^ a. Gibt a zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die als abhängiges Datenelement zugewiesen werden soll |
| metric_Y | Die Metrik, die als unabhängiges Datenelement zugewiesen werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |



## Quadratische Regression: Korrelationskoeffizient {#quadratic-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-quadratic"
>title="Quadratische Regression: Korrelationskoeffizient"
>abstract="Quadratische Regression: Y = (a + bX) ^ 2. Gibt den Korrelationskoeffizienten zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"} Quadratische Regression: Y = (a + bX) ^ 2. Gibt den Korrelationskoeffizienten zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Die Metrik, die mit metric_Y korreliert werden soll |
| metric_Y | Die Metrik, die mit metric_X korreliert werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |

## Quadratische Regression: Schnittpunkt {#quadratic-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-quadratic"
>title="Quadratische Regression: Schnittpunkt"
>abstract="Quadratische Regression: Y = (a + bX) ^ 2. Gibt a zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"} Quadratische Regression: Y = (a + bX) ^ 2. Gibt a zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die als abhängiges Datenelement zugewiesen werden soll |
| metric_Y | Die Metrik, die als unabhängiges Datenelement zugewiesen werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |


## Quadratische Regression: Vorhersage für Y {#quadratic-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-quadratic"
>title="Quadratische Regression: Vorhersage für Y"
>abstract="Quadratische Regression: Y = (a + bX) ^ 2. Gibt Y zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Zeile]{type="Neutral"} Quadratische Regression: Y = (a + bX) ^ 2. Gibt Y zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die als abhängiges Datenelement zugewiesen werden soll |
| metric_Y | Die Metrik, die als unabhängiges Datenelement zugewiesen werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |


## Quadratische Regression: Steigung {#quadratic-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-quadratic"
>title="Quadratische Regression: Steigung"
>abstract="Quadratische Regression: Y = (a + bX) ^ 2. Gibt b zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"} Quadratische Regression: Y = (a + bX) ^ 2. Gibt b zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die als abhängiges Datenelement zugewiesen werden soll |
| metric_Y | Die Metrik, die als unabhängiges Datenelement zugewiesen werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |



## Reziproke Regression: Korrelationskoeffizient {#reciprocal-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-reciprocal"
>title="Reziproke Regression: Korrelationskoeffizient"
>abstract="Reziproke Regression: Y = a + b X ^ -1. Gibt den Korrelationskoeffizienten zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"} Reziproke Regression: Y = a + b X ^ -1. Gibt den Korrelationskoeffizienten zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Die Metrik, die mit metric_Y korreliert werden soll |
| metric_Y | Die Metrik, die mit metric_X korreliert werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |


## Reziproke Regression: Schnittpunkt {#reciprocal-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-reciprocal"
>title="Reziproke Regression: Schnittpunkt"
>abstract="Reziproke Regression: Y = a + b X ^ -1. Gibt a zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"} Reziproke Regression: Y = a + b X ^ -1. Gibt a zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die als abhängiges Datenelement zugewiesen werden soll |
| metric_Y | Die Metrik, die als unabhängiges Datenelement zugewiesen werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |


## Reziproke Regression: Vorhersage für Y {#reciprocal-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-reciprocal"
>title="Reziproke Regression: Vorhersage für Y"
>abstract="Reziproke Regression: Y = a + b X ^ -1. Gibt Y zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Reihe]{type="Neutral"} Reziproke Regression: Y = a + b X ^ -1. Gibt Y zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die als abhängiges Datenelement zugewiesen werden soll |
| metric_Y | Die Metrik, die als unabhängiges Datenelement zugewiesen werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |


## Reziproke Regression: Steigung {#reciprocal-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-reciprocal"
>title="Reziproke Regression: Steigung"
>abstract="Reziproke Regression: Y = a + b X ^ -1. Gibt b zurück."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabelle]{type="Neutral"} Reziproke Regression: Y = a + b X ^ -1. Gibt b zurück.

| Argument | Beschreibung |
|---|---|
| metric_X | Eine Metrik, die als abhängiges Datenelement zugewiesen werden soll |
| metric_Y | Die Metrik, die als unabhängiges Datenelement zugewiesen werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |



## Stichprobenvarianz

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-variance-estimate"
>title="Stichprobenvarianz"
>abstract="Berechnet eine Schätzung der Stichprobenvarianz anhand der Formel (sum(metric^2) / (N - 1)) - (sum(metric))^2/(N*(N-1)). Wobei N die Anzahl des Normalisierungs-Containers ist. <br/>Dies wird im Rahmen von *jederzeit gültigen* Konfidenzberechnungen verwendet. Grundsätzlich ist diese Funktion allein nicht nützlich, sie kann aber verwendet werden, um Berechnungen zu überprüfen oder Konfidenzberechnungen *manuell* durchzuführen."

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL STICHPROBENVARIANZ(Normalisierungs-Container, Erfolgsmetrik)]**

Berechnet eine Schätzung der Stichprobenvarianz.

| Argument | Beschreibung |
| --- | --- |
| normalizing-container | Die Grundlage (Personen, Sitzungen oder Ereignisse) für die Ausführung eines Tests. |
| success-metric | Die Metrik oder Metriken, die eine Benutzerin bzw. ein Benutzer verwendet. |

<!-- markdownlint-enable MD034 -->



## Sine {#sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sin"
>title="Sine"
>abstract="Gibt den Sinus des gegebenen Winkels zurück. Wenn der Winkel in Grad angegeben ist, multiplizieren Sie den Winkel mit PI()/180."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL SINE(metric)]**


[!BADGE Row]{type="Neutral"} Gibt den Sinus des gegebenen Winkels zurück. Wenn der Winkel in Grad angegeben ist, multiplizieren Sie den Winkel mit PI()/180.


| Argument | Beschreibung |
|---|---|
| metric | Der Winkel in Radianten, für den Sie den Sinus ermitteln möchten |




## t-Wert {#t-score}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-t-score"
>title="t-Wert"
>abstract="Die Abweichung vom [ARITHMETISCHEN MITTEL](cm-functions.md#mean) geteilt durch die Standardabweichung. Alias für [Z-Score](#z-score)."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL T-SCORE(metric, include_zeros)]**

Die Abweichung vom [ARITHMETISCHEN MITTEL](cm-functions.md#mean) geteilt durch die Standardabweichung. Alias für [Z-Score](#z-score).

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die der t-Wert angezeigt werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |


## t-Test {#t-test}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-t-test"
>title="t-Test"
>abstract="Führt einen m-seitigen t-Test mit einem t-Wert von x und n Freiheitsgraden durch."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL T-TEST(metric, degrees, tails)]**

Führt einen m-seitigen t-Test mit einem t-Wert von x und n Freiheitsgraden durch.

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die ein t-Test durchgeführt werden soll |
| degrees | Die Freiheitsgrade |
| Longtails | Die Länge des Longtails, der für die Durchführung des t-Tests verwendet werden soll |

### Details

Die Signatur ist T-TEST(metric, degrees, tails). Darunter wird einfach ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-T(-ABSOLUTE VALUE(tails), degrees)]](#cdf-t)** aufgerufen. Diese Funktion ähnelt der **[Z-TEST](#z-test)**-Funktion, die ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-Z(-ABSOLUTE VALUE(tails))]](#cdf-z)** ausführt.

- ***m*** ist die Anzahl der Longtails.
- ***n*** ist der Freiheitsgrad. Dies sollte eine konstante Zahl für den gesamten Bericht sein, d. h., sie ändert sich nicht Zeile für Zeile.
- ***X*** ist die t-Test-Statistik. Hierbei handelt es sich häufig um eine auf einer Metrik basierende Formel (z. B. **[Z-WERT](#z-score)**), die in jeder Zeile bewertet wird.

Der Rückgabewert ist die Wahrscheinlichkeit, die Teststatistik x zu erhalten, bei gegebenen Freiheitsgraden und der Anzahl an Seiten.

### Beispiele

1. Verwenden Sie die Funktion zum Auffinden von Ausreißern:

   ```
   T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2)
   ```

1. Kombinieren Sie die Funktion mit **[IF](#if)**, um sehr hohe oder niedrige Bounce-Raten zu ignorieren und alle weiteren Sitzungen zu zählen:

   ```
   IF(T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2) < 0.01, 0, sessions )
   ```



## Tangente {#tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-tan"
>title="Tangente"
>abstract="Gibt den Tangens des gegebenen Winkels zurück. Wenn der Winkel in Grad angegeben ist, multiplizieren Sie den Winkel mit PI()/180."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL TANGENT(metric)]**

Gibt den Tangens des gegebenen Winkels zurück. Wenn der Winkel in Grad angegeben ist, multiplizieren Sie den Winkel mit PI()/180.

| Argument | Beschreibung |
|---|---|
| metric | Der Winkel in Radianten, für den Sie die Tangente ermitteln möchten |



## Z-Score {#z-score}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-z-score"
>title="Z-Score"
>abstract="Die Abweichung vom arithmetischen Mittel geteilt durch die Standardabweichung."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL Z-SCORE(metric, include_zeros)]**

[!BADGE Zeile]{type="Neutral"} Die Abweichung vom Mittelwert dividiert durch die Standardabweichung.

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die der z-Wert angezeigt werden soll |
| include_zeros | Gibt an, ob Nullwerte in die Berechnungen einbezogen werden sollen oder nicht |

Ein z-Wert von 0 (null) gibt an, dass der Wert mit dem arithmetischen Mittel identisch ist. Eine z-Transformation kann positiv oder negativ sein, abhängig davon, ob sie über oder unter dem arithmetischen Mittel liegt und um wie viele Standardabweichungen es sich handelt.

Die Gleichung für z-Transformation lautet:

![](assets/z_score.png)

Dabei ist ***[!DNL x]*** der Rohwert, ***[!DNL μ]*** das arithmetische Mittel der Population und ***[!DNL σ]*** die Standardabweichung der Population.

>[!NOTE]
>
>***[!DNL μ]*** (Mu) und ***[!DNL σ]*** (Sigma) werden automatisch aus der Metrik berechnet.



## z-Test {#z-test}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-z-test"
>title="z-Test"
>abstract="Führt einen n-seitigen z-Test mit einem z-Wert von x durch."

<!-- markdownlint-enable MD034 -->

![Effekt](/help/assets/icons/Effect.svg) **[!UICONTROL Z-TEST(metric_tails)]**

Führt einen n-seitigen z-Test mit einem z-Wert von x durch.

| Argument | Beschreibung |
|---|---|
| metric | Die Metrik, für die ein z-Test durchgeführt werden soll |
| Longtails | Die Länge des Longtails, der für die Durchführung des z-Tests verwendet werden soll |

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