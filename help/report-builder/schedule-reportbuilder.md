---
title: Zeitliche Planung von Arbeitsmappen mithilfe von Report Builder in Customer Journey Analytics
description: Erfahren Sie, wie Sie die Zeitplanfunktion in Report Builder verwenden
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 7429d8f9-1e8f-4fbd-8b04-cbe7adbff3e2
source-git-commit: 6dd8a70293161ff58361953a7e48a98834b7abe0
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 13%

---

# Arbeitsmappen planen

Nachdem Sie Ihre Arbeitsmappe gespeichert und Ihre Analyse abgeschlossen haben, können Sie Ihre Arbeitsmappe mithilfe der Zeitplanfunktion für andere in Ihrem Team freigeben. Mit der Zeitplanfunktion können Sie einen Zeitplan erstellen, der die Daten in der Arbeitsmappe automatisch aktualisiert. Senden Sie die Excel-Arbeitsmappendatei per E-Mail als Anhang an Ihre angegebene Zielgruppe zu einem bestimmten Zeitpunkt. Durch die Einrichtung eines Zeitplans erhalten die Empfänger und Empfängerinnen automatisch regelmäßige Aktualisierungen. Sie können die Zeitplanfunktion auch verwenden, um die Arbeitsmappe nur einmal zu senden, ohne automatische Aktualisierungen festzulegen.

Für eine Arbeitsmappe können mehrere Zeitpläne erstellt werden. Sie erstellen beispielsweise zwei Zeitpläne, um einmal wöchentlich eine Arbeitsmappe an Ihr Team und Ihren Vorgesetzten zu senden.

Mit der Zeitplanfunktion können Sie auch einen Passwortschutz für eine Arbeitsmappe einrichten und zuvor geplante Arbeitsmappen bearbeiten.


>[!BEGINSHADEBOX]

Siehe ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Arbeitsmappen planen](https://video.tv.adobe.com/v/3413079/?quality=12&learn=on){target="_blank"} für ein Demovideo.

>[!ENDSHADEBOX]


## Festlegen eines Zeitplans für eine Arbeitsmappe

So planen Sie eine Arbeitsmappe:

1. Wählen Sie **[!UICONTROL Zeitplan]** im Report Builder-Hub aus, um einen Zeitplan zu erstellen, damit Sie automatisch eine Excel-Arbeitsmappe (.xlsx) an eine Einzelperson oder eine Gruppe verteilen können.

   ![Wählen Sie die Schaltfläche „Zeitplan“, um einen Zeitplan zu erstellen.](./assets/schedule.png){zoomable="yes"}

1. Wählen Sie **[!UICONTROL Arbeitsmappe planen]** oder ![Hinzufügen](/help/assets/icons/Add.svg), um eine neue geplante Arbeitsmappe zu erstellen.

   ![Das Fenster „Arbeitsmappen planen“.](./assets/schedule-workbook.png){zoomable="yes"}

   Im Zeitplanfenster werden einige vordefinierte Informationen zur Arbeitsmappe angezeigt, z. B. der Arbeitsmappenname und das Datum der letzten Änderung der Arbeitsmappe.

### Datei

Im Abschnitt **[!UICONTROL Datei]** geben Sie Details zum Dateityp, zum Dateinamen und zu einem Kennwort zum Schutz der Datei an.

![Der Zeitplanbereich.](./assets/schedule-pane.png){zoomable="yes"}

1. Verwenden ![TableSelect](/help/assets/icons/TableSelect.svg), um die aktuelle Arbeitsmappe auszuwählen, falls noch nicht ausgewählt.

1. (Optional) Geben Sie einen **[!UICONTROL Dateinamen]** ein.

   Der Dateiname der Arbeitsmappe entspricht standardmäßig dem Namen der Arbeitsmappe. Sie können den Dateinamen jedoch bei Bedarf ändern.

1. Wählen Sie einen **[!UICONTROL Dateityp]** aus.

   * **[!UICONTROL Excel]**
   * **[!UICONTROL PDF]**
   * **[!UICONTROL CSV]**

   Beachten Sie bei Auswahl **[!UICONTROL CSV]**, dass die geplante Arbeitsmappe als ZIP-Anlage gesendet wird. Einige E-Mail-Administratoren im Unternehmen blockieren möglicherweise E-Mails mit ZIP-Anhängen. Dementsprechend wird eine Warnung angezeigt.

1. (Optional) Wählen Sie **[!UICONTROL Zeitstempel an Dateinamen anhängen]**.

   Sie können einen Zeitstempel an den Dateinamen anhängen, um das Datum der Aktualisierung der Arbeitsmappe anzugeben. Ein Zeitstempel ist hilfreich, um zu sehen, welche Version einer Arbeitsmappe an einem bestimmten Datum gesendet wurde. Wenn diese Option aktiviert ist, können Sie zwischen folgenden Optionen wählen:

   * **[!UICONTROL ISO-Datumsformat]**, was dazu führt, dass `YYYY-MM-DD` an den Dateinamen angehängt wird.
   * **[!UICONTROL ISO-Datumsformat + Zeitstempel]** was dazu führt, dass `YYYY-MM-DD_HH-MM-SS` an den Dateinamen angehängt wird.

<!-- Does no longer seem to be an option? 
1. (Optional) Select **.zip compression** to compress the file and set up password protection on the file.

    When you make this selection, you're prompted to enter a password to open the file. This is helpful if you have concerns about data security and you want to password protect the workbook. Protecting the file with a password requires you to select **.zip compression**. The password must be at least 8 characters and contain a number and a special character.

    ![Enter a password in the Password protect the workbook field.](./assets/zip-compression.png){zoomable="yes"}{width="55%"}
-->

1. Geben Sie in „Kennwort **[!UICONTROL die Arbeitsmappe schützen“ ein]** ein. Ein gültiges Kennwort muss mindestens 8 Zeichen, eine Zahl und ein Sonderzeichen enthalten. Wählen Sie ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) aus, um das Kennwort anzuzeigen, und ![Visibility](/help/assets/icons/Visibility.svg), um das Kennwort auszublenden (Standard).


### E-Mail

Im Abschnitt **[!UICONTROL E-Mail]** geben Sie die Empfänger, den Betreff und die Beschreibung der E-Mail an.

![E-Mail-Einstellungen planen](assets/schedule-email.png){zoomable="yes"}

1. Eingeben der **Empfänger und Empfängerinnen**. Sie können den Namen einer in Ihrem Unternehmen bekannten Person eingeben. Sie können auch eine E-Mail-Adresse einer Person eingeben, die nicht zu Ihrem Unternehmen gehört.

1. Geben Sie den **Betreff** Ihrer E-Mail und eine Beschreibung ein. Der Betreff verwendet standardmäßig den Namen der Arbeitsmappen-Datei. Sie können den Betreff jedoch bei Bedarf ändern. Im Beschreibungsabschnitt können Sie Informationen hinzufügen.

1. Sie können optional eine Beschreibung im Textbereich **[!UICONTROL Beschreibung]** eingeben.


### Zeitplan

Im Abschnitt **[!UICONTROL Zeitplan]** können Sie den Zeitplan definieren, nach dem die E-Mails mit der Arbeitsmappe an Ihre Empfänger gesendet werden sollen.

![Zeitplandefinition](assets/schedule-enable.png){zoomable="yes"}

1. Wählen Sie **[!UICONTROL Planungsoptionen anzeigen]**, um einen Zeitplan zu definieren.

1. Geben Sie in &quot;**[!UICONTROL am“ ein]** ein. Wählen Sie alternativ ![Kalender](/help/assets/icons/Calendar.svg) aus, um ein Startdatum aus dem Kalender auszuwählen.

1. Geben Sie in „Endet am **[!UICONTROL ein Enddatum]**. Wählen Sie alternativ ![Kalender](/help/assets/icons/Calendar.svg) aus, um ein Enddatum aus dem Kalender auszuwählen.

1. Wählen Sie eine **[!UICONTROL Häufigkeit]** aus. Je nach ausgewählter Häufigkeit stehen Ihnen zusätzliche Optionen zur Verfügung. Siehe Tabelle unten.

   | Häufigkeit | Optionen |
   |---|---|
   | **[!UICONTROL Stündlich senden]** | Geben Sie einen Wert für **[!UICONTROL Alle Stunden senden]** ein. |
   | **[!UICONTROL Täglich senden]** | Wählen Sie eine **[!UICONTROL Tägliche Häufigkeit]** aus: **[!UICONTROL Täglich senden]**, **[!UICONTROL Täglich senden]** oder **[!UICONTROL Benutzerdefinierte Häufigkeit]**.<br/>Wenn Sie **[!UICONTROL Benutzerdefinierte Häufigkeit]** auswählen, geben Sie einen Wert für **[!UICONTROL Alle Tage senden]** ein. |
   | **[!UICONTROL Wöchentlich senden]** | Geben Sie einen Wert für **[!UICONTROL Nach jeder Anzahl von Wochen senden]** ein. und wählen Sie einen **[!UICONTROL Wochentag]**. |
   | **[!UICONTROL Monatlich nach Wochentag senden]** | Wählen Sie einen **[!UICONTROL Wochentag]** und eine **[!UICONTROL Woche des Monats]** aus. |
   | **[!UICONTROL Monatlich nach Tag des Monats senden]** | Wählen Sie einen Wert unter **[!UICONTROL An diesem Tag des Monats senden]** aus. |
   | **[!UICONTROL Jährlich nach Tag des Monats senden]** | Wählen Sie einen **[!UICONTROL Wochentag]**, eine **[!UICONTROL Woche des Monats]** und einen **[!UICONTROL Monatstag des Jahres]** aus. |
   | **[!UICONTROL Jährlich nach bestimmtem Datum senden]** | Wählen Sie einen **[!UICONTROL Monat des Jahres]** und wählen Sie einen Wert aus **[!UICONTROL An diesem Tag des Monats senden]**. |

### Senden

So senden Sie die Arbeitsmappe:

* Wenn Sie keinen Zeitplan mit **[!UICONTROL Planungsoptionen anzeigen]** definiert haben, wählen Sie **[!UICONTROL Jetzt senden]** aus, um die Arbeitsmappe sofort per E-Mail zu senden.
* Wenn Sie einen Zeitplan mit **[!UICONTROL Planungsoptionen anzeigen]** definiert haben, wählen Sie **[!UICONTROL Planmäßig senden]** aus, um die Arbeitsmappe mithilfe des von Ihnen definierten Zeitplans per E-Mail zu senden.

In beiden Fällen wird unten im Report Builder-Hub ein Bestätigungsfoast angezeigt.

Um den Versand der Arbeitsmappe abzubrechen, wählen Sie **[!UICONTROL Abbrechen]** aus.


## Anzeigen und Verwalten geplanter Arbeitsmappen

Sie können alle geplanten Arbeitsmappen auf der Registerkarte „Arbeitsmappen **[!UICONTROL anzeigen und]**.

1. Wählen Sie **[!UICONTROL Zeitplan]** im Report Builder-Hub aus.

1. Wählen Sie die **[!UICONTROL Arbeitsmappen]** aus. Es wird eine Liste aller geplanten Arbeitsmappen angezeigt.

   ![Geplante Arbeitsmappe](assets/scheduled-workbooks.png){zoomable="yes"}

   Sie können den Mauszeiger über das Symbol bewegen, um den Status einer geplanten Arbeitsmappe anzuzeigen.

   Verwenden Sie ![Suche](/help/assets/icons/Search.svg), um nach bestimmten geplanten Arbeitsmappen zu suchen.
Mit ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) können Sie festlegen, welche Spalten angezeigt werden sollen.

1. Eine oder mehrere Arbeitsmappen auswählen.

   ![Arbeitsmappen planen ausgewählt](assets/scheduled-workbooks-selected.png){zoomable="yes"}

   Die folgenden Optionen sind verfügbar:

   | Option | Beschreibung |
   |---|---|
   | ![Bearbeiten](/help/assets/icons/Edit.svg) | Bearbeiten Sie den Zeitplan für eine ausgewählte Arbeitsmappe. |
   | ![Verlauf](/help/assets/icons/History.svg) | Zeigt den Verlauf der ausgewählten Arbeitsmappen an. |
   | ![Pause](/help/assets/icons/Pause.svg) | Aussetzen des Zeitplans ausgewählter Arbeitsmappen. |
   | ![Play](/help/assets/icons/Play.svg) | Setzt den Zeitplan der ausgewählten Arbeitsmappen fort. |
   | ![Herunterladen](/help/assets/icons/Download.svg) | Die ausgewählte Arbeitsmappe in eine neue Arbeitsmappe herunterladen. |
   | ![Löschen](/help/assets/icons/Delete.svg) | Löscht den Zeitplan der ausgewählten Arbeitsmappen. |


## Verlauf und Status geplanter Arbeitsmappen

Sie können den Verlauf und den Status geplanter Arbeitsmappen auf der Registerkarte **[!UICONTROL Verlauf]** anzeigen.

1. Wählen Sie **[!UICONTROL Zeitplan]** im Report Builder-Hub aus.

1. Wählen Sie die **[!UICONTROL Verlauf]** aus. Es wird eine Liste aller geplanten Arbeitsmappen angezeigt.

   ![Geplanter Verlauf](assets/scheduled-workbooks-history.png){zoomable="yes"}

   Verwenden Sie ![Suche](/help/assets/icons/Search.svg), um in der Liste nach bestimmten Arbeitsmappen zu suchen.
Mit ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) können Sie festlegen, welche Spalten angezeigt werden sollen.

   Auf **[!UICONTROL Registerkarte]** Verlauf“ können Sie den Status jeder geplanten Aufgabe überprüfen. In einer separaten Zeile wird die Statusänderung für jede geplante Aufgabe dokumentiert.

   * Eine ![CheckmarkCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg) zeigt an, dass die Arbeitsmappe erfolgreich gesendet wurde.
   * Ein ![AlertRed](/help/assets/icons/AlertRed.svg) zeigt an, dass ein Fehler aufgetreten ist.

Alternativ können Sie ![Verlauf](/help/assets/icons/History.svg) für eine oder mehrere ausgewählte Arbeitsmappen auf der Registerkarte **[!UICONTROL Arbeitsmappen]** auswählen. Diese Aktion zeigt die Registerkarte **[!UICONTROL Verlauf]** mit einer nach Ihrer Auswahl gefilterten Liste an. Wählen Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg) aus, um einen Filter zu entfernen.
