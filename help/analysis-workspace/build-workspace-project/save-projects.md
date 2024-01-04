---
description: Erfahren Sie mehr über die verschiedenen Speicheroptionen, einschließlich automatisches Speichern, Speichern unter, Speichern als Vorlage und Öffnen früherer Versionen.
title: Projekte speichern
feature: Workspace Basics
role: User
exl-id: d751057e-6a5f-4605-abc1-9259a1f95a28
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 93%

---

# Projekte speichern

Projekte in Analysis Workspace werden automatisch alle zwei Minuten gespeichert.

Sie können Projekte auch manuell speichern. Beim manuellen Speichern eines Projekts stehen zusätzliche Optionen wie das Hinzufügen von Tags oder Notizen zur Verfügung.

## Speichern von Projektoptionen {#Save}

Beim manuellen Speichern eines Projekts in Analysis Workspace stehen verschiedene Optionen zur Verfügung.

Gehen Sie folgendermaßen vor, um ein Projekt manuell zu speichern:

1. Wenn Ihr Projekt in Analysis Workspace geöffnet ist, wählen Sie **[!UICONTROL Projekt]** und dann eine der folgenden Optionen aus:

   | Aktion | Beschreibung |
   |---|---| 
   | **[!UICONTROL Speichern]** | Speichern Sie die Änderungen an Ihrem Projekt. Wenn das Projekt freigegeben ist, sehen auch die Empfänger des Projekts die Änderungen. Wenn Sie das Projekt zum ersten Mal speichern, werden Sie aufgefordert, dem Projekt einen Namen, eine (optionale) Beschreibung und (optionale) Tags hinzuzufügen. |
   | **[!UICONTROL Mit Hinweisen speichern]** | Bevor Sie das Projekt speichern, fügen Sie Notizen zu den Änderungen im Projekt hinzu. Notizen werden mit der Projektversion gespeichert und stehen allen Editoren unter [!UICONTROL Projekt] > [!UICONTROL Frühere Version öffnen] zur Verfügung. |
   | **[!UICONTROL Speichern unter]** | Erstellen Sie ein Duplikat Ihres Projekts. Das ursprüngliche Projekt bleibt davon unberührt. |
   | **[!UICONTROL Als Vorlage speichern]** | Speichern Sie Ihr Projekt als [benutzerdefinierte Vorlage](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=de), die für Ihr Unternehmen unter **[!UICONTROL Projekt > Neu]** zur Verfügung steht. |

## Automatisches Speichern {#Autosave}

Alle Projekte in Analysis Workspace werden automatisch alle 2 Minuten auf Ihrem lokalen Computer gespeichert. Dazu gehören auch neu erstellte Projekte, die noch nicht manuell gespeichert wurden.

* **Neue Projekte:** Obwohl neue Projekte automatisch gespeichert werden, müssen Sie jedes neue Projekt beim ersten Mal manuell speichern. Analysis Workspace fordert Sie auf, neue Projekte manuell zu speichern, wenn Sie zu einem anderen Projekt wechseln, die Browser-Registerkarte schließen usw.

  Wenn Sie aus irgendeinem Grund unerwartet den Zugriff auf ein neu erstelltes Projekt verlieren, bevor Sie es manuell gespeichert haben, wird eine Wiederherstellungsversion Ihres Projekts auf der Analysis Workspace-Landingpage in einem Ordner namens `Recovered Projects (Last 7 Days)` gespeichert. Sie müssen das betroffene Projekt wiederherstellen und manuell an einem gewünschten Ort speichern.

  Gehen Sie folgendermaßen vor, um ein Projekt wiederherzustellen:

   1. Gehen Sie zum Ordner [!UICONTROL **Wiederhergestellte Projekte**] auf der Landingpage von Analysis Workspace.

      ![Die Liste der Ordner, die den Ordner Wiederhergestelltes Projekt hervorheben.](assets/recovered-folder.png)

   1. Öffnen Sie das Projekt und speichern Sie es an einem gewünschten Ort.


* **Bestehende Projekte:** Wenn Sie aus irgendeinem Grund ein Projekt verlassen, das noch nicht automatisch gespeicherten Änderungen enthält, fordert Sie Analysis Workspace entweder auf, Ihre Änderungen zu speichern, oder gibt eine Warnmeldung aus.

  Im Folgenden finden Sie einige gängige Szenarien:

### Öffnen eines weiteres Projekts

Wenn Sie ein weiteres Projekt öffnen, während Sie an einem Projekt arbeiten, das noch nicht automatisch gespeicherte Änderungen enthält, werden Sie von Analysis Workspace aufgefordert, das aktuelle Projekt zu speichern, bevor Sie es verlassen.

Die folgenden Optionen sind verfügbar:

* **Speichern:** Ersetzt die neueste automatisch gespeicherte lokale Kopie Ihres Projekts durch Ihre letzten Änderungen.
* **Speichern unter:** Speichert Ihre letzten Änderungen als neues Projekt. Das ursprüngliche Projekt wird nur mit den letzten automatisch gespeicherten Änderungen gespeichert.
* **Änderungen verwerfen:** Verwirft Ihre letzten Änderungen. Das Projekt behält die letzten automatisch gespeicherten Änderungen bei.

![Klicken Sie auf Speichern , um Änderungen an einem Projekt zu speichern.](assets/existing-save.png)

### Verlassen oder Schließen einer Registerkarte

Wenn Sie eine Seite verlassen oder die Browser-Registerkarte schließen, während Sie ein Projekt mit noch nicht automatisch gespeicherten Änderungen betrachten, warnt Sie der Browser, dass Ihre nicht gespeicherten Änderungen verloren gehen. Sie können entscheiden, ob Sie die Registerkarte verlassen oder abbrechen möchten.

![Klicken Sie auf Leeren , um die Site zu verlassen, oder auf Abbrechen , um zu navigieren, ohne Änderungen zu speichern. ](assets/browser-image.png)

### Browser-Abstürze oder Zeitüberschreitung der Sitzung

Wenn Ihr Browser abstürzt oder Ihre Sitzung durch eine Zeitüberschreitung beendet wird, werden Sie beim nächsten Zugriff auf Analysis Workspace aufgefordert, alle Änderungen am Projekt wiederherzustellen, die noch nicht automatisch gespeichert wurden.

Im Folgenden finden Sie das Dialogfeld „Projektwiederherstellung“, das beim ersten Zugriff auf Analysis Workspace nach einem Absturz oder einer Zeitüberschreitung angezeigt wird.

Wählen Sie **Ja**, um das Projekt auf der Basis der letzten automatisch gespeicherten Kopie wiederherzustellen.

Wählen Sie **Nein**, um die automatisch gespeicherte Kopie zu löschen und die letzte vom Benutzer bzw. der Benutzerin gespeicherte Version des Projekts zu öffnen.

![Dialogfeld &quot;Projektwiederherstellung&quot;.](assets/project-recovery.png)

Bei **neuen** Projekten, die noch nie gespeichert wurden, können nicht gespeicherte Änderungen nicht wiederhergestellt werden.

## Vorherige Version öffnen {#previous-version}

So öffnen Sie eine frühere Version eines Projekts:

1. Gehen Sie zu **[!UICONTROL Projekt]** > **[!UICONTROL Frühere Version öffnen]**

   ![Liste und Optionen der zuvor gespeicherten Projektversionen zum Anzeigen aller Versionen oder Nur Versionen mit Anmerkungen.](assets/previous-versions.png)

1. Überprüfen Sie die Liste der verfügbaren älteren Versionen.
   [!UICONTROL Zeitstempel] und [!UICONTROL Editor] werden ebenso wie [!UICONTROL Notizen] angezeigt, wenn diese beim Speichern im [!UICONTROL Editor] hinzugefügt wurden. Versionen ohne Notizen werden 90 Tage lang gespeichert. Versionen mit Notizen werden für ein Jahr gespeichert.
1. Wählen Sie eine frühere Version aus und klicken Sie auf **[!UICONTROL Laden]**.
Die vorherige Version wird dann mit einer Benachrichtigung geladen. Die vorherige Version wird nur dann zur aktuell gespeicherten Version Ihres Projekts, wenn Sie auf **[!UICONTROL Speichern]** klicken. Wenn Sie die geladene Version verlassen, sehen Sie bei der Rückkehr die zuletzt gespeicherte Version des Projekts.
