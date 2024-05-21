---
title: Frequenzansicht
description: Messen Sie die Interaktion anhand der Nutzungshäufigkeit.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
exl-id: 27eaa7c7-f1e1-4cf1-9d59-67ac552eb430
role: User
source-git-commit: 481e52bbfe06268642522b908f9b7ac66c882433
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 6%

---

# [!UICONTROL Häufigkeit] Ansicht

Die **[!UICONTROL Häufigkeit]** -Ansicht gruppiert Ereignisdaten nach der Häufigkeit von Ereignissen in Ihrem Produkt. Die vertikale Achse dieser Ansicht enthält Behälter, die die Häufigkeit des Ereignisses darstellen. Die horizontale Achse misst die Anzahl der Benutzer oder Sitzungen für jeden Behälter.

>[!VIDEO](https://video.tv.adobe.com/v/3428089/?learn=on)

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Interaktion**: Verfolgen Sie, wie engagiert Benutzer bei Ereignissen in Ihrem Produkt sind. Sie können auf einen beliebigen Teil des Balkendiagramms klicken, um ihn als Segment zu speichern. Segmente für Behälter mit geringer Interaktion können Ihnen dabei helfen festzustellen, warum Benutzer nicht mit dem Ereignis in der gewünschten Häufigkeit interagieren. Segmente für Behälter mit hoher Interaktion können Ihnen dabei helfen zu verstehen, warum Benutzer häufig mit dem Ereignis interagieren. Von dort aus können Sie andere Benutzer dazu ermutigen, ein ähnliches Verhalten anzuwenden.
* **Kundentreue**: Setzen Sie das Ereignis auf Bestellungen und die Metrik auf Benutzer. Mit dieser Ansicht können Sie Benutzer nach der Anzahl der Male gruppieren, die sie innerhalb des angegebenen Datumsbereichs auf Ihrer Site gekauft haben.
* **Support-Optimierung**: Zeigen Sie die Anzahl der Support-Aufrufe oder offenen Fälle durch den Benutzer an, um Einblicke zu erhalten, auf welche Benutzer die meisten Probleme stoßen. Anschließend können Sie ein Segment erstellen, das sich auf sein Erlebnis konzentriert, um die Probleme zu identifizieren und zu beheben.
* **Abonnementdienste**: Bei Benutzern mit geringer Interaktion ist die Wahrscheinlichkeit höher, dass sie abwandern. Das Verständnis des Verhaltens stark engagierter Benutzer kann dazu beitragen, für wenig beteiligte Benutzer ein ähnliches Verhalten zu fördern, wodurch die Wahrscheinlichkeit verringert wird, dass sie ihr Abonnement kündigen.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Wechselt zwischen diesem Ansichtstyp und [Nutzung](usage.md).
* **[!UICONTROL Ereignisse]**: Die Ereignisse, die Sie messen möchten. Jedes ausgewählte Ereignis wird als separates Diagramm dargestellt. Eine Zeile, die das Trendereignis darstellt, wird der Tabelle hinzugefügt. Sie können bis zu fünf Ereignisse einbeziehen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll. Optionen umfassen [!UICONTROL Benutzer], [!UICONTROL Sitzungen], [!UICONTROL Prozentsatz der Benutzer] und [!UICONTROL Prozentsatz der Sitzungen]. Der Nenner für prozentsatzbasierte Metriken in dieser Ansicht sind Benutzer oder Sitzungen, die die ausgewählten Ereignisse durchgeführt haben, nicht alle aktiven Benutzer des Produkts.
* **[!UICONTROL Segmente]**: Die Segmente, die Sie messen möchten. Jedes ausgewählte Segment verdoppelt die Anzahl der Balken in der Grafik und Zeilen in der Tabelle. Sie können bis zu fünf Segmente einbeziehen.

## Diagrammeinstellungen

Die [!UICONTROL Häufigkeit] Die Ansicht bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, den Sie verwenden möchten. Optionen umfassen [!UICONTROL Horizontalbalken] und [!UICONTROL Gestapelte Leiste].

## Bucket-Einstellungen

Bestimmt, wie das Ereignis in Gruppen kategorisiert wird.

* **[!UICONTROL Auto-Buckets]**: Identifizieren Sie automatisch die optimale Behältergröße basierend auf der Datenverteilung.
* **[!UICONTROL Benutzerdefinierte Behälter]**: Passen Sie an, wie die Daten in Behälter gruppiert werden.
   * [!UICONTROL Von]: Der erste Behälter. Die Häufigkeit, die kleiner als dieser Wert ist, wird von der Berichterstellung ausgeschlossen.
   * [!UICONTROL nach]: Die Frequenz, die größer als dieser Wert ist, wird in die letzte Gruppe gruppiert.
   * [!UICONTROL Größe]: Das Behälterintervall.

## Zeitvergleich

{{apply-time-comparison}}

## Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trenddaten angezeigt werden sollen. Diese Einstellung wirkt sich nicht auf Trend-Ansichten wie Häufigkeit aus.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.
