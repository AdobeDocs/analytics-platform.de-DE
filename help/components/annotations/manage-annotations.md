---
title: Verwalten von Anmerkungen
description: Verwalten von Anmerkungen in Workspace.
feature: Components
exl-id: 12f2cc2f-477c-4f16-afdd-b0db84725b32
role: User
source-git-commit: 6a279ac39e6b94200ff93ac1a3796d202e6349c7
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 8%

---

# Verwalten von Anmerkungen

Sie können Anmerkungen in einer zentralen Verwaltungsoberfläche von [!UICONTROL Anmerkungen] freigeben, filtern, taggen, genehmigen, kopieren, löschen und als Favoriten markieren. So verwalten Sie Anmerkungen:

* Wählen Sie **[!UICONTROL Komponenten]** in der Hauptbenutzeroberfläche und dann **[!UICONTROL Anmerkungen]** aus.


>[!NOTE]
>
>Die Anmerkungen, die Sie in einem bestimmten Workspace-Projekt erstellen, werden nicht im Manager [!UICONTROL Anmerkungen] angezeigt, es sei denn, Sie haben die Anmerkung für alle Ihre Projekte verfügbar gemacht.
>

## Anmerkungs-Manager

Der Anmerkungs-Manager verfügt über die folgenden Elemente der Benutzeroberfläche:

![ Benutzeroberfläche für Anmerkungen](assets/annotations-manager.png)

### Anmerkungsliste

In der Liste der Anmerkungen, die Sie besitzen, werden alle Anmerkungen, die für alle Ihre Projekte in den Gültigkeitsbereich fallen, sowie die für Sie freigegebenen Anmerkungen angezeigt. Die Liste enthält die folgenden Spalten:

| Spalte | Beschreibung |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Wählen Sie diese Option aus, um ![Star](/help/assets/icons/Star.svg) oder eine Anmerkung für ![StarOutline](/help/assets/icons/StarOutline.svg) zu bevorzugen. |
| **[!UICONTROL Titel und Beschreibung]** | Werden durch den Anmerkungsgenerator bereitgestellt. Um den Titel und die Beschreibung zu bearbeiten, wählen Sie den Titel-Link aus. Dadurch wird der [Anmerkungs-Builder](/help/components/annotations/create-annotations.md#annotation-builder) geöffnet. Eine gemeinsame Anmerkung wird mit ![Freigabe](/help/assets/icons/ShareAlt.svg) angegeben. |
| **[!UICONTROL Datenansicht]** | Die Datenansichten, für die diese Anmerkung gilt. |
| **[!UICONTROL Inhabende]** | Der Eigentümer der Anmerkung. Als Benutzer sehen Sie nur die Anmerkungen, deren Inhaber Sie sind, oder die Anmerkungen, die für Sie freigegeben wurden. |
| **[!UICONTROL Angewandter Datumsbereich]** | Das Datum oder der Datumsbereich, für das bzw. den diese Anmerkung gilt. |
| **[!UICONTROL Tags]** | Die Tags für diese Anmerkung. |
| **[!UICONTROL Freigegeben für]** | Die Personen oder Gruppen, für die Sie die Anmerkung freigegeben haben. Klicken Sie auf , um das Dialogfeld **[!UICONTROL Komponente freigeben]** zu öffnen. |
| **[!UICONTROL Datum geändert]** | Zeigt Datum und Uhrzeit der letzten Änderung der Anmerkung an. |

{style="table-layout:auto"}

Verwenden Sie ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) , um anzugeben, welche Spalten angezeigt werden sollen.

### Symbolleiste

Mit der Aktionsleiste können Sie Aktionen für Anmerkungen durchführen. Die Aktionsleiste enthält die folgenden Aktionen:

| Symbol | Aktion | Beschreibung |
|:--:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Hinzufügen]** | Fügen Sie mit dem [Anmerkung-Builder](create-annotations.md#annotation-builder) eine weitere Anmerkung hinzu. |
| ![Durchsuchen](/help/assets/icons/Search.svg) | [!UICONTROL *Suche nach Titel*] | Wenn in der Liste keine Anmerkung ausgewählt ist, suchen Sie mithilfe dieses Suchfelds nach Anmerkungen. |
| ![Beschriftung](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Taggen Sie die ausgewählten Anmerkungen. Wählen Sie im Dialogfeld **[!UICONTROL Tag-Komponente]** die Tags für die ausgewählten Anmerkungen aus oder heben Sie die Auswahl auf. Wählen Sie **[!UICONTROL Speichern]** aus, um die Tags für die ausgewählten Anmerkungen zu speichern. |
| ![Freigeben](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Freigeben]** | Freigeben der ausgewählten Anmerkungen. Im Dialogfeld **[!UICONTROL Komponente freigeben]** können Sie ![Suchen](/help/assets/icons/Search.svg) *Einzelpersonen oder Gruppen durchsuchen* oder Sie können **[!UICONTROL Organisation]** oder **[!UICONTROL Gruppen]** auswählen. Wählen Sie **[!UICONTROL Speichern]** aus, um Freigabedetails für die ausgewählten Anmerkungen zu speichern. Weitere Informationen finden Sie unter [Freigeben von Anmerkungen](#share-annotations) . |
| ![Löschen](/help/assets/icons/Delete.svg) | **[!UICONTROL Löschen]** | Löschen Sie die ausgewählten Anmerkungen. Sie werden zur Bestätigung aufgefordert. |
| ![Bearbeiten](/help/assets/icons/Edit.svg) | **[!UICONTROL Umbenennen]** | Umbenennen einer einzelnen ausgewählten Anmerkung Wenn diese Option aktiviert ist, können Sie die Anmerkung inline umbenennen. |
| ![Kopieren](/help/assets/icons/Copy.svg) | **[!UICONTROL Kopieren]** | Kopieren Sie die ausgewählten Anmerkungen. Neue Anmerkungen werden mit demselben Namen und Suffix (Kopieren) erstellt. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL In CSV exportieren]** | Exportieren Sie die Anmerkungen in eine `Annotations List.csv` -Datei. |

### Aktive Filterleiste

Die Filterleiste zeigt die aktiven Filter an (falls vorhanden). Mit ![CrossSize75](/help/assets/icons/CrossSize75.svg) können Sie schnell einen Filter entfernen. Wenn mehr als ein Filter angegeben ist, können Sie alle Filter mit **[!UICONTROL Alle entfernen]** entfernen.

### Filterbereich

Sie können Anmerkungen mithilfe des linken Fensterbereichs **[!UICONTROL Filter]** filtern. Im Filterbereich werden der Filtertyp und die Anzahl der Anmerkungen angezeigt, die den Filter berücksichtigen. Wählen Sie ![Filter](/help/assets/icons/Filter.svg) aus, um die Anzeige des Filterbereichs umzuschalten.

So filtern Sie die Filterliste:

1. Wählen Sie ![Filter](/help/assets/icons/Filter.svg) aus, um den Bereich &quot;Filter&quot;zu öffnen. Wenn Sie mehr Platz für die Liste &quot;Filter&quot;benötigen, können Sie ![Filter](/help/assets/icons/Filter.svg) erneut auswählen, um den Bereich zu schließen.
1. Sie können die Anmerkungen mit einem der verfügbaren [Filterabschnitte](#filter-sections) filtern.

   >[!INFO]
   >
   >*Elemente* beziehen sich auf die Anmerkungselemente, die in der Liste [Anmerkungen](manage-annotations.md#annotations-list) angezeigt werden.
   > 

#### Filterabschnitte

{{tagfiltersection}}
{{dataviewfiltersection}}
{{ownerfiltersection}}
{{daterangefiltersection}}
{{otherfiltersfiltersection}}


Die [Anmerkungsliste](manage-annotations.md#annotations-list) wird basierend auf Ihrer Filterkonfiguration automatisch aktualisiert. Die konfigurierten Filter werden in der [aktiven Filterleiste](manage-annotations.md#active-filter-bar) angezeigt.


## Bearbeiten von Anmerkungen

Sie können Anmerkungen auf zwei Arten bearbeiten:

* Verwenden Sie in einem Workspace-Projekt das Symbol [Komponenteninformationen](/help/components/use-components-in-workspace.md#component-info) .

* Wählen Sie in der Liste [[!UICONTROL Anmerkungen] ](#annotations-list) den Titel der Anmerkung aus.

Sie verwenden den [Anmerkungs-Builder](/help/components/annotations/create-annotations.md#annotation-builder), um die Anmerkung zu bearbeiten.

## Freigeben von Anmerkungen

Folgendes gilt beim Freigeben von Anmerkungen oder Arbeiten mit Anmerkungen, die für Sie freigegeben sind:

* Für diese Benutzer werden nur Projektanmerkungen in einem Projekt angezeigt, das Sie für andere Benutzer freigeben. Die Benutzer können diese reinen Anmerkungen des Projekts nicht bearbeiten oder löschen.
* Wenn Sie eine Anmerkung speichern und die Anmerkung direkt für einen Benutzer freigeben, kann dieser Benutzer die Anmerkung nur dann bearbeiten und löschen, wenn dieser Benutzer über Administratorrechte verfügt.

* Wenn ein Projekt für Sie freigegeben wird, werden in diesem Projekt erstellte Anmerkungen nur in diesem Projekt angezeigt. Wenn eine Anmerkung direkt für Sie freigegeben wird, wird die Anmerkung in allen Projekten angezeigt, in denen diese Anmerkung angezeigt werden kann.

## Anmerkungen und Zeitzonen

Alle Anmerkungen werden mit einem Zeitstempel erstellt, jedoch keine Stunden- oder Zeitzoneninformationen. Zum Zeitpunkt des Berichts wird die Zeitzone der für das Bedienfeld konfigurierten Datenansicht verwendet.
