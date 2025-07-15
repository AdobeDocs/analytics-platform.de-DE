---
description: Grundlegendes zu den Funktionen von Echtzeit-Berichten in Customer Journey Analytics
title: Übersicht über das Echtzeit-Reporting
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 12fbb760-936d-4e30-958f-764febca5ae7
source-git-commit: e7a7a297e303a410c73598f373219644e50ede74
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 1%

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

Erwägen Sie keine Echtzeitberichte für Anwendungsfälle zur Betriebsüberwachung. Um zum Beispiel die Frage zu beantworten: Funktioniert eine Site tatsächlich?


## Definition

Der Echtzeitaspekt des Echtzeit-Reportings für Customer Journey Analytics ist definiert als Daten und Visualisierungen, die innerhalb von etwa 5 Minuten nach dem Zeitpunkt aktualisiert werden, zu dem die zugrunde liegenden Daten über die zugehörige Verbindung aufgenommen werden.

## Einschränkungen

Beachten Sie die folgende Einschränkung für Echtzeit-Berichte:

* Echtzeitberichte berichten nur über Daten, die über einen rollierenden Zeitraum von 24 Stunden verfügbar sind. Daten, die diesen rollierenden 24-Stunden-Zeitraum überschreiten, sind nicht verfügbar.
* Attribution, Segmentierung, berechnete Metriken und mehr arbeiten nur mit den Daten, die innerhalb des rollierenden Zeitraums von 24 Stunden verfügbar sind.
* Echtzeitberichte eignen sich am besten für Daten auf Ereignis- und Sitzungsebene. Bei der Verwendung von Echtzeitberichten für Daten auf Personenebene sollten Sie daher vorsichtig sein. <!--Need to explain this a bit better --> Da für Echtzeitberichte nur Ereignisse aus dem rollierenden 24-Stunden-Zeitraum verfügbar sind, ist der Ereignisverlauf einer Person auch auf dieses Fenster beschränkt. Berücksichtigen Sie bei der Auswahl von Dimensionsmetriken (berechneten) die Präferenz für Daten auf Ereignis- und Sitzungsebene. Und wenn Sie Funktionen wie Aufschlüsselungen, Nächstes oder Vorheriges und mehr in Ihrem Bedienfeld für die Echtzeit-Aktualisierung verwenden.
* Zuordnung und Echtzeitberichte können nicht kombiniert werden. <!-- Do we need to explain this in more detail, why? --> wie bereits erwähnt, geht es beim Echtzeit-Reporting um Daten auf Ereignis- und Sitzungsebene und nicht so sehr um personenbasierte Daten.
* Es sind keine von Heartbeat erfassten Medienmetriken verfügbar, mit Ausnahme der Metriken „Medienstart“ und „Medienabschluss“. So können Sie weiterhin Echtzeitberichte verwenden, um einen Medienanwendungsfall zu aktivieren.
