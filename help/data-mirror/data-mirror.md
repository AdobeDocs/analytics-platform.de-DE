---
title: Übersicht über Data Mirror
description: Erfahren Sie, wie Sie Daten zwischen nativen Data Warehouse-Lösungen und Customer Journey Analytics synchronisieren
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
source-git-commit: a6cdade9790ef4bc222eb5979b7370f7403b5ad5
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 1%

---

# Übersicht über Experience Platform Data Mirror

{{release-limited-testing}}

Data Mirror ist eine Experience Platform-Funktion, die die Aufnahme von Änderungen auf Zeilenebene aus externen Datenbanken in den Data Lake mithilfe von modellbasierten Schemata ermöglicht. Sie behält Datenbeziehungen bei, erzwingt Eindeutigkeit und unterstützt die Versionierung, ohne dass vorgelagerte ETL-Prozesse (Extract, Transform, Load) erforderlich sind.

Verwenden Sie Data Mirror, um Einfügungen, Aktualisierungen und Löschungen (veränderliche Daten) aus externen Data Warehouse-nativen Lösungen wie [!DNL Snowflake], [!DNL Azure Databricks] oder [!DNL Google BigQuery] direkt in Experience Platform zu synchronisieren. Mit Data Mirror können Sie Ihre bestehende Datenbankmodellstruktur und Datenintegrität beibehalten, wenn Sie Daten in Experience Platform importieren.


## Funktionen und Vorteile

Data Mirror bietet die folgenden grundlegenden Funktionen für die Datenbanksynchronisierung:

* **Primäre Schlüsseldurchsetzung**. Stellt Eindeutigkeit innerhalb von Datensätzen sicher und verhindert doppelte Datensätze während der Aufnahme.
* **Änderungsaufnahme auf Zeilenebene**. Unterstützt granulare Datenänderungen, einschließlich Upserts und Löschungen mit Präzisionssteuerung.
* **Schema-Beziehungen**. Aktiviert Fremdschlüssel- und Primärschlüsselbeziehungen zwischen Datensätzen über Deskriptoren.
* **Fehlerhafte Ereignisbehandlung**. Prozesse ändern Ereignisse mithilfe von Versions- und Zeitstempeldeskriptoren, auch wenn sie nicht in der richtigen Reihenfolge eintreffen.
* **Direct Warehouse-Integration**. Stellt eine Verbindung zu unterstützten Cloud-Data-Warehouses für die Synchronisierung von Änderungen in Echtzeit her.

Verwenden Sie Data Mirror, um Änderungen direkt aus Ihren Quellsystemen aufzunehmen, die Schemaintegrität durchzusetzen und die Daten für Analysen, Journey-Orchestrierung und Compliance-Workflows verfügbar zu machen. Data Mirror eliminiert komplexe vorgelagerte ETL-Prozesse und beschleunigt die Implementierung durch die Möglichkeit der direkten Spiegelung vorhandener Datenbankmodelle. Durch diese Eliminierung kann die Data Governance durch eine präzise Kontrolle von Löschungen und Datenhygienevorgängen verbessert werden.

<!-- Add link when AEP docs are ready... -->

Siehe auch die Experience Platform-Dokumentation zu Data Mirror.


## Data Mirror für Customer Journey Analytics

>[!NOTE]
>
>Die Experience Platform Data Mirror-Funktion für Customer Journey Analytics ist bis zum 25 **März 2026 in einer öffentlichen Betaversion**. Während der Beta-Phase sind Aktualisierungen der Änderungsdatenerfassung (Change Data Capture, CDC) auf eine Berechtigung für tägliche Änderungen von 10 Millionen Zeilen für Customer Journey Analytics beschränkt. Adobe behält sich das Recht vor, den Beta-Zugriff auf Experience Platform Data Mirror-Funktionen zu beenden, falls Ihr Unternehmen diese Grenze überschreitet. Weitere Informationen zur Funktion, einschließlich der Auswirkungen auf die Abrechnung, finden Sie in diesem Abschnitt der Dokumentation zu Experience League.
>

Die Funktion von Experience Platform Data Mirror für Customer Journey Analytics ist für ausgewählte native Data Warehouse-Lösungen ([!DNL Azure Databricks], [!DNL Google BigQuery] und [!DNL Snowflake]) verfügbar. Die Customer Journey Analytics-Version der Data Mirror-Funktion erfordert eine ordnungsgemäße Einrichtung und Konfiguration mehrerer Komponenten:

* [Native Data Warehouse-Lösung](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)


>[!MORELIKETHIS]
>
>[Data Mirror-Schnellstartanleitung: Spiegeln und Verwenden modellbasierter Daten](model-based.md)
>
