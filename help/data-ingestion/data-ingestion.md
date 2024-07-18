---
title: Datenaufnahme – Übersicht
description: Hier erhalten Sie Informationen über die unterschiedlichen Methoden der Datenaufnahme in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
role: Admin
source-git-commit: dca1cc33058ba57815c3534ab21da86d5247531a
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 65%

---

# Datenaufnahme – Übersicht

Sie haben mehrere Möglichkeiten bei der Aufnahme von Daten in Customer Journey Analytics. In einigen Szenarien sollen Daten aus Adobe Analytics verschoben, in anderen Daten in Adobe Experience Platform aufgenommen werden.

>[!IMPORTANT]
>
>Doch alle haben gemeinsam, dass die Daten, die in Customer Journey Analytics _verwendet_ werden sollen, eigentlich in Adobe Experience Platform _aufgenommen_ werden müssen.

Sehen Sie sich dazu die übergeordnete Customer Journey Analytics-Architektur an, die zuvor in der [Übersicht](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) dargestellt wurde:

![Customer Journey Analytics-Architektur, die in diesem Abschnitt beschrieben wird](./assets/cja-architecture.png)

Der Datensatz in der obigen Architektur kann aus verschiedenen Quellen stammen:

- Batch-Daten

- Streaming-Daten

- Daten aus einer aktuellen Adobe Analytics-Bereitstellung

- Daten aus der Verfolgung Ihrer Website/App mithilfe des Adobe Experience Platform Web/Mobile SDK,

- Daten aus der Verfolgung einer Desktop-Applikation, eines Konsolenspiels, einer Set-Top-Box oder eines IoT-Geräts mithilfe der Adobe Experience Platform Edge Network Server API oder

- Daten von einem Third-Party-Datenanbieter, für die Adobe einen Quell-Connector bereitstellt

Von diesen Datensätzen kann es viele geben.

Im Folgenden finden Sie Kurzanleitungen für verschiedene Szenarien.

## Aufnahmen priorisieren und Latenz

Sie können Ihre Ereignisdaten innerhalb von 90 Minuten (SLT) in Customer Journey Analytics erfassen, unabhängig davon, ob die Daten 24 Stunden, 48 Stunden oder 7 Tage alt sind.

Beachten Sie, dass sich diese Funktion je nach dem von Ihrem Unternehmen erworbenen SKU-Paket unterscheidet:

- Priority Ingestion Standard: 24-Stunden-Daten innerhalb der 90-minütigen SLT-Verarbeitung (verfügbar für **CJA Foundation** und **CJA Select**)

- Priority Ingestion Intermediate: 72 Stunden alte Daten innerhalb der 90-minütigen SLT-Verarbeitung (verfügbar für **CJA Prime**)

- Priority Ingestion Erweitert: 1 Woche alte Daten innerhalb einer 90-minütigen SLT-Verarbeitung (verfügbar für **CJA Ultimate**)

## Aufnehmen und Verwenden von Daten aus Adobe Analytics

Sie haben Adobe Analytics bereits bereitgestellt und möchten diese Daten in Adobe Experience Platform aufnehmen und in Customer Journey Analytics gemeinsam mit Daten aus anderen Kanälen und Datenquellen nutzen, kombinieren und analysieren.

Weitere Informationen finden Sie unter [Aufnehmen und Verwenden von Daten aus Adobe Analytics](./analytics.md).


## Daten über das Edge Network erfassen und verwenden

### Verwenden des Adobe Experience Platform Web SDK

Sie möchten Ihre Website mit Adobe-Technologie analysieren, möglicherweise von einer anderen Lösung migrieren oder das Verhalten Ihrer Person verfolgen. Sie sollten die Best Practices von Adobe bei der Implementierung befolgen, bei der die Adobe Experience Platform SDKs und das Edge Network zur Aufnahme von Daten verwendet werden. Anschließend können Sie die aufgenommenen Daten mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Weitere Informationen finden Sie unter [Aufnehmen und Verwenden von Daten über das Adobe Experience Platform Web SDK](./aepwebsdk.md) .

### Verwenden des Adobe Experience Platform Mobile SDK

Sie möchten Ihre App mit Adobe-Technologie analysieren, möglicherweise von einer anderen Lösung migrieren oder das Verhalten einer Person in der App von Grund auf verfolgen. Sie sollten die Best Practices von Adobe bei der Implementierung befolgen, bei der die Adobe Experience Platform SDKs und das Edge Network zur Aufnahme von Daten verwendet werden. Anschließend können Sie die aufgenommenen Daten mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Weitere Informationen finden Sie unter [Aufnehmen und Verwenden von Daten über das Adobe Experience Platform Mobile SDK](./aepmobilesdk.md) .

### Verwenden der Adobe Experience Platform Edge Network Server-API

Sie möchten Ihre Desktop-Applikation, das Spiel, wie es auf einer Spielkonsole gespielt wird, die Nutzung einer Video-Streaming-Applikation auf einer Set-Top-Box oder Ihr IoT-Gerät mit Adobe-Technologie analysieren. Möglichkeit der Migration von einer anderen Lösung oder der Verfolgung des Verhaltens einer Person auf diesen Geräten von Grund auf. Sie möchten die Best Practices für die Implementierung befolgen, bei der die Adobe Experience Platform Edge Network Server-APIs und Edge Network zur Aufnahme der Daten verwendet werden. Anschließend können Sie die aufgenommenen Daten mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Weitere Informationen finden Sie unter [Aufnehmen und Verwenden von Daten über die Adobe Experience Platform Edge Network Server API](./serverapi.md) .

## Aufnehmen und Verwenden von Batch-Daten

Ihnen stehen relevante Batch-Daten zur Verfügung, die Ihnen helfen, das Kundenverhalten besser zu verstehen und Kundeninteraktionen zu analysieren. Beispiele für solche Batch-Daten sind flache Dateien im CSV-, JSON- oder Parquet-Format aus einem CRM-System, einem Treueprogramm oder einer anderen Lösung, für die Adobe derzeit keinen Quell-Connector bereitstellt. Durch die Aufnahme dieser Batch-Daten in Adobe Experience Platform können Sie sie mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Weitere Informationen dazu finden Sie unter [Aufnehmen und Verwenden von Batch-Daten](./batch.md).

## Aufnehmen und Verwenden von Streaming-Daten

Sie verfügen über eine relevante Datenquelle wie z. B. ein CRM-System, ein ERP-System oder eine andere Quelle, die Details liefert, anhand derer Sie das Kundenverhalten besser verstehen und Kundeninteraktionen analysieren können. Diese Datenquelle kann über HTTP oder eine öffentliche Cloud-Streaming-Infrastruktur kommunizieren, Adobe bietet dafür derzeit aber keinen Quell-Connector. Wenn Sie diese Streaming-Daten in Echtzeit in Adobe Experience Platform aufnehmen, können Sie sie mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Weitere Informationen dazu finden Sie unter [Aufnehmen und Verwenden von Streaming-Daten](./streaming.md).

## Aufnehmen und Verwenden von Daten über Quell-Connectoren

Sie verfügen über Daten aus einer Quelle, die von einem Quell-Connector unterstützt wird. Quell-Connectoren sind konfigurierbar und ermöglichen Ihnen, Daten von Adobe sowie First-Party- und Third-Party-Anwendungen in Adobe Experience Platform aufzunehmen. Eine Übersicht über die verfügbaren Quell-Connectoren finden Sie unter [Übersicht über Quell-Connectoren](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=de). Mithilfe des Quell-Connectors können Sie einfach Daten aus der Quelle in Adobe Experience Platform aufnehmen und diese dann mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Weitere Informationen finden Sie unter [Aufnehmen und Verwenden von Daten über Quell-Connectoren](./sources.md).
