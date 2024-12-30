---
title: Erfahren Sie, wie Sie in Customer Journey Analytics erstellte Zielgruppen verwalten
description: Erfahren Sie, wie Sie Zielgruppen in Customer Journey Analytics verwalten
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: e131fd78ceee67a05a1ea7256e58b4b34ce44ae5
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 20%

---

# Verwalten von Audiences

Zielgruppen können im Customer Journey Analytics mithilfe von **[!UICONTROL Komponenten]** > **[!UICONTROL Zielgruppen]** verwaltet werden.

Die Verwaltung zuvor erstellter Zielgruppen ermöglicht Ihnen Folgendes:

* **Erstellen eines Zeitplans bzw. Aufhebung des Zeitplans** für die automatische Aktualisierung der Zielgruppe. Die maximale Gültigkeit des Zeitplans beträgt 1 Jahr.
* **Verlängern Sie einen Zeitplan für die Aktualisierung der Zielgruppe**, bevor er abläuft. Vor der Beendigung der Zielgruppen-Aktualisierung erhält der Administrierende ähnlich wie bei der Beendigung von geplanten Berichten einen Monat vor Ablauf des Zeitplans eine E-Mail.
* Anzeigen des **Aktualisierungsintervalls** und der **letzten Aktualisierung einer Zielgruppe**
* Gewinnen Sie Einblicke in die **Zeit, die für die Erstellung einer Zielgruppe benötigt wurde** von Customer Journey Analytics. Und die Zeit, die benötigt wurde, um die Zielgruppe zur Aktivierung in der Echtzeit-Kundenplattform angezeigt zu bekommen.
* Überprüfen, ob die Zielgruppen in Customer Journey Analytics **aktiv von der Echtzeit-Kundenplattform verwendet werden**. Oder (im Idealfall) alle Experience Platform-Anwendungen, die die vom Customer Journey Analytics erstellten Zielgruppen nutzen.

Wenn Sie nicht über Zugriff [Zielgruppenansicht](/help/technotes/access-control.md#user-level-access) verfügen, können Sie Zielgruppen anzeigen. Wenn Sie nicht über [Zielgruppe erstellen](/help/technotes/access-control.md#user-level-access) verfügen, können Sie Zielgruppen bearbeiten und löschen. Die [Liste Zielgruppen](#audiences-list) zeigt die Zielgruppen.

![Audience Manager](assets/audiences-manager.png)

## Liste der Zielgruppen

Die Liste „Zielgruppen“ Spalten für:

| Spalte | Beschreibung |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | Wenn eine oder mehrere Zielgruppen ausgewählt sind, wird unten in der Benutzeroberfläche „Zielgruppen“ eine blaue Aktionsleiste angezeigt. Weitere Informationen finden [ unter ](#actions). |
| **[!UICONTROL Titel und Beschreibung]** | Titel und Beschreibung, die Sie beim Erstellen der Zielgruppe eingegeben haben. |
| **[!UICONTROL Datenansicht]** | Die Datenansicht, in der diese Zielgruppe erstellt wurde. |
| **[!UICONTROL Zielgruppengröße]** | Die Gesamtzahl der Personen in dieser Zielgruppe. |
| **[!UICONTROL Inhaber]** | Der Verantwortliche der Zielgruppe - die Person, die die Zielgruppe erstellt hat. |
| **[!UICONTROL Häufigkeit der Aktualisierung]** | Das bei der Erstellung der Zielgruppe konfigurierte Aktualisierungsintervall. |
| **[!UICONTROL Tags]** | Alle Tags, die auf diese Zielgruppe angewendet werden. |
| **[!UICONTROL Veröffentlichungsstatus]** | Kann ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Ready]**, ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL In Bearbeitung]** oder ![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL error]** anzeigen. |
| **[!UICONTROL Zuletzt aktualisiert]** | Zeitstempel der letzten Aktualisierung der Zielgruppe. |
| **[!UICONTROL Zuletzt geändert]** | Zeitstempel, wann die Zielgruppe zuletzt bearbeitet oder geändert wurde. |

Sie können mit ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) konfigurieren, welche Spalten angezeigt werden sollen. Suchen Sie mithilfe von ![Suche](/help/assets/icons/Search.svg) nach einer Zielgruppe.

So bearbeiten Sie eine Zielgruppe:

1. Wählen Sie den Titel der Zielgruppe aus. Verwenden Sie das Dialogfeld **[!UICONTROL Zielgruppenprojekt bearbeiten]**, um die Zielgruppe zu aktualisieren. Weitere Informationen finden [ unter ](publish.md#audience-builder)Audience Builder).

1. Wählen Sie **[!UICONTROL Erneut veröffentlichen]** aus, um die Zielgruppe erneut zu veröffentlichen.


## Aktionen

Im Folgenden finden Sie häufige Aktionen im Manager für geplante Projekte. Sie können Aktionen im Kontextmenü auswählen:

| Symbol | Aktion | Beschreibung |
|:---:|---|---|
| ![Bezeichnungen](/help/assets/icons/Labels.svg) | **[!UICONTROL Tag]** | Markieren Sie die ausgewählten Zielgruppen. Wählen Sie **[!UICONTROL Dialogfeld Tags aktualisieren: *Zielgruppenname *]**aus dem Dropdown-Menü die Option Tags aus oder geben Sie einen oder mehrere neue Tags ein. Wählen Sie**[!UICONTROL Speichern ]**aus, um zu speichern. |
| ![Löschen](/help/assets/icons/Delete.svg) | **[!UICONTROL Löschen]** | Löscht die ausgewählten Zielgruppen. |
| ![Bearbeiten](/help/assets/icons/Edit.svg) | **[!UICONTROL Umbenennen]** | Benennen Sie die ausgewählte Zielgruppe um. Verwenden Sie das Dialogfeld **[!UICONTROL Umbenennen: *Zielgruppenname *]**zum Umbenennen der Zielgruppe und wählen Sie**[!UICONTROL Speichern ]**. |

Die folgenden Aktionen sind in der blauen Aktionsleiste verfügbar, wenn Sie ein oder mehrere geplante Projekte auswählen.

| Symbol | Aktion | Beschreibung |
|:---:|---|---|
| ![Schließen](/help/assets/icons/Close.svg) | **[!UICONTROL *x *ausgewählt]** | Auswählen, um die Auswahl der ausgewählten Zielgruppen aufzuheben. |
| ![Löschen](/help/assets/icons/Delete.svg) | **[!UICONTROL Löschen]** | Löscht die ausgewählten Zielgruppen. |
| ![CSV-Datei](/help/assets/icons/FileCSV.svg) | **[!UICONTROL In CSV exportieren]** | Exportieren Sie die ausgewählten Zielgruppen in eine Datei mit dem Namen `audiences.csv`. |

## Filter

Sie können die [Zielgruppenliste“ mithilfe ](#audiences-list) Filterbedienfelds filtern. Verwenden Sie zum Ein- oder Ausblenden des Filterbereichs ![Filter](/help/assets/icons/Filter.svg).

Das Filterbedienfeld besteht aus den folgenden Abschnitten.

### Datenansicht

| Datenansicht | Beschreibung |
|---|---|
| ![Inhaber](/help/components/audiences/assets/audiences-filter-dataviews.png){width="300"} | Im **[!UICONTROL Datenansicht]** können Sie nach Datenansichten filtern. <ul><li>Sie verwenden ![Suche](/help/assets/icons/Search.svg), um nach Datenansichten zu suchen, die Sie zum Filtern verwenden möchten.</li><li>Sie können mehrere Datenansichten auswählen.</li></ul> |

### Inhaber

| Besitzer | Beschreibung |
|---|---|
| ![Inhaber](/help/components/audiences/assets/audiences-filter-owner.png){width="300"} | Im Abschnitt **[!UICONTROL Verantwortlicher]** können Sie nach Verantwortlichen filtern. <ul><li>Sie verwenden ![Suche](/help/assets/icons/Search.svg), um nach Inhabern zu suchen, die Sie zum Filtern verwenden möchten.</li><li>Sie können mehrere Besitzer auswählen. </li></ul> |

## Häufigkeit der Aktualisierung

| Häufigkeit der Aktualisierung | Beschreibung |
|---|---|
| ![Häufigkeit der Aktualisierung](/help/components/audiences/assets/audiences-filter-refreshfrequency.png){width="300"} | Im **[!UICONTROL Aktualisierungshäufigkeit]** können Sie nach der Aktualisierungshäufigkeit filtern. <ul><li>Sie verwenden ![Suche](/help/assets/icons/Search.svg), um nach der Aktualisierungshäufigkeit zu suchen, die Sie zum Filtern verwenden möchten.</li><li>Nur die für die Zielgruppen definierten Aktualisierungsfrequenzen <br/> der [Zielgruppenliste](#audiences-list) werden als verfügbare Optionen angezeigt.</li></ul> |


### Tags

| Tags | Beschreibung |
|---|---|
| ![Tags](/help/components/audiences/assets/audiences-filter-tags.png){width="300"} | Im Abschnitt **[!UICONTROL Tags]** können Sie nach Tags filtern. <ul><li>Sie verwenden ![Suche](/help/assets/icons/Search.svg), um nach Tags zu suchen, die Sie zum Filtern verwenden möchten. |
