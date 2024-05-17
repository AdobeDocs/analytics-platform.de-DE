---
title: Interaktionsansicht
description: Machen Sie sich mit der Breite und Tiefe der Interaktion mit Funktionen vertraut.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
role: User
exl-id: 8a48ad3b-fa30-497e-8306-f8d881b1a335
source-git-commit: a4c35466b225d44130bb55204e2fdb155fa7dee6
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 3%

---

# [!UICONTROL Interaktion] Ansicht

Die **[!UICONTROL Interaktion]** bietet einen Einblick, wie oft eine Funktion verwendet wird und wie viele Benutzer sie verwenden. Diese Analyse funktioniert am besten, wenn mehrere Funktionen miteinander verglichen werden. Sie hilft bei Investitionsentscheidungen, indem sie verstehen, was Ihr Kern, Ihre Macht, Ihre einmaligen und fragwürdigen Merkmale sind.

Funktionen, die oben in dieser Visualisierung dargestellt werden, zeigen an, dass sie häufig von engagierten Benutzern verwendet werden. Funktionen, die rechts neben dieser Visualisierung dargestellt werden, zeigen an, dass sie von Ihren aktiven Benutzern auf breiter Front verwendet werden. Die mittlere Häufigkeit, mit der eine Funktion verwendet wird, teilt das Diagramm horizontal. Der mittlere Prozentsatz aktiver Benutzer teilt das Diagramm vertikal. Die Medianberechnung basiert auf den in der Abfrage ausgewählten Ereignissen, nicht auf allen Daten.

* Die Funktionen oben links in der Matrix sind Ihre **power** -Funktionen; sie sind nicht weit verbreitet, werden aber häufig von engagierten Benutzern verwendet.
* Die Funktionen oben rechts in der Matrix sind Ihre **starke Auswirkung** -Funktionen, die sowohl allgemein als auch häufig verwendet werden.
* Die Funktionen unten links in der Matrix sind Ihre **geringe Auswirkung** -Funktionen; sie sind nicht weit verbreitet oder werden häufig verwendet.
* Die Funktionen unten rechts in der Matrix sind Ihre **einmalig** -Funktionen; sie werden zwar weithin angewendet, jedoch nicht häufig verwendet.

![Interaktionsbildschirm](../assets/feature-matrix.png)

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Interaktion nach Funktion**: Sie können eine direkte Korrelation zwischen Interaktion und Übernahme einer bestimmten Funktion herstellen. Wenn Sie wissen, welche Funktionen am häufigsten verwendet werden, können Sie feststellen, in welche Funktionen Sie weiter investieren sollten.
* **Nicht verwendete Funktionen**: Funktionen mit niedrigen aktiven Benutzern, aber hoher Auslastung können auf eine Stromversorgungsfunktion hinweisen, die zwar nützlich ist, aber von der breiteren Bevölkerung nicht entdeckt oder genutzt wird. Erwägen Sie, die Entdeckung dieser Funktionen zu verbessern, damit mehr Benutzer sie nutzen.
* **Verbessern beliebter Funktionen**: Funktionen mit hohen aktiven Benutzern, aber geringer Nutzung können darauf hinweisen, dass eine Funktion zwar dringend benötigt, aber nicht verwendet wird. Diese Situationen bieten Möglichkeiten, von Ihren Benutzern mehr darüber zu erfahren, welche Verbesserungen die Funktion für sie wertvoller machen würden.
* **Funktionsbasierte Segmente erstellen**: Zeigen Sie die Verwendung von Funktionen auf diese Weise an, um zusätzliche Analysemöglichkeiten zu erhalten. Erstellen Sie ein Segment für jeden Punkt im Diagramm, um sich weiter in diese Benutzergruppe zu vertiefen und diese Erkenntnisse auf Ihre Benutzerinteraktionsstrategie anzuwenden.
* **A/B-Tests zur Funktionsakzeptanz**: Vergleichen Sie die Nutzung mehrerer Funktionen für verschiedene Benutzergruppen. Fügen Sie in der Abfrageleiste Segmente hinzu, um den Unterschied bei der Nutzung von Funktionen über wichtige Benutzergruppen hinweg zu ermitteln.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ereignisse]**: Die Ereignisse, die Sie messen möchten. Jedes Ereignis stellt die Verwendung einer bestimmten Funktion dar und wird als Punkt in der Matrix angezeigt. Sie können bis zu zehn Ereignisse einbeziehen. Der Median wird anhand der ausgewählten Ereignisse berechnet.
* **[!UICONTROL Zählt als]**: Auf der x-Achse können Sie den durchschnittlichen Prozentsatz der aktiven Benutzer pro Tag, Woche, Monat oder Quartal messen. Die Y-Achse passt die durchschnittlichen Zeiten pro Benutzer automatisch an die X-Achse-Auswahl an.
* **[!UICONTROL Segmente]**: Die Segmente, die Sie messen möchten. Jedes ausgewählte Segment verdoppelt die Anzahl der gezeichneten Punkte im Diagramm und in den Zeilen in der Tabelle. Sie können bis zu drei Segmente einbeziehen.

>[!TIP]
>
>Wenn mehrere Ereignisse die Verwendung einer einzelnen Funktion darstellen, können Sie ein neues Ereignis ableiten, das die Funktion in Datenansichten darstellt.

## Diagrammeinstellungen

Die [!UICONTROL Interaktion] Die Ansicht bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Medien]**: Bestimmen Sie, wo die Medianlinien angezeigt werden und wie sich die gezeichneten Punkte auf diese Mediane beziehen.
   * **[!UICONTROL Standard]**: Zeigt den absoluten Wert von Nutzung und Interaktion an.
   * **[!UICONTROL Normalisiert]**: Zeigt relative Änderungen von jedem Median an.
* **[!UICONTROL Überlagerung &quot;Top-Ereignisse&quot;]**: Sehen Sie sich die Leistung Ihrer Ereignisse im Vergleich zu den 20 wichtigsten Ereignissen basierend auf der Neuigkeit und Relevanz des Unternehmens sowie der Benutzer an (derselbe Algorithmus wurde auf die Ereignisauswahl in der Abfrageleiste angewendet).

## Zeitvergleich

{{apply-time-comparison}}

## Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trenddaten angezeigt werden sollen. Dieser Ansichtstyp behandelt [!UICONTROL Intervall] ähnlich wie [!UICONTROL Zählt als] in der Abfrageleiste. Stündlich aktive Benutzer werden nicht unterstützt.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.
