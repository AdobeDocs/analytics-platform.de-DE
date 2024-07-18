---
description: Ein Histogramm ähnelt einem Balkendiagramm, fasst jedoch Zahlen zu Bereichen (Behältern) zusammen.
title: Histogramm
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 80%

---

# Histogramm

Ein Histogramm ähnelt einem Balkendiagramm, fasst jedoch Zahlen zu Bereichen (Behältern) zusammen. Analytics automatisiert diese Zusammenfassung von Zahlen zu Bereichen, wobei Sie jedoch die Einstellungen unter [Erweiterte Einstellungen](#section_09D774C584864D4CA6B5672DC2927477) ändern können.

## Erstellen eines Histogramms {#section_74647707CC984A1CB6D3097F43A30B45}

So erstellen Sie ein Histogramm:

1. Klicken Sie in der linken Leiste auf **[!UICONTROL Visualisierungen]**.
1. Ziehen Sie **[!UICONTROL Histogramm]** in das Bedienfeld.
1. Wählen Sie eine Metrik zum Ziehen der Visualisierung „Histogramm“ aus und klicken Sie dann auf **[!UICONTROL Erstellen]**.

![Leeres Histogrammbedienfeld, das das Feld Metrik unter Feld ablegen anzeigt.](assets/histogram.png)

>[!NOTE]
>
>Histogramme unterstützen nur Standardmetriken, keine berechneten Metriken.

Hier haben wir die Metrik „Seitenansichten pro Unique Visitors“ verwendet. Der erste (linke) Behälter entspricht 1 Seitenansicht pro Einzelperson, der zweite Behälter zwei Seitenansichten usw.

![](assets/histogram2.png)

## Erweiterte Einstellungen {#section_09D774C584864D4CA6B5672DC2927477}

Wenn Sie die Einstellungen für Ihr Histogramm ändern möchten, klicken Sie auf das Einstellungssymbol (Zahnrad) in der Ecke oben rechts. Die folgenden Einstellungen können Sie ändern:

| Histogramm-Einstellungen | Dient dem folgenden Zweck |
|---|---|
| Startpaket | Bestimmt, mit welchem Paket das Histogramm beginnt. Die Standardeinstellung lautet 1. Sie können Startwerte von null bis unendlich festlegen, jedoch keine negativen Zahlen. |
| Metrische Behälter | Hiermit können Sie die Anzahl der Datumsbereiche (Behälter) erhöhen/verringern. Maximal 50 Buckets sind möglich. |
| Metrische Behältergröße | Hiermit können Sie die Größe der einzelnen Behälter festlegen. So könnten Sie zum Beispiel die Behältergröße von 1 Seitenansicht zu 2 Seitenansichten ändern. |
| Zählmethode | Sie können als Typ [Besucher](https://experienceleague.adobe.com/docs/analytics/components/metrics/unique-visitors.html?lang=de), [Besuch](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=de) oder „Treffer“ auswählen, Zum Beispiel Seitenansichten pro Besuch oder Seitenansichten pro Person oder Seitenansichten pro Ereignis. Für Hits wird „Vorkommen“ in der Freiformtabelle als Metrik der Y-Achse verwendet. |

<!--Russ or Meike - Check Hit Type link above. -->

**Beispiele**:

* Startpaket: 1; Metrische Behälter: 5; Metrische Behältergröße: 2 – Diese Werte würden zu dem folgenden Histogramm führen: 1-2, 3-4, 5-6, 7-8, 9-10.
* Startpaket: 0; Metrische Behälter: 3; Metrische Behältergröße: 5 – Diese Werte würden zu dem folgenden Histogramm führen: 0-4, 5-9, 10-14.

## Anzeigen und Bearbeiten von Histogrammdaten {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

Wenn Sie die Datenquelle für das Histogramm anzeigen oder ändern möchten, klicken Sie auf den Punkt neben der Histogramm-Überschrift und navigieren Sie zu **[!UICONTROL Datenquelleneinstellungen]** > **[!UICONTROL Datenquelle anzeigen]**.

![Optionen für Daten-Source-Einstellungen mit ausgewählter Option &quot;Data Source anzeigen&quot;und &quot;Auswahl sperren&quot;](assets/manage-data-source.png)

Vorkonfigurierte Filter, die in der Tabelle angezeigt werden, sind interne Filter und werden in der Filterauswahl nicht angezeigt. Klicken Sie auf das Symbol „i“ neben dem Filternamen und dann auf **[!UICONTROL Veröffentlichen]**, um den Filter öffentlich zu machen.

![Segmente, die das Bearbeitungsfenster und den öffentlichen Link anzeigen.](assets/prebuilt_segments.png)

Weitere Möglichkeiten zum Verwalten von Freiform-Datentabellen und anderen Visualisierungen (wie zum Beispiel Datenaufschlüsselungen) finden Sie [hier](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=de).

## Blogpost

In diesem Blogpost finden Sie Informationen zu [mithilfe von Histogrammen zur Identifizierung unerwarteter Datenwerte](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168).
