---
description: Zeigt Beispiele für berechnete Metriken.
title: Beispiele für berechnete Metriken
feature: Calculated Metrics
exl-id: 5e73ab52-627a-4064-bfb7-354c0ba1e4ee
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 5%

---

# Beispiele für berechnete Metriken

Dieser Artikel zeigt Beispiele zum Definieren erweiterter berechneter Metriken.

## Absprungrate

Sie möchten die Absprungrate berechnen.

+++ Details

Die Definition eines Bounces ist Thema einer anderen Diskussion, aber in diesem Beispiel definieren Sie einen Filter für unzustellbare Ereignisse, bei dem Sitzungsbeginn gleich 1 und Sitzungsende gleich 1 ist. Mit diesem Filter definieren Sie die Rate der nicht zugestellten Sitzungen für Sitzungen.


### Filter

![Bounce-Ereignisse](assets/example-bounce-bouncedevents.png)

### Berechnete Metrik

![Absprungrate](assets/example-bounce-rate.png)


### Abgeleitete Felder

Alternativ können Sie eine [Absprungrate“ mithilfe abgeleiteter Felder ](/help/data-views/derived-fields/derived-fields.md#bounces).

Abgeleitete Felder sind Teil einer Datenansicht, was den Vorteil hat, dass nicht jeder Benutzer die Definition einer Metrik für die Absprungrate überschreiben oder ändern kann. Dieser Vorteil führte auch zu einer Einschränkung. Benutzende, die keinen Zugriff auf eine Datenansicht haben, können keine abgeleiteten Felder verwenden und müssen auf Filter und berechnete Metriken zurückgreifen, um eine Absprungrate zu definieren.

Weitere Hintergrundinformationen zur Berechnung von Bounces und Bounce-Raten in Customer Journey Analytics finden Sie in diesem [Blogpost](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446).

+++


## Bedingte Seitenansichten

Sie möchten eine berechnete Metrik definieren, die nur die Seitenansichten der Seiten berechnet, die in über 100 Sitzungen besucht wurden.

+++ Details

![Bedingte Seitenansichten](assets/conditional-page-views.png)

+++

## Seitenansichten für die 30 % wichtigsten Sitzungen

Sie möchten eine berechnete Metrik definieren, die nur die Seitenansichten für die wichtigsten 30 % Sitzungen berechnet.

+++ Details

![Top 30 % Seitenansichten](assets/top30-page-views.png)

+++
