---
title: Bedienfeld „Gleichzeitige Medienbetrachter“
description: Verwendung und Interpretation des Bedienfelds "Gleichzeitige Medienbetrachter"in Analysis Workspace.
feature: Panels
exl-id: a442fb9c-165f-4136-95e2-ce92b9280c25
role: User
source-git-commit: 1dff53e244e5d231e7075ce087705e33e0978096
workflow-type: tm+mt
source-wordcount: '1208'
ht-degree: 36%

---

# Bedienfeld &quot;Gleichzeitige Medienbetrachter&quot; {#media-concurrent-viewers-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaconcurrentviewers_button"
>title="Gleichzeitige Medienbetrachter"
>abstract="Erstellen Sie ein Bedienfeld, um die durchschnittliche Minutenzielgruppe für bestimmte Inhalte oder über einen bestimmten Zeitraum zu analysieren."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaconcurrentviewers_panel"
>title="Gleichzeitige Medienbetrachter"
>abstract="Analysieren Sie gleichzeitige Betrachter im Zeitverlauf, sehen Sie Spitzenzeiten bei gleichzeitigen Ansichten oder unterteilen Sie die Ansichten und vergleichen Sie sie.<br/><br>**Granularität**: Wählen Sie einen Zeitraum aus, nach dem gleichzeitige Betrachter angezeigt werden sollen.<br/>**Bereichszusammenfassungsnummern**:<br/>Option, Zusammenfassungsnummern mit Datums- oder Uhrzeitdetails für jede Zeile anzuzeigen. Maximal zeigt Details für Spitzengleichzeitigkeit an. Das Minimum zeigt Details für den Tief an.<br/>**Aufschlüsselung nach Serie (optional)**: Schlüsseln Sie die Visualisierung nach Segmenten, Dimensionen, Dimensionselementen oder Datumsbereichen auf. Sie können bis zu 10 Zeilen gleichzeitig anzeigen. Aufschlüsselungen sind auf eine einzelne Ebene beschränkt."

<!-- markdownlint-enable MD034 -->



>[!NOTE]
>
>Das Zielgruppen-Bedienfeld &quot;Durchschnittliche Medienminuten&quot;steht nur Kunden zur Verfügung, die das Streaming-Mediensammlungs-Add-on für Customer Journey Analytics erworben haben.
>
>Weitere Informationen erhalten Sie von Ihrem Adobe Sales-Support-Mitarbeiter oder Adobe-Account-Team.
>

Das Bedienfeld **[!UICONTROL Gleichzeitige Medienbetrachter]** ermöglicht die Analyse gleichzeitiger Betrachter im Zeitverlauf mit Details zu Spitzenzeiten bei gleichzeitigen Betrachtern und die Möglichkeit, aufzuschlüsseln und zu vergleichen.

Sie können gleichzeitige Betrachter analysieren, um zu verstehen, wo Spitzenzeiten von gleichzeitigen Ansichten auftraten oder wo es zu Abbrüchen kam. So erhalten Sie wertvolle Einblicke in die Qualität von Inhalten und die Interaktion mit Betrachtern. Und um bei der Fehlerbehebung oder Planung für Volumen oder Skalierung zu helfen.

In Analysis Workspace bezeichnet die Metrik &quot;Gleichzeitige Betrachter&quot;die Anzahl der Einzelanwender, die Ihre Medien-Streams zu einem bestimmten Zeitpunkt anzeigen, unabhängig von der Anzahl der Sitzungen.


+++ Sehen Sie sich ein Video an, um diese Funktion zu demonstrieren.

>[!VIDEO](https://video.tv.adobe.com/v/330177/?quality=12)

{{videoaa}}

+++

## Verwenden Sie stattdessen 

So verwenden Sie ein Bedienfeld für gleichzeitige Medienbetrachter ]**:**[!UICONTROL 

1. Erstellen Sie ein Bedienfeld für gleichzeitige Medienbetrachter ]**.**[!UICONTROL  Informationen zum Erstellen eines Bedienfelds finden Sie unter [Erstellen eines Bedienfelds](panels.md#create-a-panel).

1. Stellen Sie sicher, dass Sie eine Datenansicht für das Bedienfeld auswählen, für das im Add-on für Streaming-Mediensammlung Komponenten konfiguriert sind.

1. Geben Sie die [Eingabe](#panel-input) für das Bedienfeld an.

1. Beobachten Sie die [Ausgabe](#panel-output) für das Bedienfeld.

### Bedienfeldeingabe

Sie können das Bedienfeld &quot;Gleichzeitige Medienbetrachter&quot;mit den folgenden Eingabeeinstellungen konfigurieren:

| Einstellung | Beschreibung |
|---|---|
| **[!UICONTROL Datumsbereich des Bedienfelds]** | Der Datumsbereich des Panels ist standardmäßig „Heute“.  Sie können ihn so verändern, dass Sie einen einzelnen Tag oder viele Monate auf einmal betrachten können. <br> <br>Diese Visualisierung ist auf 1440 Datenzeilen beschränkt (z. B. 24 Stunden bei einer Granularität auf Minutenebene).  Wenn eine Kombination aus Datumsbereich und Granularität zu mehr als 1440 Zeilen führt, wird die Granularität automatisch reduziert, um den vollständigen Datumsbereich zu erlauben. |
| **[!UICONTROL Granularität]** | Die Standardeinstellung für die Granularität ist „Minute“.<br>Diese Visualisierung ist auf 1440 Datenzeilen beschränkt (z. B. 24 Stunden bei einer Granularität auf Minutenebene).  Wenn eine Kombination aus Datumsbereich und Granularität zu mehr als 1440 Zeilen führt, wird die Granularität automatisch reduziert, um den vollständigen Datumsbereich zu erlauben. |
| **[!UICONTROL Zusammenfassungsnummern der Bedienfelder]** | Um Details zu Datum und Uhrzeit für gleichzeitige Betrachter anzuzeigen, steht eine Zusammenfassungsnummer zur Verfügung. Das Maximum zeigt Details zu Spitzenzeiten von gleichzeitigen Aufrufen an. **[!UICONTROL Minimum]** zeigt Details für den Tief an.  Die Standardeinstellung im Bedienfeld zeigt nur das Maximum an, Sie können diese Einstellung jedoch ändern, um nur das Minimum oder sowohl Maximum als auch Minimum anzuzeigen.<br><br>Wenn Sie Aufschlüsselungen verwenden, wird jeweils eine Zusammenfassungsnummer angezeigt. |
| **[!UICONTROL Aufschlüsselung nach Serie]** | Optional können Sie Ihre Visualisierung nach Filtern, Dimensionen, Dimensionselementen oder Datumsbereichen aufschlüsseln.<br>Sie können bis zu 10 Zeilen gleichzeitig anzeigen. Aufschlüsselungen sind auf eine einzelne Ebene beschränkt.<br>Beim Ziehen einer Dimension werden die obersten Dimensionselemente automatisch basierend auf dem ausgewählten Datumsbereich des Bedienfelds ausgewählt.<br>Um Datumsbereiche zu vergleichen, ziehen Sie zwei oder mehr Datumsbereiche in den Filter für die Aufschlüsselung nach Reihen. |

Im Folgenden finden Sie ein Beispiel für das Bedienfeld, das für die Granularität **[!UICONTROL Minute]** konfiguriert ist, mit den Zusammenfassungsnummern **[!UICONTROL Nur Maximum]** . und aufgeschlüsselt nach **[!UICONTROL Sonstiges]**, **[!UICONTROL Tabelle]**, **[!UICONTROL Mobiltelefon]**, **[!UICONTROL Spielekonsole]**, **[!UICONTROL Medienplayer]**, **[!UICONTROL Set-Top-Box]**, **[!UICONTROL Fernsehen]**.

![Die Aufschlüsselungsansicht der Serie &quot;Gleichzeitige Medienbetrachter&quot;mit 7 von 10 Dimensionen, Segmenten oder Datumsbereichen.](assets/concurrent-viewers-series-breakdown.png)

### Bedienfeldausgabe

Das Bedienfeld „Gleichzeitige Medienbetrachter“ gibt ein Liniendiagramm und Zusammenfassungsnummern zurück, die Details zu maximalen und/oder minimalen gleichzeitigen Betrachtern enthalten.  Oben im Bedienfeld wird eine Zusammenfassungszeile angezeigt, die Sie an die ausgewählten Bedienfeldeinstellungen erinnert.

Wählen Sie jederzeit ![Bedienfeld &quot;Gleichzeitige Medienbetrachter bearbeiten&quot;](/help/assets/icons/Edit.svg) aus, um das Bedienfeld zu bearbeiten und neu zu erstellen.

Wenn Sie eine Aufschlüsselung nach Serie auswählen, werden eine Zeile im Liniendiagramm und eine Zusammenfassungsnummer für jede Zeile angezeigt:

![ Die Ausgabe der gleichzeitigen Medienbetrachter.](assets/concurrent-viewers-output.png)

### Datenquelle

Die einzige Metrik, die in diesem Bedienfeld verwendet werden kann, ist **[!UICONTROL Gleichzeitige Viewer]**:

| Metrik | Beschreibung |
|---|---|
| **[!UICONTROL Gleichzeitige Betrachter]** | Die Anzahl der Einzelanwender, die Ihre Medien-Streams zu einem bestimmten Zeitpunkt anzeigen, unabhängig von der Anzahl der Sitzungen. |

Eine Freiformtabelle ist in dieser Ansicht nicht verfügbar.  Um die Datenquelle anzuzeigen, können Sie die Datenquelle aus dem Kontextmenü für die Liniendiagrammvisualisierung herunterladen und **[!UICONTROL Daten als CSV herunterladen]** auswählen.  Serienunterteilungen sind enthalten.

![Die Ausgabeoptionen der gleichzeitigen Viewer mit &quot;Daten als CSV herunterladen&quot;sind hervorgehoben.](assets/concurrent-viewers-download-csv.png)

## Häufig gestellte Fragen (FAQ)

| Frage | Antwort |
|---|---|
| Wo ist die Freiformtabelle? Wie kann ich die Datenquelle anzeigen? | Die Freiformtabelle ist in dieser Ansicht nicht verfügbar.  Sie können die Datenquelle aus dem Kontextmenü für Liniendiagramme herunterladen und **[!UICONTROL Daten als CSV herunterladen]** auswählen. |
| Warum hat sich meine Granularität verändert? | Diese Visualisierung ist auf 1440 Datenzeilen beschränkt (z. B. 24 Stunden bei einer Granularität auf Minutenebene).  Wenn eine Kombination aus Datumsbereich und Granularität mehr als 1.440 Zeilen zur Folge hat, wird die Granularität automatisch aktualisiert, um den vollständigen Datumsbereich anzuzeigen.<br><br>Wenn Sie von einem größeren Datumsbereich in einen kleineren wechseln, wird die Granularität auf das niedrigste Detail aktualisiert, das nach Änderung des Datumsbereichs zulässig ist. Um eine höhere Granularität zu sehen, bearbeiten Sie das Bedienfeld und erstellen Sie es erneut. |
| Wie vergleiche ich Videonamen, Filter, Inhaltstypen und andere? | Um diese Elemente in einer einzigen Visualisierung zu vergleichen, ziehen Sie Filter, Dimensionen oder bestimmte Dimensionselemente in den Filter für die Serienaufschlüsselung.<br><br>Die Ansicht ist auf 10 Aufschlüsselungen beschränkt.  Um mehr als 10 ansehen zu können, müssen Sie mehrere Bedienfelder verwenden. |
| Wie vergleiche ich Datumsbereiche? | Um Datumsbereiche in einer einzigen Visualisierung zu vergleichen, verwenden Sie die Serienaufschlüsselungen, indem Sie zwei oder mehr Datumsbereiche in das Panel ziehen.  Die Datumsbereiche überschreiben den Datumsbereich des Bedienfelds. |
| Wie ändere ich den Visualisierungstyp? | Dieses Bedienfeld ermöglicht nur die Linienvisualisierung für die Zeitreihen. |
| Kann ich die Anomalieerkennung ausführen? | Nein.  Die Anomalieerkennung ist für dieses Panel nicht verfügbar. |
| Warum sollten Sie eindeutige Personen anstelle aktiver Sitzungen verwenden? | Die Verwendung von Einzelpersonen ermöglicht die Entfernung unerwünschter Spitzen an Vorstellungsgrenzen (wobei Sitzungen gleichzeitig enden und beginnen). |
| Was bedeutet es, parallele Betrachter mit einer Granularität von mehr als einer Minute zu haben? | Bei einer Granularität von mehr als einer Minute stellen gleichzeitige Betrachter die Summe der gleichzeitigen Unique Viewers für alle Minuten innerhalb dieses Zeitraums dar. Beispielsweise stellen gleichzeitige Betrachter auf Stundenebene die Summe der eindeutigen gleichzeitigen Betrachter für alle Minuten innerhalb der Stunde dar. |
| Zeigt das Arbeitsbereich-Bedienfeld dieselben Informationen wie der Bericht zu gleichzeitigen Betrachtern? | Nein.  In Analysis Workspace ist die Metrik &quot;Gleichzeitige Betrachter&quot;definiert als die Anzahl eindeutiger Personen, die Ihren Medienstream zu einem bestimmten Zeitpunkt anzeigen. Unabhängig von der Anzahl der Sitzungen.<br><br>Diese Metrik unterscheidet sich von der Berichterstellung für gleichzeitige Betrachter im Abschnitt &quot;Berichte&quot;, der &quot;Gleichzeitige aktive Sitzungen&quot;verwendet. Durch die Verwendung von Einzelpersonen werden unerwünschte Spitzen an den Grenzen der Show entfernt (wobei Sitzungen gleichzeitig enden und beginnen). |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->


>[!MORELIKETHIS]
>
>[Erstellen eines Bedienfelds](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>[Bedienfeld &quot;Besuchszeit für Medienwiedergabe&quot;](media-playback-time-spent.md)
>[Mediendurchschnittl. Minute-Audience-Bereich](average-minute-audience-panel.md)
>