---
description: Erfahren Sie, wie Sie mit dem Bedienfeld „Quick Insights“ Freiformtabellen und Visualisierungen in Analysis Workspace erstellen können.
title: Bedienfeld Quick Insights
feature: Panels
exl-id: 09ebc3af-34ac-4f1f-8a5d-90da008f8697
role: User
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 86%

---

# Bedienfeld „Quick Insights“ {#quick-insights-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_quickinsights_button"
>title="Quick Insights"
>abstract="Erstellen Sie ein Bedienfeld, um im Handumdrehen eine Freiformtabelle und eine entsprechende Visualisierung zu erstellen, um Erkenntnisse schneller zu analysieren und bereitzustellen."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_In diesem Artikel wird das Bedienfeld „Quick Insights“ in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;_ beschrieben.<br/>_Unter [Bedienfeld „Quick Insights“](https://experienceleague.adobe.com/de/docs/analytics/analyze/analysis-workspace/panels/quickinsight) finden Sie die_![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**-Version dieses Artikels._

>[!ENDSHADEBOX]


[!UICONTROL Quick Insights] bietet Nicht-Analytikern und neuen Benutzern von [!UICONTROL Analysis Workspace] die Möglichkeit, betriebliche Fragen schnell und einfach zu beantworten. Es ist auch ein großartiges Tool für fortgeschrittene Benutzer, die eine einfache Frage schnell beantworten möchten, ohne selbst eine Tabelle erstellen zu müssen.

Wenn Sie [!UICONTROL Analysis Workspace] zum ersten Mal verwenden, stellen Sie sich vielleicht folgende Fragen:

* Welche Visualisierungen sind am nützlichsten?
* Welche Dimensionen und Metriken können Erkenntnisse erleichtern?
* Wo werden Elemente per Drag-and-Drop eingefügt?
* wo ein Segment erstellt werden soll,
* und vieles mehr.

Um Ihnen bei diesen Fragen zu helfen[!UICONTROL &#x200B; nutzt „Quick Insights] einen Algorithmus, der Ihnen die beliebtesten Dimensionen, Metriken, Segmente und Datumsbereiche präsentiert, die Ihr Unternehmen verwendet. Dieser Algorithmus basiert auf der Verwendung von Datenkomponenten durch Ihr eigenes Unternehmen in [!UICONTROL Analysis Workspace]. Tatsächlich werden Dimensionen, Metriken und Segmente mit dem Tag [!UICONTROL POPULAR] im Dropdown-Menü angezeigt, wie hier gezeigt:

![Das Bedienfeld „Quick Insights“.](assets/popular-tag.png)

[!UICONTROL Quick Insights] hilft Ihnen bei Folgendem:

* Ordnungsgemäßes Erstellen einer Datentabelle und einer zugehörigen Visualisierung in [!UICONTROL Analysis Workspace].
* Vertrautmachen mit der Terminologie und dem Vokabular für grundlegende Komponenten und Bestandteile von [!UICONTROL Analysis Workspace].
* Ausführen einfacher Aufschlüsselungen von Dimensionen, Hinzufügen mehrerer Metriken oder Vergleichen von Segmenten in einer [!UICONTROL Freiformtabelle].
* Ändern oder Ausprobieren verschiedener Visualisierungstypen, um das Suchwerkzeug für Ihre Analyse schnell und intuitiv zu finden.

## Grundlegende Terminologie

Im Folgenden finden Sie einige grundlegende Begriffe, mit denen Sie vertraut sein müssen. Jede Datentabelle besteht aus zwei oder mehr Bausteinen (Komponenten), die Sie für Ihre Daten verwenden.

| Baustein (Komponente) | Definition |
|---|---|
| **[!UICONTROL Dimension]** | Dimensionen sind Beschreibungen oder Eigenschaften metrischer Daten, die in einem Projekt angezeigt, aufgeschlüsselt und verglichen werden können. Es handelt sich um nicht-numerische Werte und Daten, die in Dimensionselemente aufgeschlüsselt werden. Zum Beispiel ist *Browser* oder *Seite* eine Dimension. |
| **[!UICONTROL Dimensionselement]** | Dimensionselemente sind individuelle Werte für eine Dimension. Dimensionselemente für die Dimension „Browser“ wären zum Beispiel *Chrome*, *Firefox*, *Edge* oder andere. |
| [!UICONTROL Metrik] | Metriken sind quantitative Informationen über Aktivitäten von Personen wie Ansichten, Clickthroughs, Neuladungen, durchschnittliche Besuchszeit, Einheiten, Bestellungen, Umsatz usw. |
| **[!UICONTROL Visualisierung]** | Workspace bietet [eine Reihe von Visualisierungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md), um visuelle Darstellungen Ihrer Daten zu erstellen. Zum Beispiel Balkendiagramme, Ringdiagramme, Histogramme, Liniendiagramme, Karten, Streudiagramme und andere. |
| **[!UICONTROL Dimensionsaufschlüsselung]** | Mit einer Dimensionsaufschlüsselung können Sie eine Dimension nach anderen Dimensionen aufschlüsseln. Sie können beispielsweise die US-Bundesstaaten nach Mobilgeräten aufschlüsseln, um die Besuche durch Mobilgeräte pro Bundesstaat zu erhalten. Oder Sie können Mobilgeräte nach Mobilgerätetypen, Regionen, internen Kampagnen und mehr aufschlüsseln. |
| **[!UICONTROL Segment]** | Mit Segmenten können Personenuntergruppen anhand von Merkmalen oder Website-Interaktionen identifiziert werden. Sie können beispielsweise Segmente [!UICONTROL Personen] basierend auf erstellen. <li>Attribute: Browser-Typ, Gerät, Anzahl der Besuche, Land, Geschlecht; oder</li><li>Interaktionen: Kampagnen, Keyword-Suche, Suchmaschine; oder</li><li>Ausstiege und Eintritte: Personen aus Facebook, einer definierten Landingpage, einer Referrer Domain; oder</li><li> Benutzerdefinierte Variablen: Formularfeld, definierte Kategorien, Kunden-ID. |

## Verwenden

So verwenden Sie ein Bedienfeld **[!UICONTROL Quick Insights]**:

1. Erstellen Sie ein Bedienfeld **[!UICONTROL Quick Insights]**. Informationen zum Erstellen eines Bedienfelds finden Sie unter [Erstellen eines Bedienfelds](panels.md#create-a-panel).

1. Wenn Sie zum ersten Mal ein Bedienfeld **[!UICONTROL Quick Insights]** verwenden, sollten Sie sich das kurze [!UICONTROL Einführungs-Tutorial] ansehen, das Ihnen einige Grundlagen vermittelt. Wählen Sie ![Hilfesymbol](/help/assets/icons/HelpOutline.svg) neben dem Titel des Bedienfelds „Quick Insights“ und dann im Popup-Fenster die Option **[!UICONTROL Einführungs-Tutorial]** aus.

1. Legen Sie die [Eingabe](#panel-input) für das Bedienfeld fest.

1. Sehen Sie sich die [Ausgabe](#panel-output) für das Bedienfeld an.


### Bedienfeldeingabe

Wählen Sie die gewünschten Bausteine aus:

* **[!UICONTROL Analysieren]**: Zum Festlegen einer Dimension (orange)
* **[!UICONTROL Nach]**: Zum Festlegen einer Metrik (grün)
* **[!UICONTROL Segment nach]** - Segment angeben (blau)
* **[!UICONTROL Am]**: Zum Festlegen eines Datumsbereichs (violett).

Sie müssen mindestens eine Dimension und eine Metrik auswählen, damit die Visualisierung ordnungsgemäß funktioniert.



Sie haben drei Möglichkeiten, um die Bausteine festzulegen:

* Ziehen Sie Komponenten aus dem linken Bedienfeld und legen Sie sie ab.
* Beginnen Sie mit der Eingabe in eines der Bausteinfelder. Wenn eine Eingabe gefunden wird, wird das Bausteinfeld automatisch mit möglichen Werten aufgefüllt.
* Geben Sie ein Dropdown-Menü für Bausteine an (z. B. Land in **[!UICONTROL Analysieren]**) und **[!UICONTROL Suchen]** die Liste möglicher Werte (mit ![ChevronRight](/help/assets/icons/ChevronRight.svg)) für den gewünschten Wert (z. B. **[!UICONTROL Länder-Code]**).

Wählen Sie **[!UICONTROL Löschen]** aus, um alle Eingabefelder zu löschen.


### Bedienfeldausgabe

1. Wenn Sie mindestens eine Dimension und eine Metrik hinzugefügt haben, können Sie die Ergebnisse sehen.

   ![Die Freiformtabelle, die die Dimension vertikal und die Metrik horizontal anzeigt.](assets/quick-insights-output.png)

   * Eine Freiformtabelle mit der Dimension (Länder-Code) und Metrik (Sitzungen), segmentiert nach Web-Sitzungen für die letzten 12 Monate.

   * Eine begleitende Visualisierung, in diesem Fall ein [Balkendiagramm](/help/analysis-workspace/visualizations/bar.md). Die erstellte Visualisierung basiert auf dem Datentyp, den Sie der Tabelle hinzugefügt haben. Für zeitbasierte Daten (z. B. [!UICONTROL Sitzungen] pro Tag/Monat) wird standardmäßig ein [!UICONTROL Liniendiagramm] verwendet. Für alle nicht zeitbasierten Daten (z. B. [!UICONTROL Sitzungen] pro [!UICONTROL Gerät]) wird standardmäßig ein [!UICONTROL Balkendiagramm] verwendet. Sie können den Visualisierungstyp ändern, indem Sie auf den Dropdown-Pfeil neben dem Visualisierungstyp klicken.

1. Versuchen Sie, weitere Verfeinerungen hinzuzufügen, wie nachfolgend unter [Weitere Tipps](#more-tips) beschrieben.

1. Speichern Sie Ihr Projekt, indem Sie **[!UICONTROL Projekt > Speichern]** auswählen.

## Weitere Tipps

Weitere nützliche Hinweise werden im [!UICONTROL Quick Insights Builder] angezeigt. Einige davon hängen von Ihrer letzten Aktion ab.

* Zunächst sollten Sie das Tutorial **[!UICONTROL Mehr Tipps]** abschließen. Dieses Tutorial wird 24 Stunden nach dem Erstellen eines Projekts mit mindestens einer Dimension und einer Metrik angezeigt. Wählen Sie ![Hilfesymbol](/help/assets/icons/HelpOutline.svg) neben dem Titel des Bedienfelds „Quick Insights“ und dann im Popup-Fenster die Option **[!UICONTROL Mehr Tipps]** aus.

  ![Die Benachrichtigung zum Bedienfeld „Quick Insights“ wird angezeigt, nachdem Sie auf das Hilfesymbol geklickt haben.](assets/qibuilder4.png)

* Sie können mehrere Dimensionen und Metriken analysieren, Segmente kombinieren oder vergleichen und einen Datumsbereich angeben:

  ![Quick Insights Builder-Ergebnis](assets/qibuilder-result.png)

   * Unter **[!UICONTROL Analysieren]** > **[!UICONTROL Aufschlüsselung nach]**: Sie können bis zu drei Aufschlüsselungsebenen für Dimensionen verwenden, um einen Drilldown zu den Daten durchzuführen, die Sie benötigen. Siehe ➊, ➋ und ➌.

   * Weitere Metriken **[!UICONTROL nach]** hinzufügen: Sie können bis zu zwei weitere Metriken hinzufügen. Siehe ➍ und ➎.

   * **[!UICONTROL Segment nach]**: Sie können bis zu 2 weitere Segmente hinzufügen. Sie können beispielsweise „Buchungen“ als Segment hinzufügen und dieses Segment mit den von Ihnen verglichenen Segmenten für Personen, die häufig fliegen, und Personen, die zum ersten Mal fliegen, kombinieren. Siehe ➏, ➐ und ➑.

   * Am: Sie können den Datumsbereich festlegen. Siehe ➒.

## Bekannte Einschränkungen

Wenn Sie versuchen, die Datei direkt in der Tabelle zu bearbeiten, wird das Bedienfeld [!UICONTROL Quick Insights] möglicherweise nicht mehr synchronisiert. Wählen Sie oben rechts im Bedienfeld die Option **[!UICONTROL Builder neu synchronisieren]** aus, um die vorherigen Einstellungen für [!UICONTROL Quick Insights] wiederherzustellen.

Sie erhalten eine Warnung, bevor Sie etwas direkt zur Tabelle hinzufügen:

![Die Warnung der Option zum Neusynchronisieren des Builders.](assets/qibuilder-outofsync.png)

Andernfalls verhält sich die Tabelle beim direkten Erstellen wie eine herkömmliche Freiformtabelle, ohne die hilfreichen Funktionen für neue Benutzende.


>[!MORELIKETHIS]
>
>[Erstellen eines Bedienfelds](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>