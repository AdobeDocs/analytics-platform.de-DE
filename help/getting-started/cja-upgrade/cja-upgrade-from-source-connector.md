---
title: Wechsel vom Analytics-Quell-Connector zum Web SDK für Customer Journey Analytics
description: Erfahren Sie, wie Sie beim Upgrade auf Customer Journey Analytics vom Analytics-Quell-Connector zum Web SDK wechseln
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: a1feb2e8458169ed208da2c42fab62d25e1015bb
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 0%

---

# Wechsel vom Analytics-Quell-Connector zum Web SDK für Customer Journey Analytics

>[!NOTE]
> 
>Verwenden Sie die Informationen auf dieser Seite, wenn Sie Fragen in der Checkliste für das [Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/) beantworten.

Die Verwendung des Analytics-Quell-Connectors als einzige Implementierung für Customer Journey Analytics hat Nachteile. Wenn Ihr Unternehmen bereits über die Implementierung des Analytics-Quell-Connectors auf Customer Journey Analytics aktualisiert hat, sollten Sie erwägen, zu einer Web SDK-Implementierung zu wechseln.

Adobe empfiehlt die Verwendung des Analytics-Quell-Connectors (zur Erfassung historischer Daten) in Verbindung mit einer neuen Implementierung des Web SDK (zur kontinuierlichen Datenerfassung).

## Vorteile und Nachteile der ausschließlichen Verwendung des Analytics-Quell-Connectors

Informationen zu den Vor- und Nachteilen der Verwendung des Analytics-Quell-Connectors finden Sie unter [Verwenden des Analytics-Quell-Connectors ausschließlich für die Aktualisierung auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md).

## Wechsel vom Analytics-Quell-Connector zum Web SDK

Im Folgenden finden Sie den allgemeinen Prozess zum Übergang vom Analytics-Quell-Connector zu einer Implementierung, die sowohl aus dem Analytics-Quell-Connector als auch einer Web-SDK-Implementierung besteht:

1. Erstellen Sie eine Web SDK-Implementierung, wie in [Detaillierte empfohlene Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) im Artikel, [Aktualisierung von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) beschrieben.

   Nachdem die Web SDK-Implementierung konfiguriert wurde, fahren Sie mit den folgenden Schritten fort.

1. Entscheiden Sie, ob Sie das Adobe Analytics-Schema oder ein XDM-Schema in Ihrer Web SDK-Implementierung verwenden.

   Weitere Informationen finden Sie unter [Schema für Customer Journey Analytics auswählen](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

1. (Bedingt) Wenn Sie planen, das Adobe Analytics-Schema mit Ihrer Web SDK-Implementierung zu verwenden, fügen Sie Ihrer Customer Journey Analytics-Verbindung den Datensatz hinzu, der automatisch vom Analytics-Quell-Connector erstellt wurde.

   Weitere Informationen finden Sie unter [Hinzufügen des Analytics-Quell-Connector-Datensatzes zur Verbindung](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Bedingt) Wenn Sie ein XDM-Schema zur Verwendung mit Ihrer Web SDK-Implementierung erstellen möchten:

   1. [Erstellen Sie ein XDM-Schema für den Analytics-Quell-Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

   1. Fügen Sie den Datensatz hinzu, der automatisch mit Ihrem ursprünglichen Analytics-Quell-Connector erstellt wurde, zu Ihrer Customer Journey Analytics-Verbindung.

      Weitere Informationen finden Sie unter [Hinzufügen des Datensatzes aus Ihrem aktuellen Analytics-Quell-Connector zur Verbindung](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

   1. Löschen Sie den ursprünglichen Analytics-Quell-Connector. <!-- need to add steps somewhere about how to do this -->

   1. [Erstellen Sie einen neuen Analytics-Quell-Connector und Zuordnungsfelder](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).
