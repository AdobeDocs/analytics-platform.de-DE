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

- **Metrik**. So vergleichen Sie beispielsweise eine Dimension für zwei verschiedene Monate mit einer bestimmten Metrik.
- **Dimension**. So vergleichen Sie eine Metrik in verschiedenen Dimensionselementen für die Datumsbereichsdimension.

>[!NOTE]
>
>Wenn Sie Datumsbereiche in einer Freiformtabelle verwenden, überschreiben die Datumsbereiche den Kalender, der für das Bedienfeld angegeben ist, zu dem die Freiformtabelle gehört.
>

Sie verwenden einen Datumsbereich so, wie Sie [eine beliebige Komponente) ](/help/components/overview.md#analysis-workspace-components). Ziehen Sie den Datumsbereich aus dem Komponentenfeld ![Kalender](/help/assets/icons/Calendar.svg) **[!UICONTROL Datumsbereiche]** und legen Sie die Komponente ab:

- **[!UICONTROL Kalender]**: Sie ![Umschalten](/help/assets/icons/Switch.svg) **[!UICONTROL Ersetzen]** die aktuelle Kalenderkonfiguration durch den Datumsbereich.
- **Metrik-Spaltenüberschrift**: Sie ![Umschalten](/help/assets/icons/Switch.svg) **[!UICONTROL Ersetzen]** die Metrik, ![Hinzufügen](/help/assets/icons/Add.svg)**[!UICONTROL Hinzufügen ]**den Datumsbereich als Metrik oder ![Filter](/help/assets/icons/Filter.svg)**[!UICONTROL  Filter ]**die Metrik mithilfe der Datumsbereichskomponente.
- **Spaltenüberschrift der Dimension**: Sie ![Umschalten](/help/assets/icons/Switch.svg) **[!UICONTROL Ersetzen]** die aktuellen Dimensionen. Die neue Dimension lautet jetzt **[!UICONTROL Datumsbereiche]**. Sobald es sich bei der Dimension um Datumsbereiche handelt, können ![Hinzufügen](/help/assets/icons/Add.svg)**[!UICONTROL Hinzufügen ]**zusätzliche Datumsbereiche als Dimensionselemente hinzufügen.
- Dimension **Dimensionselement**: Sie ![Aufschlüsselung](/help/assets/icons/Breakdown.svg)**[!UICONTROL Aufschlüsselung]** das spezifische Dimensionselement nach dem Datumsbereich.

Sie können einer Freiformtabellen-Visualisierung auch direkt eine Datumsbereichsspalte hinzufügen:

1. Wählen Sie in einer Metrikspalte aus dem Kontextmenü:

   - **[!UICONTROL Spalte für Zeitraum hinzufügen]**. Sie können zwischen vorgeschlagenen Optionen wählen, die auf dem aktuellen Kalender basieren, oder einen [benutzerdefinierten Datumsbereich“ ](#custom-date-ranges).
   - **[!UICONTROL Zeiträume vergleichen]**. Sie können zwischen einer vorgeschlagenen Option, die auf dem aktuellen Kalender basiert, und einem [benutzerdefinierten Datumsbereich“ ](#custom-date-ranges).

1. Je nach Ihrer Auswahl werden der Freiformtabelle zusätzliche Datumsbereichsspalten hinzugefügt.

## Standardmäßige Datumsbereiche

Analysis Workspace bietet eine Reihe von standardmäßigen Datumsbereichen.


| Tag | Woche | Monat | Quartal | Jahr |
|---|---|---|---|---|
| Am aktuellen Tag | Diese Woche | Diesen Monat | Dieses Quartal | Dieses Jahr |
| Am Vortag | Diese Woche (ohne heute) | Dieser Monat (ohne heute) | Dieses Quartal (ohne heute) | Dieses Jahr (ohne heute) |
| vor 2 Tagen | Vor 2 Wochen | vor 2 Monaten |   |  |
| vor 3 Tagen | Vor 3 Wochen | vor 3 Monaten |  | |
| Letzte 7 Tage | Letzte Woche | Letzter Monat | Letztes Quartal | Letztes Jahr |
| Letzte 14 Tage | Letzte 2 volle Wochen | Letzte 2 volle Monate | Letzte 4 volle Quartale | |
| Letzte 30 Tage | Letzte 3 volle Wochen | Letzte 3 Monate | | |
| Letzte 60 Tage | Letzte 4 volle Wochen | Letzte 6 Monate | | |
| Letzte 90 Tage | Letzte 12 volle Wochen | Letzte 12 Monate | | |
| Letzte 7 volle Tage | Letzte 52 volle Wochen | Letzte 13 Monate | | |
| Letzte 14 volle Tage | | | | |
| Letzte 30 volle Tage | | | | |
| Letzte 90 volle Tage | | | | |

<table style="table-layout:fixed">

## Benutzerdefinierte Datumsbereiche

Sie können auch eigene benutzerdefinierte Datumsbereiche erstellen. Siehe [Datumsbereich erstellen](/help/components/date-ranges/create.md) für die verschiedenen verfügbaren Optionen zum Erstellen von Datumsbereichen. Anschließend erstellen, ändern und speichern Sie Datumsbereiche im [Datumsbereichsersteller](create.md#date-range-builder).

Sie verwenden den [Datumsbereichsmanager](manage.md) um Datumsbereiche zu verwalten.
