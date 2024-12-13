---
title: Aktive Wachstumsanalyse
description: Identifizieren Sie, wer neu ist, bleibt, zurückkehrt oder inaktiv ist.
exl-id: 53ef7485-9cae-4663-bf61-4eb77c126830
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 7%

---

# Analyse [!UICONTROL Aktives Wachstum] {#active-growth}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_activegrowth_button"
>title="Aktives Wachstum"
>abstract="Identifizieren Sie, wer neu ist, bleibt, zurückkehrt oder inaktiv ist."

<!-- markdownlint-enable MD034 -->


Die ![PeopleGroup](/help/assets/icons/PeopleGroup.svg) **[!UICONTROL Active growth]**-Analyse bietet Einblicke in das Wachstum und die Akquise von Nutzern in einem bestimmten Zeitraum. Die horizontale Achse ist ein Zeitintervall, während die vertikale Achse ein Maß für Benutzende ist. Die Benutzer sind in vier Kategorien unterteilt:

* **[!UICONTROL Neu]**: Der Benutzer war im aktuellen Zeitraum aktiv, aber nicht zuvor. Sehen Sie, wie weit diese Analyse zurückblickt, indem Sie in der Diagrammlegende den Mauszeiger _[!UICONTROL Neue Benutzer]_ bewegen. Der Lookback-Bereich wird basierend auf dem ausgewählten Datumsbereich und Intervall dynamisch bestimmt.
* **[!UICONTROL Wiederholen]**: Der Benutzer war im aktuellen und unmittelbar vorherigen Zeitraum aktiv.
* **[!UICONTROL Zurück]**: Der Benutzer war im aktuellen Zeitraum aktiv und im unmittelbar vorherigen Zeitraum nicht aktiv, war aber zu einem früheren Zeitpunkt aktiv. Sie können sehen, wie weit die Analyse zurückblickt, indem Sie den Mauszeiger über _[!UICONTROL Benutzer zurückgeben]_ in der Legende des Diagramms bewegen. Der Lookback-Bereich wird basierend auf dem ausgewählten Datumsbereich und Intervall dynamisch bestimmt.
* **[!UICONTROL Inaktiv]**: Der/die Benutzende war unmittelbar im vorherigen Zeitraum aktiv, ist aber im aktuellen Zeitraum nicht aktiv. Inaktive Benutzende werden nicht zur Gesamtzahl der aktiven Benutzenden gezählt.

Alle aktiven Benutzenden (Neu + Wiederholen + Zurück) werden über der horizontalen Achse als echte Schattierung angezeigt, während alle inaktiven Benutzenden unter der horizontalen Achse in Orange angezeigt werden.


>[!VIDEO](https://video.tv.adobe.com/v/3421667/?learn=on)

## Anwendungsfälle

Anwendungsfälle für diese Analyse sind:

* **Benutzerbindung und Abwanderung:** Bietet eine klare Visualisierung von Zeiträumen hoher oder niedriger Benutzerbindung. Wenn Sie diese Zeiten hoher oder niedriger Kundenbindung erkennen, können Sie Produktentscheidungen treffen, um eine hohe Kundenbindung zu fördern oder die Abwanderung zu minimieren.
* **Kampagnenbewertung**: Die Anzeige einer bestimmten Kampagne hilft Ihnen zu verstehen, wie viel Traffic sie generiert hat und wie gut sie Benutzern geholfen hat, aktiv zu bleiben.
* **Benutzerlebenszyklusanalyse**: Die Analyse des aktiven Benutzerwachstums im gesamten Benutzerlebenszyklus kann dabei helfen, bestimmte Phasen zu identifizieren, in denen die Benutzerinteraktion abnimmt. Wenn beispielsweise in einer Onboarding-Phase eine hohe Anzahl von inaktiven Benutzern für Einzelanwender vorhanden ist, kann dies auf Benutzerprobleme oder einen Bedarf an besserer produktinterner Anleitung hinweisen.

## Benutzeroberfläche

Siehe [Schnittstelle](../overview.md#interface) für einen Überblick über die Oberfläche der geführten Analyse. Die folgenden Einstellungen sind für diese Analyse spezifisch:

### Abfrageleiste

Mit der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Wechseln Sie zwischen dieser Analyse und [Nettowachstum](net-growth.md).
* **[!UICONTROL Ereignisse]**: Das Ereignis, das Sie messen möchten. Da diese Analyse benutzerbasiert ist, wird ein Benutzer, der innerhalb des Zeitraums mit dem Ereignis interagiert, als aktiver Benutzer gezählt. Sie können ein Ereignis in eine Abfrage einbeziehen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll.  Die Optionen umfassen [!UICONTROL Anzahl der ]) und [!UICONTROL Prozentsatz der ].
* **[!UICONTROL Segmente]**: Das Segment, nach dem Sie Daten filtern möchten. Sie können ein Segment in eine Abfrage einbeziehen.

### Diagrammeinstellungen

Die [!UICONTROL Aktives Wachstum]-Analyse bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, den Sie verwenden möchten. Zu den Optionen gehören [!UICONTROL Gestapelter Balken] und [!UICONTROL Gestapelter Bereich].

### Zeitvergleich

{{apply-time-comparison}}

### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trend-Daten angezeigt werden sollen. Gültige Optionen sind stündlich, täglich, wöchentlich, monatlich und vierteljährlich. Derselbe Datumsbereich kann unterschiedliche Intervalle aufweisen, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Wenn Sie beispielsweise eine Analyse mit dreitägiger Granularität anzeigen, werden nur drei Datenpunkte angezeigt, während eine Analyse mit dreitägiger Granularität 72 Datenpunkte ergibt.
* **[!UICONTROL Date]**: Das Start- und Enddatum. Rollierende Datumsbereichsvorgaben und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Sie können auch den Kalenderselektor verwenden, um einen festen Datumsbereich auszuwählen.

<!--
## Example

See below for an example of the analysis.

![Active time compare](../assets/active-growth-compare.png)

-->
