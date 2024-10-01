---
description: Mit dem Generator für berechnete Metriken kann jeder eine Beitragsmetrik erstellen.
title: Beitragsmetrik
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: 65eafd65358d9370b452338ce1036e59b3c69d1a
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---

# Beitragsmetriken

Beitragsmetriken werden verwendet, um zu quantifizieren, wie einzelne Werte für eine Dimension (wie Seitenansichten) zu Sitzungen mit einer bestimmten Metrik (wie Bestellungen) beitragen oder daran teilnehmen.

>[!NOTE]
>
>Administratoren können im Rahmen einer [Datenansicht](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views) Metriken mit nicht standardmäßigen Attributionsmodellen wie &quot;Beitrag&quot;erstellen. Weitere Informationen finden Sie unter [Einstellungen der Zuordnungskomponente](../../../data-views/component-settings/attribution.md) .

Die folgenden Schritte zeigen, wie jeder Benutzer mit [Berechtigung für berechnete Metriken erstellen](/help/technotes//access-control.md#user-level-access) eine Beitragsmetrik erstellen kann.

1. [Erstellen Sie eine berechnete Metrik](cm-workflow.md) und nennen Sie im [Generator für berechnete Metriken](cm-build-metrics.md) die Metrik `Participation` oder etwas Ähnliches.
1. Ziehen Sie eine Metrik, die ein Erfolgsereignis enthält, z. B. [!DNL Orders], in den Bereich [!UICONTROL **[!UICONTROL Definition]**] .
1. Wählen Sie ![Zahnrad](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) für die Metrik aus.
1. Wählen Sie im angezeigten Popup die Option **[!UICONTROL Nicht standardmäßiges Attributionsmodell verwenden]** aus, um das [Attributionsmodell](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) dieses Ereignisses in **[!UICONTROL Beitrag]** zu definieren, und wählen Sie **[!UICONTROL Sitzung]** für das [!UICONTROL Lookback-Fenster]. Wählen Sie zur Bestätigung **[!UICONTROL Anwenden]** aus.


   ![Spalten-Attributionsmodell-Popup mit ausgewähltem Beitrag als Modell und ausgewählter Sitzung für das Lookback-Fenster.](assets/participation-setup.png)

   **(Partipation|Session)** wird zum Namen der Metrik-Komponente hinzugefügt.



1. Wählen Sie [!UICONTROL **Speichern**] aus, um die Metrik zu speichern.
1. Verwenden Sie die berechnete Metrik in Ihrem Bericht. Verwenden Sie beispielsweise die berechnete Metrik [!DNL Orders (Session Participation)] in einem Bericht, um anzuzeigen, welche Kundenebene zu Sitzungen beigetragen hat (oder an Sitzungen teilgenommen hat), die eine Bestellung enthielten.

   ![Freiformtabelle mit der Kundenebene und den Bestellungen.](assets/participation-pages-customer-tier.png)
