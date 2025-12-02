---
title: Content Analytics-Reporting
description: Erstellen von Content Analytics-Berichten
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 100%

---

# Überblick über das Content Analytics-Reporting

Zu Content Analytics können Sie in [Analysis Workspace](/help/analysis-workspace/home.md) Berichte erstellen, Analysen durchführen und Erkenntnisse gewinnen. Eine bestimmte Workspace-[Vorlage](#template) ist verfügbar, sodass Sie sofort auf ein vorausgefülltes Workspace-Projekt mit relevanten Inhalten zugreifen können.

So starten Sie das Content Analytics-Reporting erstmalig:

1. [Erstellen Sie ein neues](/help/analysis-workspace/build-workspace-project/create-projects.md) oder [öffnen Sie ein vorhandenes](/help/analysis-workspace/build-workspace-project/open-projects.md) Projekt in Workspace.
1. Stellen Sie sicher, dass Sie für das Content Analytics-Reporting eine [Datenansicht auswählen](/help/analysis-workspace/c-panels/panels.md#data-view). Das Content Analytics-Reporting ist nur für Datenansichten verfügbar, die für Content Analytics [konfiguriert](/help/content-analytics/config/configuration.md) sind.
1. Ziehen Sie die Visualisierung ![Tabelle](/help/assets/icons/Table.svg) [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) auf die Arbeitsfläche.
1. Verwenden Sie [spezifische Content Analytics-Komponenten](components.md) und andere allgemeine [Komponenten](/help/components/overview.md) (wie Segmente, Datumsbereiche, Anmerkungen), um Erkenntnisse zu Content Analytics zu erhalten.

## Miniaturen

Basierend auf den Content Analytics-spezifischen Dimensionen in Ihrem Projekt werden Miniaturen für Assets und Dimensionen angezeigt.

![Content Analytics-Miniaturen](../assets/aca-thumbnails.png)

Standardmäßig werden Miniaturen für die entsprechenden Content Analytics-Dimensionen angezeigt. So konfigurieren Sie die Anzeige von Miniaturen für eine Content Analytics-Dimension:

* Bewegen Sie den Mauszeiger über eine Kopfzeile für eine Content Analytics-Dimension, z. B. **[!UICONTROL Asset-IDs]** oder **[!UICONTROL Erlebnis-IDs]**.
* Wählen Sie ![Einstellung](/help/assets/icons/Setting.svg) aus.
* Aktivieren oder deaktivieren Sie im Popup **[!UICONTROL Zeileneinstellungen]** unter **[!UICONTROL Einstellungen]** die Option **[!UICONTROL Miniaturansichten anzeigen]**.


## Vorschau

Für Zeilen mit einer Content Analytics-Dimension, die Miniaturen anzeigen, können Sie ein Popup-Fenster „Vorschau“ öffnen.

So öffnen Sie eine Vorschau mit den folgenden Details:

* Wählen Sie ![Info-Gliederung](/help/assets/icons/InfoOutline.svg) aus. Es werden die folgenden Details angezeigt.

  | Erlebnisvorschau | Asset-Vorschau |
  |---|---|
  | ![Content Analytics-Erlebnisvorschau](../assets/aca-experience-preview.png) | ![Content Analytics-Asset-Vorschau](../assets/aca-asset-preview.png) |
  | Name der Dimension (z. B. **[!UICONTROL Erlebnis-ID])** | Name der Asset-Dimension (z. B. **[!UICONTROL Asset-ID])** |
  | **[!UICONTROL Impressions (gesamte Zeit)]**: Anzahl der Impressions für das Erlebnis. | **[!UICONTROL Impressions (gesamte Zeit)]**: Anzahl der Impressions für das Asset. |
  | **[!UICONTROL Assets]**: Anzahl der Assets, die dieses Erlebnis umfasst. <br/>Wählen Sie ![Aufschlüsselung](/help/assets/icons/Breakdown.svg) **[!UICONTROL Aufschlüsselung]** aus, um die Assets zu überprüfen. | **[!UICONTROL Erlebnisse]**: Anzahl der Erlebnisse, bei denen dieses Asset angezeigt wird. <br/>Wählen Sie ![Aufschlüsselung](/help/assets/icons/Breakdown.svg) **[!UICONTROL Aufschlüsselung]** aus, um die Assets zu überprüfen. |
  | **[!UICONTROL Erste Impression]**: Datum der ersten Impression des Erlebnisses. | **[!UICONTROL Erste Impression]**: Datum der ersten Impression des Assets. |
  | **[!UICONTROL Letzte Impression]**: Datum der letzten Impression des Erlebnisses. | **[!UICONTROL Letzte Impression]**: Datum der letzten Impression des Assets. |
  | **[!UICONTROL Erlebnisattribute]**: Die [Attribute](/help/content-analytics/report/components.md#experience-attributes) des Erlebnisses. | **[!UICONTROL Asset-Attribute]**: Die [Attribute](/help/content-analytics/report/components.md#asset-attributes) des Assets. |


## Vorlage

Es ist eine Content Analytics-[Vorlage](/help/analysis-workspace/templates/use-templates.md) verfügbar, mit der Sie ermitteln können, welche Inhalte und Inhaltsattribute am besten funktionieren. Die Vorlage ist Teil des Anwendungsfalls [Web-Kanal und Interaktion](/help/analysis-workspace/templates/use-templates.md#web-engagement) und beschreibt, wie Ihre Inhalte auf granularer Ebene abschneiden. Sie können die Leistung einzelner Assets oder bestimmter Attribute überprüfen. 

Basierend auf Ihren Erkenntnissen können Sie eine Reihe von Schritten ausführen, z. B. Assets mit hoher Leistung auf Ihrer Startseite fördern, Inhalte für bestimmte Segmente personalisieren, um Attribute mit hoher Leistung einzuschließen, oder Inhalte austauschen, die nicht mehr aktuell sind.

So verwenden Sie die Vorlage:

1. Wählen Sie im Hauptmenü die Option **[!UICONTROL Arbeitsbereich]** aus.
1. Stellen Sie sicher, dass Sie eine Datenansicht ausgewählt haben, die bereits für Content Analytics konfiguriert ist. 
1. Suchen Sie nach oder verwenden Sie Segmente (**[!UICONTROL Web]** für **[!UICONTROL Kanal]** und **[!UICONTROL Interaktion]** für **[!UICONTROL Anwendungsfall]**) und wählen Sie die Vorlage **[!UICONTROL Content Analytics]** aus.
1. Wählen Sie **[!UICONTROL Vorlage verwenden]** aus.
1. Wählen Sie im Dialogfeld **[!UICONTROL Vorlage einrichten]** eine Metrik aus dem Dialogfeld **[!UICONTROL Konversionsmetrik auswählen]** aus, z. B. **[!UICONTROL Asset – CTR]**.
1. Wählen Sie **[!UICONTROL Weiter]** aus.

Ein Projekt vom Typ **[!UICONTROL Übersicht über Content Analytics]** wird in [Analysis Workspace](/help/analysis-workspace/home.md) geöffnet. Das Projekt besteht aus vier [Panels](/help/analysis-workspace/c-panels/panels.md), jeweils mit [Freiformtabellen](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) und [Visualisierungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) zur Beantwortung einer bestimmten Frage:

* **Welche Inhalte schneiden am besten ab?**
Durch dieses Panel erfahren Sie, welche Erlebnisse und welche Assets in diesen Erlebnissen zu Interaktionen und Konversionen beitragen. Erlebnisse bedeuten hier eine vollständige Web-Seite, die zu einem bestimmten Zeitpunkt erfasst wird. Ein Erlebnis kann sowohl Text als auch mehrere einzelne Bild-Assets enthalten. Ein Asset ist ein einzelnes Bild.

  Das Panel besteht aus den folgenden Visualisierungen:

   * **Erlebnisse**

     >[!NOTE]
     >
     >Diese Visualisierungen werden nur angezeigt, wenn Sie in Ihre Content Analytics-Konfiguration [Erlebnisse eingeschlossen](/help/content-analytics/config/guided.md#experience-capture-and-definition) haben.
     > 

      * **Erlebnis – CTR**: Eine Visualisierung vom Typ [Zusammenfassungsänderung](/help/analysis-workspace/visualizations/summary-number-change.md), die die Erlebnis-CTR zeigt.
      * **Erlebnisse mit den meisten Konversionen**: Eine Visualisierung vom Typ [Horizontalbalken](/help/analysis-workspace/visualizations/horizontal-bar.md), die die besten Konversionserlebnisse basierend auf der ausgewählten Konversionsmetrik zeigt.
      * **Erlebnisse mit der besten Performance**: Eine [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (einschließlich [Miniaturen](#thumbnails) und [Vorschauen](#previews)) für die Erlebnisse mit der besten Leistung.

   * **Assets**

      * **Asset – CTR**
Eine Visualisierung vom Typ [Zusammenfassungsänderung](/help/analysis-workspace/visualizations/summary-number-change.md), die die Asset-CTR zeigt.
      * **Assets mit den meisten Konversionen**
Eine Visualisierung vom Typ [Horizontalbalken](/help/analysis-workspace/visualizations/horizontal-bar.md), die die Assets mit den meisten Konversionen basierend auf der ausgewählten Konversionsmetrik zeigt.
      * **Assets mit der besten Performance**
Eine [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (einschließlich [Miniaturen](#thumbnails) und [Vorschauen](#previews)) für die Assets mit der besten Leistung.
      * **Assets – Ansichten vs. Konversion**
Eine Visualisierung vom Typ [Streudiagramm](/help/analysis-workspace/visualizations/scatterplot.md), die ein Streudiagramm der Asset-Ansichten im Vergleich zu den Asset-Konversionen zeigt.

* **Welche Asset-Attribute tragen zu Konversionen bei?**
Content Analytics nutzt KI und generative KI, um alle Asset-Metadaten automatisch zuzuweisen, z. B. Themen, Szenen, Vordergrundfarben usw. Ein Attribut ist ein von KI zugewiesenes Metadaten-Tag, das beschreibt, was in einem Asset oder Erlebnis vorhanden ist. Beispielsweise ist <code>foreground color: red</code> ein automatisch zugewiesenes Attribut. Mithilfe von Visualisierungen können Sie erkennen, welche Attribute Ihrer Assets am meisten zur Konversion beitragen.

  Das Panel besteht aus den folgenden Visualisierungen:

   * **Asset-Attribute mit den meisten Konversionen**
Eine Visualisierung vom Typ [Horizontalbalken](/help/analysis-workspace/visualizations/horizontal-bar.md), die die Asset-Attribute mit den meisten Konversionen basierend auf der ausgewählten Konversionsmetrik zeigt.
   * **Asset-Attribute mit den meisten Konversionen vs. letzte 30 Tage**
Eine Visualisierung vom Typ [Horizontalbalken](/help/analysis-workspace/visualizations/horizontal-bar.md), die die Asset-Attribute mit den meisten Konversionen im Vergleich zu den letzten 30 Tagen basierend auf der ausgewählten Konversionsmetrik zeigt.
   * **Daten zu den Asset-Attributen mit den meisten Konversionen**
Eine [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), die die Attribute mit den meisten Konversionen basierend auf der ausgewählten Konversionsmetrik zeigt. Wählen Sie eine Zeile in der Tabelle aus, um die Visualisierung „Attribut-Trend“ zu aktualisieren.
   * **Attribut-Trend**
Eine Visualisierung vom Typ [Linie](/help/analysis-workspace/visualizations/line.md), die den Attribut-Trend für das ausgewählte Asset-Attribut mit den meisten Konversionen zeigt.
   * **Asset – Vordergrundfarben**
Eine beispielhafte [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), die die Leistung von Elementen aus einer einzelnen Asset-Attributkategorie vergleicht: Vordergrundfarben. Sie können dieses Asset-Attribut durch andere Dimensionen der Asset-Attributkategorie ersetzen.

* **Welche Erlebnisattribute tragen zu Konversionen bei?**

  >[!NOTE]
  >
  >Dieses Panel wird nur angezeigt, wenn Sie in Ihre Content Analytics-Konfiguration [Erlebnisse eingeschlossen](/help/content-analytics/config/guided.md#experience-capture-and-definition) haben.
  > 

  Während sich Asset-Attribute auf die visuellen Qualitäten von Bildern konzentrieren, liegt der Fokus bei Erlebnisattributen auf dem Seitentext. Mit den folgenden Visualisierungen können Sie untersuchen, welche Erlebnisattribute zur Konversion beitragen. Diese Attribute werden auch automatisch mithilfe von KI- und GenKI-Modellen zugewiesen.

  Das Panel besteht aus den folgenden Visualisierungen:

   * **Erlebnisattribute mit den meisten Konversionen**
Eine Visualisierung vom Typ [Horizontalbalken](/help/analysis-workspace/visualizations/horizontal-bar.md), die die Erlebnisattribute mit den meisten Konversionen basierend auf der ausgewählten Konversionsmetrik zeigt.
   * **Erlebnisattribute mit den meisten Konversionen vs. letzte 30 Tage**
Eine Visualisierung vom Typ [Horizontalbalken](/help/analysis-workspace/visualizations/horizontal-bar.md), die die Erlebnisattribute mit den meisten Konversionen im Vergleich zu den letzten 30 Tagen basierend auf der ausgewählten Konversionsmetrik zeigt.
   * **Daten zu den Erlebnisattributen mit den meisten Konversionen**
Eine [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), die die Erlebnisse mit den meisten Konversionen basierend auf der ausgewählten Konversionsmetrik zeigt. Wählen Sie eine Zeile in der Tabelle aus, um die Visualisierung „Linie“ zu aktualisieren.
   * **Linie**
Eine Visualisierung vom Typ [Linie](/help/analysis-workspace/visualizations/line.md), die den Trend für das ausgewählte am häufigsten konvertierte Erlebnisattribut anzeigt.
   * **Erlebnis – Keywords**
Eine [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) mit den wichtigsten Erlebnis-Keywords basierend auf der ausgewählten Konversionsmetrik.

* **Wo werden Assets auf meiner Site angezeigt?**
Ein Panel, das aus einer Freiformtabelle besteht, in der angegeben ist, wo die am häufigsten angesehenen Assets auf Ihrer Site erscheinen.

  Das Panel besteht aus einer Visualisierung:

   * **Wo werden die am häufigsten angesehenen Assets angezeigt?**
Sie können jedes Asset nach Dimensionen aufschlüsseln, um nachvollziehen zu können, wo dieses Bild angezeigt wird.

     Im Beispiel [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (einschließlich [Miniaturen](#thumbnails) und [Vorschauen](#previews)) wird **[!UICONTROL Asset-Wahrnehmungs-ID]** anstelle von [!UICONTROL Element-ID] verwendet. Manchmal kann exakt dasselbe Bild mit einer anderen Bild-URL auf Ihrer Site dupliziert werden. Mit dem Attribut [!UICONTROL Asset-Wahrnehmungs-ID] können diese Duplikate unter einer einzigen ID gruppiert werden.

     Da sich Assets auf einer Seite ändern können, werden die einzelnen Assets nach **[!UICONTROL Erlebnis-ID]** aufgeschlüsselt, um zu ermitteln, auf welcher Version dieser Seite das Asset angezeigt wurde. Sie können die [!UICONTROL Erlebnis-ID] durch andere Dimensionen ersetzen, anhand derer Sie die Position eines Assets auf Ihrer Site ermitteln können. Beispiel: [!UICONTROL Seitenname], [!UICONTROL Seiten-URL] oder [!UICONTROL Site-Bereich].

     Sie können [!UICONTROL Asset-Wahrnehmungs-ID] auch durch [!UICONTROL Element-ID] ersetzen, um einen Eintrag mit Informationen dazu zu erhalten, wo bestimmte Bild-URLs referenziert werden.


>[!MORELIKETHIS]
>
>[Content Analytics-Komponenten](components.md)
>[Verwenden von Vorlagen](/help/analysis-workspace/templates/use-templates.md#web-engagement)
>
