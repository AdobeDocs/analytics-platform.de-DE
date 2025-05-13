---
description: Fragen zur Datenanalyse in der Dokumentation zu Customer Journey Analytics
title: Visualisieren von Daten mit dem Data Insights Agent in Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: f3f3b34c904c1aeba3fbd07218f323ccd81974d4
workflow-type: tm+mt
source-wordcount: '1861'
ht-degree: 3%

---

# Visualisieren von Daten mit Data Insights Agent in Customer Journey Analytics

{{release-limited-testing}}

>[!AVAILABILITY]
>
>Data Insights Agent ist bis zum 30. November 2025 für berechtigte Customer Journey Analytics-Kunden verfügbar. Nach diesem Datum ist eine Lizenz erforderlich, wenn Sie Data Insights Agent weiterhin verwenden möchten. Wenden Sie sich an Ihr Adobe-Accountteam, um Unterstützung beim Lizenzierungsprozess zu erhalten.

Data Insights Agent, auf das über den KI-Assistenten in Customer Journey Analytics zugegriffen werden kann, ist ein generativer KI-Konversationsagent, der Fragen zu Ihren Daten schnell und effizient beantwortet. Er erstellt relevante Visualisierungen in Analysis Workspace mithilfe von Komponenten aus Ihrer Datenansicht und unter Verwendung Ihrer tatsächlichen Daten.

Die Verwendung von Data Insights Agent zur Beantwortung datenorientierter Fragen in Analysis Workspace kann unzählige Stunden einsparen, die Sie andernfalls möglicherweise damit verbringen würden, Visualisierungen in Analysis Workspace manuell zu erstellen und sich mit Ihren Datenansichtskomponenten vertraut zu machen.

![Data Insights-Agent im KI-Assistenten](assets/cja-ai-asst-da.gif)

## Funktionen innerhalb und außerhalb des Projektumfangs



### Umfangreiche Funktionen

| Unterstützte Funktion | Beschreibung |
| --- | --- |
| **Erstellen und Aktualisieren von Visualisierungen** | Erzeugt eine Freiformtabelle und eine dazugehörige Visualisierung (z. B. Linie, Balken, Ringdiagramm usw.).<p>Beispiel: *Was ist der Gewinn für alle SKUs von Februar bis Mai?* |
| **Unterstützte Visualisierungstypen** | <ul><li>Linie</li><li>Mehrzeilig</li><li>Freiformtabelle</li><li>Balken</li><li>Ringdiagramm</li><li>Zusammenfassungszahl</li></ul> |
| **Out-of-Scope Prompt Detection** | Wenn Sie eine Eingabeaufforderung übermitteln, die außerhalb des Projektumfangs liegt, z. B. „Dieses Projekt exportieren“, teilt Data Insights Agent Ihnen mit, dass die Frage außerhalb des Projektumfangs liegt. |
| **Fragen klären** | Wenn Sie eine Frage stellen, die nicht genügend Kontext für eine Antwort von Data Insights Agent hat oder zu generisch ist, antwortet Data Insights Agent mit einer klärenden Frage oder empfohlenen Optionen. Beispiele: <p>**Komponenten**<ul><li>Metrik: *Welche „Umsatz“-Metrik meinten Sie?*</li><li>Dimension: *Auf welche der folgenden „Regionen“ möchten Sie sich konzentrieren?*</li><li>Segment: *Welches „Konto“-Segment wollten Sie anwenden?*</li><li>Datumsbereich: *Mit „letztem Monat“ meinen Sie den letzten vollen Monat oder die letzten 30 Tage?*</li></ul>**Dimension-Elemente**: Welchen „Store-Namen“ meinten Sie? (Beispiel: #5274, #2949 usw.) |
| **Multi-Turn** | Data Insights Agent reagiert auf eine Eingabeaufforderung mit dem Kontext aus allen vorherigen Eingabeaufforderungen, sodass Benutzende Visualisierungen aktualisieren und Fragen stellen können. Beispiel: <ul><li>Eingabeaufforderung 1: *Trendereignisse ab März.*</li><li>Eingabeaufforderung 2: *Zeigen Sie mir stattdessen die Daten von März bis April*</li></ul> |
| **Verifizierbarkeit** | Die Datenverifizierbarkeit und -richtigkeit kann über die generierte Freiformtabelle und Datenvisualisierung bestätigt werden. Wenn ein(e) Benutzende(r) beispielsweise *Bestellungen im letzten Monat* fragt, können Sie bestätigen, dass im neu generierten Bedienfeld, in der Datenvisualisierung und in der Freiformtabelle die richtige Metrik („Bestellungen„) und der richtige Datumsbereich („letzter Monat„) ausgewählt wurden. |
| **Feedback** | <ul><li>Daumen hoch</li><li>Daumen runter</li><li>Markierung</li></ul> |

### Nicht im Umfang enthaltene Funktionen

| Nicht unterstützte Funktion | Beschreibung |
| --- | --- |
| **Inline-Zusammenfassung oder -Antwort** | Data Insights Agent kann in der Chat-Leiste nicht mit einer zusammenfassenden Antwort auf eine Benutzeraufforderung antworten. Beispiel für Eingabeaufforderungen außerhalb des Bereichs:<ul><li>*Geben Sie mir eine Zusammenfassung der Erkenntnisse aus meiner letzten Eingabeaufforderung.*</li><li>*Fassen Sie die Highlights der Linienvisualisierung zusammen.*</li></ul> |
| **Fragen klären** | Die Klärung von Fragen beschränkt sich auf Komponenten und Dimensionselemente. Data Insights Agent kann Dinge wie Datenansichten, Visualisierungen, Datengranularität, Vergleich und Umfang nicht verdeutlichen. Wenn Klärungsfragen nicht verwendet werden können, verwendet der Agent standardmäßig das, was Sie am wahrscheinlichsten anfordern. Wenn eine unerwartete Visualisierung oder Datengranularität zurückgegeben wird, können Sie die Funktion „Multi-Turn/Update“ verwenden, um die Visualisierung und die Daten anzupassen. |
| **Workspace-Aktionen/-Funktionen** | Data Insights Agent kann für einen Benutzer in Workspace keine Aktionen ausführen, abgesehen von der Erstellung und Aktualisierung von Visualisierungen. Sie kann beispielsweise keine der folgenden Aktionen ausführen:<ul><li>Schaltflächen der kontextuellen Aktionsbenutzeroberfläche (zum Diagramm hinzufügen, neues Bedienfeld, neue Tabelle)</li><li>Freigeben</li><li>Exportieren</li><li>Download</li><li>Benutzereinstellungen verwalten</li><li>Kuratieren</li><li>Datenansicht verwalten</li><li>Analytics Dashboards App</li><li>Attribution</li></ul> |
| **Nicht unterstützte Visualisierungsarten** | <ul><li>Fluss</li><li>Fallout</li><li>Kohortentabelle</li><li>Bereich, Bereich gestapelt</li><li>Balken gestapelt</li><li>Bullet</li><li>Kombination</li><li>Histogramm</li><li>Horizontalbalken, Horizontalbalken gestapelt</li><li>Zusammenfassung einer Schlüsselmetrik</li><li>Streuung</li><li>Zusammenfassende Änderung</li><li>Text</li><li>Baumkarte</li><li>Venn</li></ul> |

## Verwalten des Zugriffs auf Data Insights Agent in Customer Journey Analytics

Die folgenden Parameter regeln den Zugriff auf Data Insights Agent in Customer Journey Analytics:

* **Zugriff auf Lösungen**: Data Insights Agent ist für Kunden von Customer Journey Analytics Prime und Ultimate verfügbar. Sie ist in Adobe Analytics nicht verfügbar.

* **Vertragszugriff**: Wenn Sie Data Insights Agent nicht im KI-Assistenten verwenden können, wenden Sie sich bitte an den Administrator Ihres Unternehmens oder an Ihr Adobe-Accountteam. Bevor Ihr Unternehmen Data Insights Agent verwenden kann, müssen Sie bestimmten rechtlichen Bedingungen im Zusammenhang mit generativer KI zustimmen.

* **Berechtigungen**: Die erforderlichen Berechtigungen müssen in der [!UICONTROL Adobe Admin Console gewährt werden] bevor Benutzerinnen und Benutzer auf Data Insights Agent zugreifen können.

  Um Berechtigungen zu erteilen, muss [Produktprofil-Administrator](https://helpx.adobe.com/de/enterprise/using/manage-product-profiles.html) in der [!UICONTROL Admin Console die folgenden Schritte ausführen]:
   1. Wählen Sie in **[!UICONTROL Admin Console]** die Registerkarte **[!UICONTROL Produkte]** aus, um die Seite **[!UICONTROL Alle Produkte und Services]** anzuzeigen.
   1. **[!UICONTROL Customer Journey Analytics]**.
   1. Wählen Sie auf **[!UICONTROL Registerkarte]** den Titel des Produktprofils aus, für das Sie Zugriff auf den [!UICONTROL KI-Assistenten: Produktkenntnisse“ &#x200B;] möchten.
   1. Wählen Sie im jeweiligen Produktprofil die Registerkarte **[!UICONTROL Berechtigungen]** aus.

      ![Registerkarte „Berechtigungen“ in Admin Console](assets/ai-assistant-permissions-tab.png)

   1. Wählen Sie in **[!UICONTROL Zeile „Reporting]** Tools“ in der angegebenen Tabelle das Bearbeitungssymbol ![Bearbeiten](/help/assets/icons/Edit.svg).
   1. Scrollen Sie zu oder suchen Sie nach **[!UICONTROL KI-Assistent:]** Produktkenntnisse“ und klicken Sie dann auf das Pluszeichen ![AddCircle](/help/assets/icons/AddCircle.svg) neben dieser Berechtigung.

      Die Berechtigung **[!UICONTROL KI-Assistent: Produktwissen]** wird zur Spalte **[!UICONTROL Enthaltene Berechtigungselemente]** hinzugefügt.

      ![Berechtigung hinzufügen](assets/ai-assistant-permissions.png).

   1. Wählen Sie die Registerkarte **[!UICONTROL Datenansichts-Tools]** und klicken Sie auf das Pluszeichen ![AddCircle](/help/assets/icons/AddCircle.svg) neben der Berechtigung **[!UICONTROL Data Insights Agent]**.

      Die Berechtigung **[!UICONTROL Data Insights Agent]** wird der Spalte **[!UICONTROL Enthaltene Berechtigungselemente“]**.

      ![Berechtigung hinzufügen](assets/ai-assistant-permissions-dataviewtools.png).

   1. Wählen Sie die **[!UICONTROL Datenansichten]**, um die Datenansichten auszuwählen, die Sie für Data Insights Agent aktivieren möchten.

      >[!IMPORTANT]
      >
      >Die Data Insights Agent kann auf die enthaltenen Datenansichten verweisen, und zwar irgendwann während desselben Tages, an dem Sie sie in der Admin Console aktivieren.

   1. Suchen Sie nach den Datenansichten, die Sie aktivieren möchten, oder scrollen Sie zu ihnen. Klicken Sie dann auf das Pluszeichen ![AddCircle](/help/assets/icons/AddCircle.svg) neben dem Namen der einzelnen Datenansichten.

      Jede hinzugefügte Datenansicht ist in der Spalte &quot;**[!UICONTROL Berechtigungselemente“]**.

      ![Berechtigung hinzufügen](assets/ai-assistant-permissions-dataviews.png).

   1. Wählen Sie **[!UICONTROL Speichern]** aus, um die Berechtigungen zu speichern.

  Weitere Informationen zur Zugriffssteuerung finden Sie unter [Zugriffssteuerung](/help/technotes/access-control.md#access-control).

## Zugriff auf Data Insights Agent im KI-Assistenten

1. Gehen Sie zu [experience.adobe.com](https://experience.adobe.com/) und melden Sie sich mit Ihrer Adobe ID an.

2. Wählen Sie **Customer Journey Analytics** auf der Experience Cloud-Startseite aus.

3. Wählen Sie **[!UICONTROL Leeres Projekt]** im Banner oben auf der Projektseite aus, um ein neues leeres Projekt zu öffnen.

4. Stellen Sie sicher, dass es sich bei der für das Bedienfeld ausgewählten Datenansicht um eine Datenansicht handelt, die für die Verwendung mit Data Insights Agent aktiviert wurde, wie unter [Verwalten des Zugriffs auf Data Insights Agent in Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics) beschrieben.

5. Wählen Sie oben rechts auf der Seite das Chat-Symbol für den KI-Assistenten aus.

   Wenn das Chat-Symbol nicht angezeigt wird, wenden Sie sich an Ihren Administrator, damit er die folgenden Funktionen in der Admin Console aktivieren kann:

   * Reporting-Tools: **[!UICONTROL KI-Assistent: Produktkenntnisse]**

   * Datenansichts-Tools: **[!UICONTROL Data Insights Agent]**

   Weitere Informationen finden Sie unter [Zugriff auf Data Insights Agent in Customer Journey Analytics verwalten](#manage-access-to-data-insights-agent-in-customer-journey-analytics).

   ![KI-Assistenten-Symbol](/help/assets/ai-asst-icon.png)

6. Stellen Sie im **[!UICONTROL Fragen zu Customer Journey Analytics]** unten auf der Seite eine Frage zur Datenvisualisierung mit Data Insights Agent.

   Weitere Informationen finden Sie in den folgenden Beispielen.

### Beispiel 1

Nehmen wir beispielsweise an, Sie sind an den Bestellungen interessiert, die Ihr Unternehmen im Juli erhalten hat.

**Eingabeaufforderung:** Geben Sie *„Trend der Bestellungen im Juli“ ein*

![KI-Eingabeaufforderung](/help/assets/ai-asst-prompt1.png)

**Antwort:** Data Insights Agent sammelt Einblicke, indem es die Daten in der Datenansicht durchsucht, einschließlich der Metriken und Komponenten. Dadurch wird die Eingabeaufforderung in die richtigen Dimensionen und Metriken innerhalb des Datenbereichs übersetzt.

Wie Sie sehen können, wurden automatisch ein Liniendiagramm und eine Freiformtabelle generiert, um Bestellungen für Juli anzuzeigen.

![Antwort auf Eingabeaufforderung - Liniendiagramm und Freiformtabelle](/help/assets/ai-asst-result.png)

### Beispiel 2

Als Nächstes möchten Sie sehen, wie Ihr Umsatz nach Region verglichen wird.

**Prompt:** Geben Sie im Eingabeaufforderungsfenster *„Umsatz nach Region anzeigen“ ein*

**Antwort:** Data Insights Agent versteht, dass Sie mit „Region“ „Kundenregion“ meinen. Es wird ein Balkendiagramm erstellt, das den Umsatz am besten nach Region zeigt:

![Balkendiagramm](/help/assets/ai-asst-result2.png)

### Beispiel 3

Als Nächstes möchten Sie nicht nur den Umsatz nach Region verstehen, sondern auch Daten für den Gewinn nach Region anzeigen. Anstatt die vorherige Eingabeaufforderung zu wiederholen, können Sie Data Insights Agent bitten, die neueste Visualisierungs- und Freiformtabelle zu aktualisieren.

**Prompt:** Geben Sie im Eingabeaufforderungsfenster „Gewinn hinzufügen *ein*

**Antwort:** Das **[!UICONTROL Balkendiagramm]** bietet weiterhin die prägnanteste Antwort, aber die Gewinnmetrik wurde als Spalte in der Freiformtabelle hinzugefügt:

![Balkendiagramm](/help/assets/ai-asst-result4.png)

### Beispiel 4

Sehen wir uns abschließend den Umsatz nach Produktkategorie an.

**Eingabeaufforderung:** Geben Sie im Eingabeaufforderungsfenster *„Umsatzanteil nach Produktkategorie“ ein*

**Antwort** Auch hier wählt Data Insights Agent die am besten geeignete Visualisierung aus, in diesem Fall die **[!UICONTROL Ringdiagramm]**-Visualisierung, um die Frage zu beantworten.

![Ringdiagramm](/help/assets/ai-asst-result3.png)

## Eingabeaufforderungen zur Beispieldatenvisualisierung

Im Folgenden finden Sie einige Beispiele für häufige Eingabeaufforderungen und die Visualisierungen, die von Data Insights Agent verwendet werden, um auf diese Eingabeaufforderungen zu reagieren.

| Beispiel-Eingabeaufforderung | Erwartete Visualisierung |
| --- | --- |
| Gewinne anzeigen in [Monat] | Linie<p>Wenn Sie innerhalb eines bestimmten Zeitbereichs nach einem Trend oder einer Metrik fragen, wird standardmäßig eine Linienvisualisierung zurückgegeben. |
| Trend der Bestellungen in [Monat] | Linie |
| Umsatz nach Region anzeigen in [Monat] | Balken |
| Umsatzanteil nach Produktkategorie | Ringdiagramm |
| Bestellungen nach Wochentag von Januar bis Mai | Balken |
| Bestellungen nach Geschlecht anzeigen, von März bis Juni | Balken |
| Wie hoch ist der Gewinn aller SKUs von Februar bis Mai? | Balken |
| Umsatz nach Filialname in [Monat] | Balken |
| Was waren meine Top 10 SKUs nach Gewinn in [Monat]? | Balken |
| Anteil der Käufe nach Monat des Jahres | Ringdiagramm |
| Gesamtgewinn in [Monat] | Zusammenfassungszahl<p>Wenn Sie über einen bestimmten Zeitraum nach der „Gesamtsumme“ einer Metrik fragen, sollte eine Visualisierung der Zusammenfassungszahl zurückgegeben werden. |


## Best Practices bei der Eingabeaufforderung

Data Insights Agent verarbeitet den Kontext, der von jeder Benutzeraufforderung bereitgestellt wird, und versucht, mit der am besten geeigneten Visualisierung und den am besten geeigneten Komponenten in einer Freiformtabelle intelligent zu reagieren.

Die Antworten können je nach den in der Eingabeaufforderung verwendeten spezifischen Wörtern und Ausdrücken variieren, und leichte Sprachänderungen können zu unterschiedlichen Ergebnissen führen.

Um die besten Ergebnisse zu erzielen, beachten Sie die folgenden Richtlinien:

* **Spezifisch:** Sie genaue Begriffe ein, um die Antwort einzugrenzen. Es folgt ein Beispiel für eine bestimmte Eingabeaufforderung: „Umsatz des letzten Monats in Kalifornien“

* **Klare Metriken, Dimensionen und Segmente verwenden:** Durch das Hinzufügen spezifischer Metriken (z. B. „Umsatz„), Dimensionen (z. B. „Website-Name„), Segmente (z. B. &quot;iPhone-Benutzer„) und Datumsbereiche (z. B. „Letzte drei Monate„) kann Data Insights Agent sich auf die richtigen Daten konzentrieren.

* **Direkte Fragen stellen:** Das direkte Formulieren von Fragen erleichtert Data Insights Agent die Bereitstellung klarer, relevanter Erkenntnisse. Im Folgenden finden Sie ein Beispiel für eine direkte Frage in einer Eingabeaufforderung: „Wie hoch ist der durchschnittliche Umsatz nach Produktkategorie in diesem Jahr?“

Sehen Sie sich die folgende Tabelle mit Beispielbegriffen und -ausdrücken an, die Sie in Eingabeaufforderungen mit Data Insights Agent verwenden können, zusammen mit den Antworttypen, die Sie erwarten können.

Diese Beispiele sollen Ihnen dabei helfen, sich mit der Frage vertraut zu machen, wie bestimmte Wörter oder Strukturen die Ausgabe des Data Insight-Agenten beeinflussen können, um präzisere und wertvollere Einblicke zu ermöglichen. Data Insights Agent verwendet generative KI, sodass Visualisierungen oder ausgewählte Daten über ähnliche Eingabeaufforderungen hinweg leicht variieren können.

| Gewünschtes Ergebnis | Beispielbegriffe und Ausdrücke |
| --- | --- |
| Visualisierung der Zusammenfassungszahl | <ul><li>Gesamt</li></ul> |
| Vergleichen von Komponenten | <ul><li>Vergleichen</li><li>VS</li><li>Kontrast</li><li>Week-to-Week</li><li>Monat-zu-Monat</li><li>Quartalsvergleich</li><li>Year-over-Year</li></ul> |
| Ringvisualisierung | <ul><li>Verhältnis</li><li>Anteil von</li><li>Verteilung</li><li>Prozent</li><li>Beitrag</li><li>Teil</li><li>Teile</li></ul> |
| Linienvisualisierung | <ul><li>Trend</li><li>[Metrik] in [Zeitbereich]</li></ul> |
| Balkenvisualisierung | <ul><li>[Metrik] von [Dimension]</li></ul> |

<!--

## Beta testing expectations and requested feedback

After posing each question, carefully review the assistant's provided answer. It's crucial to evaluate the generated visualizations comprehensively before providing feedback. 

Consider the following when evaluating a response from Data Insights Agent: 

* Chat rail response or template: Evaluate the textual response provided. Is the response appropriate given the context of your prompt? 

* Visualization/chart: Evaluate the visualization. Is it the appropriate or expected visualization for your question, or would you have expected a different visualization?  

* Freeform table: Evaluate the freeform table. Is the freeform table data correct? Is it breaking down data where requested? Are the applied segments those that you requested or expected? 

* Error Message / Out-of-Scope: If a generic error message is given stating the question is out of scope, provide feedback on whether you think the out-of-scope message is appropriate, given your prompt. Was your prompt actually in scope? 

**For every response, give a thumbs up or thumbs down, based on the response.**

Following the thumbs up or thumbs down selection, please make a selection for the relevant multi-select feedback boxes. If you want to provide additional feedback, add notes in the open text box.

## Questions and Contact

* Send questions and feedback in the Beta Slack channel: #data-insights-agent-in-cja-beta

-->

