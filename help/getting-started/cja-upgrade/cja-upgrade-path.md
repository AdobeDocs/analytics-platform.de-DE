---
title: Customer Journey Analytics-Aktualisierungspfad auswählen
description: Erfahren Sie mehr über die Vor- und Nachteile der möglichen Aktualisierungspfade bei der Aktualisierung auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 01df8b8b55ff8e8c0826bf98adfbd85d3412e6bb
workflow-type: tm+mt
source-wordcount: '3043'
ht-degree: 51%

---

# Schritt 2: Upgrade-Pfad auswählen

+++ Erweitern Sie diesen Abschnitt, um zu sehen, wo die Informationen auf dieser Seite in den größeren Aktualisierungsprozess passen. Stellen Sie sicher, dass alle vorherigen Aktualisierungsschritte abgeschlossen sind.

Bevor Sie mit diesem Abschnitt fortfahren, stellen Sie zunächst sicher, dass Sie alle vorherigen Aktualisierungsaufgaben abgeschlossen haben.

Die Informationen auf dieser Seite decken Schritt 2 des Aktualisierungsprozesses ab, wie in der folgenden Tabelle hervorgehoben:

| Aktualisierungsaufgabe | Details |
|---------|----------|
| **Schritt 1: [Erste Schritte mit der Aktualisierung](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Erfahren Sie mehr über die Vorteile der Aktualisierung auf Customer Journey Analytics und den grundlegenden Upgrade-Prozess. |
| <span class="preview">**Schritt 2: Aktualisierungspfad auswählen**</span> | <span class="preview">Für die Aktualisierung auf Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie je nach aktueller Adobe Analytics-Umgebung und den langfristigen Zielen Ihrer Organisation die für Ihre Organisation am besten geeignete Methode aus.</span> |
| **Schritt 3: [Senden von Daten an Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Der Prozess zum Senden von Daten an Adobe Experience Platform hängt vom Aktualisierungspfad ab, den Sie in Schritt 2 ausgewählt haben. |
| **Schritt 4: [Beibehalten historischer Daten](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | Die meisten Organisationen müssen ihre historischen Adobe Analytics-Daten über einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung. |
| **Schritt 5: [Durchführen zusätzlicher Implementierungsaufgaben](/help/getting-started/cja-getting-started.md)** | An dieser Stelle des Aktualisierungsprozesses müssen Sie verschiedene Aufgaben ausführen, bevor Ihre Customer Journey Analytics-Umgebung verwendet werden kann.<p>Diese zusätzlichen Aufgaben gelten für Aktualisierungen von Adobe Analytics sowie für neue Customer Journey Analytics-Implementierungen.</p><p>Zu diesen Aufgaben zählen:</p><ul><li>Erfassen von Daten in Experience Platform</li><li>Erstellen von Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics</li><li>Erstellen von Datenansichten</li><li>Portieren der Reporting-API-Nutzung</li><li>Abrechnung für Daten-Feeds und Data Warehouse</li><li>Migrieren von Projekten und Komponenten</li><li>Planen des Benutzer-Onboardings</li></ul> <p>Weitere Informationen finden Sie unter [Customer Journey Analytics – Erste Schritte](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Nachdem Sie sich für eine Aktualisierung auf Customer Journey Analytics entschieden haben, müssen Sie den optimalen Aktualisierungspfad für Ihr Unternehmen ermitteln.

Der Pfad, den Sie für die Aktualisierung von Adobe Analytics auf Customer Journey Analytics wählen, hängt von den folgenden Faktoren ab:

* Ihrer vorhandenen Adobe Analytics-Implementierung

* Ihren zukünftigen Zielen

Verwenden Sie die Informationen auf dieser Seite, um zu bestimmen, welcher Customer Journey Analytics-Aktualisierungspfad am besten mit der aktuellen Implementierung und den zukünftigen Zielen Ihres Unternehmens übereinstimmt.

Um den optimalen Aktualisierungspfad für Ihr Unternehmen zu bestimmen, sollten die folgenden Abschnitte nacheinander gelesen werden:

1. Zunächst einmal verstehen [die verfügbaren Aktualisierungspfade](#understand-upgrade-paths).

1. Dann beurteilen Sie mit [, welche Aktualisierungspfade Ihnen zur Verfügung stehen](#assess-the-upgrade-paths-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. Und schließlich wägt [die Vor- und Nachteile jedes Aktualisierungspfads ab](#weigh-the-advantages-and-disadvantages-of-the-upgrade-paths-available-to-you).

## Aktualisierungspfade verstehen

Für die Aktualisierung von Adobe Analytics auf Customer Journey Analytics gibt es verschiedene Aktualisierungspfade.

Im Allgemeinen unterscheidet sich jeder Aktualisierungspfad sowohl hinsichtlich des Aufwands, der für die Durchführung des Upgrades erforderlich ist, als auch hinsichtlich der langfristigen Rentabilität, die nach Abschluss des Upgrades erzielt wird.

In der folgenden Tabelle sind die einzelnen Aktualisierungspfade, der jeweilige Aufwand und die langfristige Rentabilität aufgeführt:

| Aktualisierungspfad | Aufwand | Langfristige Brauchbarkeit |
|---------|----------|---------|
| (Empfohlen) **Neue Implementierung des Experience Platform Web SDK mit dem Analytics-Quell-Connector**</br> Sie können mit der Verwendung von Customer Journey Analytics beginnen, indem Sie eine neue Implementierung des Experience Platform Web SDK durchführen. Dadurch können Sie Daten an Adobe Experience Platform Edge Network und Customer Journey Analytics senden. <p>Für Unternehmen, die noch nicht im Web SDK enthalten sind, ist dieser Aktualisierungspfad möglicherweise der einfachste Weg, Daten an Edge Network weiterzuleiten, da er die geringste Anzahl von Schritten erfordert. Da jedoch die gesamte Arbeit vorab erledigt ist (z. B. Erstellen des XDM-Schemas), ist zunächst ein größerer Aufwand erforderlich.</p><p>Führen Sie die folgenden grundlegenden Schritte sind:</p><ol><li>Richten Sie den Analytics-Quell-Connector ein.</li><li>Erstellen Sie ein XDM-Schema für Ihre Organisation.</li><li>Implementieren Sie das Web SDK.</li><li>Senden Sie Daten an Platform.</li></ol><p>**Hinweis:** Dies ist der empfohlene Aktualisierungspfad bei der Aktualisierung auf Customer Journey Analytics. Weitere Informationen zu diesem empfohlenen Aktualisierungspfad finden Sie unter [Empfohlener Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p> | Hoch | Hoch |
| **Neue Implementierung des Experience Platform Web SDK**</br> Sie können mit der Verwendung von Customer Journey Analytics beginnen, indem Sie eine neue Implementierung des Experience Platform Web SDK durchführen. Dadurch können Sie Daten an Adobe Experience Platform Edge Network und Customer Journey Analytics senden. <p>Für Unternehmen, die noch nicht im Web SDK enthalten sind, ist dieser Aktualisierungspfad möglicherweise der einfachste Weg, Daten an Edge Network weiterzuleiten, da er die geringste Anzahl von Schritten erfordert. Da jedoch die gesamte Arbeit vorab erledigt ist (z. B. Erstellen des XDM-Schemas), ist zunächst ein größerer Aufwand erforderlich.</p><p>Führen Sie die folgenden grundlegenden Schritte sind:</p><ol><li>Erstellen Sie ein XDM-Schema für Ihre Organisation.</li><li>Implementieren Sie das Web SDK.</li><li>Senden Sie Daten an Platform.</li></ol><p>**Hinweis:** Dieser Aktualisierungspfad kann unabhängig verwendet werden. Um die bestmöglichen Ergebnisse zu erzielen, wurde jedoch empfohlen, diesen Aktualisierungspfad in Verbindung mit dem Adobe Analytics-Quell-Connector zu verwenden. Weitere Informationen zu diesem empfohlenen Aktualisierungspfad finden Sie unter [Empfohlener Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p> | Hoch | Hoch |
| **Migrieren der Adobe Analytics-Implementierung zur Web SDK-Verwendung**</br> Wenn es sich bei Ihrer Adobe Analytics-Implementierung um AppMeasurement oder die Analytics-Erweiterung ist handelt, können Sie die Implementierung so migrieren, dass das Adobe Experience Platform Web SDK verwendet wird, um Daten an Edge Network und Adobe Analytics senden, bevor sie an Customer Journey Analytics gesendet werden.<p>Für Organisationen, die das Web SDK noch nicht nutzen, ist dies die einfachste und unkomplizierteste Methode, Daten an Edge Network zu senden. Es sind zwar mehr Schritte erforderlich, der Wechsel von Adobe Analytics zu Customer Journey Analytics läuft aber methodischer und mit konkreteren Meilensteinen ab.</p><p>Führen Sie die folgenden grundlegenden Schritte sind:</p><ol><li>Verschieben Sie Ihre vorhandene Adobe Analytics-Implementierung in das Web SDK und überprüfen Sie, ob alles in Adobe Analytics funktioniert.</li><li>Erstellen Sie ein XDM-Schema für Ihre Organisation, wenn Sie Zeit dazu haben.</li><li>Verwenden Sie die Datastream-Zuordnung, um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen.</li><li>Senden Sie Daten an Platform.</li></ol> | Moderat | Hoch |
| **Konfigurieren Sie Ihre vorhandene Adobe Analytics Web SDK-Implementierung**</br> Wenn Ihre Adobe Analytics-Implementierung bereits das Adobe Experience Platform Web SDK verwendet, können Sie mit dem Senden von Daten an Platform beginnen, indem Sie einen Datastream einrichten. Wenn Sie bereits Daten an Platform senden, müssen Sie einfach eine Verbindung zwischen Platform-Datensätzen und Customer Journey Analytics herstellen.<p>Bevor Sie Daten zur Verwendung in Customer Journey Analytics an Platform senden, sollten Sie erwägen, Ihr Adobe Analytics-Schema auf die spezifischen Anforderungen Ihres Unternehmens und anderer von Ihnen verwendeter Platform-Anwendungen zu aktualisieren.</p><p>Führen Sie die folgenden grundlegenden Schritte sind:</p><ol><li>Senden Sie Daten an Platform.<p>Wenn Sie mit Ihrer Adobe Analytics-Implementierung bereits Daten an Platform senden, ist dieser Schritt nicht erforderlich. Sie müssen einfach eine Verbindung zwischen Platform-Datensätzen und Customer Journey Analytics erstellen, wie weiter unten in diesem Vorgang beschrieben.</p></li><li>(Optional) Erstellen Sie ein XDM-Schema für Ihre Organisation, wenn Sie Zeit dazu haben.</li><li>(Bedingt) Wenn Sie ein XDM-Schema erstellt haben, verwenden Sie die Datastream-Zuordnung, um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen.</li></ol> | Gering | Hoch |
| **Verwenden des Analytics-Quell-Connectors**</br> Wenn es sich bei Ihrer Adobe Analytics-Implementierung um AppMeasurement oder die Analytics-Erweiterung handelt, können Sie damit beginnen, Daten an eine Datenansicht in Customer Journey Analytics zu senden.<p>Dies ist der einfachste Weg, Daten an Customer Journey Analytics zu übertragen. Langfristig ist es aber eine Methode, die am wenigsten brauchbar ist.</p> <p>**Hinweis:** Dieser Aktualisierungspfad kann unabhängig verwendet werden. Um die bestmöglichen Ergebnisse zu erzielen, empfehlen wir jedoch, diesen Aktualisierungspfad zusammen mit einer neuen Implementierung des Experience Platform WebSDK zu verwenden. Weitere Informationen zu diesem empfohlenen Aktualisierungspfad finden Sie unter [Empfohlener Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p> | Gering | Gering |

{style="table-layout:auto"}

Verwenden Sie das folgende Diagramm, um zu visualisieren, wo jeder Aktualisierungspfad im Hinblick auf Aufwand und langfristige Lebensfähigkeit auf das Spektrum fällt:

![cja-Aktualisierungspfade](assets/cja-upgrade-path-chart.png)

## Überprüfen Sie die für Sie verfügbaren Aktualisierungspfade anhand Ihrer aktuellen Adobe Analytics-Implementierung.

Es sind nicht alle Aktualisierungspfade für die einzelnen Typen von Adobe Analytics-Implementierungen verfügbar.

Verwenden Sie die folgenden Informationen, um zu verstehen, welcher Aktualisierungspfad für Ihr Unternehmen am besten geeignet ist.

Wenden Sie sich an den Adobe-Support, wenn Sie konkretere Ratschläge, Anleitungen oder Unterstützung benötigen.

| Vorhandene Adobe Analytics-Implementierung | Verfügbare Aktualisierungswege |
|---------|----------|
| AppMeasurement | <ul><li>Neue Implementierung des Experience Platform Web SDK</li><li>Migrieren von Adobe Analytics zum Web SDK</li><li>Analytics-Quell-Connector</li><li>(Empfohlen) Neue Implementierung des Experience Platform Web SDK mit dem Analytics Source Connector</li></ul> |
| Adobe Analytics-Erweiterung | <ul><li>Neue Implementierung des Experience Platform Web SDK</li><li>Migrieren von Adobe Analytics zum Web SDK</li><li>Analytics-Quell-Connector</li><li>(Empfohlen) Neue Implementierung des Experience Platform Web SDK mit dem Analytics Source Connector</li></ul> |
| Web SDK | <ul><li>Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Platform</li><li>(Empfohlen) Neue Implementierung des Experience Platform Web SDK mit dem Analytics Source Connector</li></ul> |

{style="table-layout:auto"}

## Abwägen der Vor- und Nachteile der Ihnen zur Verfügung stehenden Aktualisierungspfade

Die Vor- und Nachteile eines bestimmten Aktualisierungspfads hängen von Ihrer bestehenden Adobe Analytics-Implementierung ab.

Bevor Sie mithilfe der folgenden Informationen ermitteln, welcher Aktualisierungspfad für Sie geeignet ist, lesen Sie die Informationen unter [Aktualisierungspfade verstehen](#understand-migration-methods) , falls Sie dies noch nicht getan haben.

>[!NOTE]
>
>Während alle in den folgenden Abschnitten beschriebenen Aktualisierungspfade unabhängig verwendet werden können, empfiehlt Adobe beim Aktualisieren von Adobe Analytics auf Customer Journey Analytics einen zweigleisigen Aktualisierungsansatz, unabhängig von Ihrer aktuellen Adobe Analytics-Implementierung: **Adobe Analytics-Quell-Connector** und eine **neue Implementierung des Experience Platform WebSDK**.
>
>Weitere Informationen zu diesem empfohlenen Aktualisierungspfad finden Sie unter [Empfohlener Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)

### Für Adobe Analytics-Implementierungen mit AppMeasurement und Adobe Analytics-Erweiterung

Im Folgenden finden Sie die Aktualisierungspfade für Organisationen, die Adobe Analytics mit AppMeasurement oder der Adobe Analytics-Erweiterung implementiert haben. Erweitern Sie die einzelnen Abschnitte, um die Vor- und Nachteile der einzelnen Aktualisierungspfade anzuzeigen.

#### Aktualisierungspfade

+++Neue Implementierung des Experience Platform Web SDK

| Vorteile | Nachteile |
|----------|---------|
| <ul><li>**Bietet alle Vorteile des Hostings von Daten in Experience Edge Network**: <p>Dazu gehören:</p><ul><li>Reporting und Datenverfügbarkeit sind hochperformant, da Adobe Experience Platform zur Unterstützung von [Anwendungsfällen für die Echtzeit-Personalisierung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=de) entwickelt wurde. </li><li>Sie können die Implementierung für die Adobe Experience Cloud-Datenerfassung zwischen anderen Experience Cloud-Produkten (AJO, RTCDP usw.) konsolidieren.</li><li>Es besteht keine Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar, Ereignis usw.).</li></ul></li><li>**Zukunftssicher**: Künftige Implementierungsaktualisierungen sind einfacher.</li></ul> | <ul><li>**Erfordert eine völlig neue Implementierung**: Die Anforderung, eine neue Implementierung von Grund auf durchzuführen, ist mit den folgenden Nachteilen verbunden: </li><ul><li>**Zeitaufwendig**: Dies ist der zeitaufwendigste und anspruchsvollste Aktualisierungspfad, da Sie mit einer neuen Implementierung beginnen müssen.</li><li>**Neuerstellung des vollständigen Schemas in XDM erforderlich**: Bevor Sie mit der Implementierung des Web SDK beginnen können, müssen Sie das vollständige Schema in XDM neu erstellen.</li><li>**Neuerstellung von Regeln und Datenelementen erforderlich**: Bevor Sie mit der Implementierung des Web SDK beginnen können, müssen Sie alle Regelbedingungen und Datenelemente aus Ihrer Adobe Analytics-Implementierung neu erstellen.</li></ul><li>**Behält keine historischen Daten bei:** Adobe empfiehlt die Verwendung des Analytics-Quell-Connectors in Verbindung mit einer neuen Implementierung des Experience Platform Web SDK, um historische Daten nach der Aktualisierung auf Customer Journey Analytics beizubehalten. Weitere Informationen zu diesem empfohlenen Aktualisierungspfad finden Sie unter [Empfohlener Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>**Berücksichtigt keinen Vergleich der Daten Ihrer ursprünglichen Implementierung mit denen Ihrer neuen Implementierung:** Adobe empfiehlt die Verwendung des Analytics-Quell-Connectors in Verbindung mit einer neuen Implementierung des Experience Platform Web SDK, um Daten nach der Aktualisierung auf Customer Journey Analytics zu vergleichen. Weitere Informationen zu diesem empfohlenen Aktualisierungspfad finden Sie unter [Empfohlener Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li></ul> |

{style="table-layout:auto"}

+++

+++Migration von Adobe Analytics zu Experience Platform Web SDK

| Vorteile | Nachteile |
|----------|---------|
| <ul><li>**Bietet alle Vorteile des Hostings von Daten in Experience Edge Network**: <p>Dazu gehören:</p><ul><li>Reporting und Datenverfügbarkeit sind hochperformant, da Adobe Experience Platform zur Unterstützung von [Anwendungsfällen für die Echtzeit-Personalisierung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=de) entwickelt wurde. </li><li>Sie können die Implementierung für die Adobe Experience Cloud-Datenerfassung zwischen anderen Experience Cloud-Produkten (AJO, RTCDP usw.) konsolidieren.</li><li>Es besteht keine Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar, Ereignis usw.).</li></ul><li>**Nutzt Ihre vorhandene Implementierung**: Dieser Ansatz erfordert zwar einige Implementierungsänderungen, aber keine völlig neue Implementierung. Sie können die vorhandene Datenschicht und den bestehenden Code mit minimal geänderter Implementierungslogik verwenden, ohne dass sich dies auf Ihre vorhandenen Adobe Analytics-Berichte auswirkt.</li><li>**Bietet Flexibilität zum späteren Erstellen eines XDM-Schemas für Ihre Organisation**: Sie können Ihre vorhandene Adobe Analytics-Implementierung zur Nutzung des Web SDK migrieren und überprüfen, ob alles in Adobe Analytics funktioniert. Erstellen Sie dann das XDM-Schema. Diese Flexibilität ermöglicht eine methodischere und sorgfältigere Aktualisierung auf Customer Journey Analytics.</li></ul> | <ul><li>**Erfordert eine Zuordnung zum Senden von Daten an Platform**: Wenn Ihre Organisation für die Verwendung von Customer Journey Analytics bereit ist, müssen Sie Daten an einen Datensatz in Adobe Experience Platform senden. Diese Aktion erfordert, dass jedes Feld im Datenobjekt ein Eintrag im Datastream-Zuordnungs-Tool ist, das es einem XDM-Schemafeld zuweist. Die Zuordnung muss nur einmal für diesen Workflow durchgeführt werden. Implementierungsänderungen sind nicht erforderlich. Es handelt sich jedoch um einen zusätzlichen Schritt, der beim Senden von Daten in ein XDM-Objekt nicht erforderlich ist.</li><li>**Technische Schulden**: Da dieser Ansatz eine modifizierte Form Ihrer vorhandenen Implementierung nutzt, kann es schwieriger sein, die Implementierungslogik nachzuverfolgen und bei Bedarf zukünftige Änderungen vorzunehmen. </li></ul> |

{style="table-layout:auto"}

+++

+++Verwenden des Analytics-Quell-Connectors

| Vorteile | Nachteile |
|----------|---------|
| <ul><li>Weniger zeitaufwendige und anspruchsvolle Aktualisierungspfade. <p>Daten werden schnell und mit minimalem Aufwand zu Customer Journey Analytics migriert.</p></li></ul> | <ul><li>**Daten werden nicht an Edge Network gesendet**: <p>Dies führt zu folgenden Nachteilen:</p><ul><li>Höchste [Latenz](/help/technotes/guardrails.md#latencies) bei der Berichterstellung über alle Aktualisierungspfade hinweg; nicht optimiert für Echtzeit-Personalisierung.</li><li>Daten können nicht für andere Adobe Experience Platform-Anwendungen freigegeben werden. Sie sind auf Customer Journey Analytics beschränkt.</li><li>Es besteht Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar, Ereignis usw.).</li></ul><li>**Schwierigkeiten beim zukünftigen Wechsel zum Web SDK**: Schließlich möchten Sie wahrscheinlich Zugriff auf die Vorteile des Experience Platform Web SDK haben. Um mit der Verwendung des Experience Platform Web SDK zu beginnen, müssen Sie eine neue Implementierung durchführen.</li><li>**Verwendet die Feldergruppe „Analytics-Erlebnisereignis“ in Ihrem Schema**: Diese Feldergruppe fügt viele Adobe Analytics-Ereignisse hinzu, die in Ihrem Customer Journey Analytics-Schema nicht benötigt werden. Dies kann zu einem überladenen, komplexeren Schema führen, als es sonst für Customer Journey Analytics erforderlich wäre.</li></ul><p>Aufgrund dieser Nachteile empfiehlt Adobe die Verwendung des Analytics-Quell-Connectors in Verbindung mit einer neuen Implementierung des Experience Platform Web SDK. Weitere Informationen zu diesem empfohlenen Aktualisierungspfad finden Sie unter [Empfohlener Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |

{style="table-layout:auto"}

+++

### Für Adobe Analytics-Implementierungen mit Web SDK

Der folgende Aktualisierungspfad ist für Unternehmen verfügbar, die Adobe Analytics mit dem Experience Platform Web SDK implementiert haben.

Bei der Auswahl dieses Aktualisierungspfads müssen Sie auch Ihr Schema auswählen.

#### Aktualisierungspfad

+ + + Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Platform

| Vorteile | Nachteile |
|----------|---------|
| Dies ist der bevorzugte Aktualisierungspfad, wenn Ihre Adobe Analytics-Implementierung bereits das Web SDK verwendet.<ul><li>**Bietet alle Vorteile des Hostings von Daten in Experience Edge Network**: <p>Dazu gehören:</p><ul><li>Reporting und Datenverfügbarkeit sind hochperformant, da Adobe Experience Platform zur Unterstützung von [Anwendungsfällen für die Echtzeit-Personalisierung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=de) entwickelt wurde. </li><li>Sie können die Implementierung für die Adobe Experience Cloud-Datenerfassung zwischen anderen Experience Cloud-Produkten (AJO, RTCDP usw.) konsolidieren.</li><li>Es besteht keine Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar, Ereignis usw.).</li></ul><li>**Nutzt Ihre vorhandene Implementierung**: Dieser Ansatz erfordert zwar einige Implementierungsänderungen, aber keine völlig neue Implementierung. Sie können die vorhandene Datenschicht und den bestehenden Code mit minimal geänderter Implementierungslogik verwenden, ohne dass sich dies auf Ihre vorhandenen Adobe Analytics-Berichte auswirkt.</li><li>**Bietet eine Option zur Nutzung eines XDM-Schemas**: Sie können Ihr vorhandenes Adobe Analytics-Schema verwenden oder ein XDM-Schema erstellen und Felder im Datenobjekt Ihrem XDM-Schema zuordnen. [XDM-Schemata](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/home#xdm-schemas) sind flexible Schemata, um die erforderlichen Felder und nur die relevanten Felder zu definieren. <p>Weitere Informationen zu den Vorteilen bei der Verwendung eigener XDM-Schemata finden Sie unten unter „Verwenden Ihres eigenen XDM-Schemas“.</p></li><li>**Behält Regeln und Datenelemente bei**: Es sind zwar neue Regelaktionen erforderlich, Sie können aber vorhandene Datenelemente und Regelbedingungen mit minimalen Änderungen wiederverwenden.</li><li>**Zukunftssicher**: Wenn Sie sich für die Nutzung Ihres eigenen XDM-Schemas entscheiden, sind zukünftige Implementierungsaktualisierungen einfacher.</li></ul> | Keine |

{style="table-layout:auto"}

+++

#### Auswählen Ihres Schemas

Wenn Sie den Aktualisierungspfad auswählen, über den Sie die Adobe Analytics Web SDK-Implementierung konfigurieren können, um Daten an Platform zu senden, können Sie das Schema auswählen, das Sie verwenden möchten.

Sie können entscheiden, ob Sie Ihr vorhandenes Adobe Analytics-Schema verwenden oder ein Update auf Ihr eigenes XDM-Schema vornehmen möchten, um es bei der Nutzung anderer Platform-Dienste besser an die Anforderungen Ihrer Organisation anzupassen.

+++Verwenden des Adobe Analytics-Schemas bei der Adobe Analytics Web SDK-Implementierung

| Vorteile | Nachteile |
|----------|---------|
| <p>Vorteile der Verwendung des Adobe Analytics-Schemas:</p><ul><li>Einfachere Aktualisierung<p>Wenn Sie mit dem Adobe Experience Platform Web SDK bereits Daten an Adobe Analytics senden, können Sie Ihrem Datastream einen zusätzlichen Dienst hinzufügen, um Daten an Adobe Experience Platform zu senden (der dann in Ihrer Customer Journey Analytics-Konfiguration verwendet werden kann).</p></li></ul> | <p>Nachteile der Verwendung des Adobe Analytics-Schemas:</p><ul><li>Die Nutzung des Adobe Analytics-Schemas schränkt Sie zwar nicht in Bezug auf seine Verwendung mit anderen Platform-Anwendungen ein, führt aber zu einem Schema, das unnötig komplex ist. Dies liegt daran, dass das Adobe Analytics-Schema viele Adobe Analytics-spezifische Objekte enthält, die wahrscheinlich nicht von Ihrer Organisation verwendet werden.<p>Wenn Änderungen am Schema erforderlich sind, müssen Sie Tausende nicht verwendeter Felder durchgehen, um das zu aktualisierende Feld zu finden.</p></li></ul> |

+++

+++Verwenden Ihres eigenen XDM-Schemas bei der Adobe Analytics Web SDK-Implementierung

| Vorteile | Nachteile |
|----------|---------|
| <ul><p>Vorteile der Aktualisierung auf Ihr eigenes XDM-Schema:</p><ul><li>Ein optimiertes Schema, das auf die Anforderungen Ihrer Organisation und die spezifischen von Ihnen verwendeten Platform-Anwendungen zugeschnitten ist.</li><p>Wenn Änderungen am Schema erforderlich sind, müssen Sie nicht Tausende nicht verwendeter Felder durchgehen, um das zu aktualisierende Feld zu finden.</p></ul> | <p>Nachteile der Aktualisierung auf Ihr eigenes XDM-Schema:</p><ul><li>Die Aktualisierung Ihres Schemas ist ein zeitaufwendiger Prozess, der erforderlich ist, bevor Sie mit dem Senden von Daten an Platform beginnen.</li></ul> |

+++

## Der nächste Schritt – Senden von Daten an Adobe Experience Platform

Nachdem Sie die oben genannten Informationen zur Auswahl eines Aktualisierungspfads verwendet haben, erfahren Sie, wie Sie je nach gewähltem Aktualisierungspfad Daten an Adobe Experience Platform senden können.[](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)
