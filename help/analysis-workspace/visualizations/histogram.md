---
description: Ein Histogramm ähnelt einem Balkendiagramm, fasst jedoch Zahlen zu Bereichen (Behältern) zusammen.
title: Histogramm
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
source-git-commit: bf5853a1d23d6e648024016a64dc67d09da3fbb4
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 35%

---

# Histogramm {#histogram}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="Histogramm"
>abstract="Erstellen Sie eine Histogrammvisualisierung, um die Verteilung numerischer Daten in Bereichsgruppen darzustellen."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*In diesem Artikel wird die Histogrammvisualisierung in **Customer Journey Analytics.**.<br/>Siehe [Histogramm](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/histogram) für die **Adobe Analytics**-Version dieses Artikels.*

>[!ENDSHADEBOX]


Die ![Histogramm](/help/assets/icons/Histogram.svg)**[!UICONTROL Histogramm]**-Visualisierung ähnelt einer [!UICONTROL Balken]-Visualisierung, gruppiert jedoch Zahlen in Bereiche (Buckets). Analytics automatisiert diese Zusammenfassung von Zahlen zu Bereichen, wobei Sie jedoch die Einstellungen unter [Erweiterte Einstellungen](#advanced-settings) ändern können.

## Verwenden

So erstellen Sie ein Histogramm:

1. Fügen Sie ![ Visualisierung ](/help/assets/icons/Histogram.svg)Histogramm **[!UICONTROL hinzu]**. Siehe [Hinzufügen einer Visualisierung zu einem Bedienfeld](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Ziehen Sie eine Metrik aus der **[!UICONTROL Metriken]** Komponentenliste oder wählen Sie eine Metrik aus dem [!UICONTROL *Metrik hinzufügen*] Dropdown-Menü aus.
1. (Optional) Wählen Sie **[!UICONTROL Erweiterte Einstellungen anzeigen]** aus. Siehe [Erweiterte Einstellungen](#advanced-settings)
1. Wählen Sie **[!UICONTROL Erstellen]** aus.

>[!NOTE]
>
>Histogramme unterstützen nur Standardmetriken, keine berechneten Metriken.

Im folgenden Beispiel wird ein Histogramm verwendet, um Sitzungen für die Anzahl der Personen zu gruppieren. Das Histogramm zeigt, dass die meisten Personen für den ausgewählten Datumsbereich zwischen 16 und 21 Sitzungen haben.

![](assets/histogram.png)

## Erweiterte Einstellungen

Im Rahmen der Visualisierung stehen spezifische Histogrammeinstellungen zur Verfügung.

| Histogramm-Einstellungen | Beschreibung |
|---|---|
| **[!UICONTROL Start-Bucket]** | Bestimmt, mit welchem Paket das Histogramm beginnt. Die Standardeinstellung lautet 1. Sie können Startwerte von null bis unendlich festlegen, jedoch keine negativen Zahlen. |
| **[!UICONTROL Metrische Buckets]** | Ermöglicht das Erhöhen/Verringern der Anzahl der Datenbereiche (Buckets). Die maximale Anzahl von Buckets ist 50. |
| **[!UICONTROL Metrik-Bucket-Größe]** | Hiermit können Sie die Größe der einzelnen Behälter festlegen. So könnten Sie zum Beispiel die Behältergröße von 1 Seitenansicht zu 2 Seitenansichten ändern. |
| **[!UICONTROL Zählmethode]** | Wählen Sie aus **[!UICONTROL Person]**, **[!UICONTROL Sitzung]** oder **[!UICONTROL Ereignis]**. Zum Beispiel Seitenansichten pro Sitzung oder Seitenansichten pro Person oder Seitenansichten pro Ereignis. |

<!--Russ or Meike - Check Hit Type link above. -->

**Beispiele**:

| Startereimer | Metrische Buckets | Metrik-Bucket-Größe | Ergebnis |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![Histogramm, Start-Bucket 1, Metrik-Buckets 5, Metrik-Bucket Größe 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![Histogramm, Start-Bucket 0, Metrik-Buckets 3, Metrik-Bucket Größe 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[Hinzufügen einer Visualisierung zu einem Bedienfeld](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualisierungseinstellungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Kontextmenü der Visualisierung](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>


## Blogpost

In diesem Blogpost finden Sie Informationen zu [Verwendung von Histogrammen zur Identifizierung unerwarteter Datenwerte](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168).
