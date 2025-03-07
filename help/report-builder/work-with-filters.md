---
title: Verwenden von Segmenten in Report Builder in Customer Journey Analytics
description: Beschreibt die Verwendung von Segmenten in Report Builder für Customer Journey Analytics
role: User
feature: Report Builder
type: Documentation
exl-id: 1f39d7f4-b508-45d8-9b97-81242c3805d3
solution: Customer Journey Analytics
source-git-commit: 0d87f28aa4f8c1b16f46227abad7d374800dcb66
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 56%

---

# Arbeiten mit Segmenten in Report Builder

Segmente können angewendet werden, wenn Sie einen neuen Datenblock erstellen oder wenn Sie die Option **Datenblock bearbeiten** im Bedienfeld „Befehle“ auswählen.

## Filter auf einen Datenblock anwenden

Um einen Filter auf den gesamten Datenblock anzuwenden, doppelklicken Sie auf einen Filter oder ziehen Sie Filter aus der Komponentenliste in den Bereich „Filter“ der Tabelle.

## Filter auf einzelne Metriken anwenden

Um Filter auf einzelne Metriken anzuwenden, ziehen Sie einen Filter auf eine Metrik in der Tabelle. Sie können auch auf das Symbol **...** rechts neben einer Metrik im Tabellenbereich klicken und dann die **Filtermetrik** auswählen. Um angewendete Filter anzuzeigen, bewegen Sie den Mauszeiger über eine Metrik im Tabellenbereich oder wählen Sie sie aus. Metriken mit angewendeten Filtern zeigen ein Filtersymbol an.

![Registerkarte „Filter“ mit Metriken.](./assets/filter_by.png)

## Schnellbearbeitungs-Filter

Sie können im Bereich „Schnellbearbeitung“ Filter für vorhandene Datenblöcke hinzufügen, entfernen oder ersetzen.

Wenn Sie einen Zellenbereich im Arbeitsblatt auswählen, wird der Link **Filter** im Bereich „Schnellbearbeitung“ eine zusammenfassende Liste der Filter anzeigen, die von den in dieser Auswahl enthaltenen Datenblöcken verwendet werden.

So bearbeiten Sie Filter über das Bedienfeld „Schnellbearbeitung“

1. Wählen Sie einen Zellenbereich aus einem oder mehreren Datenblöcken aus.

   ![Bedienfeld „Schnellbearbeitung“ mit Filteroptionen für Datenansichten, Datumsbereich und Filter.](./assets/select_multiple_dbs.png)

1. Klicken Sie auf den Link „Filter“, um das Bedienfeld „Schnellbearbeitung – Filter“ zu öffnen.

   ![das Bedienfeld „Filter“ mit dem Feld „Filter hinzufügen“ und den Listen „Angewendete Filter“.](./assets/quick_edit_filters.png)

### Hinzufügen oder Entfernen eines Filters

Mithilfe der Optionen „Hinzufügen“/„Entfernen“ können Sie Filter hinzufügen oder entfernen.

1. Wählen Sie die Registerkarte **Hinzufügen/Entfernen** im Bedienfeld „Schnellbearbeitungsfilter“ aus.

   Alle auf die ausgewählten Datenblöcke angewendeten Filter werden im Bedienfeld „Schnellbearbeitungsfilter“ aufgeführt. Filter, die auf alle Datenblöcke in der Auswahl angewendet werden, werden unter der Überschrift **Auf alle ausgewählten Datenblöcke angewendet** gelistet. Filter, die auf einige, aber nicht alle Datenblöcke angewendet werden, werden unter der Überschrift **Auf einen oder mehrere ausgewählte Datenblöcke angewendet** gelistet.

   Wenn in den ausgewählten Datenblöcken mehrere Filter vorhanden sind, können Sie mithilfe des Suchfelds **Filter hinzufügen** nach konkreten Filtern suchen.

   ![Das Feld Filter hinzufügen.](./assets/add_filter.png)

1. Fügen Sie Filter hinzu, indem Sie Filter aus dem Dropdown-Menü **Filter hinzufügen** auswählen.

   Die Liste durchsuchbarer Filter enthält alle Filter, die für die Datenansichten, die in einem oder mehreren der ausgewählten Datenblöcke vorhanden sind, zugänglich sind, sowie alle Filter, die in der Organisation global verfügbar sind.

   Durch Hinzufügen eines Filters wird der Filter auf alle Datenblöcke in der Auswahl angewendet.

1. Um Filter zu entfernen, klicken Sie auf das Löschsymbol **x** rechts neben den Filtern in der Liste **Angewendete Filter**.

1. Klicken Sie auf **Anwenden**, um Änderungen zu speichern und zum Hub-Bedienfeld zurückzukehren.

   Report Builder zeigt eine Meldung zur Bestätigung der angewendeten Filteränderungen an.

### Filter ersetzen

Sie können einen vorhandenen Filter durch einen anderen Filter ersetzen, um zu ändern, wie die Daten gefiltert werden.

1. Wählen Sie die Registerkarte **Ersetzen** im Bedienfeld „Schnellbearbeitungsfilter“.

   ![Wählen Sie die Registerkarte Ersetzen aus.](./assets/replace_filter.png)

1. Suchen Sie mithilfe des Suchfelds **Suchliste** nach bestimmten Filtern.

1. Wählen Sie einen oder mehrere Filter aus, die Sie ersetzen möchten.

1. Suchen Sie im Feld „Ersetzen durch“ nach einem oder mehreren Filtern.

   Wenn Sie einen Filter auswählen, wird dieser der Liste **Ersetzen durch**... hinzugefügt.

   ![Die Registerkarte Ersetzen , auf der der Datenblock Personen in der App ausgewählt ist, und die Liste Ersetzen durch wurde aktualisiert, sodass „Personen in der App überarbeitet“ angezeigt wird.](./assets/replace_screen_new.png)

1. Klicken Sie auf **Anwenden**.

   Report Builder aktualisiert die Filterliste entsprechend der Ersetzung.

### Definieren von Datenblockfiltern aus Zellen

Datenblöcke können auf Filter aus einer Zelle verweisen. Mehrere Datenblöcke können dieselbe Zelle für Filter referenzieren, sodass Sie Filter für mehrere Datenblöcke gleichzeitig einfach umschalten können.

So wenden Sie Filter aus einer Zelle an

1. Navigieren Sie entweder beim Erstellen oder Bearbeiten von Datenblöcken zu Schritt 2. Siehe [Erstellen eines Datenblocks](./create-a-data-block.md).
1. Klicken Sie auf **Filter**, um Filter zu definieren.
1. Klicken Sie **Filter aus Zelle erstellen**.

   ![Filter aus Zellensymbol erstellen.](./assets/create-filter-from-cell.png)

1. Wählen Sie die Zelle aus, aus der die Datenblöcke auf einen Filter verweisen sollen.

1. Fügen Sie die Filterauswahl hinzu, die Sie der Zelle hinzufügen möchten, indem Sie entweder auf den Filter doppelklicken oder ihn per Drag-and-Drop in den Abschnitt Einbezogene Filter ziehen.

   Hinweis: Für die jeweilige Zelle kann jeweils nur eine Auswahl ausgewählt werden.

   ![Das Fenster Filter aus Zelle hinzufügen , das die eingeschlossenen Filter anzeigt.](./assets/select-filters.png)

1. Klicken Sie auf **Anwenden**, um die Referenzzelle zu erstellen.

1. Fügen **auf der Registerkarte** den neu erstellten Referenzzellenfilter zu Ihrem Datenblock hinzu.

   ![Registerkarte „Filter“ mit Sheet1!J1(All Data)-Filter, der zur Tabelle hinzugefügt wurde.](./assets/reference-cell-filter.png)

1. Klicken Sie auf **Fertig stellen**.

   Jetzt kann diese Zelle von anderen Datenblöcken in ihren Filtern referenziert werden. Um die Referenzzelle als Filter auf andere Datenblöcke anzuwenden, fügen Sie einfach den Zellverweis auf der Registerkarte Filter zu ihren Filtern hinzu.

#### Verwenden der Referenzzelle zum Ändern von Datenblockfiltern

1. Wählen Sie die Referenzzelle im Arbeitsblatt aus.

1. Klicken Sie auf den Link unter **Filter aus Zelle** im Menü „Schnellbearbeitung“.

   ![Filter aus Zellenlink zeigen Blatt1!J1 (Alle Daten)](./assets/filters-from-cell-link.png)

1. Wählen Sie Ihren Filter aus dem Dropdown-Menü aus.

   ![Dropdown-Menü „Filter“](./assets/filter-drop-down.png)

1. Klicken Sie auf **Anwenden**.
