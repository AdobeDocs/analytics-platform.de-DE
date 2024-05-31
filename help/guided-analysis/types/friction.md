---
title: Friktionsansicht
description: Vergleichen Sie die Konversionsraten zwischen den Schritten.
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
role: User
source-git-commit: 63dd68d31a9f2b907419fa660904f1dfdacaa0b8
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 2%

---

# [!UICONTROL Friktion] Ansicht

Die **[!UICONTROL Friktion]** -Ansicht bietet eine visuelle Darstellung eines kritischen Benutzer-Journey in Ihrem Produkt. Die horizontale Achse stellt jeden Schritt dar, den ein Benutzer durchlaufen muss. Die vertikale Achse stellt den Prozentsatz der Benutzer oder Sitzungen bei jedem Schritt dar. Alle Schritte müssen in der gewünschten Reihenfolge durchgeführt werden, können jedoch jederzeit im Berichtsfenster erfolgen.

>[!VIDEO](https://video.tv.adobe.com/v/3421663/?learn=on)

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Konversionsanalyse**: Sie können Konversionen in jeder Phase des Trichters analysieren, z. B. einen Checkout für den Einzelhandel, eine Kontoanmeldung, einen Abonnementfluss oder eine andere wichtige Journey innerhalb Ihres Produkterlebnisses. Indem Sie die Anzahl der Benutzer verfolgen, die von einem Schritt zum nächsten gelangen, können Sie Engpässe identifizieren, die ungewöhnliche oder unerwünschte Konversionsraten aufweisen. Diese Informationen sind nützlich, um zu verstehen, wo Sie die Journey Ihres Produkts verbessern können, um sofort Ergebnisse zu erzielen.
* **Experimentanalyse**: Sie können Konversionsraten über einen Trichter vergleichen, der optionale Schritte oder Schritte enthält, in denen ein A/B-Experiment ausgeführt wird. Mithilfe dieser Informationen können Sie ermitteln, welche Variante des Trichters zur höchsten Konversionsrate führt, sodass Sie mehr Benutzer in diesem Pfad ermutigen können.
* **Onboarding-Optimierung**: Optimieren Sie den Onboarding-Prozess Ihres Produkts, indem Sie das Benutzerverhalten in Bezug auf wichtige Ereignisse untersuchen. Sie können ermitteln, mit welchen Schritten Benutzer zu kämpfen haben oder welche Schritte nicht ausgeführt werden können.
* **Funktionsbereitschaft und Interaktion**: Erfahren Sie, wie Benutzer mit bestimmten Funktionen in Ihrem Produkt interagieren. Durch die Analyse des Fortschritts der Benutzer durch funktionsbezogene Schritte können Sie die Akzeptanzraten anzeigen und Bereiche identifizieren, in denen Benutzer bestimmte Funktionen möglicherweise nicht nutzen. Anschließend können Sie diese Informationen verwenden, um sich auf Funktionsverbesserungen zu konzentrieren und so die Akzeptanzraten zu erhöhen.
* **Marketing-Kanaleffizienz**: Messen Sie die Effektivität von Marketing-Kanälen. Sie können ein Segment erstellen, das sich auf Benutzer konzentriert, die mit verschiedenen Marketing-Kanälen interagiert haben (z. B. Paid Search, Display, natürliche Suche oder Direktsuche), und dann ihre Journey vergleichen, um zu sehen, welcher Kanal zu den besten Produktergebnissen führt.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Wechselt zwischen diesem Ansichtstyp und [Konversionstrends](conversion-trends.md).
* **[!UICONTROL Schritte]**: Die Ereignis-Touchpoints, die Sie verfolgen möchten. Jede Leiste im Diagramm stellt einen Schritt dar. Sie können bis zu zehn Schritte einbeziehen.
   * [!UICONTROL Vergleichen]: Jeder Schritt bietet eine Option zum Vergleichen mehrerer Ereignisse in einem einzelnen Trichterschritt und zum Erstellen eines &quot;abgespalteten Trichters&quot;. Mit dieser Funktion können Sie die Reibung von zwei Journey nebeneinander vergleichen, ohne zwei separate Analysen zu erstellen. Dies ist nützlich, wenn Schritt-Optionen vorhanden sind oder ein A/B-Experiment im Trichter ausgeführt wird.
* **[!UICONTROL Zählt als]**: Der Bereich, der auf den Trichter angewendet werden soll. Optionen umfassen [!UICONTROL Sitzungen] und [!UICONTROL Benutzer].
   * [!UICONTROL Sitzungen]: Alle Schritte müssen innerhalb derselben Sitzung erfolgen, damit sie gezählt werden.
   * [!UICONTROL Benutzer]: Alle Schritte müssen innerhalb des ausgewählten Berichtsfensters ausgeführt werden, damit sie gezählt werden können.
* **[!UICONTROL Segmente]**: Die Segmente, über die Sie den Trichter vergleichen möchten. Jedes ausgewählte Segment teilt jeden Schritt in mehrere Balken auf. Jede Farbe stellt ein anderes Segment dar. Sie können bis zu drei Segmente einbeziehen.

## Diagrammeinstellungen

Die Ansicht &quot;Friction&quot;bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, den Sie verwenden möchten. Optionen umfassen [!UICONTROL Schritte].
* **[!UICONTROL Konversion von]**: Bestimmt die Berechnung des Prozentsatzes von Schritt zu Schritt. Zu den Optionen gehören die Berechnung der Konversionsrate aus [!UICONTROL Erster Schritt] oder [!UICONTROL Vorheriger Schritt].

## Zeitvergleich

{{apply-time-comparison}}

![Fristvergleich](../assets/friction-compare.png){style="border:1px solid gray"}

## Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Sie Trenddaten anzeigen möchten. Diese Einstellung wirkt sich nicht auf Trend-Ansichten wie &quot;Friction&quot;aus.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.
