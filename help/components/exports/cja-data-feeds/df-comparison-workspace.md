---
description: Erfahren Sie, wie Sie die Funktionen von Daten-Feeds in Customer Journey Analytics und Adobe Analytics vergleichen
keywords: Clickstream;Daten-Feed;Daten-Feed;Data Feed
title: Vergleich der Funktionen von Daten-Feeds in Customer Journey Analytics und Adobe Analytics
feature: Components
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7f3fb46b9c1928f8b02ce2108b4e98b5cc8da766
workflow-type: tm+mt
source-wordcount: '1140'
ht-degree: 0%
---
# Datendiskrepanzen zwischen Daten-Feeds und Analysis Workspace verstehen

{{release-limited-testing}}

Die Daten in einem Daten-Feed-Export stimmen nicht immer genau mit den Daten überein, die Sie in Analysis Workspace sehen. Die Informationen auf dieser Seite erläutern einige der Hauptgründe.

Einige dieser Unterschiede rühren aus Verhaltensweisen von Workspace her, die nur schwer allein in Workspace-Berichten zu sehen sind, da Workspace-Daten aggregiert werden. Daten-Feeds liefern Daten auf Ereignisebene, sodass diese Verhaltensweisen deutlich werden, wenn Sie die Daten-Feed-Ausgabe mit Workspace-Berichten vergleichen.

## Verarbeitungsfenster (Daten-Feeds) im Vergleich zum Reporting-Fenster (Analysis Workspace) {#processing-window}

Jeder Daten-Feed-Versand verwendet ein rollierendes 30-tägiges Verarbeitungsfenster. Das Verarbeitungsfenster liefert den historischen Kontext, der zur Klassifizierung der Ereignisse in einem Daten-Feed-Versand benötigt wird. Einzelheiten zum Verarbeitungsfenster, einschließlich Beispiele, finden Sie unter [Grundlegendes zum Verarbeitungsfenster](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-window).

In diesem Sinne ähnelt das Verarbeitungsfenster dem Berichtsfenster in Analysis Workspace (dem Datumsbereich, den Sie für einen Bericht auswählen). Es gibt jedoch wesentliche Unterschiede.

| Die wichtigsten Unterschiede | Reporting-Fenster (Analysis Workspace) | Verarbeitungsfenster (Daten-Feeds) |
|---------|---------|----------|
| **Zeitrahmen für den Bericht**<br/> Welche Ereignisse sind in einem Bericht oder Feed enthalten? | Beginnt am ersten Tag des Kalendermonats, in dem das Berichtsfenster beginnt, und endet am Ende des Berichtsfensters.<p>Beispielsweise enthält ein Bericht mit einem Berichtsfenster vom 6. Oktober bis zum 5. November auch Ereignisse vom 1. Oktober bis zum 5. Oktober. Da Workspace-Daten aggregiert werden, sind diese zusätzlichen Ereignisse möglicherweise nur schwer zu beachten.</p><!--SME CHECK: Confirm that every Workspace report includes events from the first day of the calendar month in which the reporting window starts (per Luke, Nov 5, 2026), including segment qualification for segments limited to the reporting window. Other docs (persistence.md Person Reporting Window row, analysis-workspace/attribution/models.md lookback window) don't describe this yet.--> | Nicht dasselbe wie das Verarbeitungsfenster. <p>Der Zeitrahmen für den Bericht ist das Häufigkeitsfenster, das eine einzelne Stunde oder ein einzelner Tag am Ende des Verarbeitungsfensters sein kann.</p> |
| **Datengrenze**<br/> Ob Daten außerhalb des Fensters in einem Bericht oder Feed enthalten sind oder davon beeinflusst werden | Flexibel<p>Ereignisse vom ersten Tag des Kalendermonats, in dem das Berichtsfenster beginnt, werden in einen Workspace-Bericht aufgenommen, auch wenn sie vor das Berichtsfenster fallen. Weitere Informationen finden Sie oben unter **Zeitrahmen für den Bericht**.</p><p>Ereignisse, die nicht in das Reporting-Fenster fallen, können die Daten in einem Workspace-Bericht auch durch einen der folgenden Faktoren beeinflussen:</p><ul><li>**Dimension-Persistenz**: Kann bei Verwendung von Sitzung, benutzerdefinierter Zeit oder Metrik ([) über das Berichtsfenster hinaus bestehen bleiben](/help/data-views/component-settings/persistence.md#expiration-settings).</li><li>**Segmentqualifikation**: Segmente können standardmäßig über das Reporting-Fenster hinaus erweitert werden.<p>Benutzer können das Segment beim Erstellen auf das Reporting-Fenster beschränken. Selbst dann berücksichtigt die Segmentqualifikation Ereignisse vom ersten Tag des Kalendermonats, in dem das Reporting-Fenster beginnt.</p></li><li>**Sitzungsberechnung**: Sitzungen können über das Berichtsfenster hinaus ausgeführt werden. </li><li>**Abgeleitete Feldtransformationen**: Alle abgeleiteten Feldfunktionen, die auf Container verweisen, verwenden das Berichtsfenster.<!--SME CHECK: Confirm that Session- and Person-scoped derived field functions (Deduplicate, Next or Previous, Summarize, Date Math) are limited to the reporting window in Workspace, or whether Session scope can extend beyond it like session calculation. ALSO: In the Segment qualification bullet, add a link to the new docs about limiting a segment to the reporting window.--></li></ul> | Fest<p>Nur Ereignisse im Häufigkeitsfenster sind in einem Daten-Feed enthalten. Weitere Informationen finden Sie oben unter **Zeitrahmen für den Bericht**.</p><p>Ereignisse, die außerhalb des Häufigkeitsfensters, aber innerhalb des Verarbeitungsfensters liegen, können die Daten in einem Daten-Feed beeinflussen. Ereignisse, die vor das Verarbeitungsfenster fallen, können im Allgemeinen nicht. Das Verarbeitungsfenster begrenzt die folgenden Faktoren:</p><ul><li>**Dimension-Persistenz**: Bei Verwendung des Sitzungs-, Personen-Reporting- oder Metrik-Fensters (Ablauf[&#x200B; kann die Persistenz nicht über das Verarbeitungsfenster &#x200B;](/help/data-views/component-settings/persistence.md#expiration-settings). Im Gegensatz zu Workspace erstreckt sich der Lookback nicht auf den ersten Tag des Monats. Kann bei Verwendung des benutzerdefinierten Zeitfensters (Ablauf) über das Verarbeitungsfenster hinaus [&#x200B; (bis zu 90 Tage](/help/data-views/component-settings/persistence.md#expiration-settings) wie in Workspace. Sowohl in Workspace als auch in den Daten-Feeds erstreckt sich der benutzerdefinierte Zeit-Lookback nicht auf den ersten Tag des Monats.<p>**Hinweis:** Derzeit ist die Gültigkeit der benutzerdefinierten Zeit auch auf das Verarbeitungsfenster beschränkt. Die Unterstützung benutzerdefinierter Zeiten, die über das Verarbeitungsfenster hinausgehen, wird bald verfügbar sein.</p></li><li>**Segmentqualifikation**: Immer auf das Verarbeitungsfenster beschränkt. Im Gegensatz zu Workspace gilt nicht für den ersten Tag des Monats.</li><li>**Sitzungsberechnung**: Immer auf das Verarbeitungsfenster beschränkt.</li><li>**Abgeleitete Feldtransformationen**: Alle abgeleiteten Feldfunktionen, die auf Container verweisen, verwenden das Verarbeitungsfenster in Daten-Feed-Exporten.</li></ul> |

>[!BEGINSHADEBOX]

**Beispiel**

Die folgenden Beispiele veranschaulichen, wie Unterschiede zwischen dem Reporting-Fenster und dem Verarbeitungsfenster zu Datendiskrepanzen zwischen Workspace-Berichten und Daten-Feed-Sendungen führen können.

* **Zeitraum für den Bericht**: Ein Benutzer hat am 1. Oktober ein Ereignis, das einen Dimensionswert festlegt, und später im Oktober weitere Ereignisse. Ein Workspace-Bericht mit einem Berichtsfenster, das am 6. Oktober beginnt, enthält das Ereignis vom 1. Oktober, da Workspace Ereignisse vom ersten Tag des Monats an enthält. Der am 1. Oktober festgelegte Wert kann auch im Berichtsfenster für die Ereignisse des Benutzers beibehalten werden. Ein Daten-Feed-Versand mit einem Verarbeitungsfenster, das am 6. Oktober beginnt, berücksichtigt nicht das Ereignis vom 1. Oktober, sodass der von ihm festgelegte Wert nicht für die Ereignisse des Benutzers im Versand beibehalten wird.

* **Segmentqualifikation**: Ein Benutzer hat sich vor 45 Tagen für ein Segment mit einem Personen-Container qualifiziert und hat heute ein Ereignis. Ein Workspace-Bericht mit einem 30-tägigen Berichtsfenster enthält das Benutzerereignis, da Segmente standardmäßig über das Berichtsfenster hinaus erweitert werden können. Die Daten-Feed-Bereitstellung für heute umfasst nicht das Ereignis, da die Segmentqualifikation auf das 30-tägige Verarbeitungsfenster beschränkt ist.

<!-- update the following graphic: ![Data differences between workspace and data feeds](assets/data-feed-data-differences.png) -->

>[!ENDSHADEBOX]

## Wiederholungen zusammenfügen

Bei jeder Ausführung einer Zusammenfügungs-Wiederholung werden historische Identitätsdaten rückwirkend aktualisiert.

Daten-Feeds und Analysis Workspace behandeln Zuordnungswiederholungen wie folgt unterschiedlich:

* **Daten-Feeds**: Gibt die zugeordnete Identität nur zum Zeitpunkt des Exports an. Wiederholungsergebnisse werden nicht rückwirkend auf exportierte Dateien angewendet.

* **Analysis Workspace**: Zeigt die aktuellen zugeordneten Daten an, die bei jeder Ausführung einer Wiederholung rückwirkend aktualisiert werden. Historische Daten ändern sich nach jeder Wiederholung, sodass Workspace immer die neueste Identitätsauflösung widerspiegelt.

## Verspätete Ereignisse

In einem Daten-Feed können Ereignisse eintreffen, nachdem das Fenster für den Daten-Feed-Export geschlossen wurde.

Daten-Feeds und Analysis Workspace funktionieren hinsichtlich vergangener Ereignisse wie folgt unterschiedlich:

* **Daten-Feeds**: Exportiert Daten innerhalb eines festen Zeitfensters (Stunde oder Tag jedes Versands) basierend auf Ereignis-Zeitstempeln.

  Vor der Verarbeitung jedes Versands wartet Customer Journey Analytics auf die [Verarbeitungsverzögerung](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-delay) die Sie auswählen. Ereignisse, die während der Verarbeitungsverzögerung eintreffen, werden in den Versand einbezogen. Ereignisse, die nach Beginn der Verarbeitung eingehen, werden nicht in die Daten-Feed-Datei aufgenommen.

* **Analysis Workspace**: Verarbeitet Daten zum Zeitpunkt des Berichts, sodass Ereignisse in Berichten unabhängig vom Zeitpunkt ihres Eingangs enthalten sind.

## Daten-Batching

Manchmal werden Daten in einem Batch übermittelt, der sich über einen längeren Zeitraum erstreckt.

Daten-Feeds und Analysis Workspace funktionieren in Bezug auf Batch-Daten unterschiedlich:

* **Daten-Feeds**: Verteilt Batch-Daten über jeden Tag oder jede Stunde basierend auf den ursprünglichen Zeitstempeln. Ein Batch mit Daten für 30 Tage wird beispielsweise über 30 Tage an Exporten verteilt, sodass in einem Export nur ein kleiner Teil angezeigt wird.

* **Analysis Workspace**: Zeigt alle Daten in einem Batch an, sobald sie vollständig verarbeitet sind, unabhängig vom im Batch enthaltenen Zeitbereich.

