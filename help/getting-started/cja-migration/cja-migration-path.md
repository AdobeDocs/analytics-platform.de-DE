---
title: Wählen Sie den Customer Journey Analytics-Migrationspfad aus
description: Erfahren Sie mehr über die Vor- und Nachteile der möglichen Migrationspfade bei der Migration zum Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 5a0c383104fa4df79bc3c24d4af3677d255612f6
workflow-type: tm+mt
source-wordcount: '2641'
ht-degree: 0%

---

# Schritt 2: Migrationspfad auswählen

+++ Erweitern Sie diesen Abschnitt, um zu sehen, wo die Informationen auf dieser Seite in den größeren Migrationsprozess passen. Stellen Sie sicher, dass alle vorherigen Migrationsschritte abgeschlossen sind.

Bevor Sie mit diesem Abschnitt fortfahren, stellen Sie zunächst sicher, dass Sie alle vorherigen Migrationsaufgaben abgeschlossen haben.

Die Informationen auf dieser Seite beziehen sich auf Schritt 2 der Migration, wie in der folgenden Tabelle hervorgehoben:

| Migrationsaufgabe | Details |
|---------|----------|
| **Schritt 1: [Erste Schritte mit der Migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Erfahren Sie mehr über die Vorteile der Migration zu Adobe Analytics und den grundlegenden Migrationsprozess. |
| <span class="preview">**Schritt 2: Migrationspfad auswählen**</span> | <span class="preview">Für die Migration zum Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie je nach aktueller Adobe Analytics-Umgebung und langfristigen Zielen Ihres Unternehmens die für Ihr Unternehmen am besten geeignete Methode aus.</span> |
| **Schritt 3: [Daten an Adobe Experience Platform senden](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Der Prozess zum Senden von Daten an Adobe Experience Platform hängt vom in Schritt 2 ausgewählten Migrationspfad ab. |
| **Schritt 4: [Verlaufsdaten beibehalten](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | Die meisten Unternehmen müssen ihre historischen Adobe Analytics-Daten für einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung. |
| **Schritt 5: [Zusätzliche Implementierungsaufgaben durchführen](/help/getting-started/cja-getting-started.md)** | An dieser Stelle im Migrationsprozess müssen Sie verschiedene Aufgaben ausführen, bevor Ihre Customer Journey Analytics-Umgebung einsatzbereit ist.<p>Diese zusätzlichen Aufgaben gelten für Migrationen von Adobe Analytics sowie für neue Customer Journey Analytics-Implementierungen.</p><p>Zu diesen Aufgaben gehören:</p><ul><li>Andere Daten in Experience Platform integrieren</li><li>Erstellen von Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics</li><li>Erstellen von Datenansichten</li><li>Portieren der Nutzung der Reporting-API</li><li>Abrechnung von Daten-Feeds und Data Warehouse</li><li>Migrieren von Projekten und Komponenten</li><li>Benutzerintegration planen</li></ul> <p>Weitere Informationen finden Sie unter [Customer Journey Analytics - Erste Schritte](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Nachdem Sie sich für eine Migration zu Customer Journey Analytics entschieden haben, müssen Sie den optimalen Migrationspfad für Ihr Unternehmen ermitteln.

Der Pfad, den Sie für die Migration von Adobe Analytics zu Customer Journey Analytics wählen, hängt von den folgenden Faktoren ab:

* Ihre vorhandene Adobe Analytics-Implementierung

* Ihre zukünftigen Ziele

Verwenden Sie die Informationen auf dieser Seite, um zu bestimmen, welcher Customer Journey Analytics-Migrationspfad am besten mit der aktuellen Implementierung und den zukünftigen Zielen Ihres Unternehmens übereinstimmt.

Um den optimalen Migrationspfad für Ihre Organisation zu bestimmen, sollten die folgenden Abschnitte nacheinander gelesen werden:

1. Erstens: [die verfügbaren Migrationspfade](#understand-migration-methods).

1. Dann [beurteilen, welche Migrationspfade Ihnen zur Verfügung stehen](#assess-the-migration-methods-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. Und schließlich: [Abwägen der Vor- und Nachteile jedes Migrationspfads](#weigh-the-advantages-and-disadvantages-of-the-migration-methods-available-to-you).

## Migrationspfade verstehen

Für die Migration von Adobe Analytics zu Customer Journey Analytics gibt es verschiedene Migrationspfade.

Im Allgemeinen unterscheidet sich jeder Migrationspfad in dem für die Ausführung der Migration erforderlichen Aufwand sowie in der nach Abschluss der Migration erzielten langfristigen Rentabilität.

In der folgenden Tabelle sind die einzelnen Migrationspfade, ihr Aufwand und ihre langfristige Rentabilität aufgeführt:

| Migrationspfad | Aufwand | Langfristige Rentabilität |
|---------|----------|---------|
| **Neue Implementierung des Experience Platform Web SDK**</br> Obwohl dies technisch keine Migration ist, können Sie mit der Verwendung von Customer Journey Analytics beginnen, indem Sie eine neue Implementierung des Experience Platform Web SDK durchführen. Dadurch können Sie mit dem Senden von Daten an Adobe Experience Platform Edge Network und Customer Journey Analytics beginnen. <p>Für Unternehmen, die noch nicht im Web SDK enthalten sind, ist dieser Migrationspfad möglicherweise der einfachste Weg, Daten an Edge Network weiterzuleiten, da er die geringste Anzahl von Schritten erfordert. Da jedoch die gesamte Arbeit vorab erledigt ist (z. B. Erstellen des XDM-Schemas), ist zunächst ein größerer Aufwand erforderlich.</p><p>Die grundlegenden Schritte sind:</p><ol><li>Erstellen Sie ein XDM-Schema für Ihre Organisation.</li><li>Implementieren Sie das Web SDK.</li><li>Senden von Daten an Platform.</li></ol> | Hoch | Hoch |
| **Migrieren der Adobe Analytics-Implementierung zur Verwendung des Web SDK**</br> Wenn Ihre Adobe Analytics-Implementierung AppMeasurement oder die Analytics-Erweiterung ist, können Sie sie migrieren, um das Adobe Experience Platform Web SDK zu verwenden und mit dem Senden von Daten an Edge Network und Adobe Analytics zu beginnen, bevor sie an Customer Journey Analytics gesendet werden.<p>Für Unternehmen, die noch nicht über das Web SDK verfügen, ist dies die einfachste und reibungsloseste Methode, Daten an Edge Network zu übertragen. Sie erfordert mehr Schritte, bietet aber einen methodischeren Übergang von Adobe Analytics zu Customer Journey Analytics mit greifbareren Meilensteinen.</p><p>Die grundlegenden Schritte sind:</p><ol><li>Verschieben Sie Ihre vorhandene Adobe Analytics-Implementierung in das Web-SDK und überprüfen Sie, ob in Adobe Analytics alles funktioniert.</li><li>Erstellen Sie ein XDM-Schema für Ihre Organisation so, wie Sie Zeit haben.</li><li>Verwenden Sie die Datastream-Zuordnung, um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen.</li><li>Senden von Daten an Platform.</li></ol> | Moderieren | Hoch |
| **Bestehende Adobe Analytics Web SDK-Implementierung konfigurieren**</br> Wenn Ihre Adobe Analytics-Implementierung bereits das Adobe Experience Platform Web SDK verwendet, können Sie mit minimalem Aufwand mit dem Senden von Daten an Customer Journey Analytics beginnen.<p>Bevor Sie Daten an Customer Journey Analytics senden, sollten Sie erwägen, Ihr Adobe Analytics-Schema auf die spezifischen Anforderungen Ihres Unternehmens und anderer von Ihnen verwendeter Platform-Anwendungen zu aktualisieren.</p><p>Die grundlegenden Schritte sind:</p><ol><li>Senden Sie Daten an Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Optional) Erstellen Sie ein XDM-Schema für Ihre Organisation, da Sie Zeit haben.</li><li>(Bedingt) Wenn Sie ein XDM-Schema erstellt haben, verwenden Sie die Datastream-Zuordnung, um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen.</li></ol> | Niedrig | Hoch |
| **Verwenden des Analytics Source Connectors**</br> Wenn Ihre Adobe Analytics-Implementierung AppMeasurement oder die Analytics-Erweiterung ist, können Sie mit dem Senden von Daten an eine Datenansicht in Customer Journey Analytics beginnen.<p>Dies ist der einfachste Weg, Daten an Customer Journey Analytics zu übertragen, aber langfristig ist dies die am wenigsten praktikable Methode.</p> | Niedrig | Niedrig |

{style="table-layout:auto"}

Verwenden Sie das folgende Diagramm, um zu visualisieren, wo jeder Migrationspfad im Hinblick auf Aufwand und langfristige Lebensfähigkeit auf das Spektrum fällt:

![cja-Migrationswege](assets/cja-migration-methods.png)

## Prüfen Sie die verfügbaren Migrationspfade auf Grundlage Ihrer aktuellen Adobe Analytics-Implementierung.

Es sind nicht alle Migrationspfade für die einzelnen Typen von Adobe Analytics-Implementierungen verfügbar.

Verwenden Sie die folgenden Informationen, um zu verstehen, welcher Migrationspfad für Ihr Unternehmen am besten geeignet ist.

Wenden Sie sich an Ihren Adobe-Support-Mitarbeiter, wenn Sie spezifischere Ratschläge, Anleitungen oder Support benötigen.

| Bestehende Adobe Analytics-Implementierung | Verfügbare Migrationswege |
|---------|----------|
| AppMeasurement | <ul><li>Neue Implementierung des Experience Platform Web SDK</li><li>Migrieren von Adobe Analytics zum Web SDK</li><li>Analytics Source Connector</li></ul> |
| Adobe Analytics-Erweiterung | <ul><li>Neue Implementierung des Experience Platform Web SDK</li><li>Migrieren von Adobe Analytics zum Web SDK</li><li>Analytics Source Connector</li></ul> |
| Web SDK | <ul><li>Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Customer Journey Analytics</li></ul> |

{style="table-layout:auto"}

## Abwägen der Vor- und Nachteile der Ihnen zur Verfügung stehenden Migrationspfade

Die Vor- und Nachteile eines bestimmten Migrationspfads hängen von Ihrer bestehenden Adobe Analytics-Implementierung ab.

Bevor Sie die unten stehenden Informationen verwenden, um zu ermitteln, welcher Migrationspfad für Sie geeignet ist, lesen Sie die Informationen unter [Migrationspfade verstehen](#understand-migration-methods) wenn Sie es noch nicht getan haben.

### Für Adobe Analytics-Implementierungen mit: AppMeasurement und Adobe Analytics-Erweiterung

Im Folgenden finden Sie die Migrationspfade, die für Organisationen verfügbar sind, die Adobe Analytics mit AppMeasurement oder die Adobe Analytics-Erweiterung implementiert haben. Erweitern Sie jeden Abschnitt, um die Vor- und Nachteile der einzelnen Migrationspfade anzuzeigen.

**Migrationspfade:**

+++ Neue Implementierung des Experience Platform Web SDK

| Vorteile | Nachteile |
|----------|---------|
| <ul><li>**Bietet alle Vorteile des Hosting von Daten in Experience Edge Network**: <p>Zu diesen Vorteilen zählen:</p><ul><li>Leistungsstarke Berichterstellung und Datenverfügbarkeit, da Adobe Experience Platform zur Leistungsoptimierung entwickelt wurde [Anwendungsfälle für die Echtzeit-Personalisierung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=de)</li><li>Tags für die Adobe Experience Cloud-Datenerfassung zwischen anderen Experience Cloud-Produkten zusammenfassen (AJO, RTCDP usw.)</li><li>Nicht von der Adobe Analytics-Nomenklatur abhängig (Prop, eVar, Ereignis usw.)</li></ul></li><li>**Verwendet ein XDM-Schema**: [XDM-Schemata](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) sind ein flexibles Schema, um die erforderlichen Felder und nur die relevanten Felder zu definieren. Mithilfe eines XDM-Schemas können Sie von der Gruppe &quot;Adobe Analytics-Erlebnisereignisfeld&quot;weg wechseln.</li><li>**Keine Zeichenbeschränkungen**: Das XDM-Schema hat keine Zeichenbeschränkungen.</li><li>**Zukunftssicher**: Das Experience Platform Web SDK erhält die neuesten Funktionen und Funktionen.</li><li>**Bessere Genauigkeit der Besucheridentifizierung**: Das Experience Platform Web SDK verwendet [Erstanbieter-Geräte-IDs](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=de) für eine höhere Genauigkeit der Besucheridentifizierung.</li></ul> | <ul><li>**Neue Implementierung erforderlich von Grund auf**: Die Anforderung, eine neue Implementierung von Grund auf durchzuführen, bedeutet die folgenden Nachteile: </li><ul><li>**Zeitaufwendig**: Dies ist der zeitaufwendigste und anspruchsvollste Migrationspfad, da Sie dazu mit einer neuen Implementierung beginnen müssen.</li><li>**Muss das vollständige Schema in XDM neu erstellen**: Bevor Sie mit der Implementierung des Web SDK beginnen können, müssen Sie das vollständige Schema in XDM neu erstellen.</li><li>**Muss Regeln und Datenelemente neu erstellen**: Bevor Sie mit der Implementierung des Web SDK beginnen können, müssen Sie alle Regelbedingungen und Datenelemente aus Ihrer Adobe Analytics-Implementierung neu erstellen.</li></ul></ul> |

{style="table-layout:auto"}

+++

+++Adobe Analytics zum Experience Platform Web SDK migrieren

| Vorteile | Nachteile |
|----------|---------|
| <ul><li>**Bietet alle Vorteile des Hosting von Daten in Experience Edge Network**: <p>Zu diesen Vorteilen zählen:</p><ul><li>Leistungsstarke Berichterstellung und Datenverfügbarkeit, da Adobe Experience Platform zur Leistungsoptimierung entwickelt wurde [Anwendungsfälle für die Echtzeit-Personalisierung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=de)</li><li>Tags für die Adobe Experience Cloud-Datenerfassung zwischen anderen Experience Cloud-Produkten zusammenfassen (AJO, RTCDP usw.)</li><li>Nicht von der Adobe Analytics-Nomenklatur abhängig (Prop, eVar, Ereignis usw.)</li></ul><li>**Verwendet Ihre vorhandene Implementierung**: Dieser Ansatz erfordert zwar einige Implementierungsänderungen, erfordert jedoch keine völlig neue Implementierung. Sie können Ihre vorhandene Datenschicht und Ihren Code mit minimalen Änderungen an der Implementierungslogik verwenden, ohne dass sich dies auf Ihre vorhandene Adobe Analytics-Berichterstellung auswirkt.</li><li>**Flexibilität beim Erstellen eines XDM-Schemas für Ihre Organisation zu einem späteren Zeitpunkt**: Sie können Ihre vorhandene Adobe Analytics-Implementierung migrieren, um das Web SDK zu verwenden und zu überprüfen, ob in Adobe Analytics alles funktioniert, und dann das XDM-Schema erstellen. Diese Flexibilität ermöglicht eine methodischere und sorgfältigere Migration.</li><li>**Verwendet ein XDM-Schema**: [XDM-Schemata](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) sind ein flexibles Schema, um die erforderlichen Felder und nur die relevanten Felder zu definieren. Mithilfe eines XDM-Schemas können Sie von der Gruppe &quot;Adobe Analytics-Erlebnisereignisfeld&quot;weg wechseln.</li><li>(bei der Migration von der Adobe Analytics-Tag-Erweiterung) **Behält Regeln und Datenelemente bei**: Es sind zwar neue Regelaktionen erforderlich, Sie können aber Ihre vorhandenen Datenelemente und Regelbedingungen mit minimalen Änderungen wiederverwenden.</li><li>**Keine Zeichenbeschränkungen**: Das XDM-Schema hat keine Zeichenbeschränkungen.</li><li>**Zukunftssicher**: Das Experience Platform Web SDK erhält die neuesten Funktionen und Funktionen.</li><li>**Bessere Genauigkeit der Besucheridentifizierung**: Das Experience Platform Web SDK verwendet [Erstanbieter-Geräte-IDs](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=de) für eine höhere Genauigkeit der Besucheridentifizierung.</li></ul> | <ul><li>**Erfordert Zuordnung zum Senden von Daten an Platform**: Wenn Ihr Unternehmen für die Verwendung von Customer Journey Analytics bereit ist, müssen Sie Daten an einen Datensatz in Adobe Experience Platform senden. Diese Aktion erfordert, dass jedes Feld im Datenobjekt ein Eintrag im Datastream-Mapping-Tool ist, der es einem XDM-Schemafeld zuweist. Die Zuordnung muss nur einmal für diesen Workflow durchgeführt werden. Es müssen keine Implementierungsänderungen vorgenommen werden. Es handelt sich jedoch um einen zusätzlichen Schritt, der beim Senden von Daten in ein XDM-Objekt nicht erforderlich ist.</li><li>**Technische Schulden**: Da dieser Ansatz eine modifizierte Form Ihrer vorhandenen Implementierung verwendet, kann es schwieriger sein, die Implementierungslogik zu verfolgen und bei Bedarf zukünftige Änderungen vorzunehmen. </li><li>(Nur bei der Migration von AppMeasurement) **Implementierungsänderungen erfordern eine Intervention von Entwicklern**: Wenn Sie Änderungen an Ihrer Web SDK-Implementierung vornehmen möchten, müssen Sie sich an Ihr Entwicklungsteam wenden, um den Code auf Ihrer Site zu bearbeiten. Dies gilt nicht bei der Migration von der Analytics-Tag-Erweiterung zum Web SDK.</li></ul> |

{style="table-layout:auto"}

+++

++ + Verwenden des Analytics Source Connectors

| Vorteile | Nachteile |
|----------|---------|
| <ul><li>Weniger zeitaufwendiger und anspruchsvoller Migrationspfad. <p>Daten werden schnell und mit minimalem Aufwand zu Customer Journey Analytics migriert</p></li></ul> | <ul><li>**Daten werden nicht an Edge Network gesendet**: <p>Dies führt zu folgenden Nachteilen:</p><ul><li>Höchste Ebene von [Latenz](/help/admin/guardrails.md#latencies) in Berichten über alle Migrationspfade hinweg, nicht optimiert für Anwendungsfälle der Echtzeit-Personalisierung.</li><li>Daten können nicht für andere Adobe Experience Platform-Anwendungen freigegeben werden. Sie sind auf Customer Journey Analytics beschränkt</li><li>Auf die Adobe Analytics-Nomenklatur (Eigenschaft, eVar, Ereignis usw.) angewiesen</li></ul><li>**Schwierigkeit, in Zukunft zum Web SDK zu wechseln**: </li><li>**Verwendet die Feldergruppe Analytics-Erlebnisereignis in Ihrem Schema**: Diese Feldergruppe fügt viele Adobe Analytics-Ereignisse hinzu, die in Ihrem Customer Journey Analytics-Schema nicht benötigt werden.  Dies kann zu einem übersichtlicheren, komplexeren Schema führen, als es sonst für das Customer Journey Analytics erforderlich wäre.</li></ul> |

{style="table-layout:auto"}

+++

### Für Adobe Analytics-Implementierungen mit: Web SDK

Der folgende Migrationspfad steht für Organisationen zur Verfügung, die Adobe Analytics mit dem Experience Platform Web SDK implementiert haben:

**Migrationspfad:**

+ + + Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Customer Journey Analytics

| Vorteile | Nachteile |
|----------|---------|
| Dies ist der bevorzugte Migrationspfad, wenn Ihre Adobe Analytics-Implementierung bereits das Web SDK verwendet.<ul><li>**Bietet alle Vorteile des Hosting von Daten in Experience Edge Network**: <p>Zu diesen Vorteilen zählen:</p><ul><li>Leistungsstarke Berichterstellung und Datenverfügbarkeit, da Adobe Experience Platform zur Leistungsoptimierung entwickelt wurde [Anwendungsfälle für die Echtzeit-Personalisierung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=de)</li><li>Tags für die Adobe Experience Cloud-Datenerfassung zwischen anderen Experience Cloud-Produkten zusammenfassen (AJO, RTCDP usw.)</li><li>Nicht von der Adobe Analytics-Nomenklatur abhängig (Prop, eVar, Ereignis usw.)</li></ul><li>**Verwendet Ihre vorhandene Implementierung**: Dieser Ansatz erfordert zwar einige Implementierungsänderungen, erfordert jedoch keine völlig neue Implementierung. Sie können Ihre vorhandene Datenschicht und Ihren Code mit minimalen Änderungen an der Implementierungslogik verwenden, ohne dass sich dies auf Ihre vorhandene Adobe Analytics-Berichterstellung auswirkt.</li><li>**Bietet eine Option zur Verwendung eines XDM-Schemas**: Sie können Ihr vorhandenes Adobe Analytics-Schema verwenden oder ein XDM-Schema erstellen und Felder im Datenobjekt Ihrem XDM-Schema zuordnen. [XDM-Schemata](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) sind ein flexibles Schema, um die erforderlichen Felder und nur die relevanten Felder zu definieren. <p>Weitere Informationen zu den Vorteilen der Verwendung des XDM-Schemas finden Sie unten unter &quot;Verwenden des XDM-Schemas&quot;.</p></li><li>**Behält Regeln und Datenelemente bei**: Es sind zwar neue Regelaktionen erforderlich, Sie können aber Ihre vorhandenen Datenelemente und Regelbedingungen mit minimalen Änderungen wiederverwenden.</li><li>**Keine Zeichenbeschränkungen**: Es gibt keine Zeichenbeschränkungen, wenn Sie ein XDM-Schema erstellen und verwenden.</li><li>**Zukunftssicher**: Das Experience Platform Web SDK erhält die neuesten Funktionen und Funktionen.</li><li>**Bessere Genauigkeit der Besucheridentifizierung**: Das Experience Platform Web SDK verwendet [Erstanbieter-Geräte-IDs](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=de) für eine höhere Genauigkeit der Besucheridentifizierung.</li></ul><p>**Schema auswählen**</p><p>Bei Verwendung dieses Migrationspfads können Sie entscheiden, ob Sie Ihr vorhandenes Adobe Analytics-Schema verwenden möchten oder ob Sie das XDM-Schema aktualisieren möchten, um es besser an die Anforderungen Ihres Unternehmens anzupassen, wenn Sie mit der Verwendung anderer Platform-Anwendungen beginnen.</p><p>**Verwenden des Adobe Analytics-Schemas**</p><p>Vorteile der Verwendung des Adobe Analytics-Schemas:</p><ul><li>Erleichterung der Migration<p>Wenn Sie mit dem Adobe Experience Platform Web SDK bereits Daten an Adobe Analytics senden, können Sie Ihrem Datenspeicher einen zusätzlichen Dienst hinzufügen, um Daten an Adobe Experience Platform zu senden (der dann in Ihrer Customer Journey Analytics-Konfiguration verwendet werden kann).</p></li></ul><p>Die Verwendung des Adobe Analytics-Schemas hat folgende Nachteile:</p><ul><li>Die Verwendung des Adobe Analytics-Schemas schränkt Sie zwar nicht in Bezug auf die Verwendung mit anderen Platform-Anwendungen ein, führt aber zu einem Schema, das komplexer ist, als es sonst sein könnte. Dies liegt daran, dass das Adobe Analytics-Schema viele Adobe Analytics-spezifische Objekte enthält, die wahrscheinlich nicht von Ihrem Unternehmen verwendet werden.<p>Wenn Änderungen am Schema erforderlich sind, müssen Sie Tausende nicht verwendeter Felder durchlaufen, um das zu aktualisierende Feld zu finden.</p></li></ul><p>**Verwenden des XDM-Schemas**</p><p>Vorteile der Aktualisierung des XDM-Schemas sind:</p><ul><li>Ein optimiertes Schema, das auf die Anforderungen Ihres Unternehmens und die spezifischen Platform-Anwendungen zugeschnitten ist, die Sie verwenden.</li><p>Wenn Änderungen am Schema erforderlich sind, müssen Sie nicht Tausende nicht verwendeter Felder durchlaufen, um das zu aktualisierende Feld zu finden.</p></ul><p>Zu den Vorteilen der Aktualisierung des XDM-Schemas gehören:</p><ul><li>Die Aktualisierung Ihres Schemas ist ein zeitaufwendiger Prozess, der erforderlich ist, bevor Sie mit dem Senden von Daten an Customer Journey Analytics beginnen.</li></ul> | Keine |

{style="table-layout:auto"}

+++

## Senden Sie als Nächstes Daten an Adobe Experience Platform

Nachdem Sie die oben genannten Informationen zur Auswahl eines Migrationspfads verwendet haben, erfahren Sie, wie Sie [Daten an Adobe Experience Platform senden](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) abhängig vom ausgewählten Migrationspfad.
