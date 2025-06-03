---
title: Erfahren Sie, wie Sie Verbindungen in Customer Journey Analytics verwalten
description: Beschreibt, wie Verbindungen zu Experience Platform-Datensätzen in Customer Journey Analytics (CJA) verwaltet werden.
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: f229b6c9241660d3e8a386638ae68d4cb3627ba1
workflow-type: tm+mt
source-wordcount: '4163'
ht-degree: 74%

---

# Verwalten von Verbindungen {#manage-connections}

>[!CONTEXTUALHELP]
>id="connections_use_ajo"
>title="Verwenden der Journey Optimizer-Verbindung"
>abstract="Nutzt die erweiterten Reporting-Funktionen von Customer Journey Analytics mit Journey Optimizer."

>[!CONTEXTUALHELP]
>id="connections_cancel_ajo"
>title="Abbrechen der Journey Optimizer-Verbindung"
>abstract="Deaktiviert die erweiterten Reporting-Funktionen von Customer Journey Analytics mit Journey Optimizer."


Nachdem Sie [eine oder mehrere Verbindungen erstellt oder bearbeitet haben](/help/connections/create-connection.md), können Sie sie in unter **[!UICONTROL Verbindungen]** verwalten. Die [!UICONTROL Verbindungen] ermöglicht Ihnen Folgendes:

* alle Verbindungen auf einen Blick anzeigen, einschließlich der oder des Verantwortlichen, der Sandbox und des Zeitpunkts der Verbindungserstellung und -änderung.
* Verbindungen bearbeiten.
* Eine Verbindung löschen.
* Eine Datenschicht aus einer Verbindung erstellen.
* Lassen Sie sich alle Datensätze in einer Verbindung anzeigen.
* den Status der Datensätze Ihrer Verbindung und des Aufnahmevorgangs überprüfen. Beispielsweise, wann Ihre Daten verfügbar sind, damit Sie mit der Berichterstellung und Analyse in Analysis Workspace beginnen können.
* alle Datendiskrepanzen identifizieren, die aufgrund einer Fehlkonfiguration entstanden sind. Fehlen Zeilen? Wen dies der Fall ist, welche Zeilen fehlen und warum? Haben Sie Verbindungen falsch konfiguriert und dadurch das Fehlen von Daten in Customer Journey Analytics verursacht?
* Erkenntnisse zur Verwendung aufgenommener und berichtsfähiger Zeilen über alle Verbindungen hinweg erhalten.

Für [!UICONTROL Verbindungen] gibt es zwei Benutzeroberflächen: [[!UICONTROL Liste]](#list) und [[!UICONTROL Nutzung]](#usage).


## Liste

Die Benutzeroberfläche **[!UICONTROL Liste]** ist die Standardbenutzeroberfläche für Verbindungen. Wenn sie nicht ausgewählt ist, wählen Sie die Registerkarte **[!UICONTROL Liste]** aus, um auf die Benutzeroberfläche zuzugreifen.

![Listenansicht](assets/list-view.png)

Auf der Benutzeroberfläche [!UICONTROL Liste] wird eine Tabelle aller verfügbaren Verbindungen angezeigt. Sie können im Feld Suchen ![Search](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) nach einer Verbindung suchen.

Die folgenden Spalten oder Symbole sind in der Tabelle verfügbar.

| Spalte oder Symbol | Beschreibung |
| --- | --- |
| **[!UICONTROL _Name_]** | Der Anzeigename der Verbindung. Wählen Sie den Hyperlink-Namen aus, um die [Details der Verbindung“ ](#connection-details). |
| ![Information](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Um Informationen zu [!UICONTROL enthaltenen Datensätzen], [!UICONTROL Sandbox], der oder dem [!UICONTROL Verantwortlichen] usw. anzuzeigen, wählen Sie ![Information](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) neben dem Verbindungsnamen aus.<p>Ein Popup-Fenster zeigt Details zum Datensatz an. <p>![Popup mit Verbindungsinformationen](assets/connection-info-popup.png) |
| ![Mehr](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Wählen Sie ![Mehr](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg), um ein Kontextmenü zu öffnen. Folgende Optionen stehen zur Auswahl: <p>![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Bearbeiten]**, um [ Verbindung ](#edit-a-connection) bearbeiten.<p>![Löschen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Löschen]** um eine Verbindung [löschen](#delete-a-connection).<p>![Datenansicht](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Neue Datenansicht erstellen]** um [eine neue Datenansicht zu erstellen](#create-a-data-view) für die Verbindung.<p>![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Verbindungszuordnung]** zum Anzeigen einer [Verbindungszuordnung](#map-a-connection) für die Verbindung. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Verbindungstyp &#x200B;]** | Der Verbindungstyp: **[!UICONTROL personenbasierte]** oder **[!UICONTROL Account]**-basierte Verbindung. |
| **[!UICONTROL Datensätze]** | Ein oder mehrere Links zu den Datensätzen, die Teil der Verbindung sind. Sie können den Datensatz-Hyperlink auswählen, um den Datensatz in der Verbindung anzuzeigen. Wenn weitere Datensätze Teil der ausgewählten Verbindung sind, wählen Sie **[!UICONTROL +*x* mehr]** aus, um das Panel **[!UICONTROL Enthaltene Datensätze]** anzuzeigen. In diesem Bedienfeld werden Links zu allen Datensätzen und eine Option zum ![Suchen](/help/assets/icons/Search.svg) nach bestimmten Datensätzen angezeigt, die Teil der Verbindung sind.<p>![Datensätze enthalten](assets/datasets-included.png)<p>Wählen Sie einen Datensatznamen aus, um den Datensatz in der Benutzeroberfläche von Experience Platform in einer neuen Registerkarte zu öffnen. |
| **[!UICONTROL Sandbox]** | Die [Experience Platform-Sandbox](https://experienceleague.adobe.com/de/docs/experience-platform/sandbox/home), aus der diese Verbindung ihre Datensätze abruft. Sie wählen diese Sandbox aus, als Sie die Verbindung erstellt haben. Sie können die Sandbox nicht mehr ändern, sobald eine Verbindung gespeichert wurde. |
| **[!UICONTROL Inhaber]** | Die Person, die die Verbindung hergestellt hat. |
| **[!UICONTROL Importieren neuer Daten]** | Der Status des Imports neuer Daten für Datensätze: <p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _Ein]**&#x200B;für Datensätze, die zum Importieren neuer Daten konfiguriert sind, und<p>![Status gray](assets/status-gray.svg)   **[!UICONTROL _x Aus_]** für Datensätze, die nicht für den Import neuer Daten konfiguriert sind. |
| **[!UICONTROL Erstellt am]** | Der Zeitstempel, wann die Verbindung erstellt wurde. |
| **[!UICONTROL Zuletzt geändert]** | Der Zeitstempel, wann die Verbindung zuletzt aktualisiert wurde. |
| **[!UICONTROL Aufstockungsdaten]** | Der Status für die Aufstockung von Daten in allen Datensätzen:<p>![Status red](assets/status-red.svg)   **[!UICONTROL _x _Aufstockungen fehlgeschlagen]**&#x200B;für die Anzahl der datensatzübergreifend fehlgeschlagenen Aufstockungen über Datensätze,<p>![Status orange](assets/status-orange.svg)   **[!UICONTROL _x _Aufstockungen werden verarbeitet]**&#x200B;für die Anzahl der datensatzübergreifend verarbeiteten Aufstockungen,<p>![Status grün](assets/status-green.svg)   **[!UICONTROL _x _Aufstockungen abgeschlossen]**&#x200B;für die Anzahl der abgeschlossenen Aufstockungen für Datensätze,<p>![Status gray](assets/status-gray.svg)   **[!UICONTROL _Aus_]**, falls für die Datensätze in der Verbindung keine Aufstockungen definiert sind. |

Um zu konfigurieren, welche Spalten in der Tabelle angezeigt werden sollen, wählen Sie ![Spalteneinstellungen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) aus. Wählen Sie im Dialogfeld Tabelle anpassen die anzuzeigenden Spalten aus.

### Verbindung bearbeiten

So bearbeiten Sie eine Verbindung:

1. Wählen Sie ![More](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) neben dem Verbindungsnamen aus
1. Wählen Sie im Kontextmenü die Option ![Edit](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Bearbeiten]** aus.

Sie können auch wie folgt vorgehen:

1. Wählen Sie die Verbindungszeile aus.

1. Wählen ![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Bearbeiten]** in der blauen Aktionsleiste aus.

Weitere Informationen finden Sie unter [Erstellen oder Bearbeiten einer Verbindung](create-connection.md).


### Eine Verbindung löschen {#connections-delete}

So löschen Sie eine Verbindung:

1. Wählen Sie ![More](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) neben dem Verbindungsnamen aus.
1. Wählen Sie ![Delete](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Löschen]** aus.

Sie können auch wie folgt vorgehen:

1. Wählen Sie die Verbindungszeile aus.

1. Wählen ![Löschen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Löschen]** in der blauen Aktionsleiste aus.

Wenn Sie eine Verbindung löschen, wird im Panel **[!UICONTROL Verbindung löschen]** angezeigt, welche Datenansichten gelöscht werden und welche Workspace-Projekte betroffen sind.

* In ➊ **[!UICONTROL Info]** werden die Auswirkungen des Löschens der Verbindung angezeigt.

  ![Löschen einer Verbindung](assets/delete-connection.png)

  Klicken Sie **[!UICONTROL Fortfahren]**, um den Löschvorgang zu bestätigen.

* Geben Sie ➋ **[!UICONTROL Bestätigung]** den Namen der Verbindung in **[!UICONTROL Verbindungsnamen eingeben]** ein und wählen Sie **[!UICONTROL Löschen]**, um die Verbindung zu löschen. Wählen Sie zum Abbrechen **[!UICONTROL Abbrechen]** aus.

Weitere Informationen zum Löschen einer Verbindung finden Sie unter [Auswirkungen des Löschens](/help/technotes/deletion.md).


### Erstellen einer Datenschicht für eine Verbindung

So erstellen Sie eine Datenansicht für eine Verbindung:

1. Wählen Sie ![More](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) neben dem Verbindungsnamen aus.
1. Wählen Sie ![Add data view](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Neue Datenansicht erstellen]** aus.

Sie können auch wie folgt vorgehen:

1. Wählen Sie die Verbindungszeile aus.

1. Wählen Sie ![Datenansicht hinzufügen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Datenansicht erstellen]** in der blauen Aktionsleiste aus.

Weitere Informationen finden Sie unter [Erstellen oder Bearbeiten einer Datenansicht](/help/data-views/create-dataview.md).


### Zuordnen einer Verbindung

So zeigen Sie eine [Verbindungszuordnung](/help/connections/create-connection.md#connection-map) an, die die Beziehungen zwischen den Datensätzen, die Teil einer Verbindung sind, genau angibt:

1. Wählen Sie ![Mehr](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) neben dem Verbindungsnamen aus.
1. Wählen Sie ![Diagrammpfade](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Verbindungszuordnung]** aus.

### Verbindungsdetails {#connection-detail}

Um zu den Details einer Verbindung zu wechseln, wählen Sie einen Hyperlink-Verbindungsnamen in der Tabelle Verbindungen aus.

![Fenster Alle Datensätze mit den Widgets und Einstellungen](assets/conn-details.png)

In der Benutzeroberfläche mit den Verbindungsdetails erhalten Sie einen sehr detaillierten Überblick über den Status einer Verbindung. Sie haben folgende Möglichkeiten:

* Überprüfen Sie den Status der Datensätze Ihrer Verbindung und des Aufnahmevorgangs.
* Identifizieren Sie Konfigurationsprobleme, die zu übersprungenen oder gelöschten Datensätzen führen können.
* Finden Sie heraus, wann die Daten für das Reporting verfügbar sind.

| Benutzeroberfläche | Beschreibung |
| --- | --- |
| ![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Verbindung bearbeiten]** | Um die Details einer Verbindung zu bearbeiten, wählen Sie ![Edit](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Verbindung bearbeiten]** aus. Weitere Informationen finden Sie unter [Erstellen oder Bearbeiten einer Verbindung](create-connection.md). |
| **[!UICONTROL *Datensatzauswahl *]** | Wählen Sie einen oder alle Datensätze aus, um Details für in der Verbindung anzuzeigen. Datensätze können nicht mehrmals ausgewählt werden. Die Standardeinstellung ist **[!UICONTROL Alle Datensätze]**. |
| **[!UICONTROL *Datumsbereichsauswahl *]** | Wählen Sie einen Datenbereich aus, um Details für in der Verbindung anzuzeigen. Bearbeiten Sie das Start- und Enddatum oder wählen Sie ![Calendar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) aus, um die Datumsbereichsauswahl zu öffnen. Wählen Sie in der Datumsbereichsauswahl einen Datumsbereich aus, indem Sie einen der vordefinierten Zeiträume verwenden (z. B. **[!UICONTROL Letzte 6 Monate]**), oder legen Sie das Start- und Enddatum über den Kalender fest. Wählen Sie **[!UICONTROL Anwenden]** aus, um den neuen Datumsbereich auf die Verbindungsdetails anzuwenden. |
| **[!UICONTROL Verfügbare Einträge von Ereignisdaten]** | Die Gesamtzahl der für das Reporting verfügbaren Ereignisdatensätze **für die gesamte Verbindung**. Diese Anzahl ist unabhängig von einem Datumsbereich oder einer Datensatzauswahl. |
| [!UICONTROL **[!UICONTROL Metriken]**] | Fasst die hinzugefügten, übersprungenen und gelöschten Ereignis-, Lookup-, Profil- und Zusammenfassungs-Datensatzeinträge sowie die Anzahl der hinzugefügten Batches zusammen. Diese Metriken basieren auf **dem ausgewählten Datensatz und Datumsbereich**.<p>Wählen Sie **[!UICONTROL Detail überprüfen]** aus, um das Popup **[!UICONTROL Übersprungenes Detail überprüfen]** anzuzeigen. Im Popup werden die Anzahl der übersprungenen Datensätze und der Grund für alle Ereignisdatensätze oder ausgewählten Datensätze aufgeführt.<p>![Übersprungene Datensätze](assets/skipped-records.png)<p>Wählen Sie das Popup ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) mit weiteren Informationen aus. Aus einigen übersprungenen Gründen, z. B. [!UICONTROL Leere Besucher-ID], zeigt das Popup **[!UICONTROL Beispiel-PSQL für EQS]** (Experience Platform für Abfrage-Service) an, die Sie in [Abfrage-Service](https://experienceleague.adobe.com/de/docs/experience-platform/query/home) verwenden können, um die übersprungenen Datensätze im Datensatz abzufragen. Wählen Sie ![Copy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL Muster-PSQL für EQS kopieren]** aus, um die SQL zu kopieren. |
| **[!UICONTROL Hinzugefügte Datensätze]** | Eine Visualisierung, die angibt, wie viele Zeilen im ausgewählten Zeitraum hinzugefügt wurden **für den ausgewählten Datensatz und Datumsbereich**. Aktualisierungen alle 10 Minuten. |
| **[!UICONTROL Übersprungene Datensätze]** | Eine Visualisierung, die anzeigt, wie viele Zeilen im ausgewählten Zeitraum übersprungen wurden **für den ausgewählten Datensatz und den ausgewählten Datumsbereich**. B2B edition Gründe für das Überspringen von Datensätzen sind: fehlende Zeitstempel, fehlende oder ungültige Personen-ID oder Konto-ID {type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} usw. Aktualisierungen alle 10 Minuten. <p>Ungültige IDs (z. B. `undefined` oder `00000000` oder jede Kombination aus Zahlen und Buchstaben in einer [!UICONTROL Personen-ID], die in einem Ereignis mehr als eine Million Mal in einem bestimmten Monat auftritt) sind IDs, die keiner bestimmten Benutzerin bzw. keinem bestimmten Benutzer oder keiner bestimmten Person zugeordnet werden können. Diese Zeilen können nicht in das System aufgenommen werden und führen möglicherweise zu Fehlern bei Datenaufnahme und Reporting. Um ungültige Personen- oder Konto-IDs [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} zu beheben, haben Sie drei Möglichkeiten:<ul><li>Verwenden Sie die [Zuordnungsfunktion](/help/stitching/overview.md), um die Benutzer-IDs, die nicht definiert sind oder nur Nullen enthalten, mit gültigen Benutzer-IDs aufzufüllen.</li><li>Blenden Sie Benutzer-IDs aus, die dann während der Aufnahme übersprungen werden (was ungültigen oder Benutzer-IDs mit nur null vorzuziehen ist).</li><li>Korrigieren Sie alle ungültigen Benutzer-IDs in Ihrem System, bevor Sie die Daten aufnehmen.</li></ul> |
| **[!UICONTROL Gelöschte Einträge]** | Eine Visualisierung, die anzeigt, wie viele Zeilen im ausgewählten Zeitraum gelöscht wurden **für den ausgewählten Datensatz und Datumsbereich**. Beispielsweise könnte jemand einen Datensatz in [!DNL Experience Platform] gelöscht haben. Aktualisierungen alle 10 Minuten.<p>In einigen Szenarien kann dieser Wert auch ersetzte Datensätze enthalten, wie etwa bei der Zuordnung oder bei einigen Aktualisierungen von Lookup-Datensätzen. Sehen Sie sich dieses Beispiel an:</p><ul><li>Sie laden einen Datensatz in einen Datensatz vom Typ „XDM-Profil für Einzelpersonen“ hoch, der von Customer Journey Analytics als Profil-Lookup-Daten aufgenommen wird. In den Verbindungsdetails wird für diesen Datensatz angezeigt, dass ein Datensatz hinzugefügt wurde.</li><li>Sie laden ein Duplikat des ursprünglichen Datensatzes in denselben AEP-Datensatz hoch, der jetzt zwei Datensätze enthält. Customer Journey Analytics nimmt den zusätzlichen Eintrag aus dem Profil-Lookup-Datensatz oder Konto-Lookup-Datensatz [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} auf. Da für diese Personen-ID oder Konto-ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} bereits ein Profil- oder Kontodatensatz in die Verbindung aufgenommen wurde, löscht Customer Journey Analytics seine frühere Version und fügt die neuen Profildaten hinzu. In den Verbindungsdetails würde diese Aktion bedeuten, dass 1 Datensatz hinzugefügt und 1 Datensatz gelöscht wird, da Customer Journey Analytics nur die neuesten Profilsuchdaten für eine aufgenommene Personen-ID oder Konto-ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} beibehält.</li><li>Insgesamt enthält der AEP-Datensatz zwei Datensätze, die zufällig identisch sind. Separat zeigen die Customer Journey Analytics-Verbindungsdetails den Status der aufgenommenen Daten an: Für diesen Profildatensatz wurden zwei Datensätze hinzugefügt und ein Datensatz gelöscht. </li></ul> |
| ![Durchsuchen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | Das Datensatz-Suchfeld. Sie können die Datensatztabelle nach Datensatznamen oder Datensatz-ID durchsuchen. |
| [!UICONTROL Datensatztabelle] | Die Datensätze, die Teil der Verbindung sind. Weitere Erläuterungen finden Sie in der unten stehenden Tabelle. Wählen Sie ![SelectBox](/help/assets/icons/SelectBox.svg) einen einzelnen Datensatz aus, um nur Verbindungsdetails für den ausgewählten Datensatz anzuzeigen. Dies entspricht der Auswahl eines Datensatzes aus der **[!UICONTROL _Datensatzauswahl_]**. |

Die Tabelle Datensätze zeigt für jeden Datensatz die folgenden Spalten an:

| Spalte | Beschreibung |
| --- | --- |
| **[!UICONTROL Datensätze]** | Der Name des Datensatzes. Sie können den Hyperlink auswählen, um den Datensatz in der Experience Platform-Benutzeroberfläche auf einer neuen Registerkarte zu öffnen. Sie können die Zeile auswählen oder das Kontrollkästchen aktivieren, um nur Details für den ausgewählten Datensatz anzuzeigen. |
| **[!UICONTROL Datensatz-ID]** | Die von Experience Platform generierte Datensatz-ID. |
| **[!UICONTROL Hinzugefügte Datensätze]** | Die Anzahl der Datensatzdatensätze (Zeilen), die einer Verbindung während des ausgewählten Datumsbereichs hinzugefügt wurden. |
| **[!UICONTROL Übersprungene Datensätze]** | Die Anzahl der bei der Datenübertragung für eine Verbindung übersprungenen Datensatzdatensätze (Zeilen) im ausgewählten Datumsbereich. |
| **[!UICONTROL Gelöschte Einträge]** | Die Anzahl der Datensätze (Zeilen), die während des ausgewählten Datumsbereichs aus einer Verbindung entfernt wurden. |
| **[!UICONTROL Batches hinzugefügt]** | Die Anzahl der Batches, die einer Verbindung im ausgewählten Datumsbereich hinzugefügt wurden. |
| **[!UICONTROL Zuletzt hinzugefügt]** | Der Zeitstempel des letzten Batches, der einer Verbindung hinzugefügt wurde. |
| **[!UICONTROL Datenquellentyp]** | Der Quelltyp. Sie definieren den Quelltyp, wenn Sie einen Datensatz zu einer Verbindung hinzufügen. |
| **[!UICONTROL Typ des Datensatzes]** | Der [Datensatztyp](create-connection.md#dataset-types). Der Typ kann [!UICONTROL Ereignis], [!UICONTROL Profil], [!UICONTROL Suche] oder [!UICONTROL Zusammenfassung]. |
| **[!UICONTROL Schema]** | Das Experience Platform-Schema, auf dem der Datensatz basiert. |
| **[!UICONTROL Importieren neuer Daten]** | Der Status des Imports neuer Daten für den Datensatz: <p>![Status green](assets/status-green.svg)   **[!UICONTROL _x _Ein]**, wenn der Datensatz für den Import neuer Daten konfiguriert ist,<p>![Status gray](assets/status-gray.svg)   **[!UICONTROL _x Aus_]**, wenn der Datensatz so konfiguriert ist, dass keine neuen Daten importiert werden. |
| **[!UICONTROL Umwandeln von Daten]** | Der Umwandlungsstatus von entsprechenden B2B-Lookup-Datensätzen. Weitere Informationen finden Sie unter [Umwandeln von Datensätzen für B2B-Suchen](transform-datasets-b2b-lookups.md).<p>![Status green](assets/status-green.svg)   **[!UICONTROL _x _Ein]**&#x200B;für entsprechende Datensätze, die für die Umwandlung aktiviert sind, <p>![Status gray](assets/status-gray.svg)   **[!UICONTROL _x Aus_]** für entsprechende Datensätze, die nicht für die Umwandlung aktiviert sind,<p>**[!UICONTROL Nicht zutreffend]** für alle anderen Datensätze, nicht für eine Umwandlung in Frage kommen. |
| **[!UICONTROL Aufstockungsdaten]** | Der Status der Aufstockungsdaten für den Datensatz.<p>![Status red](assets/status-red.svg)   **[!UICONTROL _x _Aufstockungen fehlgeschlagen]**&#x200B;für die Anzahl der fehlgeschlagenen Aufstockungen,<p>![Status orange](assets/status-orange.svg)   **[!UICONTROL _x _Aufstockungen werden verarbeitet]**&#x200B;für die Anzahl der verarbeiteten Aufstockungen,<p>![Status green](assets/status-green.svg)   **[!UICONTROL _x _Aufstockungen abgeschlossen]**&#x200B;für die Anzahl der abgeschlossenen Aufstockungen,<p>![Status gray](assets/status-gray.svg)   **[!UICONTROL _Aus_]**, falls keine Aufstockungen konfiguriert sind. |

>[!IMPORTANT]
>
>Daten, die vor dem 13. August 2021 aufgenommen wurden, werden in der Benutzeroberfläche [!UICONTROL Verbindungen] nicht angezeigt.
>

#### Panel „Verbindung“

Wenn kein einzelner Datensatz in der Datensatztabelle ausgewählt ist, zeigt der rechte Bereich Verbindungsoptionen und -details an.

| Optionen | Beschreibung |
| --- | --- |
| ![Refresh](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Aktualisieren]** | Um die Verbindung zu aktualisieren und die Anzeige kürzlich hinzugefügter Datensätze zuzulassen, wählen Sie ![Refresh](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Aktualisieren]** aus. |
| ![Löschen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Löschen]** | [Löschen](#delete-a-connection) Sie diese Verbindung. |
| ![Add data view](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Datenansicht erstellen]** | [Erstellen Sie eine Datenansicht](#create-a-data-view) auf Grundlage dieser Verbindung. Weitere Informationen finden Sie unter [Datenansichten](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/data-views). |
| **[!UICONTROL Name der Verbindung]** | Der Anzeigename der Verbindung. |
| **[!UICONTROL Beschreibung der Verbindung]** | Die Beschreibung der Verbindung. |
| **[!UICONTROL Sandbox]** | Die [Experience Platform-Sandbox](https://experienceleague.adobe.com/de/docs/experience-platform/sandbox/home), aus der diese Verbindung ihre Datensätze abruft. Sie wählen diese Sandbox aus, als Sie die Verbindung erstellt haben. Sie können die Sandbox nicht mehr ändern, sobald eine Verbindung gespeichert wurde. |
| **[!UICONTROL Verbindungs-ID]** | Eine generierte Kennung für die Verbindung. Sie können ![Kopieren](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) verwenden, um den Wert zu kopieren. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Primärer ID-Typ &#x200B;]** | Der primäre ID-Typ für die Verbindung **[!UICONTROL (Person]** für eine personenbasierte Verbindung, **[!UICONTROL Konto]** für eine kontobasierte Verbindung. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Containers &#x200B;]** | Die konfigurierten Container für die Verbindung. |
| **[!UICONTROL Datenaufrufe, die Verbindungen verwenden]** | Die Datenansichten, die diese Verbindung verwenden. |
| **[!UICONTROL Importieren neuer Daten]** | Der Status des Imports neuer Daten für Datensätze: <p>![Status green](assets/status-green.svg)   **[!UICONTROL _x _Ein]**&#x200B;für die Anzahl der Datensätze, die für den Import neuer Daten konfiguriert sind,<p>![Status gray](assets/status-gray.svg)   **[!UICONTROL _x Aus_]** für die Anzahl der Datensätze, für die der Import neuer Daten deaktiviert ist. |
| **[!UICONTROL Aufstockungsdaten]** | Der Status der Aufstockungsdaten für Datensätze:<p>![Status red](assets/status-red.svg)   **[!UICONTROL _x _Aufstockungen fehlgeschlagen]**&#x200B;für die Anzahl der datensatzübergreifend fehlgeschlagenen Aufstockungen,<p>![Status orange](assets/status-orange.svg)   **[!UICONTROL _x _Aufstockungen werden verarbeitet]**&#x200B;für die Anzahl der datensatzübergreifend verarbeiteten Aufstockungen,<p>![Status green](assets/status-green.svg)   **[!UICONTROL _x _Aufstockungen abgeschlossen]**&#x200B;für die Anzahl der abgeschlossenen Aufstockungen für Datensätze,<p>![Status gray](assets/status-gray.svg)   **[!UICONTROL _Aus_]**, falls für die Datensätze in der Verbindung keine Aufstockungen definiert sind. |
| **[!UICONTROL Umwandeln von Daten]** | Der Umwandlungsstatus von entsprechenden B2B-Lookup-Datensätzen. Weitere Informationen finden Sie unter [Umwandeln von Datensätzen für B2B-Suchen](transform-datasets-b2b-lookups.md).<p>![Status green](assets/status-green.svg)   **[!UICONTROL _x _Ein]**&#x200B;für die Anzahl der für die Umwandlung aktivierten Datensätze. |
| **[!UICONTROL Erstellt von]** | Der Name der Person, die die Verbindung erstellt hat. |
| **[!UICONTROL Zuletzt geändert]** | Der Zeitstempel der letzten Änderung der Verbindung. |
| **[!UICONTROL Zuletzt geändert von]** | Der Name der Person, die die Verbindung zuletzt geändert hat. |

#### Panel „Datensatz“

Wenn eine Datensatzzeile in der Datensatztabelle ausgewählt ist, werden in einem Panel auf der rechten Seite der Benutzeroberfläche „Verbindung“ Details zum ausgewählten Datensatz angezeigt.

| Details | Beschreibung |
| --- | --- |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL ID des globalen Kontos &#x200B;]** | Die Identität, die Sie als globale Konto-ID für die Verbindung angegeben haben. Gilt nur für eine kontobasierte Verbindung, für die ein Container für ein globales Konto konfiguriert ist. |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Konto-ID &#x200B;]** | Die Identität, die Sie als Konto-ID für die Verbindung angegeben haben. Gilt nur für eine kontobasierte Verbindung, für die kein globaler Konto-Container konfiguriert ist. |
| **[!UICONTROL Personen-ID]** | Die Identität, die Sie als Personen-ID für die Verbindung angegeben haben. |
| **[!UICONTROL Schlüssel]** | Der Schlüssel, den Sie für einen Lookup-Datensatz angegeben haben. |
| **[!UICONTROL Übereinstimmender Schlüssel]** | Der übereinstimmende Schlüssel, den Sie für einen Lookup-Datensatz angegeben haben. |
| **[!UICONTROL Zeitstempel]** | Der für einen Ereignisdatensatz definierte Zeitstempel. |
| **[!UICONTROL Verfügbare Datensätze]** | Die Gesamtzahl der Zeilen, die für diesen Datensatz in dem im Kalender ausgewählten Zeitraum aufgenommen wurden. Es gibt keine Latenz im Hinblick darauf, ab wann die Daten nach dem Hinzufügen in Berichten angezeigt werden. Wenn Sie jedoch eine völlig neue Verbindung erstellen, gibt es eine [Latenz](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-faq). |
| **[!UICONTROL Hinzugefügte Datensätze]** | Die Anzahl der Datensatzdatensätze (Zeilen), die einer Verbindung während des ausgewählten Datumsbereichs hinzugefügt wurden. |
| **[!UICONTROL Übersprungene Datensätze]** | Die Anzahl der bei der Datenübertragung für eine Verbindung übersprungenen Datensatzdatensätze (Zeilen) im ausgewählten Datumsbereich. |
| **[!UICONTROL Batches hinzugefügt]** | Die Anzahl der Batches, die einer Verbindung hinzugefügt wurden. |
| **[!UICONTROL Gelöschte Einträge]** | Die Anzahl der Datensätze (Zeilen), die während des ausgewählten Datumsbereichs aus einer Verbindung entfernt wurden. |
| **[!UICONTROL Zuletzt hinzugefügt]** | Der Zeitstempel des letzten Batches, der einer Verbindung hinzugefügt wurde. |
| **[!UICONTROL Importieren neuer Daten]** | Der Status des Imports neuer Daten für den Datensatz: <p>![Status green](assets/status-green.svg)   **[!UICONTROL _x _Ein]**, wenn der Datensatz für den Import neuer Daten konfiguriert ist,<p>![Status gray](assets/status-gray.svg)   **[!UICONTROL _x Aus_]**, wenn der Datensatz so konfiguriert ist, dass keine neuen Daten importiert werden. |
| **[!UICONTROL Aufstockungsdaten]** | Der Status der Aufstockungsdaten für den Datensatz.<p>![Status red](assets/status-red.svg)   **[!UICONTROL _x _Aufstockungen fehlgeschlagen]**&#x200B;für die Anzahl der fehlgeschlagenen Aufstockungen,<p>![Status orange](assets/status-orange.svg)   **[!UICONTROL _x _Aufstockungen werden verarbeitet]**&#x200B;für die Anzahl der verarbeiteten Aufstockungen,<p>![Status green](assets/status-green.svg)   **[!UICONTROL _x _Aufstockungen abgeschlossen]**&#x200B;für die Anzahl der abgeschlossenen Aufstockungen,<p>![Status gray](assets/status-gray.svg)   **[!UICONTROL _Aus_]**, falls keine Aufstockungen konfiguriert sind.<p>Um ein Dialogfeld mit einer Übersicht über die früheren Aufstockungen für den Datensatz anzuzeigen, wählen Sie <img src="./assets/pastbackfill.svg" alt="Frühere Aufstockungen" width="15"/> **[!UICONTROL Frühere Aufstockungen]** aus. |
| **[!UICONTROL Datenquellentyp]** | Datenquellentyp, wie er beim Hinzufügen des Datensatzes zur Verbindung definiert wurde. |
| **[!UICONTROL Typ des Datensatzes]** | Der [Datensatztyp](create-connection.md#dataset-types). |
| **[!UICONTROL Schema]** | Das Experience Platform-Schema, auf dem dieser Datensatz basiert. |
| **[!UICONTROL Datensatz-ID]** | Die Datensatz-ID, wie in Experience Platform generiert. |


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
>abstract="Für die Monate vor September 2024 wurden Daten auf Datensatzebene erfasst. Sie werden der Klarheit halber als *andere Datensätze* angezeigt. Seit September 2024 werden Daten auf einer granularen Datensatzebene erfasst und *andere Datensätze* werden nicht mehr angezeigt."
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
>abstract="Historische Daten, die älter sind als September 2024, sind aufgrund von Systembeschränkungen nicht verfügbar. Metriken werden seit September 2024 erfasst und angezeigt. Das Diagramm zeigt die letzten 18 Monate in der Timeline und zukünftige Daten werden angezeigt, sobald die Daten verfügbar werden."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_corereportablerows"
>title="Berichtsfähige Zeilen zu Kerndaten"
>abstract="Die Gesamtzahl der für die letzten 13 Monate verfügbaren Zeilen. Beispielsweise zeigt die Zahl am 1. Februar 2024 die Gesamtzahl der verfügbaren Zeilen mit einem Ereignis-Zeitstempel von Januar 2023 bis Januar 2024 an."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_historicalreportablerows"
>title="Berichtsfähige Zeilen zu historischen Daten"
>abstract="Die Gesamtzahl der verfügbaren Zeilen für den Zeitraum, der länger als 13 Monate zurückliegt. Beispielsweise zeigt die Zahl am 1. Februar 2024 die Gesamtzahl der verfügbaren Zeilen mit einem Ereignis-Zeitstempel an, der älter als Januar 2023 ist."

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
>abstract="Für die Monate vor September 2024 wurden Daten auf Datensatzebene erfasst. Sie werden der Klarheit halber als *andere Datensätze* angezeigt. Seit September 2024 werden Daten auf einer granularen Datensatzebene erfasst und *andere Datensätze* werden nicht mehr angezeigt."
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
>abstract="Historische Daten, die älter sind als September 2024, sind aufgrund von Systembeschränkungen nicht verfügbar. Metriken werden seit September 2024 erfasst und angezeigt. Das Diagramm zeigt die letzten 18 Monate in der Timeline und zukünftige Daten werden angezeigt, sobald die Daten verfügbar werden."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_corereportablerows"
>title="Berichtsfähige Zeilen zu Kerndaten"
>abstract="Die Gesamtzahl der für die letzten 13 Monate verfügbaren Zeilen. Beispielsweise zeigt die Zahl am 1. Februar 2024 die Gesamtzahl der verfügbaren Zeilen mit einem Ereignis-Zeitstempel von Januar 2023 bis Januar 2024 an."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_historicalreportablerows"
>title="Berichtsfähige Zeilen zu historischen Daten"
>abstract="Die Gesamtzahl der verfügbaren Zeilen für den Zeitraum, der länger als 13 Monate zurückliegt. Beispielsweise zeigt die Zahl am 1. Februar 2024 die Gesamtzahl der verfügbaren Zeilen mit einem Ereignis-Zeitstempel an, der älter als Januar 2023 ist."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_breakdown_corereportablerows"
>title="Berichtsfähige Zeilen zu Kerndaten"
>abstract="Berichtsfähige Zeilen zu Kerndaten sind Momentaufnahmenwerte, keine aggregierten Gesamtwerte. Diese Werte werden basierend auf dem letzten Monat im ausgewählten Datumsbereich dynamisch aktualisiert. Bei der Auswahl von Januar bis März spiegeln die Werte die Momentaufnahme von März wider."

>[!CONTEXTUALHELP]
>id="connections_breakdown_historicalreportablerows"
>title="Berichtsfähige Zeilen zu historischen Daten"
>abstract="Berichtsfähige Zeilen zu historischen Daten sind Momentaufnahmenwerte, keine aggregierten Gesamtwerte. Diese Werte werden basierend auf dem letzten Monat im ausgewählten Datumsbereich dynamisch aktualisiert. Bei der Auswahl von Januar bis März spiegeln die Werte die Momentaufnahme von März wider."

>[!CONTEXTUALHELP]
>id="connections_breakdown_cumulativereportablerows"
>title="Kumulative berichtsfähige Zeilen"
>abstract="Kumulative berichtsfähige Zeilen sind Momentaufnahmenwerte, keine aggregierten Gesamtwerte. Diese Werte werden basierend auf dem letzten Monat im ausgewählten Datumsbereich dynamisch aktualisiert. Bei der Auswahl von Januar bis März spiegeln die Werte die Momentaufnahme von März wider."

<!-- markdownlint-enable MD034 -->



In der Benutzeroberfläche [!UICONTROL Nutzung] wird die Verwendung von aufgenommenen und berichtsfähigen Zeilen über alle Verbindungen hinweg angezeigt. Wenn sie nicht ausgewählt ist, wählen Sie die Registerkarte **[!UICONTROL Nutzung]** aus, um auf die Benutzeroberfläche zuzugreifen.

Über diese Benutzeroberfläche können Sie ermitteln, ob Ihre Customer Journey Analytics-Nutzung den vertraglich vereinbarten Bedingungen entspricht. Zusätzlich zur Überwachung können Sie die Benutzeroberfläche „Nutzung“ verwenden, um die Verlängerung Ihrer Customer Journey Analytics-Lizenz zu planen.

Die Benutzeroberfläche verwendet die folgenden Metriken:

| Metrikname | Beschreibung |
|---|---|
| Berichtsfähige Zeilen zu historischen Daten | Die Anzahl der Zeilen für den Zeitraum, der länger als 13 Monate zurückliegt. |
| Berichtsfähige Zeilen zu Kerndaten | Die Anzahl der Zeilen in den letzten 13 Monaten. |
| Aufgenommene Zeilen | Die Anzahl der im jeweiligen Zeitraum aufgenommenen Zeilen. |
| Berichtsfähige Zeilen | Die Anzahl der Datenzeilen, die als Teil der Verbindung für den angegebenen Zeitraum vorliegen. |
| Kumulative Zeilen | Die Anzahl der Zeilen, die bis zum angegebenen Monat aufgenommen werden. |

>[!NOTE]
>
>Die Daten werden ab Juli 2024 für die Kern-, historischen und Gesamtdatensätze erfasst. Wenden Sie sich an die Kundenbetreuung, wenn Sie frühere historische Daten benötigen.
>



Die Benutzeroberfläche „Nutzung“ besteht aus zwei Panels:

* Das Panel **[!UICONTROL Schlüsselnutzungsmetriken]** bietet berichtsfähige Zeilen zu Kern- und historischen Daten. Außerdem werden prozentuale Änderungen im Vergleich zum Vormonat sowohl für Kern- als auch für historische Datenzeilen verfolgt.

  Das Bedienfeld zeigt eine Visualisierung an, die Folgendes enthält:

   * **[!UICONTROL Berichtsfähige Zeilen zu Kerndaten]**.

     Die Anzahl der berichtsfähigen Zeilen in den letzten 13 Monaten. Die Zusammenfassungszahl ist die Anzahl der berichtsfähigen Zeilen zu Kerndaten (z. B. 741 Mio.) für den letzten Monat (z. B. Dezember 2024).

   * **[!UICONTROL Berichtsfähige Zeilen zu historischen Daten]**.

     Die Anzahl der berichtsfähigen Zeilen für den Zeitraum, der länger als 13 Monate zurückliegt. Die Zusammenfassungszahl ist die Anzahl der berichtsfähigen Zeilen zu historischen Daten (z. B. 127 Mio.) für den letzten Monat (z. B. Dezember 2024).

  Wenn Sie den Mauszeiger über einen gestapelten Balken in der Visualisierung bewegen, wird in einem Popup die Anzahl der Zeilen für diesen bestimmten Teil des Balkens angezeigt, z. B.:


  ![Schlüsselnutzungsmetriken](assets/usage-key-usage-metrics.png)

* Ein kombiniertes Panel mit den drei folgenden Unter-Panels:

+++ Aufgenommene Zeilen

  Das Unter-Panel **[!UICONTROL Aufgenommene Zeilen]** misst die Gesamtzahl der Datensätze, die dem System jeden Monat hinzugefügt werden, und liefert Erkenntnisse zu Datenwachstum und Aufnahmeraten. Dieses Unter-Panel bietet eine Zusammenfassung der insgesamt aufgenommenen Zeilen dieses Monats und der Änderung gegenüber dem Vormonat.

  ![Aufgenommene Zeilen](assets/usage-ingested-rows.png)

  Sie können den Mauszeiger über Datenpunkte in der Visualisierung bewegen, um ein Popup mit weiteren Details anzuzeigen.

+++

+++ Berichtsfähige Zeilen

  Die Visualisierung **[!UICONTROL Berichtsfähige Zeilen]** verfolgt die Anzahl der für die das Reporting verfügbaren Zeilen, indem übersprungene und gelöschte Zeilen von den aufgenommenen Zeilen subtrahiert werden. Dies dient als Schlüsselmetrik für die Abrechnung und die Datennutzung. Dieses Unter-Panel bietet zwei Zusammenfassungen:

   * **[!UICONTROL Letzter Monat insgesamt]**: Eine Zusammenfassung der insgesamt berichtsfähigen Zeilen bis zu diesem Monat.
   * **[!UICONTROL Dieser Monat]**: Eine Zusammenfassung der insgesamt berichtsfähigen Zeilen dieses Monats und der Änderung gegenüber dem Vormonat.

  ![Berichtsfähige Zeilen](assets/usage-reportable-rows.png)

  Sie können den Mauszeiger über Datenpunkte in den Visualisierungen bewegen, um ein Popup mit weiteren Details anzuzeigen.

+++

+++ Detailaufschlüsselung

  Sie können die Tabelle **[!UICONTROL Detailaufschlüsselung]** verwenden, um detaillierte Metriken nach Verbindung, Datensatz, Sandbox und Tags anzuzeigen. Über Datensätze wird mit IDs anstelle von Namen berichtet, da Datensatznamen während eines Berichtszeitraums geändert werden können. Über unbekannte Datensätze oder Verbindungen wird mithilfe von IDs berichtet.

  Seit Monaten vor September 2024 wurden Daten auf Datensatzebene erfasst. Sie werden der Klarheit halber als [!UICONTROL andere Datensätze] angezeigt. Ab September 2024 werden Daten auf einer granularen Datensatzebene erfasst und [!UICONTROL Andere Datensätze] werden nicht mehr angezeigt.

   * Um die Aufschlüsselung zu ändern, wählen Sie eine Kombination für **[!UICONTROL Anzeigen nach]** und **[!UICONTROL Aufschlüsselung nach]** aus.

     | Optionen **[!UICONTROL Anzeigen nach]** | Optionen **[!UICONTROL Aufschlüsselung nach]** |
     |---|---|
     | **[!UICONTROL Verbindung]** | **[!UICONTROL -]** und **[!UICONTROL Datensatz]** |
     | **[!UICONTROL Datensatz]** | **[!UICONTROL -]** |
     | **[!UICONTROL Sandbox]** | **[!UICONTROL Verbindung]** |
     | **[!UICONTROL Tag]** | **[!UICONTROL Verbindung]** |

  ![Detailaufschlüsselung](assets/usage-detail-breakdown.png)

+++

  Sie können einen **[!UICONTROL Zeitraum]** in Monaten definieren, über den berichtet werden soll. Verwenden Sie ![Calendar](/help/assets/icons/Calendar.svg), um den Zeitraum auszuwählen.

>[!MORELIKETHIS]
>
>Tutorial [Anzeigen, Beheben von Problemen und Ändern von Verbindungseinstellungen](https://experienceleague.adobe.com/de/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja).
>&#x200B;>[Verwalten der Customer Journey Analytics-Nutzung](/help/technotes/estimate-usage.md)
>
