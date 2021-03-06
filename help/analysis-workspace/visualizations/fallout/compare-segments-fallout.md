---
description: Sie können in Analysis Workspace Filter aus einem Touchpoint erstellen, Filter als Touchpoints hinzufügen und wichtige Workflows über verschiedene Filter hinweg vergleichen.
keywords: Fallout und Filter;Filter in Fallout-Analyse;Filter in Fallout vergleichen
title: Anwenden von Filtern in der Fallout-Analyse
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: ht
source-wordcount: '405'
ht-degree: 100%

---

# Anwenden von Filtern in der Fallout-Analyse

Sie können in Analysis Workspace Filter aus einem Touchpoint erstellen, Filter als Touchpoints hinzufügen und wichtige Workflows über verschiedene Filter hinweg vergleichen.

>[!IMPORTANT]
>
>Filter, die als Checkpoints in Fallout verwendet werden, müssen einen Container verwenden, der auf einer niedrigeren Ebene als der Gesamtkontext der Fallout-Visualisierung liegt. Bei einem auf den Besucherkontext bezogenen Fallout müssen Filter, die als Checkpoints verwendet werden, besuchs- oder trefferbasierte Filter sein. Bei einem auf den Besuchskontext bezogenen Fallout müssen Segmente, die als Checkpoint verwendet werden, trefferbasierte Segmente sein. Wenn Sie eine ungültige Kombination verwenden, beträgt der Fallout 100 %. Wir haben eine Warnmeldung zur Fallout-Visualisierung hinzugefügt, die angezeigt wird, wenn Sie einen inkompatiblen Filter als Touchpoint hinzufügen. Bestimmte ungültige Filter-Container-Kombinationen führen zu ungültigen Fallout-Diagrammen, z. B.:

* Verwenden eines besucherbasierten Filters als Touchpoint innerhalb einer auf den Besucherkontext bezogenen Fallout-Visualisierung
* Verwenden eines besucherbasierten Filters als Touchpoint innerhalb einer auf den Besuchskontext bezogenen Fallout-Visualisierung
* Verwenden eines besuchsbasierten Filters als Touchpoint innerhalb einer auf den Besuchskontext bezogenen Fallout-Visualisierung

## Erstellen eines Filters aus einem Touchpoint {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Erstellen Sie einen Filter aus einem bestimmten Touchpoint, an dem Sie interessiert sind und den Sie eventuell auch in andere Berichte übernehmen möchten. Klicken Sie dazu mit der rechten Maustaste auf den Touchpoint und wählen Sie dann **[!UICONTROL Filter aus Touchpoint erstellen]** aus.

   ![](assets/segment-from-touchpoint.png)

   Der Filtergenerator wird geöffnet und enthält bereits den vorkonfigurierten sequenziellen Filter, der zu dem von Ihnen ausgewählten Touchpoint passt:

   ![](assets/segment-builder.png)

1. Geben Sie einen Titel und eine Beschreibung für den Filter ein und speichern Sie ihn.

   Nun können Sie diesen Filter in jedem gewünschten Projekt verwenden.

## Hinzufügen eines Filters als Touchpoint {#section_17611C1A07444BE891DC21EE8FC03EFC}

Wenn Sie zum Beispiel wissen möchten, wie der Trend bei Ihren Benutzern aus den USA aussieht und wie sich dies in der Fallout-Analyse auswirkt, ziehen Sie einfach den Filter „USA-Benutzer“ in den Fallout:

![](assets/segment-touchpoint.png)

Oder Sie erstellen einen AND-Touchpoint, indem Sie den Filter „USA-Benutzer“ auf einen anderen Checkpoint ziehen.

## Vergleichen von Filtern im Fallout {#section_E0B761A69B1545908B52E05379277B56}

In der Fallout-Visualisierung können Sie eine unbegrenzte Anzahl von Filtern miteinander vergleichen.

1. Wählen Sie die zu vergleichenden Filter links in der Leiste [!UICONTROL Filter] aus. Im vorliegenden Beispiel haben wir zwei Filter ausgewählt: „USA-Benutzer“ und „Benutzer außerhalb der USA“.
1. Ziehen Sie sie nach oben in die Ablegezone „Filter“.

   ![](assets/segment-drop.png)

1. Optional: Sie können „Alle Besuche“ als Standard-Container belassen oder ihn löschen.

   ![](assets/seg-compare.png)

1. Sie können nun den Fallout über zwei Filter hinweg vergleichen (z. B. an welcher Stelle ein Filter eine bessere Leistung als der andere hat) oder sonstige Einblicke erhalten.
