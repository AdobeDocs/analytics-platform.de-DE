---
title: Weiterentwicklung von Adobe Analytics
description: Schritte zum Umwandeln von Adobe Analytics-Daten in Customer Journey Analytics-Daten
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 37d9e8e84e1982d63f2173601d75f0b7fa552b73
workflow-type: tm+mt
source-wordcount: '1495'
ht-degree: 94%

---

# Weiterentwicklung von Adobe Analytics

Wenn sich Ihr Unternehmen entschließt, Customer Journey Analytics zu verwenden, sollten Sie sich mit diesen Schritten vertraut machen, um Ihre Daten vorzubereiten, und über die wichtigen Unterschiede zwischen den beiden Technologien Bescheid wissen. Dieser Artikel richtet sich an Administratoren.

## Vorbereiten Ihrer Daten

Die Vorbereitung Ihrer Adobe Analytics-Daten auf einen nahtlosen Wechsel zu Customer Journey Analytics ist für die Datenintegrität und die Konsistenz der Berichte von entscheidender Bedeutung.

### 1. Identitäten erfassen {#identities}

Die vielleicht wichtigste Komponente beim Verständnis einer Customer Journey ist, zu wissen, wer bei jedem Schritt der Kunde ist. Customer Journey Analytics verfügt über eine Kennung über alle Kanäle hinweg und für die entsprechenden Daten, die es ermöglicht, mehrere Quellen in Customer Journey Analytics einander zuzuordnen.
Beispiele für Identitäten sind Kunden-ID, Konto-ID oder E-Mail-ID. Für jede ID gilt Folgendes unabhängig von der Identität (es kann auch mehrere Identitäten geben):

* Die ID ist vorhanden oder kann zu allen Datenquellen hinzugefügt werden, die in Customer Journey Analytics integriert werden sollen
* Die ID wird in jeder Datenzeile angegeben
* Die ID enthält keine persönlich identifizierbare Informationen. Wenden Sie Hashing auf alle sensiblen Elemente an.
* Die ID verwendet dasselbe Format für alle Quellen (gleiche Länge, gleiche Hashing-Methode usw.)

In Datensätzen wie Adobe Analytics ist möglicherweise nicht in jeder Datenzeile eine Identität vorhanden, aber eine sekundäre Identität schon. In diesem Fall kann die Cross-Channel-Analyse (früher als „Zuordnung“ oder „Stitching“ bezeichnet) verwendet werden, um die Lücke zwischen Zeilen zu schließen, wenn eine Kundin oder ein Kunde nur durch die ECID identifiziert wird und wenn eine Identität erfasst wird (z. B. bei der Authentifizierung einer Person). [Weitere Informationen](../stitching/overview.md).

### 2. Anpassen der Variablen {#variables}

Die einfachste Methode, Adobe Analytics-Daten in Customer Journey Analytics-Daten umzuwandeln, besteht darin, eine [globale Report Suite](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=de) mithilfe des [Adobe Analytics-Quell-Connectors](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de) in Experience Platform aufzunehmen. Dieser Connector ordnet Ihre Adobe Analytics-Variablen direkt einem XDM-Schema und -Datensatz in Experience Platform zu, die wiederum einfach mit Customer Journey Analytics verbunden werden können.

Eine vollständige globale Report Suite ist nicht in jedem Fall für eine Implementierung möglich. Wenn Sie planen, mehrere Report Suites in Customer Journey Analytics zu integrieren, haben Sie zwei Möglichkeiten:

* Planen Sie im Voraus, damit Sie die Variablen in diesen Report Suites in Einklang bringen können. Beispielsweise kann eVar1 in Report Suite 1 auf [!UICONTROL Seite] verweisen. In Report Suite 2 kann eVar1 auf [!UICONTROL Interne Kampagne] verweisen. Wenn diese Variablen in Customer Journey Analytics importiert werden, werden sie in einer gemeinsamen eVar1-Dimension vermischt, was zu möglicherweise verwirrenden und ungenauen Berichten führt.

* Verwenden Sie die Funktion der [Datenvorbereitung](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de) zum Zuordnen von Variablen. Es ist zwar einfacher, wenn alle Report Suites denselben Variablenaufbau verwenden, dies ist aber nicht erforderlich, wenn Sie die neue [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de#mapping)-Funktion von Experience Platform verwenden. Damit können Sie eine Variable anhand ihres zugeordneten Werts referenzieren, der sich auf der Ebene des Datenstroms (oder der Eigenschaft) befindet.

Wenn Sie den Wechsel zu einer globalen Report Suite aufgrund von Problemen mit [!UICONTROL überschrittenen eindeutigen Werten] oder [!UICONTROL geringem Traffic] vermieden haben, beachten Sie, dass es in Customer Journey Analytics keine [Kardinalitätsbeschränkungen für eine Dimension](/help/components/dimensions/high-cardinality.md) gibt. Dadurch können alle eindeutigen Werte angezeigt und gezählt werden.

Im Folgenden finden Sie ein Anwendungsbeispiel für das [Kombinieren von Report Suites mit verschiedenen Schemata](/help/use-cases/aa-data/combine-report-suites.md).

### 3. Marketing-Kanäle (erneut) konfigurieren {#marketing-channels}

Herkömmliche Einstellungen für Marketing-Kanäle in Adobe Analytics funktionieren in Customer Journey Analytics nicht auf die gleiche Weise. Dies hat zwei Gründe:

* Die Verarbeitungsstufe für die in Adobe Experience Platform aufgenommenen Adobe Analytics-Daten

* Der Berichtscharakter von Customer Journey Analytics

Adobe hat [aktualisierte Best Practices für die Implementierung von Marketing-Kanälen](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=de) veröffentlicht. Diese aktualisierten Empfehlungen helfen Ihnen dabei, die bereits in Adobe Analytics vorhandenen Funktionen mit Attribution IQ optimal zu nutzen. Diese werden Ihnen auch bei der Umstellung auf Customer Journey Analytics helfen.

Mit der Einführung von [abgeleiteten Feldern](../data-views/derived-fields/derived-fields.md) im Rahmen der Datenansichten von Customer Journey Analytics werden Marketing-Kanäle auch zerstörungsfrei und rückwirkend unterstützt, indem die Vorlage [Marketing-Kanal-Funktion](../data-views/derived-fields/derived-fields.md#function-templates) verwendet wird.

### 4. Entscheidung zwischen Analytics-Quell-Connector und Experience Platform SDKs {#connector-vs-sdk}

Adobe Analytics-Kundinnen und -Kunden können ihre Report Suites in Adobe Experience Platform und Customer Journey Analytics ganz einfach mit dem Analytics-Quell-Connector nutzen. Informationen zur Verwendung des Analytics-Quell-Connectors finden Sie in der Schnellstartanleitung zum [Aufnehmen von Daten aus Adobe Analytics und ihre Verwendung in Customer Journey Analytics](../data-ingestion/analytics.md). Siehe auch [Erstellen einer Adobe Analytics-Quellverbindung in der Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de), um weitere Informationen zu erhalten.

Im Zuge der Weiterentwicklung der [Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=de)-Datenerfassung werden Sie wahrscheinlich entweder auf das [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=de) oder das [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html?lang=de) mit dem Adobe Experience Platform Edge Network migrieren. Während eine typische Implementierung der SDKs Daten an Adobe Analytics sendet, gibt es eine neue Möglichkeit, Daten direkt an Adobe Experience Platform zu senden. Diese Daten können dann in Customer Journey Analytics aufgenommen werden, während gleichzeitig die an Adobe Analytics gesendeten Daten beibehalten werden.

Diese Methode erweitert die Möglichkeiten für die Datenerfassung deutlich: Die Anzahl der Felder ist nicht mehr beschränkt und es besteht keine Notwendigkeit mehr, Datenelemente Props, eVars und Ereignissen wie in Analytics zuzuordnen. Sie können unbegrenzte Schemaelemente verschiedener Typen verwenden und sie mithilfe von Customer Journey Analytics-[Datenansichten](/help/data-views/data-views.md) unterschiedlich darstellen. Die Geschwindigkeit der Datenverfügbarkeit steigt, wenn die Daten direkt an Adobe Experience Platform gesendet werden, da die Zeit für die Datenverarbeitung über Adobe Analytics entfällt.

**Vorteile der Verwendung von Experience Platform-SDKs:**

* Flexibles Schema zur Definition von erforderlichen Feldern
* Nicht von der Adobe Analytics-Nomenklatur abhängig (Prop, eVar, Ereignis usw.)
* Keine Längenbeschränkung (100 Zeichen für Props)
* Schnellere Datenverfügbarkeit in Adobe Experience Platform, um [Anwendungsfälle der Echtzeit-Personalisierung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=de) zu unterstützen
* [Erstanbieter-Geräte-IDs](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=de) für eine genauere Besucheridentifizierung

**Nachteile der Verwendung von Experience Platform-SDKs**

Die folgenden Adobe Analytics-Funktionen oder -Komponenten werden nicht unterstützt:

* Bot-Filterung
* Messung von Streaming-Medien
* Livestream oder Livestream-Trigger

### 5. Zuordnen von Komponenten und Projekten von Adobe Analytics zu Customer Journey Analytics

Adobe Analytics-Administratoren können Adobe Analytics-Projekte und die zugehörigen Komponenten auf Customer Journey Analytics migrieren.

Der Migrationsprozess umfasst:

* Erstellen Sie Adobe Analytics-Projekte im Customer Journey Analytics neu.

* Zuordnen von Dimensionen und Metriken aus Adobe Analytics Report Suites zu Dimensionen und Metriken in Customer Journey Analytics-Datenansichten.

Bevor Sie mit der Migration beginnen, müssen Sie [Vorbereiten der Migration von Komponenten und Projekten von Adobe Analytics zu Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=de).

Nachdem Sie alle notwendigen Vorbereitungen getroffen haben, können Sie [Migrieren von Komponenten und Projekten von Adobe Analytics zum Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html?lang=de).

## Einige wichtige Unterschiede

### Machen Sie sich vertraut mit der Verarbeitung zur Berichtslaufzeit {#report-time}

Das Reporting in Adobe Analytics beruht auf einer erheblichen Datenvorverarbeitung, um Ergebnisse zu generieren, wie die Persistenz in [!UICONTROL eVars]. Im Gegensatz dazu führt Customer Journey Analytics (CJA) diese Berechnungen zur Berichtslaufzeit aus.

[!UICONTROL Berichtszeitverarbeitung] eröffnet die Möglichkeit, rückwirkende Einstellungen anzuwenden und mehrere Versionen der Variablenpersistenz zu erstellen, ohne die Art der Erfassung der zugrunde liegenden Daten ändern zu müssen.

Diese Änderung führt zu gewissen Unterschieden in der Verwendung von Daten zur Berichtserstellung, insbesondere bei Variablen, die länger gültig sind. Sie können beurteilen, wie sich die Verarbeitung zur Berichtslaufzeit auf Ihr Reporting auswirken kann, indem Sie eine [Virtual Report Suite](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=de) verwenden.

### Identifizieren Sie wichtige Segmente und berechnete Metriken {#segments-calcmetrics}

Adobe Analytics-Segmente (in Customer Journey Analytics als [!UICONTROL Filter] bezeichnet) und berechnete Metriken sind nicht mit Customer Journey Analytics kompatibel. In vielen Fällen können diese Komponenten in Customer Journey Analytics mithilfe der neuen Schemata und verfügbaren Daten neu erstellt werden.

Um den Wechsel zwischen den Systemen für Benutzer so reibungslos wie möglich zu gestalten, führen Sie folgende Maßnahmen aus:

1. Identifizieren Sie die wichtigsten dieser Komponenten.

2. Dokumentieren Sie ihre Definitionen

3. Ermitteln Sie, welche Felder in den Daten erforderlich sind, um sie in Customer Journey Analytics als [Filter](/help/components/filters/filters-overview.md) und [berechnete Metriken](/help/components/calc-metrics/calc-metr-overview.md) zu replizieren.

Hier sind einige Videos, die Ihnen dabei helfen:

* [Verschieben von Adobe Analytics-Segmenten nach Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=de)

* [Verschieben der berechneten Metriken von Adobe Analytics nach Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/calc-metrics/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=de)

### Weitere Überlegungen

* Durch die leistungsstarken Customer Journey Analytics-Datenansichten haben Sie bei der Definition von Metriken und Dimensionen in Customer Journey Analytics deutlich mehr Flexibilität. Sie können beispielsweise den Wert einer Dimension als Definition einer Metrik verwenden. [Weitere Informationen](/help/use-cases/data-views/data-views-usecases.md)

* Wenn Sie einen benutzerdefinierten Kalender in Adobe Analytics festgelegt haben, verfügen Sie in Customer Journey Analytics über ähnliche [benutzerdefinierte Kalenderfunktionen](/help/components/date-ranges/custom-date-ranges.md). Sie müssen sicherstellen, dass Ihr Kalender korrekt definiert ist.

* In Customer Journey Analytics können Sie eine benutzerdefinierte maximale Wartezeit für Besuche/Sitzungen definieren sowie eine Metrik festlegen, durch die eine neue Sitzung gestartet wird. Sie können Datenansichten mit verschiedenen Sitzungsdefinitionen erstellen, um Einblicke zu erhalten, die weit darüber hinausgehen, was in Adobe Analytics möglich war. Diese Funktion kann besonders für Datensätze im Mobile-Bereich von Nutzen sein.

* Erwägen Sie die Bereitstellung eines Datenwörterbuchs für Ihre Benutzer – oder erweitern Sie das SDR, um den Experience Platform-Feldnamen für Schemaelemente einzuschließen.

## Nächste Schritte

Wenn Sie nach dem Wechsel zu Customer Journey Analytics Datendiskrepanzen feststellen, können Sie Ihre ursprünglichen Adobe Analytics-Daten mit den aktuellen Adobe Analytics-Daten in Customer Journey Analytics vergleichen. [Weitere Informationen](/help/troubleshooting/compare.md)
