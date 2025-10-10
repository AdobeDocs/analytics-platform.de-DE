---
title: Analyse „Aktives Wachstum“
description: Identifizieren Sie, wer neu ist, bleibt, zurückkehrt oder inaktiv ist.
exl-id: 53ef7485-9cae-4663-bf61-4eb77c126830
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
role: User
source-git-commit: be617c59cd2fced0031fda1130b86e638bee8f68
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 92%

---

# Analyse [!UICONTROL Aktives Wachstum] {#active-growth}

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_activegrowth_button"
>title="Aktives Wachstum"
>abstract="Identifizieren Sie, wer neu ist, bleibt, zurückkehrt oder inaktiv ist."



Die Analyse ![PeopleGroup](/help/assets/icons/PeopleGroup.svg) **[!UICONTROL Aktives Wachstum]** liefert Erkenntnisse zu Wachstum und Akquise von Benutzenden in einem bestimmten Zeitraum. Die horizontale Achse ist ein Zeitintervall, die vertikale Achse ein Maß für Benutzende. Die Benutzenden sind in vier Kategorien unterteilt:

* **[!UICONTROL Neu]**: Die Person war im aktuellen Zeitraum aktiv, aber nicht zuvor. Um zu erfahren, wie weit die Analyse zurückreicht, bewegen Sie den Mauszeiger in der Diagrammlegende über _[!UICONTROL Neue Benutzende]_. Der Lookback-Bereich wird basierend auf dem ausgewählten Datumsbereich und Intervall dynamisch bestimmt.
* **[!UICONTROL Wiederkehrend]**: Die Person war im aktuellen und unmittelbar vorherigen Zeitraum aktiv.
* **[!UICONTROL Rückkehrend]**: Die Person war im aktuellen Zeitraum aktiv und im unmittelbar vorherigen Zeitraum nicht aktiv, war aber zu einem früheren Zeitpunkt aktiv. Um zu erfahren, wie weit die Analyse zurückreicht, bewegen Sie den Mauszeiger in der Diagrammlegende über _[!UICONTROL Rückkehrende Benutzende]_. Der Lookback-Bereich wird basierend auf dem ausgewählten Datumsbereich und Intervall dynamisch bestimmt.
* **[!UICONTROL Inaktiv]**: Die Person war im unmittelbar vorherigen Zeitraum aktiv, ist aber im aktuellen Zeitraum nicht aktiv. Inaktive Benutzende werden nicht zur Gesamtzahl der aktiven Benutzenden gezählt.

Alle aktiven Benutzenden (Neu + Wiederkehrend + Rückkehrend) werden über der horizontalen Achse in einem hellen Blaugrün angezeigt, während alle inaktiven Benutzenden unter der horizontalen Achse in Orange angezeigt werden.


>[!VIDEO](https://video.tv.adobe.com/v/3421667/?quality=12&learn=on)

## Anwendungsfälle

Zu den Anwendungsfällen für diese Analyse gehören:

* **Benutzerbindung und Abwanderung:** Bietet eine klare Visualisierung von Zeiträumen hoher oder niedriger Benutzerbindung. Wenn Sie diese Zeiten hoher oder niedriger Bindung erkennen, können Sie Produktentscheidungen treffen, um eine hohe Bindung zu fördern oder die Abwanderung zu minimieren.
* **Kampagnenbewertung**: Durch Betrachtung einer bestimmten Kampagne können Sie nachvollziehen, wie viel Traffic diese generiert hat und inwiefern sie zu anhaltenden Benutzerinteraktionen beigetragen hat.
* **Benutzerlebenszyklusanalyse**: Die Analyse des aktiven Benutzerwachstums im gesamten Benutzerlebenszyklus kann dabei helfen, bestimmte Phasen zu identifizieren, in denen die Benutzerinteraktion abnimmt. Wenn beispielsweise in der Onboarding-Phase eine hohe Anzahl von inaktiven Benutzenden vorhanden ist, kann dies auf Probleme bei der Anwenderfreundlichkeit oder einen Bedarf an einer besseren produktinternen Anleitung hinweisen.

## Benutzeroberfläche

Einen Überblick über die Benutzeroberfläche für die geführte Analyse erhalten Sie unter [Benutzeroberfläche](../overview.md#interface). Die folgenden Einstellungen sind für diese Analyse spezifisch:

### Abfrageleiste

Mit der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Wechseln Sie zwischen dieser Analyse und [Nettowachstum](net-growth.md).
* **[!UICONTROL Ereignisse]**: Die Ereignisse, die gemessen werden sollen. Da diese Analyse benutzerbasiert ist, wird eine Person, die innerhalb des Zeitraums mit dem Ereignis interagiert, zur Gruppe der aktiven Benutzenden gezählt. Sie können ein Ereignis in eine Abfrage einbeziehen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll. <ul><li>**[!UICONTROL Optionen]** umfassen [!UICONTROL Anzahl der &#x200B;] und [!UICONTROL Prozentsatz der Benutzer].</li><li>[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} Zusätzliche **[!UICONTROL B2B-Optionen]** sind für Customer Journey Analytics B2B edition verfügbar: [!UICONTROL Globale Konten], [!UICONTROL Konten], [!UICONTROL Einkaufsgruppen], [!UICONTROL Opportunities], [!UICONTROL Prozentsatz der globalen Konten], [!UICONTROL Prozentsatz der Konten], [!UICONTROL Prozentsatz der Einkaufsgruppen] und [!UICONTROL Prozentsatz der Vertriebschancen].</li></ul>
* **[!UICONTROL Segmente]**: Das Segment, nach dem Daten segmentiert werden sollen. Sie können ein Segment in eine Abfrage einbeziehen.

### Diagrammeinstellungen

Die Analyse [!UICONTROL Aktives Wachstum] bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, der verwendet werden soll. Zu den Optionen gehören [!UICONTROL Gestapelter Balken] und [!UICONTROL Gestapelter Bereich].

### Zeitvergleich

{{apply-time-comparison}}

### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trend-Daten angezeigt werden sollen. Gültige Optionen sind „Stündlich“, „Täglich“, „Wöchentlich“, „Monatlich“ und „Quartalsweise“. Derselbe Datumsbereich kann unterschiedliche Intervalle aufweisen, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Bei einer Analyse über drei Tage mit täglicher Granularität werden beispielsweise nur drei Datenpunkte angezeigt, während eine Analyse über drei Tage mit stündlicher Granularität 72 Datenpunkte ergibt.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Ihnen stehen rollierende Datumsbereichsvorgaben und zuvor gespeicherte benutzerdefinierte Bereiche zur Verfügung. Sie können auch die Kalenderauswahl verwenden, um einen festen Datumsbereich zu definieren.

<!--
## Example

See below for an example of the analysis.

![Active time compare](../assets/active-growth-compare.png)

-->
