---
title: Bedienfeld „Zielgruppendurchschnitt pro Minute“
description: Verwendung und Interpretation des Audience-Bedienfelds "Durchschnittliche Minute"in Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: c55b5534-a9a6-47f1-8b43-c8c0b8686c53
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '1796'
ht-degree: 17%

---

# Zielgruppenbereich mit mittlerer Medienmindebene {#media-average-minute-audience-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaminuteaverageaudience_button"
>title="Durchschnittliche Medienminuten-Audience"
>abstract="Erstellen Sie ein Bedienfeld, um die durchschnittliche Minutenzielgruppe für bestimmte Inhalte oder über einen bestimmten Zeitraum zu analysieren."


<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaaverageminuteaudience_panel"
>title="Durchschnittliche Medienminuten-Audience"
>abstract="Zeigt die Leistung bestimmter Medieninhalte oder über einen benutzerdefinierten Zeitraum an.<br/><br/>**Allgemeine Parameter **<br/>**Berechnete Metrik für**: Wählen Sie die für den Bereich zu verwendende Metrik aus. Wählen Sie **Spezifischer Inhalt** aus, um die durchschnittliche Minutenzielgruppe für bestimmte Inhalte oder Ereignisse basierend auf der Inhaltsdauer zu analysieren. **Wählen Sie Benutzerdefinierter Zeitraum aus**, um zu analysieren, wie sich die durchschnittliche Minutenzielgruppe über einen benutzerdefinierten ausgewählten Zeitraum ändert.<br/>**Berichtsdimension**: Wählen Sie diese Option aus, um einen Bericht nach der Dimension **Videoname** der Dimension **Inhalts-ID** zu erstellen. Nur verfügbar, wenn Sie Spezifischen Inhalt als Metrik ausgewählt haben.<br/>**Granularität**: Wählen Sie die Granularität für die Berichterstellung aus. Nur verfügbar, wenn Sie als Metrik benutzerdefinierten Zeitraum ausgewählt haben.<br/>**Inhalt filtern nach (optional)**: Wählen Sie eine bestimmte Sendung, Staffel, Folge oder eine benutzerdefinierte Dimension aus, um den Inhalt zu filtern.<br/><br/>**Erweiterte Einstellungen **<br/>**Tabelleneinstellungen**: Wählen Sie aus, ob Berechnungswerte in der Tabelle angezeigt werden sollen.<br/>**Besuchszeitmetrik**: Wählen Sie aus, welche Besuchszeitmetrik Sie für die spezifische Inhaltsberechnung verwenden möchten. Nur verfügbar, wenn Sie Spezifischen Inhalt als Metrik ausgewählt haben."
>additional-url="https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/average-minute-audience-panel#specific-content" text="Bestimmter Inhalt"
>additional-url="https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/average-minute-audience-panel#custom-time-period" text="Benutzerdefinierter Zeitraum"

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>Das Bedienfeld **[!UICONTROL Durchschnittliche Medienminuten-Audience-Zielgruppe]** ist nur für Kunden verfügbar, die das Streaming-Mediensammlungs-Add-on für Customer Journey Analytics erworben haben.
>
>Weitere Informationen erhalten Sie von Ihrem Adobe Sales-Support-Mitarbeiter oder Adobe-Account-Team.
>

In Analysis Workspace kann die Zielgruppe mit der durchschnittlichen Minute Informationen zu

* die mit der Anzeige eines bestimmten Medien-Streams verbrachte Zeit dividiert durch die Dauer des Inhalts oder
* die Zeit, die mit der Anzeige während eines benutzerdefinierten Zeitraums mit der ausgewählten Granularität verbracht wurde.

Mit dem Zielgruppenbereich für die durchschnittliche Minute in Medien können Sie den durchschnittlichen Verbrauch Ihrer Inhalte durch den Vergleich von Programmen beliebiger Länge oder Genres verstehen. Beispielsweise können Sie den durchschnittlichen Verbrauch beim Vergleich einer 30-minütigen Website mit einer 3-stündigen Sportveranstaltung nachvollziehen.

Darüber hinaus können Sie das Mediendurchschnitts-Minute-Zielgruppenfeld verwenden, um diese digitale durchschnittliche Minute-Zielgruppe mit linearen TV-Durchschnittsminuten-Metriken zu vergleichen oder anzuhängen.

Der Bereich Zielgruppe für durchschnittliche Medienminuten bietet im Vergleich zur Metrik Zielgruppendurchschnitt pro Minute die folgenden Vorteile:

* Unterstützt benutzerdefinierte Zeiträume

* Ermöglicht die Aktualisierung der Dauer-Classification nach Verarbeitung der Ansichten (wenn die Dauer-Classification nicht vorhanden war oder korrigiert werden muss)

  Wenn Sie diese Aktualisierung bei Verwendung der Metrik vornehmen, ist die Dauer-Classification nicht vorhanden (sofern die Classification nicht vorhanden war). Oder die Dauer-Classification ist veraltet (wenn die Classification vorhanden, aber nicht korrekt war).

## Verwenden Sie stattdessen 

So verwenden Sie ein Bedienfeld mit der durchschnittlichen Medienminuten-Audience ]**:**[!UICONTROL 

1. Erstellen Sie ein Bedienfeld mit der durchschnittlichen Medienminuten-Audience ]**.**[!UICONTROL  Informationen zum Erstellen eines Bedienfelds finden Sie unter [Erstellen eines Bedienfelds](panels.md#create-a-panel).

1. Stellen Sie sicher, dass Sie eine Datenansicht für das Bedienfeld auswählen, für das im Add-on für Streaming-Mediensammlung Komponenten konfiguriert sind.


1. Geben Sie die [Eingabe](#panel-input) für das Bedienfeld an.

1. Beobachten Sie die [Ausgabe](#panel-output) für das Bedienfeld.

### Bedienfeldeingabe

Verwenden Sie die in diesem Abschnitt beschriebenen Eingabeeinstellungen, um das Audience-Bedienfeld für die durchschnittliche Minute der Medien zu konfigurieren.

1. Konfigurieren Sie die folgenden Eingabeeinstellungen:

   | Einstellung | Beschreibung |
   |---------|------------|
   | **Datumsbereich des Bedienfelds** | Der Datumsbereich des Bedienfelds ist standardmäßig [!UICONTROL **Dieser Monat**]. Sie können sie bearbeiten, um einen oder mehrere Monate gleichzeitig anzuzeigen. <br></br> Diese Visualisierung ist auf 1.440 Datenzeilen beschränkt (z. B. 24 Stunden bei einer Granularität auf Minutenebene). Wenn eine Kombination aus Datumsbereich und Granularität mehr als 1.440 Zeilen zur Folge hat, wird die Granularität automatisch aktualisiert, um den vollständigen Datumsbereich anzuzeigen. |
   | [!UICONTROL **Segment hier (oder einer anderen Komponente) ablegen**] | Wie andere Bedienfelder filtert diese Einstellung Ihre Auswahl anhand von Segmenten, die Sie erstellt haben. Diese Einstellung bietet eine hervorragende Möglichkeit, bestimmte Plattformen, Live-Streams oder andere gängige Mediensegmente anzuzeigen. |
   | [!UICONTROL **Berechnete Metrik für**] | Wählen Sie aus, ob die durchschnittliche Minutenzielgruppe für [**[!UICONTROL spezifischen Inhalt]**](#specific-content) angezeigt werden soll. Oder wenn Sie die durchschnittliche Minutenzielgruppe für einen [**[!UICONTROL benutzerdefinierten Zeitraum]**](#custom-time-period) sehen möchten.<br/><br/>Wählen Sie [!UICONTROL **Benutzerdefinierter Zeitraum**] aus: <ul><li>Wenn die Dauer nicht verfügbar ist, oder </li><li>wenn Sie die durchschnittliche Minutenzielgruppe für eine Zeitreihe mit mehreren Inhaltselementen anzeigen möchten, oder</li><li>für Inhalte ohne bestimmte Dauer (z. B. während eines Live-Streams oder -Ereignisses)</li></ul></li></li></ul> <p>Diese Einstellung ändert den Workflow und die Berichtsausgabe.</p> |

1. Fahren Sie mit [spezifischem Inhalt](#specific-content) oder [benutzerdefinierter Zeitraum](#custom-time-period) fort, je nachdem, welche Option Sie in der Dropdownliste [!UICONTROL **Metrik berechnen für**] ausgewählt haben.

#### Bestimmter Inhalt

1. Wenn Sie [!UICONTROL **Spezifischer Inhalt**] im Dropdown-Menü [!UICONTROL **Metrik für**] berechnen ausgewählt haben, wenn [Bedienfeldeingaben konfigurieren](#panel-inputs), geben Sie die folgenden Konfigurationsoptionen an:

   | Einstellung | Beschreibung |
   |---------|------------|
   | [!UICONTROL **Berichtsdimension**] | Wenn Sie bestimmte Inhalte auswählen, können Sie die Berichtsausgabe auswählen, um entweder die Felder für Videoname oder Inhalts-ID zu verwenden und den Inhalt und die zugehörige durchschnittliche Minutenzielgruppe anzuzeigen. |
   | [!UICONTROL **Inhalt filtern nach (optional)**] | Wählen Sie aus, wie der spezifische Inhalt gefiltert werden soll, je nach gewünschter Ansicht oder Struktur der Daten. <ul>[!UICONTROL **Anzeigen, Staffel, Folge**]: Zeigt Ihre verfügbaren Sendungen in der Dropdown-Liste an, die Sie mithilfe einer Suche filtern können (oder durch Ziehen und Ablegen des Anzeigennamens aus der linken Spalte). Sie können Ihre Auswahl hier beenden, um alle Staffeln Ihrer Sendung zu sehen, oder Sie können nach einzelnen Staffeln und dann nach einzelnen Folgen filtern. Diese Einstellung zeigt die Daten für diese Sendungen, Staffeln oder Folgen für den ausgewählten Zeitraum an.</li><li>[!UICONTROL **Benutzerdefinierte Dimension**]: Wenn Ihr Anzeigename unter einer benutzerdefinierten Dimension liegt, können Sie ihn entweder durch Suchen in der Dropdown-Liste &quot;Dimension&quot;(optional) oder durch Verwenden der linken Spaltensuche finden. Das Dimensionselement wird basierend auf dieser Auswahl automatisch ausgefüllt und als Folge behandelt.</li><li>[!UICONTROL **Keine**]: Zeigt alle Videonamen an, die durchschnittliche Minutenzielgruppendaten für die ausgewählte Auswahl enthalten. (Diese Option ist standardmäßig aktiviert.)</li></ul> |

1. Fahren Sie mit den erweiterten Einstellungen für [Spezifischer Inhalt](#specific-content-advanced-settings) fort, um erweiterte Einstellungen zu konfigurieren.

#### Erweiterte Einstellungen für spezifischen Inhalt

1. Wenn [!UICONTROL **Spezifischer Inhalt**] im Dropdown-Menü [!UICONTROL **Metrik für**] berechnen ausgewählt ist, wählen Sie [!UICONTROL **Erweiterte Einstellungen anzeigen**] und geben Sie dann die folgenden Konfigurationsoptionen an:

   | Optionen | Beschreibung |
   |---------|------------|
   | **[!UICONTROL Tabelleneinstellungen]** | Die Standardoption **[!UICONTROL Berechnungswerte in Tabelle anzeigen]** zeigt den Zähler und Nenner der durchschnittlichen Minutenzielgruppe als die vorangehenden Spalten in der Tabelle an. Wenn Sie diese Option deaktivieren, werden diese beiden Spalten entfernt. Die durchschnittliche Minute-Zielgruppenspalte bleibt in der Tabelle neben dem Videonamen oder der Inhalts-ID. |
   | **[!UICONTROL Besuchszeitmetrik]** | Sie können die Standardoption **[!UICONTROL Besuchszeit für Inhalt]** wählen, die nur die Inhaltszeit enthält. Oder Sie können **[!UICONTROL Besuchszeit für Medien]** verwenden, wobei Inhalt und Anzeigenzeit zusammen als Zählerberechnung für die Zielgruppe mit der durchschnittlichen Minute verwendet werden. |

1. Wählen Sie [!UICONTROL **Erstellen**] aus, um die Erstellung des Audience-Bereichs für die durchschnittliche Minute der Medien abzuschließen.

1. Fahren Sie mit der [Bedienfeldausgabe](#panel-output) fort, um Informationen zur Verwendung des Zielgruppenbereichs &quot;Durchschnittliche Medienminuten&quot;zu erhalten.

#### Benutzerdefinierter Zeitraum

1. Wenn Sie im Dropdownmenü [!UICONTROL **Metrik berechnen für**] bei der Konfiguration von Bereichseingaben [ den benutzerdefinierten Zeitraum **]ausgewählt haben, geben Sie die folgenden Konfigurationsoptionen an:[!UICONTROL **](#panel-inputs)

   | Optionen | Beschreibung |
   |---------|------------|
   | **[!UICONTROL Granularität]** | Die Standardgranularität lautet [!UICONTROL **5-Minute**], Sie können jedoch eine der Granularitäten auswählen, die als Nenner für die Zeitreihe innerhalb des ausgewählten Zeitraums verwendet werden. Wenn Sie beispielsweise 12:00 Uhr bis 23:30 Uhr mit einer Granularität von 5 Minuten auswählen, werden die durchschnittliche Minutenzielgruppe über die gesamte halbe Stunde sowie sechs Zeilen mit der durchschnittlichen Minutenzielgruppe für jeden 5-minütigen Zeitraum zurückgegeben. Diese Zeilen werden als Datenpunkte für das Zeitreihendiagramm verwendet. |
   | [!UICONTROL **Inhalt filtern nach (optional)**] | Wählen Sie aus, wie der spezifische Inhalt gefiltert werden soll, je nach gewünschter Ansicht oder Struktur der Daten. <ul>[!UICONTROL **Anzeigen, Staffel, Folge**]: Zeigt Ihre verfügbaren Sendungen in der Dropdown-Liste an, die Sie mithilfe einer Suche filtern können (oder durch Ziehen und Ablegen des Anzeigennamens aus der linken Spalte). Sie können Ihre Auswahl hier beenden, um alle Staffeln Ihrer Sendung zu sehen, oder Sie können nach einzelnen Staffeln und dann nach einzelnen Folgen filtern. Diese Einstellung zeigt die Daten für diese Sendungen, Staffeln oder Folgen für den ausgewählten Zeitraum an.</li><li>[!UICONTROL **Benutzerdefinierte Dimension**]: Wenn Ihr Anzeigename unter einer benutzerdefinierten Dimension liegt, können Sie ihn entweder durch Suchen in der Dropdown-Liste &quot;Dimension&quot;(optional) oder durch Verwenden der linken Spaltensuche finden. Das Dimensionselement wird basierend auf dieser Auswahl automatisch ausgefüllt und als Folge behandelt.</li><li>[!UICONTROL **Keine**]: Zeigt alle Videonamen an, die durchschnittliche Minutenzielgruppendaten für die ausgewählte Auswahl enthalten. (Diese Option ist standardmäßig aktiviert.)</li></ul> |

1. Fahren Sie mit den erweiterten Einstellungen für [Benutzerdefinierte Zeiträume](#custom-time-period-advanced-settings) fort, um erweiterte Einstellungen zu konfigurieren.

#### Erweiterte Einstellungen für benutzerdefinierte Zeiträume

1. Wählen Sie bei ausgewähltem [!UICONTROL **benutzerdefinierten Zeitraum**] im Dropdown-Menü [!UICONTROL **Metrik für**] berechnen die Option [!UICONTROL **Erweiterte Einstellungen anzeigen**] und geben Sie dann die folgende Konfigurationsoption an:

   | Option | Beschreibung |
   |---------|------------|
   | **[!UICONTROL Tabelleneinstellungen]** | Die Standardeinstellung zeigt die Berechnungswerte in der Tabelle an, die den Zähler und Nenner des Zielgruppendurchschnitts pro Minute als die vorangehenden Spalten in der Tabelle anzeigt. Wenn Sie diese Option deaktivieren, werden die beiden Spalten entfernt, sodass neben dem Zeitraum nur der Zielgruppendurchschnitt pro Minute verbleibt. |

1. Wählen Sie [!UICONTROL **Erstellen**] aus, um die Erstellung des Audience-Bereichs für die durchschnittliche Minute der Medien abzuschließen.

1. Fahren Sie mit der [Bedienfeldausgabe](#panel-output) fort, um Informationen zur Verwendung des Zielgruppenbereichs &quot;Durchschnittliche Medienminuten&quot;zu erhalten.

### Bedienfeldausgabe

Die Bedienfeldausgabe hängt davon ab, ob Sie im Dropdown-Menü [!UICONTROL **Metrik berechnen für**] [!UICONTROL **Spezifischer Inhalt**] oder [!UICONTROL **Benutzerdefinierter Zeitraum**] ausgewählt haben, wenn [Bedienfeldeingaben konfigurieren](#panel-inputs).

#### Bestimmter Inhalt

Das Zielgruppen-Bedienfeld für die durchschnittliche Medienminütigkeit gibt Folgendes zurück:

* Gesamtwert des Zielgruppendurchschnitts pro Minute für Ihre gesamte Auswahl
* In einer Tabelle angezeigte Filter und durchschnittliche Minutenzielgruppe für einzelne Videos
* Mit dem Inhalt verbrachte Zeit und Videolänge (Dauer), wenn diese erweiterte Einstellung ausgewählt wurde

Um das Bedienfeld jederzeit zu bearbeiten und neu zu erstellen, wählen Sie oben rechts ![Bearbeiten](/help/assets/icons/Edit.svg) aus.

![Standardansicht](assets/specific-content-panel-output.png)

#### Spezifische Inhaltsdatenquellen

Im Zielgruppenbereich für die durchschnittliche Minute in den Medien wird nur die Metrik für die durchschnittliche Minute der Zielgruppe verwendet, um Daten zu erfassen. Aufschlüsselungen oder andere Metriken können nicht im Bereich verwendet werden.

| Metrik | Beschreibung |
|--------|-------------|
| **[!UICONTROL Durchschnittliche Minutenzielgruppe]** | Die Zeit, die mit der Ansicht Ihres Medien-Streams verbracht wurde, dividiert durch die Videolänge (Dauer), die über Classifications bereitgestellt wird. |

#### Benutzerdefinierter Zeitraum {#custom-time-period-output}

Das Zielgruppen-Bedienfeld für die durchschnittliche Medienminütigkeit gibt Folgendes zurück:

* Gesamtdurchschnittl. Minutenzielgruppe für die gesamte Auswahl

* Maximale und minimale durchschnittliche Minutenzielgruppe

* Das Liniendiagramm zeigt die durchschnittliche Minutenzielgruppe über die gesamte Auswahl.

* Eine Tabelle mit den Filtern und der durchschnittlichen Minutenzielgruppe für die Granularitäten sowie der Besuchszeit für den Inhalt und der Granularität für jeden Zeitraum

  Diese Tabelle wird nur angezeigt, wenn die Option unter den erweiterten Einstellungen [!UICONTROL **Berechnungswerte in Tabelle anzeigen**] ausgewählt ist.

Um das Bedienfeld jederzeit zu bearbeiten und neu zu erstellen, wählen Sie oben rechts die Option ![Bereich für durchschnittliche Medienminuten bearbeiten](/help/assets/icons/Edit.svg) aus.


#### Datenquelle für benutzerdefinierte Zeiträume

Im Zielgruppenbereich für die durchschnittliche Minute in den Medien wird nur die Metrik für die durchschnittliche Minute der Zielgruppe verwendet, um Daten zu erfassen. Aufschlüsselungen oder andere Metriken können nicht im Bereich verwendet werden.

| Metrik | Beschreibung |
|---|---|
| **[!UICONTROL Zielgruppendurchschnitt pro Minute]** | Die mit der Ansicht Ihres Medien-Streams verbrachte Zeit dividiert durch die Gesamtauswahl oder die ausgewählte Granularität in Minuten. |


>[!MORELIKETHIS]
>
> [Erstellen eines Bedienfelds](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
> [Bedienfeld &quot;Gleichzeitige Medienbetrachter&quot;](media-concurrent-viewers.md)
> [Bedienfeld &quot;Besuchszeit für Medienwiedergabe&quot;](media-playback-time-spent.md)
>