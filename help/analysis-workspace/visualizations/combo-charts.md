---
description: Visualisieren Sie auf einfache Weise Vergleichsdaten in Analysis Workspace, z. B. durch Erstellen von Vergleichen mit dem letzten Monat, dem letzten Jahr usw.
title: Visualisierung von Kombinationsdiagrammen
feature: Visualizations
exl-id: 06faa997-3a4e-4c41-b64e-64a15ada6552
role: User
source-git-commit: acb4d9269d604857eaef80466d6f7b9b46d53c26
workflow-type: ht
source-wordcount: '603'
ht-degree: 100%

---

# Kombination {#combo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_combo_button"
>title="Kombination"
>abstract="Erstellen Sie schnell eine Visualisierung eines Kombinationsdiagramms, ohne dass Sie zuerst eine Freiformtabelle erstellen müssen."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_In diesem Artikel wird die Visualisierung Kombination in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** beschrieben._

_Unter [Kombination](https://experienceleague.adobe.com/de/docs/analytics/analyze/analysis-workspace/visualizations/combo-charts) finden Sie die Version dieses Artikels für_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._

>[!ENDSHADEBOX]


Mit der Visualisierung ![Combo chart](/help/assets/icons/ComboChart.svg) **[!UICONTROL Kombination]** können Sie schnell und einfach eine Vergleichsvisualisierung erstellen, ohne zuerst eine Tabelle erstellen zu müssen. Sie können Trends in Ihren Daten einfach in einer Kombination aus Linien- und Balkendiagramm anzeigen.

Sie können eine [!UICONTROL Kombination] für Folgendes verwenden:

* Vergleichen der Bestellungen dieser Woche mit denen zur selben Zeit im letzten Monat (und im letzten Jahr).
* Schnelles Analysieren und Vergleichen mehrerer Metriken (z. B. [!UICONTROL Personen] und [!UICONTROL Umsatz]) im selben Diagramm.
* Analysieren einer Metrik anhand einer Funktion (z. B. [!UICONTROL Kumulativer Durchschnitt]) in einem bestimmten Zeitrahmen.

Bedenken Sie Folgendes:

* Sie können einem einzigen [!UICONTROL Kombinationsdiagramm] mehrere Vergleiche hinzufügen.
* Wenn Sie einen oder mehrere Vergleiche hinzufügen, müssen diese vom gleichen Typ sein, z. B. [!UICONTROL ein Zeitvergleich].
* Sie können bis zu 5 Vergleiche hinzufügen.
* Sie können bis zu 3 Filter auf eine Metrik anwenden.
* Berechnete Metriken werden in Kombinationsdiagrammen nicht unterstützt.

## Verwenden

1. Fügen Sie eine Visualisierung des Typs ![Comment](/help/assets/icons/ComboChart.svg) [!UICONTROL Kombination] hinzu. Siehe [Hinzufügen einer Visualisierung zu einem Panel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)

1. Wählen Sie aus den Dropdown-Listen eine Dimension für die X-Achse und eine Metrik für die Y-Achse aus.

1. Wählen Sie den Typ des [!UICONTROL Linienvergleichs] aus, den Sie verwenden möchten.

   | Linienvergleichstyp | Definition |
   | --- | --- |
   | **[!UICONTROL Zeitvergleich]** | Der häufigste Vergleichstyp, z. B. Vergleich dieses Zeitraums mit dem vor 4 Wochen. Wenn Sie [!UICONTROL Zeitvergleich] auswählen, führen Sie eine zweite Auswahl durch, um anzugeben, mit welchem Zeitraum der Vergleich durchgeführt werden soll.<p>![Linienvergleich mit ausgewähltem Zeitraum und sekundärem Auswahlfeld für Zeitraum.](assets/combo-time-period.png) |
   | **[!UICONTROL Funktion]** | Sie können zum Vergleich eine Funktion wie [!UICONTROL Durchschnitt] hinzufügen. Hier finden Sie eine Liste der [unterstützten Funktionen](#supported-functions).<p>![Dropdown-Menü Linienvergleich mit ausgewählten Funktionen und einer Liste der verfügbaren unterstützten Funktionen.](assets/combo-functions.png) |
   | **[!UICONTROL Sekundäre Metrik]** | Sie können beispielsweise den [!UICONTROL Umsatz] mit einer anderen Metrik vergleichen.<p>![Ein Kombinationsdiagramm, in dem zwei Metriken verglichen werden.](assets/combo-2metrics-settings.png) |

   {style="table-layout:auto"}

1. Wählen Sie **[!UICONTROL Erstellen]** aus.

   Die Ausgabe sieht in etwa so aus:

   ![Ein Kombinationsdiagramm, das den aktuellen Zeitraum in einem Balkendiagramm und den Vergleichszeitraum in einem Liniendiagramm anzeigt ](assets/combo-output.png)

   Der aktuelle Zeitraum wird als Balkendiagramm angezeigt. Das Liniendiagramm stellt den Vergleichszeitraum dar. Die Punkte im Liniendiagramm werden als *Datenpunkte* bezeichnet.

## Unterstützte Funktionen

Wenn Sie **[!UICONTROL Funktion]** als den [!UICONTROL Linienvergleichstyp] auswählen, wird eine Funktion der gewählten Metrik zurückgegeben.

| Funktion | Definition |
| --- | --- |
| **[!UICONTROL Spaltensumme]** | Addiert alle numerischen Werte für eine Metrik innerhalb einer Spalte (über die Elemente einer Dimension hinweg) |
| **[!UICONTROL Kumulativer Durchschnitt]** | Gibt den Durchschnitt der letzten N Zeilen zurück. |
| **[!UICONTROL Median]** | Gibt den Medianwert für eine Metrik in einer Spalte zurück. Der Median ist die Zahl in der Mitte einer Zahlenreihe. Die Hälfte der Zahlen weist Werte auf, die größer als oder gleich dem Median sind, und die Hälfte der Zahlen weist Werte auf, die kleiner als oder gleich dem Median sind. |
| **[!UICONTROL Kumulativ]** | Die kumulative Summe von N Zeilen. |
| **[!UICONTROL Spaltenmaximum]** | Gibt den größten Wert in einem Satz aus Dimensionselementen für eine Metrikspalte zurück. |
| **[!UICONTROL Mittel]** | Gibt das arithmetische Mittel (bzw. den Durchschnitt) einer Metrik zurück. |
| **[!UICONTROL Spaltenminimum]** | Gibt den kleinsten Wert in einem Satz aus Dimensionselementen für eine Metrikspalte zurück. |

{style="table-layout:auto"}

Im Folgenden finden Sie ein Beispiel für den kumulativen Durchschnitt der Umsatzmetrik:

![Ein Kombinationsdiagramm, das den kumulativen Durchschnitt anzeigt](assets/combo-cumul-avg.png)

Im Folgenden finden Sie ein Beispiel für ein Kombinationsdiagramm mit den Funktionen „Kumulativer Durchschnitt“ und „Mittel“:

![Ein Kombinationsdiagramm, das sowohl die Funktion Kumulativer Durchschnitt als auch die Funktion Median anzeigt.](assets/combo-three-functions.png)

>[!MORELIKETHIS]
>
>[Hinzufügen einer Visualisierung zu einem Panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualisierungseinstellungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Kontextmenü der Visualisierung](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
