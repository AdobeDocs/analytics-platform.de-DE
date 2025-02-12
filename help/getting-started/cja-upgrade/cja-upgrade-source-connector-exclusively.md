---
title: Verwenden Sie den Analytics-Quell-Connector ausschließlich für das Upgrade auf Customer Journey Analytics
description: Erfahren Sie, wie Sie den Analytics-Quell-Connector erstellen und Felder zuordnen
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 34e5f97b-c936-4de6-acc9-5774bc908655
source-git-commit: 971600fcc7d8a5aac4ad39812ab4a7af69d45ccc
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 23%

---

# Verwenden Sie den Analytics-Quell-Connector ausschließlich für das Upgrade auf Customer Journey Analytics {#use-source-connector-exclusively}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-exclusively"
>title="Nur Analytics-Quell-Connector verwenden"
>abstract="(Nicht empfohlen) Sie können nicht mit anderen Adobe Experience Platform-Services integrieren oder Adobe Analytics mit dem Analytics-Quell-Connector verlassen. Das Verbinden von Daten aus anderen Quellen erfordert wahrscheinlich das Zusammenfügen. Erfüllen Sie alle diese Anforderungen im Fragebogen, um diese Option auszuwählen."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Verwenden Sie die Informationen auf dieser Seite bei der Beantwortung von Fragen in der Checkliste für das Customer Journey Analytics-Upgrade [](https://gigazelle.github.io/cja-ttv/).

Obwohl dies nicht empfohlen wird, können Sie den Analytics-Quell-Connector als einzigen Implementierungspfad für Customer Journey Analytics verwenden. Aufgrund der mit dieser Art von Upgrade verbundenen Nachteile empfiehlt Adobe jedoch, den Analytics-Quell-Connector in Verbindung mit einer neuen Implementierung der Experience Platform Web SDK zu verwenden. Weitere Informationen zu diesem empfohlenen Aktualisierungspfad finden Sie unter [Empfohlener Pfad beim Upgrade von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

Anhand der Informationen in der folgenden Tabelle können Sie die Vor- und Nachteile einer ausschließlichen Verwendung des Quell-Connectors ermitteln.

Wenn Sie sich entscheiden, den Analytics-Quell-Connector als einzigen Implementierungspfad für Customer Journey Analytics zu verwenden, befolgen Sie die in [Aufnehmen und Verwenden von Daten mithilfe von Quell-Connectoren](/help/data-ingestion/sources.md) beschriebenen Implementierungsschritte.

| Vorteile | Nachteile |
|----------|---------|
| <ul><li>Der zeitaufwendigste und anspruchsvollste Aktualisierungspfad. <p>Daten werden schnell und einfach nach Customer Journey Analytics migriert.</p></li></ul> | <ul><li>**Daten werden nicht an Edge Network gesendet**: <p>Dies führt zu folgenden Nachteilen:</p><ul><li>Höchste [ (Latenz](/help/technotes/guardrails.md#latencies) beim Reporting über alle Upgrade-Pfade hinweg; nicht optimiert für Anwendungsfälle der Echtzeit-Personalisierung.</li><li>Daten können nicht für andere Adobe Experience Platform-Anwendungen freigegeben werden. Sie sind auf Customer Journey Analytics beschränkt.</li><li>Es besteht Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar, Ereignis usw.).</li></ul><li>**Künftig nur schwer auf Web SDK umzustellen**: Am Ende möchten Sie wahrscheinlich Zugriff auf die Vorteile von Experience Platform Web SDK. Um Experience Platform Web SDK verwenden zu können, müssen Sie eine neue Implementierung durchführen.</li><li>**Verwendet die Feldergruppe „Analytics-Erlebnisereignis“ in Ihrem Schema**: Diese Feldergruppe fügt viele Adobe Analytics-Ereignisse hinzu, die in Ihrem Customer Journey Analytics-Schema nicht benötigt werden. Dies kann zu einem überladenen, komplexeren Schema führen, als es sonst für Customer Journey Analytics erforderlich wäre.</li><li>**Erfordert Lizenzen für Adobe Analytics und Customer Journey Analytics**: Für die Verwendung des Analytics-Quell-Connectors müssen Sie sowohl für Adobe Analytics als auch für Customer Journey Analytics bezahlen.</li></ul> |

{style="table-layout:auto"}
