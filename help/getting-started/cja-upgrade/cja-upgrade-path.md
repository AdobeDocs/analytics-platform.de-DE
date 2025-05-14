---
title: Auswählen des Customer Journey Analytics-Upgrade-Pfads
description: Erfahren Sie mehr über die Vor- und Nachteile der möglichen Upgrade-Pfade beim Upgrade auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '2981'
ht-degree: 100%

---

# Schritt 2: Auswählen des Upgrade-Pfads

+++Erweitern Sie diesen Abschnitt, um zu sehen, wo die Informationen auf dieser Seite in den allgemeinen Upgrade-Prozess einzuordnen sind. Stellen Sie sicher, dass alle vorherigen Upgrade-Schritte abgeschlossen sind.

Bevor Sie mit diesem Abschnitt fortfahren, stellen Sie zunächst sicher, dass Sie alle vorherigen Upgrade-Aufgaben abgeschlossen haben.

Die Informationen auf dieser Seite beziehen sich auf Schritt 2 des Upgrades, wie in der folgenden Tabelle hervorgehoben:

| Upgrade-Aufgabe | Details |
|---------|----------|
| **Schritt 1: [Erste Schritte beim Upgrade](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Erfahren Sie mehr über die Vorteile des Upgrades auf Customer Journey Analytics und den grundlegenden Upgrade-Prozess. |
| <span class="preview">**Schritt 2: Auswählen des Upgrade-Pfads**</span> | <span class="preview">Für das Upgrade auf Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie je nach aktueller Adobe Analytics-Umgebung und den langfristigen Zielen Ihrer Organisation die für Ihre Organisation am besten geeignete Methode aus.</span> |
| **Schritt 3: [Senden von Daten an Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Der Prozess zum Senden von Daten an Adobe Experience Platform richtet sich nach dem in Schritt 2 ausgewählten Upgrade-Pfad. |
| **Schritt 4: [Beibehalten historischer Daten](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | Die meisten Organisationen müssen ihre historischen Adobe Analytics-Daten über einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung. |
| **Schritt 5: [Durchführen zusätzlicher Implementierungsaufgaben](/help/getting-started/cja-getting-started.md)** | An dieser Stelle im Upgrade-Prozess müssen Sie verschiedene Aufgaben ausführen, bevor Ihre Customer Journey Analytics-Umgebung einsatzbereit ist.<p>Diese zusätzlichen Aufgaben gelten für Upgrades von Adobe Analytics sowie für neue Customer Journey Analytics-Implementierungen.</p><p>Zu diesen Aufgaben zählen:</p><ul><li>Erfassen von Daten in Experience Platform</li><li>Erstellen von Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics</li><li>Erstellen von Datenansichten</li><li>Portieren der Reporting-API-Nutzung</li><li>Abrechnung für Daten-Feeds und Data Warehouse</li><li>Migrieren von Projekten und Komponenten</li><li>Planen des Benutzer-Onboardings</li></ul> <p>Weitere Informationen finden Sie unter [Customer Journey Analytics – Erste Schritte](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>Die Informationen auf dieser Seite werden durch die folgenden, umfassenderen Upgrade-Informationen ersetzt: <ul><li>**Empfohlene Upgrade-Schritte**<p>Weitere Informationen finden Sie unter [Empfohlener Pfad für das Upgrade von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Leitfaden für das Upgrade auf Customer Journey Analytics**<p>Es ist ein neuer Upgrade-Leitfaden verfügbar, in dem dynamisch Upgrade-Schritte generiert werden, die auf Ihre Organisation und Ihre individuellen Bedingungen zugeschnitten sind.</p><p>Um über Customer Journey Analytics auf den Leitfaden zuzugreifen, wählen Sie die Registerkarte **[!UICONTROL Arbeitsbereich]** und dann im linken Panel die Option **[!UICONTROL Upgrade auf Customer Journey Analytics]** aus. Befolgen Sie die Anweisungen auf dem Bildschirm.</p></li></ul>


Nachdem Sie sich für ein Upgrade auf Customer Journey Analytics entschieden haben, müssen Sie den optimalen Upgrade-Pfad für Ihre Organisation bestimmen.

Der Pfad, den Sie für das Upgrdae von Adobe Analytics auf Customer Journey Analytics auswählen, hängt von den folgenden Faktoren ab:

* Ihrer vorhandenen Adobe Analytics-Implementierung

* Ihren zukünftigen Zielen

Verwenden Sie die Informationen auf dieser Seite, um zu bestimmen, welcher Customer Journey Analytics-Upgrade-Pfad am besten zur aktuellen Implementierung und zu den künftigen Zielen Ihrer Organisation passt.

Um den optimalen Upgrade-Pfad für Ihre Organisation zu bestimmen, sollten Sie die folgenden Abschnitte nacheinander lesen:

1. [Grundlagen der Upgrade-Pfade](#understand-upgrade-paths).

1. [Beurteilen der verfügbaren Upgrade-Pfade](#assess-the-upgrade-paths-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. [Abwägen der Vor- und Nachteile jedes Upgrade-Pfads](#weigh-the-advantages-and-disadvantages-of-the-upgrade-paths-available-to-you)

## Informationen zu Upgrade-Pfaden

Für das Upgrade von Adobe Analytics auf Customer Journey Analytics stehen verschiedene Upgrade-Pfade zur Verfügung.

Im Allgemeinen unterscheidet sich jeder Upgrade-Pfad hinsichtlich des für die Durchführung des Upgrades erforderlichen Aufwands und der nach Abschluss des Upgrades erzielten langfristigen Brauchbarkeit.

In der folgenden Tabelle sind die einzelnen Upgrade-Pfade, ihr Aufwand und ihre langfristige Brauchbarkeit aufgeführt:

| Upgrade-Pfad | Aufwand | Langfristige Brauchbarkeit |
|---------|----------|---------|
| **Neue Implementierung des Experience Platform Web SDK mit dem Analytics-Quell-Connector**</br> Sie können mit der Verwendung von Customer Journey Analytics beginnen, indem Sie eine neue Implementierung des Experience Platform Web SDK durchführen. Dadurch können Sie Daten an Adobe Experience Platform Edge Network und Customer Journey Analytics senden. Darüber hinaus verwenden Sie den Analytics-Quell-Connector, um historische Daten in Customer Journey Analytics zu importieren.<p>Für Organisationen, die das Web SDK noch nicht nutzen, ist dieser Upgrade-Pfad wegen der geringsten Anzahl durchzuführender Schritte möglicherweise der einfachste Weg, um Daten an Edge Network zu senden. Da jedoch alle Arbeit vorab erledigt werden muss (z. B. die Erstellung des XDM-Schemas), ist zunächst ein größerer Aufwand erforderlich.</p><p>Führen Sie die folgenden grundlegenden Schritte sind:</p><ol><li>Erstellen Sie ein XDM-Schema für Ihre Organisation.</li><li>Implementieren Sie das Web SDK.</li><li>Senden Sie Daten an Platform.</li><li>Richten Sie den Adobe Analytics-Quell-Connector ein.</br>Der Analytics-Quell-Connector wird verwendet, um historische Adobe Analytics-Daten in Customer Journey Analytics zu importieren.<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).--></li></ol><p><!-- **Note:** This is the recommended upgrade path when upgrading to Customer Journey Analytics. For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). --></p> | Hoch | Hoch |
| **Neue Implementierung des Experience Platform Web SDK**</br> Sie können mit der Verwendung von Customer Journey Analytics beginnen, indem Sie eine neue Implementierung des Experience Platform Web SDK durchführen. Dadurch können Sie Daten an Adobe Experience Platform Edge Network und Customer Journey Analytics senden. <p>Für Organisationen, die das Web SDK noch nicht nutzen, ist dieser Upgrade-Pfad wegen der geringsten Anzahl durchzuführender Schritte möglicherweise der einfachste Weg, um Daten an Edge Network zu senden. Da jedoch alle Arbeit vorab erledigt werden muss (z. B. die Erstellung des XDM-Schemas), ist zunächst ein größerer Aufwand erforderlich.</p><p>Führen Sie die folgenden grundlegenden Schritte sind:</p><ol><li>Erstellen Sie ein XDM-Schema für Ihre Organisation.</li><li>Implementieren Sie das Web SDK.</li><li>Senden Sie Daten an Platform.</li></ol> | Hoch | Hoch |
| **Migrieren der Adobe Analytics-Implementierung zur Web SDK-Verwendung**</br> Wenn es sich bei Ihrer Adobe Analytics-Implementierung um AppMeasurement oder die Analytics-Erweiterung ist handelt, können Sie die Implementierung so migrieren, dass das Adobe Experience Platform Web SDK verwendet wird, um Daten an Edge Network und Adobe Analytics senden, bevor sie an Customer Journey Analytics gesendet werden.<p>Für Organisationen, die das Web SDK noch nicht nutzen, ist dies die einfachste und unkomplizierteste Methode, Daten an Edge Network zu senden. Es sind zwar mehr Schritte erforderlich, der Wechsel von Adobe Analytics zu Customer Journey Analytics läuft aber methodischer und mit konkreteren Meilensteinen ab.</p><p>Führen Sie die folgenden grundlegenden Schritte sind:</p><ol><li>Verschieben Sie Ihre vorhandene Adobe Analytics-Implementierung in das Web SDK und überprüfen Sie, ob alles in Adobe Analytics funktioniert.</li><li>Erstellen Sie ein XDM-Schema für Ihre Organisation, wenn Sie Zeit dazu haben.</li><li>Verwenden Sie die Datastream-Zuordnung, um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen.</li><li>Senden Sie Daten an Platform.</li></ol> | Moderat | Hoch |
| **Konfigurieren Ihrer vorhandenen Adobe Analytics Web SDK-Implementierung**</br> Wenn Ihre Adobe Analytics-Implementierung bereits das Adobe Experience Platform Web SDK verwendet, können Sie mit dem Datenversand an Customer Journey Analytics beginnen, indem Sie einen Datenstrom einrichten. Wenn Sie bereits Daten an Platform senden, können Sie auch einfach eine Verbindung zwischen Platform-Datensätzen und Customer Journey Analytics herstellen.<p>Bevor Sie Daten an Platform zur Verwendung in Customer Journey Analytics senden, sollten Sie ggf. Ihr Adobe Analytics-Schema in Bezug auf die spezifischen Anforderungen Ihrer Organisation und anderer von Ihnen verwendeter Platform-Anwendungen aktualisieren.</p><p>Führen Sie die folgenden grundlegenden Schritte sind:</p><ol><li>Beginnen Sie mit dem Datenversand an Platform.<p>Wenn Sie bereits Daten mit Ihrer Adobe Analytics-Implementierung an Platform senden, ist dieser Schritt nicht erforderlich. Sie müssen lediglich eine Verbindung zwischen Platform-Datensätzen und Customer Journey Analytics herstellen, wie weiter unten in diesem Prozess beschrieben.</p></li><li>(Optional) Erstellen Sie ein XDM-Schema für Ihre Organisation, wenn Sie Zeit dazu haben.</li><li>(Bedingt) Wenn Sie ein XDM-Schema erstellt haben, verwenden Sie die Datastream-Zuordnung, um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen.</li></ol> | Gering | Hoch |
| **Verwenden des Analytics-Quell-Connectors**</br> Wenn es sich bei Ihrer Adobe Analytics-Implementierung um AppMeasurement oder die Analytics-Erweiterung handelt, können Sie damit beginnen, Daten an eine Datenansicht in Customer Journey Analytics zu senden.<p>Dies ist der einfachste Weg, Daten an Customer Journey Analytics zu übertragen. Langfristig ist es aber eine Methode, die am wenigsten brauchbar ist.</p> <p>**Hinweis:** Dieser Upgrade-Pfad kann unabhängig verwendet werden. Um jedoch optimale Ergebnisse zu erzielen, wird empfohlen, diesen Upgrade-Pfad in Verbindung mit einer neuen Implementierung des Experience Platform WebSDK zu verwenden. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).--> </p> | Gering | Gering |

{style="table-layout:auto"}

Verwenden Sie das folgende Diagramm, um sich ein Bild davon zu machen, wo sich jeder Upgrade-Pfad im Hinblick auf Aufwand und langfristige Brauchbarkeit im Spektrum einordnet:

![CJA-Upgrade-Pfade](assets/cja-upgrade-path-chart.png)

## Beurteilen der verfügbaren Upgrade-Pfade auf Basis der aktuellen Adobe Analytics-Implementierung

Es sind nicht alle Upgrade-Pfade für die einzelnen Adobe Analytics-Implementierungstypen verfügbar.

Verwenden Sie die folgenden Informationen, um zu verstehen, welcher Upgarde-Pfad für Ihre Organisation am besten geeignet ist.

Wenden Sie sich an den Adobe-Support, wenn Sie konkretere Ratschläge, Anleitungen oder Unterstützung benötigen.

| Vorhandene Adobe Analytics-Implementierung | Verfügbare Upgrade-Pfade |
|---------|----------|
| AppMeasurement | <ul><li>Neue Implementierung des Experience Platform Web SDK</li><li>Migrieren von Adobe Analytics zum Web-SDK</li><li>Analytics-Quell-Connector</li><li>(Empfohlen) Neue Implementierung des Experience Platform Web SDK mit dem Analytics-Quell-Connector</li></ul> |
| Adobe Analytics-Erweiterung | <ul><li>Neue Implementierung des Experience Platform Web SDK</li><li>Migrieren von Adobe Analytics zum Web-SDK</li><li>Analytics-Quell-Connector</li><li>(Empfohlen) Neue Implementierung des Experience Platform Web SDK mit dem Analytics-Quell-Connector</li></ul> |
| Web SDK | <ul><li>Konfigurieren der Adobe Analytics-Web-SDK-Implementierung zum Senden von Daten an Platform</li><li>(Empfohlen) Neue Implementierung des Experience Platform Web SDK mit dem Analytics-Quell-Connector</li></ul> |

{style="table-layout:auto"}

## Abwägen der Vor- und Nachteile der zur Verfügung stehenden Upgrade-Pfade

Die Vor- und Nachteile eines bestimmten Upgrade-Pfads hängen von der vorhandenen Adobe Analytics-Implementierung ab.

Bevor Sie mithilfe der nachfolgenden Informationen den für Sie geeigneten Upgrade-Pfad ermitteln, lesen Sie unter [Grundlagen der Upgrade-Pfade](#understand-migration-methods) nach, sofern noch nicht geschehen.

>[!NOTE]
>
>Zwar kann jeder der in den folgenden Abschnitten beschriebenen Upgrade-Pfade unabhängig verwendet werden, Adobe empfiehlt allerdings – unabhängig von Ihrer aktuellen Adobe Analytics-Implementierung – beim Upgrade von Adobe Analytics auf Customer Journey Analytics einen zweigleisigen Upgrade-Ansatz: **den Adobe Analytics-Quell-Connector** und eine **neue Implementierung des Experience Platform Web SDK**.
><!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) -->

### Für Adobe Analytics-Implementierungen mit AppMeasurement und Adobe Analytics-Erweiterung

Im Folgenden finden Sie die Upgrade-Pfade, die für Organisationen verfügbar sind, die Adobe Analytics mit AppMeasurement oder mit der Adobe Analytics-Erweiterung implementiert haben. Erweitern Sie jeden Abschnitt, um die Vor- und Nachteile der einzelnen Upgrade-Pfade anzuzeigen.

#### Upgrade-Pfade

+++Neue Implementierung des Experience Platform Web SDK

| Vorteile | Nachteile |
|----------|---------|
| <ul><li>**Bietet alle Vorteile des Hostings von Daten in Experience Edge Network**: <p>Dazu gehören:</p><ul><li>Reporting und Datenverfügbarkeit sind hochperformant, da Adobe Experience Platform zur Unterstützung von [Anwendungsfällen für die Echtzeit-Personalisierung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=de) entwickelt wurde</li><li>Sie können die Implementierung für die Adobe Experience Cloud-Datenerfassung zwischen anderen Experience Cloud-Produkten (AJO, RTCDP usw.) konsolidieren</li><li>Es besteht keine Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar, Ereignis usw.)</li></ul></li><li>**Zukunftssicher**: Künftige Implementierungsaktualisierungen sind einfacher.</li></ul> | <ul><li>**Erfordert eine völlig neue Implementierung**: Die Anforderung, eine neue Implementierung von Grund auf durchzuführen, ist mit den folgenden Nachteilen verbunden: </li><ul><li>**Zeitaufwendig**: Dies ist der zeitaufwendigste und anspruchsvollste Upgrade-Pfad, da Sie dazu mit einer neuen Implementierung beginnen müssen.</li><li>**Neuerstellung des vollständigen Schemas in XDM erforderlich**: Bevor Sie mit der Implementierung des Web SDK beginnen können, müssen Sie das vollständige Schema in XDM neu erstellen.</li><li>**Neuerstellung von Regeln und Datenelementen erforderlich**: Bevor Sie mit der Implementierung des Web SDK beginnen können, müssen Sie alle Regelbedingungen und Datenelemente aus Ihrer Adobe Analytics-Implementierung neu erstellen.</li></ul><li>**Keine Beibehaltung historischer Daten**: Adobe empfiehlt die Verwendung des Analytics-Quell-Connectors in Verbindung mit einer neuen Implementierung des Experience Platform Web SDK, um historische Daten nach dem Upgrade auf Customer Journey Analytics beizubehalten. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li><li>**Kein Vergleich der Daten aus ursprünglicher und neuer Implementierung**: Adobe empfiehlt die Verwendung des Analytics-Quell-Connectors in Verbindung mit einer neuen Implementierung des Experience Platform Web SDK, um Daten nach dem Upgrade auf Customer Journey Analytics zu vergleichen. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li></ul> |

{style="table-layout:auto"}

+++

+++Migration von Adobe Analytics zu Experience Platform Web SDK

| Vorteile | Nachteile |
|----------|---------|
| <ul><li>**Bietet alle Vorteile des Hostings von Daten in Experience Edge Network**: <p>Dazu gehören:</p><ul><li>Reporting und Datenverfügbarkeit sind hochperformant, da Adobe Experience Platform zur Unterstützung von [Anwendungsfällen für die Echtzeit-Personalisierung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=de) entwickelt wurde</li><li>Sie können die Implementierung für die Adobe Experience Cloud-Datenerfassung zwischen anderen Experience Cloud-Produkten (AJO, RTCDP usw.) konsolidieren</li><li>Es besteht keine Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar, Ereignis usw.)</li></ul><li>**Nutzt Ihre vorhandene Implementierung**: Dieser Ansatz erfordert zwar einige Implementierungsänderungen, aber keine völlig neue Implementierung. Sie können die vorhandene Datenschicht und den bestehenden Code mit minimal geänderter Implementierungslogik verwenden, ohne dass sich dies auf Ihre vorhandenen Adobe Analytics-Berichte auswirkt.</li><li>**Bietet Flexibilität zum späteren Erstellen eines XDM-Schemas für Ihre Organisation**: Sie können Ihre vorhandene Adobe Analytics-Implementierung zur Nutzung des Web SDK migrieren und überprüfen, ob alles in Adobe Analytics funktioniert. Erstellen Sie dann das XDM-Schema. Diese Flexibilität ermöglicht ein methodischeres und durchdachtes Upgrade auf Customer Journey Analytics.</li></ul> | <ul><li>**Erfordert eine Zuordnung zum Senden von Daten an Platform**: Wenn Ihre Organisation für die Verwendung von Customer Journey Analytics bereit ist, müssen Sie Daten an einen Datensatz in Adobe Experience Platform senden. Diese Aktion erfordert, dass jedes Feld im Datenobjekt ein Eintrag im Datastream-Zuordnungs-Tool ist, das es einem XDM-Schemafeld zuweist. Die Zuordnung muss nur einmal für diesen Workflow durchgeführt werden. Implementierungsänderungen sind nicht erforderlich. Es handelt sich jedoch um einen zusätzlichen Schritt, der beim Senden von Daten in ein XDM-Objekt nicht erforderlich ist.</li><li>**Technische Schulden**: Da dieser Ansatz eine modifizierte Form Ihrer vorhandenen Implementierung nutzt, kann es schwieriger sein, die Implementierungslogik nachzuverfolgen und bei Bedarf zukünftige Änderungen vorzunehmen. </li></ul> |

{style="table-layout:auto"}

+++

+++Verwenden des Analytics-Quell-Connectors

| Vorteile | Nachteile |
|----------|---------|
| <ul><li>Der am wenigsten zeitaufwendige und anspruchsvolle Upgrade-Pfad. <p>Daten werden schnell und mit minimalem Aufwand zu Customer Journey Analytics migriert</p></li></ul> | <ul><li>**Daten werden nicht an Edge Network gesendet**: <p>Dies führt zu folgenden Nachteilen:</p><ul><li>Höchste [Latenzebene](/help/technotes/guardrails.md#latencies) beim Reporting über alle Upgrade-Pfade hinweg; nicht optimiert für Anwendungsfälle für die Echtzeit-Personalisierung.</li><li>Daten können nicht für andere Adobe Experience Platform-Anwendungen freigegeben werden. Sie sind auf Customer Journey Analytics beschränkt</li><li>Es besteht Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar, Ereignis usw.)</li></ul><li>**Zukünftiger Wechsel zum Web-SDK schwierig**: Früher oder später werden Sie sich wahrscheinlich Zugriff auf die Vorteile des Experience Platform-Web-SDK wünschen. Um das Experience Platform-Web-SDK verwenden zu können, müssen Sie eine neue Implementierung durchführen.</li><li>**Verwendet die Feldergruppe Analytics-Erlebnisereignis in Ihrem Schema**: Diese Feldergruppe fügt viele Adobe Analytics-Ereignisse hinzu, die in Ihrem Customer Journey Analytics-Schema nicht benötigt werden.  Dies kann zu einem überladenen, komplexeren Schema führen, als es sonst für Customer Journey Analytics erforderlich wäre.</li></ul><p>Aufgrund dieser Nachteile empfiehlt Adobe die Verwendung des Analytics-Quell-Connectors in Verbindung mit einer neuen Implementierung des Experience Platform-Web-SDK <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) -->. </p> |

{style="table-layout:auto"}

+++

### Für Adobe Analytics-Implementierungen mit Web SDK

Der folgende Upgrade-Pfad ist für Organisationen verfügbar, die Adobe Analytics mit dem Experience Platform-Web-SDK implementiert haben.

Bei der Auswahl dieses Upgrade-Pfads müssen Sie auch Ihr Schema auswählen.

#### Upgrade-Pfad

+++Konfigurieren der Adobe Analytics-Web-SDK-Implementierung zum Senden von Daten an Platform

| Vorteile | Nachteile |
|----------|---------|
| Dies ist der bevorzugte Upgrade-Pfad, wenn Ihre Adobe Analytics-Implementierung bereits das Web-SDK verwendet.<ul><li>**Bietet alle Vorteile des Hostings von Daten in Experience Edge Network**: <p>Dazu gehören:</p><ul><li>Reporting und Datenverfügbarkeit sind hochperformant, da Adobe Experience Platform zur Unterstützung von [Anwendungsfällen für die Echtzeit-Personalisierung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=de) entwickelt wurde</li><li>Sie können die Implementierung für die Adobe Experience Cloud-Datenerfassung zwischen anderen Experience Cloud-Produkten (AJO, RTCDP usw.) konsolidieren</li><li>Es besteht keine Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar, Ereignis usw.)</li></ul><li>**Nutzt Ihre vorhandene Implementierung**: Dieser Ansatz erfordert zwar einige Implementierungsänderungen, aber keine völlig neue Implementierung. Sie können die vorhandene Datenschicht und den bestehenden Code mit minimal geänderter Implementierungslogik verwenden, ohne dass sich dies auf Ihre vorhandenen Adobe Analytics-Berichte auswirkt.</li><li>**Bietet eine Option zur Nutzung eines XDM-Schemas**: Sie können Ihr vorhandenes Adobe Analytics-Schema verwenden oder ein XDM-Schema erstellen und Felder im Datenobjekt Ihrem XDM-Schema zuordnen. [XDM-Schemata](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/home#xdm-schemas) sind flexible Schemata, um die erforderlichen Felder und nur die relevanten Felder zu definieren. <p>Weitere Informationen zu den Vorteilen bei der Verwendung eigener XDM-Schemata finden Sie unten unter „Verwenden Ihres eigenen XDM-Schemas“.</p></li><li>**Behält Regeln und Datenelemente bei**: Es sind zwar neue Regelaktionen erforderlich, Sie können aber vorhandene Datenelemente und Regelbedingungen mit minimalen Änderungen wiederverwenden.</li><li>**Zukunftssicher**: Wenn Sie sich für die Nutzung Ihres eigenen XDM-Schemas entscheiden, sind zukünftige Implementierungsaktualisierungen einfacher.</li></ul> | Keine |

{style="table-layout:auto"}

+++

#### Auswählen Ihres Schemas

Wenn Sie den Upgrade-Pfad auswählen, über den Sie die Adobe Analytics-Web-SDK-Implementierung für den Datenversand an Platform konfigurieren können, haben Sie die Möglichkeit, das von Ihnen gewünschte Schema auszuwählen.

Sie können entscheiden, ob Sie Ihr vorhandenes Adobe Analytics-Schema verwenden oder ein Update auf Ihr eigenes XDM-Schema vornehmen möchten, um es bei der Nutzung anderer Platform-Dienste besser an die Anforderungen Ihrer Organisation anzupassen.

+++Verwenden des Adobe Analytics-Schemas bei der Adobe Analytics Web SDK-Implementierung

| Vorteile | Nachteile |
|----------|---------|
| <p>Vorteile der Verwendung des Adobe Analytics-Schemas:</p><ul><li>Einfaches Upgrade<p>Wenn Sie mit dem Adobe Experience Platform Web SDK bereits Daten an Adobe Analytics senden, können Sie Ihrem Datastream einen zusätzlichen Dienst hinzufügen, um Daten an Adobe Experience Platform zu senden (der dann in Ihrer Customer Journey Analytics-Konfiguration verwendet werden kann).</p></li></ul> | <p>Nachteile der Verwendung des Adobe Analytics-Schemas:</p><ul><li>Die Nutzung des Adobe Analytics-Schemas schränkt Sie zwar nicht in Bezug auf seine Verwendung mit anderen Platform-Anwendungen ein, führt aber zu einem Schema, das unnötig komplex ist. Dies liegt daran, dass das Adobe Analytics-Schema viele Adobe Analytics-spezifische Objekte enthält, die wahrscheinlich nicht von Ihrer Organisation verwendet werden.<p>Wenn Änderungen am Schema erforderlich sind, müssen Sie Tausende nicht verwendeter Felder durchgehen, um das zu aktualisierende Feld zu finden.</p></li></ul> |

+++

+++Verwenden Ihres eigenen XDM-Schemas bei der Adobe Analytics Web SDK-Implementierung

| Vorteile | Nachteile |
|----------|---------|
| <ul><p>Vorteile der Aktualisierung auf Ihr eigenes XDM-Schema:</p><ul><li>Ein optimiertes Schema, das auf die Anforderungen Ihrer Organisation und die spezifischen von Ihnen verwendeten Platform-Anwendungen zugeschnitten ist.</li><p>Wenn Änderungen am Schema erforderlich sind, müssen Sie nicht Tausende nicht verwendeter Felder durchgehen, um das zu aktualisierende Feld zu finden.</p></ul> | <p>Nachteile der Aktualisierung auf Ihr eigenes XDM-Schema:</p><ul><li>Die Aktualisierung Ihres Schemas ist ein zeitaufwendiger Prozess, der erforderlich ist, bevor Sie Daten an Platform senden können.</li></ul> |

+++

## Der nächste Schritt – Senden von Daten an Adobe Experience Platform

Nachdem Sie die oben genannten Informationen zur Auswahl eines Upgrade-Pfads verwendet haben, erfahren Sie als Nächstes, wie Sie abhängig vom ausgewählten Upgrade-Pfad [Daten an Adobe Experience Platform senden](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md).
