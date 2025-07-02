---
title: Verwalten von Anmerkungen
description: Verwalten von Anmerkungen in Analysis Workspace.
feature: Components
exl-id: 12f2cc2f-477c-4f16-afdd-b0db84725b32
role: User
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 91%

---

# Verwalten von Anmerkungen

Sie können Anmerkungen in einer zentralen Verwaltungsoberfläche für [!UICONTROL Anmerkungen] freigeben, filtern, mit Tags versehen, genehmigen, kopieren, löschen und als Favoriten markieren. So verwalten Sie Anmerkungen:

* Wählen Sie in der Hauptbenutzeroberfläche die Option **[!UICONTROL Komponenten]** und dann **[!UICONTROL Anmerkungen]** aus.


>[!NOTE]
>
>Die Anmerkungen, die Sie in einem bestimmten Workspace-Projekt erstellen, werden nicht im [!UICONTROL Anmerkungs-Manager] angezeigt, es sei denn, Sie haben die Anmerkung für all Ihre Projekte verfügbar gemacht.
>

## Anmerkungs-Manager

Der Anmerkungs-Manager verfügt über die folgenden Benutzeroberflächenelemente:

![Benutzeroberfläche für Anmerkungen](assets/annotations-manager.png)

### Anmerkungsliste

Die ➊ der Anmerkungsliste zeigt alle Anmerkungen an, die Ihnen gehören, die Anmerkungen, die für alle Ihre Projekte gelten, und die Anmerkungen, die für Sie freigegeben wurden. Die Liste umfasst die folgenden Spalten:

| Spalte | Beschreibung |
| --- | --- | 
| ![UnausgefüllterStern](/help/assets/icons/StarOutline.svg) | Wählen Sie diese Option aus, um eine Anmerkung als Favoriten zu markieren ![Stern](/help/assets/icons/Star.svg) oder aus den Favoriten zu entfernen ![UnausgefüllterStern](/help/assets/icons/StarOutline.svg). |
| **[!UICONTROL Titel und Beschreibung]** | Werden durch den Anmerkungsgenerator bereitgestellt. Um den Titel und die Beschreibung zu bearbeiten, wählen Sie den Titel-Link aus. Dadurch wird das Dialogfeld [Anmerkungserstellung](/help/components/annotations/create-annotations.md#annotation-builder) geöffnet. Eine freigegebene Anmerkung wird mit dem Symbol ![Freigabe](/help/assets/icons/ShareAlt.svg) gekennzeichnet. |
| **[!UICONTROL Datenansicht]** | Die Datenansichten, für die diese Anmerkung gilt. |
| **[!UICONTROL Inhabende]** | Die Inhaberin oder der Inhaber der Anmerkung. Benutzende können nur die Anmerkungen sehen, die ihnen gehören oder die für sie freigegeben wurden. |
| **[!UICONTROL Angewendeter Datumsbereich]** | Das Datum oder der Datumsbereich, für das bzw. den diese Anmerkung gilt. |
| **[!UICONTROL Tags]** | Die Tags für diese Anmerkung. |
| **[!UICONTROL Freigegeben für]** | Die Einzelpersonen oder Gruppen, für die Sie die Anmerkung freigegeben haben. Wählen Sie diese Option aus, um das Dialogfeld **[!UICONTROL Komponente freigeben]** zu öffnen. |
| **[!UICONTROL Änderungsdatum]** | Wählen Sie diese Option aus, um das Datum und die Uhrzeit der letzten Änderung der Anmerkung anzuzeigen. |

{style="table-layout:auto"}

Verwenden Sie ![Spalteneinstellung](/help/assets/icons/ColumnSetting.svg), um die anzuzeigenden Spalten anzugeben.

### Aktionsleiste

Sie können Aktionen für Anmerkungen mithilfe der Aktionsleiste ➋. Die Aktionsleiste ermöglicht die folgenden Aktionen:

| Symbol | Aktion | Beschreibung |
|:--:|---|---|
| ![Hinzufügen](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Hinzufügen]** | Verwenden Sie das Dialogfeld [Anmerkungserstellung](create-annotations.md#annotation-builder), um eine weitere Anmerkung hinzuzufügen. |
| ![Durchsuchen](/help/assets/icons/Search.svg) | [!UICONTROL *Nach Titel suchen*] | Wenn in der Liste keine Anmerkung ausgewählt ist, suchen Sie mithilfe dieses Suchfelds nach Anmerkungen. |
| ![Beschriftung](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Versehen Sie die ausgewählten Anmerkungen mit Tags. Wählen Sie im Dialogfeld **[!UICONTROL Tag-Komponente]** die Tags für die ausgewählten Anmerkungen aus oder ab. Wählen Sie **[!UICONTROL Speichern]** aus, um die Tags für die ausgewählten Anmerkungen zu speichern. |
| ![Freigeben](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Freigeben]** | Geben Sie die ausgewählten Anmerkungen frei. Im Dialogfeld **[!UICONTROL Komponente freigeben]** können Sie *Einzelpersonen oder Gruppen suchen* ![Suchen](/help/assets/icons/Search.svg) oder die Option **[!UICONTROL Organisation]** oder **[!UICONTROL Gruppen]** auswählen. Wählen Sie **[!UICONTROL Speichern]** aus, um Freigabedetails für die ausgewählten Anmerkungen zu speichern. Weitere Informationen finden Sie unter [Freigeben von Anmerkungen](#share-annotations). |
| ![Löschen](/help/assets/icons/Delete.svg) | **[!UICONTROL Löschen]** | Löschen Sie die ausgewählten Anmerkungen. Sie werden zur Bestätigung aufgefordert. |
| ![Bearbeiten](/help/assets/icons/Edit.svg) | **[!UICONTROL Umbenennen]** | Benennen Sie eine einzelne ausgewählte Anmerkung um. Wenn diese Option aktiviert ist, ist eine Inline-Umbenennung der Anmerkung möglich. |
| ![Kopieren](/help/assets/icons/Copy.svg) | **[!UICONTROL Kopieren]** | Kopieren Sie die ausgewählten Anmerkungen. Neue Anmerkungen werden mit demselben Namen und Suffix erstellt (Kopie). |
| ![CSV-Datei](/help/assets/icons/FileCSV.svg) | **[!UICONTROL In CSV exportieren]** | Exportieren Sie die Anmerkungen in eine Datei namens `Annotations List.csv`. |

### Aktive Filterleiste

Die Filterleiste zeigt ➌ die aktiven Filter an (falls vorhanden). Mit ![XGröße75](/help/assets/icons/CrossSize75.svg) können Sie schnell einen Filter entfernen. Wenn mehr als ein Filter angegeben ist, können Sie alle Filter mit **[!UICONTROL Alle entfernen]** entfernen.

### Panel „Filter“

Sie können Anmerkungen mithilfe der **[!UICONTROL im linken Bedienfeld]** Filter➍ filtern. Im Bedienfeld „Filter“ werden der Filtertyp und die Anzahl der Anmerkungen angezeigt, auf die gefiltert wurde. Wählen Sie ![Filter](/help/assets/icons/Filter.svg) aus, um die Anzeige des Bedienfelds „Filter“ umzuschalten.

So filtern Sie die Filterliste:

1. Wählen Sie ![Filter](/help/assets/icons/Filter.svg) aus, um das Bedienfeld „Filter“ zu öffnen. Wenn Sie mehr Platz für die Filterliste benötigen, können Sie ![Filter](/help/assets/icons/Filter.svg) erneut auswählen, um das Bedienfeld zu schließen.
1. Sie können die Anmerkungen mit einem der verfügbaren [Filterabschnitte](#filter-sections) filtern.

   >[!INFO]
   >
   >*Elemente* beziehen sich auf die Anmerkungselemente, die in der [Anmerkungsliste](manage-annotations.md#annotations-list) angezeigt werden.
   > 

#### Filterabschnitte

{{tagfiltersection}}
{{dataviewfiltersection}}
{{ownerfiltersection}}
{{daterangefiltersection}}
{{otherfiltersfiltersection}}


Die [Anmerkungsliste](manage-annotations.md#annotations-list) wird basierend auf Ihrer Filterkonfiguration automatisch aktualisiert. Die konfigurierten Filter werden in der [aktiven Filterleiste](manage-annotations.md#active-filter-bar) angezeigt.


## Bearbeiten von Anmerkungen

Anmerkungen können auf zwei Arten bearbeitet werden:

* Verwenden Sie in einem Workspace-Projekt das Symbol [Komponenteninformationen](/help/components/use-components-in-workspace.md#component-info) aus.

* Klicken Sie in der [[!UICONTROL Anmerkungsliste]](#annotations-list) auf den Titel der Anmerkung.

Um die Anmerkung zu bearbeiten, verwenden Sie das Dialogfeld [Anmerkungserstellung](/help/components/annotations/create-annotations.md#annotation-builder).

## Freigeben von Anmerkungen

Folgendes gilt beim Freigeben von Anmerkungen oder Arbeiten mit Anmerkungen, die für Sie freigegeben wurden:

* Reine projektbezogene Anmerkungen in einem Projekt, die Sie für andere Benutzende freigeben, werden nur für diese Benutzenden angezeigt. Die Benutzenden können diese Anmerkungen, die nur für das Projekt gelten, nicht bearbeiten oder löschen.
* Wenn Sie eine Anmerkung speichern und sie direkt für eine Person freigeben, kann diese Person die Anmerkung nur bearbeiten und löschen, wenn sie über Administratorrechte verfügt.

* Wenn ein Projekt für Sie freigegeben wird, werden die in diesem Projekt erstellten Anmerkungen nur in diesem Projekt angezeigt. Wenn eine Anmerkung direkt für Sie freigegeben wird, wird sie in allen Projekten angezeigt, in denen diese Anmerkung angezeigt werden kann.

## Anmerkungen und Zeitzonen

Alle Anmerkungen werden mit einem Zeitstempel erstellt, jedoch ohne Stunden- oder Zeitzoneninformationen. Zum Zeitpunkt der Berichterstellung wird immer die Zeitzone der für das Panel konfigurierten Datenansicht angewendet. 
