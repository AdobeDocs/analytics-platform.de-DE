---
description: Zeigt Beispiele für berechnete Metriken an.
title: Beispiele für berechnete Metriken
feature: Calculated Metrics
exl-id: 5e73ab52-627a-4064-bfb7-354c0ba1e4ee
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 5%

---

# Beispiele für berechnete Metriken

Dieser Artikel zeigt Beispiele für die Definition erweiterter berechneter Metriken.

## Absprungrate

Sie möchten die Absprungrate berechnen.

+++ Details

Die Definition eines Bounce dient einer weiteren Diskussion. In diesem Beispiel definieren Sie jedoch einen Filter für Bounce-Ereignisse, bei dem der Sitzungsstart gleich 1 und der Sitzungsende gleich 1 ist. Sie verwenden diesen Filter, um die Rate von nicht beendeten Sitzungen zu Sitzungen zu definieren.


### Filter

![Bounce-Ereignisse](assets/example-bounce-bouncedevents.png)

### Berechnete Metrik

![Absprungrate](assets/example-bounce-rate.png)


### Abgeleitete Felder

Alternativ können Sie eine [Absprungrate mithilfe abgeleiteter Felder](/help/data-views/derived-fields/derived-fields.md#bounces) definieren.

Abgeleitete Felder sind Teil einer Datenansicht, die den Vorteil hat, dass nicht jeder Benutzer die Definition einer Absprungratenmetrik überschreiben oder ändern kann. Dieser Vorteil führte auch zu einer Einschränkung. Benutzer, die keinen Zugriff auf eine Datenansicht haben, können keine abgeleiteten Felder verwenden und müssen Filter und berechnete Metriken verwenden, um eine Absprungrate zu definieren.

Weitere Hintergrundinformationen zur Berechnung von Absprüngen und Absprungraten in Customer Journey Analytics finden Sie in diesem [Blogpost](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446).

+++


## Bedingte Seitenansichten

Sie möchten eine berechnete Metrik definieren, die nur Seitenansichten für die Seiten berechnet, die in über 100 Sitzungen besucht wurden.

+++ Details

![ Bedingte Seitenansichten](assets/conditional-page-views.png)

+++

## Seitenansichten für die 30 % wichtigsten Sitzungen

Sie möchten eine berechnete Metrik definieren, die nur Seitenansichten für die 30 % wichtigsten Sitzungen berechnet.

+++ Details

![Die 30 % häufigsten Seitenansichten](assets/top30-page-views.png)

+++
