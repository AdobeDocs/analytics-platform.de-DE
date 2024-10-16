---
title: Häufigkeitsansicht
description: Messen Sie die Interaktion anhand der Nutzungshäufigkeit.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
exl-id: 27eaa7c7-f1e1-4cf1-9d59-67ac552eb430
role: User
source-git-commit: ce04e69d2c933f893eeeff04abb0f56fb4000e6f
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 6%

---

# Ansicht [!UICONTROL Häufigkeit]

Die Ansicht ![Häufigkeit](/help/assets/icons/Histogram.svg) **[!UICONTROL Häufigkeit]** gruppiert Ereignisdaten danach, wie oft Ereignisse in Ihrem Produkt auftreten. Die vertikale Achse dieser Ansicht enthält Behälter, die die Häufigkeit des Ereignisses darstellen. Die horizontale Achse misst die Anzahl der Benutzer oder Sitzungen für jeden Behälter.

>[!VIDEO](https://video.tv.adobe.com/v/3428089/?learn=on)

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Interaktion**: Verfolgen Sie, wie engagiert Benutzer bei Ereignissen in Ihrem Produkt sind. Sie können auf einen beliebigen Teil des Balkendiagramms klicken, um ihn als Segment zu speichern. Segmente für Behälter mit geringer Interaktion können Ihnen dabei helfen festzustellen, warum Benutzer nicht mit dem Ereignis in der gewünschten Häufigkeit interagieren. Segmente für Behälter mit hoher Interaktion können Ihnen dabei helfen zu verstehen, warum Benutzer häufig mit dem Ereignis interagieren. Von dort aus können Sie andere Benutzer dazu ermutigen, ein ähnliches Verhalten anzuwenden.
* **Kundentreue**: Setzen Sie das Ereignis auf Bestellungen und die Metrik auf Benutzer. Mit dieser Ansicht können Sie Benutzer nach der Anzahl der Male gruppieren, die sie innerhalb des angegebenen Datumsbereichs auf Ihrer Site gekauft haben.
* **Support-Optimierung**: Zeigen Sie die Anzahl der Support-Aufrufe oder offenen Fälle durch den Benutzer an, um Einblicke zu erhalten, auf welche Benutzer die meisten Probleme stoßen. Anschließend können Sie ein Segment erstellen, das sich auf sein Erlebnis konzentriert, um die Probleme zu identifizieren und zu beheben.
* **An-/Abmeldedienst**: Benutzer mit geringer Interaktion neigen eher zu Abwanderung. Das Verständnis des Verhaltens stark engagierter Benutzer kann dazu beitragen, für wenig beteiligte Benutzer ein ähnliches Verhalten zu fördern, wodurch die Wahrscheinlichkeit verringert wird, dass sie ihr Abonnement kündigen.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Wechseln Sie zwischen diesem Ansichtstyp und [Nutzung](trends.md).
* **[!UICONTROL Ereignisse]**: Die Ereignisse, die Sie messen möchten. Jedes ausgewählte Ereignis wird als separates Diagramm dargestellt. Eine Zeile, die das Trendereignis darstellt, wird der Tabelle hinzugefügt. Sie können bis zu fünf Ereignisse einbeziehen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll. Zu den Optionen gehören [!UICONTROL Benutzer], [!UICONTROL Sitzungen], [!UICONTROL Prozentsatz der Benutzer] und [!UICONTROL Prozentsatz der Sitzungen]. Der Nenner für prozentsatzbasierte Metriken in dieser Ansicht sind Benutzer oder Sitzungen, die die ausgewählten Ereignisse durchgeführt haben, nicht alle aktiven Benutzer des Produkts.
* **[!UICONTROL Segmente]**: Die Segmente, die Sie messen möchten. Jedes ausgewählte Segment verdoppelt die Anzahl der Balken in der Grafik und Zeilen in der Tabelle. Sie können bis zu fünf Segmente einbeziehen.

## Diagrammeinstellungen

Die Ansicht [!UICONTROL Häufigkeit] bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Typ der Visualisierung, die Sie verwenden möchten. Zu den Optionen gehören [!UICONTROL Horizontalbalken] und [!UICONTROL Gestapelter Balken].

## Bucket-Einstellungen

Bestimmt, wie das Ereignis in Gruppen (Behälter) kategorisiert wird. In der Trendtabellenansicht werden Benutzer basierend auf der Häufigkeit der Verwendung insgesamt und in jedem Intervall zusammengefasst, d. h. 1 Benutzer kann in verschiedenen Intervallen für verschiedene Behälter zählen.

* **[!UICONTROL Automatische Behälter]**: Identifizieren Sie automatisch die optimale Behältergröße basierend auf der Datenverteilung.
* **[!UICONTROL Benutzerdefinierte Behälter]**: Passen Sie an, wie die Daten in Behälter gruppiert werden.
   * [!UICONTROL Von]: Der erste Behälter. Die Häufigkeit, die kleiner als dieser Wert ist, wird von der Berichterstellung ausgeschlossen.
   * [!UICONTROL bis]: Die Häufigkeit, die größer als dieser Wert ist, wird in den letzten Behälter gruppiert.
   * [!UICONTROL Größe]: Das Behälterintervall.

## Zeitvergleich

{{apply-time-comparison}}

## Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Trenddaten angezeigt werden sollen. Diagramm und Tabelle zeigen standardmäßig aggregierte Daten mit der Option, die Tabelle in eine Trendansicht zu erweitern. In der Trendansicht werden Benutzer basierend auf der Häufigkeit der Verwendung insgesamt und in jedem Intervall zusammengefasst, d. h. 1 Benutzer kann in verschiedenen Intervallen für verschiedene Behälter zählen.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.
