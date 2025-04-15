---
title: Verwalten von Filtern
description: Erfahren Sie, wie Sie Filter in Customer Journey Analytics verwalten
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: 97b831d7eee477ee7ef0bf8ae65e6a415d243464
workflow-type: ht
source-wordcount: '884'
ht-degree: 100%

---

# Verwalten von Filtern


Sie können Filter in einer zentralen Verwaltungsoberfläche für [!UICONTROL Filter] [freigeben](filters-share.md), [filtern](filters-filter.md), [mit Tags versehen](filters-tag.md), [genehmigen](filters-approve.md), umbenennen, [kopieren](filters-copy.md), löschen, exportieren und als [Favoriten](filters-favorite.md) markieren. So verwalten Sie Filter:

* Wählen Sie in der Hauptbenutzeroberfläche die Option **[!UICONTROL Komponenten]** und dann **[!UICONTROL Filter]** aus.


>[!NOTE]
>
>Die Schnellfilter, die Sie in einem bestimmten Workspace-Projekt erstellen, werden nicht im Manager [!UICONTROL Filter] angezeigt, es sei denn, Sie haben den Filter für all Ihre Projekte verfügbar gemacht.
>

## Manager „Filter“

Der Manager „Filter“ verfügt über die folgenden Benutzeroberflächenelemente:

![Benutzeroberfläche für Filter](assets/filters-manager.png)

### Filterliste

Die Filterliste ➊ zeigt alle Filter an, die Ihnen gehören, die für all Ihre Projekte gelten und die für Sie freigegeben wurden. Die Liste umfasst die folgenden Spalten:

| Spalte | Beschreibung |
| --- | --- | 
| ![UnausgefüllterStern](/help/assets/icons/StarOutline.svg) | Wählen Sie diese Option aus, um einen Filter als Favoriten zu markieren ![Stern](/help/assets/icons/Star.svg) oder aus den Favoriten zu entfernen ![UnausgefüllterStern](/help/assets/icons/StarOutline.svg). Siehe [Filter als Favoriten markieren](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL Titel und Beschreibung]** | Wählen Sie zum Bearbeiten des Filters den Titel-Link aus. Dadurch wird der [Filteraufbau](filter-builder.md) geöffnet. Ein freigegebener Filter wird mit dem Symbol ![Freigeben](/help/assets/icons/ShareAlt.svg) gekennzeichnet. |
| **[!UICONTROL Datenansicht]** | Die Datenansichten, für die dieser Filter gilt. |
| **[!UICONTROL Inhabende]** | Die Inhaberin oder der Inhaber des Filters. Benutzende können nur die Filter sehen, die ihnen gehören oder die für sie freigegeben wurden. |
| **[!UICONTROL Tags]** | Die Tags für diesen Filter. |
| **[!UICONTROL Freigegeben für]** | Die Anzahl der Einzelpersonen oder Gruppen, für die Sie Anmerkung freigegeben haben. Wählen Sie diese Option aus, um das Dialogfeld **[!UICONTROL Komponente freigeben]** zu öffnen. Weitere Informationen finden Sie unter [Freigeben von Filtern](filters-share.md). |
| **[!UICONTROL Änderungsdatum]** | Datum und Uhrzeit der letzten Änderung des Filters. |
| **[!UICONTROL Verwendet in]** | Zeigt an, wo Filter derzeit verwendet werden und wie oft sie in den einzelnen Bereichen verwendet werden. <p>Wenn der Filter beispielsweise in 40 Projekten und 2 Warnhinweisen verwendet wird, wird der Wert dieser Spalte als [!UICONTROL **42 Komponenten**] angezeigt.</p> <p>Wählen Sie den Wert in dieser Spalte aus, um die Aufschlüsselung anzuzeigen, wo die Filter verwendet werden (z. B. [!UICONTROL **Projekte (40)**], [!UICONTROL **Mobile Scorecards (2)**]). Darüber hinaus können Sie die Liste der Elemente anzeigen, in denen die Filter verwendet werden. Um beispielsweise die Liste der Projekte anzuzeigen, in denen sie verwendet werden, klicken Sie auf den Link [!UICONTROL **Projekte (40)**].</p><p>Jeder der folgenden Bereiche zeigt die Anzahl der Instanzen der in diesem Bereich verwendeten Filter an:</p>  <ul><li>[!UICONTROL **Projekte**]<p>Enthält Filter, die [im Filteraufbau erstellt wurden](/help/components/filters/filter-builder.md#) und für alle Projekte verfügbar sind.</p></li><li>[!UICONTROL **Ad-hoc-Komponenten**]<p>Enthält Filter, die [als Schnellfilter erstellt wurden](/help/components/filters/quick-filters.md) und nur in einem einzigen Projekt verfügbar sind.</p></li><li>[!UICONTROL **Geplante Projekte**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Anmerkungen**]</li><li>[!UICONTROL **Berechnete Metriken**]</li><li>[!UICONTROL **Report Builder**]<p>Wenn Sie diese Option wählen, wird eine CSV-Datei mit den folgenden Datenspalten heruntergeladen:</p><ul><li>Report Builder-Name</li><li>Letzter Zugriff</li><li>Letzter Zugriff – IMS-Benutzer-ID</li><li>Letzter Zugriff – Benutzername</li></ul></li></ul><p>Mithilfe dieser Informationen können Sie feststellen, ob eine Komponente für Benutzerinnen und Benutzer in Ihrer Organisation nützlich ist, wo die Komponente verwendet wird und ob die Komponente gelöscht oder geändert werden muss. </p><p>Beachten Sie Folgendes beim Anzeigen dieser Option:</p><ul><li>Diese Informationen stehen nur Systemadmins zur Verfügung.</li><li>Die Spalte [!UICONTROL **Verwendet in**] wird standardmäßig nicht angezeigt. Mit ![Spalteneinstellung](/help/assets/icons/ColumnSetting.svg) können Sie die Anzeige dieser Spalte konfigurieren.</li><li>Diese Informationen umfassen nicht die Nutzung über die API oder Data Warehouse.</li><li>Wenn in dieser Spalte keine Daten für eine bestimmte Komponente vorhanden sind, die Komponente jedoch ein Datum [!UICONTROL **Zuletzt verwendet**] aufweist, wurde die Komponente möglicherweise in einer Analyse verwendet, ohne gespeichert zu werden.</li><li>Nutzungsinformationen sind ab September 2023 verfügbar.</li></ul><p>Sie können das [Datenwörterbuch](/help/components/data-dictionary/data-dictionary-overview.md) zusammen mit diesen Informationen verwenden, um die Verwendung von Komponenten in Ihrer Organisation zu verfolgen und besser zu verstehen.</p> |
| **[!UICONTROL Zuletzt verwendet]** | Zeitpunkt der letzten Verwendung des Filters. |

{style="table-layout:auto"}

Verwenden Sie ![Spalteneinstellung](/help/assets/icons/ColumnSetting.svg), um die anzuzeigenden Spalten anzugeben.

### Aktionsleiste

Mit der Aktionsleiste ➋ können Sie Aktionen für Filter durchführen. Die Aktionsleiste ermöglicht die folgenden Aktionen:

| Aktion | Beschreibung |
|---|---|
| ![Hinzufügen](/help/assets/icons/AddCircle.svg) **[!UICONTROL Hinzufügen]** | Verwenden Sie den [Filteraufbau](filter-builder.md), um einen weiteren Filter hinzuzufügen. |
| ![Suchen](/help/assets/icons/Search.svg) [!UICONTROL *Nach Titel suchen*] | Wenn in der Liste kein Filter ausgewählt ist, suchen Sie mithilfe dieses Suchfelds nach Filtern. |
| ![Label](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Versehen Sie die ausgewählten Filter mit Tags. Wählen Sie im Dialogfeld **[!UICONTROL Filter mit Tag versehen]** die Tags für die ausgewählten Filter aus oder ab. Wählen Sie **[!UICONTROL Speichern]** aus, um die Tags für die ausgewählten Filter zu speichern. Weitere Informationen finden Sie unter [Versehen von Filtern mit Tags](/help/components/filters/filters-tag.md). |
| ![Freigeben](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Freigeben]** | Geben Sie die ausgewählten Filter frei. Im Dialogfeld **[!UICONTROL Filter freigeben]** können Sie ![Suchen](/help/assets/icons/Search.svg) *Personen oder Gruppen suchen* oder **[!UICONTROL Organisation]** oder **[!UICONTROL Gruppen]** auswählen. Wählen Sie **[!UICONTROL Speichern]** aus, um Freigabedetails für die ausgewählten Filter zu speichern. Weitere Informationen finden Sie unter [Freigeben von Filtern](filters-share.md). |
| ![Löschen](/help/assets/icons/Delete.svg) **[!UICONTROL Löschen]** | Löschen Sie die ausgewählten Filter. Sie werden zur Bestätigung aufgefordert. |
| ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Umbenennen]** | Benennen Sie einen einzelnen ausgewählten Filter um. Wenn diese Option ausgewählt ist, ist eine Inline-Umbenennung es Filters möglich. |
| ![Häkchen](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Genehmigen]** | Genehmigen Sie die ausgewählten Filter. Weitere Informationen finden Sie unter [Genehmigen von Filtern](filters-approve.md). |
| ![Kopieren](/help/assets/icons/Copy.svg) **[!UICONTROL Kopieren]** | Kopieren Sie den ausgewählten Filter. Neue Filter werden mit demselben Namen und Suffix erstellt `(Copy)`. |
| ![CSV-Datei](/help/assets/icons/FileCSV.svg) **[!UICONTROL In CSV exportieren]** | Exportieren Sie die Filter in eine Datei namens `Filters List.csv`. |

### Aktive Filterleiste

Die Filterleiste ➌ zeigt die aktiven Filter an, die über das Panel „Filter“ auf die Filterliste angewendet wurden (falls vorhanden). Mit ![XGröße75](/help/assets/icons/CrossSize75.svg) können Sie schnell einen Filter entfernen. Wenn mehr als ein Filter angegeben ist, können Sie alle Filter mit **[!UICONTROL Alle entfernen]** entfernen.

### Panel „Filter“

Sie können die Filterliste mithilfe des Panels ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** auf der linken Seite filtern. Im Panel „Filter“ werden der Filtertyp und die Anzahl der Filter angezeigt, auf die spezifisch gefiltert wurde. Wählen Sie ![Filter](/help/assets/icons/Filter.svg) aus, um die Anzeige des Bedienfelds „Filter“ umzuschalten.

Weitere Informationen finden Sie unter [Filtern der Filterliste](filters-filter.md).
