---
description: Erfahren Sie, wie sich Warnhinweise in Customer Journey Analytics von Adobe Analytics unterscheiden
title: Funktionsvergleich von Warnhinweisen zwischen Customer Journey Analytics und Adobe Analytics
feature: Workspace Basics
role: User, Admin
exl-id: 04e819c4-9fb5-4459-9f8b-40d78385ed90
TQID: https://experienceleague.adobe.com/NEm3Mu7q6RDKbCyG-PJzOFPrjJF4Y-unHgyBXyKd1HM
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
    internal-label: Workspace basics
  - id: e4a0bad2-b448-47f1-9fa6-222ebdb3b5b0
    internal-label: Alerts
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 4f3c4a214bb9676ced6fe3c9627c969413013790
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 23%
---
# Funktionsvergleich von Warnhinweisen zwischen Customer Journey Analytics und Adobe Analytics

Die Verwendung von Warnhinweisen in Customer Journey Analytics ist nahezu identisch mit der Verwendung von Warnhinweisen in Adobe Analytics. Es gibt jedoch wichtige Unterschiede. In den folgenden Abschnitten werden die wichtigsten Unterschiede beschrieben.

## Stündliche Warnhinweise können für bestimmte Datentypen nicht sinnvoll sein

Da Sie verschiedene Datentypen in Adobe Experience Platform aufnehmen können, sind nicht alle Daten, die in einem Warnhinweis enthalten sein können, für einen stündlichen Warnhinweis geeignet. Bestimmte Datentypen können innerhalb einer Stunde nicht zuverlässig erfasst und verfügbar sein.

Weitere Informationen finden Sie unter [Datenaufnahmezeiten variieren](#data-ingestion-times-vary).

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

## Weniger Möglichkeiten zum Erstellen von Warnhinweisen

In Analysis Workspace in Adobe Analytics können Sie [Warnhinweise aus Analysis Workspace auf verschiedene Arten erstellen](https://experienceleague.adobe.com/en/docs/analytics/components/alerts/alert-builder). In Customer Journey Analytics können Sie [Warnhinweis erstellen](alert-builder.md) in Analysis Workspace nur aus einer Auswahl in einer Freiformtabelle erstellen.

Sowohl Adobe Analytics als auch Customer Journey Analytics unterstützen die Erstellung von Warnhinweisen über den [Warnhinweis-Manager](alert-manager.md)
