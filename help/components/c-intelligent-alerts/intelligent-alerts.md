---
description: Informationen zu Warnhinweisen zur granularen Steuerung der Benachrichtigungen und Integration mit der Anomalieerkennung.
title: Warnhinweise – Überblick
feature: Workspace Basics
role: User, Admin
exl-id: 029be0c8-ec78-4bb7-a6cd-bb303b5ac82a
TQID: https://experienceleague.adobe.com/kXRxlgfo9-F6KyXQ590--TZOZcVqvHkZZGS6alcAC0E
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: a8b1c240-f315-46e3-b813-f545c4279dd1id: aff2ef09-fc60-4018-9197-e2befd623064id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: e4a0bad2-b448-47f1-9fa6-222ebdb3b5b0
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 478
ht-degree: 57%

---

# Überblick über Warnhinweise

Warnhinweise in Customer Journey Analytics ermöglichen es Ihnen, sich über geänderte Prozentsätze oder bestimmte Datenpunkte benachrichtigen zu lassen.

Je nach Customer Journey Analytics-Paket können Sie auch Warnhinweise verwenden, die basierend auf Schwellenwerten für Anomalien ausgelöst werden. Diese Warnhinweise (auch *intelligente Warnhinweise* genannt) bieten granulare Steuerelemente, die in die [Anomalieerkennung“ integriert sind ](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) ausgelöst werden, wenn Sie sie am meisten benötigen.

* Vorschau der Trigger eines Warnhinweises.
* Warnhinweise per E-Mail oder SMS mit Links zu automatisch erstellten Projekten in Analysis Workspace verschicken.
* Erstellen *gestapelten* Warnhinweisen, die mehrere Metriken in einem Warnhinweis erfassen.
* Erstellen von Warnhinweisen basierend auf:
   * Anomalien in Metriken, die vorhanden sind, über oder unter den erwarteten Schwellenwerten liegen.

     [Anomalieerkennung](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) erstellt anhand historischer Daten einen erwarteten Wert plus eine obere und untere Grenze. Wenn der tatsächliche Metrikwert über die Obergrenze oder unter die Untergrenze, die als Schwellenwert definiert ist, fällt, wird dieses Ereignis als Anomalie auf der Konfidenzschwelle des Schwellenwerts betrachtet und führt zum Trigger des Warnhinweises. Ein höherer Schwellenwert (z. B.: 99 % oder 99,9 %) bedeutet eine breitere Bandbreite, was zu weniger Warnungen führt, die durch extremere Anomalien verursacht werden. Ein niedrigerer Schwellenwert (z. B.: 90 %) bedeutet eine engere Bandbreite, was zu mehr Warnungen führt, die durch weniger extreme Anomalien verursacht werden.
   * Änderungen an Metriken um einen bestimmten Prozentsatz.
   * Metriken, die über, unter oder gleich einem bestimmten Wert sind. (nur für Adobe Analytics-Kunden mit einem Select-, Prime- oder Ultimate-Paket verfügbar)

Dieses [Video-Tutorial](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/data-science/intelligent-alerts) bietet einen grundlegenden Überblick über Warnhinweise.



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
