---
description: Erfahren Sie, wie Sie eine einfache berechnete Metrik erstellen.
title: Einfache berechnete Metrik erstellen
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
TQID: https://experienceleague.adobe.com/hbiAmMoSUMm2Ggf5Vkxm484SzYETtgRRZAuaWvlS884
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 225
ht-degree: 10%

---

# Einfache berechnete Metrik erstellen

In den folgenden Informationen wird erläutert, wie Sie eine einfache Metrik *Seitenansichten pro Besuch* erstellen.

1. Beginnen Sie mit dem Erstellen einer Metrik, wie in [Metriken erstellen](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) beschrieben.
1. Benennen Sie die Metrik `Page Views per Session` oder etwas Ähnliches.
1. Geben Sie der Metrik eine benutzerfreundliche **[!UICONTROL Beschreibung]**, um anzuzeigen, wofür die Metrik verwendet wird.
1. Wählen Sie rechts **[!UICONTROL Format]** aus. Wählen Sie für dieses Beispiel &quot;**[!UICONTROL &quot;]**.
1. Legen Sie fest, wie viele Dezimalstellen der Bericht anzeigen soll.
1. Wählen Sie **[!UICONTROL Dropdown-Menü]** Aufwärts-Trend anzeigen als▲ die Option **[!UICONTROL Gut (Grün)]**.
1. Fügen Sie ein **[!UICONTROL Tag]** hinzu, um die Metriken zu organisieren.
1. Ziehen Sie für diese berechnete Metrik zunächst **[!UICONTROL Seitenansichten]** aus den **[!UICONTROL Metriken]**-Komponenten in den **[!UICONTROL Definition]**-Abschnitt der Arbeitsfläche.
1. Ziehen Sie dann **[!UICONTROL Sitzungen]** aus den Komponenten **[!UICONTROL Metriken]** und legen Sie die Metrik unter **[!UICONTROL Seitenansichten]** ab (warten Sie, bis die blaue Linie angezeigt wird, bevor Sie die Metrik ablegen).
1. Wählen Sie den Operator ![Trennen](/help/assets/icons/Divide.svg). (Dividieren ist der Standardoperator.)
1. Sie können eine **[!UICONTROL Vorschau]** der Metrik sehen, während Sie die Metrik erstellen.
1. **[!UICONTROL Produktkompatibilität]** Zeigt an, ob die berechnete Metrik überall in Customer Journey Analytics kompatibel ist (ohne Experimente).

   ![Einfache berechnete Metrik](assets/simple-calculated-metric.png)
1. Wählen Sie **[!UICONTROL Speichern]** aus.

   Beachten Sie, dass die Formel unter **[!UICONTROL Zusammenfassung]** jedes Mal, wenn Sie die Metrikdefinition ändern, aktualisiert wird.

1. (Optional) Zum Freigeben, Genehmigen, (erneuten) Taggen, Umbenennen oder Löschen einer Metrik können Sie zum [Manager für berechnete Metriken](/help/components/calc-metrics/cm-workflow/cm-manager.md).

