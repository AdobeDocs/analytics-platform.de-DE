---
title: Architektur Ihres Schemas für die Verwendung mit Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 59089146b8e56db3b0b4084615f99dc65899b74f
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 7%

---

# Architektur Ihres Schemas für die Verwendung mit Customer Journey Analytics

>[!NOTE]
> 
>Führen Sie die Schritte auf dieser Seite erst aus, nachdem Sie alle vorherigen Aktualisierungsschritte ausgeführt haben. Sie können die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die für Ihr Unternehmen dynamisch generierten Aktualisierungsschritte mit dem Fragebogen [Adobe Analytics to Customer Journey Analytics Upgrade Fragenkatalog](https://gigazelle.github.io/cja-ttv/) ausführen.
>
>Nachdem Sie die Schritte auf dieser Seite ausgeführt haben, fahren Sie mit den empfohlenen Aktualisierungsschritten oder den dynamisch generierten Aktualisierungsschritten fort.

Adobe empfiehlt, beim Upgrade auf Customer Journey Analytics ein Experience-Datenmodell (XDM)-Schema zu erstellen. Ein XDM-Schema ermöglicht ein optimiertes Schema, das auf die Bedürfnisse Ihres Unternehmens und die spezifischen von Ihnen verwendeten Platform-Anwendungen zugeschnitten ist. Wenn Änderungen am Schema erforderlich sind, müssen Sie nicht Tausende nicht verwendeter Felder durchgehen, um das zu aktualisierende Feld zu finden.

Überprüfen Sie die folgenden Abschnitte, während Sie mit der Architektur Ihres XDM-Schemas beginnen.

## Vermeiden von Adobe Analytics-Einschränkungen in Ihrem XDM-Schema

Die zugrunde liegende Architektur von Customer Journey Analytics bietet viel mehr Flexibilität als Adobe Analytics. Das Erstellen eines neuen XDM-Schemas ist eine wichtige Methode, um diese Flexibilität zu entsperren. Stellen Sie beim Upgrade auf Customer Journey Analytics sicher, dass Sie keine unnötigen Adobe Analytics-Einschränkungen in Ihr Schema einfügen.

| Adobe Analytics-Datenarchitektur | XDM-Schemaarchitektur |
|---------|----------|
| Individuelle Metriken werden der Analytics-Datenarchitektur hinzugefügt.<br/>In Adobe Analytics beispielsweise gibt es für jedes Ereignis einen anderen eVar. | Erstellen Sie einzelne Metriken in der Datenansicht anstatt im XDM-Schema. Dies bietet mehr Flexibilität in , wenn Sie Änderungen zu einem späteren Zeitpunkt vornehmen müssen.<br/>In der Customer Journey Analytics haben Sie beispielsweise ein einzelnes Ereignis im Schema und die Option zum Erstellen von Ereignissen in der Datenansicht. |
| Props und eVars sind zum Erstellen benutzerdefinierter Variablen erforderlich. | B2 |
| A3 | B3 |

## Identifizieren Sie Ihr Datenteam und andere Interessengruppen in Ihrer Organisation.


## Andere in Ihrem Unternehmen verwendete Adobe Experience Platform-Anwendungen berücksichtigen



1. Führen Sie die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oder die dynamisch generierten Aktualisierungsschritte](https://gigazelle.github.io/cja-ttv/) aus.[
