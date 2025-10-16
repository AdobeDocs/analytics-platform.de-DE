---
description: Verwenden Sie den Kalender und die Datenbereiche, um Datumsbereiche in Analysis Workspace anzugeben.
title: Datumsbereiche – Überblick
feature: Calendar
exl-id: 99b31bd9-32f1-4da1-9e47-6d90c66282c5
role: User
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 100%

---

# Übersicht über Datumsbereiche

In einem Workspace-Projekt verwenden Sie normalerweise den [Kalender in einem Panel](/help/analysis-workspace/c-panels/panels.md#calendar), um den Datumsbereich für die Visualisierungen in diesem Panel anzugeben.

Mit Datumsbereichskomponenten können Sie die Kalendereinstellungen für das Panel definieren und überschreiben.

<!-- Very old video, should we show it?

+++ View a video illustrating use of calendar and date ranges

>[!VIDEO](https://video.tv.adobe.com/v/327347?captions=ger&format=jpeg)

{{videoaa}}
+++

-->

## Verwenden von Datumsbereichen

Sie können eine Datumsbereichskomponente verwenden, um den Kalender für das Panel neu zu definieren.

Sie können auch einen Datumsbereich in einer Freiformtabelle als Metrik oder Dimension verwenden.

![Nutzung von Datumsbereich](/help/components/date-ranges/assets/date-ranges-usage.png)

- **Metrik**. Sie können beispielsweise eine Dimension für zwei verschiedene Monate einer Metrik vergleichen.
- **Dimension**. So vergleichen Sie eine Metrik zu verschiedenen Dimensionselementen für die Dimension Datumsbereich.

>[!NOTE]
>
>Wenn Sie Datumsbereiche in einer Freiformtabelle verwenden, überschreiben die Datumsbereiche den Kalender, der für das Panel angegeben ist, zu dem die Freiformtabelle gehört.
>

Sie verwenden einen Datumsbereich so wie Sie [eine beliebige Komponente verwenden würden](/help/components/overview.md#analysis-workspace-components). Sie ziehen den Datumsbereich aus dem Komponenten-Panel ![Kalender](/help/assets/icons/Calendar.svg) **[!UICONTROL Datumsbereiche]** und legen Sie die Komponente hier ab:

- **[!UICONTROL Kalender]**: Sie ![Wechseln](/help/assets/icons/Switch.svg) **[!UICONTROL Ersetzen]** die aktuelle Kalenderkonfiguration durch den Datumsbereich.
- **Spaltenkopf Metrik**: Sie ![Switch](/help/assets/icons/Switch.svg) **[!UICONTROL ersetzen]** die Metrik, ![Add](/help/assets/icons/Add.svg)**[!UICONTROL fügen ]**den Datumsbereich als Metrik hinzu oder ![Filter](/help/assets/icons/Filter.svg)**[!UICONTROL  filtern ]**die Metrik mit der Komponente Datumsbereich.
- **Spaltenkopf Dimension**: Sie ![Wechseln](/help/assets/icons/Switch.svg) **[!UICONTROL ersetzen]** die aktuellen Dimensionen. Die neue Dimension lautet jetzt **[!UICONTROL Datumsbereiche]**. Sobald die Dimension Datumsbereiche lautet, können Sie zusätzliche Datumsbereiche als Dimensionselemente ![Hinzufügen](/help/assets/icons/Add.svg)**[!UICONTROL hinzufügen ]**.
- **Dimensionselement**: Sie ![Aufschlüsselung](/help/assets/icons/Breakdown.svg) **[!UICONTROL schlüsseln]** das spezifische Dimensionselement nach Datumsbereich auf.

Sie können eine Spalte für Datumsbereich auch direkt in einer Visualisierung „Freiformtabelle“ hinzufügen:

1. Wählen Sie in einer Spalte für Metrik aus dem Kontextmenü:

   - **[!UICONTROL Spalte für Zeitraum hinzufügen]**. Sie können zwischen vorgeschlagenen Optionen wählen, die auf dem aktuellen Kalender basieren, oder einen [benutzerdefinierten Datumsbereich](#custom-date-ranges) erstellen.
   - **[!UICONTROL Zeiträume vergleichen]**. Sie können zwischen einer vorgeschlagenen Option wählen, die auf dem aktuellen Kalender basiert, oder einen [benutzerdefinierten Datumsbereich](#custom-date-ranges) erstellen.

1. Entsprechend Ihrer Auswahl werden der Freiformtabelle zusätzliche Spalten für Datumsbereich hinzugefügt.

## Fehlgeschlagene Datumsbereiche

Analysis Workspace bietet eine Reihe von standardmäßigen Datumsbereichen.


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

Sie können eigene, benutzerdefinierte Datumsbereiche erstellen. Unter [Datumsbereich erstellen](/help/components/date-ranges/create.md) finden Sie die verschiedenen Optionen zum Erstellen von Datumsbereichen. Anschließend erstellen, ändern und speichern Sie Datumsbereiche im [Datumsbereichsgenerator](create.md#date-range-builder).

Sie verwenden die [Datumsbereichsverwaltung](manage.md), um Datumsbereiche zu verwalten.
