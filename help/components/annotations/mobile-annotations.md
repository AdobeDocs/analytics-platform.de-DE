---
title: Anmerkungen zu mobilen Scorecards
description: Erfahren Sie, wie Sie Anmerkungen in mobilen Scorecards einblenden können.
solution: Customer Journey Analytics
feature: Components
exl-id: c0f276b4-3514-4f93-8b6c-6896eb4da6e4
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 100%

---


# Freigeben von Anmerkungen in mobilen Scorecards

Sie können in Workspace erstellte Anmerkungen in mobilen Scorecards anzeigen. Auf diese Weise können Sie kontextbezogene Datennuancen und Erkenntnisse zu Ihrer Organisation und Ihren Kampagnen direkt in Projekten mit mobiler Scorecard, die in der Dashboard-Mobile-App von Analytics angezeigt werden.

## Einblenden von Anmerkungen in mobilen Scorecards

Um Anmerkungen in mobilen Scorecards einzublenden, erstellen Sie die Anmerkung zuerst aus Workspace-Projekten oder aus dem Menü „Komponenten“.

Informationen zum Erstellen von Anmerkungen finden Sie unter [Erstellen von Anmerkungen](create-annotations.md). Anmerkungen sind standardmäßig in mobilen Scorecards deaktiviert und müssen für jede Scorecard aktiviert sein, für die Sie sie in mobilen Scorecards verwenden möchten.

1. Aktivieren Sie Anmerkungen. Informationen zum Aktivieren von Anmerkungen finden Sie unter [Aktivieren oder Deaktivieren von Anmerkungen](overview.md#annotations-on-off).

1. Erstellen Sie eine Anmerkung und stellen Sie sicher, dass sie für alle Ihre Projekte freigegeben ist. Informationen zum Erstellen einer Anmerkung in Workspace finden Sie unter [Erstellen von Anmerkungen](create-annotations.md).

1. Wählen Sie **[!UICONTROL Anmerkungen anzeigen]**, um die Anmerkung in mobilen Scorecards anzuzeigen.

   ![Optionen für mobile Anmerkungen für Scorecards.](assets/show-annotations.png)

1. Um sicherzustellen, dass die Option „Anmerkungen anzeigen“ ausgewählt ist, gehen Sie zu **[!UICONTROL Projekt]** > **[!UICONTROL Projektinformationen und Einstellungen]**.

   ![Optionen für mobile Anmerkungen für Projektinformationen und Einstellungen, wobei die Option „Anmerkungen anzeigen“ hervorgehoben ist.](assets/project-info-settings.png)

## Anzeigen von Anmerkungen in mobilen Scorecards

Wenn Anmerkungen aktiviert sind, werden in Scorecard Builder Anmerkungssymbole angezeigt. Anmerkungen werden nur in Diagrammen und Tabellen in der Detailansicht angezeigt. in der Ansicht der Hauptkachel der Scorecard sind Anmerkungen nicht sichtbar.

![Scorecard Builder, wobei die Anmerkungssymbole hervorgehoben sind.](assets/view-annotations.png)

Wenn Anmerkungssymbole sichtbar sind, können Sie Anmerkungen auf der Arbeitsfläche des Builders nicht vollständig anzeigen oder damit interagieren. Verwenden Sie den Vorschaumodus, um Anmerkungen so anzuzeigen und zu bearbeiten, wie sie in der App angezeigt werden. ![Vorschausymbol](assets/preview-icon.png)

Es werden Anmerkungsfarben ausgewählt, wenn die Anmerkung in Workspace erstellt wird. Graue Anmerkungen weisen auf das Vorhandensein von mehr als einer Anmerkung hin. ![Anmerkungssymbole](assets/gray-annotations1.png) ![Mobile Scorecard mit hervorgehobenem Anmerkungssymbol.](assets/gray-annotations2.png)

## Anzeigen von Diagrammanmerkungen

| Datum | Erscheinungsbild |
| --- | --- |
| **[!UICONTROL Einzeltag]** | ![](assets/single-day-mobile-annotations.png)<br></br> |
| **[!UICONTROL Datumsbereich]** | ![](assets/date-range.png) |
| **[!UICONTROL Überlappende Anmerkungen]** | ![](assets/overlapping-annotations.png)<br></br>Um Anmerkungsdetails in der Analytics-Dashboards-App anzuzeigen, tippen Sie auf ein Anmerkungssymbol. <br></br>Wenn Sie eine Anmerkung in einem Diagramm anzeigen, können Sie nach links und rechts wischen, um durch alle im Diagramm vorhandenen Anmerkungen zu navigieren. Wischen Sie beim Anzeigen einer Anmerkung in der Tabelle nach links und rechts, um durch alle Anmerkungen zu navigieren, die mit diesem Zeilenelement in der Tabelle verknüpft sind. <br></br>![](assets/swipe-multiple-annotations.png) <br></br>In Diagrammen ohne zeitbasierte *x-Achse*, wie z. B. Ringdiagrammen oder horizontalen Balkendiagrammen, können Anmerkungen, die für das Diagramm gelten, durch Tippen auf das Symbol unten rechts angezeigt werden.<br></br> ![](assets/charts-without-timebase.png) |
