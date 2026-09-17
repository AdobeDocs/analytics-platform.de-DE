---
title: Anwendungsfälle für den Datenexport
description: Verschiedene Anwendungsfälle für Datenexporte für Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 8b9c164e-01da-4b43-8e2c-99904223cae5
TQID: https://experienceleague.adobe.com/ad4wWxqEZZxsnSTpus7pxFMlwNo3nNUpHeS9VfxrEdw
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
    internal-label: Data governance
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '1079'
ht-degree: 1%
---
# Anwendungsfälle für den Datenexport {#data-export-use-cases}

<!-- This contextual help is for the upgrade checklist -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds-step"
>title="Verwenden von Exportfunktionen ähnlich den Daten-Feeds"
>abstract="Während in Customer Journey Analytics noch kein exakter Ersatz für Daten-Feeds verfügbar ist, sind ähnliche Funktionen über den vollständigen Tabellenexport, den Platform-Datensatzexport, die BI-Tool-Integration und die Reporting-API verfügbar."

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

Die Berichtszeitverarbeitung wirkt sich auf den Export von Daten aus Customer Journey Analytics aus. Exporte, die persistente Werte enthalten, stimmen nicht mit Customer Journey Analytics-Berichten überein, und die Werte weichen im Laufe der Zeit voneinander ab.

Aus Gründen der Metrikkonsistenz wird die Verwendung der neuen Funktionen in Customer Journey Analytics bevorzugt. Im Allgemeinen überschreiten die Datenexportfunktionen von Experience Platform und Customer Journey Analytics die Daten-Feed-Funktionen von Adobe Analytics. Experience Platform und Customer Journey Analytics bieten:

* Neue Datenquellen und Verarbeitungen, die dem Datenexport unterliegen

  * Nicht-digitale Datenquellen einschließen,
  * benutzerdefinierte Attribution und Sitzungserstellung basierend auf Geschäftsregeln anwenden und
  * Halten Sie die Journey der Kunden beim Zusammenfügen auf dem neuesten Stand.

* Implementierung maßgeschneiderter Anwendungsfälle für den Datenexport

  * Exportieren Sie Daten dorthin, wo Sie sie benötigen, einschließlich Business Intelligence (BI)-Tools und Cloud-Ziele,
  * die Synchronisierung von Daten mit Analysis Workspace durch die Integration von BI-Tools,
  * Keine Notwendigkeit, Verarbeitungslogik in Ihren eigenen Systemen zu duplizieren,
  * Neue Unterstützung für berechnete Metriken, abgeleitete Felder und Segmentierung

* Berücksichtigung von Sicherheit und Data Governance

  * alle Datenexporte nach Benutzer und Ziel überwachen,
  * Sie legt Grenzen für die Daten fest, die für den Export verfügbar sind.
  * Warnhinweise für Versandprobleme und Einschränkungen bei terminierten Versandfenstern festlegen.


## Anwendungsfälle und Funktionen

Im Allgemeinen unterstützt der Datenexport eine Reihe von Anwendungsfällen. Jeder Anwendungsfall unterscheidet sich hinsichtlich der erforderlichen Daten und der Art und Weise, wie auf diese Daten zugegriffen werden kann und wie sie exportiert werden. Experience Platform und Customer Journey Analytics bieten eine Reihe von Funktionen, die entweder unabhängig oder kombiniert die verschiedenen Anwendungsfälle lösen können. Die folgende Tabelle bietet einen Überblick über identifizierte Anwendungsfälle für Datenexporte und die Experience Platform- und Customer Journey Analytics-Funktionen zur Implementierung dieser Anwendungsfälle.

| Anwendungsfälle für den Datenexport | Funktionen von Experience Platform und Customer Journey Analytics |
|---|---|
| **Datensicherung:**<br/> Sie eine vollständige Kopie Ihrer digitalen Daten für Compliance- oder behördliche Zwecke auf. | **Experience Platform**: [**Exportieren von Datensätzen**](export-datasets.md)<br/> Exportieren Sie in Experience Platform erfasste Daten direkt in Cloud-Ziele nach einem Zeitplan oder Ad-hoc-Zeitplan. |
| **Datenvalidierung**<br/> Auswerten von Clickstream-Daten auf Genauigkeit bei der Datenerfassung. | **Experience Platform**: [**Abfrage-Service (Data Distiller) und Datensätze exportieren**](queryservice-export-datasets.md)<br/> Interaktive PostgreSQL-Schnittstelle zum Ausführen von Ad-hoc-SQL-Abfragen mithilfe Ihres bevorzugten SQL-Tools zum Überprüfen der Daten in Ihren Datensätzen.<br/><br/>**Customer Journey Analytics**: [**Vollständige Tabelle exportieren**](export-full-table.md)<br/> Verarbeitete Daten aus CJA mit angewendeter Attribution und Sitzungserstellung überprüfen. |
| **Data Lake, Data Warehouse oder BI-Tools**<br/> Bringen Sie digitale Daten in Ihre eigenen BI-Tools oder in den Data Lake zur Verwendung mit zusätzlichen Datensätzen. | **Customer Journey Analytics**: [**BI-Erweiterung**](bi-extension.md)<br/> Fügen Sie verarbeitete Customer Journey Analytics-Metriken zu Datenvisualisierungs-Tools wie Power BI hinzu und kombinieren Sie sie mit zusätzlichen Daten für benutzerdefinierte Berichte <br/><br/>**Experience Platform**: [**Abfrage-Service (Data Distiller) und Datensätze exportieren**](queryservice-export-datasets.md)<br> Generieren Sie benutzerdefinierte Clickstream-Daten mithilfe von SQL, die an Cloud-Ziele bereitgestellt werden. |
| **Bereitschaft für KI/ML**<br/> Verbesserung von Modellen und Aufgaben für künstliche Intelligenz/maschinelles Lernen mit Customer Journey Analytics-Daten. | **Customer Journey Analytics**: [**Vollständige Tabelle exportieren**](export-full-table.md)<br/> Customer Journey Analytics verarbeitete Dimensionen und Metriken einmal oder wiederholt an Cloud-Ziele exportieren, einschließlich berechneter Metriken und Segmentierung.<br/><br/>**Experience Platform**: [**Abfrage-Service (Data Distiller) und Exportieren von Datensätzen**](queryservice-export-datasets.md)<br/> Generieren von benutzerdefinierten Clickstream-Daten mithilfe von SQL zur Anreicherung von KI-/ML-Modellen. |
| **Ad-hoc- und wiederkehrende Berichte**<br/> Gewähren Sie einzelnen Benutzenden oder Unternehmens-Teams Self-Service-Zugriff auf verarbeitete Customer Journey Analytics-Daten, ohne eine Daten-Pipeline einzurichten. | **Customer Journey Analytics**: [**Workspace-Export**](workspace-export.md)<br/> Download oder E-Mail-Daten direkt aus einem Analysis Workspace-Projekt zur einmaligen Analyse oder Freigabe.<br/><br/>**Customer Journey Analytics**: [**Report Builder**](report-builder.md)<br/> Ziehen Sie Customer Journey Analytics-Daten in Excel-Arbeitsmappen, um wiederkehrendes, benutzerfreundliches Reporting zu ermöglichen. |
| **Benutzerdefinierte Anwendungsintegration**<br/> Power-Dashboards, interne Tools oder automatisierte Workflows mit Customer Journey Analytics-Daten. | **Customer Journey Analytics**: [**Reporting-API**](reporting-api.md)<br/> Rufen Sie Customer Journey Analytics-Daten programmgesteuert ab, um sie in Ihre eigenen Programme oder Automatisierungsprogramme zu integrieren. |

## Zwischen Funktionen wählen

Mehrere Funktionen können denselben Anwendungsfall implementieren. Wenn Sie sich zwischen diesen Optionen entscheiden, sollten Sie Folgendes berücksichtigen:

* **Datenvolumen**: Ad-hoc-Methoden wie der [Workspace-Export](/help/use-cases/data-export/workspace-export.md) und [Report Builder](/help/use-cases/data-export/report-builder.md) sind auf Zehntausende von Zeilen beschränkt. [Vollständige Tabelle exportieren](/help/use-cases/data-export/export-full-table.md) und [Datensätze exportieren](/help/use-cases/data-export/export-datasets.md) unterstützen Millionen von Zeilen.
* **Rohdaten im Vergleich zu verarbeiteten Daten**: [Datensätze exportieren](/help/use-cases/data-export/export-datasets.md) und [Abfrage-Service (Data Distiller) und Datensätze exportieren](/help/use-cases/data-export/queryservice-export-datasets.md) Rohdaten aus dem Data Lake bereitstellen. [BI-Erweiterung](/help/use-cases/data-export/bi-extension.md), [Exportieren der vollständigen Tabelle](/help/use-cases/data-export/export-full-table.md), [Workspace-Export](/help/use-cases/data-export/workspace-export.md), [Report Builder](/help/use-cases/data-export/report-builder.md) und die [Reporting-API](/help/use-cases/data-export/reporting-api.md) Daten bereitstellen, die bereits von Customer Journey Analytics verarbeitet wurden, einschließlich Attribution, Sitzungserstellung und berechneter Metriken.
* **Technisches Know**: [Query Service (Data Distiller) und Datensätze exportieren](/help/use-cases/data-export/queryservice-export-datasets.md) und die [BI-Erweiterung](/help/use-cases/data-export/bi-extension.md) erfordern SQL-Kenntnisse. [Workspace-](/help/use-cases/data-export/workspace-export.md) und [Report Builder](/help/use-cases/data-export/report-builder.md) verwenden Point-and-Click-Schnittstellen. Die [Reporting-API](/help/use-cases/data-export/reporting-api.md) erfordert Programmierkenntnisse.
* **Planungsanforderungen**: [Exportieren von Datensätzen](/help/use-cases/data-export/export-datasets.md), [Exportieren einer vollständigen Tabelle](/help/use-cases/data-export/export-full-table.md) und [Report Builder](/help/use-cases/data-export/report-builder.md) unterstützen einen wiederkehrenden, geplanten Versand. [Workspace-Export](/help/use-cases/data-export/workspace-export.md) Downloads sind nur ad hoc möglich.
* **Ausgabeformat und Ziel**: Überlegen Sie, ob Sie eine Datei im Cloud-Speicher, eine Tabelle in einem BI-Tool, eine Arbeitsmappe in Excel oder eine Antwort aus einem API-Aufruf benötigen, und gleichen Sie diese dann mit der Funktionalität ab, die sie bereitstellt.
