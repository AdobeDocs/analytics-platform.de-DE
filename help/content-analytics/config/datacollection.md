---
title: Datenerfassung in Content Analytics
description: Ein Überblick darüber, wie Daten in Content Analytics erfasst werden
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: 89f7d8b388ab8c742712d748813520a51c736003
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 1%

---

# Datenerfassung in Content Analytics

{{release-limited-testing}}

In diesem Artikel wird detailliert erläutert, wie Content Analytics Daten erfasst


## Definitionen

Im Zusammenhang mit diesem Artikel werden die folgenden Definitionen verwendet:

* **Erlebnis**: Ein Erlebnis wird als Textinhalt auf einer gesamten Web-Seite definiert. Für die Datenerfassung zeichnet Content Analytics die Erlebnis-ID auf, die auf der Seiten-URL basiert. Später wird der Text auf der Seite über den Abrufdienst erfasst.
* **Erlebnis-**: Eine eindeutige Kombination aus relevanter URL (Basis-URL plus alle Parameter, die den Inhalt auf der Seite steuern) und [Erlebnisversion](manual.md#versioning).
   * Sie geben als Teil der [Konfiguration](configuration.md) an, welche Parameter für eine bestimmte vollständige URL relevant sind.
   * Sie können die [Versionskennung](manual.md#versioning) definieren, die verwendet wird.
* **Asset**: Ein Bild. Content Analytics zeichnet die Asset-URL auf.
* **Asset-**: Die URL des Assets.
* **Relevante URL**: Die Basis-URL plus alle Parameter, die den Inhalt auf der Seite steuern.


## Funktionalität

Die Content Analytics-Bibliothek erfasst Daten, wenn:

* Content Analytics ist in der Tag-Bibliothek enthalten, die auf der Seite geladen wird.
* Die Seiten-URL wird in der [Content Analytics-Erweiterung](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"} konfiguriert, die Teil der enthaltenen Tag-Bibliothek ist.


## Content Analytics-Ereignis

Ein Content Analytics-Ereignis besteht aus:

* Standardfelder
   * Zeitstempel
   * Identität
* Erlebnisansichten (falls vorhanden und falls konfiguriert)
* Erlebnis-Klicks (falls vorhanden und falls konfiguriert)
* Asset-Ansichten (falls vorhanden und konfiguriert)
* Asset-Klicks (falls vorhanden und konfiguriert)


Content Analytics-Ereignisse werden erfasst als eine Abfolge von:

1. [Eine aufgezeichnete Ansicht oder ein aufgezeichneter Klick](#recorded-view-or-click).
1. [Ein regelmäßiges oder spezifisches (Verhaltens-)Ereignis](#regular-or-specific-behaviorial-event).

Content Analytics erfasst auf diese Weise Daten, die diese Sequenz widerspiegeln, anstatt eine Ansicht zu erfassen oder getrennt von der Erfassung des Ereignisses zu klicken, das unmittelbar auf diese Ansicht oder diesen Klick folgt. Diese Methode zur Erfassung von Inhaltsanalysedaten reduziert auch die Menge der erfassten Daten. Datenerfassung.

### Aufgezeichnete Ansicht oder Klick

Eine Asset-Ansicht wird aufgezeichnet, wenn:

* Das Asset wurde gemäß der Konfiguration der Content Analytics-Erweiterung nicht ausgeschlossen.
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


### Regelmäßiges oder spezifisches (verhaltensbezogenes) Ereignis

Trigger zum Auslösen eines regulären oder bestimmten (verhaltensbezogenen) Ereignisses im Kontext von Content Analytics sind:

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

Content Analytics-Daten werden in Datensätzen in Experience Platform basierend auf bestimmten Content Analytics-Schemata erfasst. Referenzschemata sind öffentlich verfügbar:

* [Schema für digitale Assets](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Schema für digitale Erlebnisse](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Inhaltsschema für Erlebnisereignisse](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
