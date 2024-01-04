---
title: Geführte Analyse – Übersicht
description: Eine Methode zur Datenanalyse in Customer Journey Analytics, mit der Produktteams schnell hochwertige Einblicke erhalten können. Wird auch als Product Analytics bezeichnet.
keywords: Produktanalyse
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1278'
ht-degree: 2%

---

# Geführte Analyse – Übersicht

Mit Adobe Product Analytics können Produktteams Daten und Einblicke über ihr Produkterlebnis selbst bereitstellen, indem sie geleitete Analyse-Workflows durchführen, die auf den kanalübergreifenden Daten von Customer Journey Analytics aufbauen. Geführte Analyse ist ein Berichtsformat, das es Produktteams ermöglicht, schnell ihre Datenanforderungen selbst zu erfüllen, sodass sie schnell hochwertige Einblicke erhalten und datengesteuerte Produktentscheidungen treffen können. Funktions-Teams können in Echtzeit eine Verbindung herstellen, um diese Berichte zu verwenden und zu verstehen.

Ähnlich wie bei Analysis Workspace- und Mobile-Scorecards verwendet ein Bericht mit einer geführten Analyse Daten aus einer [Datenansicht](../data-views/data-views.md), die Daten in Adobe Experience Platform über eine referenziert [Verbindung](../connections/overview.md). Alle in der geführten Analyse erstellten Berichte können nahtlos zur weiteren Recherche an Analysis Workspace übermittelt werden.

Geführte Analyse bietet mehrere Möglichkeiten, Daten zu analysieren und anzuzeigen. Ansichtstypen können dieselben Daten auf unterschiedliche Weise anzeigen, was zu unterschiedlichen Einblicken mit denselben Ereignissen und Segmenten führt. Je nach gewählter Ansicht werden unterschiedliche Abfrageleisten und Visualisierungseinstellungen angezeigt. Sie können frei zwischen Ansichten wechseln und alle anwendbaren Komponenten der Abfrageleiste übernehmen, wenn die Ansicht sie unterstützt.

Geführte Analyse kategorisiert Ansichtstypen in **Analysetypen**. Die folgenden Analyse- und Ansichtstypen sind verfügbar:

| Analysetyp | Ansichtstyp | Beschreibung |
| --- | --- | --- |
| [!UICONTROL Auswirkung] | [Version](types/release.md) | Vergleichen Sie die Leistung über gleiche Zeiträume vor und nach der Veröffentlichung. |
| [!UICONTROL Auswirkung] | [Erste Verwendung](types/first-use.md) | Messen Sie die Auswirkungen der erstmaligen Verwendung von Funktionen auf Schlüsselindikatoren. |
| [!UICONTROL Trichter] | [Friktion](types/friction.md) | Vergleichen Sie die Konversionsraten zwischen Schritten. |
| [!UICONTROL Trichter] | [Konversionstrends](types/conversion-trends.md) | Verfolgen Sie Änderungen der Konversionsraten im Zeitverlauf. |
| [!UICONTROL Benutzerwachstum] | [Aktiv](types/active.md) | Identifizieren Sie, wer neu ist, beibehalten, zurückkehren oder ruhend ist. |
| [!UICONTROL Benutzerwachstum] | [Nettowachstum](types/net-growth.md) | Gewinnen oder verlieren Sie Nutzende? |
| [!UICONTROL Trends] | [Verwendung](types/usage.md) | Messen Sie die Benutzerinteraktion im Zeitverlauf. |
| [!UICONTROL Trends] | [Häufigkeit](types/frequency.md) | Messen Sie die Interaktion nach Häufigkeit der Verwendung. |

{style="table-layout:auto"}

## Zugriff auf

Wenn Ihr Unternehmen für eine geleitete Analyse vorgesehen ist, können Sie über die Customer Journey Analytics-Startseite darauf zugreifen.

1. Klicks **[!UICONTROL Geführte Analyse]** von der Startseite aus, die Sie direkt zur [Ansicht zu Nutzungstrends](types/usage.md).

   ![Kachel der Landingpage](assets/landing-page-tile.png)

1. Klicks **[!UICONTROL Neu erstellen]** um die verschiedenen Ansichtsoptionen anzuzeigen und einen anderen Ausgangspunkt für Ihre Analyse auszuwählen.

   ![Neues Modal erstellen](assets/create-new-modal.png)

## Benutzeroberfläche

Die Oberfläche für die geführte Analyse folgt einem Frage- und Antwortformat. Erstellen Sie Ihre Frage in der Abfrageleiste und erhalten Sie dann eine Antwort mit einem schriftlichen Einblick, einer Grafik und einer Tabelle. Sie können dann die nächste Frage mit den Visualisierungseinstellungen und Ansichtstypen stellen.

Unabhängig vom Analysetyp verwendet die geführte Analyse die folgenden UI-Elemente:

| Benutzeroberfläche | UI-Element | Beschreibung |
| --- | --- | --- |
| ![Abfrageleiste](assets/query-rail.png) | Abfrageleiste | Konfigurieren Sie die gewünschten Komponenten (Ereignisse, Eigenschaften und Segmente), aus denen eine Analyse besteht. Jeder Analysetyp erzwingt unterschiedliche Beschränkungen für die Anzahl der Ereignisse und Segmente, die Sie konfigurieren können.<p>Verwenden Sie das Filtersymbol, um die Eigenschaften eines bestimmten Ereignisses einzugrenzen oder Segmente spontan zu erstellen. Sobald eine Eigenschaft ausgewählt ist, ist zusätzlich zu den Standardfilterkriterien wie &quot;gleich&quot;, &quot;enthält&quot;und &quot;endet mit&quot; eine Liste der Top-1000-Eigenschaftswerte verfügbar, die schnell gefiltert werden können.<p>Wenn Sie zu einem neuen Analysetyp wechseln, werden Ihre Abfrageauswahlen innerhalb der für diesen Analysetyp zulässigen Grenzen beibehalten. |
| ![Diagramm](assets/chart.png) | Diagramm | Eine Visualisierung der zurückgegebenen Daten basierend auf Ihrer Eingabe aus der Abfrageleiste und den Einstellungen. Welche Visualisierung Sie sehen, hängt von der Ansicht und den Einstellungen über dem Diagramm ab. Das Diagramm enthält außerdem: <ul><li>**Tooltips**: Bewegen Sie den Mauszeiger über einen beliebigen Diagrammdatenpunkt, um eine QuickInfo mit weiteren Informationen anzuzeigen.</li><li>**Legende**: Bewegen Sie den Mauszeiger über die Reihen der Diagrammlegende, um nach Möglichkeit Definitionen anzuzeigen, konzentrieren Sie sich auf diese Reihe und blenden Sie vorübergehend andere Reihen aus. Klicken Sie auf eine Reihe in der Legende, um sie auszublenden.</li><li>**Anmerkungen**: Gültig [Anmerkungen](../components/annotations/overview.md) zwischen der Visualisierung und der Legende sichtbar sind. Dies wird als ![Anmerkungssymbol](assets/annotation.png) in der konfigurierten Farbe der Anmerkung. Anzeigen von Typen, die Daten über einen bestimmten Zeitraum anzeigen, platzieren die ![Anmerkungssymbol](assets/annotation.png) unter dem konfigurierten Datum oder Datumsbereich. Wenn Sie Typen anzeigen, die keine Daten im Zeitverlauf anzeigen, wird die Variable ![Anmerkungssymbol](assets/annotation.png) in der rechten unteren Ecke des Diagramms.</li><li>**Klickaktionen**: Zeigen Sie die nächsten verfügbaren Aktionen an, indem Sie mit der linken Maustaste auf einen beliebigen Datenpunkt klicken. Optionen umfassen **Segment speichern**.</li></ul> |
| ![Tabelle](assets/table.png) | Tabelle | Eine Tabellendarstellung der zurückgegebenen Daten basierend auf Ihrer Eingabe aus der Abfrageleiste und den Einstellungen. Die Spalten in der Tabelle hängen vom Ansichtstyp über dem Diagramm ab. Die Tabelle enthält auch: <ul><li>**Klickaktionen**: Blendet eine Diagrammreihe aus oder zeigt sie an, indem Sie die ![Symbol zum Ausblenden](assets/hide-in-chart.png) in jeder Zeile. Weitere Aktionen sind verfügbar, indem Sie auf die **[!UICONTROL Mehr]** Menü. Optionen umfassen **Segment speichern**.</li></ul> |
| ![Visualisierungseinstellungen](assets/visualization-settings.png) | Visualisierungseinstellungen | Optionen über dem Diagramm, mit denen Sie die nächste Frage stellen und anpassen können, wie die Grafik und Tabelle Daten zurückgeben. Die folgenden Optionen sind für alle Ansichtstypen verfügbar, mit zusätzlichen Einstellungen, die pro Ansicht verfügbar sind. <ul><li>**Ansichtstyp**: Eine Dropdown-Auswahl, mit der Sie Daten für einen bestimmten Analysetyp auf andere Weise darstellen können.</li><li>**Diagrammeinstellungen**: Passen Sie die Anzeige Ihrer Diagramme und Tabellen an. Die verfügbaren Optionen hängen von der gewählten Ansicht ab.</li><li>**Datumsbereich**: Eine Kalenderauswahl, mit der Sie den Datumsbereich der Analyse ermitteln können. Sie können auch ein Intervall für Trend-Ansichten auswählen, z. B. für tägliche, wöchentliche oder monatliche Ansichten.</li><li>**Insights**: Kontextuelle Einblicke in Abhängigkeit von der von Ihnen angezeigten Analyse. Mithilfe der Pfeile können Sie weitere Einblicke aufrufen oder diese Einblicke mithilfe des Glühbirnensymbols oben rechts ein- oder ausblenden.</li></ul> |
| ![Menü](assets/menu.png) | Menü | Befehle oben rechts in der geführten Analyse, die übergreifende Aktionen für Ihre Analyse bieten.<ul><li>**Datenansichtsauswahl**: Ändern Sie die Datenansicht, die von der Analyse verwendet wird. Wenn Sie die Datenansicht ändern, ändern sich auch die verfügbaren Komponenten in der Abfrageleiste.</li><li>**Speichern**: Speichert die Analyse. Wenn Sie eine neue Analyse speichern, wird ein modales Fenster angezeigt, das einen Namen und eine Beschreibung anfordert.</li><li>**Speichern unter**: Speichert die Analyse getrennt von der aktuellen Analyse und erstellt eine Kopie. Es wird ein modales Fenster angezeigt, das einen neuen Namen und eine neue Beschreibung anfordert.</li><li>**In Workspace öffnen**: Erstellt die aktuelle geführte Analyse in Analysis Workspace erneut. Das Workspace-Projekt wird in einer neuen Registerkarte erstellt, wodurch Unterbrechungen beim Arbeiten mit der geführten Analyse verhindert werden. Es handelt sich um eine Kopie der Analyse, die nach dem Öffnen nicht mit der ursprünglichen geführten Analyse synchronisiert bleibt. Verwenden Sie diesen Befehl, wenn Sie die Daten an Ihr Analyseteam übergeben oder tiefer in die Daten eintauchen möchten, als die geführte Analyse zulässt.</li><li>**In Zwischenablage kopieren**: Kopiert die Diagrammgrafik in die Zwischenablage, um sie in andere Anwendungen einzufügen. Die Abfrageleiste und die Tabelle sind nicht in der Grafik enthalten.</li><li>**PNG herunterladen**: Laden Sie die Diagrammgrafik als `.png`. Die Abfrageleiste und die Tabelle sind nicht in der Grafik enthalten.</li><li>**CSV herunterladen**: Lädt die Tabellendaten als `.csv`. Die Abfrageleiste und das Diagramm sind nicht in der Datei enthalten.</li></ul> |

{style="table-layout:auto"}

## Bereitstellung

Geführte Analysen sind Teil des Adobe Product Analytics, das ein kostenpflichtiges Add-on zum Customer Journey Analytics ist. Wenden Sie sich an Ihr Adobe-Account-Team, wenn Ihr Unternehmen mit der Verwendung dieser Funktionen beginnen möchte.

Nachdem Ihr Unternehmen für die Verwendung der geführten Analyse bereitgestellt wurde, können Produktprofiladministratoren den Zugriff darauf in der Adobe Admin Console hinzufügen oder entfernen.

1. Melden Sie sich bei [Adobe Admin Console](https://adminconsole.adobe.com).
1. Auswählen **[!UICONTROL Customer Journey Analytics]** in der Liste der Erzeugnisse.
1. Wählen Sie das gewünschte Produktprofil für die Berechtigungen aus, die Sie bearbeiten möchten.
1. Klicken Sie auf **[!UICONTROL Berechtigungen]** Registerkarte und klicken Sie dann auf **[!UICONTROL Bearbeiten]** under [!UICONTROL Reporting-Tools].
1. Klicken Sie auf das Pluszeichen neben **[!UICONTROL Geführter Zugriff auf Analysen]** in der Liste der [!UICONTROL Verfügbare Berechtigungselemente], wodurch sie zur Liste der [!UICONTROL Eingeschlossene Berechtigungselemente].
1. Klicken Sie auf **[!UICONTROL Speichern]**.

>[!TIP]
>
>Manche Administratoren ziehen es vor, die Guided Analysis zu aktivieren und Analysis Workspace für neue Benutzer zum Customer Journey Analytics zu deaktivieren. Sobald diese Benutzer mit dem Produkt und Ihren Organisationsdaten vertraut sind, können Sie den Zugriff auf Analysis Workspace aktivieren.
