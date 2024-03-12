---
title: Bedienfeld „Zielgruppendurchschnitt pro Minute“
description: Verwenden und Interpretieren des Bedienfelds „Medien-Zielgruppendurchschnitt pro Minute“ in Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: be8371ee-8bc6-4a99-8527-dd94eab8a7f9
source-git-commit: a6dd3495b51edcb823431ccb87b283665ccd765d
workflow-type: tm+mt
source-wordcount: '1656'
ht-degree: 31%

---


# Zielgruppenbereich mit mittlerer Medienmindebene

>[!NOTE]
>
>Das Zielgruppenfeld Durchschnittliche Medienminuten ist nur für Kunden verfügbar, die das Media Analytics-Add-on für Customer Journey Analytics erworben haben.
>
>Wenden Sie sich an Ihren Adobe-Vertriebsmitarbeiter oder Adobe-Account-Team, um Media Analytics zu erwerben.

In Analysis Workspace bezeichnet der Zielgruppendurchschnitt pro Minute die Zeit, die mit der Ansicht Ihres Medien-Streams verbracht wurde, geteilt durch die Inhaltsdauer oder die Gesamtauswahl des Zeitraums mit der ausgewählten Granularität.

Mit dem Zielgruppenbereich Durchschnittliche Medienminuten können Sie die durchschnittliche Nutzung Ihrer Inhalte besser verstehen, indem Sie Programme beliebiger Länge oder Genres vergleichen. Beispielsweise können Sie den durchschnittlichen Verbrauch beim Vergleich einer 30-minütigen Website mit einer 3-stündigen Sportveranstaltung nachvollziehen.

Darüber hinaus können Sie das Mediendurchschnitts-Minute-Zielgruppenfeld verwenden, um diese digitale durchschnittliche Minute-Zielgruppe mit linearen TV-Durchschnittsminuten-Metriken zu vergleichen oder anzuhängen.

Der Bereich Zielgruppe für durchschnittliche Medienminuten bietet im Vergleich zur Metrik Zielgruppendurchschnitt pro Minute die folgenden Vorteile:

* Unterstützt benutzerdefinierte Zeiträume

* Ermöglicht die Aktualisierung der Dauer-Classification nach Verarbeitung der Ansichten (falls diese nicht vorhanden waren oder korrigiert werden müssen)

  Wenn Sie dies bei Verwendung der Metrik getan haben, ist die Metrik entweder nicht vorhanden (wenn die Classification nicht vorhanden war) oder sie ist veraltet (wenn die Classification vorhanden, aber falsch war).

## Auf das Zielgruppenfeld &quot;Durchschnittliche Medienminuten&quot;zugreifen

1. Wechseln Sie in Analysis Workspace zu einer Report Suite, für die Media Analytics-Komponenten aktiviert sind.

1. Wählen Sie im linken Navigationsbereich die **Bedienfelder** Symbol.

   ![Symbol &quot;Bedienfelder&quot;im linken Navigationsbereich](assets/panels-icon.png)

1. Ziehen Sie die [!UICONTROL **Durchschnittliche Medienminuten-Audience**] auf die Arbeitsfläche in Analysis Workspace.

1. Um das Bedienfeld zu konfigurieren, fahren Sie mit [Bedienfeldeingaben](#panel-inputs).

## Bedienfeldeingaben {#Input}

Verwenden Sie die in diesem Abschnitt beschriebenen Eingabeeinstellungen, um das Audience-Bedienfeld für die durchschnittliche Minute der Medien zu konfigurieren.

1. Beginnen Sie mit der Erstellung eines Audience-Bedienfelds mit der durchschnittlichen Medienminuten, wie beschrieben in [Auf das Zielgruppenfeld &quot;Durchschnittliche Medienminuten&quot;zugreifen](#access-the-media-average-minute-audience-panel).

1. Konfigurieren Sie die folgenden Eingabeeinstellungen:

   | Einstellung | Beschreibung |
   |---------|------------|
   | **Datumsbereich des Bedienfelds** | Der Datumsbereich des Bedienfelds ist standardmäßig [!UICONTROL **Diesen Monat**]. Sie können sie bearbeiten, um einen oder mehrere Monate gleichzeitig anzuzeigen. <br></br> Diese Visualisierung ist auf 1.440 Datenzeilen beschränkt (z. B. 24 Stunden bei einer Granularität auf Minutenebene). Wenn eine Kombination aus Datumsbereich und Granularität mehr als 1.440 Zeilen zur Folge hat, wird die Granularität automatisch aktualisiert, um den vollständigen Datumsbereich anzuzeigen. |
   | [!UICONTROL **Segment hier (oder einer anderen Komponente) ablegen**] | Wie andere Bedienfelder filtert diese Einstellung Ihre Auswahl anhand von Segmenten, die Sie erstellt haben. Dies ist eine hervorragende Möglichkeit, bestimmte Plattformen, Live-Streams oder andere gängige Mediensegmente anzusehen. |
   | [!UICONTROL **Berechnete Metrik für**] | Wählen Sie aus, ob Sie die durchschnittliche Minutenzielgruppe für einen bestimmten Inhalt anzeigen möchten oder ob Sie die durchschnittliche Minutenzielgruppe für einen benutzerdefinierten Zeitraum anzeigen möchten:<ul><li>**Spezifischer Inhalt:** Dies ist nur verfügbar, wenn die Dauer mithilfe von Classifications aktualisiert wurde. Wenn die Dauer nicht verfügbar ist oder Sie die durchschnittliche Minutenzielgruppe für eine Zeitreihe mit mehreren Inhalten oder Inhalten ohne bestimmte Dauer anzeigen möchten (z. B. während eines Live-Streams oder -Ereignisses), sollten Sie Folgendes auswählen: [!UICONTROL **Benutzerdefinierter Zeitraum**]. (Die Dauer kann mithilfe von Classifications entweder vor oder nach der Verarbeitungszeit festgelegt werden.)</li><li>**Benutzerdefinierter Zeitraum:** Dies ist unabhängig davon verfügbar, ob die Dauer mit Classifications verfügbar gemacht wird.</li></ul> <p>Diese Einstellung ändert den Workflow und die Berichtsausgabe.</p> |

1. Fahren Sie mit [Spezifischer Inhalt](#specific-content) oder [Benutzerdefinierter Zeitraum](#custom-time-period), abhängig von der in der Variablen [!UICONTROL **Berechnete Metrik für**] Dropdown-Menü.

### Bestimmter Inhalt

1. Wenn Sie [!UICONTROL **Spezifischer Inhalt**] im [!UICONTROL **Berechnete Metrik für**] Dropdown-Menü beim [Konfigurieren von Bedienfeldeingaben](#panel-inputs)Legen Sie die folgenden Konfigurationsoptionen fest:

   | Einstellung | Beschreibung |
   |---------|------------|
   | [!UICONTROL **Berichtsdimension**] | Wenn Sie einen bestimmten Inhalt auswählen, können Sie für die Berichtsausgabe entweder das Feld für den Videonamen oder die Inhalts-ID verwenden, um den Inhalt und den zugehörigen Zielgruppendurchschnitt pro Minute für den ausgewählten Zeitraum anzuzeigen. |
   | [!UICONTROL **Filtern von Inhalten nach (optional)**] | Wählen Sie aus, wie der spezifische Inhalt gefiltert werden soll, je nach gewünschter Ansicht oder Struktur der Daten. <ul>[!UICONTROL **Einblenden, Staffel, Folge**]: Zeigt Ihre verfügbaren Anzeigen in der Dropdown-Liste an, die Sie mithilfe einer Suche filtern können (oder durch Ziehen und Ablegen des Anzeigennamens aus der linken Spalte). Sie können Ihre Auswahl hier beenden, um alle Staffeln Ihrer Sendung zu sehen, oder Sie können nach einzelnen Staffeln und dann nach einzelnen Folgen filtern. Diese Einstellung zeigt die Daten für diese Sendungen, Staffeln oder Folgen für den ausgewählten Zeitraum an.</li><li>[!UICONTROL **Benutzerdefinierte Dimension**]: Wenn Ihr Anzeigename unter einer benutzerdefinierten Dimension liegt, können Sie ihn entweder durch Suchen in der Dropdown-Liste &quot;Dimension&quot;(optional) oder durch Verwenden der linken Spaltensuche finden. Das Dimensionselement wird basierend auf dieser Auswahl automatisch ausgefüllt und als Folge behandelt.</li><li>[!UICONTROL **Keines**]: Zeigt alle Videonamen an, die für die ausgewählte Auswahl durchschnittliche Minutenzielgruppendaten aufweisen. (Diese Optionen sind standardmäßig ausgewählt.)</li></ul> |

1. Fahren Sie mit [Erweiterte Einstellungen für spezifischen Inhalt](#specific-content-advanced-settings) , um die erweiterten Einstellungen zu konfigurieren.

### Erweiterte Einstellungen für spezifischen Inhalt

1. Mit [!UICONTROL **Spezifischer Inhalt**] in der [!UICONTROL **Berechnete Metrik für**] Dropdown-Menü auswählen [!UICONTROL **Erweiterte Einstellungen anzeigen**] und geben Sie dann die folgenden Konfigurationsoptionen an:

   | Einstellung | Beschreibung |
   |---------|------------|
   | Tabelleneinstellungen | Die Standardeinstellung zeigt die Berechnungswerte in der Tabelle an, wobei Zähler und Nenner des Zielgruppendurchschnitts pro Minute als die vorangehenden Spalten in der Tabelle angezeigt werden. Wenn Sie diese Option deaktivieren, werden diese beiden Spalten entfernt, sodass nur der Zielgruppendurchschnitt pro Minute neben dem Videonamen oder der Inhalts-ID verbleibt. |
   | Besuchszeit-Kennzahl | Sie können die standardmäßige mit dem Inhalt verbrachte Zeit auswählen, die nur die Inhaltsdauer enthält, oder die mit der Medienwiedergabe verbrachte Zeit verwenden, die die mit dem Inhalt und den Werbeanzeigen verbrachte Zeit als Zählerberechnung für den Zielgruppendurchschnitt pro Minute enthält. |

1. Auswählen [!UICONTROL **Build**] , um die Erstellung des Audience-Bedienfelds für die durchschnittliche Minute der Medien abzuschließen.

1. Fahren Sie mit [Bedienfeldausgabe](#panel-output) für Informationen zur Verwendung des Bereichs Zielgruppe mit durchschnittlich Medienminuten.

### Benutzerdefinierter Zeitraum

1. Wenn Sie [!UICONTROL **Benutzerdefinierter Zeitraum**] im [!UICONTROL **Berechnete Metrik für**] Dropdown-Menü beim [Konfigurieren von Bedienfeldeingaben](#panel-inputs)Legen Sie die folgenden Konfigurationsoptionen fest:

   | Einstellung | Beschreibung |
   |---------|------------|
   | Granularität | Die Standardgranularität lautet [!UICONTROL **5 Minuten**], Sie können jedoch eine beliebige Granularität auswählen, die als Nenner für die Zeitreihe innerhalb der Gesamtzeitauswahl, die in der Kalenderauswahl vorgenommen wird, verwendet wird. Wenn Sie beispielsweise 12:00 Uhr bis 23:30 Uhr mit einer Granularität von 5 Minuten auswählen, werden die durchschnittliche Minutenzielgruppe über die gesamte halbe Stunde sowie sechs Zeilen mit der durchschnittlichen Minutenzielgruppe für jeden 5-minütigen Zeitraum zurückgegeben. Diese Zeilen werden als Datenpunkte für das Zeitreihendiagramm verwendet. |
   | [!UICONTROL **Filtern von Inhalten nach (optional)**] | Wählen Sie aus, wie der spezifische Inhalt gefiltert werden soll, je nach gewünschter Ansicht oder Struktur der Daten. <ul>[!UICONTROL **Einblenden, Staffel, Folge**]: Zeigt Ihre verfügbaren Anzeigen in der Dropdown-Liste an, die Sie mithilfe einer Suche filtern können (oder durch Ziehen und Ablegen des Anzeigennamens aus der linken Spalte). Sie können Ihre Auswahl hier beenden, um alle Staffeln Ihrer Sendung zu sehen, oder Sie können nach einzelnen Staffeln und dann nach einzelnen Folgen filtern. Diese Einstellung zeigt die Daten für diese Sendungen, Staffeln oder Folgen für den ausgewählten Zeitraum an.</li><li>[!UICONTROL **Benutzerdefinierte Dimension**]: Wenn Ihr Anzeigename unter einer benutzerdefinierten Dimension liegt, können Sie ihn entweder durch Suchen in der Dropdown-Liste &quot;Dimension&quot;(optional) oder durch Verwenden der linken Spaltensuche finden. Das Dimensionselement wird basierend auf dieser Auswahl automatisch ausgefüllt und als Folge behandelt.</li><li>[!UICONTROL **Keines**]: Zeigt alle Videonamen an, die für die ausgewählte Auswahl durchschnittliche Minutenzielgruppendaten aufweisen. (Diese Optionen sind standardmäßig ausgewählt.)</li></ul> |

1. Fahren Sie mit [Erweiterte Einstellungen für benutzerdefinierte Zeiträume](#custom-time-period-advanced-settings) , um die erweiterten Einstellungen zu konfigurieren.

### Erweiterte Einstellungen für benutzerdefinierte Zeiträume

1. Mit [!UICONTROL **Benutzerdefinierter Zeitraum**] in der [!UICONTROL **Berechnete Metrik für**] Dropdown-Menü auswählen [!UICONTROL **Erweiterte Einstellungen anzeigen**] und geben Sie dann die folgende Konfigurationsoption an:

   | Einstellung | Beschreibung |
   |---------|------------|
   | Tabelleneinstellungen | Die Standardeinstellung zeigt die Berechnungswerte in der Tabelle an, die den Zähler und Nenner des Zielgruppendurchschnitts pro Minute als die vorangehenden Spalten in der Tabelle anzeigt. Wenn Sie diese Option deaktivieren, werden die beiden Spalten entfernt, sodass neben dem Zeitraum nur der Zielgruppendurchschnitt pro Minute verbleibt. |

1. Auswählen [!UICONTROL **Build**] , um die Erstellung des Audience-Bedienfelds für die durchschnittliche Minute der Medien abzuschließen.

1. Fahren Sie mit [Bedienfeldausgabe](#panel-output) für Informationen zur Verwendung des Bereichs Zielgruppe mit durchschnittlich Medienminuten.

## Bedienfeldausgabe

Die Bedienfeldausgabe variiert je nachdem, ob Sie ausgewählt haben [!UICONTROL **Spezifischer Inhalt**] oder [!UICONTROL **Benutzerdefinierter Zeitraum**] im [!UICONTROL **Berechnete Metrik für**] Dropdown-Menü beim [Konfigurieren von Bedienfeldeingaben](#panel-inputs).

### Bestimmter Inhalt

Das Zielgruppen-Bedienfeld für die durchschnittliche Medienminütigkeit gibt Folgendes zurück:

* Gesamtwert des Zielgruppendurchschnitts pro Minute für Ihre gesamte Auswahl
* Filter und Zielgruppendurchschnitt pro Minute für die einzelnen Videos, die in einer Tabelle angezeigt werden
* Mit dem Inhalt verbrachte Zeit und Videolänge (Dauer), wenn diese erweiterte Einstellung ausgewählt wurde

Um das Bedienfeld jederzeit zu bearbeiten und neu zu erstellen, wählen Sie oben rechts das Symbol Bearbeiten (Bleistift) aus.

![Standardansicht](assets/specific-content-panel-output.png)

### Spezifische Inhaltsdatenquellen

Im Bereich Zielgruppe für Medien mit durchschnittlicher Minute werden zur Datenerfassung nur die Metrik Zielgruppendurchschnitt pro Minute verwendet. Aufschlüsselungen oder andere Metriken können nicht im Bereich verwendet werden.

| Metrik | Beschreibung |
|--------|-------------|
| Zielgruppendurchschnitt pro Minute | Die Zeit, die mit der Ansicht Ihres Medien-Streams verbracht wurde, dividiert durch die Videolänge (Dauer), die über Classifications bereitgestellt wird. |

### Benutzerdefinierter Zeitraum {#custom-time-period-output}

Das Zielgruppen-Bedienfeld für die durchschnittliche Medienminütigkeit gibt Folgendes zurück:

* Gesamtdurchschnittl. Minutenzielgruppe für die gesamte Auswahl

* Maximale und minimale durchschnittliche Minutenzielgruppe

* Das Liniendiagramm zeigt die durchschnittliche Minutenzielgruppe über die gesamte Auswahl.

* Eine Tabelle mit den Filtern und der durchschnittlichen Minutenzielgruppe für die Granularitäten sowie der Besuchszeit für den Inhalt und der Granularität für jeden Zeitraum

  Diese Tabelle wird nur angezeigt, wenn die Option unter den erweiterten Einstellungen [!UICONTROL **Berechnungswerte in Tabelle anzeigen**] ausgewählt ist.

Um das Bedienfeld jederzeit zu bearbeiten und neu zu erstellen, wählen Sie oben rechts das Symbol Bearbeiten (Bleistift) aus.

![Output von gleichzeitigen Betrachtern](assets/custom-time-period-panel-output.png)

### Datenquelle für benutzerdefinierte Zeiträume

Im Bereich Zielgruppe für Medien mit durchschnittlicher Minute werden zur Datenerfassung nur die Metrik Zielgruppendurchschnitt pro Minute verwendet. Aufschlüsselungen oder andere Metriken können nicht im Bereich verwendet werden.

| Metrik | Beschreibung |
|---|---|
| Zielgruppendurchschnitt pro Minute | Die mit der Ansicht Ihres Medien-Streams verbrachte Zeit dividiert durch die Gesamtauswahl oder die ausgewählte Granularität in Minuten. |
