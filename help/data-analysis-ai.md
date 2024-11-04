---
description: So stellen Sie Fragen zur Datenanalyse in der Customer Journey Analytics-Dokumentation
title: Assistent für Datenanalyse-KI im Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: true
hide: true
source-git-commit: ab8a4c65de59e725d7d181ee699d7a196988bf98
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 4%

---


# Data Analysis AI Assistant in Customer Journey Analytics - Alpha

Der Data Analysis AI-Assistent ist ein intelligenter, kontextbezogener Konversationsagent, der Ihnen dabei hilft, Fragen zu Ihren Analysis Workspace-Daten in Customer Journey Analytics schneller und effizienter zu beantworten.

Der Assistent durchsucht alle Daten in einer Datenansicht, einschließlich der verschiedenen Metriktypen und Komponenten, und übersetzt Ihre Eingabeaufforderung in die richtige Dimension, Metrik und den richtigen Datumsbereich für diese Analyse. Anstatt sich mit den Datenansichtskomponenten vertraut zu machen und diese Komponenten zur Beantwortung Ihrer Frage per Drag-and-Drop in die beste Kombination zu ziehen, können Sie die Frage einfach in den AI-Assistenten eingeben.

## Funktionen für die Alpha-Version im Vergleich zum Umfang

### Funktionen im Bereich

| Unterstützte Funktion | Beschreibung |
| --- | --- |
| **Visualisierungen erstellen und aktualisieren** | Erzeugt eine Freiformtabelle und die zugehörige Visualisierung (z. B. Linie, Balken, Ring usw.).<p>Beispiel: *Welchen Gewinn erzielen SKUs zwischen Februar und Mai?* |
| **Unterstützte Visualisierungstypen** | <ul><li>Linie</li><li>Mehrzeilig</li><li>Freiform</li><li>Balken</li><li>Ringdiagramm</li><li>Zusammenfassungszahl</li></ul> |
| **Erkennung von Eingabeaufforderungen außerhalb des Umfangs** | Wenn Sie eine Eingabeaufforderung senden, die nicht im Umfang vorhanden ist, z. B. &quot;dieses Projekt exportieren&quot;, antwortet der Assistent, indem er Ihnen mitteilt, dass die Frage außerhalb des Anwendungsbereichs liegt. |
| **Fragen klären** | Wenn Sie eine Frage stellen, die nicht genügend Kontext für eine Antwort des KI-Assistenten bietet oder zu allgemein ist, antwortet der KI-Assistent mit einer Frage zur Klarstellung und/oder mit vorgeschlagenen Optionen. Beispiele: <p>**Komponenten**<ul><li>Metrik: *Welche &quot;Umsatz&quot;-Metrik haben Sie gemeint?*</li><li>Dimension: *Auf welche der folgenden &quot;Regionen&quot;möchten Sie sich konzentrieren?*</li><li>Filter: *Welchen &quot;Konto&quot;-Filter wollten Sie anwenden?*</li><li>Datumsbereich: *Mit &quot;Letzter Monat&quot;haben Sie den letzten vollen Monat oder die letzten 30 Tage gemeint?*</li></ul>**Dimension items**: Welchen &quot;Speichernamen&quot;haben Sie gemeint? (Beispiel: Store #5274, Store #2949 usw.) |
| **Mehrfachwechsel** | Der AI-Assistent antwortet auf eine Eingabeaufforderung mit dem Kontext der vorherigen Aufforderung(en), sodass Benutzer Visualisierungen aktualisieren und Folgenachfragen stellen können. Beispiel: *Zeigen Sie mir stattdessen die Daten von März bis April.* |
| **Feedback** | <ul><li>Daumen nach oben</li><li>Nach unten</li><li>Markierung</li></ul> |

### Out-of-Scope-Funktionen

| Nicht unterstützte Funktion | Beschreibung |
| --- | --- |
| **Inline-Zusammenfassung oder -Antwort** | Der KI-Assistent kann in der Chatleiste nicht mit einer zusammenfassenden Antwort auf eine Benutzeraufforderung linear antworten. Beispielhafte Eingabeaufforderungen außerhalb des Umfangs:<ul><li>*Geben Sie mir eine Zusammenfassung der Einblicke aus meiner letzten Eingabeaufforderung.*</li><li>*Fassen Sie die Highlights aus der Linienvisualisierung zusammen.*</li></ul> |
| **Fragen klären** | Die Klärung von Fragen ist auf Komponenten und Dimensionselemente beschränkt. Der AI-Assistent kann keine Datenansichten, Visualisierungen, Datengranularität, Vergleich, Umfang usw. klären. Ohne Klarstellung der Fragen verwendet die Assistenzkraft standardmäßig das, was Sie am ehesten wünschen. Wenn eine unerwartete Visualisierung oder Datengranularität zurückgegeben wird, können Sie dann die Funktion für die Mehrfachumstellung/Aktualisierung verwenden, um die Visualisierung und die Daten anzupassen. |
| **Workspace-Aktionen/-Funktionen** | Der KI-Assistent kann für einen Benutzer in Workspace keine Aktionen durchführen, außer Visualisierungen zu erstellen und zu aktualisieren. Sie kann beispielsweise keine der folgenden Aktionen durchführen:<ul><li>Schaltflächen der Benutzeroberfläche für kontextbezogene Aktionen (zu Diagramm hinzufügen, neues Bedienfeld, neue Tabelle)</li><li>Freigeben</li><li>Exportieren</li><li>Download</li><li>Verwalten von Benutzereinstellungen</li><li>Kuratieren</li><li>Datenansicht verwalten</li><li>Analytics-Dashboards-App</li><li>Attribution</li></ul> |
| **Nicht unterstützte Visualisierungstypen** | <ul><li>Fluss</li><li>Fallout</li><li>Kohortentabelle</li><li>Bereich, Bereich gestapelt</li><li>Balken gestapelt</li><li>Horizontales Säulendiagramm</li><li>Kombination</li><li>Histogramm</li><li>Horizontalbalken, Horizontalbalken gestapelt</li><li>Zusammenfassung einer Schlüsselmetrik</li><li>Streuung</li><li>Zusammenfassende Änderung</li><li>Text</li><li>Treemap</li><li>Venn</li></ul> |
| **Erklärbarkeit und Überprüfbarkeit** | Transparente Beschreibung oder Zitation, wie der KI-Assistent eine Antwort generiert hat, und eine Möglichkeit, die Richtigkeit der Antwort zu bestätigen. |

<!---## Feature access in the Customer Journey Analytics UI

[Do we even need this section for the Alpha?]

The following parameters govern access to the Data Analysis AI Assistant feature:

* **Solution access**: The Data Analysis AI Assistant is available for Customer Journey Analytics Prime and Ultimate customers. It is not available in Adobe Analytics. 

It is also available in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP and additional Experience Platform apps.

* **Contractual access**: If you are not able to use AI Assistant, please contact your organization's administrator or Adobe Account Representative. Before your organization can use Data Analysis AI Assistant, your must agree to certain GenAI-related legal terms.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL AI Assistant: Data Analysis]** permission determines access to this tool. A [product profile admin](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) needs to follow these steps in the [!UICONTROL Admin Console]:
   1. Navigate to **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Select the title of the product profile for which you want to provide access to [!UICONTROL AI Assistant: Product Knowledge].
   1. In the specific product profile, select **[!UICONTROL Permissions]**.
   1. Select ![Edit](/help/assets/icons/Edit.svg) to edit **[!UICONTROL Reporting Tools]**.
   1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) to add **AI Assistant: Data Analysis** to **[!UICONTROL Included permission items]**.
   
      ![Add permission](assets/ai-assistant-permissions.png).

   1. Select **[!UICONTROL Save]** to save the permissions.

See [Access control](/help/technotes/access-control.md#access-control) for more information.--->

## Data Analysis AI-Assistent aufrufen und verwenden

1. Klicken Sie auf diesen Link, um Workspace in der Labs IMS-Organisation (in der Phase) zu öffnen und sich mit Ihrer Adobe ID anzumelden.

1. Klicken Sie oben auf der Projektseite im Banner auf **[!UICONTROL Leeres Projekt]** , um ein neues leeres Projekt zu öffnen.

1. Klicken Sie oben rechts auf das Chat-Symbol für den AI-Assistenten.

   ![Symbol &quot;KI-Assistent&quot;](/help/assets/ai-asst-icon.png)

1. Stellen Sie im unteren Dialogfeld **[!UICONTROL Fragen Sie nach Customer Journey Analytics]** im AI-Assistenten eine Frage zur Datenanalyse.

### Beispiel 1

Nehmen wir beispielsweise an, Sie interessieren sich für die Bestellungen, die Ihr Unternehmen im Juli erhalten hat.

1. Geben Sie &quot;Bestellungen im Juli anzeigen&quot;ein.

   ![AI-Eingabeaufforderung](/help/assets/ai-asst-prompt1.png)

1. Der KI-Assistent erfasst jetzt Einblicke, indem er die Daten in der Datenansicht, einschließlich der Metriken und Komponenten, durchsucht. Die Eingabeaufforderung wird in die richtige(n) Dimension(en), Metrik(en) und den richtigen Datenbereich übersetzt.

   Wie Sie sehen können, wurden automatisch ein Liniendiagramm und eine Freiformtabelle mit Bestellungen für Juli erstellt.

   ![Antwort auf Eingabeaufforderung - Kantengraph und Freiformtabelle](/help/assets/ai-asst-result.png)

### Beispiel 2

Als Nächstes möchten Sie sehen, wie der Umsatz nach Region verteilt ist.

1. Geben Sie im Eingabeaufforderungsfenster &quot;Umsatz nach Region anzeigen&quot;ein.

2. Die KI ist intelligent genug, um zu verstehen, dass Sie nach &quot;Region&quot;eine &quot;Kundenregion&quot;meinen. Es wird ein Balkendiagramm erstellt, das den Umsatz am besten nach Region anzeigt:

   ![Balkendiagramm](/help/assets/ai-asst-result2.png)

### Beispiel 3

Betrachten wir nun den Umsatz nach Produktkategorie.

1. Geben Sie im Eingabeaufforderungsfenster &quot;Umsatz nach Produktkategorie anzeigen&quot;ein.

2. Auch hier wählt der Data Analysis AI-Assistent die am besten geeignete Visualisierung aus, in diesem Fall die Visualisierung **[!UICONTROL Donut]** , um die Frage zu beantworten.

   ![Ringdiagramm](/help/assets/ai-asst-result3.png)

### Beispiel 4

Schließlich möchten Sie wissen, welche SKU die profitabelste ist und wo Sie Marketing-Ressourcen investieren sollten.

1. Fragen Sie im Eingabeaufforderungsfenster nach &quot;Welchen Gewinn erzielen die SKUs von Februar bis Mai?&quot;

1. Ein einfaches **[!UICONTROL Balkendiagramm]** liefert die präziseste Antwort:

   ![Balkendiagramm](/help/assets/ai-asst-result4.png)

## Beispieldatenanalyse - Eingabeaufforderungen

Im Folgenden finden Sie einige Beispiele für häufige Eingabeaufforderungen, und welche Visualisierung der Assistent verwendet, um auf diese Aufforderungen zu reagieren.

| Beispielaufforderung | Erwartete Visualisierung |
| --- | --- |
| Anzeigen von Gewinnen in [Monat] | Linie<p>Wenn Sie nach einem Trend oder einer Metrik innerhalb eines bestimmten Zeitraums fragen, wird standardmäßig eine Linienvisualisierung zurückgegeben. |
| Trend-Bestellungen in [Monat] | Linie |
| Umsatz nach Region in [Monat] anzeigen | Balken |
| Umsatzanteil nach Produktkategorie | Ringdiagramm |
| Bestellungen nach Wochentagen, von Januar bis Mai | Balken |
| Bestellungen nach Geschlecht anzeigen, von März bis Juni | Balken |
| Was ist der Gewinn der SKUs zwischen Februar und Mai? | Balken |
| Umsatz nach Speichername in [Monat] | Balken |
| Was waren meine 10 wichtigsten SKUs gewinnbringend im [Monat]? | Balken |
| Anteil der Käufe pro Monat des Jahres | Ringdiagramm |
| Gesamtgewinn in [Monat] | Zusammenfassungszahl<p>Die Anforderung der &quot;Gesamtsumme&quot;einer Metrik über einen bestimmten Zeitraum hinweg sollte eine Visualisierung der Zusammenfassungsnummer zurückgeben. |


## Best Practices auffordern

TBD

## Erwartungen und Feedback zu Alpha-Tests

Nachdem Sie jede Frage gestellt haben, lesen Sie die von der Assistenzkraft gegebene Antwort sorgfältig durch. Es ist entscheidend, die generierten Visualisierungen umfassend zu bewerten, bevor Sie Feedback geben.

Bewerten Sie die Antwort: Ist die gegebene Antwort richtig?

Wenn der Assistent in der Chatleiste antwortet: Beurteilen Sie die Textantwort.

* Wenn eine Visualisierung/Grafik angezeigt wird: Auswertung der Visualisierung. Ist dies die geeignete/erwartete Visualisierung für Ihre Frage?

* Wenn eine Freiformtabelle angezeigt wird: Bewerten Sie die Freiformtabelle. Sind die Daten der Freiformtabelle korrekt? Unterteilen sie die Daten, wo sie angefordert wurden? Sind die angewendeten Filter diejenigen, die Sie angefordert haben oder erwartet haben?

* Wenn eine allgemeine Fehlermeldung angezeigt wird, in der erklärt wird, dass die Frage nicht ausführbar ist, geben Sie Feedback dazu, ob die Nachricht über den Umfang hinaus Ihrer Aufforderung angemessen ist. War Ihre Eingabeaufforderung tatsächlich im Bereich?

Geben Sie für jede Antwort je nach Antwort Daumen nach oben oder Daumen nach unten.

Wählen Sie nach der Auswahl der Daumen nach oben/unten für die entsprechenden Mehrfachauswahl-Feedback-Felder aus. Wenn Sie zusätzliches Feedback geben möchten, fügen Sie Anmerkungen in das geöffnete Textfeld ein.

## Fragen und Kontakt

* E-Mail `taylorb@adobe.com` (PM)
* Senden Sie Fragen und Feedback im Alpha-Slack-Kanal: #aep-cja-ai-assistant-testers ???


