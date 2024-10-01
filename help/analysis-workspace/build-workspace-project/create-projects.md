---
description: Erfahren Sie, wie Sie ein Projekt in Analysis Workspace erstellen
title: Erstellen von Projekten
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
source-git-commit: 383fad799944f7405af6de1754aa2e0af83e2cab
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 40%

---

# Erstellen von Projekten

Mit [Projekten](/help/analysis-workspace/build-workspace-project/freeform-overview.md) in Analysis Workspace können Sie geschäftskritische Analysen erstellen und anzeigen.  Diese Analysen können für Interessengruppen innerhalb oder außerhalb Ihres Unternehmens freigegeben werden.

1. Wählen Sie unter Customer Journey Analytics die Option **[!UICONTROL Workspace]** aus.

1. Wählen Sie im linken Bereich **[!UICONTROL Projekte]** und dann **[!UICONTROL Projekt erstellen]**.

1. Wählen Sie **Leeres Workspace-Projekt** aus, um Ihr Workspace-Projekt mit einem Browser zu erstellen.

   Weitere Informationen zum Erstellen eines mobilen Scorecard-Projekts, das Sie mit einer Mobile App für andere Interessengruppen freigeben können, finden Sie unter [Leere mobile Scorecard](/help/mobile-app/curator.md) . Weitere Informationen zu den verschiedenen verfügbaren Optionen zum Erstellen Ihres geführten Analyseprojekts finden Sie unter [Geführte Analyse](/help/guided-analysis/overview.md) .

1. Wählen Sie [!UICONTROL **Erstellen**] aus.


Nachdem Sie jetzt ein leeres Workspace-Projekt erstellt haben, sollten Sie mit der Benutzeroberfläche von [Analysis Workspace](/help/analysis-workspace/home.md) vertraut sein. Danach können Sie Ihr Projekt erstellen. Gehen Sie dazu wie folgt vor:

![Beispielprojekt](assets/example-project.png)

* Fügen Sie [Bedienfelder](/help/analysis-workspace/c-panels/panels.md) zu Ihrem Projekt hinzu. Zum Beispiel der **[!DNL Example Panel]**-Befehl.

* Fügen Sie Ihren Bedienfeldern [Visualisierungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) hinzu. Zum Beispiel:
   * **[!DNL Line Graph]** ](/help/analysis-workspace/visualizations/line.md) Visualisierung der Linie[
   * **[!DNL Countries]** [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) visualisierung
* Fügen Sie Ihren Visualisierungen [Komponenten](/help/components/overview.md) hinzu. Zum Beispiel:
   * **[!DNL Store Country]** [dimension](/help/components/dimensions/overview.md) ➍
   * **[!DNL People]** [metric](/help/components/apply-create-metrics.md) ➎
   * **[!DNL Avg Order Value]** [berechnete Metrik](/help/components/calc-metrics/calc-metr-overview.md) ➏
   * **[!DNL Mobile App Sessions]** [filter](/help/components/filters/filters-overview.md) ➐
   * **[!DNL Last Month]** [Datumsbereich](/help/components/date-ranges/overview.md) ➑
   * **[!DNL Example]** [annotation](/help/components/annotations/overview.md) ➒


## Projektinfo und Einstellungen {#project-info-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_project_repeatinstances"
>title="Wiederholte Instanzen zählen"
>abstract="Diese Einstellung legt fest, ob wiederholte Instanzen in Berichten gezählt werden sollen.<br/>Hinweis: Diese Einstellung gilt nicht für Fluss- oder Trichteranalysen."

<!-- markdownlint-enable MD034 -->


Die Projekteinstellungen enthalten Informationen auf Projektebene zum derzeit aktiven Projekt.

![Das Fenster Projektinfo und Einstellungen.](./assets/projectinfo.png)

Zu den Einstellungen gehören:

| Einstellung | Beschreibung |
|---|---|
| Projektname | Der Name des Projekts. Sie können auf den Namen doppelklicken, um ihn zu bearbeiten. |
| Verantwortlicher | Name des Projektinhabers. |
| Zuletzt geändert | Das Datum, an dem die letzte Änderung an dem Projekt vorgenommen wurde. |
| Tags | Zeigt eine Liste aller Tags an, die auf ein Projekt angewendet wurden, um die Kategorisierung zu vereinfachen. |
| Beschreibung | Eine Beschreibung hilft, den Zweck eines Projekts anzugeben. Sie können auf die Beschreibung doppelklicken, um sie zu bearbeiten. |
| Wiederholte Instanzen zählen | Geben Sie an, ob Wiederholungsinstanzen in Berichten gezählt werden sollen. Hinweis: Diese Einstellung gilt nicht für Fluss- oder Fallout-Visualisierungen. |
| Anmerkungen anzeigen | Geben Sie an, ob Anmerkungen für dieses Projekt angezeigt werden sollen. |
| [Projekt-Farbpalette](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Sie können die in Workspace verwendete Farbpalette für Kategorien ändern, indem Sie aus den vordefinierten Paletten wählen, die für die Farbenblindheit optimiert wurden, oder indem Sie eine benutzerdefinierte Palette angeben. Diese Funktion betrifft vieles in Workspace, einschließlich der meisten Visualisierungen. |
| [Dichte anzeigen](/help/analysis-workspace/build-workspace-project/view-density.md) | Ermöglicht die Anzeige weiterer Daten auf dem Bildschirm durch Reduzierung des vertikalen Abstands des linken Bedienfelds, der Freiformtabellen und der Kohortentabellen. |



