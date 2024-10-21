---
title: Trichteranalyse
description: Vergleichen Sie die Konversionsraten zwischen den Schritten.
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
role: User
source-git-commit: f71abfb76a22171004a6f2a501c8ec70d8485478
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 2%

---

# Analyse [!UICONTROL Trichter]

Die Analyse ![ConversionTrichter](/help/assets/icons/ConversionFunnel.svg)**[!UICONTROL Trichter ]**bietet eine visuelle Darstellung eines kritischen Benutzer-Journey in Ihrem Produkt. Die horizontale Achse stellt jeden Schritt dar, den ein Benutzer durchlaufen muss. Die vertikale Achse stellt den Prozentsatz der Benutzer oder Sitzungen bei jedem Schritt dar. Alle Schritte müssen in der gewünschten Reihenfolge durchgeführt werden, können jedoch jederzeit im Berichtsfenster erfolgen.

+++ Demovideo

>[!VIDEO](https://video.tv.adobe.com/v/3421663/?learn=on){width="90%"}

+++

![Trichterzeitvergleich](../assets/funnel-compare.png)

## Anwendungsbeispiele

Anwendungsbeispiele für diese Analyse sind:

* **Konversionsanalyse**: Sie können Konversionen in jeder Phase des Trichters analysieren, z. B. einen Checkout für den Einzelhandel, eine Kontoanmeldung, einen Abonnementfluss oder eine andere wichtige Journey innerhalb Ihres Produkterlebnisses. Indem Sie die Anzahl der Benutzer verfolgen, die von einem Schritt zum nächsten gelangen, können Sie Engpässe identifizieren, die ungewöhnliche oder unerwünschte Konversionsraten aufweisen. Diese Informationen sind nützlich, um zu verstehen, wo Sie die Journey Ihres Produkts verbessern können, um sofort Ergebnisse zu erzielen.
* **Experimentierungsanalyse**: Sie können Konversionsraten über einen Trichter vergleichen, der optionale Schritte oder Schritte enthält, in denen ein A/B-Experiment ausgeführt wird. Mithilfe dieser Informationen können Sie ermitteln, welche Variante des Trichters zur höchsten Konversionsrate führt, sodass Sie mehr Benutzer in diesem Pfad ermutigen können.
* **Onboarding-Optimierung**: Optimieren Sie den Onboarding-Prozess für Ihr Produkt, indem Sie das Benutzerverhalten in Bezug auf wichtige Ereignisse untersuchen. Sie können ermitteln, mit welchen Schritten Benutzer zu kämpfen haben oder welche Schritte nicht ausgeführt werden können.
* **Funktionsbereitschaft und -interaktion**: Erfahren Sie, wie Benutzer mit bestimmten Funktionen in Ihrem Produkt interagieren. Durch die Analyse des Fortschritts der Benutzer durch funktionsbezogene Schritte können Sie die Akzeptanzraten anzeigen und Bereiche identifizieren, in denen Benutzer bestimmte Funktionen möglicherweise nicht nutzen. Anschließend können Sie diese Informationen verwenden, um sich auf Funktionsverbesserungen zu konzentrieren und so die Akzeptanzraten zu erhöhen.
* **Effektivität des Marketing-Kanals**: Messen Sie die Effektivität der Marketing-Kanäle. Sie können ein Segment erstellen, das sich auf Benutzer konzentriert, die mit verschiedenen Marketing-Kanälen interagiert haben, wie z. B. Paid Search, Display, natürliche Suche oder Direktsuche. Anschließend können Sie die Journey vergleichen, um zu sehen, welcher Kanal zu den besten Produktergebnissen führt.

## Benutzeroberfläche

Eine Übersicht über die Benutzeroberfläche der geführten Analyse finden Sie unter [Schnittstelle](../overview.md#interface) . Die folgenden Einstellungen beziehen sich auf diese Analyse:

### Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Zwischen dieser Analyse und [Konversionstrends](conversion-trends.md) wechseln.
* **[!UICONTROL Schritte]**: Die Ereignis-Touchpoints, die Sie verfolgen möchten. Jede Leiste im Diagramm stellt einen Schritt dar. Sie können bis zu zehn Schritte einbeziehen.
   * [!UICONTROL Vergleichen]: Jeder Schritt bietet eine Option zum Vergleichen mehrerer Ereignisse in einem einzelnen Trichterschritt und zum Erstellen eines &quot;abgespalteten Trichters&quot;. Mit dieser Funktion können Sie die Reibung von zwei Journey nebeneinander vergleichen, ohne zwei separate Analysen zu erstellen. Dies ist nützlich, wenn Schritt-Optionen vorhanden sind oder ein A/B-Experiment im Trichter ausgeführt wird. Unter [Trichter](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/funnel) in Customer Journey Analytics-Tutorials finden Sie ein Video, in dem erläutert wird, wie Trichter verglichen werden.
* **[!UICONTROL Zählt als]**: Der Bereich, der auf den Trichter angewendet werden soll. Zu den Optionen gehören [!UICONTROL Sitzungen] und [!UICONTROL Benutzer].
   * [!UICONTROL Sitzungen]: Alle Schritte müssen innerhalb derselben Sitzung erfolgen, damit sie gezählt werden.
   * [!UICONTROL Benutzer]: Alle Schritte müssen innerhalb des ausgewählten Berichtsfensters erfolgen, damit sie gezählt werden.
* **[!UICONTROL Segmente]**: Die Segmente, über die Sie den Trichter vergleichen möchten. Jedes ausgewählte Segment teilt jeden Schritt in mehrere Balken auf. Jede Farbe stellt ein anderes Segment dar. Sie können bis zu drei Segmente einbeziehen.

### Diagrammeinstellungen

Die Analyse [!UICONTROL Trichter] bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Typ der Visualisierung, die Sie verwenden möchten. Zu den Optionen gehören [!UICONTROL Schritte].
* **[!UICONTROL Konvertierung von]**: Bestimmt die Berechnung des Prozentsatzes von Schritt zu Schritt. Zu den Optionen gehören die Berechnung der Konvertierung aus dem [!UICONTROL ersten Schritt] oder dem [!UICONTROL vorherigen Schritt].

### Zeitvergleich

{{apply-time-comparison}}



### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Trenddaten angezeigt werden sollen. Diese Einstellung wirkt sich nicht auf Trendanalysen wie [Trichter](funnel.md) aus.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.
