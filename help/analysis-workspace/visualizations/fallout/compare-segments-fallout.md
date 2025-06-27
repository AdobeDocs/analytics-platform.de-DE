---
description: Erfahren Sie, wie Sie in einer Fallout-Analyse in Analysis Workspace Segmente aus einem Touchpoint erstellen, Segmente als Touchpoint hinzufügen und wichtige Workflows über verschiedene Segmente hinweg vergleichen können.
keywords: Fallout und Segmentierung;Segmente in Fallout-Analyse;Segmente in Fallout vergleichen
title: Segmente in Fallout-Analyse anwenden
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
role: User
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 34%

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
<!-- Should we add B2B context here?
* [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} Usimg a B2B container based segment as a touchpoint inside a non-container based context Fallout visualization.
* -->

## Erstellen eines Segments aus einem Touchpoint

1. Als Erstes erstellen Sie ein Segment aus einem bestimmten Touchpoint, an dem Sie interessiert sind und der sich möglicherweise lohnt, auch in andere Berichte übernommen zu werden. Klicken Sie mit der rechten Maustaste auf den Touchpoint und wählen Sie **[!UICONTROL Segment aus Touchpoint erstellen]**.

   ![Das Dropdown-Menü „Touchpoint“ mit hervorgehobener Option „Segment aus Touchpoint erstellen“.](assets/fallout-createfilter.png)

   Der [!UICONTROL Segment Builder] wird geöffnet und enthält vorab das vordefinierte sequenzielle Segment, das dem von Ihnen ausgewählten Touchpoint entspricht:

   ![Segment Builder zeigt das vorausgefüllte und vordefinierte sequenzielle Segment an.](assets/fallout-definefilter.png)

1. Geben Sie einen Titel und eine Beschreibung für das Segment ein, und speichern Sie es.

   Dieses Segment kann jetzt in jedem gewünschten Projekt verwendet werden.

## Hinzufügen eines Segments als Touchpoint

Wenn Sie zum Beispiel wissen möchten, wie der Trend bei Ihren Benutzern aus den USA aussieht und wie sich dies in der Fallout-Analyse auswirkt, ziehen Sie einfach das Segment „USA-Benutzer“ in den Trichter:

![Das Segment „US-Benutzer“ wurde ausgewählt und hervorgehoben, um es in den Fallout zu ziehen.](assets/fallout-addfilter.png)

Oder Sie erstellen einen AND-Touchpoint, indem Sie das Segment „USA-Benutzer“ auf einen anderen Checkpoint ziehen.

## Vergleichen von Segmenten im Fallout

In der Fallout-Visualisierung können Sie eine unbegrenzte Anzahl von Segmenten miteinander vergleichen.

1. Wählen Sie die zu vergleichenden Segmente aus dem Bedienfeld [!UICONTROL Segment] auf der linken Seite aus. Im Beispiel werden drei Segmente ausgewählt: *Flugdetails: Seitenversion A*, *Flugdetails: Seitenversion B* und *Flugdetails: Seitenversion C*.
1. Ziehen Sie die drei Segmente in den Ablegebereich für Segmente am oberen Rand der Visualisierung.


1. Optional: Sie können *Alle Besuche* als Standard-Container beibehalten oder den Container löschen.

   ![Der Fallout, der alle Besuche zusammen mit den beiden Segmenten anzeigt, die im vorherigen Schritt gezogen wurden.](assets/fallout-multiplefilters.png)

1. Sie können jetzt den Fallout über die drei Segmente hinweg vergleichen, z. B. wo ein Segment eine bessere Leistung als das andere erzielt, oder andere Einblicke erhalten.
