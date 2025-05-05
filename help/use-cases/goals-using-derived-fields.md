---
title: Verwenden abgeleiteter Felder für Berichte zu Zielen
description: Erfahren Sie, wie Sie mit abgeleiteten Feldern Berichte zu Zielen (Zielen) in Ihren Workspace-Projekten erstellen können.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: 5cd838f7-e394-4a67-9d2e-e1d08a864ca0
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 6%

---

# Verwenden abgeleiteter Felder für Berichte zu Zielen

In diesem Anwendungsfall wird beschrieben, wie Sie die Leistungsfähigkeit abgeleiteter Felder nutzen können, um Ziele für eine bestimmte Dimension festzulegen und diese Ziele dann in Ihrem Workspace-Projekt zu verwenden.

Wenn Sie mit abgeleiteten Feldern nicht vertraut sind, finden Sie in der [Tutorial](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/data-views/derived-fields-in-cja.html?lang=de) und [Dokumentation](../data-views/derived-fields/derived-fields.md) eine Einführung.


## Ziele definieren

Um Ziele zu definieren, erstellen Sie ein neues abgeleitetes Feld, in dem Sie benutzerdefinierte numerische Werte direkt oder indirekt mit den Werten festlegen, die sich aus Regeln zuvor in Ihrer abgeleiteten Felddefinition ergeben.


### Ziele für monatliche Geschenkgutscheinbestellungen

Sie möchten explizit Ziele für Ihre Geschenkgutscheinbestellungen für vier Monate festlegen, von Juli 2023 bis Oktober 2023. Gehen Sie folgendermaßen vor:

1. Erstellen Sie ein neues abgeleitetes Feld mit dem Namen `Monthly Gift Certificate Orders Goal (Incremental)`.

1. Legen Sie mithilfe einer WENN-GROSS-/KLEINSCHREIBUNGSREGEL statische Werte für jeden Monat fest, indem Sie einen &quot;**[!UICONTROL numerischen Wert“]**. Siehe die Regel Monatliche Produktziele unten.

   ![Monthly Product Goals](assets/goals-derived-field-product-goals-1.png)


### Umsatzziele für Marketing-Kanäle

Sie möchten für jeden Ihrer Marketing-Kanäle ein monatliches Umsatzziel festlegen. Gehen Sie folgendermaßen vor:

1. Erstellen Sie mithilfe der Vorlage [Funktionskanäle“ ein neues abgeleitetes Feld ](/help/data-views/derived-fields/derived-fields.md#marketing-channels) dem Namen `Monthly Marketing Channel Revenue Goal (Incremental)`.

1. Definieren Sie alle Regeln, um jeden Marketing-Kanal anhand einer Kombination aus URL-PARSE- und CASE-WHEN-Regeln korrekt zu identifizieren. z. B.:

   ![Definition von Regeln für ein vom Marketing-Kanal abgeleitetes Feld](assets/goals-derived-field-marketing-channel-1.png)

1. Legen Sie in einer endgültigen WENN-Regel explizit statische Werte, die monatliche Umsatzziele darstellen, für die spezifischen Marketing-Kanäle fest, indem Sie einen &quot;**[!UICONTROL numerischen Wert“]**. Siehe die [!DNL Monthly Goal] unten.

   ![Monatliche Ziele](assets/goals-derived-field-marketing-channel-2.png)



## Ziele verwenden

Um Ziele in Ihrem Workspace-Projekt zu verwenden, verwenden Sie die Funktion für berechnete Metriken , um das abgeleitete Feld wieder auf seinen ursprünglichen statischen Wert zu „normalisieren“. Diese Normalisierung ist erforderlich, da die statischen Werte, die Sie für die abgeleiteten Felder festlegen, die Ziele definieren, mit jedem Ereignis inkrementiert werden.

### Ziele für monatliche Geschenkgutscheinbestellungen

1. Erstellen Sie ein Feld für berechnete Metriken mit dem Namen `Monthly Gift Certificate Orders Goal`, das wie folgt definiert ist:

   ![Bestellungsziel](assets/calculated-metric-ordersgoals.png)

1. Sie können zusätzliche berechnete Felder erstellen, z. B. `% of Monthly Gift Certificate Orders Goal`, um den tatsächlichen Fortschritt bei den Zielen anzuzeigen, z. B.:

   ![Auftrags-Zielprozentsatz](assets/calculated-metric-ordersgoalspercent.png)

Sie können diese berechneten Metriken verwenden, um den Fortschritt in Freiformtabellen und Visualisierungen zu melden. z. B.:

![Freiformtabelle mit Marketing-Umsatzzielen](assets/freeform-table-product-order-goals.png)


### Umsatzziele für Marketing-Kanäle

1. Erstellen Sie ein Feld für berechnete Metriken mit dem Namen `Marketing Channel Revenue Goal`, das wie folgt definiert ist:

   ![Umsatzziel](assets/calculated-metric-revenuegoals.png)

1. Sie können zusätzliche berechnete Felder erstellen, z. B. `% of Marketing Channel Revenue Goal`, um den tatsächlichen Fortschritt bei den Zielen anzuzeigen, z. B.:

   ![Umsatzziel in Prozent](assets/calculated-metric-revenuegoalspercent.png)

Sie können diese berechneten Metriken verwenden, um den Fortschritt in Freiformtabellen und Visualisierungen zu melden. z. B.:

![Freiformtabelle mit Marketing-Umsatzzielen](assets/freeform-table-marketing-channel-revenue-goals.png)
