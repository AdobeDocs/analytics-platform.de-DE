---
description: Das Datenwörterbuch in Analysis Workspace ermöglicht es Benutzenden, die verschiedenen Komponenten in Analysis Workspace zu katalogisieren und im Auge zu behalten, einschließlich ihres Verwendungszwecks, welche genehmigt sind, welche Duplikate sind usw.
title: Einträge im Datenwörterbuch bearbeiten
feature: Components
role: Admin
exl-id: 2d232811-e34a-4667-819c-cbe2a3e72702
source-git-commit: de04792035aa7c235751019ee9f9fe5b74b9b102
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 60%

---

# Bearbeiten von Komponenteneinträgen im Datenwörterbuch

Customer Journey Analytics-Administratoren können Komponenteneinträge im Datenwörterbuch für eine bestimmte Datenansicht bearbeiten. Alle vorgenommenen Änderungen sind für alle Benutzer der Datenansicht sichtbar.

Bearbeiten einer Komponente im Datenwörterbuch:

1. Wechseln Sie zum Analysis Workspace-Projekt, das die zu bearbeitende Komponente enthält.

1. Wählen Sie im Schaltflächenbedienfeld von Analysis Workspace das Symbol **Datenwörterbuch** aus. (Alternative Möglichkeiten für den Zugriff auf das Datenwörterbuch sind unter „Zugriff auf das Datenwörterbuch“ in [Datenwörterbuch – Überblick](/help/components/data-dictionary/data-dictionary-overview.md) beschrieben.)

   Das Fenster „Datenwörterbuch“ wird angezeigt.

   ![Administratoransicht des Datenwörterbuchs mit Ansicht des Wörterbuchzustands](assets/data-dictionary-admin.png)

1. Stellen Sie sicher, dass im Dropdown-Menü die richtige Datenansicht ausgewählt ist. Standardmäßig wird die Datenansicht angezeigt, in der Sie sich bereits befinden.

1. (Optional) Geben Sie im Suchfeld den Namen der Komponente ein, die Sie bearbeiten möchten.

   Der Komponententyp kann sowohl durch Farbe als auch durch ein Symbol identifiziert werden. **Dimensionen** ![Dimension-Symbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) sind orange, **Filter** ![Segmentsymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) blau, **Datumsbereiche** ![Datumsbereichssymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) ist violett und **Metriken** ![Metriksymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) sind grün. Das Adobe-Symbol zeigt entweder eine Vorlage für berechnete Metriken oder eine Filtervorlage an und das Taschenrechnersymbol ![Taschenrechner-Symbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) gibt eine berechnete Metrik an, die von einem Analytics-Administrator in Ihrem Unternehmen erstellt wurde.

   {{dd-filter-criteria}}

1. (Optional) Wählen Sie das Symbol **Sortieren** Symbol ![Komponenten sortieren](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) aus und wählen Sie dann eine der folgenden Filteroptionen, um die Liste der Komponenten zu sortieren:

{{components-sort-options}}

1. Wählen Sie aus der Komponentenliste die Komponente aus, die Sie bearbeiten möchten.

1. Wählen Sie das Symbol **Bearbeiten** ![Datenwörterbuch bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) neben dem Komponentennamen.

1. Bearbeiten Sie eine der folgenden Informationen zur Komponente:

{{dd-component-information}}

1. Klicken Sie auf das Symbol **Speichern** ![Datenwörterbuch speichern](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg), um Ihre Änderungen zu speichern.
