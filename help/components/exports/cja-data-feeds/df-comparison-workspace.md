---
description: Erfahren Sie, wie Sie die Funktionen von Daten-Feeds in Customer Journey Analytics und Adobe Analytics vergleichen
keywords: Clickstream;Daten-Feed;Daten-Feed;Data Feed
title: Vergleich der Funktionen von Daten-Feeds in Customer Journey Analytics und Adobe Analytics
feature: Components
hide: true
source-git-commit: de8748a1dddbc0ddaadca4c805c9b4aba99a4267
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 0%

---

# Datendiskrepanzen zwischen Daten-Feeds und Analysis Workspace verstehen

{{release-limited-testing}}

Die Daten in einem Daten-Feed-Export stimmen nicht immer genau mit den Daten überein, die Sie in Analysis Workspace sehen. Die Informationen auf dieser Seite erläutern einige der Hauptgründe.

## Lookback-Datumsbereich (Daten-Feeds) im Vergleich zum Reporting-Datumsbereich (Analysis Workspace)

Der Lookback-Datumsbereich in Daten-Feeds bestimmt, wie weit Customer Journey Analytics zurückblickt, wenn Ereignisse gefunden werden, die für eine Daten-Feed-Bereitstellung qualifiziert sind. Weitere Informationen zum Lookback-Datumsbereich, einschließlich Beispiele, finden Sie unter [Grundlegendes zum Lookback-Datumsbereich](/help/components/exports/cja-data-feeds/create-feed.md#understand-the-lookback-date-range).

In diesem Sinne ähnelt der Lookback-Datumsbereich dem Berichtsdatumsbereich in Analysis Workspace. Es gibt jedoch wesentliche Unterschiede.

| Die wichtigsten Unterschiede | Datumsbereich für Berichte (Analysis Workspace) | Lookback-Datumsbereich (Daten-Feeds) |
|---------|---------|----------|
| **Datengrenze**<br/> Ob Daten in einem Bericht oder Feed enthalten sind | Flexibel<p>Ereignisse, die außerhalb des Datumsbereichs des Berichts liegen, können weiterhin in einen Workspace-Bericht aufgenommen werden, wenn die Ereignisse durch einen der folgenden Faktoren beeinflusst werden:</p><ul><li>**Dimension-Persistenz**: Kann über den Datumsbereich des Berichts hinaus bestehen bleiben. Daten werden aggregiert.</li><li>**Segmentqualifikation**: Segmente können standardmäßig über den Datumsbereich des Berichts hinaus erweitert werden.<p>Benutzer können das Segment beim Erstellen auf den Datumsbereich des Berichts beschränken.<!--add link to new docs--></p></li><li>**Sitzungsberechnung**: Sitzungen können über den Datumsbereich des Berichts hinausgehen. </li><li>**Abgeleitete Feldtransformationen**</li></ul> | Fest<p>Ereignisse, die außerhalb des Lookback-Datumsbereichs liegen, werden nie in einen Daten-Feed eingeschlossen, unabhängig davon, ob sie durch die folgenden Faktoren beeinflusst werden:</p></p><ul><li>**Dimension-Persistenz**: Kann nicht über den Lookback-Datumsbereich hinaus beibehalten werden. Daten werden nicht aggregiert.</li><li>**Segmentqualifikation**: Immer auf den Datumsbereich des Lookback beschränkt.</li><li>**Sitzungsberechnung**: Immer auf den Lookback-Datumsbereich beschränkt.</li><li>**Abgeleitete Feldtransformationen**: Alle abgeleiteten Feldfunktionen, die auf Container verweisen, verwenden den Lookback-Datumsbereich in Daten-Feed-Exporten.</li></ul><p>Weitere Informationen zum Konfigurieren des Lookback-Datumsbereichs finden Sie unter [Erstellen eines Daten-Feeds](/help/components/exports/cja-data-feeds/create-feed.md#create-and-configure-a-data-feed).</p> |
| **Reporting-Fenster**<br/> Der Zeitrahmen, über den berichtet werden soll | Wie das Reporting-Fenster (der Zeitrahmen, über den Sie einen Bericht erstellen möchten). | Nicht identisch mit dem Zeitrahmen, über den Sie einen Bericht erstellen möchten. <p>Der Zeitrahmen für den Bericht ist das Häufigkeitsfenster, das eine einzelne Stunde oder ein einzelner Tag sein kann.</p> |

>[!BEGINSHADEBOX]

**Beispiel**

Das folgende Beispiel zeigt, wie Unterschiede zwischen dem Berichtsdatumsbereich und dem Lookback-Datumsbereich zu Datendiskrepanzen zwischen Workspace-Berichten und Daten-Feed-Sendungen führen können.

Ereignis A trat vor 85 Tagen auf und befindet sich in einer Dimension mit einer Persistenzeinstellung von 90 Tagen (z. B. ein Attributionsfenster, auf das eine Kampagne klickt). Das Ereignis wird im Analysis Workspace-Bericht und nicht in der Daten-Feed-Bereitstellung angezeigt.

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

  Ereignisse, die nach dem Schließen des Fensters eingehen, werden möglicherweise nicht in den Export einbezogen. Dies wird durch den [Lookback-Datumsbereich](#lookback-date-range-data-feeds-vs-reporting-date-range-analysis-workspace) beeinflusst.

* **Analysis Workspace**: Verarbeitet Daten zum Zeitpunkt des Berichts, sodass Ereignisse in Berichten unabhängig vom Zeitpunkt ihres Eingangs enthalten sind.

## Daten-Batching

Manchmal werden Daten in einem Batch übermittelt, der sich über einen längeren Zeitraum erstreckt.

Daten-Feeds und Analysis Workspace funktionieren in Bezug auf Batch-Daten unterschiedlich:

* **Daten-Feeds**: Verteilt Batch-Daten über jeden Tag oder jede Stunde basierend auf den ursprünglichen Zeitstempeln. Ein Batch mit Daten für 30 Tage wird beispielsweise über 30 Tage an Exporten verteilt, sodass in einem Export nur ein kleiner Teil angezeigt wird.

* **Analysis Workspace**: Zeigt alle Daten in einem Batch an, sobald sie vollständig verarbeitet sind, unabhängig vom im Batch enthaltenen Zeitbereich.

