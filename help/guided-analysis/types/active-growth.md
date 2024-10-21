---
title: Aktive Wachstumsanalyse
description: Identifizieren Sie, wer neu ist, bleibt, zurückkehrt oder inaktiv ist.
exl-id: 53ef7485-9cae-4663-bf61-4eb77c126830
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
role: User
source-git-commit: 7ccc9f28acf08fb49d86005abb7fbb648a1564ce
workflow-type: tm+mt
source-wordcount: '627'
ht-degree: 3%

---

# Analyse [!UICONTROL Aktives Wachstum]

Die Analyse ![PeopleGroup](/help/assets/icons/PeopleGroup.svg) **[!UICONTROL Aktives Wachstum]** bietet Einblicke in das Wachstum und die Akquise von Benutzern über einen bestimmten Zeitraum. Die horizontale Achse ist ein Zeitintervall, während die vertikale Achse eine Benutzermessung darstellt. Benutzer sind in vier Kategorien unterteilt:

* **[!UICONTROL Neu]**: Der Benutzer war während des aktuellen Zeitraums aktiv, jedoch nicht zuvor. Sehen Sie, wie weit die Analyse zurückblickt, indem Sie in der Diagrammlegende den Mauszeiger über _[!UICONTROL Neue Benutzer]_ bewegen. Der Lookback-Bereich wird basierend auf dem ausgewählten Datumsbereich und Intervall dynamisch bestimmt.
* **[!UICONTROL Wiederholen]**: Der Benutzer war im aktuellen und unmittelbar vorherigen Zeitraum aktiv.
* **[!UICONTROL Zurück]**: Der Benutzer war im aktuellen Zeitraum aktiv und nicht im unmittelbar vorherigen Zeitraum aktiv, war aber zu einem früheren Zeitpunkt aktiv. Sehen Sie, wie weit die Analyse zurückblickt, indem Sie in der Diagrammlegende den Mauszeiger über _[!UICONTROL Zurückkehrende Benutzer]_ bewegen. Der Lookback-Bereich wird basierend auf dem ausgewählten Datumsbereich und Intervall dynamisch bestimmt.
* **[!UICONTROL Dormant]**: Der Benutzer war im unmittelbar vorherigen Zeitraum aktiv, ist aber im aktuellen Zeitraum nicht aktiv. Dormant-Benutzer zählen nicht zur Gesamtanzahl aktiver Benutzer.

Alle aktiven Benutzer (neu + Wiederholen + Rückgabe) werden als Teelichtenschatten über der horizontalen Achse angezeigt, während alle ruhenden Benutzer unter der horizontalen Achse orange dargestellt werden.


>[!VIDEO](https://video.tv.adobe.com/v/3421667/?learn=on)

## Anwendungsbeispiele

Anwendungsbeispiele für diese Analyse sind:

* **Benutzerbindung und -abwanderung:** Bietet eine klare Visualisierung der Zeiträume mit hoher oder niedriger Benutzerbindung. Die Erkennung dieser Zeiträume mit hoher oder niedriger Aufbewahrung kann Ihnen dabei helfen, Produktentscheidungen zu treffen, um eine hohe Beibehaltung zu fördern oder Abwanderung zu minimieren.
* **Kampagnenbewertung**: Die Anzeige einer bestimmten Kampagne kann Ihnen dabei helfen zu verstehen, wie viel Traffic sie generiert hat und wie gut sie den Benutzern geholfen hat, aktiv zu bleiben.
* **Analyse des Benutzerlebenszyklus**: Die Analyse des aktiven Benutzerwachstums während des gesamten Benutzerlebenszyklus kann dabei helfen, bestimmte Phasen zu identifizieren, in denen die Benutzerinteraktion abnimmt. Wenn beispielsweise eine hohe Anzahl ruhender Benutzer für Einzelpersonen in einer Onboarding-Phase vorhanden ist, kann dies auf Nutzungsprobleme oder die Notwendigkeit einer besseren produktinternen Anleitung hinweisen.

## Benutzeroberfläche

Eine Übersicht über die Benutzeroberfläche der geführten Analyse finden Sie unter [Schnittstelle](../overview.md#interface) . Die folgenden Einstellungen beziehen sich auf diese Analyse:

### Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Wechseln Sie zwischen dieser Analyse und [Nettowachstum](net-growth.md).
* **[!UICONTROL Ereignisse]**: Das Ereignis, das Sie messen möchten. Da diese Analyse benutzerbasiert ist, wird ein Benutzer, der innerhalb des Zeitraums einmal mit dem Ereignis interagiert, als aktiver Benutzer gezählt. Sie können ein Ereignis in eine Abfrage einbeziehen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll. Zu den Optionen gehören [!UICONTROL Anzahl der Benutzer] und [!UICONTROL Prozentsatz der Benutzer].
* **[!UICONTROL Segmente]**: Das Segment, nach dem Sie Daten filtern möchten. Sie können ein Segment in eine Abfrage einbeziehen.

### Diagrammeinstellungen

Die Analyse [!UICONTROL Aktives Wachstum] bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Typ der Visualisierung, die Sie verwenden möchten. Zu den Optionen gehören [!UICONTROL Gestapelter Balken] und [!UICONTROL Gestapelter Bereich].

### Zeitvergleich

{{apply-time-comparison}}

### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Trenddaten angezeigt werden sollen. Gültige Optionen sind &quot;Stündlich&quot;, &quot;Täglich&quot;, &quot;Wöchentlich&quot;, &quot;Monatlich&quot;und &quot;Quartal&quot;. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Wenn Sie beispielsweise eine Analyse betrachten, die sich auf drei Tage mit täglicher Granularität erstreckt, werden nur drei Datenpunkte angezeigt, während eine Analyse, die drei Tage mit stündlicher Granularität umfasst, 72 Datenpunkte anzeigen würde.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.

<!--
## Example

See below for an example of the analysis.

![Active time compare](../assets/active-growth-compare.png)

-->
