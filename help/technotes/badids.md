---
title: Ungültige Customer Journey Analytics-IDs
description: Ungültige IDs (BAVIDs) in Customer Journey Analytics verstehen. Erfahren Sie, wie Sie fehlerhafte IDs in Ihren Daten identifizieren, warum sie sich auf das Reporting auswirken und wie Sie die Gefährdung durch fehlerhafte IDs in Ihren Verbindungen untersuchen und beheben können.
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: 4f71fbf2-290b-4076-b2ad-b086c2b854d9
autotag-review: '2026-05-19T06:53:00.572Z'
TQID: 'https://experienceleague.adobe.com/6vut30l-BSIxhTK96Tt3BG01q-rjHagcmer0WZ2GL-c'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 632
ht-degree: 2%

---

# Ungültige IDs

Dieser Artikel bietet Kontext zu ungültigen IDs und beschreibt, wie Sie mithilfe des Abfrage-Service feststellen können, ob diese in Ihren Daten vorhanden sind oder wie das Risiko eines Auftretens auftritt.


>[!INFO]
>
>Fehlerhafte IDs werden in der Customer Journey Analytics-Benutzeroberfläche auch als BAVIDs bezeichnet (stammen von [Analytics BAVID](https://experienceleague.adobe.com/de/docs/experience-cloud-kcs/kbarticles/ka-16444)).
>

## Definition

In Customer Journey Analytics ist eine ungültige ID ein Bezeichner, da sie Teil aller in einer Verbindung definierten Daten ist:

* mit einem bestimmten ID-Wert, der stammt
   * aus einem Personen-ID-Feld (nicht zugeordnete Datensätze) **oder**
   * von einer persistenten ID oder einem Personen-ID-Feld (Zusammenfügen von -aktivierten Datensätzen) aus,

  **und**
* ist auf mehr als eine Million (1.000.000) Ereignisse in den Verbindungsdaten (gezählt für alle Datensätze innerhalb der Verbindung) innerhalb eines Monats.

Wenn ein ID-Wert als ungültige ID markiert wird, werden alle zukünftigen Ereignisse, die diesen ID-Wert enthalten, aus den Verbindungsdaten verworfen und nicht im Bericht angezeigt.

### Beispiel

Ein Beispiel für ein Szenario mit ungültigen IDs sind benutzerdefinierte Werte oder Platzhalterwerte im Feld für die Personen-ID (z. B. `undefined`für anonymen Traffic). Bei einem Datensatz mit aktivierter Zuordnung kann diese Situation sogar noch größere Auswirkungen auf die Berichtsdaten haben, da die Zuordnungsqualität höchstwahrscheinlich beeinträchtigt ist. Um dies zu beheben, müssen Sie möglicherweise die Zusammenfügungseinrichtung löschen und erneut aktivieren, einschließlich des Löschens historischer Daten von Datensätzen in der Verbindung.


## Metriken

Die Customer Journey Analytics-Verbindungsschnittstelle bietet **[!UICONTROL ungültige IDs]** Metrikinformationen an verschiedenen Stellen in der Benutzeroberfläche.

* Sie sehen **[!UICONTROL Ungültige IDs]** (oder **[!UICONTROL BAVIDs]**) als mögliche Gründe für das Überspringen von Datensätzen im Dialogfeld **[!UICONTROL Übersprungene Details überprüfen]**. Verwenden Sie **[!UICONTROL Detail überprüfen]** (falls verfügbar) unter **[!UICONTROL Datensätze übersprungen]** im [Detailbildschirm einer Verbindung](/help/connections/create-connection.md).
* Für einen Datensatz mit aktiviertem Stitching zeigt [**[!UICONTROL Datensatzvorschau]**](/help/stitching/use-stitching-ui.md#bad-ids) &quot;**[!UICONTROL IDs]** als Teil der **[!UICONTROL Zuordnungsmetriken]** an. Diese Metrik kann Ihnen dabei helfen, mögliche Fälle falscher IDs zu identifizieren. Beachten Sie jedoch, dass diese Metrik auf der Grundlage eines begrenzten Satzes von Daten berechnet wird.

Unter [Gefährdung durch ungültige IDs](#bad-ids-exposure) erfahren Sie, wie Sie fehlerhafte IDs für einen Datensatz identifizieren, den Sie in einer Verbindung verwenden möchten (unabhängig davon, ob die Zuordnung aktiviert ist oder nicht).


## Aufdeckung

Um die Gefährdung durch ungültige IDs für ein bestimmtes Datensatzfeld zu untersuchen, sollten Sie die folgende Abfrage im Abfrage-Service von Experience Platform durchführen. Überprüfen Sie die am häufigsten zurückgegebenen ID-Werte, um festzustellen, ob Kandidaten für ungültige IDs vorhanden sind. Beachten Sie, dass die [Definition für ungültige ID](#definition) alle Datensätze innerhalb der Verbindung berücksichtigt.


### Identifizieren (Risiko) falscher IDs innerhalb eines Felds

Sie können den Abfrage-Service von Experience Platform verwenden, um das potenzielle Risiko ungültiger IDs innerhalb eines Felds zu identifizieren.

Die nachstehende Abfrage gibt die ersten 20 ID-Werte aus einem Feld zurück. In absteigender Reihenfolge nach Anzahl der Gesamtereignisse. Dabei wird jeder Wert innerhalb eines bestimmten Intervalls (z. B. innerhalb der letzten 30 Tage) erkannt.

Führen Sie diese Abfrage für ein bestimmtes Personen-ID-Feld aus, das Sie analysieren möchten. Bei einem Datensatz, der zugeordnet werden muss, können Sie auch die Abfrage für ein persistentes ID-Feld ausführen.

```sql
SELECT
    /* INSERT FIELD HERE */,
    COUNT(*) AS occurrences
FROM /* INSERT DATASET TABLE NAME HERE */
WHERE timestamp >= NOW() - INTERVAL '30 days' 
GROUP BY /* INSERT FIELD HERE */
ORDER BY occurrences DESC
LIMIT 20; 
```

Ersetzen Sie in der Abfrage `INSERT FIELD HERE` je nach dem Typ des Felds, das Sie auf ungültige IDs untersuchen:

* `full.field.path.from.XDM.schema` (für Zeichenfolgenfelder, die im XDM-Schema definiert sind)
* `identityMap['namespace_value'][0].id` (für Felder, die mit `namespace_value` in `identityMap` definiert wurden)

Überprüfen Sie die Ergebnisse, um festzustellen, ob problematische ID-Werte vorhanden sind. Wie benutzerdefinierte Werte oder Platzhalterwerte oder Werte mit hoher Häufigkeit, die innerhalb eines Monats auf der Verbindungsdatenebene auf fast 1 Million ansteigen oder kommen könnten.
Selbst wenn sich Ihre Implementierung noch in der Entwicklungsphase befindet, sollten Sie das Risiko des Vorhandenseins falscher IDs bewerten, sobald die Einrichtung stabil und für die Produktion bereit ist.
