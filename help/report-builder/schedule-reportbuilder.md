---
title: Zeitliche Planung von Arbeitsmappen mithilfe von Report Builder in Customer Journey Analytics
description: Beschreibt die Verwendung der Zeitplanfunktion in Report Builder
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 7429d8f9-1e8f-4fbd-8b04-cbe7adbff3e2
source-git-commit: cd3ed8873619c7fb5281d42b1f74c32b245400d0
workflow-type: ht
source-wordcount: '1078'
ht-degree: 100%

---

# Erstellen von Zeitplänen für Arbeitsmappen

Nachdem Sie Ihre Arbeitsmappe gespeichert und Ihre Analyse abgeschlossen haben, können Sie die Arbeitsmappe mithilfe der Zeitplanfunktion für andere in Ihrem Team freigeben. Mit der Zeitplanfunktion können Sie einen Zeitplan erstellen, anhand dessen die Daten in der Arbeitsmappe automatisch aktualisiert werden und die Excel-Arbeitsmappe (.xlsx) als E-Mail-Anhang an Ihre ausgewählte Zielgruppe gesendet wird. Durch die Einrichtung eines Zeitplans erhalten die Empfänger und Empfängerinnen automatisch regelmäßige Aktualisierungen. Sie können die Zeitplanfunktion auch verwenden, um die Arbeitsmappe nur einmal zu senden, ohne automatische Aktualisierungen festzulegen.

Für eine Arbeitsmappe können mehrere Zeitpläne erstellt werden. So können Sie beispielsweise eine Arbeitsmappe täglich an Ihr Team und einmal wöchentlich an Ihren Vorgesetzten senden, indem Sie zwei verschiedene Zeitpläne erstellen.

Außerdem können Sie mit der Zeitplanfunktion einen Passwortschutz für eine Arbeitsmappe einrichten und zuvor geplante Arbeitsmappen bearbeiten.

>[!VIDEO](https://video.tv.adobe.com/v/3413079/?quality=12&learn=on)

## Festlegen eines Zeitplans für eine Arbeitsmappe

Verwenden Sie im Report Builder-Hub die Schaltfläche „Aufgabe planen“, um schnell einen Zeitplan zu erstellen, sodass eine Excel-Arbeitsmappe (.xlsx) automatisch an eine Einzelperson oder eine Gruppe gesendet wird.

1. Klicken Sie im Report Builder-Hub auf die Schaltfläche „Planen“.

   ![](./assets/schedule-button.png){width="55%"}

1. Klicken Sie oben links auf „Arbeitsmappe planen“ oder auf die Plusschaltfläche, um eine neue Arbeitsmappe mit Zeitplan zu erstellen.

   ![ALT-Beschreibung](./assets/schedule-workbook.png){width="55%"}

   Im Zeitplanfenster werden einige vordefinierte Informationen zur Arbeitsmappe angezeigt, z. B. der Arbeitsmappenname und das Datum der letzten Änderung der Arbeitsmappe.

   ![ALT-Beschreibung](./assets/schedule-pane.png){width="55%"}

1. (Optional) Geben Sie einen Dateinamen ein.

   Der Dateiname der Arbeitsmappe entspricht standardmäßig dem Namen der Arbeitsmappe. Sie können ihn jedoch bei Bedarf ändern. Das könnte beispielsweise der Fall sein, wenn Sie dieselbe Arbeitsmappe an mehrere Zielgruppen senden und für eine bestimmte Zielgruppe eine etwas benutzerfreundlichere Bezeichnung wählen möchten.

1. (Optional) Wählen Sie **Zeitstempel an Dateinamen anhängen**.

   Sie können einen Zeitstempel an den Dateinamen anhängen, um das Datum der Aktualisierung der Arbeitsmappe anzugeben. Dies ist hilfreich, wenn Sie schnell feststellen möchten, welche Version einer Arbeitsmappe an einem bestimmten Datum gesendet wurde. In der **Dateinamenvorschau** ist zu sehen, wie der Dateiname der Arbeitsmappe beim Versand in der E-Mail angezeigt wird. Das Zeitstempelformat ist JJJ-MM-TT.

1. (Optional) Wählen Sie **.zip-Komprimierung**, um die Datei zu komprimieren und einen Passwortschutz für die Datei einzurichten.

   Wenn Sie diese Auswahl treffen, werden Sie beim Öffnen der Datei aufgefordert, ein Passwort einzugeben. Dies ist hilfreich, wenn Sie Bedenken hinsichtlich der Datensicherheit haben und die Arbeitsmappe mit einem Passwort schützen möchten. Wenn Sie die Datei mit einem Passwort schützen möchten, wählen Sie **.zip-Komprimierung** aus. Das Passwort muss mindestens 8 Zeichen lang sein und eine Zahl und ein Sonderzeichen enthalten.

   ![ALT-Beschreibung](./assets/zip-compression.png){width="55%"}

1. Eingeben der **Empfänger und Empfängerinnen**. Sie können entweder den Namen einer in Ihrem Unternehmen bekannten Person oder eine E-Mail-Adresse einer unternehmensinternen oder -externen Person eingeben.

1. Geben Sie den **Betreff** Ihrer E-Mail und eine Beschreibung ein. Der Betreff verwendet standardmäßig den Namen der Arbeitsmappen-Datei. Sie können den Betreff jedoch bei Bedarf ändern. Im Beschreibungsabschnitt können Sie Informationen hinzufügen.

   ![ALT-Beschreibung](./assets/recipients-subject.png){width="55%"}

1. Aktivieren Sie die Zeitplanoptionen, um das Datum und die Uhrzeit festzulegen, zu denen die Arbeitsmappe per E-Mail an Ihre Empfänger und Empfängerinnen gesendet werden soll.

   Wählen Sie das Start- und Enddatum sowie den Zeitrahmen aus. Dies kann das heutige Datum oder ein Datum in der Zukunft sein.

   Wählen Sie aus dem Dropdown-Menü die **Häufigkeit** aus. Sie können die Häufigkeit auf stündlich, täglich, wöchentlich, monatlich oder jährlich an einem bestimmten Tag einstellen. Sie können beispielsweise einen Zeitplan einrichten, um die Arbeitsmappe am ersten Sonntagabend des Monats zu senden, sodass Ihre Empfänger und Empfängerinnen die E-Mail am Montagmorgen in ihrem Posteingang haben.

   ![ALT-Beschreibung](./assets/frequency.png){width="55%"}

1. Nachdem Sie den Zeitplan festgelegt haben, klicken Sie auf **Planmäßig senden**.

   ![ALT-Beschreibung](./assets/send-on-schedule.png){width="55%"}

   Im Report Builder-Abschnitt wird unten eine Bestätigungsmitteilung angezeigt, und die zeitlich geplante Arbeitsmappe wird auf der Registerkarte „Arbeitsmappen“ aufgeführt.

   ![ALT-Beschreibung](./assets/confirmation-toast.png){width="55%"}

## Einmaliges Senden der Arbeitsmappe

Sie können die Arbeitsmappe auch nur ein einziges Mal versenden.

1. Deaktivieren Sie die Option **Planungsoptionen anzeigen**.

   ![ALT-Beschreibung](./assets/send-now.png){width="40%"}

1. Klicken Sie auf **Jetzt senden**.

## Anzeigen und Bearbeiten geplanter Arbeitsmappen

Sie können alle geplanten Arbeitsmappen auf der Registerkarte „Arbeitsmappen“ anzeigen und verwalten.

1. Klicken Sie im Report Builder-Hub im Bereich „Zeitplan“ auf die Registerkarte „Arbeitsmappen“. In dieser Ansicht finden Sie eine Liste aller geplanten Arbeitsmappen.

1. Wählen Sie eine Arbeitsmappe aus. Es werden verschiedene Tools angezeigt, mit denen Sie die Arbeitsmappe bearbeiten und den Zeitplan ändern, anhalten und neu starten oder löschen können.

   ![ALT-Beschreibung](./assets/edit-icons.png){width="55%"}

* (Optional) Klicken Sie auf das Stiftsymbol, um den Arbeitsmappen-Zeitplan zu bearbeiten.

* (Optional) Klicken Sie auf das Uhrensymbol, um den Verlauf jeder geplanten Aufgabe anzuzeigen.

* (Optional) Klicken Sie auf das Pausensymbol, um den Versandzeitplan anzuhalten und neu zu starten. Dies ist hilfreich, wenn Sie die Arbeitsmappe vor ihrem Versand ändern müssen. Klicken Sie erneut auf das Pausensymbol, wenn Sie den Versand neu starten möchten.

* (Optional) Klicken Sie auf den Papierkorb, um den Zeitplan zu löschen.

## Überprüfen des Status geplanter Aufgaben

In der Verlaufsansicht können Sie den Status jeder geplanten Aufgabe überprüfen. Für jede geplante Aufgabe wird in einer eigenen Zeile die Statusänderung festgehalten. Im folgenden Beispiel wurde *der neue stündliche Zeitplan* am 5. Januar um 15:04 Uhr gestartet. Um 15:05 Uhr waren die Aktualisierung und der Versand an die Empfänger und Empfängerinnen erfolgreich abgeschlossen. Die nächste Arbeitsmappe, *Fehlerhafte Arbeitsmappe*, meldete einen Fehler während des Aktualisierungsprozesses. Wenn eine Arbeitsmappe nicht gesendet werden kann, hilft Ihnen die Registerkarte „Verlauf“ bei der Fehlerbehebung, da sie anzeigt, wo im Prozess der Fehler aufgetreten ist. In diesem Fall ist der Fehler wahrscheinlich auf einen Datenblockfehler, vielleicht eine fehlende Komponente, zurückzuführen, sodass die Arbeitsmappe nicht erfolgreich aktualisiert werden konnte.

Ein grünes Häkchen bedeutet, dass die Arbeitsmappe erfolgreich gesendet wurde. Ein Ausrufezeichen in einem roten Dreieck gibt an, dass ein Fehler aufgetreten ist.

Sie können auswählen, welche Spalten in der Registerkarte „Verlauf“ angezeigt werden sollen, indem Sie rechts neben der Suchleiste auf das Spalteneinstellungssymbol klicken.

![ALT-Beschreibung](./assets/history.png){width="55%"}

Sie können den Verlauf so filtern, dass nur der Verlauf einer einzigen geplanten Arbeitsmappen angezeigt wird. Gehen Sie dazu zur Registerkarte „Arbeitsmappen“, wählen Sie die Arbeitsmappe aus und klicken Sie auf das Verlaufsymbol.

Sie können den Verlauf einer bestimmten Arbeitsmappe auch auf der Registerkarte „Arbeitsmappen“ einsehen. Wählen Sie dazu auf der Registerkarte „Arbeitsmappen“ die entsprechende Arbeitsmappe aus und klicken Sie auf das Verlaufsymbol.

![ALT-Beschreibung](./assets/history2.png){width="55%"}

Der Arbeitsmappen-Filter wird dann oben im Verlauf angezeigt. Um wieder den Verlauf aller geplanten Aufgaben anzuzeigen, klicken Sie auf das x neben dem Filter.

![ALT-Beschreibung](./assets/history3.png){width="55%"}
