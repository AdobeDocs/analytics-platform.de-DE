---
title: Erfahren Sie, wie Sie in Customer Journey Analytics erstellte Zielgruppen verwalten.
description: Erfahren Sie, wie Sie Zielgruppen in Customer Journey Analytics verwalten
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: 8676497c9341e3ff74d1b82ca79bc1e73caf514f
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 20%

---

# Verwalten von Audiences

Zielgruppen können im Customer Journey Analytics mit **[!UICONTROL Komponenten]** > **[!UICONTROL Zielgruppen]** verwaltet werden.

Die Verwaltung zuvor erstellter Audiences ermöglicht Ihnen Folgendes:

* **Erstellen eines Zeitplans bzw. Aufhebung des Zeitplans** für die automatische Aktualisierung der Zielgruppe. Die maximale Gültigkeit des Zeitplans beträgt 1 Jahr.
* **Verlängern Sie einen Zeitplan für die Aktualisierung der Zielgruppe**, bevor er abläuft. Vor der Beendigung der Zielgruppen-Aktualisierung erhält der Administrierende ähnlich wie bei der Beendigung von geplanten Berichten einen Monat vor Ablauf des Zeitplans eine E-Mail.
* Anzeigen des **Aktualisierungsintervalls** und des **letzten Aktualisierens einer Audience**
* Gewinnen Sie Einblicke in die **Zeitdauer, die zum Erstellen einer Audience erforderlich war** von Customer Journey Analytics. Und wie lange es dauerte, bis die Zielgruppe zur Aktivierung in der Echtzeit-Kundenplattform angezeigt wurde.
* Überprüfen Sie, ob die Zielgruppen in Customer Journey Analytics **aktiv von der Echtzeit-Kundenplattform verwendet werden**. Oder (idealerweise) alle Experience Platform-Anwendungen, die die durch Customer Journey Analytics erstellten Zielgruppen nutzen.

Wenn Sie Zugriff auf die [Zielgruppenansicht](/help/technotes/access-control.md#user-level-access) haben, können Sie Zielgruppen anzeigen. Wenn Sie Zugriff auf [Zielgruppe erstellen](/help/technotes/access-control.md#user-level-access) haben, können Sie Zielgruppen bearbeiten und löschen. Die Liste [Zielgruppen](#audiences-list) zeigt die Zielgruppen an.

## Zielgruppenliste

Die Liste Zielgruppen enthält Spalten für:

| Spalte | Beschreibung |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | Wenn eine oder mehrere Zielgruppen ausgewählt sind, wird am unteren Rand der Benutzeroberfläche &quot;Zielgruppen&quot;eine blaue Aktionsleiste angezeigt. Weitere Informationen finden Sie unter [Aktionen](#actions) . |
| **[!UICONTROL Titel und Beschreibung]** | Der Titel und die Beschreibung, die Sie beim Erstellen der Audience eingegeben haben. |
| **[!UICONTROL Datenansicht]** | Die Datenansicht, in der diese Zielgruppe erstellt wurde. |
| **[!UICONTROL Zielgruppengröße]** | Die Gesamtzahl der Personen in dieser Zielgruppe. |
| **[!UICONTROL Inhaber]** | Der Eigentümer der Zielgruppe - die Person, die die Zielgruppe erstellt hat. |
| **[!UICONTROL Häufigkeit der Aktualisierung]** | Das bei der Erstellung der Audience konfigurierte Aktualisierungsintervall. |
| **[!UICONTROL Tags]** | Alle Tags, die auf diese Zielgruppe angewendet werden. |
| **[!UICONTROL Veröffentlichungsstatus]** | Kann ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Bereit]**, ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Gestartet]** oder ![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Fehler]** anzeigen. |
| **[!UICONTROL Zuletzt aktualisiert]** | Zeitstempel der letzten Aktualisierung der Audience. |
| **[!UICONTROL Zuletzt geändert]** | Zeitstempel der letzten Bearbeitung oder Änderung der Audience. |

Mit ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) können Sie konfigurieren, welche Spalten angezeigt werden sollen. Suchen Sie mithilfe von ![Suche](/help/assets/icons/Search.svg) nach einer Zielgruppe.

So bearbeiten Sie eine Zielgruppe:

1. Wählen Sie den Titel der Audience aus. Verwenden Sie das Dialogfeld **[!UICONTROL Zielgruppenprojekt bearbeiten]** , um die Zielgruppe zu aktualisieren. Weitere Informationen finden Sie unter [Audience Builder](publish.md#audience-builder) .

1. Wählen Sie **[!UICONTROL Neu veröffentlichen]** aus, um die Zielgruppe erneut zu veröffentlichen.


## Aktionen

Im Folgenden finden Sie allgemeine Aktionen im Manager für geplante Projekte. Sie können Aktionen im Kontextmenü auswählen:

| Symbol | Aktion | Beschreibung |
|:---:|---|---|
| ![Bezeichnungen](/help/assets/icons/Labels.svg) | **[!UICONTROL Tag]** | Markieren Sie die ausgewählten Zielgruppen. Wählen Sie im Dialogfeld **[!UICONTROL Tags aktualisieren: *Zielgruppenname *]**die gewünschten Tags aus dem Dropdown-Menü aus oder geben Sie einen oder mehrere neue Tags ein. Wählen Sie**[!UICONTROL Speichern ]**aus, um zu speichern. |
| ![Löschen](/help/assets/icons/Delete.svg) | **[!UICONTROL Löschen]** | Löschen Sie die ausgewählten Zielgruppen. |
| ![Bearbeiten](/help/assets/icons/Edit.svg) | **[!UICONTROL Umbenennen]** | Benennen Sie die ausgewählte Zielgruppe um. Verwenden Sie das Dialogfeld **[!UICONTROL Umbenennen: *Audience name *]**, um die Audience umzubenennen, und wählen Sie zum Speichern**[!UICONTROL Speichern ]**aus. |

Die folgenden Aktionen sind in der blauen Aktionsleiste verfügbar, wenn Sie ein oder mehrere geplante Projekte auswählen.

| Symbol | Aktion | Beschreibung |
|:---:|---|---|
| ![close](/help/assets/icons/Close.svg) | **[!UICONTROL *x *selected]** | Wählen Sie diese Option aus, um die Auswahl der ausgewählten Zielgruppen aufzuheben. |
| ![Löschen](/help/assets/icons/Delete.svg) | **[!UICONTROL Löschen]** | Löschen Sie die ausgewählten Zielgruppen. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL In CSV exportieren]** | Exportieren Sie die ausgewählten Zielgruppen in eine Datei mit dem Namen `audiences.csv`. |

## Filter

Sie können die Liste der Zielgruppen [1} mithilfe des Filterbedienfelds filtern. ](#audiences-list) Verwenden Sie ![Filter](/help/assets/icons/Filter.svg), um den Filterbereich ein- oder auszublenden.

Das Filterbedienfeld besteht aus den folgenden Abschnitten.

### Datenansicht

| Datenansicht | Beschreibung |
|---|---|
| ![Inhaber](/help/components/audiences/assets/audiences-filter-dataviews.png){width="300"} | Im Abschnitt **[!UICONTROL Datenansicht]** können Sie nach Datenansichten filtern. <ul><li>Sie verwenden ![Suche](/help/assets/icons/Search.svg) , um nach Datenansichten zu suchen, die Sie zum Filtern verwenden möchten.</li><li>Sie können mehrere Datenansichten auswählen.</li></ul> |

### Inhaber

| Verantwortlicher | Beschreibung |
|---|---|
| ![Inhaber](/help/components/audiences/assets/audiences-filter-owner.png){width="300"} | Im Abschnitt **[!UICONTROL Inhaber]** können Sie nach Eigentümern filtern. <ul><li>Sie verwenden ![Suche](/help/assets/icons/Search.svg), um nach Eigentümern zu suchen, die Sie zum Filtern verwenden möchten.</li><li>Sie können mehrere Inhaber auswählen. </li></ul> |

## Häufigkeit der Aktualisierung

| Häufigkeit der Aktualisierung | Beschreibung |
|---|---|
| ![Häufigkeit der Aktualisierung](/help/components/audiences/assets/audiences-filter-refreshfrequency.png){width="300"} | Im Abschnitt **[!UICONTROL Aktualisierungshäufigkeit]** können Sie nach Aktualisierungshäufigkeit filtern. <ul><li>Sie verwenden ![Suche](/help/assets/icons/Search.svg) , um nach der Aktualisierungshäufigkeit zu suchen, die Sie zum Filtern verwenden möchten.</li><li>Als verfügbare Optionen werden nur die Aktualisierungsfrequenzen angezeigt, die für die Zielgruppen<br/> in der Liste [Zielgruppen](#audiences-list) definiert sind.</li></ul> |


### Tags

| Tags | Beschreibung |
|---|---|
| ![Tags](/help/components/audiences/assets/audiences-filter-tags.png){width="300"} | Im Abschnitt **[!UICONTROL Tags]** können Sie nach Tags filtern. <ul><li>Sie verwenden ![Suche](/help/assets/icons/Search.svg) , um nach Tags zu suchen, die Sie zum Filtern verwenden möchten. |
