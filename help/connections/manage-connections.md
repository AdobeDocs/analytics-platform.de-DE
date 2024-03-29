---
title: Erfahren Sie, wie Sie Verbindungen in Customer Journey Analytics verwalten.
description: Beschreibt, wie Verbindungen zu Experience Platform-Datensätzen in Customer Journey Analytics (Customer Journey Analytics) verwaltet werden.
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 17956f66d0bed46b876ba83aba8782c664fe2530
workflow-type: tm+mt
source-wordcount: '2764'
ht-degree: 23%

---

# Verbindungen verwalten

Einmal [eine oder mehrere Verbindungen erstellt oder bearbeitet](/help/connections/create-connection.md)können Sie sie in **[!UICONTROL Verbindungen]**. Verbindungen ermöglichen Ihnen Folgendes:

* Zeigen Sie alle Verbindungen auf einen Blick an, einschließlich des Eigentümers, der Sandbox und des Zeitpunkts der Erstellung und Änderung der Verbindungen.
* Bearbeiten Sie eine Verbindung.
* Eine Verbindung löschen.
* Eine Datenschicht aus einer Verbindung erstellen.
* Lassen Sie sich alle Datensätze in einer Verbindung anzeigen.
* Überprüfen Sie den Status der Datensätze Ihrer Verbindung und den Status des Aufnahmevorgangs. Wann sind Ihre Daten beispielsweise verfügbar, damit Sie mit der Berichterstellung und Analyse in Analysis Workspace beginnen können.
* Identifizieren Sie alle Datendiskrepanzen aufgrund einer Fehlkonfiguration. Fehlen Zeilen? Wenn ja, welche Zeilen fehlen und warum? Haben Sie Verbindungen falsch konfiguriert und fehlende Daten im Customer Journey Analytics verursacht?
* Hier erhalten Sie Einblicke in die Verwendung von aufgenommenen und berichtspflichtigen Zeilen über alle Verbindungen hinweg.

[!UICONTROL Verbindungen] hat zwei Schnittstellen: [[!UICONTROL Liste]](#list) und [[!UICONTROL Nutzung]](#usage).


## Liste

Die [!UICONTROL Liste] -Schnittstelle ist die Standardschnittstelle für Verbindungen. Wenn nicht ausgewählt, wählen Sie die **[!UICONTROL Liste]** -Tab, um auf die Benutzeroberfläche zuzugreifen.

Die [!UICONTROL Liste] -Schnittstelle zeigt eine Tabelle aller verfügbaren Verbindungen. Mithilfe der Suche können Sie schnell nach einer Verbindung suchen ![Suche](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) ankreuzen.

Die folgenden Spalten/Symbole sind in der Tabelle verfügbar.

| Spalte/Symbol | Beschreibung |
| --- | --- |
| [!UICONTROL Name] | Der Anzeigename der Verbindung. Um die Details der Verbindung anzuzeigen, wählen Sie den Hyperlink-Namen aus. Siehe [Verbindungsdetails](#connection-details). |
| ![Informationen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | So zeigen Sie Informationen an [!UICONTROL Enthaltene Datensätze], [!UICONTROL Sandbox], [!UICONTROL Inhaber]und wählen Sie ![Informationen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) neben dem Verbindungsnamen.<p>In einem Popup-Fenster werden Details angezeigt. <p><img src="./assets/conn-info.png" alt="Verbindungsinformationen anzeigen" width="50%" /> |
| ![Datenansicht](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | nach [Datenansicht erstellen](#create-a-data-view) Wählen Sie für die Verbindung ![Datenansicht](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) . Dieses Symbol wird nur angezeigt, wenn der Verbindung bereits keine Datenansicht zugeordnet ist. |
| ![Mehr](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Auswählen ![Mehr](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) an: <p>![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [Bearbeiten](#edit-a-connection) eine Verbindung.<p>![Löschen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [Löschen](#delete-a-connection) eine Verbindung.<p>![Datenansicht](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [Neue Datenansicht erstellen](#create-a-data-view). Verwenden Sie dies, um zusätzliche Datenansichten für die Verbindung zu erstellen. |
| [!UICONTROL Datensätze] | Zeigt eine oder mehrere Links zu den Datensätzen an, die Teil der Verbindung sind. Sie können den Datensatz-Hyperlink auswählen, um den Datensatz in der Verbindung anzuzeigen. Wenn weitere Datensätze Teil der ausgewählten Verbindung sind, wählen Sie **[!UICONTROL +*x* more]** , um **[!UICONTROL Enthaltene Datensätze]** Bedienfeld. In diesem Bereich werden Links zu allen Datensätzen und eine Option zur Suche nach einem bestimmten Datensatz angezeigt, der Teil der Verbindung ist.<p><img src="./assets/datasets-included.png" alt="Enthaltene Datenbestände" width="50%" /><p>Wenn Sie einen Datensatznamen auswählen, wird der Datensatz in der Experience Platform-Benutzeroberfläche in einer neuen Registerkarte geöffnet. |
| [!UICONTROL Sandbox] | Zeigt die [Experience Platform-Sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=de) von dem aus diese Verbindung ihre Datensätze zeichnet. Diese Sandbox wurde beim erstmaligen Erstellen der Verbindung ausgewählt. Sie kann nicht geändert werden. |
| [!UICONTROL Inhaber] | Die Person, die die Verbindung hergestellt hat. |
| [!UICONTROL Neue Daten importieren] | Zeigt den Status des Imports neuer Daten für Datensätze an: <p><span style="color:green">●</span>   **[!UICONTROL _x _on]**für die Anzahl der Datensätze, die für den Import neuer Daten konfiguriert sind, und&lt;/<p><span style="color:gray">●</span>   **[!UICONTROL _x Aus_]** für die Anzahl der Datensätze, für die der neue Datenimport deaktiviert ist. |
| [!UICONTROL Erstellt am] | Der Zeitstempel, zu dem die Verbindung erstellt wurde. |
| [!UICONTROL Zuletzt geändert] | Der Zeitstempel, zu dem die Verbindung zuletzt aktualisiert wird. |
| [!UICONTROL Aufstockungsdaten] | Zeigt den Status für Aufstockungsdaten in allen Datensätzen an.<p><span style="color:red">●</span>   **[!UICONTROL _x _Aufstockungen fehlgeschlagen]**für die Anzahl fehlgeschlagener Aufstockungen in Datensätzen,<p><span style="color:orange">●</span>   **[!UICONTROL _x _Verarbeitung von Backfilets]**für die Anzahl der Aufstockungen für die Verarbeitung in Datensätzen,<p><span style="color:green">●</span>   **[!UICONTROL _x _Aufstockungen abgeschlossen]**für die Anzahl abgeschlossener Backups für Datensätze und<p><span style="color:grey">●</span>   **[!UICONTROL _Aus_]** , falls für die Datensätze in der Verbindung keine Rückfüllungen definiert sind. |

Sie können konfigurieren, welche Spalten angezeigt werden sollen, indem Sie ![Spalteneinstellungen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg). Dies zeigt die **Tabelle anpassen** -Dialogfeld, in dem Sie Spalten in der Tabelle ein-/ausschalten können.

### Verbindung bearbeiten

Ermöglicht es Administratoren, die Verbindung zu bearbeiten.

1. Auswählen ![Mehr](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) neben dem Verbindungsnamen
1. Auswählen ![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Bearbeiten]** aus dem Kontextmenü aus.

Alternativ können Sie:

1. Wählen Sie die Verbindungszeile aus.

1. Auswählen ![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Bearbeiten]** aus der blauen Leiste.

Beim Bearbeiten einer Verbindung haben Sie folgende Möglichkeiten:

* Import neuer Daten starten und beenden.
* Eine Verbindung umbenennen.
* Aktualisieren Sie die Datensätze.
* Entfernen Sie Datensätze aus den Verbindungen.

Siehe [Erstellen oder Bearbeiten einer Verbindung](create-connection.md) für weitere Informationen.


### Eine Verbindung löschen {#connections-delete}

Ermöglicht Administratoren das Löschen der Verbindung.

1. Auswählen ![Mehr](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) neben dem Verbindungsnamen.
1. Auswählen ![Löschen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Löschen]**.

Alternativ können Sie:

1. Wählen Sie die Verbindungszeile aus.

1. Auswählen ![Löschen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Löschen]** aus der blauen Leiste.

Wenn Sie eine Verbindung löschen, wird eine **[!UICONTROL Verbindung löschen]** gibt an, welche Datenansichten gelöscht werden und welche Workspace-Projekte betroffen sind.

<img src="./assets/delete-connection.png" alt="Verbindung löschen" width="50%" />

Auswählen **[!UICONTROL Weiter]** , um die Verbindung zu löschen.

Siehe [Auswirkungen löschen](/help/admin/cja-deletion.md) für weitere Informationen zu den Auswirkungen des Löschens einer Verbindung.


### Erstellen einer Datenansicht

Ermöglicht Administratoren das Erstellen einer Datenansicht für die Verbindung.

* Wenn der Verbindung keine Datenansicht zugeordnet ist:

   1. Auswählen ![Datenansicht hinzufügen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) neben dem Verbindungsnamen.

* Wenn bereits eine oder mehrere Datenansichten für die Verbindung erstellt wurden:

   1. Auswählen ![Mehr](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) neben dem Verbindungsnamen.
   1. Auswählen ![Datenansicht hinzufügen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Neue Datenansicht erstellen]**.

Alternativ können Sie:

1. Wählen Sie die Verbindungszeile aus.

1. Auswählen ![Datenansicht hinzufügen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Datenansicht erstellen]** aus der blauen Schaltflächenleiste.

Weitere Informationen finden Sie unter [Erstellen oder Bearbeiten einer Datenansicht](/help/data-views/create-dataview.md).

### Verbindungsdetails {#connection-detail}

Um zu den Details für eine Verbindung zu wechseln, wählen Sie einen Verbindungsnamen in der Verbindungstabelle aus.

![Fenster mit allen Datensätzen mit Widgets und Einstellungen](assets/conn-details.png)

Die Benutzeroberfläche &quot;Verbindungsdetails&quot;bietet einen detaillierten Überblick über den Status einer Verbindung. Sie haben folgende Möglichkeiten:

* Überprüfen Sie den Status der Datensätze Ihrer Verbindung und des Aufnahmevorgangs.
* Ermitteln Sie Konfigurationsprobleme, die zu übersprungenen oder gelöschten Datensätzen führen können.
* Finden Sie heraus, wann die Daten für das Reporting verfügbar sind.

| Benutzeroberfläche | Beschreibung |
| --- | --- |
| ![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [!UICONTROL Verbindung bearbeiten] | Um die Details einer Verbindung zu bearbeiten, wählen Sie ![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Verbindung bearbeiten]** . Siehe [Erstellen oder Bearbeiten einer Verbindung](create-connection.md) für weitere Informationen. |
| Datensatz-Auswahl | Ermöglicht die Auswahl eines Datensatzes oder aller Datensätze in der Verbindung. Datensätze können nicht mehrmals ausgewählt werden. Die Standardeinstellung ist [!UICONTROL Alle Datensätze]. |
| Datumsbereichsauswahl | Start- und/oder Enddatum bearbeiten oder auswählen ![Kalender](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) , um die Auswahl für den Datenbereich zu öffnen. Wählen Sie in der Datumsbereichsauswahl einen Datumsbereich aus, indem Sie einen der vordefinierten Zeiträume verwenden (z. B. **[!UICONTROL Letzte 6 Monate]**) oder verwenden Sie den Kalender, um Start- und Enddatum auszuwählen. Auswählen **[!UICONTROL Anwenden]** , um den neuen Datenbereich anzuwenden. |
| [!UICONTROL Verfügbare Aufzeichnungen von Ereignisdaten] | Stellt die Gesamtzahl der für das Reporting verfügbaren Ereignis-Datensätze **für die gesamte Verbindung** dar. Diese Anzahl ist unabhängig von Kalendereinstellungen. Die Anzahl ändert sich, wenn Sie einen Datensatz aus der Datensatz-Auswahl auswählen oder indem Sie einen Datensatz in der Tabelle auswählen. Nach dem Hinzufügen von Daten ist die Latenz von 1-2 Stunden, damit die Daten in Berichten angezeigt werden. |
| [!UICONTROL Metriken] | Fasst die hinzugefügten/übersprungenen/gelöschten Ereignis-Datensätze sowie die Anzahl der hinzugefügten Stapel **für den ausgewählten Datensatz und den ausgewählten Datumsbereich** zusammen.<p>Auswählen **[!UICONTROL Detail überprüfen]** , um **[!UICONTROL Überprüfen der übersprungenen Details]** Popup, in dem für alle Ereignis-Datensätze oder ausgewählten Datensatz die Anzahl der übersprungenen Datensätze und der Grund aufgelistet werden.<p><img src="./assets/skipped-records.png" width="70%"/><p>Auswählen ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) mit weiteren Informationen. Für einige übersprungene Gründe, wie [!UICONTROL Leere Besucher-ID], zeigt das Popup-Fenster Beispiel-PSQL für EQS (Experience Platform für Query Service) an, das Sie in [Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=de) , um nach den übersprungenen Datensätzen im Datensatz zu suchen. Auswählen ![Kopieren](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL Beispiel-PSQL für EQS kopieren]** , um die SQL zu kopieren. |
| [!UICONTROL Hinzugefügte Datensätze] | Gibt an, wie viele Zeilen im ausgewählten Zeitraum **für den ausgewählten Datensatz und Datumsbereich** hinzugefügt wurden. Wird alle zehn Minuten aktualisiert. |
| [!UICONTROL Übersprungene Datensätze] | Gibt an, wie viele Zeilen im ausgewählten Zeitraum **für den ausgewählten Datensatz und Datumsbereich** übersprungen wurden. Gründe für das Überspringen von Datensätzen sind fehlende Zeitstempel, fehlende oder ungültige Personen-ID usw. Wird alle zehn Minuten aktualisiert. <p>Ungültige Personen-IDs (z. B. „undefiniert“ oder „00000000“ oder eine beliebige Kombination aus Zahlen und Buchstaben in einer [!UICONTROL Personen-ID], die in einem Ereignis mehr als eine Million Mal in einem bestimmten Monat auftritt) können keinem bestimmten Benutzer zugeordnet werden. Sie können nicht in das System aufgenommen werden und führen zu fehlerhafter Datenaufnahme und Berichterstellung. Um ungültige Personen-IDs zu beheben, haben Sie drei Möglichkeiten:<ul><li>Verwendung [Stitching](/help/stitching/overview.md) , um die nicht definierten Benutzer-IDs oder Benutzer-IDs mit allen Identitäten mit gültigen Benutzer-IDs zu füllen.</li><li>Leeren Sie die Benutzer-ID aus, die dann bei der Erfassung übersprungen wird (vorzuziehen sind ungültige Benutzer-IDs ohne alle IDs).</li><li>Korrigieren Sie alle ungültigen Benutzer-IDs in Ihrem System, bevor Sie die Daten aufnehmen.</li></ul> |
| [!UICONTROL Datensätze] gelöscht | Gibt an, wie viele Zeilen im ausgewählten Zeitraum **für den ausgewählten Datensatz und Datumsbereich** gelöscht wurden. Beispielsweise könnte jemand einen Datensatz in Experience Platform gelöscht haben. Wird alle zehn Minuten aktualisiert. |
| ![Suche](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) _Datensatz-Namen oder ID durchsuchen_ | Datensatzsuchfeld. Sie können die Datensatztabelle nach Datensatznamen durchsuchen oder [!UICONTROL Datensatz-ID]. |
| [!UICONTROL Datensatztabelle] | Zeigt die Datensätze an, die Teil der Verbindung sind. |
| [!UICONTROL Datensätze] | Zeigt den Namen des Datensatzes an, der Teil der Verbindung ist. Sie können den Hyperlink auswählen, um den Datensatz in der Experience Platform-Benutzeroberfläche in einer neuen Registerkarte zu öffnen. Sie können die Zeile oder das Kontrollkästchen auswählen, um nur Details für den ausgewählten Datensatz anzuzeigen. |
| [!UICONTROL Datensatz-ID] | Automatisch durch Experience Platform generiert. |
| [!UICONTROL Hinzugefügte Datensätze] | Die Anzahl der Datensatzdatensätze/Zeilen, die während des ausgewählten Zeitintervalls zu einer Verbindung hinzugefügt wurden. |
| [!UICONTROL Übersprungene Datensätze] | Die Anzahl der Datensätze/Zeilen, die während der Datenübertragung für eine Verbindung während des ausgewählten Zeitintervalls übersprungen wurden. |
| [!UICONTROL Gelöschte Datensätze] | Die Anzahl der Datensätze/Zeilen, die während des ausgewählten Zeitintervalls aus einer Verbindung entfernt wurden. |
| [!UICONTROL Batches hinzugefügt] | Anzahl der Datensatz-Batches, die zu einer Verbindung hinzugefügt wurden. |
| [!UICONTROL Zuletzt hinzugefügt] | Der Zeitstempel des neuesten Batches aus dem Datensatz, der zu einer Verbindung hinzugefügt wurde. |
| [!UICONTROL Datenquellentyp] | Der Quelltyp des Datensatzes. Sie definieren den Quelltyp beim Erstellen einer Verbindung. |
| [!UICONTROL Typ des Datensatzes] | Der Datensatztyp für diesen Datensatz. Typ kann [!UICONTROL Ereignis], [!UICONTROL Suche]oder [!UICONTROL Profil]. [Weitere Infos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=de#configure-dataset) |
| Schema | Das Experience Platform-Schema, auf dem der Datensatz basiert. |
| [!UICONTROL Neue Daten importieren] | Zeigt den Status des Imports neuer Daten für den Datensatz an: <p><span style="color:green">●</span>   **[!UICONTROL _x _on]**ob der Datensatz für den Import neuer Daten konfiguriert ist, und<p><span style="color:gray">●</span>   **[!UICONTROL _x Aus_]** wenn der Datensatz so konfiguriert ist, dass er keinen neuen Datenimport importiert. |
| [!UICONTROL Aufstockungsdaten] | Zeigt den Status der Aufstockungsdaten für den Datensatz an.<p><span style="color:red">●</span>   **[!UICONTROL _x _Aufstockungen fehlgeschlagen]**für die Anzahl fehlgeschlagener Aufstockungen,<p><span style="color:orange">●</span>   **[!UICONTROL _x _Verarbeitung von Backfilets]**für die Anzahl der Aufstockungen,<p><span style="color:green">●</span>   **[!UICONTROL _x _Aufstockungen abgeschlossen]**für die Anzahl der abgeschlossenen Aufstockungen und<p><span style="color:grey">●</span>   **[!UICONTROL _Aus_]** , falls keine Aufstockungen konfiguriert sind. |

>[!IMPORTANT]
>
>Daten, die vor dem 13. August 2021 erfasst wurden, werden nicht im [!UICONTROL Verbindungen] -Schnittstelle.

#### Verbindungs-Panel

Wenn in der Datensatztabelle kein Datensatz ausgewählt ist, werden in einem Bedienfeld auf der rechten Seite der Schnittstelle Verbindungen Verbindungsoptionen und -details angezeigt.

| Optionen/Details | Beschreibung |
| --- | --- |
| ![Aktualisieren](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL Aktualisieren] | Um die Verbindung zu aktualisieren und die Anzeige kürzlich hinzugefügter Datensätze zuzulassen, wählen Sie ![Aktualisieren](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Aktualisieren]**. |
| ![Löschen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Löschen]** | [Löschen](#delete-a-connection) diese Verbindung. |
| ![Datenansicht hinzufügen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Datenansicht erstellen]** | [Datenansicht erstellen](#create-a-data-view) auf dieser Verbindung basieren. Siehe [Datenansichten](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=de) für weitere Informationen. |
| [!UICONTROL Name der Verbindung] | Zeigt den Anzeigenamen der Verbindung an. |
| [!UICONTROL Beschreibung der Verbindung] | Zeigt eine detailliertere Beschreibung an, die den Zweck dieser Verbindung beschreibt. |
| [!UICONTROL Sandbox] | Die [Experience Platform-Sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=de) von dem aus diese Verbindung ihre Datensätze zeichnet. Diese Sandbox wurde beim ersten Erstellen der Verbindung ausgewählt. Sie kann nicht geändert werden. |
| [!UICONTROL Verbindungs-ID] | Diese ID wird im Experience Platform generiert. Sie können ![Kopieren](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) zum Kopieren der ID. |
| [!UICONTROL Datenaufrufe, die Verbindungen verwenden] | Listet alle Datenansichten auf, die diese Verbindung verwenden. |
| [!UICONTROL Neue Daten importieren] | Zeigt den Status des Imports neuer Daten für Datensätze an: <p><span style="color:green">●</span>   **[!UICONTROL _x _on]**für die Anzahl der Datensätze, die für den Import neuer Daten konfiguriert sind, und<p><span style="color:gray">●</span>   **[!UICONTROL _x Aus_]** für die Anzahl der Datensätze, für die der neue Datenimport deaktiviert ist. |
| [!UICONTROL Aufstockungsdaten] | Zeigt den Status der Aufstockungsdaten für Datensätze an.<p><span style="color:red">●</span>   **[!UICONTROL _x _Aufstockungen fehlgeschlagen]**für die Anzahl fehlgeschlagener Aufstockungen in Datensätzen,<p><span style="color:orange">●</span>   **[!UICONTROL _x _Verarbeitung von Backfilets]**für die Anzahl der Aufstockungen für die Verarbeitung in Datensätzen,<p><span style="color:green">●</span>   **[!UICONTROL _x _Aufstockungen abgeschlossen]**für die Anzahl abgeschlossener Backups für Datensätze und<p><span style="color:grey">●</span>   **[!UICONTROL _Aus_]** , falls für die Datensätze in der Verbindung keine Rückfüllungen definiert sind. |
| [!UICONTROL Erstellt von] | Zeigt den Namen der Person an, die die Verbindung hergestellt hat. |
| [!UICONTROL Zuletzt geändert] | Zeigt den Zeitstempel der letzten Änderung an der Verbindung an. |
| [!UICONTROL Zuletzt geändert von] | Zeigt die Person, die die Verbindung zuletzt geändert hat. |

#### Datensatzbedienfeld

Wenn ein Datensatz in der Datensatztabelle ausgewählt ist, werden in einem Bedienfeld auf der rechten Seite der Benutzeroberfläche &quot;Verbindungen&quot;Details zum ausgewählten Datensatz angezeigt.

| Details | Beschreibung |
| --- | --- |
| [!UICONTROL Personen-ID] | Zeigt eine Identität an, die im Datensatzschema in Experience Platform definiert wurde. Dies ist die Personen-ID, die Sie bei der Erstellung der Verbindung ausgewählt haben. Wenn Sie eine Verbindung erstellen, die Datensätze mit unterschiedlichen IDs enthält, spiegelt die Berichterstellung dies wider. Zum Zusammenführen von Datensätzen müssen Sie dieselbe Personen-ID für alle Datensätze verwenden. |
| [!UICONTROL Schlüssel] | Zeigt den Schlüssel an, den Sie für einen Lookup-Datensatz angegeben haben. |
| [!UICONTROL Übereinstimmender Schlüssel] | Zeigt den übereinstimmenden Schlüssel an, den Sie für einen Lookup-Datensatz angegeben haben. |
| [!UICONTROL Zeitstempel] | Zeigt den für einen Ereignis-Datensatz definierten Zeitstempel an. |
| [!UICONTROL Verfügbare Datensätze] | Stellt die Gesamtzahl der Zeilen dar, die für diesen Datensatz in dem im Kalender ausgewählten Zeitraum aufgenommen wurden. Es gibt keine Latenz im Hinblick darauf, ab wann die Daten nach dem Hinzufügen in Berichten angezeigt werden. Wenn Sie jedoch eine brandneue Verbindung erstellen, wird [Latenz](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=de#3.-getting-data-into-customer-journey-analytics). |
| [!UICONTROL Hinzugefügte Datensätze] | Gibt an, wie viele Zeilen im ausgewählten Zeitraum hinzugefügt wurden. |
| [!UICONTROL Gelöschte Datensätze] | Gibt an, wie viele Datensätze im ausgewählten Zeitraum gelöscht wurden. |
| [!UICONTROL Batches hinzugefügt] | Zeigt, wie viele Datenstapel diesem Datensatz hinzugefügt wurden. |
| [!UICONTROL Übersprungene Datensätze] | Zeigt, wie viele Zeilen während der Aufnahme im ausgewählten Zeitraum übersprungen wurden.<p>Gründe für das Überspringen von Datensätzen sind: Fehlende Zeitstempel, fehlende oder ungültige Personen-ID usw. Wird alle zehn Minuten aktualisiert.<p>Ungültige Personen-IDs (z. B. „undefiniert“ oder „00000000“ oder eine beliebige Kombination aus Zahlen und Buchstaben in einer [!UICONTROL Personen-ID], die in einem Ereignis mehr als eine Million Mal in einem bestimmten Monat auftritt) können keinem bestimmten Benutzer zugeordnet werden. Sie können nicht in das System aufgenommen werden und führen zu fehlerhafter Datenaufnahme und Berichterstellung. Um ungültige Personen-IDs zu beheben, haben Sie drei Möglichkeiten:<ul><li>Verwendung [Stitching](/help/stitching/overview.md) , um die nicht definierten Benutzer-IDs oder Benutzer-IDs mit allen Identitäten mit gültigen Benutzer-IDs zu füllen.</li><li>Leeren Sie die Benutzer-ID aus, die dann bei der Erfassung übersprungen wird (vorzuziehen sind ungültige Benutzer-IDs oder Benutzer-IDs ohne Inhalt).</li><li>Korrigieren Sie alle ungültigen Benutzer-IDs in Ihrem System, bevor Sie die Daten aufnehmen.</li></ul> |
| [!UICONTROL Zuletzt hinzugefügt] | Zeigt den Zeitpunkt, zu dem der letzte Stapel hinzugefügt wurde. |
| [!UICONTROL Neue Daten importieren] | Zeigt den Status des Imports neuer Daten für den Datensatz an: <p><span style="color:green">●</span>   **[!UICONTROL _x _on]**ob der Datensatz für den Import neuer Daten konfiguriert ist, und<p><span style="color:gray">●</span>   **[!UICONTROL _x Aus_]** wenn der Datensatz so konfiguriert ist, dass er keinen neuen Datenimport importiert. |
| [!UICONTROL Aufstockungsdaten] | Zeigt den Status der Aufstockungsdaten für den Datensatz an.<p><span style="color:red">●</span>   **[!UICONTROL _x _Aufstockungen fehlgeschlagen]**für die Anzahl fehlgeschlagener Aufstockungen,<p><span style="color:orange">●</span>   **[!UICONTROL _x _Verarbeitung von Backfilets]**für die Anzahl der Aufstockungen,<p><span style="color:green">●</span>   **[!UICONTROL _x _Aufstockungen abgeschlossen]**für die Anzahl der abgeschlossenen Aufstockungen und<p><span style="color:grey">●</span>   **[!UICONTROL _Aus_]** , falls keine Aufstockungen konfiguriert sind.<p>Um ein Dialogfeld mit einem Überblick über die früheren Rückstände für den Datensatz anzuzeigen, wählen Sie <img src="./assets/pastbackfill.svg" alt="Frühere Aufstockungen" width="2%" /> **[!UICONTROL Frühere Backfilets]**. |
| [!UICONTROL Datenquellentyp] | Datenquellentyp, wie beim Hinzufügen des Datensatzes zur Verbindung definiert. |
| [!UICONTROL Typ des Datensatzes] | Entweder [!UICONTROL Ereignis], [!UICONTROL Suche] oder [!UICONTROL Profil]. [Weitere Infos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=de#configure-dataset) |
| [!UICONTROL Schema] | Zeigt das Experience Platform-Schema an, auf dem dieser Datensatz basiert. |
| [!UICONTROL Datensatz-ID] | Diese Datensatz-ID wird im Experience Platform generiert. |


## Nutzung

Die [!UICONTROL Nutzung] -Schnittstelle zeigt die Verwendung von aufgenommenen und berichtspflichtigen Zeilen über alle Verbindungen hinweg. Diese Schnittstelle unterstützt Sie dabei festzustellen, ob Ihre Customer Journey Analytics-Nutzung den vertraglichen Vereinbarungen entspricht.

Wählen Sie die **[!UICONTROL Nutzung]** -Tab, um auf die Benutzeroberfläche zuzugreifen.

So melden Sie die Verwendung:

1. Wählen Sie eine **[!UICONTROL Zeitraum]**. Sie können zwischen **[!UICONTROL Letzte 6 Monate]**, **[!UICONTROL Jahr bis Datum]** oder **[!UICONTROL Letzte 2 Jahre]**.
1. Wählen Sie eine **[!UICONTROL Intervall]**. Sie können zwischen **[!UICONTROL Monatlich]** oder **[!UICONTROL Vierteljährlich]**.

Für [!UICONTROL Aufgenommene Zeilen]:

* Ein Feld zeigt die [!UICONTROL Ingesamt] Anzahl der aufgenommenen Zeilen.
* Ein Feld zeigt die Anzahl der aufgenommenen Zeilen für die [!UICONTROL Letzter Monat] und die Veränderung in % (erkennbar an <span style="color:green">lake</span> oder <span style="color:c64545">ù</span>) aus dem Vormonat.
* ein Liniendiagramm anzeigt,  <span style="color:53b2ad">◼︎</span> Aufgezogene Zeilen und <span style="color:4046c3">◼︎</span> Monatlich aufgenommene Zeilen.<br/>Sie können den Mauszeiger über einen Datenpunkt für jede Zeile im Liniendiagramm bewegen, um ein Popup mit dem Datum und der Anzahl der Zeilen für den ausgewählten Datenpunkt anzuzeigen.


Für [!UICONTROL Meldepflichtige Zeilen]:

* ein Feld angezeigt wird [!UICONTROL Ingesamt] Anzahl der berichtspflichtigen Zeilen.
* Ein Feld zeigt die Anzahl der berichtspflichtigen Zeilen für die [!UICONTROL Letzter Monat] und die Veränderung in % (erkennbar an <span style="color:green">lake</span> oder <span style="color:c64545">ù</span>) aus dem Vormonat.
* ein Liniendiagramm anzeigt,  <span style="color:53b2ad">◼︎</span> Zusammenfassende berichtspflichtige Zeilen und <span style="color:4046c3">◼︎</span> Berichterstattbare Zeilen pro Monat.<br/>Sie können den Mauszeiger über einen Datenpunkt für jede Zeile im Liniendiagramm bewegen, um ein Popup mit dem Datum und der Anzahl der Zeilen für den ausgewählten Datenpunkt anzuzeigen.


>[!MORELIKETHIS]
>
>[Verbindungseinstellungen anzeigen, beheben und ändern](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja.html) Tutorial.
