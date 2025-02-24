---
description: Mithilfe eines interdimensionalen Flusses können Sie Benutzerpfade über verschiedene Dimensionen hinweg untersuchen.
title: Interdimensionale Flüsse
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
role: User
source-git-commit: 1eeba4dc9de52f2890cf25794e767f199a4aa04c
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 7%

---

# Interdimensionale Flüsse

Mithilfe eines interdimensionalen Flusses können Sie Benutzerpfade über verschiedene Dimensionen hinweg untersuchen. In diesem Artikel wird gezeigt, wie dieser Fluss für zwei Anwendungsfälle verwendet werden kann: Interaktionen mit Mobile Apps und Ereignisse und wie Kampagnen Web-Besuche fördern

<!--
A dimension label at the top of each Flow column makes using multiple dimensions in a flow visualization more intuitive:

![An intero-dimensional flow highlighting multiple dimensions including Product, Page, OS version, and Time Spent.](assets/flow.png)
-->

## Mobile-App-Interaktionen und -Ereignisse

Die Dimension [!UICONTROL Bildschirmname] wird in diesem Beispielfluss verwendet, um zu sehen, wie Benutzer die verschiedenen Bildschirme (Szenen) in der App verwenden. Der obere Bildschirm ist **[!UICONTROL luma: content: ios: en: home]**, was die Startseite der App ist:

![Ein Fluss, der das hinzugefügte Element anzeigt.](assets/flowapp.png)

Um die Interaktion zwischen Bildschirmen und Ereignistypen (z. B. zum Warenkorb hinzufügen, Käufe und andere) in dieser App zu untersuchen, ziehen Sie die Dimension **[!UICONTROL Ereignistypen]** per Drag-and-Drop:

* Ersetzen Sie diese Dimension zusätzlich zu jedem verfügbaren Schritt im Fluss:

  ![Ein Fluss, der die Seitendimension anzeigt, die in mehrere Bereiche gezogen wurde.](assets/flowapp-replace.png)

* Fügen Sie außerhalb der aktuellen Flussvisualisierung die Dimension hinzu:

  ![Ein Fluss, der die Seitendimension zeigt, die an den Leerraum am Ende gezogen wurde.](assets/flowapp-add.png)

Die folgende Flussvisualisierung zeigt das Ergebnis des Hinzufügens der Dimension **[!UICONTROL Ereignistypen]** . Die Visualisierung bietet Einblicke, wie sich Benutzer von Mobile Apps durch verschiedene Bildschirme in der App bewegen, bevor sie Produkte zu einem Warenkorb hinzufügen, die App schließen, ein Angebot erhalten und vieles mehr.

![Ein Fluss, der die Ergebnisse der Seitendimension oben in der Liste anzeigt.](assets/flowapp-result.png)

## Wie Kampagnen zu Web-Besuchen führen

Sie möchten analysieren, welche Kampagnen zu Besuchen auf der Website führen. Sie erstellen eine Flussvisualisierung mit dem **[!UICONTROL Kampagnennamen]** als Dimension

![Dimension Fluss-Web-Kampagnenname ](assets/flowweb.png)

Sie ersetzen die letzte Dimension **[!UICONTROL Kampagnenname]** durch die Dimension **[!UICONTROL Formatierter Seitenname]** und fügen am Ende **[!UICONTROL Flussvisualisierung eine weitere Dimension Formatierter Seitenname]** hinzu.

![Fluss-Web-Kampagnenname und Web-Seiten-Dimension](assets/flowweb-replace.png)

Sie können den Mauszeiger über einen der Flüsse bewegen, um weitere Details anzuzeigen. Beispielsweise welche Kampagnen zu einem Warenkorb-Checkout geführt haben.

![Fluss-Web-Kampagnenname und -Web-Seiten-Dimension-Mauszeiger](assets/flowweb-hover.png)
