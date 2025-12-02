---
title: Verwenden Sie den Analytics-Quell-Connector ausschließlich für das Upgrade auf Customer Journey Analytics
description: Erfahren Sie, wie Sie den Analytics-Quell-Connector erstellen und Felder zuordnen
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 34e5f97b-c936-4de6-acc9-5774bc908655
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 94%

---

# Alternative zum Upgrade: Ausschließliches Verwenden des Analytics-Quell-Connectors zum Upgrade auf Customer Journey Analytics {#use-source-connector-exclusively}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-exclusively"
>title="Nur Analytics-Quell-Connector verwenden"
>abstract="(Nicht empfohlen) Sie können den Analytics-Quell-Connector als einzigen Implementierungspfad für Customer Journey Analytics verwenden. <br><br>Mit dieser Option sparen Sie zwar Implementierungszeit, indem Sie Daten schnell an Customer Journey Analytics senden. Sie hat jedoch verschiedene Nachteile, wie z. B. eine höhere Latenz und Schwierigkeiten, in Zukunft Adobe Analytics zu verlassen."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Obwohl dies nicht empfohlen wird, können Sie den Analytics-Quell-Connector als einzigen Implementierungspfad für Customer Journey Analytics verwenden. Aufgrund der mit dieser Art von Upgrade verbundenen Nachteile empfiehlt Adobe jedoch die Verwendung des Analytics-Quell-Connectors in Verbindung mit einer neuen Implementierung des Experience Platform-Web-SDK. Weitere Informationen zu diesem empfohlenen Upgrade-Pfad finden Sie unter [Empfohlener Pfad für die Aktualisierung von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

## Vor- und Nachteile

Verwenden Sie die Informationen in der folgenden Tabelle, um die Vor- und Nachteile der ausschließlichen Verwendung des Quell-Connectors beim Upgrade auf Customer Journey Analytics zu verstehen.

| Vorteile | Nachteile |
|----------|---------|
| <ul><li>Der am wenigsten zeitaufwendige und anspruchsvolle Upgrade-Pfad. <p>Daten werden schnell und einfach zu Customer Journey Analytics migriert.</p></li></ul> | <ul><li>**Daten werden nicht an Edge Network gesendet**: <p>Dies führt zu folgenden Nachteilen:</p><ul><li>Höchste [Latenzebene](/help/technotes/guardrails.md#latencies) beim Reporting über alle Upgrade-Pfade hinweg; nicht optimiert für Anwendungsfälle für die Echtzeit-Personalisierung.</li><li>Daten können nicht für andere Adobe Experience Platform-Anwendungen freigegeben werden. Sie sind auf Customer Journey Analytics beschränkt</li><li>Es besteht Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar, Ereignis usw.)</li></ul><li>**Zukünftiger Wechsel zum Web-SDK schwierig**: Früher oder später werden Sie sich wahrscheinlich Zugriff auf die Vorteile des Experience Platform-Web-SDK wünschen. Um das Experience Platform-Web-SDK verwenden zu können, müssen Sie eine neue Implementierung durchführen.</li><li>**Verwendet die Feldergruppe Analytics-Erlebnisereignis in Ihrem Schema**: Diese Feldergruppe fügt viele Adobe Analytics-Ereignisse hinzu, die in Ihrem Customer Journey Analytics-Schema nicht benötigt werden.  Dies kann zu einem überladenen, komplexeren Schema führen, als es sonst für Customer Journey Analytics erforderlich wäre.</li><li>**Erfordert Lizenzen für Adobe Analytics und Customer Journey Analytics**: Für die Verwendung des Analytics-Quell-Connectors müssen Sie sowohl für Adobe Analytics als auch für Customer Journey Analytics bezahlen.</li></ul> |

{style="table-layout:auto"}

## Grundlegende Schritte

Wenn Sie sich dazu entscheiden, den Analytics-Quell-Connector als einzigen Implementierungspfad für Customer Journey Analytics zu verwenden, befolgen Sie die in [Aufnehmen und Verwenden von Daten mithilfe von Quell-Connectoren](/help/data-ingestion/sources.md) beschriebenen Implementierungsschritte.

