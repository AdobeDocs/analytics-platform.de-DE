---
description: Erstellen und Freigeben von Scorecards in Analytics-Dashboards
title: Erstellen und Freigeben von Scorecards
feature: Analytics Dashboards
role: User, Admin
exl-id: 12531600-7e88-4d56-a2a5-e5b346f91937
solution: Customer Journey Analytics
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '2698'
ht-degree: 98%

---

# Erstellen einer mobilen Scorecard {#create-a-mobile-scorecard}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="mobilescorecard_annotations"
>title="Anmerkungen"
>abstract="Anmerkungen können im Komponenten-Manager eines Arbeitsbereichsprojekts erstellt werden."

<!-- markdownlint-enable MD034 -->


Die folgenden Informationen liefern Kuratierenden von Customer Journey Analytics-Daten Beschreibungen dazu, wie Dashboards für Führungskräfte konfiguriert und dargestellt werden. Sehen Sie sich zunächst das Video zu Scorecard Builder für Analytics-Dashboards an:


>[!BEGINSHADEBOX]

Unter ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Erstellen von mobilen Scorecards](https://video.tv.adobe.com/v/343458?quality=12&learn=on){target="_blank"} finden Sie ein Demovideo.

>[!ENDSHADEBOX]


>[!NOTE]
>
>Die Analytics-Scorecard-Screenshots für diese Seite stammen aus der Adobe Analytics-Benutzeroberfläche und nicht aus Customer Journey Analytics. Die Benutzeroberflächen sind fast identisch.

Eine Analytics-Scorecard stellt wie nachfolgend gezeigt wichtige Datenvisualisierungen für Führungskräfte in einem Kachel-Layout bereit:

![Beispiel einer Analytics-Scorecard mit Demo für mobile Scorecards](assets/intro_scorecard.png)

Wenn Sie diese Scorecard kuratieren, können Sie mit dem Scorecard Builder festlegen, welche Kacheln auf der Scorecard für die Führungskraft angezeigt werden. Sie können auch konfigurieren, wie die detaillierten Ansichten bzw. Aufschlüsselungen angepasst werden können, nachdem auf die Kacheln getippt wird. So sieht die Scorecard Builder-Benutzeroberfläche aus:

![Scorecard Builder mit dem Fenster Neue mobile Scorecard. ](assets/scorecard_builder.png)

Gehen Sie zur Erstellung der Scorecard wie folgt vor:

1. Greifen Sie auf die Vorlage für [!UICONTROL leere mobile Scorecards] in Workspace zu.
2. Konfigurieren Sie die Scorecard mit Daten und speichern Sie sie.

## Zugriff auf die Vorlage für [!UICONTROL leere mobile Scorecards] {#template}

Sie können die Vorlage [!UICONTROL Leere mobile Scorecard] öffnen, indem Sie entweder ein neues Projekt erstellen oder über das Menü Tools zugreifen.

### Neues Projekt erstellen {#create}

1. Öffnen Sie Customer Journey Analytics und klicken Sie auf die Registerkarte **[!UICONTROL Arbeitsbereich]**.
1. Klicken Sie in der linken Leiste auf **[!UICONTROL Projekte]**.
1. Klicken Sie auf die Schaltfläche **[!UICONTROL Projekt erstellen]** und wählen Sie die Projektvorlage **[!UICONTROL Leere mobile Scorecard]** aus.
1. Klicken Sie auf **[!UICONTROL Erstellen]**.

![Fenster Alle Vorlagen mit ausgewählter Vorlage Leere mobile Scorecard.](assets/new_template.png)

### Tools-Menü

1. Wählen Sie im Menü **[!UICONTROL Tools]** die Option **[!UICONTROL Analytics-Dashboards (Mobile App)]** aus.
1. Klicken Sie im nachfolgenden Bildschirm auf **[!UICONTROL Neue Scorecard erstellen]**.

## Scorecard mit Daten konfigurieren und speichern {#configure}

So implementieren Sie die Scorecard-Vorlage:

1. Geben Sie unter **[!UICONTROL Scorecard-Eigenschaften]** (in der rechten Leiste) eine **[!UICONTROL Datenansicht des Projekts]** an, aus der Sie Daten verwenden möchten.

   ![Fenster Neue mobile Scorecard mit hervorgehobener Auswahl für die Datenansicht](assets/properties_save.png)

1. Um Ihrer Scorecard eine neue Kachel hinzuzufügen, ziehen Sie eine Metrik aus dem linken Panel und legen Sie sie im Bereich **[!UICONTROL Metriken hierhin ziehen und ablegen]** ab. Sie können auch eine Metrik zwischen zwei Kacheln einfügen, indem Sie einen ähnlichen Workflow verwenden.

   ![Fenster Neue mobile Scorecard mit einem Pfeil, der auf eine Metrik (Neue KPI) zeigt, die auf der Scorecard abgelegt wurde. ](assets/build_list.png)


1. Von jeder Kachel aus können Sie auf eine Detailansicht zugreifen, die zusätzliche Informationen über die Metrik anzeigt, wie z. B. die obersten Elemente in einer Liste verwandter Dimensionen.

## Dimensionen oder Metriken hinzufügen {#dimsmetrics}

Um einer Metrik eine verwandte Dimension hinzuzufügen, ziehen Sie eine Dimension aus dem linken Bereich und legen Sie sie auf einer Kachel ab.

Sie können beispielsweise geeignete Dimensionen (wie **[!DNL Marketing Channel]** in diesem Beispiel) zur Metrik **[!UICONTROL Unique Visitors]** hinzufügen, indem Sie sie auf die Kachel ziehen und dort ablegen. Aufschlüsselungen von Dimensionen werden im Abschnitt [!UICONTROL Drill Ins] (Aufschlüsselung) der kachelspezifischen **[!UICONTROL Eigenschaften]** angezeigt. Sie können jeder Kachel mehrere Dimensionen hinzufügen.

![Fenster Neue mobile Scorecard mit einem Pfeil, der von der Dimensionsliste auf den Scorecard-Bereich zeigt.](assets/layer_dimensions.png)

## Segmente anwenden {#segments}

Um ein Segment auf einzelne Kacheln anzuwenden, ziehen Sie es aus dem linken Bereich und legen Sie es direkt auf der Kachel ab.

Wenn Sie das Segment auf alle Kacheln in der Scorecard anwenden möchten, legen Sie die Kachel oben auf der Scorecard ab. Sie können Segmente auch anwenden, indem Sie im Segmentmenü unterhalb der Datumsbereiche Segmente auswählen. Die [Konfiguration und Anwendung von Segmenten für Ihre Scorecards](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=de) entspricht der Vorgehensweise in Customer Journey Analytics Workspace.

![Dropdown-Segmentauswahl, wobei die erstellten Segmente hervorgehoben sind](assets/segment_ui.png)

## Datumsbereiche hinzufügen {#dates}

Um Datumsbereichskombinationen, die in Ihrer Wertungsliste ausgewählt werden können, hinzuzufügen oder zu entfernen, wählen Sie die Dropdown-Liste „Datumsbereich“ aus.

![Fenster Neue mobile Scorecard mit hervorgehobener Gegenüberstellung Gestern vs. Selber Tag in der letzten Woche](assets/new_score_card.png)

Jede neue Scorecard Beginn mit 6 Datumsbereichskombinationen, die sich auf den Datumsbereich von heute und gestern konzentrieren. Sie können unnötige Datumsbereiche entfernen, indem Sie auf das „x“ klicken, oder Sie können jede Datumsbereichskombination durch Klicken auf den Stift bearbeiten.

![Fenster Neue mobile Scorecard mit hervorgehobenem Stiftsymbol](assets/new_score_card2.png)

Um ein Primärdatum zu erstellen oder zu ändern, wählen Sie über die Dropdown-Liste aus den verfügbaren Datumsbereichen aus oder ziehen Sie eine Datumskomponente aus der rechten Leiste in den Ablagebereich.

![Fenster Neue mobile Scorecard mit unter Datumsbereiche“ hervorgehobenem Dropdown Primäres Datum und ausgewählter Option Gestern](assets/new_score_card3.png)

Um ein Vergleichsdatum zu erstellen, können Sie im Dropdown-Menü aus praktischen Voreinstellungen für gängige Zeitvergleiche auswählen. Sie können auch eine Datumskomponente aus der rechten Leiste ziehen und ablegen.

![Fenster Neue mobile Scorecard mit unter Datumsbereiche hervorgehobenem Dropdown Vergleichsdatum und ausgewählter Option Selber Tag in der letzten Woche](assets/new_score_card4.png)

Wenn der gewünschte Datumsbereich noch nicht erstellt wurde, können Sie durch Klicken auf das Kalendersymbol einen neuen erstellen.

![Kalendersymbol](assets/new_score_card5.png)

Dadurch gelangen Sie zum Generator für den Datumsbereich, in dem Sie eine neue Komponente für den Datumsbereich erstellen und speichern können.

### Vergleichsdatumsbereiche anzeigen oder ausblenden {#show-comparison-dates}

Um Vergleichsdatumsbereiche einzubeziehen, schalten Sie die Einstellung **Vergleichsdaten einschließen** um.

![Fenster Neue mobile Scorecard mit hervorgehobener Gegenüberstellung Gestern vs. Vortag und Option Vergleichsdaten einschließen](assets/include-comparison-dates.png)

Die Einstellung ist standardmäßig *an*. Schalten Sie sie *aus*, wenn Sie keine Vergleichsdaten anzeigen möchten.

![Fenster Neue mobile Scorecard mit hervorgehobener Option Gestern und Vergleichsdaten einschließen](assets/no-comparison-dates.png)

## Visualisierungen anwenden {#viz}

Analytics-Dashboards bieten vier Visualisierungen, die Ihnen einen umfassenden Einblick in Dimensionselemente und Metriken bieten. Wenn Sie eine andere Visualisierung anwenden möchten, ändern Sie den [!UICONTROL Diagrammtyp] in den [!UICONTROL Eigenschaften] einer Kachel. Wählen Sie einfach die rechte Kachel aus und ändern Sie dann den Diagrammtyp.

![Kacheleigenschaften](assets/properties.png)

Oder klicken Sie auf das Symbol für [!UICONTROL Visualisierungen] in der linken Leiste und ziehen Sie die rechte Visualisierung per Drag &amp; Drop auf die Kachel:

![Visualisierungen](assets/vizs.png)

### [!UICONTROL Zusammenfassungszahl]

Verwenden Sie die Visualisierung der Zusammenfassungsnummer, um eine große Zahl hervorzuheben, die in einem Projekt wichtig ist.

![Fenster Neue mobile Scorecard mit Visualisierung Zusammenfassungzahl, die die Zahl von 13.300 Besuchen hervorhebt](assets/summary-number.png)

### [!UICONTROL Ringdiagramm]

Ähnlich einem Tortendiagramm zeigt diese Visualisierung die Daten als Teile eines Ganzen. Ein Ringdiagramm kann für den Vergleich der prozentualen Anteile eines Ganzen verwendet werden. Angenommen, Sie möchten sehen, welche Anzeigenplattform zur Gesamtzahl der Unique Persons beigetragen hat:

![Fenster Neue mobile Scorecard mit einer Visualisierung Ringdiagramm](assets/donut-viz.png)

### [!UICONTROL Linie]

Die Linienvisualisierung stellt Metriken anhand einer Linie dar, die den Wertverlauf über einen bestimmten Zeitraum hinweg zeigt. Ein Liniendiagramm zeigt Dimensionen im Zeitverlauf an, funktioniert aber bei jeder Visualisierung. In diesem Beispiel visualisieren Sie die Dimension „Produktkategorie“.

![Fenster Neue mobile Scorecard mit einer Visualisierung Linie](assets/line.png)

### [!UICONTROL Horizontalbalken]

Diese Visualisierung zeigt Horizontalbalken, die verschiedene Werte aus einer oder mehreren Metriken darstellen. Verwenden Sie zum Beispiel [!UICONTROL Horizontalbalken] als bevorzugte Visualisierung, um ganz leicht zu erkennen, welches Ihre Top-Produkte sind.

![Fenster Neue mobile Scorecard mit einem horizontalen Balken](assets/horizontal.png)

## Benennen von Scorecards {#name}

Um die Scorecard zu benennen, klicken Sie auf den Namensbereich in der oberen linken Ecke des Bildschirms und geben Sie den neuen Namen ein.

![Scorecards benennen](assets/new_name.png)

### Dimensionselement des Typs [!UICONTROL Nicht angegeben] entfernen {#remove-dims}

Wenn Sie Dimensionselemente des Typs [!UICONTROL Nicht angegeben] aus Ihren Daten entfernen möchten, gehen Sie wie folgt vor:

1. Wählen Sie die richtige Kachel aus.
1. Wählen Sie in der rechten Leiste unter **[!UICONTROL Drill-ins]** den Rechtspfeil neben dem Dimensionselement aus, für das Sie Elemente des Typs **[!UICONTROL Nicht angegeben]** entfernen möchten.

   ![Eigenschaften mit einem Pfeil, der auf den Pfeil nach rechts neben dem Dimensionsnamen zeigt.](assets/unspecified.png)

1. Klicken Sie auf das Symbol neben **[!UICONTROL Nicht angegeben]**, um nicht spezifizierte Daten aus Ihrem Reporting zu entfernen. (Sie können auch jedes andere Dimensionselement entfernen.)

## Anzeigen und Konfigurieren von Kacheleigenschaften {#tiles}

Wenn Sie im Scorecard Builder auf eine Kachel klicken, zeigt die rechte Leiste die Eigenschaften und Merkmale an, die mit dieser Kachel und ihrer Detailfolie verbunden sind. In dieser Leiste können Sie einen neuen **Titel** für die Kachel erstellen und die Kachel konfigurieren, indem Sie Segmente anwenden.

![Kachel „Eigenschaften“](assets/properties-tile-new.png)

## Anzeigen von Detailfolien {#view-detail-slides}

Wenn Sie auf Kacheln klicken, wird in einem dynamischen Popup-Fenster angezeigt, wie die Detailfolie für ausführende Benutzende in der Mobile App dargestellt wird. Sie können Dimensionen hinzufügen, um Ihre Daten für Ihre spezifischen Anforderungen aufzuschlüsseln. Wenn keine Dimension angewandt wurde, ist die Aufschlüsselungs-Dimension **Stunde** oder **Tage**, je nach dem standardmäßigen Datumsbereich.

Aufschlüsselungen verfeinern Ihre Analyse, indem sie die Metriken nach Dimensionselementen wie den folgenden aufschlüsseln:

* Metrik „Unique Visitors“ aufgeschlüsselt nach Anzeigenplattform (AMO-ID)
* Besuche aufgeschlüsselt nach Produktkategorie (Einzelhandel)
* Gesamtumsatz aufgeschlüsselt nach Produktnamen

![Aufschlüsselungsansicht](assets/break_view.png)

Jede der Kachel hinzugefügte Dimension wird in einem Dropdown-Menü in der Detailansicht der App angezeigt. Der ausführende Benutzer kann dann aus den im Dropdown-Menü aufgelisteten Optionen auswählen.

## Anpassen von Detailfolien {#customize-detail-slide}

Benutzerdefinierte Detailansichten ermöglichen es Ihnen, Ihre Zielgruppe mit noch zielgerichteteren Informationen anzusprechen.


>[!BEGINSHADEBOX]

Unter ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Benutzerdefinierte Detailansichten](https://video.tv.adobe.com/v/3410002?quality=12&learn=on){target="_blank"} finden Sie ein Demovideo.

{{videoaa}}

>[!ENDSHADEBOX]

Sie können das Layout für jede Detailfolie ändern und Text hinzufügen, um Endbenutzenden zu helfen, die Daten besser zu verstehen. Sie können auch über das Dropdown-Menü den Diagrammtyp ändern.

![Benutzerdefinierte Detailfolie](assets/custom-detail-slide.png)

### Ändern des Folien-Layouts

Ändern Sie das Folien-Layout, um die Aufmerksamkeit der Betrachtenden zu fokussieren. Sie können beispielsweise das Layout so ändern, dass nur ein Diagramm oder nur eine Tabelle angezeigt wird. Um das Folien-Layout zu ändern, wählen Sie eines der vordefinierten Formate aus.

![Folien-Layout](assets/layout.png)

Sie können das Folien-Layout auch ändern, indem Sie Visualisierungskomponenten aus der linken Leiste auf die Arbeitsfläche ziehen und dort ablegen. Jede Detailfolie darf nur zwei Visualisierungen gleichzeitig enthalten.

![Ändern des Folien-Layouts](assets/slide-layout-change.png)

### Hinzufügen von beschreibendem Text zu einer Folie

Sie können Text hinzufügen, um aussagekräftige Informationen über den Inhalt der Diagramme oder die Bedeutung von Daten bereitzustellen.

Um einer Detailfolie Text hinzuzufügen, wählen Sie ein Layout aus, für das das Symbol `T` angezeigt wird, oder ziehen Sie die Textvisualisierungskomponente aus der linken Leiste und legen Sie diese ab. Der Texteditor wird automatisch geöffnet, wenn eine neue Textvisualisierung hinzugefügt oder ein Folien-Layout mit Text ausgewählt wird. Der Texteditor bietet alle Standardoptionen zur Textformatierung, Sie können Textstile wie Absätze, Überschriften und Unterüberschriften anwenden und eine fett oder kursiv formatierte Schriftart auswählen. Sie können Text ausrichten sowie Listen mit Aufzählungszeichen, Nummerierungen und Links hinzufügen. Wenn Sie die Bearbeitung abgeschlossen haben, klicken Sie oben rechts im Texteditor auf die Schaltfläche „Minimieren“, um den Texteditor zu schließen. Um bereits hinzugefügten Text zu bearbeiten, wählen Sie zum erneuten Öffnen des Texteditors das Stiftsymbol aus.

![Ändern des Folien-Layouts](assets/add-descriptive-text.png)

## Entfernen von Komponenten {#remove}

Um eine Komponente zu entfernen, die auf die gesamte Scorecard angewendet wird, klicken Sie außerhalb der Kacheln auf eine beliebige Stelle auf der Scorecard. Entfernen Sie die dann die Komponente, indem Sie auf das **x** klicken, das angezeigt wird, wenn Sie den Mauszeiger über die Komponente bewegen, wie unten für die **Erstbesuche** dargestellt:

![Entfernen von Komponenten](assets/new_remove.png)

## Erstellen von Daten-Storys {#create-data-story}

Eine Daten-Story ist eine Sammlung unterstützender Datenpunkte, Geschäftskontexte und verwandter Metriken, die auf einem zentralen Thema oder einer zentralen Metrik basieren.

Wenn Sie sich beispielsweise auf den Webtraffic konzentrieren, können Besuche Ihre wichtigste Metrik sein. Neue Personen oder Unique Persons sind für Sie aber möglicherweise ebenfalls interessant. Vielleicht möchten Sie auch Daten sehen, die nach Web-Seite oder dem Gerätetyp aufgeschlüsselt sind, von dem der Traffic stammt. Daten-Storys in mobilen Scorecard-Projekten ermöglichen es Ihnen, die wichtigsten Metriken in den Vordergrund zu stellen und gleichzeitig die gesamte Story hinter den Metriken mithilfe mehrerer Detailfolien zu erzählen.

Sehen Sie sich das Video an, um mehr über das Erstellen von Daten-Storys in Mobile-Scorecard-Projekten in Analysis Workspace zu erfahren.


>[!BEGINSHADEBOX]

Unter ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Daten-Storys für ein Projekt mit mobilen Scorecards](https://video.tv.adobe.com/v/3416392/?quality=12&learn=on){target="_blank"} finden Sie ein Demovideo.

{{videoaa}}

>[!ENDSHADEBOX]


**Erstellen einer Daten-Story** {#data-story-create}

Erstellen Sie Ihre Daten-Story, indem Sie einer Kachel mehrere Detailfolien hinzufügen.

1. Beginnen Sie mit einem Mobile-Scorecard-Projekt.
1. Wählen Sie eine Kachel aus, anhand der Sie eine Story erstellen möchten.
   ![Erstellen einer Daten-Story](assets/data-story1.png)
   ![Symbole zum Erstellen einer Daten-Story](assets/create-data-story.png){width=".50%"}
1. Fügen Sie Folien hinzu, um Ihre Daten-Story zu erstellen. Die erste Folie wird standardmäßig generiert.
Um neue Folien hinzuzufügen, bewegen Sie den Mauszeiger über eine Folie oder klicken Sie auf sie. Wählen Sie dann eine der verfügbaren Optionen aus:
   * Tippen Sie auf das Pluszeichen (+), um eine neue Folie zu erstellen.
   * Tippen Sie auf das Duplizieren-Symbol, um die vorhandene Folie zu duplizieren.
1. Wenn Sie eine leere Folie erstellen, ziehen Sie Komponenten per Drag-and-Drop aus der linken Leiste oder wählen Sie ein Layout aus, um die Folie automatisch mit den Daten aus der Kachel aufzufüllen.
   ![Erstellen einer Daten-Story](assets/data-story2.png)
Um eine Folie zu löschen, tippen Sie auf das Papierkorbsymbol.

### Anpassen einer Daten-Story {#customize-data-story}

Mit Daten-Storys können Sie alles anpassen, sodass Sie Informationen, die Sie weitergeben möchten, freigeben und alles ausschließen können, was Sie nicht benötigen. Sie können Kacheln und einzelne Folien anpassen, um Segmente hinzuzufügen, Aufschlüsselungen anzuzeigen, das Layout zu ändern und die Visualisierungen zu ändern.

**Anpassen von Kacheln**

1. Tippen Sie auf eine Kachel. Die ausgewählte Kachel wird blau dargestellt, und im rechten Bereich werden die Kacheleigenschaften angezeigt.
1. Ändern Sie den Titel, den Diagrammtyp und andere Kacheloptionen.
1. Ziehen Sie eine Komponente auf die Kachel.
   ![Erstellen einer Daten-Story](assets/data-story3.png)
Wenn Sie eine Komponente, z. B. eine Visualisierung, per Drag-and-Drop auf eine Kachel ziehen, wird die Komponente auf alle Daten-Story-Folien angewendet.
1. Für eine reine Titeländerung halten Sie die Umschalttaste gedrückt, um die Änderung anzuwenden.
   ![Erstellen einer Daten-Story](assets/data-story4.png)

>[!NOTE]
>Folien übernehmen Komponenten von der Kachel, Kacheln übernehmen jedoch keine Komponenten von Folien.

**Anpassen einzelner Folien**

Sie können die Visualisierung für einzelne Folien in einer Daten-Story ändern. Sie können beispielsweise einen horizontalen Balken für eine bestimmte Folie in ein Ringdiagramm ändern. Sie können auch das Layout ändern. Siehe [Anpassen von Detailfolien](#customize-detail-slide).

### Vorschau einer Daten-Story {#preview-data-story}

Nachdem Sie eine Daten-Story erstellt haben, verwenden Sie die Schaltfläche **Vorschau**, um eine Daten-Story so anzuzeigen und mit ihr zu interagieren, als würden Sie eine App nutzen. Informationen zur Vorschau Ihrer Daten-Story finden Sie unter [Vorschau einer Scorecard](#preview)

### Navigieren zwischen Kacheln und Folien {#navigate-tiles-slides}

In der Navigationsleiste werden Symbole angezeigt, die für den Inhalt der einzelnen Folien stehen. Die Navigationsleiste erleichtert die Navigation zu einer bestimmten Folie, wenn viele Folien vorhanden sind.

Um zwischen der Kachel und den Folien zu wechseln, tippen Sie auf die Navigationsleiste.
![Erstellen einer Daten-Story](assets/data-story5.png)
![Erstellen einer Daten-Story](assets/data-story-nav.png){width="45%"}

Sie können auch hin und her navigieren, indem Sie die Pfeile auf der Tastatur verwenden oder eine Komponente auswählen und links bzw. rechts auf dem Bildschirm gedrückt halten, um einen Bildlauf durchzuführen.

## Anzeigen von Scorecards in einer Vorschau {#preview}

Sie können eine Vorschau davon anzeigen, wie die Scorecard nach ihrer Veröffentlichung in der Adobe Analytics-Dashboards-App aussieht und funktioniert.

1. Klicken Sie auf **[!UICONTROL Vorschau]** in der rechten oberen Ecke des Bildschirms.

   ![Preview_scorecards](assets/preview.png)

1. Um anzuzeigen, wie die Scorecard auf verschiedenen Geräten aussehen wird, wählen Sie ein Gerät aus dem Dropdown-Menü [!UICONTROL Gerätevorschau].

   ![Device_preview](assets/device-preview.png)

1. Um mit der Vorschau zu interagieren, haben Sie folgende Möglichkeiten:

   * Klicken Sie mit der linken Maustaste, um das Tippen auf den Bildschirm des Smartphones zu simulieren.

   * Verwenden Sie die Bildlauffunktion Ihres Computers, um das Scrollen auf dem Bildschirm des Smartphones mit Ihrem Finger zu simulieren.

   * Klicken und halten Sie, um das Drücken und Halten des Fingers auf dem Bildschirm des Smartphones zu simulieren. Dies ist für die Interaktion mit den Visualisierungen in der Detailansicht nützlich.

## Freigeben von Scorecards {#share}

So geben Sie die Scorecard für eine Führungskraft frei:

1. Klicken Sie auf das Menü **[!UICONTROL Freigeben]** und wählen Sie **[!UICONTROL Scorecard freigeben]**.

1. Füllen Sie die Felder im Formular **[!UICONTROL Mobile Scorecard freigeben]** aus, indem Sie:

   * den Namen der Scorecard angeben
   * eine Beschreibung der Scorecard angeben
   * relevante Tags hinzufügen
   * die Empfänger der Scorecard angeben

1. Klicken Sie auf **[!UICONTROL Freigabe]**.

![Scorecards freigeben](assets/new_share.png)

Nachdem Sie eine Scorecard freigegeben haben, können die Empfänger in den Analytics-Dashboards darauf zugreifen. Wenn Sie in Scorecard Builder nachträgliche Änderungen an der Scorecard vornehmen, werden diese automatisch in der freigegebenen Scorecard aktualisiert. Führungskräfte sehen die Änderungen, nachdem sie die Scorecard in ihrer App aktualisiert haben.

Wenn Sie die Scorecard durch Hinzufügen neuer Komponenten aktualisieren, sollten Sie die Scorecard erneut freigeben (und die Option zum **[!UICONTROL Freigeben eingebetteter Komponenten]** aktivieren), um sicherzustellen, dass die ausführenden Benutzer Zugriff auf diese Änderungen haben.

### Freigeben von Scorecards über einen Freigabe-Link

Die Verwendung eines Freigabe-Links erleichtert die Freigabe einer Scorecard in einer E-Mail-, Dokument- oder Textnachrichten-App. Über den Freigabe-Link können Empfängerinnen und Empfänger die Scorecard auf ihrem Desktop oder in der Dashboards-App öffnen. Deeplinks, die freigegeben werden können, erleichtern die Freigabe von Projekten und fördern die Interaktion mit Ihren Stakeholdern.

So geben Sie eine Scorecard über einen Freigabe-Link frei:

1. Klicken Sie auf das Menü **[!UICONTROL Freigeben]** und wählen Sie **[!UICONTROL Scorecard freigeben]**.

   ![Scorecards freigeben](assets/share-scorecard.png)

1. Kopieren Sie den Link und fügen Sie ihn in eine E-Mail-, Dokument- oder IM-App ein.

   Wenn der Link von einer Empfängerin oder einem Empfänger über eine Desktop-Anwendung oder einen Browser aufgerufen wird, wird das mobile Scorecard-Projekt in Workspace geöffnet.

   Wenn der Link von einer Empfängerin oder einem Empfänger auf einem Mobilgerät aufgerufen, wird die Scorecard direkt in der Adobe Analytics-Dashboards-App geöffnet.

   Wenn eine Empfängerin oder ein Empfänger die App nicht heruntergeladen hat, wird diese Person zur App-Liste im App Store oder Google Play Store weitergeleitet, wo sie sie herunterladen kann.

