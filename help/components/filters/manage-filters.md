---
title: Filter verwalten
description: Erfahren Sie, wie Sie Filter in Customer Journey Analytics verwalten
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: 97b831d7eee477ee7ef0bf8ae65e6a415d243464
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 4%

---

# Filter verwalten


Sie können in einer zentralen Verwaltungsoberfläche für [!UICONTROL Filter] die Optionen [share](filters-share.md), [filter](filters-filter.md), [tag](filters-tag.md), [approve](filters-approve.md), rename, [copy](filters-copy.md), delete, export filters und mark als [favorite](filters-favorite.md) markieren. So verwalten Sie Filter:

* Wählen Sie **[!UICONTROL Komponenten]** in der Hauptbenutzeroberfläche und dann **[!UICONTROL Filter]** aus.


>[!NOTE]
>
>Die Schnellfilter, die Sie in einem bestimmten Workspace-Projekt erstellen, werden nicht im Manager [!UICONTROL Filter] angezeigt, es sei denn, Sie haben den Filter für alle Ihre Projekte verfügbar gemacht.
>

## Filter Manager

Der Filter-Manager verfügt über die folgenden Elemente der Benutzeroberfläche:

![Filterschnittstelle](assets/filters-manager.png)

### Filterliste

In der Filterliste werden alle Filter angezeigt, die Ihnen gehören, die für alle Ihre Projekte Filter und die für Sie freigegebenen Filter. Die Liste enthält die folgenden Spalten:

| Spalte | Beschreibung |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Wählen Sie diese Option aus, um einen Filter für ![Star](/help/assets/icons/Star.svg) oder für ![StarOutline](/help/assets/icons/StarOutline.svg) zu bevorzugen. Siehe [Filter als Favoriten markieren](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL Titel und Beschreibung]** | Um den Filter zu bearbeiten, wählen Sie den Titel-Link aus, der den [Filter-Builder](filter-builder.md) öffnet. Ein freigegebener Filter wird mit ![Freigabe](/help/assets/icons/ShareAlt.svg) angegeben. |
| **[!UICONTROL Datenansicht]** | Die Datenansichten, für die dieser Filter gilt. |
| **[!UICONTROL Inhabende]** | Der Eigentümer des Filters. Als Benutzer sehen Sie nur die Filter, deren Inhaber Sie sind, oder die Anmerkungen, die für Sie freigegeben wurden. |
| **[!UICONTROL Tags]** | Die Tags für diesen Filter. |
| **[!UICONTROL Freigegeben für]** | Wie viele Einzelpersonen oder Gruppen Sie den Filter freigegeben haben. Klicken Sie auf , um das Dialogfeld **[!UICONTROL Komponente freigeben]** zu öffnen. Weitere Informationen finden Sie unter [Filter freigeben](filters-share.md) . |
| **[!UICONTROL Datum geändert]** | Datum und Uhrzeit der letzten Änderung des Filters. |
| **[!UICONTROL Verwendet in]** | Zeigt an, wo Filter derzeit verwendet werden und wie oft sie in den einzelnen Bereichen verwendet werden. <p>Wenn der Filter beispielsweise in 40 Projekten und 2 Warnhinweisen verwendet wird, wird der Wert dieser Spalte als [!UICONTROL **42 Komponenten**] angezeigt.</p> <p>Wählen Sie den Wert in dieser Spalte aus, um die Aufschlüsselung der verwendeten Filter anzuzeigen (z. B. [!UICONTROL **Projekte (40)**], [!UICONTROL **mobile Scorecards (2)**]). Darüber hinaus können Sie die Liste der Elemente anzeigen, in denen die Filter verwendet werden. Sehen Sie sich beispielsweise die Liste der Projekte an, in denen sie verwendet werden, und klicken Sie auf den Link [!UICONTROL **Projekte (40)**] .</p><p>Jeder der folgenden Bereiche zeigt die Anzahl der in diesem Bereich verwendeten Filter:</p>  <ul><li>[!UICONTROL **Projekte**]<p>Enthält Filter, die im Filtergenerator ](/help/components/filters/filter-builder.md#) erstellt wurden und für alle Projekte verfügbar sind.[</p></li><li>[!UICONTROL **Ad-hoc-Komponenten**]<p>Enthält Filter, die [als Schnellfilter erstellt wurden](/help/components/filters/quick-filters.md) und nur in einem Projekt verfügbar sind.</p></li><li>[!UICONTROL **Geplante Projekte**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Anmerkungen**]</li><li>[!UICONTROL **Berechnete Metriken**]</li><li>[!UICONTROL **Report Builder**]<p>Wenn Sie diese Option auswählen, wird eine CSV-Datei mit den folgenden Datenspalten heruntergeladen:</p><ul><li>Name des Report Builders</li><li>Zuletzt aufgerufen</li><li>Letzter Zugriff auf IMS-Benutzer-ID</li><li>Letzter Benutzername</li></ul></li></ul><p>Diese Informationen helfen Ihnen dabei festzustellen, ob eine Komponente für Benutzer in Ihrer Organisation nützlich ist, wo die Komponente verwendet wird und ob die Komponente gelöscht oder geändert werden muss.</p><p>Beachten Sie Folgendes beim Anzeigen dieser Option:</p><ul><li>Diese Informationen sind nur für Systemadministratoren verfügbar.</li><li>Die Spalte [!UICONTROL **Verwendet in**] wird nicht standardmäßig angezeigt. Verwenden Sie ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) , um die Anzeige dieser Spalte zu konfigurieren.</li><li>Diese Informationen enthalten keine Verwendung über die API oder Data Warehouse.</li><li>Wenn in dieser Spalte keine Daten für eine bestimmte Komponente vorhanden sind, die Komponente jedoch das Datum [!UICONTROL **Zuletzt verwendet**] hat, wurde die Komponente möglicherweise in einer Analyse verwendet, ohne gespeichert zu werden.</li><li>Nutzungsinformationen sind ab September 2023 verfügbar.</li></ul><p>Sie können das [Datenwörterbuch](/help/components/data-dictionary/data-dictionary-overview.md) zusammen mit diesen Informationen verwenden, um die Verwendung von Komponenten in Ihrer Organisation zu verfolgen und besser zu verstehen.</p> |
| **[!UICONTROL Zuletzt verwendet]** | Zeitpunkt der letzten Verwendung des Filters. |

{style="table-layout:auto"}

Verwenden Sie ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) , um anzugeben, welche Spalten angezeigt werden sollen.

### Symbolleiste

Mithilfe der Aktionsleiste können Sie Filter bearbeiten. Die Aktionsleiste enthält die folgenden Aktionen:

| Aktion | Beschreibung |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | Fügen Sie mit dem [Filter-Builder](filter-builder.md) einen weiteren Filter hinzu. |
| ![Suche](/help/assets/icons/Search.svg) [!UICONTROL *Suche nach Titel*] | Wenn in der Liste kein Filter ausgewählt ist, suchen Sie mithilfe dieses Suchfelds nach Filtern. |
| ![Beschriftung](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Markieren Sie die ausgewählten Filter. Wählen Sie im Dialogfeld **[!UICONTROL Tag-Filter]** die Tags für die ausgewählten Filter aus oder deaktivieren Sie sie. Wählen Sie **[!UICONTROL Speichern]** aus, um die Tags für die ausgewählten Filter zu speichern. Weitere Informationen finden Sie unter [Filter taggen](/help/components/filters/filters-tag.md) . |
| ![share](/help/assets/icons/ShareAlt.svg) **[!UICONTROL share]** | Geben Sie die ausgewählten Filter frei. Im Dialogfeld **[!UICONTROL Filter freigeben]** können Sie ![Search](/help/assets/icons/Search.svg) *Search Individues or groups* auswählen oder Sie können **[!UICONTROL Organisation]** oder **[!UICONTROL Gruppen]** auswählen. Wählen Sie **[!UICONTROL Speichern]** aus, um Freigabedetails für die ausgewählten Filter zu speichern. Weitere Informationen finden Sie unter [Filter freigeben](filters-share.md) . |
| ![Löschen](/help/assets/icons/Delete.svg) **[!UICONTROL Löschen]** | Löschen Sie die ausgewählten Filter. Sie werden zur Bestätigung aufgefordert. |
| ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Umbenennen]** | Benennen Sie einen einzelnen ausgewählten Filter um. Wenn diese Option aktiviert ist, können Sie den Filter inline umbenennen. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** | Genehmigen Sie die ausgewählten Filter. Weitere Informationen finden Sie unter [Filter genehmigen](filters-approve.md) . |
| ![Kopieren](/help/assets/icons/Copy.svg) **[!UICONTROL Kopieren]** | Kopieren Sie den ausgewählten Filter. Neue Filter werden mit demselben Namen und Suffix `(Copy)` erstellt. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export in CSV]** | Exportieren Sie die Filter in eine `Filters List.csv` -Datei. |

### Aktive Filterleiste

Die Filterleiste zeigt die aktiven Filter an, die aus dem Filterbereich auf die Liste angewendet werden (falls vorhanden). Mit ![CrossSize75](/help/assets/icons/CrossSize75.svg) können Sie schnell einen Filter entfernen. Wenn mehr als ein Filter angegeben ist, können Sie alle Filter mit **[!UICONTROL Alle entfernen]** entfernen.

### Filterbereich

Sie können die Filterliste mithilfe des linken Fensterbereichs ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** filtern. Im Filterbereich werden der Filtertyp und die Anzahl der Filter angezeigt, die den jeweiligen Filter berücksichtigen. Wählen Sie ![Filter](/help/assets/icons/Filter.svg) aus, um die Anzeige des Filterbereichs umzuschalten.

Weitere Informationen finden Sie unter [Filtern der Filterliste](filters-filter.md) .
