---
title: Übersicht über die Kohortentabelle
description: Erfahren Sie, wie Sie Ihre Audience genauer untersuchen und diese Daten mithilfe der Kohortenanalyse in verwandte Gruppen aufteilen können. Verwenden Sie die Kohortenanalyse in Analysis Workspace.
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 88%

---

# Überblick über Kohortentabellen {#cohort-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="Kohortentabelle"
>abstract="Erstellen Sie eine Kohortenvisualisierung, um Benutzende bei Abschluss eines Ereignisses zu gruppieren und die anhaltende Interaktion und Abwanderung im Zeitverlauf zu analysieren."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="Kohortentabelle"
>abstract="Gruppieren Sie Benutzende auf Grundlage des Abschlusses eines Ereignisses und analysieren Sie dann ihre anhaltenden Interaktionen und Abwanderungen im Zeitverlauf. Geben Sie zusätzliche Einstellungen wie Granularität, Typ der Kohortenanalyse und die eventuelle Verwendung rollierender Berechnungen an. Sie können erweiterte Optionen festlegen, um eine Latenztabelle oder eine benutzerdefinierte Dimensionskohorte basierend auf einer ausgewählten Dimension zu erstellen."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_In diesem Artikel wird die Kohortentabelle in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** beschrieben._<br/>_Unter [Kohortentabelle](https://experienceleague.adobe.com/de/docs/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis) finden Sie die Version dieses Artikels für_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._

>[!ENDSHADEBOX]


Eine *Kohorte* ist eine Personengruppe mit gemeinsamen Merkmalen innerhalb eines vorgegebenen Zeitraums. Eine Visualisierung ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL Kohortentabelle]** ist z. B. dann nützlich, wenn Sie wissen möchten, wie eine Kohorte mit einer Marke interagiert. Sie können problemlos Trend-Änderungen offenlegen und entsprechend reagieren. (Erläuterungen zur [!UICONTROL Kohortenanalyse] sind im Internet verfügbar, z. B. unter [Cohort Analysis 101](https://de.wikipedia.org/wiki/Cohort_analysis).)

Nachdem Sie einen Kohortenbericht erstellt haben, können Sie dessen Komponenten (bestimmte Dimensionen, Metriken und Segmente) kuratieren und den Kohortenbericht dann für andere freigeben. Weitere Informationen finden Sie unter [Kuratieren und freigeben](/help/analysis-workspace/curate-share/curate.md).

Beispiele für die Nutzung einer [!UICONTROL Kohortentabelle]:

* Starten Sie Kampagnen, die dafür ausgelegt sind, eine erwünschte Aktion anzuregen.
* Erhöhen Sie das Marketingbudget genau zum richtigen Zeitpunkt im Kundenlebenszyklus.
* Erkennen Sie, wann eine Testphase oder ein Angebot beendet werden sollte, um den Wert zu maximieren.
* Gewinnen Sie Ideen für A/B-Tests in Bereichen wie Preisstruktur, Upgrade-Pfad usw.

Die [!UICONTROL Kohortentabelle] steht allen Customer Journey Analytics-Kundinnen und -Kunden mit Zugriffsrechten auf [!UICONTROL Analysis Workspace] zur Verfügung.


>[!BEGINSHADEBOX]

Unter ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Kohortenanalyse in Analysis Workspace](https://video.tv.adobe.com/v/3430076/?quality=12&learn=on&captions=ger){target="_blank"} finden Sie ein Demovideo.

{{videoaa}}

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>[!UICONTROL Kohortenanalyse] unterstützt keine nicht segmentierbaren Metriken (einschließlich berechneter Metriken), Nicht-Ganzzahlmetriken (z. B. Umsatz) oder Vorfälle. In der [!UICONTROL Kohortenanalyse“ können nur Metriken verwendet werden, die auch in Segmenten verwendet &#x200B;] können. Darüber hinaus können diese Metriken jeweils nur 1 inkrementiert werden.

Kohortentabellen in Customer Journey Analytics unterstützen Dubletten-basierte (oder beliebige numerische) Metriken. Beispielsweise kann „Purchase.Value“ (eine Dublette) als Einschluss-/Rückgabemetrik verwendet werden. Darüber hinaus sind alle Metriken, die über den Analytics-Quell-Connector an Adobe Experience Platform übergeben werden, ebenfalls Dubletten.

## Funktionen der Kohortentabelle

In den folgenden Abschnitten werden Funktionen zur Kohortenanalyse beschrieben, die eine Feinabstimmung der Kontrolle über die Kohorten ermöglichen, die Sie erstellen.

Weitere ausführliche Informationen zum Erstellen einer Kohorte und zum Ausführen eines [!UICONTROL Kohortenanalyse-Berichts] finden Sie unter [Konfigurieren einer Kohortentabelle](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### Aufbewahrungstabelle

Eine [!UICONTROL Bindungskohortentabelle] gibt Personen zurück: Jede Datenzelle zeigt die Roh- und Prozentanzahl der Personen in der Kohorte, die die Aktion während dieses Zeitraums ausgeführt haben. Sie können bis zu 3 Metriken und bis zu 10 Segmente einschließen.

![Ein Bindungskohortenbericht mit den Einheiten und dem Prozentsatz der Personen in der Kohorte.](assets/retention-report.png)

### Abwanderungstabelle

Eine [!UICONTROL Abwanderungskohortentabelle] ist die Umkehrung einer Bindungstabelle und zeigt die Personen an, die abgewandert sind oder die Rückkehrkriterien für Ihre Kohorte im Laufe der Zeit nie erfüllt haben. Sie können bis zu 3 Metriken und bis zu 10 Segmente einschließen.

![Eine Abwanderungstabelle mit den Einheiten und dem Prozentsatz der Personen, die die Rückkehrkriterien für eine Kohorte nicht erfüllt haben.](assets/churn-report.png)

### Rollierende Berechnung

Sie können die Kundenbindung oder -abwanderung basierend auf der vorherigen Spalte berechnen, nicht basierend auf der eingeschlossenen Spalte, was als rollierende Berechnung bezeichnet wird.

![Ein Kohortenbindungsbericht mit den Berechnungen, die auf einer vorherigen Datenspalte basieren.](assets/retention-report-rolling.png)

### Latenztabelle

Eine Latenztabelle misst die verstrichene Zeit vor und nach dem Aufnahmeereignis. Das Messen der Latenz ist ein hervorragendes Instrument für die Vor- und Nachanalyse. Die Spalte **[!UICONTROL Aufnahme]** befindet sich in der Mitte der Tabelle und die Zeiträume vor und nach dem Aufnahmeereignis werden auf beiden Seiten angezeigt.

![Ein Kohortenbericht mit der verstrichenen Zeit vor und nach einem Ereignis.](assets/retention-report-latency.png)

### Benutzerdefinierte Dimensionskohorte

Sie können Kohorten auf Grundlage einer ausgewählten Dimension und nicht auf Grundlage zeitbasierter Kohorten (was die Standardeinstellung ist) erstellen. Verwenden Sie Dimensionen wie [!UICONTROL Ort-Geo], [!UICONTROL Marketing-Kanal], [!UICONTROL Kampagne], [!UICONTROL Produkt], [!UICONTROL Seite], [!UICONTROL Region] oder jede andere Dimension, um zu zeigen, wie sich die Bindung ändert. Basierend auf den verschiedenen Werten dieser Dimensionen.

![Ein Kohortenbericht, der einen benutzerdefinierten Bericht mit ausgewählten Dimensionen zeigt, nicht die standardmäßige, zeitbasierte Kohorte.](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[Konfigurieren einer Kohortentabelle](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).
>

