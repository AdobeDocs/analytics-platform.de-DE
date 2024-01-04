---
description: Ermöglicht die einfache Visualisierung von Vergleichsdaten in Analysis Workspace, z. B. das Erstellen von Vergleichen mit dem letzten Monat, dem letzten Jahr usw.
title: Visualisierung von Kombinationsdiagrammen
feature: Visualizations
exl-id: 06faa997-3a4e-4c41-b64e-64a15ada6552
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 85%

---

# Kombinationsdiagramm

Mit der Visualisierung [!UICONTROL Kombinationsdiagramm] können Sie schnell und einfach einen Vergleich darstellen, ohne zuerst eine Tabelle erstellen zu müssen. Die Entwicklung Ihrer Daten wird dabei durch eine Kombination aus Linien und Balken dargestellt.

Verwenden Sie eine [!UICONTROL Combo-Diagramm] an:

* Vergleichen der Bestellungen dieser Woche mit denen im letzten Monat (und im letzten Jahr) – alles mit nur wenigen Klicks.
* Schnelles Analysieren und Vergleichen mehrerer Metriken (z. B. [!UICONTROL Unique Visitors] und [!UICONTROL Umsatz]) im selben Diagramm.
* Analysieren einer Metrik anhand einer Funktion (z. B. [!UICONTROL Kumulativer Durchschnitt]) in einem bestimmten Zeitrahmen.

Beachten Sie:

* Sie können einem einzigen [!UICONTROL Kombinationsdiagramm] mehrere Vergleiche hinzufügen.
* Wenn Sie einen oder mehrere Vergleiche hinzufügen, müssen diese vom gleichen Typ sein, z. B. [!UICONTROL ein Zeitvergleich].
* Sie können bis zu 5 Vergleiche hinzufügen.
* Sie können bis zu 3 Filter auf eine Metrik anwenden.
* Berechnete Metriken werden in Kombinationsdiagrammen nicht unterstützt.

## Erstellen eines Kombinationsdiagramms

1. Ziehen Sie aus der Visualisierungs-Dropdown-Liste in der linken Leiste die Visualisierung [!UICONTROL Kombinationsdiagramm] in ein leeres Bedienfeld.

   ![Combo-Diagramm mit der X- und Y-Achse und dem Optionsfeld](assets/combo-chart-build.png)

1. Wählen Sie aus den Dropdown-Listen eine Dimension für die X-Achse und eine Metrik für die Y-Achse aus.

1. Wählen Sie den Typ des [!UICONTROL Linienvergleichs] aus, den Sie verwenden möchten.

   | Linienvergleichstyp | Definition |
   | --- | --- |
   | **[!UICONTROL Zeitvergleich]** | Der häufigste Vergleichstyp, z. B. Vergleich dieses Zeitraums mit dem vor 4 Wochen. Wenn Sie [!UICONTROL Zeitvergleich] auswählen, führen Sie eine zweite Auswahl durch, um anzugeben, mit welchem Zeitraum der Vergleich durchgeführt werden soll.<p>![Vergleich mit ausgewähltem Zeitraum und sekundäres Auswahlfeld für Zeitraum.](assets/combo-time-period.png) |
   | **[!UICONTROL Funktion]** | Sie können zum Vergleich eine Funktion wie [!UICONTROL Durchschnitt] hinzufügen. Eine Liste der unterstützten Funktionen finden Sie unten.<p>![Ein Dropdown-Menü für einen Vergleich mit ausgewählten Funktionen und einer Liste der verfügbaren unterstützten Funktionen.](assets/combo-functions.png) |
   | **[!UICONTROL Sekundäre Metrik]** | Sie können beispielsweise den [!UICONTROL Umsatz] mit einer anderen Metrik vergleichen.<p>![Ein Combo-Diagramm, das zwei Metriken vergleicht.](assets/combo-2metrics.png) |

   {style="table-layout:auto"}

1. Klicken Sie auf **[!UICONTROL Erstellen]**.

   Die Ausgabe sieht in etwa so aus:

   ![Ein Combo-Diagramm, das den aktuellen Zeitraum in einem Balkendiagramm und einem Vergleichszeitraum im Liniendiagramm anzeigt ](assets/combo-output.png)

   Der aktuelle Zeitraum wird im Balkendiagramm angezeigt und der Vergleichszeitraum wird durch das Liniendiagramm dargestellt. Die Punkte im Liniendiagramm werden als „Datenpunkte“ bezeichnet.

## Unterstützte Funktionen

Wenn Sie **[!UICONTROL Funktion]** als [!UICONTROL Linienvergleichstyp] auswählen, wird eine Funktion der gewählten Metrik zurückgegeben.

| Funktion | Definition |
| --- | --- |
| **[!UICONTROL Spaltensumme]** | Addiert alle numerischen Werte für eine Metrik innerhalb einer Spalte (über die Elemente einer Dimension hinweg) |
| **[!UICONTROL Kumulativer Durchschnitt]** | Gibt den Durchschnitt der letzten N Zeilen zurück. |
| **[!UICONTROL Median]** | Gibt den Medianwert für eine Metrik in einer Spalte zurück. Der Medianwert ist die Zahl in der Mitte eines Zahlensatzes, d. h. die Hälfte der Zahlen hat Werte größer oder gleich dem Medianwert und die Hälfte ist kleiner oder gleich dem Medianwert. |
| **[!UICONTROL Kumulativ]** | Die kumulative Summe von N Zeilen. |
| **[!UICONTROL Spaltenmaximum]** | Gibt den größten Wert in einem Satz aus Dimensionselementen für eine Metrikspalte zurück. |
| **[!UICONTROL Mittel]** | Gibt das arithmetische Mittel (bzw. den Durchschnitt) einer Metrik zurück. |
| **[!UICONTROL Spaltenminimum]** | Gibt den kleinsten Wert in einem Satz aus Dimensionselementen für eine Metrikspalte zurück. |

{style="table-layout:auto"}

Im Folgenden finden Sie ein Beispiel für den kumulativen Durchschnitt der Umsatzmetrik:

![Ein Combo-Diagramm mit dem kumulativen Durchschnitt](assets/combo-cumul-avg.png)

Im Folgenden finden Sie ein Beispiel für ein Kombinationsdiagramm mit den Funktionen „Kumulativer Durchschnitt“ und „Mittel“:

![Ein Combo-Diagramm, das sowohl die durchschnittliche als auch die mittlere Funktion anzeigt.](assets/combo-two-functions.png)

## Einstellungen des Kombinationsdiagramms

Klicken Sie in einem Kombinationsdiagramm oben rechts auf das Zahnradsymbol, um die Einstellungen des Diagramms zu ändern.

![Ansicht &quot;Combo chart Settings&quot;mit den unten beschriebenen Optionen.](assets/combo-settings.png)

| Einstellung | Definition |
| --- | --- |
| **[!UICONTROL Visualisierungstyp]** | Hiermit können Sie zu einem anderen Visualisierungstyp wechseln. |
| **[!UICONTROL Granularität]** | Für Trend-Visualisierungen können Sie die Zeitgranularität (Tag, Woche, Monat usw.) aus dieser Dropdown-Liste. |
| **[!UICONTROL Allgemein]** |  |
| **[!UICONTROL Prozentsätze]** | Zeigt Werte als Prozentzahlen an. |
| **[!UICONTROL Legende eingeblendet]** | Ermöglicht das Ausblenden des detaillierten Legendentextes für die Kombinationsdiagramm-Visualisierung. |
| **[!UICONTROL Grenzwert für max. Anzahl von Elementen]** | Reduziert die Anzahl der Elemente auf der X-Achse. Wenn Sie einen großen Datensatz haben, zeigen Sie möglicherweise nur die ersten 10 Elemente (oder einen beliebigen Wert) an. |
| **[!UICONTROL Überlagerungen]** | Ein- oder Ausblenden von Datenpunkten auf Linien. |
| **[!UICONTROL Achse]** | |
| **[!UICONTROL Zwei Achsen anzeigen]** | Gilt nur, wenn Sie zwei Metriken haben – möglich sind eine Y-Achse links (für die eine Metrik) und eine rechts (für die andere). Dies ist hilfreich, wenn grafisch dargestellte Metriken sehr unterschiedliche Größenordnungen aufweisen. Die Farbe der Doppelachse entspricht der Farbe der Tabelle, es sei denn, es gibt mehrere Vergleiche. In diesem Fall ist die Farbe für alle Vergleiche grau. |
| **[!UICONTROL Normalisierung]** | Erzwingt Metriken für gleiche Anteile. Dies ist hilfreich, wenn grafisch dargestellte Metriken sehr unterschiedliche Größenordnungen aufweisen. |
| **[!UICONTROL X-Achse anzeigen]** | Zeigen Sie die X-Achse an oder blenden Sie sie aus. |
| **[!UICONTROL y-Achse anzeigen]** | Zeigen Sie die Y-Achse an oder blenden Sie sie aus. |
| **[!UICONTROL Y-Achse bei null verankern]** | Wenn alle im Diagramm dargestellten Werte deutlich größer als null sind, wird der untere Teil der Y-Achse standardmäßig zu NICHT-NULL gemacht. Wenn Sie dieses Kontrollkästchen aktivieren, wird die Y-Achse zwangsweise auf null gesetzt (und das Diagramm neu gezeichnet). |

{style="table-layout:auto"}
