---
description: Warnhinweise ermöglichen eine granulare Steuerung der Benachrichtigungen und eine Integration mit der Anomalieerkennung.
title: Überblick über Warnhinweise
feature: Workspace Basics
role: User, Admin
exl-id: 029be0c8-ec78-4bb7-a6cd-bb303b5ac82a
source-git-commit: daa07b603caa613ca49b61c2e8e461d558459f57
workflow-type: ht
source-wordcount: '359'
ht-degree: 100%

---

# Überblick über Warnhinweise

Warnhinweise in Customer Journey Analytics ermöglichen es Ihnen, sich über geänderte Prozentsätze oder bestimmte Datenpunkte benachrichtigen zu lassen.

Je nach Customer Journey Analytics-Paket können Sie auch Warnhinweise verwenden, die basierend auf Schwellenwerten für Anomalien ausgelöst werden. Diese Warnhinweise (auch als „intelligente Warnhinweise“ bezeichnet) bieten granulare Steuerelemente, die mit der [Anomalieerkennung](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) integriert sind und ausgelöst werden, wenn Sie sie am dringendsten benötigen.

Mithilfe von Warnhinweisen können Sie:

* In einer Vorschau anzeigen, wie oft ein Warnhinweis ausgelöst wird
* Warnhinweise per E-Mail oder SMS mit Links zu automatisch erstellten Projekten in Analysis Workspace verschicken
* „Gestapelte“ Warnhinweise erstellen, die mehrere Metriken in einem Warnhinweis vereinen
* Warnhinweise basierend auf Anomalien erstellen (Schwellenwerte von 90 %, 95 %, 99 %, 99,75 % und 99,9 %; prozentuale Veränderung; über/unter) (nur für Adobe Analytics-Kundschaft mit einem Select-, Prime- oder Ultimate-Paket verfügbar)

Das folgende Video-Tutorial bietet einen grundlegenden Überblick über Warnhinweise: [Warnhinweise](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=de) (5:34)

## Informationen zu den Unterschieden zwischen Warnhinweisen in Customer Journey Analytics und Adobe Analytics

Die Verwendung von Warnhinweisen in Customer Journey Analytics ist nahezu identisch mit der Verwendung von Warnhinweisen in Adobe Analytics. Es gibt jedoch wichtige Unterschiede.

Weitere Informationen finden Sie unter [Warnhinweise – Funktionsvergleich: Customer Journey Analytics und Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).

## Anomalie-Suche nach Warnungen

>[!NOTE]
>
>Die Verwendung von Warnhinweisen mit Anomalieerkennung (auch als _intelligente Warnhinweise_ bezeichnet) ist nur für Organisationen mit einem Customer Journey Analytics Select-, Prime- oder Ultimate-Paket verfügbar.

Wenn ein Warnhinweis eine Anomalieerkennung verwendet, hängt der Trainings-Zeitraum von der für den Warnhinweis ausgewählten Granularität ab.

* Monatliche Granularität: 15 Monate + derselbe Bereich im letzten Jahr
* Wöchentliche Granularität: 15 Wochen + derselbe Bereich im letzten Jahr
* Tägliche Granularität: 35 Tage + derselbe Bereich im letzten Jahr
* Stündliche Granularität: 336 Stunden

Weitere Informationen finden Sie unter [In der Anomalieerkennung verwendete statistische Verfahren](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Erstellen von Warnhinweisen

Informationen zum Erstellen von Warnhinweisen in Customer Journey Analytics finden Sie unter [Erstellen von Warnhinweisen](/help/components/c-intelligent-alerts/alert-builder.md).

>[!IMPORTANT]
>
>Die Verwendung von Zeitstempeldaten zur Erstellung von Warnhinweisen kann dazu führen, dass Warnhinweise falsch ausgelöst werden. Adobe empfiehlt die Verwendung von Daten ohne Zeitstempel für Warnhinweise.

## Verwalten von Warnhinweisen

Sie können vorhandene Warnhinweise im Warnhinweis-Manager verwalten. Sie können verschiedene Verwaltungsaufgaben für Warnhinweise ausführen, z. B. Tagging, Umbenennen, Löschen und mehr.

Weitere Informationen zum Verwalten vorhandener Warnhinweise in Customer Journey Analytics finden Sie unter [Verwalten von Warnhinweisen](/help/components/c-intelligent-alerts/alert-manager.md).
