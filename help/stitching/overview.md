---
title: Überblick über die Zuordnung
description: Überblick über Zuordnung
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 50599b36d333cae3735c6d4fd1b0af6fcabe9177
workflow-type: ht
source-wordcount: '735'
ht-degree: 100%

---

# Überblick über die Zuordnung

>[!NOTE]
>
>Sie müssen über das **Select**-Paket oder höher (für [feldbasierte Zuordnung](fbs.md)) oder das **Prime**-Paket oder höher (für die [diagrammbasierte Zuordnung](gbs.md)) verfügen, um die in diesem Abschnitt beschriebenen Funktionen zu verwenden. Wenden Sie sich an Ihre Admins, wenn Sie sich nicht sicher sind, welches Customer Journey Analytics-Paket Sie besitzen.

Identitätszuordnung (oder einfach Zuordnung) ist eine leistungsstarke Funktion, die die Eignung eines Ereignis-Datensatzes für die Cross-Channel-Analyse erhöht. Die Cross-Channel-Analyse ist ein Hauptanwendungsfall, den Customer Journey Analytics handhaben kann. So können Sie Berichte auf Basis einer gemeinsamen Kennung (Personen-ID) nahtlos kombinieren und für mehrere Datensätze aus verschiedenen Kanälen ausführen.

Wenn Sie Datensätze mit ähnlichen Personen-IDs kombinieren, wird die Attribution geräte- und kanalübergreifend übernommen. Beispiel: Ein Benutzer besucht Ihre Site zum ersten Mal über eine Werbeanzeige auf seinem Desktop. Dieser Benutzer stößt bei seiner Bestellung auf ein Problem und ruft dann Ihren Kundendienst an, um das Problem zu beheben. Mit der Cross-Channel-Analyse können Sie Callcenter-Ereignisse der Anzeige zuordnen, auf die ursprünglich geklickt wurde.

Leider sind nicht alle ereignisbasierten Datensätze, die Teil Ihrer Verbindung in Customer Journey Analytics sind, ausreichend mit Daten gefüllt, um diese Attribution standardmäßig zu unterstützen. Insbesondere bei Web- oder Mobile-basierten Erlebnisdatensätzen steht häufig keine tatsächlichen Informationen zur Personen-ID zu allen Ereignissen zur Verfügung.

Durch die Zuordnung können Identitäten innerhalb der Zeilen eines Datensatzes neu zugewiesen werden, um sicherzustellen, dass die Personen-ID (zugeordnete ID) für jedes Ereignis verfügbar ist. Bei der Zuordnung werden Benutzerdaten aus authentifizierten und nicht authentifizierten Sitzungen untersucht, um den allgemeinen Wert für die vorübergehende ID (Personen-ID) zu ermitteln, der als zugeordnete ID verwendet werden kann. Diese erneute Zuweisung ermöglicht die Auflösung verschiedener Datensätze zu einer einzelnen zugeordneten ID für die Analyse auf Personenebene, statt auf Geräte- oder Cookie-Ebene.

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

>[!MORELIKETHIS]
>
>[Feldbasierte Zuordnung](fbs.md)
>>[Diagrammbasierte Zuordnung](gbs.md)
>>[Verwenden der Zuordnung](use-stitching.md)
>>[Validieren der Zuordnung](validate.md)
>>[Häufig gestellte Fragen zur Zuordnung](faq.md)

