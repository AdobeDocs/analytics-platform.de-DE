---
description: Das Datenwörterbuch in Analysis Workspace ermöglicht es Benutzenden, die verschiedenen Komponenten in Analysis Workspace zu katalogisieren und im Auge zu behalten, einschließlich ihres Verwendungszwecks, welche genehmigt sind, welche Duplikate sind usw.
title: Bearbeiten von Komponenteneinträgen
feature: Components
role: Admin
exl-id: 2d232811-e34a-4667-819c-cbe2a3e72702
source-git-commit: f940e5cba11df0ff158093a503213ff1641b1c5d
workflow-type: tm+mt
source-wordcount: '1254'
ht-degree: 67%

---

# Bearbeiten von Komponenteneinträgen

Customer Journey Analytics-Admins können Komponenteneinträge im Datenwörterbuch für eine bestimmte Datenansicht bearbeiten. Alle vorgenommenen Änderungen sind für alle Benutzer der Datenansicht sichtbar.

Bearbeiten einer Komponente im Datenwörterbuch:

1. Wechseln Sie zum Analysis Workspace-Projekt, das die zu bearbeitende Komponente enthält.

1. Wählen Sie das **Datenwörterbuch** im Schaltflächenbereich von Analysis Workspace aus. (Alternative Möglichkeiten für den Zugriff auf das Datenwörterbuch sind unter „Zugriff auf das Datenwörterbuch“ in [Datenwörterbuch – Überblick](/help/components/data-dictionary/data-dictionary-overview.md) beschrieben.)

   Das Fenster „Datenwörterbuch“ wird angezeigt.

   ![Administratoransicht des Datenwörterbuchs mit Zustand des Wörterbuchs](assets/data-dictionary-admin.png)

1. Stellen Sie sicher, dass im Dropdown-Menü die richtige Datenansicht ausgewählt ist. Standardmäßig wird die Datenansicht angezeigt, in der Sie sich bereits befinden.

1. (Optional) Geben Sie im Suchfeld den Namen der Komponente ein, die Sie bearbeiten möchten.

   Der Komponententyp kann sowohl durch Farbe als auch durch ein Symbol identifiziert werden. **Dimensionen** ![Dimensionsymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) sind orange, **Segmente** ![Segmentsymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) sind blau, **Datumsbereiche** ![Datumsbereichsymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) sind violett und **Metriken** ![Metriksymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) sind grün. Das Adobe-Symbol zeigt entweder eine Vorlage für berechnete Metriken oder eine Segmentvorlage an und das Taschenrechnersymbol ![Taschenrechnersymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) zeigt eine berechnete Metrik an, die von einer Analytics-Administratorin bzw. einem -Administrator in Ihrer Organisation erstellt wurde.

1. (Optional) Wählen Sie das Symbol **Filter** ![Datenwörterbuchfilter-Symbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) und wählen Sie dann eine der folgenden Filteroptionen, um die Liste der Komponenten zu filtern:

   | Option | Funktion |
   |---------|----------|
   | **[!UICONTROL Genehmigt]** | Nur Komponenten anzeigen, die von Admins als genehmigt markiert wurden. |
   | **[!UICONTROL Favoriten]** | Nur Komponenten anzeigen, die sich in Ihrer Favoritenliste befinden. Informationen zum Hinzufügen von Komponenten zur Favoritenliste finden Sie in der [Komponentenübersicht](/help/components/overview.md). |
   | **[!UICONTROL Dimensionen]** | Nur Komponenten anzeigen, die Dimensionen sind. (Diese Option ist auch auf der Registerkarte **[!UICONTROL Schnellsegmente]** verfügbar, wenn Sie das Datenwörterbuch zum ersten Mal aufrufen.) |
   | **[!UICONTROL Metriken]** | Nur Komponenten anzeigen, die Metriken sind. (Diese Option ist auch auf der Registerkarte **[!UICONTROL Schnellsegmente]** verfügbar, wenn Sie das Datenwörterbuch zum ersten Mal aufrufen.) |
   | **[!UICONTROL Segmente]** | Nur Komponenten anzeigen, die Segmente sind. (Diese Option ist auch auf der Registerkarte **[!UICONTROL Schnellsegmente]** verfügbar, wenn Sie das Datenwörterbuch zum ersten Mal aufrufen.) |
   | **[!UICONTROL Datumsbereiche]** | Zeigt nur Komponenten an, die Datumsbereiche sind. (Diese Option ist auch auf der Registerkarte **[!UICONTROL Schnellsegmente]** verfügbar, wenn Sie das Datenwörterbuch zum ersten Mal aufrufen.) |
   | **[!UICONTROL Alle anzeigen]** | Alle Komponenten anzeigen. Diese Option steht nur Admins zur Verfügung. |
   | **[!UICONTROL Nicht genehmigt]** | Nur Komponenten anzeigen, die von Admins noch nicht als genehmigt markiert wurden. Für Admins beim Identifizieren von Komponenten hilfreich, die überprüft und genehmigt werden müssen. Diese Option steht nur Admins zur Verfügung. |
   | **[!UICONTROL Fehlende Beschreibung]** | Nur Komponenten anzeigen, die noch keine Beschreibung im Feld „Beschreibung“ haben. Diese Option steht nur Admins zur Verfügung. |
   | **[!UICONTROL Duplikate anzeigen]** | Nur Komponenten anzeigen, die in der ausgewählten Datenansicht denselben Namen oder dieselbe Beschreibung wie eine andere Komponente haben. Dazu gehören sowohl von Ihnen erstellte als auch von Adobe bereitgestellte Komponenten. Namen oder Beschreibungen müssen exakt übereinstimmen, damit sie als Duplikate angezeigt werden. Diese Option steht nur Admins zur Verfügung. |
   | **[!UICONTROL Keine aktuellen Daten]** | Nur Komponenten anzeigen, die in den letzten 90 Tagen keine Daten erfasst haben. Diese Option steht nur Admins zur Verfügung. |
   | **[!UICONTROL Erstellt von Adobe]** <!-- I don't see this option--> | Nur Komponenten anzeigen, die von Adobe erstellt wurden. Beispiel: **[!UICONTROL Adobe Target]**. Komponenten, die von Admins oder anderen Benutzenden in deren Organisation erstellt wurden, werden nicht angezeigt. |

   {style="table-layout:auto"}

1. (Optional) Wählen Sie das Symbol **Sortieren** Symbol ![Komponenten sortieren](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) und wählen Sie dann eine der folgenden Segmentoptionen, um die Liste der Komponenten zu sortieren:

   | Option | Funktion |
   |---------|----------|
   | [!UICONTROL **Empfohlen**] | Sortiert Komponenten nach den am Anfang der Liste empfohlenen Komponenten. Komponenten, die am häufigsten und zuletzt von Ihnen oder anderen in Ihrem Unternehmen verwendet werden, werden weiter oben in der Liste angezeigt. |
   | [!UICONTROL **Alphabetisch**] | Sortiert Komponenten alphabetisch. |
   | [!UICONTROL **Kategorisch**] | Sortiert Komponenten nach Komponententyp (Dimension, Metrik, Segment, Datumsbereich). |

   {style="table-layout:auto"}

1. Wählen Sie aus der Komponentenliste die Komponente aus, die Sie bearbeiten möchten.

1. Wählen Sie das Symbol **Bearbeiten** ![Datenwörterbuch bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) neben dem Komponentennamen.

1. Bearbeiten Sie eine der folgenden Informationen zur Komponente:

   | Option | Funktion |
   |---------|----------|
   | **[!UICONTROL Genehmigt]** | <p>Zeigt an, dass die Komponente vom Admins geprüft und genehmigt wurde.</p><p>Admins wird eine Option zum **[!UICONTROL Nicht genehmigen“]**. Bei Auswahl dieser Option wird die Komponente für Benutzer als „Nicht genehmigt“ markiert.</p> |
   | **[!UICONTROL Nicht genehmigt]** | <p>Zeigt an, dass die Komponente noch nicht von Admins geprüft und genehmigt wurde.</p><p>Admins wird eine Option zum **[!UICONTROL Genehmigen]** angezeigt. Bei Auswahl dieser Option wird die Komponente gegenüber Benutzenden als „Genehmigt“ gekennzeichnet.</p> |
   | **[!UICONTROL Beschreibung]** | Beschreibt die beabsichtigte Funktion der Komponente. (Diese Informationen werden vom Analytics-Admins hinzugefügt, wie unter [Komponentenbeschreibungen hinzufügen](/help/components/add-component-descriptions.md) beschrieben.) |
   | **[!UICONTROL Häufig verwendet mit]** | <p>Zeigt Komponenten an, die am häufigsten mit der Komponente verwendet werden, die Sie anzeigen.</p><p>Es werden bis zu 5 Komponenten für die 5 primären Komponententypen angezeigt: Metrik, Berechnete Metrik, Dimension, Segment und Datumsbereich.</p><p>Diese Liste basiert auf Daten aus den letzten 90 Tagen. Es werden nur Komponenten angezeigt, auf die Sie Zugriff haben.</p><p>Admins können die Komponenten, die Benutzende in diesem Abschnitt sehen, kuratieren, indem sie die gewünschten Komponenten in den Dropdown-Feldern **[!UICONTROL Immer einschließen]** und **[!UICONTROL Immer ausschließen]** auswählen. Bevor Sie die Komponenten kuratieren, die Benutzenden angezeigt werden, wenden Sie zunächst das Segment **Alle anzeigen** an, um sicherzustellen, dass Sie alle Komponenten sehen, die nicht für Sie freigegeben sind und möglicherweise von einem anderen Administrator hinzugefügt wurden.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p> |
   | **[!UICONTROL Ähnlich wie]** | <p>Zeigt Komponenten mit ähnlichen Namen wie die angezeigte Komponente an.</p><p>Es werden bis zu 5 Komponenten für die 5 primären Komponententypen angezeigt: Metrik, Berechnete Metrik, Dimension, Segment und Datumsbereich.</p><p>Es werden nur Komponenten angezeigt, auf die Sie Zugriff haben.</p><p>Hier werden alle doppelten Komponenten in Ihrer Datenansicht angezeigt. Analytics-Admins sollten alle doppelten Komponenten identifizieren und entfernen, wie unter [Überwachen des Zustands des Datenwörterbuchs](/help/components/data-dictionary/monitor-data-dictionary-health.md) beschrieben.</p><p>Adminis können die Komponenten, die Benutzende in diesem Abschnitt sehen, kuratieren, indem sie die gewünschten Komponenten in den Dropdown-Feldern **[!UICONTROL Immer einschließen]** und **[!UICONTROL Immer ausschließen]** auswählen. Bevor Sie die Komponenten kuratieren, die Benutzenden angezeigt werden, wenden Sie zunächst das Segment **Alle anzeigen** an, um sicherzustellen, dass Sie alle Komponenten sehen, die nicht für Sie freigegeben sind und möglicherweise von einem anderen Administrator hinzugefügt wurden.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p><p>**HINWEIS:** Derzeit enthält der Abschnitt **Ähnlich wie** nur von Ihnen erstellte Komponenten und nicht die von Adobe bereitgestellten Komponenten. Von Adobe bereitgestellte Komponenten werden in einer zukünftigen Version hinzugefügt.</p> |
   | **[!UICONTROL Produktkompatibilität]** | Gibt an, wo in Customer Journey Analytics diese berechnete Metrik verwendet werden kann. <p>Die möglichen Werte sind:</p><ul><li>**[!UICONTROL Überall in Customer Journey Analytics]**: Die berechnete Metrik kann in ganz Customer Journey Analytics verwendet werden, einschließlich Analysis Workspace, Report Builder usw.</li><li>**[!UICONTROL Überall in Customer Journey Analytics (außer beim Experimentieren)]**: Die berechnete Metrik kann überall in Customer Journey Analytics verwendet werden, mit Ausnahme des Panels „Experimentieren“.</li> <p>Informationen zu den Kriterien, die bestimmen, ob eine berechnete Metrik beim Experimentieren verwendet werden kann, finden Sie unter [Verwenden berechneter Metriken im Bedienfeld ](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel)Experimentieren[ im Bedienfeld Experimentieren](/help/analysis-workspace/c-panels/experimentation.md).</p></ul> |
   | **[!UICONTROL Tags]** | Zeigt alle Tags an, die auf die Komponente angewendet werden. Benutzende mit Adminrechten können bei der Bearbeitung der Komponente Tags hinzufügen. |
   | **[!UICONTROL Typ der Komponente]** | Listet den Komponententyp auf, ob es sich um eine Dimension, eine Metrik, ein Segment oder einen Datumsbereich handelt. |
   | **[!UICONTROL Erstellt von]** | Zeigt den Namen der Person an, die die Komponente erstellt hat. |
   | **[!UICONTROL Vorschau]** | Zeigt eine Vorschau davon an, wie die Komponente im Analysis Workspace aussieht. |
   | **[!UICONTROL Datum der letzten Änderung]** | Zeigt den Tag an, an dem die Komponente zuletzt geändert wurde. Dieser Abschnitt wird beim Anzeigen von Segmenten, Metriken, berechneten Metriken und Datumsbereichen angezeigt. |

   {style="table-layout:auto"}

1. Klicken Sie auf das Symbol **Speichern** ![Datenwörterbuch speichern](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg), um Ihre Änderungen zu speichern.
