---
description: Verwenden Sie die Visualisierung der Schlüsselmetrik-Zusammenfassung, um die Leistung der Kennzahlen über zwei Timelines hinweg zu vergleichen.
title: Zusammenfassung einer Schlüsselmetrik
feature: Visualizations
exl-id: ef606c53-b370-419a-904b-573ee6d70a8d
role: User
source-git-commit: 1dff53e244e5d231e7075ce087705e33e0978096
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 38%

---

# Zusammenfassung einer Schlüsselmetrik {#key-metric-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_keymetricsummary_button"
>title="Zusammenfassung einer Schlüsselmetrik"
>abstract="Erstellen Sie eine Visualisierung, die aus den Diagrammen für Zeilen-, Zusammenfassungsänderung und Zusammenfassungsnummer besteht. Verwenden Sie diese Visualisierung, um zu vergleichen, wie wichtige Metriken zwischen zwei Zeiträumen im Trend verlaufen."

<!-- markdownlint-enable MD034 -->


Mit der Visualisierung ![Schlüsselmetriken](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Schlüsselmetrik-Zusammenfassung]** können Sie sehen, wie eine wichtige Metrik innerhalb eines einzigen Zeitrahmens in Trends gerät. Außerdem können Sie damit die Leistung von Metriken über zwei Zeitrahmen hinweg vergleichen. Sie bietet die Vorteile mehrerer Visualisierungen, die in einer Visualisierung kombiniert werden:

* **[!UICONTROL Linienvisualisierung]** zeigt, wie die Metrik Trends für die primären und Vergleichsdatumsbereiche verwendet.

* **[!UICONTROL Veränderung des Zusammenfassungs-Prozentsatzes]** zeigt die Metrikerhöhung oder -verringerung zwischen dem primären und dem Vergleichsdatumsbereich

* Aktueller Gesamtwert ([!UICONTROL **Summenzahl**]) für die Metrik

Diese Visualisierung eignet sich für eine Vielzahl gängiger Anwendungsfälle, darunter:

* Ein Analyst, der versucht zu verstehen, wie die Entwicklung der Chancen in diesem Monat im Vergleich zum gleichen Zeitraum des letzten Jahres aussah.

* Ein Vermarkter, der untersucht, wie sich die Lead-Generierung für einen bestimmten Lead-Typ von diesem Monat zum letzten Monat verändert hat.

* Eine Führungskraft, die wissen möchte, wie sich die Buchungen in diesem Quartal im Vergleich zum letzten Quartal verändert haben.

## Verwenden Sie stattdessen 

1. Fügen Sie eine Visualisierung für ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Schlüsselmetrik-Zusammenfassung]** hinzu. Siehe [Hinzufügen einer Visualisierung zu einem Bedienfeld](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Konfigurieren Sie die Visualisierung, indem Sie eine **[!UICONTROL Metrik]**, einen **[!UICONTROL Primären Datumsbereich]**, einen **[!UICONTROL Vergleichsdatumsbereich]** (optional) und einen **[!UICONTROL Filter]** (optional) auswählen:

   ![Schlüsselmetrikkonfiguration, die die Optionen für Metrik, Primärdatumsbereich, Vergleichsdatumsbereich und Segment anzeigt.](assets/key-metrics-config.png)

   | Option | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Metrik]** | Wählen Sie die Metrik aus, die Sie überprüfen möchten. Alle Metriken werden unterstützt. |
   | **[!UICONTROL Primärer Datumsbereich]** | Der aktuelle Datumsbereich für die Freiformtabelle. |
   | **[!UICONTROL Vergleichsdatumsbereich]** | Der Datumsbereich, mit dem Sie den primären Datumsbereich vergleichen möchten. |
   | **[!UICONTROL Filter (optional)]** | Alle Filter, die Sie speziell für diese Zusammenfassung interessieren. |

   {style="table-layout:auto"}

1. Wählen Sie **[!UICONTROL Erstellen]** aus.

<!--## How the Key Metric Summary visualization handles the comparison date range

(This will probably release in January. Per Jaden Howell)

* If the primary date range is set to the panel date range, there are 2-6 options that are considered 'relative' to the primary date range. These usually include the previous period (same amount of time immediately proceeding the primary date range), and 52 weeks prior to that date range.

* If the comparison date range is set to one of the 'relative' options, upon updating the primary date range, the comparison date range updates to the period immediate preceding the panel date range.

* If your comparison date range is *not* set to a 'relative' option, then updating the panel date range changes your primary date range, but has no effect on the comparison date range.

**Example 1**

Primary date range is set to the panel's date range: 'Yesterday'
Comparison date range is set to a relative date range, one of: 'Previous day', 'Same day last week', 'Same day 4 weeks prior', 'Same day last month', 'Same day last year', or 'Same day 52 weeks prior'.
When I change the panel's date range to 'This month', the comparison date range will update to 'Previous month'.

**Example 2**
 
Primary date range is set to the panel's date range: 'Yesterday'
Comparison date range is set to a non-relative date range, such as 'Feb 2nd, 2022', 'Highest sales day', 'Last week', etc. 

>[!NOTE]
>
>Last week is relative to the day the project is opened on, but it is not based on the panel's date range of 'Yesterday'. In other cases, such as if the panel's date range was 'This week', it may be relative.

When you change the panel's date range to '4 days ago', the comparison date range remains at the previous selection. -->

Die Ausgabe der Schlüsselmetrik-Zusammenfassung sieht wie folgt aus:

![Schlüsselmetrikausgabe, die die Metrik, die Zusammenfassungsänderung, die Zusammenfassungsnummer und die Liniendiagramme anzeigt.](assets/key-metrics.png)

* Das Liniendiagramm **[!UICONTROL Vorheriger Zeitraum]** (immer grau dargestellt) entspricht dem **[!UICONTROL Vergleichsdatumsbereich]** im Konfigurationsschritt.

* Wenn während der Konfiguration kein Vergleichsdatumsbereich angegeben ist, oder in den Visualisierungseinstellungen ausgeblendet wird, wird nur das Liniendiagramm für den primären Datumsbereich angezeigt. Die Zusammenfassungsänderung ist ausgeblendet.

* Von hier aus können Sie mit dem Mauszeiger über die Liniendiagramme fahren, um die Statistiken für einzelne Tage zu sehen:


## Konfigurieren

Nach dem Erstellen der Visualisierung können Sie die ursprüngliche Konfiguration bearbeiten.

1. Wählen Sie oben in der Visualisierung ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Visualisierung konfigurieren]** aus.

   Sie werden zum ursprünglichen Konfigurationsdialogfeld zurückgeführt.

1. Ändern Sie die Einstellungen wie gewünscht. Wählen Sie **[!UICONTROL Zurücksetzen]** aus, um die aktuellen Einstellungen zurückzusetzen. Wählen Sie **[!UICONTROL Build]** aus, um die Visualisierung neu zu erstellen.

## Einstellungen

Im Rahmen der Visualisierungseinstellungen sind spezifische Einstellungen für Schlüsselmetriken verfügbar.

| Einstellung | Beschreibung |
|---|---|
| **[!UICONTROL Anzeigetyp der Zusammenfassung]** | Wählen Sie zwischen **[!UICONTROL Prozentänderung hervorheben]** oder **[!UICONTROL Wert der Nummer hervorheben]**. |
| **[!UICONTROL Trendlinien anzeigen]** | Trendlinien in der Visualisierung anzeigen. |
| **[!UICONTROL Maximale und minimale Anzahl an Trendlinien anzeigen]** | Zeigt maximalen und minimalen Wert für Trendlinien an. |
| **[!UICONTROL Vergleichsprozentsatz und Trendlinie anzeigen]** | Zeigt den Vergleichsprozentsatz mit der Trendlinie an. Wenn diese Option nicht ausgewählt ist, werden beide ausgeblendet. |
| **[!UICONTROL Zahlenwertoptionen]** | **[!UICONTROL Gesamtanzahl anzeigen]** oder **[!UICONTROL Rohdifferenz anzeigen]** für den Zahlenwert anzeigen. |
| **[!UICONTROL Wert kürzen]** | Wählen Sie **[!UICONTROL Wert abkürzen]** aus, um den Zahlenwert intelligent abzukürzen. Wenn diese Option aktiviert ist, geben Sie eine Zahl ein, um die Abkürzung zu definieren. Beispiel:<br/><table><tr><td>**Ausgangswert**</td><td>**Abkürzung**</td><td>**Ergebnis**</td></tr><tr><td>12.011.141,25 $</td><td>Nicht ausgewählt</td><td  align="right">12.011.141,25 $</td></tr><tr><td>12.011.141,25 $</td><td>Ausgewählt, auf 1 gesetzt</td><td align="right">12 Mio. USD</td></tr><tr><td>12.011.141,25 $</td><td>Ausgewählt, auf 2 gesetzt</td><td  align="right">12,0 Mio. $</td></tr><tr><td>12.011.141,25 $</td><td>Ausgewählt, auf 2 gesetzt</td><td align="right">12,011 Mio. $</td></tr><tr><td>12.011.141,25 $</td><td>Select, auf 3 setzen</td><td align="right">12,011 Mio. $</td></tr></table> |

>[!MORELIKETHIS]
>
>[Hinzufügen einer Visualisierung zu einem Bedienfeld](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualisierungseinstellungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Kontextmenü &quot;Visualisierung&quot;](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
