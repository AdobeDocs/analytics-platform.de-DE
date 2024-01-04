---
description: Die Zeileneinstellungen variieren je nachdem, welche Komponente Sie in die Tabelle gezogen haben.
title: Zeileneinstellungen
feature: Visualizations
exl-id: a9438d83-498d-4b22-9e5e-c357bd3a2680
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 88%

---

# Zeileneinstellungen

Sehen Sie sich hier ein Video zu Zeilen- und Spalteneinstellungen an:

>[!VIDEO](https://video.tv.adobe.com/v/40382/?quality=12)

Die Zeileneinstellungen variieren je nachdem, welche Komponente Sie in die Tabelle gezogen haben. Um auf die Einstellungen der Tabellenzeilen zuzugreifen, klicken Sie auf das Symbol [!UICONTROL Einstellungen] neben einer Dimension, einem Filter, einer Metrik, einem Zeitraum oder einer Aufschlüsselung im jeweiligen Element:

![Freiformtabelle, in der das Einstellungssymbol für Metriken hervorgehoben wird](assets/row-settings.png)

| Einstellung | Beschreibung |
| --- | --- |
| Datum ausrichten | Mit dieser Einstellung auf Tabellenebene können Sie die Daten in allen Spalten so ausrichten, dass sie alle in derselben Zeile beginnen. Die Datumsausrichtung ist standardmäßig aktiviert, wenn eine Zeitdimension in den Tabellenzeilen verwendet wird und unterschiedliche Datumsbereiche in den Spalten angewendet werden. In einer täglichen Tabelle, bei der Oktober und September auf die Spalten angewendet werden, beginnt beispielsweise die linke Spalte mit dem 1. Oktober und die rechte Spalte mit dem 1. September. |
| Aufschlüsselung nach Position | Standardmäßig ist diese Einstellung deaktiviert und die Aufschlüsselungen sind auf statische Zeilenelemente festgelegt. Angenommen, Sie schlüsseln die drei oberen Elemente der Dimension „Seite“ (Startseite, Suchergebnisse, Checkout) nach Marketing-Kanälen auf. Dann verlassen Sie das Projekt und kehren zwei Wochen später zurück. Beim erneuten Öffnen des Projekts haben sich die drei oberen Seiten geändert, und jetzt sind Startseite, Suchergebnisse und Checkout stattdessen die oberen Seiten vier bis sechs. Standardmäßig werden Ihre Marketing-Kanal-Aufschlüsselungen weiterhin unter Startseite, Suchergebnisse und Checkout angezeigt, auch wenn sie sich jetzt in den Zeilen 4-6 befinden. <br> Im Gegensatz dazu werden bei einer **Aufschlüsselung nach Position** immer die drei obersten Elemente aufgeschlüsselt, unabhängig davon, worum es sich bei ihnen handelt. Um auf unser Beispiel zurückzukommen: Wenn Sie Ihr Projekt erneut öffnen, werden die Aufschlüsselungen der Marketing-Kanäle an die ersten 3 Seiten in der Tabelle gebunden, nicht an  Startseite, Suchergebnisse und Checkout, die sich jetzt in den Zeilen 4-6 befinden. |
| Prozentsatz | **Prozentsätze pro Spalte berechnen**: Ist die Standardeinstellung. Die in einer Spalte sichtbaren Prozentsätze werden auf der Grundlage der Spaltensumme berechnet. <br>**Prozentsätze pro Zeile berechnen**: Erzwingt, dass in der Freiform-Tabelle die Zellprozentsätze über die Zeile anstatt für die Spalte berechnet werden. Dabei sit die Gesamtsumme der Nenner. Dies ist besonders nützlich für die Trend-Darstellung von Prozentangaben. Diese Einstellung ist standardmäßig aktiviert, wenn Sie das Symbol „Visualisieren“ verwenden. |
| Spaltensummen | Diese Einstellungen sind nur für [statische Zeilen](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) verfügbar. <br> **Als Summe der aktuellen Zeilen anzeigen** zeigt eine clientseitige Summe der Zeilen in der Tabelle an, was bedeutet, dass die Summe *not* Duplizieren Sie Metriken wie Besuche oder Personen. <br> **Gesamtsumme anzeigen**: Zeigt eine Server-seitige Summe an, d. h. die Gesamtsumme dedupliziert die Metriken. |

## Ändern der Zeilenanzahl

So ändern Sie die Anzahl der angezeigten Zeilen:

1. Klicken Sie auf die Zahl neben [!UICONTROL Zeilen] oberhalb der Tabelle.

   ![Freiformtabelle mit der Dropdown-Liste der angezeigten Zeilen. 400 Zeilen sind ausgewählt.](assets/row-number.png)

1. Wählen Sie aus der Dropdown-Liste die Anzahl der Zeilen aus, die die Tabelle anzeigen soll.