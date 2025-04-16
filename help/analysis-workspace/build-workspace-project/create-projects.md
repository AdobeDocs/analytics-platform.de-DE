---
description: Erfahren Sie, wie Sie ein Projekt in Analysis Workspace erstellen
title: Erstellen von Projekten
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
source-git-commit: 04586de02765ddeba72aca3132b9eca5d22aced7
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 88%

---

# Erstellen von Projekten {#create-projects}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_project_countrepeatinstances"
>title="Wiederholungsinstanzen zählen"
>abstract="Diese Einstellung legt fest, ob wiederholte Instanzen in Berichten gezählt werden sollen.<br/><br/>Hinweis: Diese Einstellung gilt nicht für Fluss- oder Fallout-Visualisierungen."

<!-- markdownlint-enable MD034 -->


Mit [Projekten](/help/analysis-workspace/build-workspace-project/freeform-overview.md) in Analysis Workspace können Sie geschäftskritische Analysen erstellen und anzeigen.  Diese Analysen können für Stakeholderinnen und Stakeholder innerhalb oder außerhalb Ihrer Organisation freigegeben werden.

1. Wählen Sie in Customer Journey Analytics die Option **[!UICONTROL Workspace]** aus.

1. Wählen Sie im linken Bedienfeld die Option **[!UICONTROL Projekte]** und dann **[!UICONTROL Projekt erstellen]** aus.

1. Wählen Sie **Leeres Workspace-Projekt** aus, um Ihr Workspace-Projekt mit einem Browser zu erstellen.

   Weitere Informationen zum Erstellen eines mobilen Scorecard-Projekts, das per App mit anderen Stakeholderinnen und Stakeholdern geteilt werden kann, finden Sie unter [Leere mobile Scorecard](/help/mobile-app/curator.md). Außerdem gibt es unter [Geführte Analyse](/help/guided-analysis/overview.md) weitere Informationen zu den verschiedenen verfügbaren Optionen zum Erstellen geführter Analyseprojekte.

1. Wählen Sie [!UICONTROL **Erstellen**] aus.


Nachdem Sie nun ein leeres Workspace-Projekt erstellt haben, sollten Sie mit der Benutzeroberfläche von [Analysis Workspace](/help/analysis-workspace/home.md) vertraut sein. Wenn dem so ist, können Sie Ihr Projekt erstellen. Gehen Sie dazu wie folgt vor:

![Beispielprojekt](assets/example-project.png)

* Fügen Sie dem Projekt [Bedienfelder](/help/analysis-workspace/c-panels/panels.md) hinzu, z. B. das **[!DNL Example Panel]** ➊.

* Fügen Sie Ihren Bedienfeldern [Visualisierungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) hinzu, z. B.:
   * [Linienvisualisierungen](/help/analysis-workspace/visualizations/line.md) vom Typ **[!DNL Line Graph]** ➋
   * [Freiformtabellen-Visualisierungen](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) vom Typ **[!DNL Countries]** ➌
* Fügen Sie Ihren Visualisierungen [Komponenten](/help/components/overview.md) hinzu, z. B.:
   * eine [Dimension](/help/components/dimensions/overview.md) vom Typ **[!DNL Store Country]** ➍
   * eine [Metrik](/help/components/apply-create-metrics.md) vom Typ **[!DNL People]** ➎
   * eine [berechnete Metrik](/help/components/calc-metrics/calc-metr-overview.md) vom Typ **[!DNL Avg Order Value]** ➏
   * **[!DNL Mobile App Sessions]** [segment](/help/components/filters/filters-overview.md) ➐
   * einen [Datumsbereich](/help/components/date-ranges/overview.md) vom Typ **[!DNL Last Month]** ➑
   * eine [Anmerkung](/help/components/annotations/overview.md) vom Typ **[!DNL Example]** ➒


## Projektinfo und Einstellungen {#project-info-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="Wiederholungsinstanzen zählen"
>abstract="Diese Einstellung legt fest, ob wiederholte Instanzen in Berichten gezählt werden sollen.<br/>Hinweis: Diese Einstellung gilt nicht für Fluss- oder Fallout-Visualisierungen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_project_commenting"
>title="Kommentieren zulassen"
>abstract="Wenn diese Option aktiviert ist, ist in der rechten Leiste des Projekts in Analysis Workspace ein Kommentarbereich verfügbar."

<!-- markdownlint-enable MD034 -->


Die Projekteinstellungen enthalten auf der Projektebene befindliche Informationen über das derzeit aktive Projekt.

![Das Fenster „Projektinformationen und -einstellungen“](./assets/projectinfo.png)

Zu den Einstellungen gehören:

| Einstellung | Beschreibung |
|---|---|
| Projektname | Der Name des Projekts. Sie können auf den Namen doppelklicken, um ihn zu bearbeiten. |
| Besitzer | Name des Projektbesitzer. |
| Zuletzt geändert | Das Datum, an dem die letzte Änderung an dem Projekt vorgenommen wurde. |
| Tags | Zeigt eine Liste aller Tags an, die auf ein Projekt angewendet wurden, um die Kategorisierung zu vereinfachen. |
| Beschreibung | Eine Beschreibung hilft, den Zweck eines Projekts anzugeben. Sie können auf die Beschreibung doppelklicken, um sie zu bearbeiten. |
| Wiederholungsinstanzen zählen | Diese Einstellung legt fest, ob Wiederholungsinstanzen in Berichten gezählt werden sollen. Hinweis: Diese Einstellung gilt nicht für Fluss- oder Fallout-Visualisierungen. |
| Anmerkungen anzeigen | Legen Sie fest, ob Anmerkungen für dieses Projekt angezeigt werden sollen. |
| [Projekt-Farbpalette](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Sie können die in Workspace verwendete Farbpalette für Kategorien ändern, indem Sie aus den vordefinierten Paletten wählen, die für die Farbenblindheit optimiert wurden, oder indem Sie eine benutzerdefinierte Palette angeben. Diese Funktion betrifft vieles in Workspace, einschließlich der meisten Visualisierungen. |
| [Dichte anzeigen](/help/analysis-workspace/build-workspace-project/view-density.md) | Mit dieser Option können Sie mehr Daten auf dem Bildschirm anzeigen, indem Sie den vertikalen Abstand des linken Bedienfelds, der Freiformtabellen und der Kohortentabellen reduzieren. |
| Kommentieren zulassen | Wenn diese Option aktiviert ist, ist in der rechten Leiste des Projekts in Analysis Workspace ein Kommentarbereich verfügbar. Weitere Informationen finden Sie unter [Hinzufügen und Verwalten von Kommentaren in Projekten](/help/analysis-workspace/build-workspace-project/comment-projects.md). |



