---
description: Erfahren Sie, wie Sie eine Kohortentabelle erstellen und konfigurieren und einen Kohortenanalysebericht in Analysis Workspace ausführen.
keywords: Analysis Workspace
title: Konfigurieren einer Kohortentabelle
feature: Visualizations
exl-id: c3fd9fbf-b2c8-4703-92de-e6fdc141ebc6
role: User
TQID: https://experienceleague.adobe.com/BRZeBxnzNchx5oqu5RVanrwXEP1c8CgJtZuJcGUFg-0
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: bc7a5a86-1a70-451f-985c-037b65f091d1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 964
ht-degree: 78%

---

# Konfigurieren einer Kohortentabelle

So erstellen und konfigurieren Sie eine [!UICONTROL Kohortentabelle]:

1. Fügen Sie eine ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL Kohortentabellenvisualisierung]** hinzu. Weitere Informationen finden Sie unter [Hinzufügen einer Visualisierung in einem Bedienfeld](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel)

1. Bestimmen Sie die **[!UICONTROL Aufnahmekriterien]**, die **[!UICONTROL Rückkehrkriterien]**, den **[!UICONTROL Kohortentyp]** und die **[!UICONTROL Einstellungen]** wie in der Tabelle unten definiert.

   ![Konfigurieren einer Kohortentabelle](assets/cohort-configure.png)

   | Element | Beschreibung |
   |--- |--- |
   | **[!UICONTROL Aufnahmekriterien]** | Sie können bis zu 10 Aufnahmesegmente und bis zu 3 Aufnahmekennzahlen anwenden. Die Metrik gibt an, zu welcher Kohorte eine Benutzerin bzw. ein Benutzer gehört. Wenn die Aufnahmemetrik z. B. die Bestellungen sind, werden nur Benutzende, die innerhalb des Zeitraums der Kohortenanalyse bestellt haben, in der anfänglichen Kohorte platziert.<br>Der Standardoperator zwischen den Kennzahlen ist AND, kann aber in OR geändert werden. Darüber hinaus können Sie diesen Metriken numerische Segmentierung hinzufügen. Beispiel: `Sessions >= 1`.</br> |
   | **[!UICONTROL Rückkehrkriterien]** | Sie können bis zu 10 Rückkehrsegmente und bis zu 3 Rückkehrkennzahlen anwenden. Die Kennzahl gibt an, ob eine Person gewonnen wurde (Bindung) oder nicht (Abwanderung). Wenn die Rückkehrmetrik z. B. die Videoansichten sind, werden nur Benutzende, die in nachfolgenden Zeiträumen (nach dem Zeitraum, in dem sie zu einer Kohorte hinzugefügt wurden) Videos angesehen haben, als zurückgekehrt dargestellt. Eine weitere Metrik, die die Bindung quantifiziert, sind die Sitzungen. |
   | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Container ]** | Standardmäßig ist die Kohortenanalyse mit dem Personen -Container verknüpft. Wenn von der kontobasierten Verbindung, die das Workspace-Projekt unterstützt, mehr Container als Person verfügbar sind, können Sie aus dem Dropdown-Menü **[!UICONTROL Container]** einen anderen Container für die Kohortenanalyse auswählen. |
   | **[!UICONTROL Granularität]** | Die Zeitgranularität: Tag, Woche, Monat, Quartal oder Jahr. |
   | **[!UICONTROL Typ]** | **[!UICONTROL Bindung]** (Standard): Durch die **[!UICONTROL Bindungskohorte]** wird gemessen, in welchem Maße die Personenkohorten im Laufe der Zeit zu Ihnen zurückkehren. Eine Bindungskohorte ist die Standardkohorte und zeigt das Verhalten von wiederkehrenden Benutzenden an. Eine grüne Farbe zeigt eine Kohorte [!UICONTROL Bindung] in der Tabelle an.<br>**[!UICONTROL Abwanderung ]**: Eine Kohorte**[!UICONTROL  Abwanderung ]**(auch als Attrition oder Fallout bezeichnet) misst, wie Ihre Personenkohorten im Laufe der Zeit aus Ihrer Eigenschaft herausfallen. Abwanderung ist das Gegenteil von Bindung: `Churn = 1 - Retention`. Die [!UICONTROL Abwanderung] ist ein guter Messwert für die Treue und Chancen, da Ihnen gezeigt wird, wie häufig Kundinnen und Kunden nicht zurückkehren. Sie können die Abwanderung nutzen, um Fokusbereiche zu analysieren und zu identifizieren: Welche Kohortensegmente könnten Ihre Aufmerksamkeit erfordern? Eine rote Farbe zeigt eine [!UICONTROL Abwanderungskohorte] in der Tabelle an (ähnlich wie „Fallout“ in der**[!UICONTROL  Flussvisualisierung ]**).</br> |
   | **[!UICONTROL Einstellungen]** | **[!UICONTROL Rollierende Berechnung]**: Ermöglicht es Ihnen, die Bindung oder die Abwanderung auf Grundlage der vorherigen Spalte und nicht der eingeschlossenen Spalte zu berechnen (Standard). Durch eine [!UICONTROL rollierende Berechnung] wird die Berechnungsmethode für Ihre „Rückkehr“-Zeiten verändert. Im Gegensatz dazu findet die normale Berechnung Benutzende, die die Rückkehrkriterien erfüllen und Teil des Einschlusszeitraums waren, unabhängig davon, ob sie im vorherigen Zeitraum in der Kohorte waren oder nicht. Im Gegensatz dazu findet [!UICONTROL Rollierende Berechnung] Benutzer, die die „Rückkehr“-Kriterien erfüllen und Teil des vorherigen Zeitraums waren. Daher werden durch [!UICONTROL Rollierende Berechnung] die Benutzer segmentiert und getrichter, die über einen bestimmten Zeitraum hinweg kontinuierlich die Kriterien für die „Rendite“ erfüllen. [!UICONTROL Rückkehrkriterien] werden auf jeden Zeitraum bis zum ausgewählten Zeitraum angewendet. </br><br>**[!UICONTROL Latenztabelle ]**: Eine [!UICONTROL Latenztabelle] misst die Zeit, die vor und nach dem Aufnahmeereignis verstrichen ist. Die [!UICONTROL Latenztabelle] eignet sich ideal für die Vor- und Nachanalyse. Angenommen, es steht ein Produkt- oder Kampagnen-Launch bevor und Sie möchten das Verhalten vor und nach dem Launch verfolgen. Die [!UICONTROL Latenztabelle] zeigt das Verhalten davor und danach nebeneinander an, um die direkten Auswirkungen darzustellen. Die Zellen für vor der Aufnahme in der [!UICONTROL Latenztabelle] berechnen die Benutzenden, die die [!UICONTROL Einschlusskriterien] für den Aufnahmezeitraum und anschließend die [!UICONTROL Rückkehrkriterien] in den Zeiträumen vor dem Aufnahmezeitraum erfüllen. Die [!UICONTROL Latenztabelle] und die [!UICONTROL bBenutzerdefinierte Kohorte der Dimension] können nicht zusammen verwendet werden.</br><br>**[!UICONTROL Benutzerdefinierte Kohorte der Dimension]**: Erstellen Sie Kohorten auf Grundlage der ausgewählten Dimension und nicht auf Grundlage zeitbasierter Kohorten (Standard). Viele Kunden möchten ihre Kohorten nach etwas anderem als der Zeit analysieren, und die neue Funktion für benutzerdefinierte Kohorten der Dimension bietet Ihnen genau diese Flexibilität, Kohorten basierend auf Dimensionen ihrer Wahl zu erstellen. Verwenden Sie Dimensionen wie Marketing-Kanal, Kampagne, Produkt, Seite, Region oder eine beliebige andere Dimension, um anzuzeigen, wie die Bindung sich basierend auf verschiedenen Werten dieser Dimensionen verändert. Die Segmentdefinition für die Kohorte [!UICONTROL Benutzerspezifische Dimension] wendet das Dimensionselement nur als Teil des Aufnahmezeitraums an, nicht als Teil der Rückgabedefinition.</br><br>Nach Auswahl der Option [!UICONTROL Benutzerdefinierte Kohorte der Dimension] können Sie jede beliebige Dimension in die Drop-Zone ziehen. Durch Hinzufügen von Dimensionen können Sie ähnliche Dimensionselemente über den gleichen Zeitraum hinweg miteinander vergleichen. Sie können beispielsweise die Leistung von Städten nebeneinander, Produkte, Kampagnen usw. vergleichen. Die Kohortentabelle gibt Ihre 14 wichtigsten Dimensionselemente zurück. Sie können jedoch ein Segment ![Segment](/help/assets/icons/Filter.svg) verwenden, um nur die gewünschten Dimensionselemente anzuzeigen. Eine [!UICONTROL benutzerdefinierte Kohorte der Dimension] kann nicht mit der Funktion [!UICONTROL Latenztabelle] verwendet werden.</br> |

1. Klicken Sie auf **[!UICONTROL Erstellen]**.
1. Um die [!UICONTROL Kohortentabelle] erneut zu konfigurieren, wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) aus.

1. (Optional) Erstellen Sie ein Segment oder eine Zielgruppe aus einer Auswahl.

   Wählen Sie Zellen aus (fortlaufende oder nicht fortlaufende) und klicken Sie mit der rechten Maustaste auf **[!UICONTROL Segment aus Auswahl erstellen]**.

   ![Segment oder Zielgruppe erstellen](assets/retention-createfilter.png)

1. Bearbeiten Sie das Segment im [Segment Builder](/help/components/segments/seg-builder.md) weiter und klicken Sie anschließend auf **[!UICONTROL Speichern]**.

   Das gespeicherte Segment kann in [!UICONTROL Analysis Workspace] im Bedienfeld [!UICONTROL Segment] verwendet werden.

## Einstellungen

Sie können bestimmte Einstellungen für eine [!UICONTROL Kohortentabelle] definieren.

1. Wählen Sie ![Setting](/help/assets/icons/Setting.svg) aus, um die Einstellungen für die [!UICONTROL Kohortentabelle] anzupassen.

   | Einstellung | Beschreibung |
   |---|---|
   | **Nur Prozentwert anzeigen** | Entfernt den Zahlenwert und zeigt nur den Prozentsatz an. |
   | **Prozentwert auf nächste Ganzzahl runden** | Rundet den Prozentwert auf den nächsten ganzzahligen Wert, anstatt den Dezimalwert anzuzeigen. |
   | **Zeile mit durchschnittlichem Prozentwert anzeigen** | Fügt oben in der Tabelle eine neue Zeile ein und trägt dort die Spaltendurchschnitte der Werte ein. |


>[!MORELIKETHIS]
>
>[Hinzufügen einer Visualisierung zu einem Bedienfeld](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Einstellungen der Visualisierung](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Kontextmenü der Visualisierung](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

