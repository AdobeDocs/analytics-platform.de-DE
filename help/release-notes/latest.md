---
title: Aktuelle Versionshinweise zu Customer Journey Analytics
description: Anzeigen der neuesten Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad333ea6-e90d-4c8f-8d61-9f8690784d6fid: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5cid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: f3aad257d518373812176cb123d799b83cf45520
workflow-type: tm+mt
source-wordcount: 1261
ht-degree: 20%

---

# Aktuelle Versionshinweise zu Customer Journey Analytics (September 2026)

**Letzte Aktualisierung**: 9. September 2026

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom September 2026. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion und Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| -----------|-----------|-----------|
| **Customer Journey Analytics MCP-Server-Plug**<br/> In: Verwenden Sie neue Customer Journey Analytics MCP-Server-Plug-ins für ChatGPT und Claude, um schnell auf Ihre Daten zuzugreifen. <p>Weitere Informationen finden Sie unter [Mit ChatGPT verbinden](https://developer.adobe.com/analytics-mcp/docs/guides/chatgpt) und [Mit Claude verbinden](https://developer.adobe.com/analytics-mcp/docs/guides/claude).</p> | &#x200B;1. September 2026 | &#x200B;1. September 2026 |
| **Unterstützung für zusätzliche Datennutzungskennzeichnungen**<br> Customer Journey Analytics unterstützt jetzt die folgenden zusätzlichen Datennutzungskennzeichnungen für Elemente in einem Datensatz:<ul><li>C2 - Datenexport von Drittanbietern einschränken (jetzt verfügbar)</li><li>C3 - Direkt identifizierbare Datenkombination einschränken (jetzt verfügbar)</li><li>C9 - Datenwissenschaft beschränken (Veröffentlichung im August oder September geplant)</li></ul><p>Weitere Informationen finden Sie unter [Bezeichnungen, Richtlinien und Marketing-Aktionen](/help/data-views/data-governance.md).</p> | | &#x200B;3. September 2026 |
| **Filterung und Reporting von Einverständnisrichtlinien**<br> Sie können jetzt Berichte dazu erstellen, welche Besucher Ihren Adobe Experience Platform-Einverständnisrichtlinien entsprechen. (Dimensionen und Metriken der Einverständnisrichtlinie werden zu den Datenansichten in Ihrer Verbindung hinzugefügt.)<p>Darüber hinaus können Sie Besuchende, die mit ihrer Zustimmung nicht einverstanden sind, ausschließen, bevor ihre Daten in Customer Journey Analytics aufgenommen werden.</p><p>(Link zur Dokumentation folgt.)<!--For more information, see Consent reporting and filtering overview.--></p> | | September 2026 |
| **Segmente auf den Berichtsdatumsbereich beschränken**<br/> Daten in einem Workspace-Bericht können über den Berichtsdatumsbereich hinaus erweitert werden, wenn ein Segment Datumsbereichskomponenten enthält.<p>Es ist jetzt eine neue Option verfügbar, mit der Sie die Ergebnisse auf den Datumsbereich des Berichts beschränken können, unabhängig von etwaigen im Segment enthaltenen Datumskomponenten.</p><p>Diese Option ist beim Erstellen oder Ändern eines Segments verfügbar, dessen Container der obersten Ebene Person ist.</p><p>Weitere Informationen finden Sie unter [Segmente erstellen](/help/components/segments/seg-builder.md#components).</p> | &#x200B;26. August 2026 | &#x200B;9. September 2026 |
| **Analysieren von LLM-Kundenerlebnissen in Analysis Workspace mit Conversation Insights**<br/> Customer Journey Analytics bringt jetzt unstrukturierte Chat-Daten in Analysis Workspace ein, sodass Sie Berichte über LLM-gestützte Browser- und Kauferlebnisse in Ihren Properties erstellen können.<p>Mit dieser Funktion können Sie:</p><ul><li>Sammeln Sie Eingabeaufforderungen, Antworten und Agentenmetadaten von Gesprächsagenten (entweder den benutzerdefinierten Agenten Ihres Unternehmens oder Adobe Brand Concierge) über Web SDK.</li><li>Analysieren Sie Absicht, Tonfall und Sentiment, damit Sie verstehen können, was Kunden fragen, wie Ihr Agent reagiert und wie Ihre Kunden über ihre Interaktionen denken.</li><li>Analysieren Sie im benötigten Umfang anhand Ihres vorhandenen Schemas, Ihrer Datensätze und Datenansichten und nutzen Sie dann die Gelegenheit, Einblicke in Analysis Workspace zu gewinnen.</li><li>Verknüpfen Sie Konversationen mit Ergebnissen, indem Sie Agenteninteraktionen mit Ihren allgemeinen Journey-Kunden verknüpfen, damit Sie echte Auswirkungen auf Konversion, Interaktion und mehr messen können.</li></ul><p>Zuvor waren LLM-gestützte Erlebnisse schwer zu messen und es war nahezu unmöglich, eine Verbindung zu den Journey-Systemen Ihrer bestehenden Kunden herzustellen.</p><p>(Link zur Dokumentation folgt.)</p> | | &#x200B;22. September 2026 |
| **Berichte zur Gesamtpopulation**<br/> Sie können jetzt in Profil- und Lookup-Datensätzen definierte Entitäten analysieren und Berichte dazu erstellen, die in einer Customer Journey Analytics-Verbindung vorhanden sind. Diese Analyse und das Reporting gehen über zeitbasierte Ereignisreihen aus Ereignisdatensätzen hinaus. <p>Diese Funktion ermöglicht neue Klassen von Abfragen, Metriken und Zielgruppendefinitionen, die den gesamten Umfang des Kundenstamms eines Unternehmens widerspiegeln.</p><p>(Link zur Dokumentation folgt.)</p> | | &#x200B;22. September 2026 |
| **Stündliche Warnhinweise**<br/> Sie können jetzt die Zeitgranularität eines Warnhinweises auf Stündlich festlegen.<p>Stündliche Warnhinweise sind für Daten vorgesehen, die innerhalb einer bestimmten Stunde eintreffen. Wenn die Daten eine Latenz von mehr als einer Stunde aufweisen, wird durch eine längere Granularität sichergestellt, dass der Warnhinweis vollständige Daten auswertet. Wenden Sie sich an einen Dateningenieur, wenn Sie sich nicht sicher sind, wie lange die Daten bis zur Ankunft benötigen.</p>p>(Link zur Dokumentation folgt.)</p> | | September 2026 |
| **Die Bereitstellung der Warnhinweise erfolgt gemäß der konfigurierten**<br/>. Warnhinweise werden jetzt am Ende des von Ihnen festgelegten Verzögerungsfensters bereitgestellt, unabhängig davon, ob die Daten für den angegebenen Ereignisbereich vollständig sind oder noch empfangen werden. Daten, die nach Ablauf des Zeitfensters eingehen, werden nicht in den Warnhinweis einbezogen.<p>Zuvor enthielten Warnhinweise eine Hintergrundverarbeitungsprüfung, die auf verspätete Daten wartete, selbst wenn dies bedeutete, dass Warnhinweise nach dem konfigurierten Verzögerungsfenster gesendet wurden.</p>p>(Link zur Dokumentation folgt.)</p> | | September 2026 |
| **Adobe Brand Visibility-Integration**<br/> Verbinden Sie Adobe Brand Visibility mit den Customer Journey Analytics-Daten Ihres Unternehmens, damit Sie messen können, wie sich die KI-gesteuerte Erkennung in echte Website-Interaktion und Geschäftsergebnisse niederschlägt.<p>(Link zur Dokumentation folgt.)</p> | | September 2026 |
| **Upgrade- und Implementierungsfähigkeiten in CX Enterprise Coworker**<br> Neue Fähigkeiten kommen zu den Mitarbeitern. Diese Kenntnisse erleichtern nahtlosere und einfachere Upgrades und Implementierungen für Customer Journey Analytics:<ul><li>**Implementierungshandbücher -**: Erstellen einer maßgeschneiderten Liste von Upgrade- oder Implementierungsschritten und -empfehlungen. Die Upgrade- und Implementierungshandbücher können dann mithilfe eines vordefinierten Playbooks in ein Co-Worker-Projekt umgewandelt werden.</li><li>**Intelligente Upgrade- und Implementierungs-Checklisten-Fähigkeiten**: Verwenden Sie das Coworker-Projekt, um den Implementierungsfortschritt anhand der maßgeschneiderten Upgrade- oder Implementierungs-Checkliste zu verwalten und zu verfolgen, den Projektstatus zu verwalten, über Teams hinweg zusammenzuarbeiten, Aufgaben zuzuweisen und bei Bedarf Genehmigungs-Gates einzuführen.</li><li>**Datenvalidierungsfähigkeiten**: Überprüfen Sie, ob Ihre Implementierung korrekt konfiguriert und mit Best Practices abgestimmt ist.</li></ul><p>(Links zur Dokumentation folgen.)</p> | | &#x200B;30. September 2026 |

### Fehlerbehebungen in Customer Journey Analytics

**Analysis Workspace**: AN-487374, AN-487119, AN-468907, AN-468810, AN-468363, AN-468096, AN-467414, AN-466986, AN-466982, AN-465073, AN-463571, AN-462373, AN-492801, AN-488821, AN-488452, AN-486517, AN-478930, AN-468325
**Komponenten**:
**Verbindungen**: AN-451458, AN-365942
**Content Analytics**:
**Geführte Analyse**: AN-485600
**EXPORTE**: AN-489161, AN-467131, AN-464746, AN-469034, AN-447252, AN-437803, AN-394444
**Datenansichten**: AN-478732, AN-468836, AN-467851, AN-487651, AN-423592
**Datenaufnahme**: AN-489829, AN-489722, AN-469451, AN-467436, AN-467049, AN-466087, AN-465049, AN-463524, AN-457433, AN-490288, AN-487500, AN-390916, AN-342311
**Implementierung**:
**Report Builder**: AN-487486, AN-478944, AN-470036, AN-468589, AN-468436, AN-456747, AN-456700, AN-442695, AN-492330, AN-490564, AN-468293, AN-460921
**Reporting**: AN-479145, AN-469095, AN-468070, AN-467786, AN-456684, AN-465257, AN-422685, AN-406114, AN-356706, AN-322733
**Segmentierung**: AN-486561, AN-278260
**Terminierte Berichte**: AN-479157
**Freigegebene Metriken und Dimensionen**:
**Zielgruppenanalyse**: AN-468237, AN-462553
**Sonstige**: AN-469601, AN-462817, AN-362308, AN-349757, AN-326432, AN-326345, AN-324341, AN-309317

## Zurückgestellte Funktionen

| Funktion und Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| -----------|-----------|-----------|
| **Streaming-Mediendienste: Unterstützung von Zeitplandaten** <br/>Sie können jetzt Zeitplandaten von früheren Live-Inhalten von Streaming-Medien hochladen, um Zuschauerzahlen einfacher und genauer zu verfolgen.<p>Im Folgenden finden Sie Beispiele für Live-Inhalte, die beim Hochladen von Zeitplandaten unterstützt werden:</p><ul><li>FAST-Plattformen (Free Ad Supported TV)</li><li>Lokale Datenströme</li><li>Live-Sportübertragungen</li></ul><p>Durch das Hochladen von Zeitplandaten können Sie die Zuschauerzahlen für einzelne Programme verfolgen, die in dem von Ihnen in der Upload-Datei angegebenen Zeitraum gelaufen sind. Sie können sogar Zuschauerzahlen für bestimmte Themen oder Programmsegmente erfassen.</p><p>Diese Funktionen sind unabhängig davon verfügbar, wie Sie die Erfassung von Streaming-Medien implementiert haben.</p><p>Zuvor war es bei der Analyse von Live-Inhalten schwierig, eine bestimmte Sitzung genau mit bestimmten Programmen zu verknüpfen, und es war nicht möglich, eine bestimmte Sitzung mit einzelnen Themen oder Programmsegmenten zu verknüpfen.</p><p>Weitere Informationen finden Sie unter [Hochladen von Zeitplandaten zur Verfolgung von Live-Inhalten](https://experienceleague.adobe.com/de/docs/media-analytics/using/media-use-cases/track-schedule-data).</p> | &#x200B;29. Oktober 2025 | TBD<p>(Ursprünglich für den 29. Oktober 2025 geplant)</p> |

>[!MORELIKETHIS]
>
>* [Frühere Versionshinweise zu Customer Journey Analytics für 2026](/help/release-notes/2026.md)
>* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
>* [Versionshinweise zur Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
>* [CX Enterprise - Versionshinweise](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
>* [Aktualisierungen der Dokumentation zu Customer Journey Analytics](/help/release-notes/doc-changes.md)

