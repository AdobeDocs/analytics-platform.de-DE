---
title: Ansicht des Nettowachstums
description: Gewinnen oder verlieren Sie Benutzende?
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
exl-id: a4f97458-9934-4a98-8005-fa1ba7831101
role: User
source-git-commit: 240a17923b55479865affaafb098b56e32d083a3
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 2%

---

# Ansicht für [!UICONTROL Nettowachstum]

Der Ansichtstyp **[!UICONTROL Nettowachstum]** bietet Einblicke in die Rate, mit der Sie Benutzer über einen bestimmten Zeitraum gewinnen oder verlieren. Die horizontale Achse ist ein Zeitintervall, während die vertikale Achse die Wachstumsmessung darstellt.

Jeder Datenpunkt stellt das Nettowachstum dar, das anhand der folgenden Formel berechnet wird:

`([New users] + [Return users]) / [Dormant users]`

Das Ergebnis dieser Formel ist ein Verhältnis. Ein Nettowachstum von `1` stellt ein Gleichgewicht dar; das Produkt hat die gleiche Anzahl von Benutzern gewonnen, die es verloren hat. Ein Nettowachstum von mehr als `1` bedeutet ein positives Wachstum; es gab mehr neue + wiederkehrende Benutzer als ruhende Benutzer. Ebenso stellt ein Nettowachstum von weniger als `1` einen Verlust dar; es gab mehr ruhende Benutzer als neue + wiederkehrende Benutzer.

Ähnlich wie beim Ansichtstyp [Aktiv](active.md) werden Benutzer wie folgt definiert:

* **[!UICONTROL Neu]**: Der Benutzer war während des aktuellen Zeitraums aktiv, jedoch nicht zuvor. Ermitteln Sie, wie weit die Analyse zurückblickt, um einen neuen Benutzer zu ermitteln, indem Sie den Mauszeiger in der Diagrammlegende über &quot;[!UICONTROL Neue Benutzer]&quot;bewegen. Der Lookback-Bereich wird basierend auf dem ausgewählten Datumsbereich und Intervall dynamisch bestimmt.
* **[!UICONTROL Zurück]**: Der Benutzer war im aktuellen Zeitraum aktiv und nicht im unmittelbar vorherigen Zeitraum aktiv, war aber zu einem früheren Zeitpunkt aktiv. Ermitteln Sie, wie weit die Analyse zurückblickt, um einen wiederkehrenden Benutzer zu ermitteln, indem Sie den Mauszeiger in der Diagrammlegende über &quot;[!UICONTROL Wiederkehrende Benutzer]&quot;bewegen. Der Lookback-Bereich wird basierend auf dem ausgewählten Datumsbereich und Intervall dynamisch bestimmt.
* **[!UICONTROL Dormant]**: Der Benutzer war im unmittelbar vorherigen Zeitraum aktiv, ist aber im aktuellen Zeitraum nicht aktiv. Dormant-Benutzer zählen nicht zur Gesamtanzahl aktiver Benutzer.

>[!NOTE]
>
>Wiederholte Benutzer werden nicht in diese Berechnung einbezogen, da sie keinen Gewinn oder Verlust von Benutzern darstellen.

>[!VIDEO](https://video.tv.adobe.com/v/3421664/?learn=on)

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Leistungsbewertung**: Ermöglicht es Ihnen, die Gesamtleistung Ihres Produkts im Hinblick auf die Akquise neuer Benutzer zu bewerten. Durch die Verfolgung von Wachstumstrends können Sie besser nachvollziehen, ob Ihr Produkt Benutzer in einem gewünschten Tempo anzieht und bindet.
* **Analyse der Benutzerakquise**: Ermöglicht es Ihnen, die Effektivität Ihrer Benutzerakquisestrategien zu bewerten. Die Analyse der Quellen für das Benutzerwachstum, wie Suchmaschinen, Kampagnen oder andere Marketingkanäle, ermöglicht es Ihnen, die wichtigsten Wachstumsquellen zu identifizieren, sodass Sie Ressourcen entsprechend zuordnen können.
* **Abwanderungsanalyse**: Das Nettowachstum umfasst Abbruch in der Formel (ruhende Benutzer). Sie können die allgemeine Gesundheit Ihrer Benutzerbasis im Laufe der Zeit bewerten. Wenn das Nettowachstum konsequent unter `1` liegt, deutet dies auf eine hohe Abschreibungsrate hin, die die Implementierung von Treuestrategien erforderlich machen könnte.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Wechseln Sie zwischen diesem Ansichtstyp und [Aktiv](active.md).
* **[!UICONTROL Ereignisse]**: Das Ereignis, das Sie messen möchten. Da dieser Ansichtstyp benutzerbasiert ist, wird ein Benutzer, der innerhalb des Zeitraums einmal mit dem Ereignis interagiert, als aktiver Benutzer gezählt. Sie können ein Ereignis in eine Abfrage einbeziehen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll. Zu den Optionen gehören [!UICONTROL Anzahl der Benutzer] und [!UICONTROL Prozentsatz der Benutzer].
* **[!UICONTROL Segmente]**: Das Segment, das Sie messen möchten. Sie können ein Segment in eine Abfrage einbeziehen.

## Zeitvergleich

{{apply-time-comparison}}

## Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Trenddaten angezeigt werden sollen. Gültige Optionen sind &quot;Stündlich&quot;, &quot;Täglich&quot;, &quot;Wöchentlich&quot;, &quot;Monatlich&quot;und &quot;Quartal&quot;. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Wenn Sie beispielsweise eine Analyse betrachten, die sich auf drei Tage mit täglicher Granularität erstreckt, werden nur drei Datenpunkte angezeigt, während eine Analyse, die drei Tage mit stündlicher Granularität umfasst, 72 Datenpunkte anzeigen würde.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.
