---
description: Mit dem Generator für berechnete Metriken kann jeder Benutzer eine Beitragsmetrik erstellen.
title: Beitragsmetrik
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 5%

---

# Erstellen einer Teilnahmemetrik

In diesem Artikel wird erläutert, wie Sie eine Beitragsmetrik erstellen. Eine Beitragsmetrik zeigt an, wie einzelne Werte für eine Dimension (wie Seitenansichten, Marketingkanal) zu Sitzungen beitragen oder an Sitzungen teilnehmen, die eine bestimmte Metrik enthalten (z. B. Bestellungen).

Diese Art von Informationen kann für jeden Inhaltsbesitzer nützlich sein.

>[!NOTE]
>
>Metriken mit anderen Attributionsmodellen, wie z. B. Beitrag, können auch von Administratoren als Teil einer [Datenansicht](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=de) erstellt werden. Weitere Informationen finden Sie unter [Einstellungen der Zuordnungskomponente](../../../data-views/component-settings/attribution.md) .<br/>Das folgende Beispiel zeigt, wie eine Beitragsmetrik von jedem Benutzer erstellt werden kann, der Zugriff auf den Generator für berechnete Metriken in Workspace hat.


1. Beginnen Sie mit der Erstellung einer Metrik, wie in [Metriken erstellen](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) beschrieben.
1. Nennen Sie die Metrik im Generator für berechnete Metriken `Participation` oder eine ähnliche Metrik.
1. Ziehen Sie eine Metrik, die ein Erfolgsereignis enthält, z. B. [!DNL Orders], in die Arbeitsfläche [!UICONTROL Definition] .
1. Wählen Sie ![Zahnrad](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) für die Metrik aus.
1. Wählen Sie im angezeigten Popup die Option **[!UICONTROL Nicht standardmäßiges Attributionsmodell verwenden]** aus, um das [Attributionsmodell](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) dieses Ereignisses in **[!UICONTROL Beitrag]** zu definieren, und wählen Sie **[!UICONTROL Sitzung]** für das [!UICONTROL Lookback-Fenster]. Wählen Sie zur Bestätigung **[!UICONTROL Anwenden]** aus.

   Im Feld &quot;Definition&quot;wird die ausgewählte Metrik aktualisiert, indem **(Partipation|Session)** an ihren Namen angehängt wird.

   ![Spalten-Attributionsmodell-Popup mit ausgewähltem Beitrag als Modell und ausgewählter Sitzung für das Lookback-Fenster.](assets/participation-setup.png)



1. Wählen Sie [!UICONTROL **Speichern**] aus, um die Metrik zu speichern.
1. Verwenden Sie die berechnete Metrik in Ihrem Bericht. Verwenden Sie beispielsweise die berechnete Metrik [!DNL Orders (Session Participation)] (wie in Schritt 5 definiert) in einem Bericht, um anzuzeigen, welche Kundenebene zu Sitzungen beigetragen hat (oder an Sitzungen teilgenommen hat), die eine Bestellung enthielten.

   ![Freiformtabelle mit der Kundenebene und den Bestellungen.](assets/participation-pages-customer-tier.png)

1. (Optional) Geben Sie die Metrik für andere Benutzer in Ihrer Organisation frei, wie unter [Berechnete Metriken freigeben](/help/components/calc-metrics/cm-workflow/cm-sharing.md) beschrieben.
