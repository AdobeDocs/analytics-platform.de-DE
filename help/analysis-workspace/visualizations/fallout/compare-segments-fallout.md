---
description: Sie können in Analysis Workspace Segmente aus einem Touchpoint erstellen, Segmente als Touchpoints hinzufügen und wichtige Workflows über verschiedene Segmente hinweg vergleichen.
keywords: Fallout und Segmente;Segmente in Fallout-Analyse;Segmente im Fallout vergleichen
title: Segmente in der Fallout-Analyse anwenden
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
role: User
source-git-commit: 770320a0b16d26e0755203a3524b000db30cac82
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 38%

---

# Segmente in der Fallout-Analyse anwenden

Sie können in Analysis Workspace Segmente aus einem Touchpoint erstellen, Segmente als Touchpoints hinzufügen und wichtige Workflows über verschiedene Segmente hinweg vergleichen.

>[!IMPORTANT]
>
>Filter, die als Checkpoints in Fallout verwendet werden, müssen einen Container verwenden, der auf einer niedrigeren Ebene als der Gesamtkontext der Fallout-Visualisierung liegt. Bei einem personenbezogenen Kontext-Fallout müssen Segmente, die als Checkpoints verwendet werden, sitzungs- oder ereignisbasierte Segmente sein. Bei einem Sitzungskontext-Fallout müssen Segmente, die als Checkpoint verwendet werden, ereignisbasierte Segmente sein. Wenn Sie eine ungültige Kombination verwenden, beträgt der Fallout 100 %. Wenn Sie ein inkompatibles Segment als Touchpoint hinzufügen, wird eine Warnung an die Fallout-Visualisierung angezeigt. Bestimmte ungültige Segment-Container-Kombinationen führen zu ungültigen Fallout-Diagrammen, z. B.:
>
>* Verwenden eines personenbasierten Segments als Touchpoint innerhalb einer Fallout-Visualisierung des Personenkontexts
>* Verwenden eines personenbasierten Segments als Touchpoint innerhalb einer Fallout-Visualisierung mit Sitzungskontext
>* Verwenden eines sitzungsbasierten Segments als Touchpoint innerhalb einer Sitzungskontext-Fallout-Visualisierung

## Erstellen eines Segments aus einem Touchpoint

1. Als Erstes erstellen Sie ein Segment aus einem bestimmten Touchpoint, an dem Sie interessiert sind und der sich möglicherweise lohnt, auch in andere Berichte übernommen zu werden. Klicken Sie mit der rechten Maustaste auf den Touchpoint und wählen Sie **[!UICONTROL Segment aus Touchpoint erstellen]**.

   ![Das Dropdown-Menü „Touchpoint“ mit hervorgehobener Option „Segment aus Touchpoint erstellen“.](assets/fallout-createfilter.png)

   Der [!UICONTROL Filter Builder] wird geöffnet und enthält vorab das vordefinierte sequenzielle Segment, das dem von Ihnen ausgewählten Touchpoint entspricht:

   ![Der Filtergenerator zeigt das vorausgefüllte und vordefinierte sequenzielle Segment an.](assets/fallout-definefilter.png)

1. Geben Sie einen Titel und eine Beschreibung für das Segment ein, und speichern Sie es.

   Dieses Segment kann jetzt in jedem gewünschten Projekt verwendet werden.

## Hinzufügen eines Segments als Touchpoint

Wenn Sie zum Beispiel wissen möchten, wie der Trend bei Ihren Benutzern aus den USA aussieht und wie sich dies in der Fallout-Analyse auswirkt, ziehen Sie einfach das Segment „USA-Benutzer“ in den Trichter:

![Das Segment „US-Benutzer“ wurde ausgewählt und hervorgehoben, um es in den Fallout zu ziehen.](assets/fallout-addfilter.png)

Oder Sie erstellen einen AND-Touchpoint, indem Sie das Segment „USA-Benutzer“ auf einen anderen Checkpoint ziehen.

## Vergleichen von Segmenten im Fallout

In der Fallout-Visualisierung können Sie eine unbegrenzte Anzahl von Segmenten miteinander vergleichen.

1. Wählen Sie die zu vergleichenden Segmente aus dem Bedienfeld [!UICONTROL Filter] auf der linken Seite aus. Im Beispiel werden drei Segmente ausgewählt: *Flugdetails: Seitenversion A*, *Flugdetails: Seitenversion B* und *Flugdetails: Seitenversion C*.
1. Sie ziehen die drei Segmente auf den Ablegebereich für Filter oben in der Visualisierung.


1. Optional: Sie können *Alle Besuche* als Standard-Container beibehalten oder den Container löschen.

   ![Der Fallout, der alle Besuche zusammen mit den beiden Segmenten anzeigt, die im vorherigen Schritt gezogen wurden.](assets/fallout-multiplefilters.png)

1. Sie können jetzt den Fallout über die drei Segmente hinweg vergleichen, z. B. wo ein Segment eine bessere Leistung als das andere erzielt, oder andere Einblicke erhalten.
