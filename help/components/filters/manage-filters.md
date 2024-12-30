---
title: Filter verwalten
description: Erfahren Sie, wie Sie Filter in Customer Journey Analytics verwalten
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: 97b831d7eee477ee7ef0bf8ae65e6a415d243464
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 13%

---

# Filter verwalten


Sie können [freigeben](filters-share.md), [filter](filters-filter.md), [tag](filters-tag.md), [genehmigen](filters-approve.md), umbenennen [kopieren](filters-copy.md), löschen, Filter exportieren und ](filters-favorite.md) als [Favoriten über eine zentrale [!UICONTROL filters]-Verwaltungsoberfläche markieren. So verwalten Sie Filter:

* Wählen Sie **[!UICONTROL Hauptbenutzeroberfläche]** Komponenten“ aus und klicken Sie auf **[!UICONTROL Filter]**.


>[!NOTE]
>
>Die Schnellfilter, die Sie in einem bestimmten Workspace-Projekt erstellen, werden nicht im [!UICONTROL Filter]Manager angezeigt, es sei denn, Sie haben den Filter für alle Ihre Projekte verfügbar gemacht.
>

## Filter-Manager

Der Filter-Manager verfügt über die folgenden Elemente der Benutzeroberfläche:

![Filterschnittstelle](assets/filters-manager.png)

### Filterliste

Die Filterliste zeigt alle Filter an, deren Eigentümer Sie sind, die Filter, die für alle Ihre Projekte gelten, und die Filter, die für Sie freigegeben wurden. Die Liste umfasst die folgenden Spalten:

| Spalte | Beschreibung |
| --- | --- | 
| ![UnausgefüllterStern](/help/assets/icons/StarOutline.svg) | Wählen Sie aus![ um einen Filter ](/help/assets/icons/Star.svg)Star“ oder ![StarOutline](/help/assets/icons/StarOutline.svg) zu bevorzugen. Siehe [Filter als Favorit markieren](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL Titel und Beschreibung]** | Um den Filter zu bearbeiten, klicken Sie auf den Titel-Link, über den der [Filter-Builder“ ](filter-builder.md) wird. Ein freigegebener Filter wird mit &quot;![&quot; ](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Datenansicht]** | Die Datenansichten, für die dieser Filter gilt. |
| **[!UICONTROL Inhabende]** | Der Besitzer des Filters. Als Benutzer sehen Sie nur die Filter, deren Eigentümer Sie sind, oder die Anmerkungen, die für Sie freigegeben sind. |
| **[!UICONTROL Tags]** | Die Tags für diesen Filter. |
| **[!UICONTROL Freigegeben für]** | Wie viele Einzelpersonen oder Gruppen Sie den Filter freigegeben haben. Wählen Sie aus, um das Dialogfeld **[!UICONTROL Komponente freigeben]** zu öffnen. Weitere Informationen finden [ unter ](filters-share.md) freigeben . |
| **[!UICONTROL Änderungsdatum]** | Datum und Uhrzeit der letzten Änderung des Filters. |
| **[!UICONTROL Verwendet in]** | Zeigt an, wo Filter derzeit verwendet werden und wie oft sie in den einzelnen Bereichen verwendet werden. <p>Wenn der Filter beispielsweise in 40 Projekten und 2 Warnhinweisen verwendet wird, wird der Wert dieser Spalte als [!UICONTROL **42 Komponenten**] angezeigt.</p> <p>Wählen Sie den Wert in dieser Spalte aus, um die Aufschlüsselung anzuzeigen, wo die Filter verwendet werden (z. B. [!UICONTROL **Projekte (40)**], [!UICONTROL **Mobile Scorecards (2)**]). Darüber hinaus können Sie die Liste der Elemente anzeigen, in denen die Filter verwendet werden. Um beispielsweise die Liste der Projekte anzuzeigen, in denen sie verwendet werden, klicken Sie auf den Link [!UICONTROL **Projekte (40)**].</p><p>Jeder der folgenden Bereiche zeigt die Anzahl der Instanzen der in diesem Bereich verwendeten Filter an:</p>  <ul><li>[!UICONTROL **Projekte**]<p>Enthält Filter, [ im Filter-Builder erstellt wurden ](/help/components/filters/filter-builder.md#) für alle Projekte verfügbar sind.</p></li><li>[!UICONTROL **Ad-hoc-Komponenten**]<p>Enthält Filter, [ als Schnellfilter erstellt wurden ](/help/components/filters/quick-filters.md) nur in einem einzigen Projekt verfügbar sind.</p></li><li>[!UICONTROL **Geplante Projekte**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Anmerkungen**]</li><li>[!UICONTROL **Berechnete Metriken**]</li><li>[!UICONTROL **Report Builder**]<p>Wenn Sie diese Option wählen, wird eine CSV-Datei mit den folgenden Datenspalten heruntergeladen:</p><ul><li>Name des Report Builders</li><li>Zuletzt aufgerufen</li><li>Zuletzt aufgerufene IMS-Benutzer-ID</li><li>Zuletzt aufgerufener Benutzername</li></ul></li></ul><p>Anhand dieser Informationen können Sie feststellen, ob eine Komponente für Benutzende in Ihrer Organisation nützlich ist, wo die Komponente verwendet wird und ob die Komponente gelöscht oder geändert werden muss.</p><p>Beachten Sie Folgendes beim Anzeigen dieser Option:</p><ul><li>Diese Informationen stehen nur Systemadministratoren zur Verfügung.</li><li>Die Spalte [!UICONTROL **Verwendet in**] wird standardmäßig nicht angezeigt. Mit ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) können Sie die Anzeige dieser Spalte konfigurieren.</li><li>Diese Informationen beinhalten keine Verwendung über die API oder die Data Warehouse.</li><li>Wenn in dieser Spalte keine Daten für eine bestimmte Komponente vorhanden sind, die Komponente jedoch ein Datum [!UICONTROL **Zuletzt verwendet**] aufweist, wurde die Komponente möglicherweise in einer Analyse verwendet, ohne gespeichert zu werden.</li><li>Nutzungsinformationen sind ab September 2023 verfügbar.</li></ul><p>Sie können das [Datenwörterbuch](/help/components/data-dictionary/data-dictionary-overview.md) zusammen mit diesen Informationen verwenden, um zu verfolgen und besser zu verstehen, wie Komponenten in Ihrer Organisation verwendet werden.</p> |
| **[!UICONTROL Zuletzt verwendet]** | Zeitpunkt der letzten Verwendung des Filters. |

{style="table-layout:auto"}

Verwenden Sie ![Spalteneinstellung](/help/assets/icons/ColumnSetting.svg), um die anzuzeigenden Spalten anzugeben.

### Aktionsleiste

Über die Aktionsleiste können Sie Aktionen für Filter durchführen. Die Aktionsleiste ermöglicht die folgenden Aktionen:

| Aktion | Beschreibung |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | Fügen Sie mit dem Filter[Builder einen weiteren Filter ](filter-builder.md). |
| ![Suche](/help/assets/icons/Search.svg) [!UICONTROL *Suche nach Titel*] | Wenn kein Filter in der Liste ausgewählt ist, suchen Sie mithilfe dieses Suchfelds nach Filtern. |
| ![Label](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Markieren Sie die ausgewählten Filter. Wählen **[!UICONTROL im Dialogfeld]** Tag-Filter“ die Tags für die ausgewählten Filter aus bzw. heben Sie die Auswahl auf. Klicken Sie **[!UICONTROL Speichern]**, um die Tags für die ausgewählten Filter zu speichern. Siehe [Tag-](/help/components/filters/filters-tag.md)) für weitere Informationen. |
| ![Freigeben](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Freigeben]** | Freigeben der ausgewählten Filter. Im Dialogfeld **[!UICONTROL Filter freigeben]** können Sie ![Suchen](/help/assets/icons/Search.svg)*Einzelpersonen oder Gruppen suchen* oder **[!UICONTROL Organisation]** oder **[!UICONTROL Gruppen]**. Wählen Sie **[!UICONTROL Speichern]**, um Freigabedetails für die ausgewählten Filter zu speichern. Weitere Informationen finden [ unter ](filters-share.md) freigeben . |
| ![Löschen](/help/assets/icons/Delete.svg) **[!UICONTROL Löschen]** | Löscht die ausgewählten Filter. Sie werden zur Bestätigung aufgefordert. |
| ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Umbenennen]** | Umbenennen eines einzelnen ausgewählten Filters. Wenn diese Option aktiviert ist, können Sie den Filter inline umbenennen. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** | Genehmigen Sie die ausgewählten Filter. Weitere Informationen finden [ unter ](filters-approve.md)Filter genehmigen“. |
| ![Kopieren](/help/assets/icons/Copy.svg) **[!UICONTROL Kopieren]** | Kopieren Sie den ausgewählten Filter. Neue Filter werden mit demselben Namen und Suffix `(Copy)` erstellt. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exportieren in CSV]** | Exportieren Sie die Filter in eine `Filters List.csv`. |

### Aktive Filterleiste

Die Filterleiste die aktiven Filter an, die vom Filterbereich auf die Filterliste angewendet wurden (falls vorhanden). Mit ![XGröße75](/help/assets/icons/CrossSize75.svg) können Sie schnell einen Filter entfernen. Wenn mehr als ein Filter angegeben ist, können Sie alle Filter mit **[!UICONTROL Alle entfernen]** entfernen.

### Bedienfeld „Filter“

Sie können die Filterliste mithilfe des linken Bedienfelds ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** filtern. Das Bedienfeld „Filter“ zeigt den Filtertyp und die Anzahl der Filter an, die den spezifischen Filter berücksichtigen. Wählen Sie ![Filter](/help/assets/icons/Filter.svg) aus, um die Anzeige des Bedienfelds „Filter“ umzuschalten.

Weitere Informationen [ Sie unter „Filterliste ](filters-filter.md) Filtern“.
