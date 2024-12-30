---
description: Erfahren Sie, wie sich Warnhinweise beim Customer Journey Analytics von Adobe Analytics unterscheiden
title: Customer Journey Analytics mit Funktionsvergleich für Warnhinweise und Adobe Analytics
feature: Workspace Basics
role: User, Admin
exl-id: 04e819c4-9fb5-4459-9f8b-40d78385ed90
source-git-commit: daa07b603caa613ca49b61c2e8e461d558459f57
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 5%

---

# Vergleich der Funktionen von Warnhinweisen

Die Verwendung von Warnhinweisen in Customer Journey Analytics ist nahezu identisch mit der Verwendung von Warnhinweisen in Adobe Analytics. Es gibt jedoch wichtige Unterschiede. In den folgenden Abschnitten werden die wichtigsten Unterschiede beschrieben.

## Stündliche Warnhinweise sind nicht auf Customer Journey Analytics verfügbar

Stündliche Warnhinweise sind in Customer Journey Analytics nicht verfügbar wie in Adobe Analytics. In Customer Journey Analytics können tägliche, wöchentliche oder monatliche Warnhinweise konfiguriert werden.

Dies liegt an den verschiedenen Möglichkeiten, Daten in Adobe Experience Platform aufzunehmen, bevor sie auf Customer Journey Analytics gemeldet werden. Die Vollständigkeit und Verfügbarkeit von Daten kann nicht zuverlässig innerhalb einer Stunde erreicht werden, sodass stündliche Warnhinweise aufgrund des hohen Potenzials für unvollständige Daten unpraktisch sind. Weitere Informationen finden Sie unter [Datenaufnahmezeiten variieren](#data-ingestion-times-vary-in-customer-journey-analytics).

## Die Datenaufnahmezeiten variieren beim Customer Journey Analytics

Die Zeit, die erforderlich ist, bevor Daten vollständig sind und zum Customer Journey Analytics berichtet werden können, variiert je nach Unternehmen.

Dies hat folgende Gründe:

* Die Fähigkeit von Platform, alle Arten von Datenschemata und -typen zu speichern

  Im Gegensatz zu Adobe Analytics (das nur über Web-Daten berichtet) [viele verschiedene Datentypen in Adobe Experience Platform aufgenommen werden](/help/data-ingestion/data-ingestion.md) um auf Customer Journey Analytics berichtet zu werden, und nicht alle Datentypen können sequenziell und in Echtzeit gesendet werden.

* Verzögerung bei der Bereitstellung von Batch-Daten an Platform-Datensätze

  Während einige Daten möglicherweise früher für Berichte verfügbar sind, werden alle [Batch-Daten in einen Platform-Datensatz aufgenommen](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.) normalerweise zwischen 3 und 9 Stunden nach der Datenereigniszeit. Damit Warnhinweise korrekt sind, muss die Datenaufnahme vollständig sein, wobei alle Batch-Daten im Datensatz verfügbar sein müssen. <!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

Aus diesen Gründen wird die Datenaufnahme für die verschiedenen Arten von Ereignisdaten, die aufgenommen werden können, erst nach einer gewissen Verzögerung abgeschlossen, die normalerweise 3 bis 9 Stunden nach der Datenereigniszeit liegt. Damit Warnhinweise genau sind, müssen Ereignisdaten für einen bestimmten Ereignisbereich vollständig sein. Das bedeutet, dass Adobe für den angegebenen Ereignisbereich keine Ereignisdaten mehr erhält.

Um diese Verzögerung bei der Aufnahmezeit zu berücksichtigen, haben Warnhinweise standardmäßig eine Verzögerung von 9 Stunden, bevor sie gesendet werden.

Sie können die Standardverzögerung von 9 Stunden auf einen Wert zwischen 0 und 24 Stunden anpassen. Wenn Sie die Verzögerung jedoch auf unter 9 Stunden verkürzen, kann dies bedeuten, dass Sie unvollständige Daten melden, was zu ungenauen Warnhinweisinformationen führt.

Weitere Informationen zum Anpassen der Verzögerung und die dabei zu berücksichtigenden Faktoren finden Sie unter [Erstellen von Warnhinweisen](/help/components/c-intelligent-alerts/alert-builder.md).

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## Die Option zum Erstellen eines Warnhinweises in Analysis Workspace ist nicht verfügbar

In Analysis Workspace in Adobe Analytics können Sie Warnhinweise aus Analysis Workspace auf eine der unten beschriebenen Arten erstellen. Beim Customer Journey Analytics sind die Optionen zum Erstellen von Warnhinweisen von Analysis Workspace noch nicht verfügbar. Greifen Sie stattdessen auf die Warnhinweiserstellung zu, wie in [Warnhinweise erstellen](/help/components/c-intelligent-alerts/alert-builder.md) beschrieben.

In Adobe Analytics sind die folgenden Optionen verfügbar:

* Wählen Sie mindestens ein Zeilenelement in einer Freiformtabelle aus, klicken Sie mit der rechten Maustaste darauf und wählen Sie **[!UICONTROL Warnhinweis aus Auswahl erstellen]**.

  Dadurch wird die Warnhinweiserstellung sofort vorab ausgefüllt, um einen Warnhinweis mit den richtigen Metriken und Filtern zu erstellen.

* Öffnen Sie ein Projekt in Analysis Workspace und wählen Sie **[!UICONTROL Komponenten]** > **[!UICONTROL Warnhinweis erstellen]**.

* Öffnen Sie ein Projekt in Analysis Workspace und verwenden Sie dann den folgenden Tastaturbefehl: **[!UICONTROL *Strg *]**+**[!UICONTROL * Umschalt *]** + **[!UICONTROL *a *]**(Windows) oder**[!UICONTROL * cmd *]** + **[!UICONTROL *Umschalt *]**+**[!UICONTROL * a *]** (macOS).
