---
description: Erfahren Sie, wie Summen in Freiformtabellen in Analysis Workspace berechnet werden.
title: Gesamt
feature: Visualizations
exl-id: ba14b88c-44c2-45f6-b68f-f5c1263a89dd
role: User
TQID: 'https://experienceleague.adobe.com/BoH9J-fL9UxPG4wId9-GU7muMNR10aeWe0BBd1NQOjo'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
    internal-label: Freeform tables
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
    internal-label: Calculated metrics
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 73%
---
# Gesamt {#workspace-totals}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_grandtotal"
>title="Gesamtsumme"
>abstract="Die Gesamtsumme wird für Tabellen oder Aufschlüsselungen mit statischen Zeilen nicht unterstützt."


In Freiformtabellen wird auf jeder Aufschlüsselungsebene eine Summenzeile angezeigt, die zwei Summen enthalten kann:

![Freiformtabelle mit hervorgehobener Gesamt- und Tabellensumme.](assets/total-row.png)

* **[!UICONTROL Tabellensumme]** ➊ - Dieser Gesamtwert entspricht in der Regel der Gesamtsumme oder einer Teilmenge [!UICONTROL Gesamtsumme]. Die Summe spiegelt alle Tabellensegmente wider, die in der Freiformtabelle angewendet wurden, einschließlich der Option [!UICONTROL Ohne einschließen].
* **[!UICONTROL Gesamtsumme]** (**[!UICONTROL von]** *Anzahl*) ➋ - Dieser Gesamtwert stellt alle erfassten Ereignisse dar. Wenn ein Segment entweder auf Panel-Ebene oder in der Freiformtabelle angewendet wird, passt sich dieser Gesamtwert an, um alle Ereignisse wiederzugeben, die den Segmentkriterien entsprechen.




## Anzeigen von Summen

Unter ![Setting](/help/assets/icons/Setting.svg) **[!UICONTROL Spalteneinstellungen]** finden Sie die Optionen **[!UICONTROL Summen anzeigen]** und **[!UICONTROL Gesamtsumme anzeigen]**. Wenn diese Einstellungen nicht aktiviert sind, werden Summen aus der Tabelle entfernt. In Fällen, in denen Summen nicht sinnvoll sind, kann dies durchaus erwünscht sein.


In einer Freiformtabelle, die (statische [) enthält](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) verhalten sich Summen anders. und werden mithilfe von ![Einstellung](/help/assets/icons/Setting.svg) **[!UICONTROL Zeileneinstellungen]**.

| Option | Beschreibung |
|---|---|
| **[!UICONTROL Als Summe der aktuellen Zeilen anzeigen]** | Zeigen Sie eine Client-seitige Summe der Zeilen in der Tabelle an. Bei dieser Summe werden Metriken wie Sitzungen oder Personen **nicht** dedupliziert. |
| **[!UICONTROL Gesamtsumme anzeigen]** | Zeigen Sie eine Server-seitige Summe an. Bei dieser Summe werden Metriken wie Sitzungen oder Personen dedupliziert. |

Siehe [Dynamische und statische Dimensionselemente in Freiformtabellen](column-row-settings/manual-vs-dynamic-rows.md).


## Häufig gestellte Fragen

| Fragen | Antwort |
|---|---|
| Auf welcher *Summe* basieren die grauen Spaltenprozentsätze? | Diese *Summe* hängt von der Einstellung **[!UICONTROL Prozentsatz]** unter **[!UICONTROL Zeileneinstellungen]** ab:<ul><li>Prozentsätze nach Spalte berechnen: Diese Einstellung ist die Standardeinstellung. Prozentsätze basieren auf der Tabellensumme.</li><li>Prozentsätze nach Zeile berechnen: Prozentsätze werden auf Basis der Gesamtsumme berechnet.</li></ul> |
| Wie wirkt sich die Einstellung **[!UICONTROL „Kein Wert“ einschließen]** auf die Gesamtsumme aus? | Wenn die Einstellung **[!UICONTROL „Kein Wert“ einschließen]** deaktiviert ist, wird die Zeile **[!UICONTROL Kein Wert]** aus der Tabelle und der Tabellensumme entfernt und wird in alle berechneten Metriken übernommen, die [*Gesamt* als Metriktypen verwenden](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md). |
| Wenn benutzerdefinierte Tabellensegmente auf eine Freiformtabelle angewendet werden, werden die Segmente in allen meinen berechneten Metriken und der bedingten Formatierung berücksichtigt? | Derzeit nicht. **[!UICONTROL Einschließen von „Kein Wert]** wird berücksichtigt, aber benutzerdefinierte Tabellensegmente haben keine Auswirkungen auf Folgendes:<ul><li>Der maximale/minimale Spaltenbereich, den die bedingte Formatierung verwendet, wird auf Basis aller Daten berechnet.</li><li>Berechnete Metriken, die Metriktypen **[!UICONTROL Gesamtsumme]** nutzen.</li><li>Berechnete Metriken mit Funktionen, die über Zeilen in einer Freiformtabelle hinweg berechnen: Spaltensumme, Spaltenmaximum, Spaltenminimum, Anzahl, Mittelwert, Median, Perzentil, Quartil, Zeilenzahl, Standardabweichung, Varianz, kumulativer Wert, kumulativer Durchschnitt, Regressionsvarianten, T-Score, T-Test, Z-Score und Z-Test.</li></ul> |
| Was spiegelt der Metriktyp **[!UICONTROL Gesamtsumme]** in berechneten Metriken wider? | **[!UICONTROL Gesamtsumme]** bezieht sich weiterhin auf die **[!UICONTROL Gesamtsumme]** und spiegelt nicht die Segmente wider, die auf eine Tabelle oder die **[!UICONTROL Tabellensumme]**. |
| Welcher Gesamtwert wird angezeigt, wenn Daten entweder aus einer Freiformtabelle kopiert und eingefügt oder über CSV heruntergeladen werden? | Die Zeile insgesamt spiegelt nur die **[!UICONTROL Tabellensumme]** wider und berücksichtigt die Einstellung **[!UICONTROL Summen anzeigen]**. |
