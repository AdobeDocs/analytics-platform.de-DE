---
description: Grundlegendes zu den Funktionen von Echtzeit-Berichten in Customer Journey Analytics
title: Übersicht über das Echtzeit-Reporting
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 12fbb760-936d-4e30-958f-764febca5ae7
source-git-commit: b833914e7066fa660f856737d6b8a6392aae2feb
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 3%

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


## Definition

Der Echtzeitaspekt des Echtzeit-Reportings für Customer Journey Analytics ist definiert als Daten und Visualisierungen, die innerhalb von etwa 6,5 Minuten ab dem Zeitpunkt aktualisiert werden, zu dem die zugrunde liegenden Daten über die zugehörige Verbindung aufgenommen werden.

Verschiedene Komponenten bei der Einrichtung Ihrer Datenerfassung bestimmen die Echtzeit-Berichterstellungslatenz.

![Echtzeit-Reporting](assets/real-time-reporting-latencies.svg){zoomable="yes"}

| | Beschreibung | Latenz |
|:---:|---|--:|
| 1 | Daten, die über Edge Network SDK/APIs in Edge Network erfasst werden. | &lt; 500 Millisekunden |
| 2 | Daten, die von Edge Network in den Datenerfassungs- und Validierungs-Service in Experience Platform Hub repliziert wurden. | &lt; 5 Minuten |
| 3 | Daten, die über Streaming-Connectoren in den Datenerfassungs- und Validierungs-Service in Experience Platform Hub erfasst werden. | &lt; 15 Minuten |
| 4 | Daten, die über Adobe Analytics erfasst und vom Analytics-Quell-Connector an den Quell-Connector-Prozessor im Experience Platform Hub weitergeleitet werden. | &lt; 15 Minuten |
| 5 | Daten, die über andere Quell-Connectoren im Quell-Connector-Prozessor in Experience Platform Hub erfasst werden. | &lt; 24 Stunden |
| 6 | Vom Echtzeit-Prozessor verarbeitete Daten für einen konsolidierten Datensatz für Echtzeit-Reporting. | &lt; 90 Sekunden |

## Einschränkungen

Beachten Sie die folgenden Einschränkungen für das Echtzeit-Reporting:

* Echtzeitberichte berichten nur über Daten, die über einen rollierenden Zeitraum von 24 Stunden verfügbar sind. Daten, die diesen rollierenden 24-Stunden-Zeitraum überschreiten, werden für Echtzeit-Berichte ausgeblendet. Sobald die [Echtzeit-Aktualisierung](use-real-time.md) für einen Bericht deaktiviert oder automatisch deaktiviert wurde, sind alle relevanten Daten für einen Bericht wieder verfügbar.
* Attribution, Segmentierung, berechnete Metriken und mehr arbeiten nur mit den Daten, die innerhalb des rollierenden Zeitraums von 24 Stunden verfügbar sind.
* Echtzeitberichte eignen sich am besten für Daten auf Ereignis- und Sitzungsebene. Bei der Verwendung von Echtzeitberichten für Daten auf Personenebene sollten Sie daher vorsichtig sein. <!--Need to explain this a bit better --> Da für Echtzeitberichte nur Ereignisse aus dem rollierenden 24-Stunden-Zeitraum verfügbar sind, ist der Ereignisverlauf einer Person auch auf dieses Fenster beschränkt. Berücksichtigen Sie bei der Auswahl einer Dimension und (berechneter) Metriken die Präferenz für Daten auf Ereignis- und Sitzungsebene. Und wenn Sie Funktionen wie Aufschlüsselungen, Nächstes oder Vorheriges und mehr in Ihrem Bedienfeld für die Echtzeit-Aktualisierung verwenden.
* Zuordnung und Echtzeitberichte können nicht kombiniert werden. <!-- Do we need to explain this in more detail, why? --> Echtzeit-Reporting bezieht sich auf Daten auf Ereignis- und Sitzungsebene und ist für personenbasierte Daten weniger relevant.
* Es sind keine von Heartbeat erfassten Medienmetriken verfügbar, mit Ausnahme von Medienstart- und Medienschlussmetriken. Sie können also weiterhin Echtzeitberichte verwenden, um einen Medienanwendungsfall zu ermöglichen.
* Wenn Sie die [Download- oder Exportoptionen](/help/analysis-workspace/export/download-send.md) verwenden, um ein Projekt herunterzuladen oder Daten aus einer Freiformtabelle zu exportieren, beachten Sie Folgendes:
   * Ein heruntergeladenes CSV-Projekt oder eine exportierte CSV-Datei enthält die zum Zeitpunkt des Herunterladens oder Exports verfügbaren Echtzeitdaten.
   * Ein heruntergeladenes PDF-Projekt enthält Nicht-Echtzeitdaten, ähnlich den Daten, die angezeigt werden, wenn die Echtzeit-Aktualisierung deaktiviert ist.
