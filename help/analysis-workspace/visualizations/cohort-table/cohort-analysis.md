---
title: Was ist eine Kohortenanalyse?
description: Erfahren Sie mehr über die Kohortenanalyse in Analysis Workspace.
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
source-git-commit: ab30cd4e884dbf92d4148e8f81a638a8ea0b63f3
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 68%

---

# Was ist eine [!UICONTROL Kohortenanalyse]?

Eine *`cohort`* ist eine Personengruppe mit gemeinsamen Merkmalen innerhalb eines vorgegebenen Zeitraums. Die [!UICONTROL Kohortenanalyse] ist z. B. dann nützlich, wenn Sie wissen möchten, wie eine Kohorte mit einer Marke interagiert. Sie können problemlos Trend-Änderungen offenlegen und entsprechend reagieren. (Erläuterungen zur [!UICONTROL Kohortenanalyse] sind im Internet verfügbar, z. B. unter [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

Nachdem Sie einen Kohortenbericht erstellt haben, können Sie dessen Komponenten (bestimmte Dimensionen, Metriken und Filter) kuratieren und den Kohortenbericht dann für andere freigeben. Weitere Informationen finden Sie unter [Kuratieren und freigeben](/help/analysis-workspace/curate-share/curate.md).

Beispiele für die Nutzung einer [!UICONTROL Kohortenanalyse]:

* Starten Sie Kampagnen, die dafür ausgelegt sind, eine erwünschte Aktion anzuregen.
* Erhöhen Sie das Marketingbudget genau zum richtigen Zeitpunkt im Kundenlebenszyklus.
* Erkennen Sie, wann eine Testphase oder ein Angebot beendet werden sollte, um den Wert zu maximieren.
* Gewinnen Sie Ideen für A/B-Tests in Bereichen wie Preisstruktur, Upgrade-Pfad usw.

Die [!UICONTROL Kohortenanalyse] steht allen Customer Journey Analytics-Kunden mit Zugriffsrechten auf [!UICONTROL Analysis Workspace] zur Verfügung.

[Video-Tutorial zur Kohortenanalyse](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/cohort-analysis/cohort-analysis-workspace.html?lang=de) (4:36)

>[!IMPORTANT]
>
>[!UICONTROL Kohortenanalyse] unterstützt keine nicht filterbaren Metriken (einschließlich berechneter Metriken), Nicht-Ganzzahlmetriken (z. B. Umsatz) oder Vorfälle. Nur Metriken, die in Filtern verwendet werden können, können in [!UICONTROL Kohortenanalyse]und sie können jeweils nur um 1 inkrementiert werden.

## Funktionen der Kohortenanalyse

Die folgenden Fähigkeiten ermöglichen eine fein abgestimmte Kontrolle über die erstellten Kohorten:

### [!UICONTROL Bindungstabelle]

A [!UICONTROL Treue] Kohortenbericht gibt Personen zurück: Jede Datenzelle zeigt die Roh- und Prozentanzahl der Personen in der Kohorte, die die Aktion während dieses Zeitraums ausgeführt haben. Sie können bis zu 3 Metriken und bis zu 10 Filter einschließen.

![Ein Bericht zur Kohorte &quot;Rention&quot;, der die Einheiten und den Prozentsatz der Personen in der Kohorte anzeigt.](assets/retention-report.png)

### [!UICONTROL Abwanderungstabelle]

A [!UICONTROL Abwanderung] Die Kohorte ist die Umkehrung einer Bindungstabelle und zeigt die Personen an, die abgestürzt sind oder die Rückkehrkriterien für Ihre Kohorte im Laufe der Zeit nie erfüllt haben. Sie können bis zu 3 Metriken und bis zu 10 Filter einschließen.

![Eine Abwanderungstabelle, die Einheiten und Prozentsatz der Personen anzeigt, die die Rückkehrkriterien für eine Kohorte nicht erfüllt haben.](assets/churn-report.png)

### [!UICONTROL Rollierende Berechnung]

Ermöglicht es Ihnen, die Bindung oder die Abwanderung auf Grundlage der vorherigen Spalte und nicht der Aufnahmespalte zu berechnen.

![Ein Kohortenaufbewahrungsbericht, der Berechnungen basierend auf einer vorherigen Datenspalte anzeigt.](assets/cohort-rolling-calculation.png)

### [!UICONTROL Latenztabelle]

Misst die Zeit, die vor und nach dem Aufnahmeereignis verstrichen ist. Ein hervorragendes Tool für die Vor- und Nachanalyse. Die Spalte **[!UICONTROL Aufnahme]** befindet sich in der Mitte der Tabelle und die Zeiträume vor und nach dem Aufnahmeereignis werden auf beiden Seiten angezeigt.

![Ein Kohortenbericht, der die verstrichene Zeit vor und nach einem Ereignis anzeigt.](assets/cohort-latency.png)

### [!UICONTROL Angepasste Dimensionskohorte]

Erstellen Sie Kohorten auf Grundlage einer ausgewählten Dimension und nicht auf Grundlage zeitbasierter Kohorten, die Standardeinstellung sind. Verwenden Sie Dimensionen wie [!UICONTROL Marketing-Kanal], [!UICONTROL Kampagne], [!UICONTROL Produkt], [!UICONTROL Seite], [!UICONTROL Region] oder jede andere Dimension in Customer Journey Analytics, um zu zeigen, wie sich die Kundenbindung basierend auf den verschiedenen Werten dieser Dimensionen ändert.

![Ein Kohortenbericht, der einen benutzerdefinierten Bericht mit ausgewählten Dimensionen anzeigt, nicht die standardmäßige zeitbasierte Kohorte.](assets/cohort-customizable-cohort-row.png)

Anweisungen zum Einrichten und Durchführen eines Kohortenberichts finden Sie unter  [Konfigurieren eines Kohortenanalyseberichts](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).
