---
title: Trendanalyse
description: Messen Sie die Benutzerinteraktion im Zeitverlauf.
exl-id: b632475f-371e-4156-9ffc-b138325aa120
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 6%

---

# Analyse [!UICONTROL Trends] {#trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_trends_button"
>title="Trends"
>abstract="Messen Sie die Benutzerinteraktion im Zeitverlauf."

<!-- markdownlint-enable MD034 -->

Die ![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL Trends]**-Analyse bietet wertvolle Einblicke in die Leistung Ihres Produkts oder das Verhalten Ihrer Benutzer im Laufe der Zeit. Die horizontale Achse dieses Berichts ist ein Zeitintervall, während die vertikale Achse Ihre gewünschten Ereignisse misst.


>[!VIDEO](https://video.tv.adobe.com/v/3421666/?quality=12&learn=on)

## Anwendungsfälle

Anwendungsfälle für diese Analyse sind:

* **Evaluate product performance**: Mit Trends können Sie die Gesamtleistung Ihres Produkts über einen bestimmten Zeitraum bewerten. Durch die Analyse von Metriken wie Benutzerinteraktion, Akzeptanz oder Konversionsraten können Sie feststellen, ob sich die Leistung Ihres Produkts verbessert, stagniert oder abnimmt.
* **Funktionsübernahme**: Mithilfe von Trends können Sie verstehen, wie Benutzende neue Funktionen oder Aktualisierungen annehmen, die Sie veröffentlichen. Sie können feststellen, welche Funktionen beliebt sind und welche verbessert werden müssen. Diese Informationen ermöglichen es Ihnen, datengesteuerte Entscheidungen darüber zu treffen, welche Funktionen für Ihre Entwicklungsbemühungen zu priorisieren sind.
* **Benutzerverhalten**: Trends können einen Einblick in das Benutzerverhalten im Laufe der Zeit geben. Durch die Untersuchung bestimmter Aktionen, die Benutzer durchführen, können Sie Muster identifizieren, bei denen Benutzer möglicherweise abbrechen. Sie können Einblicke aus dieser Analyse mit [Trichter](funnel.md) kombinieren, um noch mehr Einblicke in das Verhalten zu erhalten.
* **A/B-Tests und**: Wenn Sie A/B-Tests innerhalb Ihres Produkts durchführen, können Sie mithilfe von Trends ermitteln, welche Tests im Laufe der Zeit am erfolgreichsten sind.

## Benutzeroberfläche

Siehe [Schnittstelle](../overview.md#interface) für einen Überblick über die Oberfläche der geführten Analyse. Die folgenden Einstellungen sind für diese Analyse spezifisch:

### Abfrageleiste

Mit der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Wechseln Sie zwischen dieser Analyse und [Häufigkeit](frequency.md).
* **[!UICONTROL Ereignisse und Metriken]**: Die Ereignisse oder Metriken, die Sie messen möchten. Jede Auswahl wird als Diagrammreihe und Tabellenzeile dargestellt. Ereignisse und Metriken können nicht in der Abfrage kombiniert werden. Sobald Sie Ihre erste Auswahl getroffen haben, müssen die verbleibenden Abfrageauswahlen vom gleichen Typ sein. Sie können bis zu fünf Auswahlen einschließen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll.  Die Optionen umfassen Ereignisse, Sitzungen, Benutzer, Prozentsatz der Benutzer, Ereignisse pro Sitzung und Ereignisse pro Benutzer. Als Optionen gezählt gelten nur für Ereignisabfragen und werden für Metrikabfragen entfernt.
* **[!UICONTROL Segmente]**: Die Segmente, die Sie messen möchten. Jedes ausgewählte Segment verdoppelt die Anzahl der Diagrammreihen und Tabellenzeilen. Sie können bis zu fünf Segmente einbeziehen.
* **[!UICONTROL Aufschlüsselungseigenschaft]**: Schlüsselt die Diagrammreihen und Tabellenzeilen nach den Werten der ausgewählten Eigenschaft auf. Eine einzelne Aufschlüsselungseigenschaft wird unterstützt. Die 20 wichtigsten Werte werden in der Tabelle angezeigt, und bis zu zehn Werte können im Diagramm angezeigt werden. Sie können eine Zeile im Diagramm ein- oder ausblenden, indem Sie das Symbol ![Ausblenden anzeigen](../assets/hide-in-chart.png) umschalten.

### Diagrammeinstellungen

Die [!UICONTROL Trends]-Analyse bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, den Sie verwenden möchten. Zu den Optionen gehören Linie, Balken, gestapelter Balken und gestapelter Bereich.

### Überlagerungen

Fügen Sie dem Diagramm zusätzliche Daten hinzu. Wenn mehr als eine Serie im Diagramm sichtbar ist, werden Überlagerungen nur beim Bewegen des Mauszeigers angezeigt.

* **[!UICONTROL Anomalieerkennung]**: Führt die [Anomalieerkennung](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) für die Trend-Analyse aus. Ausreißer werden als Punkte angezeigt, über die Sie den Mauszeiger bewegen können, um weitere Informationen zu erhalten.
* **[!UICONTROL Trendlinienüberlagerung]**: Fügt dem Diagramm eine Trendlinie hinzu, die dabei hilft, ein klareres Muster in den Daten darzustellen.
   * [!UICONTROL Linear]: Erstellt eine gerade Regressionslinie. Am besten geeignet für einfache lineare Daten, die mit konstanter Geschwindigkeit zunehmen oder abnehmen. Gleichung: `y = a + b * x`
   * [!UICONTROL Logarithmisch]: Erstellt eine gekrümmte Regressionslinie. Optimiert für Daten, die schnell ansteigen oder abnehmen und dann eine höhere Datenebene aufweisen. Gleichung: `y = a + b * log(x)`
   * [!UICONTROL Gleitender Durchschnitt]: Erstellt eine glatte Trendlinie basierend auf einer Reihe von Durchschnittswerten. Ein gleitender Mittelwert, der auch als rollierender Durchschnitt bezeichnet wird, nutzt eine bestimmte Anzahl vorheriger Datenpunkte (bestimmt durch Ihre Auswahl), errechnet einen Durchschnittswert und verwendet den Durchschnittswert als Punkt auf der Linie. Beispiele sind der gleitende Durchschnitt für sieben Tage oder der gleitende Durchschnitt für vier Wochen. Die verfügbaren Optionen für angepasste Durchschnittswerte hängen von Ihrem ausgewählten Intervall und Datumsbereich ab.

### Zeitvergleich

{{apply-time-comparison}}


### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trend-Daten angezeigt werden sollen. Gültige Optionen sind stündlich, täglich, wöchentlich, monatlich und vierteljährlich. Derselbe Datumsbereich kann unterschiedliche Intervalle aufweisen, die sich auf die Anzahl der Datenpunkte im Diagramm und auf die Anzahl der Spalten in der Tabelle auswirken. Wenn Sie beispielsweise eine Analyse mit dreitägiger Granularität anzeigen, werden nur drei Datenpunkte angezeigt, während eine Analyse mit dreitägiger Granularität 72 Datenpunkte ergibt.
* **[!UICONTROL Date]**: Das Start- und Enddatum. Rollierende Datumsbereichsvorgaben und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Sie können auch den Kalenderselektor verwenden, um einen festen Datumsbereich auszuwählen.


<!--

## Example

See below for an example of the analysis.

![Trends compare](../assets/trends-compare.png)

-->