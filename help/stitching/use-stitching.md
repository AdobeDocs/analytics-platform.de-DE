---
title: Zuordnung anfordern
description: Erfahren Sie, wie Sie das Zusammenfügen von Anfragen anfordern.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
source-git-commit: cbb18e9d0990d5df64995c2dabe8362c7c37bb45
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 26%

---

# Anfordern der Zuordnung


>[!IMPORTANT]
>
>Das Zusammenfügen von Anfragen über Adobe ist nicht mehr erforderlich und diese Methode ist veraltet. [Aktivieren Sie das Zusammenfügen in der Verbindungs-Benutzeroberfläche](use-stitching-ui.md).
>

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
      - Bei der diagrammbasierten Zuordnung der Identity-Namespace, den Sie für die Abfrage des Identitätsdiagramms verwenden möchten.
   - Ihre Voreinstellung für Lookback-Fenster und Wiederholungshäufigkeit. In Ihrem Customer Journey Analytics-Paket finden Sie [Optionen](#options) verfügbar.
   - Sandbox-Name.


2. Der Adobe-Kunden-Support arbeitet mit dem Adobe-Engineering zusammen, um die Zuordnung nach Erhalt Ihrer Anfrage zu ermöglichen. Nach der Aktivierung wird in Adobe Experience Platform ein neu verschlüsselter Datensatz angezeigt, der eine zugeordnete ID-Spalte enthält. Der Adobe-Kunden-Support kann die ID des neuen Datensatzes bereitstellen.
3. Nach der ersten Aktivierung stellt Adobe eine Aufstockung der zusammengefügten Daten bereit. In Ihrem Customer Journey Analytics-Paket finden Sie die [Option](#options).

4. Wenn Sie den zusammengefügten Datensatz in einer Cross-Channel-Analyse verwenden möchten, müssen Sie den zusammengefügten Datensatz zu einer [Verbindung](../connections/overview.md) in Customer Journey Analytics hinzufügen. Fügen Sie dann alle anderen für die kanalübergreifende Analyse erforderlichen Datensätze hinzu und wählen Sie die richtige Personen-ID für jeden Datensatz aus.

5. [Erstellen Sie eine Datenansicht](/help/data-views/create-dataview.md) auf Grundlage der Verbindung.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Nachdem die Datenansicht eingerichtet wurde, können Sie Ihre Customer Journey Analytics-Berichtsanalyse kanalübergreifend und geräteübergreifend ausführen.

## Einschränkungen

- Wenden Sie alle Änderungen, die Sie am Quellereignis-Datensatzschema vornehmen, auch auf das neue Schema des zugeordneten Datensatzes an.

- Wenn Sie den Quelldatensatz entfernen, wird der zugeordnete Datensatz nicht weiter verarbeitet und vom System entfernt.

- Labels zur Datennutzung werden nicht automatisch in das zugeordnete Datensatzschema übertragen. Wenn Sie Labels zur Datennutzung auf das Quelldatensatzschema angewendet haben, müssen Sie diese Labels zur Datennutzung manuell auf das Schema des zugeordneten Datensatzes anwenden. Weitere Informationen dazu finden Sie unter [Verwalten von Labels zur Datennutzung in Experience Platform](https://experienceleague.adobe.com/de/docs/experience-platform/data-governance/labels/overview).
