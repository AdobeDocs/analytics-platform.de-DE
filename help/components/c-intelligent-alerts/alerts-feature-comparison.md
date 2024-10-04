---
description: Erfahren Sie, wie sich Warnhinweise beim Customer Journey Analytics von Adobe Analytics unterscheiden.
title: Customer Journey Analytics und Adobe Analytics zum Vergleich von Warnhinweisen
feature: Workspace Basics
role: User, Admin
source-git-commit: 1dff53e244e5d231e7075ce087705e33e0978096
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 5%

---

# Vergleich der Warnhinweise-Funktion

Die Verwendung von Warnhinweisen in Customer Journey Analytics ist nahezu identisch mit der Verwendung von Warnhinweisen in Adobe Analytics. Es gibt jedoch wichtige Unterschiede. In den folgenden Abschnitten werden die wichtigsten Unterschiede beschrieben.

## Stündliche Warnhinweise sind nicht im Customer Journey Analytics verfügbar

Stündliche Warnhinweise sind nicht wie in Adobe Analytics auf dem Customer Journey Analytics verfügbar. In Customer Journey Analytics können tägliche, wöchentliche oder monatliche Warnhinweise konfiguriert werden.

Dies liegt an den verschiedenen Möglichkeiten, wie Daten in Adobe Experience Platform aufgenommen werden können, bevor sie in Customer Journey Analytics gemeldet werden. Datenvollständigkeit und -verfügbarkeit können nicht zuverlässig innerhalb einer Stunde erreicht werden, sodass stündliche Warnhinweise aufgrund des hohen Potenzials unvollständiger Daten nicht praktikabel sind. Weitere Informationen finden Sie unter [Datenerfassungszeiten variieren](#data-ingestion-times-vary-in-customer-journey-analytics).

## Die Datenerfassungszeiten variieren je nach Customer Journey Analytics

Die Zeit, die erforderlich ist, bevor die Daten vollständig sind und zur Verfügung stehen, um auf der Customer Journey Analytics gemeldet zu werden, variiert je nach Organisation.

Dies liegt an den folgenden Gründen:

* Fähigkeit von Platform, alle Arten von Datenschemata und -typen zu speichern

  Im Gegensatz zu Adobe Analytics (die nur Webdaten meldet) können [viele verschiedene Datentypen in Adobe Experience Platform](/help/data-ingestion/data-ingestion.md) aufgenommen werden, um in Customer Journey Analytics gemeldet zu werden. Nicht alle Datentypen können sequenziell und in Echtzeit gesendet werden.

* Verzögerung bei der Bereitstellung von Batch-Daten an Platform-Datensätze

  Auch wenn einige Daten möglicherweise bereits früher für Berichte verfügbar sind, werden alle [Batch-Daten in einen Platform-Datensatz](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.) erfasst, in der Regel zwischen 3 und 9 Stunden nach der Ereignis-Zeit. Damit Warnhinweise korrekt sind, muss die Datenerfassung abgeschlossen sein und alle Batch-Daten im Datensatz verfügbar sein. <!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

Aus diesen Gründen ist die Datenerfassung für die verschiedenen Arten von Ereignisdaten, die erfasst werden können, erst nach einiger Verzögerung abgeschlossen, in der Regel zwischen 3 und 9 Stunden nach der Datenereigniszeit. Damit Warnhinweise akkurat sind, müssen die Ereignisdaten für einen bestimmten Ereignisbereich vollständig sein, d. h. Adobe empfängt keine Ereignisdaten mehr für den angegebenen Ereignisbereich.

Um diese Verzögerung bei der Erfassungszeit zu berücksichtigen, dauert es standardmäßig neun Stunden, bis Warnhinweise gesendet werden.

Sie können die Standardverzögerung von 9 Stunden auf einen beliebigen Wert zwischen 0 und 24 Stunden einstellen. Eine Verringerung der Verzögerung auf unter 9 Stunden kann jedoch bedeuten, dass Sie über unvollständige Daten berichten, was zu ungenauen Warnhinweisinformationen führt.

Weitere Informationen zum Anpassen der Verzögerung und der Faktoren, die Sie dabei berücksichtigen sollten, finden Sie unter [Warnhinweise erstellen](/help/components/c-intelligent-alerts/alert-builder.md).

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## Die Option, einen Warnhinweis aus Analysis Workspace zu erstellen, ist nicht verfügbar

In Analysis Workspace in Adobe Analytics können Sie Warnhinweise aus Analysis Workspace auf eine der unten beschriebenen Arten erstellen. Unter Customer Journey Analytics sind die Optionen zum Erstellen von Warnhinweisen aus Analysis Workspace noch nicht verfügbar. Greifen Sie stattdessen auf die Warnhinweiserstellung zu, wie in [Warnhinweise erstellen](/help/components/c-intelligent-alerts/alert-builder.md) beschrieben.

In Adobe Analytics sind die folgenden Optionen verfügbar:

* Wählen Sie mindestens ein Zeilenelement in einer Freiformtabelle aus, klicken Sie mit der rechten Maustaste darauf und wählen Sie **[!UICONTROL Warnhinweis aus Auswahl erstellen]** aus.

  Dadurch wird der Warnhinweiserstellung sofort vorausgefüllt, um einen Warnhinweis mit den richtigen Metriken und Filtern zu erstellen.

* Öffnen Sie ein Projekt in Analysis Workspace und wählen Sie dann **[!UICONTROL Komponenten]** > **[!UICONTROL Warnhinweis erstellen]** aus.

* Öffnen Sie ein Projekt in Analysis Workspace und verwenden Sie dann den folgenden Tastaturbefehl: **[!UICONTROL *Strg *]**+**[!UICONTROL * Umschalttaste *]** + **[!UICONTROL *a *]**(Windows) oder**[!UICONTROL * Befehl *]** + **[!UICONTROL *Umschalttaste *]**+**[!UICONTROL * a *]** (macOS).







