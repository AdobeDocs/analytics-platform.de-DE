---
title: Verwenden abgeleiteter Felder für Berichte zu Zielen
description: Erfahren Sie, wie Sie abgeleitete Felder verwenden können, um über Ziele (Ziele) in Ihren Workspace-Projekten zu berichten.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: 5cd838f7-e394-4a67-9d2e-e1d08a864ca0
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 2%

---

# Verwenden abgeleiteter Felder für Berichte zu Zielen

In diesem Anwendungsbeispiel wird beschrieben, wie Sie mithilfe der Leistungsfähigkeit abgeleiteter Felder Ziele für eine bestimmte Dimension festlegen und diese Ziele dann in Ihrem Workspace-Projekt verwenden können.

Wenn Sie mit abgeleiteten Feldern nicht vertraut sind, lesen Sie den Abschnitt [Tutorial](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/data-views/derived-fields-in-cja.html) und [Dokumentation](../data-views/derived-fields/derived-fields.md) für eine Einführung.


## Ziele definieren

Um Ziele zu definieren, erstellen Sie ein neues abgeleitetes Feld, in dem Sie explizit benutzerdefinierte numerische Werte direkt oder indirekt mithilfe der Werte festlegen, die sich aus den Regeln ergeben, die zu einem früheren Zeitpunkt in Ihrer abgeleiteten Felddefinition galten.


### Ziele für monatliche Geschenkzertifikate

Sie möchten explizit Ziele für Ihre Bestellungen von Geschenkgutscheinen für vier Monate festlegen, von Juli 2023 bis Oktober 2023. Gehen Sie folgendermaßen vor:

1. Erstellen Sie ein neues abgeleitetes Feld mit dem Namen `Monthly Gift Certificate Orders Goal (Incremental)`.

1. Legen Sie für jeden Monat mithilfe einer REGEL &quot;CASE WHEN&quot; statische Werte fest, indem Sie eine **[!UICONTROL Benutzerdefinierter numerischer Wert]**. Siehe Regel &quot;Monatliche Produktziele&quot; unten.

   ![Monatliche Produktziele](assets/goals-derived-field-product-goals-1.png)


### Umsatzziele für Marketing-Kanäle

Sie möchten für jeden Ihrer Marketing-Kanäle ein monatliches Umsatzziel festlegen. Gehen Sie folgendermaßen vor:

1. Erstellen Sie ein neues abgeleitetes Feld mithilfe der [Vorlage für Marketing-Kanäle](/help/data-views/derived-fields/derived-fields.md#marketing-channels) mit dem Namen `Monthly Marketing Channel Revenue Goal (Incremental)`.

1. Definieren Sie alle Regeln, um jeden Marketing-Kanal anhand einer Kombination aus URL-PARSE und CASE WHEN-Regeln ordnungsgemäß zu identifizieren. Zum Beispiel:

   ![Definition von Regeln für das abgeleitete Marketing-Kanal-Feld](assets/goals-derived-field-marketing-channel-1.png)

1. Setzen Sie in einer endgültigen FALL WH-Regel explizit statische Werte, die monatliche Umsatzziele darstellen, für die spezifischen Marketing-Kanäle ein, indem Sie eine **[!UICONTROL Benutzerdefinierter numerischer Wert]**. Siehe [!DNL Monthly Goal] Regel unten.

   ![Monatliche Ziele](assets/goals-derived-field-marketing-channel-2.png)



## Ziele verwenden

Um Ziele in Ihrem Workspace-Projekt zu verwenden, verwenden Sie die Funktion für berechnete Metriken, um das abgeleitete Feld wieder auf seinen ursprünglichen statischen Wert zu normalisieren. Diese Normalisierung ist erforderlich, da die statischen Werte, die Sie für die abgeleiteten Felder festlegen, die Ziele definieren, mit jedem Ereignis inkrementiert werden.

### Ziele für monatliche Geschenkzertifikate

1. Erstellen Sie ein berechnetes Metrikfeld mit dem Namen `Monthly Gift Certificate Orders Goal`, definiert als:

   ![Bestellziel](assets/calculated-metric-ordersgoals.png)

1. Sie können zusätzliche berechnete Felder erstellen, beispielsweise `% of Monthly Gift Certificate Orders Goal`, um den tatsächlichen Fortschritt in Bezug auf Ziele anzuzeigen, beispielsweise:

   ![Bestellzielprozentsatz](assets/calculated-metric-ordersgoalspercent.png)

Sie können diese berechneten Metriken verwenden, um über den Fortschritt in Freiformtabellen und Visualisierungen zu berichten. Zum Beispiel:

![Freiformtabelle mit Marketing-Umsatzzielen](assets/freeform-table-product-order-goals.png)


### Umsatzziele für Marketing-Kanäle

1. Erstellen Sie ein berechnetes Metrikfeld mit dem Namen `Marketing Channel Revenue Goal`, definiert als:

   ![Umsatzziel](assets/calculated-metric-revenuegoals.png)

1. Sie können zusätzliche berechnete Felder erstellen, beispielsweise `% of Marketing Channel Revenue Goal`, um den tatsächlichen Fortschritt in Bezug auf Ziele anzuzeigen, beispielsweise:

   ![Prozentsatz des Umsatzziels](assets/calculated-metric-revenuegoalspercent.png)

Sie können diese berechneten Metriken verwenden, um über den Fortschritt in Freiformtabellen und Visualisierungen zu berichten. Zum Beispiel:

![Freiformtabelle mit Marketing-Umsatzzielen](assets/freeform-table-marketing-channel-revenue-goals.png)
