---
description: Mithilfe eines interdimensionalen Flusses können Sie Benutzerpfade über verschiedene Dimensionen hinweg untersuchen.
title: Interdimensionale Flüsse
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
role: User
source-git-commit: 80522177d5258e4b5046b3872483ce2b482ae77d
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 7%

---

# Interdimensionale Flüsse

Mithilfe eines interdimensionalen Flusses können Sie Benutzerpfade über verschiedene Dimensionen hinweg untersuchen. In diesem Artikel wird gezeigt, wie dieser Fluss für zwei Anwendungsfälle verwendet wird: Interaktionen und Ereignisse mobiler Apps und wie Kampagnen Webbesuche fördern

<!--
A dimension label at the top of each Flow column makes using multiple dimensions in a flow visualization more intuitive:

![An intero-dimensional flow highlighting multiple dimensions including Product, Page, OS version, and Time Spent.](assets/flow.png)
-->

## Interaktionen und Ereignisse mobiler Apps

In diesem Beispielfluss wird die Dimension [!UICONTROL Bildschirmname] verwendet, um zu sehen, wie Benutzer die verschiedenen Bildschirme (Szenen) in der App verwenden. Der am häufigsten zurückgegebene Bildschirm ist **[!UICONTROL luma: content: ios: en: home]**, die Startseite der App:

![Ein Fluss, der das hinzugefügte Element anzeigt.](assets/flowapp.png)

Um die Interaktion zwischen Bildschirmen und Ereignistypen (z. B. zum Warenkorb, zu Käufen und anderen) in dieser App zu untersuchen, ziehen Sie die Dimension **[!UICONTROL Ereignistypen]** in den Arbeitsbereich:

* Ersetzen Sie zusätzlich zu jedem verfügbaren Schritt im Fluss diese Dimension:

  ![Ein Fluss, der die Dimension Seite anzeigt, die in mehrere Bereiche gezogen wurde.](assets/flowapp-replace.png)

* Außerhalb der aktuellen Flussvisualisierung , um die Dimension hinzuzufügen:

  ![Ein Fluss, der die Dimension Seite anzeigt, der zum Leerraum am Ende gezogen wurde.](assets/flowapp-add.png)

Die nachstehende Flussvisualisierung zeigt das Ergebnis des Hinzufügens der Dimension **[!UICONTROL Ereignistypen]**. Die Visualisierung bietet Einblicke, wie Benutzer mobiler Apps durch verschiedene Bildschirme der App navigieren, bevor sie Produkte zu einem Warenkorb hinzufügen, die Anwendung schließen, ein Angebot präsentieren und vieles mehr.

![Ein fLow zeigt die Seitendimensionen oben in der Liste an.](assets/flowapp-result.png)

## Wie Kampagnen Webbesuche fördern

Sie möchten analysieren, welche Kampagnen zu Besuchen auf der Website führen. Sie erstellen eine Flussvisualisierung mit dem **[!UICONTROL Kampagnennamen]** als Dimension

![Dimension für Fluss-Webkampagnenname](assets/flowweb.png)

Sie ersetzen die letzte Dimension **[!UICONTROL Kampagnenname]** durch die Dimension **[!UICONTROL Formatierter Seitenname]** und fügen am Ende der Flussvisualisierung eine weitere Dimension **[!UICONTROL Formatierter Seitenname]** hinzu.

![Fluss-Webkampagnenname und Webseitendimension](assets/flowweb-replace.png)

Sie können mit dem Mauszeiger über einen der Flüsse fahren, um weitere Details anzuzeigen. Zum Beispiel, welche Kampagnen zu einem Warenkorb geführt haben.

![Bewegen Sie den Mauszeiger über den Fluss des Webkampagnennamens und der Webseitendimension](assets/flowweb-hover.png)
