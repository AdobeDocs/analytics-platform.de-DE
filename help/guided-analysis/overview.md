---
title: Überblick über die geführte Analyse
description: Eine Methode zur Datenanalyse in Customer Journey Analytics, mit der Produkt-Teams schnell hochwertige Einblicke erhalten können. Auch als „Product Analytics“ bezeichnet.
keywords: Produktanalysen
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: c403a660e1d60b1ee2e5552d615dffc2b52930a4
workflow-type: tm+mt
source-wordcount: '1454'
ht-degree: 82%

---

# Überblick über die geführte Analyse

Mit geführten Analysen können Benutzende hochwertige Daten und Erkenntnisse zur Kunden-Journey mithilfe geführter Workflows selbst bereitstellen, die auf den kanalübergreifenden Daten von Customer Journey Analytics basieren. Funktionsübergreifende Teams, vom Marketing bis zum Produkt, können in Echtzeit eine Verbindung herstellen, um diese Berichte zu verwenden und zu verstehen.

Ähnlich wie bei Analysis Workspace- und Mobile-Scorecards verwendet die geführte Analyse Daten aus einer [Datenansicht](../data-views/data-views.md), die auf Daten in Adobe Experience Platform über eine [Verbindung](../connections/overview.md) verweist. Viele Berichte, die mit einer geführten Analyse erstellt wurden, können nahtlos zur weiteren Recherche an Analysis Workspace übermittelt werden.

Die folgenden Ansichten geführter Analysen sind verfügbar:

| Ansichtstyp | Beschreibung |
| --- | --- |
| [Interaktion](types/engagement.md) | Erfahren Sie mehr über Umfang und Tiefe der Funktionsinteraktion. |
| [Reibung](types/friction.md) | Vergleichen Sie die Konversionsraten zwischen den Schritten. |
| [Konversions-Trends](types/conversion-trends.md) | Verfolgen Sie ie dVeränderungen der Konversionsraten im Laufe der Zeit. |
| [Version](types/release.md) | Vergleichen Sie die Leistung in gleichen Zeiträumen vor und nach der Veröffentlichung. |
| [Erstmalige Verwendung](types/first-use.md) | Messen Sie die Auswirkung der erstmaligen Verwendung von Funktionen auf Schlüsselindikatoren. |
| [Bindungsquote](types/retention-rates.md) | Messen Sie die Rückkehrgewohnheiten Ihrer Benutzenden. |
| [Verwendung](types/usage.md) | Messen Sie die Benutzerinteraktion im Zeitverlauf. |
| [Häufigkeit](types/frequency.md) | Messen Sie die Interaktion anhand der Nutzungshäufigkeit. |
| [Aktiv](types/active.md) | Identifizieren Sie, wer neu ist, bleibt, zurückkehrt oder inaktiv ist. |
| [Nettowachstum](types/net-growth.md) | Gewinnen oder verlieren Sie Benutzende? |
| [Timeline](types/timeline.md) | Untersuchen Sie Muster in der Sitzungsaktivität. |

{style="table-layout:auto"}

## Zugriff

Sie können von der Customer Journey Analytics-Startseite aus auf die Geführte Analyse zugreifen.

1. Wählen Sie **[!UICONTROL Geführte Analyse]** von der Startseite aus, wodurch Sie direkt zur Ansicht [Nutzungstrends](types/usage.md) gelangen.

   ![Titel der Landingpage](assets/landing-page-tile.png){style="border:1px solid gray"}

1. Wählen Sie **[!UICONTROL Neu erstellen]** aus, um die verschiedenen Anzeigeoptionen anzuzeigen und einen anderen Ausgangspunkt für Ihre Analyse auszuwählen.

   ![Erstellen eines neuen Modals](assets/create-new-modal.png){style="border:1px solid gray"}

Sie können auch von einem Analysis Workspace-Projekt aus auf die geführte Analyse zugreifen.

1. Wählen Sie auf der Startseite die Option **[!UICONTROL Leeres Projekt]** aus, um ein leeres Workspace-Projekt zu erstellen.

   ![Leeres Projekt erstellen](assets/blank-project.png){style="border:1px solid gray"}

1. Wählen Sie in der linken Leiste die Option ![Geführte Analyse](/help/assets/icons/GuidedAnalysis.svg) **[!UICONTROL Geführte Analyse]** aus.

   ![Linke Leiste von Workspace](assets/workspace-left-rail.png){style="border:1px solid gray"}

1. Ziehen Sie einen beliebigen Ansichtstyp auf die Workspace-Arbeitsfläche und wählen Sie dann **[!UICONTROL Geführte Analyse erstellen *2} aus, um die gewünschte Analyse zu generieren (z. B.**[!UICONTROL Trends erstellen ]**).*]**Sie können eine vorhandene Analyse auch aus dem Bereich**[!UICONTROL Speichern ]**auf die Workspace-Arbeitsfläche ziehen.

   ![Bedienfeld erstellen](assets/create-guided-analysis-panel.gif)

## Benutzeroberfläche

Die Oberfläche für die geführte Analyse verwendet ein Frage- und Antwortformat. Stellen Sie Ihre Frage in der Abfrageleiste. Anschließend erhalten Sie eine Antwort mit einem schriftlichen Einblick, einer Grafik und einer Tabelle. Sie können dann die nächste Frage mit Ansichtstypen und Visualisierungseinstellungen stellen.

Die geführte Analyse verwendet die folgenden Elemente der Benutzeroberfläche:

| Vorschau der Benutzeroberfläche | UI-Element | Beschreibung |
| --- | --- | --- |
| ![Abfrageleiste](assets/query-rail.png){style="border:1px solid gray"} | Abfrageleiste | Konfigurieren Sie Ihre „Frage“, indem Sie die gewünschten Komponenten (Ereignisse, Eigenschaften und Segmente) auswählen, aus denen eine Analyse besteht. Die folgenden Optionen sind für alle Ansichtstypen verfügbar, mit zusätzlichen Einstellungen, die pro Ansicht verfügbar sind. <ul><li>**Analyseauswahl**: Eine Dropdown-Liste, über die Sie zu einem neuen Analysetyp wechseln können. Ihre Abfrageauswahl wird innerhalb der für den neuen Analysetyp zulässigen Grenzen beibehalten.</li><li>**Auswahl anzeigen**: Eine Dropdown-Liste, über die Sie zu einer neuen Ansicht („Antwort“) für die erstellte Abfrage wechseln können. Ihre Abfrageauswahl wird innerhalb der zulässigen Grenzen für den neuen Ansichtstyp beibehalten.</li><li>**Ereignisse**: Die Ereignisse, die Sie messen möchten. Jeder Ansichtstyp erzwingt unterschiedliche Beschränkungen für die Anzahl der Ereignisse, die Sie konfigurieren können.</li><li>**Filter**: Verwenden Sie das ![Filter](assets/filter.png)-Symbol im Abschnitt „Ereignisse“ oder„Segmente“, um die einzelnen Eigenschaften einzuschränken. Wenn eine Eigenschaft ausgewählt ist, werden beide Standardfilterkriterien (z. B. [!UICONTROL Gleich], [!UICONTROL Enthält] oder [!UICONTROL Endet in]) und die 1000 wichtigsten Eigenschaftswerte verfügbar.</li><li>**Zählt als**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll.</li><li>**Segmente**: Die Segmente, die Sie messen möchten. Jeder Ansichtstyp erzwingt unterschiedliche Beschränkungen für die Anzahl der Segmente, die Sie konfigurieren können.</li></ul> |
| ![Diagramm](assets/chart.png){style="border:1px solid gray"} | Diagramm | Eine Visualisierung der zurückgegebenen Daten basierend auf Ihrer Eingabe aus der Abfrageleiste und den Einstellungen. Welche Visualisierung Sie sehen, hängt von der Ansicht und den Einstellungen über dem Diagramm ab. Das Diagramm enthält außerdem Folgendes: <ul><li>**QuickInfos**: Bewegen Sie den Mauszeiger über einen beliebigen Datenpunkt im Diagramm, um eine QuickInfo mit weiteren Informationen anzuzeigen.</li><li>**Legende**: Bewegen Sie den Mauszeiger über die Reihen der Diagrammlegende, um nach Möglichkeit Definitionen anzuzeigen, diese Reihe zu fokussieren und andere Reihen vorübergehend auszublenden. Blenden Sie eine Reihe in der Legende aus, indem Sie darauf klicken.</li><li>**Anmerkungen**: Gültige [Anmerkungen](../components/annotations/overview.md) sind zwischen der Visualisierung und der Legende sichtbar. Dies wird als ![Anmerkungssymbol](assets/annotation.png) in der konfigurierten Farbe der Anmerkung dargestellt. Bei Ansichtstypen, die Daten im Zeitverlauf anzeigen, befindet sich das Symbol ![Anmerkungssymbol](assets/annotation.png) unter dem konfigurierten Datum oder Datumsbereich. Bei Ansichtstypen, die Daten nicht im Zeitverlauf anzeigen, wird das Symbol ![Anmerkungssymbol](assets/annotation.png) in der unteren rechten Ecke des Diagramms angezeigt.</li><li>**Aktionen auswählen**: Machen Sie verfügbare nächste Aktionen verfügbar, indem Sie einen beliebigen Datenpunkt auswählen. Zu den Optionen gehört **Segment speichern**.</li></ul> |
| ![Tabelle](assets/table.png){style="border:1px solid gray"} | Tabelle | Eine Tabellendarstellung der zurückgegebenen Daten basierend auf Ihrer Eingabe aus der Abfrageleiste und den Einstellungen. Die Spalten in der Tabelle hängen vom Ansichtstyp über dem Diagramm ab. Die Tabelle enthält außerdem Folgendes: <ul><li>**Aktionen auswählen**: Blenden Sie eine Diagrammreihe aus oder zeigen Sie sie an, indem Sie in jeder Zeile das Symbol ![Symbol zum Anzeigen von Ausblenden](assets/hide-in-chart.png) aktivieren. Zusätzliche Aktionen sind durch Auswahl des Menüs **[!UICONTROL Mehr]** verfügbar. Zu den Optionen gehört **Segment speichern**.</li></ul> |
| ![Visualisierungseinstellungen](assets/visualization-settings.png){style="border:1px solid gray"} | Visualisierungseinstellungen | Optionen über dem Diagramm, mit denen Sie die nächste Frage stellen und anpassen können, wie das Diagramm und die Tabelle Daten zurückgeben sollen. Die folgenden Optionen sind für alle Ansichtstypen verfügbar, mit zusätzlichen Einstellungen, die pro Ansicht verfügbar sind. <ul><li>**Diagrammeinstellungen**: Passt die Anzeige Ihrer Diagramme und Tabellen an. Die verfügbaren Optionen hängen von der gewählten Ansicht ab.</li><li>**Datumsbereich**: Eine Kalenderauswahl, mit der Sie den Datumsbereich der Analyse ermitteln können. Sie können auch ein Intervall für Trend-Ansichten auswählen, z. B. für tägliche, wöchentliche oder monatliche Ansichten.</li><li>**Erkenntnisse**: Kontextuelle Erkenntnisse in Abhängigkeit von der von Ihnen angezeigten Analyse. Diese Erkenntnisse liefern Beobachtungen für die aktuelle Analyse. Wenn mehrere Erkenntnisse verfügbar sind, können Sie sie mithilfe der Pfeile auf der rechten Seite anzeigen. Mit dem Glühbirnensymbol oben rechts können Sie die Sichtbarkeit dieses Feldes umschalten.</li></ul> |
| ![Menü](assets/menu.png){style="border:1px solid gray"} | Menü | Befehle oben rechts in der geführten Analyse, die übergreifende Aktionen für Ihre Analyse bieten.<ul><li>**Datenansichtsauswahl**: Ändert die Datenansicht, die von der Analyse verwendet wird. Wenn Sie die Datenansicht ändern, ändern sich auch die verfügbaren Komponenten in der Abfrageleiste.</li><li>**Link kopieren**: Kopiert einen Link zur Analyse in die Zwischenablage. Sie werden vor der Freigabe zum Speichern aufgefordert.</li><li>**Freigeben**: Öffnet das Freigabe-Modal mit weiteren Optionen zur Freigabe für einzelne Benutzende oder Gruppen. Sie können eine Analyse für andere Benutzende freigeben oder einen Link generieren, um ihn für andere freizugeben.</li><li>**Speichern**: Speichert die Analyse. Wenn Sie eine neue Analyse speichern, wird ein Modal-Fenster angezeigt, das einen Namen und eine Beschreibung verlangt.</li><li>**Speichern unter**: Speichert die Analyse getrennt von der aktuellen Analyse und erstellt eine Kopie. Es wird ein Modal-Fenster angezeigt, das einen neuen Namen und eine neue Beschreibung verlangt.</li><li>**In Workspace öffnen**: Erstellt die aktuelle geführte Analyse in Analysis Workspace erneut. Das Workspace-Projekt wird auf einer neuen Registerkarte erstellt, wodurch Unterbrechungen beim Arbeiten mit einer geführten Analyse verhindert werden. Es handelt sich um eine Kopie der Analyse, die nach dem Öffnen nicht mit der ursprünglichen geführten Analyse synchronisiert bleibt. Verwenden Sie diesen Befehl, wenn Sie sie an Ihr Analyse-Team übergeben oder tiefer in die Daten eintauchen möchten, als es die geführte Analyse zulässt.</li><li>**In Zwischenablage kopieren**: Kopiert die Diagrammgrafik in die Zwischenablage, um sie in andere Anwendungen einzufügen. Die Abfrageleiste und die Tabelle sind nicht in der Grafik enthalten.</li><li>**PNG herunterladen**: Lädt die Diagrammgrafik als `.png` herunter. Die Abfrageleiste und die Tabelle sind nicht in der Grafik enthalten.</li><li>**CSV herunterladen**: Lädt die Tabellendaten als `.csv` herunter. Die Abfrageleiste und das Diagramm sind nicht in der Datei enthalten.</li></ul> |

{style="table-layout:auto"}

## Bereitstellung

Geführte Analyseansichten sind in Customer Journey Analytics-Paketen auf folgende Weise enthalten:

| Paket | Verfügbare Ansichten |
| --- | --- |
| [!UICONTROL Customer Journey Analytics-Add-ons] | Trends: Nutzung, Trends: Häufigkeit, Trichter: Reibung, Trichter: Konversions-Trends, Bindung: Bindungsraten, Benutzerwachstum: Aktiv, Benutzerwachstum: Nettowachstum |
| [!UICONTROL Customer Journey Analytics Foundation] | Trends: Nutzung |
| [!UICONTROL Customer Journey Analytics Select] | Foundation-Ansichten + Trends: Häufigkeit, Trichter: Funktion, Trichter: Konversionstrends, Treue: Treueraten, Benutzerwachstum: Aktiv, Benutzerwachstum: Nettowachstum |
| [!UICONTROL Customer Journey Analytics Prime] | Ansichten auswählen + Benutzerstream: Timeline, Funktionsmatrix: Interaktion, Auswirkung: Veröffentlichung, Auswirkung: Erste Verwendung |
| [!UICONTROL Customer Journey Analytics Ultimate] | Prime-Ansichten |

{style="table-layout:auto"}

Produktprofiladmins können den Zugriff auf die geführte Analyse in der Adobe Admin Console hinzufügen oder entfernen.

1. Melden Sie sich bei der [Adobe Admin Console](https://adminconsole.adobe.com) an.
1. Wählen Sie in der Produktliste **[!UICONTROL Customer Journey Analytics]** aus.
1. Wählen Sie das gewünschte Produktprofil für die Berechtigungen aus, die Sie bearbeiten möchten.
1. Wählen Sie die Registerkarte **[!UICONTROL Berechtigungen]** und klicken Sie dann unter [!UICONTROL Berichterstellungs-Tools] auf **[!UICONTROL Bearbeiten]** .
1. Wählen Sie ![Kreis hinzufügen](/help/assets/icons/AddCircle.svg) neben **[!UICONTROL Geführter Analysezugriff]** in der Liste der [!UICONTROL Verfügbaren Berechtigungselemente] aus, wodurch sie zur Liste der [!UICONTROL Eingeschlossenen Berechtigungselemente] hinzugefügt wird.
1. Wählen Sie **[!UICONTROL Speichern]** aus.

Weitere Informationen finden Sie unter [Benutzerebenenzugriff](/help/technotes/access-control.md#user-level-access) .

>[!TIP]
>
>Einige Admins ziehen es vor, für neue Benutzende von Customer Journey Analytics die geführte Analyse zu aktivieren und Analysis Workspace zu deaktivieren. Sobald diese Personen mit dem Produkt und Ihren Unternehmensdaten vertraut sind, können Sie dann den Zugriff auf Analysis Workspace aktivieren.
