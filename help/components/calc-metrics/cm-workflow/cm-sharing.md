---
description: Erfahren Sie, wie Sie Metriken für Ihre gesamte Organisation, Gruppen oder einzelne Benutzer freigeben können.
title: Berechnete Metriken freigeben
feature: Calculated Metrics
exl-id: b2a3e4e3-f0aa-4505-b3f5-7d9f14dc1640
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 5%

---

# Berechnete Metriken freigeben

Im [Manager für berechnete Metriken](cm-manager.md) können Sie berechnete Metriken freigeben. Je nach Ihren Berechtigungen können Sie berechnete Metriken für Ihre gesamte Organisation, Gruppen oder einzelne Benutzer freigeben:

* **Administratoren**: Administratoren können berechnete Metriken für die gesamte Organisation, für Gruppen innerhalb einer Organisation und für einzelne Benutzer freigeben. Weitere Informationen finden Sie in der [Dokumentation zu Admin Console](https://helpx.adobe.com/de/enterprise/using/manage-products.html).
* **Benutzer ohne Administratorrechte**: Benutzer ohne Administratorrechte können die von ihnen erstellte berechnete Metrik nur für einzelne Benutzer freigeben.

So geben Sie eine oder mehrere berechnete Metriken frei:

1. Wählen [ im Manager für ](cm-manager.md) berechnete Metriken eine oder mehrere der berechneten Metriken aus, die Sie freigeben möchten.
1. Wählen Sie in der Aktionsleiste ![Freigeben](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Freigeben]** aus.
1. Im Dialogfeld **[!UICONTROL Berechnete Metrik freigeben]**:

   ![Dialogfeld „Berechnete Metriken freigeben“](assets/share-calculated-metrics-dialog.png)

   1. (Optional) Verwenden Sie ![Suche](/help/assets/icons/Search.svg), um *Einzelpersonen oder Gruppen suchen* die Liste der Gruppen oder Einzelpersonen, für die Sie die berechnete Metrik freigeben möchten, zu suchen und einzuschränken.

   1. Wählen Sie eine oder mehrere Optionen aus dem Abschnitt **[!UICONTROL Organisation]** oder **[!UICONTROL Gruppen]** oder suchen Sie nach einer oder mehreren Einzelpersonen und wählen Sie diese aus. Welche Optionen verfügbar sind, hängt von Ihrer Rolle ab.

   1. Wählen Sie **[!UICONTROL Speichern]** aus, um die berechneten Metriken freizugeben. Wählen Sie zum Abbrechen **[!UICONTROL Abbrechen]** aus.

## Best Practices

Im Folgenden finden Sie Best Practices für die Freigabe berechneter Metriken und für Personen, für die Sie berechnete Metriken freigeben sollten.

* Geben Sie als Administrator eine berechnete Metrik nur dann für alle frei, wenn Sie überzeugt sind, dass die Verwendung der berechneten Metrik für alle Mitarbeiter in Ihrem Unternehmen annehmbar ist. Sie können auch in Betracht ziehen, diese berechneten Metriken zu bevorzugen. Weitere [ finden Sie unter „Markieren ](cm-favorite.md) berechneten Metrik als Favorit“.

* Geben Sie als Administrator eine berechnete Metrik für eine bestimmte Gruppe frei, wenn diese berechnete Metrik einen Geschäftswert für die Benutzer dieser Gruppe bietet.

* Geben Sie als Administrator oder einzelner Benutzer eine berechnete Metrik für eine oder mehrere Personen frei, um eine berechnete Metrik zu validieren. Wenn sich die Segmente als nicht nützlich erweisen, können Sie die berechnete Metrik löschen.


<!--

Depending on your permissions, you can share metrics with your whole organization, groups, or individual users.

|  Role | Permissions |
|---|---|
|  Administrator  | Can share metrics with All, with Groups, and with Users. Groups are set up as permission groups in the Admin console.  |
|  Non-Administrator  | Can share metrics only with individual users.  |

To share a calculated metric:

1. In the Calculated metrics manager, mark the checkbox next to the metric you want to share.

   ![Calculated metrics manager showing the available icons across the top of the window including Hide Filters, Tag, Share, Delete, and Copy.](assets/cm_task_bar.png)

1. Select the **[!UICONTROL Share]** icon. ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg)

   The Share Calculated metric dialog box displays.

   ![Share Calculated metric window with All selected for the Organization.](assets/cm_share.png)

1. Select **[!UICONTROL Share]**.

1. Choose who you want to share with:

   * **[!UICONTROL All]** (Administrators only): Shares with all users in the organization.

     Consider sharing with all only if it's of use to the entire company and everyone is comfortable using it. In this case, you should also consider making it an [approved metric](/help/components/calc-metrics/cm-workflow/cm-approving.md).
   
   * **[!UICONTROL Groups]** (Administrators only): Select any groups you want to share with.

     Consider sharing with a group if the metric provides good business value for that team.
   
   * **[!UICONTROL Individual users]**: Search for and select the individual users you want to share with.

      This is the only share option available to all users. Administrators might want to use this option to vet and validate a metric prior to making it available to a group or to everyone. If the metric isn't useful, it can be discarded. Administrators should not officially approve this type of metric.

1. Select **[!UICONTROL Share]**.

   The Shared icon appears next to the metric: ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg).

1. You can filter on metrics shared with you by going to **[!UICONTROL Filters]** > **[!UICONTROL Other Filters]** > **[!UICONTROL Shared with Me]**.

1. (Optional) To filter the list of calculated metrics in the Calculated metrics manager to show only metrics that are shared with you, select the **Filter** icon, expand **[!UICONTROL Other filters]**, then select **[!UICONTROL Shared with me]**.

-->