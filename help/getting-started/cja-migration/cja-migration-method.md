---
title: Customer Journey Analytics-Migrationsmethode auswählen
description: Erfahren Sie mehr über die Vorteile und Nachteile der möglichen Migrationsmethoden bei der Migration zum Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 3e362a62d2ffd6d15e3028706e3704264df80222
workflow-type: tm+mt
source-wordcount: '2026'
ht-degree: 3%

---

# Schritt 2: Customer Journey Analytics-Migrationsmethode auswählen

+++ Erweitern Sie diesen Abschnitt, um zu sehen, wo die Informationen auf dieser Seite in den größeren Migrationsprozess passen. Stellen Sie sicher, dass alle vorherigen Migrationsschritte abgeschlossen sind.

Bevor Sie mit diesem Abschnitt fortfahren, stellen Sie zunächst sicher, dass Sie alle vorherigen Migrationsaufgaben abgeschlossen haben.

Die Informationen auf dieser Seite beziehen sich auf Schritt 2, wie in der folgenden Tabelle hervorgehoben:

| Migrationsaufgabe | Details |
|---------|----------|
| **Schritt 1: [Erste Schritte mit der Migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Erfahren Sie mehr über die Vorteile der Migration zu Adobe Analytics und den grundlegenden Migrationsprozess. |
| <span class="preview">**Schritt 2: [Migrationsmethode auswählen](/help/getting-started/cja-migration/cja-migration-method.md)**</span> | <span class="preview">Für die Migration zum Customer Journey Analytics stehen verschiedene Methoden zur Verfügung. Wählen Sie je nach aktueller Adobe Analytics-Umgebung und langfristigen Zielen Ihres Unternehmens die für Ihr Unternehmen am besten geeignete Methode aus.</span> |
| **Schritt 3: [Daten an Adobe Experience Platform senden](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Der Prozess zum Senden von Daten an Adobe Experience Platform hängt von der in Schritt 1 ausgewählten Migrationsmethode ab. |
| **Schritt 4: [Zuordnen von Daten zum XDM-Schema](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM-Schemata](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) werden in Adobe Experience Platform verwendet, um die Datenstruktur konsistent und wiederverwendbar zu beschreiben. Durch die systemübergreifende einheitliche Definition von Daten wird es einfacher, deren Bedeutung beizubehalten und somit Wert aus Daten zu ziehen.<p>Die meisten Migrationsmethoden erfordern, dass Sie entweder ein neues XDM-Schema erstellen oder Ihr bestehendes Adobe Analytics-Schema mithilfe der Datastream-Zuordnung XDM zuordnen.</p> |
| **Schritt 5: [Verlaufsdaten beibehalten](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | Die meisten Unternehmen müssen ihre historischen Adobe Analytics-Daten für einen bestimmten Zeitraum aufbewahren. Dazu stehen verschiedene Optionen zur Verfügung. |
| **Schritt 6: [Benutzereinstieg planen](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Sie sollten Ihren Benutzern ausreichend Zeit (3 - 6 Monate) geben, um sich mit den wichtigsten Unterschieden von Analysis Workspace im Customer Journey Analytics vertraut zu machen. |
| **Schritt 7: [Portieren der Nutzung der Reporting-API](/help/getting-started/cja-migration/cja-migration-api.md)** | Die Customer Journey Analytics Reporting-API weist dasselbe Format auf, verwendet jedoch einen anderen Endpunkt. Portieren Sie die Nutzung der Reporting-API von der Adobe Analytics Reporting-API an die Customer Journey Analytics-Reporting-API. |
| **Schritt 8: [Ersetzen von Daten-Feeds und Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Entscheiden Sie, wie Sie die unter Customer Journey Analytics verfügbaren Exportoptionen verwenden werden, um die Daten-Feeds- und Data Warehouse-Funktionen zu ersetzen, die Sie in Adobe Analytics verwendet haben. |
| **Schritt 9: [Migrieren von Projekten und Komponenten](/help/getting-started/cja-migration/cja-migration-projects.md)** | Im Bereich Komponentenmigration in Adobe Analytics können Sie Projekte und die zugehörigen Komponenten von Adobe Analytics auf Customer Journey Analytics migrieren. |

{style="table-layout:auto"}

+++

Nachdem Sie sich für eine Migration zu Customer Journey Analytics entschieden haben, müssen Sie die optimale Migrationsmethode für Ihr Unternehmen bestimmen.

Die Methode, die Sie für die Migration von Adobe Analytics zu Customer Journey Analytics wählen, hängt von den folgenden Faktoren ab:

* Ihre vorhandene Adobe Analytics-Implementierung

* Ihre zukünftigen Ziele

Verwenden Sie die Informationen auf dieser Seite, um zu bestimmen, welche Customer Journey Analytics-Migrationsmethode am besten mit der aktuellen Implementierung und den zukünftigen Zielen Ihres Unternehmens übereinstimmt.

Die folgenden Abschnitte sollten sequenziell gelesen werden, um die optimale Migrationsmethode für Ihr Unternehmen zu bestimmen:

1. Erstens: [die verfügbaren Migrationsmethoden verstehen](#understand-migration-methods).

1. Dann [beurteilen, welche Migrationsmethoden Ihnen zur Verfügung stehen](#assess-the-migration-methods-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. Und schließlich: [Abwägen der Vor- und Nachteile jeder Migrationsmethode](#weigh-the-advantages-and-disadvantages-of-the-migration-methods-available-to-you).

## Migrationsmethoden

Für die Migration von Adobe Analytics zu Customer Journey Analytics gibt es verschiedene Migrationsmethoden.

Im Allgemeinen unterscheidet sich jede Migrationsmethode von dem Aufwand, der für die Ausführung der Migration erforderlich ist, sowie von der langfristigen Rentabilität, die nach Abschluss der Migration erzielt wird.

In der folgenden Tabelle sind die einzelnen Migrationsmethoden, ihr Aufwand und ihre langfristige Rentabilität aufgeführt:

| Migrationsmethode | Aufwand | Langfristige Rentabilität |
|---------|----------|---------|
| **Neue Implementierung des Web SDK**</br> Sie können eine neue Adobe Experience Platform Web SDK-Implementierung durchführen, um mit dem Senden von Daten an Adobe Experience Platform Edge Network zu beginnen. <!-- what is the correct branding -->. <p>Für Unternehmen, die noch nicht im Web SDK arbeiten, ist diese Migrationsmethode möglicherweise die einfachste Methode, um Daten in Edge Network zu übertragen (was die geringste Anzahl von Schritten erfordert). Da jedoch alle Aufgaben vorab erledigt sind (z. B. Erstellen des XDM-Schemas), ist zunächst mehr Aufwand erforderlich.</p><p>Die grundlegenden Schritte sind:</p><ol><li>Erstellen Sie ein XDM-Schema für Ihre Organisation.</li><li>Implementieren Sie das Web SDK.</li><li>Senden von Daten an Platform.</li></ol> | Hoch | Hoch |
| **Migrieren der Adobe Analytics-Implementierung zur Verwendung des Web SDK**</br> Wenn Ihre Adobe Analytics-Implementierung AppMeasurement oder die Analytics-Erweiterung ist, können Sie sie migrieren, um das Adobe Experience Platform Web SDK zu verwenden und mit dem Senden von Daten an Edge Network zu beginnen, bevor sie an Customer Journey Analytics gesendet werden. <!-- what else? --><p>Dies ist die einfachste und reibungsloseste Methode, um Daten an Edge Network zu übertragen. Sie erfordert zwar mehr Schritte, bietet aber einen methodischeren Übergang mit greifbareren Meilensteinen.</p><p>Die grundlegenden Schritte sind:</p><ol><li>Verschieben Sie Ihre vorhandene Adobe Analytics-Implementierung in das Web SDK und überprüfen Sie, ob dort alles funktioniert.</li><li>Erstellen Sie ein XDM-Schema für Ihre Organisation so, wie Sie Zeit haben.</li><li>Verwenden Sie die Datenstream-Zuordnung, um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen.</li><li>Senden von Daten an Platform.</li></ol> | Moderieren | Hoch |
| **Konfigurieren der vorhandenen Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Customer Journey Analytics**</br> Wenn Ihre Adobe Analytics-Implementierung bereits das Web SDK verwendet, können Sie mit minimalem Aufwand mit dem Senden von Daten an Customer Journey Analytics beginnen.<p>Bevor Sie Daten an Customer Journey Analytics senden, sollten Sie erwägen, Ihr Adobe Analytics-Schema auf die spezifischen Anforderungen Ihres Unternehmens und anderer von Ihnen verwendeter Platform-Anwendungen zu aktualisieren.</p><p>Die grundlegenden Schritte sind:</p><ol><li>Senden Sie Daten an Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Optional) Erstellen Sie ein XDM-Schema für Ihre Organisation, da Sie Zeit haben.</li><li>(Bedingt) Wenn Sie ein XDM-Schema erstellt haben, verwenden Sie die Datenstream-Zuordnung, um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen.</li></ol> | Niedrig | Hoch |
| **Analytics Source Connector**</br> Wenn Ihre Adobe Analytics-Implementierung AppMeasurement oder die Analytics-Erweiterung ist, können Sie mit dem Senden von Daten an eine Datenansicht in Customer Journey Analytics beginnen.<p>Dies ist der einfachste Weg, Daten an Customer Journey Analytics zu übertragen, aber langfristig ist dies die am wenigsten praktikable Methode.</p> | Niedrig | Niedrig |

{style="table-layout:auto"}

Verwenden Sie das folgende Diagramm, um zu visualisieren, wo jede Migrationsmethode im Hinblick auf Aufwand und langfristige Lebensfähigkeit auf das Spektrum fällt:

![cja-Migrationsmethoden](assets/cja-migration-methods.png)

## Prüfen Sie die verfügbaren Migrationsmethoden auf Grundlage Ihrer aktuellen Adobe Analytics-Implementierung.

Es sind nicht alle Migrationsmethoden für jeden Adobe Analytics-Implementierungstyp verfügbar.

Verwenden Sie die folgenden Informationen, um zu verstehen, welche Migrationsmethode für Ihr Unternehmen am besten geeignet ist.

Wenden Sie sich an Ihren Adobe-Support-Mitarbeiter, wenn Sie spezifischere Ratschläge, Anleitungen oder Support benötigen.

| Adobe Analytics-Implementierung | Verfügbare Migrationsmethoden |
|---------|----------|
| AppMeasurement | <ul><li>Neue Implementierung des Web SDK</li><li>Migrieren von Adobe Analytics zum Web SDK</li><li>Analytics Source Connector</li></ul> |
| Adobe Analytics-Erweiterung | <ul><li>Neue Implementierung des Web SDK</li><li>Migrieren von Adobe Analytics zum Web SDK</li><li>Analytics Source Connector</li></ul> |
| Web SDK | <ul><li>Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Customer Journey Analytics</li></ul> |

{style="table-layout:auto"}

## Abwägen der Vor- und Nachteile der Ihnen zur Verfügung stehenden Migrationsmethoden

Die Vor- und Nachteile einer bestimmten Migrationsmethode unterscheiden sich je nach Ihrer bestehenden Adobe Analytics-Implementierung.

Bevor Sie die unten stehenden Informationen verwenden, um zu ermitteln, welche Migrationsmethode für Sie geeignet ist, lesen Sie die Informationen unter [Migrationsmethoden](#understand-migration-methods) wenn Sie es noch nicht getan haben.

### Für Adobe Analytics-Implementierungen mit: AppMeasurement und Adobe Analytics-Erweiterung

Die folgende Tabelle zeigt die verfügbaren Migrationsmethoden für Organisationen, die Adobe Analytics mit AppMeasurement oder der Adobe Analytics-Erweiterung implementiert haben:

| Migrationsmethode | Vorteile | Nachteile |
|---------|----------|---------|
| **Neue Implementierung des Web SDK** | <ul><li>Verwendet ein XDM-Schema, ein flexibles Schema, um die erforderlichen Felder zu definieren, und nur die relevanten Felder (ermöglicht Ihnen, von der Adobe Analytics Experience Event Field-Gruppe weg zu navigieren)</li><li>Nicht von der Adobe Analytics-Nomenklatur abhängig (Prop, eVar, Ereignis usw.)</li><li>Keine Längenbeschränkung (100 Zeichen für Props)</li><li>Leistungsstarke Berichterstellung und Datenverfügbarkeit, da Adobe Experience Platform zur Leistungsoptimierung entwickelt wurde [Anwendungsfälle für die Echtzeit-Personalisierung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=de)</li><li>Zukunftssicher (wird alle neuen Funktionen erhalten)</li><li>Tags für die Adobe Experience Cloud-Datenerfassung zwischen anderen Experience Cloud-Produkten zusammenfassen (AJO, RTCDP usw.)</li><li>[Erstanbieter-Geräte-IDs](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=de) für eine genauere Besucheridentifizierung</li></ul> | <ul><li>Die zeitaufwendigste und anspruchsvollste Migrationsmethode<p>Muss das vollständige Schema in XDM neu erstellen, bevor Sie mit der Implementierung des Web SDK beginnen können</p></li></ul> |
| **Migrieren von Adobe Analytics zum Web SDK** | <ul><li>Behält Regeln und Datenelemente bei, die bereits in Ihrer Adobe Analytics-Implementierung konfiguriert sind.</li><li>Ermöglicht den Wechsel zum Web SDK ohne Beeinträchtigung der bestehenden Adobe Analytics-Berichterstellung.</li><li>Bietet Flexibilität beim Erstellen eines XDM-Schemas für Ihre Organisation zu einem späteren Zeitpunkt: ein flexibles Schema zur Definition von erforderlichen Feldern und nur der relevanten Felder.</br>Die Adobe Analytics Experience Event Field-Gruppe ist in Customer Journey Analytics nicht erforderlich. <!-- With the new implementation, you're double-counting with 2 implementation; with the migration, you're double-counting, but both of them are through Edge Network. --></li><li>Nicht von der Adobe Analytics-Nomenklatur abhängig (Prop, eVar, Ereignis usw.)</li><li>Keine Längenbeschränkung (100 Zeichen für Props)</li><li>Leistungsstarke Berichterstellung und Datenverfügbarkeit, da Adobe Experience Platform zur Leistungsoptimierung entwickelt wurde [Anwendungsfälle für die Echtzeit-Personalisierung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=de)</li><li>Zukunftssicher (wird alle neuen Funktionen erhalten)</li><li>Tags für die Adobe Experience Cloud-Datenerfassung zwischen anderen Experience Cloud-Produkten zusammenfassen (AJO, RTCDP usw.)</li><li>[Erstanbieter-Geräte-IDs](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=de) für eine genauere Besucheridentifizierung</li></ul> | <ul><li>Muss zu einem späteren Zeitpunkt mit einem XDM-Schema konform sein, wobei die Datastream-Zuordnung verwendet wird.</li><li>Informiert einige technische Schulden. Beispielsweise kann der alte AppMeasurement- oder Analytics-Erweiterungscode beibehalten werden. </li></ul> |
| **Analytics Source Connector** | <ul><li>Wenigste zeitaufwendige und anspruchsvolle Migrationsmethode. <p>Daten werden schnell und mit minimalem Aufwand zu Customer Journey Analytics migriert</p></li></ul> | <ul><li>Daten werden nicht an Edge Network gesendet und können nicht für andere Adobe Experience Platform-Anwendungen freigegeben werden. Sie sind auf Customer Journey Analytics beschränkt.<li>Schwierigkeit, in Zukunft zum Web SDK zu wechseln</li><li>Verwendet die Feldergruppe &quot;Analytics-Erlebnisereignis&quot;in Ihrem Schema.</br>Diese Feldergruppe fügt viele Adobe Analytics-Ereignisse hinzu, die in Ihrem Customer Journey Analytics-Schema nicht benötigt werden.  Dies kann zu einem übersichtlicheren, komplexeren Schema führen, als es sonst für das Customer Journey Analytics erforderlich wäre.</li><li>Höchste Ebene von [Latenz](/help/admin/guardrails.md#latencies) alle Implementierungsmethoden</li></ul> |

{style="table-layout:auto"}

### Für Adobe Analytics-Implementierungen mit: Web SDK

Die folgende Tabelle zeigt die verfügbaren Migrationsmethoden für Organisationen, die Adobe Analytics mit dem Web SDK implementiert haben:

| Migrationsmethode | Vorteile | Nachteile |
|---------|----------|---------|
| **Konfigurieren der Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Customer Journey Analytics** | Dies ist die bevorzugte Migrationsmethode, wenn Ihre Adobe Analytics-Implementierung bereits das Web SDK verwendet. <p>Bei Verwendung dieser Implementierungsmethode können Sie entscheiden, ob Sie Ihr vorhandenes Adobe Analytics-Schema verwenden möchten oder ob Sie das XDM-Schema aktualisieren können, um es besser an die Anforderungen Ihres Unternehmens anzupassen, wenn Sie mit der Verwendung anderer Platform-Anwendungen beginnen.</p><p>**Verwenden des Adobe Analytics-Schemas**</p><p>Vorteile der Verwendung des Adobe Analytics-Schemas:</p><ul><li>Erleichterung der Migration<p>Wenn Sie mit dem Adobe Experience Platform Web SDK bereits Daten an Adobe Analytics senden, können Sie Ihrem Datenspeicher einen zusätzlichen Dienst hinzufügen, um Daten an Adobe Experience Platform zu senden (der dann in Ihrer Customer Journey Analytics-Konfiguration verwendet werden kann).</p></li></ul><p>Die Verwendung des Adobe Analytics-Schemas hat folgende Nachteile:</p><ul><li>Die Verwendung des Adobe Analytics-Schemas schränkt Sie zwar nicht in Bezug auf die Verwendung mit anderen Platform-Anwendungen ein, führt aber zu einem Schema, das komplexer ist, als es sonst sein könnte. Dies liegt daran, dass das Adobe Analytics-Schema viele Adobe Analytics-spezifische Objekte enthält, die wahrscheinlich nicht von Ihrem Unternehmen verwendet werden.<p>Wenn Änderungen am Schema erforderlich sind, müssen Sie Tausende nicht verwendeter Felder durchlaufen, um das zu aktualisierende Feld zu finden.</p></li></ul><p>**Verwenden des XDM-Schemas**</p><p>Vorteile der Aktualisierung des XDM-Schemas sind:</p><ul><li>Ein optimiertes Schema, das auf die Anforderungen Ihres Unternehmens und die spezifischen Platform-Anwendungen zugeschnitten ist, die Sie verwenden.</li><p>Wenn Änderungen am Schema erforderlich sind, müssen Sie nicht Tausende nicht verwendeter Felder durchlaufen, um das zu aktualisierende Feld zu finden.</p></ul><p>Zu den Vorteilen der Aktualisierung des XDM-Schemas gehören:</p><ul><li>Die Aktualisierung Ihres Schemas ist ein zeitaufwendiger Prozess, der erforderlich ist, bevor Sie mit dem Senden von Daten an Customer Journey Analytics beginnen.</li></ul> | Keine |

{style="table-layout:auto"}

## Senden Sie als Nächstes Daten an Adobe Experience Platform

Nachdem Sie die oben genannten Informationen zur Auswahl einer Migrationsmethode verwendet haben, erfahren Sie, wie Sie [Daten an Adobe Experience Platform senden](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) abhängig von der gewählten Migrationsmethode.
