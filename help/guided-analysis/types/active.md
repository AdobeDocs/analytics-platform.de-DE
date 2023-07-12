---
title: Aktiv
description: Identifizieren Sie, wer neu ist, beibehalten, zurückkehren oder ruhend ist.
exl-id: 0a300bb2-7620-4e29-a6b5-542476893009
feature: Guided Analysis
source-git-commit: c96f30979cc8bf519a8e96a1fafa5aba2ebc4c01
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 1%

---

# Aktiv

{{release-limited-testing}}

Die **Aktiv** -Ansicht bietet Einblicke in das Wachstum und die Akquise von Benutzern über einen bestimmten Zeitraum. Die horizontale Achse ist ein Zeitintervall, während die vertikale Achse eine Benutzermessung darstellt. Benutzer sind in vier Kategorien unterteilt:

* **Neu**: Der Benutzer war im aktuellen Zeitraum aktiv, jedoch nicht zuvor. Sehen Sie, wie weit die Analyse zurückblickt, indem Sie den Mauszeiger über &quot;[!UICONTROL Neue Benutzer]&#39; in der Diagrammlegende. Der Lookback-Bereich wird basierend auf dem ausgewählten Datumsbereich und Intervall dynamisch bestimmt.
* **Wiederholen**: Der Benutzer war im aktuellen und unmittelbar vorherigen Zeitraum aktiv.
* **Rückgabe**: Der Benutzer war im aktuellen Zeitraum aktiv und nicht im unmittelbar vorherigen Zeitraum aktiv, war aber zu einem früheren Zeitpunkt aktiv. Sehen Sie, wie weit die Analyse zurückblickt, indem Sie den Mauszeiger über &quot;[!UICONTROL Wiederkehrende Benutzer]&#39; in der Diagrammlegende. Der Lookback-Bereich wird basierend auf dem ausgewählten Datumsbereich und Intervall dynamisch bestimmt.
* **Dormant**: Der Benutzer war im unmittelbar vorherigen Zeitraum aktiv, ist aber im aktuellen Zeitraum nicht aktiv. Dormant-Benutzer zählen nicht zur Gesamtanzahl aktiver Benutzer.

Alle aktiven Benutzer (neu + Wiederholen + Rückgabe) werden als Teelichtenschatten über der horizontalen Achse angezeigt, während alle ruhenden Benutzer unter der horizontalen Achse orange dargestellt werden.

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Benutzerbindung und -abwanderung:** Bietet eine klare Visualisierung für Zeiträume hoher oder niedriger Benutzerbindung. Die Erkennung dieser Zeiträume mit hoher oder niedriger Aufbewahrung kann Ihnen dabei helfen, Produktentscheidungen zu treffen, um eine hohe Beibehaltung zu fördern oder Abwanderung zu minimieren.
* **Kampagnenbewertung**: Die Anzeige einer bestimmten Kampagne kann Ihnen dabei helfen, nicht nur zu verstehen, wie viel Traffic sie generiert hat, sondern auch, wie gut die Kampagne den Benutzern geholfen hat, aktiv zu bleiben.
* **Analyse des Benutzerlebenszyklus**: Die Analyse des aktiven Nutzerwachstums während des gesamten Benutzerlebenszyklus kann dabei helfen, spezifische Phasen zu identifizieren, in denen die Benutzerinteraktion abnimmt. Wenn beispielsweise eine hohe Anzahl ruhender Benutzer für Einzelpersonen in einer Onboarding-Phase vorhanden ist, kann dies auf Nutzungsprobleme oder die Notwendigkeit einer besseren produktinternen Anleitung hinweisen.

![Aktiv](../assets/active.png)

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **Veranstaltungen**: Das Ereignis, das Sie messen möchten. Da dieser Ansichtstyp benutzerbasiert ist, wird ein Benutzer, der innerhalb des Zeitraums einmal mit dem Ereignis interagiert, als aktiver Benutzer gezählt. Sie können ein Ereignis in eine Abfrage einbeziehen.
* **Personen**: Das Segment, das Sie messen möchten. Sie können ein Segment in eine Abfrage einbeziehen.

## Diagrammeinstellungen

Die Ansicht Aktiv bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **Metrik**: Die Metrik, die Sie messen möchten. Zu den Optionen gehören die Anzahl der Benutzer und der Prozentsatz der Benutzer.
* **Diagrammtyp**: Die Art der Visualisierung, die Sie verwenden möchten. Zu den Optionen gehören &quot;Gestapelte Leiste&quot;und &quot;Gestapelter Bereich&quot;.

## Zeitvergleich anwenden

{{apply-time-comparison}}

![Vergleich der aktiven Zeit](../assets/active-compare.png)

## Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **Intervall**: Die Datumsgranularität, mit der Sie Trenddaten anzeigen möchten. Gültige Optionen sind &quot;Stündlich&quot;, &quot;Täglich&quot;, &quot;Wöchentlich&quot;, &quot;Monatlich&quot;und &quot;Quartal&quot;. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Wenn Sie beispielsweise eine Analyse betrachten, die sich auf drei Tage mit täglicher Granularität erstreckt, werden nur drei Datenpunkte angezeigt, während eine Analyse, die drei Tage mit stündlicher Granularität umfasst, 72 Datenpunkte anzeigen würde.
* **Datum**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie mit der Kalenderauswahl einen festen Datumsbereich auswählen.