---
title: Erstellen von Datumsbereichen
description: Datumsbereich zur Verwendung in Berichten erstellen.
feature: Calendar
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
role: User
source-git-commit: a913f23506f692e64633408b8cd9bad6be27970b
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 39%

---

# Erstellen von Datumsbereichen


Jeder kann einen benutzerdefinierten Datumsbereich erstellen. Sie können einen Datumsbereich wie folgt erstellen:

![Erstellen einer Anmerkung](assets/create-date-range.png)

* ?? Wählen Sie in der Hauptbenutzeroberfläche **[!UICONTROL Komponenten]** und wählen Sie **[!UICONTROL Datumsbereich]**. Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** im [[!UICONTROL Datumsbereich]-Manager](/help/components/date-ranges/manage.md).
* ?? Wählen Sie in einem Workspace-Projekt im Kontextmenü in einer Visualisierung **[!UICONTROL Benutzerdefinierter Datumsbereich für diesen Datumsbereich]** aus.
* ?? Wählen Sie in einem Workspace-Projekt **[!UICONTROL Komponenten]** aus dem Menü und wählen Sie **[!UICONTROL Datumsbereich erstellen]**
* ?? Verwenden Sie in einem Workspace-Projekt die Tastenkombination **[!UICONTROL Strg+Umschalt+D]** (Windows) oder **[!UICONTROL Umschalt+Befehl+D]** (macOS).
* ?? Wählen Sie in einem Workspace-Projekt im linken Bedienfeld Komponenten ![Hinzufügen](/help/assets/icons/Add.svg) unter ![Kalender](/help/assets/icons/Calendar.svg) **Datumsbereiche**.

Um die Anmerkung zu definieren, verwenden Sie den [[!UICONTROL Datumsbereichsersteller]](#annotation-builder):

<!-- Should we really mention API here. If so, we can do it all over the place in the docs...
| **Use the [Customer Journey Analytics Annotations API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | The Customer Journey Analytics Annotations APIs allow you to create, update, or retrieve annotations programmatically through Adobe Developer. These APIs use the same data and methods that Adobe uses inside the product UI. |
-->


## Datumsbereichsgenerator {#date-range-builder}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_dateranges_endtime"
>title="Endzeit"
>abstract="Endzeiten umfassen immer 59 Sekunden."

<!-- markdownlint-enable MD034 -->




Das Dialogfeld **[!UICONTROL Neuer Datumsbereich]** oder **[!UICONTROL Datumsbereich bearbeiten]** wird verwendet, um neue oder vorhandene Datumsbereiche zu erstellen.

![Fenster „Anmerkungsdetails“ mit Feldern und Optionen, die im nächsten Abschnitt beschrieben werden.](assets/edit-date-range.png)


1. Geben Sie einen **[!UICONTROL Titel]** für den Datumsbereich an. Beispiel: **[!UICONTROL Vierteljährlich]**.
1. Geben Sie optional eine &quot;**[!UICONTROL &quot;]**.
1. Organisieren Sie den Filter, indem Sie ein oder mehrere **[!UICONTROL Tags]** erstellen oder anwenden. Beginnen Sie mit der Eingabe, um nach vorhandenen Tags zu suchen, die Sie auswählen können. Oder drücken Sie **[!UICONTROL EINGABETASTE]**, um ein neues Tag hinzuzufügen. Wählen Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg) aus, um ein Tag zu entfernen. |
1. Wählen Sie einen **[!UICONTROL Datumsbereich]** aus, indem Sie zuerst das Startdatum und dann das Enddatum auswählen.
Alternativ können Sie eine **[!UICONTROL Voreinstellung]** aus dem Dropdown-Menü [!UICONTROL *Voreinstellung auswählen*] auswählen.

1. Wählen Sie optional **[!UICONTROL Erweiterte Einstellungen einblenden]** für Folgendes aus:

   * Geben Sie eine andere **[!UICONTROL Startzeit]** und **[!UICONTROL Endzeit]** als die Standardwerte `12:00 AM` (`0:00`) und `11:59 PM` (`23:59`) an. Endzeiten umfassen immer 59 Sekunden. Für einen Datumsbereich, der viele Tage umfasst, gilt die Startzeit für den ersten Tag des Datumsbereichs und die Endzeit gilt für den letzten Tag in Ihrem Datumsbereich. Verwenden Sie **[!UICONTROL (Zeitwerte zurücksetzen)]**, um die Start- und Endzeit auf ihre Standardwerte zurückzusetzen.
   * **[!UICONTROL Rollierende Termine verwenden]**. Wenn diese Option aktiviert ist, werden voreingestellte Datumsbereiche wie **[!UICONTROL Letzte 7 volle Tage]** dynamisch als aktuelles Datum und aktueller Zeitfortschritt aktualisiert. Wenn diese Option deaktiviert ist, werden diese Vorgaben nach der Anwendung nicht aktualisiert.

     Sie können den Text in Klammern auswählen (z. B. **[!UICONTROL fester Start - vierteljährlich rollierend]**), um das Bedienfeld zu erweitern und Details für **[!UICONTROL Start]** und **[!UICONTROL Ende]** anzugeben.

     ![Rollierende Datumswerte](assets/rolliing-dates.png)

      1. Wählen Sie **[!UICONTROL Anfang von]**, **[!UICONTROL Ende von]** oder **[!UICONTROL Festgelegter Tag]** aus.
      1. Wenn Sie **[!UICONTROL Anfang von]** oder **[!UICONTROL Ende von]** ausgewählt haben, können Sie einen vollständigen Ausdruck erstellen. Beispiel: **[!UICONTROL Ende vom]** **[!UICONTROL aktuelles Quartal]** **[!UICONTROL minus]** `20`**[!UICONTROL Tage]**. Wählen Sie den entsprechenden Wert für jeden einzelnen Teil des Ausdrucks aus.
         * Wählen Sie einen Wert für den aktuellen Zeitraum aus, Beispiel: **[!UICONTROL aktuelles Quartal]**.
         * Wählen Sie einen Wert für die zusätzliche Berechnung aus, Beispiel: **[!UICONTROL minus]**.
         * Wenn Sie eine zusätzliche Berechnung angegeben haben, geben Sie einen Wert an. Zum Beispiel `20`.
         * Wenn Sie eine zusätzliche Berechnung angegeben haben, wählen Sie den Zeitraum aus, der für die Berechnung verwendet werden soll. Beispiel: **[!UICONTROL Tage]**.

     Wählen Sie **[!UICONTROL Details ausblenden]** aus, um die Details für die Berechnung rollierender Termine auszublenden.

1. Auswählen :
   * **[!UICONTROL Speichern]**, um den Datumsbereich zu speichern.
   * **[!UICONTROL Speichern unter]**, um eine Kopie des Datumsbereichs zu speichern.
   * **[!UICONTROL Abbrechen]** zum Abbrechen aller Änderungen, die Sie am Datumsbereich vorgenommen haben, oder zum Abbrechen der Erstellung eines neuen Datumsbereichs.


<!--


You can create a date range using either of the following two methods:

* Directly in a workspace project by clicking the '`+`' button next to the list of date range components on the left
* Within the date range manager

To create a date range in the date range manager:

1. Log in to [analytics.adobe.com](https://analytics.adobe.com) using your AdobeID credentials.
1. Navigate to [!UICONTROL Components] > [!UICONTROL Date Ranges].
1. Click the [!UICONTROL Add] button to open the modal window that creates a date range.

## Create a date range modal window

The modal window has four fields you can edit:

* **Date range**: The date range you want for this component.
* **Title**: The name you want for this component. The title is used in workspace projects.
* **Description**: The description you want for this component. The description is seen when clicking the ![i](../assets/i.png) icon.
* **Tags**: Use tags to organize your date ranges. A date range can belong to multiple tags.

## Selecting a date range

When clicking the date range in the modal window, you have several options:

* **Calendar**: Select the start and end date.
* **Use rolling dates**: Check this box if you want the date range to change as time goes on. Do not check this box if you want your date range to remain static.
* **Select preset**: Use this drop-down selection if you want a custom date range based on a range that Adobe offers by default. When you select a preset, you can further customize the date range to suit your needs. It does not affect the preset that Adobe offers.

## Rolling date ranges

If you want a rolling date range, you can customize when it rolls. You can control when the start and end dates roll independently of each other.

* **When the date starts**: Choose if the date starts at the beginning of a time period, at the end of a time period, or use a fixed day.
* **The time period to use**: Choose how often the date range rolls. You can have it roll every day, every week, every month, every quarter, or every year.
* **Offset**: Choose the offset of the date range. You can add or subtract days, weeks, months, quarters, or years.

## Rolling date examples

Some date ranges can be useful in certain reports.

Year-to-date:

```text
Start: Start of current year
End: End of current day
```

Last Thursday to this Thursday:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Fiscal year (for example, if a fiscal year starts in December)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```


-->
