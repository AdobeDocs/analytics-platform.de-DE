---
description: Beim Synchronisieren von Visualisierungen können Sie kontrollieren, welche Datentabelle oder Datenquelle zu einer Visualisierung gehört.
keywords: Analysis Workspace;Synchronisieren der Visualisierung mit der Datenquelle
title: Datenquellen verwalten
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 27%

---

# Verwalten von Datenquellen {#manage-data-sources}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="Auswahl sperren"
>abstract="Aktivieren Sie diese Einstellung, um die Visualisierung an den ausgewählten Positionen oder den ausgewählten Elementen in der Datenquelle zu sperren."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="Tabelle anzeigen"
>abstract="Wenn Sie **[!UICONTROL Tabelle anzeigen]** auswählen, wird eine neue Datenquelle für Ihre aktuelle Visualisierung generiert, die von der ursprünglichen Datenquelle getrennt ist."

<!-- markdownlint-enable MD034 -->



Beim Synchronisieren von Visualisierungen können Sie kontrollieren, welche Datentabelle oder Datenquelle zu einer Visualisierung gehört.

>[!TIP]
>
>Welche Visualisierungen miteinander verbunden sind, können Sie an der Farbe ![StatusOrange](/help/assets/icons/StatusOrange.svg) neben dem Titel der Visualisierungen erkennen. Übereinstimmende Farben besagen, dass Visualisierungen auf derselben Datenquelle basieren.
>

Sie können die Datenquelle ein- oder ausblenden. Sie können die Auswahl auch an ausgewählten Positionen oder ausgewählten Elementen sperren. Diese Einstellungen legen fest, ob sich die Visualisierung ändert (oder nicht ändert), sobald neue Daten eingehen.

![Das Dialogfeld mit der Data Source-Option mit den Optionen, die im nächsten Abschnitt beschrieben werden.](assets/lock-selection.png)


| Option | Beschreibung |
|--- |--- |
| **[!UICONTROL Datenquelle]** | Wählen Sie aus dem Dropdown-Menü die Datenquelle aus, auf der die Visualisierung basiert. |
| **[!UICONTROL Verknüpfte Visualisierungen]** | Listet alle verknüpften Visualisierungen auf. Gilt für die Datenquelle (Freiformtabelle). |
| **[!UICONTROL Datenquelle anzeigen]** | Ermöglicht das Ein- oder Ausblenden der Datenquelle (Freiformtabelle), die der Visualisierung entspricht. |
| **[!UICONTROL Auswahl sperren]** | Aktivieren Sie diese Option, um die Visualisierung ![lockClosed](/help/assets/icons/LockClosed.svg) für die Daten zu sperren, die derzeit in der entsprechenden Datentabelle ausgewählt sind. Nach der Aktivierung wählen Sie zwischen:  <ul><li>**Ausgewählte Positionen**: Die Visualisierung ist für die **Positionen** gesperrt, die in der entsprechenden Datentabelle ausgewählt sind. Diese Positionen werden weiterhin visualisiert, auch wenn sich die spezifischen Elemente in diesen Positionen ändern (z. B. durch Sortieren oder Filtern). Wählen Sie diese Option beispielsweise aus, wenn Sie die fünf häufigsten Kampagnennamen, die in der Datenquelle in dieser Visualisierung aufgeführt sind, jederzeit anzeigen möchten. Egal, welche Kampagnennamen angezeigt werden.</li> <li>**Ausgewählte Elemente**: Die Visualisierung ist für die spezifischen **Elemente** gesperrt, die derzeit in der entsprechenden Datentabelle ausgewählt sind. Diese Elemente werden weiterhin visualisiert, auch wenn sie ihr Ranking unter den Elementen in der Tabelle ändern. Wählen Sie diese Option beispielsweise aus, wenn Sie jederzeit dieselben fünf spezifischen Kampagnennamen anzeigen möchten, die in der Datenquelle in dieser Visualisierung aufgeführt sind. Egal, wie diese Kampagnennamen rangieren.</li></ul>Wenn die Visualisierung für Daten gesperrt ist, die nicht mehr in der verbundenen Datentabelle sichtbar sind, können Sie eine neue Tabelle erstellen. Wählen Sie **[!UICONTROL Tabelle anzeigen]**, um eine neue Datenquelle für Ihre aktuelle Visualisierung zu generieren, die von der ursprünglichen Datenquelle getrennt ist. |
