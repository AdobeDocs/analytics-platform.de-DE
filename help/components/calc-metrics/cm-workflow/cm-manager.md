---
description: Mit dem Manager für berechnete Metriken können Sie freigeben, filtern, taggen, genehmigen, kopieren, löschen und als Favoriten markieren.
title: Manager für berechnete Metriken
feature: Calculated Metrics
exl-id: 8b257ecc-a596-4b34-ac26-eda16835f1ba
source-git-commit: b3c7ceedec7b3f6a916e97bab38fd55f1d6c7f51
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 29%

---

# Berechnete Metriken verwalten

Sie können berechnete Metriken freigeben, filtern, taggen, genehmigen, umbenennen, kopieren, löschen, exportieren und berechnete Metriken über eine zentrale Verwaltungsoberfläche [!UICONTROL Berechnete &#x200B;]&quot; als Favoriten markieren. So verwalten Sie berechnete Metriken:


* Wählen Sie **[!UICONTROL Hauptbenutzeroberfläche]** Komponenten“ und dann **[!UICONTROL Berechnete Metriken]** aus.


## Manager für berechnete Metriken

Der Manager für berechnete Metriken verfügt über die folgenden Schnittstellenelemente:


![Benutzeroberfläche des Managers für berechnete Metriken](assets/calculated-metrics-manager.png)

### Liste der berechneten Metriken

Die ➊ Liste Berechnete Metriken zeigt alle berechneten Metriken an, deren Inhaber Sie sind oder die für Sie freigegeben wurden. Die Liste umfasst die folgenden Spalten:

<!-- I think this table incorrectly talks about quick calculated metrics -->

| Spalte | Beschreibung |
| --- | --- | 
| ![UnausgefüllterStern](/help/assets/icons/StarOutline.svg) | Wählen Sie aus![ um eine berechnete Metrik ](/help/assets/icons/Star.svg)StarOutline![ zu bevorzugen oder ](/help/assets/icons/StarOutline.svg). Siehe [Berechnete Metrik als Favorit markieren](/help/components/segments/seg-favorite.md) |
| **[!UICONTROL Titel und Beschreibung]** | Um die berechnete Metrik zu bearbeiten, wählen Sie den Titel-Link aus, über den der [Generator für berechnete Metriken“ ](cm-build-metrics.md) wird. Eine freigegebene berechnete Metrik wird mit ![Freigabe](/help/assets/icons/ShareAlt.svg) angegeben. |
| **[!UICONTROL Datenansicht]** | Die Datenansichten, für die diese berechnete Metrik gilt. |
| **[!UICONTROL Inhabende]** | Inhaber der berechneten Metrik. Benutzende können nur die Anmerkungen sehen, die ihnen gehören oder die für sie freigegeben wurden. |
| **[!UICONTROL Tags]** | Listet die Tags für diese berechnete Metrik auf. |
| **[!UICONTROL Freigegeben für]** | Listet auf, für wie viele Einzelpersonen oder Gruppen Sie die berechnete Metrik freigegeben haben. Wählen Sie aus, um das Dialogfeld **[!UICONTROL Berechnete Metrik freigeben]** zu öffnen. Weitere Informationen [ Sie unter ](cm-sharing.md) berechneter Metriken freigeben . |
| **[!UICONTROL Änderungsdatum]** | Datum und Uhrzeit der letzten Änderung der berechneten Metrik. |
| **[!UICONTROL Verwendet in]** | Zeigt an, wo berechnete Metriken derzeit verwendet werden und wie oft sie in den einzelnen Bereichen verwendet werden. <p>Wenn die berechnete Metrik beispielsweise in 40 Projekten und 2 Warnhinweisen verwendet wird, wird der Wert dieser Spalte als [!UICONTROL **42 Komponenten**] angezeigt. <p>Wählen Sie den Wert in dieser Spalte aus, um die Aufschlüsselung anzuzeigen, wo die berechneten Metriken verwendet werden (z. B. [!UICONTROL **Projekte (40)**], [!UICONTROL **Mobile Scorecards (2)**]). Darüber hinaus können Sie die Liste der Elemente anzeigen, in denen die berechneten Metriken verwendet werden. Um beispielsweise die Liste der Projekte anzuzeigen, in denen sie verwendet werden, klicken Sie auf den Link [!UICONTROL **Projekte (40)**].</p><p>Jeder der folgenden Bereiche zeigt die Anzahl der Instanzen berechneter Metriken an, die in diesem Bereich verwendet werden:</p> <ul><li>[!UICONTROL **Projekte**]<p>Enthält berechnete Metriken, [ im Generator für berechnete Metriken erstellt wurden ](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) für alle Projekte verfügbar sind.</p></li><li>[!UICONTROL **Ad-hoc-Komponenten**]<p>Enthält berechnete Metriken, [ als schnelle berechnete Metriken erstellt wurden ](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) nur in einem einzigen Projekt verfügbar sind.</p></li><li>[!UICONTROL **Geplante Projekte**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Anmerkungen**]</li><li>[!UICONTROL **Report Builder**]<p>Wenn Sie diese Option wählen, wird eine CSV-Datei mit den folgenden Datenspalten heruntergeladen:</p><ul><li>Report Builder-Name</li><li>Letzter Zugriff</li><li>Letzter Zugriff – IMS-Benutzer-ID</li><li>Letzter Zugriff – Benutzername</li></ul></li></ul><p>Diese Informationen können Ihnen dabei helfen festzustellen, ob eine Komponente für Benutzende in Ihrer Organisation nützlich ist, wo sie verwendet wird und ob sie gelöscht oder geändert werden muss.</p><p>Beachten Sie Folgendes beim Anzeigen dieser Option:</p><ul><li>Diese Informationen stehen nur Systemadmins zur Verfügung.</li><li>Die Spalte [!UICONTROL **Verwendet in**] wird standardmäßig nicht angezeigt. Mit ![Spalteneinstellung](/help/assets/icons/ColumnSetting.svg) können Sie die Anzeige dieser Spalte konfigurieren.</li><li>Diese Informationen umfassen nicht die Nutzung über die API oder Data Warehouse.</li><li>Wenn in dieser Spalte keine Daten für eine bestimmte Komponente vorhanden sind, sie jedoch ein Datum [!UICONTROL **Zuletzt verwendet**] aufweist, wurde die Komponente möglicherweise in einer Analyse verwendet, ohne gespeichert zu werden.</li><li>Nutzungsinformationen sind ab September 2023 verfügbar.</li></ul><p>Sie können das [Datenwörterbuch](/help/components/data-dictionary/data-dictionary-overview.md) zusammen mit diesen Informationen verwenden, um die Verwendung von Komponenten in Ihrer Organisation zu verfolgen und besser zu verstehen.</p> |
| **[!UICONTROL Zuletzt verwendet]** | Wann die berechnete Metrik zuletzt verwendet wurde. |

{style="table-layout:auto"}

Verwenden Sie ![Spalteneinstellung](/help/assets/icons/ColumnSetting.svg), um die anzuzeigenden Spalten anzugeben.

### Aktionsleiste

Sie können Aktionen für Filter mithilfe der Aktionsleiste ➋. Die Aktionsleiste ermöglicht die folgenden Aktionen:

| Symbol | Aktion | Beschreibung |
|:---:|---|---|
| ![Hinzufügen](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Hinzufügen]** | Fügen Sie weitere berechnete Metriken mithilfe des Builders für [ berechnete Metriken ](cm-build-metrics.md). |
| ![Durchsuchen](/help/assets/icons/Search.svg) | [!UICONTROL *Nach Titel suchen*] | Wenn keine berechnete Metrik in der Liste ausgewählt ist, suchen Sie mithilfe dieses Suchfelds nach Filtern. |
| ![Beschriftung](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Kennzeichnen Sie die ausgewählten berechneten Metriken. Wählen Sie im **[!UICONTROL Berechnete Metrik]** Tag) die Tags für die ausgewählte berechnete Metrik aus oder heben Sie die Auswahl auf. Wählen Sie **[!UICONTROL Speichern]**, um die Tags für die ausgewählten berechneten Metriken zu speichern. Weitere Informationen finden [ unter &quot;](cm-tagging.md) Metriken taggen“. |
| ![Freigeben](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Freigeben]** | Geben Sie die ausgewählten berechneten Metriken frei. Im Dialogfeld **[!UICONTROL Berechnete Metriken freigeben]** können Sie ![Suchen](/help/assets/icons/Search.svg)*nach Einzelpersonen oder Gruppen* oder **[!UICONTROL Organisation]** oder **[!UICONTROL Gruppen]**. Wählen Sie **[!UICONTROL Speichern]**, um Freigabedetails für die ausgewählten berechneten Metriken zu speichern. Weitere Informationen [ Sie unter ](cm-sharing.md) berechneter Metriken freigeben . |
| ![Löschen](/help/assets/icons/Delete.svg) | **[!UICONTROL Löschen]** | Löscht die ausgewählten berechneten Metriken. Sie werden zur Bestätigung aufgefordert. |
| ![Bearbeiten](/help/assets/icons/Edit.svg) | **[!UICONTROL Umbenennen]** | Eine einzelne ausgewählte berechnete Metrik umbenennen. Wenn diese Option aktiviert ist, können Sie die berechnete Metrik inline umbenennen. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Genehmigen]** | Genehmigen Sie die ausgewählten berechneten Metriken. Siehe [Genehmigen von berechneten Metriken](cm-approving.md). |
| ![Kopieren](/help/assets/icons/Copy.svg) | **[!UICONTROL Kopieren]** | Kopieren Sie die ausgewählten berechneten Metriken. Neue berechnete Metriken werden mit demselben Namen und Suffix `(Copy)` erstellt |
| ![CSV-Datei](/help/assets/icons/FileCSV.svg) | **[!UICONTROL In CSV exportieren]** | Exportieren Sie die berechneten Metriken in eine `Calculated  metric List.csv`. |

### Aktive Filterleiste

Die Filterleiste zeigt ➌ die aktiven Filter an, die vom Bedienfeld Filter auf die Liste der berechneten Metriken angewendet wurden (falls vorhanden). Mit ![XGröße75](/help/assets/icons/CrossSize75.svg) können Sie schnell einen Filter entfernen. Wenn mehr als ein Filter angegeben ist, können Sie alle Filter mit **[!UICONTROL Alle entfernen]** entfernen.

### Panel „Filter“

Sie können die Liste der berechneten Metriken mithilfe der ➍ des ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** linken Bedienfelds filtern. Das Bedienfeld „Filter“ zeigt den Filtertyp und die Anzahl der berechneten Metriken an, die den spezifischen Filter berücksichtigen. Wählen Sie ![Filter](/help/assets/icons/Filter.svg) aus, um die Anzeige des Bedienfelds „Filter“ umzuschalten.

Weitere Informationen [ Sie unter „Filtern ](cm-filter.md) Liste berechneter Metriken“.


<!-- OLD CONTENT 

The Calculated metric manager shows you all the filters you own and that have been shared with you. Admin-level users can see all custom metrics in the organization. This overview presents the user interface and the capabilities of the Calculated metric manager.

![Calculated metrics window showing available filters.](assets/calc-metric-manager.png)

## Access the Calculated metrics manager

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Calculated metrics**].

## Available actions in the Calculated metrics manager

In the Calculated metrics manager, you can:

* [Filter calculated metrics](/help/components/calc-metrics/cm-workflow/cm-filter.md)

* [Mark calculated metrics as favorites](/help/components/calc-metrics/cm-workflow/cm-favorite.md)

* [Approve calculated metrics](/help/components/calc-metrics/cm-workflow/cm-approving.md)

* [Tag calculated metrics](/help/components/calc-metrics/cm-workflow/cm-tagging.md)

* [Share calculated metrics](/help/components/calc-metrics/cm-workflow/cm-sharing.md)

* Export a calculated metric to a CSV file. 

* [Copy calculated metrics](/help/components/calc-metrics/cm-workflow/cm-copy.md)

* Delete calculated metrics

## Configure columns

You can configure the information displayed for each calculated metric in the Calculated metrics manager by configuring the columns that are displayed.

To configure the visible columns in the Calculated metrics manager:

1. In Customer Journey Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Calculated metrics]**. 

1. In the Calculated metrics manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Calculated metrics manager.

   The following columns are available:

   | Column title  | Description |
   |---|---|
   | Favorites  | Displays star icons next to each calculated metric, allowing you to mark calculated metrics as favorites. For more information, see [Mark calculated metrics as favorites](/help/components/calc-metrics/cm-workflow/cm-favorite.md). |
   | Title and description | These values are provided in the Calculated metric builder. To edit the title and description, select the title link to open the Calculated metric builder.  |
   | Report suite | Indicates in which report suite the metric was last saved.  |
   | Owner | Indicates who owns the custom metric. As a non-admin, you can see only metrics you own or those that were shared with you.  |
   | Tags | Shows tags that were applied to the metric, either by you or by people who shared the calculated metric with you.  |
   | Shared with | Lists individuals or groups (admin only) or All (admin only) that you shared the calculated metric with. <p>When a calculated metric is being shared, a share icon displays next to the calculated metric name.</p>  |
   | Date modified | Indicates the date when the custom metric was last modified.  |
   | Used in | Shows where calculated metrics are currently being used, and how many times they are being used in each area. <p>For example, if the calculated metric is being used in 40 projects and 2 alerts, then the value of this column shows as [!UICONTROL **42 components**]. <p>Select the value in this column to see the breakdown of where the calculated metrics are being used (for example, [!UICONTROL **Projects (40)**], [!UICONTROL **Mobile Scorecards (2)**]). Furthermore, you can view the list of items where the calculated metrics are being used. For example, to see the list of projects where they are being used, select the [!UICONTROL **Projects (40)**] link.</p><p>Each of the following areas shows the number of instances of calculated metrics being used in that area:</p> <ul><li>[!UICONTROL **Projects**]<p>Contains calculated metrics that were [created in the calculated metric builder](/help/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects) and are available for all projects.</p></li><li>[!UICONTROL **Ad hoc components**]<p>Contains calculated metrics that were [created as quick calculated metrics ](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) and are available only within a single project.</p></li><li>[!UICONTROL **Scheduled projects**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Report Builder**]<p>Selecting this option downloads a CSV file, with the following columns of data:</p><ul><li>Report Builder Name</li><li>Last accessed</li><li>Last accessed IMS User ID</li><li>Last accessed user name</li></ul><p>When viewing information for Report Builder, usage information is available starting in September 2024.</p></li></ul><p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information is available only to system administrators.</li><li>The [!UICONTROL **Used in**] column does not display by default. [Configure columns](#configure-columns) to display it.</li><li>If a calculated metric includes another calculated metric in its definition, any use of that calculated metric is not shown in the [!UICONTROL **Used in**] column. If a calculated metric is included in the definition of another type of component (such as a segment), then usage is shown in the [!UICONTROL **Used in**] column.</li><li>This information does not include usage from the API or Data Warehouse.</li><li>If there is no data in this column for a given component but it has a [!UICONTROL **Last used**] date, the component might have been used in an analysis without being saved.</li><li>Usage information is available starting in September 2023.</li></ul><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization.</p> |
   | Last used | Shows the date when the calculated metric was last used in any of the following component types: <ul><li>Calculated metrics</li><li>Projects</li><li>Scheduled projects</li></ul> <p>This information can help you determine whether a component is valuable to users in your organization, or whether it should be deleted.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li><li>This information is available only to system administrators.</li></ul><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization. |

   {style="table-layout:auto"}

-->