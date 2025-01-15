---
description: Verwenden Sie die Visualisierung der Schlüsselmetrik-Zusammenfassung, um die Leistung der Kennzahlen über zwei Timelines hinweg zu vergleichen.
title: Zusammenfassung einer Schlüsselmetrik
feature: Visualizations
exl-id: ef606c53-b370-419a-904b-573ee6d70a8d
role: User
source-git-commit: c7cdeb29729af35d7554b19e395047b364f0b547
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 36%

---

# Zusammenfassung einer Schlüsselmetrik {#key-metric-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_keymetricsummary_button"
>title="Zusammenfassung einer Schlüsselmetrik"
>abstract="Erstellen Sie eine Visualisierung, die eine Kombination aus Linien-, Zusammenfassungsänderungs- und Zusammenfassungszahldiagramm darstellt. Verwenden Sie diese Visualisierung, um zu vergleichen, wie wichtige Metriken zwischen zwei Zeiträumen im Trend verlaufen."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*In diesem Artikel wird die Visualisierung der Zusammenfassung der Schlüsselmetriken in **Customer Journey Analytics.**. Siehe [Zusammenfassung der Schlüsselmetriken](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/key-metric) für die **Adobe Analytics**-Version dieses Artikels.*

>[!ENDSHADEBOX]


Mit der Visualisierung ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Key Metric Summary]** können Sie sehen, wie sich eine wichtige Metrik innerhalb eines einzigen Zeitrahmens entwickelt. Außerdem können Sie damit die Leistung von Metriken über zwei Zeitrahmen hinweg vergleichen. Sie bietet die Vorteile mehrerer Visualisierungen, die in einer Visualisierung kombiniert werden:

* **[!UICONTROL Linie]** Visualisierung zeigt, wie die Metrik für die primären und Vergleichsdatumsbereiche trendet

* **[!UICONTROL Zusammenfassende prozentuale Änderung]** zeigt die Zunahme oder Abnahme der Metrik zwischen dem primären und dem Vergleichsdatumsbereich

* Aktueller Gesamtwert ([!UICONTROL **Summenzahl**]) für die Metrik

## Anwendungsbeispiele

Diese Visualisierung behandelt verschiedene gängige Anwendungsfälle, darunter:

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
   | **[!UICONTROL Primärer Datumsbereich]** | Der aktuelle Datumsbereich für die Freiformtabelle.<p>Wählen Sie aus allen verfügbaren Datumsbereichen in Ihrer Datenansicht.</p> <p>Wählen Sie [!UICONTROL **Datumsbereich des Bedienfelds**] aus, wenn Sie denselben Datumsbereich verwenden möchten, der in dem Bedienfeld verwendet wird, in dem sich die Visualisierung befindet.</p> |
   | **[!UICONTROL Vergleichsdatumsbereich]** | Der Datumsbereich, den Sie mit dem primären Datumsbereich vergleichen möchten. |
   | **[!UICONTROL Filter (optional)]** | Alle Filter, die für diese Zusammenfassung von Interesse sind. |

   {style="table-layout:auto"}

   >[!NOTE]
   >
   >Wenn das Feld [!UICONTROL **Primärer Datumsbereich**] auf [!UICONTROL **Datumsbereich des Bedienfelds**] festgelegt ist, kann der **[!UICONTROL Vergleichsdatumsbereich]** automatisch aktualisiert werden, je nachdem, ob die gewählte Option **[!UICONTROL Vergleichsdatumsbereich]** relativ zum primären Datumsbereich oder fest ist.
   >
   >* **Relativ:** Wenn das Feld **[!UICONTROL Vergleichsdatumsbereich]** auf eine Option gesetzt ist, die relativ zum primären Datumsbereich ist ([!UICONTROL **Vortag**], [!UICONTROL **Vorletzter Wochentag**], [!UICONTROL **Selber Tag vor 4 Wochen**] usw.), bewirkt jede Aktualisierung des Felds [!UICONTROL **Primärer Datumsbereich**], dass der **[!UICONTROL Vergleichsdatumsbereich]** automatisch auf den Zeitraum aktualisiert wird, der unmittelbar auf den Datumsbereich des Bedienfelds folgt.
   >* **Behoben:** Wenn das Feld [!UICONTROL **Vergleichsdatumsbereich**] auf einen festen Datumsbereich eingestellt ist (z. B. **3. Februar 2023**), haben Änderungen am Feld [!UICONTROL **Primärer Datumsbereich**] oder am Datumsbereich des Bedienfelds keine Auswirkungen auf den [!UICONTROL **Vergleichsdatumsbereich**]. Alle Aktualisierungen des Datumsbereichs des Bedienfelds führen jedoch dazu, dass der [!UICONTROL **Primäre**] automatisch aktualisiert wird.

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

Beachten Sie beim Anzeigen der Ausgabe Folgendes:

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
| --- | --- |
| **[!UICONTROL Prozentuale Veränderung betonen]** | Anzeige der Zusammenfassungsänderung in hervorgehobener fetter Schrift in der Mitte der Visualisierung |
| **[!UICONTROL Zahlenwert hervorheben]** | Anzeige der Zusammenfassungsanzahl in hervorgehobener fetter Schrift in der Mitte der Visualisierung |
| **[!UICONTROL Legende eingeblendet]** | Ein- oder Ausblenden der Legende am unteren Rand der Visualisierung |
| **[!UICONTROL Anmerkungen anzeigen]** | Von einem Administrator hinzugefügte Anmerkungen anzeigen oder ausblenden |
| **[!UICONTROL Titel ausblenden]** | Blenden Sie den Titel der Visualisierung aus. |
| **[!UICONTROL Prozentsätze]** | Zeigt die Visualisierung in Prozent anstelle einer Zahl an. |
| **[!UICONTROL Trendlinien anzeigen]** | Zeigt Trendlinien in der Visualisierung an. |
| **[!UICONTROL Max. und Min. für Trendlinien anzeigen]** | Ein- und Ausblenden von Minimal- und Maximalwerten in Primär- und Vergleichsliniendiagrammen |
| **[!UICONTROL Vergleichsprozentsatz und Trendlinie anzeigen]** | Vergleichsdaten ein- oder ausblenden. Wenn diese Option ausgeblendet ist, werden sowohl das Vergleichszeilendiagramm als auch die Zusammenfassungsänderungsobjekte ausgeblendet. |
| **[!UICONTROL Gesamtanzahl anzeigen]** | Zusammenfassungsnummer anzeigen oder ausblenden |
| **[!UICONTROL Rohdifferenz anzeigen]** | Rohdifferenz zwischen dem Gesamtwert der Metrik im primären Datumsbereich und im sekundären Datumsbereich anzeigen oder ausblenden |
| **[!UICONTROL Wert kürzen]** | Wählen Sie **[!UICONTROL Wert abkürzen]**, um den Zahlenwert intelligent zu kürzen. Wenn ausgewählt, geben Sie eine Zahl ein, um den Betrag der Abkürzung zu definieren. Beispiel:<br/><table><tr><td>**Ausgangswert**</td><td>**Abkürzung**</td><td>**Ergebnis**</td></tr><tr><td>12 011 141,25 $</td><td>Nicht ausgewählt</td><td align="right">12 011 141,25 $</td></tr><tr><td>12 011 141,25 $</td><td>ausgewählt, auf 1 gesetzt</td><td align="right">12 Mio. $</td></tr><tr><td>12 011 141,25 $</td><td>ausgewählt, auf 2 gesetzt</td><td align="right">12,0 Mio. $</td></tr><tr><td>12 011 141,25 $</td><td>ausgewählt, auf 2 gesetzt</td><td align="right">12,011 Mio. $</td></tr><tr><td>12 011 141,25 $</td><td>Wählen Sie, setzen Sie auf 3</td><td align="right">12,011 Mio. $</td></tr></table> |

## Visualisierung bearbeiten

Nach dem Erstellen der Visualisierung können Sie die ursprüngliche Konfiguration noch bearbeiten.

1. Klicken Sie auf das Stiftsymbol in der oberen rechten Ecke der Visualisierung (neben dem Zahnradsymbol für Einstellungen).

   ![Bearbeitungssymbol für Visualisierungen](assets/edit-icon.png)

   Sie gelangen nun zurück zur ursprünglichen Konfigurationsansicht.

1. Ändern Sie die Metrik, den primären Datumsbereich, den Vergleichsdatumsbereich oder den Filter nach Bedarf.

>[!MORELIKETHIS]
>
>[Hinzufügen einer Visualisierung zu einem Bedienfeld](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualisierungseinstellungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Kontextmenü der Visualisierung](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
