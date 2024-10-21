---
title: Trendanalyse
description: Messen Sie die Benutzerinteraktion im Zeitverlauf.
exl-id: b632475f-371e-4156-9ffc-b138325aa120
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
role: User
source-git-commit: 7ccc9f28acf08fb49d86005abb7fbb648a1564ce
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 3%

---

# Analyse [!UICONTROL Trends]

Die Analyse ![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL Trends]** bietet wertvolle Einblicke in die Leistung Ihres Produkts oder das Verhalten Ihrer Benutzer im Zeitverlauf. Die horizontale Achse dieses Berichts ist ein Zeitintervall, während die vertikale Achse Ihre gewünschten Ereignisse misst.

>[!VIDEO](https://video.tv.adobe.com/v/3421666/?learn=on)

## Anwendungsbeispiele

Anwendungsbeispiele für diese Analyse sind:

* **Bewertung der Produktleistung**: Mit Trends können Sie die Gesamtleistung Ihres Produkts über einen bestimmten Zeitraum bewerten. Durch die Analyse von Metriken wie Benutzerinteraktionen, Adoptions- oder Konversionsraten können Sie feststellen, ob die Leistung Ihres Produkts sich verbessert, stagniert oder sinkt.
* **Übernahme der Funktionen**: Anhand von Trends können Sie erkennen, wie Benutzer neue Funktionen oder Aktualisierungen übernehmen, die Sie veröffentlichen. Sie können bestimmen, welche Funktionen beliebt sind und welche Funktionen verbessert werden müssen. Diese Informationen ermöglichen es Ihnen, datenbasierte Entscheidungen darüber zu treffen, welche Funktionen Ihre Entwicklungsbemühungen priorisieren sollen.
* **Benutzerverhalten**: Trends können Einblicke in das Benutzerverhalten im Zeitverlauf bieten. Indem Sie bestimmte Aktionen untersuchen, die Benutzer ausführen, können Sie Muster identifizieren, in denen Benutzer abbrechen können. Sie können Einblicke aus dieser Analyse mit [Trichter](funnel.md) kombinieren, um noch mehr Einblicke in das Verhalten zu erhalten.
* **A/B-Tests und -Experimente**: Wenn Sie innerhalb Ihres Produkts A/B-Tests durchführen, können Sie mithilfe von Trends messen, welche Tests im Laufe der Zeit am erfolgreichsten sind.

## Benutzeroberfläche

Eine Übersicht über die Benutzeroberfläche der geführten Analyse finden Sie unter [Schnittstelle](../overview.md#interface) . Die folgenden Einstellungen beziehen sich auf diese Analyse:

### Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Zwischen dieser Analyse und [Häufigkeit](frequency.md) wechseln.
* **[!UICONTROL Ereignisse und Metriken]**: Die Ereignisse oder Metriken, die Sie messen möchten. Jede Auswahl wird als Diagrammreihen und Tabellenzeile dargestellt. Ereignisse und Metriken können nicht in der Abfrage kombiniert werden. Sobald Sie Ihre erste Auswahl getroffen haben, müssen die verbleibenden Abfrageauswahlen denselben Typ aufweisen. Sie können bis zu fünf Auswahlmöglichkeiten auswählen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll. Zu den Optionen gehören Ereignisse, Sitzungen, Benutzer, Prozentsatz der Benutzer, Ereignisse pro Sitzung und Ereignisse pro Benutzer. Wird gezählt, da Optionen nur für Ereignisabfragen anwendbar sind und für Metrikabfragen entfernt werden.
* **[!UICONTROL Segmente]**: Die Segmente, die Sie messen möchten. Jedes ausgewählte Segment verdoppelt die Anzahl der Diagrammreihen und Tabellenzeilen. Sie können bis zu fünf Segmente einbeziehen.
* **[!UICONTROL Aufschlüsselungseigenschaft]**: Schlüsselt die Diagramm- und Tabellenzeilen nach den Werten der ausgewählten Eigenschaft auf. Eine einzelne Aufschlüsselungseigenschaft wird unterstützt. Die Top-20-Werte werden in der Tabelle angezeigt und bis zu zehn Werte können in der Grafik angezeigt werden. Sie können eine Zeile im Diagramm ein- oder ausblenden, indem Sie auf das Symbol ![Ausblenden anzeigen](../assets/hide-in-chart.png) klicken.

### Diagrammeinstellungen

Die Analyse [!UICONTROL Trends] bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Typ der Visualisierung, die Sie verwenden möchten. Zu den Optionen gehören &quot;Linie&quot;, &quot;Balken&quot;, &quot;Gestapelte Leiste&quot;und &quot;Gestapelter Bereich&quot;.

### Überlagerungen

Fügen Sie dem Diagramm zusätzliche Daten hinzu. Wenn mehrere Reihen im Diagramm sichtbar sind, werden Überlagerungen nur beim Bewegen des Mauszeigers angezeigt.

* **[!UICONTROL Anomalieerkennung]**: Führt [Anomalieerkennung](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) in der Trendanalyse aus. Ausreißer erscheinen als Punkte, über die Sie den Mauszeiger bewegen können, um weitere Informationen zu erhalten.
* **[!UICONTROL Trendzeilenüberlagerung]**: Fügt dem Diagramm eine Trendlinie hinzu, die dazu beiträgt, ein klareres Muster in den Daten darzustellen.
   * [!UICONTROL Linear]: Erstellt eine gerade Regressionslinie. Am besten für einfache lineare Daten, die stetig zunehmen oder abnehmen. Gleichung: `y = a + b * x`
   * [!UICONTROL Logarithmisch]: Erstellt eine gekrümmte Regressionslinie. Am besten für Daten, die schnell zunehmen oder abnehmen und dann weiter steigen. Gleichung: `y = a + b * log(x)`
   * [!UICONTROL Beweglicher Durchschnitt]: Erstellt eine glatte Trendlinie basierend auf einer Reihe von Durchschnittswerten. Ein anpassbarer Durchschnittswert, der auch als rollierender Durchschnitt bezeichnet wird, verwendet eine bestimmte Anzahl vorheriger Datenpunkte (bestimmt durch Ihre Auswahl), errechnet einen Durchschnittswert und verwendet den Durchschnittswert als Punkt in der Zeile. Beispiele sind der anpassbare Durchschnittswert von sieben Tagen oder der anpassbare Durchschnittswert von vier Wochen. Die verfügbaren anpassbaren Durchschnittsoptionen hängen von Ihrem ausgewählten Intervall und Datumsbereich ab.

### Zeitvergleich

{{apply-time-comparison}}


### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Trenddaten angezeigt werden sollen. Gültige Optionen sind &quot;Stündlich&quot;, &quot;Täglich&quot;, &quot;Wöchentlich&quot;, &quot;Monatlich&quot;und &quot;Quartal&quot;. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Wenn Sie beispielsweise eine Analyse betrachten, die sich auf drei Tage mit täglicher Granularität erstreckt, werden nur drei Datenpunkte angezeigt, während eine Analyse, die drei Tage mit stündlicher Granularität umfasst, 72 Datenpunkte anzeigen würde.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.

## Beispiel

Unten finden Sie ein Beispiel für die Analyse.

![Trends vergleichen](../assets/trends-compare.png)
