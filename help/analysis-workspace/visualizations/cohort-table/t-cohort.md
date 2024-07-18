---
description: Erstellen Sie in Analysis Workspace eine Kohorte und führen Sie einen Kohortenanalysebericht aus.
keywords: Analysis Workspace
title: Konfigurieren eines Kohortenanalyseberichts
feature: Visualizations
exl-id: c3fd9fbf-b2c8-4703-92de-e6fdc141ebc6
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 89%

---

# Konfigurieren eines [!UICONTROL Kohortenanalyseberichts]

Erstellen Sie in Analysis Workspace eine Kohorte und führen Sie einen [!UICONTROL Kohortenanalysebericht] aus.

1. Klicken Sie in Analysis Workspace in der linken Leiste auf das Symbol **[!UICONTROL Visualisierungen]** und ziehen Sie eine **[!UICONTROL Kohortentabelle]** auf die Arbeitsfläche.

   ![Eine Beispielkohortentabelle mit den Aufnahmekriterien und den Rückkehrkriterien.](assets/cohort-table.png)

1. Bestimmen Sie die **[!UICONTROL Aufnahmekriterien]**, die **[!UICONTROL Rückkehrkriterien]**, den **[!UICONTROL Kohortentyp]** und die **[!UICONTROL Einstellungen]** wie in der Tabelle unten definiert.

   | Element | Beschreibung |
   |--- |--- |
   | **[!UICONTROL Aufnahmekriterien]** | Sie können bis zu 10 Einschlussfilter und bis zu 3 Einschlussmetriken anwenden. Die Kennzahl bestimmt, durch welche Kennzahl ein Benutzer in einer Kohorte platziert wird. Wenn die Aufnahmekennzahl z. B. die Bestellungen sind, werden nur Benutzer, die innerhalb des Zeitraums der Kohortenanalyse bestellt haben, in den anfänglichen Kohorten platziert.<br>Der Standardoperator zwischen den Kennzahlen ist AND, kann aber in OR geändert werden. Außerdem können Sie diesen Metriken numerische Filter hinzufügen. Beispielsweise: „Besuche >= 1“.</br> |
   | **[!UICONTROL Rückkehrkriterien]** | Sie können bis zu 10 Rückgabefilter und bis zu 3 Rückgabemetriken anwenden. Die Kennzahl gibt an, ob ein Benutzer gewonnen wurde (Bindung) oder nicht (Abwanderung). Wenn die Rückkehrmetrik z. B. die Videoansichten sind, werden nur Benutzer, die in nachfolgenden Zeiträumen (nach dem Zeitraum, in dem sie zu einer Kohorte hinzugefügt wurden) Videos angesehen haben, als zurückgekehrt dargestellt. Eine weitere Metrik, die die Treue quantifiziert, sind die Besuche. |
   | **[!UICONTROL Granularität]** | Die Zeitgranularität: Tag, Woche, Monat, Quartal oder Jahr. |
   | **[!UICONTROL Typ]** | **[!UICONTROL Bindung]** (Standard): Durch die Bindungskohorte wird gemessen, wie die persönliche Kohorte im Laufe der Zeit zu Ihnen zurückkehrt. Dabei handelt es sich um die Standardkohorte, die schon immer vorhanden war. Sie zeigt die Rückkehr und wiederkehrendes Benutzerverhalten an. In der Tabelle wird die [!UICONTROL Bindungskohorte] grün angezeigt.<br>**[!UICONTROL Abwanderung ]**: Bei einer Abwanderungskohorte (auch &quot;Abbruch&quot;oder &quot;Fallout&quot;) wird gemessen, wie Ihre Personenkohorte im Laufe der Zeit aus Ihrem Besitz herausfällt. Abwanderung = 1 - Bindung. Die [!UICONTROL Abwanderung] ist ein guter Messwert für die Treue und Chancen, da Ihnen gezeigt wird, wie häufig Kunden nicht zurückkehren. Sie können die Abwanderung nutzen, um Fokusbereiche zu analysieren und zu identifizieren, um herauszufinden, welche Kohortenfilter etwas Aufmerksamkeit erfordern könnten. Die [!UICONTROL Abwanderungskohorte] wird in der Tabelle durch die Farbe Rot angezeigt (ähnlich wie Fallout in unserer **[!UICONTROL  Flussvisualisierung ]**).</br> |
   | **[!UICONTROL Einstellungen]** | **[!UICONTROL Rollierende Berechnung]**: Ermöglicht es Ihnen, die Bindung oder die Abwanderung auf Grundlage der vorherigen Spalte und nicht der Aufnahmespalte zu berechnen (Standard). Durch [!UICONTROL Rollierende Berechnung] wird die Berechnungsmethode für Ihre „Rückkehr“-Zeiten verändert. Die Normalberechnung findet eigenständig Benutzer, die die „Rückkehr“-Kriterien erfüllen und Teil des Aufnahmezeitraums waren, unabhängig davon, ob sie in der Kohorte des vorherigen Zeitraums waren oder nicht. Im Gegensatz dazu findet [!UICONTROL Rollierende Berechnung] Benutzer, die die „Rückkehr“-Kriterien erfüllen und Teil des vorherigen Zeitraums waren. Daher filtert [!UICONTROL Rollierende Berechnung] Benutzer, die die „Rückkehr“-Kriterien kontinuierlich in jedem Zeitraum erfüllen, und trichtert sie. [!UICONTROL Rückkehrkriterien] werden auf jeden Zeitraum bis zum ausgewählten Zeitraum angewendet. </br><br>**[!UICONTROL Latenztabelle ]**: Eine [!UICONTROL Latenztabelle] misst die Zeit, die vor und nach dem Aufnahmeereignis verstrichen ist. Die [!UICONTROL Latenz] eignet sich ideal vor/nach der Analyse. Wenn beispielsweise ein Produkt- oder Kampagnen-Lauch bevorsteht und Sie das Verhalten vorher verfolgen und sehen möchten, wie es danach ist, zeigt die [!UICONTROL Latenztabelle] das Verhalten vorher und danach nebeneinander an, um die direkten Auswirkungen darzustellen. Die Zellen in der [!UICONTROL Latenztabelle] vor der Aufnahme werden von Benutzern berechnet, die die [!UICONTROL Aufnahmekriterien] für den Aufnahmezeitraum und anschließend die [!UICONTROL Rückkehrkriterien] in den Zeiträumen vor dem Aufnahmezeitraum erfüllen. [!UICONTROL Latenztabellen] und die Kohorte [!UICONTROL Benutzerspezifische Dimension] können nicht zusammen verwendet werden.</br><br>**[!UICONTROL Angepasste Dimensionskohorte]**: Erstellen Sie Kohorten auf Grundlage der ausgewählten Dimension und nicht auf Grundlage zeitbasierter Kohorten (Standard). Viele Kunden möchten ihre Kohorten nach etwas anderem als der Zeit analysieren, und die neue Funktion für benutzerdefinierte Dimensionskohorten bietet Ihnen genau diese Flexibilität, Kohorten basierend auf Dimensionen ihrer Wahl zu erstellen. Verwenden Sie Dimensionen wie Marketing-Kanal, Kampagne, Produkt, Seite, Region oder jede andere Dimension in Customer Journey Analytics, um anzuzeigen, wie die Bindung sich basierend auf verschiedenen Werten dieser Dimensionen verändert. Die Definition eines Kohortenfilters mit [!UICONTROL benutzerspezifischer Dimension] wendet das Dimensionselement nur als Teil des Einschlusszeitraums an, nicht als Teil der Rückgabedefinition.</br><br>Nach Auswahl der Option [!UICONTROL Angepasste Dimensionskohorte] können Sie jede beliebige Dimension in die Dropzone ziehen. Auf diese Weise können Sie ähnliche Dimensionselemente über den gleichen Zeitraum hinweg miteinander vergleichen. Sie können beispielsweise die Leistung von Städten, Produkten, Kampagnen usw. nebeneinander vergleichen. Dabei werden Ihre 14 wichtigsten Dimensionselemente ausgegeben. Sie können jedoch einen Filter verwenden (auf den Sie zugreifen können, indem Sie mit der Maus über den Bereich rechts von der gezogenen Dimension fahren), um nur die gewünschten Dimensionselemente anzuzeigen. Eine Kohorte [!UICONTROL Benutzerspezifische Dimension] kann nicht mit der Funktion [!UICONTROL Latenztabelle] verwendet werden.</br> |

1. Passen Sie die **[!UICONTROL Kohortentabelleneinstellungen]** an, indem Sie auf das Zahnradsymbol klicken.

   | Einstellung | Beschreibung |
| Nur Prozentwert anzeigen | Entfernt den Zahlenwert und zeigt nur den Prozentsatz an. |
| Prozentwert auf nächste Ganzzahl runden | Rundet den Prozentwert auf den nächsten ganzzahligen Wert, anstatt den Dezimalwert anzuzeigen. |
| Zeile mit durchschnittlichem Porzentwert anzeigen | Fügt oben in der Tabelle eine neue Zeile ein und fügt dann den Durchschnitt der Werte in jeder Spalte hinzu. |

## Erstellen des Berichts [!UICONTROL Kohortenanalyse]

1. Klicken Sie auf **[!UICONTROL Erstellen]**.

   ![Kohortentabellenansicht mit ausgewählten Aufnahmekriterien und Rückkehrkriterien. Klicken Sie auf Erstellen.](assets/cohort-report.png)

   Der Bericht zeigt Personen an, die eine Bestellung aufgegeben haben ( Spalte *`Included`* ) und die bei nachfolgenden Besuchen zu Ihrer Site zurückkehrten. Über den Rückgang der Besuche im Laufe der Zeit können Sie Probleme erkennen und Maßnahmen ergreifen.
1. (Optional) Erstellen Sie einen Filter aus einer Auswahl.

   Wählen Sie Zellen aus (fortlaufende oder nicht fortlaufende) und klicken Sie mit der rechten Maustaste auf **[!UICONTROL Filter aus Auswahl erstellen]**.

1. Bearbeiten Sie den Filter im [Filter-Builder](/help/components/filters/filter-builder.md) weiter und klicken Sie dann auf **[!UICONTROL Speichern]**.

   Der gespeicherte Filter ist im Bedienfeld [!UICONTROL Filter] in [!UICONTROL Analysis Workspace] für die Verwendung verfügbar.
1. Geben Sie Ihrem Kohortenprojekt einen Namen und speichern Sie es.
1. (Optional) [Kuratieren Sie die Projektkomponenten und geben Sie sie frei](/help/analysis-workspace/curate-share/curate.md).

   >[!NOTE]
   >
   >Sie müssen Ihr Projekt speichern, damit das Kuratieren verfügbar wird.

## Kohortenvisualisierung herunterladen

Wie andere Visualisierungen in Analysis Workspace können Sie eine Kohortenvisualisierung als CSV- oder PDF-Datei herunterladen. Weitere Informationen finden Sie unter [Projektdaten herunterladen](/help/analysis-workspace/export/download-send.md).