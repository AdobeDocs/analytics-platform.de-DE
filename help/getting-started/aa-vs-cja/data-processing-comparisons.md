---
title: Vergleich der Datenverarbeitung über Adobe Analytics- und CJA-Berichterstellungsfunktionen hinweg
description: Machen Sie sich mit den Unterschieden bei der Datenverarbeitung für die verschiedenen Berichterstellungsfunktionen vertraut.
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
source-git-commit: 7c3bbe2829c83406b2e6824e509c34459ae00f94
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 21%

---

# Vergleich der Datenverarbeitung über Adobe Analytics- und CJA-Berichterstellungsfunktionen hinweg

Das Verständnis der Unterschiede bei der Datenverarbeitung für die verschiedenen Berichterstellungsfunktionen kann hilfreich sein, um zu verstehen, welche Metriken wo und warum sie sich unterscheiden können.

Da beispielsweise &quot;Besuche&quot;als Metrik in Adobe Analytics zur Datenverarbeitungszeit definiert und &quot;Sitzungen&quot;als Metrik in CJA zur Berichtszeit berechnet wird, können die beiden Metriken je nach den Regeln, die für die Sitzungsdefinition in der CJA-Datenansicht verwendet werden, unterschiedlich sein.

Außerdem sind weder Besuche noch Sitzungen als Metrik in Datensätzen verfügbar, die vom Analytics Source Connector erstellt wurden. Daher müssen Sie die Sitzung in Ihrer Abfragelogik definieren, um Vergleiche durchzuführen.

## Terminologie {#terms}

In der folgenden Tabelle wird die Terminologie für die verschiedenen Arten von Verarbeitungslogik definiert, die auf Adobe Analytics und CJA angewendet werden:

| Begriff | Definition | Hinweise |
| --- | --- | --- |
| Verarbeitungszeitlogik | Logik, die ausgeführt wird, wenn Daten verarbeitet werden, bevor sie zu Berichts- und Analysezwecken gespeichert werden. | Diese Logik wird in historische Daten &quot;gebacken&quot; und kann im Allgemeinen nicht einfach geändert werden. |
| Berichtszeitlogik | Logik, die zum Zeitpunkt der Berichterstellung ausgeführt wird. | Diese Logik kann zur Berichtslaufzeit auf zukünftige und historische Daten auf zerstörungsfreie Weise angewendet werden. |
| Logik auf Trefferebene | Logik, die Zeilen für Zeile angewendet wird. | Beispiele: Verarbeitungsregeln, VISTA, bestimmte Marketing-Kanalregeln. |
| Besuchsebene - Logik | Logik, die auf Besuchsebene angewendet wird. | Beispiele: Besuchs- und Sitzungsdefinition. |
| Logik auf Besucherebene | Logik, die auf Besucherebene angewendet wird. | Beispiel: Geräteübergreifende/kanalübergreifende Besucherzuordnung. |
| Segmentlogik (Filterlogik) | Auswertung der Segmentregeln für Treffer/Besuch/Besucher (Ereignis/Sitzung/Person) (Filter). | Beispiel: Leute, die rote Schuhe gekauft haben. |
| Berechnete Metriken | Bewertung benutzerdefinierter Metriken, die von Kunden erstellt wurden und auf komplexen Formeln einschließlich Segmenten und Filtern basieren können. | Beispiel: Anzahl der Personen, die rote Schuhe gekauft haben. |
| Attributionslogik | Logik zur Berechnung der Attribution. | Beispiel: Persistenz der eVar. |

{style=&quot;table-layout:auto&quot;}

Im Laufe der Zeit haben Adobe Analytics und jetzt Customer Journey Analytics ihre Flexibilität verbessert, indem sie die Ausführung der Datendlogik auf Besuchs- und Besucherebene zur Berichtslaufzeit ermöglichen.

## Datenverarbeitungstypen {#types}

Die für Adobe Analytics und CJA durchgeführten Datenverarbeitungsschritte und der Zeitpunkt dieser Schritte variieren von der Analytics-Funktion zur Analytics-Funktion. Die nachstehende Tabelle bietet eine Zusammenfassung der Datenverarbeitungstypen für jede Analytics-Funktion und wann die Datenverarbeitung angewendet wird.

| Analytics-Funktion | Zur Verarbeitungszeit angewendet | Zur Berichtszeit angewendet | Nicht verfügbar | Hinweise |
| --- | --- | --- | --- | --- |
| [Core AA](https://experienceleague.adobe.com/docs/analytics.html?lang=de) Berichterstellung<br/>(ohne Attribution IQ oder Virtual Report Suites mit Berichtszeitverarbeitung) | <ul><li>[Verarbeitungsregeln](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=de)</li><li>[VISTA-Regeln](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=en)</li><li>Trefferebene [Marketing-Kanalregeln](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html?lang=de)</li><li>Marketing-Kanalregeln auf Besuchsebene (siehe Hinweis)</li><li>Besuchsdefinition</li><li>Attributionslogik</li></ul> | <ul><li>Segmentlogik</li><li>Berechnete Metriken</li></ul> | <ul><li>Geräteübergreifende Analyse (siehe Hinweis)</li></ul> | <ul><li>Die geräteübergreifende Analyse erfordert die Verwendung von Virtual Report Suites mit Berichtszeitverarbeitung.</li><li>&quot;Marketing-Kanalregeln auf Besuchsebene&quot;umfassen Folgendes: **Ist erste Seite des Besuchs**, **Last Touch-Kanal überschreiben** und **Marketing-Kanalablauf**. (Siehe [Dokumentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=de).</li></ul> |
| Core AA [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=en) | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>Marketing-Kanalregeln auf Trefferebene</li><li>Marketing-Kanalregeln auf Besuchsebene</li><li>Besuchsdefinition</li><li>Attributionslogik</li></ul> | <ul><li>Segmentlogik</li></ul> | <ul><li>Berechnete Metriken</li><li>Geräteübergreifende Analyse</li></ul> |  |
| Core AA [Daten-Feeds](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=en) | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>Marketing-Kanalregeln auf Trefferebene</li><li>Marketing-Kanalregeln auf Besuchsebene</li><li>Besuchsdefinition (Besuchsfeld)</li><li>Attributionslogik (in Post-Spalten)</li></ul> |  | <ul><li>Segmentlogik</li><li>Berechnete Metriken</li><li>Geräteübergreifende Analyse</li></ul> | <ul><li>ID-Zuordnungen für bestimmte Spalten, die mit Marketing-Kanälen in Daten-Feeds in Verbindung stehen, sind nicht in Daten-Feeds enthalten. (Siehe [Datenfeed-Dokumentation](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=de).</li></ul> |
| Core AA [Livestream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) | <ul><li> Verarbeitungsregeln</li><li>VISTA-Regeln</li><ul> |  | <ul><li>Marketing-Kanalregeln auf Trefferebene</li><li>Marketing-Kanalregeln auf Besuchsebene</li><li>Besuchslogik</li><li>Attributionslogik</li><li>Segmentlogik</li><li>Berechnete Metriken</li><li>Geräteübergreifende Analyse</li></ul> |  |
| Core AA [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=de) | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>Besuchsdefinition (siehe Hinweis)</li><li>Geräteübergreifende Analyse (siehe Hinweis)</li></ul> | <ul><li>Marketing-Kanalregeln auf Trefferebene (siehe Hinweis)</li><li>Marketing-Kanalregeln auf Besuchsebene (siehe Hinweis) Attributionslogik</li><li>Segmentlogik</li><li>Berechnete Metriken</li></ul> |  | <ul><li>Die geräteübergreifende Analyse erfordert die Verwendung von Virtual Report Suites mit Berichtszeitverarbeitung.</li><li>Attribution IQ in Core Analytics verwendet Marketing-Kanäle, die vollständig zur Berichtszeit abgeleitet wurden (d. h. abgeleitete Mid-Werte).</li><li>Attribution IQ verwendet eine Besuchsdefinition für Verarbeitungszeiten, es sei denn, diese wird in einer VRS zur Berichtszeitverarbeitung verwendet.</li></ul> |
| Core AA Virtual Report Suites mit [Berichtszeitverarbeitung](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en) (VRS RTP) | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>[Geräteübergreifende Analyse](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=de)</li></ul> | <ul><li>Besuchsdefinition</li><li>Attributionslogik</li><li>Segmentlogik</li><li>Berechnete Metriken</li><li>Andere VRS RTP-Einstellungen</li></ul> | <ul><li>Marketing-Kanalregeln auf Trefferebene</li><li>Marketing-Kanalregeln auf Besuchsebene</li></ul> | <ul><li>Siehe VRS RTP [Dokumentation](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en).</li></ul> |
| [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de)-basierter Datensatz in AEP Data Lake | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>Marketing-Kanalregeln auf Trefferebene</li><li>Feldbasiertes Stitching (siehe Hinweis)</li></ul> |  | <ul><li>[Marketing-Kanalregeln auf Besuchsebene](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en)</li><li>Besuchslogik</li><li>Attributionslogik</li><li>Filterlogik</li></ul> | <ul><li>Muss Ihre eigene Filterlogik und berechnete Metriken anwenden</li><li>Beim feldbasierten Stitching wird zusätzlich zu dem vom Analytics Source Connector erstellten Datensatz ein separater zugeordneter Datensatz erstellt.</li></ul> |
| [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=de) Berichterstellung | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>Trefferebene [Marketing-Kanalregeln](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en)</li><li>[Verbindungseinstellungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=de)</li><li>Feldbasiertes Stitching (siehe Hinweis)</li></ul> | <ul><li>Sitzungsdefinition</li><li>[Datenansichtseinstellungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=de)</li><li>Attributionslogik</li><li>Berechnete Metriken</li><li>Filterlogik</li></ul> | <ul><li>Marketing-Kanalregeln auf Besuchsebene</li></ul> | <ul><li>Muss einen zugewiesenen Datensatz verwenden, um die feldbasierte Zuordnung nutzen zu können.</li></ul> |

{style=&quot;table-layout:auto&quot;}
