---
description: Erfahren Sie mehr über die verschiedenen Optionen zum Speichern Ihrer Projekte in Analysis Workspace.
title: Projekte speichern
feature: Workspace Basics
role: User
exl-id: d751057e-6a5f-4605-abc1-9259a1f95a28
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 95%

---

# Speichern von Projekten {#save-projects}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_project_addnotes"
>title="Hinzufügen von Hinweisen"
>abstract="Fügen Sie Hinweise zur Projektversion hinzu, die gespeichert wird. Diese Hinweise werden mit der Version gespeichert und sind über das Menü **[!UICONTROL Projekt]** > **[!UICONTROL Vorherige Version öffnen]** zugänglich."

<!-- markdownlint-enable MD034 -->


Projekte in Analysis Workspace werden automatisch alle zwei Minuten gespeichert. Sie können Projekte auch selbst speichern, ein Projekt als Duplikat speichern oder ein Projekt mit Versionshinweisen speichern.

## Speichern

Um ein Projekt manuell zu speichern, wählen Sie, während das Projekt geöffnet ist, **[!UICONTROL Projekt]** und dann eine der folgenden Optionen aus:

* **[!UICONTROL Speichern]**

  Speichern Sie die Änderungen an Ihrem Projekt. Wenn das Projekt freigegeben ist, sehen auch die Empfangenden des Projekts die Änderungen.

  Beim erstmaligen Speichern des Projekts wird das Dialogfeld **[!UICONTROL Speichern]** angezeigt.

  ![Projekt speichern](assets/save-project.png)

   1. Geben Sie Folgendes an:

      * **[!UICONTROL Name]** (erforderlich): Name Ihres Projekts.
      * **[!UICONTROL Beschreibung]**: Eine Beschreibung Ihres Projekts.
      * **[!UICONTROL Tags]**: Suchen Sie im Feld [!UICONTROL *Tags suchen*] nach Tags oder fügen Sie neue Tags mit **[!UICONTROL ENTER]** hinzu.
      * **[!UICONTROL Ordner]**: Wählen Sie einen Ordner aus [!UICONTROL *Dropdown-Menü*] Ordner auswählen“ aus. Wenn Sie keinen Ordner angeben, wird das Projekt im aktuellen Ordner gespeichert, aus dem Sie ein neues Projekt erstellt haben.
      * **[!UICONTROL Versionshinweise]**. Fügen Sie Versionshinweise im Textbereich *Hinweise hinzufügen* hinzu.

   1. Wählen Sie **[!UICONTROL Speichern]** aus, um Ihr Projekt zu speichern.

  Beim Speichern des Projekts wird eine Version des Projekts für 90 Tage gespeichert.

  Wenn Sie ein Projekt speichern, das Sie freigegeben haben, werden Sie über das Warnungsdialogfeld **[!UICONTROL Änderungen an freigegebenem Projekt speichern]** zur Bestätigung aufgefordert.

  ![Freigegebens Projekt speichern](assets/save-project-shared.png)

   * Wählen Sie **[!UICONTROL Speichern]** aus, um das Projekt zu speichern.
   * Wählen Sie **[!UICONTROL Speichern unter]**, um das Projekt als doppeltes Projektduplikat mit einem neuen Namen zu speichern.


* **[!UICONTROL Mit Hinweisen speichern]**

  ![Mit Hinweisen speichern](assets/save-version-notes.png)

  Wenn Sie Ihr Projekt speichern, fügen Sie Notizen zu den Änderungen im Projekt hinzu. Im Dialogfeld „Versionshinweise speichern“:

   1. Geben Sie Ihre **[!UICONTROL Versionshinweise]** im Textbereich **[!UICONTROL Hinweise hinzufügen]** ein.
   1. Wählen Sie **[!UICONTROL Speichern]** aus.

  Notizen werden mit der Projektversion gespeichert und sind beim [Öffnen einer früheren Version](open-projects.md#open-previous-version) des Projekts verfügbar. Eine mit Hinweisen gespeicherte Version wird automatisch für ein Jahr gespeichert.

* **[!UICONTROL Speichern unter]**

  ![Projekt speichern unter](assets/save-project-as.png)

  Erstellen Sie ein Duplikat Ihres Projekts mit einem neuen Namen. Das Dialogfeld „Speichern unter“ wird angezeigt.

   1. Geben Sie Folgendes an:

      * **[!UICONTROL Name]** (erforderlich): Name Ihres Projekts.
      * **[!UICONTROL Beschreibung]**: Eine Beschreibung Ihres Projekts.
      * **[!UICONTROL Tags]**: Suchen Sie im Feld [!UICONTROL *Tags suchen*] nach Tags oder fügen Sie neue Tags mit **[!UICONTROL ENTER]** hinzu.
      * **[!UICONTROL Ordner]**: Wählen Sie einen Ordner aus [!UICONTROL *Dropdown-Menü*] Ordner auswählen“ aus. Wenn Sie keinen Ordner angeben, wird das Projekt im aktuellen Ordner gespeichert, aus dem Sie ein neues Projekt erstellt haben.
      * **[!UICONTROL Versionshinweise]**. Fügen Sie Versionshinweise im Textbereich *Hinweise hinzufügen* hinzu.

   1. Wählen Sie **[!UICONTROL Speichern]** aus, um Ihr Projekt zu speichern.

  Sie können das Projekt in einem anderen Ordner speichern. Das ursprüngliche Projekt bleibt davon unberührt.


<!-- Cannot find this option in CJA 
| **[!UICONTROL Save as template]** | Save your project as a [custom template](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=de) that becomes available to your organization under **[!UICONTROL Project > New]** | 
-->

## Automatisches Speichern


>[!IMPORTANT]
>
>Obwohl neue Projekte automatisch gespeichert werden, müssen Sie jedes neue Projekt beim **ersten** Mal manuell speichern.
>

Alle Projekte in Analysis Workspace werden automatisch alle 2 Minuten auf Ihrem lokalen Computer gespeichert. Dazu gehören auch neu erstellte Projekte, die noch nicht manuell gespeichert wurden.

### Neue Projekte

Analysis Workspace fordert Sie auf, neue Projekte manuell zu speichern, wenn Sie zu einem anderen Projekt wechseln, die Browser-Registerkarte schließen usw.

Wenn Sie aus irgendeinem Grund unerwartet den Zugriff auf ein neu erstelltes Projekt verlieren, bevor Sie es manuell gespeichert haben, wird eine Wiederherstellungsversion Ihres Projekts auf der Analysis Workspace-Landingpage in einem Ordner namens **[!UICONTROL Wiederhergestellte Projekte (letzte 7 Tage)]** gespeichert. Stellen Sie das betroffene Projekt wieder her und speichern Sie es manuell am gewünschten Ort.

Gehen Sie folgendermaßen vor, um ein Projekt wiederherzustellen:

1. Gehen Sie zum Ordner **[!UICONTROL Wiederhergestellte Projekte (letzte 7 Tage)]** auf der Analysis Workspace-Landingpage.

<!-- 
     ![The list of folders highlighting the Recovered Project folder.](assets/recovered-folder.png)
  -->

1. Öffnen Sie das Projekt und speichern Sie es an einem gewünschten Ort.


### Bestehende Projekte

Wenn Sie aus irgendeinem Grund ein Projekt verlassen, das noch nicht automatisch gespeicherte Änderungen enthält, fordert Sie Analysis Workspace entweder auf, Ihre Änderungen zu speichern, oder gibt eine Warnmeldung aus.


Verschiedene gängige Szenarien:

#### Öffnen eines weiteres Projekts

Wenn Sie ein anderes Projekt öffnen, während Sie an einem Projekt arbeiten, das noch nicht automatisch gespeicherte Änderungen enthält, werden Sie von Analysis Workspace aufgefordert, das aktuelle Projekt zu speichern.

Die folgenden Optionen sind verfügbar:

* **[!UICONTROL Speichern]**: Ersetzt die neueste automatisch gespeicherte lokale Kopie Ihres Projekts durch Ihre letzten Änderungen.
* **[!UICONTROL Änderungen verwerfen]**: Verwirft Ihre letzten Änderungen. Das Projekt behält die letzte automatisch gespeicherte lokale Kopie bei.
* **[!UICONTROL Abbrechen]**: Bricht die Aktion ab, um ein anderes Projekt zu öffnen und das vorhandene Projekt geöffnet zu lassen.

<!-- ![Click Save to save changes to a project.](assets/existing-save.png) -->

#### Verlassen oder Schließen einer Registerkarte

Wenn Sie eine Seite verlassen oder die Browser-Registerkarte schließen, während Sie ein Projekt mit noch nicht automatisch gespeicherten Änderungen betrachten, warnt Sie der Browser, dass Ihre nicht gespeicherten Änderungen verloren gehen. Sie können entscheiden, ob Sie die Registerkarte verlassen oder abbrechen möchten. Wie der Browser warnt, hängt vom verwendeten Browser ab.


### Browser-Abstürze oder Zeitüberschreitung der Sitzung

Wenn Ihr Browser abstürzt oder Ihre Sitzung durch eine Zeitüberschreitung beendet wird, werden Sie beim nächsten Zugriff auf Analysis Workspace aufgefordert, alle Änderungen am Projekt wiederherzustellen, die noch nicht automatisch gespeichert wurden.

* Wählen Sie **[!UICONTROL Ja]**, um das Projekt auf der Basis der letzten automatisch gespeicherten Kopie wiederherzustellen.

* Wählen Sie **[!UICONTROL Nein]**, um die automatisch gespeicherte Kopie zu löschen und die letzte vom Benutzer bzw. der Benutzerin gespeicherte Version des Projekts zu öffnen.

<!--![The Project Recovery dialog box.](assets/project-recovery.png)-->



Bei **neuen** Projekten, die noch nie gespeichert wurden, können nicht gespeicherte Änderungen nicht wiederhergestellt werden.


<!-- Shouldn't this belong to another page?  Moved it to a new open projects page


## Open previously saved version

To open a previously saved version of a project:

1. Select **[!UICONTROL Open previous version]** from the **[!UICONTROL Project]** menu.

   ![The Previously saved project versions list and options to show All versions or Only versions with notes.](assets/open-previously-saved.png)

1. Review the list of previous versions available. You can switch between **[!UICONTROL All versions]** and **[!UICONTROL Only versions with notes]**.

   For each version, the list shows a timestamp
   [!UICONTROL Timestamp] and [!UICONTROL Editor] are shown, in addition to [!UICONTROL Notes] if they were added when the [!UICONTROL Editor] saved. Versions without notes are stored for 90 days; versions with notes are stored for 1 year.
1. Select a previous version and click **[!UICONTROL Load]**.
   The previous version then loads with a notification. The previous version does not become the current saved version of your project until you click **[!UICONTROL Save]**. If you navigate away from the loaded version, when you return, you will see the last saved version of the project.

-->
