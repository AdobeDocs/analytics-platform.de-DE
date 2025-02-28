---
title: Datenaufnahme – Übersicht
description: Hier erhalten Sie Informationen über die unterschiedlichen Methoden der Datenaufnahme in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
role: Admin
source-git-commit: 8071e8d5e1ab7e9cfc5037d710361a4d10285704
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 64%

---

# Übersicht über die Datenaufnahme

Sie haben mehrere Möglichkeiten, um Daten in Customer Journey Analytics aufzunehmen. In einigen Szenarien sollen Daten aus Adobe Analytics verschoben, in anderen Daten in Adobe Experience Platform aufgenommen werden.

>[!IMPORTANT]
>
>Doch alle haben gemeinsam, dass die Daten, die in Customer Journey Analytics _verwendet_ werden sollen, eigentlich in Adobe Experience Platform _aufgenommen_ werden müssen.

Sehen Sie sich dazu die übergeordnete Customer Journey Analytics-Architektur an, die zuvor in der [Übersicht](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) dargestellt wurde:

![Customer Journey Analytics-Architektur, die in diesem Abschnitt beschrieben wird](./assets/cja-architecture.png)

Der Datensatz in der obigen Architektur kann aus verschiedenen Quellen stammen:

- Batch-Daten

- Streaming-Daten

- Daten aus einer aktuellen Adobe Analytics-Bereitstellung

- Daten aus dem Tracking Ihrer Website/Mobile App mit dem Adobe Experience Platform Web/Mobile SDK,

- Daten aus dem Tracking einer Desktop-Anwendung, eines Konsolenspiels, einer Set-Top-Box oder eines IoT-Geräts mithilfe der Adobe Experience Platform Edge Network Server API oder

- Daten von einem Third-Party-Datenanbieter, für die Adobe einen Quell-Connector bereitstellt

Von diesen Datensätzen kann es viele geben.

Im Folgenden finden Sie Kurzanleitungen für verschiedene Szenarien.

## Aufnahme-Priorisierung und Latenz

Sie können Ihre Ereignisdaten in Customer Journey Analytics innerhalb von 90 Minuten (SLT) aufnehmen, unabhängig davon, ob die Daten 24 Stunden, 48 Stunden oder 7 Tage alt sind.

Beachten Sie, dass sich diese Funktion je nach dem von Ihrem Unternehmen erworbenen SKU-Paket unterscheidet:

- Priority Ingestion Basic: 24 Stunden alte Daten innerhalb einer 90-minütigen SLT-Verarbeitung (verfügbar für **CJA Foundation** und **CJA Select**)

- Priority Ingestion Intermediate: 72 Stunden alte Daten innerhalb von 90 Minuten SLT-Verarbeitung (verfügbar für **CJA Prime**)

- Prioritätsaufnahme Erweitert: 1 Woche alte Daten innerhalb einer 90-minütigen SLT-Verarbeitung (verfügbar für **CJA Ultimate**)

## Aufnehmen und Verwenden von Daten aus Adobe Analytics

Sie haben Adobe Analytics bereits bereitgestellt und möchten diese Daten in Adobe Experience Platform aufnehmen und in Customer Journey Analytics gemeinsam mit Daten aus anderen Kanälen und Datenquellen nutzen, kombinieren und analysieren.

Weitere Informationen finden Sie unter [Aufnehmen und Verwenden von Daten aus Adobe Analytics](./analytics.md).


## Aufnehmen und Verwenden von Daten über Edge Network

### Verwenden der Adobe Experience Platform Web SDK

Sie möchten Ihre Website mithilfe von Adobe-Technologie analysieren und migrieren möglicherweise von einer anderen Lösung oder beginnen mit dem Tracking des Verhaltens Ihrer Person. Sie sollten die Best Practices von Adobe bei der Implementierung befolgen, bei der die Adobe Experience Platform SDKs und das Edge Network zur Aufnahme von Daten verwendet werden. Anschließend können Sie die aufgenommenen Daten mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Weitere Informationen [ Sie unter „Aufnehmen und Verwenden von Daten über die Adobe Experience Platform Web](./aepwebsdk.md)SDK&quot;.

### Verwenden der Adobe Experience Platform Mobile SDK

Sie möchten Ihre Mobile App mit Adobe-Technologie analysieren, migrieren möglicherweise von einer anderen Lösung oder beginnen mit der Verfolgung des Verhaltens einer Person in der App von Grund auf. Sie sollten die Best Practices von Adobe bei der Implementierung befolgen, bei der die Adobe Experience Platform SDKs und das Edge Network zur Aufnahme von Daten verwendet werden. Anschließend können Sie die aufgenommenen Daten mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Weitere Informationen [ Sie unter „Aufnehmen und Verwenden von Daten über die Adobe Experience Platform SDK Mobile ](./aepmobilesdk.md)&quot;.

### Verwenden der Adobe Experience Platform Edge Network-Server-API

Sie möchten Ihre Desktop-Anwendung analysieren, das Spiel, wie es auf einer Spielkonsole gespielt wird, die Verwendung einer Video-Streaming-Anwendung auf einer Set-Top-Box oder Ihr IoT-Gerät mit Adobe-Technologie. Migrieren von einer anderen Lösung oder Beginnen Sie mit der Verfolgung des Verhaltens einer Person auf diesen Geräten von Grund auf. Sie sollten die Best Practices von Adobe für die Implementierung befolgen, bei der die Adobe Experience Platform Edge Network-Server-APIs und Edge Network verwendet werden, um die Daten aufzunehmen. Anschließend können Sie die aufgenommenen Daten mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Weitere Informationen finden [ unter „Aufnehmen und Verwenden von Daten über die Adobe Experience Platform Edge Network](./serverapi.md)Server-API“.

## Aufnehmen und Verwenden von Batch-Daten

Ihnen stehen relevante Batch-Daten zur Verfügung, die Ihnen helfen, das Kundenverhalten besser zu verstehen und Kundeninteraktionen zu analysieren. Beispiele für solche Batch-Daten sind flache Dateien im CSV-, JSON- oder Parquet-Format aus einem CRM-System, einem Treueprogramm oder einer anderen Lösung, für die Adobe derzeit keinen Quell-Connector bereitstellt. Durch die Aufnahme dieser Batch-Daten in Adobe Experience Platform können Sie sie mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Weitere Informationen dazu finden Sie unter [Aufnehmen und Verwenden von Batch-Daten](./batch.md).

## Aufnehmen und Verwenden von Streaming-Daten

Sie verfügen über eine relevante Datenquelle wie z. B. ein CRM-System, ein ERP-System oder eine andere Quelle, die Details liefert, anhand derer Sie das Kundenverhalten besser verstehen und Kundeninteraktionen analysieren können. Diese Datenquelle kann über HTTP oder eine öffentliche Cloud-Streaming-Infrastruktur kommunizieren, Adobe bietet dafür derzeit aber keinen Quell-Connector. Wenn Sie diese Streaming-Daten in Echtzeit in Adobe Experience Platform aufnehmen, können Sie sie mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Weitere Informationen dazu finden Sie unter [Aufnehmen und Verwenden von Streaming-Daten](./streaming.md).

## Aufnehmen und Verwenden von Daten über Quell-Connectoren

Sie verfügen über Daten aus einer Quelle, die von einem Quell-Connector unterstützt wird. Quell-Connectoren sind konfigurierbar und ermöglichen Ihnen, Daten von Adobe sowie First-Party- und Third-Party-Anwendungen in Adobe Experience Platform aufzunehmen. Eine Übersicht über die verfügbaren Quell-Connectoren finden Sie unter [Übersicht über Quell-Connectoren](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=de). Mithilfe des Quell-Connectors können Sie einfach Daten aus der Quelle in Adobe Experience Platform aufnehmen und diese dann mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Weitere Informationen finden Sie unter [Aufnehmen und Verwenden von Daten über Quell-Connectoren](./sources.md).

>[!MORELIKETHIS]
>
>Blog: [Ein genauerer Blick auf die Datenverarbeitung und -aufnahme in Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-closer-look-at-data-processing-amp-ingestion-in-adobe-customer/ba-p/665091)

