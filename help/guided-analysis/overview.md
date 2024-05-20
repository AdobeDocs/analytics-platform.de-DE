---
title: Überblick über die geführte Analyse
description: Eine Methode zur Datenanalyse in Customer Journey Analytics, mit der Produkt-Teams schnell hochwertige Einblicke erhalten können. Auch als „Product Analytics“ bezeichnet.
keywords: Produktanalysen
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: 2b8afe1dbac5057f867437e2bfce27f3bd752d57
workflow-type: ht
source-wordcount: '1397'
ht-degree: 100%

---

# Überblick über die geführte Analyse

Mit geführten Analysen können Benutzende hochwertige Daten und Erkenntnisse zur Kunden-Journey mithilfe geführter Workflows selbst bereitstellen, die auf den kanalübergreifenden Daten von Customer Journey Analytics basieren. Funktionsübergreifende Teams, vom Marketing bis zum Produkt, können in Echtzeit eine Verbindung herstellen, um diese Berichte zu verwenden und zu verstehen.

>[!NOTE]
>
> Die geführte Analyse ist derzeit nur als Bestandteil von Adobe Product Analytics erhältlich, einem kostenpflichtigen Add-on zu Customer Journey Analytics.  Wenn Ihr Unternehmen diese Reihe von Funktionen nutzen möchte, wenden Sie sich bitte an Ihr Adobe-Accountteam.

Ähnlich wie bei Analysis Workspace- und Mobile-Scorecards verwendet die geführte Analyse Daten aus einer [Datenansicht](../data-views/data-views.md), die auf Daten in Adobe Experience Platform über eine [Verbindung](../connections/overview.md) verweist. Viele Berichte, die mit einer geführten Analyse erstellt wurden, können nahtlos zur weiteren Recherche an Analysis Workspace übermittelt werden.

Die folgenden Ansichten geführter Analysen sind verfügbar:

| Analysetyp | Ansichtstyp | Beschreibung |
| --- | --- | --- |
| [!UICONTROL Funktionsmatrix] | [Interaktion](types/engagement.md) | Erfahren Sie mehr über Umfang und Tiefe der Funktionsinteraktion. |
| [!UICONTROL Trichter] | [Reibung](types/friction.md) | Vergleichen Sie die Konversionsraten zwischen den Schritten. |
| [!UICONTROL Trichter] | [Konversions-Trends](types/conversion-trends.md) | Verfolgen Sie ie dVeränderungen der Konversionsraten im Laufe der Zeit. |
| [!UICONTROL Auswirkungen] | [Version](types/release.md) | Vergleichen Sie die Leistung in gleichen Zeiträumen vor und nach der Veröffentlichung. |
| [!UICONTROL Auswirkungen] | [Erstmalige Verwendung](types/first-use.md) | Messen Sie die Auswirkung der erstmaligen Verwendung von Funktionen auf Schlüsselindikatoren. |
| [!UICONTROL Treue] | [Bindungsquote](types/retention-rates.md) | Messen Sie die Rückkehrgewohnheiten Ihrer Benutzenden. |
| [!UICONTROL Trends] | [Verwendung](types/usage.md) | Messen Sie die Benutzerinteraktion im Zeitverlauf. |
| [!UICONTROL Trends] | [Häufigkeit](types/frequency.md) | Messen Sie die Interaktion anhand der Nutzungshäufigkeit. |
| [!UICONTROL Benutzerwachstum] | [Aktiv](types/active.md) | Identifizieren Sie, wer neu ist, bleibt, zurückkehrt oder inaktiv ist. |
| [!UICONTROL Benutzerwachstum] | [Nettowachstum](types/net-growth.md) | Gewinnen oder verlieren Sie Benutzende? |
| [!UICONTROL Benutzer-Stream] | [Timeline](types/timeline.md) | Untersuchen Sie Muster in der Sitzungsaktivität. |

{style="table-layout:auto"}

## Zugriff

Wenn Ihr Unternehmen für eine geführte Analyse freigeschaltet wurde, können Sie über die Customer Journey Analytics-Startseite darauf zugreifen.

1. Klicken Sie auf der Startseite auf **[!UICONTROL Geführte Analyse]**. Von dort aus werden Sie direkt zur [Ansicht der Nutzungs-Trends](types/usage.md) weitergeleitet.

   ![Titel der Landingpage](assets/landing-page-tile.png){style="border:1px solid gray"}

1. Klicken Sie auf **[!UICONTROL Neu erstellen]**, um die verschiedenen Ansichtsoptionen anzuzeigen und einen anderen Ausgangspunkt für Ihre Analyse auszuwählen.

   ![Erstellen eines neuen Modals](assets/create-new-modal.png){style="border:1px solid gray"}

Wenn Ihr Unternehmen noch nicht für die geführte Analyse freigeschaltet ist, wenden Sie sich bitte an Ihr Adobe-Accountteam.

## Benutzeroberfläche

Die Oberfläche für die geführte Analyse verwendet ein Frage- und Antwortformat. Stellen Sie Ihre Frage in der Abfrageleiste. Anschließend erhalten Sie eine Antwort mit einem schriftlichen Einblick, einer Grafik und einer Tabelle. Sie können dann die nächste Frage mit Ansichtstypen und Visualisierungseinstellungen stellen.

Die geführte Analyse verwendet die folgenden Elemente der Benutzeroberfläche:

| Vorschau der Benutzeroberfläche | UI-Element | Beschreibung |
| --- | --- | --- |
| ![Abfrageleiste](assets/query-rail.png){style="border:1px solid gray"} | Abfrageleiste | Konfigurieren Sie Ihre „Frage“, indem Sie die gewünschten Komponenten (Ereignisse, Eigenschaften und Segmente) auswählen, aus denen eine Analyse besteht. Die folgenden Optionen sind für alle Ansichtstypen verfügbar, mit zusätzlichen Einstellungen, die pro Ansicht verfügbar sind. <ul><li>**Analyseauswahl**: Eine Dropdown-Liste, über die Sie zu einem neuen Analysetyp wechseln können. Ihre Abfrageauswahl wird innerhalb der für den neuen Analysetyp zulässigen Grenzen beibehalten.</li><li>**Auswahl anzeigen**: Eine Dropdown-Liste, über die Sie zu einer neuen Ansicht („Antwort“) für die erstellte Abfrage wechseln können. Ihre Abfrageauswahl wird innerhalb der zulässigen Grenzen für den neuen Ansichtstyp beibehalten.</li><li>**Ereignisse**: Die Ereignisse, die Sie messen möchten. Jeder Ansichtstyp erzwingt unterschiedliche Beschränkungen für die Anzahl der Ereignisse, die Sie konfigurieren können.</li><li>**Filter**: Verwenden Sie das ![Filter](assets/filter.png)-Symbol im Abschnitt „Ereignisse“ oder„Segmente“, um die einzelnen Eigenschaften einzuschränken. Wenn eine Eigenschaft ausgewählt ist, werden beide Standardfilterkriterien (z. B. [!UICONTROL Gleich], [!UICONTROL Enthält] oder [!UICONTROL Endet in]) und die 1000 wichtigsten Eigenschaftswerte verfügbar.</li><li>**Zählt als**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll.</li><li>**Segmente**: Die Segmente, die Sie messen möchten. Jeder Ansichtstyp erzwingt unterschiedliche Beschränkungen für die Anzahl der Segmente, die Sie konfigurieren können.</li></ul> |
| ![Diagramm](assets/chart.png){style="border:1px solid gray"} | Diagramm | Eine Visualisierung der zurückgegebenen Daten basierend auf Ihrer Eingabe aus der Abfrageleiste und den Einstellungen. Welche Visualisierung Sie sehen, hängt von der Ansicht und den Einstellungen über dem Diagramm ab. Das Diagramm enthält außerdem Folgendes: <ul><li>**QuickInfos**: Bewegen Sie den Mauszeiger über einen beliebigen Datenpunkt im Diagramm, um eine QuickInfo mit weiteren Informationen anzuzeigen.</li><li>**Legende**: Bewegen Sie den Mauszeiger über die Reihen der Diagrammlegende, um nach Möglichkeit Definitionen anzuzeigen, diese Reihe zu fokussieren und andere Reihen vorübergehend auszublenden. Blenden Sie eine Reihe in der Legende aus, indem Sie darauf klicken.</li><li>**Anmerkungen**: Gültige [Anmerkungen](../components/annotations/overview.md) sind zwischen der Visualisierung und der Legende sichtbar. Dies wird als ![Anmerkungssymbol](assets/annotation.png) in der konfigurierten Farbe der Anmerkung dargestellt. Bei Ansichtstypen, die Daten im Zeitverlauf anzeigen, befindet sich das Symbol ![Anmerkungssymbol](assets/annotation.png) unter dem konfigurierten Datum oder Datumsbereich. Bei Ansichtstypen, die Daten nicht im Zeitverlauf anzeigen, wird das Symbol ![Anmerkungssymbol](assets/annotation.png) in der unteren rechten Ecke des Diagramms angezeigt.</li><li>**Klick-Aktionen**: Zeigen Sie die nächsten verfügbaren Aktionen an, indem Sie mit der linken Maustaste auf einen beliebigen Datenpunkt klicken. Zu den Optionen gehört **Segment speichern**.</li></ul> |
| ![Tabelle](assets/table.png){style="border:1px solid gray"} | Tabelle | Eine Tabellendarstellung der zurückgegebenen Daten basierend auf Ihrer Eingabe aus der Abfrageleiste und den Einstellungen. Die Spalten in der Tabelle hängen vom Ansichtstyp über dem Diagramm ab. Die Tabelle enthält außerdem Folgendes: <ul><li>**Klick-Aktionen**: Blenden Sie eine Diagrammreihe aus oder zeigen Sie sie an, indem Sie in jeder Zeile das Symbol ![Symbol anzeigen/ausblenden](assets/hide-in-chart.png) umschalten. Weitere Aktionen sind verfügbar, wenn Sie auf die das Menü **[!UICONTROL Mehr]** klicken. Zu den Optionen gehört **Segment speichern**.</li></ul> |
| ![Visualisierungseinstellungen](assets/visualization-settings.png){style="border:1px solid gray"} | Visualisierungseinstellungen | Optionen über dem Diagramm, mit denen Sie die nächste Frage stellen und anpassen können, wie das Diagramm und die Tabelle Daten zurückgeben sollen. Die folgenden Optionen sind für alle Ansichtstypen verfügbar, mit zusätzlichen Einstellungen, die pro Ansicht verfügbar sind. <ul><li>**Diagrammeinstellungen**: Passt die Anzeige Ihrer Diagramme und Tabellen an. Die verfügbaren Optionen hängen von der gewählten Ansicht ab.</li><li>**Datumsbereich**: Eine Kalenderauswahl, mit der Sie den Datumsbereich der Analyse ermitteln können. Sie können auch ein Intervall für Trend-Ansichten auswählen, z. B. für tägliche, wöchentliche oder monatliche Ansichten.</li><li>**Erkenntnisse**: Kontextuelle Erkenntnisse in Abhängigkeit von der von Ihnen angezeigten Analyse. Diese Erkenntnisse liefern Beobachtungen für die aktuelle Analyse. Wenn mehrere Erkenntnisse verfügbar sind, können Sie sie mithilfe der Pfeile auf der rechten Seite anzeigen. Mit dem Glühbirnensymbol oben rechts können Sie die Sichtbarkeit dieses Feldes umschalten.</li></ul> |
| ![Menü](assets/menu.png){style="border:1px solid gray"} | Menü | Befehle oben rechts in der geführten Analyse, die übergreifende Aktionen für Ihre Analyse bieten.<ul><li>**Datenansichtsauswahl**: Ändert die Datenansicht, die von der Analyse verwendet wird. Wenn Sie die Datenansicht ändern, ändern sich auch die verfügbaren Komponenten in der Abfrageleiste.</li><li>**Link kopieren**: Kopiert einen Link zur Analyse in die Zwischenablage. Sie werden vor der Freigabe zum Speichern aufgefordert.</li><li>**Freigeben**: Öffnet das Freigabe-Modal mit weiteren Optionen zur Freigabe für einzelne Benutzende oder Gruppen. Sie können eine Analyse für andere Benutzende freigeben oder einen Link generieren, um ihn für andere freizugeben.</li><li>**Speichern**: Speichert die Analyse. Wenn Sie eine neue Analyse speichern, wird ein Modal-Fenster angezeigt, das einen Namen und eine Beschreibung verlangt.</li><li>**Speichern unter**: Speichert die Analyse getrennt von der aktuellen Analyse und erstellt eine Kopie. Es wird ein Modal-Fenster angezeigt, das einen neuen Namen und eine neue Beschreibung verlangt.</li><li>**In Workspace öffnen**: Erstellt die aktuelle geführte Analyse in Analysis Workspace erneut. Das Workspace-Projekt wird auf einer neuen Registerkarte erstellt, wodurch Unterbrechungen beim Arbeiten mit einer geführten Analyse verhindert werden. Es handelt sich um eine Kopie der Analyse, die nach dem Öffnen nicht mit der ursprünglichen geführten Analyse synchronisiert bleibt. Verwenden Sie diesen Befehl, wenn Sie sie an Ihr Analyse-Team übergeben oder tiefer in die Daten eintauchen möchten, als es die geführte Analyse zulässt.</li><li>**In Zwischenablage kopieren**: Kopiert die Diagrammgrafik in die Zwischenablage, um sie in andere Anwendungen einzufügen. Die Abfrageleiste und die Tabelle sind nicht in der Grafik enthalten.</li><li>**PNG herunterladen**: Lädt die Diagrammgrafik als `.png` herunter. Die Abfrageleiste und die Tabelle sind nicht in der Grafik enthalten.</li><li>**CSV herunterladen**: Lädt die Tabellendaten als `.csv` herunter. Die Abfrageleiste und das Diagramm sind nicht in der Datei enthalten.</li></ul> |

{style="table-layout:auto"}

## Bereitstellung

Die geführte Analyse ist Bestandteil von Adobe Product Analytics, einem kostenpflichtigen Add-on zu Customer Journey Analytics. Wenn Ihr Unternehmen diese Reihe von Funktionen nutzen möchte, wenden Sie sich bitte an Ihr Adobe-Accountteam.

Sobald Ihr Unternehmen für die Verwendung der geführten Analyse freigeschaltet ist, können Produktprofiladmins den Zugriff darauf in der Adobe Admin Console hinzufügen oder entfernen.

1. Melden Sie sich bei der [Adobe Admin Console](https://adminconsole.adobe.com) an.
1. Wählen Sie in der Produktliste **[!UICONTROL Customer Journey Analytics]** aus.
1. Wählen Sie das gewünschte Produktprofil für die Berechtigungen aus, die Sie bearbeiten möchten.
1. Klicken Sie auf die Registerkarte **[!UICONTROL Berechtigungen]** und dann unter [!UICONTROL Reporting-Tools] auf **[!UICONTROL Bearbeiten]**.
1. Klicken Sie in der Liste [!UICONTROL Verfügbare Berechtigungseinträge] auf das Plus-Symbol neben **[!UICONTROL Zugriff auf geführte Analysen]**, um es der Liste [!UICONTROL Eingeschlossene Berechtigungeinträge] hinzuzufügen.
1. Klicken Sie auf **[!UICONTROL Speichern]**.

>[!TIP]
>
>Einige Admins ziehen es vor, für neue Benutzende von Customer Journey Analytics die geführte Analyse zu aktivieren und Analysis Workspace zu deaktivieren. Sobald diese Personen mit dem Produkt und Ihren Unternehmensdaten vertraut sind, können Sie dann den Zugriff auf Analysis Workspace aktivieren.
