---
title: Erfahren Sie, wie Sie Verbindungen in Customer Journey Analytics verwalten.
description: Beschreibt, wie Verbindungen zu Experience Platform-Datensätzen in Customer Journey Analytics (Customer Journey Analytics) verwaltet werden.
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '4023'
ht-degree: 26%

---

# Verwalten von Verbindungen

Nachdem Sie [eine oder mehrere Verbindungen erstellt oder bearbeitet haben](/help/connections/create-connection.md) können Sie sie in &quot;**[!UICONTROL &quot;]**. Verbindungen ermöglichen Ihnen Folgendes:

* Zeigen Sie alle Verbindungen auf einen Blick an, einschließlich Eigentümer, Sandbox und des Zeitpunkts der Erstellung und Änderung der Verbindungen.
* Bearbeiten einer Verbindung.
* Eine Verbindung löschen.
* Eine Datenschicht aus einer Verbindung erstellen.
* Lassen Sie sich alle Datensätze in einer Verbindung anzeigen.
* Überprüfen Sie den Status der Datensätze Ihrer Verbindung und den Status des Aufnahmevorgangs. Beispielsweise, wann Ihre Daten verfügbar sind, damit Sie mit der Berichterstellung und Analyse in Analysis Workspace beginnen können.
* Identifizieren Sie alle Datendiskrepanzen, die aufgrund einer Fehlkonfiguration entstanden sind. Fehlen Zeilen? Wenn ja, welche Zeilen fehlen und warum? Haben Sie Verbindungen falsch konfiguriert und dadurch das Fehlen von Daten im Customer Journey Analytics verursacht?
* Erhalten Sie Einblicke in die Verwendung aufgenommener und berichtspflichtiger Zeilen über alle Verbindungen hinweg.

[!UICONTROL Verbindungen] verfügt über zwei Schnittstellen: [[!UICONTROL List]](#list) und [[!UICONTROL Usage]](#usage).


## Liste

Die [!UICONTROL List]-Schnittstelle ist die Standardschnittstelle für Verbindungen. Wenn sie nicht ausgewählt ist, wählen Sie die **[!UICONTROL Liste]**, um auf die Benutzeroberfläche zuzugreifen.

![Listenansicht](assets/list-view.png)

Die [!UICONTROL List] zeigt eine Tabelle aller verfügbaren Verbindungen an. Sie können im Feld Suchen (Search) schnell ![ Verbindung ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).

Die folgenden Spalten oder Symbole sind in der Tabelle verfügbar.

| Spalte oder Symbol | Beschreibung |
| --- | --- |
| [!UICONTROL Name] | Der Anzeigename der Verbindung. Um die Details der Verbindung anzuzeigen, klicken Sie auf den Hyperlink-Namen. Siehe [Verbindungsdetails](#connection-details). |
| ![Information](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Um Informationen zu [!UICONTROL Enthaltene Datensätze], [!UICONTROL Sandbox], [!UICONTROL Inhaber] und mehr anzuzeigen, klicken Sie auf ![Informationen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) neben dem Verbindungsnamen.<p>Ein Popup-Fenster mit Details wird angezeigt. <p><img src="./assets/conn-info.png" alt="Verbindungsinformationen anzeigen" width="400"/> |
| ![Datenansicht](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | Um [Datenansicht zu erstellen](#create-a-data-view) für die Verbindung wählen Sie ![Datenansicht](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg). Dieses Symbol wird nur angezeigt, wenn der Verbindung bereits keine Datenansicht zugeordnet ist. |
| ![Mehr](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Wählen Sie ![Mehr](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) aus, um: <p>![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [Bearbeiten](#edit-a-connection) einer Verbindung.<p>![Löschen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [Löschen](#delete-a-connection) einer Verbindung.<p>![Datenansicht](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [Neue Datenansicht erstellen](#create-a-data-view). So erstellen Sie zusätzliche Datenansichten für die Verbindung. |
| [!UICONTROL Datensätze] | Eine oder mehrere Verknüpfungen zu den Datensätzen, die Teil der Verbindung sind. Sie können den Datensatz-Hyperlink auswählen, um den Datensatz in der Verbindung anzuzeigen. Wenn weitere Datensätze Teil der ausgewählten Verbindung sind, wählen Sie **[!UICONTROL +*x* more]** aus, um das Bedienfeld **[!UICONTROL Datensätze enthalten]** anzuzeigen. In diesem Bedienfeld werden Links zu allen Datensätzen und eine Option zum Suchen nach einem bestimmten Datensatz angezeigt, der Teil der Verbindung ist.<p><img src="./assets/datasets-included.png" alt="Enthaltene Datensätze" width="400"/><p>Wenn Sie einen Datensatznamen auswählen, wird der Datensatz in der Experience Platform-Benutzeroberfläche auf einer neuen Registerkarte geöffnet. |
| [!UICONTROL Sandbox] | Die [Experience Platform-Sandbox](https://experienceleague.adobe.com/de/docs/experience-platform/sandbox/home) aus der diese Verbindung ihre Datensätze zieht. Diese Sandbox wurde beim erstmaligen Erstellen der Verbindung ausgewählt. Sie kann nicht geändert werden. |
| [!UICONTROL Inhaber] | Die Person, die die Verbindung hergestellt hat. |
| [!UICONTROL Importieren neuer Daten] | Der Status des Imports neuer Daten für Datensätze: <p>![Status grün](assets/status-green.svg))    **[!UICONTROL _x _Ein]** für Datensätze, die zum Importieren neuer Daten konfiguriert sind, und<p>![Status grau](assets/status-gray.svg)   **[!UICONTROL _x Aus_]** für Datensätze, die nicht für den Import neuer Daten konfiguriert sind. |
| [!UICONTROL Erstellt am] | Der Zeitstempel, zu dem die Verbindung erstellt wurde. |
| [!UICONTROL Zuletzt geändert] | Der Zeitstempel, wann die Verbindung zuletzt aktualisiert wurde. |
| [!UICONTROL Aufstockungsdaten] | Der Status für die Aufstockung von Daten in allen Datensätzen.<p>![Status rot](assets/status-red.svg)   **[!UICONTROL _x _Aufstockungen fehlgeschlagen]**für die Anzahl der fehlgeschlagenen Aufstockungen über Datensätze hinweg,<p>![Status orange](assets/status-orange.svg)   **[!UICONTROL _x _Aufstockungsverarbeitung]**für die Anzahl der Verarbeitungs-Aufstockungen über Datensätze hinweg,<p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _Aufstockungen abgeschlossen]** für die Anzahl der abgeschlossenen Aufstockungen für Datensätze und<p>![Status grau](assets/status-gray.svg)   **[!UICONTROL _Aus_]** falls für die Datensätze in der Verbindung keine Aufstockungen definiert sind. |

Um zu konfigurieren, welche Spalten angezeigt werden sollen, wählen ![Spalteneinstellungen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) aus. Dadurch wird das Dialogfeld **Tabelle anpassen** angezeigt, in dem Sie Spalten in der Tabelle aktivieren oder deaktivieren können.

### Verbindung bearbeiten

1. Klicken Sie ![Mehr](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) neben dem Verbindungsnamen
1. Wählen ![im](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) die Option **[!UICONTROL Bearbeiten]** aus.

Alternativ haben Sie folgende Möglichkeiten:

1. Wählen Sie die Verbindungszeile aus.

1. Wählen ![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Bearbeiten]** aus der blauen Leiste aus.

Beim Bearbeiten einer Verbindung haben Sie folgende Möglichkeiten:

* Starten und Beenden des Imports neuer Daten
* Eine Verbindung umbenennen.
* Aktualisieren Sie die Datensätze.
* Entfernen Sie Datensätze aus den Verbindungen.

Siehe [Erstellen oder Bearbeiten einer Verbindung](create-connection.md) für weitere Informationen.


### Eine Verbindung löschen {#connections-delete}

1. Klicken Sie ![Mehr](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) neben dem Verbindungsnamen.
1. Wählen Sie ![Löschen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Löschen]** aus.

Alternativ haben Sie folgende Möglichkeiten:

1. Wählen Sie die Verbindungszeile aus.

1. Wählen Sie ![ blauen Balken ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg)Löschen **[!UICONTROL Löschen]** aus.

Wenn Sie eine Verbindung löschen, zeigt das Bedienfeld **[!UICONTROL Verbindung löschen]** an, welche Datenansichten gelöscht werden und welche Workspace-Projekte betroffen sind.

![Verbindung löschen](assets/delete-connection.png)

Wählen Sie **[!UICONTROL Fortfahren]** aus, um die Verbindung zu löschen.

Weitere Informationen [Löschen einer Verbindung finden](/help/technotes/deletion.md) unter „Auswirkungen des Löschens“.


### Datenansicht für eine Verbindung erstellen

* Wenn der Verbindung keine Datenansicht zugeordnet ist:

   1. Wählen ![Datenansicht hinzufügen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) neben dem Verbindungsnamen aus.

* Wenn für die Verbindung bereits eine oder mehrere Datenansichten erstellt wurden:

   1. Klicken Sie ![Mehr](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) neben dem Verbindungsnamen.
   1. Wählen ![Datenansicht hinzufügen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Neue Datenansicht erstellen]**.

Alternativ haben Sie folgende Möglichkeiten:

1. Wählen Sie die Verbindungszeile aus.

1. Wählen Sie ![Datenansicht hinzufügen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Datenansicht erstellen]** in der blauen Schaltflächenleiste aus.

Weitere Informationen finden Sie unter [Erstellen oder Bearbeiten einer Datenansicht](/help/data-views/create-dataview.md).

### Verbindungsdetails {#connection-detail}

Um zu den Details für eine Verbindung zu wechseln, wählen Sie einen Verbindungsnamen in der Tabelle Verbindungen aus.

![Fenster „Alle Datensätze“ mit den Widgets und Einstellungen](assets/conn-details.png)

Die Schnittstelle Verbindungsdetails bietet eine detaillierte Ansicht des Status einer Verbindung. Sie haben folgende Möglichkeiten:

* Überprüfen Sie den Status der Datensätze Ihrer Verbindung und des Aufnahmevorgangs.
* Identifizieren Sie Konfigurationsprobleme, die zu übersprungenen oder gelöschten Datensätzen führen können.
* Finden Sie heraus, wann die Daten für das Reporting verfügbar sind.

| Benutzeroberfläche | Beschreibung |
| --- | --- |
| ![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [!UICONTROL Verbindung bearbeiten] | Um die Details einer Verbindung zu bearbeiten, wählen Sie ![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Verbindung bearbeiten]** aus. Siehe [Erstellen oder Bearbeiten einer Verbindung](create-connection.md) für weitere Informationen. |
| Datensatz-Auswahl | Ermöglicht die Auswahl eines Datensatzes oder aller Datensätze in der Verbindung. Datensätze können nicht mehrmals ausgewählt werden. Die Standardeinstellung ist [!UICONTROL Alle Datensätze]. |
| Datumsbereichsauswahl | Bearbeiten Sie das Start- und Enddatum oder wählen Sie ![Kalender](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg), um die Datumsbereichsauswahl zu öffnen. Wählen Sie in der Datumsbereichsauswahl einen Datumsbereich aus, indem Sie einen der vordefinierten Zeiträume verwenden (z. B. **[!UICONTROL Letzte 6 Monate]**) oder verwenden Sie den Kalender, um das Start- und Enddatum auszuwählen. Wählen Sie **[!UICONTROL Anwenden]** aus, um den neuen Datumsbereich anzuwenden. |
| [!UICONTROL Datensätze von Ereignisdaten verfügbar] | Die Gesamtzahl der für das Reporting verfügbaren Ereignis-Datensatzzeilen (**für die gesamte Verbindung**. Diese Anzahl ist unabhängig von Kalendereinstellungen. Die Anzahl ändert sich, wenn Sie einen Datensatz aus der Datensatzauswahl oder durch Auswahl eines Datensatzes in der Tabelle auswählen. Nachdem Daten hinzugefügt wurden, dauert es 1-2 Stunden, bis die Daten im Reporting angezeigt werden. |
| [!UICONTROL Metriken] | Zusammenfassen der hinzugefügten, übersprungenen und gelöschten Ereignis-, Lookup-, Profil- und Zusammenfassungsdatensätze sowie der Anzahl der hinzugefügten Batches. Diese Metriken basieren auf **dem ausgewählten Datensatz und Datumsbereich**.<p>Wählen Sie **[!UICONTROL Detail überprüfen]** aus, um das Popup **[!UICONTROL Übersprungene Details überprüfen]** anzuzeigen. Das Popup-Fenster listet die Anzahl der übersprungenen Datensätze und den Grund für alle Ereignis-Datensätze oder ausgewählten Datensätze auf.<p><img src="./assets/skipped-records.png" width="500"/><p>Wählen Sie ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)-Popup mit weiteren Informationen aus. Aus einigen übersprungenen Gründen, z. B. [!UICONTROL Leere Besucher-ID], zeigt das Popup Beispiel-PSQL für EQS (Experience Platform für Abfrage-Service) an, das Sie in [Abfrage-Service](https://experienceleague.adobe.com/de/docs/experience-platform/query/home) verwenden können, um die übersprungenen Datensätze im Datensatz abzufragen. Wählen Sie ![Kopieren](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL Beispiel-PSQL für EQS kopieren]**, um die SQL zu kopieren. |
| [!UICONTROL Hinzugefügte Datensätze] | Gibt an, wie viele Zeilen im ausgewählten Zeitraum **für den ausgewählten Datensatz und Datumsbereich** hinzugefügt wurden. Wird alle zehn Minuten aktualisiert. |
| [!UICONTROL Übersprungene Datensätze] | Gibt an, wie viele Zeilen im ausgewählten Zeitraum **für den ausgewählten Datensatz und Datumsbereich** übersprungen wurden. Gründe für das Überspringen von Datensätzen sind: fehlende Zeitstempel, fehlende oder ungültige Personen-ID usw. Wird alle zehn Minuten aktualisiert. <p>Ungültige Personen-IDs (z. B. `undefined` oder `00000000` oder eine beliebige Kombination aus Zahlen und Buchstaben in einer [!UICONTROL Personen-ID], die in einem Ereignis mehr als eine Million Mal in einem bestimmten Monat auftritt) sind IDs, die keinem bestimmten Benutzer bzw. keiner bestimmten Person zugeordnet werden können. Diese Zeilen können nicht in das System aufgenommen werden und führen zu fehlerhafter Aufnahme und Berichterstellung. Um ungültige Personen-IDs zu beheben, haben Sie drei Möglichkeiten:<ul><li>Verwenden Sie [Zusammenfügen](/help/stitching/overview.md) um die Benutzer-IDs, die nicht definiert sind oder nur Nullen enthalten, mit gültigen Benutzer-IDs zu füllen.</li><li>Blenden Sie die Benutzer-ID aus, die dann während der Aufnahme übersprungen werden (was ungültigen oder Benutzer-IDs mit nur null vorzuziehen ist).</li><li>Korrigieren Sie alle ungültigen Benutzer-IDs in Ihrem System, bevor Sie die Daten aufnehmen.</li></ul> |
| [!UICONTROL Datensätze] gelöscht | Gibt an, wie viele Zeilen im ausgewählten Zeitraum **für den ausgewählten Datensatz und Datumsbereich** gelöscht wurden. Beispielsweise könnte jemand einen Datensatz in [!DNL Experience Platform] gelöscht haben. Wird alle zehn Minuten aktualisiert.<p>In einigen Szenarien kann dieser Wert auch ersetzte Datensätze enthalten, wie etwa bei der Zuordnung oder bei einigen Aktualisierungen von Lookup-Datensätzen. Sehen Sie sich dieses Beispiel an:</p><ul><li>Sie laden einen Datensatz in einen XDM Individual Profile-Datensatz hoch, wobei die Customer Journey Analytics so konfiguriert ist, dass sie als Profilsuchdaten aufnimmt. In den Verbindungsdetails würde dieser Datensatz 1 hinzugefügten Datensatz anzeigen.</li><li>Sie laden ein Duplikat des ursprünglichen Datensatzes in denselben AEP-Datensatz hoch, der jetzt zwei Datensätze enthält. Beim Customer Journey Analytics wird der zusätzliche Datensatz aus dem Profilsuchdatensatz aufgenommen. Da für diese Personen-ID bereits ein Profildatensatz in der Verbindung aufgenommen wurde, löscht Customer Journey Analytics seine frühere Version und fügt die neuen Profildaten hinzu. In den Verbindungsdetails würde diese Aktion bedeuten, dass 1 Datensatz hinzugefügt und 1 Datensatz gelöscht wird, da Customer Journey Analytics nur die neuesten Profilsuchdaten für eine aufgenommene Personen-ID beibehält.</li><li>Insgesamt enthält der AEP-Datensatz zwei Datensätze, die zufällig identisch sind. Separat zeigen die Customer Journey Analytics-Verbindungsdetails den Status der aufgenommenen Daten an: 2 Datensätze wurden hinzugefügt und 1 Datensatz für diesen Profildatensatz gelöscht. </li></ul> |
| ![Suche](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) _Datensatznamen oder ID suchen_ | Datensatz-Suchfeld. Sie können die Datensatztabelle nach Datensatznamen oder [!UICONTROL Datensatz-ID) ]. |
| [!UICONTROL Tabelle Datensätze] | Die Datensätze, die Teil der Verbindung sind. |
| [!UICONTROL Datensätze] | Der Name des Datensatzes, der Teil der Verbindung ist. Sie können den Hyperlink auswählen, um den Datensatz in der Experience Platform-Benutzeroberfläche auf einer neuen Registerkarte zu öffnen. Sie können die Zeile oder das Kontrollkästchen aktivieren, um nur Details für den ausgewählten Datensatz anzuzeigen. |
| [!UICONTROL Datensatz-ID] | Automatisch durch Experience Platform generiert. |
| [!UICONTROL Hinzugefügte Datensätze] | Die Anzahl der Datensatzdatensätze (Zeilen), die einer Verbindung im ausgewählten Zeitintervall hinzugefügt wurden. |
| [!UICONTROL Übersprungene Datensätze] | Die Anzahl der bei der Datenübertragung für eine Verbindung übersprungenen Datensatzdatensätze (Zeilen) im ausgewählten Zeitintervall. |
| [!UICONTROL Gelöschte Datensätze] | Die Anzahl der Datensätze (Zeilen), die während des ausgewählten Zeitintervalls aus einer Verbindung entfernt wurden. |
| [!UICONTROL Batches hinzugefügt] | Die Anzahl der Datensatz-Batches wurde einer Verbindung hinzugefügt. |
| [!UICONTROL Zuletzt hinzugefügt] | Der Zeitstempel des letzten Batches aus dem Datensatz, der einer Verbindung hinzugefügt wurde. |
| [!UICONTROL Datenquellentyp] | Der Quelltyp des Datensatzes. Sie definieren den Quelltyp beim Erstellen einer Verbindung. |
| [!UICONTROL Typ des Datensatzes] | Der Datensatztyp für diesen Datensatz. Der Typ kann [!UICONTROL Ereignis], [!UICONTROL Profil], [!UICONTROL Suche] oder [!UICONTROL Zusammenfassung]. [Weitere Infos](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-connections/create-connection) |
| Schema | Das Experience Platform-Schema, auf dem der Datensatz basiert. |
| [!UICONTROL Importieren neuer Daten] | Der Status des Imports neuer Daten für den Datensatz: <p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _Ein]**wenn der Datensatz für den Import neuer Daten konfiguriert ist, und<p>![Status grau](assets/status-gray.svg)   **[!UICONTROL _x Aus_]** wenn der Datensatz so konfiguriert ist, dass er keinen neuen Datenimport importiert. |
| [!UICONTROL Daten transformieren] | Der Umwandlungsstatus von anwendbaren B2B-Lookup-Datensätzen. Weitere Informationen finden Sie unter [Umwandeln von Datensätzen für B2B-Suchen](transform-datasets-b2b-lookups.md).<p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _Ein]**für entsprechende Datensätze, die für die Umwandlung aktiviert sind, <p>![Status grau](assets/status-gray.svg)   **[!UICONTROL _x Aus_]** für entsprechende Datensätze, die nicht für die Umwandlung aktiviert sind, und<p>**[!UICONTROL Nicht zutreffend]** für alle anderen Datensätze, nicht anwendbar für die Umwandlung. |
| [!UICONTROL Aufstockungsdaten] | Der Status der Aufstockungsdaten für den Datensatz.<p>![Status rot](assets/status-red.svg)   **[!UICONTROL _x _Aufstockungen fehlgeschlagen]**für die Anzahl fehlgeschlagener Aufstockungen,<p>![Status rot](assets/status-orange.svg)   **[!UICONTROL _x _Aufstockungsverarbeitung]**für die Anzahl der verarbeiteten Aufstockungen,<p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _Aufstockungen abgeschlossen]**für die Anzahl der abgeschlossenen Aufstockungen und<p>![Status grau](assets/status-gray.svg)   **[!UICONTROL _Aus_]** falls keine Aufstockungen konfiguriert sind. |
| [!UICONTROL Importieren neuer Daten] | Der Status des Imports neuer Daten für den Datensatz: <p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _Ein]**wenn der Datensatz für den Import neuer Daten konfiguriert ist, und<p>![Status grau](assets/status-gray.svg)   **[!UICONTROL _x Aus_]** wenn der Datensatz so konfiguriert ist, dass er keine neuen Daten importiert. |
| [!UICONTROL Aufstockungsdaten] | Der Status der Aufstockungsdaten für den Datensatz.<p>![Status rot](assets/status-red.svg)   **[!UICONTROL _x _Aufstockungen fehlgeschlagen]**für die Anzahl fehlgeschlagener Aufstockungen,<p>![Status rot](assets/status-orange.svg)   **[!UICONTROL _x _Aufstockungsverarbeitung]**für die Anzahl der verarbeiteten Aufstockungen,<p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _Aufstockungen abgeschlossen]**für die Anzahl der abgeschlossenen Aufstockungen und<p>![Status grau](assets/status-gray.svg)   **[!UICONTROL _Aus_]** falls keine Aufstockungen konfiguriert sind. |

>[!IMPORTANT]
>
>Daten, die vor dem 13. August 2021 aufgenommen wurden, werden in der Schnittstelle [!UICONTROL Verbindungen] nicht angezeigt.

#### Anschlussfeld

Wenn kein Datensatz in der Datensatztabelle ausgewählt ist, zeigt ein Bedienfeld auf der rechten Seite der Verbindungsschnittstelle Verbindungsoptionen und -details an.

| Optionen | Beschreibung |
| --- | --- |
| ![Aktualisieren](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL Aktualisieren] | Um die Verbindung zu aktualisieren und die Anzeige kürzlich hinzugefügter Datensätze zuzulassen, wählen Sie ![Aktualisieren](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Aktualisieren]** aus. |
| ![Löschen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Löschen]** | [Löschen](#delete-a-connection) diese Verbindung. |
| ![Datenansicht hinzufügen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Datenansicht erstellen]** | [Erstellen einer Datenansicht](#create-a-data-view) basierend auf dieser Verbindung. Weitere Informationen finden [ unter ](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/data-views)Datenansichten“. |
| [!UICONTROL Name der Verbindung] | Der Anzeigename der Verbindung. |
| [!UICONTROL Beschreibung der Verbindung] | Eine detailliertere Beschreibung, die den Zweck dieser Verbindung beschreibt. |
| [!UICONTROL Sandbox] | Die [Experience Platform-Sandbox](https://experienceleague.adobe.com/de/docs/experience-platform/sandbox/home) aus der diese Verbindung ihre Datensätze abruft. Diese Sandbox wurde beim erstmaligen Erstellen der Verbindung ausgewählt. Sie kann nicht geändert werden. |
| [!UICONTROL Verbindungs-ID] | Diese ID wird in Experience Platform generiert. Sie können ![Kopieren](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) verwenden, um die ID zu kopieren. |
| [!UICONTROL Datenaufrufe, die Verbindungen verwenden] | Listet alle Datenansichten auf, die diese Verbindung verwenden. |
| [!UICONTROL Neue Daten importieren] | Der Status des Imports neuer Daten für Datensätze: <p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _Ein]**für die Anzahl der Datensätze, die für den Import neuer Daten konfiguriert sind, und<p>![Status grau](assets/status-gray.svg)   **[!UICONTROL _x Aus_]** für wie viele Datensätze der neue Datenimport deaktiviert ist. |
| [!UICONTROL Aufstockungsdaten] | Der Status der Aufstockungsdaten für Datensätze.<p>![Status rot](assets/status-red.svg)   **[!UICONTROL _x _Aufstockungen fehlgeschlagen]**für die Anzahl der fehlgeschlagenen Aufstockungen über Datensätze hinweg,<p>![Status rot](assets/status-orange.svg)   **[!UICONTROL _x _Aufstockungsverarbeitung]**für die Anzahl der Verarbeitungs-Aufstockungen über Datensätze hinweg,<p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _Aufstockungen abgeschlossen]**für die Anzahl der abgeschlossenen Aufstockungen für Datensätze und<p>![Status grau](assets/status-gray.svg)   **[!UICONTROL _Aus_]** falls für die Datensätze in der Verbindung keine Aufstockungen definiert sind. |
| Daten transformieren | Der Umwandlungsstatus von anwendbaren B2B-Lookup-Datensätzen. Weitere Informationen finden Sie unter [Umwandeln von Datensätzen für B2B-Suchen](transform-datasets-b2b-lookups.md).<p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _Ein]**für die Anzahl der für die Umwandlung aktivierten Datensätze. |
| [!UICONTROL Erstellt von] | Der Name der Person, die die Verbindung hergestellt hat. |
| [!UICONTROL Zuletzt geändert] | Der Zeitstempel der letzten Änderung der Verbindung. |
| [!UICONTROL Zuletzt geändert von] | Die Person, die die Verbindung zuletzt geändert hat. |

#### Datensatz-Panel

Wenn ein Datensatz in der Datensatztabelle ausgewählt ist, werden in einem Bedienfeld auf der rechten Seite der Verbindungsschnittstelle Details zum ausgewählten Datensatz angezeigt.

| Details | Beschreibung |
| --- | --- |
| [!UICONTROL Personen-ID] | Eine Identität, die im Datensatzschema auf der Experience Platform definiert wurde. Diese Identität ist die Personen-ID, die Sie bei der Erstellung der Verbindung ausgewählt haben. Wenn Sie eine Verbindung erstellen, die Datensätze mit unterschiedlichen IDs enthält, spiegelt die Berichterstellung dies wider. Um Datensätze zusammenzuführen, müssen Sie in allen Datensätzen dieselbe Personen-ID verwenden. |
| [!UICONTROL Schlüssel] | Der Schlüssel, den Sie für einen Such-Datensatz angegeben haben. |
| [!UICONTROL Übereinstimmender Schlüssel] | Der übereinstimmende Schlüssel, den Sie für einen Such-Datensatz angegeben haben. |
| [!UICONTROL Zeitstempel] | Der für einen Ereignis-Datensatz definierte Zeitstempel. |
| [!UICONTROL Verfügbare Datensätze] | Die Gesamtzahl der Zeilen, die für diesen Datensatz in dem im Kalender ausgewählten Zeitraum aufgenommen wurden. Es gibt keine Latenz im Hinblick darauf, ab wann die Daten nach dem Hinzufügen in Berichten angezeigt werden. Wenn Sie jedoch eine brandneue Verbindung erstellen, gibt es [Latenz](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-faq). |
| [!UICONTROL Hinzugefügte Datensätze] | Wie viele Zeilen im ausgewählten Zeitraum hinzugefügt wurden. |
| [!UICONTROL Gelöschte Datensätze] | Wie viele Datensätze wurden im ausgewählten Zeitraum gelöscht. |
| [!UICONTROL Batches hinzugefügt] | Wie viele Datenstapel diesem Datensatz hinzugefügt wurden. |
| [!UICONTROL Übersprungene Datensätze] | Wie viele Zeilen während der Aufnahme im ausgewählten Zeitraum übersprungen wurden.<p>Gründe für das Überspringen von Datensätzen sind: fehlende Zeitstempel, fehlende oder ungültige Personen-ID usw. Wird alle zehn Minuten aktualisiert.<p>Ungültige Personen-IDs (z. B. `undefined` oder `00000000` oder eine beliebige Kombination aus Zahlen und Buchstaben in einer [!UICONTROL Personen-ID], die in einem Ereignis mehr als eine Million Mal in einem bestimmten Monat auftritt) sind IDs, die keinem bestimmten Benutzer bzw. keiner bestimmten Person zugeordnet werden können. Diese Zeilen können nicht in das System aufgenommen werden und führen zu fehlerhafter Aufnahme und Berichterstellung. Um ungültige Personen-IDs zu beheben, haben Sie drei Möglichkeiten:<ul><li>Verwenden Sie [Zusammenfügen](/help/stitching/overview.md) um die Benutzer-IDs, die nicht definiert sind oder nur Nullen enthalten, mit gültigen Benutzer-IDs zu füllen.</li><li>Blenden Sie die Benutzer-ID aus, die dann während der Aufnahme übersprungen wird (was ungültigen oder Benutzer-IDs mit nur null vorzuziehen ist).</li><li>Korrigieren Sie alle ungültigen Benutzer-IDs in Ihrem System, bevor Sie die Daten aufnehmen.</li></ul> |
| [!UICONTROL Zuletzt hinzugefügt] | Der Zeitstempel, der dem letzten Batch hinzugefügt wurde. |
| [!UICONTROL Importieren neuer Daten] | Der Status des Imports neuer Daten für den Datensatz: <p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _Ein]**wenn der Datensatz für den Import neuer Daten konfiguriert ist, und<p>![Status grau](assets/status-gray.svg)   **[!UICONTROL _x Aus_]** wenn der Datensatz so konfiguriert ist, dass er keine neuen Daten importiert. |
| [!UICONTROL Aufstockungsdaten] | Der Status der Aufstockungsdaten für den Datensatz.<p>![Status rot](assets/status-red.svg)   **[!UICONTROL _x _Aufstockungen fehlgeschlagen]**für die Anzahl fehlgeschlagener Aufstockungen,<p>![Status rot](assets/status-orange.svg)   **[!UICONTROL _x _Aufstockungsverarbeitung]**für die Anzahl der verarbeiteten Aufstockungen,<p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _Aufstockungen abgeschlossen]**für die Anzahl der abgeschlossenen Aufstockungen und<p>![Status grau](assets/status-gray.svg)   **[!UICONTROL _Aus_]** falls keine Aufstockungen konfiguriert sind.<p>Um ein Dialogfeld mit einer Übersicht über die früheren Aufstockungen für den Datensatz anzuzeigen, wählen Sie aus <img src="./assets/pastbackfill.svg" alt="Frühere Aufstockungen" width="15"/> **[!UICONTROL Frühere Aufstockungen]**. |
| [!UICONTROL Datenquellentyp] | Datenquellentyp, wie er beim Hinzufügen des Datensatzes zur Verbindung definiert wurde. |
| [!UICONTROL Typ des Datensatzes] | Entweder [!UICONTROL Ereignis], [!UICONTROL Profil], [!UICONTROL Suche] oder [!UICONTROL Zusammenfassung]. [Weitere Infos](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-connections/create-connection) |
| [!UICONTROL Schema] | Das Experience Platform-Schema, auf dem dieser Datensatz basiert. |
| [!UICONTROL Datensatz-ID] | Diese Datensatz-ID wird im Experience Platform generiert. |


## Nutzung {#connections-usage}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_keyusagemetrics"
>title="Wichtige Nutzungsmetriken"
>abstract="Stellen Sie berichtsfähige Zeilen zu Kern- und historischen Daten pro Monat und insgesamt bereit."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyingestedrows"
>title="Monatlich aufgenommene Zeilen"
>abstract="Misst die Gesamtzahl der monatlich zum System hinzugefügten Datensätze, um Einblicke in das Datenwachstum und die Aufnahmeraten zu erhalten."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyreportablerows"
>title="Monatliche berichtsfähige Zeilen"
>abstract="Verfolgt die Anzahl der für das Reporting verfügbaren Zeilen. Berichtsfähige Zeilen sind die aufgenommenen Zeilen abzüglich der Zeilen, die bei der Aufnahme übersprungen und gelöscht wurden. Berichtsfähige Zeilen dienen als Schlüsselmetrik für die Rechnungsstellung und Datennutzung."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_detailbreakdown"
>title="Detailaufschlüsselung."
>abstract="Sie können detaillierte Metriken nach Verbindung, Datensatz, Sandbox und Tags mit der Option zum Herunterladen einer CSV-Datei der Daten anzeigen."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_otherdatasets"
>title="Andere Datensätze"
>abstract="Seit Monaten vor September 2024 wurden Daten auf Datensatzebene erfasst. Sie werden der Klarheit halber als *andere Datensätze* angezeigt. Seit September 2024 werden Daten auf einer granularen Datensatzebene erfasst und *andere Datensätze* werden nicht mehr angezeigt."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_unknowndatasetsorconnections"
>title="Unbekannte Datensätze oder Verbindungen"
>abstract="Unbekannte Datensätze oder Verbindungen werden mit ihren IDs angezeigt."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_datanotavailable"
>title="Daten nicht verfügbar"
>abstract="Historische Daten, die älter sind als September 2024, sind aufgrund von Systembeschränkungen nicht verfügbar. Metriken werden seit September 2024 erfasst und angezeigt. Das Diagramm zeigt die letzten 18 Monate auf der Timeline, und zukünftige Daten werden angezeigt, sobald die Daten verfügbar werden."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_corereportablerows"
>title="Berichtsfähige Zeilen zu Kerndaten"
>abstract="Zeigt die Gesamtzahl der für die letzten 13 Monate verfügbaren Zeilen an. Beispielsweise zeigt die Zahl am 1. Februar 2024 die Gesamtzahl der verfügbaren Zeilen mit einem Ereignis-Zeitstempel von Januar 2023 bis Januar 2024 an."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_historicalreportablerows"
>title="Berichtsfähige Zeilen zu historischen Daten"
>abstract="Zeigt die Gesamtzahl der verfügbaren Zeilen für den Zeitraum an, der länger als 13 Monate zurückliegt. Beispielsweise zeigt die Zahl am 1. Februar 2024 die Gesamtzahl der verfügbaren Zeilen mit einem Ereignis-Zeitstempel an, der älter als Januar 2023 ist."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_keyusagemetrics"
>title="Wichtige Nutzungsmetriken"
>abstract="Stellen Sie berichtsfähige Zeilen zu Kern- und historischen Daten pro Monat und insgesamt bereit."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyingestedrows"
>title="Monatlich aufgenommene Zeilen"
>abstract="Misst die Gesamtzahl der monatlich zum System hinzugefügten Datensätze, um Einblicke in das Datenwachstum und die Aufnahmeraten zu erhalten."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyreportablerows"
>title="Monatliche berichtsfähige Zeilen"
>abstract="Verfolgt die Anzahl der für das Reporting verfügbaren Zeilen. Berichtsfähige Zeilen sind die aufgenommenen Zeilen abzüglich der Zeilen, die bei der Aufnahme übersprungen und gelöscht wurden. Berichtsfähige Zeilen dienen als Schlüsselmetrik für die Rechnungsstellung und Datennutzung."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_detailbreakdown"
>title="Detailaufschlüsselung."
>abstract="Sie können detaillierte Metriken nach Verbindung, Datensatz, Sandbox und Tags mit der Option zum Herunterladen einer CSV-Datei der Daten anzeigen."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_otherdatasets"
>title="Andere Datensätze"
>abstract="Seit Monaten vor September 2024 wurden Daten auf Datensatzebene erfasst. Sie werden der Klarheit halber als *andere Datensätze* angezeigt. Seit September 2024 werden Daten auf einer granularen Datensatzebene erfasst und *andere Datensätze* werden nicht mehr angezeigt."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_unknowndatasetsorconnections"
>title="Unbekannte Datensätze oder Verbindungen"
>abstract="Unbekannte Datensätze oder Verbindungen werden mit ihren IDs angezeigt."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_datanotavailable"
>title="Daten nicht verfügbar"
>abstract="Historische Daten, die älter sind als September 2024, sind aufgrund von Systembeschränkungen nicht verfügbar. Metriken werden seit September 2024 erfasst und angezeigt. Das Diagramm zeigt die letzten 18 Monate auf der Timeline, und zukünftige Daten werden angezeigt, sobald die Daten verfügbar werden."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_corereportablerows"
>title="Berichtsfähige Zeilen zu Kerndaten"
>abstract="Zeigt die Gesamtzahl der für die letzten 13 Monate verfügbaren Zeilen an. Beispielsweise zeigt die Zahl am 1. Februar 2024 die Gesamtzahl der verfügbaren Zeilen mit einem Ereignis-Zeitstempel von Januar 2023 bis Januar 2024 an."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_historicalreportablerows"
>title="Berichtsfähige Zeilen zu historischen Daten"
>abstract="Zeigt die Gesamtzahl der verfügbaren Zeilen für den Zeitraum an, der länger als 13 Monate zurückliegt. Beispielsweise zeigt die Zahl am 1. Februar 2024 die Gesamtzahl der verfügbaren Zeilen mit einem Ereignis-Zeitstempel an, der älter als Januar 2023 ist."

<!-- markdownlint-enable MD034 -->


Die [!UICONTROL Usage]-Schnittstelle zeigt die Verwendung aufgenommener und berichtspflichtiger Zeilen über alle Verbindungen hinweg. Wenn sie nicht ausgewählt ist, wählen Sie die **[!UICONTROL Nutzung]**, um auf die Benutzeroberfläche zuzugreifen.

Über diese Schnittstelle können Sie feststellen, ob Ihre Customer Journey Analytics-Nutzung den vertraglich vereinbarten Vorgaben entspricht. Zusätzlich zu Überwachungszwecken können Sie die Nutzungsoberfläche verwenden, um die Verlängerung Ihrer Customer Journey Analytics-Lizenz zu planen.

Die Benutzeroberfläche verwendet die folgenden Metriken

| Metrikname | Beschreibung |
|---|---|
| Berichtsfähige Zeilen zu historischen Daten | Anzahl der Zeilen für den Zeitraum, der älter als 13 Monate ist. |
| Berichtsfähige Zeilen zu Kerndaten | Anzahl der Zeilen in den letzten 13 Monaten. |
| Aufgenommene Zeilen | Wie viele Zeilen im jeweiligen Zeitraum aufgenommen werden. |
| Berichtsfähige Zeilen | Wie viele Datenzeilen haben Sie im Rahmen der Verbindung für den bestimmten Zeitraum? |
| Kumulative Zeilen | Wie viele Zeilen bis zum angegebenen Monat aufgenommen werden. |

>[!NOTE]
>
>Die Daten werden ab Juli 2024 für die Kern-, Verlaufs- und Gesamtdatensätze erfasst. Wenden Sie sich an Ihren Account Manager, wenn Sie frühere historische Daten benötigen.
>



Die Benutzeroberfläche von besteht aus zwei Bereichen:

* Das Bedienfeld **[!UICONTROL Schlüsselnutzungsmetriken]** enthält Berichtszeilen zu Kern- und Verlaufsdaten. Das Bedienfeld verfolgt auch prozentuale Änderungen gegenüber dem Vormonat für Kern- und historische Datenzeilen.

  Das Bedienfeld wird in einer Visualisierung angezeigt:

   * **[!UICONTROL Kerndaten - Berichterstellbare Zeilen]**.

     Wie viele meldepflichtige Zeilen haben Sie in den letzten 13 Monaten? Die Zusammenfassungszahl ist die Anzahl der Core-Reporting-Zeilen (z. B. 741M) für den letzten Monat (z. B. Dezember 2024).

   * **[!UICONTROL Berichtszeilen zu historischen Daten]**.

     Wie viele meldepflichtige Zeilen gibt es für den Zeitraum, der älter als 13 Monate ist? Die Zusammenfassungszahl ist die Anzahl der historischen berichtspflichtigen Zeilen (z. B. 127M) für den letzten Monat (z. B. Dezember 2024).

  Wenn Sie den Mauszeiger über einen gestapelten Balken in der Visualisierung bewegen, wird in einem Popup die Anzahl der Zeilen für diesen bestimmten Teil des Balkens angezeigt (z. B. ).


  ![Schlüsselmetriken zur Nutzung](assets/usage-key-usage-metrics.png)

* Ein kombiniertes Bedienfeld mit drei Unterfeldern für:

+++ Aufgenommene Zeilen

  Das Unterbedienfeld **[!UICONTROL Aufgenommene Zeilen]** misst die Gesamtzahl der monatlich zum System hinzugefügten Datensätze und bietet so Einblicke in das Datenwachstum und die Aufnahmeraten. Das Unterbedienfeld bietet eine Zusammenfassung der insgesamt aufgenommenen Zeilen dieses Monats und der Änderung gegenüber dem Vormonat.

  ![Aufgenommene Zeilen](assets/usage-ingested-rows.png)

  Sie können den Mauszeiger über Datenpunkte in der Visualisierung bewegen, um ein Popup mit weiteren Details anzuzeigen.

+++

+++ Berichtsfähige Zeilen

  Die **[!UICONTROL Berichterstellbare Zeilen]**-Visualisierung verfolgt die Anzahl der für das Reporting verfügbaren Zeilen, indem übersprungene und gelöschte Zeilen von erfassten Zeilen subtrahiert werden. Dies dient als Schlüsselmetrik für die Abrechnung und Datennutzung. Das Unterbedienfeld bietet zwei Zusammenfassungen:

   * **[!UICONTROL Letzter Monat insgesamt]**: Eine Zusammenfassung der gesamten meldepflichtigen Zeilen bis zu diesem Monat.
   * **[!UICONTROL Diesen Monat]**: Eine Zusammenfassung der gesamten berichtspflichtigen Zeilen dieses Monats und der Änderung gegenüber dem Vormonat.

  ![Berichterstellbare Zeilen](assets/usage-reportable-rows.png)

  Sie können den Mauszeiger über Datenpunkte in den Visualisierungen bewegen, um ein Popup mit weiteren Details anzuzeigen.

+++

+++ Detailaufschlüsselung

  Sie können die Tabelle **[!UICONTROL Detailaufschlüsselung]** verwenden, um detaillierte Metriken nach Verbindung, Datensatz, Sandbox und Tags anzuzeigen. Datensätze werden mit IDs anstelle von Namen gemeldet, da Datensatznamen während eines Berichtszeitraums geändert werden können. Unbekannte Datensätze oder Verbindungen werden mit IDs gemeldet.

  Seit Monaten vor September 2024 wurden Daten auf Datensatzebene erfasst. Sie werden der Klarheit halber als [!UICONTROL andere Datensätze] angezeigt. Ab September 2024 werden Daten auf einer granularen Datensatzebene erfasst und [!UICONTROL Andere Datensätze] werden nicht mehr angezeigt.

   * Um die Aufschlüsselung zu ändern, wählen Sie eine Kombination für **[!UICONTROL Anzeigen nach]** und **[!UICONTROL Aufschlüsselung nach]** aus.

     | **[!UICONTROL Anzeigen nach]** Optionen | **[!UICONTROL Aufschlüsselung nach]** Optionen |
     |---|---|
     | **[!UICONTROL Verbindung]** | **[!UICONTROL -]** und **[!UICONTROL Datensatz]** |
     | **[!UICONTROL Datensatz]** | **[!UICONTROL -]** |
     | **[!UICONTROL Sandbox]** | **[!UICONTROL Verbindung]** |
     | **[!UICONTROL Tag]** | **[!UICONTROL Verbindung]** |

  ![Detailaufschlüsselung](assets/usage-detail-breakdown.png)

+++

  Sie können einen **[!UICONTROL Zeitraum“ in]** definieren, über den berichtet werden soll. Wählen ![ den ](/help/assets/icons/Calendar.svg) mithilfe von „Kalender“ aus.

>[!MORELIKETHIS]
>
>[Tutorial zum Anzeigen, Beheben und Ändern ](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja) Verbindungseinstellungen.
