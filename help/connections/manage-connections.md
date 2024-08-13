---
title: Erfahren Sie, wie Sie Verbindungen in Customer Journey Analytics verwalten.
description: Beschreibt, wie Verbindungen zu Experience Platform-Datensätzen in Customer Journey Analytics (Customer Journey Analytics) verwaltet werden.
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: bafe2bfdd62065b58ebe5ea6f54a892e0177bbce
workflow-type: tm+mt
source-wordcount: '3263'
ht-degree: 14%

---

# Verwalten von Verbindungen

Nachdem Sie [ eine oder mehrere Verbindungen erstellt oder bearbeitet haben](/help/connections/create-connection.md), können Sie sie in **[!UICONTROL Verbindungen]** verwalten. Verbindungen ermöglichen Ihnen Folgendes:

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

Die [!UICONTROL Liste] -Schnittstelle ist die Standardschnittstelle für Verbindungen. Wenn diese Option nicht ausgewählt ist, wählen Sie die Registerkarte **[!UICONTROL Liste]** aus, um auf die Benutzeroberfläche zuzugreifen.

![Listenansicht](assets/list-view.png)

Die [!UICONTROL Liste] -Schnittstelle zeigt eine Tabelle aller verfügbaren Verbindungen. Mit dem Feld &quot;Suchen&quot;![Suchen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) können Sie schnell nach einer Verbindung suchen.

Die folgenden Spalten oder Symbole sind in der Tabelle verfügbar.

| Spalte oder Symbol | Beschreibung |
| --- | --- |
| [!UICONTROL Name] | Der Anzeigename der Verbindung. Um die Details der Verbindung anzuzeigen, wählen Sie den Hyperlink-Namen aus. Siehe [Verbindungsdetails](#connection-details). |
| ![Information](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Um Informationen zu [!UICONTROL eingeschlossenen Datensätzen], [!UICONTROL Sandbox], [!UICONTROL Inhaber] und mehr anzuzeigen, wählen Sie neben dem Verbindungsnamen ![Informationen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) aus.<p>In einem Popup-Fenster werden Details angezeigt. <p><img src="./assets/conn-info.png" alt="Verbindungsinformationen anzeigen" width="400"/> |
| ![Datenansicht](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | Um [eine Datenansicht](#create-a-data-view) für die Verbindung zu erstellen, wählen Sie ![Datenansicht](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) aus. Dieses Symbol wird nur angezeigt, wenn der Verbindung bereits keine Datenansicht zugeordnet ist. |
| ![Mehr](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Wählen Sie ![Mehr](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) aus, um: <p>![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [Bearbeiten](#edit-a-connection) einer Verbindung.<p>![Löschen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [Löschen](#delete-a-connection) einer Verbindung.<p>![Datenansicht](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [Neue Datenansicht erstellen](#create-a-data-view). So erstellen Sie zusätzliche Datenansichten für die Verbindung. |
| [!UICONTROL Datensätze] | Eine oder mehrere Links zu den Datensätzen, die Teil der Verbindung sind. Sie können den Datensatz-Hyperlink auswählen, um den Datensatz in der Verbindung anzuzeigen. Wenn mehr Datensätze Teil der ausgewählten Verbindung sind, wählen Sie **[!UICONTROL +*x* more]** aus, um den Bereich **[!UICONTROL Datensätze enthalten]** anzuzeigen. In diesem Bereich werden Links zu allen Datensätzen und eine Option zur Suche nach einem bestimmten Datensatz angezeigt, der Teil der Verbindung ist.<p><img src="./assets/datasets-included.png" alt="Enthaltene Datenbestände" width="400"/><p>Wenn Sie einen Datensatznamen auswählen, wird der Datensatz in der Experience Platform-Benutzeroberfläche in einer neuen Registerkarte geöffnet. |
| [!UICONTROL Sandbox] | Die [Experience Platform-Sandbox](https://experienceleague.adobe.com/de/docs/experience-platform/sandbox/home), aus der diese Verbindung ihre Datensätze zeichnet. Diese Sandbox wurde beim erstmaligen Erstellen der Verbindung ausgewählt. Sie kann nicht geändert werden. |
| [!UICONTROL Inhaber] | Die Person, die die Verbindung hergestellt hat. |
| [!UICONTROL Importieren neuer Daten] | Der Status des Imports neuer Daten für Datensätze: <p>![Status grün](assets/status-green.svg))    **[!UICONTROL _x _On]**für Datensätze, die zum Importieren neuer Daten konfiguriert sind, und<p>![Status gray](assets/status-gray.svg)   **[!UICONTROL _x Aus_]** für Datensätze, die nicht für den Import neuer Daten konfiguriert sind. |
| [!UICONTROL Erstellt am] | Der Zeitstempel, zu dem die Verbindung erstellt wurde. |
| [!UICONTROL Zuletzt geändert] | Der Zeitstempel, zu dem die Verbindung zuletzt aktualisiert wird. |
| [!UICONTROL Aufstockungsdaten] | Der Status für Aufstockungsdaten in allen Datensätzen.<p>![Status rot](assets/status-red.svg)   **[!UICONTROL _x _Aufstockungen fehlgeschlagen]**für die Anzahl fehlgeschlagener Aufstockungen in Datensätzen,<p>![Status orange](assets/status-orange.svg)   **[!UICONTROL _x _Aufstockung der Verarbeitung]**für die Anzahl der Aufstockungen der Verarbeitung über Datensätze hinweg,<p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _-Aufstockungen abgeschlossen]**für die Anzahl der abgeschlossenen Aufstockungen für Datensätze und<p>![Status gray](assets/status-gray.svg)   **[!UICONTROL _Aus_]** , falls für die Datensätze in der Verbindung keine Rückfüllungen definiert sind. |

Um zu konfigurieren, welche Spalten angezeigt werden sollen, wählen Sie ![Spalteneinstellungen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) aus, was das Dialogfeld **Tabelle anpassen** anzeigt, in dem Sie Spalten in der Tabelle aktivieren oder deaktivieren können.

### Verbindung bearbeiten

1. Wählen Sie ![Mehr](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) neben dem Verbindungsnamen aus.
1. Wählen Sie ![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Bearbeiten]** aus dem Kontextmenü.

Alternativ können Sie:

1. Wählen Sie die Verbindungszeile aus.

1. Wählen Sie in der blauen Leiste ![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Bearbeiten]** aus.

Beim Bearbeiten einer Verbindung haben Sie folgende Möglichkeiten:

* Import neuer Daten starten und beenden.
* Eine Verbindung umbenennen.
* Aktualisieren Sie die Datensätze.
* Entfernen Sie Datensätze aus den Verbindungen.

Weitere Informationen finden Sie unter [Erstellen oder Bearbeiten einer Verbindung](create-connection.md) .


### Eine Verbindung löschen {#connections-delete}

1. Wählen Sie neben dem Verbindungsnamen ![Mehr](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) aus.
1. Wählen Sie ![Löschen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Löschen]** aus.

Alternativ können Sie:

1. Wählen Sie die Verbindungszeile aus.

1. Wählen Sie ![Löschen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Löschen]** aus der blauen Leiste.

Wenn Sie eine Verbindung löschen, zeigt ein Bedienfeld &quot;**[!UICONTROL Verbindung löschen]**&quot;an, welche Datenansichten gelöscht werden und welche Workspace-Projekte betroffen sind.

![Verbindung löschen](assets/delete-connection.png)

Wählen Sie **[!UICONTROL Weiter]** aus, um die Verbindung zu löschen.

Weitere Informationen zum Löschen einer Verbindung finden Sie unter [Auswirkungen auf das Löschen ](/help/technotes/deletion.md) .


### Datenansicht für eine Verbindung erstellen

* Wenn der Verbindung keine Datenansicht zugeordnet ist:

   1. Wählen Sie ![Datenansicht hinzufügen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) neben dem Verbindungsnamen aus.

* Wenn bereits eine oder mehrere Datenansichten für die Verbindung erstellt wurden:

   1. Wählen Sie neben dem Verbindungsnamen ![Mehr](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) aus.
   1. Wählen Sie ![Datenansicht hinzufügen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Neue Datenansicht erstellen]**.

Alternativ können Sie:

1. Wählen Sie die Verbindungszeile aus.

1. Wählen Sie ![Datenansicht hinzufügen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Datenansicht erstellen]** aus der blauen Schaltflächenleiste.

Weitere Informationen finden Sie unter [Erstellen oder Bearbeiten einer Datenansicht](/help/data-views/create-dataview.md).

### Verbindungsdetails {#connection-detail}

Um zu den Details für eine Verbindung zu wechseln, wählen Sie einen Verbindungsnamen in der Verbindungstabelle aus.

![Fenster &quot;Alle Datensätze&quot;mit den Widgets und Einstellungen](assets/conn-details.png)

Die Benutzeroberfläche &quot;Verbindungsdetails&quot;bietet einen detaillierten Überblick über den Status einer Verbindung. Sie haben folgende Möglichkeiten:

* Überprüfen Sie den Status der Datensätze Ihrer Verbindung und des Aufnahmevorgangs.
* Ermitteln Sie Konfigurationsprobleme, die zu übersprungenen oder gelöschten Datensätzen führen können.
* Finden Sie heraus, wann die Daten für das Reporting verfügbar sind.

| Benutzeroberfläche | Beschreibung |
| --- | --- |
| ![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [!UICONTROL Verbindung bearbeiten] | Um die Details einer Verbindung zu bearbeiten, wählen Sie ![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Verbindung bearbeiten]** aus. Weitere Informationen finden Sie unter [Erstellen oder Bearbeiten einer Verbindung](create-connection.md) . |
| Datensatz-Auswahl | Ermöglicht die Auswahl eines Datensatzes oder aller Datensätze in der Verbindung. Datensätze können nicht mehrmals ausgewählt werden. Die Standardeinstellung ist [!UICONTROL Alle Datensätze]. |
| Datumsbereichsauswahl | Bearbeiten Sie das Start- und Enddatum oder wählen Sie ![Kalender](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) aus, um die Auswahl für den Datenbereich zu öffnen. Wählen Sie in der Datumsbereichsauswahl einen Datumsbereich aus, indem Sie einen der vordefinierten Zeiträume verwenden (z. B. **[!UICONTROL Letzte 6 Monate]**) oder den Kalender verwenden, um Start- und Enddatum auszuwählen. Wählen Sie **[!UICONTROL Anwenden]** aus, um den neuen Datenbereich anzuwenden. |
| [!UICONTROL Verfügbare Aufzeichnungen von Ereignisdaten] | Die Gesamtzahl der für die Berichterstellung verfügbaren Datensatz-Ereigniszeilen, **für die gesamte Verbindung**. Diese Anzahl ist unabhängig von Kalendereinstellungen. Die Anzahl ändert sich, wenn Sie einen Datensatz aus der Datensatz-Auswahl auswählen oder indem Sie einen Datensatz in der Tabelle auswählen. Nach dem Hinzufügen von Daten ist die Latenz von 1-2 Stunden, damit die Daten in Berichten angezeigt werden. |
| [!UICONTROL Metriken] | Fasst die hinzugefügten, übersprungenen und gelöschten Ereignis-, Lookup-, Profil- und Zusammenfassungsdatensätze sowie die Anzahl der hinzugefügten Batches zusammen. Diese Metriken basieren auf **dem ausgewählten Datensatz und Datumsbereich**.<p>Wählen Sie **[!UICONTROL Detail überprüfen]** aus, um das Popup **[!UICONTROL Übersprungenes Detail prüfen]** anzuzeigen. Das Popup listet die Anzahl der übersprungenen Datensätze und den Grund für alle Ereignis-Datensätze oder ausgewählten Datensatz auf.<p><img src="./assets/skipped-records.png" width="500"/><p>Wählen Sie das Popup ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) mit weiteren Informationen aus. Aus einigen übersprungenen Gründen, z. B. [!UICONTROL leere Besucher-ID], zeigt das Popup-Fenster Beispiel-PSQL für EQS (Experience Platform für Query Service) an, die Sie in [Query Service](https://experienceleague.adobe.com/de/docs/experience-platform/query/home) verwenden können, um nach den übersprungenen Datensätzen im Datensatz zu suchen. Wählen Sie ![Kopieren](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL Beispiel-PSQL für EQS kopieren]** aus, um die SQL zu kopieren. |
| [!UICONTROL Hinzugefügte Datensätze] | Gibt an, wie viele Zeilen im ausgewählten Zeitraum **für den ausgewählten Datensatz und Datumsbereich** hinzugefügt wurden. Wird alle zehn Minuten aktualisiert. |
| [!UICONTROL Übersprungene Datensätze] | Gibt an, wie viele Zeilen im ausgewählten Zeitraum **für den ausgewählten Datensatz und Datumsbereich** übersprungen wurden. Gründe für das Überspringen von Datensätzen sind fehlende Zeitstempel, fehlende oder ungültige Personen-ID usw. Wird alle zehn Minuten aktualisiert. <p>Ungültige Personen-IDs (z. B. `undefined` oder `00000000` oder eine Kombination aus Zahlen und Buchstaben in einer [!UICONTROL Personen-ID], die in einem Ereignis angezeigt wird, das mehr als 1 Million Mal in einem bestimmten Monat stattfindet) sind IDs, die keinem bestimmten Benutzer oder einer bestimmten Person zugeordnet werden können. Diese Zeilen können nicht in das System aufgenommen werden und führen zu fehleranfälliger Erfassung und Berichterstellung. Um ungültige Personen-IDs zu beheben, haben Sie drei Möglichkeiten:<ul><li>Verwenden Sie die [Zuordnung](/help/stitching/overview.md) , um die nicht definierten oder Benutzer-IDs ohne jegliche Kennung mit gültigen Benutzer-IDs zu füllen.</li><li>Leeren Sie die Benutzer-ID aus, die dann bei der Erfassung herausgegeben wird (vorzuziehen sind ungültige Benutzer-IDs oder Benutzer-IDs ohne Inhalt).</li><li>Korrigieren Sie alle ungültigen Benutzer-IDs in Ihrem System, bevor Sie die Daten aufnehmen.</li></ul> |
| [!UICONTROL Datensätze] gelöscht | Gibt an, wie viele Zeilen im ausgewählten Zeitraum **für den ausgewählten Datensatz und Datumsbereich** gelöscht wurden. Jemand könnte z. B. einen Datensatz in [!DNL Experience Platform] gelöscht haben. Wird alle zehn Minuten aktualisiert.<p>In einigen Szenarien kann dieser Wert auch ersetzte Datensätze umfassen, z. B. das Stitching oder einige Lookup-Datensatz-Aktualisierungen. Betrachten Sie dieses Beispiel:</p><ul><li>Sie laden einen Datensatz in einen Datensatz &quot;XDM Individual Profile&quot;hoch, der von Customer Journey Analytics für die Aufnahme als Profilsuchdaten konfiguriert wurde. In den Verbindungsdetails zeigte dieser Datensatz 1 hinzugefügten Datensatz an.</li><li>Sie laden ein Duplikat des ursprünglichen Datensatzes in denselben AEP-Datensatz hoch, der jetzt zwei Datensätze enthält. Customer Journey Analytics erfasst den zusätzlichen Datensatz aus dem Profilsuchdatensatz. Da bereits ein Profildatensatz in der Verbindung für diese Personen-ID erfasst wurde, löscht Customer Journey Analytics seine frühere Version und fügt die neuen Profildaten hinzu. In den Verbindungsdetails würde diese Aktion 1 hinzugefügten und 1 gelöschten Datensatz darstellen, da Customer Journey Analytics nur die neuesten Profilsuchdaten für eine aufgenommene Personen-ID speichert.</li><li>Insgesamt enthält der AEP-Datensatz zwei Datensätze, die zufällig identisch sind. Die Customer Journey Analytics-Verbindungsdetails zeigen getrennt den Status der erfassten Daten an: 2 Datensätze wurden hinzugefügt und 1 Datensatz wurde für diesen Profildatensatz gelöscht. </li></ul> |
| ![Suche](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) _Name des Suchdatensatzes oder Kennung_ | Datensatzsuchfeld. Sie können die Datensatztabelle nach dem Datensatznamen oder der [!UICONTROL Datensatz-ID] durchsuchen. |
| [!UICONTROL Datensatztabelle] | Die Datensätze, die Teil der Verbindung sind. |
| [!UICONTROL Datensätze] | Der Name des Datensatzes, der Teil der Verbindung ist. Sie können den Hyperlink auswählen, um den Datensatz in der Experience Platform-Benutzeroberfläche in einer neuen Registerkarte zu öffnen. Sie können die Zeile oder das Kontrollkästchen auswählen, um nur Details für den ausgewählten Datensatz anzuzeigen. |
| [!UICONTROL Datensatz-ID] | Automatisch durch Experience Platform generiert. |
| [!UICONTROL Hinzugefügte Datensätze] | Die Anzahl der Datensatzdatensätze (Zeilen), die während des ausgewählten Zeitintervalls zu einer Verbindung hinzugefügt wurden. |
| [!UICONTROL Übersprungene Datensätze] | Die Anzahl der Datensatzdatensätze (Zeilen), die während der Datenübertragung für eine Verbindung während des ausgewählten Zeitintervalls übersprungen wurden. |
| [!UICONTROL Gelöschte Datensätze] | Die Anzahl der Datensatzdatensätze (Zeilen), die während des ausgewählten Zeitintervalls aus einer Verbindung entfernt wurden. |
| [!UICONTROL Batches hinzugefügt] | Die Anzahl der Datensatz-Batches wurde zu einer Verbindung hinzugefügt. |
| [!UICONTROL Zuletzt hinzugefügt] | Der Zeitstempel des neuesten Batches aus dem Datensatz, der zu einer Verbindung hinzugefügt wurde. |
| [!UICONTROL Datenquellentyp] | Der Quelltyp des Datensatzes. Sie definieren den Quelltyp beim Erstellen einer Verbindung. |
| [!UICONTROL Typ des Datensatzes] | Der Datensatztyp für diesen Datensatz. Der Typ kann [!UICONTROL event], [!UICONTROL profile], [!UICONTROL lookup] oder [!UICONTROL summary] lauten. [Weitere Infos](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-connections/create-connection) |
| Schema | Das Experience Platform-Schema, auf dem der Datensatz basiert. |
| [!UICONTROL Importieren neuer Daten] | Der Status des Imports neuer Daten für den Datensatz: <p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _On]**, wenn der Datensatz für den Import neuer Daten konfiguriert ist, und<p>![Status gray](assets/status-gray.svg)   **[!UICONTROL _x Aus_]** , wenn der Datensatz so konfiguriert ist, dass er keinen neuen Datenimport zulässt. |
| [!UICONTROL Daten transformieren] | Der Transformationsstatus der entsprechenden B2B-Lookup-Datensätze. Weitere Informationen finden Sie unter [Umwandeln von Datensätzen für B2B-Suchen](transform-datasets-b2b-lookups.md).<p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _On]**für die entsprechenden Datensätze, die für die Transformation aktiviert sind, <p>![Status gray](assets/status-gray.svg)   **[!UICONTROL _x Aus_]** für die entsprechenden Datensätze, die nicht für die Transformation aktiviert sind, und<p>**[!UICONTROL K/A]** für alle anderen Datensätze, die nicht für die Umwandlung gelten. |
| [!UICONTROL Aufstockungsdaten] | Der Status der Aufstockungsdaten für den Datensatz.<p>![Status rot](assets/status-red.svg)   **[!UICONTROL _x _Aufstockungen fehlgeschlagen]**für die Anzahl fehlgeschlagener Aufstockungen,<p>![Status rot](assets/status-orange.svg)   **[!UICONTROL _x _Aufstockung der Verarbeitung]**für die Anzahl der Aufstockungen,<p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _-Aufstockungen abgeschlossen]**für die Anzahl der abgeschlossenen Aufstockungen und<p>![Status gray](assets/status-gray.svg)   **[!UICONTROL _Aus_]** , falls die Aufstockungen nicht konfiguriert sind. |
| [!UICONTROL Importieren neuer Daten] | Der Status des Imports neuer Daten für den Datensatz: <p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _On]**, wenn der Datensatz für den Import neuer Daten konfiguriert ist, und<p>![Status gray](assets/status-gray.svg)   **[!UICONTROL _x Aus_]** , wenn der Datensatz so konfiguriert ist, dass er keine neuen Daten importiert. |
| [!UICONTROL Aufstockungsdaten] | Der Status der Aufstockungsdaten für den Datensatz.<p>![Status rot](assets/status-red.svg)   **[!UICONTROL _x _Aufstockungen fehlgeschlagen]**für die Anzahl fehlgeschlagener Aufstockungen,<p>![Status rot](assets/status-orange.svg)   **[!UICONTROL _x _Aufstockung der Verarbeitung]**für die Anzahl der Aufstockungen,<p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _-Aufstockungen abgeschlossen]**für die Anzahl der abgeschlossenen Aufstockungen und<p>![Status gray](assets/status-gray.svg)   **[!UICONTROL _Aus_]** , falls keine Aufstockungen konfiguriert sind. |

>[!IMPORTANT]
>
>Daten, die vor dem 13. August 2021 erfasst wurden, werden nicht in der Benutzeroberfläche [!UICONTROL Verbindungen] angezeigt.

#### Verbindungs-Panel

Wenn in der Datensatztabelle kein Datensatz ausgewählt ist, werden in einem Bedienfeld auf der rechten Seite der Schnittstelle Verbindungen Verbindungsoptionen und -details angezeigt.

| Optionen | Beschreibung |
| --- | --- |
| ![Aktualisieren](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL Aktualisieren] | Um die Verbindung zu aktualisieren und die Darstellung kürzlich hinzugefügter Datensätze zuzulassen, wählen Sie ![Aktualisieren](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Aktualisieren]** aus. |
| ![Löschen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Löschen]** | [Löschen](#delete-a-connection) Sie diese Verbindung. |
| ![Datenansicht hinzufügen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Datenansicht erstellen]** | [Erstellen Sie eine Datenansicht](#create-a-data-view), die auf dieser Verbindung basiert. Weitere Informationen finden Sie unter [Datenansichten](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views) . |
| [!UICONTROL Name der Verbindung] | Der Anzeigename der Verbindung. |
| [!UICONTROL Beschreibung der Verbindung] | Eine detailliertere Beschreibung, die den Zweck dieser Verbindung beschreibt. |
| [!UICONTROL Sandbox] | Die [Experience Platform-Sandbox](https://experienceleague.adobe.com/de/docs/experience-platform/sandbox/home), aus der diese Verbindung ihre Datensätze zeichnet. Diese Sandbox wurde beim ersten Erstellen der Verbindung ausgewählt. Sie kann nicht geändert werden. |
| [!UICONTROL Verbindungs-ID] | Diese ID wird im Experience Platform generiert. Sie können ![Kopieren](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) verwenden, um die ID zu kopieren. |
| [!UICONTROL Datenaufrufe, die Verbindungen verwenden] | Listet alle Datenansichten auf, die diese Verbindung verwenden. |
| [!UICONTROL Neue Daten importieren] | Der Status des Imports neuer Daten für Datensätze: <p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _On]**für die Anzahl der Datensätze, die für den Import neuer Daten konfiguriert sind, und<p>![Status gray](assets/status-gray.svg)   **[!UICONTROL _x Aus_]** für die Anzahl der Datensätze, für die der neue Datenimport deaktiviert ist. |
| [!UICONTROL Aufstockungsdaten] | Der Status der Aufstockungsdaten für Datensätze.<p>![Status rot](assets/status-red.svg)   **[!UICONTROL _x _Aufstockungen fehlgeschlagen]**für die Anzahl fehlgeschlagener Aufstockungen in Datensätzen,<p>![Status rot](assets/status-orange.svg)   **[!UICONTROL _x _Aufstockung der Verarbeitung]**für die Anzahl der Aufstockungen der Verarbeitung über Datensätze hinweg,<p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _-Aufstockungen abgeschlossen]**für die Anzahl der abgeschlossenen Aufstockungen für Datensätze und<p>![Status gray](assets/status-gray.svg)   **[!UICONTROL _Aus_]** , falls für die Datensätze in der Verbindung keine Rückfüllungen definiert sind. |
| Daten transformieren | Der Transformationsstatus der entsprechenden B2B-Lookup-Datensätze. Weitere Informationen finden Sie unter [Umwandeln von Datensätzen für B2B-Suchen](transform-datasets-b2b-lookups.md).<p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _On]**für die Anzahl der für die Transformation aktivierten Datensätze. |
| [!UICONTROL Erstellt von] | Der Name der Person, die die Verbindung erstellt hat. |
| [!UICONTROL Zuletzt geändert] | Der Zeitstempel der letzten Änderung an der Verbindung. |
| [!UICONTROL Zuletzt geändert von] | Die Person, die die Verbindung zuletzt geändert hat. |

#### Datensatzbedienfeld

Wenn ein Datensatz in der Datensatztabelle ausgewählt ist, werden in einem Bedienfeld auf der rechten Seite der Benutzeroberfläche &quot;Verbindungen&quot;Details zum ausgewählten Datensatz angezeigt.

| Details | Beschreibung |
| --- | --- |
| [!UICONTROL Personen-ID] | Eine Identität, die im Datensatzschema in der Experience Platform definiert wurde. Diese Identität ist die Personen-ID, die Sie bei der Erstellung der Verbindung ausgewählt haben. Wenn Sie eine Verbindung erstellen, die Datensätze mit unterschiedlichen IDs enthält, spiegelt die Berichterstellung dies wider. Um Datensätze zusammenzuführen, müssen Sie dieselbe Personen-ID für Datensätze verwenden. |
| [!UICONTROL Schlüssel] | Der Schlüssel, den Sie für einen Lookup-Datensatz angegeben haben. |
| [!UICONTROL Übereinstimmender Schlüssel] | Der passende Schlüssel, den Sie für einen Lookup-Datensatz angegeben haben. |
| [!UICONTROL Zeitstempel] | Der für einen Ereignis-Datensatz definierte Zeitstempel. |
| [!UICONTROL Verfügbare Datensätze] | Die Gesamtzahl der für diesen Datensatz erfassten Zeilen für den ausgewählten Zeitraum im Kalender. Es gibt keine Latenz im Hinblick darauf, ab wann die Daten nach dem Hinzufügen in Berichten angezeigt werden. Wenn Sie jedoch eine brandneue Verbindung erstellen, ist [Latenz](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-faq) vorhanden. |
| [!UICONTROL Hinzugefügte Datensätze] | Wie viele Zeilen im ausgewählten Zeitraum hinzugefügt wurden. |
| [!UICONTROL Gelöschte Datensätze] | Anzahl der im ausgewählten Zeitraum gelöschten Datensätze. |
| [!UICONTROL Batches hinzugefügt] | Wie viele Datenstapel diesem Datensatz hinzugefügt wurden. |
| [!UICONTROL Übersprungene Datensätze] | Wie viele Zeilen während der Aufnahme im ausgewählten Zeitraum übersprungen wurden.<p>Gründe für das Überspringen von Datensätzen sind: Fehlende Zeitstempel, fehlende oder ungültige Personen-ID usw. Wird alle zehn Minuten aktualisiert.<p>Ungültige Personen-IDs (z. B. `undefined` oder `00000000` oder eine Kombination aus Zahlen und Buchstaben in einer [!UICONTROL Personen-ID], die in einem Ereignis angezeigt wird, das mehr als 1 Million Mal in einem bestimmten Monat stattfindet) sind IDs, die keinem bestimmten Benutzer oder einer bestimmten Person zugeordnet werden können. Diese Zeilen können nicht in das System aufgenommen werden und führen zu fehleranfälliger Erfassung und Berichterstellung. Um ungültige Personen-IDs zu beheben, haben Sie drei Möglichkeiten:<ul><li>Verwenden Sie die [Zuordnung](/help/stitching/overview.md) , um die nicht definierten oder Benutzer-IDs ohne jegliche Kennung mit gültigen Benutzer-IDs zu füllen.</li><li>Leeren Sie die Benutzer-ID aus, die dann bei der Erfassung übersprungen wird (vorzuziehen sind ungültige Benutzer-IDs oder Benutzer-IDs ohne Inhalt).</li><li>Korrigieren Sie alle ungültigen Benutzer-IDs in Ihrem System, bevor Sie die Daten aufnehmen.</li></ul> |
| [!UICONTROL Zuletzt hinzugefügt] | Der Zeitpunkt, zu dem der letzte Stapel hinzugefügt wurde. |
| [!UICONTROL Importieren neuer Daten] | Der Status des Imports neuer Daten für den Datensatz: <p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _On]**, wenn der Datensatz für den Import neuer Daten konfiguriert ist, und<p>![Status gray](assets/status-gray.svg)   **[!UICONTROL _x Aus_]** , wenn der Datensatz so konfiguriert ist, dass er keine neuen Daten importiert. |
| [!UICONTROL Aufstockungsdaten] | Der Status der Aufstockungsdaten für den Datensatz.<p>![Status rot](assets/status-red.svg)   **[!UICONTROL _x _Aufstockungen fehlgeschlagen]**für die Anzahl fehlgeschlagener Aufstockungen,<p>![Status rot](assets/status-orange.svg)   **[!UICONTROL _x _Aufstockung der Verarbeitung]**für die Anzahl der Aufstockungen,<p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _-Aufstockungen abgeschlossen]**für die Anzahl der abgeschlossenen Aufstockungen und<p>![Status gray](assets/status-gray.svg)   **[!UICONTROL _Aus_]** , falls keine Aufstockungen konfiguriert sind.<p>Um ein Dialogfeld mit einem Überblick über die früheren Rückstände für den Datensatz anzuzeigen, wählen Sie <img src="./assets/pastbackfill.svg" alt="Frühere Aufstockungen" width="15"/> **[!UICONTROL Vergangene Aufstockungen]**. |
| [!UICONTROL Datenquellentyp] | Datenquellentyp, wie beim Hinzufügen des Datensatzes zur Verbindung definiert. |
| [!UICONTROL Typ des Datensatzes] | Entweder [!UICONTROL event], [!UICONTROL profile], [!UICONTROL lookup] oder [!UICONTROL summary]. [Weitere Infos](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-connections/create-connection) |
| [!UICONTROL Schema] | Das Experience Platform-Schema, auf dem dieser Datensatz basiert. |
| [!UICONTROL Datensatz-ID] | Diese Datensatz-ID wird im Experience Platform generiert. |


## Nutzung

Die Oberfläche von [!UICONTROL Nutzung] zeigt die Verwendung von aufgenommenen und berichtspflichtigen Zeilen über alle Verbindungen hinweg. Diese Schnittstelle unterstützt Sie dabei festzustellen, ob Ihre Customer Journey Analytics-Nutzung den vertraglich vereinbarten Bedingungen entspricht. Zusätzlich zu Überwachungszwecken können Sie die Nutzungs-Benutzeroberfläche verwenden, um die Verlängerung Ihrer Customer Journey Analytics-Lizenz zu planen.

Sie können einen Zeitraum (zwischen den letzten 6 Monaten, dem aktuellen Jahr oder den letzten 2 Jahren) und ein Intervall (zwischen monatlich und vierteljährlich) auswählen, um die Nutzung der Customer Journey Analytics zu überwachen. Die Benutzeroberfläche ist in zwei Abschnitte unterteilt:

* Aufgenommene Zeilen: Gesamtzahl der aus Ereignis-Datensätzen erfassten/gesendeten Zeilen über alle Customer Journey Analytics-Verbindungen hinweg, einschließlich der bei der Aufnahme übersprungenen Datensätze
* Berichterstellbare Zeilen: Gesamtzahl der berichtspflichtigen Zeilen, die alle Ereignisdaten über alle Customer Journey Analytics-Verbindungen hinweg enthalten

![usage-view](assets/usage-view.png)

Wählen Sie die Registerkarte **[!UICONTROL Nutzung]** aus, um auf die Benutzeroberfläche zuzugreifen.

### Verwendungsbericht

1. Wählen Sie einen **[!UICONTROL Zeitbereich]** aus. Sie können zwischen **[!UICONTROL Letzte 6 Monate]**, **[!UICONTROL Jahr bis Datum]** oder **[!UICONTROL Letzte 2 Jahre]** auswählen.
1. Wählen Sie ein **[!UICONTROL Intervall]** aus. Sie können zwischen **[!UICONTROL Monatlich]** oder **[!UICONTROL vierteljährlich]** wählen.

Für [!UICONTROL aufgenommene Zeilen]:

* In einem Bedienfeld werden die insgesamt erfassten Zeilen angezeigt, die alle Ereignisdaten für alle Verbindungen enthalten, die an jedem zweiten Tag eines Monats aktualisiert wurden. Innerhalb des Bedienfelds:
   * Ein Feld zeigt die Anzahl der aufgenommenen Zeilen für den letzten Monat und die Änderung in % (angegeben durch Schaltflächen oder Schaltflächen) für den Vormonat an.
   * Ein Liniendiagramm zeigt die ◼︎ [!UICONTROL Monatlich aufgenommenen Zeilen] an.<br/>Um ein Popup anzuzeigen, das die Anzahl der monatlich erfassten Zeilen für einen Monat anzeigt, bewegen Sie den Mauszeiger über einen Datenpunkt im Liniendiagramm.


Für [!UICONTROL MELDEPFLICHTIGE Zeilen]:

* In einem Bedienfeld werden alle berichtspflichtigen Zeilen angezeigt, die alle Ereignisdaten für alle Verbindungen enthalten, die an jedem zweiten Tag eines Monats aktualisiert wurden. Innerhalb des Bedienfelds:
   * Ein Feld zeigt die kumulative Gesamtzahl der berichtspflichtigen Zeilen an.
   * Ein Feld zeigt die Gesamtzahl der berichtspflichtigen Zeilen für den letzten Monat und die Änderung in % (angegeben durch Schaltflächen oder Schaltflächen) im Vergleich zum vorherigen Monat an.
   * Ein Liniendiagramm zeigt die ◼︎ [!UICONTROL Berichterstattungszeilen pro Monat] an.<br/>Um ein Popup anzuzeigen, das die Anzahl der kumulativen berichtbaren Zeilen für einen bestimmten Monat anzeigt, bewegen Sie den Mauszeiger über einen Datenpunkt im Liniendiagramm.
   * Ein Liniendiagramm zeigt die ◼︎ [!UICONTROL Kumulativen berichtspflichtigen Zeilen] an.<br/>Um ein Popup anzuzeigen, in dem die Anzahl der monatlich berichteten Zeilen für einen Monat angezeigt wird, bewegen Sie den Mauszeiger über einen Datenpunkt im Liniendiagramm.


>[!MORELIKETHIS]
>
>Tutorial zum Anzeigen, Fehlerbehebung und Ändern von Verbindungseinstellungen](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja).[
