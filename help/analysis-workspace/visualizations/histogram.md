---
description: Ein Histogramm ähnelt einem Balkendiagramm, fasst jedoch Zahlen zu Bereichen (Behältern) zusammen.
title: Histogramm
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
source-git-commit: c94e97723a4ed30e675144e02196c93016b13235
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 75%

---

# Histogramm {#histogram}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="Histogramm"
>abstract="Erstellen Sie eine Histogrammvisualisierung, um die Verteilung numerischer Daten in Bereichsgruppen darzustellen."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_In diesem Artikel wird die Histogrammvisualisierung in {_}![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Siehe [Histogramm](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/histogram) für die_![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**-Version dieses Artikels._

>[!ENDSHADEBOX]


Die ![Histogram](/help/assets/icons/Histogram.svg) **[!UICONTROL Histogrammvisualisierung]** ähnelt einer [!UICONTROL Balkenvisualisierung], fasst jedoch Zahlen zu Bereichen (Buckets) zusammen. Analytics automatisiert diese Zusammenfassung von Zahlen zu Bereichen, wobei Sie jedoch die Einstellungen unter [Erweiterte Einstellungen](#advanced-settings) ändern können.

## Verwenden

So erstellen Sie ein Histogramm:

1. Fügen Sie eine ![Histogram](/help/assets/icons/Histogram.svg) **[!UICONTROL Histogrammvisualisierung]** hinzu. Weitere Informationen finden Sie unter [Hinzufügen einer Visualisierung in einem Bedienfeld](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
1. Ziehen Sie eine Metrik aus der Komponentenliste **[!UICONTROL Metriken]** oder wählen Sie eine Metrik aus dem Dropdown-Menü [!UICONTROL *Metrik hinzufügen*] aus.
1. (Optional) Wählen Sie **[!UICONTROL Erweiterte Einstellungen einblenden]** aus. Weitere Informationen finden Sie unter [Erweiterte Einstellungen](#advanced-settings).
1. Wählen Sie **[!UICONTROL Erstellen]** aus.

>[!NOTE]
>
>Histogramme unterstützen nur Standardmetriken, keine berechneten Metriken.

Im folgenden Beispiel wird ein Histogramm für das Bucketing von Sitzungen für die Anzahl der Personen verwendet. Das Histogramm zeigt, dass für die meisten Personen für den ausgewählten Datumsbereich zwischen 16 und 21 Sitzungen vorliegen.

![Histogramm](assets/histogram.png)

## Erweiterte Einstellungen

Im Rahmen der Visualisierung sind bestimmte Histogrammeinstellungen verfügbar.

| Histogrammeinstellungen | Beschreibung |
|---|---|
| **[!UICONTROL Anfangs-Bucket]** | Bestimmt, mit welchem Paket das Histogramm beginnt. Die Standardeinstellung lautet 1. Sie können Startwerte von null bis unendlich festlegen, jedoch keine negativen Zahlen. |
| **[!UICONTROL Metrik-Buckets]** | Ermöglicht das Erhöhen/Verringern der Anzahl der Datenbereiche (Buckets). Die maximale Anzahl von Buckets ist 50. |
| **[!UICONTROL Metrik-Bucket-Größe]** | Hiermit können Sie die Größe der einzelnen Behälter festlegen. So könnten Sie zum Beispiel die Behältergröße von 1 Seitenansicht zu 2 Seitenansichten ändern. |
| **[!UICONTROL Zählmethode]** | Wählen Sie aus **[!UICONTROL Globales Konto]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Einkaufsgruppe]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Opportunity]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Person]**, **[!UICONTROL Sitzung]** oder **[!UICONTROL Event]**. Beispielsweise Seitenansichten pro Konto [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, Seitenansichten pro Sitzung oder Seitenansichten pro Person oder Seitenansichten pro Ereignis. |

<!--Russ or Meike - Check Hit Type link above. -->

**Beispiele**:

| Anfangs-Bucket | Metrik-Buckets | Metrik-Bucket-Größe | Ergebnis |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![Histogramm, Anfangs-Bucket 1, Metrik-Buckets 5, Metrik-Bucket Größe 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![Histogramm, Anfangs-Bucket 0, Metrik-Buckets 3, Metrik-Bucket Größe 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[Hinzufügen einer Visualisierung in einem Bedienfeld](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualisierungseinstellungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Kontextmenü der Visualisierung](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>[Verwenden von Histogrammen zur Identifizierung unerwarteter Datenwerte](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168?profile.language=de)

