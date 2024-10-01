---
description: Beim Synchronisieren von Visualisierungen können Sie kontrollieren, welche Datentabelle oder Datenquelle zu einer Visualisierung gehört.
keywords: Analysis Workspace;Synchronisieren der Visualisierung mit der Datenquelle
title: Datenquellen verwalten
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
source-git-commit: 388e008f4ee092dd8224bfacd020cdf762d4fb82
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 17%

---

# Datenquellen verwalten {#manage-data-sources}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_freeformtable_lockselection"
>title="Auswahl sperren"
>abstract="Aktivieren Sie diese Einstellung, um die Visualisierung an den ausgewählten Positionen oder den ausgewählten Elementen in der Datenquelle zu sperren."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_freeformtable_lockselection_showtable"
>title="Tabelle anzeigen"
>abstract="Wenn Sie **[!UICONTROL Tabelle anzeigen]** auswählen, wird eine neue Datenquelle für Ihre aktuelle Visualisierung generiert, die von der ursprünglichen Datenquelle getrennt ist."

<!-- markdownlint-enable MD034 -->



Beim Synchronisieren von Visualisierungen können Sie kontrollieren, welche Datentabelle oder Datenquelle zu einer Visualisierung gehört.

>[!TIP]
>
>Sie können erkennen, welche Visualisierungen sich auf die Farbe von ![StatusOrange](/help/assets/icons/StatusOrange.svg) neben dem Titel der Visualisierungen beziehen. Übereinstimmende Farben besagen, dass Visualisierungen auf derselben Datenquelle basieren.
>

Sie können die Datenquelle ein- oder ausblenden. Sie können die Auswahl auch an ausgewählten Positionen oder Elementen sperren. Diese Einstellungen legen fest, ob sich die Visualisierung ändert (oder nicht ändert), sobald neue Daten eingehen.

![Das Dialogfeld für die Option &quot;Data Source&quot;mit den im nächsten Abschnitt beschriebenen Optionen.](assets/lock-selection.png)


| Option | Beschreibung |
|--- |--- |
| **[!UICONTROL Datenquelle]** | Wählen Sie im Dropdown-Menü die Datenquelle aus, auf der die Visualisierung basiert. |
| **[!UICONTROL Verknüpfte Visualisierungen]** | Listet alle verknüpften Visualisierungen auf. Gilt für die Datenquelle (Freiformtabelle). |
| **[!UICONTROL Datenquelle anzeigen]** | Ermöglicht das Anzeigen oder Verbergen der Datenquelle (Freiformtabelle), die der Visualisierung entspricht. |
| **[!UICONTROL Auswahl sperren]** | Aktivieren Sie diese Option, um die Visualisierung ![LockClosed](/help/assets/icons/LockClosed.svg) mit den aktuell in der entsprechenden Datentabelle ausgewählten Daten zu sperren. Wählen Sie nach der Aktivierung zwischen:  <ul><li>**Ausgewählte Positionen**: Die Visualisierung wird auf den in der entsprechenden Datentabelle ausgewählten **Positionen** gesperrt. Diese Positionen werden weiterhin visualisiert, auch wenn sich die Elemente an diesen Positionen ändern (z. B. aufgrund von Sortierung oder Filterung). Wählen Sie diese Option beispielsweise aus, wenn Sie die fünf Kampagnennamen, die in der Datenquelle in dieser Visualisierung am häufigsten aufgeführt sind, jederzeit anzeigen möchten. Unabhängig davon, welche Kampagnennamen angezeigt werden.</li> <li>**Ausgewählte Elemente**: Die Visualisierung ist für die spezifischen **Elemente** gesperrt, die derzeit in der entsprechenden Datentabelle ausgewählt sind. Diese Elemente werden weiterhin visualisiert, auch wenn sie ihren Rang unter den Elementen in der Tabelle ändern. Wählen Sie diese Option beispielsweise aus, wenn Sie immer dieselben fünf Kampagnennamen anzeigen möchten, die in der Datenquelle in dieser Visualisierung aufgeführt sind. Egal, wie diese Kampagnennamen ranken.</li></ul>Wenn die Visualisierung auf Daten beschränkt ist, die nicht mehr in der verbundenen Datentabelle sichtbar sind, können Sie eine neue Tabelle generieren. Wählen Sie **[!UICONTROL Tabelle anzeigen]** aus, um eine neue Datenquelle für Ihre aktuelle Visualisierung zu generieren, die von der ursprünglichen Datenquelle getrennt ist. |
