---
description: Grundlegendes zu den Funktionen von Echtzeit-Berichten in Customer Journey Analytics
title: Übersicht über das Echtzeit-Reporting
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 12fbb760-936d-4e30-958f-764febca5ae7
source-git-commit: 804668db5e104d1a1de7d5d9ce0c92a9bb1980dc
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 2%

---

# Übersicht über die Echtzeitberichterstellung

Echtzeitberichte in Customer Journey Analytics zeigen Daten und Visualisierungen in einem oder mehreren Bedienfeldern in Analysis Workspace in Echtzeit an und aktualisieren diese.

{{release-limited-testing}}

{{ultimate-package}}

## Anwendungsfälle

Dieser Abschnitt bietet einen Überblick über typische wertvolle und weniger wertvolle Anwendungsfälle. Und auch Informationen, wann Echtzeit-Reporting nicht in Betracht gezogen werden sollte.

* Die wertvollsten Anwendungsfälle für Echtzeit-Reporting sind große Verkäufe, Promotions oder Produkteinführungen.
Im Rahmen dieses Launches sollten Sie Folgendes wissen:

   * Wie hoch sind die Umsätze im Vergleich zu Ihrem letzten Verkauf?
   * Wie sieht dieser Produktstart im Vergleich zum letzten Produktstart aus?
   * Funktionieren Ihre Promotions für diesen wichtigen Tag oder Event tatsächlich?

* Relevante, aber weniger wertvolle Anwendungsfälle für das Echtzeit-Reporting sind Validierungs-Anwendungsfälle.
Sie möchten beispielsweise Folgendes überprüfen:

   * Funktioniert die Kampagnen-Journey, die Sie kürzlich gestartet haben?
   * Wenn Ihre neue Produktseite aktiviert wurde, erfassen Sie dann Kundendaten von der Seite?
   * Geht Ihr Live-Medienereignis in Ordnung?

Erwägen Sie keine Echtzeitberichte für Anwendungsfälle zur Betriebsüberwachung. Zum Beispiel, um die Frage zu beantworten, ob eine Site ordnungsgemäß funktioniert. Da der Umschalter [Echtzeit-Aktualisierung](use-real-time.md) nach 30 Minuten automatisch deaktiviert wird und der Echtzeitbericht nicht mehr aktualisiert wird, sollten Sie für diese Anwendungsfälle keinen Echtzeitbericht als zuverlässige Quelle verwenden.


## Latenzen

Die Art und Weise, wie Sie Daten erfassen, bestimmt die Echtzeit-Latenz von Echtzeit-Berichten für Customer Journey Analytics. Die folgende Abbildung und Tabelle zeigen ungefähre Latenzen für verschiedene Datenerfassungsszenarien bei der Verwendung von Echtzeit- und Standardberichten.

In der Abbildung wird auch hervorgehoben, dass das Echtzeit-Reporting einen konsolidierten Datensatz verwendet, der vollständig vom [konsolidierten (kombinierten) Datensatz) getrennt ](/help/connections/combined-dataset.md), der für das Standard-Reporting verwendet wird. Mit dem Umschalter [Echtzeit-Aktualisierung](use-real-time.md) können Sie zwischen folgenden Optionen wechseln:

* Echtzeitberichte zu einem konsolidierten Datensatz, der bis zu 24 Stunden rollierende Daten enthält.
* Standardberichte zum konsolidierten Datensatz, der bis zu 13 Monate rollierende Daten enthält (oder länger, falls Sie das Add-on für erweiterte Datenkapazität lizenziert haben).

![Echtzeit-Reporting](assets/real-time-reporting-latencies.svg){zoomable="yes"}

| | Datenerfassung | Echtzeit-Berichterstellungslatenz | Standard-Berichtslatenz |
|:---:|---|--:|--:|
| 1 | Edge Network SDK / APIs in Edge Network | &amp;ca; &lt; 00h:06m:30s | &amp;ca; &lt; 01h:35m:00s |
| 2 | Streaming-Connectoren | &amp;ca; &lt; 00h:16m:30s | &amp;ca; &lt; 01h:45m:00s |
| 3 | Adobe Analytics-Quell-Connector | &amp;ca; &lt; 00h:16m:30s | &amp;ca; &lt; 01h:45m:00s |
| 4 | Andere Quell-Connectoren in die Quell-Connectoren (einschließlich Batch-Daten) | &amp;ca; &lt; 24h:01m:30s | &amp;ca; &lt; 25h:30m:00s |

## Einschränkungen

Beachten Sie die folgenden Einschränkungen für das Echtzeit-Reporting:

* Echtzeitberichte berichten nur über Daten, die über einen rollierenden Zeitraum von 24 Stunden verfügbar sind. Daten, die mehr sind als   24 Stunden alt ist nicht für Echtzeit-Reporting verfügbar. Sobald die [Echtzeit-Aktualisierung](use-real-time.md) für einen Bericht deaktiviert oder automatisch deaktiviert wurde, sind alle relevanten Daten erneut aus dem [konsolidierten Datensatz“ verfügbar, ](/help/connections/combined-dataset.md) normalerweise für das Reporting in Customer Journey Analytics verwendet wird.
* Attribution, Segmentierung, berechnete Metriken und mehr arbeiten nur mit den Daten, die innerhalb des rollierenden Zeitraums von 24 Stunden verfügbar sind. Ein Segment *Besucher wiederholen* enthält beispielsweise nur sehr wenige Personen in einem Echtzeitbericht, da der Bericht nur Personen enthält, die in den letzten 24 Stunden mehrmals besucht haben. Eine ähnliche Einschränkung gilt, wenn Sie einen Echtzeitbericht über Personen erstellen, die zuvor auf eine Kampagne geklickt haben, die nicht mehr aktiv ist.
* Echtzeitberichte eignen sich am besten für Daten auf Ereignis- und Sitzungsebene. Bei der Verwendung von Echtzeitberichten für Daten auf Personenebene sollten Sie daher vorsichtig sein. <!--Need to explain this a bit better --> Da für Echtzeitberichte nur Ereignisse aus dem rollierenden 24-Stunden-Zeitraum verfügbar sind, ist der Ereignisverlauf einer Person auch auf dieses Fenster beschränkt. Berücksichtigen Sie bei der Auswahl einer Dimension und (berechneter) Metriken die Präferenz für Daten auf Ereignis- und Sitzungsebene. Und wenn Sie Funktionen wie Aufschlüsselungen, Nächstes oder Vorheriges und mehr in Ihrem Bedienfeld für die Echtzeit-Aktualisierung verwenden.
* Zuordnung und Echtzeitberichte können nicht kombiniert werden. <!-- Do we need to explain this in more detail, why? --> Echtzeit-Reporting bezieht sich auf Daten auf Ereignis- und Sitzungsebene und ist für personenbasierte Daten weniger relevant.
* Es sind keine von Heartbeat erfassten Medienmetriken verfügbar, mit Ausnahme von Medienstart- und Medienschlussmetriken. Sie können also weiterhin Echtzeitberichte verwenden, um einen Medienanwendungsfall zu ermöglichen.
* Wenn Sie die [Download- oder Exportoptionen](/help/analysis-workspace/export/download-send.md) verwenden, um ein Projekt herunterzuladen oder Daten aus einer Freiformtabelle zu exportieren, beachten Sie Folgendes:
   * Ein heruntergeladenes CSV-Projekt oder eine exportierte CSV-Datei enthält die zum Zeitpunkt des Herunterladens oder Exports verfügbaren Echtzeitdaten.
   * Ein heruntergeladenes PDF-Projekt enthält Nicht-Echtzeitdaten, ähnlich den Daten, die angezeigt werden, wenn die Echtzeit-Aktualisierung deaktiviert ist.
