---
title: Konzepte und Funktionen von Customer Journey Analytics B2B edition
description: Konzepte und Funktionen für die B2B edition von Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: df2cc922-d214-49b9-8fdb-443cc1dac05b
source-git-commit: 68f2fe684f6eb9590ab047e893fb04b1cbe1a8cd
workflow-type: tm+mt
source-wordcount: '1469'
ht-degree: 2%

---


# Konzepte und Funktionen von B2B edition

In diesem Artikel werden Konzepte wie Verbindungen, Kennungen, Container und Datensätze erläutert, die häufig in Customer Journey Analytics verwendet werden. Und wie Customer Journey Analytics B2B edition zusätzliche Funktionen zu diesen Konzepten hinzufügt.


## Verbindungen und Kennungen

In Customer Journey Analytics wählen Sie eine allgemeine Kennung, die Personen-ID, um Ihre Ereignisdaten mit anderen Datensätzen wie Profildatensätzen und Lookup-Datensätzen zu verbinden. Dieser Verbindungstyp wird als personenbasierte Verbindung bezeichnet, die das personenbasierte Reporting und die Analyse erleichtert.

In Customer Journey Analytics B2B edition können Sie zwischen einer personenbasierten Verbindung und einer kontobasierten Verbindung wählen. Eine Account-basierte Verbindung erleichtert die Account-basierte Berichterstellung und Analyse.

* Für eine personenbasierte Verbindung wählen Sie Person als primäre Kennung. Anschließend können Sie Ihre Verbindungs-, Datenansichts- und Arbeitsbereich-Projekte für personenbasierte Berichte konfigurieren und einrichten.
* Für eine kontobasierte Verbindung wählen Sie Konto als primäre Kennung aus. Anschließend können Sie optional zusätzliche Container für Globales Konto, Einkaufsgruppe und Opportunity hinzufügen. Je nachdem, ob Sie ein globales Konto hinzufügen oder nicht, ist Ihre primäre Kennung eine Kontokennung oder eine globale Kontokennung.


## Container

In Customer Journey Analytics werden Container im Rahmen der Konfiguration einer Verbindung und Datenansicht generiert und stellen die Datenstruktur und den Umfang bereit. Container speichern Kennungsgruppen, um alle Ereigniszeitstempel nach eindeutigen Kennungen zu sequenzieren. Dieser Speicher erleichtert die schnelle und leistungsstarke Ausführung von Funktionen wie Segmentierung, Attribution und Visualisierungen.

### Standard-Container

Customer Journey Analytics basiert auf dem Konzept von drei Containern: Person, Sitzung und Ereignis. Während einer Konfiguration werden diese Container implizit generiert.

Sie können beim Konfigurieren einer Datenansicht den Namen dieser Container neu definieren, aber die Hierarchie und die Beziehungen zwischen den Containern sind vorbestimmt. Der Sitzungs-Container wird basierend auf der Definition einer Sitzung in den [Sitzungseinstellungen](/help/data-views/session-settings.md) in Ihrer Datenansicht generiert.

![B2C](assets/b2c-containers.svg){zoomable="yes"}


### B2B-Container

In Customer Journey Analytics B2B edition wird der Liste der generierten Container ein Konto-Container hinzugefügt. Außerdem haben Sie die Möglichkeit, die Generierung zusätzlicher Container wie „Globales Konto“, „Einkaufsgruppe“ und „Opportunity“ zu konfigurieren.

Die Hierarchie und die Beziehungen zwischen den Containern sind vorgegeben. Opportunity, Einkaufsgruppe und Person sind gleichrangige Container des Konto-Containers. In dieser Hierarchie wird der Sitzungs-Container zwischen dem Personen-Container und dem Ereignis-Container basierend auf der Definition einer Sitzung in den [Sitzungseinstellungen](/help/data-views/session-settings.md) in Ihrer Datenansicht generiert. Zusätzliche Sitzungs-Container, z. B. zwischen dem Konto-Container und dem Ereignis-Container, werden derzeit nicht generiert und unterstützt. In der folgenden Tabelle finden Sie eine Beschreibung und eine allgemeine Verwendung der B2B-Container.

![B2B](assets/b2b-containers.svg){zoomable="yes"}

| B2B-Container | Beschreibung<br/>Grundlegender Anwendungsfall |
|---|---|
| Konto | Ein Unternehmen, das ein Kunde oder potenzieller Kunde Ihres Unternehmens ist. Das Unternehmen könnte eine Tochtergesellschaft oder ein Geschäftsbereich einer größeren Organisation sein. Konto stellt die Organisation dar, an die Sie verkaufen und die Sie auf dieser Organisationsebene verfolgen möchten. |
| Globales Konto (optional) | Die oberste Muttergesellschaft einer Gruppe verbundener Unternehmen. Ein globales Konto hat keine Muttergesellschaft, kann jedoch Tochtergesellschaften oder Geschäftsbereiche haben, die zum globalen Konto gehören. Wenn Sie den Container Globales Konto in Ihrer Verbindung konfiguriert haben, sollte ein Konto, das keine übergeordneten oder untergeordneten Elemente hat, sowohl im Feld Konto als auch im Feld Globales Konto aufgeführt werden. |
| Opportunity (optional) | Eine Sammlung von Produkten und Dienstleistungen, die zusammen verkauft werden. Eine Opportunity umfasste oft verschiedene Phasen des Verkaufszyklus bis zum Abschluss des Verkaufs.<br>Sie würden Daten verwenden, um den Opportunity-Fortschritt durch den Verkaufstrichter zu messen. Beispiel: ein Bericht mit Details zu den wichtigsten Opportunitys, die von Phase 3 zu Phase 4 übergegangen sind. |
| Einkaufsgruppe (optional) | Eine Sammlung von Personen innerhalb einer Organisation, die am Entscheidungsprozess zum Kauf eines Produkts oder einer Dienstleistung beteiligt ist. <br/>Sie würden kaufende Gruppendaten verwenden, um Einkaufsgruppen über das Kampagnen-Management zu verfolgen. Erstellen Sie beispielsweise ein Zielgruppensegment aus wichtigen Einkaufsgruppen.<br/> Sie möchten wahrscheinlich eine Suche von der Einkaufsgruppe zu den Profildaten durchführen, damit Sie Berichte zu den Personen in einer Einkaufsgruppe erstellen können. |
| Person | Eine Person, die häufig durch eine eindeutige E-Mail-Adresse identifiziert wird, die mit dem Unternehmen interagiert hat. <br/>Sie würden die Profildaten verwenden, um Personen zu identifizieren, die für ein Konto arbeiten. Beispiel: Targeting aller Personen auf einem Konto, die sich für eine Konferenz angemeldet haben. |

>[!IMPORTANT]
>
>* Wenn Sie **aktiviert** den Container Globales Konto in einer kontobasierten Verbindung haben, sollte jeder Datensatz in Ihren Ereignisdatensätzen eine Konto-ID und eine globale Konto-ID enthalten. Andernfalls wird der Datensatz übersprungen.
>* Wenn Sie **nicht aktiviert** den Container Globales Konto in einer kontobasierten Verbindung aktiviert haben, sollte jeder Datensatz in Ihren Ereignisdatensätzen eine Konto-ID enthalten. Andernfalls wird der Datensatz übersprungen.

Sie können die B2B-Container für bestimmte B2B-Funktionen in Analysis Workspace verwenden:

* **Segmentierung**: Mit [B2B-Segment-Containern](/help/components/segments/seg-overview.md#b2b-containers) können Sie Segmente mit einem Container-Bereich außerhalb von Person, Sitzung oder Ereignis erstellen. Beispiel: ein Konto mit dem Segment „Ereignisregistrierung“ oder ein US-Konto mit dem Segment „Einkaufsgruppen“ und „Vertriebschancen“ der Stufe 5.

  >[!NOTE]
  >
  >Die B2B-Ereignisdaten in einer kontobasierten Einrichtung in Customer Journey Analytics B2B edition können Datenzeilen ohne Person oder Sitzung enthalten. Beispiel: Eine Zeile mit Details zum Fortschritt des Opportunity-Stadiums. Beachten Sie bei der Bewertung Ihres Segments, dass Personen und Sitzungen möglicherweise nicht mehr die richtigen Kriterien sind.
  >

* **Attribution**: Sie können die neuen B2B-Container im [Attributionsbereich](/help/analysis-workspace/c-panels/attribution.md), in [Attributionskomponenteneinstellungen](/help/data-views/component-settings/attribution.md), in [berechneten Metriken](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) oder in [Spalten in einer Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md). Account-Lookbacks werden auf 13 Monate verlängert.

* **Visualisierungen**: [Ausfallen](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), [Fluss](/help/analysis-workspace/visualizations/c-flow/flow.md), [Journey-Arbeitsfläche](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) und [Kohortentabelle](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) Visualisierungen unterstützen die neuen B2B-Container. Beispiel: Sie können die neuen Container verwenden, um zu verstehen, wie Einkaufsgruppen Inhalte konsumieren oder wie sich Opportunity-Kohorten dem Verkaufsabschluss nähern.
Sie können auch den Standard-Container für diese Visualisierungen unter [Benutzereinstellungen“ ](/help/analysis-workspace/user-preferences.md#visualizations-preferences).

Segmente, Attribution und Visualisierungen unterstützen Sie zusammen mit den B2B-Containern bei der umfassenden B2B-Analyse und bei der Erweiterung Ihrer Erkenntnisse.


## Datensätze

Customer Journey Analytics B2B unterscheidet zwischen den folgenden Datentypen und Datensätzen.

| Datentyp | Zeitreihe | Container-Datensätze | Feldeinträge |
|---|---|---|---|
| **Datensätze** | **Ereignisdatensätze**<br/> Beispiel:<ul><li>Digitale Analyse</li><li>CRM-Ereignisse</li><li>Persönliche Ereignisse</li><li>Callcenter-Daten</li></ul> | **Profildatensätze**<br/> Beispiel:<ul><li>CRM-Datensätze</li><li>AJO B2B-Einträge</li><li>CDP-Einträge</li><ul> | **Klassifizierungen**<br/> Beispiel:<ul><li>Kampagneneinträge</li><li>Einträge in der Marketing-Liste</li><li>Inhaltsmetadaten</li><li>Produktaufzeichnungen</li></ul> |
| Voraussetzungen | **Zeitstempel**<br> Jeder Datensatz benötigt:<ul><li>Konto-ID</li><li>ID des globalen Kontos</li><li>Personen-ID</li></ul> | **Konto-ID**<br> Datensätze benötigen eine Container-ID, z. B.:<ul><li>Konto</li><li>Person</li><li>Opportunity</li><li>Käufergruppe</li></ul> | **Übereinstimmende Schlüssel**<br> Datensätze benötigen eine ID, die in einem Container oder Ereignis-Datensatz enthalten ist, z. B.:<ul><li>Kampagnen-ID</li><li>Inhalts-ID</li><li>Produkt-ID</li></ul> |

{style="table-layout:fixed"}

Beispielhafte kontobasierte Verbindung in der Customer Journey Analytics B2B edition:

![Beispiel für eine kontobasierte Verbindung](assets/b2b-datasets.svg)

Customer Journey Analytics B2B edition bietet die [Verbindungszuordnung](/help/connections/create-connection.md#connection-map), um Ihnen einen Überblick über die Beziehungen zwischen Datensätzen in Ihrer Verbindung zu geben.


Ähnlich wie Customer Journey Analytics bilden ereignisbasierte Zeitreihendaten den Kern von Customer Journey Analytics B2B edition. Der Hauptunterschied bei einer kontobasierten Verbindung besteht darin, dass Sie für jeden Datensatz in Ihrem Ereignisdatensatz eine Konto-ID anstelle einer Personen-ID benötigen.

Beim Konfigurieren [Datensatzeinstellungen](/help/connections/create-connection.md#dataset-settings) für Ihre kontobasierte Verbindung in Customer Journey Analytics B2B edition hängen die für einige Einstellungen verfügbaren Optionen vom [Datensatztyp](/help/connections/create-connection.md#dataset-types) ab. Sie müssen beispielsweise:

* Geben Sie Kennungen für jeden der Container an, die Sie für Ihre Ereignis-Datensätze konfiguriert haben.
* Definieren Sie ein Kontofeld oder ein globales Kontofeld für Ihre Profildatensätze.
* Definieren Sie Schlüssel und wie diese Schlüssel (nach Container des Felds) für Lookup-Datensätze zugeordnet werden.

## Übereinstimmung nach Container oder Feld

Sie können für jeden Lookup-Datensatz definieren, unabhängig davon, ob Sie dem Datensatz nach Feld oder nach Container entsprechen.

### Übereinstimmung nach Container

Wenn ein Datensatzdatensatz eine Übereinstimmung nach Container verwendet, wird der Datensatzdatensatz in der Benutzeroberfläche als Profildatensatztyp und als Profildatensatz behandelt. Verwenden Sie „Übereinstimmung nach Container“ für Datensätze, die Container-Datensätze enthalten und die Ihre konfigurierten Container unterstützen. Beispiel: ein Datensatz für eine Einkaufsgruppe.

### Übereinstimmung nach Feld

Wenn ein Datensatzdatensatz ein Feld vom Typ Übereinstimmung verwendet, wird der Datensatzdatensatz in der Benutzeroberfläche als Such-Datensatztyp und als Such-Datensatz behandelt. Verwenden Sie das Feld „Übereinstimmung nach“ für Datensätze, die zusätzliche Klassifizierungsdetails über die Suche enthalten. Beispiel: ein Marketing-Listenmitglied-Datensatz oder ein Produktdetails-Datensatz.


## Bericht zu Personen- und Account-basierten Daten

Wenn Sie Berichte zu personenbasierten Containern (und Personenidentitäten) und kontobasierten Containern (und Kontoidentitäten) erstellen möchten, sollten Sie zwei separate Verbindungen innerhalb von Customer Journey Analytics einrichten. Eine Verbindung, bei der Sie Person als Primäre ID auswählen, und eine Verbindung, bei der Sie Account als Primäre ID auswählen. Customer Journey Analytics unterstützt keine personenbasierten und kontobasierten Berichte aus einer einzelnen Container-Hierarchie.

