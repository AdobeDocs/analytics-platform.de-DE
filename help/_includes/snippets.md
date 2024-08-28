---
source-git-commit: d903745e105edb11ef6f43b6137e1e03d43e5e07
workflow-type: tm+mt
source-wordcount: '1253'
ht-degree: 58%

---
# Snippets

## Eingeschränkte Testphase der Veröffentlichung {#release-limited-testing}

>[!AVAILABILITY]
>
>Die in diesem Artikel beschriebene Funktion befindet sich in der eingeschränkten Testphase der Version und ist möglicherweise noch nicht in Ihrer Umgebung verfügbar. Diese Anmerkung wird entfernt, wenn die Funktion allgemein verfügbar ist. Weitere Informationen zum Customer Journey Analytics-Veröffentlichungsprozess finden Sie unter [Customer Journey Analytics-Feature Releases](/help/release-notes/releases.md).

## Abschnitt zur eingeschränkten Testphase der Veröffentlichung {#release-limited-testing-section}

>[!AVAILABILITY]
>
>Die in diesem Abschnitt beschriebene Funktion befindet sich in der eingeschränkten Testphase der Version und ist möglicherweise noch nicht in Ihrer Umgebung verfügbar. Diese Anmerkung wird entfernt, wenn die Funktion allgemein verfügbar ist. Weitere Informationen zum Customer Journey Analytics-Veröffentlichungsprozess finden Sie unter [Customer Journey Analytics-Feature Releases](/help/release-notes/releases.md).

## Paket auswählen {#select-package}

>[!NOTE]
>
>Sie müssen über das Paket **Select** oder höher verfügen, um die in diesem Abschnitt beschriebene Funktion verwenden zu können. Wenden Sie sich an Ihre Admins, wenn Sie sich nicht sicher sind, welches Customer Journey Analytics-Paket Sie besitzen.

## Prime-Paket {#prime-package}

>[!NOTE]
>
>Sie müssen über das Paket **Prime** oder höher verfügen, um die in diesem Abschnitt beschriebene Funktionalität nutzen zu können. Wenden Sie sich an Ihre Admins, wenn Sie sich nicht sicher sind, welches Customer Journey Analytics-Paket Sie besitzen.

## Ultimate Package {#ultimate-package}

>[!NOTE]
>
>Sie müssen über das Paket **Ultimate** verfügen, um die in diesem Abschnitt beschriebene Funktionalität nutzen zu können. Wenden Sie sich an Ihre Admins, wenn Sie sich nicht sicher sind, welches Customer Journey Analytics-Paket Sie besitzen.


## Filterkriterien für Datenwörterbuch {#dd-filter-criteria}

1. (Optional) Wählen Sie das Symbol **Filter** ![Datenwörterbuchfilter-Symbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) und wählen Sie dann eine der folgenden Filteroptionen, um die Liste der Komponenten zu filtern:

   | Option | Funktion |
   |---------|----------|
   | [!UICONTROL **Genehmigt**] | Nur Komponenten anzeigen, die von Admins als genehmigt markiert wurden. |
   | [!UICONTROL **Favoriten**] | Nur Komponenten anzeigen, die sich in Ihrer Favoritenliste befinden. Informationen zum Hinzufügen von Komponenten zur Favoritenliste finden Sie in der [Komponentenübersicht](/help/components/overview.md). |
   | [!UICONTROL **Dimensionen**] | Nur Komponenten anzeigen, die Dimensionen sind. (Diese Option ist auch auf der Registerkarte [!UICONTROL **Schnellfilter**] verfügbar, wenn Sie das Datenwörterbuch zum ersten Mal aufrufen.) |
   | [!UICONTROL **Metriken**] | Nur Komponenten anzeigen, die Metriken sind. (Diese Option ist auch auf der Registerkarte [!UICONTROL **Schnellfilter**] verfügbar, wenn Sie das Datenwörterbuch zum ersten Mal aufrufen.) |
   | [!UICONTROL **Filter**] | Nur Komponenten anzeigen, die Filter sind. (Diese Option ist auch auf der Registerkarte [!UICONTROL **Schnellfilter**] verfügbar, wenn Sie das Datenwörterbuch zum ersten Mal aufrufen.) <!--this is Filters in Customer Journey Analytics--> |
   | [!UICONTROL **Datumsbereiche**] | Zeigt nur Komponenten an, die Datumsbereiche sind. (Diese Option ist auch auf der Registerkarte [!UICONTROL **Schnellfilter**] verfügbar, wenn Sie das Datenwörterbuch zum ersten Mal aufrufen.) |
   | [!UICONTROL **Alle anzeigen**] | Alle Komponenten anzeigen. Diese Option steht nur Admins zur Verfügung. |
   | [!UICONTROL **Nicht genehmigt**] | Nur Komponenten anzeigen, die von Admins noch nicht als genehmigt markiert wurden. Für Admins beim Identifizieren von Komponenten hilfreich, die überprüft und genehmigt werden müssen. Diese Option steht nur Admins zur Verfügung. |
   | [!UICONTROL **Fehlende Beschreibung**] | Nur Komponenten anzeigen, die noch keine Beschreibung im Feld „Beschreibung“ haben. Diese Option steht nur Admins zur Verfügung. |
   | [!UICONTROL **Duplikate anzeigen**] | Zeigen Sie in der ausgewählten Datenansicht nur Komponenten mit demselben Namen oder derselben Beschreibung wie eine andere Komponente an. Dies umfasst sowohl von Ihnen erstellte Komponenten als auch die von Adobe bereitgestellten Komponenten. Namen oder Beschreibungen müssen exakt übereinstimmen, damit sie als Duplikate angezeigt werden. Diese Option steht nur Admins zur Verfügung. |
   | [!UICONTROL **Keine aktuellen Daten**] | Nur Komponenten anzeigen, die in den letzten 90 Tagen keine Daten erfasst haben. Diese Option steht nur Admins zur Verfügung. |
   | [!UICONTROL **Erstellt von Adobe**] <!-- I don't see this option--> | Nur Komponenten anzeigen, die von Adobe erstellt wurden. Komponenten, die von Admins oder anderen Benutzenden in deren Organisation erstellt wurden, werden nicht angezeigt. |

   {style="table-layout:auto"}

## Komponenteninformationen für Datenwörterbuch {#dd-component-information}

| Option | Funktion |
|---------|----------|
| [!UICONTROL **Genehmigt**] | <p>Zeigt an, dass die Komponente vom Admins geprüft und genehmigt wurde.</p><p>Administratoren sehen die Option &quot;[!UICONTROL **Nicht genehmigen**]&quot;. Wenn Sie diese Option auswählen, wird die Komponente für Benutzer als &quot;Nicht genehmigt&quot;gekennzeichnet.</p> |
| [!UICONTROL **Nicht genehmigt**] | <p>Zeigt an, dass die Komponente noch nicht von Admins geprüft und genehmigt wurde.</p><p>Admins wird eine Option zum [!UICONTROL **Genehmigen**] angezeigt. Bei Auswahl dieser Option wird die Komponente gegenüber Benutzenden als „Genehmigt“ gekennzeichnet.</p> |
| [!UICONTROL **Beschreibung**] | Beschreibt die beabsichtigte Funktion der Komponente. (Diese Informationen werden vom Analytics-Admins hinzugefügt, wie unter [Komponentenbeschreibungen hinzufügen](/help/components/add-component-descriptions.md) beschrieben.) |
| [!UICONTROL **Häufig verwendet mit**] | <p>Zeigt Komponenten an, die am häufigsten mit der Komponente verwendet werden, die Sie anzeigen.</p><p>Bis zu 5 Komponenten werden für die fünf primären Komponententypen angezeigt: Metrik, berechnete Metrik, Dimension, Filter und Datumsbereich.</p><p>Diese Liste basiert auf Daten aus den letzten 90 Tagen. Es werden nur Komponenten angezeigt, auf die Sie Zugriff haben.</p><p>Admins können die Komponenten, die Benutzende in diesem Abschnitt sehen, kuratieren, indem sie die gewünschten Komponenten in den Dropdown-Feldern [!UICONTROL **Immer einschließen**] und [!UICONTROL **Immer ausschließen**] auswählen. Wenden Sie vor dem Kuratieren der Komponenten, die Benutzern angezeigt werden, zunächst den Filter **Alle anzeigen** an, um sicherzustellen, dass Sie alle Komponenten sehen, die nicht für Sie freigegeben sind und möglicherweise von einem anderen Administrator hinzugefügt wurden.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Ähnlich wie**] | <p>Zeigt Komponenten mit ähnlichen Namen wie die angezeigte Komponente an.</p><p>Bis zu 5 Komponenten werden für die fünf primären Komponententypen angezeigt: Metrik, berechnete Metrik, Dimension, Filter und Datumsbereich.</p><p>Es werden nur Komponenten angezeigt, auf die Sie Zugriff haben.</p><p>Hier werden alle doppelten Komponenten in Ihrer Datenansicht angezeigt. Analytics-Admins sollten alle doppelten Komponenten identifizieren und entfernen, wie unter [Überwachen des Zustands des Datenwörterbuchs](/help/components/data-dictionary/monitor-data-dictionary-health.md) beschrieben.</p><p>Adminis können die Komponenten, die Benutzende in diesem Abschnitt sehen, kuratieren, indem sie die gewünschten Komponenten in den Dropdown-Feldern [!UICONTROL **Immer einschließen**] und [!UICONTROL **Immer ausschließen**] auswählen. Wenden Sie vor dem Kuratieren der Komponenten, die Benutzern angezeigt werden, zunächst den Filter **Alle anzeigen** an, um sicherzustellen, dass Sie alle Komponenten sehen, die nicht für Sie freigegeben sind und möglicherweise von einem anderen Administrator hinzugefügt wurden.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**HINWEIS:** Derzeit enthält der Abschnitt **Ähnlich wie** nur von Ihnen erstellte Komponenten und nicht die von Adobe bereitgestellten Komponenten. Von Adobe bereitgestellte Komponenten werden in einer zukünftigen Version hinzugefügt.</p> |
| [!UICONTROL **Produktkompatibilität**] | Gibt an, wo in der Customer Journey Analytics diese berechnete Metrik verwendet werden kann. <p>Die möglichen Werte sind:</p><ul><li>[!UICONTROL **Überall auf Customer Journey Analytics**]: Die berechnete Metrik kann für alle Customer Journey Analytics verwendet werden, einschließlich Analysis Workspace, Report Builder usw.</li><li>[!UICONTROL **Überall auf Customer Journey Analytics (ohne Experimentierung)**]: Die berechnete Metrik kann überall auf der Customer Journey Analytics verwendet werden, außer im Bereich &quot;Experimentierung&quot;.</li> <p>Informationen zu den Kriterien, die bestimmen, ob eine berechnete Metrik mit Experimenten verwendet werden kann, finden Sie unter [Berechnete Metriken im Experimentierungsbereich verwenden](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) im [Experimentierungsbereich](/help/analysis-workspace/c-panels/experimentation.md).</p></ul> |
| [!UICONTROL **Tags**] | Zeigt alle Tags an, die auf die Komponente angewendet werden. Benutzende mit Adminrechten können bei der Bearbeitung der Komponente Tags hinzufügen. |
| [!UICONTROL **Typ der Komponente**] | Listet den Komponententyp auf, der es ist, unabhängig davon, ob es sich um eine Dimension, eine Metrik, einen Filter oder einen Datumsbereich handelt. |
| [!UICONTROL **Erstellt von**] | Zeigt den Namen der Person an, die die Komponente erstellt hat. |
| [!UICONTROL **Vorschau**] | Zeigt eine Vorschau davon an, wie die Komponente im Analysis Workspace aussieht. |
| [!UICONTROL **Datum der letzten Änderung**] | Zeigt den Tag an, an dem die Komponente zuletzt geändert wurde. Dieser Abschnitt wird beim Anzeigen von Filtern, Metriken, berechneten Metriken und Datumsbereichen angezeigt. |

{style="table-layout:auto"}

## Sortieroptionen von Komponenten {#components-sort-options}

| Option | Funktion |
|---------|----------|
| [!UICONTROL **Empfohlen**] | Sortiert Komponenten nach den am Anfang der Liste empfohlenen Komponenten. Komponenten, die am häufigsten und zuletzt von Ihnen oder anderen in Ihrem Unternehmen verwendet werden, werden weiter oben in der Liste angezeigt. |
| [!UICONTROL **Alphabetisch**] | Sortiert Komponenten alphabetisch. |
| [!UICONTROL **Kategorisch**] | Sortiert Komponenten nach Komponententyp (Dimension, Metrik, Filter, Datumsbereich). |

{style="table-layout:auto"}

## Zeitvergleich {#apply-time-comparison}

Sie können den aktuellen Zeitraum mit einem vorherigen Zeitraum vergleichen. Wenn Sie in diesem Menü eine Option auswählen, erhält jeder Datenpunkt ein ähnlich farbiges gepunktetes Gegenstück. Dieses Gegenstück stellt dieselbe Metrik im ausgewählten vorherigen Datumsbereich dar. Wenn Sie diese Option festlegen, verdoppelt sich die Anzahl der Elemente im Diagramm und der Zeilen in der Tabelle.

Zu den verfügbaren Zeitvergleichsoptionen gehören der vorherige Zeitraum, 13 Wochen zuvor, 52 Wochen zuvor und ein benutzerdefinierter Datumsbereich. Wenn Sie den benutzerdefinierten Datumsbereich auswählen, werden zusätzliche Optionen angezeigt, mit denen Sie die Zahl und Granularität auswählen können. Wenn Sie &quot;Keine&quot;auswählen, wird der Datumsvergleich entfernt.
