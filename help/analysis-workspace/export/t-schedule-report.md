---
description: Erfahren Sie, wie Sie ein Analysis Workspace-Projekt direkt oder nach einem Zeitplan für den E-Mail-Versand senden.
keywords: Analysis Workspace
title: Senden und Planen von Projekten
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
role: User
source-git-commit: 973e999b611d578da12018e60becf48efd7a76f8
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 51%

---

# Senden und Planen von Projekten

Sie können Customer Journey Analytics-Projekte als Dateien per E-Mail an ausgewählte Benutzer senden. Sie können Dateien ad hoc senden oder Projekte so konfigurieren, dass sie nach einem Zeitplan gesendet werden.

Beachten Sie beim Senden von Dateien Folgendes:

* Dateien können im CSV- oder PDF-Format gesendet werden.

* Alle auf das Projekt angewendeten Tags werden automatisch auf den Export angewendet.

Es sind auch andere Methoden zum Exportieren von Customer Journey Analytics-Daten verfügbar, wie unter [Exportübersicht](/help/analysis-workspace/export/export-project-overview.md) beschrieben.

![Datei senden](assets/send-file.png)

## Datei senden

So senden Sie eine Datei per E-Mail an Empfänger:

1. Wählen Sie **[!UICONTROL Freigeben] > [!UICONTROL Datei senden]**.
1. Geben Sie den Dateityp an:
   * [!UICONTROL **CSV**]: Wählen Sie diese Option aus, wenn Sie Daten in Textform verwenden möchten.
   * [!UICONTROL **PDF**]: Wählen Sie diese Option, wenn die heruntergeladene Datei alle angezeigten (sichtbaren) Tabellen und Visualisierungen im Projekt enthalten soll.
1. (Optional) Verwenden Sie **[!UICONTROL Beschreibung]** um eine Beschreibung hinzuzufügen, die in die E-Mail aufgenommen werden soll.
1. Fügen Sie Empfänger oder Gruppen hinzu. Sie können auch E-Mail-Adressen eingeben.
1. (Nur für Kundinnen und Kunden von Healthcare Shield) Geben Sie ein Kennwort ein, um [einen terminierten Bericht mit einem Kennwort zu schützen](#password-protect-a-new-scheduled-project).
1. (Optional) Wählen Sie **[!UICONTROL Planungsoptionen anzeigen]** aus, um [einen Dateiexport zu ](#schedule-file-export).
1. Klicken Sie **[!UICONTROL Jetzt senden]**. Wählen Sie zum Abbrechen **[!UICONTROL Abbrechen]** aus.


## Dateiexport planen {#schedule}

So senden Sie eine Datei nach einem Zeitplan per E-Mail an Empfänger:

1. Wählen Sie **[!UICONTROL Freigeben] > [!UICONTROL Dateiexport planen]**.
1. Geben Sie den Dateityp an:
   * [!UICONTROL **CSV**]: Wählen Sie diese Option aus, wenn Sie Daten in Textform verwenden möchten.
   * [!UICONTROL **PDF**]: Wählen Sie diese Option, wenn die heruntergeladene Datei alle angezeigten (sichtbaren) Tabellen und Visualisierungen im Projekt enthalten soll.
1. (Optional) Verwenden Sie **[!UICONTROL Beschreibung]** um eine Beschreibung hinzuzufügen, die in die E-Mail aufgenommen werden soll.
1. Fügen Sie Empfänger oder Gruppen hinzu. Sie können auch E-Mail-Adressen eingeben.
1. (Nur für Kundinnen und Kunden von Healthcare Shield) Geben Sie ein Kennwort ein, um [einen terminierten Bericht mit einem Kennwort zu schützen](#password-protect-a-new-scheduled-project).
1. Stellen Sie sicher **[!UICONTROL dass „Planungsoptionen]**&quot; ausgewählt ist.
1. Wählen Sie eine **[!UICONTROL Häufigkeit]** aus. Folgende Optionen stehen zur Auswahl:

   | Häufigkeit | Optionen |
   |---|---|
   | **[!UICONTROL Stündlich senden]** | Geben Sie einen Wert für **[!UICONTROL Alle Stunden senden]** ein. |
   | **[!UICONTROL Täglich senden]** | Wählen Sie eine **[!UICONTROL Tägliche Häufigkeit]** aus: **[!UICONTROL Täglich senden]**, **[!UICONTROL Täglich senden]** oder **[!UICONTROL Benutzerdefinierte Häufigkeit]**.<br/>Wenn Sie **[!UICONTROL Benutzerdefinierte Häufigkeit]** auswählen, geben Sie einen Wert für **[!UICONTROL Alle Tage senden]** ein. |
   | **[!UICONTROL Wöchentlich senden]** | Geben Sie einen Wert für **[!UICONTROL Nach jeder Anzahl von Wochen senden]** ein. und wählen Sie einen **[!UICONTROL Wochentag]**. |
   | **[!UICONTROL Monatlich nach Wochentag senden]** | Wählen Sie einen **[!UICONTROL Wochentag]** und eine **[!UICONTROL Woche des Monats]** aus. |
   | **[!UICONTROL Monatlich nach Tag des Monats senden]** | Wählen Sie einen Wert unter **[!UICONTROL An diesem Tag des Monats senden]** aus. |
   | **[!UICONTROL Jährlich nach Tag des Monats senden]** | Wählen Sie einen **[!UICONTROL Wochentag]**, eine **[!UICONTROL Woche des Monats]** und einen **[!UICONTROL Monatstag des Jahres]** aus. |
   | **[!UICONTROL Jährlich nach bestimmtem Datum senden]** | Wählen Sie einen **[!UICONTROL Monat des Jahres]** und wählen Sie einen Wert aus **[!UICONTROL An diesem Tag des Monats senden]**. |

1. Geben Sie in &quot;**[!UICONTROL am“ ein]** ein. Wählen Sie alternativ ![Kalender](/help/assets/icons/Calendar.svg) aus, um ein Startdatum aus dem Kalender auszuwählen.

1. Geben Sie in „Endet am **[!UICONTROL ein Enddatum]**. Wählen Sie alternativ ![Kalender](/help/assets/icons/Calendar.svg) aus, um ein Enddatum aus dem Kalender auszuwählen.
1. Wählen Sie **[!UICONTROL Planmäßig senden]** aus. Wählen Sie zum Abbrechen **[!UICONTROL Abbrechen]** aus.


## Passwortschutz für ein geplantes Projekt {#password}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_sendfile_password"
>title="Passwortverschlüsselung"
>abstract="Das angegebene Passwort dient dazu, die Datei für das geplante Projekt zu verschlüsseln. Gemäß den Sicherheitsanforderungen Ihrer Organisation ist eine Passwortverschlüsselung erforderlich."

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>Die Option, ein geplantes Projekt mit einem Passwort zu schützen, wird nur für Customer Journey Analytics-Kunden angezeigt, die das [Healthcare Shield](https://business.adobe.com/solutions/industries/healthcare.html)-Add-on-Produkt gekauft haben.

Adobe verwendet das Passwort zum Verschlüsseln geplanter Projekte, unabhängig davon, ob sie im .pdf- oder .csv-Format gesendet werden.

Nachdem Ihr Unternehmen die Healthcare Shield-Produktnummer erworben hat und mit ihr verknüpft wurde, wird die Aufforderung zur Erstellung eines Passworts für ein geplantes Projekt unter den folgenden Bedingungen angezeigt:

* Wenn jemand ein neues geplantes Projekt erstellt.

* Wenn ein vorhandenes geplantes Projekt kurz vor dem Senden steht. Das aktuell geplante Projekt wird deaktiviert, bis der Passwortschutz eingerichtet ist. Die Inhaberin oder der Inhaber des geplanten Projekts erhält eine E-Mail, in der sie bzw. er über diese Anforderung informiert wird.

### Passwortanforderungen

Die Passwortanforderungen entsprechen dem Adobe-Standard und schreiben mindestens acht Zeichen mit mindestens einer Zahl und einem Sonderzeichen vor.

### Passwortschutz für ein neues geplantes Projekt

1. Nachdem Sie Ihr Projekt gespeichert haben, navigieren Sie zu **[!UICONTROL Freigeben]** > **[!UICONTROL Jetzt Datei senden]** oder **[!UICONTROL Freigeben]** > **[!UICONTROL Datei nach Zeitplan senden]**.
1. Befolgen Sie die oben stehenden Anweisungen unter [Datei jetzt senden](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/t-schedule-report.html#now) oder [Datei planmäßig senden](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/t-schedule-report.html#schedule).

### Passwortschutz für ein vorhandenes geplantes Projekt

Wenn Sie ein vorhandenes geplantes Projekt mit einem Passwort schützen, erhält der Projektbesitzer eine E-Mail wie die folgende:

![Die Customer Journey Analytics-E-Mail-Benachrichtigung mit dem Hinweis, dass für eine Passwortverschlüsselung für Ihre Organisation erforderlich ist.](assets/email-password.png)

1. Melden Sie sich bei Customer Journey Analytics an.
1. Wählen Sie **[!UICONTROL Geplantes Projekt anzeigen]** aus.
1. Geben Sie in **[!UICONTROL Geplantes Projekt bearbeiten]** ein Passwort ein und bestätigen Sie es.
1. Teilen Sie den Empfangenden des geplanten Projekts dieses Passwort mit. Geben Sie das Passwort nicht an Personen weiter, die keine Empfangenden des geplanten Projekts sind.



## Manager für geplante Projekte {#manager}

Geplante Analysis Workspace-Projekte können über die Hauptbenutzeroberfläche mithilfe von **[!UICONTROL Komponenten]** > **[!UICONTROL Geplante Projekte]** verwaltet werden. Weitere Informationen finden Sie unter [Geplante Projekte](/help/components/scheduled-projects-manager.md).
