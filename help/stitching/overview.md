---
title: Stitching-Übersicht
description: 'Überblick über Zuordnung '
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 4ce1b22cce3416b8a82e5c56e605475ae6c27d88
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 15%

---

# Stitching-Übersicht

>[!NOTE]
>
>Sie müssen über das Paket **Select** oder höher (für [feldbasiertes Stitching](fbs.md)) oder das Paket **Prime** oder höher (für [grafikbasiertes Stitching](gbs.md)) verfügen, um die in diesem Abschnitt beschriebene Funktion verwenden zu können. Wenden Sie sich an Ihre Admins, wenn Sie sich nicht sicher sind, welches Customer Journey Analytics-Paket Sie besitzen.

Die Identitätszuordnung (oder einfach das Stitching) ist eine leistungsstarke Funktion, die die Eignung eines Ereignis-Datensatzes für die kanalübergreifende Analyse erhöht. Die kanalübergreifende Analyse ist ein Hauptanwendungsfall, den Customer Journey Analytics handhaben kann. So können Sie Berichte basierend auf einer gemeinsamen Kennung (Personen-ID) nahtlos mit mehreren Datensätzen aus verschiedenen Kanälen kombinieren und ausführen.

Wenn Sie Datensätze mit ähnlichen Personen-IDs kombinieren, wird die Attribution geräte- und kanalübergreifend übernommen. Beispiel: Ein Benutzer besucht Ihre Site zum ersten Mal über eine Werbeanzeige auf seinem Desktop. Dieser Benutzer stößt bei seiner Bestellung auf ein Problem und ruft dann Ihren Kundendienst an, um das Problem zu beheben. Mit der kanalübergreifenden Analyse können Sie Callcenter-Ereignisse der Anzeige zuordnen, auf die sie ursprünglich geklickt haben.

Leider sind nicht alle ereignisbasierten Datensätze, die Teil Ihrer Customer Journey Analytics-Verbindung sind, ausreichend mit Daten gefüllt, um diese Attribution standardmäßig zu unterstützen. Insbesondere verfügen Web- oder mobile-basierte Erlebnisdatensätze häufig nicht über tatsächliche Personen-ID-Informationen für alle Ereignisse.

Die Zuordnung ermöglicht die Neuzuordnung von Identitäten in den Zeilen eines Datensatzes und stellt sicher, dass die Personen-ID (zugeordnete ID) für jedes Ereignis verfügbar ist. Beim Zuordnen werden Benutzerdaten aus authentifizierten und nicht authentifizierten Sitzungen untersucht, um den allgemeinen Wert für die vorübergehende ID (Personen-ID) zu ermitteln, der als zugeordnete ID verwendet werden kann. Diese Neuzuweisung ermöglicht die Auflösung verschiedener Datensätze zu einer einzigen zugeordneten ID, die auf der Personenebene und nicht auf der Geräte- oder Cookie-Ebene analysiert werden kann.

Customer Journey Analytics unterstützt zwei Arten von Stitching: [feldbasiertes Stitching](fbs.md) und [grafikbasiertes Stitching](gbs.md).

## Voraussetzungen

>[!IMPORTANT]
>
>Wenn nicht alle Voraussetzungen erfüllt sind, kann die kanalübergreifende Analyse nicht ordnungsgemäß durchgeführt werden.

Stellen Sie vor der Verwendung von Stitching sicher, dass Ihr Unternehmen wie folgt vorbereitet ist:

- Die Zuordnung umfasst das Zusammenführen authentifizierter und nicht authentifizierter Benutzerdaten. Stellen Sie sicher, dass Sie die geltenden Gesetze und Vorschriften einhalten, einschließlich der Erlangung der erforderlichen Endbenutzerberechtigungen, bevor Sie die Zuordnung für einen Ereignis-Datensatz aktivieren. Weitere Informationen finden Sie unter [Definieren von Identitätsfeldern in der Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/ui/fields/identity).

- Importieren Sie die gewünschten Daten in Adobe Experience Platform:

   - Informationen zu Adobe Analytics-Daten finden Sie unter [Verwenden von Adobe Analytics Report Suite-Daten in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - Informationen zu anderen Datentypen finden Sie unter [Erstellen eines Schemas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) und [Aufnehmen von Daten](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) in der Adobe Experience Platform-Dokumentation.

Sie profitieren von einer kanalübergreifenden Analyse, wenn Sie einen oder mehrere Ihrer zugeordneten Datensätze mit anderen Datensätzen, z. B. Callcenter-Daten, kombinieren, um Ihre Customer Journey Analytics-Verbindung zu definieren. Bei dieser Verbindungskonfiguration wird davon ausgegangen, dass diese anderen Datensätze bereits in jeder Zeile eine Personen-ID enthalten, die der zugeordneten ID ähnelt.


## Einschränkungen

>[!IMPORTANT]
>
>- Die Verwendung von `identityMap` als beständige ID wird nicht unterstützt. Sie müssen eine bestimmte Kennung im Datensatz (z. B. `ECID`) als beständige ID definieren.
>
>- Wenden Sie alle Änderungen, die Sie an dem Quellereignis-Datensatzschema vornehmen, auch auf das neue zugeordnete Datensatzschema an. Andernfalls wird der zugeordnete Datensatz beschädigt.
>
>- Wenn Sie den Quelldatensatz entfernen, stoppt der zugeordnete Datensatz die Verarbeitung und wird vom System entfernt.
>
>- Datennutzungsbezeichnungen werden nicht automatisch in das zugeordnete Datensatzschema übertragen. Wenn Sie Datennutzungsbezeichnungen auf das Quelldatensatzschema angewendet haben, müssen Sie diese Datennutzungsbezeichnungen manuell auf das zugeordnete Datensatzschema anwenden. Weitere Informationen finden Sie unter [Verwalten von Datennutzungsbezeichnungen in Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview) .

Das Stitching ist eine innovative und zuverlässige Funktion, die jedoch Einschränkungen hinsichtlich der Verwendung aufweist.

- Es werden nur Ereignis-Datensätze unterstützt. Andere Datensätze, wie beispielsweise Lookup-Datensätze, werden nicht unterstützt.
- Beim Stitching wird das für das Stitching verwendete Feld in keiner Weise umgewandelt. Beim Zuordnen wird der Wert im angegebenen Feld verwendet, da er im nicht zugeordneten Datensatz im Data Lake vorhanden ist.
- Beim Zuordnen wird zwischen Groß- und Kleinschreibung unterschieden. Wenn beispielsweise manchmal das Wort &quot;Bob&quot;im Feld erscheint und manchmal das Wort &quot;BOB&quot;erscheint, werden diese IDs als zwei separate Personen behandelt.

Vergewissern Sie sich, dass Sie die Zuordnung nicht mit Folgendem verwechseln:

- Die Zusammenführung von zwei oder mehr Datensätzen. Die Zuordnung gilt nur für einen Datensatz. Die Zusammenführung von Datensätzen erfolgt durch Einrichtung einer Customer Journey Analytics-Verbindung und Auswahl derselben Personen-ID für die ausgewählten Datensätze in der Verbindung.

- Der Join zweier Datensätze. Unter Customer Journey Analytics wird häufig ein Join für Suchen oder Klassifizierungen in Analysis Workspace verwendet. Obwohl das Stitching die Join-Funktion verwendet, umfasst der Prozess selbst mehr als nur Joins.

>[!MORELIKETHIS]
>
>[Feldbasierte Zuordnung](fbs.md)
>[Diagrammbasierte Zuordnung](gbs.md)
>[Stitching verwenden](use-stitching.md)
>[Häufig gestellte Fragen zum Stitching](faq.md)

