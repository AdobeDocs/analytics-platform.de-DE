---
description: Erfahren Sie, wie Sie die Funktionen von Daten-Feeds in Customer Journey Analytics und Adobe Analytics vergleichen
keywords: Clickstream;Daten-Feed;Daten-Feed;Data Feed
title: Vergleich der Funktionen von Daten-Feeds in Customer Journey Analytics und Adobe Analytics
feature: Components
hide: true
exl-id: 32b71016-7c53-409f-9ce4-521a40e2eb96
autotag-review: '2026-05-19T08:44:26.806Z'
TQID: 'https://experienceleague.adobe.com/R7c5-VutwSkyghNvwC2gZv2KUEJoa263AN0Tkdg3w4o'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: ede5644096e8b1169819fb94399d5360066ca529
workflow-type: tm+mt
source-wordcount: '1746'
ht-degree: 1%
---
# Vergleichen von Daten-Feeds in Customer Journey Analytics und Adobe Analytics

{{release-limited-testing}}

Daten-Feeds in Customer Journey Analytics und Adobe Analytics ermöglichen den Export von Rohdaten in Drittanbieterplattformen.

Wenn Sie zuvor Daten-Feeds in Adobe Analytics verwendet haben, verwenden Sie die folgenden Informationen, um Unterschiede in den verfügbaren Funktionen und Konzepten zu verstehen.

Einen Vergleich der Daten-Feeds mit anderen Customer Journey Analytics-Exportmethoden, z. B. dem vollständigen Tabellenexport, finden Sie unter [Analytics-Produktvergleich](/help/getting-started/analytics-product-comparison.md).

## Nur in Customer Journey Analytics verfügbare Funktionen in Daten-Feeds

Die folgenden Funktionen sind in Customer Journey Analytics-Daten-Feeds verfügbar, aber nicht in Adobe Analytics-Daten-Feeds:

* **Abgeleitete Felder**: Benutzerdefinierte Komponenten, die aus regelbasierten Transformationen erstellt wurden, die in Ihr Daten-Feed-Schema aufgenommen werden können. <!-- add benefit -->

* **Komponenteneinstellungen**: Einstellungen für die Datenansichtskomponente wie Persistenz, Metrik-Deduplizierung und Wert-Bucketing können den Wert einer Komponente direkt in Ihrer Daten-Feed-Ausgabe umwandeln, ohne dass SQL erforderlich ist.

* **Zusammenfügen**: Geräteübergreifende Identitätsauflösung, die Ereignisse geräteübergreifend mit einer einzelnen Person verknüpft.

* **Strukturiertes Datenmodell**: Feeds werden mithilfe strukturierter Daten und nicht anhand flacher Zeichenfolgen wie „post_product_list“ erstellt und bereitgestellt. spiegelt die vorhandene Struktur aus dem XDM-Schema und der Datenansicht wider.

* **Parquet-Ausgabe**: Dateien werden im Parquet-Format bereitgestellt, das nativ komplexe verschachtelte und strukturierte Daten unterstützt. Das bedeutet, dass der Zugriff auf Daten in einer Datenbank mithilfe von branchenüblichen Verfahren einfacher ist.

* **Segmentierung**: Segmente, die auf die Datenansicht angewendet werden, werden automatisch übernommen, und zusätzliche Segmente können direkt auf den Feed angewendet werden.

* **Partitionspfade im Hive-Stil**: Ausgabedateien verwenden hive-artige Pfade für effiziente Abfragen in Data-Lake-Umgebungen.

* **Komponentenaktualisierungen gelten rückwirkend**: Änderungen an Komponenten in der Datenansicht werden historisch in Aufstockungen widergespiegelt.

* **Suchen**: Klassifizierungen sind nicht in Adobe Analytics-Daten-Feeds enthalten. In Customer Journey Analytics sind alle Suchen direkt in die Daten eingebettet.

* **Benutzeroberfläche, die Analysis Workspace-Benutzern vertraut ist**: Komponenten stammen direkt aus der Datenansicht und sind auch in Analysis Workspace verfügbar. Sie können Dimensionen und Metriken über dieselbe Komponentenleiste wie Analysis Workspace auswählen, anstatt über eine statische Liste von Variablennamen.

* **Weitere Persistenzmodelle verfügbar**: Es gibt fünf verschiedene Persistenzmodelle, die in Customer Journey Analytics-Daten-Feeds verwendet werden können.

<!-- * Web MCP when it's added -->

Die nachstehende [Funktionsvergleich](#functionality-comparison) Tabelle behandelt alle diese Funktionen im Detail, zusammen mit den Unterschieden bei den Funktionen, die in beiden Produkten vorhanden sind.


## Funktionsvergleich

In der folgenden Tabelle werden die wichtigsten Konzepte und Konfigurationsoptionen von Customer Journey Analytics-Daten-Feeds und Adobe Analytics-Daten-Feeds verglichen.

| **Konzepte und Konfigurationsoptionen** | **Customer Journey Analytics** | **Adobe Analytics** |
|---------|----------|---------|
| **Dateneingabe**<br/> Der Datentyp, der erfasst und in Daten-Feeds eingeschlossen werden kann. | Unterstützt Cross-Channel-Dateneingabe, einschließlich Web-Daten, Callcenter-Daten, Point-of-Sale-Daten und mehr. | Unterstützt in erster Linie Web- und mobile Dateneingabe. Andere Datentypen (z. B. Callcenter- oder Point-of-Sale-Daten) können über Datenquellen aufgenommen werden, jedoch mit sehr begrenzten Verarbeitungsfunktionen. |
| **Datenverarbeitung**<br/> Daten werden in verschiedenen Phasen verarbeitet, je nachdem, welches Produkt Sie verwenden. | Die Daten werden zur **verarbeitet** und daher können viele Berichtsfunktionen verwendet werden, um historische Daten zu ändern, wie z. B. Zuordnung, abgeleitete Felder und Segmentierung. | Daten werden zur **Erfassungszeit“ verarbeitet** sodass Berichtsfunktionen wie Verarbeitungsregeln und VISTA-Regeln keine Auswirkungen auf historische Daten haben. |
| **Zuordnung**<br/> Geräteübergreifende und kanalübergreifende Identitätsauflösung, die Ereignisse mit einer einzelnen Person verknüpft. | Unterstützt. Zusammengefügte Identitäten können in Daten-Feed-Exporte aufgenommen werden, wenn das Zusammenfügen für die Verbindung konfiguriert ist. | Nicht unterstützt. Die Besucheridentität wird zur Erfassungszeit aus Besucher-ID-Cookies bestimmt; es ist keine geräteübergreifende Auflösung nach der Erfassung verfügbar. |
| **Versandfrequenz**<br/> Bestimmt, wie oft der Daten-Feed gesendet wird und in welchem Zeitfenster der Feed verfügbar ist. | **Täglich** (Mitternacht bis Mitternacht in der Zeitzone der Datenansicht) oder **Stündlich**. | **Täglich** (Mitternacht bis Mitternacht in der Zeitzone der Report Suite) oder **Stündlich**. <p>Feeds von 15 Minuten sind möglich, aber standardmäßig nicht verfügbar.</p> |
| **Verspätet eintreffende Treffer**<br/> Treffer, deren Zeitstempel zu einem früheren Versand-Häufigkeitsfenster gehören, aber nach Ablauf dieses Fensters eintreffen. <p>Beispielsweise können verspätete Treffer von einer Mobile App stammen, die Ereignisse im Offline-Modus puffert und bei einer erneuten Verbindung sendet.</p> | Mit **Einstellung „Verarbeitungsverzögerung** wird festgelegt, wie lange das System nach dem Schließen des Häufigkeitsfensters wartet, bevor der Export ausgelöst wird. Dadurch wird mehr Zeit für das Eintreffen verzögerter Daten bereitgestellt. | Verspätete Treffer können über **** Konfigurationsoption **Verspätete Treffer** eingeschlossen oder ausgeschlossen werden. <p>Die Einstellung **Lookback** steuert, wie weit das System zurückreicht, um verzögerte Daten einzuschließen.</p> |
| **Nicht in der ReihenfolgeTreffer**<br/> Treffer, deren Zeitstempel nicht mit der Reihenfolge übereinstimmen, in der sie empfangen wurden. | Da Customer Journey Analytics sowohl Streaming- als auch Batch-Daten akzeptiert, gibt es keine Garantie dafür, dass Ereignisse für eine bestimmte Person in der Zeitstempelreihenfolge eintreffen. Obwohl Customer Journey Analytics nach Zeitstempel pro Person neu anordnet, kann es nur die eingetroffenen Daten exportieren. Dies bedeutet, dass verspätete Treffer nach Treffern mit einem späteren Zeitstempel exportiert werden können.<p>Mit **Einstellung „Verarbeitungsverzögerung** können Sie nicht in der Reihenfolge vorkommende Ereignisse in der Daten-Feed-Ausgabe reduzieren, indem Sie mehr Zeit dafür haben, dass Batch-Daten vor dem Export eingehen. Die Ereignisreihenfolge im Versand ist nicht garantiert.</p><p>**Wichtig**: Der Endverbraucher Ihrer Daten-Feed-Daten muss in der Lage sein, pro Person Zeitstempel zu verarbeiten, die nicht in der Reihenfolge sind, da die Trefferreihenfolge im Daten-Feed-Versand nicht garantiert ist.</p> | Adobe Analytics verlangt, dass die Daten zur Erfassungszeit in der richtigen Reihenfolge pro Besucher eintreffen, aber die Trefferreihenfolge im Daten-Feed-Versand ist nicht garantiert. |
| **Aufstockungsfenster**<br/> Exportiert historische Daten zwischen zwei früheren Datumsangaben. | Beschränkung auf das rollierende Datenfenster der Verbindung. | Auf das Datenaufbewahrungslimit der Report Suite beschränkt: **25 Monate** Standardmäßig. |
| **Schema**<br/> Das Daten-Feed-Schema bestimmt, welche Spalten in einen Daten-Feed aufgenommen werden können. | Das Daten-Feed-Schema basiert auf der Konfiguration der Datenansicht.  Die Komponenten, die für die Aufnahme in das Daten-Feed-Schema verfügbar sind, sind eine Teilmenge der in der Datenansichtskonfiguration verfügbaren Komponenten. | Eine vordefinierte statische Liste von über 1.100 Variablen. Viele Spalten werden als **vor- und nachverarbeitete Paare** exportiert (z. B. `eVar1` / `post_eVar1`), was einen Großteil der Spaltenanzahl ausmacht. |
| **Daten-Feed-Builder**<br/> Die Schnittstelle zum Konfigurieren der in einem Daten-Feed enthaltenen Spalten. | Verwendet eine Komponentenleiste mit denselben benannten Dimensionen und Metriken, die in der Datenansicht verfügbar sind, und stimmt damit mit dem Analysis Workspace-Erlebnis überein. | Verwendet eine flache Liste von rohen Variablennamen (z. B. `eVar1`, `prop5`), die aus einem vordefinierten Satz von über 1.100 Spalten ausgewählt wurden. Komponenten werden jenseits ihrer Variablenkennung weder benannt noch beschrieben. |
| **Abgeleitete Felder**<br/> benutzerdefinierte Komponenten, die mithilfe regelbasierter Transformationen definiert wurden, die zum Zeitpunkt der Berichterstellung angewendet wurden. | Unterstützt. Abgeleitete Feldkomponenten können zusammen mit Standarddimensionen und Metriken in das Daten-Feed-Schema aufgenommen werden. | Nicht unterstützt. |
| **Komponenteneinstellungen**<br/> Komponenteneinstellungen für die Datenansicht wie Persistenz, Metrik-Deduplizierung und Wert-Bucketing, die den Wert einer Komponente zur Berichtszeit transformieren. | Wird für die meisten Einstellungen unterstützt. Diese Einstellungen gelten für die Daten-Feed-Ausgabe auf die gleiche Weise wie für Analysis Workspace. | Nicht unterstützt. |
| **Komponentenaktualisierungen**<br/> Ob Änderungen an der Komponentenkonfiguration in vergangene und künftige Daten-Feed-Ausgaben übernommen werden. | Änderungen an Komponenten in der Datenansicht (z. B. das Umbenennen oder Entfernen einer Dimension) werden an zukünftige Daten-Feeds weitergegeben und auch in Aufstockungen übernommen. | Änderungen an Komponenten in der Report Suite gelten nur für Daten, die in der Zukunft erfasst werden. |
| **Lookups**<br/> Lookup-Datensätze in Customer Journey Analytics entsprechen den Klassifizierungen in Adobe Analytics. | Alle Suchen werden direkt in die Daten eingebettet. | Klassifizierungen sind nicht in den Daten-Feeds von Adobe Analytics enthalten. |
| **Sitzungsdefinition**<br/> Wie eine Besuchs- oder Sitzungsgrenze definiert wird, die sich darauf auswirkt, wie Ereignisse gruppiert und zugeordnet werden. | Wird in der Datenansicht definiert. | Wird zur Sammlungszeit definiert. |
| **Segmentierung**<br/> Die Möglichkeit, die Daten-Feed-Ausgabe mithilfe von Segmenten zu filtern. | Segmente, die auf die Datenansicht angewendet werden, werden automatisch vom Daten-Feed übernommen. Zusätzliche Segmente können auch direkt auf einen einzelnen Daten-Feed angewendet werden. Weitere Informationen finden Sie unter [Segmentierung in Daten-Feeds](/help/components/exports/cja-data-feeds/df-segmentation.md). | Nicht unterstützt. Daten-Feeds exportieren alle erfassten Daten ohne Segmentfilterung. |
| **Berechnete Metriken**<br/> Benutzerdefinierte Metriken, die Sie aus vorhandenen Metriken erstellen können. | Nicht unterstützt | Nicht unterstützt |
| **Persistenzmodell:**<br/> oder ob Dimensionswerte von einem Ereignis zum nächsten bestehen bleiben. | Flexibel. Persistenzeinstellungen aus der Datenansicht (Zuordnung und Gültigkeit) werden zum Zeitpunkt der Berichterstellung angewendet, wenn der Feed generiert wird. Unterstützt alle in einer Datenansicht verfügbaren Zuordnungseinstellungen: **Original**, **Zuletzt**, **Alle**, **Erster bekannter** und **Letzter bekannter**. | Es werden nur **Attributionsmodelle „Zuletzt verwendet (Letztkontakt** und **Ausgangswert (Erstkontakt)** dargestellt. Die lineare Zuordnung wird wie beim letzten Kontakt gehandhabt. |
| **Behandlung von Unterereignissen**<br/> So werden Unterereignisse in der Daten-Feed-Ausgabe dargestellt. | In einer einzigen Zeile dargestellt, aber die relationale Hierarchie bleibt erhalten. Weitere Informationen finden Sie [Unterereignisse in Daten-Feeds](/help/components/exports/cja-data-feeds/df-sub-event.md). | In einer einzelnen Zeile als reduzierte, durch Trennzeichen getrennte Zeichenfolge dargestellt. Das Parsen der Zeichenfolge erfordert eine benutzerdefinierte Logik. |
| **Ausgabedateiformat**<br/> Das Format, das für Daten-Feed-Ausgabedateien verwendet wird, die an Ihr Cloud-Ziel gesendet werden. | Parquet<p>unterstützt nativ komplexe verschachtelte und strukturierte Daten. Felder wie `post_product_list` werden als strukturierte Arrays/verschachtelte Objekte dargestellt. </p><p>Erfordert ein Parquet-orientiertes Tool zum Lesen, z. B. BigQuery, Snowflake oder Apache Spark.</p><p>Die Schemastruktur ist in die Ausgabedatei eingebettet.</p> | TSV<p>Flache, für Menschen lesbare Zeilen. unterstützt nicht nativ strukturierte Daten. Komplexe Felder wie Produktlisten müssen als proprietäre, durch Trennzeichen getrennte Zeichenfolgen codiert werden, was eine benutzerdefinierte Parsing-Logik erfordert.</p> |
| **Pfade für Ausgabedateien**<br/> Die Ordnerstruktur, die für bereitgestellte Ausgabedateien verwendet wird. | Verwendet **hive-artige Partitionspfade** (z. B. `year=2024/month=01/day=15/`), was ein effizientes Partitionsbereinigen bei der Abfrage von Daten in Data-Lake-Umgebungen wie Databricks oder Apache Spark ermöglicht. | Verwendet eine flache Verzeichnisstruktur. Hive-artige Pfade werden nicht unterstützt. |
| **Versandziele**<br/> Die Cloud-Speicherorte, an die Daten-Feed-Ausgabedateien gesendet werden können. | Amazon S3, Azure RBAC, Azure SAS, Google Cloud Platform. | Amazon S3, Azure RBAC, Azure SAS, Google Cloud Platform. <p>unterstützt auch **SFTP**.</p> |
| **Ähnlichkeit mit Analysis Workspace**<br/> Ob der Daten-Feed-Builder dieselben Komponenten und dieselbe Terminologie wie Analysis Workspace verwendet. | Die linke Leiste in Daten-Feeds ähnelt der linken Leiste von Workspace, und Komponenten, die in Daten-Feeds verfügbar sind, sind auch in Workspace verfügbar. | Eine statische Liste von Variablennamen, die nicht unbedingt mit dem übereinstimmen, was Sie in Analysis Workspace sehen. |
| **Verfügbarkeit des Persistenzmodells**<br/> Die Persistenzmodelle, die für Dimensionen in einem Daten-Feed verfügbar sind. | Für Daten-Feeds sind fünf Persistenzmodelle verfügbar: Original, Zuletzt verwendet, Alle, Erster bekannter, Letzter bekannter | Für Daten-Feeds sind zwei Persistenzmodelle verfügbar: Erstkontakt und Letztkontakt |

{style="table-layout:auto"}

