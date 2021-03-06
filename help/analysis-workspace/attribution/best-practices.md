---
title: Best Practices für die Attribution
description: Welche Best Practices bestehen für die Wahl eines Attributionsmodells?
feature: Attribution
exl-id: d612dc79-24e4-4d50-bccd-dfb58328bd4e
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: ht
source-wordcount: '391'
ht-degree: 100%

---

# Best Practices für die Attribution

Welches Attributionsmodells für Ihr Unternehmen am besten geeignet ist, hängt von einer Reihe von Überlegungen ab. Dieser Artikel zeigt eine Methodik sowie einige allgemeine Best Practices auf.

## Schritt 1: Explorative Analyse

>[!NOTE]
>Diese Analyse muss der Entscheidung für ein bestimmtes Attributionsmodell vorangehen.

In dieser vorbereitenden Phase geht es darum, ein Verständnis des Kundenverhaltens zu gewinnen und Konversionsmetriken zu bestimmen. Basierend auf den Konversionsmetriken können Tools wie Analysis Workspace und das Abrufen von Datenquellen aus verschiedenen Kanälen (z.B. Daten zu Impressions) Ihr Verständnis für folgende Aspekte erleichtern:

* Wie viele Kunden haben jeweils Kontakt mit den einzelnen Marketing-Kanälen, bevor es zu ihrer Konversion kommt?
* Der Anteil/die Verteilung dieser Verhaltensweisen.

Wenn beispielsweise 50 % der Kunden vor ihrer Konversion über drei Kanäle mit Ihnen in Kontakt kommen, besteht dann eine Interaktion zwischen diesen drei Kanälen?
Sie können dann eine Analyse des oberen und des unteren Ende des Trichters durchführen, um Ihr Verständnis zu erweitern.

### Analyse des oberen Ende des Trichters

Bei der Analyse des oberen Ende des Trichters werden diejenigen Kanäle untersucht, die zur Förderung der Marken- oder Produkwahrnehmung dienen. So zielen etwa TV-Werbespots in der Regel auf die Markenwahrnehmung ab. Hierfür empfiehlt sich das [Attributionsmodell des Zeitverfalls](/help/analysis-workspace/attribution/models.md), da Ihr TV-Werbespot im Zeitverlauf aus dem Gedächtnis Ihrer Zielgruppe verschwinden wird.

### Analyse des unteren Ende des Trichters

Dieser Analyse liegt die Annahme zugrunde, dass Ihre Zielgruppe Ihre Marke bereits kennt und dass Sie versuchen, diese anhand bestimmter Methoden zur Konversion zu bringen. Dies geschieht über E-Mail- und Push-Benachrichtigungen oder etwa auch über Facebook-Anzeigen.

## Schritt 2: Regelbasierte Attribution

Dieser Schritt dient der Validierung Ihrer Hypothesen.

**Beispiel 1**

Angenommen, Ihre Hypothese lautet: „Mein für den Erstkontakt verwendeter Kanal hat größeren Einfluss auf die Konversion als mein für den Letztkontakt verwendeter“. In diesem Fall würden Sie das [Attributionsmodell Umgekehrt J-förmig](/help/analysis-workspace/attribution/models.md) anwenden, um diese Hypothese zu testen. Dieses Modell schreibt dem ersten Kontaktpunkt (bzw. „Touchpoint“) eine Gewichtung von 60 % zu.

**Beispiel 2**

Ihre Hypothese könnte lauten: „In unserer Branche (z. B. der Reisebranche) liegt das Attributionsfenster nicht bei 30, sondern bei 60 oder 90 Tagen, da Kunden vor dem Produktkauf intensive Recherchen vornehmen“. In diesem Fall würden Sie das [Lookback-Fenster](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=de#lookback-windows) entsprechend auf 90 Tage anpassen.

## Schritt 3: Algorithmische Attribution verwenden

Die Validierung einer großen Anzahl möglicher Hypothesen und Kombinationen ist mit einem enormen Aufwand verbunden. Diese komplexe Aufgabe können Sie mittels [algorithmischer Attribution](/help/analysis-workspace/attribution/algorithmic.md) jedoch auch von integrierten Algorithmen erledigen lassen. Sofern Sie bereits das Attributionsmodell ermittelt haben, das ihre Fragen allesamt beantwortet und perfekt zu Ihren Anforderungen passt, ist dieser Schritt logischerweise nicht vonnöten.

## Weiter Überlegungen

* Möglicherweise sollten Sie ergänzend zu Analysis Workspace einen Datenwissenschaftler hinzuziehen.
