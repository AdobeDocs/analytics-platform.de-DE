---
description: Erfahren Sie, wie Sie in einer Fallout-Analyse in Analysis Workspace Segmente aus einem Touchpoint erstellen, Segmente als Touchpoint hinzufügen und wichtige Workflows über verschiedene Segmente hinweg vergleichen können.
keywords: Fallout und Segmentierung;Segmente in Fallout-Analyse;Segmente in Fallout vergleichen
title: Segmente in Fallout-Analyse anwenden
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
role: User
autotag-review: '2026-05-19T08:42:20.474Z'
TQID: 'https://experienceleague.adobe.com/ZJqvJYmUSMfWD-yX3B-qbR5QNq7bjr9xtGN-yPXkl5E'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 484
ht-degree: 23%

---

# Segmente in der Fallout-Analyse anwenden

Sie können in Analysis Workspace Segmente aus einem Touchpoint erstellen, Segmente als Touchpoints hinzufügen und wichtige Workflows über verschiedene Segmente hinweg vergleichen.

>[!IMPORTANT]
>
>Segmente, die als Checkpoints in Fallout verwendet werden, müssen einen Container verwenden, der auf einer niedrigeren Ebene liegt als der Gesamtkontext der Fallout-Visualisierung. Bei einem personenbezogenen Kontext-Fallout müssen Segmente, die als Checkpoints verwendet werden, sitzungs- oder ereignisbasierte Segmente sein. Bei einem Sitzungskontext-Fallout müssen Segmente, die als Checkpoint verwendet werden, ereignisbasierte Segmente sein. Wenn Sie eine ungültige Kombination verwenden, beträgt der Fallout 100 %. In der Fallout-Visualisierung wird eine Warnung angezeigt, wenn Sie ein inkompatibles Segment als Touchpoint hinzufügen. Bestimmte ungültige Segment-Container-Kombinationen führen zu ungültigen Fallout-Diagrammen, z. B.:
>
>* Verwenden eines personenbasierten Segments als Touchpoint innerhalb einer Fallout-Visualisierung des Personenkontexts.
>* Verwenden eines personenbasierten Segments als Touchpoint innerhalb einer Fallout-Visualisierung mit Sitzungskontext.
>* Verwenden eines sitzungsbasierten Segments als Touchpoint innerhalb einer Sitzungskontext-Fallout-Visualisierung.

<!-- 
Should we add B2B context here?
* [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} Usimg a B2B container based segment as a touchpoint inside a non-container based context Fallout visualization.
* 
-->

## Erstellen eines Segments aus einem Touchpoint

1. Als Erstes erstellen Sie ein Segment aus einem bestimmten Touchpoint, an dem Sie interessiert sind und der sich möglicherweise lohnt, auch in andere Berichte übernommen zu werden. Klicken Sie mit der rechten Maustaste auf den Touchpoint und wählen Sie **[!UICONTROL Segment aus Touchpoint erstellen]**.

   ![Das Dropdown-Menü „Touchpoint“ mit hervorgehobener Option „Segment aus Touchpoint erstellen“.](assets/fallout-createsegment.png)

   Der [!UICONTROL Segment Builder] wird geöffnet und enthält vorab das vordefinierte sequenzielle Segment, das dem von Ihnen ausgewählten Touchpoint entspricht:

   ![Segment Builder zeigt das vorausgefüllte und vordefinierte sequenzielle Segment an.](assets/fallout-definesegment.png)

1. Geben Sie dem Segment einen Titel und eine Beschreibung und speichern Sie es.

   Dieses Segment kann jetzt in jedem gewünschten Projekt verwendet werden.

## Hinzufügen eines Segments als Touchpoint

Wenn Sie z. B. wissen möchten, wie der Trend bei Ihren US-Benutzern aussieht und wie sich dies auf den Fallout auswirkt, ziehen Sie einfach das Segment „US-Benutzer“ in den Fallout:

![Das Segment „US-Benutzer“ wurde ausgewählt und hervorgehoben, um es in den Fallout zu ziehen.](assets/fallout-addfilter.png)

Oder Sie können einen UND-Touchpoint erstellen, indem Sie das Segment „US-Benutzer“ auf einen anderen Checkpoint ziehen.

## Vergleichen von Segmenten im Fallout

In der Fallout-Visualisierung können Sie eine unbegrenzte Anzahl von Segmenten miteinander vergleichen.

1. Wählen Sie die zu vergleichenden Segmente aus dem Bedienfeld [!UICONTROL Segment] auf der linken Seite aus. Im Beispiel werden drei Segmente ausgewählt: *Flugdetails: Seitenversion A*, *Flugdetails: Seitenversion B* und *Flugdetails: Seitenversion C*.
1. Ziehen Sie die drei Segmente in den Ablegebereich für Segmente am oberen Rand der Visualisierung.


1. Optional: Sie können *Alle Personen* als Standard-Container beibehalten oder den Container löschen.

   ![Der Fallout, der alle Besuche zusammen mit den beiden Segmenten anzeigt, die im vorherigen Schritt gezogen wurden.](assets/fallout-multiplefilters.png)

1. Sie können jetzt den Fallout über die drei Segmente hinweg vergleichen, z. B. wo ein Segment eine bessere Leistung als das andere erzielt, oder andere Einblicke erhalten.
