---
description: Mit dem Datumsvergleich in Analysis Workspace können Sie mit einer Spalte, die einen Datumsbereich enthält, einen standardmäßigen Datumsvergleich erstellen, z. B. Jahres-, Quartals-, Monatsvergleich usw.
title: Datumsvergleich
feature: Calendar
exl-id: 08113536-658f-486b-ac56-6c531240c3c2
role: User
source-git-commit: b196b8c05ba05a3f46d71c10fdcaa2ad8ef0dcd6
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 56%

---

# Datumsvergleich

Mit dem Datumsvergleich in Analysis Workspace können Sie mit einer Spalte, die einen Datumsbereich enthält, einen allgemeinen Datumsvergleich erstellen, z. B. Jahres-, Quartals- oder Monatsvergleich.

## Zeiträume vergleichen

Für Analysen wird Kontext benötigt, der oft durch einen vorherigen Zeitraum bereitgestellt wird. Beispielsweise ist „Wie viel besser/schlechter geht es uns als zu diesem Zeitpunkt letztes Jahr?“ eine Kernfrage, um Ihr Geschäft zu verstehen. Der Datumsvergleich enthält automatisch eine Spalte „Differenz“, die die prozentuale Veränderung im Vergleich zu einem bestimmten Zeitraum angibt.

1. Erstellen Sie eine Freiformtabelle mit beliebigen Dimensionen und Metriken, die Sie mit einem bestimmten Zeitraum vergleichen möchten.
1. Klicken Sie mit der rechten Maustaste auf eine Tabellenzeile und wählen Sie **[!UICONTROL Zeiträume vergleichen]** aus.

   ![Tabellenzeile mit ausgewählten Zeiträumen vergleichen](assets/compare-time.png)

   >[!NOTE]
   >
   >Diese Rechtsklickoption ist für Metrikzeilen, Datumsbereichzeilen und Zeitdimensionszeilen deaktiviert.

1. Je nachdem, wie Sie den Datumsbereich der Tabelle festgelegt haben, stehen die folgenden Optionen zum Vergleich zur Verfügung:

   | Option | Beschreibung |
   |---|---|
   | **[!UICONTROL Vorhergehende/r/s Woche/Monat/Quartal/Jahr vor diesem Datumsbereich]** | Vergleich mit der Woche/dem Monat usw. unmittelbar vor diesem Datumsbereich. |
   | **[!UICONTROL Diese Woche/dieser Monat/dieses Quartal/Dieses Jahr des letzten Jahres bis zu diesem Datumsbereich]** | Vergleich mit demselben Datumsbereich vor einem Jahr. |
   | **[!UICONTROL Benutzerdefinierter Datumsbereich für diesen Datumsbereich]** | Ermöglicht die Auswahl eines benutzerdefinierten Datumsbereichs. |

   >[!NOTE]
   >
   >Wenn Sie eine benutzerdefinierte Anzahl von Tagen auswählen, z. B. 7. bis 20. Oktober (ein Zeitraum von 14 Tagen), erhalten Sie nur zwei Optionen: **[!UICONTROL Vorherige 14 Tage vor diesem Datumsbereich]** und **[!UICONTROL Benutzerdefinierter Datumsbereich bis zu diesem Datumsbereich]**.

1. Der resultierende Vergleich sieht wie folgt aus:

   ![Freiformtabelle mit einem Vergleich von Datumsbereichen und prozentualen Änderungen.](assets/compare-time-result.png)

   Zeilen in der Spalte „Prozentwertänderung“ sind rot bei negativen Werten und grün bei positiven Werten.

1. (Optional) Wie bei allen anderen Workspace-Projekten können Sie basierend auf diesen Zeitvergleichen Visualisierungen erstellen. Hier ist z. B. ein Balkendiagramm:

   ![Workspace-Projektleistendiagramm.](assets/compare-time-barchart.png)

   Beachten Sie, dass Sie die Einstellung [!UICONTROL Prozentsätze] in den [!UICONTROL Visualisierungseinstellungen] aktivieren müssen, damit die prozentuale Änderung im Balkendiagramm angezeigt wird.

## Eine Zeitraumspalte zum Vergleich hinzufügen

Sie können jetzt Zeiträume zu allen Spalten in einer Tabelle hinzufügen. So können Sie einen Zeitraum hinzufügen, der von dem abweicht, auf den Ihr Kalender eingestellt ist. Dies ist eine weitere Möglichkeit, um Daten zu vergleichen.

1. Klicken Sie mit der rechten Maustaste auf eine Spalte in der Tabelle und wählen Sie **[!UICONTROL Spalte &quot;Zeitraum hinzufügen&quot;]** aus.

   ![](assets/add-time-period-column.png)

1. Je nachdem, wie Sie den Datumsbereich der Tabelle festgelegt haben, stehen die folgenden Optionen zum Vergleich zur Verfügung:

   | Option | Beschreibung |
   |---|---|
   | **[!UICONTROL Vorhergehende/r/s Woche/Monat/Quartal/Jahr vor diesem Datumsbereich]** | Fügt eine Spalte mit der Woche/dem Monat usw. unmittelbar vor diesem Datumsbereich hinzu. |
   | **[!UICONTROL Diese Woche/dieser Monat/dieses Quartal/Dieses Jahr des letzten Jahres bis zu diesem Datumsbereich]** | Fügt denselben Datumsbereich des Vorjahres hinzu. |
   | **[!UICONTROL Benutzerdefinierter Datumsbereich für diesen Datumsbereich]** | Ermöglicht die Auswahl eines benutzerdefinierten Datumsbereichs. |

   >[!NOTE]
   >
   >Wenn Sie eine benutzerdefinierte Anzahl von Tagen auswählen, z. B. 7. bis 20. Oktober (ein Zeitraum von 14 Tagen), erhalten Sie nur zwei Optionen: **[!UICONTROL Vorherige 14 Tage vor diesem Datumsbereich]** und **[!UICONTROL Benutzerdefinierter Datumsbereich bis zu diesem Datumsbereich]**.

1. Der Zeitraum wird am Anfang der ausgewählten Spalte eingefügt:

   ![Freiformtabelle mit Vorfällen für den aktuellen Kalenderzeitraum und den vorherigen Kalendermonat.](assets/add-time-period-column2.png)

1. Sie können so viele Zeitspalten hinzufügen, wie Sie möchten, sowie verschiedene Datumsbereiche kombinieren:

   ![Freiformtabelle, die die Vorkommen für diesen Monat, den Vormonat, den Vormonat vor einem Jahr und eine Woche vor einem Jahr anzeigt.](assets/add-time-period-column4.png)

1. Sie können außerdem nach jeder Spalte sortieren. Dadurch wird die Reihenfolge der Tage abhängig von der jeweiligen Spalte geändert.

## Beginn der Spaltendaten an derselben Zeile ausrichten {#section_5085E200082048CB899C3F355062A733}

Sie können die Daten in jeder Spalte so ausrichten, dass sie alle in derselben Zeile beginnen.

Wenn Sie beispielsweise das Datum ausrichten und einen Monatsvergleich zwischen Oktober und September 2016 durchführen, beginnt die linke Spalte mit dem 1. Oktober und die rechte Spalte mit dem 1. September:

![](assets/add-time-period-column3.png)

>[!NOTE]
>
>Beachten Sie bei Verwendung dieser Option Folgendes:
>
>* Diese Einstellung ist standardmäßig für alle neuen Projekte aktiviert.
>
>* Diese Einstellung gilt für die gesamte Tabelle. Wenn Sie beispielsweise diese Einstellung für eine Aufschlüsselung innerhalb der Tabelle ändern, wird die Einstellung für die gesamte Tabelle geändert.
>

So aktivieren Sie diese Einstellung, falls sie noch nicht aktiviert ist:

1. Wählen Sie in der Tabelle, in der Sie die Spaltendaten ausrichten möchten, das Symbol **Einstellungen** in der Tabellenüberschrift aus.

1. Wählen Sie auf der Registerkarte [!UICONTROL **Einstellungen**] die Option **[!UICONTROL Datumsangaben in jeder Spalte so ausrichten, dass sie alle auf derselben Zeile beginnen (gilt für die gesamte Tabelle)]**.

![](assets/date-comparison-setting.png)
