---
title: Interaktionsansicht
description: Machen Sie sich mit der Breite und Breite der Interaktion mit Funktionen vertraut.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
role: User
source-git-commit: 2b8afe1dbac5057f867437e2bfce27f3bd752d57
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 4%

---

# [!UICONTROL Interaktion] Ansicht

Die **[!UICONTROL Interaktion]** bietet einen Einblick, wie oft eine Funktion verwendet wird und wie viele Benutzer sie verwenden. Diese Analyse funktioniert am besten, wenn mehrere Funktionen miteinander verglichen werden.

Funktionen, die oben in dieser Visualisierung dargestellt werden, zeigen an, dass sie häufig von den Personen besucht werden, die sie verwenden. Funktionen, die rechts neben dieser Visualisierung dargestellt werden, weisen darauf hin, dass der größte Teil der Benutzer mit der Funktion interagiert. Die mittlere Häufigkeit, mit der eine Funktion verwendet wird, teilt das Diagramm horizontal. Der mittlere Prozentsatz aktiver täglicher Benutzer teilt das Diagramm vertikal.

* Die Funktionen oben links in der Matrix zeigen, dass eine Funktion nicht weit verbreitet ist. Bei den Personen, die es verwenden, wird es jedoch häufig verwendet.
* Die Funktionen oben rechts in der Matrix bedeuten, dass eine Funktion sowohl allgemein als auch häufig verwendet wird.
* Funktionen unten rechts in der Matrix bedeuten, dass eine Funktion zwar allgemein, jedoch nicht häufig verwendet wird.
* Funktionen unten links in der Matrix bedeuten, dass eine Funktion nicht weit verbreitet ist und auch nicht häufig verwendet wird.

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Interaktion nach Funktion**: Sie können eine direkte Korrelation zwischen Interaktion und Übernahme einer bestimmten Funktion herstellen. Wenn Sie wissen, welche Funktionen am häufigsten verwendet werden, können Sie feststellen, welche Funktionen die Optimierung priorisieren sollen.
* **Nicht genutzte Funktionen**: Funktionen mit niedrigen täglichen aktiven Benutzern, aber hoher Nutzung können auf eine ausgeblendete, aber wertvolle Funktion hinweisen. Erwägen Sie, diese Arten von Funktionen mehr Benutzern zur Verfügung zu stellen.
* **Verbessern beliebter Funktionen**: Funktionen mit hohen aktiven Benutzern, aber geringer Nutzung können darauf hinweisen, dass eine Funktion zwar dringend benötigt, aber nicht verwendet wird. Erwägen Sie, in die Verbesserung dieser Funktionen zu investieren, damit sie häufiger verwendet werden.
* **Funktionsbasierte Segmente erstellen**: Wenn Sie analysieren, wie oft eine Funktion verwendet wird, können Sie anhand der Anzahl der Anwender ermitteln, welche Arten von Benutzern eine bestimmte Funktion verwenden. Sie können Segmente basierend auf Benutzern erstellen, die eine Funktion in der Regel verwenden, oder basierend auf Benutzern, die diese Funktion häufig verwenden.
* **A/B-Tests zur Funktionsakzeptanz**: Vergleichen Sie die Nutzung mehrerer Funktionen mithilfe von Segmenten. Fügen Sie die Segmente jeder Kohorte in der Abfrageleiste hinzu, um den Unterschied bei der Funktionsnutzung einfach zu ermitteln.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ereignisse]**: Die Ereignisse, die Sie messen möchten. Diese Ereignisse stellen normalerweise die Nutzung einer bestimmten Funktion dar. Jede Auswahl wird als Punkt innerhalb der Matrix dargestellt. Sie können bis zu zehn Ereignisse einbeziehen.
* **[!UICONTROL Zählt als]**: Legen Sie die Details fest, wie die X-Achse Benutzer zählt. Sie können den durchschnittlichen Prozentsatz der aktiven Benutzer pro Tag, Woche, Monat oder Quartal messen. Die Y-Achse passt die durchschnittlichen Zeiten pro Benutzer automatisch an die X-Achse-Auswahl an.
* **[!UICONTROL Segmente]**: Die Segmente, die Sie messen möchten. Jedes ausgewählte Segment verdoppelt die Anzahl der gezeichneten Punkte im Diagramm und in den Zeilen in der Tabelle. Sie können bis zu drei Segmente einbeziehen.

## Diagrammeinstellungen

Die [!UICONTROL Interaktion] Die Ansicht bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Medien]**: Bestimmen Sie, wo die Medianlinien angezeigt werden und wie sich die gezeichneten Punkte auf diese Mediane beziehen.
   * **[!UICONTROL Standard]**: Zeigt den absoluten Wert von Nutzung und Interaktion an.
   * **[!UICONTROL Normalisiert]**: Zeigt relative Änderungen von jedem Median an.
* **[!UICONTROL Überlagerung &quot;Top-Ereignisse&quot;]**: Erfahren Sie, wie Ihre Ereignisse im Vergleich zu den häufigsten Ereignissen aussehen.

## Zeitvergleich

{{apply-time-comparison}}

## Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trenddaten angezeigt werden sollen. Dieser Ansichtstyp behandelt [!UICONTROL Intervall] ähnlich wie [!UICONTROL Zählt als] in der Abfrageleiste. Stündlich aktive Benutzer werden nicht unterstützt.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.
