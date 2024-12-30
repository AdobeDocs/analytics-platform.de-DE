---
title: Entwickeln eines Schemas zur Verwendung mit Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad beim Upgrade von Adobe Analytics auf Customer Journey Analytics
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

# Entwickeln eines Schemas zur Verwendung mit Customer Journey Analytics

>[!NOTE]
> 
>Befolgen Sie die Schritte auf dieser Seite erst, nachdem Sie alle vorherigen Upgrade-Schritte abgeschlossen haben. Sie können die [empfohlenen Upgrade-Schritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die Upgrade-Schritte ausführen, die für Ihr Unternehmen mit dem [Fragebogen für das Upgrade von Adobe Analytics auf Customer Journey Analytics dynamisch generiert wurden](https://gigazelle.github.io/cja-ttv/).
>
>Nachdem Sie die Schritte auf dieser Seite abgeschlossen haben, folgen Sie den empfohlenen Upgrade-Schritten oder den dynamisch generierten Upgrade-Schritten.

Adobe empfiehlt, beim Upgrade auf Customer Journey Analytics ein Experience-Datenmodell-Schema (XDM) zu erstellen. Ein XDM-Schema ermöglicht ein optimiertes Schema, das auf die Anforderungen Ihres Unternehmens und die von Ihnen verwendeten Platform-Programme zugeschnitten ist. Wenn Änderungen am Schema erforderlich sind, müssen Sie nicht Tausende nicht verwendeter Felder durchgehen, um das zu aktualisierende Feld zu finden.

Lesen Sie die folgenden Abschnitte, wenn Sie mit der Architektur Ihres XDM-Schemas beginnen.

## Vermeiden von Adobe Analytics-Einschränkungen in Ihrem XDM-Schema

Die zugrunde liegende Architektur von Customer Journey Analytics bietet deutlich mehr Flexibilität als Adobe Analytics. Die Erstellung eines neuen XDM-Schemas ist eine wichtige Möglichkeit, diese Flexibilität zu erschließen. Stellen Sie beim Upgrade auf Customer Journey Analytics sicher, dass Sie nicht unnötige Adobe Analytics-Einschränkungen in Ihr Schema übertragen.

| Adobe Analytics-Datenarchitektur | XDM-Schemaarchitektur |
|---------|----------|
| Einzelne Metriken werden zur Analytics-Datenarchitektur hinzugefügt.<br/>In Adobe Analytics haben Sie beispielsweise für jedes Ereignis eine andere eVar. | Erstellen Sie einzelne Metriken in der Datenansicht anstatt im XDM-Schema. Dadurch erhalten Sie mehr Flexibilität bei , wenn Sie zu einem späteren Zeitpunkt Änderungen vornehmen müssen.<br/>Beispiel: Beim Customer Journey Analytics befindet sich im Schema ein einzelnes Ereignis, das in der Datenansicht mit „Ereignisse erstellen“ angezeigt wird. |
| Props und eVars sind erforderlich, um benutzerdefinierte Variablen zu erstellen. | B2 |
| A3 | B3 |

## Identifizieren Ihres Daten-Teams und anderer Stakeholder in Ihrem Unternehmen


## Erwägen anderer in Ihrem Unternehmen verwendeter Adobe Experience Platform-Anwendungen



1. Fahren Sie mit den [empfohlenen Upgrade-Schritten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oder den [dynamisch generierten Upgrade-Schritten](https://gigazelle.github.io/cja-ttv/) fort.
