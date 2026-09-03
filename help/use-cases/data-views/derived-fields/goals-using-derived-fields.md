---
title: Verwenden abgeleiteter Felder für Berichte zu Zielen
description: Erfahren Sie, wie Sie mit abgeleiteten Feldern Berichte zu Zielen (Zielen) in Ihren Workspace-Projekten erstellen können.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: 5cd838f7-e394-4a67-9d2e-e1d08a864ca0
role: User
autotag-review: '2026-05-19T06:55:50.510Z'
TQID: 'https://experienceleague.adobe.com/dTARH-90RV1yHWQX3tqotqum-WizfgFh5mgUeYySI6c'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2: id: f3ca85c1-72de-4df2-97ed-05753cd77c47
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 442
ht-degree: 9%

---

# Verwenden abgeleiteter Felder für Berichte zu Zielen

In diesem Anwendungsfall wird beschrieben, wie Sie die Leistungsfähigkeit abgeleiteter Felder nutzen können, um Ziele für eine bestimmte Dimension festzulegen und diese Ziele dann in Ihrem Workspace-Projekt zu verwenden.

Wenn Sie mit abgeleiteten Feldern nicht vertraut sind, finden Sie in der [Tutorial](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/data-views/derived-fields-in-cja.html?lang=de) und [Dokumentation](/help/data-views/derived-fields/derived-fields.md) eine Einführung.


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

1. Definieren Sie alle Regeln, um jeden Marketing-Kanal anhand einer Kombination aus URL-PARSE- und CASE-WHEN-Regeln korrekt zu identifizieren. Zum Beispiel:

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

Sie können diese berechneten Metriken verwenden, um den Fortschritt in Freiformtabellen und Visualisierungen zu melden. Zum Beispiel:

![Freiformtabelle mit Marketing-Umsatzzielen](assets/freeform-table-marketing-channel-revenue-goals.png)




### Umsatzziele für Marketing-Kanäle

1. Erstellen Sie ein Feld für berechnete Metriken mit dem Namen `Marketing Channel Revenue Goal`, das wie folgt definiert ist:

   ![Umsatzziel](assets/calculated-metric-revenuegoals.png)

1. Sie können zusätzliche berechnete Felder erstellen, z. B. `% of Marketing Channel Revenue Goal`, um den tatsächlichen Fortschritt bei den Zielen anzuzeigen, z. B.:

   ![Umsatzziel in Prozent](assets/calculated-metric-revenuegoalspercent.png)

Sie können diese berechneten Metriken verwenden, um den Fortschritt in Freiformtabellen und Visualisierungen zu melden. Zum Beispiel:

![Freiformtabelle mit Marketing-Umsatzzielen](assets/freeform-table-product-order-goals.png)
