---
title: Unterereignisse und Objekt-Arrays in Daten-Feeds
description: Erfahren Sie, wie Customer Journey Analytics-Daten-Feeds Unterereignisse aus Schema-Arrays exportieren und dabei die Hierarchie beibehalten, anstatt sie wie Workspace zu reduzieren.
hide: true
feature: Components
source-git-commit: afc1b55eb54b5f3342800489d0a7f63508ee8b10
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%
---
# Unterereignisse in Daten-Feeds

{{release-limited-testing}}

Im XDM-Schema ist alles, was ein Array ist (Zeichenfolge oder Objekt), ein Unterereignis. Unterereignisse in Customer Journey Analytics werden in Daten-Feed-Exporten mit ihrer Hierarchie dargestellt.

In Adobe Analytics werden Unterereignisse als einzelne Spalte dargestellt.

Verwenden Sie die folgenden Informationen, um zu verstehen, wie Sie mit Unterereignissen in Ihren Customer Journey Analytics-Daten-Feeds arbeiten.

## Unterereignisse im XDM-Schema, in Workspace und in Daten-Feeds

Sie definieren Unterereignisse im XDM-Schema entweder als Zeichenfolgen-Arrays oder Objekt-Arrays.

Diese Unterereignisse werden unterschiedlich dargestellt, je nachdem, ob Sie sie in Analysis Workspace oder in Daten-Feeds anzeigen.

| Standort | Darstellung von Unterereignissen |
| --- | --- |
| **Analysis Workspace** | Einzelne Objekte in einem Array von Objekten können als einzelne Komponenten unabhängig von der sichtbaren Hierarchie ausgewählt werden. |
| **Daten-Feeds** | Objekte in einem Array von Objekten werden als Gruppe dargestellt, wobei ihre Hierarchie intakt ist. |

## Hinzufügen von Unterereignisdaten zu einem Daten-Feed

Wenn Sie beim Erstellen eines Daten-Feeds versuchen, eine Spalte hinzuzufügen, die ein Unterereignis ist, wird ein Dialogfeld angezeigt, in dem Sie alle Peer-Unterereignisse hinzufügen können. Alle diese Ereignisse werden in einer einzigen Spalte der Daten-Feed-Ausgabe angezeigt.

## Anzeigen von Unterereignisdaten in der Daten-Feed-Ausgabe

Daten von Unterereignissen (z. B. mehrere Produkte in einem einzigen Ereignis) werden in Customer Journey Analytics-Daten-Feeds anders angezeigt als in Adobe Analytics-Daten-Feeds. In der folgenden Tabelle wird verglichen, wie jedes Produkt Unterereignisdaten darstellt.

| Produkt | So werden Unterereignisdaten in Daten-Feeds angezeigt | Beispiel: Produktliste |
| --- | --- | --- |
| **Adobe Analytics** | In eine durch Trennzeichen getrennte Zeichenfolge in einer einzigen Spalte reduziert. | Eine Produktliste enthält mehrere Produkte, die in einer einzigen Zeichenfolge gruppiert sind:<p>`;LG Washing Machine 2000;1;1600,;LG Dryer 2000;1;500` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Unterereignisse behalten die in Ihrem XDM-Schema definierte Hierarchie bei. Sie bleiben zusammen mit ihrem übergeordneten Ereignis und den gleichrangigen Unterereignissen in derselben Spalte gruppiert. | Eine Produktliste behält ihre Hierarchie bei, die im XDM-Schema als Array definiert ist:<p>`[{"name":"LG Washing Machine 2000","units":1,"revenue":1600},{"name":"LG Dryer 2000","units":1,"revenue":500}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## Abfragen von Unterereignisdaten in der Daten-Feed-Ausgabe

Da Unterereignisdaten [in Customer Journey Analytics-Daten-Feeds anders angezeigt werden](#customer-journey-analytics-vs-adobe-analytics) unterscheiden sich die Abfragen, die Sie dafür verwenden, von denen, die Sie für Adobe Analytics-Daten-Feeds verwenden.

Die folgenden Beispiele zeigen, wie Sie Ereignisse finden, die ein bestimmtes Produkt enthalten. Die Beispiele verwenden die Google BigQuery-Syntax. Andere Data Warehouses, wie Snowflake und Databricks, unterstützen denselben Ansatz mit geringfügigen Syntaxunterschieden.

+++ Abfragen von Produktdaten in Adobe Analytics-Daten-Feeds

In Adobe Analytics-Daten-Feeds wird ein Ereignis mit zwei gemeinsam gekauften Produkten als einzelne, durch Trennzeichen getrennte Zeichenfolge in der `product_list` angezeigt:

```text
Power Tools;Cordless Drill;1;129.99;event1=1;eVar10=DrillBundle,Power Tools;Drill Battery Pack;2;39.98;event1=1;eVar10=DrillBundle
```

Um Ereignisse zu finden, die einen Akku-Bohrer enthalten, analysieren Sie diese Zeichenfolge mit einem regulären Ausdruck:

```sql
SELECT hitid_high, hitid_low, post_evar10
FROM aa_hit_data
WHERE REGEXP_CONTAINS(product_list, r'(^|,)[^;]*;Cordless Drill;')
```

+++

+++ Abfragen von Produktdaten in Customer Journey Analytics-Daten-Feeds

In Customer Journey Analytics-Daten-Feeds werden dieselben beiden Produkte als Array von Objekten in der Spalte `product_list_items` angezeigt. Es ist kein Parsen von Trennzeichen erforderlich:

```json
{
  "row_id": "01K3F2M9-...-4821",
  "timestamp_utc": "2026-09-16T14:32:07.512000Z",
  "product_list_items": [
    { "category": "Power Tools", "product": "Cordless Drill", "quantity": 1, "revenue": 129.99,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} },
    { "category": "Power Tools", "product": "Drill Battery Pack", "quantity": 2, "revenue": 39.98,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} }
  ]
}
```

Wie Sie die Abfrage schreiben, hängt davon ab, ob Sie eine Zeile pro Ereignis oder eine Zeile pro übereinstimmendem Produkt wünschen.

**Gibt eine Zeile pro Ereignis zurück**

Um Ereignisse zu filtern, ohne die Anzahl der Zeilen zu ändern, verwenden Sie `UNNEST` in einer `EXISTS` Unterabfrage:

```sql
SELECT row_id, timestamp_utc, product_list_items
FROM `project.dataset.cja_data_feed` AS f
WHERE EXISTS (
  SELECT 1
  FROM UNNEST(f.product_list_items) AS item
  WHERE item.product = 'Cordless Drill'
);
```

Diese Abfrage gibt für jedes übereinstimmende Ereignis eine Zeile zurück, wobei das vollständige `product_list_items`-Array intakt ist, unabhängig davon, wie viele Produkte im Array übereinstimmen.

**Gibt eine Zeile pro übereinstimmendem Produkt zurück**

Um für jedes übereinstimmende Produkt eine Zeile zurückzugeben, verschieben Sie `UNNEST` in die äußere `FROM`:

```sql
SELECT f.row_id, f.timestamp_utc, item.product, item.quantity, item.revenue
FROM `project.dataset.cja_data_feed` AS f,
     UNNEST(f.product_list_items) AS item
WHERE item.product = 'Cordless Drill';
```

Ein Ereignis mit mehr als einem übereinstimmenden Produkt wird als mehrere Zeilen angezeigt, und die Spalten des Ereignisses, wie `row_id`, wiederholen sich in jeder Zeile. Verwenden Sie diesen Ansatz nur, wenn Sie Details auf Produktebene benötigen. Um Ereignisse in den Ergebnissen zu zählen, verwenden Sie `COUNT(DISTINCT row_id)` anstelle von Zeilen zu zählen.

Dieser Ansatz gilt für alle Array-Felder in Ihrem XDM-Schema, nicht nur für Produkte.

+++






