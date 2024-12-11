---
title: Anwendungsfälle für den Datenexport
description: Verstehen verschiedener Anwendungsfälle für den Datenexport zum Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 8b9c164e-01da-4b43-8e2c-99904223cae5
source-git-commit: ae0e7a906700522d7babc1d573a0b4cdbf1be6fc
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 1%

---

# Anwendungsfälle für den Datenexport

In diesem Abschnitt finden Sie Anwendungsbeispiele für den Datenexport und die Implementierung dieser Anwendungsfälle mit einer oder mehreren Funktionen von Customer Journey Analytics oder Experience Platform. Jede Funktion wird in einem separaten Artikel näher beschrieben.

## Einführung

Einer der eindeutigen Unterschiede zwischen Adobe Analytics und Customer Journey Analytics besteht in der Verarbeitung von Daten für die Attribution und Sitzungserstellung. Weitere Informationen finden Sie unter [Datenverarbeitung in Adobe Analytics und Customer Journey Analytics vergleichen](/help/getting-started/aa-vs-cja/data-processing-comparisons.md) .

### Adobe Analytics: Attribution der Sammlungszeit und Sitzungserstellung.

In Adobe Analytics werden alle Ereignisse live und in Reihenfolge nach Geräte-ID verarbeitet, sodass Adobe Clickstream-Daten mit beibehaltenen oder zugewiesenen Werten zur Erfassungszeit generieren, speichern und exportieren kann, einschließlich:

* Persistenz der Dimension (z. B. Kampagnen-Trackingcodes, die nach 90 Tagen ablaufen).
* Besuchsnummer und Sitzungserstellung.
* Dimensionen, berechnet durch Verarbeitungs- und VISTA-Regeln.

Dies wirkt sich auf den Export von Daten aus Adobe Analytics aus:

* Die Datenverarbeitung ist nach der ersten Erfassung statisch.
* Datenfeeds enthalten &quot;Post&quot;-Spalten, die die Verarbeitung der Erfassungszeit widerspiegeln.


### Customer Journey Analytics: Attribution und Sitzungserstellung der Abfragezeit

Unter Customer Journey Analytics werden Ereignisse nicht der Reihe nach erfasst und anstelle einer Geräte-ID wird eine Personen-ID verwendet, sodass Customer Journey Analytics die Attribution und Sitzungserstellung zum Zeitpunkt des Berichts aktualisieren kann. Diese Art der Datenerfassung bietet Flexibilität, z. B.:

* Durch die Zuordnung können _Daten täglich oder wöchentlich wiederholt werden_, wodurch anonyme Ereignisse bekannten Ereignissen zugeordnet werden. Weitere Informationen finden Sie unter [Stitching](../../stitching/overview.md) .
* Die Sessionierung und beibehaltene Werte ändern sich jedes Mal
   * neue Daten erfasst werden oder
   * Beim Zuordnen werden Ereignisse zum Verlauf einer Person hinzugefügt.

Die Berichtszeitverarbeitung wirkt sich auf den Export von Daten von Customer Journey Analytics aus. Exporte, die beibehaltene Werte enthalten, stimmen nicht mit Customer Journey Analytics-Berichten überein, und die Werte werden im Laufe der Zeit verworfen.

Zur Konsistenz der Metriken wird die Verwendung der neuen Funktionen im Customer Journey Analytics bevorzugt. Im Allgemeinen übersteigt die Experience Platform- und Customer Journey Analytics-Datenexportfunktion die Daten-Feed-Funktion von Adobe Analytics. Experience Platform und Customer Journey Analytics bieten Folgendes:

* neue Datenquellen und Verarbeitungen, die dem Datenexport unterliegen

   * nicht digitale Datenquellen einschließen,
   * benutzerdefinierte Attribution und Sitzungserstellung auf der Grundlage von Geschäftsregeln anwenden und
   * halten Sie die Journey der Kunden über das Stitching auf dem Laufenden.

* Implementierung von maßgeschneiderten Anwendungsfällen für den Datenexport

   * Daten an die Stelle exportieren, an die Sie sie benötigen, einschließlich Business Intelligence-Tools (BI) und Cloud-Zielen;
   * Daten mithilfe der BI-Tools-Integration mit Analysis Workspace synchronisieren lassen,
   * keine Notwendigkeit besteht, die Verarbeitungslogik in Ihren eigenen Systemen zu replizieren,
   * neue Unterstützung für berechnete Metriken, abgeleitete Felder und Segmentierung sowie

* Berücksichtigung von Sicherheit und Data Governance bei der Konzeption

   * den gesamten Datenexport nach Benutzer und Ziel überwachen,
   * Festlegung von Beschränkungen dafür, welche Daten für den Export verfügbar sind, und
   * Warnhinweise für Versandprobleme und Einschränkungen bei geplanten Versandfenstern festlegen.


## Anwendungsbeispiele und Funktionen

Im Allgemeinen unterstützt der Datenexport eine Reihe von Anwendungsfällen. Jeder Anwendungsfall unterscheidet sich hinsichtlich der erforderlichen Daten und des Zugriffs und Exports auf diese Daten. Experience Platform und Customer Journey Analytics bieten eine Reihe von Funktionen, die entweder unabhängig oder kombiniert die verschiedenen Anwendungsfälle lösen können. Die nachstehende Tabelle bietet einen Überblick über die Anwendungsfälle für identifizierte Datenexporte und die Experience Platform- und Customer Journey Analytics-Funktionen zur Implementierung dieser Anwendungsfälle.

| Anwendungsfälle für den Datenexport | Experience Platform und Customer Journey Analytics |
|---|---|
| **Datensicherung**<br/> Speichern Sie eine vollständige Kopie Ihrer digitalen Daten aus Compliance- oder Regelungsgründen. | **Experience Platform**: [**Exportieren Sie Datensätze**](export-datasets.md)<br/> Exportieren Sie in Experience Platform erfasste Daten direkt in Cloud-Ziele, und zwar zeitplanmäßig oder ad-hoc. |
| **Datenvalidierung**<br/> Bewerten Sie Clickstream-Daten auf ihre Genauigkeit bei der Datenerfassung. | **Experience Platform**: [**Query Service (Data Distiller) und Export von Datensätzen**](queryservice-export-datasets.md)<br/> Interaktive PostgreSQL-Schnittstelle zum Ausführen von Ad-hoc-SQL-Abfragen mithilfe Ihres bevorzugten SQL-Tools zur Überprüfung der Daten in Ihren Datensätzen.<br/><br/>**Customer Journey Analytics**: [**Exportieren Sie die vollständige Tabelle**](export-full-table.md)<br/> Validieren Sie verarbeitete Daten aus CJA mit angewendeter Attribution und Sitzungserstellung. |
| **Data Lake-, Data Warehouse- oder BI-Tools**<br/> Bringen Sie digitale Daten in Ihre eigenen BI-Tools oder in den Data Lake zur Verwendung mit zusätzlichen Datensätzen. | **Customer Journey Analytics**: [**BI-Erweiterung**](bi-extension.md)<br/> Fügen Sie Customer Journey Analytics verarbeitete Metriken zu Datenvisualisierungs-Tools wie Power BI hinzu und kombinieren Sie sie mit zusätzlichen Daten für benutzerdefinierte Berichte <br/><br/>**Experience Platform**: [**Abfragedienst (Data Distiller) und exportieren Sie Datensätze**](queryservice-export-datasets.md)<br> Generieren Sie benutzerdefinierte Clickstream-Daten mit SQL, die an Cloud-Ziele bereitgestellt werden. |
| **Bereitschaft für KI/ML**<br/> Verbessern der Modelle und Aufgaben für künstliche Intelligenz/maschinelles Lernen mit Customer Journey Analytics-Daten. | **Customer Journey Analytics**: [**Exportieren Sie die vollständige Tabelle**](export-full-table.md)<br/> Exportieren Sie verarbeitete Dimensionen und Metriken aus der Customer Journey Analytics in Cloud-Ziele einmalig oder wiederkehrend, einschließlich berechneter Metriken und Segmentierung.<br/><br/>**Experience Platform**: [**Query Service (Data Distiller) und Export von Datensätzen**](queryservice-export-datasets.md)<br/> Generieren Sie benutzerdefinierte Clickstream-Daten mit SQL, um KI-/ML-Modelle anzureichern. |
