---
title: Verwenden des Analytics-Quell-Connectors ausschließlich für die Aktualisierung auf Customer Journey Analytics
description: Erfahren Sie, wie Sie den Analytics-Quell-Connector und die Zuordnungsfelder erstellen.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 07570641949e17d30b7f9f5b38eb95c29c5176c0
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 27%

---

# Verwenden des Analytics-Quell-Connectors ausschließlich für die Aktualisierung auf Customer Journey Analytics

>[!NOTE]
> 
>Verwenden Sie die Informationen auf dieser Seite, wenn Sie Fragen in der Checkliste für das [Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/) beantworten.

Obwohl dies nicht empfohlen wird, können Sie den Analytics-Quell-Connector als einzigen Implementierungspfad für Customer Journey Analytics verwenden. Aufgrund der mit dieser Art von Aktualisierung verbundenen Nachteile empfiehlt Adobe jedoch die Verwendung des Analytics-Quell-Connectors in Verbindung mit einer neuen Implementierung des Experience Platform Web SDK. Weitere Informationen zu diesem empfohlenen Aktualisierungspfad finden Sie unter [Empfohlener Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

Verwenden Sie die folgenden Informationen, um die Vor- und Nachteile der ausschließlichen Verwendung des Quell-Connectors zu verstehen:

| Vorteile | Nachteile |
|----------|---------|
| <ul><li>Weniger zeitaufwendige und anspruchsvolle Aktualisierungspfade. <p>Daten werden schnell und einfach zu Customer Journey Analytics migriert.</p></li></ul> | <ul><li>**Daten werden nicht an Edge Network gesendet**: <p>Dies führt zu folgenden Nachteilen:</p><ul><li>Höchste [Latenz](/help/technotes/guardrails.md#latencies) bei der Berichterstellung über alle Aktualisierungspfade hinweg; nicht optimiert für Echtzeit-Personalisierung.</li><li>Daten können nicht für andere Adobe Experience Platform-Anwendungen freigegeben werden. Sie sind auf Customer Journey Analytics beschränkt.</li><li>Es besteht Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar, Ereignis usw.).</li></ul><li>**Schwierigkeiten beim zukünftigen Wechsel zum Web SDK**: Schließlich möchten Sie wahrscheinlich Zugriff auf die Vorteile des Experience Platform Web SDK haben. Um mit der Verwendung des Experience Platform Web SDK zu beginnen, müssen Sie eine neue Implementierung durchführen.</li><li>**Verwendet die Feldergruppe „Analytics-Erlebnisereignis“ in Ihrem Schema**: Diese Feldergruppe fügt viele Adobe Analytics-Ereignisse hinzu, die in Ihrem Customer Journey Analytics-Schema nicht benötigt werden. Dies kann zu einem überladenen, komplexeren Schema führen, als es sonst für Customer Journey Analytics erforderlich wäre.</li><li>**Erfordert Lizenzen für Adobe Analytics und Customer Journey Analytics**: Für die Verwendung des Analytics-Quell-Connectors müssen Sie sowohl für Adobe Analytics als auch für Customer Journey Analytics bezahlen.</li></ul> |

{style="table-layout:auto"}

