---
title: Schema für Customer Journey Analytics auswählen
description: Erfahren Sie mehr über die verfügbaren Optionen bei der Auswahl eines Schemas zum Customer Journey Analytics und die Vor- und Nachteile jedes einzelnen Schemas
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: a2b90ab2-2fcb-4bf4-a862-2f0675dc2fe2
source-git-commit: 45f2097d2f0657f623b825acb8d06ec6972f757f
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 49%

---

# Schema für Customer Journey Analytics auswählen

>[!NOTE]
>
>Diese Dokumentation sollte im Rahmen des Fragebogens [Adobe Analytics zum Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/) verwendet werden.

<!-- this page exists as the "Learn more" link in the info icons for the options "I am comfortable using my Adobe Analytics schema as a basis" and "I want to use a schema tailored to my organization" -->

Bei der Aktualisierung auf Customer Journey Analytics empfiehlt Adobe, ein benutzerdefiniertes Experience-Datenmodell (XDM)-Schema zu erstellen, um es besser an die Anforderungen Ihres Unternehmens anzupassen, da Sie mit der Verwendung anderer Platform-Dienste beginnen. Alternativ können Sie Ihr vorhandenes Adobe Analytics-Schema verwenden.

Betrachten Sie die Vorteile und Nachteile jedes einzelnen.

## Erstellen Sie ein benutzerdefiniertes Schema, das auf Ihre Organisation zugeschnitten ist (empfohlen)

Adobe empfiehlt, beim Upgrade auf Customer Journey Analytics ein benutzerdefiniertes Schema zu erstellen.

| Vorteile | Nachteile |
|----------|---------|
| <ul><p>Zu den Vorteilen der Aktualisierung auf Ihr eigenes benutzerdefiniertes Schema zählen:</p><ul><li>Ein optimiertes Schema, das auf die Anforderungen Ihrer Organisation und die spezifischen von Ihnen verwendeten Platform-Anwendungen zugeschnitten ist.</li><p>Wenn Änderungen am Schema erforderlich sind, müssen Sie nicht Tausende nicht verwendeter Felder durchgehen, um das zu aktualisierende Feld zu finden.</p></ul> | <p>Die Aktualisierung auf Ihr eigenes benutzerdefiniertes Schema hat folgende Nachteile:</p><ul><li>Die Aktualisierung Ihres Schemas ist ein zeitaufwendiger Prozess, der erforderlich ist, bevor Sie mit dem Senden von Daten an Platform beginnen.</li></ul> |

## Vorhandenes Adobe Analytics-Schema verwenden

Die Option zur Verwendung Ihres bestehenden Adobe Analytics-Schemas mit Customer Journey Analytics ist nur verfügbar, wenn Ihre Adobe Analytics-Implementierung mit dem Adobe Experience Platform Web SDK konfiguriert ist. <!-- correct? Or can you do this with an AppMeasurement implementation?-->

| Vorteile | Nachteile |
|----------|---------|
| <p>Vorteile der Verwendung des Adobe Analytics-Schemas:</p><ul><li>Einfachere Aktualisierung<p>Wenn Sie mit dem Adobe Experience Platform Web SDK bereits Daten an Adobe Analytics senden, können Sie Ihrem Datastream einen zusätzlichen Dienst hinzufügen, um Daten an Adobe Experience Platform zu senden (der dann in Ihrer Customer Journey Analytics-Konfiguration verwendet werden kann).</p></li></ul> | <p>Nachteile der Verwendung des Adobe Analytics-Schemas:</p><ul><li>Die Nutzung des Adobe Analytics-Schemas schränkt Sie zwar nicht in Bezug auf seine Verwendung mit anderen Platform-Anwendungen ein, führt aber zu einem Schema, das unnötig komplex ist. Dies liegt daran, dass das Adobe Analytics-Schema viele Adobe Analytics-spezifische Objekte enthält, die wahrscheinlich nicht von Ihrer Organisation verwendet werden.<p>Wenn Änderungen am Schema erforderlich sind, müssen Sie Tausende nicht verwendeter Felder durchgehen, um das zu aktualisierende Feld zu finden.</p></li></ul> |




<!-- Not sure about any of this: 

If you plan to use your Adobe Analytics schema, the following steps are required:

For Adobe Analytics implementations using AppMeasurement:

1. Datastream mapping

For Adobe Analytics implementations using the Web SDK:

1. 



the upgrade steps provided by the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/).

If you want to create an XDM schema to use with Customer Journey Analytics, continue with [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).


Tags: (All 3 require data prep mapping. Would need to go into the datastream and map every single field to its appropriate place in XDM. Because whenever you use the data object, it always requires mapping. If you send something in the data object and it doesn't get mapped, the it is permanently lost and can't be recovered.)

1. Shim - Intercepts and instead of sending data to a report suite, it sends it to a Data View. (Data object)

1. Russ special - convert current implementation to a Web SDK implementation - put everything in the data object. 

1. Plop entire data layer into the data object and send that to the datastream. (not documented. Might be the Web SDK docs.)

-->
