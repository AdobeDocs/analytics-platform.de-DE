---
title: Analyse „Nettowachstum“
description: Gewinnen oder verlieren Sie Benutzende?
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
exl-id: a4f97458-9934-4a98-8005-fa1ba7831101
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: ht
source-wordcount: '676'
ht-degree: 100%

---

# Analyse [!UICONTROL Nettowachstum] {#net-growth}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_netgrowth_button"
>title="Nettowachstum"
>abstract="Gewinnen oder verlieren Sie Benutzende?"

<!-- markdownlint-enable MD034 -->

Die Analyse ![NetGrowth](/help/assets/icons/NetGrowth.svg) **[!UICONTROL Nettowachstum]** liefert Erkenntnisse zu der Rate, mit der Sie Benutzende in einem bestimmten Zeitraum gewinnen oder verlieren. Die horizontale Achse ist ein Zeitintervall und die vertikale Achse ist die Messung des Wachstums.

Jeder Datenpunkt stellt das Nettowachstum dar, das anhand der folgenden Formel berechnet wird:

`([New users] + [Return users]) / [Dormant users]`

Das Ergebnis dieser Formel ist ein Verhältnis. Ein Nettowachstum von `1` stellt ein Gleichgewicht dar; das Produkt hat die gleiche Anzahl von Benutzenden gewonnen, die es auch verloren hat. Ein Nettowachstum über `1` stellt ein positives Wachstum dar; es gab mehr neue und rückkehrende Benutzende als inaktive Benutzende. Ebenso stellt ein Nettowachstum unter `1` einen Verlust dar; es gab mehr inaktive Benutzende als neue und rückkehrende Benutzende.

Ähnlich wie bei der [Aktiv](active-growth.md)-Analyse werden Benutzende wie folgt definiert:

* **[!UICONTROL Neu]**: Die Person war im aktuellen Zeitraum aktiv, aber nicht zuvor. Sehen Sie sich an, wie weit die Analyse zurückreicht, um eine Benutzerin bzw. einen Benutzer zu ermitteln, indem Sie den Mauszeiger in der Diagrammlegende über [!UICONTROL Neue Benutzende] bewegen. Der Lookback-Bereich wird basierend auf dem ausgewählten Datumsbereich und Intervall dynamisch bestimmt.
* **[!UICONTROL Rückkehrend]**: Die Person war im aktuellen Zeitraum aktiv und im unmittelbar vorherigen Zeitraum nicht aktiv, war aber zu einem früheren Zeitpunkt aktiv. Sehen Sie sich an, wie weit die Analyse zurückreicht, um eine rückkehrende Benutzerin bzw. einen rückkehrenden Benutzer zu ermitteln, indem Sie den Mauszeiger in der Diagrammlegende über [!UICONTROL Rückkehrende Benutzende] bewegen. Der Lookback-Bereich wird basierend auf dem ausgewählten Datumsbereich und Intervall dynamisch bestimmt.
* **[!UICONTROL Inaktiv]**: Die Person war im unmittelbar vorherigen Zeitraum aktiv, ist aber im aktuellen Zeitraum nicht aktiv. Inaktive Benutzende werden nicht zur Gesamtzahl der aktiven Benutzenden gezählt.

>[!NOTE]
>
>Wiederkehrende Benutzende werden in diese Berechnung nicht einbezogen, da sie keinen Gewinn oder Verlust von Benutzenden darstellen.

>[!VIDEO](https://video.tv.adobe.com/v/3421664/?quality=12&learn=on)


## Anwendungsfälle

Zu den Anwendungsfällen für diese Analyse gehören:

* **Leistungsbewertung**: Damit können Sie die Gesamtleistung Ihres Produkts in Bezug auf die Akquise neuer Benutzerinnen und Benutzer bewerten. Durch die Verfolgung von Wachstumstrends können Sie besser nachvollziehen, ob Ihr Produkt Benutzende in einem gewünschten Tempo anzieht und bindet.
* **Analyse der Benutzerakquise**: Damit können Sie die Effektivität Ihrer Strategien zur Benutzerakquise zu bewerten. Durch die Analyse der Quellen des Benutzerwachstums, wie Suchmaschinen, Kampagnen oder andere Marketing-Kanäle, können Sie die wichtigsten Wachstumsquellen identifizieren und Ressourcen dann entsprechend zuweisen.
* **Abwanderungsanalyse**: Das Nettowachstum beinhaltet Abbrüche in der Formel (Inaktive Benutzende). Sie können den Gesamtzustand Ihres Benutzerkreises im Zeitverlauf bewerten. Wenn das Nettowachstum durchgängig unter `1` liegt, deutet dies auf eine hohe Anzahl an Abbrüchen hin, die die Implementierung von Kundenbindungsstrategien erforderlich machen könnte.

## Benutzeroberfläche

Einen Überblick über die Benutzeroberfläche für die geführte Analyse erhalten Sie unter [Benutzeroberfläche](../overview.md#interface). Die folgenden Einstellungen sind für diese Analyse spezifisch:

### Abfrageleiste

Mit der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Wechseln Sie zwischen dieser Analyse und [Aktives Wachstum](active-growth.md).
* **[!UICONTROL Ereignisse]**: Die Ereignisse, die gemessen werden sollen. Da diese Analyse benutzerbasiert ist, wird eine Person, die innerhalb des Zeitraums mit dem Ereignis interagiert, zur Gruppe der aktiven Benutzenden gezählt. Sie können ein Ereignis in eine Abfrage einbeziehen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll. Zu den Optionen gehören [!UICONTROL Anzahl der Benutzenden] und [!UICONTROL Prozentualer Anteil der Benutzenden].
* **[!UICONTROL Segmente]**: Das Segment, das Sie messen möchten. Sie können ein Segment in eine Abfrage einbeziehen.

### Zeitvergleich

{{apply-time-comparison}}

### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trend-Daten angezeigt werden sollen. Gültige Optionen sind „Stündlich“, „Täglich“, „Wöchentlich“, „Monatlich“ und „Quartalsweise“. Derselbe Datumsbereich kann unterschiedliche Intervalle aufweisen, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Bei einer Analyse über drei Tage mit täglicher Granularität werden beispielsweise nur drei Datenpunkte angezeigt, während eine Analyse über drei Tage mit stündlicher Granularität 72 Datenpunkte ergibt.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Ihnen stehen rollierende Datumsbereichsvorgaben und zuvor gespeicherte benutzerdefinierte Bereiche zur Verfügung. Sie können auch die Kalenderauswahl verwenden, um einen festen Datumsbereich zu definieren.

<!-- 
## Example

See below for an example of the analysis.

![Net growth compare](../assets/net-growth-compare.png)

-->
