---
description: Verwenden Sie die Visualisierung der Schlüsselmetrik-Zusammenfassung, um die Leistung der Kennzahlen über zwei Timelines hinweg zu vergleichen.
title: Zusammenfassung einer Schlüsselmetrik
feature: Visualizations
exl-id: ef606c53-b370-419a-904b-573ee6d70a8d
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 41%

---

# Zusammenfassung einer Schlüsselmetrik {#key-metric-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_keymetricsummary_button"
>title="Zusammenfassung einer Schlüsselmetrik"
>abstract="Erstellen Sie eine Visualisierung, die eine Kombination aus Linien-, Zusammenfassungsänderungs- und Zusammenfassungszahldiagramm darstellt. Verwenden Sie diese Visualisierung, um zu vergleichen, wie wichtige Metriken zwischen zwei Zeiträumen im Trend verlaufen."

<!-- markdownlint-enable MD034 -->


Mit der Visualisierung ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Key Metric Summary]** können Sie sehen, wie sich eine wichtige Metrik innerhalb eines einzigen Zeitrahmens entwickelt. Außerdem können Sie damit die Leistung von Metriken über zwei Zeitrahmen hinweg vergleichen. Sie bietet die Vorteile mehrerer Visualisierungen, die in einer Visualisierung kombiniert werden:

* **[!UICONTROL Linie]** Visualisierung zeigt, wie die Metrik für die primären und Vergleichsdatumsbereiche trendet

* **[!UICONTROL Zusammenfassende prozentuale Änderung]** zeigt die Zunahme oder Abnahme der Metrik zwischen dem primären und dem Vergleichsdatumsbereich

* Aktueller Gesamtwert ([!UICONTROL **Summenzahl**]) für die Metrik

Diese Visualisierung eignet sich für eine Vielzahl gängiger Anwendungsfälle, darunter:

* Ein Analyst, der versucht zu verstehen, wie die Entwicklung der Chancen in diesem Monat im Vergleich zum gleichen Zeitraum des letzten Jahres aussah.

* Ein Vermarkter, der untersucht, wie sich die Lead-Generierung für einen bestimmten Lead-Typ von diesem Monat zum letzten Monat verändert hat.

* Eine Führungskraft, die wissen möchte, wie sich die Buchungen in diesem Quartal im Vergleich zum letzten Quartal verändert haben.

## Verwenden

1. Fügen Sie eine Visualisierung ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Key Metric Summary]** hinzu. Siehe [Hinzufügen einer Visualisierung zu einem Bedienfeld](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Konfigurieren Sie die Visualisierung, indem Sie eine **[!UICONTROL Metrik]** einen **[!UICONTROL Primären]**, einen **[!UICONTROL Vergleichsdatumsbereich]** (optional) und einen **[!UICONTROL Filter]** (optional) auswählen:

   ![Konfiguration der Schlüsselmetrik mit den Optionen für die Metrik, den primären Datumsbereich, den Vergleichsdatumsbereich und das Segment.](assets/key-metrics-config.png)

   | Option | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Metrik]** | Wählen Sie die Metrik aus, die Sie überprüfen möchten. Alle Metriken werden unterstützt. |
   | **[!UICONTROL Primärer Datumsbereich]** | Der aktuelle Datumsbereich für die Freiformtabelle. |
   | **[!UICONTROL Vergleichsdatumsbereich]** | Der Datumsbereich, mit dem Sie den primären Datumsbereich vergleichen möchten. |
   | **[!UICONTROL Filter (optional)]** | Alle Filter, an denen Sie für diese Zusammenfassung interessiert sind. |

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

Die Ausgabe der Zusammenfassung der Schlüsselmetriken sieht wie folgt aus:

![Ausgabe einer Schlüsselmetrik mit der Metrik, der Zusammenfassungsänderung, der Zusammenfassungsnummer und den Liniendiagrammen.](assets/key-metrics.png)

* Das **[!UICONTROL Vorheriger Zeitraum]** Liniendiagramm (immer grau dargestellt) entspricht dem **[!UICONTROL Vergleichsdatumsbereich]** im Konfigurationsschritt.

* Wenn während der Konfiguration kein Vergleichsdatumsbereich angegeben ist, oder in den Visualisierungseinstellungen ausgeblendet wird, wird nur das Liniendiagramm für den primären Datumsbereich angezeigt. Die Zusammenfassungsänderung ist ausgeblendet.

* Von hier aus können Sie mit dem Mauszeiger über die Liniendiagramme fahren, um die Statistiken für einzelne Tage zu sehen:


## Konfigurieren

Nach dem Erstellen der Visualisierung können Sie die ursprüngliche Konfiguration bearbeiten.

1. Wählen ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Visualisierung konfigurieren]** oben in der Visualisierung aus.

   Sie gelangen zurück zum ursprünglichen Konfigurationsdialogfeld.

1. Ändern Sie die Einstellungen wie gewünscht. Mit **[!UICONTROL Zurücksetzen]** werden die aktuellen Einstellungen zurückgesetzt. Wählen Sie **[!UICONTROL Erstellen]** aus, um die Visualisierung neu zu erstellen.

## Einstellungen

Im Rahmen der Visualisierungseinstellungen sind spezifische Einstellungen für die Zusammenfassung der Schlüsselmetriken verfügbar.

| Einstellung | Beschreibung |
|---|---|
| **[!UICONTROL Anzeigetyp „Zusammenfassung“]** | Wählen Sie **[!UICONTROL Prozentuale Änderung hervorheben]** oder **[!UICONTROL Zahlenwert hervorheben]**. |
| **[!UICONTROL Trendlinien anzeigen]** | Zeigt Trendlinien in der Visualisierung an. |
| **[!UICONTROL Max. und Min. für Trendlinien anzeigen]** | Höchst- und Mindestwerte für Trendlinien anzeigen. |
| **[!UICONTROL Vergleichsprozentsatz und Trendlinie anzeigen]** | Vergleichsprozentsatz mit Trendlinie anzeigen. Wenn diese Option nicht ausgewählt ist, werden beide ausgeblendet. |
| **[!UICONTROL Zahlenwert-Optionen]** | **[!UICONTROL Gesamtanzahl anzeigen]** oder **[!UICONTROL Rohdifferenz anzeigen]** für den Zahlenwert. |
| **[!UICONTROL Wert kürzen]** | Wählen Sie **[!UICONTROL Wert abkürzen]**, um den Zahlenwert intelligent zu kürzen. Wenn ausgewählt, geben Sie eine Zahl ein, um den Betrag der Abkürzung zu definieren. Beispiel:<br/><table><tr><td>**Ausgangswert**</td><td>**Abkürzung**</td><td>**Ergebnis**</td></tr><tr><td>12 011 141,25 $</td><td>Nicht ausgewählt</td><td  align="right">12 011 141,25 $</td></tr><tr><td>12 011 141,25 $</td><td>ausgewählt, auf 1 gesetzt</td><td align="right">12 Mio. $</td></tr><tr><td>12 011 141,25 $</td><td>ausgewählt, auf 2 gesetzt</td><td  align="right">12,0 Mio. $</td></tr><tr><td>12 011 141,25 $</td><td>ausgewählt, auf 2 gesetzt</td><td align="right">12,011 Mio. $</td></tr><tr><td>12 011 141,25 $</td><td>Wählen Sie, setzen Sie auf 3</td><td align="right">12,011 Mio. $</td></tr></table> |

>[!MORELIKETHIS]
>
>[Hinzufügen einer Visualisierung zu einem Bedienfeld](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualisierungseinstellungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Kontextmenü der Visualisierung](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
