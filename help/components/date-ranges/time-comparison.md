---
description: Mit dem Datumsvergleich in Analysis Workspace können Sie jede Spalte, die einen Datumsbereich enthält, mit einem allgemeinen Datumsvergleich durchführen, z. B. Jahres-, Quartals-, Monatsvergleich usw.
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

Für Analysen wird Kontext benötigt, der oft durch einen vorherigen Zeitraum bereitgestellt wird. Zum Beispiel die Frage *Wie viel besser oder schlechter geht es Ihnen jetzt im Vergleich zu dieser Zeit im letzten Jahr?* ist von grundlegender Bedeutung für das Verständnis Ihres Geschäfts. Der Datumsvergleich enthält automatisch die Spalte *Differenz* , die die prozentuale Änderung im Vergleich zu einem bestimmten Zeitraum anzeigt.

1. Erstellen Sie eine [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) mit allen Dimensionen und Metriken, die Sie über einen Zeitraum vergleichen möchten.
1. Öffnen Sie das Kontextmenü für eine Tabellenzeile und wählen Sie **[!UICONTROL Zeiträume vergleichen]** aus.

   ![Tabellenzeile mit ausgewählten Zeiträumen vergleichen](assets/compare-time.png)

   >[!NOTE]
   >
   >Diese Kontextmenüoption ist für Metrikzeilen, Datumsbereichzeilen und Zeitdimensionszeilen deaktiviert.

1. Je nachdem, wie Sie den Datumsbereich der Tabelle festgelegt haben, stehen die folgenden Optionen zum Vergleich zur Verfügung:

   | Option | Beschreibung |
   |---|---|
   | **[!UICONTROL Vorherige *x* Wochen/Monate/Quartale/Jahre vor diesem Datumsbereich]** | Vergleichen Sie den ausgewählten Datumsbereich unmittelbar vor diesem Datumsbereich. |
   | **[!UICONTROL Diese x Wochen/Monate/Quartale/Jahre des letzten Jahres bis zu diesem Datumsbereich]** | Vergleichen Sie den gleichen Datumsbereich wie vor einem Jahr. |
   | **[!UICONTROL Benutzerdefinierter Datumsbereich für diesen Datumsbereich]** | Ermöglicht die Definition eines benutzerdefinierten Datumsbereichs. |

   >[!NOTE]
   >
   >Wenn Sie eine benutzerdefinierte Anzahl von Tagen auswählen, z. B. 7. bis 20. Oktober (ein Zeitraum von 14 Tagen), erhalten Sie nur zwei Optionen: **[!UICONTROL Vorherige 14 Tage vor diesem Datumsbereich]** und **[!UICONTROL Benutzerdefinierter Datumsbereich bis zu diesem Datumsbereich]**.

1. Der resultierende Vergleich sieht wie folgt aus:

   ![Freiformtabelle mit einem Vergleich von Datumsbereichen und prozentualen Änderungen.](assets/compare-time-result.png)

   Zeilen in der Spalte Prozentänderung werden für negative Werte rot und für positive Werte grün angezeigt.

## Eine Zeitraumspalte zum Vergleich hinzufügen

Jetzt können Sie jeder Spalte in einer Tabelle einen Zeitraum hinzufügen, um einen Zeitraum hinzuzufügen, der sich von dem Zeitraum unterscheidet, auf den Ihr Kalender eingestellt ist.

1. Klicken Sie mit der rechten Maustaste auf eine Spalte in der Tabelle und wählen Sie **[!UICONTROL Spalte &quot;Zeitraum hinzufügen&quot;]** aus.

   ![](assets/add-time-period-column.png)

1. Je nachdem, wie Sie den Datumsbereich der Tabelle festgelegt haben, stehen die folgenden Optionen zum Vergleich zur Verfügung:

   | Option | Beschreibung |
   |---|---|
   | **[!UICONTROL Vorherige *x* Wochen/Monate/Quartale/Jahre vor diesem Datumsbereich]** | Fügen Sie eine Spalte mit Woche/Monat/etc. hinzu. unmittelbar vor diesem Datumsbereich. |
   | **[!UICONTROL Diese *x* Wochen/Monate/Quartale/Jahre des letzten Jahres bis zu diesem Datumsbereich]** | Fügen Sie denselben Datumsbereich vor einem Jahr hinzu. |
   | **[!UICONTROL Benutzerdefinierter Datumsbereich für diesen Datumsbereich]** | Ermöglicht die Erstellung eines benutzerdefinierten Datumsbereichs. |

   >[!NOTE]
   >
   >Wenn Sie eine benutzerdefinierte Anzahl von Tagen auswählen, z. B. 7. bis 20. Oktober (ein Zeitraum von 14 Tagen), erhalten Sie nur zwei Optionen: **[!UICONTROL Vorherige 14 Tage vor diesem Datumsbereich]** und **[!UICONTROL Benutzerdefinierter Datumsbereich bis zu diesem Datumsbereich]**.

1. Der Zeitraum wird oberhalb der von Ihnen ausgewählten Spalte eingefügt:

   ![Freiformtabelle mit Vorfällen für den aktuellen Kalenderzeitraum und den vorherigen Kalendermonat.](assets/add-time-period-column2.png)

1. Sie können so viele Zeitspalten hinzufügen, wie Sie möchten, sowie verschiedene Datumsbereiche kombinieren:

1. Darüber hinaus können Sie jede Spalte sortieren, wodurch die Reihenfolge der Tage von der Spalte abhängt, nach der Sie sortieren.

## Spaltendaten so ausrichten, dass sie in derselben Zeile beginnen

Sie können die Daten in jeder Spalte so ausrichten, dass sie alle in derselben Zeile beginnen.

Beispiel: Sie führen einen täglichen Vergleich für die letzte Woche (endet am 5. Oktober 2024) und die vorherige Woche durch. Standardmäßig beginnt die linke Spalte am 22. September und die rechte Spalte am 29. September.

![Nicht ausgerichtete Datumswerte](assets/not-align-dates.png)

Sie können die Option **[!UICONTROL Datumsangaben aus jeder Spalte so ausrichten, dass sie alle in derselben Zeile beginnen]** in [Einstellungen](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md#settings-1) aktivieren, damit die Freiformtabellenvisualisierung die Spaltendaten so ausrichten kann, dass sie in derselben Zeile beginnen.

![](assets/align-dates.png)

Beachten Sie bei Verwendung dieser Option Folgendes:

* Diese Einstellung ist standardmäßig für alle neuen Projekte aktiviert.

* Diese Einstellung gilt für die gesamte Tabelle. Wenn Sie diese Einstellung beispielsweise für eine Aufschlüsselung innerhalb der Tabelle ändern, wird die Einstellung auf die gesamte Tabelle angewendet.

