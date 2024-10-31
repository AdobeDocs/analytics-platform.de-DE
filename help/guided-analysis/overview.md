---
title: Überblick über die geführte Analyse
description: Eine Methode zur Datenanalyse in Customer Journey Analytics, mit der Produktteams schnell hochwertige Einblicke erhalten können.
keywords: Produktanalysen
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: 1e7d61f05a8351a1bd9e4d289c9d31906676f909
workflow-type: tm+mt
source-wordcount: '1806'
ht-degree: 32%

---

# Überblick über die geführte Analyse

Geführte Analysen ermöglichen es Benutzern, vom Marketing über das Produkt bis hin zu Analysten, hochwertige Daten und Einblicke über die Journey des Kunden mithilfe geführter Workflows bereitzustellen, die auf den kanalübergreifenden Daten von Customer Journey Analytics aufbauen. Ähnlich wie bei Analysis Workspace und Mobile Scorecards verwendet die geführte Analyse Daten aus einer [Datenansicht](/help/data-views/data-views.md), die Daten in Adobe Experience Platform über eine [Verbindung](../connections/overview.md) referenziert. Viele in der geführten Analyse erstellte Berichte können nahtlos in Analysis Workspace übertragen werden, um zusätzliche Forschungsarbeiten zu erhalten.

Die folgenden geführten Analysen sind verfügbar:

| Symbol | Analyse | Beschreibung |
| :----:|--- | --- |
| ![PeopleGroup](/help/assets/icons/PeopleGroup.svg) | [Aktives Wachstum](types/active-growth.md) | Identifizieren Sie, wer neu ist, bleibt, zurückkehrt oder inaktiv ist. |
| ![ConversionTrens](/help/assets/icons/ConversionTrends.svg) | [Konversions-Trends](types/conversion-trends.md) | Verfolgen Sie ie dVeränderungen der Konversionsraten im Laufe der Zeit. |
| ![EngagementGraph](/help/assets/icons/EngagementGraph.svg) | [Interaktion](types/engagement.md) | Erfahren Sie mehr über Umfang und Tiefe der Funktionsinteraktion. |
| ![FirstUse](/help/assets/icons/FirstUse.svg) | [Auswirkungen der ersten Verwendung](types/first-use-impact.md) | Messen Sie die Auswirkung der erstmaligen Verwendung von Funktionen auf Schlüsselindikatoren. |
| ![Histogramm](/help/assets/icons/Histogram.svg) | [Häufigkeit](types/frequency.md) | Messen Sie die Interaktion anhand der Nutzungshäufigkeit. |
| ![Konversionstrichter](/help/assets/icons/ConversionFunnel.svg) | [Trichter](types/funnel.md) | Vergleichen Sie die Konversionsraten zwischen den Schritten. |
| ![NetGrowth](/help/assets/icons/NetGrowth.svg) | [Nettowachstum](types/net-growth.md) | Gewinnen oder verlieren Sie Benutzende? |
| ![Version](/help/assets/icons/Release.svg) | [Auswirkungen der Veröffentlichung](types/release-impact.md) | Vergleichen Sie die Leistung in gleichen Zeiträumen vor und nach der Veröffentlichung. |
| ![Treue](/help/assets/icons/Retention.svg) | [Treue](types/retention.md) | Messen Sie die Rückkehrgewohnheiten Ihrer Benutzenden. |
| ![Timeline](/help/assets/icons/Timeline.svg) | [Timeline](types/timeline.md) | Untersuchen Sie Muster in der Sitzungsaktivität. |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [Trends](types/trends.md) | Messen Sie die Benutzerinteraktion im Zeitverlauf. |



## Zugriff

Sie können von der Customer Journey Analytics-Startseite aus auf die geführte Analyse zugreifen.

1. Wählen Sie **[!UICONTROL Geführte Analyse]** von der Startseite aus, wodurch Sie direkt zur [Trendanalyse](types/trends.md) gelangen.

   ![Titel der Landingpage](assets/landing-page-tile.png){style="border:1px solid gray"}

1. Wählen Sie **[!UICONTROL Neu erstellen]**, um die verschiedenen Ansichtsoptionen anzuzeigen und einen anderen Ausgangspunkt für Ihre Analyse auszuwählen.

   ![Erstellen eines neuen Modals](assets/create-new-modal.png){style="border:1px solid gray"}

Sie können auch von einem Analysis Workspace-Projekt aus auf die geführte Analyse zugreifen.

1. Wählen Sie auf der Startseite **[!UICONTROL Leeres Projekt]** aus, um ein leeres Workspace-Projekt zu erstellen.

   ![Erstellen eines leeren Projekts](assets/blank-project.png){style="border:1px solid gray"}

1. Wählen Sie in der linken Leiste ![Geführte Analyse](/help/assets/icons/GuidedAnalysis.svg) **[!UICONTROL Geführte Analyse]** aus.

   ![Linke Leiste in Workspace](assets/workspace-left-rail.png){style="border:1px solid gray"}

1. Ziehen Sie eine neue Analyse auf die Workspace-Arbeitsfläche und wählen Sie dann **[!UICONTROL Erstellen]** aus, um die gewünschte Analyse zu erstellen (z. B. **[!UICONTROL Trends erstellen]**). Sie können eine vorhandene Analyse auch aus dem Bereich **[!UICONTROL Gespeichert]** auf die Workspace-Arbeitsfläche ziehen.

   ![Erstellen eines Bedienfelds](assets/create-guided-analysis-panel.gif)

## Benutzeroberfläche

Die Schnittstelle für die geführte Analyse folgt einem Frage- und Antwortformat. Stellen Sie Ihre Frage in der Abfrageleiste. Anschließend erhalten Sie eine Antwort mit einem schriftlichen Einblick, einer Grafik und einer Tabelle. Anschließend können Sie die nächste Frage mit Analyse- und Visualisierungseinstellungen stellen.

Die geführte Analyse verwendet die folgenden Elemente der Benutzeroberfläche:

| Vorschau der Benutzeroberfläche | UI-Element | Beschreibung |
| --- | --- | --- |
| ![Abfrageleiste](assets/query-rail.png){style="border:1px solid gray"} | **[!UICONTROL Abfrageleiste]** | Konfigurieren Sie Ihre *Frage*, indem Sie die gewünschten Komponenten (Ereignisse, Eigenschaften und Segmente) auswählen, aus denen eine Analyse besteht. Die folgenden Optionen sind für alle Analysen verfügbar, mit zusätzlichen Einstellungen, die pro Ansicht verfügbar sind. <ul><li>**Ansicht**: Wählen Sie aus den Optionen aus, um zu einer neuen Analyse zu wechseln. Ihre Abfrageauswahlen bleiben innerhalb der für die neue Analyse zulässigen Grenzen.</li><li>**Ereignisse**: Die Ereignisse, die Sie messen möchten. Jede Analyse erzwingt unterschiedliche Beschränkungen für die Anzahl der Ereignisse, die Sie konfigurieren können.  Ereignisse werden manchmal als **[!UICONTROL Start- und Rückgabeereignisse]**, **[!UICONTROL Schritte]** oder **[!UICONTROL Schlüsselindikatoren]** bezeichnet. Ereignisse werden in der Analyse anhand von 1, 2, ...<br/>Wählen Sie ![Hinzufügen](/help/assets/icons/Add.svg) **[!UICONTROL Ereignis hinzufügen]** aus, um neue Ereignisse hinzuzufügen.</li><li>**[!UICONTROL Faktoren]**: Wenn verfügbar, können Sie Faktoren wie das Datum seit und das erste Mal angeben.</li><li>**Zählt als**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll. Wählen Sie aus dem Dropdown-Menü aus.</li><li>**Segmente**: Die Segmente, die Sie messen möchten. Jede Analyse erzwingt unterschiedliche Begrenzungen für die Anzahl der Segmente, die Sie konfigurieren können. Segmente werden in der Analyse anhand von A, B, ...<br/>Wählen Sie ![Hinzufügen](/help/assets/icons/Add.svg) **[!UICONTROL Hinzufügen eines Segments]** aus, um neue Segmente hinzuzufügen.</li><li>**[!UICONTROL Aufschlüsselung]**: Falls verfügbar, die Aufschlüsselung, die Sie auf die Analyse anwenden möchten.</li></ul>In einigen Einstellungen ist eine zusätzliche Konfiguration verfügbar.<ul><li>**Filter**: Verwenden Sie ![Filter](assets/filter.png), um Ereignisse oder Segmente nach bestimmten Dimensionen einzugrenzen. Wenn eine Dimension ausgewählt wird, sind beide Standardfilterkriterien (z. B. **[!UICONTROL Entspricht]**, **[!UICONTROL Enthält]** oder **[!UICONTROL Endet mit]**) und die Top-1000-Dimensionswerte verfügbar.<br/>Wählen Sie ![Filter](/help/assets/icons/Filter.svg) aus, um weitere Filter hinzuzufügen.<br/>Wählen Sie ![Entfernen](/help/assets/icons/Remove.svg) aus, um einen Filter zu entfernen.</li><li>**Mehr Aktionen**: Verwenden Sie ![Mehr](/help/assets/icons/More.svg), um Aktionen wie<ul><li>![Umbenennen](/help/assets/icons/Rename.svg) **[!UICONTROL Umbenennen]**: Zum Umbenennen eines Ereignisses oder Segments.</li><li>![Duplizieren](/help/assets/icons/Duplicate.svg) **[!UICONTROL Duplizieren]**: Duplizieren Sie ein Ereignis oder Segment.</li><li>![Löschen](/help/assets/icons/Delete.svg) **[!UICONTROL Entfernen]**: Zum Entfernen eines Ereignisses, Segments oder einer Aufschlüsselung.</li><li>![Segment bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Segment bearbeiten]**: Zum Bearbeiten eines Segments im [Filter-Builder](/help/components/filters/filter-builder.md).</li><li>![Stern](/help/assets/icons/Star.svg) **[!UICONTROL Zu Favoriten hinzufügen]**: Um das Segment zur Liste der Lieblingsfilter im [Filter-Manager](/help/components/filters/manage-filters.md) hinzuzufügen.</li><li>![SaveAsFloppy](/help/assets/icons/SaveAsFloppy.svg) **[!UICONTROL Save as]**: Zum Speichern des Segments als neue Komponente. Im Dialogfeld **[!UICONTROL Segmente in Komponenten speichern]** können Sie einen Segmentnamen und eine Beschreibung angeben. Sie können ![StarOutline](/help/assets/icons/StarOutline.svg) auswählen, um das neue Segment als Favoriten zu markieren. Wählen Sie **[!UICONTROL Speichern]** aus, um das Segment als neuen Filter zu speichern.</li><li>![Link](/help/assets/icons/Link.svg) **[!UICONTROL Link-Start- und -Rückgabeereignisse]**.: zum Verknüpfen von Start- und Rückgabeereignissen in einer [Bindungsanalyse](types/retention.md).</li><li>![Verknüpfung aufheben](/help/assets/icons/Unlink.svg) **[!UICONTROL Aufheben der Verknüpfung von Start- und Rückgabeereignissen]**: Um die Verknüpfung von Start- und Rückgabeereignissen in einer [Bindungsanalyse](types/retention.md) aufzuheben.</li></ul></li></ul> |
| ![Diagramm](assets/chart.png){style="border:1px solid gray"} | **[!UICONTROL Diagramm]** | Eine Visualisierung der zurückgegebenen Daten basierend auf Ihrer Eingabe aus der Abfrageleiste und den Einstellungen. Welche Visualisierung Sie sehen, hängt von der Ansicht und den Einstellungen über dem Diagramm ab. Das Diagramm enthält außerdem Folgendes: <ul><li>**QuickInfos**: Bewegen Sie den Mauszeiger über einen beliebigen Datenpunkt im Diagramm, um eine QuickInfo mit weiteren Informationen anzuzeigen.</li><li>**Legende**: Bewegen Sie den Mauszeiger über die Reihen der Diagrammlegende, um nach Möglichkeit Definitionen anzuzeigen, diese Reihe zu fokussieren und andere Reihen vorübergehend auszublenden. Wählen Sie eine Reihe in der Legende aus, um die Serie auszublenden.</li><li>**Anmerkungen**: Gültige [Anmerkungen](../components/annotations/overview.md) sind zwischen der Visualisierung und der Legende sichtbar. Dies wird als ![Anmerkungssymbol](assets/annotation.png) in der konfigurierten Farbe der Anmerkung dargestellt. Analysiert, die Daten im Zeitverlauf anzeigen, platzieren das Symbol ![Anmerkungssymbol](assets/annotation.png) unter dem konfigurierten Datumsbereich. Bei Analysen, die keine Daten im Zeitverlauf anzeigen, wird das Symbol ![Anmerkung](assets/annotation.png) in der rechten unteren Ecke des Diagramms angezeigt.</li><li>**Aktionen auswählen**: Machen Sie die nächsten verfügbaren Aktionen verfügbar, indem Sie einen beliebigen Datenpunkt auswählen. Zu den Optionen gehört **Segment speichern**.</li></ul> |
| ![Tabelle](assets/table.png){style="border:1px solid gray"} | **[!UICONTROL Tabelle]** | Eine Tabellendarstellung der zurückgegebenen Daten basierend auf Ihrer Eingabe aus der Abfrageleiste und den Einstellungen. Zeilen in der Tabelle mit Ereignis (1, 2, ...) und Segmentkennungen (A, B, ...) als Referenz. Die Spalten in der Tabelle hängen von der Analyse über dem Diagramm ab. Die Tabelle enthält auch für jede Zeile: <ul><li>**Aktionen auswählen**: Schalten Sie ![Ausblenden-Symbol anzeigen](assets/hide-in-chart.png) um, um eine Diagrammreihe für eine Zeile ein- oder auszublenden. Wählen Sie ![Mehr](/help/assets/icons/More.svg) für weitere Aktionen aus. Zu den Optionen gehört **Segment speichern**.</li></ul> |
| ![Visualisierungseinstellungen](assets/visualization-settings.png){style="border:1px solid gray"} | **[!UICONTROL Visualisierungseinstellungen]** | Optionen über dem Diagramm, mit denen Sie die nächste Frage stellen und anpassen können, wie das Diagramm und die Tabelle Daten zurückgeben sollen. Die folgenden Optionen stehen für alle Analysen zur Verfügung, wobei für jede Analyse zusätzliche Einstellungen verfügbar sind. <ul><li>![GraphTrend](/help/assets/icons/GraphTrend.svg) **Diagrammeinstellungen**: Passen Sie die Anzeige Ihres Diagramms und Ihrer Tabelle an. Die verfügbaren Optionen hängen von der ausgewählten Analyse ab.</li><li>![Ebene](/help/assets/icons/Layer.svg) **Überlagerungseinstellungen**: Fügen Sie eine Überlagerung hinzu. Die verfügbaren Optionen hängen von der ausgewählten Analyse ab.</li><li>![Bucket](/help/assets/icons/Bucket.svg) **[!UICONTROL Bucket-Einstellungen]**: Automatischer Bucket oder Anwendung benutzerdefinierter Behältereinstellungen auf die Daten. Die verfügbaren Optionen hängen von der ausgewählten Analyse ab.<li>![DataCorrelated](/help/assets/icons/DataCorrelated.svg) **[!UICONTROL Einstellungen vergleichen]**: Vergleichen Sie Daten mit einem bestimmten Datumsbereich. Die verfügbaren Optionen hängen von der ausgewählten Analyse ab.</li><li>![Schritte](/help/assets/icons/Footsteps.svg) **[!UICONTROL Anzeigeeinstellungen]**: Wählen Sie aus, wie die Daten angezeigt werden sollen. Die verfügbaren Optionen hängen von der ausgewählten Analyse ab.<li>![Kalender](/help/assets/icons/Calendar.svg) **Datumsbereich**: Eine Kalenderauswahl, mit der Sie den Datumsbereich der Analyse ermitteln können. Sie können auch ein Intervall für Trendanalysen auswählen, z. B. täglich, wöchentlich oder monatlich.</li><li>![LightBulb](/help/assets/icons/LightBulb.svg) **Insights**: Kontextuelle Einblicke in Abhängigkeit von der von Ihnen angezeigten Analyse. Diese Erkenntnisse liefern Beobachtungen für die aktuelle Analyse. Wenn mehrere Erkenntnisse verfügbar sind, können Sie sie mithilfe der Pfeile auf der rechten Seite anzeigen. Mit dem Glühbirnensymbol oben rechts können Sie die Sichtbarkeit dieses Feldes umschalten.</li></ul> |
| ![Menü](assets/menu.png){style="border:1px solid gray"} | **[!UICONTROL Menü]**<br/>In einem Projekt mit einer geführten Analyse verfügbar | Befehle oben rechts in einem geführten Analyseprojekt, die übergreifende Aktionen für Ihre Analyse bieten.<ul><li>![Daten](/help/assets/icons/Data.svg) ***Name der Datenansicht***: Ändern Sie die Datenansicht, die von der Analyse verwendet wird. Wenn Sie die Datenansicht ändern, ändern sich auch die verfügbaren Komponenten in der Abfrageleiste.</li><li>![Link](/help/assets/icons/Link.svg) **Link kopieren**: Kopiert einen Link zur Analyse in die Zwischenablage. Sie werden vor der Freigabe zum Speichern aufgefordert.</li><li>**Freigeben**: Öffnet das Freigabe-Modal mit weiteren Optionen zur Freigabe für einzelne Benutzende oder Gruppen. Sie können eine Analyse für andere Benutzende freigeben oder einen Link generieren, um ihn für andere freizugeben.</li><li>**Speichern**: Speichert die Analyse. Wenn Sie eine neue Analyse speichern, wird das Dialogfeld **[!UICONTROL Analyse speichern]** angezeigt, das einen Namen und eine Beschreibung anfordert. Nach dem Speichern können Sie mit einem Dialogfeld **[!UICONTROL Analyse gespeichert]** Ihre Analyse freigeben.</li></ul>Wählen Sie ![Mehr](/help/assets/icons/More.svg) für weitere Aktionen, z. B.:<ul><li>**Speichern unter**: Speichert die Analyse getrennt von der aktuellen Analyse und erstellt eine Kopie. Es wird ein Dialogfeld angezeigt, das einen neuen Namen und eine neue Beschreibung anfordert.</li><li>**Nach Workspace exportieren**: Erstellt die aktuelle Geführte Analyseabfrage in Analysis Workspace erneut. Das Workspace-Projekt wird in einer neuen Registerkarte erstellt, wodurch Unterbrechungen beim Arbeiten mit der geführten Analyse verhindert werden. Es handelt sich um eine Kopie der Analyse, die nach dem Öffnen nicht mit der ursprünglichen Analyse synchronisiert bleibt. Verwenden Sie diesen Befehl, wenn Sie die Daten an Ihr Analyseteam übergeben oder tiefer in die Daten eintauchen möchten, als die Analyse zulässt.</li><li>**Diagramm in die Zwischenablage kopieren**: Kopiert die Diagrammgrafik in die Zwischenablage, um sie in andere Anwendungen einzufügen. Die Abfrageleiste und die Tabelle sind nicht in der Grafik enthalten.</li><li>**PNG herunterladen**: Lädt die Diagrammgrafik als `.png` herunter. Die Abfrageleiste und die Tabelle sind nicht in der Grafik enthalten.</li><li>**CSV herunterladen**: Lädt die Tabellendaten als `.csv` herunter. Die Abfrageleiste und das Diagramm sind nicht in der Datei enthalten.</li></ul> |
| ![Menüvisualisierung](assets/menu-visualization.png){style="border:1px solid gray"} | **Menü**<br/> In einer Visualisierung der geführten Analyse im Analysis Workspace verfügbar. | Befehle in der Visualisierung einer geführten Analyse in Analysis Workspace.<ul><li>![GraphStreuung](/help/assets/icons/GraphScatter.svg) **[!UICONTROL Diagramm]**: Damit wird nur das Diagramm der Analyse angezeigt.</li><li>![Tabelle](/help/assets/icons/Table.svg) **[!UICONTROL Tabelle]**: Damit wird nur die Tabelle der Analyse angezeigt.</li><li>![TableAndChart](/help/assets/icons/TableAndChart.svg) **[!UICONTROL All]**: Zum Anzeigen von Diagrammen und Tabellen der Analyse.</li><li>![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]**: Zum Bearbeiten der Konfiguration der Analyse</li><li>![Kalender](/help/assets/icons/Calendar.svg) **[!UICONTROL *Datumsbereich *]**: Zum Konfigurieren des Datumsbereichs für die Analyse.</li></ul> |


## Bereitstellung

Geführte Analysen sind in Customer Journey Analytics-Packages wie folgt enthalten:

| Paket | Verfügbare Analysen |
| --- | --- |
| [!UICONTROL Customer Journey Analytics-Add-ons] | Aktives Wachstum, Konversionstrends, Häufigkeit, Trichter, Nettowachstum, Treue, Trends |
| [!UICONTROL Customer Journey Analytics Foundation] | Trends |
| [!UICONTROL Customer Journey Analytics Select] | Foundation-Ansichten + aktives Wachstum, Konversionstrends, Häufigkeit, Trichter, Nettowachstum, Treue |
| [!UICONTROL Customer Journey Analytics Prime] | Ansichten + Interaktion, Auswirkung auf die erste Verwendung, Auswirkungen auf die Veröffentlichung, Timeline auswählen |
| [!UICONTROL Customer Journey Analytics Ultimate] | Prime-Ansichten |

{style="table-layout:auto"}

Produktprofiladministratoren können den Zugriff auf die geführte Analyse in der Adobe Admin Console hinzufügen oder entfernen.

1. Melden Sie sich bei der [Adobe Admin Console](https://adminconsole.adobe.com) an.
1. Wählen Sie in der Produktliste **[!UICONTROL Customer Journey Analytics]** aus.
1. Wählen Sie das gewünschte Produktprofil für die Berechtigungen aus, die Sie bearbeiten möchten.
1. Wählen Sie die Registerkarte **[!UICONTROL Berechtigungen]** und klicken Sie dann unter [!UICONTROL Berichterstellungs-Tools] auf **[!UICONTROL Bearbeiten]** .
1. Wählen Sie ![Kreis hinzufügen](/help/assets/icons/AddCircle.svg) neben **[!UICONTROL Geführter Analysezugriff]** in der Liste der [!UICONTROL Verfügbaren Berechtigungselemente] aus, wodurch sie zur Liste der [!UICONTROL Eingeschlossenen Berechtigungselemente] hinzugefügt wird.
1. Wählen Sie **[!UICONTROL Speichern]** aus.

Weitere Informationen finden Sie unter [Benutzerebenenzugriff](/help/technotes/access-control.md#user-level-access) .

>[!TIP]
>
>Manche Administratoren ziehen es vor, die Guided Analysis zu aktivieren und Analysis Workspace für neue Benutzer zum Customer Journey Analytics zu deaktivieren. Sobald diese Personen mit dem Produkt und Ihren Unternehmensdaten vertraut sind, können Sie dann den Zugriff auf Analysis Workspace aktivieren.
