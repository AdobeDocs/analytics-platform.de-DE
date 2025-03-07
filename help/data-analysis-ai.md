---
description: Fragen zur Datenanalyse in der Dokumentation zu Customer Journey Analytics
title: Datenanalyse-KI-Assistent in Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
hidefromtoc: true
hide: true
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: ac3ec479938acf509bbd26be282b75e75dd49c33
workflow-type: tm+mt
source-wordcount: '1650'
ht-degree: 3%

---

# Visualisieren von Daten mit dem KI-Assistenten in Customer Journey Analytics

Der KI-Assistent in Customer Journey Analytics ist ein generativer KI-Konversationsagent, der Fragen zu Ihren Daten schnell und effizient beantwortet. Er erstellt relevante Visualisierungen in Analysis Workspace mithilfe von Komponenten aus Ihrer Datenansicht und unter Verwendung Ihrer tatsächlichen Daten.

Wenn Sie den KI-Assistenten zur Beantwortung datenorientierter Fragen in Analysis Workspace verwenden, können Sie unzählige Stunden einsparen, die Sie andernfalls möglicherweise damit verbringen würden, Visualisierungen in Analysis Workspace manuell zu erstellen und sich mit Ihren Datenansichtskomponenten vertraut zu machen.

![Datenanalyse-KI-Assistent](assets/cja-ai-asst-da.gif)

## Funktionen innerhalb und außerhalb des Projektumfangs für die Alpha-Version

### Alpha-Funktionen im Umfang

| Unterstützte Funktion | Beschreibung |
| --- | --- |
| **Erstellen und Aktualisieren von Visualisierungen** | Erzeugt eine Freiformtabelle und eine dazugehörige Visualisierung (z. B. Linie, Balken, Ringdiagramm usw.).<p>Beispiel: *Was ist der Gewinn für alle SKUs von Februar bis Mai?* |
| **Unterstützte Visualisierungstypen** | <ul><li>Linie</li><li>Mehrzeilig</li><li>Freiformtabelle</li><li>Balken</li><li>Ringdiagramm</li><li>Zusammenfassungszahl</li></ul> |
| **Out-of-Scope Prompt Detection** | Wenn Sie eine Eingabeaufforderung übermitteln, die außerhalb des Projektumfangs liegt, z. B. „Dieses Projekt exportieren“, antwortet der Assistent, indem er Ihnen mitteilt, dass die Frage außerhalb des Projektumfangs liegt. |
| **Fragen klären** | Wenn Sie eine Frage stellen, die nicht genügend Kontext für die Antwort des KI-Assistenten hat oder zu generisch ist, antwortet der KI-Assistent mit einer klärenden Frage oder vorgeschlagenen Optionen. Beispiele: <p>**Komponenten**<ul><li>Metrik: *Welche „Umsatz“-Metrik meinten Sie?*</li><li>Dimension: *Auf welche der folgenden „Regionen“ möchten Sie sich konzentrieren?*</li><li>Filter: *Welchen Filter „Konto“ wollten Sie anwenden?*</li><li>Datumsbereich: *Mit „letztem Monat“ meinen Sie den letzten vollen Monat oder die letzten 30 Tage?*</li></ul>**Dimension-Elemente**: Welchen „Store-Namen“ meinten Sie? (Beispiel: #5274, #2949 usw.) |
| **Multi-Turn** | Der KI-Assistent antwortet auf eine Eingabeaufforderung mit dem Kontext früherer Eingabeaufforderungen, sodass Benutzende Visualisierungen aktualisieren und Fragen stellen können. Beispiel: <ul><li>Eingabeaufforderung 1: *Trendereignisse ab März.*</li><li>Eingabeaufforderung 2: *Zeigen Sie mir stattdessen die Daten von März bis April*</li></ul> |
| **Verifizierbarkeit** | Die Datenverifizierbarkeit und -richtigkeit kann über die generierte Freiformtabelle und Datenvisualisierung bestätigt werden. Wenn ein(e) Benutzende(r) beispielsweise *Bestellungen im letzten Monat* fragt, können Sie bestätigen, dass im neu generierten Bedienfeld, in der Datenvisualisierung und in der Freiformtabelle die richtige Metrik („Bestellungen„) und der richtige Datumsbereich („letzter Monat„) ausgewählt wurden. |
| **Feedback** | <ul><li>Daumen hoch</li><li>Daumen runter</li><li>Markierung</li></ul> |

### Beta-Funktionen, die nicht im Umfang enthalten sind

| Nicht unterstützte Funktion | Beschreibung |
| --- | --- |
| **Inline-Zusammenfassung oder -Antwort** | Der KI-Assistent kann in der Chat-Leiste nicht mit einer zusammenfassenden Antwort auf eine Benutzeraufforderung antworten. Beispiel für Eingabeaufforderungen außerhalb des Bereichs:<ul><li>*Geben Sie mir eine Zusammenfassung der Erkenntnisse aus meiner letzten Eingabeaufforderung.*</li><li>*Fassen Sie die Highlights der Linienvisualisierung zusammen.*</li></ul> |
| **Fragen klären** | Die Klärung von Fragen beschränkt sich auf Komponenten und Dimensionselemente. Der KI-Assistent kann Dinge wie Datenansichten, Visualisierungen, Datengranularität, Vergleich und Umfang nicht klären. Wenn Klärungsfragen nicht verwendet werden können, verwendet der Assistent standardmäßig das, was Sie am wahrscheinlichsten verlangen. Wenn eine unerwartete Visualisierung oder Datengranularität zurückgegeben wird, können Sie die Funktion „Multi-Turn/Update“ verwenden, um die Visualisierung und die Daten anzupassen. |
| **Workspace-Aktionen/-Funktionen** | Der KI-Assistent kann für einen Benutzer in Workspace keine Aktionen ausführen, abgesehen von der Erstellung und Aktualisierung von Visualisierungen. Sie kann beispielsweise keine der folgenden Aktionen ausführen:<ul><li>Schaltflächen der kontextuellen Aktionsbenutzeroberfläche (zum Diagramm hinzufügen, neues Bedienfeld, neue Tabelle)</li><li>Freigeben</li><li>Exportieren</li><li>Download</li><li>Benutzereinstellungen verwalten</li><li>Kuratieren</li><li>Datenansicht verwalten</li><li>Analytics Dashboards App</li><li>Attribution</li></ul> |
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

1. Gehen Sie zu [experience.adobe.com](https://experience.adobe.com/) und melden Sie sich mit Ihrer Adobe ID an.

2. Wählen Sie **Customer Journey Analytics** auf der Experience Cloud-Startseite aus.

3. Wählen Sie **[!UICONTROL Leeres Projekt]** im Banner oben auf der Projektseite aus, um ein neues leeres Projekt zu öffnen.

4. Stellen Sie sicher, dass es sich bei der für das Bedienfeld ausgewählten Datenansicht um dieselbe Datenansicht handelt, die für die Verwendung mit dem KI-Assistenten für Beta-Tests aktiviert wurde.

   Wenn Sie sich nicht sicher sind, wenden Sie sich an den Beta Slack-Kanal.

5. Wählen Sie oben rechts auf der Seite das Chat-Symbol für den KI-Assistenten aus.

   Wenn das Chat-Symbol nicht angezeigt wird, wenden Sie sich an Ihren Administrator, damit er die folgenden Funktionen in der Admin Console aktivieren kann:

   * **[!UICONTROL KI-Assistent: Produktkenntnisse]**

   * **[!UICONTROL KI-Assistent: Datenanalyse]**

   Weitere Informationen erhalten Admins unter [diese Anweisungen](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/access).

   ![KI-Assistenten-Symbol](/help/assets/ai-asst-icon.png)

6. Customer Journey Analytics Stellen Sie im Dialogfeld **[!UICONTROL Fragen über]**&quot; unten auf der Seite im KI-Assistenten eine Frage zur Datenvisualisierung.

   Weitere Informationen finden Sie in den folgenden Beispielen.

### Beispiel 1

Nehmen wir beispielsweise an, Sie sind an den Bestellungen interessiert, die Ihr Unternehmen im Juli erhalten hat.

**Eingabeaufforderung:** Geben Sie *„Trend der Bestellungen im Juli“ ein*

![KI-Eingabeaufforderung](/help/assets/ai-asst-prompt1.png)

**Antwort:** Der KI-Assistent sammelt Einblicke, indem er die Daten in der Datenansicht durchsucht, einschließlich der Metriken und Komponenten. Dadurch wird die Eingabeaufforderung in die richtigen Dimensionen und Metriken innerhalb des Datenbereichs übersetzt.

Wie Sie sehen können, wurden automatisch ein Liniendiagramm und eine Freiformtabelle generiert, um Bestellungen für Juli anzuzeigen.

![Antwort auf Eingabeaufforderung - Liniendiagramm und Freiformtabelle](/help/assets/ai-asst-result.png)

### Beispiel 2

Als Nächstes möchten Sie sehen, wie Ihr Umsatz nach Region verglichen wird.

**Prompt:** Geben Sie im Eingabeaufforderungsfenster *„Umsatz nach Region anzeigen“ ein*

**Antwort:** Der KI-Assistent versteht intelligent, dass Sie mit „Region“ „Kundenregion“ meinen. Es wird ein Balkendiagramm erstellt, das den Umsatz am besten nach Region zeigt:

![Balkendiagramm](/help/assets/ai-asst-result2.png)

### Beispiel 3

Als Nächstes möchten Sie nicht nur den Umsatz nach Region verstehen, sondern auch Daten für den Gewinn nach Region anzeigen. Anstatt die vorherige Eingabeaufforderung zu wiederholen, können Sie den KI-Assistenten bitten, die neueste Visualisierungs- und Freiformtabelle zu aktualisieren.

**Prompt:** Geben Sie im Eingabeaufforderungsfenster „Gewinn hinzufügen *ein*

**Antwort:** Das **[!UICONTROL Balkendiagramm]** bietet weiterhin die prägnanteste Antwort, aber die Gewinnmetrik wurde als Spalte in der Freiformtabelle hinzugefügt:

![Balkendiagramm](/help/assets/ai-asst-result4.png)

### Beispiel 4

Sehen wir uns abschließend den Umsatz nach Produktkategorie an.

**Eingabeaufforderung:** Geben Sie im Eingabeaufforderungsfenster *„Umsatzanteil nach Produktkategorie“ ein*

**Antwort:** Auch hier wählt die Datenvisualisierung im KI-Assistenten die am besten geeignete Visualisierung aus, in diesem Fall die **[!UICONTROL Ringdiagramm]**-Visualisierung, um die Frage zu beantworten.

![Ringdiagramm](/help/assets/ai-asst-result3.png)

## Eingabeaufforderungen zur Beispieldatenvisualisierung

Im Folgenden finden Sie einige Beispiele für häufige Eingabeaufforderungen und die Visualisierungen, die vom KI-Assistenten verwendet werden, um auf diese Eingabeaufforderungen zu reagieren.

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

Der KI-Assistent verarbeitet den von jeder Benutzeraufforderung bereitgestellten Kontext und versucht, mit der am besten geeigneten Visualisierung und den am besten geeigneten Komponenten in einer Freiformtabelle intelligent zu reagieren.

Die Antworten können je nach den in der Eingabeaufforderung verwendeten spezifischen Wörtern und Ausdrücken variieren, und leichte Sprachänderungen können zu unterschiedlichen Ergebnissen führen.

Um die besten Ergebnisse zu erzielen, beachten Sie die folgenden Richtlinien:

* Seien Sie spezifisch: Schließen Sie genaue Begriffe ein, um die Antwort einzugrenzen. Im Folgenden finden Sie ein Beispiel für eine bestimmte Eingabeaufforderung: „Umsatz des letzten Monats in Kalifornien“

* Klare Metriken und Filter verwenden: Durch das Hinzufügen spezifischer Metriken (z. B. „Umsatz„), Dimensionen (z. B. „Website-Name„), Filter (z. B. &quot;iPhone-Benutzer„) und Datumsbereiche (z. B. „Letzte drei Monate„) kann sich der KI-Assistent auf die richtigen Daten konzentrieren.

* Stellen Sie direkte Fragen: Die direkte Formulierung von Fragen erleichtert dem KI-Assistenten die Bereitstellung klarer, relevanter Einblicke. Im Folgenden finden Sie ein Beispiel für eine direkte Frage in einer Eingabeaufforderung: „Wie hoch ist der durchschnittliche Umsatz nach Produktkategorie in diesem Jahr?“

Sehen Sie sich die folgende Tabelle mit Beispielbegriffen und -ausdrücken an, die Sie bei Eingabeaufforderungen mit der Datenvisualisierung im KI-Assistenten verwenden können, zusammen mit den Antworttypen, die Sie erwarten können.

Diese Beispiele sollen Ihnen dabei helfen, sich damit vertraut zu machen, wie bestimmte Wörter oder Strukturen die Ausgabe des KI-Assistenten beeinflussen können, und so präzisere und wertvollere Einblicke sicherstellen. Der KI-Assistent verwendet generative KI, sodass Visualisierungen oder ausgewählte Daten über ähnliche Eingabeaufforderungen hinweg leicht variieren können.

| Gewünschtes Ergebnis | Beispielbegriffe und Ausdrücke |
| --- | --- |
| Visualisierung der Zusammenfassungszahl | <ul><li>Gesamt</li></ul> |
| Vergleichen von Komponenten | <ul><li>Vergleichen</li><li>VS</li><li>Kontrast</li><li>Week-to-Week</li><li>Monat-zu-Monat</li><li>Quartalsvergleich</li><li>Year-over-Year</li></ul> |
| Ringvisualisierung | <ul><li>Verhältnis</li><li>Anteil von</li><li>Verteilung</li><li>Prozent</li><li>Beitrag</li><li>Teil</li><li>Teile</li></ul> |
| Linienvisualisierung | <ul><li>Trend</li><li>[Metrik] in [Zeitbereich]</li></ul> |
| Balkenvisualisierung | <ul><li>[Metrik] von [Dimension]</li></ul> |

## Erwartungen an Beta-Tests und angefordertes Feedback

Überprüfen Sie nach dem Stellen jeder Frage sorgfältig die Antwort des Assistenten. Es ist wichtig, die generierten Visualisierungen umfassend zu bewerten, bevor Sie Feedback geben.

Beachten Sie bei der Auswertung einer Antwort des KI-Assistenten Folgendes:

* Antwort oder Vorlage der Chat-Leiste: Bewerten Sie die vom Assistenten bereitgestellte textliche Antwort. Ist die Antwort im Kontext Ihrer Eingabeaufforderung angemessen?

* Visualisierung/Diagramm: Bewertung der Visualisierung. Ist es die geeignete oder erwartete Visualisierung für Ihre Frage, oder hätten Sie eine andere Visualisierung erwartet?

* Freiformtabelle : Bewerten Sie die Freiformtabelle. Sind die Daten der Freiformtabelle korrekt? Werden die Daten bei Bedarf aufgeschlüsselt? Sind die angewendeten Filter die von Ihnen angeforderten oder erwarteten?

* Fehlermeldung/Außerhalb des Bereichs: Wenn eine allgemeine Fehlermeldung angezeigt wird, die besagt, dass die Frage außerhalb des Bereichs liegt, geben Sie Feedback dazu, ob Sie der Meinung sind, dass die außerhalb des Bereichs liegende Nachricht angesichts Ihrer Eingabeaufforderung angemessen ist. War Ihre Eingabeaufforderung tatsächlich im Umfang?

**Geben Sie für jede Antwort je nach Antwort einen Daumen hoch oder einen Daumen runter.**

Nach der Auswahl der Daumen hoch oder Daumen runter treffen Sie bitte eine Auswahl für die entsprechenden Mehrfachauswahl-Feedback-Boxen. Wenn Sie zusätzliches Feedback geben möchten, fügen Sie im Textfeld Öffnen Anmerkungen hinzu.

## Fragen und Kontakt

* Senden Sie Fragen und Feedback über den Alpha Slack-Kanal: #cja-assistant-data-alpha
