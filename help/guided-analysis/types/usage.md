---
title: Nutzungsansicht
description: Benutzerinteraktion im Lauf der Zeit messen.
exl-id: b632475f-371e-4156-9ffc-b138325aa120
feature: Guided Analysis
keywords: Produktanalyse
source-git-commit: 170737214fea4dbd4d90d33ebf770920c8344fb1
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 2%

---

# [!UICONTROL Nutzung] Ansicht

Die **[!UICONTROL Nutzung]** -Ansicht bietet wertvolle Einblicke in die Leistung Ihres Produkts oder das Verhalten Ihrer Benutzer im Zeitverlauf. Die horizontale Achse dieses Berichts ist ein Zeitintervall, während die vertikale Achse Ihre gewünschten Ereignisse misst.

>[!VIDEO](https://video.tv.adobe.com/v/3421666/?learn=on)

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Bewertung der Produktleistung**: Trends ermöglichen es Ihnen, die Gesamtleistung Ihres Produkts über einen bestimmten Zeitraum zu bewerten. Durch die Analyse von Metriken wie Benutzerinteraktionen, Adoptions- oder Konversionsraten können Sie feststellen, ob die Leistung Ihres Produkts sich verbessert, stagniert oder sinkt.
* **Funktionsbereitstellung**: Trends ermöglichen Ihnen, zu verstehen, wie Benutzer neue Funktionen oder Aktualisierungen übernehmen, die Sie veröffentlichen. Sie können bestimmen, welche Funktionen beliebt sind und welche Funktionen verbessert werden müssen. Diese Informationen ermöglichen es Ihnen, datenbasierte Entscheidungen darüber zu treffen, welche Funktionen Ihre Entwicklungsbemühungen priorisieren sollen.
* **Benutzerverhalten**: Trends können Einblicke in das Benutzerverhalten im Zeitverlauf bieten. Indem Sie bestimmte Aktionen untersuchen, die Benutzer ausführen, können Sie Muster identifizieren, in denen Benutzer abbrechen können. Sie können Einblicke aus dieser Ansicht mit [Friktion](friction.md) für noch mehr Einblicke in das Verhalten.
* **A/B-Tests und -Experimente**: Wenn Sie in Ihrem Produkt A/B-Tests durchführen, können Sie mithilfe von Trends messen, welche Tests im Laufe der Zeit am erfolgreichsten sind.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Veranstaltungen]**: Die Ereignisse, die Sie messen möchten. Jedes ausgewählte Ereignis wird als Diagrammreihen und Tabellenzeile dargestellt. Sie können bis zu fünf Ereignisse einbeziehen.
* **[!UICONTROL Personen]**: Die Segmente, die Sie messen möchten. Jedes ausgewählte Segment verdoppelt die Anzahl der Diagrammreihen und Tabellenzeilen. Sie können bis zu fünf Segmente einbeziehen.
* **[!UICONTROL Aufschlüsselungseigenschaft]**: Schlüsselt die Diagrammreihen und Tabellenzeilen nach den Werten der ausgewählten Eigenschaft auf. Eine einzelne Aufschlüsselungseigenschaft wird unterstützt. Die Top-20-Werte werden in der Tabelle angezeigt und bis zu zehn Werte können in der Grafik angezeigt werden. Sie können eine Zeile im Diagramm ausblenden oder verfügbar machen, indem Sie die ![Symbol zum Ausblenden](../assets/hide-in-chart.png) Symbol.

## Diagrammeinstellungen

Die [!UICONTROL Nutzung] Die Ansicht bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Metrik]**: Die zu messende Metrik. Zu den Optionen gehören Ereignisse, Sitzungen, Benutzer, Ereignisse pro Sitzung und Ereignisse pro Benutzer.
* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, den Sie verwenden möchten. Zu den Optionen gehören &quot;Linie&quot;, &quot;Balken&quot;, &quot;Gestapelte Leiste&quot;und &quot;Gestapelter Bereich&quot;.

## Überlagerungen

Fügen Sie dem Diagramm zusätzliche Daten hinzu. Wenn mehrere Reihen im Diagramm sichtbar sind, werden Überlagerungen nur beim Bewegen des Mauszeigers angezeigt.

* **[!UICONTROL Anomalieerkennung]**: Ausführungen [Anomalieerkennung](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) in der Trendanalyse. Ausreißer erscheinen als Punkte, über die Sie den Mauszeiger bewegen können, um weitere Informationen zu erhalten.
* **[!UICONTROL Trendzeilenüberlagerung]**: Fügt dem Diagramm eine Trendlinie hinzu, die dazu beiträgt, ein klareres Muster in den Daten darzustellen.
   * [!UICONTROL Linear]: Erstellt eine gerade Regressionslinie. Am besten für einfache lineare Daten, die stetig zunehmen oder abnehmen. Gleichung: `y = a + b * x`
   * [!UICONTROL Logarithmisch]: Erstellt eine gekrümmte Regressionslinie. Am besten für Daten, die schnell zunehmen oder abnehmen und dann weiter steigen. Gleichung: `y = a + b * log(x)`
   * [!UICONTROL anpassbarer Durchschnittswert]: Erstellt eine glatte Trendlinie basierend auf einer Reihe von Durchschnittswerten. Ein anpassbarer Durchschnittswert, der auch als rollierender Durchschnitt bezeichnet wird, verwendet eine bestimmte Anzahl vorheriger Datenpunkte (bestimmt durch Ihre Auswahl), errechnet einen Durchschnittswert und verwendet den Durchschnittswert als Punkt in der Zeile. Beispiele sind der anpassbare Durchschnittswert von sieben Tagen oder der anpassbare Durchschnittswert von vier Wochen. Die verfügbaren anpassbaren Durchschnittsoptionen hängen von Ihrem ausgewählten Intervall und Datumsbereich ab.

## Zeitvergleich anwenden

{{apply-time-comparison}}

![Zeitvergleich der Nutzung](../assets/usage-compare.png)

## Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Sie Trenddaten anzeigen möchten. Gültige Optionen sind &quot;Stündlich&quot;, &quot;Täglich&quot;, &quot;Wöchentlich&quot;, &quot;Monatlich&quot;und &quot;Quartal&quot;. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Wenn Sie beispielsweise eine Analyse betrachten, die sich auf drei Tage mit täglicher Granularität erstreckt, werden nur drei Datenpunkte angezeigt, während eine Analyse, die drei Tage mit stündlicher Granularität umfasst, 72 Datenpunkte anzeigen würde.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.
