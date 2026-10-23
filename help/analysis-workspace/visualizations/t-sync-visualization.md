---
description: Erfahren Sie, wie Sie Visualisierungen mit einer Freiformtabellen-Datenquelle verknüpfen.
keywords: Analysis Workspace;Synchronisieren der Visualisierung mit der Datenquelle
title: Verwalten von Visualisierungsdatenquellen in Analysis Workspace
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
source-git-commit: f7d853a3b658328f952b675f838ce314b7c30fb1
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 18%
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

Jede Visualisierung in Analysis Workspace basiert auf einer Datenquelle, normalerweise einer Freiformtabelle. Durch das Synchronisieren von Visualisierungen können Sie steuern, welche Freiformtabelle oder Datenquelle einer Visualisierung entspricht und ob die Visualisierung für bestimmte Zeilen in dieser Tabelle gesperrt bleibt.

>[!TIP]
>
>Die Farbe von ![StatusOrange](/help/assets/icons/StatusOrange.svg) neben dem Titel der Visualisierungen gibt an, welche Visualisierungen zusammenhängen. Übereinstimmende Farben besagen, dass Visualisierungen auf derselben Datenquelle basieren.
>

## Datenquelleneinstellungen konfigurieren {#configure}

1. Wechseln Sie in Analysis Workspace zu der Visualisierung, deren Datenquelle oder Sperreinstellungen Sie konfigurieren möchten.

1. Bewegen Sie den Mauszeiger über die Visualisierung und wählen Sie dann das Symbol **[!UICONTROL Einstellungen]** (![) ](/help/assets/icons/Setting.svg).

1. Wählen Sie die **[!UICONTROL Datenquelle]** aus.

   ![Registerkarte „Datenquelle“ mit den Einstellungen für Datenquelle, verknüpfte Visualisierung und Sperrauswahl.](assets/lock-selection.png)

1. Konfigurieren Sie eine der folgenden Einstellungen:

   | Einstellung | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Datenquelle]** | Wählen Sie die Datenquelle aus, auf der die Visualisierung basiert. |
   | **[!UICONTROL Verknüpfte Visualisierungen]** | Listet alle mit der Datenquelle verknüpften Visualisierungen auf (Freiformtabelle). |
   | **[!UICONTROL Datenquelle zeigen]** | Ein- oder Ausblenden der Datenquelle (Freiformtabelle), die der Visualisierung entspricht. |
   | **[!UICONTROL Auswahl sperren]** | Sperren Sie die Visualisierung für die derzeit in der Datenquelle ausgewählten Zeilen und wählen Sie dann **[!UICONTROL Ausgewählte Positionen]** oder **[!UICONTROL Ausgewählte Elemente]** aus. Siehe [Auswahl sperren](#lock-selection). |

## Auswahl sperren {#lock-selection}

Durch das Sperren der Auswahl wird die Visualisierung weiterhin auf die Zeilen fokussiert, die Sie in der Datenquelle auswählen, auch wenn sich die Tabelle ändert. Beispielsweise ändert sich die Tabelle, wenn Sie sie sortieren oder filtern, ihren Datumsbereich ändern oder ein Segment anwenden. Eine gesperrte Visualisierung zeigt ![LockClosed](/help/assets/icons/LockClosed.svg) neben dem Titel an.

Wenn sich die Segmente, Dimensionen oder Metriken in der Datenquelle ändern und die gesperrten Daten nicht mehr sichtbar sind, wählen Sie **[!UICONTROL Tabelle anzeigen]** aus, um eine neue, von der ursprünglichen Datenquelle getrennte Datenquelle für die Visualisierung zu generieren.

Wenn Sie die Auswahl sperren, wählen Sie eine der folgenden Optionen:

| Option | Beschreibung |
| --- | --- |
| **[!UICONTROL Ausgewählte Positionen]** | Sperrt die Visualisierung für die **Positionen** der in der Datenquelle ausgewählten Zeilen. Diese Positionen werden weiterhin visualisiert, auch wenn sich die Elemente in ihnen ändern. Wählen Sie beispielsweise diese Option aus, um immer die fünf häufigsten Kampagnennamen in der Datenquelle anzuzeigen, unabhängig davon, welche Kampagnen es sind.<br><br>Wenn Sie Aufschlüsselungszeilen sperren und diese Zeilen nicht mehr in der Tabelle enthalten sind, wird die Visualisierung nicht angezeigt. Um sie erneut anzuzeigen, aktualisieren Sie die Tabelle (z. B. ihr Datumsbereich, ihre Segmente oder Filter) oder aktualisieren Sie die Sperrauswahl. |
| **[!UICONTROL Ausgewählte Elemente]** | Sperrt die Visualisierung für die spezifischen **Elemente** die in der Datenquelle ausgewählt sind. Diese Elemente werden weiterhin visualisiert, auch wenn sich ihr Rang in der Tabelle ändert. Wählen Sie beispielsweise diese Option aus, um immer dieselben fünf Kampagnennamen anzuzeigen, unabhängig davon, welchen Rang sie einnehmen. |
