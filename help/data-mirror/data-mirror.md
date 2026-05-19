---
title: Übersicht über Data Mirror
description: Erfahren Sie, wie Sie Daten zwischen nativen Data Warehouse-Lösungen und Customer Journey Analytics synchronisieren
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
autotag-review: '2026-05-19T08:55:53.979Z'
TQID: 'https://experienceleague.adobe.com/10YCh2cnMTVriKKVOyYfzFfngvGQ2VVHOxzedE5NpWA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 447
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
