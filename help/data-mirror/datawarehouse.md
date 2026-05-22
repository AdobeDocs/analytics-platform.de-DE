---
title: Konfigurieren von nativen Data Warehouse-Lösungen
description: Erfahren Sie, wie Sie native Data Warehouse-Lösungen für Experience Platform Data Mirror für Customer Journey Analytics konfigurieren
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: 92cffcc5-d7a7-47f5-869d-1fc665594bf4
autotag-review: '2026-05-19T08:56:46.637Z'
TQID: 'https://experienceleague.adobe.com/A3GkkNVAO9qpbOqCrZnf6PNJfRuwMaodJVOOuSRg0w8'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 442
ht-degree: 0%

---

# Konfigurieren von nativen Data Warehouse-Lösungen

{{release-limited-testing}}

Zur Unterstützung von Experience Platform Data Mirror für Customer Journey Analytics müssen die Daten, die Sie aus den drei unterstützten nativen Data Warehouse-Lösungen ([[!DNL Azure Databricks]](#azure-databricks), [[!DNL Google BigQuery]](#google-bigquery), [[!DNL Snowflake]](#snowflake)) verwenden möchten, für die Änderungsdatenerfassung aktiviert werden.


## [!DNL Azure Databricks]

Aktivieren Sie **Daten-Feed ändern** in Ihren [!DNL Azure Databricks]-Tabellen, um die Änderungsdatenerfassung in Ihrer Quellverbindung zu verwenden.

Verwenden Sie die folgenden Befehle, um den Änderungsdaten-Feed in Ihren Tabellen zu aktivieren:

**Neue Tabelle**

Um den Änderungsdaten-Feed auf eine neue Tabelle anzuwenden, müssen Sie die Tabelleneigenschaft `delta.enableChangeDataFeed` im `CREATE TABLE`-Befehl auf `TRUE` setzen.

```sql
CREATE TABLE student (id INT, name STRING, age INT) TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**Vorhandene Tabelle**

Um den Änderungsdaten-Feed auf eine vorhandene Tabelle anzuwenden, müssen Sie die Tabelleneigenschaft `delta.enableChangeDataFeed` im `ALTER TABLE`-Befehl auf `TRUE` setzen.

```sql
ALTER TABLE myDeltaTable SET TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**Alle neuen Tabellen**

Um den Änderungsdaten-Feed auf alle neuen Tabellen anzuwenden, müssen Sie Ihre Standardeigenschaften auf `TRUE` festlegen.

```sql
set spark.databricks.delta.properties.defaults.enableChangeDataFeed = true;
```

Weitere Informationen finden Sie im [[!DNL Azure Databricks] Handbuch zum Aktivieren des Änderungsdaten-Feeds](https://docs.databricks.com/aws/en/delta/delta-change-data-feed#enable-change-data-feed).

Lesen Sie die folgende Dokumentation, um zu erfahren, wie Sie die Änderungsdatenerfassung für Ihre [!DNL Azure Databricks]-Quellverbindung aktivieren:

* [Erstellen  [!DNL Azure Databricks]  Basisverbindung](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/databricks).
* [Erstellen einer Quellverbindung für eine Datenbank](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).

## [!DNL Google BigQuery]

Um die Änderungsdatenerfassung in Ihrer [!DNL Google BigQuery]-Quellverbindung zu verwenden, navigieren Sie in der [!DNL Google Cloud]-Konsole zu Ihrer [!DNL Google BigQuery]-Seite und setzen `enable_change_history` auf `TRUE`. Diese Eigenschaft aktiviert den Änderungsverlauf für Ihre Datentabelle.

Weitere Informationen finden Sie im Handbuch zu [Datendefinitionssprachanweisungen in [!DNL GoogleSQL]](https://cloud.google.com/bigquery/docs/reference/standard-sql/data-definition-language#table_option_list).

Lesen Sie die folgende Dokumentation, um zu erfahren, wie Sie die Änderungsdatenerfassung für Ihre [!DNL Google BigQuery]-Quellverbindung aktivieren:

* [Erstellen  [!DNL Google BigQuery]  Basisverbindung](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/bigquery).
* [Erstellen einer Quellverbindung für eine Datenbank](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).

## [!DNL Snowflake]

Aktivieren Sie **Änderungs-Tracking** in Ihren [!DNL Snowflake], um die Änderungsdatenerfassung in Ihren Quellverbindungen zu verwenden.

Aktivieren Sie [!DNL Snowflake] die Änderungsverfolgung mithilfe der `ALTER TABLE` und legen Sie `CHANGE_TRACKING` auf `TRUE` fest.

```sql
ALTER TABLE mytable SET CHANGE_TRACKING = TRUE
```

Weitere Informationen finden Sie im [[!DNL Snowflake] Handbuch zur Verwendung der changes-Klausel](https://docs.snowflake.com/en/sql-reference/constructs/changes#usage-notes).

Lesen Sie die folgende Dokumentation, um zu erfahren, wie Sie die Änderungsdatenerfassung für Ihre [!DNL Snowflake]-Quellverbindung aktivieren:

* [Erstellen  [!DNL Snowflake]  Basisverbindung](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/snowflake).
* [Erstellen einer Quellverbindung für eine Datenbank](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).


>[!MORELIKETHIS]
>
>[Data Mirror-Schnellstartanleitung: Spiegeln und Verwenden von relationalen Daten](relational.md)
>
