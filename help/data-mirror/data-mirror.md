---
title: Übersicht über Data Mirror
description: Erfahren Sie, wie Sie Daten zwischen nativen Data Warehouse-Lösungen und Customer Journey Analytics synchronisieren
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
source-git-commit: dc3aa31c280c1a8ee8a0187edeca9bd34a2c9e2e
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# Übersicht über Experience Platform Data Mirror

{{release-limited-testing}}

Data Mirror ist eine Experience Platform-Funktion, die die Aufnahme von Änderungen auf Zeilenebene aus externen Datenbanken in den Data Lake mithilfe relationaler Schemata ermöglicht. Sie behält Datenbeziehungen bei, erzwingt Eindeutigkeit und unterstützt die Versionierung, ohne dass ETL-Prozesse (Upstream Extract, Transform, Load) erforderlich sind.

Verwenden Sie Experience Platform Data Mirror, um Einfügungen, Aktualisierungen und Löschungen (veränderliche Daten) aus externen Data Warehouse-nativen Lösungen ([!DNL Snowflake], [!DNL Azure Databricks] oder [!DNL Google BigQuery]) direkt mit Daten in Experience Platform zu synchronisieren. Mit Data Mirror können Sie Ihre bestehende Datenbankmodellstruktur und Datenintegrität beibehalten, wenn Sie Daten in Experience Platform importieren.

## Funktionen und Vorteile

Data Mirror bietet die folgenden grundlegenden Funktionen für die Datenbanksynchronisierung:

* **Primäre Schlüsseldurchsetzung.** Stellt Eindeutigkeit innerhalb von Datensätzen sicher und verhindert doppelte Datensätze während der Aufnahme.
* **Änderungsaufnahme auf Zeilenebene.** Unterstützt granulare Datenänderungen, einschließlich Upserts und Löschungen mit Präzisionssteuerung.
* **Schemabeziehungen.** Aktiviert Fremdschlüssel- und Primärschlüsselbeziehungen zwischen Datensätzen über Deskriptoren.
* **Fehlerhafte Ereignisbehandlung.** Prozesse ändern Ereignisse mithilfe von Versions- und Zeitstempeldeskriptoren, auch wenn sie nicht in der richtigen Reihenfolge eintreffen.
* **Direct Warehouse-Integration.** Stellt eine Verbindung zu unterstützten Cloud-Data-Warehouses für die Synchronisierung von Änderungen in Echtzeit her.

Verwenden Sie Data Mirror, um Änderungen direkt aus Ihren Quellsystemen aufzunehmen, die Schemaintegrität durchzusetzen und die Daten für Analysen, Journey-Orchestrierung und Compliance-Workflows verfügbar zu machen. Data Mirror eliminiert komplexe vorgelagerte ETL-Prozesse und beschleunigt die Implementierung durch die Möglichkeit der direkten Spiegelung vorhandener Datenbankmodelle. Durch diese Eliminierung kann die Data Governance durch eine präzise Kontrolle von Löschungen und Datenhygienevorgängen verbessert werden.

Siehe auch die [Experience Platform-Dokumentation zu Data Mirror](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview){target="_blank"}.

## Data Mirror für Customer Journey Analytics

>[!NOTE]
>
>Data Mirror ist eine Funktion, die sich derzeit in der Beta-Phase befindet und die die Synchronisierung von Daten aus ausgewählten Data Warehouses mithilfe der Änderungsdatenerfassung (CDC) für Analysen in Customer Journey Analytics unterstützt. <br/>Diese Funktion wird am 18. Juni 2026 allgemein für Customer Journey Analytics verfügbar sein. Informationen dazu, wie sich dies künftig auf die jährliche Aufnahmebegrenzung auswirken könnte, finden Sie in der entsprechenden Produktbeschreibung. Bitte beachten Sie, dass Ihr Unternehmen weiterhin Zugriff auf die Funktion hat, wenn Data Mirror von der Beta-Version zur allgemeinen Verfügbarkeit übergeht.
>

Experience Platform Data Mirror für Customer Journey Analytics ist für ausgewählte native Data Warehouse-Lösungen ([!DNL Azure Databricks], [!DNL Google BigQuery] und [!DNL Snowflake]) verfügbar. Die Customer Journey Analytics-Version von Experience Platform Data Mirror erfordert eine ordnungsgemäße Konfiguration der folgenden Anwendungen oder Komponenten:

* [Native Data-Warehouse-Lösungen](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>[Schnellstartanleitung zu Data Mirror: Relationale Daten spiegeln und verwenden](relational.md)
>[Data Mirror (Dokumentation zu Experience Platform)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>[Relationale Schemata (Dokumentation zu Experience Platform)](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/schema/relational)
