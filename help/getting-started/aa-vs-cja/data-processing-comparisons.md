---
title: Vergleich der Datenverarbeitung zwischen Reporting-Funktionen von Adobe Analytics und Customer Journey Analytics
description: Verstehen der Unterschiede bei der Datenverarbeitung für die verschiedenen Reporting-Funktionen
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
feature: Basics
role: User
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 96%

---

# Vergleich der Datenverarbeitung zwischen Adobe Analytics und Customer Journey Analytics

Häufig ist es erforderlich, Daten zu verarbeiten, damit sie für Berichte nützlich werden. Sie können diese Daten in verschiedenen Phasen der Journey verarbeiten, von der Datenerfassung bis zur Erstellung des Berichts oder der Visualisierung.

In Adobe Analytics erfolgt der Großteil dieser Datenverarbeitung unmittelbar nach der Datenerfassung. Funktionen wie VISTA-Regeln, Verarbeitungsregeln sowie Verarbeitungsregeln für Marketing-Kanäle stehen zur Verfügung, um diese **Verarbeitung zum Zeitpunkt der Erfassung** zu unterstützen.
Die Daten werden dann gespeichert, und zum Zeitpunkt der Berichtserstellung kann eine zusätzliche Verarbeitung durchgeführt werden. Beispielsweise können Sie Dimensionen aufschlüsseln, eine Segmentierung anwenden oder ein anderes Attributionsmodell auswählen. Diese **Verarbeitung zum Zeitpunkt der Berichtserstellung** erfolgt in Echtzeit.

In Adobe Analytics ist der Verarbeitungsumfang zum Zeitpunkt der Berichtserstellung normalerweise kleiner als zum Zeitpunkt der Erfassung.

![Verarbeitung zum Zeitpunkt der Erfassung mit Adobe Analytics](../assets/aa-processing.png)

Im Gegensatz dazu ist Customer Journey Analytics so konzipiert, dass eine minimale Vorabverarbeitung zum Zeitpunkt der Erfassung erforderlich ist, bevor Daten organisiert und gespeichert werden. Die zugrunde liegende Architektur von Customer Journey Analytics sieht vor, dass mit den gespeicherten Daten zur Berichtszeit gearbeitet wird. Diese leistungsstarke Funktion für die Verarbeitung zum Zeitpunkt der Berichtserstellung wird nicht nur in Workspace geboten, sondern vor allem auch durch die Definition von [Komponenten](/help/data-views/component-settings/overview.md) und [abgeleiteten Feldern](/help/data-views/derived-fields/derived-fields.md) in Ihren Datenansichten ermöglicht.

![Verarbeitung zum Zeitpunkt der Berichtserstellung mit Customer Journey Analytics](../assets/cja-processing.png)

Das Verständnis der Unterschiede bei der Datenverarbeitung für die verschiedenen Berichtsfunktionen kann hilfreich sein, um zu verstehen, welche Metriken wo verfügbar sind und warum sie sich unterscheiden können.

Da beispielsweise „Besuche“ als Metrik in Adobe Analytics zum Zeitpunkt der Datenverarbeitung definiert wird und „Sitzungen“ als Metrik in Customer Journey Analytics zum Zeitpunkt der Berichtserstellung berechnet wird, können die beiden Metriken je nach den Regeln, die für die Sitzungsdefinition in der Customer Journey Analytics-Datenansicht verwendet werden, unterschiedlich sein.

Außerdem sind weder Besuche noch Sitzungen als Metrik in Datensätzen verfügbar, die vom Analytics-Quell-Connector erstellt wurden. Daher müssten Sie die Sitzung in Ihrer Abfragelogik definieren, um Vergleiche durchzuführen.

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
| Berechnete Metriken | Auswertung benutzerdefinierter Metriken, die von Kunden erstellt wurden und auf komplexen Formeln, einschließlich Segmenten, basieren können. | Beispiel: Anzahl der Personen, die rote Schuhe gekauft haben. |
| Attributionslogik | Logik zur Berechnung der Attribution. | Beispiel: eVar-Persistenz. |
| Komponenteneinstellungen | Anwenden von Anpassungen auf Metriken oder Dimensionen, z. B. Attribution, Verhalten und Format. | Beispiel: Wert-Bucketing zum Kombinieren numerischer Werte basierend auf einem Bereich |
| Abgeleitete Felder | Logik gilt für Schema- oder Standardfelder bei der Definition von Komponenten in einer Datenansicht. | Beispiel: Erstellen einer neuen Marketing-Kanal-Dimension |

{style="table-layout:auto"}

Im Laufe der Zeit wurde die Flexibilität von Adobe Analytics und jetzt Customer Journey Analytics verbessert, indem die Ausführung der Logik für Daten auf Besuchs- und Personenebene zur Berichtslaufzeit ermöglicht wurde.

## Typen von Datenverarbeitung {#types}

Die für Adobe Analytics und Customer Journey Analytics durchgeführten Datenverarbeitungsschritte und der Zeitpunkt dieser Schritte sind je nach Analytics-Funktion unterschiedlich. Die nachstehende Tabelle bietet eine Zusammenfassung der Typen von Datenverarbeitung für jede Analytics-Funktion und gibt an, wann die Datenverarbeitung angewendet wird.

| Funktion | Zur Verarbeitungszeit angewendet | Zur Berichtszeit angewendet | Nicht verfügbar | Hinweise |
| --- | --- | --- | --- | --- |
| [Adobe Analytics](https://experienceleague.adobe.com/docs/analytics.html?lang=de)-Berichtserstellung<br/>(ohne Attribution IQ oder Virtual Report Suites mit Verarbeitung zum Zeitpunkt der Berichtserstellung) | <ul><li>[Verarbeitungsregeln](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=de)</li><li>[VISTA-Regeln](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=de)</li><li>Trefferebene [Regeln von Marketing-Kanälen](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules.html?lang=de)</li><li>Regeln von Marketing-Kanälen auf Besuchsebene (siehe Hinweis)</li><li>Besuchsdefinition</li><li>Attributionslogik</li></ul> | <ul><li>Segmentlogik</li><li>Berechnete Metriken</li></ul> | <ul><li>Cross-Device Analytics (siehe Hinweis)</li></ul> | <ul><li>CDA erfordert die Verwendung von Virtual Report Suites mit Berichtszeitverarbeitung.</li><li>Die „Regeln für Marketing-Kanäle auf Besuchsebene“ umfassen Folgendes: **Ist erste Seite des Besuchs**, **Last Touch-Kanal überschreiben** und **Marketing-Kanalgültigkeit**. (Siehe die [Dokumentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=de).)</li></ul> |
| Adobe Analytics [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=de) | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>Regeln für Marketing-Kanäle auf Trefferebene</li><li>Regeln für Marketing-Kanäle auf Besuchsebene</li><li>Besuchsdefinition</li><li>Attributionslogik</li></ul> | <ul><li>Segmentlogik</li></ul> | <ul><li>Berechnete Metriken</li><li>Cross-Device Analytics</li></ul> |     |
| Adobe Analytics-[Daten-Feeds](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=de) | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>Regeln für Marketing-Kanäle auf Trefferebene</li><li>Regeln für Marketing-Kanäle auf Besuchsebene</li><li>Besuchsdefinition (visitnum-Feld)</li><li>Attributionslogik (in Post-Spalten)</li></ul> |   | <ul><li>Segmentlogik</li><li>Berechnete Metriken</li><li>Cross-Device Analytics</li></ul> | <ul><li>ID-Zuordnungen für bestimmte Spalten, die mit Marketing-Kanälen in Daten-Feeds in Verbindung stehen, sind nicht in den Daten-Feeds enthalten. (Siehe [Daten-Feed-Dokumentation](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=de).)</li></ul> |
| Adobe Analytics-[Livestream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) | <ul><li> Verarbeitungsregeln</li><li>VISTA-Regeln</li><ul> |   | <ul><li>Regeln für Marketing-Kanäle auf Trefferebene</li><li>Regeln für Marketing-Kanäle auf Besuchsebene</li><li>Besuchslogik</li><li>Attributionslogik</li><li>Segmentlogik</li><li>Berechnete Metriken</li><li>Cross-Device Analytics</li></ul> |  |
| Adobe Analytics [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=de) | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>Besuchsdefinition (siehe Hinweis)</li><li>Cross-Device Analytics (siehe Hinweis)</li></ul> | <ul><li>Regeln für Marketing-Kanäle auf Trefferebene (siehe Hinweis)</li><li>Regeln für Marketing-Kanäle auf Besuchsebene (siehe Hinweis) Attributionslogik</li><li>Segmentlogik</li><li>Berechnete Metriken</li></ul> |  | <ul><li>CDA erfordert die Verwendung von Virtual Report Suites mit Berichtszeitverarbeitung.</li><li>Attribution IQ in Core Analytics verwendet Marketing-Kanäle, die vollständig zur Berichtszeit abgeleitet wurden (d. h. abgeleitete Mittelwerte).</li><li>Attribution IQ verwendet eine Besuchsdefinition für Verarbeitungszeiten, es sei denn, diese wird in einer Virtual Report Suite mit Berichtszeitverarbeitung verwendet.</li></ul> |
| Virtual Report Suites von Adobe Analytics mit [Berichtszeitverarbeitung](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=de) | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>[Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=de)</li></ul> | <ul><li>Besuchsdefinition</li><li>Attributionslogik</li><li>Segmentlogik</li><li>Berechnete Metriken</li><li>Andere Einstellungen der Berichtszeitverarbeitung für Virtual Report Suites</li></ul> | <ul><li>Regeln für Marketing-Kanäle auf Trefferebene</li><li>Regeln für Marketing-Kanäle auf Besuchsebene</li></ul> | <ul><li>Siehe die [Dokumentation](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=de) zur Berichtszeitverarbeitung für Virtual Report Suites. </li></ul> |
| [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de)-basierter Datensatz im Adobe Experience Platform Data Lake | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>Regeln für Marketing-Kanäle auf Trefferebene</li><li>Feldbasierte Zuordnung (siehe Hinweis)</li></ul> |   | <ul><li>[Regeln für Marketing-Kanäle auf Besuchsebene](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=de)</li><li>Besuchslogik</li><li>Attributionslogik</li><li>Segmentlogik</li></ul> | <ul><li>Muss Ihre eigene Segmentlogik und berechnete Metriken anwenden</li><li>Bei der feldbasierten Zuordnung wird zusätzlich zu dem vom Analytics-Quell-Connector erstellten Datensatz ein separater zugeordneter Datensatz erstellt.</li></ul> |
| Reporting in [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=de) | <ul><li>Implementiert als Teil der Adobe Experience Platform-Datenerfassung</li></ul> | <ul><li>Sitzungsdefinition</li><li>[Datenansichtseinstellungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=de)<li>Attributionslogik</li><li>Berechnete Metriken</li><li>Segmentlogik</li></ul> | <ul><li>Regeln für Marketing-Kanäle auf Besuchsebene</li></ul> | <ul><li>Muss zugeordnete Datensätze verwenden, um die Cross-Channel-Analyse nutzen zu können.</li></ul> |

{style="table-layout:auto"}
