---
description: Verstehen, wie Sie mit einem interdimensionalen Fluss Benutzerpfade über verschiedene Dimensionen hinweg untersuchen können.
title: Interdimensionale Flüsse
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
role: User
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 89%

---

# Interdimensionale Flüsse

Mithilfe eines interdimensionalen Flusses können Sie Benutzerpfade über verschiedene Dimensionen hinweg untersuchen. In diesem Artikel wird gezeigt, wie dieser Fluss für zwei Anwendungsfälle verwendet werden kann: Interaktionen mit Mobile Apps und Ereignisse und wie Kampagnen Web-Besuche fördern

<!--
A dimension label at the top of each Flow column makes using multiple dimensions in a flow visualization more intuitive:

![An intero-dimensional flow highlighting multiple dimensions including Product, Page, OS version, and Time Spent.](assets/flow.png)
-->

## App-Interaktionen und -Ereignisse

Die Dimension [!UICONTROL Bildschirmname] wird in diesem Beispielfluss verwendet, um zu sehen, wie Benutzende die verschiedenen Bildschirme (Szenen) in der App verwenden. Der zurückgegebene Bildschirm der obersten Ebene, **[!UICONTROL luma: content: ios: en: home]**, ist die Startseite der App:

![Ein Fluss mit dem hinzugefügtem Element.](assets/flowapp.png)

Um die Interaktion zwischen Bildschirmen und Ereignistypen (z. B. „Hinzufügen zum Warenkorb“, „Käufe“ usw.) in dieser App zu untersuchen, ziehen Sie die Dimension **[!UICONTROL Ereignistypen]** per Drag-and-Drop:

* So ersetzen Sie diese Dimension zusätzlich zu jedem verfügbaren Schritt im Fluss:

  ![Ein Fluss, der zeigt, dass die Seitendimension in mehrere Bereiche gezogen wurde](assets/flowapp-replace.png)

* So fügen Sie außerhalb der aktuellen Flussvisualisierung die Dimension hinzu:

  ![Ein Fluss, bei dem die Seitendimension in den Leerraum am Ende gezogen wurde.](assets/flowapp-add.png)

Die folgende Flussvisualisierung zeigt das Ergebnis nach dem Hinzufügen der Dimension **[!UICONTROL Ereignistypen]**. Die Visualisierung bietet Erkenntnisse dazu, wie sich App-Benutzende durch verschiedene Bildschirme in der App bewegen, bevor sie Produkte zu einem Warenkorb hinzufügen, die App schließen, ein Angebot erhalten und vieles mehr.

![Ein Fluss mit den Ergebnissen der Seitendimension oben in der Liste](assets/flowapp-result.png)

## Fördern von Web-Besuchen durch Kampagnen

Sie möchten analysieren, welche Kampagnen Besuche auf der Website fördern. Erstellen Sie dazu eine Flussvisualisierung mit dem **[!UICONTROL Kampagnennamen]** als Dimension.

![Fluss – Web-Kampagnenname als Dimension](assets/flowweb.png)

Ersetzen Sie die letzte Dimension **[!UICONTROL Kampagnenname]** durch die Dimension **[!UICONTROL Formatierter Seitenname]** und fügen Sie am Ende der Flussvisualisierung eine weitere Dimension **[!UICONTROL Formatierter Seitenname]** hinzu.

![Fluss – Web-Kampagnenname und Web-Seite als Dimension](assets/flowweb-replace.png)

Sie können den Mauszeiger über einen der Flüsse bewegen, um weitere Details anzuzeigen, z. B. welche Kampagnen zu einem Warenkorb-Checkout geführt haben.

![Bewegen des Mauszeigers über einen Fluss – Web-Kampagnenname und Web-Seite als Dimension](assets/flowweb-hover.png)
