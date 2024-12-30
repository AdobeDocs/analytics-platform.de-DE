---
description: Erfahren Sie, wie Sie berechnete Metriken erstellen.
title: Erstellen von berechneten Metriken
feature: Calculated Metrics
exl-id: 55ed36c1-99ca-400a-bc2b-661994cbf720
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 2%

---

# Erstellen von berechneten Metriken

Standardmäßig können nur Administratoren berechnete Metriken erstellen. Benutzer haben die Berechtigung, berechnete Metriken anzuzeigen, ähnlich wie Benutzer andere Komponenten anzeigen (z. B. Filter, Anmerkungen).

Administratoren können jedoch die Berechtigung **[!UICONTROL Erstellung berechneter Metriken]** für **[!UICONTROL Reporting-Tools]** in **[!UICONTROL Berechtigungen für CJA Workspace bearbeiten]** über die [Admin Console ](/help/technotes/access-control.md#user-level-access).


Sie können eine berechnete Metrik wie folgt erstellen:

![Möglichkeiten zum Erstellen eines Filters](assets/create-metric.png)

* ?? Wählen Sie in der Hauptbenutzeroberfläche die Option **[!UICONTROL Komponenten]** und wählen Sie **[!UICONTROL Berechnete Metriken]**. Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**] aus dem [[!UICONTROL Manager für berechnete ]](/help/components/calc-metrics/cm-workflow/cm-manager.md).
* ?? Wählen Sie in einem Workspace-Projekt im linken Bedienfeld Komponenten ![Hinzufügen](/help/assets/icons/Add.svg) unter ![Ereignis](/help/assets/icons/Event.svg) **Metriken**.
* ?? Wählen Sie in einem Workspace-Projekt im Kontextmenü in der Spaltenüberschrift Metriken die Option **[!UICONTROL Metrik aus Auswahl erstellen]**. Aus dem Untermenü können Sie eine Funktion auswählen oder auf **[!UICONTROL In Generator für berechnete Metriken öffnen]** klicken. <br/>Wenn Sie eine Funktion auswählen, wird die berechnete Metrik als reine Projektmetrik definiert. Wenn Sie diese Metrik später über das Popup [Komponenteninformationen](/help/components/use-components-in-workspace.md#component-info) bearbeiten, erhalten Sie eine Benachrichtigung im Generator [Berechnete Metrik](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
* ?? Wählen Sie in einem Workspace-Projekt **[!UICONTROL Komponenten]** aus dem Menü aus und wählen Sie **[!UICONTROL Metrik erstellen]**.
* ?? Verwenden Sie in einem Workspace-Projekt die Tastenkombination **[!UICONTROL Umschalt+Befehlstaste+C]** (macOS) oder **[!UICONTROL Umschalt+Strg+C]** (Windows).

Um die neue berechnete Metrik zu definieren, verwenden Sie den [Generator für berechnete ](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)&quot;.

<!--

Learn about the steps to take for creating calculated metrics.

| Workflow Task | Description |
| --- | --- |
| Plan Calculated Metrics | Especially for metrics that are going to be officially "approved", it makes sense to outline which calculated metrics will be widely used and how they will be defined. |
| [Build](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) Calculated Metrics | Build and edit calculated and advanced calculated metrics for use in [!DNL Customer Journey Analytics] components. |
| [Tag](cm-tagging.md) Calculated Metrics | Tag calculated metrics for ease of organization and sharing. See how to plan and assign tags for simple and advanced searches and organization. |
| [Approve](cm-approving.md) Calculated Metrics | Approve calculated metrics to make them canonical. |
| Apply Calculated Metrics | You can apply metrics directly from a report, from the Metric Selector (to access it, click [!UICONTROL Show Metrics]). |
| Filter Calculated Metrics | In the Metric Selector, click [!UICONTROL Advanced Selection] and filter by tags, owners, and other filters (Show All, Mine, Shared With me, Favorites, and Approved.) |
| Mark Calculated Metrics as [Favorites](cm-finding.md) | Marking metrics as favorites is another way to organize them for ease of use.|

-->
