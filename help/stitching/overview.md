---
title: Überblick über die Zuordnung
description: Überblick über Zuordnung
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 359fe2a718ccef816377083aceb2652b4a905072
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 74%

---

# Überblick über die Zuordnung

>[!NOTE]
>
>Sie müssen über das **Select**-Paket oder höher (für [feldbasierte Zuordnung](fbs.md)) oder das **Prime**-Paket oder höher (für die [diagrammbasierte Zuordnung](gbs.md)) verfügen, um die in diesem Abschnitt beschriebenen Funktionen zu verwenden. Wenden Sie sich an Ihre Admins, wenn Sie sich nicht sicher sind, welches Customer Journey Analytics-Paket Sie besitzen.

Identitätszuordnung (oder einfach Zuordnung) ist eine leistungsstarke Funktion, die die Eignung eines Ereignis-Datensatzes für die Cross-Channel-Analyse erhöht. Die Cross-Channel-Analyse ist ein Hauptanwendungsfall für Customer Journey Analytics. Mit der Funktion können Sie Berichte auf der Grundlage einer gemeinsamen Kennung (Personen-ID) nahtlos mit mehreren Datensätzen aus verschiedenen Kanälen kombinieren und ausführen.

Wenn Sie Datensätze mit ähnlichen Personen-IDs kombinieren, wird die Attribution geräte- und kanalübergreifend übernommen. Ein Benutzer besucht Ihre Site beispielsweise über eine Anzeige auf seinem Desktop-Computer. Die Benutzenden kaufen ein Produkt, aber dann stößt der Benutzende auf ein Problem mit der Bestellung. Der Benutzer ruft dann Ihr Kundendienst-Team an, um das Problem zu beheben. Bei der kanalübergreifenden Analyse können Sie Callcenter-Ereignisse der Anzeige zuordnen, auf die der Benutzer ursprünglich geklickt hat.

Leider sind nicht alle ereignisbasierten Datensätze, die Teil Ihrer Verbindung in Customer Journey Analytics sind, ausreichend mit Daten gefüllt, um diese Attribution standardmäßig zu unterstützen. Insbesondere bei Web- oder mobilen Erlebnisdatensätzen stehen häufig nicht bei allen Ereignissen tatsächliche Personen-ID-Informationen zur Verfügung.

Durch das Zusammenfügen können Sie Identitäten in den Zeilen eines Datensatzes neu zuweisen, um sicherzustellen, dass die Personen-ID (zusammengefügte ID) für jedes Ereignis verfügbar ist. Beim Zusammenfügen werden Benutzerdaten aus authentifizierten und nicht authentifizierten Sitzungen betrachtet, um den allgemeinen Wert der Personen-ID zu ermitteln, der als zusammengefügte ID verwendet werden kann. Diese Neuzuweisung ermöglicht die Auflösung unterschiedlicher Datensätze zu einer einzigen zusammengefügten ID für die Analyse auf Personenebene und nicht auf Geräte- oder Cookie-Ebene.

Customer Journey Analytics unterstützt zwei Arten der Zuordnung: [Feldbasierte Zuordnung](fbs.md) und [Diagrammbasierte Zuordnung](gbs.md).

## Voraussetzungen

>[!IMPORTANT]
>
>Wenn nicht alle Voraussetzungen erfüllt sind, können Cross-Channel-Analysen möglicherweise nicht ordnungsgemäß durchgeführt werden.

Bevor Sie die Zuordnung verwenden, sollten Sie sicherstellen, dass Ihr Unternehmen folgende Voraussetzungen erfüllt:

- Die Zuordnung umfasst das Zusammenführen von authentifizierten und nicht authentifizierten Benutzerdaten. Vergewissern Sie sich vor dem Aktivieren der Zuordnung eines Ereignisdatensatzes, dass Sie die geltenden Gesetze und Vorschriften einhalten, wie etwa das Einholen der erforderlichen Berechtigungen der Endanwenderinnen und Endanwender. Weitere Informationen finden Sie unter [Definieren von Identitätsfeldern in der Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/ui/fields/identity).

- Importieren Sie die gewünschten Daten in Adobe Experience Platform:

   - Informationen zu Adobe Analytics-Daten finden Sie unter [Verwenden von Daten aus Report Suites von Adobe Analytics in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md). 
   - Informationen zu anderen Datentypen finden Sie unter [Erstellen eines Schemas](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/tutorials/create-schema-ui) und [Aufnehmen von Daten](https://experienceleague.adobe.com/de/docs/experience-platform/ingestion/home) in der Adobe Experience Platform-Dokumentation.

Sie profitieren von der Cross-Channel-Analyse, wenn Sie einen oder mehrere Ihrer zugeordneten Datensätze als Teil der Definition Ihrer Customer Journey Analytics-Verbindung mit anderen Datensätzen kombinieren, z. B. Callcenter-Daten. Bei dieser Verbindungskonfiguration wird davon ausgegangen, dass diese anderen Datensätze bereits eine Personen-ID in jeder Zeile enthalten, ähnlich der zugeordneten ID.

## Zusammenfügung aktivieren

Sie können das Zusammenfügen auf zwei Arten aktivieren:

- [Anfrage zum Aktivieren der Zuordnung](/help/stitching/use-stitching.md)
- [Zusammenfügung in der Verbindungsschnittstelle aktivieren](/help/stitching/use-stitching-ui.md) [!BADGE Beta]{type=Informative}

## Einschränkungen

>[!IMPORTANT]
>
>
>- Wenden Sie alle Änderungen, die Sie am Quellereignis-Datensatzschema vornehmen, auch auf das neue Schema des zugeordneten Datensatzes an.
>
>- Wenn Sie den Quelldatensatz entfernen, wird der zugeordnete Datensatz nicht weiter verarbeitet und vom System entfernt.
>
>- Labels zur Datennutzung werden nicht automatisch in das zugeordnete Datensatzschema übertragen. Wenn Sie Labels zur Datennutzung auf das Quelldatensatzschema angewendet haben, müssen Sie diese Labels zur Datennutzung manuell auf das Schema des zugeordneten Datensatzes anwenden. Weitere Informationen dazu finden Sie unter [Verwalten von Labels zur Datennutzung in Experience Platform](https://experienceleague.adobe.com/de/docs/experience-platform/data-governance/labels/overview).

Die Zuordnung ist eine innovative und zuverlässige Funktion, deren Verwendung jedoch gewissen Einschränkungen unterliegt.

- Es werden nur Ereignis-Datensätze unterstützt. Andere Datensätze, wie beispielsweise Lookup-Datensätze, werden nicht unterstützt.
- Die Zuordnung transformiert nicht das zum Verbinden verwendete Feld. Die Zuordnung verwendet den Wert im angegebenen Feld so, wie er im nicht zugewiesenen Datensatz innerhalb des Data Lake vorhanden ist. 
- Beim Zuordnen wird zwischen Groß- und Kleinschreibung unterschieden. Wenn beispielsweise manchmal das Wort „Bob“ im Feld erscheint und manchmal das Wort „BOB“, werden diese IDs als zwei separate Personen behandelt.

Verwechseln Sie die Zuordnung nicht mit:

- Dem Zusammenführen von zwei oder mehr Datensätzen. Die Zuordnung wird nur auf einen Datensatz angewendet. Die Zusammenführung von Datensätzen erfolgt infolge der Einrichtung einer Customer Journey Analytics-Verbindung und der Auswahl derselben Personen-ID für alle in der Verbindung ausgewählten Datensätze.

- Dem Join zweier Datensätze. In Customer Journey Analytics wird ein Join häufig für Suchen oder Klassifizierungen in Analysis Workspace verwendet. Obwohl bei der Zuordnung die Funktion „Join“ verwendet wird, umfasst der Prozess selbst mehr als Joins.


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
>[Feldbasiertes Stitching](fbs.md)
>>[Diagrammbasiertes Stitching](gbs.md)
>>[Verwenden der Zuordnung](use-stitching.md)
>>[Validieren der Zuordnung](validate.md)
>>[Häufig gestellte Fragen zur Zuordnung](faq.md)

