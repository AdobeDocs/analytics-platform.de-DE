---
title: Anwendungsfälle für den Datenexport
description: Verschiedene Anwendungsfälle für Datenexporte für Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 8b9c164e-01da-4b43-8e2c-99904223cae5
source-git-commit: efb961c571ddcde1017e6bf2080fc2a97c28bb13
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 1%

---

# Anwendungsfälle für den Datenexport {#data-export-use-cases}

<!-- This contextual help is for the upgrade checklist -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds-step"
>title="Verwenden von Exportfunktionen ähnlich wie Daten-Feeds"
>abstract="Ein exakter Ersatz für Daten-Feeds ist in Customer Journey Analytics noch nicht verfügbar. Ähnliche Funktionen können jedoch mit Funktionen wie dem vollständigen Tabellenexport, dem Platform-Datensatzexport, der BI-Tool-Integration und der Reporting-API erreicht werden."

<!-- markdownlint-enable MD034 -->

In diesem Abschnitt finden Sie Anwendungsfälle für Datenexporte und erfahren, wie Sie diese Anwendungsfälle mit einer oder mehreren Funktionen von Customer Journey Analytics oder Experience Platform implementieren. Jede Funktion wird in einem separaten Artikel näher beschrieben.

## Einführung

Einer der einzigartigen Unterschiede zwischen Adobe Analytics und Customer Journey Analytics hängt mit der Verarbeitung von Daten für die Attribution und Sitzungserstellung zusammen. Weitere [ finden Sie unter „Vergleich der Datenverarbeitung in Adobe Analytics ](/help/getting-started/aa-vs-cja/data-processing-comparisons.md) Customer Journey Analytics&quot;.

### Adobe Analytics: Attribution und Sitzungserstellung der Erfassungszeit.

In Adobe Analytics werden alle Ereignisse live und in der richtigen Reihenfolge nach Geräte-ID verarbeitet, sodass Adobe Clickstream-Daten zur Erfassungszeit mit persistenten oder zugewiesenen Werten generieren, speichern und exportieren kann, darunter:

* Persistenz in Dimension (z. B. Kampagnen-Trackingcodes, die nach 90 Tagen ablaufen).
* Besuchsnummer und Sitzungserstellung.
* Dimension-Werte, berechnet durch Verarbeitung und VISTA-Regeln.

Dies wirkt sich auf den Export von Daten aus Adobe Analytics aus:

* Die Datenverarbeitung ist nach der ersten Erfassung statisch.
* Daten-Feeds enthalten „Post“-Spalten, die die Verarbeitung zur Sammlungszeit widerspiegeln.


### Customer Journey Analytics: Attribution und Sitzungserstellung zur Abfragezeit

In Customer Journey Analytics werden Ereignisse nicht in der richtigen Reihenfolge erfasst, sondern eine Personen-ID anstelle einer Geräte-ID verwendet, sodass Customer Journey Analytics die Attribution und die Sitzungserstellung zum Zeitpunkt der Berichterstellung aktualisieren kann. Diese Art der Datenerfassung bietet Flexibilität, z. B.:

* Beim Stitching können _Daten_ oder wöchentlich wiedergegeben werden, wobei anonyme Ereignisse bekannten Ereignissen zugeordnet werden. Weitere Informationen finden [ unter ](../../stitching/overview.md).
* Sitzungserstellung und beibehaltene Werte ändern sich jedes Mal
   * neue Daten erfasst werden oder
   * Das Zusammenfügen fügt Ereignisse zum Verlauf einer Person hinzu.

Die Berichtszeitverarbeitung wirkt sich auf den Export von Daten aus Customer Journey Analytics aus. Exporte, die persistente Werte enthalten, stimmen nicht mit Customer Journey Analytics-Berichten überein, und die Werte werden mit der Zeit verschwinden.

Aus Gründen der Metrikkonsistenz wird die Verwendung der neuen Funktionen in Customer Journey Analytics bevorzugt. Im Allgemeinen überschreiten die Datenexportfunktionen von Experience Platform und Customer Journey Analytics die Daten-Feed-Funktionen von Adobe Analytics. Experience Platform und Customer Journey Analytics bieten:

* Neue Datenquellen und Verarbeitungen, die dem Datenexport unterliegen

   * Nicht-digitale Datenquellen einschließen,
   * benutzerdefinierte Attribution und Sitzungserstellung basierend auf Geschäftsregeln anwenden und
   * Halten Sie die Journey der Kunden beim Zusammenfügen auf dem neuesten Stand.

* Realisierung maßgeschneiderter Anwendungsfälle für den Datenexport

   * Exportieren Sie Daten dorthin, wo Sie sie benötigen, einschließlich Business Intelligence (BI)-Tools und Cloud-Ziele,
   * die Synchronisierung von Daten mit Analysis Workspace durch die Integration von BI-Tools,
   * Keine Notwendigkeit, die Verarbeitungslogik in Ihren eigenen Systemen zu replizieren,
   * Neue Unterstützung für berechnete Metriken, abgeleitete Felder und Segmentierung

* Berücksichtigung von Sicherheit und Data Governance per Design

   * alle Datenexporte nach Benutzer und Ziel überwachen,
   * Sie legt Grenzen für die Daten fest, die für den Export verfügbar sind.
   * Warnhinweise für Versandprobleme und Einschränkungen bei terminierten Versandfenstern festlegen.


## Anwendungsfälle und Funktionen

Im Allgemeinen unterstützt der Datenexport eine Reihe von Anwendungsfällen. Jeder Anwendungsfall unterscheidet sich hinsichtlich der erforderlichen Daten und der Art und Weise, wie auf diese Daten zugegriffen werden kann und wie sie exportiert werden. Experience Platform und Customer Journey Analytics bieten eine Reihe von Funktionen, die entweder unabhängig oder kombiniert die verschiedenen Anwendungsfälle lösen können. Die folgende Tabelle bietet einen Überblick über identifizierte Anwendungsfälle für Datenexporte und die Experience Platform- und Customer Journey Analytics-Funktionen zur Implementierung dieser Anwendungsfälle.

| Anwendungsfälle für den Datenexport | Funktionen von Experience Platform und Customer Journey Analytics |
|---|---|
| **Datensicherung:**<br/> Sie eine vollständige Kopie Ihrer digitalen Daten für Compliance- oder behördliche Zwecke auf. | **Experience Platform**: [**Exportieren von Datensätzen**](export-datasets.md)<br/> Exportieren Sie in Experience Platform erfasste Daten direkt in Cloud-Ziele nach einem Zeitplan oder Ad-hoc-Zeitplan. |
| **Datenvalidierung**<br/> Auswerten von Clickstream-Daten auf Genauigkeit bei der Datenerfassung. | **Experience Platform**: [**Abfrage-Service (Data Distiller) und Datensätze exportieren**](queryservice-export-datasets.md)<br/> Interaktive PostgreSQL-Schnittstelle zum Ausführen von Ad-hoc-SQL-Abfragen mithilfe Ihres bevorzugten SQL-Tools zum Überprüfen der Daten in Ihren Datensätzen.<br/><br/>**Customer Journey Analytics**: [**Exportieren einer vollständigen Tabelle**](export-full-table.md)<br/> Validieren verarbeiteter Daten aus CJA mit angewendeter Attribution und Sitzungserstellung. |
| **Data Lake, Data Warehouse oder BI-Tools**<br/> Bringen Sie digitale Daten in Ihre eigenen BI-Tools oder in den Data Lake zur Verwendung mit zusätzlichen Datensätzen. | **Customer Journey Analytics**: [**BI-Erweiterung**](bi-extension.md)<br/> Fügen Sie verarbeitete Customer Journey Analytics-Metriken zu Datenvisualisierungs-Tools wie Power BI hinzu und kombinieren Sie sie mit zusätzlichen Daten für benutzerdefinierte Berichte <br/><br/>**Experience Platform**: [**Abfrage-Service (Data Distiller) und Datensätze exportieren**](queryservice-export-datasets.md)<br> Generieren Sie benutzerdefinierte Clickstream-Daten mithilfe von SQL, die an Cloud-Ziele bereitgestellt werden. |
| **Bereitschaft für KI/ML**<br/> Verbesserung von Modellen und Aufgaben für künstliche Intelligenz/maschinelles Lernen mit Customer Journey Analytics-Daten. | **Customer Journey Analytics**: [**Vollständige Tabelle exportieren**](export-full-table.md)<br/> Customer Journey Analytics verarbeitete Dimensionen und Metriken einmal oder wiederholt an Cloud-Ziele exportieren, einschließlich berechneter Metriken und Segmentierung.<br/><br/>**Experience Platform**: [**Abfrage-Service (Data Distiller) und Exportieren von Datensätzen**](queryservice-export-datasets.md)<br/> Generieren von benutzerdefinierten Clickstream-Daten mithilfe von SQL zur Anreicherung von KI-/ML-Modellen. |
