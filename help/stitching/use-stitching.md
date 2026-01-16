---
title: Anfordern der Zuordnung
description: So fordern Sie die Zuordnung an
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
source-git-commit: d117ba255151f730e0b5e4958ee56f5ffc88ade9
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 7%

---

# Anfordern der Zuordnung

Sobald Ihr Unternehmen alle [Voraussetzungen](overview.md#prerequisites) erfüllt und die gängigen [Einschränkungen](overview.md#limitations) und Stitching-Methodenspezifischen ([feldbasiert](fbs.md#limitations) und [diagrammbasiert](gbs.md#limitations)) Einschränkungen versteht, können Sie diese Schritte ausführen, um das Stitching in Customer Journey Analytics anzufordern und zu verwenden.

## Optionen auswählen

Das Customer Journey Analytics-Paket, zu dem Sie berechtigt sind, bestimmt die verfügbaren Stitching-Methoden, Optionen für die anfängliche Aufstockungsdauer, das Lookback-Fenster, die Wiederholungshäufigkeit und die maximale Anzahl von Datensätzen, die für das Stitching zulässig sind. Weitere Informationen finden Sie in der {0[ Customer Journey Analytics-Produktbeschreibung. ](https://helpx.adobe.com/de/legal/product-descriptions/customer-journey-analytics.html) Vor der Supportanfrage über die verfügbaren Optionen entscheiden.

| | Customer Journey Analytics-<br/> | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Verfügbare Stitching-Methoden | Feldbasierte Zuordnung | Feldbasiertes Stitching<br/>Diagrammbasiertes Stitching | Feldbasiertes Stitching<br>Diagrammbasiertes Stitching</li> |
| Einmaliges Zusammenfügen der Aufstockungsdauer | 13 Monate | 13 Monate | 25 Monate |
| Lookback-Fenster und Wiederholungshäufigkeit | 1 Tag, jeden Tag<br/> bis zu 7 Tage, wöchentlich | 1 Tag, jeden Tag<br/> bis zu 14 Tage, wöchentlich | 1 Tag, jeden Tag<br/> bis zu 30 Tage, wöchentlich |
| Maximal zulässige Anzahl von Datensätzen für das Zusammenfügen | 5 | 15 | 50 |

## Support anfordern

1. Wenden Sie sich mit den folgenden Informationen an den Adobe-Support:

   - Eine Anfrage zum Aktivieren der Zuordnung.
   - Die Datensatz-ID für den Datensatz, den Sie neu zuweisen möchten.
   - Der Spaltenname (Identitätspfad und Namespace) der persistenten ID für den gewünschten Datensatz (die Kennung, die in jeder Zeile angezeigt wird).
   - Wenn der Datensatz `identityMap` unterstützt:
      - Geben Sie für das feldbasierte Stitching den Namespace für die persistenten und Personen-IDs an.
      - Geben Sie für das diagrammbasierte Stitching den Namespace für die persistente ID und den Identity-Namespace an, der für die Abfrage des Identitätsdiagramms verwendet werden soll.
   - Wenn der Datensatz `identityMap` nicht unterstützt:
      - Bei feldbasiertem Stitching der Spaltenname der Personen-ID für den gewünschten Datensatz (die Personenkennung, die auch als Link zwischen Datensätzen im Kontext einer Verbindung dient).
      - Bei der diagrammbasierten Zuordnung der Identity-Namespace, der für die Abfrage des Identitätsdiagramms verwendet werden soll.
   - Ihre Voreinstellung für Lookback-Fenster und Wiederholungshäufigkeit. In Ihrem Customer Journey Analytics-Paket finden Sie [Optionen](#options) verfügbar.
   - Sandbox-Name.


2. Der Adobe-Kunden-Support arbeitet mit dem Adobe-Engineering zusammen, um die Zuordnung nach Erhalt Ihrer Anfrage zu ermöglichen. Nach der Aktivierung wird in Adobe Experience Platform ein neu verschlüsselter Datensatz angezeigt, der eine zugeordnete ID-Spalte enthält. Der Adobe-Kunden-Support kann die ID des neuen Datensatzes bereitstellen.
3. Nach der ersten Aktivierung stellt Adobe eine Aufstockung der zusammengefügten Daten bereit. In Ihrem Customer Journey Analytics-Paket finden Sie die [Option](#options).

4. Wenn Sie den zusammengefügten Datensatz in einer Cross-Channel-Analyse verwenden möchten, müssen Sie den zusammengefügten Datensatz zu einer [Verbindung](../connections/overview.md) in Customer Journey Analytics hinzufügen. Fügen Sie dann alle anderen für die kanalübergreifende Analyse erforderlichen Datensätze hinzu und wählen Sie die richtige Personen-ID für jeden Datensatz aus.

5. [Erstellen Sie eine Datenansicht](/help/data-views/create-dataview.md) auf Grundlage der Verbindung.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Nachdem die Datenansicht eingerichtet wurde, können Sie Ihre Customer Journey Analytics-Berichtsanalyse kanalübergreifend und geräteübergreifend ausführen.

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
