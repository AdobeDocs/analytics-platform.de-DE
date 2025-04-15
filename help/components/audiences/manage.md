---
title: Erfahren Sie, wie Sie in Customer Journey Analytics erstellte Zielgruppen verwalten
description: Erfahren Sie, wie Sie Zielgruppen in Customer Journey Analytics verwalten
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: 65dcbf63d9e155cb7e04bf9a550151a37b8457e6
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 79%

---

# Verwalten von Zielgruppen

Zielgruppen können in Customer Journey Analytics mithilfe von **[!UICONTROL Komponenten]** > **[!UICONTROL Zielgruppen]** verwaltet werden.

## Aufgaben des Zielgruppen-Managements

Die Verwaltung zuvor erstellter Zielgruppen ermöglicht Ihnen Folgendes:

* **Erstellen eines Zeitplans bzw. Aufhebung des Zeitplans** für die automatische Aktualisierung der Zielgruppe. Die maximale Gültigkeit des Zeitplans beträgt 1 Jahr.
* **Verlängern Sie einen Zeitplan für die Aktualisierung der Zielgruppe**, bevor er abläuft. Vor der Beendigung der Zielgruppen-Aktualisierung erhält der Administrierende ähnlich wie bei der Beendigung von geplanten Berichten einen Monat vor Ablauf des Zeitplans eine E-Mail.
* Sehen Sie sich das **Aktualisierungsintervall** und die **letzte Aktualisierung einer Zielgruppe** an
* Gewinnen Sie Einblicke in die **benötigte Dauer für die Erstellung einer Zielgruppe** aus Customer Journey Analytics. Und die benötigte Zeit, damit die Zielgruppe zur Aktivierung in der Echtzeit-Kundenplattform angezeigt wird.
* Überprüfen, ob die Zielgruppen in Customer Journey Analytics **aktiv von der Echtzeit-Kundenplattform verwendet werden**. Oder (im Idealfall) alle Experience Platform-Programme, die die von Customer Journey Analytics erstellten Zielgruppen nutzen.

Wenn Sie Zugriff auf die [Zielgruppenansicht](/help/technotes/access-control.md#user-level-access) haben, können Sie Zielgruppen anzeigen. Wenn Sie nicht über [Zielgruppe erstellen](/help/technotes/access-control.md#user-level-access) verfügen, können Sie Zielgruppen bearbeiten und löschen.

## Anzeigen von Zielgruppen in der Liste „Zielgruppen“

Die Liste Audiences zeigt die vorhandenen Audiences.

![Audience Manager](assets/audiences-manager.png)

So zeigen Sie die Liste der Zielgruppen an:

1. Wählen Sie in Customer Journey Analytics **[!UICONTROL Komponenten]** > **[!UICONTROL Zielgruppen]** aus.

1. (Optional) Verwenden Sie ![ColumnSetting](/help/assets/icons/ColumnSetting.svg), um zu konfigurieren, welche Spalten angezeigt werden sollen.

1. (Optional) Suchen Sie mit „Suchen![ nach einer ](/help/assets/icons/Search.svg).

   Die folgenden Spalten sind mit Informationen zu jeder Zielgruppe verfügbar:

   | Spalte | Beschreibung |
   | --- | --- |
   | ![SelectBox](/help/assets/icons/SelectBox.svg) | Wenn eine oder mehrere Zielgruppen ausgewählt sind, wird unten in der Benutzeroberfläche „Zielgruppen“ eine blaue Aktionsleiste angezeigt. Weitere Informationen finden Sie unter [Aktionen](#actions). |
   | **[!UICONTROL Titel und Beschreibung]** | Der Titel und die Beschreibung, den bzw. die Sie beim Erstellen der Zielgruppe eingegeben haben. |
   | **[!UICONTROL Datenansicht]** | Die Datenansicht, in der diese Zielgruppe erstellt wurde. |
   | **[!UICONTROL Zielgruppengröße]** | Die Gesamtzahl der Personen in dieser Zielgruppe. |
   | **[!UICONTROL Inhaber]** | Die Inhaberin oder Inhaber der Zielgruppe, d. h. die Person, die die Zielgruppe erstellt hat. |
   | **[!UICONTROL Häufigkeit der Aktualisierung]** | Das Aktualisierungsintervall, das bei der Erstellung der Zielgruppe konfiguriert wurde. |
   | **[!UICONTROL Tags]** | Alle Tags, die auf diese Zielgruppe angewendet werden. |
   | **[!UICONTROL Veröffentlichungsstatus]** | Kann ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Bereit]**, ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL In Bearbeitung]** oder ![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Fehler]** anzeigen. |
   | **[!UICONTROL Zuletzt aktualisiert]** | Zeitstempel der letzten Aktualisierung der Zielgruppe. |
   | **[!UICONTROL Zuletzt geändert]** | Zeitstempel der letzten Bearbeitung oder Änderung der Zielgruppe. |

## Audiences bearbeiten

Sie können die Einstellungen einer Audience jederzeit bearbeiten. Wenn Sie eine Zielgruppe bearbeiten (entweder eine einmalige Zielgruppe oder eine wiederkehrende Zielgruppe), ist eine erneute Veröffentlichung erforderlich.

So bearbeiten Sie eine Zielgruppe:

1. Wählen Sie in Customer Journey Analytics **[!UICONTROL Komponenten]** > **[!UICONTROL Zielgruppen]** aus.

   Die Seite Zielgruppen wird angezeigt.

1. Wählen Sie den Titel der Zielgruppe aus, die Sie bearbeiten möchten.

   Das **[!UICONTROL Zielgruppe bearbeiten]** Dialogfeld wird angezeigt.

1. Sie können jedes der verfügbaren Felder für die Zielgruppe aktualisieren. Informationen zu den Feldern, die Sie aktualisieren können, finden Sie unter [Audience Builder](/help/components/audiences/publish.md#audience-builder) im Artikel [Erstellen und Veröffentlichen von Zielgruppen](/help/components/audiences/publish.md).

1. Wählen Sie **[!UICONTROL Neu veröffentlichen]** aus.

## Aktionen

Die folgenden Aktionen werden im Manager für geplante Projekte häufig ausgeführt. Sie können Aktionen im Kontextmenü auswählen:

| Symbol | Aktion | Beschreibung |
|:---:|---|---|
| ![Bezeichnungen](/help/assets/icons/Labels.svg) | **[!UICONTROL Tag]** | Versehen Sie die ausgewählten Zielgruppen mit Tags. Wählen Sie im Dialogfeld **[!UICONTROL Tags aktualisieren: *Zielgruppenname *]**im Dropdown-Menü die Option „Tags“ aus oder geben Sie einen oder mehrere neue Tags ein. Wählen Sie zum Speichern**[!UICONTROL Speichern ]**aus. |
| ![Löschen](/help/assets/icons/Delete.svg) | **[!UICONTROL Löschen]** | Löschen Sie die ausgewählten Zielgruppen. |
| ![Bearbeiten](/help/assets/icons/Edit.svg) | **[!UICONTROL Umbenennen]** | Benennen Sie die ausgewählte Zielgruppe um. Verwenden Sie das Dialogfeld **[!UICONTROL Umbenennen: *Zielgruppenname *]**, um die Zielgruppe umzubenennen, und wählen Sie zum Speichern**[!UICONTROL Speichern ]**aus. |

Die folgenden Aktionen sind in der blauen Aktionsleiste verfügbar, wenn Sie ein oder mehrere geplante Projekte auswählen.

| Symbol | Aktion | Beschreibung |
|:---:|---|---|
| ![Schließen](/help/assets/icons/Close.svg) | **[!UICONTROL *x *ausgewählt]** | Wählen Sie die Option aus, um die Auswahl der ausgewählten Zielgruppen aufzuheben. |
| ![Löschen](/help/assets/icons/Delete.svg) | **[!UICONTROL Löschen]** | Löschen Sie die ausgewählten Zielgruppen. |
| ![CSV-Datei](/help/assets/icons/FileCSV.svg) | **[!UICONTROL In CSV exportieren]** | Exportieren Sie die ausgewählten Zielgruppen in eine Datei mit dem Namen `audiences.csv`. |

## Filtern der Audience-Liste

Sie können die [Liste „Zielgruppen“](#audiences-list) mithilfe des Panels „Filter“ ➋ filtern. Verwenden Sie ![Filter](/help/assets/icons/Filter.svg), um das Panel „Filter“ ein- oder auszublenden.

![Audience Manager](assets/audiences-manager.png)

Das Panel „Filter“ besteht aus den folgenden Abschnitten.

### Datenansicht

| Datenansicht | Beschreibung |
|---|---|
| ![Inhaberin oder Inhaber](/help/components/audiences/assets/audiences-filter-dataviews.png){width="300"} | Im Abschnitt **[!UICONTROL Datenansicht]** können Sie nach Datenansichten filtern. <ul><li>Mit ![Durchsuchen](/help/assets/icons/Search.svg) suchen Sie nach Datenansichten, die Sie zum Filtern verwenden möchten.</li><li>Sie können mehr als nur eine Datenansicht auswählen.</li></ul> |

### Inhaberinnen oder Inhaber

| Inhaberin oder Inhaber | Beschreibung |
|---|---|
| ![Inhaberinnen oder Inhaber](/help/components/audiences/assets/audiences-filter-owner.png){width="300"} | Im Abschnitt **[!UICONTROL Inhaberin oder Inhaber]** können Sie nach Inhaberinnen und Inhabern filtern. <ul><li>Mit ![Durchsuchen](/help/assets/icons/Search.svg) suchen Sie nach Inhaberinnen oder Inhabern, die Sie zum Filtern verwenden möchten.</li><li>Sie können mehr als eine Inhaberin bzw. einen Inhaber auswählen. </li></ul> |

## Häufigkeit der Aktualisierung

| Häufigkeit der Aktualisierung | Beschreibung |
|---|---|
| ![Häufigkeit der Aktualisierung](/help/components/audiences/assets/audiences-filter-refreshfrequency.png){width="300"} | Im Abschnitt **[!UICONTROL Häufigkeit der Aktualisierung]** können Sie nach der Aktualisierungshäufigkeit filtern. <ul><li>Mit ![Durchsuchen](/help/assets/icons/Search.svg) suchen Sie nach der Aktualisierungshäufigkeit, die Sie zum Filtern verwenden möchten.</li><li>Nur die für die Zielgruppen definierten Aktualisierungshäufigkeiten<br/> der [Liste „Zielgruppen“](#audiences-list) werden als verfügbare Optionen angezeigt.</li></ul> |


### Tags

| Tags | Beschreibung |
|---|---|
| ![Tags](/help/components/audiences/assets/audiences-filter-tags.png){width="300"} | Im Abschnitt **[!UICONTROL Tags]** können Sie nach Tags filtern. <ul><li>Mit ![Durchsuchen](/help/assets/icons/Search.svg) suchen Sie nach Tags, die Sie zum Filtern verwenden möchten. |
