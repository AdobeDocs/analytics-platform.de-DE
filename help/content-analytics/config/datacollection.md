---
title: Datenerfassung in Content Analytics
description: Erfahren Sie, wie Daten in Content Analytics erfasst werden.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: b8b0237a092b37d28bec56bba05c30a853097d4f
workflow-type: tm+mt
source-wordcount: '1093'
ht-degree: 52%

---


# Content Analytics-Benutzeroberfläche

In diesem Artikel wird ausführlich beschrieben, wie Content Analytics Daten erfasst.

## Definitionen

Im Zusammenhang mit diesem Artikel werden die folgenden Definitionen verwendet:

* **Erfahrung**:
   * Für den **Web**-Kanal wird ein Erlebnis als Textinhalt auf einer gesamten Web-Seite definiert. Für die Datenerfassung zeichnet Content Analytics die Erlebnis-ID auf, die auf der Seiten-URL basiert. Später wird der Text auf der Seite über den Abrufdienst erfasst.
   * Für den **mobile**-Kanal wird ein Erlebnis in der Mobile App mithilfe der Content Analytics-Erweiterung für Adobe Experience Platform Mobile SDK definiert und verfolgt.
* **Experience ID**:
   * Für den Web-Kanal ist die Erlebnis-ID eine eindeutige Kombination aus relevanter URL (Basis-URL plus alle Parameter, die den Inhalt auf der Seite steuern) und [Erlebnisversion](manual.md#versioning).
      * Sie geben im Rahmen der [Konfiguration](configuration.md) an, welche Parameter für eine bestimmte vollständige URL relevant sind.
      * Sie definieren eine [Versionskennung](manual.md#versioning), damit Sie Änderungen an Ihren Erlebnissen ordnungsgemäß erfassen können.
   * Für den **mobile**-Kanal ist die Erlebnis-ID der Rückgabewert von unter Verwendung des `registerExperience`-API-Aufrufs.
* **Asset**: Ein Bild. Content Analytics zeichnet die Asset-URL auf.
* **Asset-ID**: Die URL des Assets.
* **Relevante URL**: Die Basis-URL plus alle Parameter, die den Inhalt auf der Seite steuern.


## Funktionalität

Content Analytics benötigt die Experience Platform Edge Network Web SDK (für den Webkanal) und die Experience Platform Edge Network Mobile SDK (für den mobilen Kanal), um Inhaltsereignisdaten zu erfassen. Diese Ereignisdaten werden mithilfe von Experience Platform Edge Network (Web SDK, Mobile SDK oder Server-API) oder einem Analytics-Quell-Connector wie Adobe AppMeasurement mit vorhandenen Verhaltensdaten kombiniert.

Die Content Analytics-Bibliothek erfasst Daten in folgenden Fällen:

* Content Analytics ist in der Tag-Bibliothek enthalten, die auf der Seite geladen oder in der Mobile App verwendet wird.
* Die Seiten-URL und die Asset-URL werden in der [Content Analytics-Web-Erweiterung](https://experienceleague.adobe.com/de/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"} konfiguriert, die Teil der enthaltenen Tag-Bibliothek ist.
* Die Asset-URL, der Asset-Speicherort oder der Erlebnisspeicherort sind in der [Content Analytics Mobile-Erweiterung nicht &#x200B;](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/).


## Content Analytics-Ereignis

In diesem Abschnitt werden die Besonderheiten für Web-Content Analytics-Ereignisse beschrieben. Siehe [Erlebnis-Tracking](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/experience-tracking/) für Details zu mobilen Content Analytics-Ereignissen.
Ein Content Analytics-Ereignis besteht aus:

* Standardfeldern
   * Zeitstempel
   * Identität
* Erlebnisansichten (sofern vorhanden und konfiguriert)
* Erlebnisklicks (sofern vorhanden und konfiguriert)
* Asset-Ansichten (sofern vorhanden und konfiguriert)
* Asset-Klicks (sofern vorhanden und konfiguriert)

Content Analytics-Ereignisse werden erfasst als eine Abfolge:

1. Eine [aufgezeichnete Ansicht oder ein Klicken](#recorded-view-or-click).
1. Ein [Trigger zum Senden eines Content Analytics-Ereignisses](#trigger-to-send-a-content-analytics-event).

Content Analytics erfasst auf diese Weise Daten, die diese Abfolge widerspiegeln, anstatt eine Ansicht oder einen Klick getrennt von dem Ereignis zu erfassen, das unmittelbar auf diese Ansicht oder diesen Klick folgt. Diese Methode zur Erfassung von Content Analytics-Daten reduziert auch die Menge der erfassten Daten.

### Aufgezeichnete Ansichten oder Klicks

Eine Asset-Ansicht wird in folgenden Fällen aufgezeichnet:

* Das Asset wurde gemäß der Konfiguration der Content Analytics-Erweiterung nicht ausgeschlossen.
* Das Asset wird zu 75 % angezeigt.
* Dieses Asset wurde für diese Seite noch nicht aufgezeichnet.

Ein Asset-Klick wird in folgenden Fällen aufgezeichnet:

* Das Asset wurde angezeigt.
* Das Asset wurde gemäß der Konfiguration der Content Analytics-Erweiterung nicht ausgeschlossen.
* Ein Klick direkt auf das Asset, bei dem es sich um einen Link handelt, führt zu einer anderen Seite.

Eine Erlebnisansicht wird in folgenden Fällen aufgezeichnet:

* Erlebnisse sind in der Content Analytics-Konfiguration aktiviert.

Ein Erlebnisklick wird in folgendem Fall aufgezeichnet:

* Mit jedem Klick auf einen aktivierten Link wird ein Erlebnis Trigger.


### Trigger zum Senden eines Content Analytics-Ereignisses

Um die Anzahl der von der Seite gesendeten Netzwerkanfragen zu reduzieren, sammelt Content Analytics Informationen, sendet diese jedoch nicht sofort. Informationen zu Inhaltsinteraktionen werden erfasst und ein Ereignis, das diese Informationen enthält, wird nur gesendet, wenn einer der folgenden Trigger auftritt:

* Web SDK oder Adobe AppMeasurement senden ein Ereignis.
* Die Sichtbarkeit ändert sich (ausgeblendeter Status). Beispiele:
   * Die Seite wird entladen.
   * Die Registerkarte wird gewechselt.
   * Der Browser wird minimiert.
   * Der Browser wird geschlossen.
   * Der Bildschirm wird gesperrt.
* Die URL ändert sich, was zu einer Änderung der relevanten URL führt.
* Aufgezeichnete und versandbereite Asset-Ansichten überschreiten 32.

>[!NOTE]
>
>Die weiteren Content Analytics-Ereignisse wirken sich höchstwahrscheinlich auf alle Definitionen von Absprungraten aus, die auf der Anzahl der Ereignisse in einer Sitzung oder auf einer Seite basieren.
>

## Identitäten

In diesem Abschnitt wird erläutert, wie Content Analytics mit Identitäten umgeht.

### Web

Content Analytics verarbeitet Identitäten für den Webkanal wie folgt:

* ECID wird im Abschnitt „`identityMap`“ des Content Analytics-Schemas automatisch gefüllt.
* Wenn Sie andere Identitätswerte in der `identityMap` benötigen, müssen Sie diese Werte im `onBeforeEventSend`-Rückruf innerhalb der Web SDK-Erweiterung festlegen.
* Feldbasiertes Stitching wird nicht unterstützt, da das Schema systemeigen ist. Sie können dem Schema also kein weiteres Feld zur Unterstützung von feldbasiertem Stitching hinzufügen.


Um sicherzustellen, dass Content Analytics-Identitätsdaten und Web-SDK-Daten-Identitätsdaten auf Feldebene korrekt zugeordnet werden, ändern Sie den Rückruf Web SDK [on vor &#x200B;](https://experienceleague.adobe.com/de/docs/experience-platform/collection/js/commands/configure/onbeforeeventsend){target="_blank"}.

1. Navigieren Sie zu Ihrer **[!UICONTROL Tags]**-Eigenschaft, die die Adobe Experience Platform Web SDK-Erweiterung und die Adobe Content Analytics-Erweiterung enthält.
1. Wählen Sie ![Stecker](/help/assets/icons/Plug.svg) **[!UICONTROL Erweiterungen]** aus.
1. Wählen Sie die Erweiterung **[!UICONTROL Adobe Experience Platform Web SDK]** aus.
1. Wählen Sie **[!UICONTROL Konfigurieren]** aus.
1. Scrollen Sie im Abschnitt **[!UICONTROL SDK-Instanzen]** nach unten zu **[!UICONTROL Datenerfassung]** - **[!UICONTROL On before event send callback]**.

   ![On before event send callback](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. Wählen Sie **[!UICONTROL &lt;/> Provide on before event send callback code]** aus.
1. Fügen Sie folgenden Code hinzu:

   ```JavaScript
   window.adobeContentAnalytics?.forwardEvent(content);
   
   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![On before event send callback](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**, um den Code zu speichern.
1. Klicken Sie auf **[!UICONTROL Speichern]**, um die Erweiterung zu speichern.
1. [Veröffentlichen](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/overview) Sie die Änderungen an Ihrer Tags-Eigenschaft.


### Mobile

Weitere Informationen [&#x200B; Arbeiten mit Identitäten in Ihrer Mobile App finden Sie unter &#x200B;](https://developer.adobe.com/client-sdks/home/base/mobile-core/identity/)Identity for Experience Cloud ID Service-Erweiterung[&#128279;](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/) und Identity for Edge Network Mobile-Erweiterung .

Sobald sich die Identität in der Mobile App ändert, wird der aktuelle [Batch](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/#batching-settings) der Content Analytics-Daten zurückgesetzt, um eine neue Erfassung der Content Analytics-Daten für die neue Identität zu starten.

## Schemata

Experience Platform erfasst Content Analytics-Daten in Datensätzen basierend auf bestimmten Content Analytics-Schemata. Referenzschemata sind öffentlich verfügbar:

* [Schema digitaler Assets](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Schema der digitalen Erlebnisse](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Inhaltsschema für Erlebnisereignisse](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
