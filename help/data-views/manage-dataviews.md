---
title: Datenansichten verwalten
description: Erfahren Sie, wie Sie Datenansichten verwalten.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: cb5baf2ec8d3ad4449a9b08d0a025a2d39a11425
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 11%

---


# Datenansichten verwalten


Nachdem Sie [eine oder mehrere Datenansichten erstellt oder bearbeitet haben](/help/data-views/create-dataview.md) können Sie sie in &quot;**[!UICONTROL &quot;]**.

Wählen **[!UICONTROL Daten-Management]** > **[!UICONTROL Datenansichten]** in der Hauptmenüleiste von Customer Journey Analytics aus.

Die **[!UICONTROL Datenansichten]** zeigt eine Tabelle aller verfügbaren Datenansichten an.

![Datenansichtsoberfläche](/help/data-views/assets/data-views.png)

Die folgenden Spalten und Symbole sind in der Tabelle verfügbar:

| Spalte oder Symbol | Beschreibung |
| --- | --- |
| **[!UICONTROL Name]** | Der Name der Datenansicht. |
| ![Information](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Um Informationen zur Datenansicht anzuzeigen, klicken Sie auf ![InfoOutline](/help/assets/icons/InfoOutline.svg) neben dem Namen der Datenansicht.<br/>Ein Popup-Fenster zeigt Details zur Datenansicht an. |
| ![Mehr](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Wählen Sie ![Mehr](/help/assets/icons/More.svg) aus, um ein Kontextmenü zu öffnen. Sie können Folgendes auswählen<br/>![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]**, um [ Datenansicht ](#edit-data-views) bearbeiten.<br/>![Kopieren](/help/assets/icons/Copy.svg) **[!UICONTROL Kopieren]**, um [eine Datenansicht zu kopieren](#copy-data-views).<br/>![Löschen](/help/assets/icons/Delete.svg) **[!UICONTROL Löschen]**, um [ Datenansicht ](#delete-data-views)löschen.<br/>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exportieren in CSV]**, um [die Details der Datenansicht in eine CSV-Datei zu exportieren](#export-data-views-to-csv).<br/>![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Create Project]**, um [ein neues Workspace-Projekt zu erstellen](#create-project-from-data-views) für die Datenansicht. |
| **[!UICONTROL Verbindung]** | Der Name der Verbindung, die der Datenansicht zugeordnet ist. |
| **[!UICONTROL Sandbox]** | Der Name der Sandbox, die der Datenansicht zugeordnet ist. |
| **[!UICONTROL Inhabende]** | Der Inhaber der Datenansicht. |
| **[!UICONTROL Data Insights Agent]** ![InfoOutline](/help/assets/icons/InfoOutline.svg) | Gibt an, ob die [Data Insights Agent](/help/data-analysis-ai.md) für die Datenansicht **[!UICONTROL aktiviert]** oder **[!UICONTROL deaktiviert]** ist. <br/>Wählen Sie ![InfoOutline](/help/assets/icons/InfoOutline.svg) aus, um ein Popup mit dem Status **[!UICONTROL Data Insights Agent]** in Ihren Datenansichten anzuzeigen. <br/>![Nutzung von Data Insights Agent](/help/data-views/assets/data-views-dia-status.png) |
| **[!UICONTROL Integrationen]** | Auflisten von Integrationen mit anderen Lösungen. Beispiel: Adobe Audience Analysis, Content Analytics, Brand Concierge, Journey Optimizer, GenStudio und Usage Analytics. |
| **[!UICONTROL In CJA verwenden]** | Geben Sie an, ob die Datenansicht in Customer Journey Analytics verwendet wird. Dieser Wert ist nur **[!UICONTROL Aus]** für Datenansichten, die automatisch im Rahmen der Adobe Journey Optimizer-Integration generiert werden. |
| **[!UICONTROL Erstellt am]** | Der Zeitstempel, zu dem die Datenansicht erstellt wurde. |
| **[!UICONTROL Zuletzt geändert]** | Der Zeitstempel, wann die Datenansicht zuletzt geändert wurde. |

Um zu konfigurieren, welche Spalten in der Tabelle angezeigt werden sollen, wählen Sie ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) aus. Wählen **[!UICONTROL Dialogfeld „Tabelle anpassen]** die anzuzeigenden Spalten aus. Wählen Sie dann **[!UICONTROL Übernehmen]** aus.


## Datenansichten suchen

Sie können mit dem Feld Suchen (Search) schnell ![ Datenansicht ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).

## Datenansichten filtern

Um einen Filter auf die Liste der Datenansichten anzuwenden, klicken Sie auf ![Filter](/help/assets/icons/Filter.svg)-Symbol und wählen Sie dann eine der folgenden Filteroptionen aus:

| Filteroption | Beschreibung |
|---------|----------|
| **[!UICONTROL Verbindungen]** | Es werden nur Datenansichten angezeigt, die mit den von Ihnen ausgewählten Verbindungen verknüpft sind. |
| **[!UICONTROL Inhabende]** | Es werden nur Datenansichten angezeigt, die den von Ihnen ausgewählten Personen gehören. |
| **[!UICONTROL Sandbox]** | Es werden nur Datenansichten angezeigt, die in den von Ihnen ausgewählten Sandboxes verfügbar sind. |
| **[!UICONTROL Integrationen]** | Es werden nur Datenansichten mit ausgewählten Integrationen angezeigt. |
| **[!UICONTROL In CJA verwenden]** | Wählen Sie **[!UICONTROL Ein]** aus, um nur Datenansichten anzuzeigen, die für die Verwendung mit Customer Journey Analytics aktiviert sind. Wählen Sie **[!UICONTROL Aus]**, um nur Datenansichten anzuzeigen, die noch nicht für die Verwendung mit Customer Journey Analytics aktiviert sind. |


## Erstellen einer Datenansicht

Um [neue Datenansicht zu erstellen](/help/data-views/create-dataview.md) wählen Sie **[!UICONTROL Neue Datenansicht erstellen]** aus.


## Datenansichten bearbeiten

Wenn Sie [eine Datenansicht bearbeiten](/help/data-views/create-dataview.md):

1. Klicken Sie ![Mehr](/help/assets/icons/More.svg) neben dem Namen der Datenansicht.
1. Wählen Sie im Kontextmenü die Option ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]** aus.

Sie können auch wie folgt vorgehen:

1. Wählen Sie die Datenansichtszeile aus.
1. Wählen Sie in der blauen Aktionsleiste die Option ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]** aus.


## Datenansichten kopieren

Wenn Sie eine Datenansicht kopieren möchten:

1. Klicken Sie ![Mehr](/help/assets/icons/More.svg) neben dem Namen der Datenansicht.
1. Wählen ![Kopieren](/help/assets/icons/Copy.svg) **[!UICONTROL Kopieren]** aus dem Kontextmenü aus.

Sie können auch wie folgt vorgehen:

1. Eine oder mehrere Datenansichtszeilen auswählen.
1. Wählen Sie ![Kopieren](/help/assets/icons/Copy.svg) **[!UICONTROL Kopieren]** in der blauen Aktionsleiste aus.

Die Datenansicht wird kopiert und der Liste hinzugefügt, wobei **[!UICONTROL (Kopieren)]** an den Namen angehängt wird.


## Löschen von Datenansichten

Wenn Sie eine Datenansicht löschen möchten:

1. Klicken Sie ![Mehr](/help/assets/icons/More.svg) neben dem Namen der Datenansicht.
1. Wählen Sie ![ Kontextmenü ](/help/assets/icons/Delete.svg)Löschen **[!UICONTROL Löschen]** aus.

Sie können auch wie folgt vorgehen:

1. Eine oder mehrere Datenansichtszeilen auswählen.
1. Wählen Sie in der blauen Aktionsleiste die Option ![Löschen](/help/assets/icons/Delete.svg) **[!UICONTROL Löschen]** aus.

Wenn Sie eine oder mehrere Datenansichten löschen, zeigt ein Bedienfeld **[!UICONTROL Datenansicht löschen]** an, welche Projekte betroffen sind.

![Datenansicht löschen](/help/data-views/assets/delete-data-view.png)


* In ➊ **[!UICONTROL Bestätigung]** werden die Auswirkungen des Löschens der Datenansichten angezeigt.
* Wählen Sie **[!UICONTROL Löschen]** aus, um die Datenansichten dauerhaft zu löschen. Wählen Sie zum Abbrechen **[!UICONTROL Abbrechen]** aus.


## Datenansichten in CSV exportieren

Sie können eine Datenansicht in eine CSV-Datei exportieren.

1. Klicken Sie ![Mehr](/help/assets/icons/More.svg) neben dem Namen der Datenansicht.
1. Wählen Sie ![DateiCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL In CSV exportieren]** aus dem Kontextmenü aus.

Sie können auch wie folgt vorgehen:

1. Eine oder mehrere Datenansichtszeilen auswählen.
1. Wählen Sie ![DateiCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exportieren in CSV]** aus der blauen Aktionsleiste aus.

Details der ausgewählten Datenansichten werden in eine CSV-Datei mit dem Namen `Data views List (x).csv` im Downloads-Ordner Ihres Browsers exportiert.


## Erstellen eines Projekts aus Datenansichten

Sie können ein Workspace-Projekt direkt über die Datenansichtsoberfläche erstellen.

1. Klicken Sie ![Mehr](/help/assets/icons/More.svg) neben dem Namen der Datenansicht.
1. Wählen ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Projekt erstellen]** aus dem Kontextmenü aus.

Sie können auch wie folgt vorgehen:

1. Datenansichtszeile auswählen.
1. Wählen Sie ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Projekt erstellen]** in der blauen Aktionsleiste aus.


## Aktivieren oder Deaktivieren von Datenansichten für Data Insights Agent

Sie können eine Datenansicht für die [Data Insights Agent aktivieren oder ](/help/data-analysis-ai.md).

1. Klicken Sie ![Mehr](/help/assets/icons/More.svg) neben dem Namen der Datenansicht.
1. Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Für Data Insights Agent aktivieren]** oder ![RemoveCircle](/help/assets/icons/RemoveCircle.svg)**[!UICONTROL Deaktivieren für Data Insights Agent]** aus dem Kontextmenü aus.

Sie können auch wie folgt vorgehen:

1. Wählen Sie eine oder mehrere Datenansichtszeilen aus, die für die Data Insights Agent entweder deaktiviert oder aktiviert sind.
1. Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Enable for Data Insights Agent]** oder ![RemoveCircle](/help/assets/icons/RemoveCircle.svg)**[!UICONTROL Disable for Data Insights Agent]** in der blauen Aktionsleiste aus.

