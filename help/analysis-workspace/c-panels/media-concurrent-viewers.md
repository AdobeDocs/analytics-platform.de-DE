---
title: Bedienfeld „Gleichzeitige Medienbetrachter“
description: Verwendung und Interpretation des Bedienfelds „Gleichzeitige Medienbetrachter“ in Analysis Workspace.
feature: Panels
exl-id: a442fb9c-165f-4136-95e2-ce92b9280c25
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '1238'
ht-degree: 46%

---

# Bedienfeld „Gleichzeitige Medienbetrachter“ {#media-concurrent-viewers-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_button"
>title="Gleichzeitige Medienbetrachtende"
>abstract="Erstellen Sie ein Panel, um den Zielgruppendurchschnitt pro Minute für bestimmte Inhalte oder über einen bestimmten Zeitraum zu analysieren."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_panel"
>title="Gleichzeitige Medienbetrachtende"
>abstract="Analysieren Sie gleichzeitige Betrachtende im Zeitverlauf, zeigen Sie Informationen zum maximalen gleichzeitigen Zugriff an oder schlüsseln Sie Daten auf und vergleichen Sie sie.<br/><br>**Granularität**: Wählen Sie aus, nach welchem Zeitraum gleichzeitige Betrachtende angezeigt werden sollen.<br/>**Zusammenfassende Zahlen der Bedienfelder**:<br/>Wählen Sie diese Option aus, um für jede Zeile zusammenfassende Zahlen mit Datums- oder Uhrzeitangaben anzuzeigen. „Maximum“ zeigt Details zum maximalen gleichzeitigen Zugriff an. „Minimum“ zeigt Details für die minimale Wiedergabedauer an.<br/>**Serienaufschlüsselung (optional)**: Schlüsseln Sie Visualisierungen nach Segmenten, Dimensionen, Dimensionselementen oder Datumsbereichen auf. Sie können jeweils bis zu 10 Zeilen anzeigen. Aufschlüsselungen sind auf eine einzelne Ebene beschränkt."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_In diesem Artikel wird das Bedienfeld „Gleichzeitige Medienbetrachter“ in {_}![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_.<br/>_Siehe [Bedienfeld „Gleichzeitige Medienbetrachter](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/media-concurrent-viewers) für die_![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**-Version dieses Artikels._

>[!ENDSHADEBOX]


>[!NOTE]
>
>Das Bedienfeld „Medien-Zielgruppendurchschnitt pro Minute“ ist nur für Kunden verfügbar, die das Add-on „Streaming Media Collection“ zum Customer Journey Analytics erworben haben.
>
>Wenden Sie sich an Ihren Adobe-Kundenbetreuer oder Ihr Adobe-Kundenbetreuerteam, um weitere Informationen zu erhalten.
>

Das Bedienfeld **[!UICONTROL Gleichzeitige Medienbetrachter]** ermöglicht die Analyse gleichzeitiger Betrachter im Zeitverlauf mit Details zu Spitzenzeiten von gleichzeitigen Betrachtern und der Möglichkeit, diese aufzuschlüsseln und zu vergleichen.

Sie können gleichzeitige Betrachter analysieren, um zu verstehen, wo Spitzenzeiten mit gleichzeitigen Ansichten auftraten oder wo es zu Abbrüchen kam. So erhalten Sie wertvolle Einblicke in die Qualität von Inhalten und die Interaktion mit Betrachtern. Und um bei der Fehlerbehebung oder Planung von Volumen oder Skalierung zu helfen.

In Analysis Workspace bezeichnet die Metrik „Gleichzeitige Betrachter“ die Anzahl der eindeutigen Personen, die sich Ihre Medien-Streams zu einem bestimmten Zeitpunkt ansehen, unabhängig von der Anzahl der Sitzungen.


>[!BEGINSHADEBOX]

Siehe ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Bedienfeld „Gleichzeitige Medienbetrachter](https://video.tv.adobe.com/v/26990/?quality=12&learn=on){target="_blank"} für ein Demovideo.

{{videoaa}}

>[!ENDSHADEBOX]

## Verwenden

So verwenden Sie ein Bedienfeld **[!UICONTROL Gleichzeitige Medienbetrachter]**:

1. Erstellen Sie ein Bedienfeld **[!UICONTROL Gleichzeitige Medienbetrachter]**. Informationen zum Erstellen eines Bedienfelds finden Sie unter [Erstellen eines Bedienfelds](panels.md#create-a-panel).

1. Stellen Sie sicher, dass Sie eine Datenansicht für das Bedienfeld auswählen, in dem Komponenten aus der Streaming-Mediensammlung konfiguriert sind.

1. Legen Sie die [Eingabe](#panel-input) für das Bedienfeld fest.

1. Sehen Sie sich die [Ausgabe](#panel-output) für das Bedienfeld an.

### Bedienfeldeingabe

Sie können das Bedienfeld „Gleichzeitige Medienbetrachter“ mithilfe der folgenden Eingabeeinstellungen konfigurieren:

| Einstellung | Beschreibung |
|---|---|
| **[!UICONTROL Datumsbereich des Bedienfelds]** | Der Datumsbereich des Panels ist standardmäßig „Heute“.  Sie können ihn so verändern, dass Sie einen einzelnen Tag oder viele Monate auf einmal betrachten können. <br> <br>Diese Visualisierung ist auf 1440 Datenzeilen beschränkt (z. B. 24 Stunden bei einer Granularität auf Minutenebene).  Wenn eine Kombination aus Datumsbereich und Granularität zu mehr als 1440 Zeilen führt, wird die Granularität automatisch reduziert, um den vollständigen Datumsbereich zu erlauben. |
| **[!UICONTROL Granularität]** | Die Standardeinstellung für die Granularität ist „Minute“.<br>Diese Visualisierung ist auf 1440 Datenzeilen beschränkt (z. B. 24 Stunden bei einer Granularität auf Minutenebene).  Wenn eine Kombination aus Datumsbereich und Granularität zu mehr als 1440 Zeilen führt, wird die Granularität automatisch reduziert, um den vollständigen Datumsbereich zu erlauben. |
| **[!UICONTROL Zusammenfassungszahlen des Bedienfelds]** | Um Details zu Datum und Uhrzeit für gleichzeitige Betrachter anzuzeigen, steht eine Zusammenfassungsnummer zur Verfügung. Das Maximum zeigt Details zu Spitzenzeiten von gleichzeitigen Aufrufen an. **[!UICONTROL Minimum]** zeigt Details zum Tiefstand an.  Die Standardeinstellung im Bedienfeld zeigt nur das Maximum an, Sie können diese Einstellung jedoch ändern, um nur das Minimum oder sowohl Maximum als auch Minimum anzuzeigen.<br><br>Wenn Sie Aufschlüsselungen verwenden, wird jeweils eine Zusammenfassungsnummer angezeigt. |
| **[!UICONTROL Aufschlüsselung nach Serie]** | Optional können Sie Ihre Visualisierung nach Filtern, Dimensionen, Dimensionselementen oder Datumsbereichen aufschlüsseln.<br>Sie können bis zu 10 Zeilen auf einmal ansehen. Aufschlüsselungen sind auf eine einzelne Ebene beschränkt.<br>Beim Ziehen einer Dimension werden die oberen Dimensionselemente automatisch anhand des im Bedienfeld ausgewählten Datumsbereichs ausgewählt.<br>Ziehen Sie zum Vergleichen von Datumsbereichen zwei oder mehr Datumsbereiche in den Filter für die Aufschlüsselung der Serie. |

Im Folgenden finden Sie ein Beispiel für das für die Granularität **[!UICONTROL Minute]** konfigurierte Bedienfeld mit **[!UICONTROL nur maximalen]** Zusammenfassungszahlen. und aufgeschlüsselt nach **[!UICONTROL Sonstige]**, **[!UICONTROL Tisch]**, **[!UICONTROL Mobiltelefon]**, **[!UICONTROL Spielkonsole]**, **[!UICONTROL Media Player]**, **[!UICONTROL Set-Top-Box]**, **[!UICONTROL Fernsehen]**.

![Die Aufschlüsselungsansicht „Gleichzeitige Medienbetrachter“ mit 7 von 10 Dimensionen, Segmenten oder Datumsbereichen.](assets/concurrent-viewers-series-breakdown.png)

### Bedienfeldausgabe

Das Bedienfeld „Gleichzeitige Medienbetrachter“ gibt ein Liniendiagramm und Zusammenfassungsnummern zurück, die Details zu maximalen und/oder minimalen gleichzeitigen Betrachtern enthalten.  Oben im Bedienfeld wird eine Zusammenfassungszeile angezeigt, die Sie an die ausgewählten Bedienfeldeinstellungen erinnert.

Wählen Sie jederzeit ![Bedienfeld „Gleichzeitige Medienbetrachter bearbeiten](/help/assets/icons/Edit.svg) aus, um das Bedienfeld zu bearbeiten und neu zu erstellen.

Wenn Sie eine Serienaufschlüsselung auswählen, wird jeweils eine Zeile im Liniendiagramm und eine Zusammenfassungsnummer angezeigt:

![Die Ausgabe gleichzeitiger Medienbetrachter.](assets/concurrent-viewers-output.png)

### Datenquelle

Die einzige Metrik, die in diesem Bedienfeld verwendet werden kann, ist **[!UICONTROL Gleichzeitige Betrachter]**:

| Metrik | Beschreibung |
|---|---|
| **[!UICONTROL Gleichzeitige Betrachter]** | Die Anzahl der eindeutigen Personen, die sich Ihre Medien-Streams zu einem bestimmten Zeitpunkt ansehen, unabhängig von der Anzahl der Sitzungen. |

Eine Freiformtabelle ist in dieser Ansicht nicht verfügbar.  Um die Datenquelle anzuzeigen, können Sie die Datenquelle über das Kontextmenü für die Liniendiagrammvisualisierung herunterladen und **[!UICONTROL Daten als CSV herunterladen]** auswählen.  Serienaufschlüsselungen sind enthalten.

![Die Ausgabeoptionen von gleichzeitigen Betrachtern mit der hervorgehobenen Option „Daten als CSV herunterladen“.](assets/concurrent-viewers-download-csv.png)

## Häufig gestellte Fragen (FAQ)

| Frage | Antwort |
|---|---|
| Wo ist die Freiformtabelle? Wie kann ich die Datenquelle anzeigen? | Die Freiformtabelle ist in dieser Ansicht nicht verfügbar.  Sie können die Datenquelle über das Kontextmenü des Liniendiagramms herunterladen und die Option **[!UICONTROL Daten als CSV herunterladen]** auswählen. |
| Warum hat sich meine Granularität verändert? | Diese Visualisierung ist auf 1440 Datenzeilen beschränkt (z. B. 24 Stunden bei einer Granularität auf Minutenebene).  Wenn eine Kombination aus Datumsbereich und Granularität mehr als 1.440 Zeilen zur Folge hat, wird die Granularität automatisch aktualisiert, um den vollständigen Datumsbereich anzuzeigen.<br><br>Wenn Sie von einem größeren auf einen kleineren Datumsbereich wechseln, wird die Granularität auf das niedrigste zulässige Detail aktualisiert, sobald der Datumsbereich geändert wird. Um eine höhere Granularität zu sehen, bearbeiten Sie das Bedienfeld und erstellen Sie es erneut. |
| Wie vergleiche ich Videonamen, Filter, Inhaltstypen und andere? | Um diese Elemente in einer einzigen Visualisierung zu vergleichen, ziehen Sie Filter, Dimensionen oder bestimmte Dimensionselemente in den Filter für die Serienaufschlüsselung.<br><br>Die Ansicht ist auf 10 Aufschlüsselungen beschränkt.  Um mehr als 10 ansehen zu können, müssen Sie mehrere Bedienfelder verwenden. |
| Wie vergleiche ich Datumsbereiche? | Um Datumsbereiche in einer einzigen Visualisierung zu vergleichen, verwenden Sie die Serienaufschlüsselungen, indem Sie zwei oder mehr Datumsbereiche in das Panel ziehen.  Die Datumsbereiche überschreiben den Datumsbereich des Bedienfelds. |
| Wie ändere ich den Visualisierungstyp? | Dieses Bedienfeld ermöglicht nur die Linienvisualisierung für die Zeitreihen. |
| Kann ich die Anomalieerkennung ausführen? | Nein.  Die Anomalieerkennung ist für dieses Panel nicht verfügbar. |
| Warum sollte ich statt aktiver Sitzungen eindeutige Personen verwenden? | Die Verwendung von Einzelpersonen ermöglicht das Entfernen unerwünschter Spitzen an den Anzeigegrenzen (wo Sitzungen gleichzeitig enden und beginnen). |
| Was bedeutet es, parallele Betrachter mit einer Granularität von mehr als einer Minute zu haben? | Bei einer Granularität von mehr als einer Minute stellen gleichzeitige Betrachter die Summe der gleichzeitigen Unique Viewers für alle Minuten innerhalb dieses Zeitraums dar. Beispielsweise ist die Granularität gleichzeitiger Betrachter auf Stundenebene die Summe der gleichzeitigen Unique Viewers für alle Minuten innerhalb der Stunde. |
| Zeigt das Arbeitsbereich-Bedienfeld dieselben Informationen wie der Bericht zu gleichzeitigen Betrachtern? | Nein.  In Analysis Workspace ist die Metrik „Gleichzeitige Betrachter“ definiert als die Anzahl der eindeutigen Personen, die sich Ihren Medien-Stream zu einem bestimmten Zeitpunkt ansehen. Unabhängig von der Anzahl der Sitzungen.<br><br>Diese Metrik unterscheidet sich vom Bericht „Gleichzeitige Betrachter“ im Bereich „Berichte“, wo die gleichzeitigen aktiven Sitzungen zugrunde gelegt werden. Durch die Verwendung von Einzelpersonen werden unerwünschte Spitzen an den Anzeigegrenzen (wo die Sitzungen gleichzeitig enden und beginnen) entfernt. |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->


>[!MORELIKETHIS]
>
>[Erstellen eines Bedienfelds](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>[Panel „Verbrachte Zeit bei der Medienwiedergabe“](media-playback-time-spent.md)
>[Bedienfeld „Medien-Zielgruppendurchschnitt pro Minute“](average-minute-audience-panel.md)
>