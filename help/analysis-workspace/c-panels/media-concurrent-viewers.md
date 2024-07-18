---
title: Bedienfeld „Gleichzeitige Medienbetrachter“
description: Verwendung und Interpretation des Bedienfelds „Gleichzeitige Medienbetrachter“ in Analysis Workspace.
feature: Panels
exl-id: a442fb9c-165f-4136-95e2-ce92b9280c25
role: User
source-git-commit: e4d4ff530d28e692301ca0671e055a164b9f7035
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 75%

---

# Bedienfeld „Gleichzeitige Medienbetrachter“

Sie können gleichzeitig Betrachtende analysieren, um zu verstehen, wo Spitzenzeiten mit gleichzeitigen Ansichten auftraten oder wo es zu Abbrüchen kam. So erhalten Sie wertvolle Einblicke in die Qualität von Inhalten und die Interaktion mit Betrachtern, die bei der Fehlerbehebung, Planung von Volumen oder Skalierung helfen können.

In Analysis Workspace bezeichnet der Begriff &quot;Gleichzeitige Betrachter&quot;die Anzahl der Einzelanwender, die Ihre Medienstreams unabhängig von der Anzahl der Sitzungen zu einem bestimmten Zeitpunkt anzeigen.

Das Bedienfeld „Gleichzeitige Medienbetrachter“ ermöglicht die Analyse von gleichzeitigen Betrachtern im Zeitverlauf mit Details zu Spitzenzeiten des gleichzeitigen Betrachtens und der Möglichkeit, Unterteilungen und Vergleiche vorzunehmen. Um auf das Bedienfeld &quot;Gleichzeitige Medienbetrachter&quot;zuzugreifen, navigieren Sie über das Add-on für Streaming-Mediensammlung zu einer Datenansicht mit aktivierten Komponenten. Klicken Sie dann auf das Panel-Symbol ganz links und ziehen Sie das Panel in Ihr Analysis Workspace-Projekt.

Im Folgenden finden Sie eine Videoübersicht zu diesem Panel:

>[!VIDEO](https://video.tv.adobe.com/v/330177/?quality=12)

## Panel-Eingaben {#Input}

Sie können das Bedienfeld „Gleichzeitige Medienbetrachter“ mithilfe der folgenden Eingabeeinstellungen konfigurieren:

| Einstellung | Beschreibung |
|---|---|
| Datumsbereich der Bedienfelder | Der Datumsbereich des Panels ist standardmäßig „Heute“.  Sie können ihn so verändern, dass Sie einen einzelnen Tag oder viele Monate auf einmal betrachten können. <br> <br>Diese Visualisierung ist auf 1440 Datenzeilen beschränkt (z. B. 24 Stunden bei einer Granularität auf Minutenebene).  Wenn eine Kombination aus Datumsbereich und Granularität zu mehr als 1440 Zeilen führt, wird die Granularität automatisch reduziert, um den vollständigen Datumsbereich zu erlauben. |
| Granularität | Die Standardeinstellung für die Granularität ist „Minute“. <br> <br>Diese Visualisierung ist auf 1440 Datenzeilen beschränkt (z. B. 24 Stunden bei einer Granularität auf Minutenebene).  Wenn eine Kombination aus Datumsbereich und Granularität zu mehr als 1440 Zeilen führt, wird die Granularität automatisch reduziert, um den vollständigen Datumsbereich zu erlauben. |
| Zusammenfassende Zahlen der Bedienfelder | Um Details zu Datum und Uhrzeit für gleichzeitige Betrachter anzuzeigen, steht eine Zusammenfassungsnummer zur Verfügung. Das Maximum zeigt Details zu Spitzenzeiten von gleichzeitigen Aufrufen an. Das Minimum zeigt Details zum Tiefpunkt an.  Die Standardeinstellung im Bedienfeld zeigt nur das Maximum an, Sie können diese Einstellung jedoch ändern, um nur das Minimum oder sowohl Maximum als auch Minimum anzuzeigen.<br><br>Wenn Sie Aufschlüsselungen verwenden, wird jeweils eine Zusammenfassungsnummer angezeigt. |
| Serienaufschlüsselung | Optional können Sie Ihre Visualisierung nach Filtern, Dimensionen, Dimensionselementen oder Datumsbereichen aufschlüsseln. <br><br>– Sie können bis zu 10 Zeilen auf einmal ansehen. Aufschlüsselungen sind auf eine einzelne Ebene beschränkt.<br><br>– Beim Ziehen einer Dimension werden die oberen Dimensionselemente automatisch anhand des im Bedienfelds ausgewählten Datumsbereichs ausgewählt.<br><br>– Ziehen Sie zum Vergleichen von Datumsbereichen zwei oder mehr Datumsbereiche in den Filter für die Aufschlüsselung der Serie. |

### Standardansicht

![Die Standardansicht der gleichzeitigen Medienbetrachter.](assets/concurrent-viewers-default.png)


### Serienaufschlüsselungsansicht

![Die Aufschlüsselungsansicht der Serie &quot;Gleichzeitige Medienbetrachter&quot;mit 7 von 10 Dimensionen, Segmenten oder Datumsbereichen.](assets/concurrent-viewers-series-breakdown.png)

## Panel-Ausgabe {#Output}

Das Bedienfeld „Gleichzeitige Medienbetrachter“ gibt ein Liniendiagramm und Zusammenfassungsnummern zurück, die Details zu maximalen und/oder minimalen gleichzeitigen Betrachtern enthalten.  Oben im Bedienfeld wird eine Zusammenfassungszeile angezeigt, die Sie an die ausgewählten Bedienfeldeinstellungen erinnert.

Sie können das Bedienfeld jederzeit bearbeiten oder erneut erstellen, indem Sie oben rechts auf den Stift zum Bearbeiten klicken.

Wenn Sie Serienaufschlüsselung ausgewählt haben, wird für jeden der folgenden Punkte eine Zeile im Liniendiagramm und eine Zusammenfassungsnummer angezeigt:

![ Die Ausgabe der gleichzeitigen Medienbetrachter.](assets/concurrent-viewers-output.png)

### Datenquelle

Die einzige Metrik, die in diesem Bedienfeld verwendet werden kann, ist „Gleichzeitige Betrachter“:

| Metrik | Beschreibung |
|---|---|
| Gleichzeitige Betrachter | Anzahl der individuellen Personen, die Ihre Medien-Streams zu einem bestimmten Zeitpunkt anzeigen, unabhängig von der Anzahl der Sitzungen.<br><br>Dies unterscheidet sich vom Bericht „Gleichzeitige Betrachter“ im Bereich „Berichte“, wo die gleichzeitigen aktiven Sitzungen zugrunde gelegt werden.  Die Verwendung von Einzelpersonen ermöglicht die Entfernung unerwünschter &quot;Spitzen&quot;an Show-Grenzen (wenn Sitzungen gleichzeitig enden und beginnen). |

Eine Freiformtabelle ist in dieser Ansicht nicht verfügbar.  Zur Ansicht der Datenquelle können Sie mit der rechten Maustaste auf das Liniendiagramm klicken und es als csv-Datei herunterladen.  Serienaufschlüsselungen werden einbezogen.


![Die Ausgabeoptionen der gleichzeitigen Viewer mit &quot;Daten als CSV herunterladen&quot;sind hervorgehoben.](assets/concurrent-viewers-download-csv.png)

## Häufig gestellte Fragen (FAQ) {#FAQ}

| Frage | Antwort |
|---|---|
| Wo ist die Freiformtabelle? Wie kann ich die Datenquelle anzeigen? | Die Freiformtabelle ist in dieser Ansicht nicht verfügbar.  Sie können die Datenquelle herunterladen, indem Sie mit der rechten Maustaste auf das Liniendiagramm klicken und die CSV-Datei herunterladen. |
| Warum hat sich meine Granularität verändert? | Diese Visualisierung ist auf 1440 Datenzeilen beschränkt (z. B. 24 Stunden bei einer Granularität auf Minutenebene).  Wenn eine Kombination aus Datumsbereich und Granularität zu mehr als 1440 Zeilen führt, wird die Granularität automatisch aktualisiert, um den vollständigen Datumsbereich aufzunehmen.<br><br>Wenn Sie von einem größeren auf einen kleineren Datumsbereich wechseln, wird die Granularität auf das niedrigste zulässige Detail aktualisiert, sobald der Datumsbereich geändert wird. Um eine höhere Granularität zu sehen, bearbeiten Sie das Bedienfeld und erstellen Sie es erneut. |
| Wie vergleiche ich Videonamen, Filter, Inhaltstypen usw. | Um diese in einer einzigen Visualisierung zu vergleichen, ziehen Sie Filter, Dimensionen oder bestimmte Dimensionselemente in den Filter für die Serienaufschlüsselung.<br><br>Die Ansicht ist auf 10 Aufschlüsselungen beschränkt.  Um mehr als 10 ansehen zu können, müssen Sie mehrere Bedienfelder verwenden. |
| Wie vergleiche ich Datumsbereiche? | Um Datumsbereiche in einer einzigen Visualisierung zu vergleichen, verwenden Sie die Serienaufschlüsselungen, indem Sie zwei oder mehr Datumsbereiche in das Panel ziehen.  Diese Datumsbereiche setzen den Datumsbereich des Bedienfelds außer Kraft. |
| Wie ändere ich den Visualisierungstyp? | Dieses Bedienfeld ermöglicht nur die Linienvisualisierung für die Zeitreihen. |
| Kann ich die Anomalieerkennung ausführen? | Nein.  Die Anomalieerkennung ist für dieses Panel nicht verfügbar. |
| Warum sollten Sie eindeutige Personen anstelle aktiver Sitzungen verwenden? | Die Verwendung von Einzelpersonen ermöglicht die Entfernung unerwünschter Spitzen an Vorstellungsgrenzen (wobei Sitzungen gleichzeitig enden und beginnen). |
| Was bedeutet es, parallele Betrachter mit einer Granularität von mehr als einer Minute zu haben? | Bei einer Granularität von mehr als einer Minute stellen gleichzeitige Betrachter die Summe der gleichzeitigen Unique Viewers für alle Minuten innerhalb dieses Zeitraums dar. Beispielsweise ist die Granularität gleichzeitiger Betrachter auf Stundenebene die Summe der gleichzeitigen Unique Viewers für alle Minuten innerhalb der Stunde. |
| Zeigt das Arbeitsbereich-Bedienfeld dieselben Informationen wie der Bericht zu gleichzeitigen Betrachtern? | Nein.  In Analysis Workspace ist &quot;Gleichzeitige Betrachter&quot;definiert als die Anzahl der Einzelanwender, die Ihren Medienstream zu einem bestimmten Zeitpunkt anzeigen, unabhängig von der Anzahl der Sitzungen.<br><br>Dies unterscheidet sich vom Bericht „Gleichzeitige Betrachter“ im Bereich „Berichte“, wo die gleichzeitigen aktiven Sitzungen zugrunde gelegt werden.  Die Verwendung von Einzelpersonen ermöglicht die Entfernung unerwünschter Spitzen an den Grenzen der Show, an denen Sitzungen gleichzeitig enden und beginnen. |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->
