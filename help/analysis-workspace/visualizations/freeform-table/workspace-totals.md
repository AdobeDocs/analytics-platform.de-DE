---
description: Erfahren Sie, wie die Gesamtsummen in Workspace berechnet werden.
title: Workspace-Summen
feature: Visualizations
exl-id: ba14b88c-44c2-45f6-b68f-f5c1263a89dd
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 75%

---

# Workspace-Summen

In Freiformtabellen wird auf jeder Unterteilungsebene eine Zeile insgesamt angezeigt, die zwei Summen enthalten kann:

* **[!UICONTROL Gesamtsumme]** (graue &quot;von&quot;-Zahl) - dieser Gesamtwert stellt alle erfassten Ereignisse dar. Wenn ein Filter entweder auf Bereichsebene oder in der Freiformtabelle angewendet wird, passt sich diese Summe an, um alle Ereignisse widerzuspiegeln, die den Filterkriterien entsprechen.
* **[!UICONTROL Tabellensumme]** (schwarze Zahl) - dieser Gesamtwert entspricht in der Regel der [!UICONTROL Gesamtsumme] oder einer Untergruppe davon. Er spiegelt alle Tabellenfilter wider, die innerhalb der Freiformtabelle angewendet werden, einschließlich der Option [!UICONTROL Keine einschließen].

![Freiformtabelle, die die Gesamtsumme und die Tabellensumme hervorhebt.](assets/total-row.png)

## Gesamteinstellung anzeigen

Unter **[!UICONTROL Spalteneinstellungen]** finden Sie die Optionen **[!UICONTROL Summen anzeigen]** und **[!UICONTROL Gesamtsumme anzeigen]**. Wenn diese Einstellungen deaktiviert sind, werden die Summen aus der Tabelle entfernt. Dies kann in Fällen gewünscht werden, in denen Summen beispielsweise in bestimmten [Szenarien mit berechneten Metriken](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html?lang=de) keinen Sinn ergeben.

![Optionen für die Spalteneinstellungen mit Häkchen für &quot;Gesamt anzeigen&quot;und &quot;Zuschusssumme anzeigen&quot;](assets/column-settings-total.png)

## Gesamteinstellungen für statische Zeile

Die Gesamtwerte für [statische Zeilen](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) verhalten sich anders und werden unter **[!UICONTROL Zeileneinstellungen]** gesteuert.

* **[!UICONTROL Anzeigen der Summe der aktuellen Zeilen als Gesamtsumme]** - Zeigt eine clientseitige Summe der Zeilen in der Tabelle an, was bedeutet, dass die Gesamtsumme die Duplizierung von Metriken wie Besuche oder Personen **nicht** dedupliziert.
* **[!UICONTROL Gesamtsumme anzeigen]** - Zeigt eine Server-seitige Summe an, d. h. die Gesamtsumme dedupliziert Metriken wie Besuche oder Personen.

![Zeileneinstellungen, die die ausgewählte Gesamtsumme anzeigen anzeigen.](assets/static-rows.png)

## Häufig gestellte Fragen

| Fragen | Antwort |
|---|---|
| Auf welcher Summe basieren die grauen Spaltenprozentsätze? | Dies hängt von der Einstellung **[!UICONTROL Prozentwerte]** unter **[!UICONTROL Zeileneinstellungen]** ab:<ul><li>Prozentsatz nach Spalte berechnen - Dies ist die Standardeinstellung. Prozentsätze basieren auf der Tabellensumme.</li><li>Prozentsatz nach Zeile berechnen - Prozentsätze werden auf Basis der Gesamtsumme berechnet.</li></ul> |
| Wie wirkt sich die Einstellung **[!UICONTROL Nicht angegeben (keine) einschließen]** auf die Gesamtwerte aus? | Wenn die Einstellung **[!UICONTROL Nicht angegeben (keine) einschließen]** deaktiviert ist, wird die Zeile „Keine/Nicht angegeben“ aus der Tabelle und der Tabellensumme entfernt und wird in alle berechneten Metriken übernommen, die [Metriktypen ‚Gesamt‘](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc.html?lang=de) verwenden. |
| Wenn benutzerdefinierte Tabellenfilter auf eine Freiformtabelle angewendet werden, werden alle berechneten Metriken und die bedingte Formatierung für den Filter berücksichtigt? | Derzeit nicht. **[!UICONTROL Nicht angegeben (keine) einschließen]** wird berücksichtigt, benutzerdefinierte Tabellenfilter haben jedoch keine Auswirkungen auf Folgendes:<ul><li>Maximaler/minimaler Spaltenbereich, der bei der bedingten Formatierung verwendet wird, wird über alle Daten hinweg angezeigt.</li><li>Berechnete Metriken, die Metriktypen **[!UICONTROL insgesamt]** nutzen.</li><li>Berechnete Metriken mit Funktionen, die über Zeilen in einer Freiformtabelle berechnen - d. h. Spaltensumme, Spaltenmax., Spaltenanzahl, Anzahl, Mittelwert, Median, Perzentil, Quartil, Zeilenzahl, Standardabweichung, Varianz, Kumulativer Wert, Kumulativer Durchschnitt, Regressionsvarianten, T-Score, T-Test, Z-Score, Z-Test.</li></ul> |
| Was spiegelt der Metriktyp **[!UICONTROL Gesamtsumme]** in berechneten Metriken wider? | Die **[!UICONTROL Gesamtsumme]** bezieht sich weiterhin auf die **[!UICONTROL Gesamtsumme]** und spiegelt keine Filter wider, die auf eine Tabelle oder die **[!UICONTROL Tabellensumme]** angewendet wurden. |
| Welcher Gesamtwert wird angezeigt, wenn Daten entweder kopiert und aus einer Freiformtabelle eingefügt oder über CSV heruntergeladen werden? | Die Zeile insgesamt spiegelt nur die **[!UICONTROL Tabellensumme]** wider und berücksichtigt die Einstellung **[!UICONTROL Summen anzeigen]**. |
