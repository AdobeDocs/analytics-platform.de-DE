---
title: Alternative Methoden beim Upgrade auf Customer Journey Analytics
description: Erfahren Sie mehr über die alternativen Methoden beim Upgrade auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 3a0d03d1-def0-45e6-8eb2-115b88497e6d
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 44%

---

# Alternative zum Upgrade: Senden der Datenschicht an Customer Journey Analytics {#data-collection-data-layer}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer"
>title="Senden der Datenschicht an Adobe"
>abstract="Statt Daten über ein XDM-Objekt zu senden, können Sie die gesamte Datenschicht über das Datenobjekt an Adobe senden.<br><br>Mit dieser Option sparen Sie Implementierungszeit, da Sie die Datenschicht XDM zuordnen können, anstatt ein XDM-Objekt von Grund auf neu zu befüllen. Diese Zuordnung ist jedoch sehr aufwändig, da eine erhebliche Datenmenge vorhanden ist, die Adobe nicht ohne weiteres interpretieren kann. Außerdem führt diese Option im Laufe der Zeit zu zusätzlicher Komplexität, da jedes Feld, das Sie den Daten später hinzufügen, im Datenstrom XDM zugeordnet werden muss."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-send-data-layer"
>title="Senden der Datenschicht an Adobe"
>abstract="Konfigurieren Sie die Implementierung so, dass Daten zum gewünschten Zeitpunkt an Adobe gesendet werden, und konfigurieren Sie die JSON-Payload so, dass sie Ihre vollständige Datenschicht ist."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer-map"
>title="Zuweisen jedes Datenschichtelements zu XDM"
>abstract="Ordnen Sie jedes Datenschichtelement dem gewünschten XDM-Feld zu. Alle Datenschichtelemente, die keinem XDM-Feld zugeordnet sind, werden dauerhaft verworfen, da Adobe nicht weiß, wo und wie diese Daten gespeichert werden sollen."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Beim Upgrade auf Customer Journey Analytics empfiehlt Adobe [eine neue Implementierung der Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). Abhängig von verschiedenen Faktoren, wie z. B. Timeline- und Ressourcenbeschränkungen, sind die empfohlenen Upgrade-Schritte für Ihr Unternehmen möglicherweise nicht praktikabel.

Sie können Ihre gesamte Datenschicht an Customer Journey Analytics senden, anstatt Daten mit dem XDM-Objekt zu erfassen. Diese Alternative führt jedoch im Laufe der Zeit zu zusätzlicher Komplexität.

## Vor- und Nachteile

Diese Methode schließt sich gegenseitig aus [unter Verwendung Ihrer AppMeasurement-Datenerfassungslogik mit Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md) da beide Methoden dieselbe Aufgabe erfüllen.

Die Verwendung dieser Upgrade-Alternative hat folgende Vor- und Nachteile:

| Vorteile | Nachteile |
|----------|---------|
| <ul><li>**Bietet alle Vorteile des Hostings von Daten in Experience Edge Network**: <p>Dazu gehören:</p><ul><li>Reporting und Datenverfügbarkeit sind hochperformant, da Adobe Experience Platform zur Unterstützung von [Anwendungsfällen für die Echtzeit-Personalisierung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=de) entwickelt wurde. </li><li>Sie können die Implementierung für die Adobe Experience Cloud-Datenerfassung zwischen anderen Experience Cloud-Produkten (AJO, RTCDP usw.) konsolidieren.</li><li>Es besteht keine Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar, Ereignis usw.).</li></ul><li>**Verwendet Ihre aktuelle Datenschichtlogik**: Diese Methode verwendet Ihre aktuelle Datenschichtlogik anstelle einer herkömmlichen Web-SDK-Implementierung. Dieser Ansatz erfordert zwar einige Konfigurationen, erfordert jedoch keine komplett neue Implementierung von Grund auf und erfordert kein Ausfüllen von Datenelementen oder Tag-Regeln. Damit können Sie Daten aus Ihrer Datenschicht XDM zuordnen, anstatt ein XDM-Objekt von Grund auf neu zu befüllen.</li></ul> | <ul><li>**Zuordnung erforderlich, um Daten an Platform zu senden**: Wenn Ihr Unternehmen für die Verwendung von Customer Journey Analytics bereit ist, müssen Sie Daten an einen Datensatz in Adobe Experience Platform senden. <p>Da Sie mit dieser Option Ihre gesamte Client-seitige Datenschicht in das Datenobjekt einfügen und an Adobe senden können, führt dies zu einer erheblichen Datenmenge, die Adobe nicht ohne weiteres interpretieren kann. Damit Adobe die Daten interpretieren kann, müssen Sie mithilfe der Datenstromzuordnung jedes einzelne Feld dem gewünschten XDM-Feld zuordnen.</p></li><li>**Starre Implementierung**: Die Implementierung ist auf das beschränkt, was die Datenschicht zum Zeitpunkt des Treffers bereitstellt. Dies mag für Organisationen mit grundlegenden Datenanforderungen akzeptabel sein, aber die meisten Organisationen sollten diese Art der starren Implementierung vermeiden und stattdessen eine flexiblere Implementierung wählen, die das Ausfüllen von Datenelementen ermöglicht.</li><li>**Zukünftige Änderungen sind schwieriger zu implementieren**: Jedes Feld, das Sie Ihren Daten später in der Zukunft hinzufügen, muss im Datenstrom XDM zugeordnet werden.</li></ul> |

{style="table-layout:auto"}

## Grundlegende Schritte

Die wichtigsten Schritte zum Senden Ihrer gesamten Datenschicht an Customer Journey Analytics sind:

1. Konfigurieren Sie die Implementierung so, dass Daten zum gewünschten Zeitpunkt an Adobe gesendet werden, und konfigurieren Sie die JSON-Payload so, dass sie Ihre vollständige Datenschicht ist.

1. Ordnen Sie jedes Datenschichtelement dem gewünschten XDM-Feld zu.

   Alle Datenschichtelemente, die keinem XDM-Feld zugeordnet sind, werden dauerhaft verworfen, da Adobe nicht weiß, wo und wie diese Daten gespeichert werden sollen.
