---
title: Unterereignisse und Objekt-Arrays in Daten-Feeds
description: Erfahren Sie, wie Customer Journey Analytics-Daten-Feeds Unterereignisse aus Schema-Arrays exportieren und dabei die Hierarchie beibehalten, anstatt sie wie Workspace zu reduzieren.
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
source-git-commit: a4fdb1f8d49b42b6de21881e0c8392995124c1ea
workflow-type: tm+mt
source-wordcount: '1191'
ht-degree: 2%
---
# Unterereignisse in Daten-Feeds

{{release-limited-testing}}

[Unterereignisse](/help/components/segments/sub-event.md) in Customer Journey Analytics ermöglichen die Analyse von Ereignisdaten auf einer Ebene, die detaillierter ist als die Ereignisebene.

Verwenden Sie die folgenden Informationen, um zu verstehen, wie Sie mit Unterereignissen in Ihren Customer Journey Analytics-Daten-Feeds arbeiten.

## Grundlegendes zu Unterereignissen

### Unterereignisse im XDM-Schema

Im XDM-Schema ist jedes Element eines Arrays (ein Zeichenfolgen-Array oder ein Objekt-Array) ein Unterereignis.

Um ein Ereignis mit Unterereignissen innerhalb des XDM-Schemas in Adobe Experience Platform anzuzeigen, wählen Sie [!UICONTROL **Schemas**] aus und erweitern Sie dann ein Ereignis, das Unterereignisse enthält.

Im folgenden Beispiel ist `Product list items` ein Objekt-Array, das verschiedene Unterereignisse enthält.

![XDM-Schema, das ein Objekt-Array und Unterereignisse enthält](assets/df-sub-event-schema.png)

### Beispiel für Unterereignisse: Produkte in einem Kaufereignis

Ein Kunde kauft zwei Produkte in einer Bestellung: einen Akku-Bohrer und zwei Akku-Bohrer. Ihre Implementierung sendet ein einzelnes Kaufereignis, das beide Produkte im `productListItems` Objekt-Array enthält:

```json
{
  "eventType": "commerce.purchases",
  "timestamp": "2026-09-16T14:32:07.512Z",
  "commerce": {
    "purchases": { "value": 1 }
  },
  "productListItems": [
    { "SKU": "CD-2000", "name": "Cordless Drill", "quantity": 1, "priceTotal": 129.99 },
    { "SKU": "BP-2000", "name": "Drill Battery Pack", "quantity": 2, "priceTotal": 39.98 }
  ]
}
```

Dieses Ereignis enthält zwei Unterereignisse, eines für jedes Objekt im `productListItems`-Array. Die folgende Tabelle zeigt, welche Felder zum Ereignis und welche zu den Unterereignissen gehören.

| Ebene | Felder | Beschreibung der Felder |
| --- | --- | --- |
| **Ereignis** | `eventType`, `timestamp`, `commerce.purchases.value` | Der Kauf insgesamt. Jedes Feld hat einen Wert für das Ereignis. Die Metrik **Bestellungen** zählt `1` für dieses Ereignis, unabhängig davon, wie viele Produkte es enthält. |
| **Unter-Ereignis** | `SKU`, `name`, `quantity`, `priceTotal` in jedem `productListItems` | Ein einzelnes Produkt im Kauf. Jedes Feld hat einen -Wert pro Produkt. Beispielsweise ist `quantity` für den Akku-Bohrer und `2` für den Akku-Bohrer `1`. |

{style="table-layout:auto"}

>[!NOTE]
>
>Unterereignisse enthalten nur die Daten, die mit dem Ereignis gesendet werden. Customer Journey Analytics rekonstruiert den Inhalt des Warenkorbs nicht aus früheren Ereignissen, z. B. Hinzufügungen zum Warenkorb oder Checkouts. Damit Produkte als Unterereignisse eines Kaufereignisses angezeigt werden, muss sie Ihre Implementierung in `productListItems` dieses Kaufereignisses einschließen.

## Hinzufügen von Unterereignisdaten zu einem Daten-Feed

Wenn Sie versuchen, beim Erstellen eines Daten-Feeds eine Spalte hinzuzufügen, die ein Unterereignis ist, wird ein Dialogfeld angezeigt, in dem Sie aufgefordert werden, eines der Peer-Unterereignisse hinzuzufügen. In der Daten-Feed-Ausgabe werden alle diese Ereignisse in einer Spalte angezeigt.

## Anzeigen von Unterereignisdaten in der Daten-Feed-Ausgabe

### Unterschiede bei Unterereignissen zwischen Analysis Workspace und Daten-Feeds

Unterereignisse werden in Analysis Workspace und Daten-Feeds in Customer Journey Analytics unterschiedlich dargestellt.

| Standort | Darstellung von Unterereignissen |
| --- | --- |
| **Analysis Workspace (in Customer Journey Analytics)** | Kann als einzelne Komponenten getrennt von einer sichtbaren Hierarchie ausgewählt werden. |
| **Daten-Feeds (in Customer Journey Analytics)** | Wird als Gruppe mit intakter Hierarchie dargestellt. |

### Unterschiede bei Unterereignissen zwischen Adobe Analytics und Customer Journey Analytics

Daten von Unterereignissen (z. B. mehrere Produktdetails in einem einzigen Kaufereignis) werden in Customer Journey Analytics-Daten-Feeds anders angezeigt als in Adobe Analytics-Daten-Feeds. In der folgenden Tabelle wird verglichen, wie jedes Produkt Unterereignisdaten darstellt.

| Produkt | So werden Unterereignisdaten in Daten-Feeds angezeigt | Beispiel: Produktliste |
| --- | --- | --- |
| **Adobe Analytics** | In eine durch Trennzeichen getrennte Zeichenfolge in einer einzigen Spalte reduziert. | Eine Produktliste enthält mehrere Produkte, die in einer einzigen Zeichenfolge gruppiert sind:<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Unterereignisse behalten die in Ihrem XDM-Schema definierte Hierarchie bei. Obwohl sie in derselben Spalte gruppiert sind, zeigen sie ihre relationale Hierarchie zum übergeordneten Ereignis und zu den gleichrangigen Unterereignissen an. | Eine Produktliste behält ihre Hierarchie bei, die im XDM-Schema als Array definiert ist:<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

### Unterschiede zu Adobe Analytics

### Unterschiede bei der Ausgabe zwischen Daten-Feeds von Adobe Analytics und Customer Journey Analytics

Daten von Unterereignissen (z. B. mehrere Produktdetails in einem einzigen Kaufereignis) werden in Customer Journey Analytics-Daten-Feeds anders angezeigt als in Adobe Analytics-Daten-Feeds. In der folgenden Tabelle wird verglichen, wie jedes Produkt Unterereignisdaten darstellt.

| Produkt | So werden Unterereignisdaten in Daten-Feeds angezeigt | Beispiel: Produktliste |
| --- | --- | --- |
| **Adobe Analytics** | In eine durch Trennzeichen getrennte Zeichenfolge in einer einzigen Spalte reduziert. | Eine Produktliste enthält mehrere Produkte, die in einer einzigen Zeichenfolge gruppiert sind:<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Unterereignisse behalten die in Ihrem XDM-Schema definierte Hierarchie bei. Obwohl sie in derselben Spalte gruppiert sind, zeigen sie ihre relationale Hierarchie zum übergeordneten Ereignis und zu den gleichrangigen Unterereignissen an. | Eine Produktliste behält ihre Hierarchie bei, die im XDM-Schema als Array definiert ist:<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## Unterschiede zwischen Unterereignissen zwischen der Ausgabe von Analysis Workspace- und Daten-Feeds

Unterereignisse werden in Analysis Workspace und Daten-Feeds in Customer Journey Analytics unterschiedlich dargestellt.

| Standort | Darstellung von Unterereignissen |
| --- | --- |
| **Analysis Workspace** | Kann als einzelne Komponenten getrennt von einer sichtbaren Hierarchie ausgewählt werden. |
| **Daten-Feeds** | Wird als Gruppe mit intakter Hierarchie dargestellt. |


## Anzeigen von Unterereignisdaten in der Daten-Feed-Ausgabe

Daten von Unterereignissen (z. B. mehrere Produktdetails in einem einzigen Kaufereignis) werden in Customer Journey Analytics-Daten-Feeds anders angezeigt als in Adobe Analytics-Daten-Feeds. In der folgenden Tabelle wird verglichen, wie jedes Produkt Unterereignisdaten darstellt.

| Produkt | So werden Unterereignisdaten in Daten-Feeds angezeigt | Beispiel: Produktliste |
| --- | --- | --- |
| **Adobe Analytics** | In eine durch Trennzeichen getrennte Zeichenfolge in einer einzigen Spalte reduziert. | Eine Produktliste enthält mehrere Produkte, die in einer einzigen Zeichenfolge gruppiert sind:<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Unterereignisse behalten die in Ihrem XDM-Schema definierte Hierarchie bei. Obwohl sie in derselben Spalte gruppiert sind, zeigen sie ihre relationale Hierarchie zum übergeordneten Ereignis und zu den gleichrangigen Unterereignissen an. | Eine Produktliste behält ihre Hierarchie bei, die im XDM-Schema als Array definiert ist:<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## Abfragen von Unterereignisdaten in der Daten-Feed-Ausgabe

Da Unterereignisdaten [in Customer Journey Analytics-Daten-Feeds anders angezeigt werden](#view-sub-event-data-in-data-feed-output) unterscheiden sich die Abfragen, die Sie dafür verwenden, von denen, die Sie für Adobe Analytics-Daten-Feeds verwenden.

Die folgenden Beispiele zeigen, wie Sie Ereignisse finden, die ein bestimmtes Produkt enthalten. Die Beispiele verwenden die Google BigQuery-Syntax. Andere Data Warehouses, wie Snowflake und Databricks, unterstützen denselben Ansatz mit geringfügigen Syntaxunterschieden.

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






