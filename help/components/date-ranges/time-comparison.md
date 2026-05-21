---
description: Erfahren Sie, wie Sie einen Datumsvergleich in Analysis Workspace verwenden, indem Sie aus einer beliebigen Spalte mit einem Datumsbereich einen allgemeinen Datumsvergleich erstellen.
title: Datumsvergleich
feature: Calendar
exl-id: 08113536-658f-486b-ac56-6c531240c3c2
role: User
TQID: https://experienceleague.adobe.com/LhPSvchJbDMPV-HmGSA2JaBZxoPQ7UyEKd7GMS-33UU
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 770
ht-degree: 90%

---

# Datumsvergleich

Mit dem Datumsvergleich in Analysis Workspace können Sie eine beliebige Spalte mit einem Datumsbereich verwenden und einen allgemeinen Datumsvergleich erstellen, z. B. Jahres-, Quartals- oder Monatsvergleich.

## Zeiträume vergleichen

Für Analysen wird Kontext benötigt, der oft durch einen vorherigen Zeitraum geliefert wird. Zum Beispiel die Frage *Wie viel besser oder schlechter geht es Ihnen jetzt im Vergleich zu dieser Zeit im letzten Jahr?* ist grundlegend für das Verständnis Ihres Unternehmens. Der Datumsvergleich enthält automatisch eine Spalte *Differenz*, die die prozentuale Veränderung im Vergleich zu einem bestimmten Zeitraum angibt.

1. Erstellen Sie eine [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) mit beliebigen Dimensionen und Metriken, die Sie mit einem bestimmten Zeitraum vergleichen möchten.
1. Legen Sie den Zeitraum im Panel oder in der Spalte fest, um den Vergleichszeitrahmen zu bestimmen und um anzugeben, ob es sich um einen rollierenden oder einen festen Zeitvergleich handelt.

   Zum Erstellen eines rollierenden Zeitvergleichs legen Sie für den Datumsbereich des Bedienfelds oder der Spalte einen rollierenden Datumsbereich fest (z. B. **[!UICONTROL Letzte 7 Tage]**, **[!UICONTROL Letzte 30 Tage]** usw.).

   Zum Erstellen eines festen Zeitvergleichs legen Sie für den Datumsbereich des Panels oder der Spalte einen benutzerdefinierten Datumsbereich fest.

1. Öffnen Sie das Kontextmenü für eine Tabellenzeile und wählen Sie **[!UICONTROL Zeiträume vergleichen]** aus.

   ![Tabellenzeile mit ausgewählter Option „Zeiträume vergleichen“](assets/compare-time.png)

   >[!NOTE]
   >
   >Diese Kontextmenüoption ist für Metrikzeilen, Datumsbereichzeilen und Zeitdimensionszeilen deaktiviert.

1. Abhängig davon, wie Sie den Datumsbereich der Tabelle festgelegt haben, stehen Ihnen die folgenden Vergleichsoptionen zur Verfügung:

   | Option | Beschreibung |
   |---|---|
   | **[!UICONTROL Vorherige *x* Wochen/Monate/Quartale/Jahre bis zu diesem Datumsbereich]** | Vergleich mit dem ausgewählten Datumsbereich unmittelbar vor diesem Datumsbereich. |
   | **[!UICONTROL Diese x Wochen/Monate/Quartale/Jahre im letzten Jahr vor diesem Datumsbereich]** | Vergleich mit demselben Datumsbereich vor einem Jahr. |
   | **[!UICONTROL Benutzerdefinierter Datumsbereich vor diesem Datumsbereich]** | Ermöglicht die Definition eines benutzerdefinierten Datumsbereichs. |

   >[!NOTE]
   >
   >Wenn Sie eine benutzerdefinierte Anzahl an Tagen auswählen, z. B. 7.–20. Oktober (ein Zeitraum von 14 Tagen), stehen nur zwei Optionen zur Verfügung: **[!UICONTROL Vorhergehende 14 Tage vor diesem Datumsbereich]** und **[!UICONTROL Benutzerdefinierter Datumsbereich vor diesem Datumsbereich]**.

1. Der resultierende Vergleich sieht wie folgt aus:

   ![Freiformtabelle mit einem Vergleich der Datumsbereiche und der prozentualen Änderung.](assets/compare-time-result.png)

   Zeilen in der Spalte „Prozentuale Veränderung“ sind rot bei negativen Werten und grün bei positiven Werten.

## Hinzufügen einer Zeitraumspalte zum Vergleich

Sie können jetzt allen Spalten in einer Tabelle Zeiträume hinzufügen. So können Sie einen Zeitraum hinzufügen, der von dem abweicht, auf den Ihr Kalender eingestellt ist.

1. Klicken Sie mit der rechten Maustaste auf eine Spalte in der Tabelle und wählen Sie **[!UICONTROL Spalte für Zeitraum hinzufügen]** aus

   ![](assets/add-time-period-column.png)

1. Abhängig davon, wie Sie den Datumsbereich der Tabelle festgelegt haben, stehen Ihnen die folgenden Vergleichsoptionen zur Verfügung:

   | Option | Beschreibung |
   |---|---|
   | **[!UICONTROL Vorherige *x* Wochen/Monate/Quartale/Jahre bis zu diesem Datumsbereich]** | Fügen Sie unmittelbar vor diesem Datumsbereich eine Spalte mit dem Wochentag/Monat usw. hinzu. |
   | **[!UICONTROL Diese *x* Wochen/Monate/Quartale/Jahre im letzten Jahr vor diesem Datumsbereich]** | Fügt denselben Datumsbereich des Vorjahres hinzu. |
   | **[!UICONTROL Benutzerdefinierter Datumsbereich vor diesem Datumsbereich]** | Ermöglicht die Erstellung eines benutzerdefinierten Datumsbereichs. |

   >[!NOTE]
   >
   >Wenn Sie eine benutzerdefinierte Anzahl an Tagen auswählen, z. B. 7.–20. Oktober (ein Zeitraum von 14 Tagen), stehen nur zwei Optionen zur Verfügung: **[!UICONTROL Vorhergehende 14 Tage vor diesem Datumsbereich]** und **[!UICONTROL Benutzerdefinierter Datumsbereich vor diesem Datumsbereich]**.

1. Der Zeitraum wird am Anfang der ausgewählten Spalte eingefügt:

   ![Freiformtabelle mit Vorfällen für den aktuellen Kalenderzeitraum und den vorherigen Kalendermonat.](assets/add-time-period-column2.png)

1. Sie können so viele Zeitspalten hinzufügen, wie Sie möchten, sowie verschiedene Datumsbereiche kombinieren:

1. Sie können außerdem nach jeder Spalte sortieren. Dadurch wird die Reihenfolge der Tage abhängig von der jeweiligen Spalte geändert.

## Beginn der Spaltendaten an derselben Zeile ausrichten

Sie können die Daten in den einzelnen Spalten so ausrichten, dass sie alle in derselben Zeile beginnen.

Sie führen beispielsweise einen Tagesvergleich für die letzte Woche (bis zum 5. Oktober 2024) und die vorherige Woche durch. Standardmäßig beginnt die linke Spalte am 22. September und die rechte Spalte am 29. September.

![Nicht abgestimmte Daten](assets/not-align-dates.png)

Sie können unter [Einstellungen](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md#settings-1) für die Freiformtabellen-Visualisierung die Option **[!UICONTROL Datum in allen Spalten ausrichten, sodass es in derselben Zeile beginnt]** aktivieren, um Spaltendaten so anzuordnen, dass sie in derselben Zeile beginnen.

![](assets/align-dates.png)

Beachten Sie beim Verwenden dieser Option Folgendes:

* Diese Einstellung ist standardmäßig für alle neuen Projekte aktiviert.

* Diese Einstellung gilt für die gesamte Tabelle. Wenn Sie diese Einstellung beispielsweise für eine Aufschlüsselung innerhalb der Tabelle ändern, wird die Einstellung auf die gesamte Tabelle angewendet.

