---
title: Content Analytics-Benutzeroberfläche
description: Ein Überblick darüber, wie Daten in Content Analytics erfasst werden
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: e8cba64e706a456861fd8392ce9260b7a1c4636b
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 100%

---

# Content Analytics-Benutzeroberfläche

In diesem Artikel wird ausführlich beschrieben, wie Content Analytics Daten erfasst.

## Definitionen

Im Zusammenhang mit diesem Artikel werden die folgenden Definitionen verwendet:

* **Erlebnis**: Der Textinhalt einer gesamten Web-Seite. Zur Datenerfassung zeichnet Content Analytics die Erlebnis-ID auf, die auf der Seiten-URL basiert. Später wird der Text auf der Seite über den Abrufdienst erfasst.
* **Erlebnis-ID**: Eine eindeutige Kombination aus relevanter URL (Basis-URL plus alle Parameter, die den Inhalt auf der Seite steuern) und [Erlebnisversion](manual.md#versioning).
   * Sie geben im Rahmen der [Konfiguration](configuration.md) an, welche Parameter für eine bestimmte vollständige URL relevant sind.
   * Sie definieren eine [Versionskennung](manual.md#versioning), damit Sie Änderungen an Ihren Erlebnissen ordnungsgemäß erfassen können.
* **Asset**: Ein Bild. Content Analytics zeichnet die Asset-URL auf.
* **Asset-ID**: Die URL des Assets.
* **Relevante URL**: Die Basis-URL plus alle Parameter, die den Inhalt auf der Seite steuern.


## Funktionalität

Content Analytics erfordert, dass das Experience Platform Edge Network Web-SDK Inhaltsereignisdaten erfasst. Diese Ereignisdatenerfassung wird mit der (vorhandenen) Datenerfassung von Verhaltensereignisdaten über Mechanismen wie Experience Platform Edge Network (Web-SDK, Server-API) oder Analytics Source Connector (z. B. mit AppMeasurement) kombiniert.

Die Content Analytics-Bibliothek erfasst Daten in folgenden Fällen:

* Content Analytics ist in der Tags-Bibliothek enthalten, die auf der Seite geladen wird.
* Die Seiten-URL ist in der [Content Analytics-Erweiterung](https://experienceleague.adobe.com/de/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"} konfiguriert und Teil der enthaltenen Tag-Bibliothek.


## Content Analytics-Ereignis

Ein Content Analytics-Ereignis besteht aus:

* Standardfeldern
   * Zeitstempel
   * Identität
* Erlebnisansichten (sofern vorhanden und konfiguriert)
* Erlebnisklicks (sofern vorhanden und konfiguriert)
* Asset-Ansichten (sofern vorhanden und konfiguriert)
* Asset-Klicks (sofern vorhanden und konfiguriert)

Content Analytics-Ereignisse werden erfasst als eine Abfolge:

1. [einer aufgezeichneten Ansicht oder eines aufgezeichneten Klicks](#recorded-view-or-click)
1. [eines Triggers zum Senden eines Content Analytics-Ereignisses](#trigger-to-send-a-content-analytics-event).

Content Analytics erfasst auf diese Weise Daten, die diese Abfolge widerspiegeln, anstatt eine Ansicht oder einen Klick getrennt von dem Ereignis zu erfassen, das unmittelbar auf diese Ansicht oder diesen Klick folgt. Diese Methode zur Erfassung von Content Analytics-Daten reduziert auch die Menge der erfassten Daten.

### Aufgezeichnete Ansichten oder Klicks

Eine Asset-Ansicht wird in folgenden Fällen aufgezeichnet:

* Das Asset wurde gemäß der Konfiguration der Content Analytics-Erweiterung nicht ausgeschlossen.
* Das Asset wird zu 75 % angezeigt.
* Dieses Asset wurde für diese Seite noch nicht aufgezeichnet.

Ein Asset-Klick wird in folgenden Fällen aufgezeichnet:

* Das Asset wurde angezeigt.
* Das Asset wurde gemäß der Konfiguration der Content Analytics-Erweiterung nicht ausgeschlossen.
* Es wird direkt auf das Asset geklickt, d. h. einen Link, der zu einer anderen Seite führt.

Eine Erlebnisansicht wird in folgenden Fällen aufgezeichnet:

* Erlebnisse sind in der Content Analytics-Konfiguration aktiviert.

Ein Erlebnisklick wird in folgendem Fall aufgezeichnet:

* Es wird auf einen Link auf der Seite geklickt, für die Erlebnisse aktiviert sind.


### Trigger zum Senden eines Content Analytics-Ereignisses

Um die Anzahl der Aufrufe zu reduzieren, die von der Seite abgesetzt werden, sammelt Content Analytics Informationen, sendet diese jedoch nicht sofort. Informationen zu Inhaltsinteraktionen werden erfasst und ein Ereignis, das diese Informationen enthält, wird nur gesendet, wenn einer der folgenden Trigger auftritt:

* Web SDK oder AppMeasurement sendet ein Ereignis.
* Die Sichtbarkeit ändert sich (ausgeblendeter Status). Beispiele:
   * Die Seite wird entladen.
   * Die Registerkarte wird gewechselt.
   * Der Browser wird minimiert.
   * Der Browser wird geschlossen.
   * Der Bildschirm wird gesperrt.
* Die URL ändert sich, was zu einer Änderung der relevanten URL führt.
* Die Anzahl der aufgezeichneten und sendebereiten Asset-Ansichten überschreitet das Limit von 32.

>[!NOTE]
>
>Die weiteren Content Analytics-Ereignisse wirken sich höchstwahrscheinlich auf alle Definitionen von Absprungraten aus, die auf der Anzahl der Ereignisse in einer Sitzung oder auf einer Seite basieren.
>


## Schemata

Content Analytics-Daten werden in Datensätzen in Experience Platform basierend auf bestimmten Content Analytics-Schemata erfasst. Referenzschemata sind öffentlich verfügbar:

* [Schema für digitale Assets](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Schema für digitale Erlebnisse](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Schema für Erlebnisereignis-Inhalte](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
