---
title: Callcenter- und Web-Daten importieren
description: Erfahren Sie, wie Sie einen Datensatz erstellen, mit dem Sie Callcenter- und Website-Daten verknüpfen.
exl-id: 48546227-029c-4cf9-9b7e-66d547769270
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '1141'
ht-degree: 88%

---

# Callcenter- und Web-Daten importieren

Customer Journey Analytics bietet die wertvolle Möglichkeit, Datensätze aus verschiedenen Quellen in einem einzigen Arbeitsbereich-Projekt zu kombinieren. Verwenden Sie diesen Leitfaden, um zu verstehen, wie Ihr Unternehmen Website-Daten mit Callcenter-Daten kombinieren kann. Sie können beispielsweise verstehen, welche Aktionen ein Kunde durchführt, welche Inhalte er anzeigt und nach welchen Begriffen er sucht, bevor er sich an den Support wendet. Anschließend können Sie die Inhalte und Self-Service-Tools ermitteln, die verbessert werden sollen, damit Kunden Probleme besser selbst lösen können, ohne anrufen zu müssen.

## Voraussetzungen

* Die wichtigste Komponente für die Kombination dieser beiden Datensätze ist eine gemeinsame Kennung für die einzelnen Datenquellen. Beispiele sind eine Kunden-ID, eine gehashte E-Mail-Adresse, ein Anmeldename oder eine Telefonnummer.
* Zugang zu Adobe Experience Platform und Customer Journey Analytics
* Wenn Ihr Datensatz Protokolle aus einem Interactive Voice Response-System enthält, empfiehlt Adobe, die Daten vor dem Import in die Platform so zu verarbeiten, dass diese nur Aufforderungs-Interaktionen enthalten.
* Wenn Ihr Datensatz Anrufprotokolle enthält, empfiehlt Adobe, die folgenden Spalten einzubeziehen:
   * Datum/Uhrzeit des Anrufbeginns
   * Grund für den Anruf
   * Callcenter-ID
   * Callcenter-Mitarbeiter-ID
   * Dauer des Anrufs
   * Ergebnisse des Anrufs
   * Kosten des Anrufs (falls verfügbar)
   * Weitere Anruf-Metadaten, die Ihre Organisation einbeziehen kann

## Web- und Callcenter-Daten in die Platform importieren

Importieren Sie die Daten in Adobe Experience Platform. Informationen zum [Erstellen eines Schemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=de) und [Aufnehmen von Daten](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=de) finden Sie in der Adobe Experience Platform-Dokumentation.

Beim Importieren von Daten in die Platform können folgende Tipps hilfreich sein, um einen besseren Einblick in die resultierenden Berichte zu gewinnen:

* Stellen Sie sicher, dass die Kennungen, die zum Verknüpfen von Callcenter- und Web-Daten verwendet werden, ähnlich formatiert sind.
* Beziehen Sie die Datenquelle in jeden Datensatz ein. Fügen Sie beispielsweise eine Spalte `data_source` in jedes Schema ein und setzen Sie den Wert jedes Ereignisses jeweils auf `"Web"` bzw. `"Call center"`. <!--mapper-->

## Ordnen Sie die Personen-IDs zu

Customer Journey Analytics erfordert eine gemeinsame Kennung, um einen [kombinierten Datensatz“ ](/help/connections/combined-dataset.md).

* Wenn Ihre Datensätze bereits für jedes Ereignis in beiden Datensätzen eine gemeinsame Kennung aufweisen, können Sie diesen Schritt überspringen und eine Verbindung erstellen.
* Wenn einer Ihrer Datensätze nur für einige Ereignisse eine gemeinsame Kennung hat, können Sie Daten mithilfe von [Zusammenfügung](/help/stitching/overview.md) für Schritte zusammenfügen, um die kanalübergreifende Analyse für diese beiden Datensätze zu aktivieren.

## Erstellen einer Verbindung in Customer Journey Analytics

[Erstellen einer Verbindung](/help/connections/create-connection.md) in Customer Journey Analytics.

* Wenn die kanalübergreifende Analyse verwendet wird, steht Ihnen ein neuer zugeordneter Datensatz zur Verfügung. Verwenden Sie das neu erstellte Feld für die zugeordnete ID als die Personen-ID.
* Andernfalls können Sie auch die ursprünglichen Web- und Callcenter-Datensätze für die Verbindung verwenden.

## Datenansicht erstellen

Nachdem Sie eine Verbindung erstellt haben, können Sie eine [Datenansicht erstellen](/help/data-views/create-dataview.md), die in Analysis Workspace verwendet werden kann. Nützliche Komponenten sind:

* Eine Seitendimension mit Letztkontakt- und Sitzungspersistenz. Sie können Callcenter-Metriken mit der letzten Seite verbinden, die ein Kunde vor dem Anruf aufgerufen hat.
* Eine Anrufmetrik, die das Schemafeld „Callcenter-Grund“ verwendet, um das Vorkommen zu erhöhen. Verwenden Sie [Metrik-Deduplizierung](/help/data-views/component-settings/metric-deduplication.md), damit sie nur einmal pro Sitzung erhöht wird.

## Visualisierungen erstellen

Die folgenden Visualisierungen können verwendet werden, um Einblicke aus Ihrem zugeordneten Datensatz zu gewinnen.

### Datensatz-Überschneidung

In dieser Visualisierung können Sie die Qualität der Datenzuordnung in der kanalübergreifenden Analyse erkennen.

1. Erstellen Sie zwei Segmente. Die in diesen beiden Segmenten verwendete Variable ist dieselbe oben erwähnte Variable, die die Datenquelle jedes Ereignisses widerspiegelt. Weitere [ finden Sie unter ](/help/components/segments/seg-create.md) erstellen .
   * Personen-Container, bei dem die Datensatz-ID mit Ihren Web-Daten übereinstimmt
   * Personen-Container, bei dem die Datensatz-ID mit Ihren Callcenter-Daten übereinstimmt
2. Ziehen Sie in Analysis Workspace eine [Venn](/help/analysis-workspace/visualizations/venn.md)-Visualisierung auf die Arbeitsbereich-Arbeitsfläche.
3. Ziehen Sie die beiden neu erstellten Segmente in den Bereich **[!UICONTROL Segment hinzufügen]** und die Metrik „Personen“ in den Bereich **[!UICONTROL Metrik hinzufügen]**.

In der entsprechenden Venn-Visualisierung wird die Anzahl der Personen in Ihrem Datensatz angezeigt, die sowohl Web- als auch Callcenter-Daten enthalten. Je größer die Überschneidung, desto mehr Personen wurden erfolgreich zugeordnet. Die Bereiche, die sich nicht überschneiden, stellen Personen dar, die sich ausschließlich in einem der beiden Datensätze befinden.

### Callcenter-Ereignisse zu Web-Seiten zuordnen

Diese Freiformtabelle zeigt die wichtigsten Seiten, die zum Aufruf von Callcenter-Ereignissen beitragen. Stellen Sie zunächst sicher, dass die gewünschten Dimensionen und Metriken das richtige Attributionsmodell haben:

1. Ziehen Sie die Dimension, die die Namen Ihrer Web-Seiten beinhaltet, in eine Freiformtabellen-Visualisierung.
1. Ersetzen Sie die Metrik durch die gewünschte Callcenter-Metrik, die Sie messen möchten.
1. Klicken Sie auf das Zahnradsymbol neben der Metrikkopfzeile. Klicken Sie auf **[!UICONTROL Nicht-standardmäßiges Attributionsmodell verwenden]**.
1. Legen Sie das gewünschte [Attributionsmodell](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) fest. Beispiel: ein Modell für einen Zeitverfall mit einer Halbwertszeit von 15 Minuten und einem Lookback-Fenster für die Sitzung. Dieses Attributionsmodell schreibt den Seiten gut, die zu dem Anruf in Ihrem Callcenter führen.

Der resultierende Bericht zeigt die wichtigsten Seiten an, die Anufe an Ihr Callcenter leiten. <!-- use case behind what we use these pages for -->

<!-- Complement with donut visualization -->

Sie können die Einblicke in diese Tabelle weiter verbessern, indem Sie Anrufe nach Grund oder Kategorie aufteilen.

1. Klicken Sie in der Komponentenliste unter der Dimension „Grund des Anrufs“ auf den Pfeil nach rechts. Diese Aktion zeigt individuelle Dimensionswerte an.
2. Ziehen Sie den/die gewünschten Dimensionswert(e) unter die Metrik „Anrufe“, die diese Metrik nach jedem jeweiligen Anrufgrund segmentiert.
3. Wiederholen Sie diesen Vorgang für jeden Anrufgrund, den Sie detailliert anzeigen möchten. Verwenden Sie das Segment „Alle Sitzungen“, um die Gesamtsumme anzuzeigen.

<!-- screenshot -->

### Flussvisualisierung

Sie können Einblicke in das erhalten, was ein Kunde versucht hat, bevor er den Callcenter-Kanal verwendet hat. Diese Flussvisualisierung hilft Ihnen dabei, die häufigsten Journey zu verstehen, über die ein Kunde in Ihr Callcenter gelangt. Mit diesen Einblicken können Sie die effektivsten Verbesserungen ermitteln, die Sie an Ihrer Site vornehmen können, sodass Kunden mit geringerer Wahrscheinlichkeit anrufen.

1. Klicken Sie auf das Symbol **[!UICONTROL Visualisierungen]** auf der linken Seite und ziehen Sie die gewünschte Visualisierung in den Arbeitsbereich.
2. Klicken Sie links auf die Registerkarte **[!UICONTROL Komponenten]** und suchen Sie die Dimension „Grund des Anrufs“.
3. Klicken Sie auf den Pfeil nach rechts neben dieser Dimension. Diese Aktion zeigt individuelle Dimensionswerte an.
4. Ziehen Sie das gewünschte Dimensionselement für den Anrufgrund an die mittlere Position der Flussvisualisierung.
5. Die Flussvisualisierung füllt automatisch die Gründe für den vorherigen und nächsten Anruf. Ersetzen Sie den vorherigen Anrufgrund durch die Dimension der Web-Seite.
6. Klicken Sie auf das Zahnradsymbol oben rechts in der Flussvisualisierung und ändern Sie den Fluss-Container in **[!UICONTROL Sitzung]**.

### Histogramm

Wie viele Kunden haben einmal angerufen, zweimal angerufen oder mehr als sechs Mal angerufen? Einige dieser Personen besuchen die Website nie. Verwenden Sie die Histogrammvisualisierung, um zu bestimmen, wie viele Personen in die einzelnen Behälter fallen. Sehen Sie, wie Sie Personen, die die Website nie besuchen, zum Self-Service ermutigen können.

1. Klicken Sie auf das Symbol **[!UICONTROL Visualisierungen]** auf der linken Seite und ziehen Sie eine Histogrammvisualisierung in den Arbeitsbereich.
2. Klicken Sie links auf die Registerkarte **[!UICONTROL Komponenten]** und ziehen Sie die Anrufmetrik in die Histogrammvisualisierung.
3. Klicken Sie in der Mitte der Visualisierung auf **[!UICONTROL Erweiterte Einstellungen anzeigen]** und passen Sie die gewünschten Behälter an.
4. Klicken Sie auf **[!UICONTROL Erstellen]**.

<!--
### Web to call, call to web

### Fallout

Fallout sessions - session

All sessions > page views metric > calls metric

All sessions > calls metric > page views

Orrr we could also use dataset ID

step 1: all sessions
step 2: 


### Site sections that result in a call within 30 minutes

Slide 4

Create a bunch of segments - facets to their business. Segments were used because they didn't have all of these in the same dimension, so they could create everything in this report as a single dimension (really segments)

wanted to understand when someone interacts with a facet, whats the highest percentage of people that abandon that channel to call them. not from volume perspective, but percentage perspective.

use sequential segments, but you lose the ability to use attribution IQ

## What to do when you've found insight -->
