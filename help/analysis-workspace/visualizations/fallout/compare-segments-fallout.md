---
description: Sie können in Analysis Workspace Filter aus einem Touchpoint erstellen, Filter als Touchpoints hinzufügen und wichtige Workflows über verschiedene Filter hinweg vergleichen.
keywords: Fallout und Filter;Filter in Fallout-Analyse;Filter in Fallout vergleichen
title: Anwenden von Filtern in der Fallout-Analyse
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 76%

---

# Anwenden von Filtern in der Fallout-Analyse

Sie können in Analysis Workspace Filter aus einem Touchpoint erstellen, Filter als Touchpoints hinzufügen und wichtige Workflows über verschiedene Filter hinweg vergleichen.

>[!IMPORTANT]
>
>Filter, die als Checkpoints in Fallout verwendet werden, müssen einen Container verwenden, der auf einer niedrigeren Ebene als der Gesamtkontext der Fallout-Visualisierung liegt. Bei einer personenbezogenen Fallout-Funktion müssen Filter, die als Checkpoints verwendet werden, besuchs- oder ereignisbasierte Filter sein. Bei einem besuchskontextbezogenen Fallout müssen als Checkpoint verwendete Filter ereignisbasierte Filter sein. Wenn Sie eine ungültige Kombination verwenden, beträgt der Fallout 100 %. Wir haben eine Warnmeldung zur Fallout-Visualisierung hinzugefügt, die angezeigt wird, wenn Sie einen inkompatiblen Filter als Touchpoint hinzufügen. Bestimmte ungültige Filter-Container-Kombinationen führen zu ungültigen Fallout-Diagrammen, z. B.:

* Verwenden eines personenbasierten Filters als Touchpoint innerhalb einer Fallout-Visualisierung für Personen
* Verwenden eines personenbasierten Filters als Touchpoint innerhalb einer Fallout-Visualisierung für Besuche
* Verwenden eines besuchsbasierten Filters als Touchpoint innerhalb einer auf den Besuchskontext bezogenen Fallout-Visualisierung

## Erstellen eines Filters aus einem Touchpoint {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Erstellen Sie einen Filter aus einem bestimmten Touchpoint, an dem Sie interessiert sind und den Sie eventuell auch in andere Berichte übernehmen möchten. Klicken Sie dazu mit der rechten Maustaste auf den Touchpoint und wählen Sie dann **[!UICONTROL Filter aus Touchpoint erstellen]** aus.

   ![Das Dropdown-Menü &quot;Touchpoint&quot;mit hervorgehobenem Symbol &quot;Segment aus Touchpoint erstellen&quot;.](assets/segment-from-touchpoint.png)

   Der Filtergenerator wird geöffnet und enthält bereits den vorkonfigurierten sequenziellen Filter, der zu dem von Ihnen ausgewählten Touchpoint passt:

   ![Der Filtergenerator zeigt den vorausgefüllten und vordefinierten sequenziellen Filter an.](assets/segment-builder.png)

1. Geben Sie einen Titel und eine Beschreibung für den Filter ein und speichern Sie ihn.

   Nun können Sie diesen Filter in jedem gewünschten Projekt verwenden.

## Hinzufügen eines Filters als Touchpoint {#section_17611C1A07444BE891DC21EE8FC03EFC}

Wenn Sie zum Beispiel wissen möchten, wie der Trend bei Ihren Benutzern aus den USA aussieht und wie sich dies in der Fallout-Analyse auswirkt, ziehen Sie einfach den Filter „USA-Benutzer“ in den Fallout:

![Der Filter &quot;US-Benutzer&quot;wurde ausgewählt und hervorgehoben, um ihn in den Fallout zu ziehen.](assets/segment-touchpoint.png)

Oder Sie erstellen einen AND-Touchpoint, indem Sie den Filter „USA-Benutzer“ auf einen anderen Checkpoint ziehen.

## Vergleichen von Filtern im Fallout {#section_E0B761A69B1545908B52E05379277B56}

In der Fallout-Visualisierung können Sie eine unbegrenzte Anzahl von Filtern miteinander vergleichen.

1. Wählen Sie die zu vergleichenden Filter links in der Leiste [!UICONTROL Filter] aus. Im vorliegenden Beispiel haben wir zwei Filter ausgewählt: „USA-Benutzer“ und „Benutzer außerhalb der USA“.
1. Ziehen Sie sie nach oben in die Ablegezone „Filter“.

   ![Die Fallout-Visualisierung mit ausgewählten Filtern und dem roten Pfeil, der auf die Filterablagezone zeigt.](assets/segment-drop.png)

1. Optional: Sie können „Alle Besuche“ als Standard-Container belassen oder ihn löschen.

   ![Der Fallout, der alle Besuche anzeigt, zusammen mit den beiden Filtern, die im vorherigen Schritt gezogen wurden.](assets/seg-compare.png)

1. Sie können nun den Fallout über zwei Filter hinweg vergleichen (z. B. an welcher Stelle ein Filter eine bessere Leistung als der andere hat) oder sonstige Einblicke erhalten.
