---
description: Fragen zur Datenanalyse in der Customer Journey Analytics-Dokumentation
title: Datenanalyse-KI-Assistent in Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
hidefromtoc: true
hide: true
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: 20b578a6269aeaf54f6296b1f4337937887ecf05
workflow-type: tm+mt
source-wordcount: '1637'
ht-degree: 3%

---

# Die Datenvisualisierung ist jetzt im KI-Assistenten in CJA verfügbar

Der KI-Assistent in Customer Journey Analytics (CJA) ist ein Agent für generative KI-Unterhaltungen, mit dem Sie Fragen zu Ihren Analysis Workspace-Daten in CJA schneller und effizienter beantworten können.

Wenn Sie eine Frage zur Datenvisualisierung stellen, scannt der KI-Assistent alle Komponenten in Ihrer Datenansicht, einschließlich der verschiedenen Arten von Metriken und Komponenten, und übersetzt Ihre Eingabeaufforderung in die richtige Dimension, Metrik und den richtigen Datumsbereich für Ihre Analyse. Anstatt sich mit den Komponenten der Datenansicht vertraut machen zu müssen und diese Komponenten dann in der besten Kombination zur Beantwortung Ihrer Frage per Drag-and-Drop abzulegen, können Sie die Frage einfach in den KI-Assistenten eingeben.

![Datenanalyse-KI-Assistent](assets/cja-ai-asst-da.gif)

## Funktionen innerhalb und außerhalb des Projektumfangs für die Alpha-Version

### Alpha-Funktionen im Umfang

| Unterstützte Funktion | Beschreibung |
| --- | --- |
| **Erstellen und Aktualisieren von Visualisierungen** | Erstellt eine Freiformtabelle und zugehörige Visualisierungen (z. B. Linie, Balken, Ringdiagramm usw.).<p>Beispiel: *Was ist der Gewinn für alle SKUs von Februar bis Mai?* |
| **Unterstützte Visualisierungstypen** | <ul><li>Linie</li><li>Mehrzeilig</li><li>Freiform</li><li>Balken</li><li>Ringdiagramm</li><li>Zusammenfassungszahl</li></ul> |
| **Out-of-Scope Prompt Detection** | Wenn Sie eine Eingabeaufforderung übermitteln, die außerhalb des Bereichs liegt, z. B. „Dieses Projekt exportieren“, antwortet der Assistent, indem er Ihnen mitteilt, dass die Frage außerhalb des Bereichs liegt. |
| **Fragen klären** | Wenn Sie eine Frage stellen, die nicht genügend Kontext für die Antwort des KI-Assistenten hat oder zu generisch ist, antwortet der KI-Assistent mit einer klärenden Frage und/oder vorgeschlagenen Optionen. Beispiele: <p>**Komponenten**<ul><li>Metrik: *Welche „Umsatz“-Metrik meinten Sie?*</li><li>Dimension: *Auf welche der folgenden „Regionen“ möchten Sie sich konzentrieren?*</li><li>Filter: *Welchen Filter „Konto“ wollten Sie anwenden?*</li><li>Datumsbereich: *Mit „letztem Monat“ meinen Sie den letzten vollen Monat oder die letzten 30 Tage?*</li></ul>**Dimensionen-Elemente**: Welchen „Store-Namen“ meinten Sie? (z. B. #5274, #2949 usw.) |
| **Multi-Turn** | Der KI-Assistent antwortet auf eine Eingabeaufforderung mit dem Kontext der vorherigen Eingabeaufforderung(en), sodass Benutzende Visualisierungen aktualisieren und Anschlussfragen stellen können.Beispiel: <ul><li>Eingabeaufforderung 1: *Trendereignisse ab März.*</li><li>Eingabeaufforderung 2: *Zeigen Sie mir stattdessen die Daten von März bis April*</li></ul> |
| **Verifizierbarkeit** | Die Datenverifizierbarkeit und -richtigkeit kann über die generierte Freiformtabelle und Datenvisualisierung bestätigt werden. Wenn ein(e) Benutzende(r) beispielsweise *Trend-Bestellungen im letzten Monat* fragt, können Sie bestätigen, dass im neu generierten Bedienfeld, in der Datenvisualisierung und in der Freiformtabelle die richtige Metrik („Bestellungen„) und der richtige Datumsbereich („letzter Monat„) ausgewählt wurden. |
| **Feedback** | <ul><li>Daumen hoch</li><li>Daumen runter</li><li>Markierung</li></ul> |

### Alpha-Funktionen außerhalb des Projektumfangs

| Nicht unterstützte Funktion | Beschreibung |
| --- | --- |
| **Inline-Zusammenfassung oder Antwort** | Der KI-Assistent kann in der Chat-Leiste nicht mit einer zusammenfassenden Antwort auf eine Benutzeraufforderung antworten.Beispiel Eingabeaufforderungen außerhalb des Bereichs:<ul><li>*Geben Sie mir eine Zusammenfassung der Erkenntnisse aus meiner letzten Eingabeaufforderung.*</li><li>*Fassen Sie die Highlights der Linienvisualisierung zusammen.*</li></ul> |
| **Fragen klären** | Die Klärung von Fragen beschränkt sich auf Komponenten und Dimensionselemente. Der KI-Assistent kann keine Datenansichten, Visualisierungen, Datengranularität, Vergleiche, den Umfang usw. klären. Ohne Klärung der Fragen ist der Assistent auf das zurückgekehrt, was Sie am ehesten verlangen. Wenn eine unerwartete Visualisierung oder Datengranularität zurückgegeben wird, können Sie die Visualisierung und die Daten dann mit der Funktion „Multi-Turn/Update“ anpassen. |
| **Workspace-Aktionen/-Funktionen** | Der KI-Assistent kann für einen Benutzer in Workspace keine Aktionen ausführen, abgesehen von der Erstellung und Aktualisierung von Visualisierungen. Sie kann beispielsweise Folgendes nicht tun:<ul><li>Schaltflächen der kontextuellen Aktionsbenutzeroberfläche (zum Diagramm hinzufügen, neues Bedienfeld, neue Tabelle)</li><li>Freigeben</li><li>Exportieren</li><li>Download</li><li>Benutzereinstellungen verwalten</li><li>Kuratieren</li><li>Datenansicht verwalten</li><li>Analytics Dashboards App</li><li>Attribution</li></ul> |
| **Nicht unterstützte Visualisierungsarten** | <ul><li>Fluss</li><li>Fallout</li><li>Kohortentabelle</li><li>Bereich, Bereich gestapelt</li><li>Balken gestapelt</li><li>Horizontales Säulendiagramm</li><li>Kombination</li><li>Histogramm</li><li>Horizontalbalken, Horizontalbalken gestapelt</li><li>Zusammenfassung einer Schlüsselmetrik</li><li>Streuung</li><li>Zusammenfassende Änderung</li><li>Text</li><li>Treemap</li><li>Venn</li></ul> |

<!---## Feature access in the Customer Journey Analytics UI

[Do we even need this section for the Alpha?]

The following parameters govern access to Data visualization in AI Assistant:

* **Solution access**: Data visualization in AI Assistant is available for Customer Journey Analytics Prime and Ultimate customers. It is not available in Adobe Analytics. 

It is also available in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP and additional Experience Platform apps.

* **Contractual access**: If you are not able to use AI Assistant, please contact your organization's administrator or Adobe Account Representative. Before your organization can use Data visualization in AI Assistant, your must agree to certain GenAI-related legal terms.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL AI Assistant: Data visualization]** permission determines access to this tool. A [product profile admin](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) needs to follow these steps in the [!UICONTROL Admin Console]:
   1. Navigate to **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Select the title of the product profile for which you want to provide access to [!UICONTROL AI Assistant: Product Knowledge].
   1. In the specific product profile, select **[!UICONTROL Permissions]**.
   1. Select ![Edit](/help/assets/icons/Edit.svg) to edit **[!UICONTROL Reporting Tools]**.
   1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) to add **AI Assistant: Data visualization** to **[!UICONTROL Included permission items]**.
   
      ![Add permission](assets/ai-assistant-permissions.png).

   1. Select **[!UICONTROL Save]** to save the permissions.

See [Access control](/help/technotes/access-control.md#access-control) for more information.--->

## Zugreifen auf und Verwenden der Datenvisualisierung im KI-Assistenten

1. Navigieren Sie zu [experience.adobe.com](https://experience.adobe.com/) und melden Sie sich mit Ihrer Adobe ID an.

2. **Customer Journey Analytics** von Experience Cloud Home auswählen

3. Klicken Sie **[!UICONTROL Leeres Projekt]** im Banner oben auf der Seite „Projekte“, um ein neues leeres Projekt zu öffnen.

4. Stellen Sie sicher, dass die ausgewählte Datenansicht für das Bedienfeld die Datenansicht ist, die für die Verwendung des KI-Assistenten für Alpha-Tests aktiviert wurde (kontaktieren Sie den Alpha-Slack-Kanal, wenn Sie sich nicht sicher sind)

5. Klicken Sie oben rechts auf das Chat-Symbol des KI-Assistenten. Hinweis: Wenn das Chat-Symbol oben rechts nicht angezeigt wird, wenden Sie sich bitte an Ihren Administrator und lassen Sie ihn [diese Anweisungen) ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/ai-assistant#feature-access), um „KI-Assistent: Produktkenntnisse“ und „KI-Assistent: Datenanalyse“ in Admin Console zu aktivieren.

   ![KI-Assistenten-Symbol](/help/assets/ai-asst-icon.png)

6. Customer Journey Analytics Stellen Sie im Dialogfeld **[!UICONTROL Fragen zum]**&quot; unten im KI-Assistenten eine Frage zur Datenvisualisierung.

### Beispiel 1

Nehmen wir beispielsweise an, Sie sind an den Bestellungen interessiert, die Ihr Unternehmen im Juli erhalten hat.

1. Geben Sie *„Trend der Bestellungen im Juli“ ein*

   ![KI-Eingabeaufforderung](/help/assets/ai-asst-prompt1.png)

2. Der KI-Assistent sammelt jetzt Erkenntnisse, indem er die Daten in der Datenansicht durchsucht, einschließlich der Metriken und Komponenten. Dabei wird die Eingabeaufforderung in die richtigen Dimensionen, Metriken und den richtigen Datenbereich übersetzt.

   Wie Sie sehen können, hat es automatisch ein Liniendiagramm und eine Freiformtabelle generiert, die Bestellungen für Juli anzeigt.

   ![Antwort auf Eingabeaufforderung - Liniendiagramm und Freiformtabelle](/help/assets/ai-asst-result.png)

### Beispiel 2

Als Nächstes möchten Sie sehen, wie Ihr Umsatz nach Region verglichen wird.

1. Geben Sie im Eingabeaufforderungsfenster *„Umsatz nach Region anzeigen“ ein*

2. Der KI-Assistent versteht intelligent, dass man mit „Region“ „Kundenregion“ meint. Es wird ein Balkendiagramm erstellt, das den Umsatz am besten nach Region zeigt:

   ![Balkendiagramm](/help/assets/ai-asst-result2.png)

### Beispiel 3

Als Nächstes möchten Sie nicht nur den Umsatz nach Region verstehen, sondern auch Daten für den Gewinn nach Region anzeigen. Anstatt die letzte Eingabeaufforderung erneut eingeben zu müssen, können Sie den KI-Assistenten bitten, die neueste Visualisierung und Freiformtabelle zu aktualisieren.

1. Geben Sie im Eingabeaufforderungsfenster „Gewinn hinzufügen *ein*

2. Das **[!UICONTROL Balkendiagramm]** bietet weiterhin die prägnanteste Antwort, aber die Gewinnmetrik wurde als Spalte in der Freiformtabelle hinzugefügt:

   ![Balkendiagramm](/help/assets/ai-asst-result4.png)

### Beispiel 4

Zum Schluss sehen wir uns noch den Umsatz nach Produktkategorien an.

1. Geben Sie im Eingabeaufforderungsfenster &quot;*des Umsatzes nach Produktkategorie“ ein.*

2. Auch hier wählt die Datenvisualisierung im KI-Assistenten die am besten geeignete Visualisierung aus, in diesem Fall die **[!UICONTROL Ringdiagramm]**-Visualisierung, um die Frage zu beantworten.

   ![Ringdiagramm](/help/assets/ai-asst-result3.png)

## Eingabeaufforderungen zur Beispieldatenvisualisierung

Im Folgenden finden Sie einige Beispiele für häufige Eingabeaufforderungen und welche Visualisierung der KI-Assistent verwendet, um auf diese Eingabeaufforderungen zu reagieren.

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

Der KI-Assistent verarbeitet den von jeder Benutzeraufforderung bereitgestellten Kontext und versucht, mit der am besten geeigneten Visualisierung sowie Komponenten in einer Freiformtabelle intelligent zu reagieren. Die Antwort des KI-Assistenten kann jedoch je nach den in einer Eingabeaufforderung verwendeten spezifischen Wörtern und Ausdrücken variieren, sodass leichte Sprachänderungen zu unterschiedlichen Ergebnissen führen können. So machen Sie das Beste daraus: <ul><li>Seien Sie spezifisch: Fügen Sie genaue Begriffe hinzu (z. B. „Verkäufe des letzten Monats in Kalifornien„), um die Antwort einzugrenzen.</li><li>Verwenden von klaren Metriken und Filtern: Das Hinzufügen spezifischer Metriken (z. B. „Umsatz„), Dimensionen (z. B. „Website-Name„), Filter (z. B. &quot;iPhone-Benutzer„) und Datumsbereiche (z. B. „Letzte drei Monate„) hilft dem KI-Assistenten, sich auf die richtigen Daten zu konzentrieren.</li><li>Stellen Sie direkte Fragen: Formulieren Sie Fragen direkt, z. B. „Wie hoch ist der durchschnittliche Umsatz dieses Jahres nach Produktkategorie?“ erleichtert dem KI-Assistenten die Bereitstellung klarer, relevanter Einblicke.</li></ul>

Sehen Sie sich die folgende Tabelle mit Beispielbegriffen und -ausdrücken an, die Sie in Eingabeaufforderungen mit der Datenvisualisierung im KI-Assistenten verwenden können, zusammen mit den Antworttypen, die Sie erwarten können. Diese Beispiele sollen Ihnen dabei helfen, sich damit vertraut zu machen, wie bestimmte Wörter oder Strukturen die Ausgabe des KI-Assistenten beeinflussen können, und so präzisere und wertvollere Einblicke sicherstellen. Bitte beachten Sie, dass der KI-Assistent generative KI verwendet, sodass Visualisierungen oder ausgewählte Daten über ähnliche Eingabeaufforderungen hinweg leicht variieren können.

| Gewünschtes Ergebnis | Beispielbegriffe und -sätze |
| --- | --- |
| Visualisierung der Zusammenfassungszahl | <ul><li>Gesamt</li></ul> |
| Vergleichen von Komponenten | <ul><li>Vergleichen</li><li>VS</li><li>Kontrast</li><li>Week-to-Week</li><li>Monat-zu-Monat</li><li>Quartalsvergleich</li><li>Year-over-Year</li></ul> |
| Donut-Visualisierung | <ul><li>Verhältnis</li><li>Anteil von</li><li>Verteilung</li><li>Prozent</li><li>Beitrag</li><li>Teil</li><li>Teile</li></ul> |
| Linienvisualisierung | <ul><li>Trend</li><li>[Metrik] in [Zeitbereich]</li></ul> |
| Balkenvisualisierung | <ul><li>[Metrik] nach [Dimension]</li></ul> |

## Erwartungen an Alpha-Tests und angefordertes Feedback

Überprüfen Sie nach dem Stellen jeder Frage sorgfältig die Antwort des Assistenten. Es ist wichtig, die generierten Visualisierungen umfassend zu bewerten, bevor Sie Feedback geben. Beachten Sie bei der Auswertung der Antwort des KI-Assistenten Folgendes:

* Antwort oder Vorlage der Chat-Leiste: Bewerten Sie die vom Assistenten bereitgestellte textliche Antwort. Ist die Antwort im Kontext Ihrer Eingabeaufforderung(en) angemessen?

* Visualisierung/Diagramm: Bewertung der Visualisierung. Ist es die geeignete/erwartete Visualisierung für Ihre Frage, oder hätten Sie eine andere Visualisierung erwartet?

* Freiformtabelle : Bewerten Sie die Freiformtabelle. Sind die Daten der Freiformtabelle korrekt? Werden die Daten bei Bedarf aufgeschlüsselt? Sind die angewendeten Filter die von Ihnen angeforderten oder erwarteten?

* Fehlermeldung/Außerhalb des Bereichs: Wenn eine allgemeine Fehlermeldung angezeigt wird, die besagt, dass die Frage außerhalb des Bereichs liegt, geben Sie Feedback dazu, ob Sie der Meinung sind, dass die außerhalb des Bereichs liegende Nachricht für Ihre Eingabeaufforderung geeignet ist. War Ihre Eingabeaufforderung tatsächlich im Umfang enthalten?

**Bitte geben Sie für jede Antwort je nach Antwort einen Daumen hoch oder einen Daumen runter**

Bitte wählen Sie im Anschluss an die Auswahl mit dem Daumen nach oben/unten die entsprechenden Mehrfachauswahl-Feedback-Felder aus. Wenn Sie zusätzliches Feedback geben möchten, fügen Sie im Textfeld Öffnen Anmerkungen hinzu.

## Fragen und Kontakt

* Senden Sie Fragen und Feedback im Alpha-Slack-Kanal: #cja-assistant-data-alpha
