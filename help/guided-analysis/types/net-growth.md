---
title: Nettowachstumsanalyse
description: Gewinnen oder verlieren Sie Benutzende?
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
exl-id: a4f97458-9934-4a98-8005-fa1ba7831101
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 6%

---

# Analyse [!UICONTROL Nettowachstum] {#net-growth}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_netgrowth_button"
>title="Nettowachstum"
>abstract="Gewinnen oder verlieren Sie Benutzende?"

<!-- markdownlint-enable MD034 -->

Die ![NetGrowth](/help/assets/icons/NetGrowth.svg)**[!UICONTROL Net Growth]**-Analyse bietet Einblicke in die Rate, mit der Sie Benutzer in einem bestimmten Zeitraum gewinnen oder verlieren. Die horizontale Achse ist ein Zeitintervall, während die vertikale Achse die Messung des Wachstums ist.

Jeder Datenpunkt stellt das Nettowachstum dar, das anhand der folgenden Formel berechnet wird:

`([New users] + [Return users]) / [Dormant users]`

Das Ergebnis dieser Formel ist ein Verhältnis. Ein Nettowachstum von `1` stellt ein Gleichgewicht dar; das Produkt gewann die gleiche Anzahl von Nutzern, die es verlor. Ein Nettowachstum über `1` stellt ein positives Wachstum dar; es gab mehr neue und rückkehrende Nutzer als inaktive Nutzer. Ebenso bedeutet ein Nettowachstum unter `1` einen Verlust; es gab mehr inaktive Nutzer als neue + rückkehrende Nutzer.

Ähnlich wie bei [Active](active-growth.md)-Analyse werden Benutzende wie folgt definiert:

* **[!UICONTROL Neu]**: Der Benutzer war im aktuellen Zeitraum aktiv, aber nicht zuvor. Sehen Sie, wie weit die Analyse zurückreicht, um einen neuen Benutzer zu bestimmen, indem Sie den Mauszeiger über [!UICONTROL Neue Benutzer] in der Diagrammlegende bewegen. Der Lookback-Bereich wird basierend auf dem ausgewählten Datumsbereich und Intervall dynamisch bestimmt.
* **[!UICONTROL Zurück]**: Der Benutzer war im aktuellen Zeitraum aktiv und im unmittelbar vorherigen Zeitraum nicht aktiv, war aber zu einem früheren Zeitpunkt aktiv. Sehen Sie, wie weit die Analyse zurückblickt, um einen wiederkehrenden Benutzer zu bestimmen, indem Sie den Mauszeiger über [!UICONTROL wiederkehrende Benutzer] in der Diagrammlegende bewegen. Der Lookback-Bereich wird basierend auf dem ausgewählten Datumsbereich und Intervall dynamisch bestimmt.
* **[!UICONTROL Inaktiv]**: Der/die Benutzende war unmittelbar im vorherigen Zeitraum aktiv, ist aber im aktuellen Zeitraum nicht aktiv. Inaktive Benutzende werden nicht zur Gesamtzahl der aktiven Benutzenden gezählt.

>[!NOTE]
>
>Wiederholte Benutzende werden in diese Berechnung nicht einbezogen, da sie keinen Gewinn oder Verlust von Benutzenden darstellen.

>[!VIDEO](https://video.tv.adobe.com/v/3421664/?quality=12&learn=on)


## Anwendungsfälle

Anwendungsfälle für diese Analyse sind:

* **Leistungsbewertung**: Damit können Sie die Gesamtleistung Ihres Produkts in Bezug auf die Akquise neuer Benutzer bewerten. Durch die Verfolgung von Wachstumstrends können Sie besser verstehen, ob Ihr Produkt in einem gewünschten Tempo Benutzer anzieht und bindet.
* **Analyse der Benutzerakquise**: Ermöglicht Ihnen, die Effektivität Ihrer Strategien zur Benutzerakquise zu bewerten. Durch die Analyse der Quellen des Benutzerwachstums, wie Suchmaschinen, Kampagnen oder andere Marketing-Kanäle, können Sie die wichtigsten Wachstumsquellen identifizieren, damit Sie Ressourcen entsprechend zuweisen können.
* **Abwanderungsanalyse**: Das Nettowachstum beinhaltet die Abwanderung in der Formel (inaktive Nutzer). Sie können den Gesamtzustand Ihrer Benutzerbasis im Zeitverlauf bewerten. Wenn das Nettowachstum durchgängig unter `1` liegt, deutet dies auf eine hohe Abnutzung hin, die die Implementierung von Kundenbindungsstrategien erforderlich machen könnte.

## Benutzeroberfläche

Siehe [Schnittstelle](../overview.md#interface) für einen Überblick über die Oberfläche der geführten Analyse. Die folgenden Einstellungen sind für diese Analyse spezifisch:

### Abfrageleiste

Mit der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Wechseln Sie zwischen dieser Analyse und [Aktives Wachstum](active-growth.md).
* **[!UICONTROL Ereignisse]**: Das Ereignis, das Sie messen möchten. Da diese Analyse benutzerbasiert ist, wird ein Benutzer, der innerhalb des Zeitraums mit dem Ereignis interagiert, als aktiver Benutzer gezählt. Sie können ein Ereignis in eine Abfrage einbeziehen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll.  Die Optionen umfassen [!UICONTROL Anzahl der ]) und [!UICONTROL Prozentsatz der ].
* **[!UICONTROL Segmente]**: Das Segment, das Sie messen möchten. Sie können ein Segment in eine Abfrage einbeziehen.

### Zeitvergleich

{{apply-time-comparison}}

### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trend-Daten angezeigt werden sollen. Gültige Optionen sind stündlich, täglich, wöchentlich, monatlich und vierteljährlich. Derselbe Datumsbereich kann unterschiedliche Intervalle aufweisen, die sich auf die Anzahl der Datenpunkte im Diagramm und auf die Anzahl der Spalten in der Tabelle auswirken. Wenn Sie beispielsweise eine Analyse mit dreitägiger Granularität anzeigen, werden nur drei Datenpunkte angezeigt, während eine Analyse mit dreitägiger Granularität 72 Datenpunkte ergibt.
* **[!UICONTROL Date]**: Das Start- und Enddatum. Rollierende Datumsbereichsvorgaben und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Sie können auch den Kalenderselektor verwenden, um einen festen Datumsbereich auszuwählen.

<!-- 
## Example

See below for an example of the analysis.

![Net growth compare](../assets/net-growth-compare.png)

-->
