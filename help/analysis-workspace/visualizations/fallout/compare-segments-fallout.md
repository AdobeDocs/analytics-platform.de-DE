---
description: Sie können in Analysis Workspace Filter aus einem Touchpoint erstellen, Filter als Touchpoints hinzufügen und wichtige Workflows über verschiedene Filter hinweg vergleichen.
keywords: Fallout und Filter;Filter in Fallout-Analyse;Filter in Fallout vergleichen
title: Anwenden von Filtern in der Fallout-Analyse
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
role: User
source-git-commit: 6a279ac39e6b94200ff93ac1a3796d202e6349c7
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 43%

---

# Anwenden von Filtern in der Fallout-Analyse

Sie können in Analysis Workspace Filter aus einem Touchpoint erstellen, Filter als Touchpoints hinzufügen und wichtige Workflows über verschiedene Filter hinweg vergleichen.

>[!IMPORTANT]
>
>Filter, die als Checkpoints in Fallout verwendet werden, müssen einen Container verwenden, der auf einer niedrigeren Ebene als der Gesamtkontext der Fallout-Visualisierung liegt. Bei einem personenbezogenen Fallout müssen Filter, die als Checkpoints verwendet werden, sitzungs- oder ereignisbasierte Filter sein. Bei einem Sitzungskontext-Fallout müssen Filter, die als Checkpoint verwendet werden, ereignisbasierte Filter sein. Wenn Sie eine ungültige Kombination verwenden, beträgt der Fallout 100 %. Wenn Sie einen inkompatiblen Filter als Touchpoint hinzufügen, wird eine Warnung zur Fallout-Visualisierung angezeigt. Bestimmte ungültige Filter-Container-Kombinationen führen zu ungültigen Fallout-Diagrammen, wie:
>
>* Verwenden eines personenbasierten Filters als Touchpoint innerhalb einer Fallout-Visualisierung für Personen
>* Verwenden eines personenbasierten Filters als Touchpoint innerhalb einer Fallout-Visualisierung des Sitzungskontexts
>* Verwenden eines sitzungsbasierten Filters als Touchpoint innerhalb einer Fallout-Visualisierung des Sitzungskontexts

## Erstellen eines Filters aus einem Touchpoint

1. Erstellen Sie einen Filter aus einem bestimmten Touchpoint, an dem Sie interessiert sind und den Sie eventuell auch in andere Berichte übernehmen möchten. Klicken Sie mit der rechten Maustaste auf den Touchpoint und wählen Sie **[!UICONTROL Filter aus Touchpoint erstellen]** aus.

   ![Das Dropdown-Menü &quot;Touchpoint&quot;mit hervorgehobenem Symbol &quot;Segment aus Touchpoint erstellen&quot;.](assets/fallout-createfilter.png)

   Der [!UICONTROL Filter-Builder] wird geöffnet und ist vorab mit dem vordefinierten sequenziellen Filter gefüllt, der mit dem ausgewählten Touchpoint übereinstimmt:

   ![Der Filtergenerator zeigt den vorausgefüllten und vordefinierten sequenziellen Filter an.](assets/fallout-definefilter.png)

1. Geben Sie einen Titel und eine Beschreibung für den Filter ein und speichern Sie ihn.

   Nun können Sie diesen Filter in jedem gewünschten Projekt verwenden.

## Hinzufügen eines Filters als Touchpoint

Wenn Sie zum Beispiel wissen möchten, wie der Trend bei Ihren Benutzern aus den USA aussieht und wie sich dies in der Fallout-Analyse auswirkt, ziehen Sie einfach den Filter „USA-Benutzer“ in den Fallout:

![Der Filter &quot;US-Benutzer&quot;wurde ausgewählt und hervorgehoben, um ihn in den Fallout zu ziehen.](assets/fallout-addfilter.png)

Oder Sie erstellen einen AND-Touchpoint, indem Sie den Filter „USA-Benutzer“ auf einen anderen Checkpoint ziehen.

## Vergleichen von Filtern im Fallout

In der Fallout-Visualisierung können Sie eine unbegrenzte Anzahl von Filtern miteinander vergleichen.

1. Wählen Sie die zu vergleichenden Filter im Bereich [!UICONTROL Filter] auf der linken Seite aus. Im Beispiel werden drei Filter ausgewählt: *Flugdetails: Seitenversion A*, *Flugdetails: Seitenversion B* und *Flugdetails: Seitenversion C*.
1. Sie ziehen die drei Filter auf die Dropzone Filter oben in der Visualisierung.


1. Optional: Sie können *Alle Besuche* als Standardbehälter beibehalten oder den Container löschen.

   ![Der Fallout, der alle Besuche anzeigt, zusammen mit den beiden Filtern, die im vorherigen Schritt gezogen wurden.](assets/fallout-multiplefilters.png)

1. Sie können jetzt den Fallout über die drei Filter hinweg vergleichen, z. B. wo ein Filter eine bessere Leistung erzielt, oder andere Einblicke.
