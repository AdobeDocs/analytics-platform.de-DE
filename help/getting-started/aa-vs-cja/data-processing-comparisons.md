---
title: Vergleich der Datenverarbeitung zwischen Reporting-Funktionen von Adobe Analytics und Customer Journey Analytics
description: Verstehen der Unterschiede bei der Datenverarbeitung für die verschiedenen Reporting-Funktionen
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
feature: Basics
role: User
source-git-commit: 0e9dc47b80db142801a94dcbf31470d99a610949
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 64%

---

# Vergleich der Datenverarbeitung zwischen Adobe Analytics und Customer Journey Analytics

Häufig ist es erforderlich, Daten zu verarbeiten, damit sie für Berichte nützlich werden. Sie können diese Daten in verschiedenen Phasen der Journey verarbeiten, von der Datenerfassung bis zur Erstellung des Berichts oder der Visualisierung.

In Adobe Analytics erfolgt der Großteil dieser Datenverarbeitung unmittelbar nach der Datenerfassung. Funktionen wie VISTA-Regeln, Verarbeitungsregeln sowie Verarbeitungsregeln für Marketing-Kanäle stehen zur Verfügung, um diese **Verarbeitung zum Zeitpunkt der Erfassung** zu unterstützen.
Die Daten werden dann gespeichert, und zum Zeitpunkt der Berichtserstellung kann eine zusätzliche Verarbeitung durchgeführt werden. Beispielsweise können Sie Dimensionen aufschlüsseln, eine Segmentierung anwenden oder ein anderes Attributionsmodell auswählen. Diese **Verarbeitung zum Zeitpunkt der Berichtserstellung** erfolgt in Echtzeit.

In Adobe Analytics ist der Verarbeitungsumfang zum Zeitpunkt der Berichtserstellung normalerweise kleiner als zum Zeitpunkt der Erfassung.

![Verarbeitung zum Zeitpunkt der Erfassung mit Adobe Analytics](../assets/aa-processing.png)

Im Gegensatz dazu ist Customer Journey Analytics so konzipiert, dass eine minimale Vorabverarbeitung der Erfassungszeit erforderlich ist, bevor Daten organisiert und gespeichert werden. Die zugrunde liegende Architektur von Customer Journey Analytics ist so konzipiert, dass sie mit den gespeicherten Daten zur Berichtszeit funktioniert. Customer Journey Analytics bietet seine leistungsstarke Berichtszeitverarbeitungsfunktion nicht nur in Analysis Workspace. Zusätzliche Berichtszeitverarbeitungsfunktionen sind über die Definition von [Komponenten](/help/data-views/component-settings/overview.md) und [abgeleiteten Feldern](/help/data-views/derived-fields/derived-fields.md) in Ihren Datenansichten verfügbar.

![Verarbeitung zum Zeitpunkt der Berichtserstellung mit Customer Journey Analytics](../assets/cja-processing.png)

Das Verständnis der Unterschiede bei der Datenverarbeitung für die verschiedenen Berichtsfunktionen kann hilfreich sein, um zu verstehen, welche Metriken wo verfügbar sind und warum sie sich unterscheiden können.

Beispielsweise wird *Besuche* zur Datenverarbeitungszeit als Metrik in Adobe Analytics definiert. Und *Sitzungen* wird in Customer Journey Analytics zum Zeitpunkt der Berichterstellung als Metrik berechnet. Daher können die beiden Metriken je nach den Regeln für die Sitzungsdefinition in einer Customer Journey Analytics-Datenansicht unterschiedlich sein.

Außerdem sind Besuche und Sitzungen als Metrik in Datensätzen, die vom Analytics-Quell-Connector erstellt wurden, nicht verfügbar. Daher müssten Sie die Sitzung in Ihrer Abfragelogik definieren, um Vergleiche durchzuführen.

## Terminologie {#terms}

In der folgenden Tabelle wird die Terminologie für die verschiedenen Arten von Verarbeitungslogik definiert, die auf Adobe Analytics und Customer Journey Analytics angewendet werden:

| Begriff | Definition | Hinweise |
| --- | --- | --- |
| Verarbeitung zum Zeitpunkt der Erfassung | Logik, die ausgeführt wird, wenn Daten erfasst und verarbeitet werden, bevor sie zu Berichts- und Analysezwecken gespeichert werden. | Diese Logik wird in historische Daten aufgenommen und kann im Allgemeinen nicht einfach geändert werden. |
| Verarbeitung zum Zeitpunkt der Berichtserstellung | Logik, die zum Zeitpunkt der Berichtsausführung ausgeführt wird. | Diese Logik kann zur Berichtslaufzeit auf zerstörungsfreie Weise auf zukünftige und historische Daten angewendet werden. |
| Logik auf Trefferebene | Logik, die Zeile für Zeile angewendet wird. | Beispiele: Verarbeitungsregeln, VISTA, bestimmte Regeln von Marketing-Kanälen. |
| Logik auf Besuchsebene | Logik, die auf Besuchsebene angewendet wird. | Beispiele: Besuchs- und Sitzungsdefinition. |
| Logik auf Besucherebene | Logik, die auf Personenebene angewendet wird. | Beispiel: Geräteübergreifende/kanalübergreifende Personenzuordnung. |
| Segmentlogik | Auswertung der Segmentregeln für Ereignis/Besuch/Person (Ereignis/Sitzung/Person). | Beispiel: Personen, die rote Schuhe gekauft haben. |
| Berechnete Metriken | Auswertung kundenerstellter benutzerdefinierter Metriken. Berechnete Metriken können auf komplexen Formeln einschließlich Segmenten basieren. | Zum Beispiel die Anzahl der Personen, die rote Schuhe gekauft haben. |
| Attributionslogik | Logik zur Berechnung der Attribution. | Beispiel: eVar-Persistenz. |
| Komponenteneinstellungen | Anwenden von Anpassungen auf Metriken oder Dimensionen wie Attribution, Verhalten, Format und andere | Beispiel: Wert-Bucketing zum Kombinieren numerischer Werte basierend auf einem Bereich |
| Abgeleitete Felder | Logik, die für Schema- oder Standardfelder als Teil der Definition von Komponenten in einer Datenansicht gilt. | Beispiel: Erstellen einer neuen Marketing-Kanal-Dimension |

{style="table-layout:auto"}

Im Laufe der Zeit wurde die Flexibilität von Adobe Analytics und jetzt Customer Journey Analytics verbessert, indem die Ausführung der Logik für Daten auf Besuchs- und Personenebene zur Berichtslaufzeit ermöglicht wurde.

## Typen von Datenverarbeitung {#types}

Die von Adobe Analytics und Customer Journey Analytics durchgeführten Datenverarbeitungsschritte und der Zeitpunkt dieser Schritte variieren von Funktion zu Funktion. Die nachstehende Tabelle bietet eine Zusammenfassung der Arten der Datenverarbeitung für jede Funktion und gibt an, wann die Datenverarbeitung angewendet wird.

| Funktion | Zur Verarbeitungszeit angewendet | Zur Berichtszeit angewendet | Nicht verfügbar | Hinweise |
| --- | --- | --- | --- | --- |
| [Adobe Analytics](https://experienceleague.adobe.com/de/docs/analytics) Reporting<br/>(ohne erweiterte Attributionsfunktionen oder Virtual Report Suites mit Verarbeitung zur Berichtszeit) | <ul><li>[Verarbeitungsregeln](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/c-processing-rules/processing-rules)</li><li>[VISTA-Regeln](https://experienceleague.adobe.com/en/docs/analytics/technotes/terms)</li><li>Trefferebene [Regeln von Marketing-Kanälen](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules)</li><li>Regeln von Marketing-Kanälen auf Besuchsebene (siehe Hinweis)</li><li>Besuchsdefinition</li><li>Attributionslogik</li></ul> | <ul><li>Segmentlogik</li><li>Berechnete Metriken</li></ul> | <ul><li>Cross-Device Analytics (siehe Hinweis)</li></ul> | <ul><li>Geräteübergreifende Analysen erfordern die Verwendung von Virtual Report Suites mit Berichtszeitverarbeitung.</li><li>Die „Regeln für Marketing-Kanäle auf Besuchsebene“ umfassen Folgendes: **Ist erste Seite des Besuchs**, **Last Touch-Kanal überschreiben** und **Marketing-Kanalgültigkeit**. (Siehe die [Dokumentation](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels).)</li></ul> |
| Adobe Analytics [Data Warehouse](https://experienceleague.adobe.com/de/docs/analytics/export/data-warehouse/data-warehouse) | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>Regeln für Marketing-Kanäle auf Trefferebene</li><li>Regeln für Marketing-Kanäle auf Besuchsebene</li><li>Besuchsdefinition</li><li>Attributionslogik</li></ul> | <ul><li>Segmentlogik</li></ul> | <ul><li>Berechnete Metriken</li><li>Cross-Device Analytics</li></ul> |     |
| Adobe Analytics-[Daten-Feeds](https://experienceleague.adobe.com/de/docs/analytics/export/analytics-data-feed/data-feed-overview) | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>Regeln für Marketing-Kanäle auf Trefferebene</li><li>Regeln für Marketing-Kanäle auf Besuchsebene</li><li>Besuchsdefinition (visitnum-Feld)</li><li>Attributionslogik (in Post-Spalten)</li></ul> |   | <ul><li>Segmentlogik</li><li>Berechnete Metriken</li><li>Cross-Device Analytics</li></ul> | <ul><li>ID-Zuordnungen für bestimmte Spalten, die mit Marketing-Kanälen in Daten-Feeds in Verbindung stehen, sind nicht in den Daten-Feeds enthalten. (Siehe [Daten-Feed-Dokumentation](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference).)</li></ul> |
| Adobe Analytics-[Livestream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) | <ul><li> Verarbeitungsregeln</li><li>VISTA-Regeln</li><ul> |   | <ul><li>Regeln für Marketing-Kanäle auf Trefferebene</li><li>Regeln für Marketing-Kanäle auf Besuchsebene</li><li>Besuchslogik</li><li>Attributionslogik</li><li>Segmentlogik</li><li>Berechnete Metriken</li><li>Cross-Device Analytics</li></ul> |  |
| Adobe Analytics [Erweiterte Attributionsfunktionen](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/overview) | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>Besuchsdefinition (siehe Hinweis)</li><li>Cross-Device Analytics (siehe Hinweis)</li></ul> | <ul><li>Regeln für Marketing-Kanäle auf Trefferebene (siehe Hinweis)</li><li>Regeln für Marketing-Kanäle auf Besuchsebene (siehe Hinweis) Attributionslogik</li><li>Segmentlogik</li><li>Berechnete Metriken</li></ul> |  | <ul><li>Geräteübergreifende Analysen erfordern die Verwendung von Virtual Report Suites mit Berichtszeitverarbeitung.</li><li>Erweiterte Attributionsfunktionen in Core Analytics verwenden Marketing-Kanäle, die vollständig zur Berichtszeit abgeleitet wurden (d. h. abgeleitete Mittelwerte).</li><li>Erweiterte Attributionsfunktionen verwenden eine Besuchsdefinition für Verarbeitungszeiten, es sei denn, sie wird in einer Virtual Report Suite mit Berichtszeitverarbeitung verwendet.</li></ul> |
| Virtual Report Suites von Adobe Analytics mit [Berichtszeitverarbeitung](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-report-time-processing) | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>[Cross-Device Analytics](https://experienceleague.adobe.com/en/docs/analytics/components/cda/overview)</li></ul> | <ul><li>Besuchsdefinition</li><li>Attributionslogik</li><li>Segmentlogik</li><li>Berechnete Metriken</li><li>Andere Einstellungen der Berichtszeitverarbeitung für Virtual Report Suites</li></ul> | <ul><li>Regeln für Marketing-Kanäle auf Trefferebene</li><li>Regeln für Marketing-Kanäle auf Besuchsebene</li></ul> | <ul><li>Siehe die [Dokumentation](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-report-time-processing) zur Berichtszeitverarbeitung für Virtual Report Suites. </li></ul> |
| [Analytics-Quell-Connector](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics)-basierter Datensatz im Adobe Experience Platform Data Lake | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>Regeln für Marketing-Kanäle auf Trefferebene</li><li>Feldbasierte Zuordnung (siehe Hinweis)</li></ul> |   | <ul><li>[Regeln für Marketing-Kanäle auf Besuchsebene](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels)</li><li>Besuchslogik</li><li>Attributionslogik</li><li>Segmentlogik</li></ul> | <ul><li>Eigene Segmentlogik und berechnete Metriken anwenden</li><li>Bei der feldbasierten Zuordnung wird zusätzlich zu dem vom Analytics-Quell-Connector erstellten Datensatz ein separater zugeordneter Datensatz erstellt.</li></ul> |
| Reporting in [Customer Journey Analytics](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-landing) | <ul><li>Implementiert als Teil der Adobe Experience Platform-Datenerfassung</li></ul> | <ul><li>Sitzungsdefinition</li><li>[Datenansichtseinstellungen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/data-views)<li>Attributionslogik</li><li>Berechnete Metriken</li><li>Segmentlogik</li></ul> | <ul><li>Regeln für Marketing-Kanäle auf Besuchsebene</li></ul> | <ul><li>Verwenden Sie zusammengefügte Datensätze, um die Cross-Channel-Analyse zu nutzen.</li></ul> |

{style="table-layout:auto"}
