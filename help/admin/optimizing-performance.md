---
description: Faktoren, die sich auf die Leistung und Optimierung von Customer Journey Analytics und Workspace auswirken
title: Optimieren der Customer Journey Analytics- und Analysis Workspace-Leistung
feature: FAQ
exl-id: ad00e476-6f19-462b-ba53-d72ddd949802
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1980'
ht-degree: 70%

---

# Customer Journey Analytics optimieren und [!UICONTROL Analysis Workspace] Leistung

Verschiedene Faktoren können die Gesamtleistung des Customer Journey Analytics sowie die Leistung eines Projekts in Analysis Workspace beeinflussen. In Workspace erhalten Sie möglicherweise eine Fehlermeldung mit der folgenden Meldung:

`This query is too complex. Please review best practices for building Analysis Workspace queries.`

Diese Best Practices besprechen, welche Faktoren zu diesem Fehler führen können und wie der Bericht/das Projekt vereinfacht wird.

## Abfragefaktoren {#query}

Dies sind die häufigsten Abfragefaktoren, die die Customer Journey Analytics-Gesamtleistung beeinflussen:

| Faktor | Definition | Beeinflusst durch | Optimierung |
| --- | --- | --- | --- |
| **Anzahl der Freiformzeilen und -spalten** | Die Gesamtzahl der Freiform-Tabellenzellen im Projekt, berechnet durch Zeilen * Spalten in allen Tabellen. Schließt verborgene Datenquellen aus. Die Richtlinie ist 4000. | | Reduzieren Sie die Anzahl der Spalten in Ihrer Tabelle auf die relevantesten Datenpunkte. Reduzieren Sie die Anzahl der Zeilen in Ihrer Tabelle, indem Sie die Anzahl der angezeigten Zeilen anpassen oder einen Tabellenfilter oder einen Filter anwenden. |
| **Verwendete Komponenten** | Die Gesamtzahl der im Projekt verwendeten Komponenten. Die Richtlinie ist 100. | Die Anzahl der verwendeten Komponenten hat keinen direkten Einfluss auf die Leistung. Die Komplexität dieser Komponenten wird jedoch zur Leistung des Projekts beitragen. Siehe Optimierungen im Abschnitt &quot;Weitere Faktoren&quot;unten. |
| **Längster Datumsbereich** | Dieser Faktor zeigt den längsten Datumsbereich an, der für das Projekt verwendet wurde. Die Richtlinie ist ein Jahr. |  | Rufen Sie möglichst nicht mehr Daten ab, als Sie benötigen. Schränken Sie den Kalender des Bedienfelds auf die relevanten Daten für Ihre Analyse ein oder verwenden Sie Datumsbereichskomponenten (violette Komponenten) in Ihren Freiform-Tabellen. In einer Tabelle verwendete Datumsbereiche überschreiben den Datumsbereich des Bedienfelds. Beispielsweise können Sie den Tabellenspalten „Letzter Monat“, „Letzte Woche“ und „Gestern“ hinzufügen, um diese spezifischen Datenbereiche anzufordern. Weitere Informationen zu Datumsbereichen in Analysis Workspace erhalten Sie in [diesem Video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/date-ranges-and-calendar-in-analysis-workspace.html?lang=de). <br><br>Minimieren Sie außerdem die Anzahl der im Projekt verwendeten Jahresvergleiche. Bei der Berechnung eines Jahresvergleichs werden die gesamten 13 Monate von Daten zwischen den betrachteten Monaten berücksichtigt. Dies hat die gleiche Auswirkung wie die Änderung des Datumsbereichs des Bedienfelds auf 13 Monate. |
| **Filterkomplexität** | Komplizierte Filter können einen erheblichen Einfluss auf die Projektleistung haben. | Zu den Faktoren, die einem Filter Komplexität verleihen (in der Reihenfolge absteigender Auswirkungen), gehören: <ul><li>Operatoren „enthält“, „enthält beliebige von“, „stimmt überein mit“, „beginnt mit“ oder „endet mit“ </li><li>Sequenzielle Filterung, insbesondere bei Verwendung von Dimensionsbeschränkungen (In/Nach) </li><li>Anzahl der eindeutigen Dimensionselemente innerhalb der Dimensionen, die im Filter verwendet werden (z. B.: Seite = &#39;A&#39;, wenn Seite 10 eindeutige Elemente hat, ist schneller als Seite = &#39;A&#39;, wenn Seite 100.000 eindeutige Elemente hat) </li><li>Anzahl der verschiedenen verwendeten Dimensionen (z. B. Seite = &quot;Startseite&quot;und Seite = &quot;Suchergebnisse&quot;ist schneller als eVar 1 = &quot;rot&quot;und eVar 2 = &quot;blau&quot;)</li><li>Viele OR-Operatoren (anstelle von AND)</li><li>Verschachtelte Container, die sich im Umfang unterscheiden (z. B. &quot;Ereignis&quot;innerhalb von &quot;Sitzung&quot;innerhalb von &quot;Person&quot;)</li></ul> | Während einige der Komplexitätsfaktoren nicht verhindert werden können, sollten Sie nach Möglichkeiten suchen, die Komplexität Ihrer Filter zu verringern. Generell gilt: Je genauer Sie mit Ihren Filterkriterien umgehen, desto besser. Beispiel:<ul><li>Bei Containern ist die Verwendung eines einzelnen Containers am Anfang des Filters schneller als eine Reihe verschachtelter Container.</li><li>Bei Operatoren ist &quot;ist gleich&quot;schneller als &quot;enthält&quot;und &quot;entspricht einem von&quot;ist schneller als &quot;enthält beliebige von&quot;.</li><li>Bei vielen Kriterien sind AND-Operatoren schneller als eine Reihe von OR-Operatoren.</li></ul> Suchen Sie nach Möglichkeiten, viele OR-Anweisungen in eine einzelne Anweisung &quot;entspricht einem von&quot;zu reduzieren.<br> |
| **Komplexität der Visualisierung** (Filter, Metriken, Filter) | Die Art der Visualisierung (z. B. Fallout oder Freiformtabelle), die einem Projekt hinzugefügt wird, beeinflusst die Projektleistung allein nicht sonderlich. Die Verarbeitungszeit wird durch die Komplexität der Visualisierung gesteigert. | U. a. machen folgende Faktoren eine Visualisierung komplexer:<ul><li>Angeforderter Datenbereich</li><li>Anzahl der angewandten Filter, z. B. als Zeilen verwendete Filter in einer Freiformtabelle</li><li>Verwendung von komplexen Filtern</li><li>[Statische Element](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) zeilen oder Spalten in Freiformtabellen</li><li>Auf Zeilen angewandte Filter in Freiformtabellen</li><li>Anzahl verwendeter Metriken, insbesondere berechneter Metriken, die Filter verwenden</li></ul> |
| **Rechenzentrumskapazität** | Die Reporting-Kapazitäten, die Sie und andere Kunden in einem Rechenzentrum von Adobe gemeinsam nutzen. | Dies wird durch die Anzahl gleichzeitiger Abfragen von Ihrer Organisation und anderen Unternehmen innerhalb Ihres Rechenzentrums beeinflusst. | Ihre Organisation hat Anspruch auf eine bestimmte Kapazität. Ist das System nur wenig ausgelastet, überträgt Adobe mehr Kapazität auf Sie, auch über das Ihnen zustehende Maß hinaus. |
| **Anzahl der gleichzeitigen Abfragen** | Die Anzahl der Abfragen, die von Ihrem Unternehmen gleichzeitig angefordert werden. Jede Organisation hat Anspruch auf mindestens fünf gleichzeitige Abfragen. Wenn ein Bericht lange dauert, liegt dies in der Regel daran, dass er sich in einer Warteschlange mit anderen Berichten befindet. Das bedeutet, dass Ihr Unternehmen versucht, viele gleichzeitige Anfragen für eine bestimmte Datenansicht auszuführen. | Abfragen können von API-Anfragen, Reporting-Benutzeroberflächen (Analysis Workspace, Report Builder usw.), geplanten Projekten, terminierten Warnhinweisen und gleichzeitigen Benutzern, die Berichterstellungsanfragen ausführen, stammen. | Verteilen Sie Ihre Anforderungen und Zeitpläne für die Datenansicht gleichmäßig über den Tag. Verlagern Sie außerdem Ihre Anforderungen nach Möglichkeit auf Nebenzeiten. Montagmorgen, Dienstagmorgen und der erste Tag eines Monats sind Spitzenzeiten für das Reporting. |
| **Verbindungsgröße** | Die Menge der in Ihrer Verbindung erfassten Daten. |  | Wenden Sie sich an Ihr Implementierungsteam oder Ihren Customer Journey Analytics-Experte, um festzustellen, ob es Verbesserungen bei der Implementierung gibt, die zur Verbesserung des Gesamterlebnisses bei Customer Journey Analytics vorgenommen werden können. |
| **Komplexität der Dimensionseinstellungen** | Hochkomplexe Dimensionen können sich erheblich auf die Projektleistung auswirken, insbesondere Dimensionen oder Metriken, die auf komplexen benutzerdefinierten Feldern basieren. | | Reduzieren Sie die Anzahl der benutzerdefinierten Felder oder erstellen Sie separate Dimensionen. |
| **Dimensionen mit vielen eindeutigen Werten** | Diese Dimensionen, die auch als Dimensionen mit hoher Kardinalität bezeichnet werden, können sich auf die Berichterstellungsleistung auswirken. | Siehe [Dimensionen mit hoher Kardinalität](/help/components/dimensions/high-cardinality.md) | Siehe [Dimensionen mit hoher Kardinalität](/help/components/dimensions/high-cardinality.md) |

## [!UICONTROL Hilfe] > [!UICONTROL Leistung] in Analysis Workspace

Mehrere Faktoren können die Leistung eines Projekts in Analysis Workspace beeinflussen. Damit Sie Ihr Projekt optimal planen und erstellen können, sollten Sie vor Beginn diese Faktoren kennen. Dieser Abschnitt enthält eine Liste von Faktoren, die sich auf die Leistung und die Optimierungen auswirken, die Sie durchführen können, um die Spitzenleistung in Analysis Workspace sicherzustellen.

Unter **Analysis Workspace > [!UICONTROL Hilfe] > [!UICONTROL Leistung]** können Sie die Faktoren sehen, die sich auf die Leistung Ihres Projekts auswirken, einschließlich Netzwerk-, Browser- und Projektfaktoren. Um möglichst genaue Ergebnisse zu erzielen, müssen Sie das Projekt vor dem Öffnen der Seite „Leistung“ vollständig laden.

* In der Spalte „Aktuelles Projekt“ werden die Ergebnisse für Ihr aktuelles Projekt und Ihre Umgebung angezeigt.
* In der Spalte „Richtlinie“ wird der von Adobe empfohlene Schwellenwert für jeden Faktor angezeigt.

Darüber hinaus können Sie die Leistungsinhalte **als CSV-Datei herunterladen**, um sie einfach mit der Adobe-Kundenunterstützung oder Ihren IT-Teams zu teilen.

>[!NOTE]
>
>Die Informationen auf der Seite „Leistung“ variieren bei jedem Öffnen des Modells, da sich Faktoren ändern können. Darüber hinaus verfeinert Adobe die bereitgestellten Richtlinien weiter, sobald mehr Daten verfügbar sind.

![Analysis Workspace-Leistung, die den Netzwerkfaktor, das aktuelle Projekt und die Richtlinie anzeigt.](assets/performance-modal.png)

### Netzwerkfaktoren

[!UICONTROL Hilfe] > [!UICONTROL Leistungsnetzwerkfaktoren] beinhalten:

| Faktor | Definition | Beeinflusst durch | Optimierung |
| --- | --- | --- | --- |
| **Verbindung zu Adobe** | Adobe sendet 10 Testaufrufe, wenn die Leistungsseite geöffnet wird. Dies stellt den Prozentsatz der erfolgreichen Aufrufe zu Adobe dar. | Lokale Netzwerkprobleme oder Probleme mit der Adobe wirken sich auf diesen Faktor aus. | Überprüfen Sie status.adobe.com, ob bekannte Service-Probleme vorliegen. Überprüfen Sie dann Ihre lokale Netzwerkverbindung. |
| **Internetbandbreite** | Nur für Google Chrome verfügbar. Schätzung der Bandbreite Ihres Browsers an Ihrem Standort. Die Richtlinie ist 2,0 MB/s. | Ihre lokale Netzwerkverbindung wirkt sich auf diesen Faktor aus. | Überprüfen Sie die lokale Netzwerkverbindung. |
| **Internetlatenz** | Adobe sendet 10 Testaufrufe, wenn die Leistungsseite geöffnet wird. Dies stellt die Zeitdauer dar, die durchschnittlich eine Anfrage an Adobe und deren Antwort benötigt. Einfach gesagt, es ist ein Maß dafür, wie schnell das Internet zwischen Ihrem Standort und Adobe ist. Die Richtlinie ist &lt; 1 Sekunde. | Lokale Netzwerkprobleme, viele offene Browser-Registerkarten oder Probleme bei Adobe wirken sich auf diesen Faktor aus. | Überprüfen Sie status.adobe.com, ob bekannte Service-Probleme vorliegen. Überprüfen Sie dann Ihre lokale Netzwerkverbindung und schließen Sie nicht verwendete Browser-Registerkarten. |

### Browser-Faktoren

[!UICONTROL Hilfe] > [!UICONTROL Leistungs-Browser-Faktoren] beinhalten:

| Faktor | Definition | Beeinflusst durch | Optimierung |
| --- | --- | --- | --- |
| **Berechnungsgeschwindigkeit** | Wie schnell Ihr Computer einen Verarbeitungstest durchführt. Die Richtlinie ist &lt; 750 ms. | Ihre Hardware sowie gleichzeitige Programme wirken sich auf diesen Faktor aus. | Öffnen Sie den Task Manager (PC) oder Activity Monitor (Mac) Ihres Computers, um festzustellen, ob Programme geschlossen werden können. Schließen Sie dann nicht verwendete Browser-Registerkarten oder andere Programme. <br><br>Wenn diese Aktionen nicht hilfreich sind, besprechen Sie Hardware-Details mit Ihrem IT-Team. |
| **Verwendeter Speicher** | Nur für Google Chrome verfügbar. Jede Workspace-Registerkarte in einem Google Chrome-Browser verwendet insgesamt 4 GB Arbeitsspeicher. Dies entspricht dem Prozentsatz des Speicherlimits, das vom aktuellen Projekt belegt wird. Die Richtlinie ist 3.500 MB. Dies ist der Punkt, ab dem Workspace Speicherfehler zurückgibt. | Das Arbeiten mit mehreren Registerkarten oder das Herunterladen von 50.000 Zeilen mit Daten bedeutet eine höhere Speicherbelegung. | Wenn Sie einen Speicherfehler erhalten, schließen Sie andere Workspace-Registerkarten und/oder führen Sie 50.000 Zeilen-Downloads einzeln durch. |
| **Lokaler Speicher verwendet** | Daten, die lokal auf Ihrem Computer zur Verwendung im Browser gespeichert werden. Jede Herkunft (z. B. experience.adobe.com) verfügt über ein Limit von 10 MB. | Analysis Workspace verwendet lokale Datenspeicherung für verschiedene Funktionen, unter anderem zum Speichern automatisch gespeicherter (vorhandener) Projekte, Benutzereinstellungen und Feature Flags. | Um sicherzustellen, dass Analysis Workspace-Funktionen nicht gestört werden, sollten Sie die lokale Datenspeicherung für die Domain „experience.adobe.com“ löschen. |
| **Rendergeschwindigkeit** | FPS steht für Frames pro Sekunde, d. h., wie oft der Browser die Seite auf Ihrem Bildschirm zeichnet. 24 FPS sind häufig das, was das menschliche Auge als Bewegung wahrnimmt. Wenn der FPS-Wert niedriger ist, treten in Workspace Rendering-Probleme auf. | Der FPS-Wert wird durch das gleichzeitige Bearbeiten vieler Workspace-Projekte auf einmal und die Größe des angezeigten Projekts beeinflusst. Andere auf Ihrem Computer ausgeführte Programme können Auswirkungen haben, wie Streaming, Hintergrund-Scanner usw. Darüber hinaus wirkt sich Ihre Hardware auf diesen Faktor aus. | Öffnen Sie den Task Manager (PC) oder Activity Monitor (Mac) Ihres Computers, um festzustellen, ob Programme geschlossen werden können. Schließen Sie dann nicht verwendete Browser-Registerkarten oder andere Programme. <br><br>Wenn diese Aktionen nicht hilfreich sind, besprechen Sie Hardware-Details mit Ihrem IT-Team. |

### Projektfaktoren

[!UICONTROL Hilfe] > [!UICONTROL Leistungsprojektfaktoren] beinhalten:

| Faktor | Definition | Optimierung |
| --- | --- | --- |
| **Anzahl der Abfragen** | Die Gesamtzahl der Abfragen (Anfragen) an Adobe, die zum Abrufen der im Projekt angezeigten Daten vorgenommen wurden. Zu den Abfragen gehören Ranganfragen für Tabellen, Anomalieerkennung, Wortgrafiken, Komponenten in der linken Leiste und mehr. Schließt ausgeblendete Bedienfelder und Visualisierungen aus. Die Richtlinie ist 100. | Vereinfachen Sie Ihr Projekt nach Möglichkeit, indem Sie Daten in verschiedene Projekte aufteilen, die einem bestimmten Zweck oder Interessenten dienen. Verwenden Sie Tags, um Projekte in Themen zu organisieren, und verwenden Sie [direkte Verknüpfungen](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=de), um ein internes Inhaltsverzeichnis zu erstellen, damit die Interessierte leichter finden können, wonach sie suchen. |
| **Erweiterte Bedienfelder (von der Gesamtzahl der Bedienfelder)** | Die Anzahl der erweiterten Bedienfelder von der Gesamtzahl der Bedienfelder im Projekt. Die Richtlinie ist 5. | Nachdem Sie Schritte zur Vereinfachung des Projekts unternommen haben, reduzieren Sie die Bedienfelder im Projekt, die beim Laden nicht angezeigt werden müssen. Wenn das Projekt geöffnet wird, werden nur erweiterte Bedienfelder verarbeitet. Reduzierte Felder werden erst verarbeitet, wenn der Nutzer sie erweitert. |
| **Erweiterte Visualisierungen (aus der Gesamtzahl der Visualisierungen)** | Die Anzahl der erweiterten Tabellen und Visualisierungen aus der Gesamtsumme im Projekt, einschließlich der ausgeblendeten Datenquellen. Die Richtlinie ist 15. | Nachdem Sie Schritte zur Vereinfachung des Projekts unternommen haben, reduzieren Sie die Visualisierungen in Ihrem Projekt, die beim Laden nicht angezeigt werden müssen. Priorisieren Sie die Visuals, die für den Verbraucher des Berichts am wichtigsten sind, und teilen Sie die unterstützenden Visuals bei Bedarf in ein separates, detaillierteres Bedienfeld oder Projekt auf. |
| **Anzahl der Freiformzellen** | Siehe Tabelle &quot;Abfragefaktoren&quot;oben. | |
| **Verwendete Komponenten** | Siehe Tabelle &quot;Abfragefaktoren&quot;oben. | |
| **Längster Datumsbereich** | Siehe Tabelle &quot;Abfragefaktoren&quot;oben. | |
