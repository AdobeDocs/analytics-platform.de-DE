---
title: Übersicht über berechnete Metriken
description: Erfahren Sie mehr über gefilterte Metriken, die zum Zeitpunkt der Berichtserstellung abgeleitet werden.
feature: Calculated Metrics
exl-id: c9205c95-8b01-4177-a89c-038886f41d3d
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 100%

---

# Übersicht über berechnete Metriken

Berechnete und erweiterte berechnete (abgeleitete) Metriken sind benutzerdefinierte Metriken, die Sie über vorhandene Metriken erstellen können. Mit unseren Tools für berechnete Metriken können Sie Metriken auf flexiblere Weise erstellen, verwalten und kuratieren. Damit können Marketing-Experten, Produktmanager und Analytiker Fragen zu den Daten beantworten, ohne die -Implementierung ändern zu müssen.

Sie können

* gefilterte Metriken erstellen, die zur Berichtslaufzeit abgeleitet werden, ohne die Implementierung ändern zu müssen. Diese Metriken können historisch angezeigt werden, da sie auf Filtern basieren.
* (Nur erweiterte berechnete Metriken) Filtern Sie nach Metriken. Sie können beispielsweise eine Metrik für „Neue Personen“ erstellen, mit der die Personen gezählt werden, für die dies die erste Sitzung ist.
* (Nur erweiterte berechnete Metriken) Statistische Funktionen miteinbeziehen, um Daten besser beschreiben zu können. Sie könnten beispielsweise die Elemente in einem Bericht zählen oder die Anzahl der Standardabweichungen für jedes Element addieren.

## Vergleich zwischen berechneten Metriken und erweiterten berechneten Metriken

Hier sehen Sie einen Vergleich zwischen den jeweiligen Möglichkeiten, die berechnete und erweiterte berechnete Metriken bieten:

| Generatoroptionen | Berechnete Metriken | Erweiterte berechnete (abgeleitete) Metriken |
|---|---|---|
| Formattypen (Dezimal, Zeit, Prozent, Währung) | Ja | Ja |
| Attributionsänderung (Standard, Linear, Teilnahme usw.) | Ja | Ja |
| Metriktypen (Standard, Total) | Ja | Ja |
| Grundrechenarten (Addieren, Subtrahieren, Multiplizieren, Dividieren) | Ja | Ja |
| Filter anwenden | Nein | Ja |
| [Allgemeine Funktionen (Zählen, Anzeigenwert, Mittel etc.)](/help/components/calc-metrics/cm-functions.md) | Nein | Ja |
| [Erweiterte Funktionen (Regression, Wenn-Dann, T-Transformation etc.)](/help/components/calc-metrics/cm-adv-functions.md) | Nein | Ja |

## Tools

| Tool | Funktionen |
|--- |--- |
| Generator für berechnete Metriken | <ul><li>Erstellen Sie einfache berechnete Metriken oder erweiterte berechnete Metriken mit erweiterten Zuordnungsmodellen.</li><li>Filter inline zu Metrik-Formeln hinzufügen.</li><li>Filter in einem Bericht vergleichen. So können Sie beispielsweise lokale Personen mit internationalen Personen vergleichen.</li><li>Statistische Funktionen verwenden.</li><li> Detaillierte Metrikbeschreibungen angeben (was die Metrik macht, wo sie verwendet werden sollte, wo sie NICHT verwendet werden sollte.)</li><li>Definitionen in neue Metriken kopieren.</li><li>Eine Inline-Metrikvorschau bereitstellen.</li><li>Die Metrikpolarität festlegen, die angibt, ob es gut oder schlecht ist, wenn ein bestimmtes benutzerspezifisches Ereignis (eine Metrik) steigt.</li><li>Metriken taggen.</li></ul> |
| Manager für berechnete Metriken | <ul><li>Metriken für andere freigeben.</li><li>Metriken genehmigen und kuratieren.</li><li>Metriken organisieren (taggen), damit sie von Benutzern gefunden werden können.</li><li>Metriken löschen.</li><li>Metriken umbenennen.</li></ul> |
| API für berechnete Metriken | Teil des Customer Journey Analytics API-Sets. |

## Vorlagen für berechnete Metriken in Customer Journey Analytics

| Name der berechneten Metrik | Beschreibung der berechneten Metrik |
| --- | --- |
| Sitzungen pro Person | Durchschnittliche Anzahl der Sitzungen pro Person |
| Startrate der Sitzung | Der Prozentsatz der Zeit, zu der ein Dimensionselement im ersten Ereignis einer Sitzung auftrat. |
| Endrate der Sitzung | Der Prozentsatz der Zeit, in der ein Dimensionselement im letzten Ereignis einer Sitzung auftrat. |
| Aufgewendete Zeit pro Person | Die durchschnittliche Zeit, die eine Person mit einem bestimmten Dimensionselement verbracht hat. |
| Aufgewendete Zeit pro Sitzung | Die durchschnittliche Zeit, die eine Person pro Sitzung mit einem bestimmten Dimensionselement verbracht hat. |
