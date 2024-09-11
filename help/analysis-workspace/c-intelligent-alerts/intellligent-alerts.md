---
description: Das neue System für intelligente Warnhinweise erlaubt eine feiner abgestufte Kontrolle über Warnhinweise und integriert die Anomalieerkennung in das Warnhinweissystem.
title: Übersicht über intelligente Warnhinweise
feature: Workspace Basics
role: User, Admin
source-git-commit: 74ad39f6ccc6436f7c8540b7d8b69b20b93d2b5c
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 56%

---

# Übersicht über intelligente Warnhinweise

{{release-limited-testing}}

Intelligente Warnhinweise (oder nur &quot;Warnhinweise&quot;) in Customer Journey Analytics ermöglichen es Ihnen, über anormale Ereignisse in Ihren Daten informiert zu werden.

Sie können festlegen, dass Warnhinweise auf der Grundlage von Schwellenwerten für Anomalien, geänderten Prozentsätzen oder spezifischen Datenpunkten ausgelöst werden. Warnhinweise bieten granulare Steuerelemente, die mit der [Anomalieerkennung](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) integriert werden und ausgelöst werden, wenn Sie sie am dringendsten benötigen.

Mithilfe intelligenter Warnhinweise können Sie:

* Warnhinweise erstellen, die auf Anomalien basieren (90-%-, 95-%-, 99-%-, 99,75-%- und 99,9-%-Schwellen, Änderungen in %, darüber/darunter)
* In einer Vorschau anzeigen, wie oft ein Warnhinweis ausgelöst wird
* Warnhinweise per E-Mail oder SMS mit Links zu automatisch erstellten Projekten in Analysis Workspace verschicken
* „Gestapelte“ Warnhinweise erstellen, die mehrere Metriken in einem Warnhinweis vereinen.

Das folgende Video-Tutorial bietet einen grundlegenden Überblick über Warnhinweise: [Intelligente Warnhinweise](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=de) (5:34)

## Erfahren Sie, wie sich Warnhinweise beim Customer Journey Analytics von Adobe Analytics unterscheiden

Die Verwendung intelligenter Warnhinweise in Customer Journey Analytics ist fast identisch mit der Verwendung intelligenter Warnhinweise in Adobe Analytics. Es gibt jedoch wichtige Unterschiede.

Weitere Informationen finden Sie unter [Funktionsvergleich für intelligente Warnhinweise: Customer Journey Analytics und Adobe Analytics](/help/analysis-workspace/c-intelligent-alerts/alerts-feature-comparison.md).

## Anomalie-Suche nach Warnungen

Wenn ein Warnhinweis eine Anomalieerkennung verwendet, hängt der Trainings-Zeitraum von der für den Warnhinweis ausgewählten Granularität ab.

* Monatliche Granularität: 15 Monate + derselbe Bereich im letzten Jahr
* Wöchentliche Granularität: 15 Wochen + derselbe Bereich im letzten Jahr
* Tägliche Granularität: 35 Tage + derselbe Bereich im letzten Jahr
* Stündliche Granularität: 336 Stunden

Weitere Informationen finden Sie unter [Statistische Verfahren zur Anomalieerkennung](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Erstellen von Warnhinweisen

Informationen zum Erstellen von Warnhinweisen in Customer Journey Analytics finden Sie unter [Warnhinweise erstellen](/help/analysis-workspace/c-intelligent-alerts/alert-builder.md).

>[!IMPORTANT]
>
>Die Verwendung von Zeitstempeldaten zur Erstellung von Warnhinweisen kann dazu führen, dass Warnhinweise falsch ausgelöst werden. Adobe empfiehlt die Verwendung von Daten ohne Zeitstempel für intelligente Warnhinweise.

## Verwalten von Warnhinweisen

Sie können vorhandene Warnhinweise im Warnhinweis-Manager verwalten. Sie können verschiedene Verwaltungsaufgaben für Warnhinweise ausführen, z. B. Tagging, Umbenennen, Löschen usw.

Weitere Informationen zum Verwalten vorhandener Warnhinweise in Customer Journey Analytics finden Sie unter [Warnhinweise verwalten](/help/analysis-workspace/c-intelligent-alerts/alert-manager.md).

