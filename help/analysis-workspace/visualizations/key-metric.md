---
description: Verwenden Sie die Visualisierung der Schlüsselmetrik-Zusammenfassung, um die Leistung der Kennzahlen über zwei Timelines hinweg zu vergleichen.
title: Zusammenfassung einer Schlüsselmetrik
feature: Visualizations
exl-id: ef606c53-b370-419a-904b-573ee6d70a8d
role: User
source-git-commit: b196b8c05ba05a3f46d71c10fdcaa2ad8ef0dcd6
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 84%

---

# Zusammenfassung einer Schlüsselmetrik

Mit der [!UICONTROL Zusammenfassung der Schlüsselmetrik] können Sie sehen, wie eine wichtige Metrik innerhalb eines einzigen Zeitrahmens trendet. Außerdem können Sie damit die Leistung von Metriken über zwei Zeitrahmen hinweg vergleichen. Sie bietet die Vorteile mehrerer Visualisierungen, die in einer Visualisierung kombiniert werden:

* **[!UICONTROL Linie]** Visualisierungen, die zeigen, wie die Metrik für die primären und Vergleichsdatumsbereiche trendet.

* **[!UICONTROL Zusammenfassende prozentuale Änderung]**, die die Zunahme oder Abnahme der Metrik zwischen dem primären und dem Vergleichsdatumsbereich anzeigt

* Aktueller Gesamtwert ([!UICONTROL **Summenzahl**]) für die Metrik

## Anwendungsbeispiele

Diese Visualisierung eignet sich für eine Vielzahl gängiger Anwendungsfälle, darunter:

* Ein Analyst, der versucht zu verstehen, wie die Entwicklung der Chancen in diesem Monat im Vergleich zum gleichen Zeitraum des letzten Jahres aussah.

* Ein Vermarkter, der untersucht, wie sich die Lead-Generierung für einen bestimmten Lead-Typ von diesem Monat zum letzten Monat verändert hat.

* Eine Führungskraft, die wissen möchte, wie sich die Buchungen in diesem Quartal im Vergleich zum letzten Quartal verändert haben.

## Konfigurieren der Zusammenfassung einer Schlüsselmetrik

1. Ziehen Sie die Visualisierung **[!UICONTROL Zusammenfassung einer Schlüsselmetrik]** aus dem Menü **[!UICONTROL Visualisierungen]** in der linken Leiste in ein Bedienfeld.

1. Konfigurieren Sie die Visualisierung, indem Sie eine Metrik, einen primären Datumsbereich, einen Vergleichsdatumsbereich und einen Filter auswählen (falls gewünscht):

   ![Schlüsselmetrikkonfiguration, die die Optionen für Metrik, Primärdatumsbereich, Vergleichsdatumsbereich und Segment anzeigt.](assets/key-metric-config.png)

   | Konfigurationseinstellungen | Definition |
   | --- | --- |
   | **[!UICONTROL Metrik]** | Wählen Sie die Metrik aus, die Sie überprüfen möchten. Alle Metriken werden unterstützt. |
   | **[!UICONTROL Primärer Datumsbereich]** | Der aktuelle Datumsbereich für die Freiformtabelle. |
   | **[!UICONTROL Vergleichsdatumsbereich]** | Der Datumsbereich, mit dem Sie den primären Datumsbereich vergleichen möchten. |
   | **[!UICONTROL Filter (optional)]** | Alle Filter, die Sie speziell für diese Zusammenfassung interessieren. |

   {style="table-layout:auto"}

1. Klicken Sie auf **[!UICONTROL Erstellen]**.

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

## Ausgabe anzeigen

Die Ausgabe sollte ungefähr so aussehen:

![Schlüsselmetrikausgabe, die die Metrik, die Zusammenfassungsänderung, die Zusammenfassungsnummer und die Liniendiagramme anzeigt.](assets/key-metric-output.png)

Bitte beachten Sie:

* Der Kantengraph **[!UICONTROL Vorheriger Zeitraum]** (immer grau dargestellt) entspricht dem **[!UICONTROL Vergleichsdatumsbereich]** im Konfigurationsschritt.

* Wenn während der Konfiguration kein Vergleichsdatumsbereich angegeben ist, oder in den Visualisierungseinstellungen ausgeblendet wird, wird nur das Liniendiagramm für den primären Datumsbereich angezeigt. Die Änderung der Zusammenfassung wird ausgeblendet.

* Von hier aus können Sie mit dem Mauszeiger über die Liniendiagramme fahren, um die Statistiken für einzelne Tage zu sehen:

![Besuchsstatistiken](assets/key-metric-output2.png)

## Visualisierungseinstellungen

Die Zusammenfassung der Schlüsselmetriken bietet mehrere flexible Einstellungen, um eine bessere Berichterstellung und Kommunikation wichtiger Metriken zu ermöglichen. Die Einstellungen können über das Zahnradsymbol in der oberen rechten Ecke der Visualisierung aufgerufen werden.

![Schlüsselmetrikzusammenfassungs-Einstellungen, die den Anzeigetyp, die allgemeinen und die Anzeigeoptionen der Zusammenfassung anzeigen.](assets/key-metric-settings.png)

| Einstellung | Beschreibung |
| --- | --- |
| **[!UICONTROL Prozentuale Veränderung betonen]** | Anzeige der Zusammenfassungsänderung in hervorgehobener fetter Schrift in der Mitte der Visualisierung |
| **[!UICONTROL Zahlenwert hervorheben]** | Anzeige der Zusammenfassungsanzahl in hervorgehobener fetter Schrift in der Mitte der Visualisierung |
| **[!UICONTROL Legende eingeblendet]** | Ein- oder Ausblenden der Legende am unteren Rand der Visualisierung |
| **[!UICONTROL Anmerkungen anzeigen]** | Von einem Administrator hinzugefügte Anmerkungen anzeigen oder ausblenden |
| **[!UICONTROL Sparklines anzeigen]** | Liniendiagramme am unteren Rand des Diagramms anzeigen oder ausblenden. Wenn sie ausgeblendet ist, wird die Legende so geändert, dass sie keinen visuellen Bezug mehr zu den Linien hat. |
| **[!UICONTROL Min. und Max. für Wortgrafiken anzeigen]** | Ein- und Ausblenden von Minimal- und Maximalwerten in Primär- und Vergleichsliniendiagrammen |
| **[!UICONTROL Vergleich anzeigen]** | Vergleichsdaten ein- oder ausblenden. Wenn diese Option ausgeblendet ist, werden sowohl das Vergleichszeilendiagramm als auch die Zusammenfassungsänderung der Objekte ausgeblendet. |
| **[!UICONTROL Gesamtanzahl anzeigen]** | Zusammenfassungsnummer anzeigen oder ausblenden |
| **[!UICONTROL Rohdifferenz anzeigen]** | Rohdifferenz zwischen dem Gesamtwert der Metrik im primären Datumsbereich und im sekundären Datumsbereich anzeigen oder ausblenden |
| **[!UICONTROL Wert kürzen]** | Abkürzen von Zahlenwerten zur Vereinfachung der kommunizierten Einblicke (z. B. 20.000 -> 20K) |

## Visualisierung bearbeiten

Nach dem Erstellen der Visualisierung können Sie die ursprüngliche Konfiguration noch bearbeiten.

1. Klicken Sie oben rechts in der Visualisierung auf das Stiftsymbol (neben dem Zahnradsymbol für Einstellungen).

   ![Symbol für die Visualisierungsbearbeitung.s](assets/edit-icon.png)

   Sie gelangen nun zurück zur ursprünglichen Konfigurationsansicht.

1. Ändern Sie die Metrik, den primären Datumsbereich, den Vergleichsdatumsbereich oder den Filter wie gewünscht.
