---
description: Erfahren Sie, wie Sie berechnete Metriken erstellen.
title: Berechnete Metriken erstellen
feature: Calculated Metrics
exl-id: 55ed36c1-99ca-400a-bc2b-661994cbf720
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# Berechnete Metriken erstellen

Standardmäßig können nur Administratoren berechnete Metriken erstellen. Benutzer haben Berechtigungen zum Anzeigen berechneter Metriken, ähnlich wie beim Anzeigen anderer Komponenten (wie Filter, Anmerkungen usw.) durch Benutzer.

Administratoren können Benutzern über die [Admin Console](/help/technotes/access-control.md#user-level-access) jedoch die Berechtigung **[!UICONTROL Erstellung berechneter Metriken]** für die **[!UICONTROL Berichterstellungs-Tools]** in **[!UICONTROL Berechtigungen für CJA Workspace Access bearbeiten]** erteilen.


Sie können eine berechnete Metrik wie folgt erstellen:

![Möglichkeiten zum Erstellen eines Filters](assets/create-metric.png)

* ?? Wählen Sie in der Hauptbenutzeroberfläche **[!UICONTROL Komponenten]** und dann **[!UICONTROL Berechnete Metriken]** aus. Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**] aus dem [[!UICONTROL Manager für berechnete Metriken]](/help/components/calc-metrics/cm-workflow/cm-manager.md).
* ?? Wählen Sie in einem Workspace-Projekt im linken Bereich &quot;Komponenten&quot;unter ![Ereignis](/help/assets/icons/Event.svg) **Metriken** die Option ![Hinzufügen](/help/assets/icons/Add.svg) aus.
* ?? Wählen Sie in einem Workspace-Projekt im Kontextmenü in der Spaltenüberschrift Metriken die Option **[!UICONTROL Metrik aus Auswahl erstellen]**. Im Untermenü können Sie eine Funktion auswählen oder **[!UICONTROL Im Generator für berechnete Metriken öffnen]** auswählen. <br/>Wenn Sie eine Funktion auswählen, wird die berechnete Metrik als reine Projektmetrik definiert. Wenn Sie diese Metrik später über das Popup-Fenster [Komponenteninformationen](/help/components/use-components-in-workspace.md#component-info) bearbeiten, erhalten Sie eine Benachrichtigung im [Generator für berechnete Metriken](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
* ?? Wählen Sie in einem Workspace-Projekt **[!UICONTROL Komponenten]** aus dem Menü und dann **[!UICONTROL Metrik erstellen]**.
* ?? Verwenden Sie in einem Workspace-Projekt den Tastaturbefehl **[!UICONTROL shift+cmd+c]** (macOS) oder **[!UICONTROL shift+ctrl+c]** (Windows).

Um die neue berechnete Metrik zu definieren, verwenden Sie den [Generator für berechnete Metriken](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

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
