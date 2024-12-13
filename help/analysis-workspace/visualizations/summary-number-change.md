---
description: Verwenden Sie die Visualisierungen von Zusammenfassungsnummern und Zusammenfassungsänderungen, um wichtige Datenpunkte in einem Projekt anzuzeigen.
title: Sammelnummer und Sammeländerung
feature: Visualizations
exl-id: 8872fc58-0957-415d-9958-ce564612ce87
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 51%

---

# Zusammenfassungsnummer und Zusammenfassungsänderung

## Zusammenfassungszahl {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="Zusammenfassungszahl"
>abstract="Erstellen Sie eine Visualisierung, die die Summen und Zwischensummen anzeigt."

<!-- markdownlint-enable MD034 -->

Verwenden Sie die Visualisierung ![Zusammenfassen](/help/assets/icons/123.svg) **[!UICONTROL Zusammenfassungsnummer]**, um eine große Zahl hervorzuheben, die in einem Projekt wichtig ist. Diese Visualisierung verhält sich mithilfe der zugehörigen Datenquelle wie folgt:

* Wenn keine Zelle ausgewählt ist, wird die gesamte Spalte ausgewählt.
* Wenn eine einzelne Zelle ausgewählt ist, wird die Zusammenfassung für diese Zelle angezeigt.
* Wenn mehr als eine Zelle ausgewählt ist, wird die zuerst ausgewählte Zelle angezeigt.
* Wenn die Spalte ausgewählt ist, wird der erste Zellenwert in der Spalte verwendet.

![Visualisierung der Zusammenfassungszahl](asses/../assets/summary-number.png)

Im Rahmen der Visualisierungseinstellungen sind spezifische Optionen für Zusammenfassungsnummern verfügbar.

| Option | Definition |
|--- |--- |
| **[!UICONTROL Wert kürzen]** | Wählen Sie **[!UICONTROL Wert abkürzen]**, um den Zahlenwert intelligent zu kürzen. Wenn ausgewählt, geben Sie eine Zahl ein, um den Betrag der Abkürzung zu definieren. Beispiel:<br/><table><tr><td>**Ausgangswert**</td><td>**Abkürzungswert**</td><td>**Ergebnis**</td></tr><tr><td>12 011 141,25 $</td><td>Nicht ausgewählt</td><td  align="right">12 011 141,25 $</td></tr><tr><td>12 011 141,25 $</td><td>Ausgewählt, auf `0` gesetzt</td><td align="right">12 Mio. $</td></tr><tr><td>12 011 141,25 $</td><td> Ausgewählt, auf `1` gesetzt</td><td  align="right">12,0 Mio. $</td></tr><tr><td>12 011 141,25 $</td><td>Ausgewählt, auf `2` gesetzt</td><td align="right">12,01 Mio. $</td></tr><tr><td>12 011 141,25 $</td><td>Ausgewählt, auf `3` gesetzt</td><td align="right">12,011 Mio. $</td></tr></table> |
| **[!UICONTROL Wert zusammenfassen nach]** | Wählen Sie diese Option, um für ausgewählte Daten das Maximum, das Minimum, den Mittelwert, den Median oder die Summe anzuzeigen. |

## Zusammenfassungsänderung {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="Zusammenfassungsänderung"
>abstract="Erstellen Sie eine Visualisierung, die das Delta (die Änderung) zwischen zwei Zahlen anzeigt."

<!-- markdownlint-enable MD034 -->


Verwenden Sie die Visualisierung ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) **[!UICONTROL Zusammenfassungsänderung]**, um das Delta (die Änderung) zwischen zwei Zahlen anzuzeigen. <!-- This is applicable for AA, not CJA: The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.-->

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.
-->

Diese Visualisierung verhält sich folgendermaßen:

* Wenn keine Zelle ausgewählt ist, werden die ersten beiden Zellenwerte in der Spalte verglichen.
* Wenn eine Zelle ausgewählt ist, wird 0 angezeigt, weil der Zellenwert mit sich selbst verglichen wird.
* Wenn zwei Zellen ausgewählt sind, wird die erste ausgewählte Zelle als Numerator und die zweite als Denominator verwendet.
* Wenn mehr als zwei Zellen ausgewählt sind, werden nur die ersten beiden Zellen für den Vergleich berücksichtigt.
* Wenn ein Zellbereich ausgewählt ist, wird die erste Zelle mit den letzten im Bereich ausgewählten Zellen verglichen.
* Wenn die Spalte ausgewählt ist, wird der erste Wert mit sich selbst verglichen, sodass eine Änderung von 0 angezeigt wird.


![Visualisierung der Zusammenfassungsänderung mit dem Delta zwischen zwei Zahlen.s](assets/summary-change.png)


Im Rahmen der Visualisierungseinstellungen sind bestimmte **[!UICONTROL Zusammenfassungsänderungsoptionen]** verfügbar.

| Option | Definition |
|--- |--- |
| **[!UICONTROL Prozentuale Veränderung anzeigen]** | Zeigt die prozentuale Änderung zwischen den beiden Zahlen an. |
| **[!UICONTROL Rohdifferenz anzeigen]** | Den Rohunterschied zwischen den 2 Zahlen anzeigen. Mit dieser Option können Sie auch Werte kürzen und bis zu 3 Dezimalstellen anzeigen. |
| **[!UICONTROL Wert kürzen]** | Wählen Sie **[!UICONTROL Wert abkürzen]**, um den geänderten Wert intelligent zu kürzen. Wenn ausgewählt, geben Sie eine Zahl ein, um den Betrag der Abkürzung zu definieren. Beispiel:<br/><table><tr><td>**Ausgangswert**</td><td>**Abkürzungswert**</td><td>**Ergebnis**</td></tr><tr><td>12 011 141,25 $</td><td>Nicht ausgewählt</td><td  align="right">12 011 141,25 $</td></tr><tr><td>12 011 141,25 $</td><td>Ausgewählt, auf `0` gesetzt</td><td align="right">12 Mio. $</td></tr><tr><td>12 011 141,25 $</td><td> Ausgewählt, auf `1` gesetzt</td><td  align="right">12,0 Mio. $</td></tr><tr><td>12 011 141,25 $</td><td>Ausgewählt, auf `2` gesetzt</td><td align="right">12,01 Mio. $</td></tr><tr><td>12 011 141,25 $</td><td>Ausgewählt, auf `3` gesetzt</td><td align="right">12,011 Mio. $</td></tr></table> |

>[!MORELIKETHIS]
>
>[Hinzufügen einer Visualisierung zu einem Bedienfeld](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualisierungseinstellungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Kontextmenü der Visualisierung](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
