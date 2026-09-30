---
description: Erfahren Sie, wie Sie eine Freiformtabelle oder eine Datenquelle mit der entsprechenden Visualisierung synchronisieren.
keywords: Analysis Workspace;Synchronisieren der Visualisierung mit der Datenquelle
title: Data Sources verwalten
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
autotag-review: '2026-05-19T08:30:43.942Z'
TQID: 'https://experienceleague.adobe.com/UU1RlISeu-NOFAttolNcjV-p2EgtxBPFy3w7ZrLz-vY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 89%
---
# Verwalten von Datenquellen {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="Auswahl sperren"
>abstract="Aktivieren Sie diese Einstellung, um die Visualisierung an den ausgewählten Positionen oder den ausgewählten Elementen in der Datenquelle zu sperren."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="Tabelle anzeigen"
>abstract="Wenn Sie **[!UICONTROL Tabelle anzeigen]** auswählen, wird eine neue Datenquelle für Ihre aktuelle Visualisierung generiert, die von der ursprünglichen Datenquelle getrennt ist."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="Tabelle anzeigen"
>abstract="Wählen Sie **[!UICONTROL Tabelle anzeigen]** aus, um eine neue Datenquelle für Ihre aktuelle Visualisierung zu generieren, die von der ursprünglichen Datenquelle getrennt ist."

Durch das Synchronisieren von Visualisierungen können Sie steuern, welche Freiformtabelle oder Datenquelle einer Visualisierung entspricht.

>[!TIP]
>
>Die Farbe von ![StatusOrange](/help/assets/icons/StatusOrange.svg) neben dem Titel der Visualisierungen gibt an, welche Visualisierungen zusammenhängen. Übereinstimmende Farben besagen, dass Visualisierungen auf derselben Datenquelle basieren.
>

Sie können die Datenquelle ein- oder ausblenden. Sie können die Auswahl auch an ausgewählten Positionen oder ausgewählten Elementen sperren. Diese Einstellungen legen fest, ob sich die Visualisierung ändert (oder nicht ändert), sobald neue Daten eingehen.

![Das Dialogfeld mit der Option „Datenquelle“ mit den Optionen, die im nächsten Abschnitt beschrieben werden.](assets/lock-selection.png)


| Option | Beschreibung |
|--- |--- |
| **[!UICONTROL Datenquelle]** | Wählen Sie aus dem Dropdown-Menü die Datenquelle aus, auf der die Visualisierung basiert. |
| **[!UICONTROL Verknüpfte Visualisierungen]** | Listet alle verknüpften Visualisierungen auf. Gilt für die Datenquelle (Freiformtabelle). |
| **[!UICONTROL Datenquelle anzeigen]** | Ermöglicht das Ein- oder Ausblenden der Datenquelle (Freiformtabelle), die der Visualisierung entspricht. |
| **[!UICONTROL Auswahl sperren]** | Wählen Sie diese Option aus, damit die Visualisierung ![LockClosed](/help/assets/icons/LockClosed.svg) mit den aktuell in der entsprechenden Datentabelle ausgewählten Daten verknüpft bleibt. Wenn Sie die Option aktiviert haben, können Sie Folgendes auswählen:  <ul><li>**Ausgewählte Positionen**: Die Visualisierung ist für die **Positionen** gesperrt, die in der entsprechenden Datentabelle ausgewählt sind. Diese Positionen werden weiterhin visualisiert, auch wenn sich die spezifischen Elemente auf diesen Positionen ändern (z. B. durch Sortier- oder Filtervorgänge). Wählen Sie diese Option beispielsweise aus, wenn Sie die Top-5-Kampagnennamen, die in der Datenquelle aufgeführt sind, in dieser Visualisierung jederzeit anzeigen möchten. Egal, welche Kampagnennamen angezeigt werden.</li> <li>**Ausgewählte Elemente**: Die Visualisierung ist für die spezifischen **Elemente** gesperrt, die derzeit in der entsprechenden Datentabelle ausgewählt sind. Diese Elemente werden weiterhin visualisiert, selbst wenn sich ihre Rangfolge gegenüber anderen Elementen in der Tabelle ändert. Wählen Sie diese Option beispielsweise aus, wenn dieselben fünf spezifischen Kampagnennamen, die in der Datenquelle in dieser Visualisierung aufgeführt sind, jederzeit angezeigt werden sollen. Unabhängig vom Rang dieser Kampagnennamen.</li></ul>Wenn die Visualisierung für Daten gesperrt ist, die nicht mehr in der verknüpften Datentabelle sichtbar sind, können Sie eine neue Tabelle generieren. Wählen Sie **[!UICONTROL Tabelle anzeigen]** aus, um eine neue Datenquelle für Ihre aktuelle Visualisierung zu generieren, die von der ursprünglichen Datenquelle getrennt ist. |
