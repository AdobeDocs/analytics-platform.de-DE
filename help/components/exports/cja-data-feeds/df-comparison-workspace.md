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
source-git-commit: 03beb4bd52769a5428ca084beacefd8996d4c810
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 0%
---
# Datendiskrepanzen zwischen Daten-Feeds und Analysis Workspace verstehen

{{release-limited-testing}}

Die Daten in einem Daten-Feed-Export stimmen nicht immer genau mit den Daten überein, die Sie in Analysis Workspace sehen. Die Informationen auf dieser Seite erläutern einige der Hauptgründe.

## Verarbeitungsfenster (Daten-Feeds) im Vergleich zum Reporting-Fenster (Analysis Workspace) {#processing-window}

Jeder Daten-Feed-Versand verwendet ein rollierendes 30-tägiges Verarbeitungsfenster. Das Verarbeitungsfenster liefert den historischen Kontext, der zur Klassifizierung der Ereignisse in einem Daten-Feed-Versand benötigt wird. Einzelheiten zum Verarbeitungsfenster, einschließlich Beispiele, finden Sie unter [Grundlegendes zum Verarbeitungsfenster](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-window).

In diesem Sinne ähnelt das Verarbeitungsfenster dem Berichtsfenster in Analysis Workspace (dem Datumsbereich, den Sie für einen Bericht auswählen). Es gibt jedoch wesentliche Unterschiede.

| Die wichtigsten Unterschiede | Reporting-Fenster (Analysis Workspace) | Verarbeitungsfenster (Daten-Feeds) |
|---------|---------|----------|
| **Datengrenze**<br/> Ob Daten in einem Bericht oder Feed enthalten sind | Flexibel<p>Ereignisse, die nicht in das Reporting-Fenster fallen, können dennoch in einen Workspace-Bericht aufgenommen werden, wenn die Ereignisse durch einen der folgenden Faktoren beeinflusst werden:</p><ul><li>**Dimension-Persistenz**: Kann bei Verwendung von Sitzung, benutzerdefinierter Zeit oder Metrik ([) über das Berichtsfenster hinaus bestehen bleiben](/help/data-views/component-settings/persistence.md#expiration-settings). Wie das Reporting-Fenster bei Verwendung des Fensters „Person Reporting[&#x200B; (Ablauf](/help/data-views/component-settings/persistence.md#expiration-settings). Daten werden aggregiert.</li><li>**Segmentqualifikation**: Segmente können standardmäßig über das Reporting-Fenster hinaus erweitert werden.<p>Benutzer können das Segment beim Erstellen auf das Reporting-Fenster beschränken.<!--add link to new docs--></p></li><li>**Sitzungsberechnung**: Sitzungen können über das Berichtsfenster hinaus ausgeführt werden. </li><li>**Abgeleitete Feldtransformationen**</li></ul> | Fest<p>Ereignisse, die außerhalb des Verarbeitungsfensters liegen, beeinflussen in der Regel keinen Daten-Feed. Das Verarbeitungsfenster gilt für die folgenden Faktoren:</p><ul><li>**Dimension-Persistenz**: Kann bei Verwendung der benutzerdefinierten Zeitdauer (Ablauf) über das Verarbeitungsfenster hinaus bestehen bleiben (bis [&#x200B; 90 Tage](/help/data-views/component-settings/persistence.md#expiration-settings) wie in Workspace. Kann nicht über das Verarbeitungsfenster hinaus bestehen bleiben, wenn das Fenster „Person Reporting“ [Ablauf](/help/data-views/component-settings/persistence.md#expiration-settings). Daten werden nicht aggregiert.</li><li>**Segmentqualifikation**: Immer auf das Verarbeitungsfenster beschränkt.</li><li>**Sitzungsberechnung**: Immer auf das Verarbeitungsfenster beschränkt.</li><li>**Abgeleitete Feldtransformationen**: Alle abgeleiteten Feldfunktionen, die auf Container verweisen, verwenden das Verarbeitungsfenster in Daten-Feed-Exporten.</li></ul> |
| **Zeitrahmen für den Bericht**<br/> Welche Ereignisse sind in einem Bericht oder Feed enthalten? | Wie im Reporting-Fenster. | Nicht dasselbe wie das Verarbeitungsfenster. <p>Der Zeitrahmen für den Bericht ist das Häufigkeitsfenster, das eine einzelne Stunde oder ein einzelner Tag am Ende des Verarbeitungsfensters sein kann.</p> |

>[!BEGINSHADEBOX]

**Beispiel**

Das folgende Beispiel zeigt, wie Unterschiede zwischen dem Reporting-Fenster und dem Verarbeitungsfenster zu Datendiskrepanzen zwischen Workspace-Berichten und Daten-Feed-Sendungen führen können.

Ein Benutzer hat sich vor 45 Tagen für ein Segment mit einem Personen-Container qualifiziert und hat heute ein Ereignis. Ein Workspace-Bericht mit einem 30-tägigen Berichtsfenster enthält das Benutzerereignis, da Segmente standardmäßig über das Berichtsfenster hinaus erweitert werden können. Die Daten-Feed-Bereitstellung für heute umfasst nicht das Ereignis, da die Segmentqualifikation auf das 30-tägige Verarbeitungsfenster beschränkt ist.

<!-- update the following graphic -->

![Datenunterschiede zwischen Workspace und Daten-Feeds](assets/data-feed-data-differences.png)


>[!ENDSHADEBOX]

## Wiederholungen zusammenfügen

Bei jeder Ausführung einer Zusammenfügungs-Wiederholung werden historische Identitätsdaten rückwirkend aktualisiert.

Daten-Feeds und Analysis Workspace behandeln Zuordnungswiederholungen wie folgt unterschiedlich:

* **Daten-Feeds**: Gibt die zugeordnete Identität nur zum Zeitpunkt des Exports an. Wiederholungsergebnisse werden nicht rückwirkend auf exportierte Dateien angewendet.

* **Analysis Workspace**: Zeigt die aktuellen zugeordneten Daten an, die bei jeder Ausführung einer Wiederholung rückwirkend aktualisiert werden. Historische Daten ändern sich nach jeder Wiederholung, sodass Workspace immer die neueste Identitätsauflösung widerspiegelt.

## Verspätete Ereignisse

In einem Daten-Feed können Ereignisse eintreffen, nachdem das Fenster für den Daten-Feed-Export geschlossen wurde.

Daten-Feeds und Analysis Workspace funktionieren hinsichtlich vergangener Ereignisse wie folgt unterschiedlich:

* **Daten-Feeds**: Exportiert Daten innerhalb eines festen Zeitfensters, basierend auf dem Zeitpunkt, zu dem Ereignisse empfangen werden.

  Ereignisse, die nach dem Schließen des Fensters eingehen, werden möglicherweise nicht in den Export einbezogen. Dies wird durch die von [&#x200B; gewählte &#x200B;](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-delay) beeinflusst.

* **Analysis Workspace**: Verarbeitet Daten zum Zeitpunkt des Berichts, sodass Ereignisse in Berichten unabhängig vom Zeitpunkt ihres Eingangs enthalten sind.

## Daten-Batching

Manchmal werden Daten in einem Batch übermittelt, der sich über einen längeren Zeitraum erstreckt.

Daten-Feeds und Analysis Workspace funktionieren in Bezug auf Batch-Daten unterschiedlich:

* **Daten-Feeds**: Verteilt Batch-Daten über jeden Tag oder jede Stunde basierend auf den ursprünglichen Zeitstempeln. Ein Batch mit Daten für 30 Tage wird beispielsweise über 30 Tage an Exporten verteilt, sodass in einem Export nur ein kleiner Teil angezeigt wird.

* **Analysis Workspace**: Zeigt alle Daten in einem Batch an, sobald sie vollständig verarbeitet sind, unabhängig vom im Batch enthaltenen Zeitbereich.

