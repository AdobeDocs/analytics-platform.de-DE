---
description: Stellen von Fragen zur Datenanalyse an Customer Journey Analytics – Dokumentation
title: Visualisieren von Daten mit dem Data Insights Agent in Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: e4b7f1da451a7ec9171fbb623e0e79e916827fd8
workflow-type: tm+mt
source-wordcount: '2489'
ht-degree: 93%

---

# Visualisieren von Daten mit dem Data Insights Agent

>[!AVAILABILITY]
>
>Data Insights Agent steht berechtigten Kundinnen und Kunden für eine begrenzte Zeit zur Verfügung. Der Zugriff auf Data Insights Agent endet am 30. November 2025. Wenn Sie Data Insights Agent ohne Unterbrechung weiter verwenden möchten, wenden Sie sich an Ihr Adobe-Accountteam, um mehr über die Lizenzierung von Data Insights Agent zu erfahren.

Data Insights Agent, auf den über den [KI-Assistenten](/help/ai-assistant.md) in Customer Journey Analytics zugegriffen werden kann, ist ein auf generativer KI basierender Konversationsagent, der Fragen zu Ihren Daten schnell und effizient beantwortet. Er erstellt relevante Visualisierungen in Analysis Workspace mithilfe von Komponenten aus Ihrer Datenansicht und unter Verwendung Ihrer tatsächlichen Daten.

Die Verwendung von Data Insights Agent zur Beantwortung datenorientierter Fragen in Analysis Workspace kann unzählige Stunden einsparen, die Sie andernfalls möglicherweise damit verbringen würden, manuell Visualisierungen in Analysis Workspace zu erstellen und sich mit Ihren Datenansichtskomponenten vertraut zu machen.

![Data Insights Agent im KI-Assistenten](assets/cja-ai-asst-da.gif)

## Enthaltene und nicht enthaltene Funktionen

| Funktion | Enthalten | Nicht enthalten |
| --- | --- | --- |
| **Visualisierungstypen** | <ul><li>Linie</li><li>Mehrliniendiagramm</li><li>Freiformtabelle</li><li>Balken</li><li>Ringdiagramm</li><li>Zusammenfassungszahl</li></ul> | <ul><li>Fluss</li><li>Fallout</li><li>Kohortentabelle</li><li>Bereich, Bereich gestapelt</li><li>Balken gestapelt</li><li>Bullet</li><li>Kombination</li><li>Histogramm</li><li>Horizontalbalken, Horizontalbalken gestapelt</li><li>Zusammenfassung einer Schlüsselmetrik</li><li>Streuung</li><li>Zusammenfassende Änderung</li><li>Text</li><li>Baumkarte</li><li>Venn</li><li>Geführte Analyse: Aktives Wachstum, Konversions-Trends, Interaktion, Wirkung der ersten Verwendung, Häufigkeit, Trichter, Nettowachstum, Auswirkungen der Version, Bindung, Timeline, Trends</li></ul> |
| **Workspace-Aktionen und Funktionen des Agents** | <ul><li>Erstellen und Aktualisieren von Visualisierungen<p>Erstellt eine Freiformtabelle und eine dazugehörige Visualisierung (z. B. Linie, Balken, Ringdiagramm usw.).<p>Beispiel: *Wie hoch ist der Gewinn für alle SKUs von Februar bis Mai?*</p></li><li>Stellen von Folgefragen<p>Antworten Sie auf einen Prompt im Kontext aller vorherigen Prompts. Zum Beispiel:</p> <ul><li>Prompt 1: *Trendereignisse aus März.*</li><li>Prompt 2: *Zeig mir stattdessen die Daten von März bis April*</li></ul> </li><li>Erkennung eines nicht enthaltenen Prompts<p>Wenn Sie einen nicht enthaltenen Prompt übermitteln, z. B. *Dieses Projekt exportieren*, teilt Data Insights Agent Ihnen mit, dass die Frage außerhalb des Umfangs liegt.</p></li></ul> | <ul><li>Freigeben</li><li>Exportieren</li><li>Herunterladen</li><li>Verwalten von Benutzervoreinstellungen</li><li>Verwalten der Datenansicht</li><li>Analytics Dashboards-App</li><li>Attribution</li><li>Inline-Zusammenfassung oder -Antwort<p>Data Insights Agent kann in der Chat-Leiste nicht mit einer zusammenfassenden Antwort auf einen Prompt antworten. Beispiele für Prompts außerhalb des Umfangs sind: *Fasse mir die Erkenntnisse meines letzten Prompts zusammen* und *Fasse die Highlights aus der Linienvisualisierung zusammen.*</p></li></ul> |
| **Klärende Fragen** | Wenn Sie eine Frage stellen, die nicht ausreichend Kontext für eine Antwort von Data Insights Agent bietet oder zu generisch ist, antwortet Data Insights Agent mit einer klärenden Frage oder empfohlenen Optionen. <p>Die folgenden klärenden Fragen sind Beispiele für komponentenbezogene Fragen:</p><ul><li>Metrik: *Welche „Umsatz“-Metrik meinten Sie?*</li><li>Dimension: *Auf welche der folgenden „Regionen“ möchten Sie sich konzentrieren?*</li><li>Segment: *Welches „Konto“-Segment sollte angewendet werden?*</li><li>Datumsbereich: *Meinten Sie mit „letztem Monat“ den letzten vollen Monat oder die letzten 30 Tage?*</li></ul><p>Die folgende klärende Frage ist ein Beispiel für eine Frage im Zusammenhang mit Dimensionselementen:</p> <ul><li>Welchen „Store-Namen“ meinten Sie? (Beispiel: Store #5274, Store #2949 usw.)</li></ul> | Klärende Fragen sind auf Komponenten und Dimensionselemente beschränkt. Data Insights Agent kann Elemente wie Datenansichten, Visualisierungen, Datengranularität, Vergleiche und den Umfang nicht weiter klären. Wenn keine klärenden Fragen verwendet werden können, antwortet der Agent standardmäßig mit dem, wonach Sie am wahrscheinlichsten fragen. Wenn er eine unerwartete Visualisierung oder Datengranularität zurückgibt, können Sie eine Folgefrage stellen oder die Visualisierung und die Daten anpassen. |
| **Datenverifizierbarkeit und -korrektheit** | Die Verifizierbarkeit und Korrektheit von Daten kann über die generierte Freiformtabelle und Datenvisualisierung bestätigt werden. <p>Wenn Sie Data Insights Agent beispielsweise nach *Trend-Bestellungen im letzten Monat* fragen, können Sie bestätigen, dass im neu generierten Panel, in der Datenvisualisierung und in der Freiformtabelle die richtige Metrik („Bestellungen“) und der richtige Datumsbereich („letzter Monat“) ausgewählt wurden. | Data Insights Agent informiert Sie nicht darüber, welche Komponenten oder Visualisierungen hinzugefügt wurden.</p> |
| **Feedback-Mechanismen** | <ul><li>Daumen hoch</li><li>Daumen runter</li><li>Markierung</li></ul> |  |


## Verwalten des Zugriffs auf den Data Insights Agent {#manage-access}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-enable-data-insights-data-view"
>title="Für Data Insights Agent aktivieren"
>abstract="Diese Option aktiviert diese Datenansicht für die Verwendung mit Data Insights Agent. Data Insights Agent ist ein auf generativer KI basierender Konversations-Agent, auf den in Customer Journey Analytics über den KI-Assistenten zugegriffen werden kann. So können Sie Daten schnell mit Text-Prompts analysieren. Er erstellt relevante Visualisierungen in Analysis Workspace mithilfe von Komponenten aus Ihrer Datenansicht und unter Verwendung Ihrer tatsächlichen Daten."

<!-- markdownlint-enable MD034 -->

Die folgenden Parameter regeln den Zugriff auf Data Insights Agent in Customer Journey Analytics:

* **Lösungsbasierter Zugriff**: Data Insights Agent steht allen Customer Journey Analytics-Kundinnen und -Kunden im Rahmen eines eingeschränkten Zugriffsprogramms bis zum 30. November 2025 zur Verfügung. Er ist nicht in Adobe Analytics verfügbar.

* **Zugriff auf vertraglicher Grundlage**: Wenn Sie den Data Insights Agent im KI-Assistenten nicht verwenden können, wenden Sie sich an die bzw. den Admin Ihrer Organisation oder das Adobe-Accountteam. Bevor Ihre Organisation Data Insights Agent verwenden kann, müssen Sie bestimmten rechtlichen Bedingungen im Zusammenhang mit generativer KI zustimmen.

* **Berechtigungen**: Die erforderlichen Berechtigungen müssen in der [!UICONTROL Adobe Admin Console] gewährt werden, bevor Benutzerinnen und Benutzer auf den Data Insights Agent zugreifen können.

  Zum Gewähren von Berechtigungen muss die oder der [Produktprofil-Admin](https://helpx.adobe.com/de/enterprise/using/manage-product-profiles.html) die folgenden Schritte in der [!UICONTROL Admin Console] ausführen:
   1. Wählen Sie in der **[!UICONTROL Admin Console]** die Registerkarte **[!UICONTROL Produkte]** aus, um die Seite **[!UICONTROL Alle Produkte und Services]** anzuzeigen.
   1. Wählen Sie **[!UICONTROL Customer Journey Analytics]** aus.
   1. Wählen Sie auf der Registerkarte **[!UICONTROL Produktprofile]** den Titel des Produktprofils aus, dem Zugriff auf [!UICONTROL KI-Assistent: Produktkenntnisse] gewährt werden soll.
   1. Wählen Sie im entsprechenden Produktprofil die Registerkarte **[!UICONTROL Berechtigungen]** aus.

      ![Registerkarte „Berechtigungen“ in der Admin Console](assets/ai-assistant-permissions-tab.png)

   1. Wählen Sie in der Zeile **[!UICONTROL Reporting-Tools]** der bereitgestellten Tabelle das Bearbeitungssymbol ![Bearbeiten](/help/assets/icons/Edit.svg) aus.
   1. Scrollen Sie zu oder suchen Sie nach **[!UICONTROL KI-Assistent: Produktkenntnisse]** und wählen Sie dann das Plussymbol ![Hinzufügen](/help/assets/icons/AddCircle.svg) neben dieser Berechtigung aus.
   1. Scrollen Sie zu oder suchen Sie nach **[!UICONTROL Data Insights Agent]** und wählen Sie dann das Pluszeichen ![AddCircle](/help/assets/icons/AddCircle.svg) neben dieser Berechtigung aus.

      Die Berechtigung **[!UICONTROL KI-Assistent: Produktwissen]** und die Berechtigung **[!UICONTROL Data Insights Agent]** werden der Spalte **[!UICONTROL Enthaltene Berechtigungselemente]** hinzugefügt.

      ![Hinzufügen einer Berechtigung](assets/ai-assistant-permissions.png)

   1. Wählen Sie **[!UICONTROL Speichern]** aus, um die Berechtigungen zu speichern.

  Weitere Informationen zur Zugriffssteuerung finden Sie unter [Zugriffssteuerung](/help/technotes/access-control.md#access-control).

* **Zugriff auf Datenansicht**: Datenansichten müssen für Data Insights Agent aktiviert sein.

  >[!IMPORTANT]
  >
  >Beachten Sie beim Aktivieren von Datenansichten Folgendes:
  >* Sie können maximal 50 Datenansichten pro IMS-Organisation aktivieren. Wenn Sie für ein Unternehmen mehr als 50 Datenansichten für alle Produktprofile aktivieren, verwendet Data Insights Agent die 50 am häufigsten verwendeten Datenansichten.
  >* Die Data Insights Agent kann die enthaltenen Datenansichten an einem Tag referenzieren, an dem Sie sie aktivieren.

  So aktivieren Sie Datenansichten für Data Insights Agent:

   1. Wählen Sie in Customer Journey Analytics **[!UICONTROL Daten-Management]** > **[!UICONTROL Datenansichten]**.

   1. Wählen Sie eine oder mehrere Datenansichten aus, die Sie für Data Insights Agent aktivieren möchten, und wählen Sie dann **[!UICONTROL Für Data Insights Agent aktivieren]**.

      ![Aktivieren von Datenansichten für Data Insights Agent](assets/data-view-enable-dia.png)

  So zeigen Sie die Anzahl der Datenansichten an, die für Data Insights Agent in Ihrer IMS-Organisation aktiviert sind:

   1. Wählen Sie in Customer Journey Analytics **[!UICONTROL Daten-Management]** > **[!UICONTROL Datenansichten]**.

   1. Wählen Sie das Informationssymbol oben in der Spalte **[!UICONTROL Data Insights Agent]** aus.

      ![Infosymbol zu Data Insights Agent](assets/data-insights-agent-tooltip.png)

## Zugreifen auf den Data Insights Agent im KI-Assistenten

1. Gehen Sie zu [experience.adobe.com](https://experience.adobe.com/) und melden Sie sich mit Ihrer Adobe ID an.

2. Wählen Sie **Customer Journey Analytics** auf der Experience Cloud-Startseite aus.

3. Wählen Sie im Banner oben auf der Projektseite die Option **[!UICONTROL Leeres Projekt]** aus, um ein neues leeres Projekt zu öffnen.

4. Stellen Sie sicher, dass es sich bei der für das Panel ausgewählten Datenansicht um eine Datenansicht handelt, die für den Data Insights Agent aktiviert wurde, wie unter [Verwalten des Zugriffs auf Data Insights Agent in Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics) beschrieben.

5. Wählen Sie oben rechts auf der Seite das Chat-Symbol für den KI-Assistenten aus.

   Wenn das Chat-Symbol nicht angezeigt wird, wenden Sie sich an Ihr Admin-Team, damit es die folgenden Funktionen in der Admin Console aktivieren kann:

   * Reporting-Tools: **[!UICONTROL KI-Assistent: Produktkenntnisse]**

   * Tools für die Datenansicht: **[!UICONTROL Data Insights Agent]**

   Weitere Informationen finden Sie unter [Verwalten des Zugriffs auf Data Insights Agent in Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics).

   ![Symbol „KI-Assistent“](/help/assets/ai-asst-icon.png)

6. Stellen Sie unten auf der Seite im Dialogfeld **[!UICONTROL Fragen zu Customer Journey Analytics]** eine Frage zur Datenvisualisierung mit dem Data Insights Agent.

   Weitere Informationen erhalten Sie in den folgenden Beispielen.

### Beispiel 1

Angenommen, Sie sind an den Bestellungen interessiert, die Ihr Unternehmen im Juli erhalten hat.

**Prompt:** Geben Sie *Bestellungen im Juli als Trend anzeigen* ein.

![KI-Prompt](/help/assets/ai-asst-prompt1.png)

**Antwort:** Der Data Insights Agent sammelt Erkenntnisse, indem er die Daten in der Datenansicht durchsieht, einschließlich Metriken und Komponenten. Dadurch wird der Prompt in die richtigen Dimensionen und Metriken innerhalb des Datenbereichs übersetzt.

Wie Sie sehen können, wurden automatisch ein Liniendiagramm und eine Freiformtabelle generiert, um die Bestellungen für den Monat Juli anzuzeigen.

![Antwort auf Prompt – Liniendiagramm und Freiformtabelle](/help/assets/ai-asst-result.png)

### Beispiel 2

Als Nächstes möchten Sie den Umsatz nach Region vergleichen.

**Prompt:** Geben Sie im Prompt-Fenster *Umsatz nach Region anzeigen* ein.

**Antwort:** Der Data Insights Agent versteht auf intelligente Weise, dass mit „Region“ die „Kundenregion“ gemeint ist. Es wird ein Balkendiagramm erstellt, das den Umsatz nach Region am besten zeigt:

![Balkendiagramm](/help/assets/ai-asst-result2.png)

### Beispiel 3

Als Nächstes möchten Sie nicht nur den Umsatz nach Region nachvollziehen, sondern sich auch Daten für den Gewinn nach Region anzeigen lassen. Anstatt den vorherigen Prompt zu wiederholen, können Sie den Data Insights Agent bitten, die letzte Visualisierung und Freiformtabelle zu aktualisieren.

**Prompt:** Geben Sie im Prompt-Fenster *Gewinn hinzufügen* ein.

**Antwort:** Das **[!UICONTROL Balkendiagramm]** liefert weiterhin die prägnanteste Antwort, aber die Gewinnmetrik wurde als Spalte in der Freiformtabelle hinzugefügt:

![Balkendiagramm](/help/assets/ai-asst-result4.png)

### Beispiel 4

Schließlich möchten Sie sich noch den Umsatz nach Produktkategorie ansehen.

**Prompt:** Geben Sie im Prompt-Fenster *Anteiligen Umsatz nach Produktkategorie* ein.

**Antwort** Auch hier wählt der Data Insights Agent die am besten geeignete Visualisierung aus (in diesem Fall eine Visualisierung vom Typ **[!UICONTROL Ringdiagramm]**), um die Frage zu beantworten.

![Ringdiagramm](/help/assets/ai-asst-result3.png)

## Zugreifen auf Data Insights Agent über Experience Cloud-Anwendungen hinweg

Adobe Experience Platform Agent Orchestrator ermöglicht den Zugriff auf die Funktionen von Data Insights Agent in mehreren Adobe Experience Cloud-Anwendungen, z. B. Adobe Journey Optimizer und Real-Time CDP.

Agent Orchestrator interpretiert Ihre Anfrage, bestimmt, welche spezialisierten Agents benötigt werden, und orchestriert sie, um die richtige Antwort bereitzustellen. Außerdem wird der Kontext über Multi-Turn-Interaktionen hinweg verfolgt, sodass Sie auf natürliche Weise auf früheren Abfragen aufbauen können.

Weitere Informationen finden Sie unter [Adobe Experience Platform Agent Orchestrator](http://www.adobe.com/go/agent-orchestrator-home_de).

## Beispielhafte Prompts zur Datenvisualisierung

Im Folgenden finden Sie einige Beispiele für gängige Prompts und die vom Data Insights Agent verwendeten Visualisierungen, um auf diese Prompts zu reagieren.

| Beispiel-Prompt | Erwartete Visualisierung |
| --- | --- |
| Gewinne im [Monat] anzeigen | Linie<p>Wenn Sie innerhalb eines bestimmten Zeitbereichs nach einem Trend oder einer Metrik fragen, wird standardmäßig eine Linienvisualisierung zurückgegeben. |
| Bestellungen im [Monat] als Trend anzeigen | Linie |
| Umsatz nach Region im [Monat] anzeigen | Balken |
| Anteiliger Umsatz nach Produktkategorie | Ringdiagramm |
| Bestellungen nach Wochentag von Januar bis Mai | Balken |
| Bestellungen nach Geschlecht von März bis Juni anzeigen | Balken |
| Wie hoch ist der Gewinn für alle SKUs von Februar bis Mai? | Balken |
| Umsatz nach Filialnamen im [Monat] | Balken |
| Was waren meine 10 besten SKUs nach Gewinn im [Monat]? | Balken |
| Anteilige Käufe nach Monat des Jahres | Ringdiagramm |
| Gesamtgewinn im [Monat] | Zusammenfassungszahl<p>Wenn Sie über einen bestimmten Zeitraum nach der „Gesamtsumme“ einer Metrik fragen, sollte eine Visualisierung vom Typ „Zusammenfassungszahl“ zurückgegeben werden. |


## Best Practices für die Prompt-Erstellung

Der Data Insights Agent verarbeitet den Kontext, der bei jedem Benutzer-Prompt bereitgestellt wird, und versucht, intelligent mit der am besten geeigneten Visualisierung und den am besten geeigneten Komponenten in einer Freiformtabelle zu antworten.

Die Antworten können je nach den im Prompt verwendeten Wörtern und Ausdrücken variieren. Geringfügige sprachliche Änderungen können also zu unterschiedlichen Ergebnissen führen.

Um die besten Ergebnisse zu erzielen, beachten Sie die folgenden Richtlinien:

* **Seien Sie spezifisch:** Wählen Sie genaue Begriffe, um die Antwort einzugrenzen. Dies ist ein Beispiel für einen spezifischen Prompt: „Umsatz des letzten Monats in Kalifornien“.

* **Verwenden Sie klare Metriken, Dimensionen und Segmente:** Durch das Hinzufügen spezifischer Metriken (z. B. „Umsatz“), Dimensionen (z. B. „Website-Name“), Segmente (z. B. „iPhone-Benutzende“) und Datumsbereiche (z. B. „letzte drei Monate“) kann sich der Data Insights Agent auf die richtigen Daten konzentrieren.

* **Stellen Sie direkte Fragen:** Durch direkt formulierte Fragen ist der Data Insights Agent besser in der Lage, klarere, relevantere Erkenntnisse zu liefern. Dies ist ein Beispiel für eine direkte Frage in einem Prompt: „Wie hoch ist der durchschnittliche Umsatz nach Produktkategorie in diesem Jahr?“

Sehen Sie sich die folgende Tabelle mit beispielhaften Begriffen und Ausdrücken an, die Sie in Prompts mit dem Data Insights Agent verwenden können, sowie die zu erwartenden Antworttypen.

Diese Beispiele sollen Ihnen dabei helfen, sich damit vertraut zu machen, wie bestimmte Wörter oder Strukturen die Data Insight Agent-Ausgabe beeinflussen können, um präzisere und wertvollere Erkenntnisse sicherzustellen. Der Data Insights Agent nutzt generative KI, sodass Visualisierungen oder ausgewählte Daten bei ähnlichen Prompts geringfügig variieren können.

| Gewünschte Ausgabe | Beispiele für Begriffe und Ausdrücke |
| --- | --- |
| Visualisierung „Zusammenfassungszahl“ | <ul><li>Gesamt</li></ul> |
| Vergleichen von Komponenten | <ul><li>Vergleichen</li><li>vs.</li><li>Kontrast</li><li>Woche-zu-Woche</li><li>Monat-zu-Monat</li><li>Quartal-zu-Quartal</li><li>Jahr-zu-Jahr</li></ul> |
| Ringvisualisierung | <ul><li>Verhältnis</li><li>Anteil von</li><li>Verteilung</li><li>Prozent</li><li>Beitrag</li><li>Teil</li><li>Teile</li></ul> |
| Linienvisualisierung | <ul><li>Trend</li><li>[Metrik] in [Zeitraum]</li></ul> |
| Balkenvisualisierung | <ul><li>[Metrik] nach [Dimension]</li></ul> |

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


## Best Practices bei der Konfiguration

Im Folgenden finden Sie Best Practices für Ihre Customer Journey Analytics-Konfiguration (Datenansicht, berechnete Metriken, Segmente usw.), um sicherzustellen, dass der Data Insights Agent die richtigen Komponenten finden und sauberere Antworten zurückgeben kann, ohne Sie nach zusätzlichen Informationen fragen zu müssen.

* **Wägen Sie die benötigten Komponenten ab**. Fügen Sie nicht alle Felder Ihrer Datensätze als Metriken oder Dimensionskomponenten zu Ihrer Datenansicht hinzu. Insbesondere keine, die Sie mit Sicherheit nicht in Ihrer Analyse benötigen werden. Beschränken Sie sich jedoch nicht ausschließlich auf die Felder, die Sie für Ihre Analyse benötigen. Eine zu begrenzte Datenansicht schränkt die Flexibilität Ihrer Analyse und die Data Insights Agent-Funktionen ein.
* **Verwenden Sie immer klare Anzeigenamen**. Stellen Sie sicher, dass alle Felder, die Sie in Ihrer Datenansicht entweder als Metrik- oder Dimensionskomponente definieren, einen Anzeigenamen für die Komponente aufweisen. Der Prozess des Umbenennens von Feldern mit einem Anzeigenamen ist insbesondere für Felder aus Adobe Analytics-Quell-Connector-Datensätzen relevant. Diese Felder haben häufig keine benutzerfreundlichen und identifizierbaren Namen wie `eVar41` oder `prop25`.
* **Verwenden Sie eindeutige Namen**. Eindeutige Namen sind besonders relevant, wenn Sie dasselbe Feld sowohl als Metrik- als auch als Dimensionskomponente in Ihrer Datenansicht verwenden. Oder wenn Sie ein Feld in mehreren Komponenten desselben Typs verwenden (z. B. in zwei verschiedenen Metriken), die jeweils unterschiedliche Komponenteneinstellungen aufweisen.
* **Verwenden Sie eine Benennungskonvention für Komponenten**. Mit einer Benennungskonvention für Komponenten können Sie Komponenten gruppieren. Beispiel: **[!UICONTROL Bestellungen | Produkt]** und **[!UICONTROL Bestellungen | Kunde/Kundin]** kann zwischen verschiedenen Bestellmetriken unterscheiden, die möglicherweise in Ihren Daten vorhanden sind.
* **Verwenden Sie das Datenwörterbuch**. Fügen Sie eine Beschreibung und andere relevante Daten für Komponenten im Datenwörterbuch hinzu. Der Data Insight-Agent verwendet derzeit keine Beschreibung und Tags aus dem Datenwörterbuch, könnte dies aber in Zukunft tun.
* **Verwenden Sie genehmigte berechnete Metriken**. Sie müssen sich auf einen Prozess einigen, bei dem nur genehmigte berechnete Metriken als Komponenten in Ihrer Datenansicht verwendet werden, und die Verwendung experimenteller berechneter Metriken vermeiden.
* **Geben Sie erforderliche Segmente frei**. Stellen Sie sicher, dass Sie Segmente freigeben und Segmente sichtbar machen, die für Data Insights Agent-Prompts erforderlich sind.
* **Standardisieren Sie Komponentennamen in Datenansichten**. Wenn Sie dieselben Felder wie eine Komponente in mehreren Datenansichten verwenden, stellen Sie sicher, dass Sie einen einzigen Anzeigenamen und eine einzige Kennung für diese Komponente verwenden. Durch einen einzigen Namen und eine einzige Kennung kann der Data Insights-Agent Datenansichten wechseln, ohne den Kontext zu verlieren.

>[!MORELIKETHIS]
>
>[Einstellungen der Komponente](/help/data-views/component-settings/overview.md)
>>[Datenwörterbuch](/help/components/data-dictionary/data-dictionary-overview.md)
>>[Berechnete Metrik genehmigen](/help/components/calc-metrics/cm-workflow/cm-approving.md)
>>[Segmente freigeben](/help/components/segments/seg-share.md)
>
