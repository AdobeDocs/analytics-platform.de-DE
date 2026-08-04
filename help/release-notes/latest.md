---
title: Aktuelle Versionshinweise zu Customer Journey Analytics
description: Anzeigen der neuesten Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
hold: true
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad333ea6-e90d-4c8f-8d61-9f8690784d6fid: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5cid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: feb7b3364e7981c42e3a31f75acfbddfdc463485
workflow-type: tm+mt
source-wordcount: 795
ht-degree: 35%

---

# Aktuelle Customer Journey Analytics-Versionshinweise (August 2026)

**Letzte Aktualisierung**: 4. August 2026

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom August 2026. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion und Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| -----------|-----------|-----------|
| **Verbesserungen der Journey**<br> Arbeitsfläche: Die folgenden Verbesserungen der Journey-Arbeitsfläche sind jetzt verfügbar:<ul><li>Vergleichen Sie die Journey mit einem früheren Zeitrahmen. Vergleichen Sie die aktuelle Journey mit der Journey 4 Wochen vorher, 2 Quartale vorher, 1 Jahr vorher oder mit einem benutzerdefinierten Datumsbereich.</li><li>Zeigen Sie für einen ausgewählten Knoten die obersten Dimensionselemente an, die zu einem beliebigen Zeitpunkt im Journey nach dem ausgewählten Knoten stehen. Verwenden Sie dies, wenn der ausgewählte Knoten das Schlüsselereignis in Ihrer Analyse ist und Sie sehen möchten, was die Benutzer zu einem späteren Zeitpunkt tun.<p>Zuvor konnten nur die unmittelbar am häufigsten angezeigten Knoten vor oder nach dem ausgewählten Knoten angezeigt werden. </p></li><li>Ändern Sie die Form und den Stil der Pfeile zwischen den Knoten. Ziehen Sie die Pfeile zwischen Knoten, um die Form (Krümmung) des Pfeils zu ändern, und klicken Sie mit der rechten Maustaste auf einen Pfeil, um seinen Stil in eine der folgenden Optionen zu ändern: Volumenkörper, Gestrichelt, Punkte, Gestrichelt-Punkt oder Animiert.</li></ul><p></p>Weitere Informationen finden Sie unter [Konfigurieren einer Visualisierung „Journey-Arbeitsfläche“](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md). |  | &#x200B;18. August 2026 |
| **Unterstützung für zusätzliche Datennutzungskennzeichnungen**<br> Customer Journey Analytics unterstützt jetzt die folgenden zusätzlichen Datennutzungskennzeichnungen für Elemente in einem Datensatz:<ul><li>C2 - Datenexport von Drittanbietern einschränken (jetzt verfügbar)</li><li>C3 - Direkt identifizierbare Datenkombination einschränken (jetzt verfügbar)</li><li>C9 - Datenwissenschaft beschränken (Veröffentlichung im August geplant)</li></ul><p>Weitere Informationen finden Sie unter [Bezeichnungen, Richtlinien und Marketing-Aktionen](/help/data-views/data-governance.md).</p> | | August 2026 |
| **Filterung und Reporting von Einverständnisrichtlinien**<br> Sie können jetzt Berichte dazu erstellen, welche Besucher Ihren Adobe Experience Platform-Einverständnisrichtlinien entsprechen. (Dimensionen und Metriken der Einverständnisrichtlinie werden zu den Datenansichten in Ihrer Verbindung hinzugefügt.)<p>Darüber hinaus können Sie Besuchende, die mit ihrer Zustimmung nicht einverstanden sind, ausschließen, bevor ihre Daten in Customer Journey Analytics aufgenommen werden.</p><p>Weitere Informationen finden Sie unter Übersicht über Einverständnisberichte und -filter.</p> | | August 2026 |
| **Migrationsplaner: Adobe Analytics zu Customer Journey Analytics**<br> Der Migrationsplaner bietet einen Migrationsassistenten, der einige der komplexesten und zeitaufwendigsten Aufgaben im Zusammenhang mit einem Upgrade von Adobe Analytics auf Customer Journey Analytics automatisiert, einschließlich der Erstellung von XDM-Schemata und der Migration von AppMeasurement oder der Analytics-Erweiterung (Tags) zu Experience Platform Web SDK. <p>(Link zur Dokumentation folgt.)</p> | | Ende August oder September 2026 |
| **B2B: Person-Konto-Zuordnung**<br> B2B-Kontozuordnung reichert Ihre Ereignisdatensätze mit Kontoinformationen an und ermöglicht eine vollständige Analyse des gesamten Kunden-Journey in Customer Journey Analytics. <p>Wenn Ereignisse keine Konto-ID haben, die Customer Journey Analytics B2B edition für die Aufnahme benötigt, leitet die Kontozuordnung diese Informationen automatisch ab und fügt sie mithilfe des von Ihnen bereitgestellten Personenkonto-Zuordnungsdatensatzes hinzu.</p><p>(Link zur Dokumentation folgt.)</p> | | Ende August oder September 2026 |
| **Handbuch zu ersten Aufrufen der CJA Report API**<br> Handbuch zu ersten Aufrufen der Adobe Customer Journey Analytics-API enthält Anweisungen und Beispiele zur Konfiguration grundlegender Berichtsanfragen. | | &#x200B;10. August 2026 |
| **Datums-Trendanleitung für die CJA-Berichts**<br> API-Datums-Trendanleitung für Adobe Customer Journey Analytics enthält Anweisungen und Beispiele zur Konfiguration grundlegender Berichtsanfragen. | | &#x200B;17. August 2026 |

### Fehlerbehebungen in Customer Journey Analytics

**Analysis Workspace**:
**Komponenten**:
**Verbindungen**:
**Content Analytics**:
**Geführte Analyse**:
**Exporte**:
**Datenansichten**:
**Datenaufnahme**:
**Implementierung**:
**Report Builder**:
**Reporting**:
**Segmentierung**:
**Geplante Berichte**:
**Freigegebene Metriken und Dimensionen**:
**Zielgruppenanalyse**:
**Sonstige**:

## Zurückgestellte Funktionen

| Funktion und Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| -----------|-----------|-----------|
| **Streaming-Mediendienste: Unterstützung von Zeitplandaten** <br/>Sie können jetzt Zeitplandaten von früheren Live-Inhalten von Streaming-Medien hochladen, um Zuschauerzahlen einfacher und genauer zu verfolgen.<p>Im Folgenden finden Sie Beispiele für Live-Inhalte, die mit dem Upload von Zeitplandaten unterstützt werden:</p><ul><li>FAST-Plattformen (Free Ad Supported TV)</li><li>Lokale Datenströme</li><li>Live-Sportübertragungen</li></ul><p>Durch das Hochladen von Zeitplandaten können Sie die Zuschauerzahlen für einzelne Programme verfolgen, die in dem von Ihnen in der Upload-Datei angegebenen Zeitraum gelaufen sind. Sie können sogar Zuschauerzahlen für bestimmte Themen oder Programmsegmente erfassen.</p><p>Diese Funktionen sind unabhängig davon verfügbar, wie Sie die Erfassung von Streaming-Medien implementiert haben.</p><p>Zuvor war es bei der Analyse von Live-Inhalten schwierig, eine bestimmte Sitzung genau mit bestimmten Programmen zu verknüpfen, und es war nicht möglich, eine bestimmte Sitzung mit einzelnen Themen oder Programmsegmenten zu verknüpfen.</p><p>Weitere Informationen finden Sie unter [Hochladen von Zeitplandaten zur Verfolgung von Live-Inhalten](https://experienceleague.adobe.com/de/docs/media-analytics/using/media-use-cases/track-schedule-data). | &#x200B;29. Oktober 2025 | TBD<p>(Ursprünglich für den 29. Oktober 2025 geplant)</p> |

>[!MORELIKETHIS]
>
>* [Frühere Versionshinweise zu Customer Journey Analytics für 2026](/help/release-notes/2026.md)
>* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
>* [Versionshinweise zur Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
>* [CX Enterprise - Versionshinweise](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
>* [Aktualisierungen der Dokumentation zu Customer Journey Analytics](/help/release-notes/doc-changes.md)

