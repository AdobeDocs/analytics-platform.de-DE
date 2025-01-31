---
description: Die Zeileneinstellungen variieren je nachdem, welche Komponente Sie in die Tabelle gezogen haben.
title: Zeileneinstellungen
feature: Visualizations
exl-id: a9438d83-498d-4b22-9e5e-c357bd3a2680
role: User
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: tm+mt
source-wordcount: '1026'
ht-degree: 14%

---

# Zeileneinstellungen


>[!BEGINSHADEBOX]

Siehe ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Zeilen- und Spalteneinstellungen in einer Freiformtabelle](https://video.tv.adobe.com/v/40382/?quality=12&learn=on){target="_blank"} für ein Demovideo.

>[!ENDSHADEBOX]

Die Zeileneinstellungen variieren je nachdem, welche Komponente Sie in die Tabelle gezogen haben. Um auf die Einstellungen der Tabellenzeilen zuzugreifen![ wählen Sie ](/help/assets/icons/Setting.svg)Einstellung **[!UICONTROL Einstellungen]** neben einer Dimension, einem Filter, einer Metrik, einem Zeitraum oder einer Aufschlüsselung in jedem dieser Objekte aus.

![Freiformtabelle mit hervorgehobenem Einstellungssymbol für Metriken](assets/row-settings.png)

| Einstellung | Beschreibung |
| --- | --- |
| **[!UICONTROL Aufschlüsselung nach Position]** | Standardmäßig ist diese Einstellung deaktiviert und die Aufschlüsselungen sind auf statische Zeilenelemente festgelegt. Angenommen, Sie schlüsseln die drei wichtigsten Dimensionselemente der Seite (Homepage, Suchergebnisse, Checkout) nach Marketing-Kanal auf. Dann verlassen Sie das Projekt und kehren zwei Wochen später zurück. Beim erneuten Öffnen des Projekts haben sich die drei oberen Seiten geändert, und jetzt sind Startseite, Suchergebnisse und Checkout stattdessen die oberen Seiten vier bis sechs. Standardmäßig werden Ihre Aufschlüsselungen des Marketing-Kanals weiterhin unter Startseite, Suchergebnisse und Checkout angezeigt, auch wenn sie sich jetzt in den Zeilen 4-6 befinden. <br> Im Gegensatz dazu werden bei einer **Aufschlüsselung nach Position** immer die drei obersten Elemente aufgeschlüsselt, unabhängig davon, worum es sich bei ihnen handelt. Wenn Sie auf das Beispiel zurückgreifen, werden die Aufschlüsselungen des Marketing-Kanals beim erneuten Öffnen des Projekts an die drei obersten Seiten der Tabelle gebunden. Und nicht zu Homepage, Suchergebnissen und Checkout, die sich jetzt in den Zeilen 4-6 befinden. |
| **[!UICONTROL Prozentsätze]** | **Prozentsätze nach Spalte berechnen** (Standard): Die in einer Zelle sichtbaren Prozentsätze werden auf der Grundlage der Spaltensumme berechnet. <br>**Prozentsätze nach Zeile berechnen**: Die Prozentsätze in den Zellen werden über die Zeile hinweg berechnet, im Gegensatz zur Spalte nach unten, mit einem Gesamtwert als Nenner. Diese Berechnung ist für Trend-Prozentsätze nützlich. |
| **[!UICONTROL Spaltensummen]** | Diese Einstellungen sind nur für [statische Zeilen](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) verfügbar. <br> **Als Summe der aktuellen Zeilen anzeigen** zeigt eine Client-seitige Summe der Zeilen in der Tabelle an, was bedeutet, dass die Summe *Metriken wie Besuche oder Personen* dedupliziert. <br> **Gesamtsumme anzeigen** Zeigt eine Server-seitige Summe an, d. h. die Gesamtzahl der deduplizierten Metriken. |

## Ändern der Zeilenanzahl

So ändern Sie die Anzahl der angezeigten Zeilen:

1. Klicken Sie auf die Zahl neben **[!UICONTROL Zeilen]** oben in der ersten Spalte der Tabelle.

   ![Freiformtabelle mit der Dropdown-Liste der für die Anzahl der angezeigten Zeilen. 400 Zeilen sind ausgewählt.](assets/change-row-count.gif)

1. Wählen Sie aus der Dropdown-Liste die Anzahl der Zeilen aus, die die Tabelle anzeigen soll.


## Kontextmenü

Die folgenden Kontextmenüoptionen sind bei der Auswahl der Dimensionskopfzeile verfügbar.

| Option | Beschreibung |
| --- | --- |
| **[!UICONTROL Auswahl in Zwischenablage kopieren]** | Kopieren Sie die Auswahl aus der Visualisierung in die Zwischenablage. |
| **[!UICONTROL Objekte als CSV herunterladen (*Dimensionsname*)]** | Laden Sie sofort die Dimensionselemente (bis zu maximal 50.000) der Visualisierung auf Ihr lokales Gerät herunter. Maximal 50.000 Dimensionselemente für die ausgewählte Dimension. |
| **[!UICONTROL Auswahl als CSV herunterladen]** | Laden Sie die Dimensionselemente der Visualisierung sofort auf Ihr lokales Gerät herunter. |
| **[!UICONTROL Erstellen eines Hyperlinks für alle Dimensionselemente]** | Erstellen Sie Hyperlinks für alle Dimensionselemente. Siehe [Hyperlinks für Dimensionen in einer Freiformtabelle](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Link für alle Dimensionselemente bearbeiten]** | Hyperlinks für alle Dimensionselemente bearbeiten. Siehe [Hyperlinks für Dimensionen in einer Freiformtabelle](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Hyperlink für alle Dimensionselemente entfernen]** | Entfernen Sie Hyperlinks für alle Dimensionselemente. Siehe [Hyperlinks für Dimensionen in einer Freiformtabelle](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Löschen]** | Löscht die Dimension aus der Tabelle. |
| **[!UICONTROL Visualisieren]** | Visualisieren Sie die Dimension mithilfe einer der verfügbaren Visualisierungen. |
| **[!UICONTROL Nur ausgewählte Zeilen anzeigen]** | Nur ausgewählte Elemente in der Visualisierung anzeigen. |
| **[!UICONTROL Anmerkung aus Auswahl erstellen]** | Öffnen Sie die **[!UICONTROL Anmerkungsdetails]**, um eine Anmerkung hinzuzufügen. |


Die folgenden zusätzlichen Optionen im Kontextmenü sind verfügbar, wenn ein oder mehrere Dimensionselemente (erste Spalte) oder eine oder mehrere einzelne Zellen in der Freiformtabelle ausgewählt werden.

| Option | Beschreibung |
| --- | --- |
| **[!UICONTROL Erstellen eines Hyperlinks]** | Erstellen Sie einen Hyperlink für das Element. Siehe [Hyperlinks für Dimensionen in einer Freiformtabelle](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Hyperlink bearbeiten]** | Bearbeiten Sie einen Hyperlink für das Element. Siehe [Hyperlinks für Dimensionen in einer Freiformtabelle](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Hyperlink entfernen]** | Entfernen Sie einen Hyperlink für das Element. Siehe [Hyperlinks für Dimensionen in einer Freiformtabelle](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Aufschlüsselung]** | Schlüsseln Sie das Dimensionselement auf. Wählen Sie aus der Liste von **[!UICONTROL Dimensionen]**, **[!UICONTROL Metriken]**, **[!UICONTROL Filtern]** oder **[!UICONTROL Datumsbereichen]**. Alternative Suche nach einer Komponente mit *Suche*. |
| **[!UICONTROL Ausgewählte löschen]** | Löscht die ausgewählten Zeilen (Elemente). |
| **[!UICONTROL Trendauswahl]** | Erstellen Sie eine Trend-Liniendiagramm-Visualisierung für die Auswahl. |
| **[!UICONTROL Nur ausgewählte Zeilen anzeigen]** | Nur ausgewählte Zeilen in der Visualisierung anzeigen. |
| **[!UICONTROL Alle Zeilen anzeigen]** | Zeigt alle Zeilen in der Visualisierung an. |
| **[!UICONTROL Filter aus Auswahl erstellen]** | Öffnen Sie den **[!UICONTROL Filter-Builder]**, um einen Filter aus der Auswahl zu erstellen. |
| **[!UICONTROL Zielgruppe aus Auswahl erstellen]** | Öffnen Sie das Dialogfeld **[!UICONTROL Zielgruppe erstellen]**, um eine Zielgruppe aus der Auswahl zu erstellen. |

Die folgenden zusätzlichen Optionen im Kontextmenü sind bei der Auswahl einer Metrik -Spaltenüberschrift verfügbar.

| Option | Beschreibung |
|---|---|
| **[!UICONTROL Metrik aus Auswahl erstellen]** | Erstellen Sie eine neue Metrik aus der ausgewählten Metrik. Metrik kann „Mittel“, „Medien“, „Spalte max“, „Spalte min“ oder „Spaltensumme“ sein. Sie können auch Im Generator für berechnete Metriken öffnen auswählen, um eine berechnete Metrik zu erstellen. |
| **[!UICONTROL Spalte mit Zeitraum hinzufügen]** | Fügen Sie eine Zeitraumspalte hinzu. Es werden mehrere Optionen angeboten, wobei der Kalenderbereich des Bedienfelds den *Datumsbereich“*: <li>**[!UICONTROL Vorheriger *Datumsbereich* zu diesem Datumsbereich]**</li><li>**[!UICONTROL Diese *Datumsbereich* auf diesen Datumsbereich]**.</li><li>**[!UICONTROL Benutzerdefinierter Datumsbereich für diesen Datumsbereich]**. Öffnet den **[!UICONTROL Generator für Datumsbereiche]** um den Datumsbereich anzugeben.</li>Weitere Informationen finden [ unter ](/help/components/date-ranges/time-comparison.md)Datumsvergleich“. |
| **[!UICONTROL Zeiträume vergleichen]** | Fügt Vergleichszeitraumspalten hinzu. Nur verfügbar, wenn die Dimension nicht auf der Zeit basiert. Ihnen stehen mehrere Optionen zur Verfügung, die den *Datumsbereich* bestimmen: <li>**[!UICONTROL Vorheriger *Datumsbereich* zu diesem Datumsbereich]**</li><li>**[!UICONTROL Benutzerdefinierter Datumsbereich für diesen Datumsbereich]**. Öffnet den **[!UICONTROL Generator für Datumsbereiche]** um den Datumsbereich anzugeben.</li>Weitere Informationen finden [ unter ](/help/components/date-ranges/time-comparison.md)Datumsvergleich“. |
| **[!UICONTROL Attributionsmodelle ändern]** | Ändern Sie das Attributionsmodell für die Spalte . |
| **[!UICONTROL Attributionsmodell vergleichen]** | Geben Sie ein neues Attributionsmodell an und vergleichen Sie es mit dem Attributionsmodell für die ausgewählte Spalte. Mit den neuen Attributionsmodell-Metriken wird eine neue Spalte hinzugefügt. Außerdem wird eine Spalte für die prozentuale Änderung zum Vergleich hinzugefügt. |
| **[!UICONTROL Spaltenbreiten zurücksetzen]** | Spaltenbreiten auf die Standardbreite zurücksetzen. |
| **[!UICONTROL Anmerkung aus Auswahl erstellen]** | Öffnen Sie die **[!UICONTROL Anmerkungsdetails]**, um eine Anmerkung hinzuzufügen. |
| **[!UICONTROL Filter aus Auswahl erstellen]** | Öffnen Sie den **[!UICONTROL Filter-Builder]**, um einen Filter aus der Auswahl zu erstellen. |
| **[!UICONTROL Zielgruppe aus Auswahl erstellen]** | Öffnen Sie das Dialogfeld **[!UICONTROL Zielgruppe erstellen]**, um eine Zielgruppe aus der Auswahl zu erstellen. |
