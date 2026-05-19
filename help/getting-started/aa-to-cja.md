---
title: Weiterentwicklung von Adobe Analytics
description: Schritte zum Umwandeln von Adobe Analytics-Daten in Customer Journey Analytics-Daten
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
autotag-review: '2026-05-19T06:31:08.010Z'
TQID: 'https://experienceleague.adobe.com/q1l52F-xc4rXHXJB-2aMYUVd1ySLzyWbZhVAja92ojQ'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cb6c7d24-631f-46e5-9e39-3a2705f73962id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11id: d00e9f03-e50b-4162-b143-0c0817c937c2id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 1183
ht-degree: 100%

---

# Weiterentwicklung von Adobe Analytics

## Vorbereiten Ihrer bestehenden Daten

Die Vorbereitung Ihrer Adobe Analytics-Daten auf einen nahtlosen Wechsel zu Customer Journey Analytics ist für die Datenintegrität und die Konsistenz der Berichte von entscheidender Bedeutung.

### Sammeln von Identitäten

Die vielleicht wichtigste Komponente beim Verständnis einer Customer Journey ist, zu wissen, wer bei jedem Schritt der Kunde ist. Customer Journey Analytics verfügt über eine Kennung über alle Kanäle hinweg und für die entsprechenden Daten, die es ermöglicht, mehrere Quellen in Customer Journey Analytics einander zuzuordnen.
Beispiele für Identitäten sind Kunden-ID, Konto-ID oder E-Mail-ID. Für jede ID gilt Folgendes unabhängig von der Identität (es kann auch mehrere Identitäten geben):

* Die ID ist vorhanden oder kann zu allen Datenquellen hinzugefügt werden, die in Customer Journey Analytics integriert werden sollen
* Die ID wird in jeder Datenzeile angegeben
* Die ID enthält keine persönlich identifizierbare Informationen. Wenden Sie Hashing auf alle sensiblen Elemente an.
* Die ID verwendet dasselbe Format für alle Quellen (gleiche Länge, gleiche Hashing-Methode usw.)

In Datensätzen wie Adobe Analytics ist möglicherweise nicht in jeder Datenzeile eine Identität vorhanden, aber eine sekundäre Identität schon. In diesem Fall kann die [Cross-Channel-Analyse (früher als „Zuordnung“ oder „Stitching“ bezeichnet)](/help/stitching/overview.md) verwendet werden, um die Lücke zwischen Zeilen zu schließen, wenn eine Kundin oder ein Kunde nur durch die ECID identifiziert wird und wenn eine Identität erfasst wird (z. B. bei der Authentifizierung einer Person).

### Anpassen Ihrer Variablen

Die einfachste Methode, Adobe Analytics-Daten in Customer Journey Analytics-Daten umzuwandeln, ist die Aufnahme einer [globalen Report Suite](https://experienceleague.adobe.com/de/docs/analytics/implementation/prepare/global-rs) in Experience Platform mit dem [Analytics-Quell-Connectors](https://experienceleague.adobe.com/de/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics). Dieser Connector ordnet Ihre Adobe Analytics-Variablen direkt einem XDM-Schema und -Datensatz in Experience Platform zu, die wiederum einfach mit Customer Journey Analytics verbunden werden können.

Eine vollständige globale Report Suite ist nicht in jedem Fall für eine Implementierung möglich. Wenn Sie planen, mehrere Report Suites in Customer Journey Analytics zu integrieren, haben Sie zwei Möglichkeiten:

* Planen Sie im Voraus, damit Sie die Variablen in diesen Report Suites in Einklang bringen können. Beispielsweise kann eVar1 in Report Suite 1 auf [!UICONTROL Seite] verweisen. In Report Suite 2 kann eVar1 auf [!UICONTROL Interne Kampagne] verweisen. Wenn diese Variablen in Customer Journey Analytics importiert werden, werden sie in einer gemeinsamen eVar1-Dimension vermischt, was zu möglicherweise verwirrenden und ungenauen Berichten führt.

* Verwenden Sie die Funktion der [Datenvorbereitung](https://experienceleague.adobe.com/de/docs/experience-platform/data-prep/home) zum Zuordnen von Variablen. Es ist zwar einfacher, wenn alle Report Suites denselben Variablenaufbau verwenden, dies ist aber nicht erforderlich, wenn Sie die neue [Data Prep](https://experienceleague.adobe.com/de/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)-Funktion von Experience Platform verwenden. Damit können Sie eine Variable anhand ihres zugeordneten Werts referenzieren, der sich auf der Ebene des Datenstroms (oder der Eigenschaft) befindet.

Wenn Sie den Wechsel zu einer globalen Report Suite aufgrund von Problemen mit [!UICONTROL überschrittenen eindeutigen Werten] oder [!UICONTROL geringem Traffic] vermieden haben, beachten Sie, dass es in Customer Journey Analytics keine [Kardinalitätsbeschränkungen für eine Dimension](/help/components/dimensions/high-cardinality.md) gibt. Dadurch können alle eindeutigen Werte angezeigt und gezählt werden.

Im Folgenden finden Sie ein Anwendungsbeispiel für das [Kombinieren von Report Suites mit verschiedenen Schemata](/help/use-cases/aa-data/combine-report-suites.md).

### (Erneutes) Konfigurieren Ihrer Marketing-Kanäle

Herkömmliche Einstellungen für Marketing-Kanäle in Adobe Analytics funktionieren in Customer Journey Analytics nicht auf die gleiche Weise. Für diesen Unterschied gibt es zwei Gründe:

* Die Verarbeitungsstufe für die in Adobe Experience Platform aufgenommenen Adobe Analytics-Daten

* Der Berichtscharakter von Customer Journey Analytics

Adobe hat [aktualisierte Best Practices für die Implementierung von Marketing-Kanälen](https://experienceleague.adobe.com/de/docs/analytics/components/marketing-channels/mchannel-best-practices) veröffentlicht. Diese aktualisierten Empfehlungen helfen Ihnen dabei, die meisten der bereits in Adobe Analytics vorhandenen Funktionen mit erweiterter Attribution optimal zu nutzen. Die Empfehlungen helfen Ihnen auch bei der Umstellung auf Customer Journey Analytics.

Mit der Einführung von [abgeleiteten Feldern](../data-views/derived-fields/derived-fields.md) im Rahmen der Datenansichten von Customer Journey Analytics werden Marketing-Kanäle auch zerstörungsfrei und rückwirkend unterstützt, indem die Vorlage [Marketing-Kanal-Funktion](../data-views/derived-fields/derived-fields.md#function-templates) verwendet wird.

## Vorbereiten auf wichtige Unterschiede bei der Migration zu Customer Journey Analytics

Wenn sich Ihr Unternehmen entschließt, Customer Journey Analytics zu verwenden, sollten Sie sich mit diesen Schritten vertraut machen, um Ihre Daten vorzubereiten, und über die wichtigen Unterschiede zwischen den beiden Technologien Bescheid wissen. Dieser Artikel richtet sich an Administratoren.

### Machen Sie sich vertraut mit der Verarbeitung zur Berichtslaufzeit {#report-time}

Das Reporting in Adobe Analytics beruht auf einer erheblichen Datenvorverarbeitung, um Ergebnisse zu generieren, wie die Persistenz in [!UICONTROL eVars]. Im Gegensatz dazu führt Customer Journey Analytics (CJA) diese Berechnungen zur Berichtslaufzeit aus.

[!UICONTROL Berichtszeitverarbeitung] eröffnet die Möglichkeit, rückwirkende Einstellungen anzuwenden und mehrere Versionen der Variablenpersistenz zu erstellen, ohne die Art der Erfassung der zugrunde liegenden Daten ändern zu müssen.

Diese Änderung führt zu gewissen Unterschieden in der Verwendung von Daten zur Berichtserstellung, insbesondere bei Variablen, die länger gültig sind. Sie können beurteilen, wie sich die Verarbeitung zur Berichtslaufzeit auf Ihr Reporting auswirken kann, indem Sie eine [Virtual Report Suite](https://experienceleague.adobe.com/de/docs/analytics/components/virtual-report-suites/vrs-report-time-processing) verwenden.

### Identifizieren Sie wichtige Segmente und berechnete Metriken {#segments-calcmetrics}

Adobe Analytics-Segmente und berechnete Metriken sind nicht mit Customer Journey Analytics kompatibel. In vielen Fällen können diese Komponenten in Customer Journey Analytics mithilfe der neuen Schemata und verfügbaren Daten neu erstellt werden.

Um den Wechsel zwischen den Systemen für Benutzer so reibungslos wie möglich zu gestalten, führen Sie folgende Maßnahmen aus:

1. Identifizieren Sie die wichtigsten dieser Komponenten.

2. Dokumentieren Sie ihre Definitionen

3. Ermitteln Sie, welche Felder in den Daten erforderlich sind, um sie in Customer Journey Analytics als [Segmente](/help/components/segments/seg-overview.md) und [berechnete Metriken](/help/components/calc-metrics/calc-metr-overview.md) zu replizieren.

Hier sind einige Videos, die Ihnen dabei helfen:

* [Verschieben von Adobe Analytics-Segmenten nach Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/filters/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=de)

* [Verschieben der berechneten Metriken von Adobe Analytics nach Customer Journey Analytics](https://experienceleague.adobe.com/de/docs/customer-journey-analytics-learn/tutorials/components/calc-metrics/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics)

### Weitere Überlegungen

* Durch die leistungsstarken Customer Journey Analytics-Datenansichten haben Sie bei der Definition von Metriken und Dimensionen in Customer Journey Analytics deutlich mehr Flexibilität. Sie können beispielsweise den Wert einer Dimension als Definition einer Metrik verwenden. [Weitere Informationen](/help/use-cases/data-views/data-views-usecases.md)

* Wenn Sie einen benutzerdefinierten Kalender in Adobe Analytics festgelegt haben, verfügen Sie in Customer Journey Analytics über ähnliche [benutzerdefinierte Kalenderfunktionen](/help/components/date-ranges/overview.md). Sie müssen sicherstellen, dass Ihr Kalender korrekt definiert ist.

* In Customer Journey Analytics können Sie ein benutzerdefiniertes Sitzungs-Timeout definieren und eine Metrik festlegen, durch die eine neue Sitzung gestartet wird. Sie können Datenansichten mit verschiedenen Sitzungsdefinitionen erstellen, um Einblicke zu erhalten, die weit darüber hinausgehen, was in Adobe Analytics möglich war. Diese Funktion kann besonders für Datensätze im Mobile-Bereich von Nutzen sein.

* Erwägen Sie die Bereitstellung eines Datenwörterbuchs für Ihre Benutzerinnen und Benutzer. Oder erweitern Sie die SDR, um den Experience Platform-Feldnamen für Schemaelemente einzuschließen.

### Nächste Schritte

Wenn Sie nach dem Wechsel zu Customer Journey Analytics Datendiskrepanzen feststellen, können Sie Ihre ursprünglichen Adobe Analytics-Daten mit den aktuellen Adobe Analytics-Daten in Customer Journey Analytics vergleichen. [Weitere Informationen](/help/troubleshooting/compare.md)
