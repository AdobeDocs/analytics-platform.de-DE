---
description: Erfahren Sie mehr über bekannte Einschränkungen in Adobe Analysis Workspace und den zugehörigen Komponenten.
title: Bekannte Einschränkungen in Analysis Workspace
feature: FAQ
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: ht
source-wordcount: '313'
ht-degree: 100%

---

# Bekannte Einschränkungen in Analysis Workspace

Im Folgenden finden Sie eine Liste der bekannten Einschränkungen in Analysis Workspace und der zugehörigen Komponenten:

## Tabellen

* Datumsvergleichsspalten können nicht hinzugefügt werden, wenn Datumsbereiche oder Metriken als Tabellenzeilen verwendet werden.
* „Metrik aus Auswahl erstellen“ ist deaktiviert, wenn Segmente als Zeilen einer Tabelle verwendet werden. Darüber hinaus sollte die Option „Metrik aus Auswahl erstellen“ nicht auf datumsorientierte Spalten angewendet werden.
* Bedingte Formatierung für Aufschlüsselungszeilen kann keine benutzerdefinierten Bereiche verwenden.
* Tabellengesamtzeilen können nicht als Trend-Ansicht dargestellt werden, wenn die Einstellung für die Berechnung der Summen durch Addition der Zeilenwerte angewendet wird (üblicherweise bei statischen Zeilenelementen).

## Visualisierungen

* Visualisierungen, die Segmente nutzen, wie [!UICONTROL Fallout], [!UICONTROL Fluss], [!UICONTROL Kohorte] und [!UICONTROL Histogramm], können keine berechneten Metriken als Eingaben akzeptieren.
* [!UICONTROL Fluss]: Einstiegs-/Ausstiegsdimensionen, z. B. [!UICONTROL Entrypage], können nicht im Fluss verwendet werden.
* [!UICONTROL Kohorte]: Nur Ganzzahlen können als Kohortenkriterien verwendet werden.

## Segmente

* Bestimmte Metriken und Dimensionen können nicht segmentiert werden, wie etwa [!UICONTROL Ereignisse], [!UICONTROL Personen] usw.
* Die im [Ablegebereich des Panels](/help/analysis-workspace/c-panels/panels.md) erstellten Ad-hoc-Segmente sind eine Art Schnellsegment. Sie werden nicht im linken Panel von Workspace oder im Segment-Manager angezeigt, es sei denn, sie werden veröffentlicht. Weitere Informationen finden Sie unter [Schnellsegmente](/help/components/segments/seg-quick.md).

## Berechnete Metriken

* Berechnete Metriken können in bestimmten Visualisierungen nicht verwendet werden. Siehe [Visualisierungen](#visualizations).
* Berechnete Metriken können nicht im Bereich [!UICONTROL Attribution] verwendet werden, da berechnete Metriken selbst separate Attributionsmodelle enthalten können.
* Bestimmte Komponenten und Operatoren sind nicht verfügbar, wenn eine berechnete Metrik aus Workspace erstellt wird (im Gegensatz zu [!UICONTROL Komponenten > Segmente]). Beispiel: [!UICONTROL IP-Adresse].

## Datumsbereiche

* Benutzerdefinierte Datumsbereiche werden nicht unterstützt [!UICONTROL Dieser Tag im letzten Jahr], [!UICONTROL Dieser Tag im letzten Monat] usw.


## Berichtseinstellungen

* Einige der Einstellungen auf der Seite [!UICONTROL Berichtseinstellungen] gelten nicht. Analysis Workspace verwendet nur die [!UICONTROL Einstellungen für Sprache/Währung/Kodierung] am unteren Rand: [!UICONTROL Tausendertrennzeichen], [!UICONTROL Kodierung des terminierten Berichts] und [!UICONTROL CSV-Trennzeichen].

