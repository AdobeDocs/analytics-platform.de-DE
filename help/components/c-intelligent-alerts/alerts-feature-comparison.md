---
description: Erfahren Sie, wie sich Warnhinweise in Customer Journey Analytics von Adobe Analytics unterscheiden
title: Funktionsvergleich von Warnhinweisen Customer Journey Analytics und Adobe Analytics
feature: Workspace Basics
role: User, Admin
exl-id: 04e819c4-9fb5-4459-9f8b-40d78385ed90
source-git-commit: 9e07dfc84bc06aef987d99c225cefb4e0406f552
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 24%

---

# Vergleich der Funktionen von Warnhinweisen

Die Verwendung von Warnhinweisen in Customer Journey Analytics ist nahezu identisch mit der Verwendung von Warnhinweisen in Adobe Analytics. Es gibt jedoch wichtige Unterschiede. In den folgenden Abschnitten werden die wichtigsten Unterschiede beschrieben.

## Stündliche Warnhinweise sind nicht verfügbar

Stündliche Warnhinweise sind **nicht** in Customer Journey Analytics verfügbar, während stündliche Warnhinweise in Adobe Analytics verfügbar sind. In Customer Journey Analytics können tägliche, wöchentliche oder monatliche Warnhinweise konfiguriert werden.

Sie haben verschiedene Möglichkeiten, Daten in Adobe Experience Platform aufzunehmen. Daher können die Vollständigkeit und Verfügbarkeit von Daten innerhalb einer Stunde nicht zuverlässig erreicht werden.  Die Flexibilität bei der Datenerfassung bedeutet, dass stündliche Warnhinweise aufgrund des hohen Potenzials für unvollständige Daten unpraktisch sind. Weitere Informationen finden Sie unter [Datenaufnahmezeiten variieren](#data-ingestion-times-vary-in-customer-journey-analytics).

## Die Datenerfassungszeiten variieren

Die Zeit, die erforderlich ist, bevor Daten abgeschlossen sind und für Berichte in Customer Journey Analytics zur Verfügung stehen, variiert je nach Unternehmen.

Dies hat folgende Gründe:

* Die Fähigkeit von Platform, alle Arten von Datenschemata und -typen zu speichern

  Im Gegensatz zu Adobe Analytics (das nur über Web-Daten berichtet) [viele verschiedene Datentypen in Adobe Experience Platform aufgenommen werden](/help/data-ingestion/data-ingestion.md) um in Customer Journey Analytics berichtet zu werden, und nicht alle Datentypen können sequenziell und in Echtzeit gesendet werden.

* Verzögerung bei der Bereitstellung von Batch-Daten an Platform-Datensätze

  Während einige Daten möglicherweise früher für Berichte verfügbar sind, werden alle [Batch-Daten in einen Platform-Datensatz aufgenommen](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.) normalerweise zwischen 3 und 9 Stunden nach der Datenereigniszeit. Damit Warnhinweise korrekt sind, muss die Datenaufnahme vollständig sein, wobei alle Batch-Daten im Datensatz verfügbar sein müssen. <!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

Aus diesen Gründen wird die Datenaufnahme für die verschiedenen Arten von Ereignisdaten, die aufgenommen werden können, erst nach einer gewissen Verzögerung abgeschlossen, die normalerweise 3 bis 9 Stunden nach der Datenereigniszeit liegt. Damit Warnhinweise genau sind, müssen Ereignisdaten für einen bestimmten Ereignisbereich vollständig sein. Das bedeutet, dass Adobe für den angegebenen Ereignisbereich keine Ereignisdaten mehr erhält.

Um diese Verzögerung bei der Aufnahmezeit zu berücksichtigen, haben Warnhinweise standardmäßig eine Verzögerung von 9 Stunden, bevor sie gesendet werden.

Sie können die Standardverzögerung von 9 Stunden auf einen Wert zwischen 0 und 24 Stunden anpassen. Wenn Sie die Verzögerung jedoch auf weniger als 9 Stunden verkürzen, kann dies bedeuten, dass für Berichte unvollständige Daten vorliegen, was zu ungenauen Warnhinweisinformationen führt.

Weitere Informationen zum Anpassen der Verzögerung und die dabei zu berücksichtigenden Faktoren finden Sie unter [Erstellen von Warnhinweisen](/help/components/c-intelligent-alerts/alert-builder.md).

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## Warnhinweis erstellen

In Analysis Workspace in Adobe Analytics können Sie [Warnhinweise aus Analysis Workspace auf verschiedene Arten erstellen](https://experienceleague.adobe.com/de/docs/analytics/components/alerts/alert-builder). In Customer Journey Analytics können Sie [Warnhinweis erstellen](alert-builder.md) in Analysis Workspace nur aus einer Auswahl in einer Freiformtabelle erstellen.

Sowohl Adobe Analytics als auch Customer Journey Analytics unterstützen die Erstellung von Warnhinweisen über den [Warnhinweis-Manager](alert-manager.md)
