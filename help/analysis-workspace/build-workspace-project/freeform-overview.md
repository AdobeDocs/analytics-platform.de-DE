---
description: Übersicht über Workspace-Projekte mit Menüleiste und Einstellungen
keywords: Analysis Workspace
title: Übersicht über Projekte
feature: Workspace Basics
exl-id: 2eeb615c-57a1-4469-8d4a-8a61956bd6e6
role: User
source-git-commit: 4942c83e34b129e3718084601d5a733bcebf4de9
workflow-type: tm+mt
source-wordcount: '1627'
ht-degree: 8%

---

# Übersicht über Projekte

Mit Workspace-Projekten können Sie Bedienfelder, Visualisierungen und Komponenten kombinieren, um Ihre Analyse zu gestalten und für andere in Ihrem Unternehmen freizugeben. Bevor Sie mit dem ersten Projekt beginnen, erfahren Sie, wie Sie auf Ihre Projekte zugreifen, darin navigieren und sie verwalten können.

Um auf Projekte im Customer Journey Analytics zuzugreifen, wählen Sie **[!UICONTROL Workspace]** aus.  Der Manager **[!UICONTROL Projekte]** listet alle Projekte auf, deren Inhaber Sie sind, sowie Projekte, die für Sie freigegeben wurden. Der Projektmanager mit der Projektliste ist auch die Standard-Landingpage für Customer Journey Analytics, sofern Sie unter Voreinstellungen nichts anderes konfiguriert haben.

![Projekt-Landingpage mit der Projektliste.](assets/projects.png)


## Titelbereich

Im Titelbereich können Sie ein Projekt erstellen, einen Ordner bearbeiten und ein Bedienfeld mit zusätzlichen Kacheln ein- oder ausblenden.

* Um einen linken Bereich ein- oder auszublenden, in dem Sie zwischen **[!UICONTROL Projekten]** und **[!UICONTROL Lernen]** wählen können, wählen Sie ![Leiste](/help/assets/icons/Rail.svg) aus.
* Der Titel zeigt Projekte, die optional mit einem Pfad zum ausgewählten Ordner hinzugefügt werden. Beispiel: [!UICONTROL Projekte] > **[!UICONTROL Unternehmensordner]**. Sie können einzelne Unterordnerteile auswählen, um direkt zum jeweiligen Ordner zu gelangen.
* Um Bausteine für ein [**[!UICONTROL leeres Projekt]**](create-projects.md), [**[!UICONTROL leeres mobiles Scorecard]**](/help/mobile-app/create-scorecard.md), [**[!UICONTROL geführte Analyse]**](/help/guided-analysis/overview.md), **[!UICONTROL Öffnen Sie die Dokumentation]** und **[!UICONTROL Versionshinweise öffnen]** anzuzeigen, wählen Sie ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Mehr anzeigen]** aus. Um den Bereich mit Kacheln auszublenden, wählen Sie ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Weniger anzeigen]**.
* Je nachdem, was Sie anzeigen möchten, können Sie mit dem [Selektor anzeigen](#show-selector) die Voreinstellungen bearbeiten und Aktionen für den aktuellen Ordner ausführen, der in **[!UICONTROL Projekten]** angezeigt wird:

  | Aktion | Beschreibung |
  |---|---|
  | **[!UICONTROL Erstellen eines Projekts]** | Wählen Sie &quot;[Neues Projekt erstellen](create-projects.md)&quot;aus. |
  | **[!UICONTROL Ordner erstellen]** | Wählen Sie &quot;[Erstellen eines neuen Ordners](workspace-folders/create-folders.md)&quot;aus. |
  | ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL Voreinstellungen bearbeiten]** | [Bearbeiten Sie die Voreinstellungen](/help/analysis-workspace/user-preferences.md) für alle Ihre Projekte. Wenn der Breadcrumb zu begrenztem Speicherplatz führt, ist diese Aktion Teil des Untermenüs ![Mehr](/help/assets/icons/More.svg) . |
  | **[!UICONTROL Projekte hinzufügen]** | Wählen Sie &quot;[add projects](workspace-folders/add-projects.md)&quot;zum aktuellen Ordner aus. Wenn der Breadcrumb zu begrenztem Speicherplatz führt, ist diese Aktion Teil des Untermenüs ![Mehr](/help/assets/icons/More.svg) . |
  | **[!UICONTROL Ordner umbenennen]** | [ Benennt den aktuellen Ordner um ](workspace-folders/manage-folders.md#rename-folders). |
  | **[!UICONTROL Ordner verschieben]** | [Verschiebt](workspace-folders/manage-folders.md#move-folders) den aktuellen Ordner. |
  | **[!UICONTROL Ordner löschen]** | [Löscht ](workspace-folders/manage-folders.md#delete-folders) den aktuellen Ordner. |




## Projektliste


In der Projektliste werden alle Projekte angezeigt, die Ihnen gehören und für Sie freigegeben wurden. Die Liste umfasst die folgenden Spalten:

| Spalte | Beschreibung |
| --- | --- | 
| ![SelectBox](/help/assets/icons/SelectBox.svg) | Wenn ein oder mehrere Projekte ausgewählt sind, wird am unteren Rand der Projektoberfläche eine blaue Aktionsleiste angezeigt. Weitere Informationen finden Sie unter [Aktionen](#actions) . |
| ![UnausgefüllterStern](/help/assets/icons/StarOutline.svg) | Wählen Sie diese Option aus, um ein Projekt mit ![Stern](/help/assets/icons/Star.svg) oder mit ![StarOutline](/help/assets/icons/StarOutline.svg) zu favorisieren. |
| **[!UICONTROL Titel und Beschreibung]** | Um das Projekt zu bearbeiten, wählen Sie den Titellink aus, der das [Workspace-Projekt](/help/analysis-workspace/home.md) öffnet. Für Sie freigegebene Projekte werden mit ![Freigabe](/help/assets/icons/ShareAlt.svg) angegeben. Wählen Sie ![InfoOutline](/help/assets/icons/InfoOutline.svg) aus, um ein Popup-Menü mit weiteren Details zum Projekt anzuzeigen. Wählen Sie ![Mehr](/help/assets/icons/More.svg) aus, um ein Kontextmenü mit Aktionen zu öffnen. Weitere Informationen finden Sie unter [Aktionen](#actions) . |
| **[!UICONTROL Typ]** | Ein Workspace-Projekt, ein Ordner ![FolderUser](/help/assets/icons/FolderUser.svg) oder eine [mobile Scorecard](/help/mobile-app/home.md). |
| **[!UICONTROL Tags]** | Die auf das Projekt angewendeten Tags. |
| Eingeplant | Gibt an, ob ein Projekt für die E-Mail-Versendung an Empfänger geplant ist. Optionen sind ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL On]** oder ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Off]**. Siehe [Projektdaten an andere senden](/help/analysis-workspace/export/t-schedule-report.md). |
| **[!UICONTROL Freigegebener Link (jeder)]** | Ob ein Projekt für andere freigegeben wird, auch für Personen, die keinen Zugriff auf Analysis Workspace haben. Optionen sind ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Active]** oder ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Inaktiv]**. Weitere Informationen finden Sie unter [Freigeben eines Projekts für andere (keine Anmeldung erforderlich)](/help/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required) in [Freigeben von Projekten](/help/analysis-workspace/curate-share/share-projects.md) . |
| **[!UICONTROL Projektrolle]** | Ihre Rolle für das Projekt. Die Optionen sind: Bearbeiten, Duplizieren, Anzeigen. Weitere Informationen finden Sie unter [Projektrollen](/help/analysis-workspace/curate-share/curate.md) . |
| **[!UICONTROL Datenansicht]** | Die Datenansicht, mit der das Projekt verknüpft ist. |
| **[!UICONTROL Inhabende]** | Die Person, die dieses Projekt erstellt hat (entweder Sie oder eine Person, die das Projekt für Sie freigegeben hat). |
| **[!UICONTROL Freigegeben für]** | Benutzer, für die das Projekt freigegeben wurde. |
| **[!UICONTROL Zuletzt geändert]** | Datum und Zeitpunkt der letzten Änderung des Projekts. |
| **[!UICONTROL Zuletzt geöffnet]** | Datum und Uhrzeit des letzten Öffnens des Projekts. |
| **[!UICONTROL Projekt-ID]** | Die ID des Projekts. |
| **[!UICONTROL Längster Datumsbereich]** | Der längste Datumsbereich eines der Bedienfelder oder Visualisierungen im Projekt. |
| **[!UICONTROL Anzahl der Abfragen]** | Die Gesamtzahl der im Projekt enthaltenen Abfragen. |
| **[!UICONTROL Ort]** | Der Ordner, in dem sich das Projekt befindet. |

Bewegen Sie den Mauszeiger über eine Spaltenüberschrift, um ![ChevronDown](/help/assets/icons/ChevronDown.svg) anzuzeigen, und wählen Sie im Kontextmenü die Option aus:

* **[!UICONTROL Aufsteigende Sortierung]**
* **[!UICONTROL Absteigende Sortierung]**
* **[!UICONTROL Spaltengröße ändern]**. Es wird eine blaue Linie angezeigt, die Sie bei der Größenanpassung der Spalte unterstützt.

### Aktionen

Sie können Aktionen für ein oder mehrere Projekte über das Kontextmenü ![Mehr](/help/assets/icons/More.svg) oder die blaue Aktionsleiste ausführen.

| Symbol | Aktion | Beschreibung |
|:---:| ---|---|
| ![CrossSize75](/help/assets/icons/Close.svg) | **[!UICONTROL *x *selected]** | Heben Sie die Auswahl der ausgewählten Projekte und Ordner auf und entfernen Sie die blaue Aktionsleiste. |
| ![Löschen](/help/assets/icons/Delete.svg) | **[!UICONTROL Löschen]** | Löschen Sie ein oder mehrere Projekte oder Ordner. Sie werden zur Bestätigung aufgefordert. |
| ![Freigeben](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Freigeben]** | Freigeben eines Projekts. Weitere Informationen finden Sie unter [Projekt freigeben](/help/analysis-workspace/curate-share/share-projects.md) . |
| ![Bearbeiten](/help/assets/icons/Edit.svg) | **[!UICONTROL Umbenennen]** | Benennen Sie ein Projekt um. Öffnet das Dialogfeld **[!UICONTROL Umbenennen: *Projektname *]**. Geben Sie einen neuen Namen ein und wählen Sie**[!UICONTROL Speichern ]**aus. |
| ![Kopieren](/help/assets/icons/Copy.svg) | **[!UICONTROL Kopieren]** | Kopieren Sie ein oder mehrere Projekte. Das Projekt erhält denselben Namen und das Suffix `(Copy)`. |
| ![PinOnff](/help/assets/icons/PinOff.svg) | **[!UICONTROL Pin]** oder **[!UICONTROL Unpin]** | Ein oder mehrere Projekte oder Ordner anheften oder entsperren. Angeheftete Projekte und Ordner werden oben in der Liste angezeigt und ignorieren die von Ihnen angegebene Sortierreihenfolge. |
| ![arrowUp](/help/assets/icons/ArrowUp.svg) | **[!UICONTROL Nach oben verschieben]** | Verschieben Sie ein gebundenes Projekt oder einen Ordner in der Projektliste nach oben. |
| ![ArrowDown](/help/assets/icons/ArrowDown.svg) | **[!UICONTROL Nach unten verschieben]** | Verschieben Sie ein gebundenes Projekt oder einen Ordner in die Projektliste. |
| ![Beschriftung](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Taggen Sie ein oder mehrere Projekte oder Ordner. Das Dialogfeld **[!UICONTROL Komponenten taggen]** wird angezeigt, um ein oder mehrere Tags auszuwählen. Wählen Sie **[!UICONTROL Speichern]** aus, um die Tags für die ausgewählten Projekte oder Ordner zu speichern. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Genehmigen]** oder **[!UICONTROL Nicht genehmigen]** | Genehmigen oder deaktivieren Sie ein Projekt. Nur Administratoren können Projekte genehmigen. |
| ![CSV-Datei](/help/assets/icons/FileCSV.svg) | **[!UICONTROL CSV exportieren]** | Exportieren Sie die ausgewählten Projekte in eine CSV-Datei mit dem Namen &quot;`Project List.csv`&quot;. |
| ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) | **[!UICONTROL Projekte hinzufügen]** | Fügen Sie einem ausgewählten Ordner ein oder mehrere Projekte hinzu. In **[!UICONTROL Projekte hinzufügen]** können Sie ein oder mehrere Projekte auswählen. Wählen Sie **[!UICONTROL Hinzufügen]** aus, um die Projekte zum Ordner hinzuzufügen. Weitere Informationen finden Sie unter [Hinzufügen von Projekten zu Ordnern](workspace-folders/add-projects.md#from-inside-a-folder) . |
| ![FolderAddTo](/help/assets/icons/FolderAddTo.svg) | **[!UICONTROL Verschieben nach]** | Verschieben Sie ein oder mehrere ausgewählte Projekte in einen Ordner. Wählen Sie in &quot;**[!UICONTROL Ordner auswählen]**&quot;den Ordner aus, in den das ausgewählte Projekt verschoben werden soll, und wählen Sie &quot;**[!UICONTROL Verschieben]**&quot;. Weitere Informationen finden Sie unter [Hinzufügen von Projekten zu Ordnern](workspace-folders/add-projects.md#from-the-project-list) . |



## Selektor anzeigen

Mit der Auswahl **[!UICONTROL Anzeigen]** können Sie das Erscheinungsbild der Projektoberfläche ändern. Der Selektor **[!UICONTROL Anzeigen]** definiert, welche Optionen im [Titelbereich](#title-area) verfügbar sind und welche Spalten in der [Projektliste](#project-list) angezeigt werden.

* Um die für den [Titelbereich](#title-area) verfügbaren Optionen zu ändern, wählen Sie **[!UICONTROL Alle Projekte anzeigen]** **[!UICONTROL Alle Projekte]** oder **[!UICONTROL Anzeigen]** **[!UICONTROL Ordner und Projekte]** aus.

* Um zu definieren, welche Spalten für die [Projektliste](#project-list) angezeigt werden sollen, wählen Sie ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) aus und wählen Sie im Dialogfeld **[!UICONTROL Tabelle anpassen]** Spalten aus oder heben Sie die Auswahl auf. Wählen Sie **[!UICONTROL Anwenden]** aus, um die Anpassung anzuwenden. Weitere Informationen zu den Spalten finden Sie unter [Projektliste](#project-list) .

## Bedienfeld „Filter“

Sie können die Projekte und Ordner in der [Projektliste](#project-list) mithilfe des ➍ Filterbereichs filtern. Verwenden Sie ![Filter](/help/assets/icons/Filter.svg), um den Filterbereich ein- oder auszublenden.

Das Filterbedienfeld besteht aus den folgenden Abschnitten.

### Tags

| Tags | Beschreibung |
|---|---|
| ![Tags](/help/analysis-workspace/build-workspace-project/assets/projects-filters-tags.png){width="300"} | Im Abschnitt **[!UICONTROL Tags]** können Sie nach Tags filtern. <ul><li>Sie verwenden ![Suche](/help/assets/icons/Search.svg) *Tags durchsuchen*, um nach Tags zu suchen, die Sie zum Filtern verwenden möchten.</li><li>Sie können mehr als ein Tag auswählen. Die verfügbaren Tags hängen von der Auswahl ab, die in anderen Abschnitten des Filterbereichs vorgenommen wurde.</li><li>Die Zahlen geben an:<ul><li>**2︎⃣**: Die Anzahl der Tags, die für die Projekte verfügbar sind, die aus dem aktuellen Filter resultieren.</li><li>7︎⃣: Die Anzahl der mit dem spezifischen Tag verknüpften Projekte.</li></ul></li></ul> |


### Datenansicht

| Datenansicht | Beschreibung |
|---|---|
| ![Datenansichten](/help/analysis-workspace/build-workspace-project/assets/projects-filters-dataviews.png){width="300"} | Im Abschnitt **[!UICONTROL Datenansicht]** können Sie nach Datenansichten filtern. <ul><li>Sie verwenden ![Suche](/help/assets/icons/Search.svg) *Datenansichten durchsuchen*, um nach Datenansichten zu suchen, die Sie zum Filtern verwenden möchten.</li><li>Sie können mehrere Datenansichten auswählen. Die verfügbaren Datenansichten hängen von der Auswahl ab, die in anderen Abschnitten des Filterbereichs vorgenommen wurde.</li><li>Die Zahlen geben an:<ul><li>**3︎⃣**: Die Anzahl der für die Projekte verfügbaren Datenansichten, die aus dem aktuellen Filter resultieren.</li><li>4︎⃣: Die Anzahl der mit der spezifischen Datenansicht verknüpften Projekte.</li></ul></li></ul> |


### Inhaber

| Besitzer | Beschreibung |
|---|---|
| ![Inhaber](/help/analysis-workspace/build-workspace-project/assets/projects-filters-owners.png){width="300"} | Im Abschnitt **[!UICONTROL Inhaber]** können Sie nach Eigentümern filtern. <ul><li>Sie verwenden ![Suche](/help/assets/icons/Search.svg) *Inhaber durchsuchen*, um nach Eigentümern zu suchen, die Sie zum Filtern verwenden möchten.</li><li>Sie können mehrere Inhaber auswählen. Die verfügbaren Inhaber hängen von der Auswahl ab, die in anderen Abschnitten des Filterbereichs vorgenommen wurde.</li><li>Die Zahlen geben an:<ul><li>**3︎⃣**: Die Anzahl der Inhaber, die für die aus dem aktuellen Filter resultierenden Projekte verfügbar sind.</li><li>4︎⃣: Die Anzahl der Projekte, die mit dem jeweiligen Eigentümer verknüpft sind.</li></ul></li></ul> |


### Typ

| Typ | Beschreibung |
|---|---|
| ![Typ](/help/analysis-workspace/build-workspace-project/assets/projects-filters-type.png){width="300"} | Im Abschnitt **[!UICONTROL Typ]** können Sie nach dem Typ der Projekte oder Ordner filtern.<ul><li>Sie können eine oder mehrere der folgenden Optionen auswählen:<ul><li> **[!UICONTROL folder]**</li><li>**[!UICONTROL Analysis Workspace-Projekt]**</li><li>**[!UICONTROL Mobile Scorecard]**</li></ul> <li>Sie können mehrere Filter auswählen. Die anderen verfügbaren Filter hängen von der Auswahl ab, die in anderen Abschnitten des Filterbereichs vorgenommen wurde.</li><li>Die Zahlen geben an:<ul><li>**5︎⃣**: Die Anzahl der anderen Filter, die für die Projekte verfügbar sind, die aus dem aktuellen Filter resultieren.</li><li>4︎⃣: Die Anzahl der Projekte, die mit dem jeweiligen anderen Filter verknüpft sind.</li></ul></li></ul> |


### Sonstige Filter

| Sonstige Filter | Beschreibung |
|---|---|
| ![Sonstige Filter](/help/analysis-workspace/build-workspace-project/assets/projects-filters-others.png){width="300"} | Im Bereich **[!UICONTROL Sonstige Filter]** können Sie nach anderen vordefinierten Filtern filtern.<ul><li>Sie können eine oder mehrere der folgenden Optionen auswählen:<ul><li> **[!UICONTROL Alle anzeigen]**</li><li>**[!UICONTROL Für mich freigegeben]**</li><li>**[!UICONTROL Meine]**</li><li>**[!UICONTROL Genehmigt]**</li><li>**[!UICONTROL Favoriten]**</li></ul> Was Sie auswählen können, hängt von Ihrer Rolle und Ihren Berechtigungen ab.</li><li>Sie können mehrere Filter auswählen. Die anderen verfügbaren Filter hängen von der Auswahl ab, die in anderen Abschnitten des Filterbereichs vorgenommen wurde.</li><li>Die Zahlen geben an:<ul><li>**5︎⃣**: Die Anzahl der anderen Filter, die für die Projekte verfügbar sind, die aus dem aktuellen Filter resultieren.</li><li>4︎⃣: Die Anzahl der Projekte, die mit dem jeweiligen anderen Filter verknüpft sind.</li></ul></li></ul> |

## Durchsuchen

Sie verwenden den ➎ Suchbereich , um mithilfe des Felds ![Suchen](/help/assets/icons/Search.svg) nach Projekten und Ordnern zu suchen. Beginnen Sie mit der Eingabe und die [Projektliste](#project-list) filtert automatisch Ihre Sucheingabe.

Im Suchbereich werden auch die im Filterbereich angewendeten Filter angezeigt.

* Um einen Filter zu entfernen, wählen Sie im Filter ![CrossSize75](/help/assets/icons/CrossSize75.svg) aus.
* Um alle Filter zu entfernen, wählen Sie Alle löschen aus.

Wenn der Platz auf die Anzeige der einzelnen Filter beschränkt ist, wird **[!UICONTROL Filterung nach *x* Filtern]** angezeigt.

* So entfernen Sie einen Filter:

   1. Verwenden Sie oben **[!UICONTROL *x *Filter]**![ChevronDown](/help/assets/icons/ChevronDown.svg) , um ein Kontextmenü zu öffnen, das die Filtertypen und die einzelnen Filter auflistet.
   1. Verwenden Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg) , um einen Filter zu entfernen.


<!--

The Projects page contains the following information: 

>[!NOTE]
>
>Some columns are not displayed by default. To customize the columns you see, click the **Customize table** icon ![Customize table](assets/projects-page-customize-columns-icon.png).

|  Element  | Description  |
|---|---|
| [Edit preferences](/help/analysis-workspace/user-preferences.md) | Manage settings for Analysis Workspace and its related components for all new projects or panels that you create.  |
| [Create folder](/help/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)  | Add a new folder or subfolder to the list of projects and folders. |
| [Create project](/help/analysis-workspace/build-workspace-project/create-projects.md)  | Start a new project from scratch.  |
|  Show more  |Reveals options for creating a blank project or mobile scorecard, [viewing training tutorials](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction.html), or [viewing release notes](/help/release-notes/latest.md).  |
| Show Folders & Projects| Choose whether to show the folder structure of projects. For more information, see [About Folders in Analytics](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
|  Customize table (icon)  | Allows you to customize the information that shows for each project on the Projects page.  |
|  Name  | Name of the Workspace project.  |
| Type | Indicates whether this is a Workspace Project, a folder, or a [Mobile Scorecard](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html). |
|  Tags  |Tags that were applied to the project.  |
| Scheduled | Indicates whether projects are scheduled to be emailed to recipients on a schedule. See [Send project data to others](/help/analysis-workspace/export/t-schedule-report.md). |
| Shared link (anyone) | Projects can be shared with anyone--even with people who don't have access to Analysis Workspace. This column shows whether projects have been shared in this way. See [Share a project with anyone (no login required)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Share projects](/help/analysis-workspace/curate-share/share-projects.md) for more information. |
| Data view | The data view that the project is associated with. |
| [Project Role](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html) | Indicates your role for the project - owners, edit, duplicate, view. |
|  Owner  | The person who created this project (either you or someone who shared the project with you.)  |
|  Shared with  | Users that the project has been shared with.  |
|  Last Modified  | Date and time when the project was last modified.  |
|  Last Opened  | Date and time when the project was last opened.  |
|  Project ID  | The ID of the project.  |
|  Longest Date Range  | The longest date range of the project.  |
|  Number of Queries  | The total number of queries contained in the project.  |
|  Location  | The folder where the project resides.  |

## Menu bar {#menu-bar}

Within a project, the menu provides options for managing your project, adding components, finding help, and more. Each menu option can also be accessed by keyboard [shortcuts](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![New Project options including the Project, Edit, Insert, Components, Share, and Help options.](assets/menu.png)

|  Menu item  | Description  |
|---|---|
|  Project  | Includes common actions for project management, including New, Open, Save, and Save As. You can also refresh the entire project to retrieve the most recent data and definitions by clicking Refresh Project. [Download project data](/help/analysis-workspace/export/download-send.md) options enable you to export data from Workspace. **Project Info & Settings** (see below) offers many options for managing your project.  |
|  Edit  | Undo or redo your last action. Clear All will reset your project to a blank starting point. |
|  Insert  | Insert new panels or visualizations from this menu. You can also insert new panels and visualizations from the left panel.  |
|  [Components](/help/components/overview.md)  | Create new filters, calculated metric, date range, or alert components from your project. You can also create new components from the left panel. If your component definitions have recently changed, Refresh Components will retrieve the latest definitions. |
|  [Share](/help/analysis-workspace/curate-share/send-schedule-files.md)  | Curate, share and schedule PDF/CSV projects to recipients in your organization.  |
|  Help  | Access help documentation, videos, and the Analytics [Experience League community](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community). Manage the visibility of Workspace tips as well as the [debugger](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/apis/using-analysis-workspace-to-build-api-2-requests). Find details about Workspace and factors that impact project [performance](/help/technotes/optimizing-performance.md).  |
|  Share button or Owner  | If you are in an Own or Edit for the project, the Share button in the top-right gives you one-click access to manage your project recipients. If you are in a Duplicate or View role for the project, you will see the project owner's name. |

### Project Info & Settings {#info-settings}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project info & settings]** provides project-level information on the currently active project.

![The Project Info & Settings window.](assets/projectinfo.png)

Settings include:

|  Setting  | Description  |
|---|---|
|  Project Name  | The name given to the project. You can double-click the name to edit it.  |
|  Created By  | Project owner name  |
|  Last Modified  | Date of last modification to the project.  |
|  Tags  |Lists any tags applied to a project for easier categorization.  |
|  Description  | A description is useful for clarifying the purpose of a project. You can double-click the description to edit it.  |
|  Count repeat instances in project  | Specifies whether repeat instances are counted in reports. Note: this setting does not apply to Flow or Fallout visualizations.  |
|  [Project color palette](/help/analysis-workspace/build-workspace-project/color-palettes.md)  | You can change the categorical color palette used in Workspace, by choosing from out-of-the-box palettes that have been optimized for color blindness, or by specifying your custom palette. This feature affects many things in Workspace, including most visualizations.  |
| [View Density](/help/analysis-workspace/build-workspace-project/view-density.md) | Lets you see more data on the screen by reducing the vertical padding of the left panel, freeform tables and cohort tables. |

## Left panel

Within a project, various icons are available in the left panel, and each represents important parts of a project:

* [Panels](/help/analysis-workspace/c-panels/panels.md) ![panels icon](assets/panels-icon.png)

* [Visualizations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)![visualizations icon](assets/visualizations-icon.png)

* [Components](/help/components/overview.md)![components icon](assets/components-icon.png)

* [Data dictionary](/help/components/data-dictionary/data-dictionary-overview.md)![data dictionary icon](assets/data-dictionary-icon.png)

* [Table of contents](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md) ![toc icon](assets/toc-icon.png)

Components (Dimensions, Metrics, Filters, Date Ranges) in the left panel relate to the active panel data view. The active panel is identified by the blue border that surrounds it, and the active data view is listed at the top of the component panel.

![The components relating to the active panel data view for Cross-Industry Demo Data data view.](assets/left-rail.png)

## Project canvas {#canvas}

The project canvas is where you bring together panels, tables, visualizations, and components to build your analysis. A project can contain many panels, and each panel can contain many tables and visualizations.

Panels are helpful when you want to organize your projects according to time periods, data views, or analysis use case. The active panel will have a blue border around it, and determines what components are available in the left panel.

Depending on the starting point you chose for your projects, you will either have a [freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) or a [blank panel](/help/analysis-workspace/c-panels/blank-panel.md) in the canvas to begin with. The quickest way to start analyzing is to select one or many components and simply drag & drop them into the project canvas. A table of data will automatically be rendered for you. [Learn more](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) about the different options for building a table, or leverage our [training tutorial](/help/analysis-workspace/home.md) for more guidance on building your first project.

![A Freeform Table for the project.](assets/canvas.png)

## Project Manager {#manager}

Analysis Workspace projects can be managed under **Analytics > Components >  Projects**. The Project Manager shows the projects that a specific user created. You can transfer project ownership to a new user under Admin > Analytics Users & Assets > Transfer Assets.

In Projects Manager, you can add, tag, share, duplicate/copy, and more. Search for a project in the search bar or by using the filter options in the left panel. You can filter by tag, owners, project type and more.

![Project Manager Tags search field and Title search field.](assets/project-manager.png)

The following are common actions in the Projects manager, and can be taken on one or many projects at once:

|  Action  | Description  |
|---|---|
|  Add  | Create a new project from scratch.  |
|  Tag or Approve  | Choose "Tag" or "Approve" to organize your projects and make them easier to search for.  |
|  [Share](/help/analysis-workspace/curate-share/share-projects.md)  | Make a project available to other Analysis Workspace users in your organization.  |
|  Delete  | Delete your project.  |
|  Rename  | Edit the name of your project.  |
|  Copy  | Create a duplicate copy of your project. This creates a new project and project ID. Any shares or schedules tied to the original project will not be copied. |
|  Export to CSV  | Download your project as a CSV file, which includes plain-text data.  |

-->

