---
title: Stitching verwenden
description: Verwendung des Stitching
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
source-git-commit: 5e25cb4d974ab85cca3aa2bb777675e12f63038b
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 9%

---

# Stitching verwenden

Sobald Ihr Unternehmen alle [Voraussetzungen](#prerequisites) erfüllt und die gängigen [Einschränkungen](#limitations) und Stitching-Methodenspezifischen ([feldbasiert](#limitations-1) und [grafikbasiert](#limitations-2)) Einschränkungen versteht, können Sie diese Schritte ausführen, um mit dem Stitching in Customer Journey Analytics zu beginnen.

## Optionen auswählen

Das Customer Journey Analytics-Paket, für das Sie berechtigt sind, legt die verfügbaren Stitching-Methoden, Optionen für die anfängliche Aufstockungsdauer, das Lookback-Fenster, die Wiederholungshäufigkeit und die maximale Anzahl der für das Stitching zulässigen Datensätze fest. Weitere Informationen finden Sie in der [Customer Journey Analytics-Produktbeschreibung](https://helpx.adobe.com/de/legal/product-descriptions/customer-journey-analytics.html) . Entscheiden Sie sich für die verfügbaren Optionen, bevor Sie Support anfordern.

| | Customer Journey Analytics<br/>Select | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Verfügbare Stitverfahren | <li>Feldbasiertes Stitching</li> | <li>Feldbasiertes Stitching</li><li>Grafikbasierte Zuordnung</li> | <li>Feldbasiertes Stitching</li><li>Grafikbasierte Zuordnung</li> |
| Dauer der einmaligen Zuordnung von Aufstockungen | 13 Monate | 13 Monate | 25 Monate |
| Lookback-Fenster und Wiederholungshäufigkeit | <li>1 Tag, jeden Tag</li><li>bis zu 7 Tage, wöchentlich</li> | <li>1 Tag, jeden Tag</li><li>bis zu 14 Tage, wöchentlich</li> | <li>1 Tag, jeden Tag</li><li>bis zu 30 Tage, wöchentlich</li> |
| Maximale Anzahl an Datensätzen, die für das Stitching zulässig sind | 5 | 10 | 50 |

## Support anfordern

1. Wenden Sie sich mit den folgenden Informationen an den Adobe-Support:

   - Eine Anfrage zum Aktivieren der Zuordnung.
   - Die Datensatz-ID für den Datensatz, den Sie neu zuweisen möchten.
   - Der Spaltenname (Identitätspfad und Namespace) der beständigen ID für den gewünschten Datensatz (die Kennung, die in jeder Zeile angezeigt wird).
   - Beim feldbasierten Stitching ist der Spaltenname der vorübergehenden ID für den gewünschten Datensatz (die Personenkennung, die auch als Verknüpfung zwischen Datensätzen im Kontext einer Verbindung dient). Bei der grafikbasierten Zuordnung der Identitäts-Namespace, der zum Abfragen des Identitätsdiagramms verwendet werden soll.
   - Ihre Voreinstellung für das Lookback-Fenster und die Wiederholungshäufigkeit. In Ihrem Customer Journey Analytics-Paket finden Sie die verfügbaren [options](#options).
   - Sandbox-Name.


2. Der Adobe-Kundensupport arbeitet mit Adobe-Engineering zusammen, um das Stitching nach Erhalt Ihrer Anfrage zu aktivieren. Nach der Aktivierung wird in Adobe Experience Platform ein neuer neu zugewiesener Datensatz mit einer neuen Spalte für die zugeordnete ID angezeigt. Der Adobe-Kundensupport kann die ID des neuen Datensatzes angeben.

3. Wenn die Option zum ersten Mal aktiviert ist, stellt Adobe eine Aufstockung der zugewiesenen Daten bereit. In Ihrem Customer Journey Analytics-Paket finden Sie die verfügbare [Option](#options).

4. Wenn Sie den neuen zugewiesenen Datensatz in einer kanalübergreifenden Analyse verwenden möchten, müssen Sie den neuen zugewiesenen Datensatz zu einer [connection](../connections/overview.md) in Customer Journey Analytics hinzufügen. Fügen Sie dann alle weiteren Datensätze hinzu, die für die kanalübergreifende Analyse erforderlich sind, und wählen Sie die richtige Personen-ID für jeden Datensatz aus.

5. [Erstellen Sie eine Datenansicht](/help/data-views/create-dataview.md) auf Grundlage der Verbindung.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Sobald die Datenansicht eingerichtet ist, können Sie Ihre Customer Journey Analytics-Berichtsanalyse kanalübergreifend und geräteübergreifend ausführen.

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->



