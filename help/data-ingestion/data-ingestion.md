---
title: Datenaufnahme – Übersicht
description: Hier erhalten Sie Informationen über die unterschiedlichen Methoden der Datenaufnahme in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
role: Admin
source-git-commit: ec56bc657961b2e4e8318ab14cd676288398462f
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 100%

---

# Überblick über die Datenaufnahme

Es gibt mehrere Möglichkeiten, um Daten in Customer Journey Analytics aufzunehmen. In einigen Szenarien sollen Daten aus Adobe Analytics verschoben, in anderen Daten in Adobe Experience Platform aufgenommen werden.

>[!IMPORTANT]
>
>Doch alle haben gemeinsam, dass die Daten, die in Customer Journey Analytics _verwendet_ werden sollen, eigentlich in Adobe Experience Platform _aufgenommen_ werden müssen.


Die allgemeine Architektur von Customer Journey Analytics ist im Folgenden dargestellt:

![Customer Journey Analytics-Architektur](/help/getting-started/assets/cja-overview.svg)

Diese Architektur veranschaulicht, wie Customer Journey Analytics Folgendes ermöglicht:

* Kombinieren mehrerer Datensätze ![Daten](/help/assets/icons/Data.svg) in einer [Verbindung](/help/connections/overview.md).
* Definieren und Konfigurieren von Dimensionen ![Dimensionen](/help/assets/icons/Dimensions.svg) und Metriken ![Ereignis](/help/assets/icons/Event.svg) in einer [Datenansicht](/help/data-views/data-views.md) basierend auf den Feldern, die in den von Ihnen in Ihrer Verbindung definierten Datensätzen verfügbar sind.
* Erstellen von Berichten ![Ansichtstabelle](/help/assets/icons/ViewTable.svg) und Visualisierungen (wie Linien- ![Linie](/help/assets/icons/GraphTrend.svg) und Flächendiagrammen ![Fläche](/help/assets/icons/GraphAreaStacked.svg)) in [Projekten](/help/analysis-workspace/home.md) basierend auf den Dimensionen und Metriken aus Ihren Datenansichten.

Die Datensätze in der Architektur können aus verschiedenen Quellen stammen:

* Batch-Daten

* Streaming-Daten

* Daten aus einer aktuellen Adobe Analytics-Bereitstellung

* Daten aus dem Tracking Ihrer Website/App unter Verwendung des Adobe Experience Platform Web/Mobile SDK

* Daten aus dem Tracking einer Desktop-Anwendung, eines Konsolenspiels, einer Set-top-Box oder eines IoT-Geräts mithilfe des Adobe Experience Platform Edge Network-Server-API oder

* Daten von einem Third-Party-Datenanbieter, für die Adobe einen Quell-Connector bereitstellt

Von diesen Datensätzen kann es viele geben.

Im Folgenden finden Sie Kurzanleitungen für verschiedene Szenarien.

## Aufnahmepriorität und Latenz

Sie können Ihre Ereignisdaten innerhalb von 90 Minuten (SLT) in Customer Journey Analytics aufnehmen, unabhängig davon, ob die Daten 24 Stunden, 48 Stunden oder 7 Tage alt sind. 

Beachten Sie, dass sich diese Funktion je nach dem von Ihrem Unternehmen erworbenen SKU-Paket unterscheidet:

* Priority Ingestion Basic: 24 Stunden alte Daten werden innerhalb von 90 Minuten mit SLT verarbeitet (verfügbar für **CJA Foundation** und **CJA Select**)

* Priority Ingestion Intermediate: 72 Stunden alte Daten werden innerhalb von 90 Minuten mit SLT verarbeitet (verfügbar für **CJA Prime**)

* Priority Ingestion Advanced: 1 Woche alte Daten werden innerhalb von 90 Minuten mit SLT verarbeitet (verfügbar für **CJA Ultimate**)

## Aufnehmen und Verwenden von Daten aus Adobe Analytics

Sie haben Adobe Analytics bereits bereitgestellt und möchten diese Daten in Adobe Experience Platform aufnehmen und in Customer Journey Analytics gemeinsam mit Daten aus anderen Kanälen und Datenquellen nutzen, kombinieren und analysieren.

Weitere Informationen finden Sie unter [Aufnehmen und Verwenden von Daten aus Adobe Analytics](./analytics.md).


## Aufnehmen und Verwenden von Daten über das Edge Network

### Verwenden des Adobe Experience Platform Web SDK

Sie möchten Ihre Website mithilfe von Adobe-Technologie analysieren und migrieren möglicherweise von einer anderen Lösung oder beginnen mit dem Tracking des Verhaltens einer Person. Sie sollten die Best Practices von Adobe bei der Implementierung befolgen, bei der die Adobe Experience Platform SDKs und das Edge Network zur Aufnahme von Daten verwendet werden. Anschließend können Sie die aufgenommenen Daten mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Weitere Informationen dazu finden Sie unter [Aufnehmen und Verwenden von Daten unter Verwendung des Adobe Experience Platform Web SDK](./aepwebsdk.md).

### Verwenden des Adobe Experience Platform Mobile SDK

Sie möchten Ihre App mit Adobe-Technologie analysieren, migrieren möglicherweise von einer anderen Lösung oder beginnen erstmalig mit dem Tracking des Verhaltens einer Person in der App. Sie sollten die Best Practices von Adobe bei der Implementierung befolgen, bei der die Adobe Experience Platform SDKs und das Edge Network zur Aufnahme von Daten verwendet werden. Anschließend können Sie die aufgenommenen Daten mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Weitere Informationen dazu finden Sie unter [Aufnehmen und Verwenden von Daten unter Verwendung des Adobe Experience Platform Mobile SDK](./aepmobilesdk.md).

### Verwenden des Adobe Experience Platform Edge Network-Server-API

Sie möchten mit Adobe-Technologie Ihre Desktop-Anwendung, ein Spiel, wie es auf einer Spielkonsole gespielt wird, die Verwendung einer Video-Streaming-Anwendung auf einer Set-top-Box oder Ihr IoT-Gerät analysieren. Sie migrieren möglicherweise von einer anderen Lösung oder beginnen erstmalig mit dem Tracking des Verhaltens einer Person auf diesen Geräten. Sie sollten die Best Practices von Adobe bei der Implementierung befolgen, bei der die Adobe Experience Platform Edge Network-Server-APIs und das Edge Network zur Aufnahme von Daten verwendet werden. Anschließend können Sie die aufgenommenen Daten mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Weitere Informationen dazu finden Sie unter [Aufnehmen und Verwenden von Daten unter Verwendung des Adobe Experience Platform Edge Network-Server-API](./serverapi.md).

## Aufnehmen und Verwenden von Batch-Daten

Ihnen stehen relevante Batch-Daten zur Verfügung, die Ihnen helfen, das Kundenverhalten besser zu verstehen und Kundeninteraktionen zu analysieren. Beispiele für solche Batch-Daten sind flache Dateien im CSV-, JSON- oder Parquet-Format aus einem CRM-System, einem Treueprogramm oder einer anderen Lösung, für die Adobe derzeit keinen Quell-Connector bereitstellt. Durch die Aufnahme dieser Batch-Daten in Adobe Experience Platform können Sie sie mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Weitere Informationen dazu finden Sie unter [Aufnehmen und Verwenden von Batch-Daten](./batch.md).

## Aufnehmen und Verwenden von Streaming-Daten

Sie verfügen über eine relevante Datenquelle wie z. B. ein CRM-System, ein ERP-System oder eine andere Quelle, die Details liefert, anhand derer Sie das Kundenverhalten besser verstehen und Kundeninteraktionen analysieren können. Diese Datenquelle kann über HTTP oder eine öffentliche Cloud-Streaming-Infrastruktur kommunizieren, Adobe bietet dafür derzeit aber keinen Quell-Connector. Wenn Sie diese Streaming-Daten in Echtzeit in Adobe Experience Platform aufnehmen, können Sie sie mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Weitere Informationen dazu finden Sie unter [Aufnehmen und Verwenden von Streaming-Daten](./streaming.md).

## Aufnehmen und Verwenden von Daten über Quell-Connectoren

Sie verfügen über Daten aus einer Quelle, die von einem Quell-Connector unterstützt wird. Quell-Connectoren sind konfigurierbar und ermöglichen Ihnen, Daten von Adobe sowie First-Party- und Third-Party-Anwendungen in Adobe Experience Platform aufzunehmen. Eine Übersicht über die verfügbaren Quell-Connectoren finden Sie unter [Übersicht über Quell-Connectoren](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=de). Mithilfe des Quell-Connectors können Sie einfach Daten aus der Quelle in Adobe Experience Platform aufnehmen und diese dann mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Weitere Informationen finden Sie unter [Aufnehmen und Verwenden von Daten über Quell-Connectoren](./sources.md).

## Aufnehmen und Verwenden von Ad-hoc-Daten

Sie verfügen über Ad-hoc-Daten, die nur einen einzigen Datensatz in Experience Platform und nicht die Konfiguration eines Experience-Datenmodellschemas (XDM) erfordern. Dieses Szenario wird als Ad-hoc-Schema bezeichnet. Ad-hoc-Schemata werden in verschiedenen Datenaufnahme-Workflows für Experience Platform verwendet, einschließlich der Aufnahme von CSV-Dateien und der Erstellung bestimmter Arten von Quellverbindungen.

Siehe [Aufnehmen und Verwenden von Ad-hoc-Daten](./adhoc.md)

>[!MORELIKETHIS]
>
>Blog: [Eine genauere Betrachtung der Datenverarbeitung und -aufnahme in Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-closer-look-at-data-processing-amp-ingestion-in-adobe-customer/ba-p/665091?profile.language=de)

