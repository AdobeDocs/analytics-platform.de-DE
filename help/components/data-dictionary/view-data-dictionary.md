---
description: Das Datenwörterbuch in Analysis Workspace ermöglicht es Benutzenden, die verschiedenen Komponenten in Analysis Workspace zu katalogisieren und im Auge zu behalten, einschließlich ihres Verwendungszwecks, welche genehmigt sind, welche Duplikate sind usw.
title: Datenwörterbuch anzeigen
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 79%

---

# Komponenteninformationen im Datenwörterbuch anzeigen

Mit dem Datenwörterbuch können Sie Informationen über eine Komponente anzeigen, einschließlich der Komponentenbeschreibung, ähnlicher Komponenten, anderer Komponenten, mit denen eine Komponente häufig verwendet wird, und mehr.

So zeigen Sie Informationen zu einer Komponente im Datenwörterbuch an:

1. Wechseln Sie zum Analysis Workspace-Projekt, das die Komponente enthält, die Sie anzeigen möchten.

1. Wählen Sie das Symbol [!UICONTROL **Datenwörterbuch**] in der linken Leiste von Analysis Workspace. (Alternative Möglichkeiten für den Zugriff auf das Datenwörterbuch sind unter „Zugriff auf das Datenwörterbuch“ in [Datenwörterbuch – Überblick](/help/components/data-dictionary/data-dictionary-overview.md) beschrieben.)

   Das Fenster „Datenwörterbuch“ wird angezeigt.

   ![Datenwörterbuchfenster mit Schnellfiltern für Dimensionen, Metriken, Segmente und Datumsbereiche](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Stellen Sie sicher, dass die Datenansicht mit der Komponente, die Sie anzeigen möchten, im Dropdown-Menü ausgewählt ist. Standardmäßig wird die Datenansicht angezeigt, in der Sie sich bereits befinden.

1. (Optional) Geben Sie im Suchfeld den Namen der Komponente ein, die Sie anzeigen möchten.

   Der Komponententyp kann sowohl durch Farbe als auch durch ein Symbol identifiziert werden. **Dimensionen** ![Dimension-Symbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) sind orange, **Filter** ![Segmentsymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) blau, **Datumsbereiche** ![Datumsbereichssymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) ist violett und **Metriken** ![Metriksymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) sind grün. Das Adobe-Symbol ![Adobe-Symbol](assets/default-calc-metric-icon.png) zeigt entweder eine Vorlage für berechnete Metriken oder eine Filtervorlage an, und das Taschenrechnersymbol ![Taschenrechnersymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) zeigt eine berechnete Metrik an, die von Analytics-Admins in Ihrer Organisation erstellt wurde.

{{dd-filter-criteria}}

1. (Optional) Wählen Sie das Symbol **Sortieren** Symbol ![Komponenten sortieren](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) aus und wählen Sie dann eine der folgenden Filteroptionen, um die Liste der Komponenten zu sortieren:

   {{components-sort-options}}

1. Wählen Sie aus der Komponentenliste die Komponente aus, die Sie anzeigen möchten.

   Es werden die folgenden Informationen über die Komponente angezeigt:

   {{dd-component-information}}

1. (Optional) Ziehen Sie eine Komponente aus dem Datenwörterbuch in Analysis Workspace.
