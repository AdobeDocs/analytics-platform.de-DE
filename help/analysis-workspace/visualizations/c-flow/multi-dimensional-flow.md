---
description: Mithilfe eines interdimensionalen Flusses können Sie Benutzerpfade über verschiedene Dimensionen hinweg untersuchen.
title: Interdimensionale Flüsse
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 73%

---

# Interdimensionale Flüsse

Mithilfe eines interdimensionalen Flusses können Sie Benutzerpfade über verschiedene Dimensionen hinweg untersuchen.

Eine Dimensionsbezeichnung jeweils oben in der Spalte „Fluss“ vereinfacht die Verwendung mehrerer Dimensionen in einer Flussvisualisierung:

![Interdimensionaler Fluss, der mehrere Dimensionen wie Produkt, Seite, Betriebssystemversion und Besuchszeit hervorhebt.](assets/flow.png)

Sehen wir uns 2 Anwendungsfälle an: einen App-Anwendungsfall und einen Web-Anwendungsfall.

## Anwendungsfall 1: Mobile App

Die Dimension [!UICONTROL Aktionsname] wurde dem Fluss hinzugefügt, wobei das oberste zurückgegebene Element [!UICONTROL ItemAdded] ist:

![Ein Fluss, der das hinzugefügte Element anzeigt.](assets/multi-dimensional-flow.png)

Um die Interaktion zwischen Bildschirmen/Seiten und Aktionen in dieser App zu untersuchen, können Sie die Dimension „Seite“ an mehrere Stellen ziehen (je nachdem, was genau Sie untersuchen möchten):

* Ziehen Sie die Dimension an eines der Enden der Dropzone (innerhalb der schwarz umrandeten rechteckigen Zone, die eingeblendet wird), um die obersten Ergebnisse an den Enden zu **ersetzen**:

  ![Ein Fluss, der die Dimension Seite anzeigt, die in mehrere Bereiche gezogen wurde.](assets/multi-dimensional-flow2.png) ![Flussdiagramm mit den gezogenen Elementen.](assets/multi-dimensional-flow3.png)

* Ziehen Sie die Dimension auf die weiße Fläche an dem Ende (beachten Sie die schwarze Klammer), um sie **der Visualisierung hinzuzufügen**:

  ![Ein Fluss, der die Dimension Seite anzeigt, die am Ende in den Leerraum gezogen wurde.](assets/multi-dimensional-flow4.png)

Falls Sie sich enschieden haben, das Element „ItemScaled“ in der rechten Spalte mit der Dimension „Seite“ zu ersetzen, sieht das Ergebnis so aus. Das oberste Ergebnis ändert sich nun so, dass es das oberste Ergebnis für die Dimension „Seite“ ist.

![Eine niedrige Anzeige der Dimension Seite ergibt sich oben in der Liste.](assets/multi-dimensional-flow5.png)

Nun können Sie erkennen, wie Ihre Kunden durch die Aktionen und Seiten navigieren. Per Klick auf die verschiedenen Knoten können Sie den Fluss noch weiter untersuchen:

![Ein Fluss, der hinzugefügte Elemente, gezogene Elemente und die Hauptansicht anzeigt.](assets/multi-dimensional-flow6.png)

Wenn Sie eine weitere Dimension Aktionsname am Ende der Visualisierung hinzufügen, geschieht Folgendes:

![Ein Fluss mit dem hinzugefügten Aktionsnamen.](assets/multi-dimensional-flow7.png)

Dies gibt Ihnen tiefere Einblicke in die App, die Sie analysieren möchten, und erlaubt geeignete Änderungen.

## Anwendungsfall 2: Web

Dieser Verwendungsfall zeigt, wie Sie anaysieren können, welche Kampagnen die meisten Einstiege auf einer Website einbringen.

Ziehen Sie die Dimension „Kampagnenname“ in einen neuen Fluss:

![Ein Fluss, der die Dimension Kampagnenname anzeigt und in einen neuen Fluss gezogen wurde.](assets/multi-dimensional-flow8.png)

Nun möchte ich wissen, auf welche Seiten diese Kampagnen Traffic leiten. Daher ziehe ich die Dimension „Seite“ nach rechts von den Flussergebnissen, um sie in der Visualisierung hinzuzufügen:

![Ein Fluss, der die Dimension Seite anzeigt, die rechts von den Flussergebnissen gezogen wurde.](assets/multi-dimensional-flow9.png)
