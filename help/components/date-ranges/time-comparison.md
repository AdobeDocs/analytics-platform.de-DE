---
description: Mit dem Datumsvergleich in Analysis Workspace können Sie eine beliebige Spalte mit einem Datumsbereich verwenden und einen allgemeinen Datumsvergleich erstellen, z. B. Jahres-, Quartals- oder Monatsvergleich.
title: Datumsvergleich
feature: Calendar
exl-id: 08113536-658f-486b-ac56-6c531240c3c2
role: User
source-git-commit: 483c0d3bcc6ff700395a51a4d550844fb6af30d2
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 17%

---

# Datumsvergleich

Mit dem Datumsvergleich in Analysis Workspace können Sie mit einer Spalte, die einen Datumsbereich enthält, einen allgemeinen Datumsvergleich erstellen, z. B. Jahres-, Quartals- oder Monatsvergleich.

## Zeiträume vergleichen

Für Analysen wird Kontext benötigt, der oft durch einen vorherigen Zeitraum bereitgestellt wird. Zum Beispiel die Frage *Wie viel besser oder schlechter geht es Ihnen jetzt im Vergleich zu dieser Zeit im letzten Jahr?* ist für das Verständnis Ihres Unternehmens von grundlegender Bedeutung. Der Datumsvergleich enthält automatisch *Spalte &quot;*&quot;, die die prozentuale Änderung im Vergleich zu einem bestimmten Zeitraum anzeigt.

1. Erstellen Sie [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) mit allen Dimensionen und Metriken, die Sie über einen bestimmten Zeitraum vergleichen möchten.
1. Öffnen Sie das Kontextmenü für eine Tabellenzeile und wählen Sie **[!UICONTROL Zeiträume vergleichen]** aus.

   ![Tabellenzeile mit ausgewählten Zeiträumen vergleichen](assets/compare-time.png)

   >[!NOTE]
   >
   >Diese Kontextmenüoption ist für Metrik -Zeilen, Datumsbereichszeilen und Zeitdimensionszeilen deaktiviert.

1. Je nachdem, wie Sie den Datumsbereich der Tabelle festgelegt haben, stehen die folgenden Optionen zum Vergleich zur Verfügung:

   | Option | Beschreibung |
   |---|---|
   | **[!UICONTROL Vorherige *x* Wochen/Monate/Quartale/Jahre bis zu diesem Datumsbereich]** | Mit dem ausgewählten Datumsbereich unmittelbar vor diesem Datumsbereich vergleichen. |
   | **[!UICONTROL Diese x Wochen/Monate/Quartale/Jahre sind im letzten Jahr bis zu diesem Datumsbereich aufgetreten]** | Mit demselben Datumsbereich vor einem Jahr vergleichen. |
   | **[!UICONTROL Benutzerdefinierter Datumsbereich auf diesen Datumsbereich]** | Sie können einen benutzerdefinierten Datumsbereich definieren. |

   >[!NOTE]
   >
   >Wenn Sie eine benutzerdefinierte Anzahl von Tagen auswählen, z. B. 7. bis 20. Oktober (ein Zeitraum von 14 Tagen), erhalten Sie nur zwei Optionen: **[!UICONTROL Vor 14 Tagen vor diesem]** und **[!UICONTROL Benutzerdefinierter Datumsbereich bis zu diesem]**.

1. Der resultierende Vergleich sieht wie folgt aus:

   ![Freiformtabelle mit einem Vergleich der Datumsbereiche und der prozentualen Änderung.](assets/compare-time-result.png)

   Zeilen in der Spalte „Prozentuale Änderung“ werden für negative Werte rot und für positive Werte grün angezeigt.

## Eine Zeitraumspalte zum Vergleich hinzufügen

Sie können jeder Spalte in einer Tabelle jetzt einen Zeitraum hinzufügen, sodass Sie einen anderen Zeitraum hinzufügen können als den, für den Ihr Kalender festgelegt ist.

1. Klicken Sie mit der rechten Maustaste auf eine Spalte in der Tabelle und wählen Sie **[!UICONTROL Spalte für Zeitraum hinzufügen]**.

   ![](assets/add-time-period-column.png)

1. Je nachdem, wie Sie den Datumsbereich der Tabelle festgelegt haben, stehen die folgenden Optionen zum Vergleich zur Verfügung:

   | Option | Beschreibung |
   |---|---|
   | **[!UICONTROL Vorherige *x* Wochen/Monate/Quartale/Jahre bis zu diesem Datumsbereich]** | Fügen Sie eine Spalte mit dem Wochentag/Monat usw. hinzu. unmittelbar vor diesem Datumsbereich. |
   | **[!UICONTROL Diese *x* Wochen/Monate/Quartale/Jahre letzten Jahres bis zu diesem Datumsbereich]** | Fügen Sie denselben Datumsbereich wie vor einem Jahr hinzu. |
   | **[!UICONTROL Benutzerdefinierter Datumsbereich auf diesen Datumsbereich]** | Sie können einen benutzerdefinierten Datumsbereich erstellen. |

   >[!NOTE]
   >
   >Wenn Sie eine benutzerdefinierte Anzahl von Tagen auswählen, z. B. 7. bis 20. Oktober (ein Zeitraum von 14 Tagen), erhalten Sie nur zwei Optionen: **[!UICONTROL Vor 14 Tagen vor diesem]** und **[!UICONTROL Benutzerdefinierter Datumsbereich bis zu diesem]**.

1. Der Zeitraum wird über der ausgewählten Spalte eingefügt:

   ![Freiformtabelle mit Vorkommnissen für den aktuellen Kalenderzeitraum und den vorherigen Kalendermonat.](assets/add-time-period-column2.png)

1. Sie können so viele Zeitspalten hinzufügen, wie Sie möchten, sowie verschiedene Datumsbereiche kombinieren:

1. Darüber hinaus können Sie nach jeder Spalte sortieren. Dadurch ändert sich die Reihenfolge der Tage in Abhängigkeit von der Spalte, nach der Sie sortieren.

## Spaltendaten so ausrichten, dass sie in derselben Zeile beginnen

Sie können die Datumsangaben in jeder Spalte so ausrichten, dass sie alle in derselben Zeile beginnen.

Sie führen beispielsweise einen Tagesvergleich für die letzte Woche (bis zum 5. Oktober 2024) und die vorherige Woche durch. Standardmäßig beginnt die linke Spalte am 22. September und die rechte Spalte am 29. September.

![Nicht abgestimmte Daten](assets/not-align-dates.png)

Sie können in **[[!UICONTROL Einstellungen“ für die Freiformtabellen-Visualisierung die Option „Datum [ jeder Spalte so ausrichten]** dass alle Spalten in derselben Zeile beginnen, aktivieren]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md#settings-1) um Spaltendaten so auszurichten, dass sie in derselben Zeile beginnen.

![](assets/align-dates.png)

Beachten Sie bei Verwendung dieser Option Folgendes:

* Diese Einstellung ist standardmäßig für alle neuen Projekte aktiviert.

* Diese Einstellung gilt für die gesamte Tabelle. Wenn Sie diese Einstellung beispielsweise für eine Aufschlüsselung innerhalb der Tabelle ändern, wird die Einstellung auf die gesamte Tabelle angewendet.

