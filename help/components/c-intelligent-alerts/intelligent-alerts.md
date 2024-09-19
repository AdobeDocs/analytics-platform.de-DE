---
description: Warnhinweise ermöglichen eine detaillierte Kontrolle der Benachrichtigungen und die Integration in die Anomalieerkennung.
title: Warnhinweise – Übersicht
feature: Workspace Basics
role: User, Admin
source-git-commit: def8b074ea468e409e340415d5e96f75d6b69312
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 28%

---

# Warnhinweise – Übersicht

Warnhinweise in Customer Journey Analytics ermöglichen es Ihnen, über geänderte Prozentsätze oder bestimmte Datenpunkte benachrichtigt zu werden.

Je nach Customer Journey Analytics-Package können Sie auch Warnhinweise verwenden, die basierend auf Anomalieschwellen ausgelöst werden. Diese Warnhinweise (auch als &quot;intelligente Warnhinweise&quot;bezeichnet) bieten granulare Steuerelemente, die in die [Anomalieerkennung](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) integriert sind und ausgelöst werden, wenn Sie sie am meisten benötigen.

Mit Warnhinweisen können Sie:

* In einer Vorschau anzeigen, wie oft ein Warnhinweis ausgelöst wird
* Warnhinweise per E-Mail oder SMS mit Links zu automatisch erstellten Projekten in Analysis Workspace verschicken
* „Gestapelte“ Warnhinweise erstellen, die mehrere Metriken in einem Warnhinweis vereinen.
* Warnhinweise erstellen, die auf Anomalien basieren (90-%-, 95-%-, 99-%-, 99,75-%- und 99,9-%-Schwellen, Änderungen in %, darüber/darunter) (nur für Customer Journey Analytics-Kunden mit einem Select-, Prime- oder Ultimate-Paket verfügbar)

Das folgende Video-Tutorial bietet einen grundlegenden Überblick über Warnungen: [Warnungen](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=de) (5:34)

## Erfahren Sie, wie sich Warnhinweise beim Customer Journey Analytics von Adobe Analytics unterscheiden

Die Verwendung von Warnhinweisen auf dem Customer Journey Analytics ist fast identisch mit der Verwendung von Warnhinweisen in Adobe Analytics. Es gibt jedoch wichtige Unterschiede.

Weitere Informationen finden Sie unter [Vergleich der Warnhinweise-Funktion: Customer Journey Analytics und Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).

## Anomalie-Suche nach Warnungen

>[!NOTE]
>
>Die Verwendung von Warnhinweisen mit Anomalieerkennung (auch _Intelligente Warnhinweise_ genannt) ist nur für Unternehmen mit einem Customer Journey Analytics Select-, Prime- oder Ultimate-Paket verfügbar.

Wenn ein Warnhinweis eine Anomalieerkennung verwendet, hängt der Trainings-Zeitraum von der für den Warnhinweis ausgewählten Granularität ab.

* Monatliche Granularität: 15 Monate + derselbe Bereich im letzten Jahr
* Wöchentliche Granularität: 15 Wochen + derselbe Bereich im letzten Jahr
* Tägliche Granularität: 35 Tage + derselbe Bereich im letzten Jahr
* Stündliche Granularität: 336 Stunden

Weitere Informationen finden Sie unter [Statistische Verfahren zur Anomalieerkennung](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Erstellen von Warnhinweisen

Informationen zum Erstellen von Warnhinweisen in Customer Journey Analytics finden Sie unter [Warnhinweise erstellen](/help/components/c-intelligent-alerts/alert-builder.md).

>[!IMPORTANT]
>
>Die Verwendung von Zeitstempeldaten zur Erstellung von Warnhinweisen kann dazu führen, dass Warnhinweise falsch ausgelöst werden. Adobe empfiehlt die Verwendung von Daten ohne Zeitstempel für Warnhinweise.

## Verwalten von Warnhinweisen

Sie können vorhandene Warnhinweise im Warnhinweis-Manager verwalten. Sie können verschiedene Verwaltungsaufgaben für Warnhinweise ausführen, z. B. Tagging, Umbenennen, Löschen usw.

Weitere Informationen zum Verwalten vorhandener Warnhinweise in Customer Journey Analytics finden Sie unter [Warnhinweise verwalten](/help/components/c-intelligent-alerts/alert-manager.md).

