---
description: Erstellen Sie eine Kohortentabelle und führen Sie eine Kohortenanalyse in Analysis Workspace durch.
keywords: Analysis Workspace
title: Konfigurieren einer Kohortentabelle
feature: Visualizations
exl-id: c3fd9fbf-b2c8-4703-92de-e6fdc141ebc6
role: User
source-git-commit: c16ad9f490abed1e15e1012a5a9347e2628b7642
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 33%

---

# Konfigurieren einer Kohortentabelle

So erstellen und konfigurieren Sie eine [!UICONTROL Kohortentabelle]:

1. Fügen Sie eine Visualisierung ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL Kohortentabelle]** hinzu. Siehe [Hinzufügen einer Visualisierung zu einem Bedienfeld](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Bestimmen Sie die **[!UICONTROL Aufnahmekriterien]**, die **[!UICONTROL Rückkehrkriterien]**, den **[!UICONTROL Kohortentyp]** und die **[!UICONTROL Einstellungen]** wie in der Tabelle unten definiert.

   ![Konfigurieren einer Kohortentabelle](assets/cohort-configure.png)

   | Element | Beschreibung |
   |--- |--- |
   | **[!UICONTROL Einschlusskriterien]** | Sie können bis zu 10 Einschlussfilter und bis zu 3 Einschlussmetriken anwenden. Die Metrik gibt an, zu welcher Kohorte ein Benutzer gehört. Wenn die Einschlussmetrik beispielsweise „Bestellungen“ lautet, werden nur Benutzende, die während des Zeitraums der Kohortenanalyse eine Bestellung aufgegeben haben, in die anfängliche Kohorte einbezogen.<br>Der Standardoperator zwischen den Kennzahlen ist AND, kann aber in OR geändert werden. Außerdem können Sie diesen Metriken numerische Filter hinzufügen. Beispiel: `Sessions >= 1`.</br> |
   | **[!UICONTROL Rückgabekriterien]** | Sie können bis zu 10 Rückgabefilter und bis zu 3 Rückgabemetriken anwenden. Die Kennzahl gibt an, ob ein Benutzer gewonnen wurde (Bindung) oder nicht (Abwanderung). Wenn die Rückgabe-Metrik beispielsweise Videoansichten lautet, werden nur Benutzer, die Videos in nachfolgenden Zeiträumen (nach dem Zeitraum, in dem sie zu einer Kohorte hinzugefügt wurden) angesehen haben, als beibehalten dargestellt. Eine weitere Metrik, die die Kundenbindung quantifiziert, sind Sitzungen. |
   | **[!UICONTROL Granularität]** | Die Zeitgranularität: Tag, Woche, Monat, Quartal oder Jahr. |
   | **[!UICONTROL Typ]** | **[!UICONTROL Bindung]** (Standard): Eine **[!UICONTROL Bindung]**-Kohorte misst, wie gut Ihre Personenkohorten im Laufe der Zeit zu Ihrer Eigenschaft zurückkehren. Eine Aufbewahrungskohorte ist die Standardkohorte und zeigt das Verhalten von wiederkehrenden und wiederholten Benutzenden an. Eine grüne Farbe weist auf eine [!UICONTROL Bindung] Kohorte in der Tabelle hin.<br>**[!UICONTROL Abwanderung ]**: Eine**[!UICONTROL  Abwanderung ]**(auch als Attrition oder Fallout bezeichnet) misst, wie Ihre Personenkohorten im Laufe der Zeit aus Ihrer Eigenschaft herausfallen. Abwanderung ist das Gegenteil von Bindung: `Churn = 1 - Retention`. Die [!UICONTROL Abwanderung] ist ein guter Messwert für die Treue und Chancen, da Ihnen gezeigt wird, wie häufig Kunden nicht zurückkehren. Sie können die Abwanderung nutzen, um Fokusbereiche zu analysieren und zu identifizieren: Welche Kohortenfilter könnten Ihre Aufmerksamkeit erfordern? Eine rote Farbe zeigt eine [!UICONTROL Abwanderung] Kohorte in der Tabelle an (ähnlich wie Fallout in der**[!UICONTROL  Fluss ]**Visualisierung)</br> |
   | **[!UICONTROL Einstellungen]** | **[!UICONTROL Rollierende Berechnung]**: Berechnung der Kundenbindung oder Abwanderung basierend auf der vorherigen Spalte und nicht auf der eingeschlossenen Spalte (Standard). Durch [!UICONTROL Rollierende Berechnung] wird die Berechnungsmethode für Ihre „Rückkehr“-Zeiten verändert. Bei der normalen Berechnung werden Benutzer gefunden, die die Rückgabekriterien erfüllen und Teil des Einschlusszeitraums waren. Unabhängig davon, ob sie im vorherigen Zeitraum in der Kohorte waren oder nicht. Im Gegensatz dazu findet [!UICONTROL Rollierende Berechnung] Benutzer, die die „Rückkehr“-Kriterien erfüllen und Teil des vorherigen Zeitraums waren. Daher filtert [!UICONTROL Rollierende Berechnung] Benutzer, die die „Rückkehr“-Kriterien kontinuierlich in jedem Zeitraum erfüllen, und trichtert sie. [!UICONTROL Return]-Kriterien werden auf jeden Zeitraum angewendet, der vor dem ausgewählten Zeitraum liegt. </br><br>**[!UICONTROL Latenztabelle ]**: Eine [!UICONTROL Latenztabelle] misst die Zeit, die vor und nach dem Einschlussereignis verstrichen ist. [!UICONTROL Latenztabelle] eignet sich hervorragend für Vor-/Nachanalysen. Sie haben beispielsweise einen bevorstehenden Produkt- oder Kampagnen-Launch und möchten das Verhalten vor und nach dem Launch verfolgen. Die [!UICONTROL Latenztabelle] zeigt das Vor- und Nachbearbeitungsverhalten nebeneinander an, um die direkten Auswirkungen anzuzeigen. Mit den Zellen vor der Aufnahme in der [!UICONTROL Latenztabelle] werden Benutzer berechnet, die die [!UICONTROL Einschluss]-Kriterien für den Einschlusszeitraum erfüllen und dann die [!UICONTROL Rückkehr]-Kriterien in den Zeiträumen vor dem Einschlusszeitraum erfüllen. Beachten Sie[!UICONTROL  dass ]Latenztabelle) und [!UICONTROL benutzerdefinierte Dimensionskohorte] nicht zusammen verwendet werden können.</br><br>**[!UICONTROL Benutzerdefinierte Dimensionskohorte]**: Erstellen Sie Kohorten basierend auf der ausgewählten Dimension und nicht auf zeitbasierten Kohorten (Standard). Viele Kunden möchten ihre Kohorten nach etwas anderem als der Zeit analysieren, und die neue Funktion für benutzerdefinierte Dimensionskohorten bietet Ihnen genau diese Flexibilität, Kohorten basierend auf Dimensionen ihrer Wahl zu erstellen. Verwenden Sie Dimensionen wie Marketing-Kanal, Kampagne, Produkt, Seite, Region oder jede andere Dimension, um anzuzeigen, wie sich die Kundenbindung basierend auf den verschiedenen Werten dieser Dimensionen ändert. Die Definition eines Kohortenfilters mit [!UICONTROL benutzerspezifischer Dimension] wendet das Dimensionselement nur als Teil des Einschlusszeitraums an, nicht als Teil der Rückgabedefinition.</br><br>Nach Auswahl der Option [!UICONTROL Benutzerdefinierte Dimensionskohorte] können Sie die gewünschte Dimension per Drag-and-Drop in den Ablagebereich ziehen. Durch das Hinzufügen von Dimensionen können Sie ähnliche Dimensionselemente über denselben Zeitraum hinweg vergleichen. Sie können beispielsweise die Leistung von Städten nebeneinander, Produkte, Kampagnen usw. vergleichen. Die Kohortentabelle gibt Ihre 14 wichtigsten Dimensionselemente zurück. Sie können jedoch einen Filter ![Filter](/help/assets/icons/Filter.svg) verwenden, um nur die gewünschten Dimensionselemente anzuzeigen. Eine [!UICONTROL Kohorte benutzerdefinierter Dimensionen] kann nicht mit der Funktion [!UICONTROL Latenztabelle] verwendet werden.</br> |

1. Klicken Sie auf **[!UICONTROL Erstellen]**.
1. Um die [!UICONTROL Kohortentabelle“ neu zu konfigurieren] wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) aus.

1. (Optional) Erstellen Sie einen Filter oder eine Zielgruppe aus einer Auswahl.

   Wählen Sie Zellen aus (fortlaufende oder nicht fortlaufende) und klicken Sie mit der rechten Maustaste auf **[!UICONTROL Filter aus Auswahl erstellen]**.

   ![Filter oder Zielgruppe erstellen](assets/retention-createfilter.png)

1. Bearbeiten [ den Filter im ](/help/components/filters/filter-builder.md) weiter und klicken Sie dann auf **[!UICONTROL Speichern]**.

   Der gespeicherte Filter ist im Bedienfeld [!UICONTROL Filter] in [!UICONTROL Analysis Workspace] für die Verwendung verfügbar.

## Einstellungen

Sie können spezifische Einstellungen für eine [!UICONTROL Kohortentabelle“ ].

1. Wählen Sie ![Einstellung](/help/assets/icons/Setting.svg) aus, um die Einstellungen [!UICONTROL Kohortentabelle] anzupassen.

   | Einstellung | Beschreibung |
   |---|---|
   | **Nur Prozentwert anzeigen** | Entfernt den Zahlenwert und zeigt nur den Prozentsatz an. |
   | **Prozentwert auf nächste Ganzzahl runden** | Rundet den Prozentwert auf den nächsten ganzzahligen Wert, anstatt den Dezimalwert anzuzeigen. |
   | **Zeile mit durchschnittlichem Prozentwert anzeigen** | Fügt oben in der Tabelle eine neue Zeile ein und fügt dann den Spaltendurchschnitt der Werte hinzu. |


>[!MORELIKETHIS]
>
>[Hinzufügen einer Visualisierung zu einem Bedienfeld](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualisierungseinstellungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Kontextmenü der Visualisierung](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

