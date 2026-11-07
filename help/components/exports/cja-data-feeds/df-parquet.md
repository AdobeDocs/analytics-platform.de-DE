---
title: Verwenden von Parquet-Dateien aus Customer Journey Analytics-Daten-Feeds
description: Erfahren Sie, warum Customer Journey Analytics-Daten-Feeds Parquet-Dateien bereitstellen, wie Parquet im Vergleich zu CSV, TSV und JSON funktioniert und wie Sie die Dateien abfragen oder laden können.
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: bd396cb4909d131ed60c97e7101cf85946555e38
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 1%
---
# Arbeiten mit Parquet-Dateien in Daten-Feeds

{{release-limited-testing}}

Customer Journey Analytics-Daten-Feeds stellen Dateien im Parquet-Format bereit. Die meisten modernen Data Warehouses können Parquet-Dateien direkt lesen, sodass Sie die Dateien normalerweise nicht konvertieren müssen, bevor Sie sie verwenden.

Verwenden Sie die folgenden Informationen, um zu verstehen, warum Daten-Feeds Parquet verwenden, wie Parquet mit anderen Dateiformaten vergleicht und wie Sie Parquet-Dateien in Ihrem Data Warehouse abfragen oder laden.

## Vorteile der Verwendung von Parquet für Daten-Feeds

Parquet eignet sich aus den folgenden Gründen besser für die Datenfeed-Ausgabe als CSV, TSV oder JSON:

* **Wide Feeds**: Daten-Feeds können Hunderte von Spalten haben. Mit Parquet kann eine Abfrage nur die benötigten Spalten lesen.

* **Verschachtelte Felder**: Parquet stellt verschachtelte Felder, z. B. eine Produktliste, nativ dar. CSV und TSV können sie nur darstellen, indem sie in Zeichenfolgen codiert werden. Weitere Informationen finden Sie unter [Komponenten von Unterereignissen in Daten-Feeds](/help/components/exports/cja-data-feeds/df-sub-event.md).

* **Große Exporte**: Parkett reduziert in der Regel die Lager- und Transferkosten. Außerdem werden das Parsen von Text und das Raten von Typen beim Laden der Daten vermieden.

## Vergleich von Parquet mit CSV, TSV und JSON

CSV, TSV und JSON sind gängige textbasierte Dateiformate:

* **CSV und TSV**: Jede Datenzeile ist eine Textzeile mit durch Kommas (CSV) oder Tabulatoren (TSV) getrennten Werten. Adobe Analytics-Daten-Feeds stellen TSV-Dateien bereit. Weitere Unterschiede zwischen Daten-Feeds in Customer Journey Analytics und Adobe Analytics finden Sie unter [Vergleichen von Daten-Feeds in Customer Journey Analytics und Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md).

* **JSON**: Jeder Datensatz wird als Text mit benannten Feldern gespeichert und kann verschachtelte Arrays und Objekte enthalten.

In der folgenden Tabelle werden die Unterschiede zwischen Parquet, CSV, TSV und JSON beschrieben:

| Kennlinie | Parquet | CSV oder TSV | JSON |
| --- | --- | --- | --- |
| **Dateigröße** | Kleinste. Die Komprimierung ist in die Datei integriert, und Tools dekomprimieren nur die Spalten, die eine Abfrage liest. | Größer. Komprimierung, wie gzip, gilt für die gesamte Datei, sodass Tools die gesamte Datei dekomprimieren müssen, um sie zu lesen und oft nicht parallel lesen können. | Größte. Feldnamen werden in jedem Datensatz wiederholt. |
| **Abfrageschwindigkeit** | Schnell. Eine Abfrage liest nur die benötigten Spalten. | Langsamer. Ganze Zeilen müssen gelesen und analysiert werden. | Langsamer. Ganze Zeilen müssen gelesen und analysiert werden. |
| **Datentypen** | Eingegeben. Das Schema ist in die Datei eingebettet. | Nicht typisiert. Alle Werte sind Textwerte, und beim Laden der Daten werden die Typen abgeleitet. | Lose Typisierung. |
| **Verschachtelte Daten** | Arrays und Objekte werden nativ unterstützt. | Nicht unterstützt. Arrays und Objekte müssen reduziert oder als Zeichenfolgen codiert werden. | Arrays und Objekte werden nativ unterstützt. |
| **Lesbarkeit** | Erfordert ein Tool wie Data Warehouse, DuckDB oder Python. | Wird in einem Texteditor oder einer Tabelle geöffnet. | Wird in einem Texteditor geöffnet. |

## Abfragen oder Laden von Parquet-Dateien

Die Daten-Feed-Dateien werden im Parquet-Format an den Cloud-Speicherort bereitgestellt, den Sie beim Erstellen [&#x200B; Daten-Feeds ausgewählt &#x200B;](/help/components/exports/cja-data-feeds/create-feed.md).

Anstatt die Dateien herunterzuladen, verbinden Sie Ihr Data Warehouse normalerweise mit dem Speicherort. Sie können die Parquet-Dateien dann auf eine der folgenden Arten verwenden:

### Abfragen der vorhandenen Dateien

Definieren Sie eine externe Tabelle, die auf die Dateien in Ihrem Cloud-Speicher verweist. Das Data Warehouse liest die Dateien, wenn Sie eine Abfrage ausführen.

* **Snowflake**: Externe Tabellen oder Abfragen für ein externes Stadium
* **Databricks**: Externe Tabellen über Amazon S3, Azure Data Lake Storage (ADLS) oder Google Cloud Storage
* **BigQuery**: Externe Tabellen über Google Cloud Storage
* **Amazon Redshift**: Redshift Spectrum über Amazon S3

### Laden der Dateien in verwaltete Tabellen

Das Laden von Dateien in verwaltete Tabellen ist eine gängige Wahl für wiederkehrende Arbeitslasten. Beispiel:

* **Snowflake**: `COPY INTO`
* **BigQuery**: Aufträge laden
* **Databricks**: `COPY INTO` oder Auto Loader

## Parquet-Daten in CSV oder JSON konvertieren

Wenn Ihre nachgelagerten Prozesse CSV- oder JSON-Dateien erfordern, können die meisten Data Warehouses und Tools Parquet-Daten nach dem Laden in eines der beiden Formate exportieren. In Snowflake können Sie beispielsweise Abfrageergebnisse als CSV- oder JSON-Datei mit `COPY INTO` entladen.
