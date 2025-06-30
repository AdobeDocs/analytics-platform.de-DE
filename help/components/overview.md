---
title: Was sind Komponenten in Customer Journey Analytics?
description: Erfahren Sie, welche Komponenten Customer Journey Analytics anbietet und wie Sie sie für die Berichterstellung verwenden können.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
role: User
source-git-commit: 70daf2251576bc3b473e63b3bb7c48f2d16dbffe
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 100%

---

# Komponentenübersicht

Komponenten sind Funktionen in Customer Journey Analytics, die in Visualisierungen (wie Freiformtabellen) verwendet werden können oder Berichtsfunktionen ergänzen.

So verwalten Sie Komponenten über die Haupt-Benutzeroberfläche von Customer Journey Analytics:

1. Wählen Sie in der oberen Leiste **[!UICONTROL Komponenten]** aus.
1. Wählen Sie **[!UICONTROL Komponenten]** aus, um einen Überblick über die Komponenten zu erhalten, die Sie verwalten können, oder wählen Sie die zu verwaltende Komponente direkt über das Menü aus.

Sie können die folgenden Komponenten verwalten:

* [Segmente](segments/seg-overview.md): Erstellen, verwalten, teilen und verwenden Sie leistungsstarke, zielgerichtete Segmente für Ihre Berichte. Mit Segmenten können Sie Teilmengen von Personen anhand von Merkmalen oder Interaktionen identifizieren.
* [Berechnete Metriken:](calc-metrics/calc-metr-overview.md) Verwenden Sie Metriken und Formeln als neue Komponenten für die Berichterstellung.
* [Datumsbereiche](date-ranges/create.md): Passen Sie die von Analysis Workspace vorgeschlagenen Datumsbereiche an und präzisieren Sie diese.
* [Anmerkungen](/help/components/annotations/overview.md): Informieren Sie andere Benutzerinnen und Benutzer in Ihrem Unternehmen über die kontextbezogene Bedeutung von Daten und Erkenntnissen.
* [Intelligente Warnhinweise](/help/components/c-intelligent-alerts/intelligent-alerts.md): Diese ermöglichen es Ihnen, sich über geänderte Prozentsätze oder bestimmte Datenpunkte benachrichtigen zu lassen.
* [Geplante Projekte](/help/analysis-workspace/curate-share/t-schedule-report.md#scheduled-projects-manager): Verwalten Sie Ihre geplanten Projekte.
* [Voreinstellungen](/help/analysis-workspace/user-preferences.md): Verwalten Sie die Voreinstellungen für Analysis Workspace.
* [Zielgruppen](/help/components/audiences/audiences-overview.md): Erstellen und veröffentlichen Sie Zielgruppen aus Customer Journey Analytics auf der [Echtzeit-Kundendatenplattform](https://experienceleague.adobe.com/de/docs/experience-platform/profile/home) in Experience Platform zu Targeting- und Personalisierungszwecken.
* [Exporte](/help/components/exports/manage-export-locations.md): Verwalten Sie Ihr Exportkonto und Ihre Speicherorte.


## Analysis Workspace-Komponenten

Komponenten in Analysis Workspace bestehen aus Metriken, Dimensionen, Segmenten und Datumsbereichen, die Sie per Drag-and-Drop auf Panels und Visualisierungen in Ihrem Workspace-Projekt anwenden können. Wenn Sie benutzerdefinierte Komponenten erstellen, z. B. eine benutzerdefinierte Metrik oder einen benutzerdefinierten Datumsbereich, werden sie zu diesen Bedienfeldern hinzugefügt.

Um auf das Bedienfeld „Komponenten“ zuzugreifen, wählen Sie im Schaltflächenbedienfeld die Option ![Kuratieren](/help/assets/icons/Curate.svg) **[!UICONTROL Komponenten]** aus.

![Workspace-Bedienfeld, in dem das Symbol „Komponenten“ in der linken Leiste markiert ist](assets/components.png)

Informationen über die Verwendung von Komponenten in einem Projekt finden Sie unter [Erstellen eines Projekts](/help/analysis-workspace/home.md).


## Verwalten von Komponenten {#actions}

Mithilfe des Menüs **[!UICONTROL Komponenten]** in Analysis Workspace können Sie schnell eine neue Komponente erstellen. Weitere Informationen finden Sie im [Menü „Analysis Workspace“](/help/analysis-workspace/home.md#menu).

Sie können Komponenten verwalten, entweder einzeln oder durch Auswahl mehrerer Komponenten.

1. Wählen Sie eine oder mehrere Komponenten aus.

1. Wählen Sie im Kontextmenü oder über die Schaltfläche ![Mehr senkrecht](/help/assets/icons/MoreVertical.svg) „Aktionen für Komponenten“ (oben in Komponenten) eine der folgenden Aktionen aus.


   >[!TIP]
   >
   >Sie können mehrere Komponenten auswählen, indem Sie die **[!UICONTROL Umschalttaste]** gedrückt halten oder indem Sie die **[!UICONTROL Befehlstaste]** (macOS) bzw. die **[!UICONTROL Strg-Taste]** (Windows) gedrückt halten.


   ![Liste der Komponentenaktionen inklusive: Tag, Favorit, Genehmigung, Freigabe und Löschen.](assets/component-menu.gif){width=100%}

   | Komponentenaktion | Beschreibung |
   |--- |--- |
   | ![Label](/help/assets/icons/Label.svg) [!UICONTROL **Tag**] | Organisieren oder verwalten Sie Komponenten, indem Sie Tags darauf anwenden. Sie können dann im linken Bedienfeld nach Tags suchen, indem Sie den ![Filter](/help/assets/icons/Filter.svg) Filter auswählen oder `#` eingeben. Tags fungieren auch als Filter in den Komponenten-Managern. |
   | ![Stern](/help/assets/icons/Star.svg) [!UICONTROL **Zu Favoriten hinzufügen**] | Fügen Sie die Komponente zu Ihrer Favoritenliste hinzu. Genauso wie nach Tags können Sie im linken Bedienfeld auch nach Favoriten suchen und diese in den Komponenten-Managern als Filter verwenden. |
   | ![UnausgefüllterStern](/help/assets/icons/StarOutline.svg) **[!UICONTROL Aus Favoriten entfernen]** | Entfernen Sie die Komponente aus Ihrer Favoritenliste.  |
   | ![Häkchen](/help/assets/icons/Checkmark.svg) [!UICONTROL **Genehmigen**] | Markieren Sie Komponenten als „Genehmigt“, um Ihren Benutzerinnen und Benutzern zu signalisieren, dass die Komponente vom Unternehmen genehmigt ist. Wie Tags können Sie im linken Bedienfeld anhand des Status „Genehmigt“ suchen und filtern. Mit einem ![Häkchen](/help/assets/icons/Checkmark.svg) werden genehmigte Komponenten gekennzeichnet. |
   | ![Freigeben](/help/assets/icons/ShareAlt.svg) [!UICONTROL **Freigeben**] | Freigeben von Komponenten für Benutzer in Ihrer Organisation. Diese Option steht nur für benutzerdefinierte Komponenten zur Verfügung, beispielsweise für Segmente oder berechnete Metriken. |
   | ![Löschen](/help/assets/icons/Delete.svg) [!UICONTROL **Löschen**] | Löschen Sie Komponenten, die Sie nicht mehr benötigen. Diese Option steht nur für benutzerdefinierte Komponenten zur Verfügung, beispielsweise für Segmente oder berechnete Metriken. |

Benutzerdefinierte Komponenten können auch über ihre jeweiligen Komponenten-Manager verwaltet werden. Weitere Informationen finden Sie unter [Verwalten von Segmenten](/help/components/segments/seg-manage.md).

## Verwalten der Komponentenliste

Sie können die Komponentenliste im linken Bedienfeld von Analysis Workspace durchsuchen, filtern und sortieren, um eine bestimmte Komponente zu finden.

### Durchsuchen

1. Wählen Sie im linken Bedienfeld **Komponenten** ![Komponentensymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) aus.

2. Geben Sie im Suchfeld den Namen der Komponente ein, die Sie in Ihrem Projekt verwenden möchten.

   Der jeweilige Komponententyp ist farblich und mit einem Symbol gekennzeichnet. **Dimensionen** ![Dimensionsymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) sind orange, **Segmente** ![Segmentsymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) sind blau, **Datumsbereiche** ![Datumsbereichsymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) sind violett und **Metriken** ![Metriksymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) sind grün. <br/>Das Adobe-Symbol ![Adobe-Logo](/help/assets/icons/AdobeLogoSmall.svg) steht entweder für eine Vorlage für berechnete Metriken oder eine Segmentvorlage. Das Taschenrechnersymbol ![Taschenrechnersymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) gibt an, dass es sich um eine berechnete Metrik handelt, die administratorseitig in Ihrer Organisation erstellt wurde.

3. Wählen Sie aus dem Dropdown-Menü die gewünschte Komponente aus.

### Filter

1. Wählen Sie im linken Bedienfeld **Komponenten** ![Komponentensymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) aus.

2. Wählen Sie **Filter** ![Datenwörterbuchfilter-Symbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) aus oder geben Sie `#` in das Suchfeld ein.

3. Wählen Sie eine der folgenden Filteroptionen aus, um die Liste der Komponenten zu filtern:

   | Symbol | Filteroption | Beschreibung |
   |---------|---|----------|
   | ![Häkchen](/help/assets/icons/Checkmark.svg) | **[!UICONTROL Genehmigt]** | Nur Komponenten anzeigen, die von Admins als genehmigt markiert wurden. |
   | ![Stern](/help/assets/icons/Star.svg) | **[!UICONTROL Favoriten]** | Nur Komponenten anzeigen, die sich in Ihrer Favoritenliste befinden. <br/>Weitere Informationen zum Hinzufügen von Komponenten zu Ihrer Favoritenliste finden Sie unter [Verwalten von Komponenten](#manage-components). |
   | ![Dimensionen](/help/assets/icons/Dimensions.svg) | **[!UICONTROL Dimensionen]** | Nur Komponenten anzeigen, die Dimensionen sind. |
   | ![Ereignis](/help/assets/icons/Event.svg) | **[!UICONTROL Metriken]** | Nur Komponenten anzeigen, die Metriken sind. |
   | ![Segmentierung](/help/assets/icons/Segmentation.svg) | **[!UICONTROL Segmente]** | Nur Komponenten anzeigen, die Segmente sind.  |
   | ![Kalender](/help/assets/icons/Calendar.svg) | **[!UICONTROL Datumsbereiche]** | Nur Komponenten anzeigen, die Datumsbereiche sind.  |
   | ![Beschriftung](/help/assets/icons/Label.svg) | **[!UICONTROL *Tag-Name *]** | Nur Komponenten mit den jeweilig ausgewählten Tags anzeigen. Für Adobe-Vorlagen, bei denen es sich um die [standardmäßig berechneten Metriken](/help/components/calc-metrics/default-calcmetrics.md) von Adobe handelt, ist ein dediziertes Tag verfügbar. |

   Wählen Sie ![XGröße75](/help/assets/icons/CrossSize75.svg) in einem Filter aus, um den Filter zu entfernen.

4. Sie können optional die Komponentenliste sortieren, wie unter [Sortieren der Komponentenliste](#sort-the-component-list) beschrieben.

### Sortieren

<!-- {{release-limited-testing-section}}-->

1. (Optional) Wenden Sie alle Filter auf die Komponentenliste an, wie unter [Filtern der Komponentenliste](#filter-the-component-list) beschrieben.

2. Wählen Sie im linken Bedienfeld **Komponenten** ![Komponentensymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) aus.

3. Wählen Sie **Sortieren** ![Symbol zum Sortieren von Komponenten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) und dann eine der folgenden Filteroptionen aus, um die Liste der Komponenten zu sortieren.

Die folgenden Sortieroptionen sind verfügbar:

{{components-sort-options}}

## Zugriffsberechtigungen

In Analysis Workspace können Admins [kuratieren](/help/analysis-workspace/curate-share/curate.md), welche Komponenten Benutzenden beim Reporting zur Verfügung stehen.
