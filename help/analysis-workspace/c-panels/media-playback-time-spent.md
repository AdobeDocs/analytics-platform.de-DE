---
title: Bedienfeld „Bei Medienwiedergabe verbrachte Zeit“
description: Verwendung und Interpretation des Bedienfelds Besuchszeit für die Medienwiedergabe in Analysis Workspace.
feature: Panels
exl-id: de0fdbea-71f0-445b-a1e4-c7e895f142d4
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '1128'
ht-degree: 42%

---

# Bedienfeld „Bei Medienwiedergabe verbrachte Zeit“ {#media-playback-time-spent-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaplaybacktimespent_button"
>title="Medienwiedergabedauer"
>abstract="Erstellen Sie ein Bedienfeld, um den Videokonsum im Zeitverlauf mit verschiedenen Granularitätsebenen zu analysieren und die Möglichkeit, aufzuschlüsseln und zu vergleichen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaplaybacktimespent_panel"
>title="Medienwiedergabedauer"
>abstract="Analysieren Sie den Videokonsum im Zeitverlauf, wählen Sie verschiedene Granularitäten aus, unterteilen Sie sie und vergleichen Sie sie.<br/><br/>**Granularität**: Wählen Sie einen Zeitraum aus, nach dem gleichzeitige Betrachter angezeigt werden sollen.<br/>**Bereichszusammenfassungsnummern (optional)**: Option zum Anzeigen von Zusammenfassungsnummern mit Datums- oder Uhrzeitdetails für jede Zeile. Maximal zeigt Details zur Spitzenwiedergabedauer an. Das Minimum zeigt Details für den Tief an. Die Summe zeigt Details zur Gesamtdauer der Wiedergabe an.<br/>**Aufschlüsselung nach Serie (optional)**: Schlüsseln Sie die Visualisierung nach Segmenten, Dimensionen, Dimensionselementen oder Datumsbereichen auf. Sie können bis zu 10 Zeilen gleichzeitig anzeigen. Aufschlüsselungen sind auf eine einzelne Ebene beschränkt.<br/>**Zeitformat**: Option zur Anzeige des Zeitformats für Visualisierungen in Stunden oder Minuten."

<!-- markdownlint-enable MD034 -->



>[!NOTE]
>
>Das Zielgruppen-Bedienfeld &quot;Durchschnittliche Medienminuten&quot;steht nur Kunden zur Verfügung, die das Streaming-Mediensammlungs-Add-on für Customer Journey Analytics erworben haben.
>Weitere Informationen erhalten Sie von Ihrem Adobe-Vertriebsmitarbeiter oder Adobe-Account-Team.
>

Das Bedienfeld **[!UICONTROL Besuchszeit für Medienwiedergabe]** ermöglicht die Analyse der Wiedergabe im Zeitverlauf mit Details zu Spitzenzeiten bei gleichzeitiger Wiedergabe und der Möglichkeit, Aufschlüsselungen und Vergleiche vorzunehmen.

In Analysis Workspace entspricht die Wiedergabedauer der Zeit, die mit der Anzeige Ihrer Medien-Streams zu einem bestimmten Zeitpunkt verbracht wurde. Er umfasst Pause, Puffer und Startzeit.

Kunden, die das Streaming-Mediensammlungs-Add-on erworben haben, können die Wiedergabedauer analysieren, um wertvolle Einblicke in die Qualität von Inhalten und die Interaktion mit Betrachtern zu erhalten. Und um bei der Fehlerbehebung oder Planung für Volumen oder Skalierung zu helfen.

Die Wiedergabedauer kann Ihnen dabei helfen, Folgendes zu verstehen:

* Wo Spitzenzeiten bei gleichzeitiger Nutzung auftraten.

* Wo es zu Abbrüchen kam.

+++ Sehen Sie sich ein Video an, um diese Funktion zu demonstrieren.

>[!VIDEO](https://video.tv.adobe.com/v/338699)

+++

## Verwenden Sie stattdessen 

So verwenden Sie ein Bedienfeld mit der **[!UICONTROL Besuchszeit für Medienwiedergabe]**:

1. Erstellen Sie ein Bedienfeld mit der **[!UICONTROL Besuchszeit für Medienwiedergabe]**. Informationen zum Erstellen eines Bedienfelds finden Sie unter [Erstellen eines Bedienfelds](panels.md#create-a-panel).

1. Stellen Sie sicher, dass Sie eine Datenansicht für das Bedienfeld auswählen, für das im Add-on für Streaming-Mediensammlung Komponenten konfiguriert sind.

1. Geben Sie die [Eingabe](#panel-input) für das Bedienfeld an.

1. Beobachten Sie die [Ausgabe](#panel-output) für das Bedienfeld.


### Bedienfeldeingabe

Sie können das Panel „Verbrachte Zeit bei der Medienwiedergabe“ mithilfe der folgenden Eingabeeinstellungen konfigurieren:

| Einstellung | Beschreibung |
|---|---|
| Datumsbereich der Bedienfelder | Der Datumsbereich des Panels ist standardmäßig „Heute“. Sie können ihn so verändern, dass Sie einen einzelnen Tag oder viele Monate auf einmal betrachten können.<br>Diese Visualisierung ist auf 1440 Datenzeilen beschränkt (z. B. 24 Stunden bei einer Granularität auf Minutenebene). Wenn eine Kombination aus Datumsbereich und Granularität zu mehr als 1440 Zeilen führt, wird die Granularität automatisch reduziert, um den vollständigen Datumsbereich zu erlauben. |
| Granularität | Die Standardeinstellung für die Granularität ist „Minute“.<br>Diese Visualisierung ist auf 1440 Datenzeilen beschränkt (z. B. 24 Stunden bei einer Granularität auf Minutenebene). Wenn eine Kombination aus Datumsbereich und Granularität zu mehr als 1440 Zeilen führt, wird die Granularität automatisch reduziert, um den vollständigen Datumsbereich zu erlauben. |
| Zusammenfassende Zahlen der Bedienfelder | Um Details zu Datum und Uhrzeit für die verbrachte Zeit bei der Medienwiedergabe anzuzeigen, steht eine zusammenfassende Zahl zur Verfügung. Das Maximum zeigt Details zu Spitzenzeiten von gleichzeitigen Aufrufen an. Das Minimum zeigt Details zum Tiefpunkt an. In der Summe wird die gesamte Wiedergabezeit für diese Auswahl dargestellt. Im Panel wird standardmäßig nur der maximale Wert angezeigt. Sie können dies jedoch ändern, sodass das Minimum, die Summe oder eine beliebige Kombination der drei Werte angegeben wird.<br>Wenn Sie Aufschlüsselungen verwenden, wird jeweils eine Zusammenfassungsnummer angezeigt. |
| Serienaufschlüsselung | Optional können Sie Ihre Visualisierung nach Filtern, Dimensionen, Dimensionselementen oder Datumsbereichen aufschlüsseln.<p>– Sie können bis zu 10 Zeilen auf einmal ansehen. Aufschlüsselungen sind auf eine einzelne Ebene beschränkt.</p><p>- Beim Ziehen einer Dimension werden die obersten Dimensionselemente automatisch basierend auf dem ausgewählten Datumsbereich des Bedienfelds ausgewählt.</p>– Ziehen Sie zum Vergleichen von Datumsbereichen zwei oder mehr Datumsbereiche in den Filter für die Aufschlüsselung der Serie. |
| Zeitformat | Sie können die Wiedergabedauer entweder in `Hours:Minutes:Seconds` (Standard) oder in `Minutes` anzeigen (die in Ganzzahlen angezeigt wird, bei 0,5 aufgerundet). |
| Anzeige der Datumsreihe | Wenn Sie mindestens zwei Datumsbereichsfilter als Serienaufschlüsselungen platziert haben, sehen Sie die Option zur Auswahl einer Überlagerung (Standard) oder einer sequenziellen Überlagerung. Overlay zeigt die Zeilen mit einem gemeinsamen X-Achsen-Start an, sodass sie parallel ausgeführt werden, während sequenziell die Zeilen mit ihrem jeweiligen X-Achsen-Start anzeigt. Wenn die Daten aufgerollt sind (z. B. Filter 1 um 20:44 Uhr endet und Filter 2 um 20:45 Uhr beginnt), werden die Zeilen nacheinander angezeigt. |


![Die Zeitdauer der Medienwiedergabe, die die Standardansicht verbracht hat.](assets/mpts_default_view.png)

### Bedienfeldausgabe

Das Panel „Verbrachte Zeit bei der Medienwiedergabe“ gibt ein Liniendiagramm und zusammenfassende Zahlen zurück, die Details zur maximalen Wiedergabedauer, minimalen Wiedergabedauer und/oder der Summe der Wiedergabedauer enthalten. Oben im Bedienfeld wird eine Zusammenfassungszeile angezeigt, die Sie an die ausgewählten Bedienfeldeinstellungen erinnert.

Wählen Sie jederzeit ![Zeitfenster für die Medienwiedergabe bearbeiten](/help/assets/icons/Edit.svg) aus, um das Bedienfeld zu bearbeiten und neu zu erstellen.

Wenn Sie die Aufschlüsselung nach Serie auswählen, werden eine Zeile im Liniendiagramm und eine Zusammenfassungsnummer für jede Zeile angezeigt:

![Die Ausgabe der Medienwiedergabezeit mit einem Liniendiagramm und einer Zusammenfassung.](assets/mpts_outputs1.png)

### Datenquelle

Die einzige Metrik, die in diesem Panel verwendet werden kann, ist „Wiedergabedauer“.

| Metrik | Beschreibung |
|---|---|
| Wiedergabedauer | Gesamtanzahl der während der ausgewählten Granularität angezeigten Inhalte `hours:minutes:seconds` (oder `minutes`), einschließlich Pause, Puffer und Startzeit. |

## Häufig gestellte Fragen (FAQ)

| Frage | Antwort |
|---|---|
| Wo ist die Freiformtabelle? Wie kann ich die Datenquelle anzeigen? | <p></p><p>Die Freiformtabelle ist in dieser Ansicht nicht verfügbar. Um die Datenquelle herunterzuladen, wählen Sie im Kontextmenü des Liniendiagramms die Option zum Herunterladen der CSV-Datei aus.</p> |
| <p>Warum hat sich meine Granularität verändert?</p> | <p>Diese Visualisierung ist auf 1440 Datenzeilen beschränkt (z. B. 24 Stunden bei einer Granularität auf Minutenebene). Wenn eine Kombination aus Datumsbereich und Granularität mehr als 1.440 Zeilen zur Folge hat, wird die Granularität automatisch aktualisiert, um den vollständigen Datumsbereich anzuzeigen.</p><p></p><p>Wenn Sie von einem größeren Datumsbereich in einen kleineren ändern, wird die Granularität auf das niedrigste Detail aktualisiert, das nach Änderung des Datumsbereichs zulässig ist. Um eine höhere Granularität zu sehen, bearbeiten Sie das Bedienfeld und erstellen Sie es erneut.</p> |
| <p></p><p>Wie vergleiche ich Videonamen, Filter, Inhaltstypen und mehr?</p> | <p>Um diese in einer einzigen Visualisierung zu vergleichen, ziehen Sie Filter, Dimensionen oder bestimmte Dimensionselemente in den Filter für die Serienaufschlüsselung.</p><p></p><p>Die Ansicht ist auf 10 Aufschlüsselungen beschränkt. Um mehr als 10 ansehen zu können, müssen Sie mehrere Bedienfelder verwenden.</p> |
| Wie vergleiche ich Datumsbereiche? | Um Datumsbereiche in einer einzigen Visualisierung zu vergleichen, verwenden Sie die Serienaufschlüsselungen, indem Sie zwei oder mehr Datumsbereiche in das Panel ziehen. Diese Datumsbereiche überschreiben den Datumsbereich des Bedienfelds. |
| Wie ändere ich den Visualisierungstyp? | <p></p><p>Dieses Bedienfeld ermöglicht nur die Linienvisualisierung für die Zeitreihen.</p> |
| Kann ich die Anomalieerkennung ausführen? | <p></p><p>Nein. Die Anomalieerkennung ist für dieses Panel nicht verfügbar.</p> |


>[!MORELIKETHIS]
>
>[Erstellen eines Bedienfelds](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>[Mediendurchschnittl. Minute-Audience-Bereich](average-minute-audience-panel.md)
>[Bedienfeld &quot;Gleichzeitige Medienbetrachter&quot;](media-concurrent-viewers.md)
>