---
title: Best Practices für die Attribution
description: Machen Sie sich mit den Best Practices vertraut, um zu entscheiden, welches Attributionsmodell verwendet werden soll.
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
source-git-commit: 1b6e1d432bfe4b0574b8ee68bcfa940941f3c36f
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 66%

---

# Best Practices für die Attribution

Welches Attributionsmodells für Ihr Unternehmen am besten geeignet ist, hängt von einer Reihe von Überlegungen ab. In diesem Artikel werden eine Methodik und einige allgemeine Best Practices untersucht:

* [Explorative Analyse](#exploratory-analysis)
* [Regelbasierte Attributionen](#rule-base-attribution)
* [Algorithmische Attribution verwenden](#use-algorithmic-attribution)

## Explorative Analyse

>[!NOTE]
>Diese Analyse muss der Entscheidung für ein bestimmtes Attributionsmodell vorangehen.

In dieser vorbereitenden Phase geht es darum, ein Verständnis des Kundenverhaltens zu gewinnen und Konversionsmetriken zu bestimmen. Basierend auf der Konversionsmetrik erleichtern Tools wie [Daten-Feeds](https://experienceleague.adobe.com/de/docs/analytics/export/analytics-data-feed/data-feed-overview) (für Rohdaten) oder Analysis Workspace Ihr Verständnis von

* Anzahl der Kundinnen und Kunden, die vor der Konvertierung verschiedene Marketing-Kanäle nutzten
* Der Anteil/die Verteilung dieser Verhaltensweisen

Wenn beispielsweise 50 % der Kunden vor ihrer Konversion über drei Kanäle mit Ihnen in Kontakt kommen, besteht dann eine Interaktion zwischen diesen drei Kanälen?
Sie können dann eine Analyse des oberen und des unteren Ende des Trichters durchführen, um Ihr Verständnis zu erweitern.

### Analyse des oberen Ende des Trichters

Bei der Analyse des oberen Ende des Trichters werden diejenigen Kanäle untersucht, die zur Förderung der Marken- oder Produktwahrnehmung dienen. So zielen etwa TV-Werbespots in der Regel auf die Markenwahrnehmung ab. Hierfür empfiehlt sich das [Attributionsmodell des Zeitverfalls](/help/analysis-workspace/attribution/models.md) da Ihr TV-Werbespot im Zeitverlauf aus dem Gedächtnis Ihrer Zielgruppe verschwinden wird.

### Analyse des unteren Ende des Trichters

Bei der Analyse des unteren Trichters geht man davon aus, dass die Menschen bereits von Ihrer Marke wissen und Sie möchten, dass sie konvertieren. Verwenden Sie E-Mail- oder Push-Benachrichtigungen oder Facebook-Anzeigen.

## Regelbasierte Attribution

Dieser Schritt dient der Validierung Ihrer Hypothesen.

**Beispiel 1**

Angenommen, Ihre Hypothese lautet: &quot;*Mein Erstkontaktkanal hat eine größere Auswirkung auf die Konversion als mein Letztkontaktkanal.*&quot;

In diesem Fall würden Sie das [Umgekehrte J-förmige Attributionsmodell) verwenden](/help/analysis-workspace/attribution/models.md) um diese Hypothese zu testen. Dieses Modell schreibt dem ersten Kontaktpunkt (bzw. „Touchpoint“) eine Gewichtung von 60 % zu.

**Beispiel 2**

Angenommen, Ihre Hypothese lautet: *„In einer bestimmten Branche (z. B. der Reisebranche) beträgt das Attributionsfenster 60 oder 90 Tage, nicht 30 Tage, da Kunden viel recherchieren, bevor sie ein Produkt kaufen.*&quot;

In diesem Fall würden Sie Ihr [Lookback-Fenster](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/models) auf 90 Tage ändern.

## Algorithmische Attribution verwenden

Wenn Sie noch kein Attributionsmodell haben, das alle Ihre Fragen zufriedenstellend beantwortet, können Sie die [algorithmische Attribution](/help/analysis-workspace/attribution/algorithmic.md) verwenden. Da es sehr schwierig ist, eine große Anzahl möglicher Hypothesen und Kombinationen zu validieren, werden bei der algorithmischen Attribution integrierte Algorithmen verwendet, um auf die einzelnen Dimensionen Punkte zu verteilen.

## Weiter Überlegungen

* Möglicherweise sollten Sie ergänzend zu Analysis Workspace einen Datenwissenschaftler hinzuziehen.
* Sie können sich auf Rohdaten verlassen, wie in Daten-Feeds von Adobe.
* Erwägen Sie beispielsweise die Verwendung von [&#128279;](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-overview)Customer Journey Analytics), wenn Sie Ihre Impressionsdaten berücksichtigen möchten.
