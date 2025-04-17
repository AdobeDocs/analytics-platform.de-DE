---
title: Segmente verwalten
description: Erfahren Sie, wie Sie Segmente in Customer Journey Analytics verwalten
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: 66ec61ea64f1265d887d4941a22e1f9757120daa
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 32%

---

# Segmente verwalten


Sie können [Freigeben](filters-share.md), [Segment](filters-filter.md), [Tag](filters-tag.md), [Genehmigen](filters-approve.md), umbenennen [Kopieren](filters-copy.md), Segmente löschen, exportieren und Segmente über eine zentrale [!UICONTROL Segment]Verwaltungsoberfläche als [Favorit](filters-favorite.md) markieren. So verwalten Sie Segmente:

* Wählen Sie **[!UICONTROL Hauptbenutzeroberfläche]** Komponenten“ aus und klicken Sie auf **[!UICONTROL Segmente]**.


>[!NOTE]
>
>Die Schnellsegmente, die Sie in einem bestimmten Workspace-Projekt erstellen, werden nicht im [!UICONTROL Filter]Manager angezeigt, es sei denn, Sie haben das Segment für alle Ihre Projekte verfügbar gemacht.
>

## Segment-Manager

Der Segment-Manager verfügt über die folgenden Elemente der Benutzeroberfläche:

![Segmentschnittstelle](assets/filters-manager.png)

### Segmentliste

In der Liste der Segmente werden alle Segmente angezeigt, deren Inhaber Sie sind, die Segmente, die für alle Ihre Projekte gelten, und die Segmente, die für Sie freigegeben wurden. Die Liste umfasst die folgenden Spalten:

| Spalte | Beschreibung |
| --- | --- | 
| ![UnausgefüllterStern](/help/assets/icons/StarOutline.svg) | Wählen Sie aus, ![ ein Segment ](/help/assets/icons/Star.svg)StarOutline![ zu bevorzugen oder ](/help/assets/icons/StarOutline.svg). Siehe [Segment als Favorit markieren](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL Titel und Beschreibung]** | Um das Segment zu bearbeiten, klicken Sie auf den Titel-Link, der den [Filter-Builder“ ](filter-builder.md). Ein freigegebenes Segment wird mit &quot;![&quot; ](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Datenansicht]** | Die Datenansichten, für die dieses Segment gilt. |
| **[!UICONTROL Inhabende]** | Der Inhaber des Segments. Als Benutzer sehen Sie nur die Segmente, deren Inhaber Sie sind, oder die Anmerkungen, die für Sie freigegeben wurden. |
| **[!UICONTROL Tags]** | Die Tags für dieses Segment. |
| **[!UICONTROL Freigegeben für]** | Wie viele Einzelpersonen oder Gruppen Sie das Segment freigegeben haben. Wählen Sie diese Option aus, um das Dialogfeld **[!UICONTROL Komponente freigeben]** zu öffnen. Weitere Informationen finden [ unter ](filters-share.md) von Segmenten . |
| **[!UICONTROL Änderungsdatum]** | Datum und Uhrzeit der letzten Änderung des Segments. |
| **[!UICONTROL Verwendet in]** | Zeigt an, wo Segmente derzeit verwendet werden und wie oft sie in den einzelnen Bereichen verwendet werden. <p>Wenn das Segment beispielsweise in 40 Projekten und 2 Warnhinweisen verwendet wird, wird der Wert dieser Spalte als [!UICONTROL **42 Komponenten**] angezeigt.</p> <p>Wählen Sie den Wert in dieser Spalte aus, um die Aufschlüsselung anzuzeigen, wo die Segmente verwendet werden (z. B. [!UICONTROL **Projekte (40)**], [!UICONTROL **Mobile Scorecards (2)**]). Darüber hinaus können Sie die Liste der Elemente anzeigen, in denen die Segmente verwendet werden. Um beispielsweise die Liste der Projekte anzuzeigen, in denen sie verwendet werden, klicken Sie auf den Link [!UICONTROL **Projekte (40)**].</p><p>Jeder der folgenden Bereiche zeigt die Anzahl der Instanzen der Segmente an, die in diesem Bereich verwendet werden:</p>  <ul><li>[!UICONTROL **Projekte**]<p>Enthält Segmente, [ im Segment Builder erstellt wurden ](/help/components/filters/filter-builder.md#) für alle Projekte verfügbar sind.</p></li><li>[!UICONTROL **Ad-hoc-Komponenten**]<p>Enthält Segmente, [ als Schnellsegmente erstellt wurden ](/help/components/filters/quick-filters.md) nur in einem einzigen Projekt verfügbar sind.</p></li><li>[!UICONTROL **Geplante Projekte**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Anmerkungen**]</li><li>[!UICONTROL **Berechnete Metriken**]</li><li>[!UICONTROL **Report Builder**]<p>Wenn Sie diese Option wählen, wird eine CSV-Datei mit den folgenden Datenspalten heruntergeladen:</p><ul><li>Report Builder-Name</li><li>Letzter Zugriff</li><li>Letzter Zugriff – IMS-Benutzer-ID</li><li>Letzter Zugriff – Benutzername</li></ul></li></ul><p>Mithilfe dieser Informationen können Sie feststellen, ob eine Komponente für Benutzerinnen und Benutzer in Ihrer Organisation nützlich ist, wo die Komponente verwendet wird und ob die Komponente gelöscht oder geändert werden muss. </p><p>Beachten Sie Folgendes beim Anzeigen dieser Option:</p><ul><li>Diese Informationen stehen nur Systemadmins zur Verfügung.</li><li>Die Spalte [!UICONTROL **Verwendet in**] wird standardmäßig nicht angezeigt. Mit ![Spalteneinstellung](/help/assets/icons/ColumnSetting.svg) können Sie die Anzeige dieser Spalte konfigurieren.</li><li>Diese Informationen umfassen nicht die Nutzung über die API oder Data Warehouse.</li><li>Wenn in dieser Spalte keine Daten für eine bestimmte Komponente vorhanden sind, die Komponente jedoch ein Datum [!UICONTROL **Zuletzt verwendet**] aufweist, wurde die Komponente möglicherweise in einer Analyse verwendet, ohne gespeichert zu werden.</li><li>Nutzungsinformationen sind ab September 2023 verfügbar.</li></ul><p>Sie können das [Datenwörterbuch](/help/components/data-dictionary/data-dictionary-overview.md) zusammen mit diesen Informationen verwenden, um die Verwendung von Komponenten in Ihrer Organisation zu verfolgen und besser zu verstehen.</p> |
| **[!UICONTROL Zuletzt verwendet]** | Zeitpunkt der letzten Verwendung des Segments. |

Verwenden Sie ![Spalteneinstellung](/help/assets/icons/ColumnSetting.svg), um die anzuzeigenden Spalten anzugeben.

### Aktionsleiste

Über die Aktionsleiste können Sie Aktionen für Segmente durchführen. Die Aktionsleiste ermöglicht die folgenden Aktionen:

| Aktion | Beschreibung |
|---|---|
| ![Hinzufügen](/help/assets/icons/AddCircle.svg) **[!UICONTROL Hinzufügen]** | Fügen Sie mit dem Filter[Builder ein weiteres Segment ](filter-builder.md). |
| ![Suchen](/help/assets/icons/Search.svg) [!UICONTROL *Nach Titel suchen*] | Wenn kein Segment in der Liste ausgewählt ist, suchen Sie mithilfe dieses Suchfelds nach Segmenten. |
| ![Label](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Tagging der ausgewählten Segmente. Wählen Sie im **[!UICONTROL Segment]**-Dialogfeld die Tags für die ausgewählten Segmente aus bzw. heben Sie die Auswahl auf. Wählen Sie **[!UICONTROL Speichern]**, um die Tags für die ausgewählten Segmente zu speichern. Weitere Informationen finden [ unter ](/help/components/filters/filters-tag.md) von Segmenten . |
| ![Freigeben](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Freigeben]** | Freigeben der ausgewählten Segmente. Im Dialogfeld **[!UICONTROL Segment freigeben]** können Sie ![Suchen](/help/assets/icons/Search.svg) *(Einzelpersonen oder Gruppen* oder **[!UICONTROL Organisation]** oder **[!UICONTROL Gruppen]**. Wählen Sie **[!UICONTROL Speichern]**, um Freigabedetails für die ausgewählten Segmente zu speichern. Weitere Informationen finden [ unter ](filters-share.md) von Segmenten . |
| ![Löschen](/help/assets/icons/Delete.svg) **[!UICONTROL Löschen]** | Löscht die ausgewählten Segmente. Sie werden zur Bestätigung aufgefordert. |
| ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Umbenennen]** | Ein einzelnes ausgewähltes Segment umbenennen. Wenn diese Option aktiviert ist, können Sie das Segment inline umbenennen. |
| ![Häkchen](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Genehmigen]** | Genehmigen Sie die ausgewählten Segmente. Weitere Informationen finden [ unter ](filters-approve.md) von Segmenten. |
| ![Kopieren](/help/assets/icons/Copy.svg) **[!UICONTROL Kopieren]** | Kopiert das ausgewählte Segment. Neue Segmente werden mit demselben Namen und derselben `(Copy)` erstellt. |
| ![CSV-Datei](/help/assets/icons/FileCSV.svg) **[!UICONTROL In CSV exportieren]** | Exportieren Sie die Segmente in eine `Filters List.csv`. |

### Aktiver Segmentbalken

In der Segmentleiste werden die aktiven Segmente angezeigt, die vom Bedienfeld Segment auf die Liste der Segmente angewendet wurden (falls vorhanden). Mit (CrossSize75![ können Sie ein Segment schnell ](/help/assets/icons/CrossSize75.svg). Wenn mehr als ein Segment angegeben ist, können Sie mit „Alle entfernen **[!UICONTROL alle Segmente]**.

### Bedienfeld „Segment“

Sie können die Segmentliste mithilfe des linken Bedienfelds ![Segment](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** segmentieren. Das Bedienfeld „Segment“ zeigt den Segmenttyp und die Anzahl der Segmente an, die das jeweilige Segment berücksichtigen. Wählen Sie ![Segment](/help/assets/icons/Filter.svg) aus, um das Segment -Bedienfeld ein-/auszublenden.

Weitere [ finden Sie unter ](filters-filter.md) der Segmentliste .
