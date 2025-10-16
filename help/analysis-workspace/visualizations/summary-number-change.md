---
description: Verwenden Sie die Visualisierungen „Zusammenfassungszahl“ und „Zusammenfassungsänderung“, um wichtige Datenpunkte in einem Projekt anzuzeigen.
title: Zusammenfassungsnummer und Zusammenfassungsänderung
feature: Visualizations
exl-id: 8872fc58-0957-415d-9958-ce564612ce87
role: User
source-git-commit: 639c3d3c349615078c76f8806bcd5bb458b0f6f2
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 69%

---

# Zusammenfassungszahl und -änderung

>[!BEGINSHADEBOX]

_In diesem Artikel werden die Visualisierungen von Zusammenfassungszahlen und Zusammenfassungsänderungen in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** beschrieben._<br/>_Unter [Zusammenfassungszahl und Zusammenfassungsänderung](https://experienceleague.adobe.com/de/docs/analytics/analyze/analysis-workspace/visualizations/summary-number-change) finden Sie die Version dieses Artikels für_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Unter ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visualisierungen von Zusammenfassungszahlen und Zusammenfassungsänderungen](https://video.tv.adobe.com/v/335564/?quality=12&learn=on){target="_blank"} finden Sie ein Demovideo.

>[!ENDSHADEBOX]

## Zusammenfassungszahl {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="Zusammenfassungszahl"
>abstract="Erstellen Sie eine Visualisierung, die die Summen und Zwischensummen anzeigt."

<!-- markdownlint-enable MD034 -->

Verwenden Sie die Visualisierung ![Summary](/help/assets/icons/123.svg) **[!UICONTROL Zusammenfassungszahl]**, um eine große Zahl hervorzuheben, die in einem Projekt wichtig ist. Diese Visualisierung verhält sich mithilfe der zugehörigen Datenquelle wie folgt:

* Wählt die Gesamtsumme der Spalte aus, wenn keine Zelle ausgewählt ist.
* Bei Auswahl einer einzelnen Zelle wird die Zusammenfassung für diese Zelle angezeigt.
* Wenn mehr als eine Zelle ausgewählt ist, wird die erste ausgewählte Zelle angezeigt.
* Wenn die Spalte ausgewählt ist, wird der erste Zellenwert in der Spalte ausgewählt.

![Visualisierung „Zusammenfassungszahl“](asses/../assets/summary-number.png)

Im Rahmen der Visualisierungseinstellungen sind bestimmte Optionen für die Zusammenfassungszahl verfügbar.

| Option | Definition |
|--- |--- |
| **[!UICONTROL Wert kürzen]** | Wählen Sie **[!UICONTROL Wert abkürzen]**, um den Zahlenwert intelligent zu kürzen. Wenn diese Option ausgewählt ist, geben Sie eine Zahl ein, um den Umfang der Abkürzung zu definieren. Beispiel:<br/><table><tr><td>**Originalwert**</td><td>**Abgekürzter Wert**</td><td>**Ergebnis**</td></tr><tr><td>12.011.141,25 USD</td><td>Nicht ausgewählt</td><td  align="right">12.011.141,25 USD</td></tr><tr><td>12.011.141,25 USD</td><td>Ausgewählt, auf `0` gesetzt</td><td align="right">12 Mio. USD</td></tr><tr><td>12.011.141,25 USD</td><td> Ausgewählt, auf `1` gesetzt</td><td  align="right">12,0 Mio. USD</td></tr><tr><td>12.011.141,25 USD</td><td>Ausgewählt, auf `2` gesetzt</td><td align="right">12,01 Mio. USD</td></tr><tr><td>12.011.141,25 USD</td><td>Ausgewählt, auf `3` gesetzt</td><td align="right">12,01 Mio. USD</td></tr></table> |
| **[!UICONTROL Wert zusammenfassen nach]** | Wählen Sie diese Option, um für ausgewählte Daten das Maximum, das Minimum, den Mittelwert, den Median oder die Summe anzuzeigen. |

## Zusammenfassungsänderung {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="Zusammenfassungsänderung"
>abstract="Erstellen Sie eine Visualisierung, die das Delta (die Änderung) zwischen zwei Zahlen anzeigt"

<!-- markdownlint-enable MD034 -->


Verwenden Sie die Visualisierung ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) **[!UICONTROL Zusammenfassungsänderung]**, um das Delta (die Änderung) zwischen zwei Zahlen anzuzeigen. <!-- This is applicable for AA, not CJA: The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.-->

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.
-->

Diese Visualisierung verhält sich folgendermaßen:

* Wenn keine Zelle ausgewählt ist, werden die ersten beiden Zellwerte in der Spalte verglichen.
* Bei ausgewählter Zelle wird 0 angezeigt, da der Zellwert mit sich selbst verglichen wird.
* Wenn zwei Zellen ausgewählt sind, wird die erste ausgewählte Zelle als Zähler und die zweite als Nenner genommen.
* Wenn mehr als zwei Zellen ausgewählt sind, werden nur die ersten beiden zum Vergleich berücksichtigt.
* Wenn ein Zellenbereich ausgewählt ist, wird die erste mit der letzten im Bereich ausgewählten Zelle verglichen.
* Wenn die Spalte ausgewählt ist, wird der erste Wert mit sich selbst verglichen, was eine Änderung von 0 anzeigt.


![Visualisierung „Zusammenfassungsänderung“ mit dem Delta zwischen zwei Zahlen.](assets/summary-change.png)


Im Rahmen der Visualisierungseinstellungen sind bestimmte **[!UICONTROL Optionen für die Zusammenfassungsänderung]** verfügbar.

| Option | Definition |
|--- |--- |
| **[!UICONTROL Prozentänderung zeigen]** | Zeigen Sie die prozentuale Änderung zwischen den beiden Zahlen an. |
| **[!UICONTROL Rohdifferenz anzeigen]** | Zeigen Sie die Rohdifferenz zwischen den beiden Zahlen an. Mit dieser Option können Sie auch Werte kürzen und bis zu 3 Dezimalstellen anzeigen. |
| **[!UICONTROL Wert kürzen]** | Wählen Sie **[!UICONTROL Wert abkürzen]**, um den geänderten Wert intelligent zu kürzen. Wenn diese Option ausgewählt ist, geben Sie eine Zahl ein, um den Umfang der Abkürzung zu definieren. Beispiel:<br/><table><tr><td>**Originalwert**</td><td>**Abgekürzter Wert**</td><td>**Ergebnis**</td></tr><tr><td>12.011.141,25 USD</td><td>Nicht ausgewählt</td><td  align="right">12.011.141,25 USD</td></tr><tr><td>12.011.141,25 USD</td><td>Ausgewählt, auf `0` gesetzt</td><td align="right">12 Mio. USD</td></tr><tr><td>12.011.141,25 USD</td><td> Ausgewählt, auf `1` gesetzt</td><td  align="right">12,0 Mio. USD</td></tr><tr><td>12.011.141,25 USD</td><td>Ausgewählt, auf `2` gesetzt</td><td align="right">12,01 Mio. USD</td></tr><tr><td>12.011.141,25 USD</td><td>Ausgewählt, auf `3` gesetzt</td><td align="right">12,01 Mio. USD</td></tr></table> |

>[!MORELIKETHIS]
>
>[Hinzufügen einer Visualisierung zu einem Panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>>[Visualisierungseinstellungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>>[Kontextmenü der Visualisierung](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
