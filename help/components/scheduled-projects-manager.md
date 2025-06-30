---
description: In Analysis Workspace gibt es zwei Möglichkeiten zur Verwendung von Metriken.
title: Metriken
feature: Components
exl-id: fa7c5a0f-4983-40ee-b9c1-3e10aab3fc28
role: User
source-git-commit: 70daf2251576bc3b473e63b3bb7c48f2d16dbffe
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 42%

---

# Geplante Projekte

Geplante Analysis Workspace-Projekte können in Customer Journey Analytics mithilfe von **[!UICONTROL Komponenten]** > **[!UICONTROL Geplante Projekte]** verwaltet werden.

In **[!UICONTROL Geplante Projekte]** können Sie wiederkehrende Projektzeitpläne bearbeiten und löschen.  Die [Geplante Projektliste](#scheduled-project-list) zeigt die Elemente an, die ein bestimmter Benutzer erstellt hat. Wenn das Benutzerkonto in der Anwendung deaktiviert ist, werden alle geplanten Sendungen gestoppt.

![Benutzeroberfläche für geplante Projekte](assets/scheduled-projects.png)

## Geplante Projektliste

Die ➊ Geplante Projekte enthält Spalten für:

| Spalte | Beschreibung |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | Wenn ein oder mehrere geplante Projekte ausgewählt werden, wird unten in der Benutzeroberfläche Geplante Projekte eine blaue Aktionsleiste angezeigt. Weitere Informationen finden Sie unter [Aktionen](#actions). |
| ![Stern](/help/assets/icons/Star.svg) | Wählen Sie aus![ um ein geplantes Projekt ](/help/assets/icons/Star.svg)![ StarOutline](/help/assets/icons/StarOutline.svg) zu bevorzugen oder zu deaktivieren. |
| **[!UICONTROL Zeitplan-ID]** | Eine ID, die hauptsächlich zum Debuggen verwendet wird. |
| **[!UICONTROL Name]** | Name dieses Projekts.<br/>Wählen Sie ![InfoOutline](/help/assets/icons/InfoOutline.svg) aus, um weitere Details für das geplante Projekt anzuzeigen.<br/>Wählen Sie ![Mehr](/help/assets/icons/More.svg), um ein Kontextmenü zu öffnen. In diesem Menü haben Sie folgende Möglichkeiten:<ul><li>![Löschen](/help/assets/icons/Delete.svg) **[!UICONTROL Löschen]** eines geplanten Projekts.</li><li>![Labels](/help/assets/icons/Labels.svg) **[!UICONTROL Tag]** ein geplantes Projekt.</li><li>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Genehmigen]** ein geplantes Projekt.</li><li>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL CSV exportieren]**: Exportieren eines geplanten Projekts in eine CSV-Datei.</li></ul> |
| **[!UICONTROL Inhabende]** | Die Person, die das Projekt erstellt hat und dafür verantwortlich ist. |
| **[!UICONTROL Tags]** | (Optional) Mit Tagging können Projekte praktisch organisiert werden. Alle Benutzer können Tags erstellen und eines oder mehrere Tags auf ein Projekt anwenden. Sie sehen Tags jedoch nur für die Projekte, deren Verantwortlicher Sie sind oder die für Sie freigegeben wurden. |
| **[!UICONTROL Gesendet an]** | Die Empfänger dieses geplanten Projekts. |
| **[!UICONTROL Ablaufdatum]** | Sie können das Ablaufdatum auf bis zu ein Jahr festlegen, unabhängig von der Häufigkeit des Zeitplans. |
| **[!UICONTROL Häufigkeit]** | Wie oft dieses geplante Projekt an einen oder mehrere Empfänger gesendet werden soll. |
| **[!UICONTROL Durchführungszeit]** | Zu welcher Tageszeit dieses geplante Projekt gesendet wird. |
| **[!UICONTROL Anzahl der Abfragen]** | Die Anzahl der Abfragen für dieses Projekt. |
| **[!UICONTROL Längster Datumsbereich]** | Der längste für das geplante Projekt definierte Datumsbereich. Dieser Wert kann für die Untersuchung von Leistungsproblemen relevant sein. Weitere Informationen finden [ unter „Reporting ](/help/reporting-activity-manager/reporting-activity-overview.md) Manager“. |
| **[!UICONTROL Anzahl der Abfragen]** | Die Anzahl der für das geplante Projekt ausgeführten Abfragen. Dieser Wert kann für die Untersuchung von Leistungsproblemen relevant sein. Weitere Informationen finden [ unter „Reporting ](/help/reporting-activity-manager/reporting-activity-overview.md) Manager“. |


Sie können mit ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) konfigurieren, welche Spalten angezeigt werden sollen.

Suchen Sie mithilfe von „Suchen![ nach einem geplanten Projekt](/help/assets/icons/Search.svg). Sie können auch im Bedienfeld Filter sehen, ob Filter angewendet werden. Um einen Filter zu entfernen, wählen Sie ![CrossSize](/help/assets/icons/CrossSize75.svg) für einen Filter aus. Um alle Filter zu entfernen, wählen Sie **[!UICONTROL Alle löschen]** aus.

Um ein geplantes Projekt zu bearbeiten, wählen Sie den Titel des geplanten Projekts aus. Aktualisieren Sie die Zeitplandetails **[!UICONTROL Dialogfeld „Geplantes Projekt]** bearbeiten“. Siehe [Senden von Dateien an andere](../analysis-workspace/curate-share/t-schedule-report.md) für weitere Details.

![Geplantes Projekt bearbeiten](assets/edit-scheduled-project.png)

Wählen Sie **[!UICONTROL Aktualisieren]** aus, um den Zeitplan zu aktualisieren.




## Aktionen

Die folgenden Aktionen werden im Manager für geplante Projekte häufig ausgeführt. Sie können Aktionen im Kontextmenü oder in der blauen Aktionsleiste auswählen, wenn Sie ein oder mehrere geplante Projekte auswählen.

| Symbol | Aktion | Beschreibung |
|:---:|---|---|
| ![Schließen](/help/assets/icons/Close.svg) | **[!UICONTROL *x *ausgewählt]** | Wählen Sie aus, um die Auswahl der geplanten Projekte aufzuheben. |
| ![Löschen](/help/assets/icons/Delete.svg) | **[!UICONTROL Löschen]** | Die ausgewählten geplanten Projekte für das Projekt löschen; die Projekte werden nicht gelöscht. |
| ![Bezeichnungen](/help/assets/icons/Labels.svg) | **[!UICONTROL Tag]** | Markieren Sie die ausgewählten geplanten Projekte. Wählen Sie in **[!UICONTROL Geplante Projekte taggen]** und klicken Sie zum Speichern **[!UICONTROL Speichern]**. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Genehmigen]** | Genehmigen Sie die ausgewählten geplanten Projekte. |
| ![CSV-Datei](/help/assets/icons/FileCSV.svg) | **[!UICONTROL In CSV exportieren]** | Exportieren Sie die ausgewählten geplanten Projekte in eine Datei mit dem Namen `Export Scheduled Projects List.csv`. |


## Filter

Sie können die geplanten Projekte [Liste geplanter Projekte](#scheduled-project-list) mithilfe des Filterbedienfelds ➌. Verwenden Sie ![Filter](/help/assets/icons/Filter.svg), um das Panel „Filter“ ein- oder auszublenden.

Das Panel „Filter“ besteht aus den folgenden Abschnitten.

### Tags

| Tags | Beschreibung |
|---|---|
| ![Tags](/help/components/assets/scheduledprojects-filter-tags.png){width="300"} | Im Abschnitt **[!UICONTROL Tags]** können Sie nach Tags filtern. <ul><li>Mit ![Search](/help/assets/icons/Search.svg) **[!UICONTROL Tags suchen]** können Sie nach Tags suchen, die Sie zum Filtern verwenden möchten.</li><li>Sie können auch mehr als ein Tag auswählen. Die verfügbaren Tags hängen von der Auswahl ab, die in anderen Abschnitten im Panel „Filter“ vorgenommen wurde.</li><li>Die Zahlen geben Folgendes an:<ul><li>7︎⃣: Die Anzahl der geplanten Projekte, die mit dem bestimmten Tag verknüpft sind.</li></ul></li></ul> |


### Inhaberinnen oder Inhaber

| Inhaberin oder Inhaber | Beschreibung |
|---|---|
| ![Inhaberinnen oder Inhaber](/help/components/assets/scheduledprojects-filter-owners.png){width="300"} | Im Abschnitt **[!UICONTROL Inhaberin oder Inhaber]** können Sie nach Inhaberinnen und Inhabern filtern. <ul><li>Sie verwenden ![Search](/help/assets/icons/Search.svg) *Verantwortliche(n) suchen*, um nach Inhaberinnen und Inhabern zu suchen, die Sie zum Filtern verwenden möchten.</li><li>Sie können mehr als eine Inhaberin bzw. einen Inhaber auswählen. Die verfügbaren Inhaberinnen und Inhaber hängen von der Auswahl ab, die in anderen Abschnitten im Panel „Filter“ vorgenommen wurde.</li><li>Die Zahlen geben Folgendes an:<ul><li>4︎⃣: Die Anzahl der geplanten Projekte, die dem jeweiligen Eigentümer zugeordnet sind.</li></ul></li></ul> |


### Andere Filter

| Andere Filter | Beschreibung |
|---|---|
| ![Sonstige Filter](/help/components/assets/scheduledprojects-filter-otherfilters.png){width="300"} | Im Abschnitt **[!UICONTROL Andere Filter]** können Sie nach anderen vordefinierten Filtern filtern.<ul><li>Sie können eine oder mehrere der folgenden Optionen auswählen:<ul><li> **[!UICONTROL Abgelaufen]**: Filtern Sie nach abgelaufenen geplanten Projekten.</li><li>**[!UICONTROL Fehlgeschlagen]**: Filtern Sie nach geplanten Projekten, bei denen der Zeitplan fehlgeschlagen ist.</li></ul>Was Sie auswählen können, hängt von Ihrer Rolle und Ihren Berechtigungen ab.</li><li>Sie können mehr als einen Filter auswählen. Die anderen verfügbaren Filter hängen von der Auswahl ab, die in anderen Abschnitten im Panel „Filter“ vorgenommen wurde.</li><li>Die Zahlen geben Folgendes an:<ul><li>4︎⃣: Die Anzahl der geplanten Projekte, die dem jeweiligen anderen Filter zugeordnet sind.</li></ul></li></ul> |
