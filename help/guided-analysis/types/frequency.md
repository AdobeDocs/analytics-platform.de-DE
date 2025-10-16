---
title: Analyse „Häufigkeit“
description: Messen Sie die Interaktion anhand der Nutzungshäufigkeit.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
exl-id: 27eaa7c7-f1e1-4cf1-9d59-67ac552eb430
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 100%

---

# Analyse [!UICONTROL Häufigkeit] {#frequency}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_frequency_button"
>title="Häufigkeit"
>abstract="Zeigen Sie die Verteilung der Aktivität der zurückkehrenden Nutzenden für bestimmte Ereignisse an."

<!-- markdownlint-enable MD034 -->

Die Analyse ![Frequency](/help/assets/icons/Histogram.svg) **[!UICONTROL Häufigkeit]** gruppiert Ereignisdaten nach der Häufigkeit, mit der Ereignisse in Ihrem Produkt auftreten. Die vertikale Achse dieser Analyse enthält Buckets, die die Häufigkeit des Ereignisses darstellen. Die horizontale Achse misst die Anzahl der Benutzenden oder Sitzungen für jeden Bucket.

>[!VIDEO](https://video.tv.adobe.com/v/3428089/?quality=12&learn=on)

## Anwendungsfälle

Zu den Anwendungsfällen für diese Analyse gehören:

* **Interaktion**: Verfolgen Sie, wie stark Benutzende mit einem Ereignis in Ihrem Produkt interagieren. Sie können auf einen beliebigen Teil des Balkendiagramms klicken, um ihn als Segment zu speichern. Segmente für Buckets mit geringer Interaktion können Ihnen dabei helfen zu ermitteln, warum Benutzende mit dem Ereignis nicht in der gewünschten Häufigkeit interagieren. Segmente für Buckets mit hoher Interaktion können Ihnen dabei helfen zu verstehen, warum Benutzende häufig mit dem Ereignis interagieren. Davon ausgehend können Sie andere Benutzende dazu ermutigen, ähnliche Verhaltensweisen anzunehmen.
* **Kundentreue**: Setzen Sie das Ereignis auf „Bestellungen“ und die Metrik auf „Benutzende“. Mit dieser Analyse können Sie Benutzende danach gruppieren, wie häufig sie innerhalb des angegebenen Datumsbereichs einen Kauf auf Ihrer Site getätigt haben.
* **Support-Optimierung**: Zeigen Sie die Anzahl der Support-Anrufe oder offenen Fälle nach Benutzenden an, um Erkenntnisse dazu zu erhalten, welche Benutzenden auf die meisten Probleme stoßen. Anschließend können Sie ein Segment erstellen, um sich auf deren Erlebnisse zu konzentrieren und so die Probleme zu identifizieren und zu lösen.
* **Abonnement-Services**: Bei Benutzenden mit geringer Interaktion ist eine Abwanderung wahrscheinlicher. Wenn Sie das Verhalten von Benutzenden mit hoher Interaktion verstehen, kann dies dazu beitragen, ein ähnliches Verhalten für Benutzende mit geringer Interaktion zu fördern, sodass es weniger wahrscheinlich ist, dass sie ihr Abonnement kündigen.

## Benutzeroberfläche

Einen Überblick über die Benutzeroberfläche für die geführte Analyse erhalten Sie unter [Benutzeroberfläche](../overview.md#interface). Die folgenden Einstellungen sind für diese Analyse spezifisch:

### Abfrageleiste

Mit der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Wechseln Sie zwischen dieser Analyse und [Trends](trends.md).
* **[!UICONTROL Ereignisse]**: Die Ereignisse, die Sie messen möchten. Jedes ausgewählte Ereignis wird als separates Diagramm dargestellt. Der Tabelle wird eine Zeile hinzugefügt, die das Trend-Ereignis darstellt. Sie können bis zu fünf Ereignisse einschließen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll. Zu den Optionen gehören [!UICONTROL Benutzende], [!UICONTROL Sitzungen], [!UICONTROL Prozentualer Anteil der Benutzenden] und [!UICONTROL Prozentsatz der Sitzungen]. Der Nenner für prozentbasierte Metriken in dieser Analyse sind Benutzende oder Sitzungen, die die ausgewählten Ereignisse durchgeführt haben, nicht alle aktiven Benutzenden des Produkts.
* **[!UICONTROL Segmente]**: Die Segmente, die Sie messen möchten. Jedes ausgewählte Segment verdoppelt die Anzahl der Balken im Diagramm und der Zeilen in der Tabelle. Sie können bis zu fünf Segmente einschließen.

### Diagrammeinstellungen

Die Analyse [!UICONTROL Häufigkeit] bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, der verwendet werden soll. Zu den Optionen gehören [!UICONTROL Horizontalbalken] und [!UICONTROL Gestapelter Balken].

### Bucket-Einstellungen

Diese Einstellungen bestimmen, wie das Ereignis in Gruppen (Buckets) kategorisiert wird. In der Trend-Tabellansicht werden Benutzende basierend auf der Häufigkeit der Verwendung insgesamt und in jedem Intervall zusammengefasst, d. h., eine Benutzerin oder Benutzer kann in verschiedenen Intervallen zu verschiedenen Buckets zählen.

* **[!UICONTROL Auto-Buckets]**: Lassen Sie die optimale Bucket-Größe anhand der Datenverteilung automatisch ermitteln.
* **[!UICONTROL Benutzerdefinierte Buckets]**: Passen Sie an, wie die Daten in Buckets gruppiert werden.
   * [!UICONTROL Von]: Der erste Bucket. Liegt die Häufigkeit unter diesem Wert, wird sie für Berichte nicht berücksichtigt.
   * [!UICONTROL Bis]: Liegt die Häufigkeit über diesem Wert, wird sie in den letzten Bucket eingruppiert.
   * [!UICONTROL Größe]: Das Bucket-Intervall.

### Zeitvergleich

{{apply-time-comparison}}

### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trend-Daten angezeigt werden sollen. Das Diagramm und die Tabelle zeigen standardmäßig aggregierte Daten an, mit der Option, die Tabelle auf eine Trend-Ansicht zu erweitern. In der Trend-Ansicht werden Benutzende basierend auf der Häufigkeit der Verwendung insgesamt und in jedem Intervall zusammengefasst, d. h. eine Benutzerin oder Benutzer kann in verschiedenen Intervallen zu verschiedenen Buckets zählen.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Ihnen stehen rollierende Datumsbereichsvorgaben und zuvor gespeicherte benutzerdefinierte Bereiche zur Verfügung. Sie können auch die Kalenderauswahl verwenden, um einen festen Datumsbereich zu definieren.


<!--
## Example

See below foran example of the analysis.

![Frequency](../assets/frequency.png)

-->
