---
description: Erfahren Sie, wie die Gesamtsummen in Workspace berechnet werden.
title: Workspace-Summen
feature: Visualizations
exl-id: ba14b88c-44c2-45f6-b68f-f5c1263a89dd
role: User
source-git-commit: b9abcf48c5334d71639d7d96558a63611a4a491c
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 18%

---

# Workspace-Summen {#workspace-totals}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_freeformtable_grandtotal"
>title="Gesamtsumme"
>abstract="Die Gesamtsumme wird für Tabellen oder Aufschlüsselungen mit statischen Zeilen nicht unterstützt."

<!-- markdownlint-enable MD034 -->


In Freiformtabellen wird auf jeder Unterteilungsebene eine Zeile insgesamt angezeigt, die zwei Summen enthalten kann:

![Freiformtabelle, die die Gesamtsumme und die Tabellensumme hervorhebt.](assets/total-row.png)

* **[!UICONTROL Tabellensumme]** - Dieser Gesamtwert entspricht normalerweise einer Untergruppe der [!UICONTROL Gesamtsumme]. Die Gesamtsumme spiegelt alle Tabellenfilter wider, die innerhalb der Freiformtabelle angewendet werden, einschließlich der Option [!UICONTROL Keine einschließen] .
* **[!UICONTROL Gesamtwert]** (**[!UICONTROL von]** *Gesamtanzahl*) - Dieser Gesamtwert stellt alle erfassten Ereignisse dar. Wenn ein Filter entweder auf Bereichsebene oder in der Freiformtabelle angewendet wird, passt sich diese Summe an, um alle Ereignisse widerzuspiegeln, die den Filterkriterien entsprechen.




## Anzeigesummen

Unter ![Einstellung](/help/assets/icons/Setting.svg) **[!UICONTROL Spalteneinstellungen]** gibt es Optionen für **[!UICONTROL Summen anzeigen]** und **[!UICONTROL Gesamtsumme anzeigen]**. Wenn diese Einstellungen deaktiviert sind, werden Summen aus der Tabelle entfernt, was in Fällen gewünscht werden kann, in denen Summen keinen Sinn ergeben. Zum Beispiel in bestimmten Szenarien mit [berechneten Metriken](https://experienceleague.adobe.com/en/docs/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals).


Die Gesamtwerte der statischen Zeile ](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) verhalten sich anders und werden mit ![Einstellung](/help/assets/icons/Setting.svg) **[!UICONTROL Zeileneinstellungen]** gesteuert.[

| Option | Beschreibung |
|---|---|
| **[!UICONTROL Anzeigen der Summe der aktuellen Zeilen als Gesamtsumme]** | Zeigt eine clientseitige Summe der Zeilen in der Tabelle an. Diese Gesamtsumme dedupliziert Metriken wie Sitzungen oder Personen **nicht**. |
| **[!UICONTROL Gesamtsumme anzeigen]** | Zeigt eine Server-seitige Summe an. Diese Gesamtzahl dedupliziert Metriken wie Sitzungen oder Personen. |

Siehe [Dynamische und statische Dimensionselemente in Freiformtabellen](column-row-settings/manual-vs-dynamic-rows.md).


## Häufig gestellte Fragen

| Fragen | Antwort |
|---|---|
| Auf welchen *total* basieren die grauen Spaltenprozentsätze? | Diese *Gesamtsumme* hängt von der Einstellung **[!UICONTROL Prozentsätze]** unter **[!UICONTROL Zeileneinstellungen]** ab:<ul><li>Prozentsätze pro Spalte berechnen - Diese Einstellung ist die Standardeinstellung. Prozentsätze basieren auf der Tabellensumme.</li><li>Prozentsätze nach Zeile berechnen - Prozentsätze basieren auf der Gesamtsumme.</li></ul> |
| Wie wirkt sich die Einstellung &quot;**[!UICONTROL Kein Wert einschließen&quot;]** auf die Gesamtwerte aus? | Wenn die Einstellung **[!UICONTROL Kein Wert einschließen]** deaktiviert ist, wird die Zeile **[!UICONTROL Kein Wert]** aus der Tabelle und dem Tabellengesamtwert entfernt und wird in alle berechneten Metriken übernommen, die Metriktypen [*Gesamt* verwenden](https://experienceleague.adobe.com/en/docs/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc) |
| Wenn benutzerdefinierte Tabellenfilter auf eine Freiformtabelle angewendet werden, werden alle berechneten Metriken und die bedingte Formatierung für den Filter berücksichtigt? | Derzeit nicht. **[!UICONTROL Include &quot;No value&quot;]** ist berücksichtigt, benutzerdefinierte Tabellenfilter haben jedoch keine Auswirkungen auf Folgendes:<ul><li>Der für die bedingte Formatierung verwendete Spaltenmaximum/-min-Bereich sucht über alle Daten hinweg.</li><li>Berechnete Metriken, die Metriktypen **[!UICONTROL Gesamtsumme]** nutzen.</li><li>Berechnete Metriken mit Funktionen, die über Zeilen in einer Freiformtabelle berechnen: Spaltensumme, Spaltenmax, Spaltenanzahl, -anzahl, Mittelwert, Median, Perzentil, Quartil, Zeilenanzahl, Standardabweichung, Varianz, Kumulativer, kumulativer Durchschnitt, Regressionsvarianten, T-Score, T-Test, Z-Score und Z-Test.</li></ul> |
| Was spiegelt der Metriktyp **[!UICONTROL Gesamtsumme]** in berechneten Metriken wider? | **[!UICONTROL Gesamtsumme]** bezieht sich weiterhin auf den **[!UICONTROL Gesamtwert]** und spiegelt keine auf eine Tabelle angewendeten Filter oder den **[!UICONTROL Tabellengesamtwert]** wider. |
| Welcher Gesamtwert wird angezeigt, wenn Daten entweder kopiert und aus einer Freiformtabelle eingefügt oder über CSV heruntergeladen werden? | Die Zeile insgesamt spiegelt nur den **[!UICONTROL Tabellengesamtwert]** wider und berücksichtigt die Einstellung für die Spalte **[!UICONTROL Summen anzeigen]** . |
