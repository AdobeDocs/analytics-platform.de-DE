---
title: Content Analytics-Reporting
description: Berichte zur Inhaltsanalyse erstellen
solution: Customer Journey Analytics
feature: Content Analytics
role: User
hide: true
hidefromtoc: true
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: dbbdfac312b1b7cbb6d8b6ce38a63f6d2bc18420
workflow-type: tm+mt
source-wordcount: '1263'
ht-degree: 0%

---

# Übersicht über das Reporting in Content Analytics

{{draft-aca}}

{{release-limited-testing}}

Sie erstellen Berichte, führen Analysen durch und erhalten Einblicke in Content Analytics innerhalb von [Analysis Workspace](/help/analysis-workspace/home.md). Eine bestimmte Workspace [Vorlage](#template) ist verfügbar, sodass Sie sofort auf ein vorausgefülltes Workspace-Projekt mit relevanten Inhalten zugreifen können.

So starten Sie das Reporting zu Inhaltsanalysen von Grund auf neu:

1. [Erstellen eines neuen](/help/analysis-workspace/build-workspace-project/create-projects.md) oder [Öffnen eines vorhandenen](/help/analysis-workspace/build-workspace-project/open-projects.md) Projekts in Workspace.
1. Stellen Sie sicher[ dass Sie für die Berichterstellung in Content Analytics ](/help/analysis-workspace/c-panels/panels.md#data-view) Datenansicht auswählen. Content Analytics Content Analytics-Berichte sind nur für Datenansichten verfügbar, die für [ konfiguriert ](/help/content-analytics/config/configuration.md).
1. Ziehen Sie ![ Visualisierung ](/help/assets/icons/Table.svg)Tabelle[/Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) auf die Arbeitsfläche.
1. Verwenden Sie [spezifischen Inhaltsanalysekomponenten](components.md) und andere generische [Komponenten](/help/components/overview.md) (wie Filter, Datumsbereiche, Anmerkungen), um Ihre Inhaltsanalyseeinblicke zu erstellen.

## Miniaturen

Basierend auf den Inhaltsanalysedimensionen, die Sie in Ihrem Projekt verwenden, werden Miniaturansichten für Assets und Dimensionen angezeigt.

![Content Analytics-Miniaturansichten](../assets/aca-thumbnails.png)

Standardmäßig werden Miniaturansichten für die entsprechenden Content Analytics-Dimensionen angezeigt. So konfigurieren Sie die Anzeige von Miniaturansichten für eine Content Analytics-Dimension:

* Bewegen Sie den Mauszeiger über eine Kopfzeile für eine Content Analytics-Dimension. Zum Beispiel **[!UICONTROL Asset-Name]** oder **[!UICONTROL Erlebnis-IDs]**.
* Wählen Sie ![Einstellung](/help/assets/icons/Setting.svg) aus.
* Aktivieren oder deaktivieren Sie im **[!UICONTROL Zeileneinstellung]**-Popup unter **[!UICONTROL Einstellungen]** die Option **[!UICONTROL Miniaturansichten anzeigen]**.


## Vorschau

Für Zeilen mit einer Content Analytics-Dimension, die Miniaturansichten anzeigen, können Sie ein Vorschau-Popup-Fenster öffnen.

So öffnen Sie die Vorschau mit den folgenden Details:

* Wählen Sie ![InfoOutline](/help/assets/icons/InfoOutline.svg) aus. Es werden die folgenden Details angezeigt.

  | Erlebnisvorschau | Asset-Vorschau |
  |---|---|
  | ![Content Analytics Experience Preview](../assets/aca-experience-preview.png) | ![Vorschau von Content Analytics-Assets](../assets/aca-asset-preview.png) |
  | **[!UICONTROL Name des Erlebnisses]** | **[!UICONTROL Name des Assets]** |
  | **[!UICONTROL Impressions (alle Zeiten)]**: Anzahl der Impressionen für das Erlebnis. | **[!UICONTROL Impressions (alle Zeiten)]**: Anzahl der Impressionen für das Asset. |
  | **[!UICONTROL Assets]**: Anzahl der Assets, die dieses Erlebnis enthält. <br/>Wählen Sie ![Aufschlüsselung](/help/assets/icons/Breakdown.svg) **[!UICONTROL Aufschlüsselung]** aus, um die Assets zu überprüfen. | **[!UICONTROL Erlebnisse]**: Anzahl der Erlebnisse, in denen dieses Asset angezeigt wird. <br/>Wählen Sie ![Aufschlüsselung](/help/assets/icons/Breakdown.svg) **[!UICONTROL Aufschlüsselung]** aus, um die Assets zu überprüfen. |
  | **[!UICONTROL Erster Impression]**: Datum des ersten Impressions des Erlebnisses. | **[!UICONTROL Erste Impression]**: Datum der ersten Impression des Assets. |
  | **[!UICONTROL Letzte Impression]**: Datum der letzten Impression des Erlebnisses. | **[!UICONTROL Letzte Impression]**: Datum der letzten Impression des Assets. |
  | **[!UICONTROL Erlebnisattribute]**: Die [Attribute](/help/content-analytics/report/components.md#experience-attributes) des Erlebnisses. | **[!UICONTROL Asset-]**: Die [Attribute](/help/content-analytics/report/components.md#asset-attributes) des Assets. |


## Vorlage

Eine Inhaltsanalysevorlage [Vorlage) ](/help/analysis-workspace/templates/use-templates.md) Ihnen dabei helfen, die beste Leistung von Inhalten und Inhaltsattributen zu ermitteln. Die Vorlage ist Teil des Anwendungsfalls [Web-Kanal und Interaktion](/help/analysis-workspace/templates/use-templates.md#web-engagement) und beschreibt, wie Ihre Inhalte auf einer granularen Ebene funktionieren. Sie können die Leistung einzelner Assets oder bestimmter Attribute überprüfen.

Je nachdem, was man lernt, kann man eine Reihe von Dingen tun. Personalisieren Sie Inhalte für bestimmte Segmente, um leistungsstarke Attribute einzuschließen, oder rotieren Sie Inhalte, die zu veralten begonnen haben, wie Assets mit hoher Leistung auf Ihrer Startseite, um Inhalte zu bewerben.

So verwenden Sie die Vorlage:

1. Wählen Sie **[!UICONTROL Workspace]** aus dem Hauptmenü aus.
1. Stellen Sie sicher, dass Sie eine Datenansicht ausgewählt haben, die für Content Analytics konfiguriert ist.
1. Suchen Sie nach oder verwenden Sie Filter (**[!UICONTROL Web]** für **[!UICONTROL Kanal]** und **[!UICONTROL Interaktion]** für **[!UICONTROL Anwendungsfall]**, um die Vorlage **[!UICONTROL Inhaltsanalytik]** zu finden und auszuwählen.
1. Wählen Sie **[!UICONTROL Vorlage verwenden]** aus.
1. Wählen **[!UICONTROL im Dialogfeld Vorlage einrichten]** eine Metrik aus dem Dialogfeld **[!UICONTROL Konversionsmetrik auswählen]**. Beispiel: **[!UICONTROL Asset-CTR]**.
1. Wählen Sie **[!UICONTROL Weiter]** aus.

Ein **[!UICONTROL Content Analytics-]**-Projekt wird in [Analysis Workspace](/help/analysis-workspace/home.md) geöffnet. Das Projekt besteht aus vier [Bedienfeldern](/help/analysis-workspace/c-panels/panels.md) in denen jedes Bedienfeld [Freiformtabellen](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) und [Visualisierungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) zur Beantwortung einer bestimmten Frage bereitstellt:

* **Welche Inhalte erzielen die besten Ergebnisse?**
In diesem Bedienfeld erfahren Sie, welche Erlebnisse und welche Assets in diesen Erlebnissen Interaktion und Konversion fördern. Erlebnisse sind eine vollständige Web-Seite, die zu einem bestimmten Zeitpunkt erfasst wird. Ein Erlebnis kann sowohl Text als auch mehrere einzelne Bild-Assets enthalten. Ein Asset ist ein einzelnes Bild.

  Das Bedienfeld besteht aus den folgenden Visualisierungen:

   * **Erlebnisse**

      * **Experience CTR**: eine Visualisierung [Zusammenfassungsänderung](/help/analysis-workspace/visualizations/summary-number-change.md) mit Experience CTR.
      * **Top-Konvertierungserlebnisse**: Eine [horizontale Balken](/help/analysis-workspace/visualizations/horizontal-bar.md) Visualisierung, die die besten Konvertierungserlebnisse basierend auf der ausgewählten Konversionsmetrik zeigt.
      * **Erlebnisse mit Top**: Eine [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)(einschließlich [Miniaturen](#thumbnails) und [Vorschauen](#previews)) für die Erlebnisse mit der besten Leistung.

   * **Assets**

      * **Asset-CTR**
Eine Visualisierung [Zusammenfassungsänderung](/help/analysis-workspace/visualizations/summary-number-change.md) die den Asset-CTR anzeigt.
      * **Top-Konvertierung von Assets**
Eine [Horizontalbalken](/help/analysis-workspace/visualizations/horizontal-bar.md) Visualisierung, die basierend auf der ausgewählten Konversionsmetrik die am häufigsten konvertierten Assets anzeigt.
      * **Assets mit der besten Leistung**
Eine [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (einschließlich [Miniaturen](#thumbnails) und [Vorschauen](#previews)) für die Assets mit der besten Performance.
      * **Assets - Ansichten vs. Konversion.**
Eine [Streudiagramm](/help/analysis-workspace/visualizations/scatterplot.md)-Visualisierung, die ein Streudiagramm der Asset-Ansichten im Vergleich zu den Asset-Konversionen zeigt.

* **Welche Asset-Attribute tragen zu Konversionen bei?**
Content Analytics verwendet KI und GenAI, um alle Asset-Metadaten automatisch zuzuweisen, z. B. Themen, Szenen, Vordergrundfarben usw. Ein Attribut ist ein von KI zugewiesenes Metadaten-Tag, das beschreibt, was sich in einem Asset oder Erlebnis befindet. Beispiel: <code>Vordergrundfarbe: rot</code> ist ein automatisch zugewiesenes Attribut. Anhand der Visualisierungen können Sie erkennen, welche Attribute Ihrer Assets am meisten zur Konversion beitragen.

  Das Bedienfeld besteht aus den folgenden Visualisierungen:

   * **Top-Konvertierung von Asset-Attributen**
Ein [horizontaler Balken](/help/analysis-workspace/visualizations/horizontal-bar.md) der die wichtigsten konvertierenden Asset-Attribute basierend auf der ausgewählten Konversionsmetrik anzeigt.
   * **Konvertieren der Asset-Attribute nach oben im Vergleich zu vorherigen 30 Tagen**
Eine [horizontale Balken](/help/analysis-workspace/visualizations/horizontal-bar.md) Visualisierung, die die wichtigsten konvertierenden Asset-Attribute basierend auf der ausgewählten Konversionsmetrik im Vergleich zu den vorherigen 30 Tagen anzeigt.
   * **Top-Konvertierung von Asset-Attributdaten**
Eine [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) die die wichtigsten konvertierenden Attribute basierend auf der ausgewählten Konversionsmetrik anzeigt. Wählen Sie eine Zeile in der Tabelle aus, um die Trendvisualisierung für Attribute zu aktualisieren.
   * **Attributtrend**
Eine [-](/help/analysis-workspace/visualizations/line.md)-Visualisierung, die den Attributtrend für das ausgewählte am häufigsten konvertierende Asset-Attribut anzeigt.
   * **Asset-Vordergrundfarbe**
Ein Beispiel [Freiformtabelle), ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) die Leistung von Elementen aus einer einzelnen Asset-Attributkategorie vergleicht: Vordergrundfarben. Sie können dieses Asset-Attribut durch andere Dimensionen der Asset-Attributkategorie ersetzen.

* **Welche Erlebnisattribute tragen zu Konversionen bei?**
Während sich Asset-Attribute auf die visuellen Qualitäten von Bildern konzentrieren, konzentrieren sich Erlebnisattribute auf den Text Ihrer Seite. Mit den folgenden Visualisierungen können Sie untersuchen, welche Erlebnisattribute zur Konversion beitragen. Diese Attribute werden auch automatisch mithilfe von KI- und GenAI-Modellen zugewiesen.

  Das Bedienfeld besteht aus den folgenden Visualisierungen:

   * **Die besten Erlebnisattribute konvertieren**
Eine [Horizontalbalken](/help/analysis-workspace/visualizations/horizontal-bar.md) Visualisierung, die die wichtigsten konvertierenden Erlebnisattribute basierend auf der ausgewählten Konversionsmetrik anzeigt.
   * **Die besten Erlebnisattribute konvertieren im Vergleich zu vorherigen 30 Tagen**
Eine [horizontale Balken](/help/analysis-workspace/visualizations/horizontal-bar.md) Visualisierung, die die wichtigsten Konvertierungserlebnisattribute im Vergleich zu den letzten 30 Tagen zeigt, basierend auf der ausgewählten Konversionsmetrik.
   * **Top-Konvertierung von Erlebnisattributdaten**
Eine [Freiformtabelle), ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) die wichtigsten Konvertierungserlebnisse basierend auf der ausgewählten Konversionsmetrik anzeigt. Wählen Sie eine Zeile in der Tabelle aus, um die Linienvisualisierung zu aktualisieren.
   * **line**
Eine [-](/help/analysis-workspace/visualizations/line.md)-Visualisierung, die den Trend für das ausgewählte am häufigsten konvertierte Erlebnisattribut anzeigt.
   * **Erlebnis-Keywords**
Eine [Freiformtabelle“, ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) die wichtigsten Erlebnisschlüsselwörter basierend auf der ausgewählten Konversionsmetrik anzeigt.

* **Wo werden Assets auf meiner Site angezeigt?**
Ein Bedienfeld, das aus einer Freiformtabelle besteht, in der angegeben ist, wo die am häufigsten angezeigten Assets auf Ihrer Site erscheinen.

  Das Bedienfeld besteht aus einer Visualisierung:

   * **Wo werden die am häufigsten angezeigten Assets angezeigt?**
Sie können jedes Asset nach Dimensionen aufschlüsseln, damit Sie besser verstehen können, wo dieses Bild angezeigt wird.

     Im Beispiel [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (einschließlich [Miniaturen](#thumbnails) und [Vorschauen](#previews)) wird **[!UICONTROL Asset Perception ID]** anstelle von [!UICONTROL Asset ID] verwendet. Manchmal kann dasselbe Bild mit einer anderen Bild-URL auf Ihrer Site dupliziert werden. Mit [!UICONTROL  Attribut „Asset Perception ID] können diese Duplikate unter einer einzigen ID gruppiert werden.

     Da sich Assets auf einer Seite ändern können, werden die einzelnen Assets nach **[!UICONTROL Erlebnis-ID]** aufgeschlüsselt, um zu ermitteln, auf welcher Version der Seite das Asset angezeigt wurde. Sie können [!UICONTROL Erlebnis-ID] durch andere Dimensionen ersetzen, die Ihnen dabei helfen, den Speicherort eines Assets auf Ihrer Site zu verstehen. Beispiel: [!UICONTROL Seitenname], [!UICONTROL Seiten-URL] oder [!UICONTROL Site-Bereich].

     Sie können [!UICONTROL Asset Perception ID] auch durch [!UICONTROL Asset ID] ersetzen, um aufzuzeichnen, wo bestimmte Bild-URLs referenziert werden.


>[!MORELIKETHIS]
>
>[Inhaltsanalysekomponenten](components.md)
>[Verwenden Sie Vorlagen](/help/analysis-workspace/templates/use-templates.md#web-engagement)
>
