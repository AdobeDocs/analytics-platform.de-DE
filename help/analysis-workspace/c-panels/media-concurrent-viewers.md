---
title: Bedienfeld „Gleichzeitige Medienbetrachter“
description: Erfahren Sie, wie Sie das Bedienfeld „Gleichzeitige Medienbetrachter“ in Analysis Workspace verwenden und interpretieren.
feature: Panels
exl-id: a442fb9c-165f-4136-95e2-ce92b9280c25
role: User
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '1175'
ht-degree: 94%

---

# Bedienfeld „Gleichzeitige Medienbetrachter“ {#media-concurrent-viewers-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_button"
>title="Gleichzeitige Medienbetrachtende"
>abstract="Erstellen Sie ein Panel, um gleichzeitige Betrachtende über einen bestimmten Zeitraum zu analysieren."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_panel"
>title="Gleichzeitige Medienbetrachtende"
>abstract="Analysieren Sie die gleichzeitig Betrachtenden im Zeitverlauf, zeigen Sie Informationen zum maximalen gleichzeitigen Zugriff an oder schlüsseln Sie Daten mithilfe von Segmenten, Dimensionen, Dimensionselementen oder Datumsbereichen auf und vergleichen Sie sie."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_In diesem Artikel wird das Panel Gleichzeitige Medienbetrachter in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;_ beschrieben.<br/>_Unter [Panel Gleichzeitige Medienbetrachter](https://experienceleague.adobe.com/de/docs/analytics/analyze/analysis-workspace/panels/media-concurrent-viewers) finden Sie die Version dieses Artikels für_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._

>[!ENDSHADEBOX]


>[!NOTE]
>
>Das Panel „Medien-Zielgruppendurchschnitt pro Minute“ ist nur für Kundinnen und Kunden verfügbar, die das Streaming Media Collection-Add-on für Customer Journey Analytics gekauft haben.
>
>Wenden Sie sich an Ihren Adobe-Vertriebskontakt oder Ihr Adobe-Acountteam, um weitere Informationen zu erhalten.
>

Das Panel **[!UICONTROL Gleichzeitige Medienbetrachter]** ermöglicht die Analyse von gleichzeitigen Betrachtenden im Zeitverlauf, mit Details zum maximalen gleichzeitigen Zugriff sowie der Möglichkeit von Aufschlüsselungen und Vergleichen.

Sie können gleichzeitige Betrachtende analysieren, um zu verstehen, wo maximaler gleichzeitiger Zugriff auftrat oder wo es zu Abbrüchen kam. So erhalten Sie wertvolle Erkenntnisse zur Qualität von Inhalten und Interaktion mit Betrachtenden. Sie können das Panel außerdem als Hilfe bei der Fehlerbehebung oder Planung von Volumen oder Skalierung verwenden.

In Analysis Workspace umfasst die Metrik „Gleichzeitige Betrachter“ die Anzahl der Unique Persons, die sich Ihre Medien-Streams unabhängig von der Anzahl der Sitzungen zu einem bestimmten Zeitpunkt ansehen.


>[!BEGINSHADEBOX]

Unter ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Panel Gleichzeitige Medienbetrachter](https://video.tv.adobe.com/v/35186/?quality=12&learn=on&captions=ger){target="_blank"} finden Sie ein Demovideo.

{{videoaa}}

>[!ENDSHADEBOX]

## Verwenden

So verwenden Sie das Panel **[!UICONTROL Gleichzeitige Medienbetrachter]**:

1. Erstellen Sie ein Panel **[!UICONTROL Gleichzeitige Medienbetrachter]**. Informationen zum Erstellen eines Bedienfelds finden Sie unter [Erstellen eines Bedienfelds](panels.md#create-a-panel).

1. Stellen Sie sicher, dass Sie eine Datenansicht für das Panel auswählen, in der Komponenten aus der Streaming-Mediensammlung konfiguriert sind.

1. Legen Sie die [Eingabe](#panel-input) für das Bedienfeld fest.

1. Sehen Sie sich die [Ausgabe](#panel-output) für das Bedienfeld an.

### Panel-Eingabe

Sie können das Panel „Gleichzeitige Medienbetrachter“ mithilfe der folgenden Eingabeeinstellungen konfigurieren:

| Einstellung | Beschreibung |
|---|---|
| **[!UICONTROL Datumsbereich der Panels]** | Der Datumsbereich des Panels ist standardmäßig „Heute“.  Sie können ihn so verändern, dass Sie einen einzelnen Tag oder viele Monate auf einmal betrachten können. <br> <br>Diese Visualisierung ist auf 1440 Datenzeilen beschränkt (z. B. 24 Stunden bei einer Granularität auf Minutenebene).  Wenn eine Kombination aus Datumsbereich und Granularität mehr als 1.440 Zeilen zur Folge hat, wird die Granularität automatisch aktualisiert, um den vollständigen Datumsbereich anzuzeigen. |
| **[!UICONTROL Granularität]** | Die Standardeinstellung für die Granularität ist „Minute“.<br>Diese Visualisierung ist auf 1440 Datenzeilen beschränkt (z. B. 24 Stunden bei einer Granularität auf Minutenebene).  Wenn eine Kombination aus Datumsbereich und Granularität mehr als 1.440 Zeilen zur Folge hat, wird die Granularität automatisch aktualisiert, um den vollständigen Datumsbereich anzuzeigen. |
| **[!UICONTROL Zusammenfassende Zahlen der Panels]** | Um Details zu Datum und Uhrzeit für gleichzeitige Betrachter anzuzeigen, steht eine Zusammenfassungsnummer zur Verfügung. Das Maximum zeigt Details zu Spitzenzeiten von gleichzeitigen Aufrufen an. **[!UICONTROL Minimum]** zeigt Details für die Talsohle an.  Die Standardeinstellung im Bedienfeld zeigt nur das Maximum an, Sie können diese Einstellung jedoch ändern, um nur das Minimum oder sowohl Maximum als auch Minimum anzuzeigen.<br><br>Wenn Sie Aufschlüsselungen verwenden, wird jeweils eine Zusammenfassungsnummer angezeigt. |
| **[!UICONTROL Serienaufschlüsselung]** | Optional können Sie Ihre Visualisierung nach Segmenten, Dimensionen, Dimensionselementen oder Datumsbereichen unterteilen.<br>Sie können bis zu 10 Zeilen auf einmal ansehen. Aufschlüsselungen sind auf eine einzelne Ebene beschränkt.<br>Beim Ziehen einer Dimension werden die oberen Dimensionselemente automatisch anhand des im Panel ausgewählten Datumsbereichs ausgewählt.<br>Ziehen Sie zum Vergleichen von Datumsbereichen zwei oder mehr Datumsbereiche in das Aufschlüsselungssegment der Serie. |

Im Folgenden finden Sie ein Beispiel für das für die Granularität **[!UICONTROL Minute]** konfigurierte Panel mit den Zusammenfassungszahlen für **[!UICONTROL Nur Maximum]**. Und aufgeschlüsselt nach **[!UICONTROL Sonstige]**, **[!UICONTROL Tabelle]**, **[!UICONTROL Handy]**, **[!UICONTROL Spielkonsole]**, **[!UICONTROL Medienplayer]**, **[!UICONTROL Set-top-Box]**, **[!UICONTROL Fernseher]**.

![Die Serienaufschlüsselungsansicht Gleichzeitige Medienbetrachter mit 7 von 10 Dimensionen, Segmenten oder Datumsbereichen.](assets/concurrent-viewers-series-breakdown.png)

### Panel-Ausgabe

Das Bedienfeld „Gleichzeitige Medienbetrachter“ gibt ein Liniendiagramm und Zusammenfassungsnummern zurück, die Details zu maximalen und/oder minimalen gleichzeitigen Betrachtern enthalten.  Oben im Panel wird eine Zusammenfassungszeile angezeigt, die Sie an die ausgewählten Panel-Einstellungen erinnert.

Sie können jederzeit ![Panel „Gleichzeitige Medienbetrachter“ bearbeiten](/help/assets/icons/Edit.svg) auswählen, um das Panel zu bearbeiten und neu zu erstellen.

Wenn Sie eine Serienaufschlüsselung ausgewählt haben, wird für jeden der folgenden Punkte eine Zeile im Liniendiagramm und eine Zusammenfassungszahl angezeigt:

![Die Ausgabe für Gleichzeitige Medienbetrachter.](assets/concurrent-viewers-output.png)

### Datenquelle

Die einzige Metrik, die in diesem Panel verwendet werden kann, ist **[!UICONTROL Gleichzeitige Betrachter]**:

| Metrik | Beschreibung |
|---|---|
| **[!UICONTROL Gleichzeitige Betrachter]** | Die Anzahl der Unique Persons, die Ihre Medien-Streams zu einem bestimmten Zeitpunkt angesehen haben, unabhängig von der Anzahl der Sitzungen. |

Eine Freiformtabelle ist in dieser Ansicht nicht verfügbar.  Um die Datenquelle anzuzeigen, können Sie die Datenquelle über das Kontextmenü für die Liniendiagrammvisualisierung herunterladen und **[!UICONTROL Daten als CSV herunterladen]** auswählen.  Serienaufschlüsselungen sind enthalten.

![Die Ausgabeoptionen für Gleichzeitige Betrachter mit der hervorgehobenen Option Daten als CSV herunterladen.](assets/concurrent-viewers-download-csv.png)

## Häufig gestellte Fragen (FAQ)

| Frage | Antwort |
|---|---|
| Wo ist die Freiformtabelle? Wie kann ich die Datenquelle anzeigen? | Die Freiformtabelle ist in dieser Ansicht nicht verfügbar.  Sie können die Datenquelle über das Kontextmenü des Liniendiagramms herunterladen und die Option **[!UICONTROL Daten als CSV herunterladen]** auswählen. |
| Warum hat sich meine Granularität verändert? | Diese Visualisierung ist auf 1440 Datenzeilen beschränkt (z. B. 24 Stunden bei einer Granularität auf Minutenebene).  Wenn eine Kombination aus Datumsbereich und Granularität mehr als 1.440 Zeilen zur Folge hat, wird die Granularität automatisch aktualisiert, um den vollständigen Datumsbereich anzuzeigen.<br><br>Wenn Sie von einem größeren zu einem kleineren Datumsbereich wechseln, wird die Granularität auf das niedrigste zulässige Detail aktualisiert, sobald der Datumsbereich geändert wird. Um eine höhere Granularität zu sehen, bearbeiten Sie das Panel und erstellen Sie es erneut. |
| Wie vergleiche ich Videonamen, Segmente, Inhaltstypen und andere? | Um diese Elemente in einer einzigen Visualisierung zu vergleichen, ziehen Sie Segmente, Dimensionen oder bestimmte Dimensionselemente in das Aufschlüsselungssegment der Serie.<br><br>Die Ansicht ist auf 10 Aufschlüsselungen beschränkt.  Um mehr als 10 ansehen zu können, müssen Sie mehrere Bedienfelder verwenden. |
| Wie vergleiche ich Datumsbereiche? | Um Datumsbereiche in einer einzigen Visualisierung zu vergleichen, verwenden Sie die Serienaufschlüsselungen, indem Sie zwei oder mehr Datumsbereiche in das Panel ziehen.  Diese Datumsbereiche setzen den Datumsbereich des Panels außer Kraft. |
| Wie ändere ich den Visualisierungstyp? | Dieses Bedienfeld ermöglicht nur die Linienvisualisierung für die Zeitreihen. |
| Kann ich die Anomalieerkennung ausführen? | Nein.  Die Anomalieerkennung ist für dieses Panel nicht verfügbar. |
| Warum sollte ich Unique Persons anstelle von aktiven Sitzungen verwenden? | Die Verwendung von Unique Persons ermöglicht das Entfernen unerwünschter Spitzen in den Anzeige-Grenzbereichen (wo Sitzungen gleichzeitig enden und beginnen). |
| Was bedeutet es, parallele Betrachter mit einer Granularität von mehr als einer Minute zu haben? | Bei einer Granularität von mehr als einer Minute stellen gleichzeitige Betrachter die Summe der gleichzeitigen Unique Viewers für alle Minuten innerhalb dieses Zeitraums dar.  Beispielsweise ist die Granularität gleichzeitiger Betrachtender auf Stundenebene die Summe der gleichzeitigen Unique Persons für alle Minuten innerhalb der Stunde. |
| Zeigt das Arbeitsbereich-Bedienfeld dieselben Informationen wie der Bericht zu gleichzeitigen Betrachtern? | Nein.  In Analysis Workspace ist die Metrik „Gleichzeitige Betrachter“ definiert als die Anzahl der Unique Persons, die sich Ihren Medien-Stream zu einem bestimmten Zeitpunkt ansehen. Unabhängig von der Anzahl der Sitzungen.<br><br>Diese Metrik unterscheidet sich vom Bericht Gleichzeitige Betrachter im Bereich Berichte, wo die gleichzeitigen aktiven Sitzungen zugrunde gelegt werden. Durch die Verwendung der Unique Persons werden unerwünschte „Spitzen“ in den Anzeige-Grenzbereichen (wo die Sitzungen gleichzeitig enden und beginnen) entfernt. |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->


>[!MORELIKETHIS]
>
>[Erstellen eines Bedienfelds](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>&#x200B;>[Panel Verbrachte Zeit bei der Medienwiedergabe](media-playback-time-spent.md)
>&#x200B;>[Panel Medien-Zielgruppendurchschnitt pro Minute](average-minute-audience-panel.md)
>