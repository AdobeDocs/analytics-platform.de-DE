---
title: Datenerfassung in Content Analytics
description: Ein Überblick darüber, wie Daten in Content Analytics erfasst werden
solution: Customer Journey Analytics
feature: Content Analytics
hide: true
hidefromtoc: true
role: Admin
source-git-commit: d835411beba3d40f67d2f93ee76aa5eda6f45041
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 1%

---


# Datenerfassung in Content Analytics

In diesem Artikel wird detailliert erläutert, wie Content Analytics Daten erfasst


## Definitionen

Im Zusammenhang mit diesem Artikel werden die folgenden Definitionen verwendet:

* **Erlebnis**: Ein Erlebnis wird als Textinhalt auf einer gesamten Web-Seite definiert. Für die Datenerfassung zeichnet Content Analytics die Erlebnis-ID auf. Content Analytics zeichnet den Text nicht auf.
* **Asset**: Ein Bild. Content Analytics zeichnet die Asset-URL auf.
* **Relevante URL**: Die Basis-URL plus alle Parameter, die den Inhalt auf der Seite steuern.
* **Erlebnis-**: Eine eindeutige Kombination aus relevanter URL und Erlebnisversion.
   * Sie geben als Teil der [Konfiguration](configuration.md) an, welche Parameter für eine bestimmte vollständige URL relevant sind.
   * Sie können die [Versionskennung](manual.md#versioning) definieren, die verwendet wird. Bei der Datenerfassung wird die Version nicht berücksichtigt. Es wird nur die relevante URL erfasst.

## Funktionalität

Die Content Analytics-Bibliothek erfasst Daten, wenn:

* Content Analytics ist in der Tag-Bibliothek enthalten, die auf der Seite geladen wird.
* Die Seiten-URL wird in der [Content Analytics-Erweiterung](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"} konfiguriert, die Teil der enthaltenen Tag-Bibliothek ist.


### Content Analytics-Ereignis

Ein Content Analytics-Ereignis besteht aus:

* Standardfelder
   * Zeitstempel
   * Identität
* Erlebnisansichten (falls vorhanden und falls konfiguriert)
* Erlebnis-Klicks (falls vorhanden und falls konfiguriert)
* Asset-Ansichten (falls vorhanden und konfiguriert)
* Asset-Klicks (falls vorhanden und konfiguriert)

#### Aufgezeichnete Ansichten oder Klicks

Eine Asset-Ansicht wird aufgezeichnet, wenn:

* Das Asset wurde gemäß der Konfiguration der ACA-Erweiterung nicht ausgeschlossen.
* Das Asset wird mit 75 % angezeigt.
* Dieses Asset wurde für diese Seite noch nicht aufgezeichnet.

Ein Asset-Klick wird aufgezeichnet, wenn:

* Das Asset wurde angezeigt.
* Das Asset wurde gemäß der Konfiguration der ACA-Erweiterung nicht ausgeschlossen.
* Ein Klick direkt auf das Asset, d. h. einen Link, der zu einer anderen Seite führt.

Eine Erlebnisansicht wird aufgezeichnet, wenn:

* Erlebnisse werden in der Content Analytics-Konfiguration aktiviert.

Ein Erlebnis-Klick wird aufgezeichnet, wenn:

* Jeder Klick auf einen Link auf der Seite, für den Erlebnisse aktiviert sind.


#### Gesendete Ereignisse

Content Analytics-Ereignisse werden gesendet, wenn die beiden folgenden Bedingungen eintreten:

* Inhalte werden gesendet, und zwar in folgenden Fällen:

   * Eine Asset-Ansicht oder ein Klick wird aufgezeichnet.
   * Eine Erlebnisansicht oder ein Klick wird aufgezeichnet.

* Ein Trigger zum Senden eines Ereignisses wird ausgelöst, der auftritt, wenn:

   * Web SDK oder AppMeasurement sendet ein -Ereignis.
   * Die Sichtbarkeit ändert sich in ausgeblendet, z. B.:
      * Seitenentladungen
      * Registerkarte „Wechseln“
      * Browser minimieren
      * Browser schließen
      * Sperrbildschirm
   * Die URL ändert sich, was zu einer geänderten relevanten URL führt.
   * Eine Asset-Ansicht überschreitet die Batch-Grenze von 32.


## Schemata

Content Analytics-Daten werden in Datensätzen in Experience Platform basierend auf bestimmten Content Analytics-Schemata erfasst. Referenzschemata sind öffentlich verfügbar und werden in einer Standardimplementierung von Content Analytics verwendet.

* [Schema für digitale Assets](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Schema für digitale Erlebnisse](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Inhaltsschema für Erlebnisereignisse](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
