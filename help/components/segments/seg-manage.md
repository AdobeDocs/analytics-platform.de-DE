---
description: Erfahren Sie, wie Sie mit dem Segment-Manager Segmente verwalten können, z. B. Segmente freigeben, filtern, taggen, genehmigen, kopieren, löschen und als Favoriten markieren.
title: Segmente verwalten
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters, Segments
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 31%

---

# Verwalten von Segmenten


Sie können [Freigeben](seg-share.md), [Segment](seg-filter.md), [Tag](seg-tag.md), [Genehmigen](seg-approve.md), umbenennen [Kopieren](seg-copy.md), Segmente löschen, exportieren und Segmente über eine zentrale [Segment](seg-favorite.md)Verwaltungsoberfläche als [!UICONTROL Favorit] markieren. So verwalten Sie Segmente:

* Wählen Sie **[!UICONTROL Hauptbenutzeroberfläche]** Komponenten“ aus und klicken Sie auf **[!UICONTROL Segmente]**.


>[!NOTE]
>
>Die Schnellsegmente, die Sie in einem bestimmten Workspace-Projekt erstellen, werden nicht im [!UICONTROL Segment]Manager angezeigt, es sei denn, Sie haben das Segment für alle Ihre Projekte verfügbar gemacht.
>

## Segment-Manager

Der Segment-Manager verfügt über die folgenden Elemente der Benutzeroberfläche:

![Segmentschnittstelle](assets/filters-manager.png)

### Segmentliste

In der ➊ „Segmentliste“ werden alle Segmente angezeigt, deren Inhaber Sie sind, die Segmente, die für alle Ihre Projekte gelten, und die Segmente, die für Sie freigegeben wurden. Die Liste umfasst die folgenden Spalten:

| Spalte | Beschreibung |
| --- | --- | 
| ![UnausgefüllterStern](/help/assets/icons/StarOutline.svg) | Wählen Sie aus, ![&#x200B; ein Segment &#x200B;](/help/assets/icons/Star.svg)StarOutline![&#x200B; zu bevorzugen oder &#x200B;](/help/assets/icons/StarOutline.svg). Siehe [Segment als Favorit markieren](/help/components/segments/seg-favorite.md) |
| **[!UICONTROL Titel und Beschreibung]** | Um das Segment zu bearbeiten, klicken Sie auf den Titel-Link, der den [Segment Builder“ &#x200B;](seg-builder.md). Ein freigegebenes Segment wird mit &quot;![&quot; &#x200B;](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Datenansicht]** | Die Datenansichten, für die dieses Segment gilt. |
| **[!UICONTROL Inhabende]** | Der Inhaber des Segments. Als Benutzer sehen Sie nur die Segmente, deren Inhaber Sie sind, oder die Anmerkungen, die für Sie freigegeben wurden. |
| **[!UICONTROL Tags]** | Die Tags für dieses Segment. |
| **[!UICONTROL Freigegeben für]** | Wie viele Einzelpersonen oder Gruppen Sie das Segment freigegeben haben. Wählen Sie diese Option aus, um das Dialogfeld **[!UICONTROL Komponente freigeben]** zu öffnen. Weitere Informationen finden [&#x200B; unter &#x200B;](seg-share.md) von Segmenten . |
| **[!UICONTROL Änderungsdatum]** | Datum und Uhrzeit der letzten Änderung des Segments. |
| **[!UICONTROL Verwendet in]** | Zeigt an, wo Segmente derzeit verwendet werden und wie oft sie in den einzelnen Bereichen verwendet werden. <p>Wenn das Segment beispielsweise in 40 Projekten und 2 Warnhinweisen verwendet wird, wird der Wert dieser Spalte als [!UICONTROL **42 Komponenten**] angezeigt.</p> <p>Wählen Sie den Wert in dieser Spalte aus, um die Aufschlüsselung anzuzeigen, wo die Segmente verwendet werden (z. B. [!UICONTROL **Projekte (40)**], [!UICONTROL **Mobile Scorecards (2)**]). Darüber hinaus können Sie die Liste der Elemente anzeigen, in denen die Segmente verwendet werden. Um beispielsweise die Liste der Projekte anzuzeigen, in denen sie verwendet werden, klicken Sie auf den Link [!UICONTROL **Projekte (40)**].</p><p>Jeder der folgenden Bereiche zeigt die Anzahl der Instanzen der Segmente an, die in diesem Bereich verwendet werden:</p>  <ul><li>[!UICONTROL **Projekte**]<p>Enthält Segmente, [&#x200B; im Segment Builder erstellt wurden &#x200B;](/help/components/segments/seg-builder.md#) für alle Projekte verfügbar sind.</p></li><li>[!UICONTROL **Ad-hoc-Komponenten**]<p>Enthält Segmente, [&#x200B; als Schnellsegmente erstellt wurden &#x200B;](/help/components/segments/seg-quick.md) nur in einem einzigen Projekt verfügbar sind.</p></li><li>[!UICONTROL **Geplante Projekte**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Anmerkungen**]</li><li>[!UICONTROL **Berechnete Metriken**]</li><li>[!UICONTROL **Report Builder**]<p>Wenn Sie diese Option wählen, wird eine CSV-Datei mit den folgenden Datenspalten heruntergeladen:</p><ul><li>Report Builder-Name</li><li>Letzter Zugriff</li><li>Letzter Zugriff – IMS-Benutzer-ID</li><li>Letzter Zugriff – Benutzername</li></ul></li></ul><p>Mithilfe dieser Informationen können Sie feststellen, ob eine Komponente für Benutzerinnen und Benutzer in Ihrer Organisation nützlich ist, wo die Komponente verwendet wird und ob die Komponente gelöscht oder geändert werden muss. </p><p>Beachten Sie Folgendes beim Anzeigen dieser Option:</p><ul><li>Diese Informationen stehen nur Systemadmins zur Verfügung.</li><li>Die Spalte [!UICONTROL **Verwendet in**] wird standardmäßig nicht angezeigt. Mit ![Spalteneinstellung](/help/assets/icons/ColumnSetting.svg) können Sie die Anzeige dieser Spalte konfigurieren.</li><li>Diese Informationen umfassen nicht die Nutzung über die API oder Data Warehouse.</li><li>Wenn in dieser Spalte keine Daten für eine bestimmte Komponente vorhanden sind, die Komponente jedoch ein Datum [!UICONTROL **Zuletzt verwendet**] aufweist, wurde die Komponente möglicherweise in einer Analyse verwendet, ohne gespeichert zu werden.</li><li>Nutzungsinformationen sind ab September 2023 verfügbar.</li></ul><p>Sie können das [Datenwörterbuch](/help/components/data-dictionary/data-dictionary-overview.md) zusammen mit diesen Informationen verwenden, um die Verwendung von Komponenten in Ihrer Organisation zu verfolgen und besser zu verstehen.</p> |
| **[!UICONTROL Zuletzt verwendet]** | Zeitpunkt der letzten Verwendung des Segments. |

Verwenden Sie ![Spalteneinstellung](/help/assets/icons/ColumnSetting.svg), um die anzuzeigenden Spalten anzugeben.

### Aktionsleiste

Sie können Aktionen für Segmente mithilfe der Aktionsleiste ➋. Die Aktionsleiste ermöglicht die folgenden Aktionen:

| Aktion | Beschreibung |
|---|---|
| ![Hinzufügen](/help/assets/icons/AddCircle.svg) **[!UICONTROL Hinzufügen]** | Fügen Sie mit dem [Segment Builder“ ein weiteres Segment &#x200B;](seg-builder.md). |
| ![Suchen](/help/assets/icons/Search.svg) [!UICONTROL *Nach Titel suchen*] | Wenn kein Segment in der Liste ausgewählt ist, suchen Sie mithilfe dieses Suchfelds nach Segmenten. |
| ![Label](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Tagging der ausgewählten Segmente. Wählen Sie im **[!UICONTROL Segment]**-Dialogfeld die Tags für die ausgewählten Segmente aus bzw. heben Sie die Auswahl auf. Wählen Sie **[!UICONTROL Speichern]**, um die Tags für die ausgewählten Segmente zu speichern. Weitere Informationen finden [&#x200B; unter &#x200B;](/help/components/segments/seg-tag.md) von Segmenten . |
| ![Freigeben](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Freigeben]** | Freigeben der ausgewählten Segmente. Im Dialogfeld **[!UICONTROL Segment freigeben]** können Sie ![Suchen](/help/assets/icons/Search.svg) *(Einzelpersonen oder Gruppen* oder **[!UICONTROL Organisation]** oder **[!UICONTROL Gruppen]**. Wählen Sie **[!UICONTROL Speichern]**, um Freigabedetails für die ausgewählten Segmente zu speichern. Weitere Informationen finden [&#x200B; unter &#x200B;](seg-share.md) von Segmenten . |
| ![Löschen](/help/assets/icons/Delete.svg) **[!UICONTROL Löschen]** | Löscht die ausgewählten Segmente. Sie werden zur Eingabe einer Bestätigung aufgefordert. <br/>Beachten Sie beim Löschen eines Segments Folgendes: <ul><li>Terminierte Berichte und Projekte, auf die dieses Segment angewendet wurde, funktionieren weiterhin normal.</li><li> Terminierte Berichte werden nicht aktualisiert, wenn Sie ein Segment mit demselben Namen bearbeiten.</li> </ul> |
| ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Umbenennen]** | Ein einzelnes ausgewähltes Segment umbenennen. Wenn diese Option aktiviert ist, können Sie das Segment inline umbenennen. |
| ![Häkchen](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Genehmigen]** | Genehmigen Sie die ausgewählten Segmente. Weitere Informationen finden [&#x200B; unter &#x200B;](seg-approve.md) von Segmenten. |
| ![Kopieren](/help/assets/icons/Copy.svg) **[!UICONTROL Kopieren]** | Kopiert das ausgewählte Segment. Neue Segmente werden mit demselben Namen und derselben `(Copy)` erstellt. |
| ![CSV-Datei](/help/assets/icons/FileCSV.svg) **[!UICONTROL In CSV exportieren]** | Exportieren Sie die Segmente in eine `Segments List.csv`. |

### Aktive Filterleiste

Die Filterleiste zeigt ➌ die aktiven Segmente an, die vom Filterbedienfeld auf die Liste der Segmente angewendet wurden (falls vorhanden). Mit ![XGröße75](/help/assets/icons/CrossSize75.svg) können Sie schnell einen Filter entfernen. Wenn mehr als ein Filter angegeben ist, können Sie mit „Alle entfernen **[!UICONTROL alle Filter]**.

### Panel „Filter“

Sie können die Liste der Segmente mithilfe der ![&#x200B; des &#x200B;](/help/assets/icons/Filter.svg)Filtern **&#x200B;**&#x200B;Filtern➍ filtern. Das Bedienfeld „Filter“ zeigt den Filtertyp und die Anzahl der Segmente an, die den spezifischen Filter berücksichtigen. Wählen Sie ![Filter](/help/assets/icons/Filter.svg) aus, um die Anzeige des Bedienfelds „Filter“ umzuschalten.

Weitere [&#x200B; finden Sie unter &#x200B;](seg-filter.md) der Segmentliste .
