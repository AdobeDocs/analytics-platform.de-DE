---
description: Informationen zu Warnhinweisen zur granularen Steuerung der Benachrichtigungen und Integration mit der Anomalieerkennung.
title: Warnhinweise – Überblick
feature: Workspace Basics
role: User, Admin
exl-id: 029be0c8-ec78-4bb7-a6cd-bb303b5ac82a
source-git-commit: 65e46a5d2a6759dd83b24bba2d1d4ee283b907c9
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 58%

---

# Überblick über Warnhinweise

Warnhinweise in Customer Journey Analytics ermöglichen es Ihnen, sich über geänderte Prozentsätze oder bestimmte Datenpunkte benachrichtigen zu lassen.

Je nach Customer Journey Analytics-Paket können Sie auch Warnhinweise verwenden, die basierend auf Schwellenwerten für Anomalien ausgelöst werden. Diese Warnhinweise (auch *intelligente Warnhinweise* genannt) bieten granulare Steuerelemente, die in die [Anomalieerkennung“ integriert sind &#x200B;](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) ausgelöst werden, wenn Sie sie am meisten benötigen.

* Vorschau der Trigger eines Warnhinweises.
* Warnhinweise per E-Mail oder SMS mit Links zu automatisch erstellten Projekten in Analysis Workspace verschicken.
* Erstellen *gestapelten* Warnhinweisen, die mehrere Metriken in einem Warnhinweis erfassen.
* Erstellen von Warnhinweisen basierend auf:
   * Anomalien in Metriken, die vorhanden sind, über oder unter den erwarteten Schwellenwerten liegen.

     [Anomalieerkennung](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) erstellt anhand historischer Daten einen erwarteten Wert plus eine obere und untere Grenze. Wenn der tatsächliche Metrikwert über die Obergrenze oder unter die Untergrenze, die als Schwellenwert definiert ist, fällt, wird dieses Ereignis als Anomalie auf der Konfidenzschwelle des Schwellenwerts betrachtet und führt zum Trigger des Warnhinweises. Ein höherer Schwellenwert (z. B.: 99 % oder 99,9 %) bedeutet eine breitere Bandbreite, was zu weniger Warnungen führt, die durch extremere Anomalien verursacht werden. Ein niedrigerer Schwellenwert (z. B.: 90 %) bedeutet eine engere Bandbreite, was zu mehr Warnungen führt, die durch weniger extreme Anomalien verursacht werden.
   * Änderungen an Metriken um einen bestimmten Prozentsatz.
   * Metriken, die über, unter oder gleich einem bestimmten Wert sind. (nur für Adobe Analytics-Kunden mit einem Select-, Prime- oder Ultimate-Paket verfügbar)

Dieses [Video-Tutorial](https://experienceleague.adobe.com/de/docs/analytics-learn/tutorials/data-science/intelligent-alerts) bietet einen grundlegenden Überblick über Warnhinweise.



## Informationen zu Unterschieden bei Warnhinweisen

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
