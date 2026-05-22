---
title: Attributionsbedienfeld
description: Erfahren Sie, wie Sie das Attributionsbedienfeld in Analysis Workspace verwenden und interpretieren.
feature: Panels
exl-id: 7fdec05b-5d99-48d1-ac1b-c243cb64e487
role: User
TQID: https://experienceleague.adobe.com/sMLOCsAtZVm-fyHPTkPl-ftUHt3k7DvjPrDYPAuAQTw
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5520579-b31f-4df7-9281-f0d9f91e2edc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 689
ht-degree: 82%

---

# Panel „Attribution“ {#attribution-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_attribution_button"
>title="Attribution"
>abstract="Vergleichen und visualisieren Sie im Handumdrehen eine beliebige Anzahl von Attributionsmodellen für eine Erfolgsmetrik, einen Kanal und das Lookback-Fenster."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Attribution IQ-Bedienfeld"

>[!CONTEXTUALHELP]
>id="workspace_attribution_panel"
>title="Panel „Attribution“"
>abstract="Vergleichen und visualisieren Sie im Handumdrehen eine beliebige Anzahl von Attributionsmodellen für eine Erfolgsmetrik. Wählen Sie den Kanal (Dimension), die einzuschließenden Modelle und das Lookback-Fenster aus."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Attribution IQ-Bedienfeld"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_In diesem Artikel wird das Attributionsbedienfeld in_![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;_.<br/>_Siehe [Attributionsbedienfeld](https://experienceleague.adobe.com/de/docs/analytics/analyze/analysis-workspace/panels/attribution)_ für die ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** Version dieses Artikels._

>[!ENDSHADEBOX]

Das **[!UICONTROL Attributionsbedienfeld]** bietet eine einfache Möglichkeit, eine Analyse zu erstellen, mit der verschiedene Attributionsmodelle verglichen werden. Das Panel bietet Ihnen einen speziellen Arbeitsbereich zum Verwenden und Vergleichen von Attributionsmodellen.

Customer Journey Analytics erweitert die Attribution und ermöglicht Ihnen Folgendes:

* Die Attribution über bezahlte Medien definieren: Dimensionen, Metriken, Kanäle oder Ereignisse können auf Modelle (z. B. die interne Suche) angewendet werden, nicht nur Marketing-Kampagnen.
* Den Vergleich für unbegrenzte Attributionsmodelle verwenden: Vergleichen Sie dynamisch so viele Modelle, wie Sie möchten.
* Implementierungsänderungen vermeiden: Mit der Berichtszeitverarbeitung und kontextabhängigen Sitzungen kann Customer Journey-Kontext erstellt und zur Laufzeit angewendet werden.
* Die Sitzung erstellen, die Ihrem Attributionsszenario am ehesten entspricht.
* Die Attribution nach Segmenten aufschlüsseln: Vergleichen Sie problemlos die Leistung Ihrer Marketing-Kanäle über jedes wichtige Segment hinweg (z. B. Neu- mit Bestandskunden, Produkt X vs. Produkt Y, Treuestufe oder CLV).
* Wechsel zwischen Kanälen und Multi-Touch-Analyse beachten: Verwenden Sie Venn-Diagramme und Histogramme und erstellen Sie Trends anhand von Attributionsergebnissen.
* Wichtige Marketing-Sequenzen visuell analysieren: Erkunden Sie zur Konversion führende Pfade visuell mithilfe von mehrknotigen Fluss- und Fallout-Visualisierungen.
* Berechnete Metriken erstellen: Verwenden Sie eine beliebige Anzahl an Attributionszuordnungsmethoden.

## Verwenden

So verwenden Sie das Panel **[!UICONTROL Attribution]**:

1. Erstellen Sie das Panel **[!UICONTROL Attribution]**. Informationen zum Erstellen eines Bedienfelds finden Sie unter [Erstellen eines Bedienfelds](panels.md#create-a-panel).

1. Legen Sie die [Eingabe](#panel-input) für das Bedienfeld fest.

1. Sehen Sie sich die [Ausgabe](#panel-output) für das Bedienfeld an.

### Panel-Eingabe

Sie können das Panel „Attribution“ mithilfe der folgenden Eingabeeinstellungen konfigurieren:

1. Fügen Sie eine **[!UICONTROL Erfolgsmetrik]** und eine Dimension aus dem **[!UICONTROL Kanal]** für die Attribution hinzu. Beispiele sind Marketing-Kanäle oder benutzerdefinierte Dimensionen wie interne Promotions.

   ![Das Fenster des Panels „Attribution“ mit mehreren ausgewählten Dimensionen und Metriken.](assets/attribution-panel.png)

1. Wählen Sie mindestens [Attributionsmodelle](#attribution-models) aus **[!UICONTROL Einbezogene Modelle]**, den [Container](#container) aus **[!UICONTROL Container]** und ein [Lookback-Fenster](#lookback-window) aus dem **[!UICONTROL Lookback-Fenster]**, das Sie für den Vergleich verwenden möchten.

1. Wählen Sie **[!UICONTROL Erstellen]** aus, um die Visualisierungen im Panel zu erstellen.

### Panel-Ausgabe

Das Panel **[!UICONTROL Attribution]** gibt einen umfangreichen Satz an Daten und Visualisierungen zurück, die die Attribution für die ausgewählte Dimension und Metrik vergleichen.

![Die Visualisierungen des Panels „Attribution“, die ausgewählte Metriken und Dimensionen vergleichen.](assets/attr_panel_vizs.png)

### Visualisierungen der Attribution

Die folgenden Visualisierungen sind Teil der Panel-Ausgabe.

* **Summenmetrik**: Die Gesamtzahl der Konversionen, die im Berichtszeitfenster stattgefunden haben und der ausgewählten Dimension zugeordnet wurden.
* **Balkendiagramm für den Vergleich der Metrik-Attribution**: Vergleicht visuell die zugeordneten Konversionen über die einzelnen Dimensionselemente der von Ihren ausgewählten Dimension hinweg. Jede Balkenfarbe stellt ein bestimmtes Attributionsmodell dar.
* **Attributionsvergleichstabelle**: Zeigt dieselben Daten wie das Balkendiagramm in Tabellenform an. Durch die Auswahl verschiedener Spalten oder Zeilen in dieser Tabelle werden das Balkendiagramm sowie mehrere andere Visualisierungen im Bedienfeld segmentiert. Diese Tabelle verhält sich ähnlich wie jede andere Freiformtabelle in Workspace. So können Sie Komponenten wie Metriken, Segmente oder Aufschlüsselungen hinzufügen.
* **Überlagerungsdiagramm**: Eine Venn-Visualisierung, die die drei wichtigsten Dimensionselemente zeigt und wie oft sie gemeinsam an einer Konversion beteiligt sind. Beispielsweise gibt die Größe der Blasenüberlagerung an, wie oft Konversionen auftraten, wenn eine Person beiden Dimensionselementen ausgesetzt war. Durch die Auswahl anderer Zeilen in der angrenzenden Freiformtabelle wird die Visualisierung entsprechend Ihrer Auswahl aktualisiert.
* **Leistungsdetail**: Eine Visualisierung vom Typ „Streuung“ zum visuellen Vergleich von bis zu drei Attributionsmodellen.
* **Trendleistung**: Zeigt den Trend der zugeordneten Konvertierungen für das Element der obersten Dimension. Durch die Auswahl anderer Zeilen in der angrenzenden Freiformtabelle wird die Visualisierung entsprechend Ihrer Auswahl aktualisiert.
* **Fluss**: Hiermit können Sie anzeigen, mit welchen Kanälen am häufigsten interagiert wird und wie sich die Reihenfolge in der Journey einer Person darstellt.

## Attributionsmodell

{{attribution-models-details}}

## Container

{{attribution-container}}

## Lookback-Fenster

{{attribution-lookback-window}}

## Beispiel

{{attribution-example}}

>[!MORELIKETHIS]
>
> [Erstellen eines Bedienfelds](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
