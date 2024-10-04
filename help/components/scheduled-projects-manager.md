---
description: In Analysis Workspace gibt es zwei Möglichkeiten zur Verwendung von Metriken.
title: Metriken
feature: Components
exl-id: fa7c5a0f-4983-40ee-b9c1-3e10aab3fc28
role: User
source-git-commit: 8676497c9341e3ff74d1b82ca79bc1e73caf514f
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 15%

---

# Geplante Projekte

Geplante Analysis Workspace-Projekte können unter Customer Journey Analytics mit **[!UICONTROL Komponenten]** > **[!UICONTROL Geplante Projekte]** verwaltet werden.

In **[!UICONTROL Geplante Projekte]** können Sie wiederkehrende Projektpläne bearbeiten und löschen.  Die Liste [Geplantes Projekt](#scheduled-project-list) enthält die Elemente, die ein bestimmter Benutzer erstellt hat. Wenn das Benutzerkonto in der Anwendung deaktiviert ist, werden alle geplanten Sendungen angehalten.

![Benutzeroberfläche für geplante Projekte](assets/scheduled-projects.png)

## Liste geplanter Projekte

In der Liste Geplante Projekte werden Spalten für Folgendes angezeigt:

| Spalte | Beschreibung |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | Wenn ein oder mehrere geplante Projekte ausgewählt sind, wird am unteren Rand der Benutzeroberfläche für geplante Projekte eine blaue Aktionsleiste angezeigt. Weitere Informationen finden Sie unter [Aktionen](#actions) . |
| ![Stern](/help/assets/icons/Star.svg) | Wählen Sie diese Option aus, um ![Star](/help/assets/icons/Star.svg) zu favorisieren oder ![StarOutline](/help/assets/icons/StarOutline.svg) für ein geplantes Projekt zu bevorzugen. |
| **[!UICONTROL Zeitplan-ID]** | Eine ID, die hauptsächlich zum Debugging verwendet wird. |
| **[!UICONTROL Name]** | Name dieses Projekts.<br/>Wählen Sie ![InfoOutline](/help/assets/icons/InfoOutline.svg) aus, um weitere Details für das geplante Projekt anzuzeigen.<br/>Wählen Sie ![Mehr](/help/assets/icons/More.svg) aus, um ein Kontextmenü zu öffnen. In diesem Menü haben Sie folgende Möglichkeiten:<ul><li>![Löschen](/help/assets/icons/Delete.svg) **[!UICONTROL Löschen]** eines geplanten Projekts.</li><li>![Beschriftungen](/help/assets/icons/Labels.svg) **[!UICONTROL Taggen]** eines geplanten Projekts.</li><li>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Genehmigen]** Sie ein geplantes Projekt.</li><li>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL CSV exportieren]**: Exportieren Sie ein geplantes Projekt in eine CSV-Datei.</li></ul> |
| **[!UICONTROL Inhabende]** | Die Person, die das Projekt erstellt hat und dafür verantwortlich ist. |
| **[!UICONTROL Tags]** | (Optional) Mit Tagging können Projekte praktisch organisiert werden. Alle Benutzer können Tags erstellen und eines oder mehrere Tags auf ein Projekt anwenden. Sie sehen Tags jedoch nur für die Projekte, deren Verantwortlicher Sie sind oder die für Sie freigegeben wurden. |
| **[!UICONTROL Gesendet an]** | Die Empfänger dieses geplanten Projekts. |
| **[!UICONTROL Ablaufdatum]** | Sie können das Ablaufdatum auf bis zu ein Jahr festlegen, unabhängig von der Häufigkeit des Zeitplans. |
| **[!UICONTROL Häufigkeit]** | Wie oft Sie möchten, dass dieses Planprojekt an einen oder mehrere Empfänger gesendet wird. |
| **[!UICONTROL Ausführungszeit]** | Zu welcher Tageszeit dieses geplante Projekt gesendet wird.  |
| **[!UICONTROL Anzahl der Abfragen]** | Die Anzahl der Abfragen für dieses Projekt. |
| **[!UICONTROL Längster Datumsbereich]** | Der längste für das geplante Projekt definierte Datumsbereich. Dieser Wert kann für die Untersuchung von Leistungsproblemen relevant sein. Weitere Informationen finden Sie unter [Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md) . |
| **[!UICONTROL Anzahl der Abfragen]** | Die Anzahl der Abfragen, die für das geplante Projekt ausgeführt werden. Dieser Wert kann für die Untersuchung von Leistungsproblemen relevant sein. Weitere Informationen finden Sie unter [Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md) . |


Mit ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) können Sie konfigurieren, welche Spalten angezeigt werden sollen.

Suchen Sie mithilfe von ![Suche](/help/assets/icons/Search.svg) nach einem geplanten Projekt. Sie können auch sehen, ob im Bedienfeld &quot;Filter&quot;Filter angewendet werden. Um einen Filter zu entfernen, wählen Sie für einen Filter ![CrossSize75](/help/assets/icons/CrossSize75.svg) aus. Um alle Filter zu entfernen, wählen Sie **[!UICONTROL Alle löschen]** aus.

Um ein geplantes Projekt zu bearbeiten, wählen Sie den Titel des geplanten Projekts aus. Verwenden Sie das Dialogfeld **[!UICONTROL Geplantes Projekt bearbeiten]** , um die Zeitplandetails zu aktualisieren.

![Geplantes Projekt bearbeiten](assets/edit-scheduled-project.png)

Wählen Sie **[!UICONTROL Aktualisieren]** aus, um den Zeitplan zu aktualisieren.




## Aktionen

Im Folgenden finden Sie allgemeine Aktionen im Manager für geplante Projekte. Sie können Aktionen im Kontextmenü oder in der blauen Aktionsleiste auswählen, wenn Sie ein oder mehrere geplante Projekte auswählen.

| Symbol | Aktion | Beschreibung |
|:---:|---|---|
| ![close](/help/assets/icons/Close.svg) | **[!UICONTROL *x *selected]** | Wählen Sie diese Option aus, um die Auswahl der ausgewählten geplanten Projekte aufzuheben. |
| ![Löschen](/help/assets/icons/Delete.svg) | **[!UICONTROL Löschen]** | Löschen Sie die ausgewählten geplanten Projekte für das Projekt. Die Projekte werden nicht gelöscht. |
| ![Bezeichnungen](/help/assets/icons/Labels.svg) | **[!UICONTROL Tag]** | Taggen Sie die ausgewählten geplanten Projekte. Wählen Sie in **[!UICONTROL Geplante Projekte taggen]** Tags aus und wählen Sie zum Speichern **[!UICONTROL Speichern]** aus. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Genehmigen]** | Genehmigen Sie die ausgewählten geplanten Projekte. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL In CSV exportieren]** | Exportieren Sie die ausgewählten geplanten Projekte in eine Datei mit dem Namen `Export Scheduled Projects List.csv`. |


## Filter

Sie können die geplanten Projekte mit der Liste &quot;Geplantes Projekt&quot;[Geplant](#scheduled-project-list) im Filterbereich &quot;Geplant&quot; filtern. Verwenden Sie ![Filter](/help/assets/icons/Filter.svg), um den Filterbereich ein- oder auszublenden.

Das Filterbedienfeld besteht aus den folgenden Abschnitten.

### Tags

| Tags | Beschreibung |
|---|---|
| ![Tags](/help/components/assets/scheduledprojects-filter-tags.png){width="300"} | Im Abschnitt **[!UICONTROL Tags]** können Sie nach Tags filtern. <ul><li>Sie verwenden ![Suche](/help/assets/icons/Search.svg) **[!UICONTROL Tags durchsuchen]**, um nach Tags zu suchen, die Sie zum Filtern verwenden möchten.</li><li>Sie können mehr als ein Tag auswählen. Die verfügbaren Tags hängen von der Auswahl ab, die in anderen Abschnitten des Filterbereichs vorgenommen wurde.</li><li>Die Zahlen geben an:<ul><li>7︎⃣: Die Anzahl der geplanten Projekte, die mit dem spezifischen Tag verknüpft sind.</li></ul></li></ul> |


### Inhaber

| Verantwortlicher | Beschreibung |
|---|---|
| ![Inhaber](/help/components/assets/scheduledprojects-filter-owners.png){width="300"} | Im Abschnitt **[!UICONTROL Inhaber]** können Sie nach Eigentümern filtern. <ul><li>Sie verwenden ![Suche](/help/assets/icons/Search.svg) *Inhaber durchsuchen*, um nach Eigentümern zu suchen, die Sie zum Filtern verwenden möchten.</li><li>Sie können mehrere Inhaber auswählen. Die verfügbaren Inhaber hängen von der Auswahl ab, die in anderen Abschnitten des Filterbereichs vorgenommen wurde.</li><li>Die Zahlen geben an:<ul><li>4︎⃣: Die Anzahl der geplanten Projekte, die mit dem spezifischen Eigentümer verknüpft sind.</li></ul></li></ul> |


### Sonstige Filter

| Sonstige Filter | Beschreibung |
|---|---|
| ![Sonstige Filter](/help/components/assets/scheduledprojects-filter-otherfilters.png){width="300"} | Im Bereich **[!UICONTROL Sonstige Filter]** können Sie nach anderen vordefinierten Filtern filtern.<ul><li>Sie können eine oder mehrere der folgenden Optionen auswählen:<ul><li> **[!UICONTROL Abgelaufen]**: Filtern nach abgelaufenen geplanten Projekten.</li><li>**[!UICONTROL Fehlgeschlagen]**: Filtern Sie nach geplanten Projekten, für die der Zeitplan fehlgeschlagen ist.</li></ul>Was Sie auswählen können, hängt von Ihrer Rolle und Ihren Berechtigungen ab.</li><li>Sie können mehrere Filter auswählen. Die anderen verfügbaren Filter hängen von der Auswahl ab, die in anderen Abschnitten des Filterbereichs vorgenommen wurde.</li><li>Die Zahlen geben an:<ul><li>4︎⃣: Die Anzahl der geplanten Projekte, die mit dem spezifischen anderen Filter verknüpft sind.</li></ul></li></ul> |
