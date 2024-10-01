---
title: Übersicht über die Kohortentabelle
description: Erfahren Sie, wie Sie eine Kohortentabelle für die Kohortenanalyse in Analysis Workspace verwenden.
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
source-git-commit: 383fad799944f7405af6de1754aa2e0af83e2cab
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 25%

---

# Übersicht über die Kohortentabelle {#cohort-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_cohorttable_button"
>title="Kohortentabelle"
>abstract="Erstellen Sie eine Kohortenvisualisierung, um Benutzer basierend auf dem Abschluss eines Ereignisses zu gruppieren und die anhaltende Interaktion und Abwanderung im Zeitverlauf zu analysieren."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_cohorttable_panel"
>title="Auswahltabelle"
>abstract="Gruppieren Sie Benutzer anhand des Abschlusses eines Ereignisses und analysieren Sie dann deren anhaltende Interaktion und Abwanderung im Zeitverlauf.<br/><br/>**Parameter **<br/>**Aufnahmekriterien**: Die Komponenten, die zur Definition der anfänglichen Besucherkohorten verwendet werden.<br/>**Rückgabekriterien**: Die Komponenten, mit denen bestimmt wird, ob ein Besucher zurückgegeben wurde."

<!-- markdownlint-enable MD034 -->


Eine *Kohorte* ist eine Personengruppe mit gemeinsamen Merkmalen innerhalb eines bestimmten Zeitraums. Eine Visualisierung der Kohortentabelle ![TextNummered](/help/assets/icons/TextNumbered.svg) [!UICONTROL 3} ist nützlich, wenn Sie beispielsweise erfahren möchten, wie eine Kohorte mit einer Marke interagiert. ] Sie können problemlos Trend-Änderungen offenlegen und entsprechend reagieren. (Erläuterungen zur [!UICONTROL Kohortenanalyse] sind im Internet verfügbar, z. B. unter [Cohort Analysis 101](https://de.wikipedia.org/wiki/Cohort_analysis).)

Nachdem Sie einen Kohortenbericht erstellt haben, können Sie dessen Komponenten (bestimmte Dimensionen, Metriken und Filter) kuratieren und den Kohortenbericht dann für andere freigeben. Weitere Informationen finden Sie unter [Kuratieren und freigeben](/help/analysis-workspace/curate-share/curate.md).

Beispiele für die Verwendung einer [!UICONTROL Kohortentabelle]:

* Starten Sie Kampagnen, die dafür ausgelegt sind, eine erwünschte Aktion anzuregen.
* Erhöhen Sie das Marketingbudget genau zum richtigen Zeitpunkt im Kundenlebenszyklus.
* Erkennen Sie, wann eine Testphase oder ein Angebot beendet werden soll, um den Wert zu maximieren.
* Gewinnen Sie Ideen für A/B-Tests in Bereichen wie Preisstruktur, Upgrade-Pfad usw.

[!UICONTROL Kohortentabelle] ist für alle Customer Journey Analytics-Kunden mit Zugriffsrechten auf [!UICONTROL Analysis Workspace] verfügbar.

+++ Sehen Sie sich eine Videodemonstration der Kohortentabelle an.

>[!VIDEO](https://video.tv.adobe.com/v/23990/?quality=12)

{{videoaa}}

+++

>[!IMPORTANT]
>
>[!UICONTROL Kohortenanalyse] unterstützt keine nicht filterbaren Metriken (einschließlich berechneter Metriken), nicht ganzzahlige Metriken (z. B. Umsatz) oder Vorfälle. In der Kohortenanalyse ] können nur Metriken verwendet werden, die in Filtern verwendet werden können, und sie können jeweils nur um 1 inkrementiert werden.[!UICONTROL 

## Funktionen der Kohortentabelle

Die folgenden Fähigkeiten ermöglichen eine fein abgestimmte Kontrolle über die erstellten Kohorten:

### Tabelle [!UICONTROL Treue]

Eine Kohortentabelle vom Typ [!UICONTROL Bindung] gibt Personen zurück: Jede Datenzelle zeigt die Roh- und Prozentanzahl der Personen in der Kohorte, die die Aktion während dieses Zeitraums ausgeführt haben. Sie können bis zu 3 Metriken und bis zu 10 Filter einschließen.

![Ein Bericht zur Kohorte &quot;Rention&quot;, der die Einheiten und den Prozentsatz der Personen in der Kohorte anzeigt.](assets/retention-report.png)

### [!UICONTROL Abwanderungstabelle]

Eine Kohortentabelle vom Typ [!UICONTROL Abwanderung] ist das Gegenteil einer Bindungstabelle und zeigt die Personen an, die abgewandert sind oder die Rückkehrkriterien für Ihre Kohorte im Laufe der Zeit nie erfüllt haben. Sie können bis zu 3 Metriken und bis zu 10 Filter einschließen.

![Eine Abwanderungstabelle, die Einheiten und Prozentsatz der Personen anzeigt, die die Rückkehrkriterien für eine Kohorte nicht erfüllt haben.](assets/churn-report.png)

### [!UICONTROL Rollierende Berechnung]

Sie können die Bindung oder die Abwanderung anhand der vorherigen Spalte und nicht der eingeschlossenen Spalte berechnen, die als rollierende Berechnung bezeichnet wird.

![Ein Kohortenaufbewahrungsbericht, der Berechnungen basierend auf einer vorherigen Datenspalte anzeigt.](assets/retention-report-rolling.png)

### Tabelle [!UICONTROL Latenz]

Eine Latenztabelle misst die verstrichene Zeit vor und nach dem Aufnahmeereignis. Die Messung der Latenz ist ein hervorragendes Werkzeug für die Vor- und Nachanalyse. Die Spalte **[!UICONTROL Aufnahme]** befindet sich in der Mitte der Tabelle und die Zeiträume vor und nach dem Aufnahmeereignis werden auf beiden Seiten angezeigt.

![Ein Kohortenbericht, der die verstrichene Zeit vor und nach einem Ereignis anzeigt.](assets/retention-report-latency.png)

### [!UICONTROL Angepasste Dimensionskohorte]

Sie können Kohorten auf der Basis einer ausgewählten Dimension und nicht auf Grundlage zeitbasierter Kohorten erstellen (Standardeinstellung). Verwenden Sie Dimensionen wie [!UICONTROL Stadt geo], [!UICONTROL Marketing-Kanal], [!UICONTROL Kampagne], [!UICONTROL Produkt], [!UICONTROL Seite], [!UICONTROL Region] oder eine andere Dimension, um anzuzeigen, wie sich die Bindung ändert. Basierend auf den unterschiedlichen Werten dieser Dimensionen.

![Ein Kohortenbericht, der einen benutzerspezifischen Bericht mit ausgewählten Dimensionen anzeigt, nicht die standardmäßige zeitbasierte Kohorte.](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[Konfigurieren einer Kohortentabelle](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).
>

