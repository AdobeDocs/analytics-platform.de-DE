---
title: Bedienfeld „Zielgruppendurchschnitt pro Minute“
description: Verwendung und Interpretation des Bedienfelds „Medien-Zielgruppendurchschnitt pro Minute“ in Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: c55b5534-a9a6-47f1-8b43-c8c0b8686c53
source-git-commit: f8abf388e0cb1e2e2eb9ff69fed2c542a26dcd66
workflow-type: tm+mt
source-wordcount: '1817'
ht-degree: 29%

---

# Bedienfeld „Zielgruppendurchschnitt pro Minute“ {#media-average-minute-audience-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaminuteaverageaudience_button"
>title="Medien-Zielgruppendurchschnitt pro Minute"
>abstract="Erstellen Sie ein Panel, um den Zielgruppendurchschnitt pro Minute für bestimmte Inhalte oder über einen bestimmten Zeitraum zu analysieren."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaaverageminuteaudience_panel"
>title="Medien-Zielgruppendurchschnitt pro Minute"
>abstract="Zeigt die Leistung bestimmter Medieninhalte oder über einen benutzerdefinierten Zeitraum an.<br/><br/>**Allgemeine Parameter **<br/>**Metrik berechnen für**: Wählen Sie die für das Bedienfeld zu verwendende Metrik aus. Wählen Sie **Bestimmter Inhalt** aus, um den Zielgruppendurchschnitt pro Minute für bestimmte Inhalte oder Ereignisse basierend auf der Inhaltslänge zu analysieren. **Wählen Sie „Benutzerdefinierter Zeitraum“ aus**, um zu analysieren, wie sich der Zielgruppendurchschnitt pro Minute über einen benutzerdefinierten Zeitraum verändert.<br/>**Reporting-Dimension**: Wählen Sie diese Option aus, um einen Bericht nach der Dimension **Videoname** oder **Inhalts-ID** zu erstellen. Nur verfügbar, wenn Sie „Bestimmter Inhalt“ als Metrik ausgewählt haben.<br/>**Granularität**: Wählen Sie die Granularität für die Berichte aus. Nur verfügbar, wenn Sie „Benutzerdefinierter Zeitraum“ als Metrik ausgewählt haben.<br/>**Inhalt filtern nach (optional)**: Wählen Sie eine bestimmte Sendung, Staffel, Folge oder eine benutzerdefinierte Dimension aus, um den Inhalt zu filtern.<br/><br/>**Erweiterte Einstellungen **<br/>**Tabelleneinstellungen**: Legen Sie fest, ob Berechnungswerte in der Tabelle angezeigt werden sollen.<br/>**Besuchszeitmetrik**: Legen Sie fest, welche Besuchszeitmetrik für die Berechnung eines bestimmten Inhalts verwendet werden soll. Nur verfügbar, wenn Sie „Bestimmter Inhalt“ als Metrik ausgewählt haben."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

*In diesem Artikel wird das Bedienfeld „Medien-Zielgruppendurchschnitt pro Minute“ in ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg)**Customer Journey Analytics)**.<br/>Siehe [Bedienfeld „Medien-Zielgruppendurchschnitt pro Minute](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/average-minute-audience-panel) für die ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg)**Adobe Analytics**-Version dieses Artikels.*

>[!ENDSHADEBOX]

>[!NOTE]
>
>Das Bedienfeld **[!UICONTROL Medien-Zielgruppendurchschnitt pro Minute]** steht nur Kunden zur Verfügung, die die Streaming-Mediensammlung zum Customer Journey Analytics erworben haben.
>
>Wenden Sie sich an Ihren Adobe-Kundenbetreuer oder Ihr Adobe-Kundenbetreuerteam, um weitere Informationen zu erhalten.
>

In Analysis Workspace kann der Zielgruppendurchschnitt pro Minute Informationen zu folgenden Themen liefern

* die Zeit, die mit der Anzeige eines bestimmten Medien-Streams verbracht wurde, dividiert durch die Dauer des Inhalts, oder
* Die Zeit, die mit der Anzeige während eines benutzerdefinierten Zeitraums mit ausgewählter Granularität verbracht wurde.

Das Bedienfeld „Medien-Zielgruppendurchschnitt pro Minute“ ermöglicht es Ihnen, die durchschnittliche Nutzung Ihrer Inhalte zu verstehen, indem Sie Programme beliebiger Länge oder Genres vergleichen. Sie können beispielsweise den durchschnittlichen Verbrauch verstehen, wenn Sie eine 30-minütige Sitcom mit einem 3-stündigen Sportereignis vergleichen.

Darüber hinaus können Sie das Bedienfeld „Medien-Zielgruppendurchschnitt pro Minute“ verwenden, um diesen digitalen Zielgruppendurchschnitt pro Minute mit linearen Metriken zum TV-Durchschnitt pro Minute zu vergleichen oder anzuhängen.

Das Bedienfeld „Medien-Zielgruppendurchschnitt pro Minute“ bietet gegenüber der Metrik „Zielgruppendurchschnitt pro Minute“ die folgenden Vorteile:

* Unterstützt benutzerdefinierte Zeiträume

* Ermöglicht die Aktualisierung der Klassifizierungsdauer, nachdem Ansichten verarbeitet wurden (wenn die Klassifizierung der Dauer nicht vorhanden war oder korrigiert werden muss)

  Wenn Sie diese Aktualisierung bei Verwendung der Metrik durchführen, ist die Klassifizierung der Dauer nicht vorhanden (wenn die Klassifizierung nicht vorhanden war). Oder die Klassifizierung der Dauer ist veraltet (wenn die Klassifizierung vorhanden, aber falsch ist).

## Verwenden

So verwenden Sie ein Bedienfeld **[!UICONTROL Medien-Zielgruppendurchschnitt pro Minute]**:

1. Erstellen Sie ein Bedienfeld **[!UICONTROL Medien-Zielgruppendurchschnitt pro Minute]**. Informationen zum Erstellen eines Bedienfelds finden Sie unter [Erstellen eines Bedienfelds](panels.md#create-a-panel).

1. Stellen Sie sicher, dass Sie eine Datenansicht für das Bedienfeld auswählen, in dem Komponenten aus der Streaming-Mediensammlung konfiguriert sind.

1. Legen Sie die [Eingabe](#panel-input) für das Bedienfeld fest.

1. Sehen Sie sich die [Ausgabe](#panel-output) für das Bedienfeld an.

### Bedienfeldeingabe

Verwenden Sie die in diesem Abschnitt beschriebenen Eingabeeinstellungen, um das Bedienfeld „Medien-Zielgruppendurchschnitt pro Minute“ zu konfigurieren.

1. Konfigurieren Sie die folgenden Eingabeeinstellungen:

   | Einstellung | Beschreibung |
   |---------|------------|
   | **Datumsbereich des Bedienfelds** | Der Datumsbereich des Bedienfelds ist standardmäßig [!UICONTROL **Diesen Monat**]. Sie können ihn so verändern, dass Sie einen einzelnen Tag oder viele Monate auf einmal betrachten können. <br></br> Diese Visualisierung ist auf 1.440 Datenzeilen beschränkt (z. B. 24 Stunden bei einer Granularität auf Minutenebene). Wenn eine Kombination aus Datumsbereich und Granularität mehr als 1.440 Zeilen zur Folge hat, wird die Granularität automatisch aktualisiert, um den vollständigen Datumsbereich anzuzeigen. |
   | [!UICONTROL **Legen Sie hier ein Segment (oder eine beliebige andere Komponente) ab**] | Wie andere Bedienfelder filtert diese Einstellung Ihre Auswahl anhand von Segmenten, die Sie erstellt haben. Diese Einstellung ist eine hervorragende Möglichkeit, bestimmte Plattformen, Live-Streams oder andere gängige Mediensegmente anzusehen. |
   | [!UICONTROL **Metrik berechnen für**] | Wählen Sie aus, ob der Zielgruppendurchschnitt pro Minute für ([**[!UICONTROL  Inhalte) angezeigt ]**](#specific-content) soll. Oder Sie möchten den Zielgruppendurchschnitt pro Minute für einen [**[!UICONTROL  Zeitraum ]**](#custom-time-period).<br/><br/>Wählen Sie [!UICONTROL **Benutzerdefinierter Zeitraum**]: <ul><li>Wenn die Dauer nicht verfügbar ist oder </li><li>wenn Sie den Zielgruppendurchschnitt pro Minute für eine Zeitreihe mit mehreren Inhalten anzeigen möchten, oder</li><li>Für Inhalte ohne bestimmte Dauer (z. B. während eines Live-Streams oder -Ereignisses)</li></ul></li></li></ul> <p>Diese Einstellung ändert den Workflow und die Berichtsausgabe.</p> |

1. Fahren Sie mit [Bestimmter Inhalt](#specific-content) oder [Benutzerdefinierter Zeitraum](#custom-time-period) fort, je nach der Option, die Sie in der Dropdown-Liste [!UICONTROL **Metrik berechnen für**] ausgewählt haben.

#### Bestimmter Inhalt

1. Wenn Sie [!UICONTROL **Spezifischer Inhalt**] im Dropdown-Menü [!UICONTROL **Metrik berechnen für**] beim [Konfigurieren von Bedienfeldeingaben](#panel-inputs) ausgewählt haben, geben Sie die folgenden Konfigurationsoptionen an:

   | Einstellung | Beschreibung |
   |---------|------------|
   | [!UICONTROL **Reporting-Dimension**] | Wenn Sie bestimmte Inhalte auswählen, können Sie für die Berichtsausgabe entweder das Feld für den Videonamen oder die Inhalts-ID verwenden, um den Inhalt und den zugehörigen Zielgruppendurchschnitt pro Minute anzuzeigen. |
   | [!UICONTROL **Inhalt filtern nach (optional)**] | Wählen Sie aus, wie der spezifische Inhalt gefiltert werden soll, je nach der gewünschten Ansicht oder der Art und Weise, wie Ihre Daten strukturiert sind. <ul>[!UICONTROL **Sendung, Staffel, Folge**]: Zeigt Ihre verfügbaren Sendungen in der Dropdown-Liste an, die Sie mithilfe einer Suche filtern können (oder indem Sie den Sendungsnamen aus der linken Spalte ziehen und ablegen). Sie können Ihre Auswahl hier beenden, um alle Staffeln Ihrer Sendung zu sehen, oder Sie können nach einzelnen Staffeln und dann nach einzelnen Folgen filtern. Diese Einstellung zeigt die Daten für diese Sendungen, Staffeln oder Folgen für den ausgewählten Zeitraum an.</li><li>[!UICONTROL **Benutzerdefinierte Dimension**]: Wenn sich der Name der Sendung unter einer benutzerdefinierten Dimension befindet, können Sie ihn entweder über die Suche im Dropdown-Menü der Dimension (optional) oder über die Suche in der linken Spalte finden. Das Dimensionselement wird basierend auf dieser Auswahl automatisch ausgefüllt und als Folge behandelt.</li><li>[!UICONTROL **None**] Zeigt alle Videonamen an, für die Daten über den Zielgruppendurchschnitt pro Minute für die von Ihnen ausgewählte Auswahl vorliegen. (Diese Option ist standardmäßig ausgewählt.)</li></ul> |

1. Fahren Sie mit [Erweiterte Einstellungen für spezifischen Inhalt](#specific-content-advanced-settings) fort, um erweiterte Einstellungen zu konfigurieren.

#### Erweiterte Einstellungen für spezifischen Inhalt

1. Wenn [!UICONTROL **Spezifischer Inhalt**] im Dropdown-Menü [!UICONTROL **Metrik berechnen für**] ausgewählt ist, wählen Sie [!UICONTROL **Erweiterte Einstellungen anzeigen**] und geben Sie dann die folgenden Konfigurationsoptionen an:

   | Optionen | Beschreibung |
   |---------|------------|
   | **[!UICONTROL Tabelleneinstellungen]** | Die Standardoption **[!UICONTROL Berechnungswerte in Tabelle anzeigen]** zeigt den Zähler und Nenner des Zielgruppendurchschnitts pro Minute als die vorangehenden Spalten in der Tabelle an. Wenn Sie diese Option deaktivieren, werden diese beiden Spalten entfernt. Die Spalte für den Zielgruppendurchschnitt pro Minute verbleibt in der Tabelle neben dem Videonamen oder der Inhalts-ID. |
   | **[!UICONTROL Besuchszeitmetrik]** | Sie können die Standardoption **[!UICONTROL Besuchszeit für Inhalt]** auswählen, die nur die Inhaltszeit enthält. Sie können auch die **[!UICONTROL Besuchszeit für Medien]** verwenden, die Inhalte und Anzeigenzeit zusammen als Zählerberechnung für den Zielgruppendurchschnitt pro Minute enthält. |

1. Wählen Sie [!UICONTROL **Erstellen**], um das Erstellen des Bedienfelds „Medien-Zielgruppendurchschnitt pro Minute“ abzuschließen.

1. Fahren Sie mit [Bedienfeldausgabe](#panel-output) fort, um Informationen zur Verwendung des Bedienfelds „Medien-Zielgruppendurchschnitt pro Minute“ zu erhalten.

#### Benutzerdefinierter Zeitraum

1. Wenn Sie [!UICONTROL **Benutzerdefinierter Zeitraum**] im Dropdown-Menü [!UICONTROL **Metrik berechnen für**] beim [Konfigurieren von Bedienfeldeingaben](#panel-inputs) ausgewählt haben, geben Sie die folgenden Konfigurationsoptionen an:

   | Optionen | Beschreibung |
   |---------|------------|
   | **[!UICONTROL Granularität]** | Die Standardgranularität beträgt [!UICONTROL **5 Minuten**] Sie können jedoch eine beliebige Granularität auswählen, die als Nenner für die Zeitreihe innerhalb Ihres ausgewählten Zeitraums verwendet wird. Wenn Sie beispielsweise 12:00 Uhr bis 12:30 Uhr mit einer Granularität von 5 Minuten auswählen, werden der Zielgruppendurchschnitt pro Minute über die gesamte halbe Stunde sowie sechs Zeilen mit dem Zielgruppendurchschnitt pro Minute für jeden 5-minütigen Zeitraum zurückgegeben. Diese Zeilen werden als Datenpunkte für das Zeitreihendiagramm verwendet. |
   | [!UICONTROL **Inhalt filtern nach (optional)**] | Wählen Sie aus, wie der spezifische Inhalt gefiltert werden soll, je nach der gewünschten Ansicht oder der Art und Weise, wie Ihre Daten strukturiert sind. <ul>[!UICONTROL **Sendung, Staffel, Folge**]: Zeigt Ihre verfügbaren Sendungen in der Dropdown-Liste an, die Sie mithilfe einer Suche filtern können (oder indem Sie den Sendungsnamen aus der linken Spalte ziehen und ablegen). Sie können Ihre Auswahl hier beenden, um alle Staffeln Ihrer Sendung zu sehen, oder Sie können nach einzelnen Staffeln und dann nach einzelnen Folgen filtern. Diese Einstellung zeigt die Daten für diese Sendungen, Staffeln oder Folgen für den ausgewählten Zeitraum an.</li><li>[!UICONTROL **Benutzerdefinierte Dimension**]: Wenn sich der Name der Sendung unter einer benutzerdefinierten Dimension befindet, können Sie ihn entweder über die Suche im Dropdown-Menü der Dimension (optional) oder über die Suche in der linken Spalte finden. Das Dimensionselement wird basierend auf dieser Auswahl automatisch ausgefüllt und als Folge behandelt.</li><li>[!UICONTROL **None**] Zeigt alle Videonamen an, für die Daten über den Zielgruppendurchschnitt pro Minute für die von Ihnen ausgewählte Auswahl vorliegen. (Diese Option ist standardmäßig ausgewählt.)</li></ul> |

1. Fahren Sie mit [Erweiterte Einstellungen für benutzerdefinierte Zeiträume](#custom-time-period-advanced-settings) fort, um die erweiterten Einstellungen zu konfigurieren.

#### Erweiterte Einstellungen für benutzerdefinierte Zeiträume

1. Wenn [!UICONTROL **Benutzerdefinierter Zeitraum**] im Dropdown-Menü [!UICONTROL **Metrik berechnen für**] ausgewählt ist, wählen Sie [!UICONTROL **Erweiterte Einstellungen anzeigen**] und geben Sie dann die folgende Konfigurationsoption an:

   | Option | Beschreibung |
   |---------|------------|
   | **[!UICONTROL Tabelleneinstellungen]** | Die Standardeinstellung zeigt die Berechnungswerte in der Tabelle an, die den Zähler und Nenner des Zielgruppendurchschnitts pro Minute als die vorangehenden Spalten in der Tabelle anzeigt. Wenn Sie diese Option deaktivieren, werden die beiden Spalten entfernt, sodass neben dem Zeitraum nur der Zielgruppendurchschnitt pro Minute verbleibt. |

1. Wählen Sie [!UICONTROL **Erstellen**], um das Erstellen des Bedienfelds „Medien-Zielgruppendurchschnitt pro Minute“ abzuschließen.

1. Fahren Sie mit [Bedienfeldausgabe](#panel-output) fort, um Informationen zur Verwendung des Bedienfelds „Medien-Zielgruppendurchschnitt pro Minute“ zu erhalten.

### Bedienfeldausgabe

Die Bedienfeldausgabe unterscheidet sich je nachdem, ob Sie [!UICONTROL **Bestimmter Inhalt**] oder [!UICONTROL **Benutzerdefinierter**] im [!UICONTROL **Metrik berechnen für**] Dropdown-Menü beim [Konfigurieren von Bedienfeldeingaben](#panel-inputs) haben.

#### Bestimmter Inhalt

Das Bedienfeld „Medien-Zielgruppendurchschnitt pro Minute“ gibt Folgendes zurück:

* Gesamtwert des Zielgruppendurchschnitts pro Minute für Ihre gesamte Auswahl
* Filter und Zielgruppendurchschnitt pro Minute für die einzelnen Videos, angezeigt in einer Tabelle
* Mit dem Inhalt verbrachte Zeit und Videolänge (Dauer), wenn diese erweiterte Einstellung ausgewählt wurde

Um das Bedienfeld jederzeit zu bearbeiten und neu zu erstellen, wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) oben rechts aus.

![Standardansicht](assets/specific-content-panel-output.png)

#### Spezifische Inhaltsdatenquelle

Das Bedienfeld „Medien-Zielgruppendurchschnitt pro Minute“ verwendet nur die Metrik „Zielgruppendurchschnitt pro Minute“ zum Erfassen von Daten. Aufschlüsselungen oder andere Metriken können im Bedienfeld nicht verwendet werden.

| Metrik | Beschreibung |
|--------|-------------|
| **[!UICONTROL Zielgruppendurchschnitt pro Minute]** | Die Zeit, die mit der Ansicht Ihres Medien-Streams verbracht wurde, dividiert durch die Videolänge (Dauer), die über Classifications bereitgestellt wird. |

#### Benutzerdefinierter Zeitraum {#custom-time-period-output}

Das Bedienfeld „Medien-Zielgruppendurchschnitt pro Minute“ gibt Folgendes zurück:

* Der Zielgruppendurchschnitt pro Minute für die gesamte Auswahl

* Der maximale und minimale Zielgruppendurchschnitt pro Minute

* Das Liniendiagramm, das den Zielgruppendurchschnitt pro Minute für die gesamte Auswahl anzeigt.

* Eine Tabelle, die die Filter und den Zielgruppendurchschnitt pro Minute für die Granularitäten sowie die mit dem Inhalt verbrachte Zeit und die Granularität für jeden Zeitraum anzeigt

  Diese Tabelle wird nur angezeigt, wenn die Option unter Erweiterte Einstellungen [!UICONTROL **Berechnungswerte in Tabelle anzeigen**] ausgewählt ist.

Um das Bedienfeld jederzeit zu bearbeiten und neu zu erstellen, wählen Sie oben ![ das Bedienfeld ](/help/assets/icons/Edit.svg)Medien-Zielgruppendurchschnitt pro Minute bearbeiten“ aus.


#### Datenquelle für benutzerdefinierten Zeitraum

Das Bedienfeld „Medien-Zielgruppendurchschnitt pro Minute“ verwendet nur die Metrik „Zielgruppendurchschnitt pro Minute“ zum Erfassen von Daten. Aufschlüsselungen oder andere Metriken können im Bedienfeld nicht verwendet werden.

| Metrik | Beschreibung |
|---|---|
| **[!UICONTROL Zielgruppendurchschnitt pro Minute]** | Die mit der Ansicht Ihres Medien-Streams verbrachte Zeit dividiert durch die Gesamtauswahl oder die ausgewählte Granularität in Minuten. |


>[!MORELIKETHIS]
>
> [Erstellen eines Bedienfelds](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
> [Bedienfeld „Gleichzeitige Medienbetrachter“](media-concurrent-viewers.md)
> [Panel „Verbrachte Zeit bei der Medienwiedergabe“](media-playback-time-spent.md)
>