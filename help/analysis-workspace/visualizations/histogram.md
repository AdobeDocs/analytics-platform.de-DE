---
description: Ein Histogramm ähnelt einem Balkendiagramm, fasst jedoch Zahlen zu Bereichen (Behältern) zusammen.
title: Histogramm
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 95%

---

# Histogramm {#histogram}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="Histogramm"
>abstract="Erstellen Sie eine Histogrammvisualisierung, um die Verteilung numerischer Daten in Bereichsgruppen darzustellen."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_In diesem Artikel wird die Visualisierung „Histogramm“ in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** beschrieben._<br/>_Unter [Histogramm](https://experienceleague.adobe.com/de/docs/analytics/analyze/analysis-workspace/visualizations/histogram) finden Sie die Version dieses Artikels für_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._

>[!ENDSHADEBOX]


Die Visualisierung ![Histogram](/help/assets/icons/Histogram.svg) **[!UICONTROL Histogramm]** ähnelt einer Visualisierung [!UICONTROL Balken], fasst jedoch Zahlen zu Bereichen (Buckets) zusammen. Analytics automatisiert diese Zusammenfassung von Zahlen zu Bereichen, wobei Sie jedoch die Einstellungen unter [Erweiterte Einstellungen](#advanced-settings) ändern können.

## Verwenden

So erstellen Sie ein Histogramm:

1. Fügen Sie eine Visualisierung ![Histogram](/help/assets/icons/Histogram.svg) **[!UICONTROL Histogramm]** hinzu. Siehe [Hinzufügen einer Visualisierung zu einem Panel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Ziehen Sie eine Metrik aus **[!UICONTROL Komponentenliste]** Metriken“ oder wählen Sie eine Metrik aus dem [!UICONTROL *Metrik hinzufügen*] Dropdown-Menü aus.
1. (Optional) Wählen Sie **[!UICONTROL Erweiterte Einstellungen einblenden]** aus. Weitere Informationen finden Sie unter [Erweiterte Einstellungen](#advanced-settings).
1. Wählen Sie **[!UICONTROL Erstellen]** aus.

>[!NOTE]
>
>Histogramme unterstützen nur Standardmetriken, keine berechneten Metriken.

Im folgenden Beispiel wird ein Histogramm für das Bucketing von Sitzungen für die Anzahl der Personen verwendet. Das Histogramm zeigt, dass für die meisten Personen für den ausgewählten Datumsbereich zwischen 16 und 21 Sitzungen vorliegen.

![Histogramm](assets/histogram.png)

## Erweiterte Einstellungen

Im Rahmen der Visualisierung sind bestimmte Histogrammeinstellungen verfügbar.

| Histogrammeinstellungen | Beschreibung |
|---|---|
| **[!UICONTROL Anfangs-Bucket]** | Bestimmt, mit welchem Paket das Histogramm beginnt. Die Standardeinstellung lautet 1. Sie können Startwerte von null bis unendlich festlegen, jedoch keine negativen Zahlen. |
| **[!UICONTROL Metrik-Buckets]** | Hiermit können Sie die Anzahl der Datenbereiche (Buckets) erhöhen/verringern. Die maximale Anzahl von Buckets ist 50. |
| **[!UICONTROL Metrik-Bucket-Größe]** | Hiermit können Sie die Größe der einzelnen Behälter festlegen. So könnten Sie zum Beispiel die Behältergröße von 1 Seitenansicht zu 2 Seitenansichten ändern. |
| **[!UICONTROL Zählmethode]** | Sie haben die Wahl zwischen **[!UICONTROL Globales Konto]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Konto]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Käufergruppe]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Opportunity]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Person]**, **[!UICONTROL Sitzung]** oder **[!UICONTROL Ereignis]**. Zum Beispiel Seitenansichten pro Konto [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, Seitenansichten pro Sitzung, Seitenansichten pro Person oder Seitenansichten pro Ereignis.  |

<!--Russ or Meike - Check Hit Type link above. -->

**Beispiele**:

| Anfangs-Bucket | Metrik-Buckets | Metrik-Bucket-Größe | Ergebnis |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![Histogramm, Anfangs-Bucket 1, Metrik-Buckets 5, Metrik-Bucket-Größe 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![Histogramm, Anfangs-Bucket 0, Metrik-Buckets 3, Metrik-Bucket-Größe 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[Hinzufügen einer Visualisierung zu einem Panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualisierungseinstellungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Kontextmenü der Visualisierung](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>[Verwenden von Histogrammen zur Identifizierung unerwarteter Datenwerte](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168)

