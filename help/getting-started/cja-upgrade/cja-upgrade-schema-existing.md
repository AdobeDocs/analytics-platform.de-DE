---
title: Auswählen des Schemas für Customer Journey Analytics
description: Erfahren Sie mehr über die verfügbaren Optionen bei der Auswahl eines Schemas für Customer Journey Analytics und die Vor- und Nachteile jedes einzelnen Schemas
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: a2b90ab2-2fcb-4bf4-a862-2f0675dc2fe2
autotag-review: '2026-05-19T08:16:39.426Z'
TQID: 'https://experienceleague.adobe.com/aBDtVtJ215UOK0slRC4ORwfnqZhaYtBXAI4-amzZ9Gw'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 476
ht-degree: 100%

---

# Auswählen des Schemas für Customer Journey Analytics {#choose-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-tailored"
>title="Verwenden eines benutzerdefinierten Schemas"
>abstract="(Empfohlen) Durch die Anpassung Ihres Schemas kann Ihre Organisation nur benötigte Informationen verfolgen und den Aufwand vermeiden, der mit unübersichtlichen und nicht benötigten Feldern verbunden ist. Diese Option umfasst Feldgruppen, die vom Web-SDK hinzugefügt wurden, und benutzerdefinierte Feldgruppen für Ihre Organisation."

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-default"
>title="Verwenden des Standardschemas"
>abstract="(Nicht empfohlen) Das Adobe Analytics-Schema enthält mehr als 1.000 Felder, was zu einem überladenen und komplexen Schema führen kann. Ihre Organisation wäre gezwungen, weiterhin das Konzept von Props und eVars einzuhalten. Dabei handelt es sich um ein Altkonzept, das nicht in Customer Journey Analytics verwendet wird. Die Integration mit anderen Adobe Experience Platform-Services ist schwieriger."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

<!-- this page exists as the "Learn more" link in the info icons for the options "I am comfortable using my Adobe Analytics schema as a basis" and "I want to use a schema tailored to my organization" -->

Beim Upgrade auf Customer Journey Analytics empfiehlt Adobe das Erstellen eines benutzerdefinierten Experience-Datenmodell(XDM)-Schemas, das bei der Verwendung anderer Platform-Services besser an die Anforderungen Ihrer Organisation angepasst wird. Alternativ können Sie auch Ihr bestehendes Adobe Analytics-Schema verwenden.

Berücksichtigen Sie die Vor- und Nachteile jedes einzelnen Schemas.

## Erstellen eines benutzerdefinierten Schemas, das auf Ihre Organisation zugeschnitten ist (empfohlen)

Adobe empfiehlt, beim Upgrade auf Customer Journey Analytics ein benutzerdefiniertes Schema zu erstellen.

| Vorteile | Nachteile |
|----------|---------|
| <ul><p>Vorteile der Aktualisierung auf Ihr eigenes benutzerdefiniertes Schema:</p><ul><li>Ein optimiertes Schema, das auf die Anforderungen Ihrer Organisation und die spezifischen von Ihnen verwendeten Platform-Anwendungen zugeschnitten ist.</li><p>Wenn Änderungen am Schema erforderlich sind, müssen Sie nicht Tausende nicht verwendeter Felder durchgehen, um das zu aktualisierende Feld zu finden.</p></ul> | <p>Nachteile der Aktualisierung auf Ihr eigenes benutzerdefiniertes Schema:</p><ul><li>Die Aktualisierung Ihres Schemas ist ein zeitaufwendiger Prozess, der erforderlich ist, bevor Sie Daten an Platform senden können.</li></ul> |

## Verwenden eines vorhandenen Adobe Analytics-Schemas

Die Option zum Verwenden Ihres bestehenden Adobe Analytics-Schemas mit Customer Journey Analytics ist nur verfügbar, wenn Ihre Adobe Analytics-Implementierung mit dem Adobe Experience Platform-Web-SDK konfiguriert ist. <!-- correct? Or can you do this with an AppMeasurement implementation?-->

| Vorteile | Nachteile |
|----------|---------|
| <p>Vorteile der Verwendung des Adobe Analytics-Schemas:</p><ul><li>Einfaches Upgrade<p>Wenn Sie mit dem Adobe Experience Platform Web SDK bereits Daten an Adobe Analytics senden, können Sie Ihrem Datastream einen zusätzlichen Dienst hinzufügen, um Daten an Adobe Experience Platform zu senden (der dann in Ihrer Customer Journey Analytics-Konfiguration verwendet werden kann).</p></li></ul> | <p>Nachteile der Verwendung des Adobe Analytics-Schemas:</p><ul><li>Die Nutzung des Adobe Analytics-Schemas schränkt Sie zwar nicht in Bezug auf seine Verwendung mit anderen Platform-Anwendungen ein, führt aber zu einem Schema, das unnötig komplex ist. Dies liegt daran, dass das Adobe Analytics-Schema viele Adobe Analytics-spezifische Objekte enthält, die wahrscheinlich nicht von Ihrer Organisation verwendet werden.<p>Wenn Änderungen am Schema erforderlich sind, müssen Sie Tausende nicht verwendeter Felder durchgehen, um das zu aktualisierende Feld zu finden.</p></li></ul> |




<!-- 
Not sure about any of this: 

If you plan to use your Adobe Analytics schema, the following steps are required:

For Adobe Analytics implementations using AppMeasurement:

1. Datastream mapping

For Adobe Analytics implementations using the Web SDK:

1. 



the upgrade steps provided by the Customer Journey Analytics Upgrade Guide.

If you want to create an XDM schema to use with Customer Journey Analytics, continue with [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).


Tags: (All 3 require data prep mapping. Would need to go into the datastream and map every single field to its appropriate place in XDM. Because whenever you use the data object, it always requires mapping. If you send something in the data object and it doesn't get mapped, the it is permanently lost and can't be recovered.)

1. Shim - Intercepts and instead of sending data to a report suite, it sends it to a Data View. (Data object)

1. Russ special - convert current implementation to a Web SDK implementation - put everything in the data object. 

1. Plop entire data layer into the data object and send that to the datastream. (not documented. Might be the Web SDK docs.)

-->
