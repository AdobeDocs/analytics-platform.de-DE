---
title: Übersicht über das Zusammenfügen
description: 'Überblick über Zuordnung '
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: c27d5f44243e2cda252ac6a484a70964f0999dfc
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 15%

---

# Übersicht über das Zusammenfügen

>[!NOTE]
>
>Sie müssen über das **Select**-Paket oder höher (für [feldbasiertes Stitching](fbs.md)) oder das **Prime**-Paket oder höher (für [graphbasiertes Stitching](gbs.md)) verfügen, um die in diesem Abschnitt beschriebenen Funktionen zu verwenden. Wenden Sie sich an Ihre Admins, wenn Sie sich nicht sicher sind, welches Customer Journey Analytics-Paket Sie besitzen.

Identitätszuordnung (oder einfach: Zuordnung) ist eine leistungsstarke Funktion, die die Eignung eines Ereignis-Datensatzes für eine kanalübergreifende Analyse erhöht. Die kanalübergreifende Analyse ist ein Hauptanwendungsfall, den Customer Journey Analytics verarbeiten kann, da sie es Ihnen ermöglicht, auf der Grundlage einer gemeinsamen Kennung (Personen-ID) Berichte nahtlos für mehrere Datensätze aus verschiedenen Kanälen zu kombinieren und auszuführen.

Wenn Sie Datensätze mit ähnlichen Personen-IDs kombinieren, wird die Attribution geräte- und kanalübergreifend übernommen. Beispiel: Ein Benutzer besucht Ihre Site zum ersten Mal über eine Werbeanzeige auf seinem Desktop. Dieser Benutzer stößt bei seiner Bestellung auf ein Problem und ruft dann Ihren Kundendienst an, um das Problem zu beheben. Bei der kanalübergreifenden Analyse können Sie Callcenter-Ereignisse der Anzeige zuordnen, auf die ursprünglich geklickt wurde.

Leider sind nicht alle ereignisbasierten Datensätze, die Teil Ihrer Verbindung in Customer Journey Analytics sind, ausreichend mit Daten gefüllt, um diese Attribution standardmäßig zu unterstützen. Insbesondere bei Web- oder mobilen Erlebnisdatensätzen steht häufig keine tatsächliche Personen-ID-Information zu allen Ereignissen zur Verfügung.

Durch das Zusammenfügen können Identitäten innerhalb der Zeilen eines Datensatzes neu zugeordnet werden, um sicherzustellen, dass die Personen-ID (zusammengefügte ID) für jedes Ereignis verfügbar ist. Beim Zusammenfügen werden Benutzerdaten aus authentifizierten und nicht authentifizierten Sitzungen betrachtet, um den allgemeinen Wert für die vorübergehende ID (Personen-ID) zu ermitteln, der als zusammengefügte ID verwendet werden kann. Diese Neuzuweisung ermöglicht die Auflösung unterschiedlicher Datensätze zu einer einzelnen zugeordneten ID für die Analyse auf Personenebene und nicht auf Geräte- oder Cookie-Ebene.

Customer Journey Analytics unterstützt zwei Arten der Zuordnung[ (feldbasiertes Stitching](fbs.md) und [grafisches Stitching](gbs.md).

## Voraussetzungen

>[!IMPORTANT]
>
>Wenn nicht alle Voraussetzungen erfüllt sind, kann es sein, dass Cross-Channel-Analysen nicht ordnungsgemäß durchgeführt werden können.

Bevor Sie Stitching verwenden, stellen Sie sicher, dass Ihre Organisation mit folgendem Inhalt vorbereitet ist:

- Das Zusammenfügen umfasst das Zusammenführen authentifizierter und nicht authentifizierter Benutzerdaten. Stellen Sie sicher, dass Sie die geltenden Gesetze und Vorschriften einhalten, einschließlich der Einholung der erforderlichen Endbenutzerberechtigungen, bevor Sie das Zusammenfügen mit einem Ereignis-Datensatz aktivieren. Weitere Informationen finden Sie unter [Definieren von Identitätsfeldern in der Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/ui/fields/identity).

- Importieren Sie die gewünschten Daten in Adobe Experience Platform:

   - Informationen zu Adobe Analytics-Daten finden Sie [Verwenden von Adobe Analytics Report Suite-Daten in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - Informationen zu anderen Datentypen finden Sie unter [Erstellen eines Schemas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) und [Aufnehmen von Daten](https://experienceleague.adobe.com/de/docs/experience-platform/ingestion/home) in der Adobe Experience Platform-Dokumentation.

Sie profitieren von der kanalübergreifenden Analyse, wenn Sie einen oder mehrere Ihrer zugeordneten Datensätze mit anderen Datensätzen, z. B. Callcenter-Daten, als Teil der Definition Ihrer Customer Journey Analytics-Verbindung kombinieren. Bei dieser Verbindungskonfiguration wird davon ausgegangen, dass diese anderen Datensätze bereits eine Personen-ID in jeder Zeile enthalten, ähnlich der zugeordneten ID.


## Einschränkungen

>[!IMPORTANT]
>
>
>- Wenden Sie alle Änderungen, die Sie am Quellereignis-Datensatzschema vornehmen, auch auf das neue Schema des zusammengefügten Datensatzes an, andernfalls wird der zusammengefügte Datensatz beschädigt.
>
>- Wenn Sie den Quelldatensatz entfernen, wird der zugeordnete Datensatz nicht mehr verarbeitet und vom System entfernt.
>
>- Datennutzungsbeschriftungen werden nicht automatisch an das Schema des zugeordneten Datensatzes weitergegeben. Wenn Sie Datennutzungsbeschriftungen auf das Quelldatensatzschema angewendet haben, müssen Sie diese Datennutzungsbeschriftungen manuell auf das Schema des zugeordneten Datensatzes anwenden. Weitere [ finden Sie unter „Verwalten ](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview) Datennutzungsbeschriftungen in Experience Platform&quot;.

Stitching ist eine innovative und zuverlässige Funktion, deren Verwendung jedoch gewissen Einschränkungen unterliegt.

- Es werden nur Ereignis-Datensätze unterstützt. Andere Datensätze, wie beispielsweise Lookup-Datensätze, werden nicht unterstützt.
- Durch das Zusammenfügen wird das zum Zusammenfügen verwendete Feld nicht umgewandelt. Beim Zusammenfügen wird der Wert im angegebenen Feld so verwendet, wie er im nicht zugeordneten Datensatz im Data Lake vorhanden ist.
- Beim Zuordnen wird zwischen Groß- und Kleinschreibung unterschieden. Wenn beispielsweise manchmal das Wort „Bob“ im Feld und manchmal das Wort „BOB“ erscheint, werden diese IDs als zwei separate Personen behandelt.

Verwechseln Sie das Zusammenfügen nicht mit:

- Die Zusammenführung von zwei oder mehr Datensätzen. Die Zuordnung gilt nur für einen Datensatz. Die Zusammenführung von Datensätzen erfolgt infolge der Einrichtung einer Customer Journey Analytics-Verbindung und der Auswahl derselben Personen-ID für alle in der Verbindung ausgewählten Datensätze.

- Der Join zweier Datensätze. In Customer Journey Analytics wird ein Join häufig für Suchen oder Klassifizierungen in Analysis Workspace verwendet. Obwohl beim Zusammenfügen die Funktion „Zusammenführen“ verwendet wird, umfasst der Prozess selbst mehr als Zusammenfügungen.

>[!MORELIKETHIS]
>
>[Feldbasiertes Stitching](fbs.md)
>[Diagrammbasiertes Stitching](gbs.md)
>[Stitching verwenden](use-stitching.md)
>[Häufig gestellte Fragen zum Zusammenfügen](faq.md)

