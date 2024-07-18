---
title: Interaktionsansicht
description: Erfahren Sie mehr über Umfang und Tiefe der Funktionsinteraktion.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
role: User
exl-id: 8a48ad3b-fa30-497e-8306-f8d881b1a335
source-git-commit: 670443a8caf6b71f49fc63a23b5328609864a9be
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 4%

---

# Ansicht [!UICONTROL Interaktion]

Die Ansicht **[!UICONTROL Interaktion]** bietet einen Einblick, wie oft eine Funktion verwendet wird und wie viele Benutzer sie verwenden. Diese Analyse funktioniert am besten, wenn mehrere Funktionen miteinander verglichen werden. Sie hilft bei Investitionsentscheidungen, indem sie verstehen, was Ihr Kern, Ihre Macht, Ihre einmaligen und fragwürdigen Merkmale sind.

Funktionen, die oben in dieser Visualisierung dargestellt werden, zeigen an, dass sie häufig von engagierten Benutzern verwendet werden. Funktionen, die rechts neben dieser Visualisierung dargestellt werden, zeigen an, dass sie von Ihren aktiven Benutzern auf breiter Front verwendet werden. Die mittlere Häufigkeit, mit der eine Funktion verwendet wird, teilt das Diagramm horizontal. Der mittlere Prozentsatz aktiver Benutzer teilt das Diagramm vertikal. Die Medianberechnung basiert auf den in der Abfrage ausgewählten Ereignissen, nicht auf allen Daten.

* Funktionen in der linken oberen Ecke der Matrix sind Ihre **Power**-Funktionen. Sie sind zwar nicht weit verbreitet, werden aber häufig von engagierten Benutzern verwendet.
* Funktionen in der rechten oberen Ecke der Matrix sind Ihre **wirkungsvollen**-Funktionen. Sie werden sowohl häufig als auch häufig verwendet.
* Funktionen in der linken unteren Ecke der Matrix sind Ihre **Funktionen mit geringer Auswirkung**; sie werden nicht weit verbreitet oder häufig verwendet.
* Funktionen in der rechten unteren Ecke der Matrix sind Ihre **einmaligen** Funktionen. Sie sind zwar weit verbreitet, werden aber nicht häufig verwendet.

>[!VIDEO](https://video.tv.adobe.com/v/3429489/&learn=on)

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Interaktion nach Funktion**: Sie können eine direkte Korrelation zwischen Interaktion und Übernahme einer bestimmten Funktion herstellen. Wenn Sie wissen, welche Funktionen am häufigsten verwendet werden, können Sie feststellen, in welche Funktionen Sie weiter investieren sollten.
* **Entdecken Sie nicht verwendete Funktionen**: Funktionen mit niedrigen aktiven Benutzern, aber hoher Nutzung können auf eine Leistungsfunktion hinweisen, die zwar nützlich ist, aber von der breiteren Bevölkerung nicht erkannt oder verwendet wird. Erwägen Sie, die Entdeckung dieser Funktionen zu verbessern, damit mehr Benutzer sie nutzen.
* **Beliebte Funktionen verbessern**: Funktionen mit hohen aktiven Benutzern, aber geringer Nutzung können darauf hinweisen, dass eine Funktion zwar dringend benötigt, aber nicht verwendet wird. Diese Situationen bieten Möglichkeiten, von Ihren Benutzern mehr darüber zu erfahren, welche Verbesserungen die Funktion für sie wertvoller machen würden.
* **Erstellen funktionsbasierter Segmente**: Zeigen Sie die Nutzung der Funktionen auf diese Weise an, um zusätzliche Analysechancen zu erhalten. Erstellen Sie ein Segment für jeden Punkt im Diagramm, um sich weiter in diese Benutzergruppe zu vertiefen und diese Erkenntnisse auf Ihre Benutzerinteraktionsstrategie anzuwenden.
* **Übernahme von A/B-Tests durch Funktionen**: Vergleichen Sie die Nutzung mehrerer Funktionen für verschiedene Benutzergruppen. Fügen Sie in der Abfrageleiste Segmente hinzu, um den Unterschied bei der Nutzung von Funktionen über wichtige Benutzergruppen hinweg zu ermitteln.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ereignisse]**: Die Ereignisse, die Sie messen möchten. Jedes Ereignis stellt die Verwendung einer bestimmten Funktion dar und wird als Punkt in der Matrix angezeigt. Sie können bis zu zehn Ereignisse einbeziehen. Der Median wird anhand der ausgewählten Ereignisse berechnet.
* **[!UICONTROL Zählt als]**: Auf der x-Achse können Sie den durchschnittlichen Prozentsatz der aktiven täglichen, wöchentlichen, monatlichen oder vierteljährlichen Benutzer messen. Die Y-Achse passt die durchschnittlichen Zeiten pro Benutzer automatisch an die X-Achse-Auswahl an.
* **[!UICONTROL Segmente]**: Die Segmente, die Sie messen möchten. Jedes ausgewählte Segment verdoppelt die Anzahl der gezeichneten Punkte im Diagramm und in den Zeilen in der Tabelle. Sie können bis zu drei Segmente einbeziehen.

>[!TIP]
>
>Wenn mehrere Ereignisse die Verwendung einer einzelnen Funktion darstellen, können Sie ein neues Ereignis ableiten, das die Funktion in Datenansichten darstellt.

## Diagrammeinstellungen

Die Ansicht [!UICONTROL Interaktion] bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Medians]**: Bestimmen Sie, wo die Medianlinien angezeigt werden und wie die gezeichneten Punkte mit diesen Medianwerten zusammenhängen.
   * **[!UICONTROL Standard]**: Zeigt den absoluten Wert von Nutzung und Interaktion an.
   * **[!UICONTROL Normalisiert]**: Zeigt relative Änderungen von jedem Median an.
* **[!UICONTROL Top-Ereignisse-Overlay]**: Sehen Sie, wie Ihre Ereignisse im Vergleich zu den 20 wichtigsten Ereignissen aussehen, basierend auf der Neuigkeit und Relevanz von Unternehmen und Benutzern (derselbe Algorithmus wurde auf die Ereignisauswahl in der Abfrageleiste angewendet).

## Zeitvergleich

{{apply-time-comparison}}

## Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trenddaten angezeigt werden sollen. Dieser Ansichtstyp behandelt [!UICONTROL Intervall] ähnlich wie [!UICONTROL Wird in der Abfrageleiste als ] gezählt. Stündlich aktive Benutzer werden nicht unterstützt.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.
