---
description: Fragen zur Datenanalyse in der Dokumentation zu Customer Journey Analytics
title: Visualisieren von Daten mit dem Data Insights Agent in Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
hidefromtoc: true
hide: true
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: a9ad08ea053b1213ac98d3e77be3d4816c0999bf
workflow-type: tm+mt
source-wordcount: '1878'
ht-degree: 5%

---

# Visualisieren von Daten mit dem Data Insights Agent in Customer Journey Analytics

Der Data Insights Agent, Teil des KI-Assistenten in Customer Journey Analytics, ist ein generativer KI-Konversationsagent, der Fragen zu Ihren Daten schnell und effizient beantwortet. Er erstellt relevante Visualisierungen in Analysis Workspace mithilfe von Komponenten aus Ihrer Datenansicht und unter Verwendung Ihrer tatsächlichen Daten.

Wenn Sie den Data Insights-Agenten verwenden, um datenorientierte Fragen in Analysis Workspace zu beantworten, können Sie unzählige Stunden einsparen, die Sie andernfalls manuell für die Erstellung von Visualisierungen in Analysis Workspace und die Einarbeitung in Ihre Datenansichtskomponenten aufwenden müssten.

![Data Insights-Agent im KI-Assistenten](assets/cja-ai-asst-da.gif)

## Funktionen innerhalb und außerhalb des Projektumfangs für Beta

### Beta-Funktionen im Umfang

| Unterstützte Funktion | Beschreibung |
| --- | --- |
| **Erstellen und Aktualisieren von Visualisierungen** | Erzeugt eine Freiformtabelle und eine dazugehörige Visualisierung (z. B. Linie, Balken, Ringdiagramm usw.).<p>Beispiel: *Was ist der Gewinn für alle SKUs von Februar bis Mai?* |
| **Unterstützte Visualisierungstypen** | <ul><li>Linie</li><li>Mehrzeilig</li><li>Freiformtabelle</li><li>Balken</li><li>Ringdiagramm</li><li>Zusammenfassungszahl</li></ul> |
| **Out-of-Scope Prompt Detection** | Wenn Sie eine Eingabeaufforderung übermitteln, die außerhalb des Bereichs liegt, z. B. „Dieses Projekt exportieren“, antwortet der Data Insights-Agent, indem er Ihnen mitteilt, dass die Frage außerhalb des Bereichs liegt. |
| **Fragen klären** | Wenn Sie eine Frage stellen, die nicht genügend Kontext für den Data Insights-Agenten hat, um beantwortet zu werden, oder die zu generisch ist, antwortet der Data Insights-Agent mit einer klärenden Frage oder empfohlenen Optionen. Beispiele: <p>**Komponenten**<ul><li>Metrik: *Welche „Umsatz“-Metrik meinten Sie?*</li><li>Dimension: *Auf welche der folgenden „Regionen“ möchten Sie sich konzentrieren?*</li><li>Filter: *Welchen Filter „Konto“ wollten Sie anwenden?*</li><li>Datumsbereich: *Mit „letztem Monat“ meinen Sie den letzten vollen Monat oder die letzten 30 Tage?*</li></ul>**Dimension-Elemente**: Welchen „Store-Namen“ meinten Sie? (Beispiel: #5274, #2949 usw.) |
| **Multi-Turn** | Der Data Insights-Agent antwortet auf eine Eingabeaufforderung mit dem Kontext früherer Eingabeaufforderungen, sodass Benutzende Visualisierungen aktualisieren und Fragen stellen können. Beispiel: <ul><li>Eingabeaufforderung 1: *Trendereignisse ab März.*</li><li>Eingabeaufforderung 2: *Zeigen Sie mir stattdessen die Daten von März bis April*</li></ul> |
| **Verifizierbarkeit** | Die Datenverifizierbarkeit und -richtigkeit kann über die generierte Freiformtabelle und Datenvisualisierung bestätigt werden. Wenn ein(e) Benutzende(r) beispielsweise *Bestellungen im letzten Monat* fragt, können Sie bestätigen, dass im neu generierten Bedienfeld, in der Datenvisualisierung und in der Freiformtabelle die richtige Metrik („Bestellungen„) und der richtige Datumsbereich („letzter Monat„) ausgewählt wurden. |
| **Feedback** | <ul><li>Daumen hoch</li><li>Daumen runter</li><li>Markierung</li></ul> |

### Beta-Funktionen, die nicht im Umfang enthalten sind

| Nicht unterstützte Funktion | Beschreibung |
| --- | --- |
| **Inline-Zusammenfassung oder -Antwort** | Der Data Insights-Agent kann in der Chat-Leiste nicht mit einer zusammenfassenden Antwort auf eine Benutzeraufforderung antworten. Beispiel für Eingabeaufforderungen außerhalb des Bereichs:<ul><li>*Geben Sie mir eine Zusammenfassung der Erkenntnisse aus meiner letzten Eingabeaufforderung.*</li><li>*Fassen Sie die Highlights der Linienvisualisierung zusammen.*</li></ul> |
| **Fragen klären** | Die Klärung von Fragen beschränkt sich auf Komponenten und Dimensionselemente. Der Data Insights-Agent kann Dinge wie Datenansichten, Visualisierungen, Datengranularität, Vergleich und Umfang nicht verdeutlichen. Wenn Klärungsfragen nicht verwendet werden können, verwendet der Agent standardmäßig das, was Sie am wahrscheinlichsten anfordern. Wenn eine unerwartete Visualisierung oder Datengranularität zurückgegeben wird, können Sie die Funktion „Multi-Turn/Update“ verwenden, um die Visualisierung und die Daten anzupassen. |
| **Workspace-Aktionen/-Funktionen** | Der Data Insights-Agent kann für eine Benutzerin oder einen Benutzer in Workspace keine Aktionen ausführen, abgesehen von der Erstellung und Aktualisierung von Visualisierungen. Sie kann beispielsweise keine der folgenden Aktionen ausführen:<ul><li>Schaltflächen der kontextuellen Aktionsbenutzeroberfläche (zum Diagramm hinzufügen, neues Bedienfeld, neue Tabelle)</li><li>Freigeben</li><li>Exportieren</li><li>Download</li><li>Benutzereinstellungen verwalten</li><li>Kuratieren</li><li>Datenansicht verwalten</li><li>Analytics Dashboards App</li><li>Attribution</li></ul> |
| **Nicht unterstützte Visualisierungsarten** | <ul><li>Fluss</li><li>Fallout</li><li>Kohortentabelle</li><li>Bereich, Bereich gestapelt</li><li>Balken gestapelt</li><li>Bullet</li><li>Kombination</li><li>Histogramm</li><li>Horizontalbalken, Horizontalbalken gestapelt</li><li>Zusammenfassung einer Schlüsselmetrik</li><li>Streuung</li><li>Zusammenfassende Änderung</li><li>Text</li><li>Baumkarte</li><li>Venn</li></ul> |

## Verwalten des Zugriffs auf den Data Insights-Agenten in Customer Journey Analytics

Die folgenden Parameter regeln den Zugriff auf den Data Insights-Agenten in Customer Journey Analytics:

* **Lösungszugriff**: Der Data Insights Agent ist für Kunden von Customer Journey Analytics Prime und Ultimate verfügbar. Sie ist in Adobe Analytics nicht verfügbar.

* **Vertragszugriff**: Wenn Sie den Data Insights-Agenten im KI-Assistenten nicht verwenden können, wenden Sie sich an den Administrator Ihres Unternehmens oder den Adobe-Kontobeauftragten. Bevor Ihr Unternehmen den Data Insights Agent verwenden kann, müssen Sie bestimmten GenAI-bezogenen rechtlichen Bedingungen zustimmen.

* **Berechtigungen**: In der [!UICONTROL Adobe Admin Console] bestimmt die Berechtigung  Reporting-Tools **[!UICONTROL KI-Assistent]** Datenvisualisierung) den Zugriff auf dieses Tool. Sie als [Produktprofil-Admin](https://helpx.adobe.com/de/enterprise/using/manage-product-profiles.html) müssen diese Schritte in der [!UICONTROL Admin Console] ausführen:
   1. Navigieren Sie zu **[!UICONTROL Admin Console]** > **[!UICONTROL Produkte und Services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Produktprofile]**
   1. Wählen Sie den Titel des Produktprofils aus, für das Sie Zugriff auf [!UICONTROL KI-Assistent: Produktkenntnisse] gewähren möchten.
   1. Wählen Sie im entsprechenden Produktprofil die Option **[!UICONTROL Berechtigungen]** aus.
   1. Wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) aus, um **[!UICONTROL Reporting-Tools]** zu bearbeiten.
   1. Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) aus, um **KI-Assistent:** und **KI-Assistent: Datenanalyse** zu **[!UICONTROL Enthaltene Berechtigungselemente]** hinzuzufügen.

      ![Berechtigung hinzufügen](assets/ai-assistant-permissions.png).

   1. Wählen Sie **[!UICONTROL Speichern]** aus, um die Berechtigungen zu speichern.

Weitere Informationen finden Sie unter [Zugriffssteuerung](/help/technotes/access-control.md#access-control).

## Zugreifen auf den Data Insights-Agenten im KI-Assistenten

1. Gehen Sie zu [experience.adobe.com](https://experience.adobe.com/) und melden Sie sich mit Ihrer Adobe ID an.

2. Wählen Sie **Customer Journey Analytics** auf der Experience Cloud-Startseite aus.

3. Wählen Sie **[!UICONTROL Leeres Projekt]** im Banner oben auf der Projektseite aus, um ein neues leeres Projekt zu öffnen.

4. Stellen Sie sicher, dass es sich bei der für das Bedienfeld ausgewählten Datenansicht um dieselbe Datenansicht handelt, die für die Verwendung mit dem Data Insights Agent für Beta-Tests aktiviert wurde.

   Wenn Sie sich nicht sicher sind, wenden Sie sich an den Beta Slack-Kanal.

5. Wählen Sie oben rechts auf der Seite das Chat-Symbol für den KI-Assistenten aus.

   Wenn das Chat-Symbol nicht angezeigt wird, wenden Sie sich an Ihren Administrator, damit er die folgenden Funktionen in der Admin Console aktivieren kann:

   * **[!UICONTROL KI-Assistent: Produktkenntnisse]**

   * **[!UICONTROL KI-Assistent: Datenanalyse]**

   Weitere Informationen erhalten Admins unter [diese Anweisungen](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/access).

   ![KI-Assistenten-Symbol](/help/assets/ai-asst-icon.png)

6. Stellen **[!UICONTROL im Dialogfeld &quot;]** über Customer Journey Analytics&quot; unten auf der Seite mithilfe des Data Insights-Agenten eine Frage zur Datenvisualisierung.

   Weitere Informationen finden Sie in den folgenden Beispielen.

### Beispiel 1

Nehmen wir beispielsweise an, Sie sind an den Bestellungen interessiert, die Ihr Unternehmen im Juli erhalten hat.

**Eingabeaufforderung:** Geben Sie *„Trend der Bestellungen im Juli“ ein*

![KI-Eingabeaufforderung](/help/assets/ai-asst-prompt1.png)

**Antwort:** Der Data Insights-Agent sammelt Insights, indem er die Daten in der Datenansicht durchsucht, einschließlich der Metriken und Komponenten. Dadurch wird die Eingabeaufforderung in die richtigen Dimensionen und Metriken innerhalb des Datenbereichs übersetzt.

Wie Sie sehen können, wurden automatisch ein Liniendiagramm und eine Freiformtabelle generiert, um Bestellungen für Juli anzuzeigen.

![Antwort auf Eingabeaufforderung - Liniendiagramm und Freiformtabelle](/help/assets/ai-asst-result.png)

### Beispiel 2

Als Nächstes möchten Sie sehen, wie Ihr Umsatz nach Region verglichen wird.

**Prompt:** Geben Sie im Eingabeaufforderungsfenster *„Umsatz nach Region anzeigen“ ein*

**Antwort:** Der Data Insights-Agent versteht auf intelligente Weise, dass Sie unter „Region“ „Kundenregion“ verstehen. Es wird ein Balkendiagramm erstellt, das den Umsatz am besten nach Region zeigt:

![Balkendiagramm](/help/assets/ai-asst-result2.png)

### Beispiel 3

Als Nächstes möchten Sie nicht nur den Umsatz nach Region verstehen, sondern auch Daten für den Gewinn nach Region anzeigen. Anstatt die vorherige Eingabeaufforderung zu wiederholen, können Sie den Data Insights-Agenten bitten, die neueste Visualisierung und Freiformtabelle zu aktualisieren.

**Prompt:** Geben Sie im Eingabeaufforderungsfenster „Gewinn hinzufügen *ein*

**Antwort:** Das **[!UICONTROL Balkendiagramm]** bietet weiterhin die prägnanteste Antwort, aber die Gewinnmetrik wurde als Spalte in der Freiformtabelle hinzugefügt:

![Balkendiagramm](/help/assets/ai-asst-result4.png)

### Beispiel 4

Sehen wir uns abschließend den Umsatz nach Produktkategorie an.

**Eingabeaufforderung:** Geben Sie im Eingabeaufforderungsfenster *„Umsatzanteil nach Produktkategorie“ ein*

**Antwort:** Wieder wählt der Data Insights-Agent die am besten geeignete Visualisierung aus, in diesem Fall die **[!UICONTROL Ringdiagramm]**-Visualisierung, um die Frage zu beantworten.

![Ringdiagramm](/help/assets/ai-asst-result3.png)

## Eingabeaufforderungen zur Beispieldatenvisualisierung

Im Folgenden finden Sie einige Beispiele für häufige Eingabeaufforderungen und die Visualisierungen, die vom Data Insights-Agenten verwendet werden, um auf diese Eingabeaufforderungen zu reagieren.

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

Der Data Insights-Agent verarbeitet den von jeder Benutzeraufforderung bereitgestellten Kontext und versucht, mit der am besten geeigneten Visualisierung und den am besten geeigneten Komponenten in einer Freiformtabelle intelligent zu reagieren.

Die Antworten können je nach den in der Eingabeaufforderung verwendeten spezifischen Wörtern und Ausdrücken variieren, und leichte Sprachänderungen können zu unterschiedlichen Ergebnissen führen.

Um die besten Ergebnisse zu erzielen, beachten Sie die folgenden Richtlinien:

* Seien Sie spezifisch: Schließen Sie genaue Begriffe ein, um die Antwort einzugrenzen. Im Folgenden finden Sie ein Beispiel für eine bestimmte Eingabeaufforderung: „Umsatz des letzten Monats in Kalifornien“

* Klare Metriken und Filter verwenden: Durch das Hinzufügen spezifischer Metriken (z. B. „Umsatz„), Dimensionen (z. B. „Website-Name„), Filter (z. B. &quot;iPhone-Benutzer„) und Datumsbereiche (z. B. „Letzte drei Monate„) kann sich der Data Insights-Agent auf die richtigen Daten konzentrieren.

* Stellen Sie direkte Fragen: Die direkte Formulierung von Fragen erleichtert es dem Data Insights-Agenten, klare, relevante Einblicke zu liefern. Im Folgenden finden Sie ein Beispiel für eine direkte Frage in einer Eingabeaufforderung: „Wie hoch ist der durchschnittliche Umsatz nach Produktkategorie in diesem Jahr?“

Sehen Sie sich die folgende Tabelle mit Beispielbegriffen und -ausdrücken an, die Sie in Eingabeaufforderungen mit dem Data Insights Agent verwenden können, zusammen mit den Arten von Antworten, die Sie erwarten können.

Diese Beispiele sollen Ihnen dabei helfen, sich damit vertraut zu machen, wie bestimmte Wörter oder Strukturen die Ausgabe des Data Insight Agents beeinflussen können, und so präzisere und wertvollere Einblicke sicherstellen. Der Data Insights-Agent verwendet generative KI, sodass Visualisierungen oder ausgewählte Daten über ähnliche Eingabeaufforderungen hinweg leicht variieren können.

| Gewünschtes Ergebnis | Beispielbegriffe und Ausdrücke |
| --- | --- |
| Visualisierung der Zusammenfassungszahl | <ul><li>Gesamt</li></ul> |
| Vergleichen von Komponenten | <ul><li>Vergleichen</li><li>VS</li><li>Kontrast</li><li>Week-to-Week</li><li>Monat-zu-Monat</li><li>Quartalsvergleich</li><li>Year-over-Year</li></ul> |
| Ringvisualisierung | <ul><li>Verhältnis</li><li>Anteil von</li><li>Verteilung</li><li>Prozent</li><li>Beitrag</li><li>Teil</li><li>Teile</li></ul> |
| Linienvisualisierung | <ul><li>Trend</li><li>[Metrik] in [Zeitbereich]</li></ul> |
| Balkenvisualisierung | <ul><li>[Metrik] von [Dimension]</li></ul> |

## Erwartungen an Beta-Tests und angefordertes Feedback

Überprüfen Sie nach dem Stellen jeder Frage sorgfältig die Antwort des Assistenten. Es ist wichtig, die generierten Visualisierungen umfassend zu bewerten, bevor Sie Feedback geben.

Beachten Sie beim Auswerten einer Antwort des Data Insights-Agenten Folgendes:

* Antwort oder Vorlage der Chat-Leiste: Bewerten Sie die bereitgestellte textliche Antwort. Ist die Antwort im Kontext Ihrer Eingabeaufforderung angemessen?

* Visualisierung/Diagramm: Bewertung der Visualisierung. Ist es die geeignete oder erwartete Visualisierung für Ihre Frage, oder hätten Sie eine andere Visualisierung erwartet?

* Freiformtabelle : Bewerten Sie die Freiformtabelle. Sind die Daten der Freiformtabelle korrekt? Werden die Daten bei Bedarf aufgeschlüsselt? Sind die angewendeten Filter die von Ihnen angeforderten oder erwarteten?

* Fehlermeldung/Außerhalb des Bereichs: Wenn eine allgemeine Fehlermeldung angezeigt wird, die besagt, dass die Frage außerhalb des Bereichs liegt, geben Sie Feedback dazu, ob Sie der Meinung sind, dass die außerhalb des Bereichs liegende Nachricht angesichts Ihrer Eingabeaufforderung angemessen ist. War Ihre Eingabeaufforderung tatsächlich im Umfang?

**Geben Sie für jede Antwort je nach Antwort einen Daumen hoch oder einen Daumen runter.**

Nach der Auswahl der Daumen hoch oder Daumen runter treffen Sie bitte eine Auswahl für die entsprechenden Mehrfachauswahl-Feedback-Boxen. Wenn Sie zusätzliches Feedback geben möchten, fügen Sie im Textfeld Öffnen Anmerkungen hinzu.

## Fragen und Kontakt

* Senden Sie Fragen und Feedback über den Beta Slack-Kanal: #data-insights-agent-in-cja-beta
