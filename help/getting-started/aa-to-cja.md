---
title: Weiterentwicklung von Adobe Analytics
description: Schritte zum Umwandeln von Adobe Analytics-Daten in Customer Journey Analytics-Daten
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 4dcf9ab808475cc3cc48cab4c076b6c3cfb66f8a
workflow-type: tm+mt
source-wordcount: '1075'
ht-degree: 79%

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

In Datensätzen wie Adobe Analytics ist möglicherweise nicht in jeder Datenzeile eine Identität vorhanden, aber eine sekundäre Identität schon. In diesem Fall kann [Cross-Channel-Analyse (auch als Zuordnung bezeichnet)](/help/stitching/overview.md) verwendet werden, um die Lücke zwischen Zeilen zu schließen, wenn ein Kunde nur durch seine ECID identifiziert wird und wenn eine Identität erfasst wird (z. B. bei der Authentifizierung eines Kunden).

### Anpassen Ihrer Variablen

Die einfachste Methode, Adobe Analytics-Daten in Customer Journey Analytics-Daten umzuwandeln, ist die Aufnahme einer [globalen Report Suite](https://experienceleague.adobe.com/de/docs/analytics/implementation/prepare/global-rs) in Experience Platform mit dem [Analytics-Quell-Connectors](https://experienceleague.adobe.com/de/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics). Dieser Connector ordnet Ihre Adobe Analytics-Variablen direkt einem XDM-Schema und -Datensatz in Experience Platform zu, die wiederum einfach mit Customer Journey Analytics verbunden werden können.

Eine vollständige globale Report Suite ist nicht in jedem Fall für eine Implementierung möglich. Wenn Sie planen, mehrere Report Suites in Customer Journey Analytics zu integrieren, haben Sie zwei Möglichkeiten:

* Planen Sie im Voraus, damit Sie die Variablen in diesen Report Suites in Einklang bringen können. Beispielsweise kann eVar1 in Report Suite 1 auf [!UICONTROL Seite] verweisen. In Report Suite 2 kann eVar1 auf [!UICONTROL Interne Kampagne] verweisen. Wenn diese Variablen in Customer Journey Analytics importiert werden, werden sie in einer einzigen eVar1-Dimension vermischt, was zu möglicherweise verwirrenden und ungenauen Berichten führt.

* Verwenden Sie die Funktion der [Datenvorbereitung](https://experienceleague.adobe.com/de/docs/experience-platform/data-prep/home) zum Zuordnen von Variablen. Es ist zwar einfacher, wenn alle Report Suites denselben Variablenaufbau verwenden, dies ist aber nicht erforderlich, wenn Sie die neue [Data Prep](https://experienceleague.adobe.com/de/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)-Funktion von Experience Platform verwenden. Damit können Sie eine Variable anhand ihres zugeordneten Werts referenzieren, der sich auf der Ebene des Datenstroms (oder der Eigenschaft) befindet.

Wenn Sie den Wechsel zu einer globalen Report Suite aufgrund von Problemen mit [!UICONTROL überschrittenen eindeutigen Werten] oder [!UICONTROL geringem Traffic] vermieden haben, beachten Sie, dass es in Customer Journey Analytics keine [Kardinalitätsbeschränkungen für eine Dimension](/help/components/dimensions/high-cardinality.md) gibt. Dadurch können alle eindeutigen Werte angezeigt und gezählt werden.

Im Folgenden finden Sie ein Anwendungsbeispiel für das [Kombinieren von Report Suites mit verschiedenen Schemata](/help/use-cases/aa-data/combine-report-suites.md).

### (Erneutes) Konfigurieren Ihrer Marketing-Kanäle

Herkömmliche Einstellungen für Marketing-Kanäle in Adobe Analytics funktionieren in Customer Journey Analytics nicht auf die gleiche Weise. Es gibt zwei Gründe für einen Unterschied:

* Die Verarbeitungsstufe für die in Adobe Experience Platform aufgenommenen Adobe Analytics-Daten

* Der Berichtscharakter von Customer Journey Analytics

Adobe hat [aktualisierte Best Practices für die Implementierung von Marketing-Kanälen](https://experienceleague.adobe.com/de/docs/analytics/components/marketing-channels/mchannel-best-practices) veröffentlicht. Diese aktualisierten Empfehlungen helfen Ihnen dabei, die bereits in Adobe Analytics vorhandenen Funktionen mit erweiterten Attributionsfunktionen optimal zu nutzen. Die Empfehlungen bieten Ihnen auch einen guten Ausgangspunkt für die Umstellung auf Customer Journey Analytics.

Mit der Einführung von [abgeleiteten Feldern](../data-views/derived-fields/derived-fields.md) im Rahmen der Datenansichten von Customer Journey Analytics werden Marketing-Kanäle auch zerstörungsfrei und rückwirkend unterstützt, indem die Vorlage [Marketing-Kanal-Funktion](../data-views/derived-fields/derived-fields.md#function-templates) verwendet wird.

## Vorbereiten auf wichtige Unterschiede bei der Migration zu Customer Journey Analytics

Wenn sich Ihr Unternehmen entschließt, Customer Journey Analytics zu verwenden, sollten Sie sich mit diesen Schritten vertraut machen, um Ihre Daten vorzubereiten, und über die wichtigen Unterschiede zwischen den beiden Technologien Bescheid wissen. Dieser Artikel richtet sich an Administratoren.

### Machen Sie sich vertraut mit der Verarbeitung zur Berichtslaufzeit {#report-time}

Das Reporting in Adobe Analytics beruht auf einer erheblichen Datenvorverarbeitung, um Ergebnisse zu generieren, wie die Persistenz in [!UICONTROL eVars]. Im Gegensatz dazu führt Customer Journey Analytics (CJA) diese Berechnungen zur Berichtslaufzeit aus.

[!UICONTROL Berichtszeitverarbeitung] eröffnet die Möglichkeit, rückwirkende Einstellungen anzuwenden und mehrere Versionen der Variablenpersistenz zu erstellen, ohne die Art der Erfassung der zugrunde liegenden Daten ändern zu müssen.

Diese Änderung führt zu gewissen Unterschieden in der Art und Weise, wie Daten gemeldet werden, insbesondere bei Variablen, die über ein langes Gültigkeitsfenster verfügen können. Sie können beurteilen, wie sich die Verarbeitung zur Berichtslaufzeit auf Ihr Reporting auswirken kann, indem Sie eine [Virtual Report Suite](https://experienceleague.adobe.com/de/docs/analytics/components/virtual-report-suites/vrs-report-time-processing) verwenden.

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

* Wenn Sie einen benutzerdefinierten Kalender in Adobe Analytics definiert haben, verfügen Sie [ Customer Journey Analytics über ähnliche ](/help/components/date-ranges/overview.md) (benutzerdefinierte Kalenderfunktionen). Sie müssen sicherstellen, dass Ihr Kalender korrekt definiert ist.

* In Customer Journey Analytics können Sie ein benutzerdefiniertes Sitzungs-Timeout definieren sowie eine Metrik festlegen, mit der eine neue Sitzung gestartet wird. Sie können Datenansichten mit verschiedenen Sitzungsdefinitionen erstellen, um Einblicke zu erhalten, die weit darüber hinausgehen, was in Adobe Analytics möglich war. Diese Funktion kann besonders für Datensätze im Mobile-Bereich von Nutzen sein.

* Erwägen Sie die Bereitstellung eines Datenwörterbuchs für Ihre Benutzerinnen und Benutzer. Oder erweitern Sie das SDR, um den Experience Platform-Feldnamen für Schemaelemente einzuschließen.

### Nächste Schritte

Wenn Sie nach dem Wechsel zu Customer Journey Analytics Datendiskrepanzen feststellen, können Sie Ihre ursprünglichen Adobe Analytics-Daten mit den aktuellen Adobe Analytics-Daten in Customer Journey Analytics vergleichen. [Weitere Informationen](/help/troubleshooting/compare.md)
