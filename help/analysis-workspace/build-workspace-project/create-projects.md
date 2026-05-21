---
description: Erfahren Sie, wie Sie ein Projekt in Analysis Workspace erstellen.
title: Erstellen von Projekten
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
TQID: https://experienceleague.adobe.com/DWTWJ2Bd9iEPO2awiiOLcUzUGPc-clZul3dNFcyWvxk
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: a8b1c240-f315-46e3-b813-f545c4279dd1id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: fa6ac035-8403-478b-9ce1-3fe29d211fca
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 459
ht-degree: 88%

---

# Erstellen von Projekten {#create-projects}


Mit [Projekten](/help/analysis-workspace/build-workspace-project/freeform-overview.md) in Analysis Workspace können Sie geschäftskritische Analysen erstellen und anzeigen.  Diese Analysen können für Stakeholderinnen und Stakeholder innerhalb oder außerhalb Ihrer Organisation freigegeben werden.

1. Wählen Sie in Customer Journey Analytics die Option **[!UICONTROL Workspace]** aus.

1. Wählen Sie im linken Bedienfeld die Option **[!UICONTROL Projekte]** und dann **[!UICONTROL Projekt erstellen]** aus.

1. Wählen Sie **Leeres Workspace-Projekt** aus, um Ihr Workspace-Projekt mit einem Browser zu erstellen.

   Weitere Informationen zum Erstellen eines mobilen Scorecard-Projekts, das per App mit anderen Stakeholderinnen und Stakeholdern geteilt werden kann, finden Sie unter [Leere mobile Scorecard](/help/mobile-app/curator.md). Außerdem gibt es unter [Geführte Analyse](/help/guided-analysis/overview.md) weitere Informationen zu den verschiedenen verfügbaren Optionen zum Erstellen geführter Analyseprojekte.

1. Wählen Sie [!UICONTROL **Erstellen**] aus.


Nachdem Sie nun ein leeres Workspace-Projekt erstellt haben, sollten Sie mit der Benutzeroberfläche von [Analysis Workspace](/help/analysis-workspace/home.md) vertraut sein. Wenn dem so ist, können Sie Ihr Projekt erstellen. Gehen Sie dazu wie folgt vor:

![Beispielprojekt](assets/example-project.png)

* Fügen Sie dem Projekt [Bedienfelder](/help/analysis-workspace/c-panels/panels.md) hinzu, Zum Beispiel das **[!DNL Example Panel]** ➊.

* Fügen Sie Ihren Bedienfeldern [Visualisierungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) hinzu, z. B.:
   * Visualisierung [Linie](/help/analysis-workspace/visualizations/line.md) **[!DNL Line Graph]** ➋
   * Visualisierung [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) **[!DNL Countries]** ➌
* Fügen Sie Ihren Visualisierungen [Komponenten](/help/components/overview.md) hinzu, z. B.:
   * [Dimension](/help/components/dimensions/overview.md) **[!DNL Store Country]** ➍
   * [Metrik](/help/components/apply-create-metrics.md) **[!DNL People]** ➎
   * [Berechnete Metrik](/help/components/calc-metrics/calc-metr-overview.md) **[!DNL Avg Order Value]** ➏
   * [Segment](/help/components/segments/seg-overview.md) **[!DNL Mobile App Sessions]** ➐
   * [Datumsbereich](/help/components/date-ranges/overview.md) **[!DNL Last Month]** ➑
   * [Anmerkung](/help/components/annotations/overview.md) **[!DNL Example]** ➒


## Projektinfo und Einstellungen {#project-info-settings}

>[!CONTEXTUALHELP]
>id="workspace_project_countrepeatinstances"
>title="Wiederholungsinstanzen zählen"
>abstract="Gibt an, ob wiederholte Instanzen in Berichten gezählt werden.<br/><br/>Hinweis: Diese Einstellung gilt nicht für Fluss- oder Fallout-Visualisierungen."

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="Wiederholungsinstanzen zählen"
>abstract="Gibt an, ob wiederholte Instanzen in Berichten gezählt werden.<br/>Hinweis: Diese Einstellung gilt nicht für Fluss- oder Fallout-Visualisierungen."


>[!CONTEXTUALHELP]
>id="workspace_project_commenting"
>title="Kommentieren zulassen"
>abstract="Wenn diese Option aktiviert ist, wird in der rechten Leiste des Projekts in Analysis Workspace ein Kommentarbereich verfügbar."


Die Projekteinstellungen enthalten auf der Projektebene befindliche Informationen über das derzeit aktive Projekt.

![Das Fenster „Projektinformationen und -einstellungen“](./assets/projectinfo.png)

Zu den Einstellungen gehören:

| Einstellung | Beschreibung |
|---|---|
| Projektname | Der Name des Projekts. Sie können auf den Namen doppelklicken, um ihn zu bearbeiten. |
| Besitzer | Name des Projektbesitzer. |
| Zuletzt geändert | Datum der letzten Änderung am Projekt. |
| Tags | Listet alle Tags auf, die auf ein Projekt angewendet werden, um die Kategorisierung zu erleichtern. |
| Beschreibung | Eine Beschreibung ist nützlich, um den Zweck eines Projekts zu verdeutlichen. Sie können auf die Beschreibung doppelklicken, um sie zu bearbeiten. |
| Wiederholungsinstanzen zählen | Diese Einstellung legt fest, ob Wiederholungsinstanzen in Berichten gezählt werden sollen. Hinweis: Diese Einstellung gilt nicht für Fluss- oder Fallout-Visualisierungen. |
| Anmerkungen anzeigen | Legen Sie fest, ob Anmerkungen für dieses Projekt angezeigt werden sollen. |
| [Projekt-Farbpalette](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Sie können die in Workspace verwendete Farbpalette für Kategorien ändern, indem Sie aus den vordefinierten Paletten wählen, die für die Farbenblindheit optimiert wurden, oder indem Sie eine benutzerdefinierte Palette angeben. Diese Funktion betrifft vieles in Workspace, einschließlich der meisten Visualisierungen. |
| [Dichte anzeigen](/help/analysis-workspace/build-workspace-project/view-density.md) | Mit dieser Option können Sie mehr Daten auf dem Bildschirm anzeigen, indem Sie den vertikalen Abstand des linken Bedienfelds, der Freiformtabellen und der Kohortentabellen reduzieren. |
| Kommentieren zulassen | Wenn diese Option aktiviert ist, wird in der rechten Leiste des Projekts in Analysis Workspace ein Kommentarbereich verfügbar. Weitere Informationen finden Sie unter [Hinzufügen und Verwalten von Kommentaren in Projekten](/help/analysis-workspace/build-workspace-project/comment-projects.md). |



