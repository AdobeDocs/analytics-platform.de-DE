---
description: Erfahren Sie, wie Sie eine Teilnahmemetrik erstellen.
title: Beitragsmetrik
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
TQID: https://experienceleague.adobe.com/no7rAZUl25LTEPqwRyC7vY4XcottzPGRq-DCAR5ez54
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
    internal-label: Calculated metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 58ed911b3d2c719dd05082c463fe66403e207ef9
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 6%
---
# Beitragsmetriken

Teilnehmermetriken werden verwendet, um zu quantifizieren, wie einzelne Werte für eine Dimension (wie Seitenansichten) zu Sitzungen, die eine bestimmte Metrik enthalten (wie Bestellungen), beitragen oder daran teilnehmen.

>[!NOTE]
>
>Admins können Metriken mit nicht standardmäßigen Attributionsmodellen wie „Teilnahme“ als Teil einer [Datenansicht“ &#x200B;](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/data-views). Weitere [&#x200B; finden Sie unter &#x200B;](../../../data-views/component-settings/attribution.md) der Attributionskomponente .

Die folgenden Schritte zeigen, wie jeder Benutzer mit der [Berechtigung Berechnete Metrik erstellen](/help/technotes//access-control.md#user-level-access) eine Teilnahmemetrik erstellen kann.

1. [Erstellen Sie eine berechnete &#x200B;](cm-workflow.md) und geben Sie der Metrik im [Generator für berechnete &#x200B;](cm-build-metrics.md)&quot; einen `Participation` oder etwas Ähnliches.
1. Ziehen Sie eine Metrik, die ein Erfolgsereignis enthält, z. B. [!DNL Orders], in den Bereich [!UICONTROL **[!UICONTROL Definition]**].
1. Wählen Sie ![&#x200B; Metrik &#x200B;](/help/assets/icons2/Settings.svg)Zahnrad) aus.
1. Wählen Sie im angezeigten Popup die Option **[!UICONTROL Nicht standardmäßiges Attributionsmodell verwenden]**, um das [Attributionsmodell](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) dieses Ereignisses für **[!UICONTROL Teilnahme]** zu definieren, und wählen Sie **[!UICONTROL Sitzung]** für den [!UICONTROL Container]. Wählen Sie **[!UICONTROL Übernehmen]** zur Bestätigung aus.


   ![Spalten-Attributionsmodell-Popup, in dem die ausgewählte Teilnahme als Modell und die für das Lookback-Fenster ausgewählte Sitzung angezeigt werden.](assets/participation-setup.png)

   **(Teilnahme|Sitzung)** wird zum Komponentennamen für die Metrik hinzugefügt.



1. Wählen [!UICONTROL **Speichern**], um die Metrik zu speichern.
1. Verwenden Sie die berechnete Metrik in Ihrem Bericht. Verwenden Sie beispielsweise die berechnete [!DNL Orders (Session Participation)]-Metrik in einem Bericht, um anzuzeigen, welche Kundenebene zu Sitzungen beigetragen hat, die eine Bestellung enthielten (oder daran teilgenommen hat).

   ![Freiformtabelle mit Kundenebene und Bestellungen.](assets/participation-pages-customer-tier.png)
