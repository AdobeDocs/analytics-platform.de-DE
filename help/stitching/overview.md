---
title: Überblick über die Zuordnung
description: Erfahren Sie mehr über die Konzepte, Vorteile, Voraussetzungen und Einschränkungen der Identitätszuordnung.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
autotag-review: '2026-05-19T09:24:34.962Z'
TQID: 'https://experienceleague.adobe.com/Y7Q0pAx9s4p2YxrcfVKsvJcppHFmtNCKAgA0oCc0CeA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: faea9abd-7024-4c5e-a5b4-87919e09b24b
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 1022
ht-degree: 58%

---

# Zuordnung – Überblick

>[!NOTE]
>
>Sie müssen über das Customer Journey Analytics **Select**-Paket oder höher (für [feldbasiertes Stitching](fbs.md)) oder das Customer Journey Analytics **Prime**-Paket oder höher (für [graphbasiertes Stitching](gbs.md)) verfügen, um die in diesem Abschnitt beschriebenen Funktionen zu verwenden. Wenden Sie sich an Ihre Admins, wenn Sie sich nicht sicher sind, welches Customer Journey Analytics-Paket Sie besitzen.

Identitätszuordnung (oder einfach Zuordnung) ist eine leistungsstarke Funktion, die die Eignung eines Ereignis-Datensatzes für die Cross-Channel-Analyse erhöht. Cross-Channel-Analyse ist ein Hauptanwendungsfall für Customer Journey Analytics. Mit Cross-Channel-Analyse können Sie Berichte auf der Grundlage einer gemeinsamen Kennung (Personen-ID) nahtlos für mehrere Datensätze aus verschiedenen Kanälen kombinieren und ausführen.

Wenn Sie Datensätze mit ähnlichen Personen-IDs kombinieren, wird die Attribution geräte- und kanalübergreifend übernommen. Beispiel: Eine Person besucht Ihre Website über eine Werbeanzeige auf dem Desktop-Computer. Der Benutzer kauft ein Produkt, aber dann stößt der Benutzer auf ein Problem mit der Bestellung. Anschließend ruft die Person Ihren Kundendienst an, um das Problem zu klären. Mit der Cross-Channel-Analyse können Sie Callcenter-Ereignisse der Anzeige zuordnen, auf die ursprünglich geklickt wurde.

Leider sind nicht alle ereignisbasierten Datensätze, die Teil Ihrer Verbindung in Customer Journey Analytics sind, ausreichend mit Daten gefüllt, um diese Attribution standardmäßig zu unterstützen. Insbesondere bei Web- oder Mobile-basierten Erlebnisdatensätzen sind die tatsächlichen Informationen zur Personen-ID oft nicht für alle Ereignisse verfügbar.

Durch das Zusammenfügen von Identitäten in den Zeilen eines Datensatzes wird sichergestellt, dass die gewünschten Personen-ID-Informationen für so viele Ereignisse wie möglich verfügbar sind. Beim Zusammenfügen werden Benutzerdaten aus authentifizierten und nicht authentifizierten Sitzungen untersucht, um den allgemeinen Wert der Personen-ID zu ermitteln, der verwendet werden kann. Durch diese Neuzuweisung werden unterschiedliche Datensätze zu einer einzelnen Personen-ID aufgelöst, die auf Personenebene und nicht auf Geräte- oder Cookie-Ebene analysiert werden kann. Wenn jedoch kein gemeinsamer Personen-ID-Wert ermittelt werden kann, wird stattdessen der persistente ID-Wert verwendet.

Customer Journey Analytics unterstützt zwei Arten der Zuordnung: [Feldbasierte Zuordnung](fbs.md) und [Diagrammbasierte Zuordnung](gbs.md).

## Voraussetzungen

>[!IMPORTANT]
>
>Wenn nicht alle Voraussetzungen erfüllt sind, können Cross-Channel-Analysen möglicherweise nicht ordnungsgemäß durchgeführt werden.

Bevor Sie die Zuordnung verwenden, sollten Sie sicherstellen, dass Ihr Unternehmen folgende Voraussetzungen erfüllt:

- Die Zuordnung umfasst das Zusammenführen von authentifizierten und nicht authentifizierten Benutzerdaten. Vergewissern Sie sich vor dem Aktivieren der Zuordnung eines Ereignisdatensatzes, dass Sie die geltenden Gesetze und Vorschriften einhalten, wie etwa das Einholen der erforderlichen Berechtigungen der Endanwenderinnen und Endanwender.

- Importieren Sie die gewünschten Daten in Adobe Experience Platform:

   - Informationen zu Adobe Analytics-Daten finden Sie unter [Verwenden von Daten aus Report Suites von Adobe Analytics in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - Informationen zu anderen Datentypen finden Sie unter [Erstellen eines Schemas](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/tutorials/create-schema-ui) und [Aufnehmen von Daten](https://experienceleague.adobe.com/de/docs/experience-platform/ingestion/home) in der Adobe Experience Platform-Dokumentation.

Sie profitieren von der Cross-Channel-Analyse, wenn Sie einen oder mehrere Ihrer zugeordneten Datensätze als Teil der Definition Ihrer Customer Journey Analytics-Verbindung mit anderen Datensätzen kombinieren, z. B. Callcenter-Daten. Bei dieser Verbindungskonfiguration wird davon ausgegangen, dass diese anderen Datensätze bereits eine Personen-ID aus demselben Namespace in möglichst vielen Zeilen enthalten.

Sobald Ihr Unternehmen die generischen [Voraussetzungen](overview.md#prerequisites) erfüllt, die üblichen [Einschränkungen](overview.md#limitations) sowie die für [&#x200B; (feldbasiert](fbs.md) und [diagrammbasiert](gbs.md)) spezifischen Voraussetzungen und Einschränkungen versteht, können Sie diese Schritte ausführen, um die Zuordnung in Customer Journey Analytics anzufordern und zu verwenden.

## Einschränkungen

Die Zuordnung ist eine innovative und zuverlässige Funktion, deren Verwendung jedoch gewissen Einschränkungen unterliegt.

- Es werden nur Ereignis-Datensätze unterstützt. Andere Datensätze, wie beispielsweise Lookup-Datensätze, werden nicht unterstützt.
- Die Zuordnung transformiert nicht das zum Verbinden verwendete Feld. Die Zuordnung verwendet den Wert im angegebenen Feld so, wie er im nicht zugewiesenen Datensatz innerhalb des Data Lake vorhanden ist.
- Beim Zuordnen wird zwischen Groß- und Kleinschreibung unterschieden. Beispielsweise werden die Identitätswerte `Bob` und `BOB` als zwei separate Personen behandelt.

Verwechseln Sie die Zuordnung nicht mit:

- Dem Zusammenführen von zwei oder mehr Datensätzen. Die Zuordnung wird nur auf einen Datensatz angewendet. Die Zusammenführung von Datensätzen erfolgt infolge der Einrichtung einer Customer Journey Analytics-Verbindung und der Auswahl derselben Personen-ID für alle in der Verbindung ausgewählten Datensätze.

- Dem Join zweier Datensätze. In Customer Journey Analytics wird ein Join häufig für Suchen oder Klassifizierungen in Analysis Workspace verwendet. Obwohl bei der Zuordnung die Funktion „Join“ verwendet wird, umfasst der Prozess selbst mehr als Joins.


## Optionen

Das Customer Journey Analytics-Paket, zu dem Sie berechtigt sind, bestimmt die verfügbaren Zuordnungsmethoden, Optionen für die anfängliche Aufstockungsdauer, das Lookback-Fenster, die Wiederholungshäufigkeit und die maximale Anzahl von Datensätzen, die für das Zusammenfügen zulässig sind. Weitere Informationen finden Sie in der &lbrace;0[&#128279;](https://helpx.adobe.com/de/legal/product-descriptions/customer-journey-analytics.html) Customer Journey Analytics-Produktbeschreibung. Legen Sie die verfügbaren Optionen fest, bevor Sie das Zusammenfügen aktivieren.

| | Customer Journey Analytics-<br/> | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Verfügbare Stitching-Methoden | Feldbasierte Zuordnung | Feldbasiertes Stitching<br/>Diagrammbasiertes Stitching | Feldbasiertes Stitching<br>Diagrammbasiertes Stitching</li> |
| Einmaliges Zusammenfügen der Aufstockungsdauer | 13 Monate | 13 Monate | 25 Monate |
| Lookback-Fenster und Wiederholungshäufigkeit | 1 Tag, jeden Tag<br/> bis zu 7 Tage, wöchentlich | 1 Tag, jeden Tag<br/> bis zu 14 Tage, wöchentlich | 1 Tag, jeden Tag<br/> bis zu 30 Tage, wöchentlich |
| Maximal zulässige Anzahl von Datensätzen für das Zusammenfügen | 5 | 15 | 50 |

## Aktivieren der Zuordnung

Die Zuordnung kann auf zwei Arten aktiviert werden:

- [Anfrage zum Aktivieren der Zuordnung](/help/stitching/use-stitching.md) (veraltet). Nach der Genehmigung wird ein doppelter Datensatz für den Datensatz erstellt, für den Sie die Zuordnung angefordert haben. Dieser doppelte Datensatz enthält eine zusätzliche Spalte mit der zusammengefügten Kennung. Sie müssen eine neue Verbindung erstellen oder eine bestehende Verbindung bearbeiten, die den zugeordneten Datensatz enthält, um die zugeordneten Daten in Customer Journey Analytics zu verwenden.
- [Aktivieren Sie das Zusammenfügen in der Verbindungsschnittstelle](/help/stitching/use-stitching-ui.md). Wenn Sie das Zusammenfügen für einen Datensatz in der Verbindungsschnittstelle konfigurieren, erfolgt das Zusammenfügen spontan während der Aufnahme von Daten aus diesem Datensatz in Customer Journey Analytics.


## Journey Optimizer-Datensätze

Die Zuordnung unterstützt die folgenden automatisch generierten Journey Optimizer-Datensätze:

- AJO-Journey-Schrittereignisse
- Ereignisdatensatz für eingehende AJO-Aktivitäten
- AJO-Oberflächen-Datensatz
- Datensatz für Feedback-Ereignisse zu AJO-Nachrichten* Datensatz für Erlebnisereignisse beim AJO-Push-Tracking
- Datensatz für Erlebnisereignisse beim AJO-E-Mail-Tracking
- Ereignisdatensatz mit Feedback zu AJO-BCC
- Datensatz für Feedback-Ereignisse zu AJO-Live-Aktivitäten
- Datensatz für Entscheidungsereignisse zu AJO-ExD

>[!MORELIKETHIS]
>
>[Feldbasierte Zuordnung](fbs.md)
>[Grafikbasierte Zuordnung](gbs.md)
>[Zuordnung verwenden](use-stitching.md)
>[Validieren der Zuordnung](validate.md)
>[Häufig gestellte Fragen zur Zuordnung](faq.md)

