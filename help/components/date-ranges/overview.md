---
title: Übersicht über Datumsbereiche
description: Erfahren Sie, was Datumsbereiche sind und wie Sie sie für die Berichterstellung verwenden können.
feature: Calendar
exl-id: 99b31bd9-32f1-4da1-9e47-6d90c66282c5
role: User
source-git-commit: 747e77b964006404d70b500b28ec44005d65d944
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 21%

---

# Übersicht über Datumsbereiche

In einem Workspace-Projekt verwenden Sie normalerweise den [Kalender in einem Bedienfeld](/help/analysis-workspace/c-panels/panels.md#calendar), um den Datumsbereich für die Visualisierungen in diesem Bedienfeld anzugeben.

Mit Datumsbereichskomponenten können Sie die Kalendereinstellungen für das Bedienfeld definieren und überschreiben.

<!-- Very old video, should we show it?

+++ View a video illustrating use of calendar and date ranges

>[!VIDEO](https://video.tv.adobe.com/v/24136?format=jpeg)

{{videoaa}}
+++

-->

## Verwenden von Datumsbereichen

Sie können eine Datumsbereichskomponente verwenden, um den Kalender für das Bedienfeld neu zu definieren.

Sie können auch einen Datumsbereich in einer Freiformtabelle als Metrik oder Dimension verwenden.

![Verwendung des Datumsbereichs](/help/components/date-ranges/assets/date-ranges-usage.png)

- **Metrik**. So können Sie beispielsweise eine Dimension für zwei verschiedene Monate mit einer bestimmten Metrik vergleichen.
- **Dimension**. Zum Vergleich einer Metrik mit verschiedenen Dimensionselementen für die Datumsbereichsdimension.

>[!NOTE]
>
>Wenn Sie Datumsbereiche in einer Freiformtabelle verwenden, überschreiben die Datumsbereiche den Kalender, der für den Bereich angegeben ist, zu dem die Freiformtabelle gehört.
>

Sie verwenden einen Datumsbereich wie [eine beliebige Komponente](/help/components/overview.md#analysis-workspace-components). Sie ziehen den Datumsbereich aus dem Komponentenbereich ![Kalender](/help/assets/icons/Calendar.svg) **[!UICONTROL Datumsbereiche]** und legen die Komponente auf:

- **[!UICONTROL Kalender]**: Sie ![wechseln](/help/assets/icons/Switch.svg) **[!UICONTROL ersetzen]** die aktuelle Kalenderkonfiguration durch den Datumsbereich.
- **Metrik-Spaltenüberschrift**: Sie ![wechseln](/help/assets/icons/Switch.svg) **[!UICONTROL ersetzen]** die Metrik, ![fügen](/help/assets/icons/Add.svg)**[!UICONTROL den Datumsbereich als Metrik hinzu ]**oder ![Filter](/help/assets/icons/Filter.svg)**[!UICONTROL  Filtern ]**die Metrik mithilfe der Datumsbereichskomponente.
- **Spaltenüberschrift der Dimension**: Sie ![wechseln](/help/assets/icons/Switch.svg) **[!UICONTROL ersetzen]** die aktuellen Dimensionen. Die neue Dimension ist jetzt **[!UICONTROL Datumsbereiche]**. Sobald die Dimension Datumsbereiche ist, können Sie ![zusätzliche Datumsbereiche als Dimensionselemente hinzufügen](/help/assets/icons/Add.svg)**[!UICONTROL 2}.]**
- **Dimension item**: Sie ![Aufschlüsselung](/help/assets/icons/Breakdown.svg) **[!UICONTROL Aufschlüsselung]** des jeweiligen Dimensionselements nach Datumsbereich.

Sie können auch eine Datumsbereichsspalte direkt in einer Freiformtabellen-Visualisierung hinzufügen:

1. Wählen Sie in einer Metrikspalte aus dem Kontextmenü die Option:

   - **[!UICONTROL Spalte für den Zeitraum hinzufügen]**. Sie können zwischen vorgeschlagenen Optionen auswählen, die auf dem aktuellen Kalender basieren, oder einen [benutzerdefinierten Datumsbereich](#custom-date-ranges) erstellen.
   - **[!UICONTROL Zeiträume vergleichen]**. Sie können zwischen einer vorgeschlagenen Option wählen, die auf dem aktuellen Kalender basiert, oder einen [benutzerdefinierten Datumsbereich](#custom-date-ranges) erstellen.

1. Je nach Auswahl werden der Freiformtabelle zusätzliche Datumsbereichsspalten hinzugefügt.

## Standarddatumsbereiche

Analysis Workspace bietet eine Reihe von Standarddatumsbereichen.


| Tag | Woche | Monat | Quartal | Jahr |
|---|---|---|---|---|
| Am aktuellen Tag | Diese Woche | Diesen Monat | Dieses Quartal | Dieses Jahr |
| Am Vortag | Diese Woche (ohne heute) | Dieser Monat (ohne heute) | Dieses Quartal (ohne heute) | Dieses Jahr (ohne heute) |
| Vor 2 Tagen | Vor 2 Wochen | Vor 2 Monaten |   |  |
| Vor 3 Tagen | Vor 3 Wochen | Vor 3 Monaten |  | |
| Letzte 7 Tage | Letzte Woche | Letzter Monat | Letztes Quartal | Letztes Jahr |
| Letzte 14 Tage | Letzte 2 volle Wochen | Letzte 2 volle Monate | Letzte 4 volle Quartale | |
| Letzte 30 Tage | Letzte 3 volle Wochen | Letzte 3 volle Monate | | |
| Letzte 60 Tage | Letzte 4 volle Wochen | Letzte 6 volle Monate | | |
| Letzte 90 Tage | Letzte 12 volle Wochen | Letzte 12 volle Monate | | |
| Letzte 7 volle Tage | Letzte 52 volle Wochen | Letzte 13 volle Monate | | |
| Letzte 14 volle Tage | | | | |
| Letzte 30 volle Tage | | | | |
| Letzte 90 volle Tage | | | | |

<table style="table-layout:fixed">

## Benutzerdefinierte Datumsbereiche

Sie können eigene benutzerdefinierte Datumsbereiche erstellen. Unter [Datumsbereich erstellen](/help/components/date-ranges/create.md) finden Sie die verschiedenen Optionen zum Erstellen von Datumsbereichen. Anschließend erstellen, ändern und speichern Sie Datumsbereiche im [Generator für Datumsbereiche](create.md#date-range-builder).

Sie verwenden den [Datumsbereichsmanager](manage.md), um Datumsbereiche zu verwalten.
