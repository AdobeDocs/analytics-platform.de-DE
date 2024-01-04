---
description: Mit dem Datumsvergleich in Analysis Workspace können Sie mit einer Spalte, die einen Datumsbereich enthält, einen standardmäßigen Datumsvergleich erstellen, z. B. Jahres-, Quartals-, Monatsvergleich usw.
title: Datumsvergleich
feature: Calendar
exl-id: 08113536-658f-486b-ac56-6c531240c3c2
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 86%

---

# Datumsvergleich

Mit dem Datumsvergleich in Analysis Workspace können Sie mit einer Spalte, die einen Datumsbereich enthält, einen allgemeinen Datumsvergleich erstellen, z. B. Jahres-, Quartals- oder Monatsvergleich.

## Zeiträume vergleichen

Für Analysen wird Kontext benötigt, der oft durch einen vorherigen Zeitraum bereitgestellt wird. Beispielsweise ist „Wie viel besser/schlechter geht es uns als zu diesem Zeitpunkt letztes Jahr?“ eine Kernfrage, um Ihr Geschäft zu verstehen. Der Datumsvergleich enthält automatisch eine Spalte „Differenz“, die die prozentuale Veränderung im Vergleich zu einem bestimmten Zeitraum angibt.

1. Erstellen Sie eine Freiformtabelle mit beliebigen Dimensionen und Metriken, die Sie mit einem bestimmten Zeitraum vergleichen möchten.
1. Rechtsklicken Sie auf eine Tabellenzeile und wählen Sie **[!UICONTROL Zeiträume vergleichen]** aus.

   ![Tabellenzeile mit ausgewählten Zeiträumen vergleichen](assets/compare-time.png)

   >[!IMPORTANT]
   >
   >Diese Rechtsklickoption ist für Metrikzeilen, Datumsbereichzeilen und Zeitdimensionszeilen deaktiviert.

1. Je nachdem, wie Sie den Datumsbereich der Tabelle festgelegt haben, stehen die folgenden Optionen zum Vergleich zur Verfügung:

   | Option | Beschreibung |
   |---|---|
   | **[!UICONTROL Vorhergehende/r/s Woche/Monat/Quartal/Jahr vor diesem Datumsbereich]** | Vergleich mit der Woche/dem Monat usw. unmittelbar vor diesem Datumsbereich. |
   | **[!UICONTROL Diese/r/s Woche/Monat/Quartal/Jahr letztes Jahr]** | Vergleich mit demselben Datumsbereich vor einem Jahr. |
   | **[!UICONTROL Bereich auswählen]** | Ermöglicht die Auswahl eines benutzerdefinierten Datumsbereichs. |

   >[!NOTE]
   >
   >Wenn Sie eine benutzerdefinierte Anzahl an Tagen auswählen, z. B. 7.–20. Oktober (ein Zeitraum von 14 Tagen), stehen nur zwei Optionen zur Verfügung: **[!UICONTROL Vorherige 14 Tage vor diesem Datumsbereich]** und **[!UICONTROL Bereich auswählen]**.

1. Der resultierende Vergleich sieht wie folgt aus:

   ![Freiformtabelle, die einen Vergleich von Datumsbereichen und prozentualen Änderungen anzeigt.](assets/compare-time-result.png)

   Zeilen in der Spalte „Prozentwertänderung“ sind rot bei negativen Werten und grün bei positiven Werten.

1. (Optional) Wie bei allen anderen Workspace-Projekten können Sie basierend auf diesen Zeitvergleichen Visualisierungen erstellen. Hier ist z. B. ein Balkendiagramm:

   ![Arbeitsbereich-Projektleistendiagramm.](assets/compare-time-barchart.png)

   Beachten Sie, dass Sie die Einstellung [!UICONTROL Prozentsätze] in den [!UICONTROL Visualisierungseinstellungen] aktivieren müssen, damit die prozentuale Änderung im Balkendiagramm angezeigt wird.

## Eine Zeitraumspalte zum Vergleich hinzufügen

Sie können jetzt Zeiträume zu allen Spalten in einer Tabelle hinzufügen. So können Sie einen Zeitraum hinzufügen, der von dem abweicht, auf den Ihr Kalender eingestellt ist. Dies ist eine weitere Möglichkeit, um Daten zu vergleichen.

1. Klicken Sie mit der rechten Maustaste auf eine Spalte in der Tabelle und wählen Sie **[!UICONTROL Spalte &quot;Zeitraum hinzufügen&quot;]** ![Tabellenspaltenliste mit hervorgehobener Spalte &quot;Zeitraum hinzufügen&quot; ](assets/add-time-period-column.png)

1. Je nachdem, wie Sie den Datumsbereich der Tabelle festgelegt haben, stehen die folgenden Optionen zum Vergleich zur Verfügung:

   | Option | Beschreibung |
   |---|---|
   | **[!UICONTROL Vorhergehende/r/s Woche/Monat/Quartal/Jahr vor diesem Datumsbereich]** | Fügt eine Spalte mit der Woche/dem Monat usw. unmittelbar vor diesem Datumsbereich hinzu. |
   | **[!UICONTROL Diese/r/s Woche/Monat/Quartal/Jahr letztes Jahr]** | Fügt denselben Datumsbereich des Vorjahres hinzu. |
   | **[!UICONTROL Bereich auswählen]** | Ermöglicht die Auswahl eines benutzerdefinierten Datumsbereichs. |

   >[!NOTE]
   >
   >Wenn Sie eine benutzerdefinierte Anzahl an Tagen auswählen, z. B. 7.–20. Oktober (ein Zeitraum von 14 Tagen), stehen nur zwei Optionen zur Verfügung: **[!UICONTROL Vorherige 14 Tage vor diesem Datumsbereich]** und **[!UICONTROL Bereich auswählen]**.

1. Der Zeitraum wird am Anfang der ausgewählten Spalte eingefügt:

   ![Freiformtabelle mit Vorfällen für den aktuellen Kalenderzeitraum und den vorherigen Kalendermonat.](assets/add-time-period-column2.png)

1. Sie können so viele Zeitspalten hinzufügen, wie Sie möchten, sowie verschiedene Datumsbereiche kombinieren:

   ![Freiformtabelle, die die Vorkommen für diesen Monat, den Vormonat, den Vormonat vor einem Jahr und eine Woche des Vormonats vor einem Jahr anzeigt.](assets/add-time-period-column4.png)

1. Sie können außerdem nach jeder Spalte sortieren. Dadurch wird die Reihenfolge der Tage abhängig von der jeweiligen Spalte geändert.

## Beginn der Spaltendaten an derselben Zeile ausrichten {#section_5085E200082048CB899C3F355062A733}

Mit einer neuen Einstellung für alle Tabellen können Sie **[!UICONTROL Datumswerte in jeder Spalte so ausrichten, dass sie in der gleichen Zeile beginnen (wird auf die gesamte Tabelle angewendet)]**. „Wird auf die gesamte Tabelle angewendet“ bedeutet, dass, wenn Sie z. B. eine Aufschlüsselung in der Tabelle durchführen und diese Einstellung für die Aufschlüsselung ändern, die Einstellung für die gesamte Tabelle geändert wird.

![Freiformtabelle mit Popup-Fenster &quot;Tabelleneinstellungen&quot;mit der Option Datumsangaben in jeder Spalte ausrichten , damit sie alle in derselben ausgewählten Zeile beginnen.](assets/date-comparison-setting.png)

>[!IMPORTANT]
>
>Diese Einstellung ist für alle bestehenden Projekte **deaktiviert** und für alle neuen Projekte **aktiviert**.

Beispiel: Wenn Sie die Daten in einem Monatsvergleich zwischen Oktober und September 2016 ausrichten, beginnt die linke Spalte mit dem 1. Oktober und die rechte Spalte mit dem 1. September:

![Vergleich mit monatlichen Prozentsätzen.](assets/add-time-period-column3.png)

<!-- 

<p>See Jonny Moon's email from November 3. </p>

 -->
