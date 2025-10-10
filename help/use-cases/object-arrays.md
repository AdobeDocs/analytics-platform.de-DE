---
title: Verwenden von Objekt-Arrays
description: Erfahren Sie, wie Customer Journey Analytics Berichte zu Datenhierarchien erstellt.
exl-id: 59318da7-5408-4a9d-82aa-8bcbec7f7364
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: aff01f4fc3520d461ca800382cc24d8d948d9cbc
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 61%

---

# Verwenden von Objekt-Arrays

Manche Plattformschemas können Objekt-Arrays enthalten. Adobe Customer Journey Analytics unterstützt die Aufnahme und das Reporting von Objekt-Arrays innerhalb von Ereignis-, Lookup- und Profildaten. Eines der häufigsten Beispiele ist ein Warenkorb, der mehrere Produkte enthält. Jedes Produkt hat einen Namen, eine Produktnummer, eine Kategorie, einen Preis, eine Menge und andere Dimensionen, die Sie verfolgen möchten. Alle diese Faktoren haben unterschiedliche Anforderungen, müssen jedoch alle in denselben Hit passen.

In früheren Versionen von Adobe Analytics wurde dies durch die `products`-Variable erreicht. Dabei handelte es sich um eine verkettete Zeichenfolge, in der die Bestandteile eines Produkts durch Semikolons (`;`) getrennt waren, während die Produkte durch Kommas (`,`) getrennte waren. Dies war die einzige Variable mit eingeschränkter Unterstützung von „Objekt-Arrays“. Variablen mit mehreren Werten, wie z. B. Listenvariablen, konnten das Äquivalent zu Arrays unterstützen, sie konnten aber keine „Objekt-Arrays“ unterstützen. Customer Journey Analytics erweitert dieses Konzept durch die Unterstützung beliebig tiefer Hierarchien innerhalb einer einzigen Datenzeile, eine Funktion, die in keiner vorherigen Version von Adobe Analytics verfügbar ist.

## Beispiel für dasselbe Ereignis

Das folgende Ereignis ist ein JSON-Objekt, das einen Kauf einer Waschmaschine und eines Trockners durch einen Kunden darstellt.

```json
{
  "ID": "1", 
  "product": [
    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
  ], 
  "timestamp": 1534219229
}
```

Beim Erstellen einer Datenansicht sind die folgenden Dimensionen und Metriken verfügbar (je nach Schema):

* **Dimensionen:**
   * ID
   * Produkt: SKU
   * Produkt: Name
   * Produkt: Bestell-ID
   * Produkt: Garantie: Gültigkeit
   * Produkt: Garantie: Länge
   * Produkt: Garantie: Name
   * Produkt: Garantie: Typ
* **Metriken:**
   * Produkt: Bestellungen
   * Produkt: Einheiten
   * Produkt: Umsatz
   * Produkt: Garantie
   * Produkt: Garantie: Umsatz

### Beispiele für dasselbe Ereignis (Reporting-Verhalten)

Unter Verwendung des obigen Ereignisses zeigen die folgenden Tabellen Workspace-Berichte mit einigen Dimensions- und Metrikkombinationen.

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

Customer Journey Analytics untersucht selektiv die Dimension und Metriken des Objekts basierend auf der Tabelle.

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
+      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
+      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
+      "name": "LG Dryer 2000", 
+      "orders": 1, 
+      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

Wenn Sie nur über Garantieumsätze berichten möchten, sieht Ihr Projekt in etwa wie folgt aus:

| `product : warranty : coverage` | `product : warranty : revenue` |
| --- | --- |
| `full coverage` | `200` |
| `extended` | `50` |
| `Total` | `250` |

Customer Journey Analytics untersucht diese Teile des Ereignisses, um den Bericht zu generieren:

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
+          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
+          "revenue": 200
+        }, 
+        {
+          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
+          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
+  ], 
+  "timestamp": 1534219229
+}
```

Da der Trockner keine Garantie hat, ist er nicht in der Tabelle enthalten.

Da Sie jede Dimension mit einer beliebigen Metrik kombinieren können, zeigt die folgende Tabelle, wie Daten mit nicht spezifizierten Dimensionselementen aussehen würden:

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

Eine Produktbestellung existiert ohne einen verknüpften Garantienamen. Daher wird das Dimensionselement „Nicht spezifiziert“ zugeschrieben. Dasselbe gilt auch für die Bestellung der Produktgarantie:

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
          "coverage": "full coverage", 
          "length": "2 year", 
+          "name": "LG 2000 standard", 
+          "orders": 1, 
          "revenue": 200
+        }, 
+        {
          "coverage": "extended", 
          "length": "1 year", 
+          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
+      "orders": 1, 
      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

Achten Sie auf die Bestellungen, die keinen mit ihnen verbundenen Namen haben. Dies sind die Bestellungen, die dem Dimensionselement „Nicht spezifiziert“ zugeordnet werden.

### Kombinieren von Metriken

Customer Journey Analytics kombiniert nativ keine ähnlich benannten Metriken, wenn sie sich auf verschiedenen Objektebenen befinden.

| `product : category` | `product : revenue` | `product : warranty : revenue` |
| --- | --- | --- |
| `Washing Machines` | `1600` | `250` |
| `Dryers` | `500` | `0` |
| `Total` | `2100` | `250` |

Sie können jedoch eine berechnete Metrik erstellen, die die gewünschten Metriken kombiniert:

Berechnete Metrik „Gesamtumsatz“: `[product : revenue] + [product : warranty : revenue]`

Durch Anwendung dieser berechneten Metrik werden die gewünschten Ergebnisse angezeigt:

| `product : warranty : name` | `Total revenue (calculated metric)` |
| --- | --- |
| `Washing Machines` | `1850` |
| `Dryers` | `500` |
| `Total` | `2350` |



## Einschränkungen

Einschränkungen gelten für Arrays in Daten, die von Customer Journey Analytics verwendet und als Teil eines Schemas in Experience Platform modelliert werden. Siehe [Datenmodellbeschränkungen](https://experienceleague.adobe.com/en/docs/experience-platform/profile/guardrails#data-model-limits) und [Datengrößenbeschränkungen](https://experienceleague.adobe.com/en/docs/experience-platform/profile/guardrails#data-size-limits) in den [Standardleitplanken für Echtzeit-Kundenprofildaten und -segmentierung](https://experienceleague.adobe.com/de/docs/experience-platform/profile/guardrails).

