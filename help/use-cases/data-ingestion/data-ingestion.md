---
title: Optionen zur Datenaufnahme für Customer Journey Analytics
description: Hier erhalten Sie Informationen über die unterschiedlichen Arten der Datenaufnahme für Customer Journey Analytics
exl-id: 4a47c587-f48e-4e29-b97f-00c7d7e6972c
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 89%

---

# Optionen zur Datenaufnahme für Customer Journey Analytics

Sie haben eine Reihe von Möglichkeiten, Daten in Customer Journey Analytics aufzunehmen. Bei einigen werden Daten aus Adobe Analytics verschoben, bei anderen werden Daten direkt von Adobe Experience Platform übertragen. Dieses Informationsmaterial enthält allgemeine Schritte mit Links zu detaillierteren Informationen.

## Daten aus Adobe Analytics erfassen

Dieser Workflow nutzt den Analytics-Quell-Connector und variiert je nachdem, ob Sie DTM oder Launch als Tag-Manager verwenden.

### Über Tags in Adobe Experience Platform (früher [!UICONTROL Launch] genannt)

1. [Erstellen Sie eine Datenschicht](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=de), wenn Sie das noch nicht getan haben. Eine Datenschicht ist ein Framework von JavaScript-Objekten auf Ihrer Website, die alle in Ihrer Implementierung verwendeten Variablenwerte enthalten. Sie ermöglicht eine bessere Kontrolle und einfachere Wartung Ihrer Implementierung.
1. Verwenden Sie [Adobe Experience Platform-Tags](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=de), um Code für die Datenerfassung auf Ihrer Website zu implementieren, falls Sie das noch nicht getan haben. Mit dieser Tag-Management-Lösung können Sie Analytics-Code zusammen mit anderen Tagging-Anforderungen bereitstellen. Tags bieten Integrationen mit anderen Lösungen und Produkten und ermöglicht die Bereitstellung von benutzerdefiniertem Code. Alle diese Aufgaben können ausgeführt werden, ohne dass Entwicklerteams in Ihrer Organisation Code auf Ihrer Website aktualisieren müssen.
1. Erstellen Sie einen [Adobe Analytics-Quellen-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de) in Adobe Experience Platform. Dieser Quellen-Connector nimmt Ihre Analytics-Daten in Experience Platform in einem standardisierten Framework mit dem Namen [Experience-Datenmodell (XDM)-System](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=de) auf. Siehe auch [Verwenden von Report-Suite-Daten von Adobe Analytics in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
1. Verwenden Sie [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=de), um eine oder mehrere Verbindungen und Datenansichten zu erstellen, die in Ihr kanalübergreifendes Reporting einfließen werden.

## Aufnehmen von Daten über das Adobe Experience Platform Web SDK und Edge Network

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=de) ist eine Client-seitige JavaScript-Bibliothek, mit der Kunden von Adobe Experience Cloud mit den verschiedenen Services in Experience Cloud interagieren können.

1. [Konfigurieren der Adobe Experience Platform Web SDK-Erweiterung in Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=de) , um Daten von Webeigenschaften über das Adobe Experience Platform Edge Network an die Adobe Experience Cloud zu senden.
1. Verwenden Sie [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=de), um eine oder mehrere [Verbindungen](/help/connections/create-connection.md) und [Datenansichten](/help/data-views/data-views.md) zu erstellen, die in Ihr kanalübergreifendes Reporting einfließen werden.

## Daten mit Batch-Erfassung und Streaming-Erfassung einlesen

Adobe Experience Platform bringt Daten aus mehreren Quellen zusammen, um Marketern ein besseres Verständnis des Verhaltens ihrer Kunden zu ermöglichen. Datenerfassung in Adobe Experience Platform stellt die verschiedenen Methoden, mit denen Platform Daten aus den Quellen erfasst, sowie die Art und Weise dar, wie die Daten im Data Lake zur Verwendung durch nachgelagerte Platform-Dienste persistiert werden.

### Batch-Erfassung

1. Richten Sie die [Batch-Erfassung](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=de#batch) ein, damit Sie Daten als Batch-Dateien in Adobe Experience Platform einlesen können. Daten, die aufgenommen werden, können Profildaten aus einer reduzierten Datei in einem CRM-System (z. B. eine Parquet-Datei) oder Daten sein, die einem bekannten Schema in der Experience-Datenmodell (XDM)-Registry entsprechen.
1. Verwenden Sie [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=de), um eine oder mehrere [Verbindungen](/help/connections/create-connection.md) und [Datenansichten](/help/data-views/data-views.md) zu erstellen, die in Ihr kanalübergreifendes Reporting einfließen werden.

### Streaming-Erfassung

1. Richten Sie die [Streaming-Erfassung](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=de#streaming) ein, um Daten von Client- und Server-seitigen Geräten in Echtzeit an Experience Platform zu senden.
1. Verwenden Sie [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=de), um eine oder mehrere [Verbindungen](/help/connections/create-connection.md) und [Datenansichten](/help/data-views/data-views.md) zu erstellen, die in Ihr kanalübergreifendes Reporting einfließen werden.

## Einbringen von Google Analytics-Daten zur Analyse in Customer Journey Analytics

In diesem Tutorial finden Sie detaillierte Schritte, wie Sie [Daten von Google Analytics mit Customer Journey Analytics analysieren](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial-v22/module12/ex5.html?lang=de).

## Verwenden Sie die Bulk-Dateneinfüge-API, um Daten in Analytics aufzunehmen, und erfassen Sie dann über den Analytics-Quell-Connector in Experience Platform.

1. [Verwenden Sie die Bulk Data Insertion API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md), um Server-seitig gesammelte Daten an Adobe Analytics zu senden. Damit können Sie Dateien im CSV-Format senden, die Ereignisdaten enthalten.
1. [Erstellen Sie einen Adobe Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de), um diese Verbraucherdaten in Adobe Experience Platform zu importieren.
1. Verwenden Sie [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=de), um eine oder mehrere [Verbindungen](/help/connections/create-connection.md) und [Datenansichten](/help/data-views/data-views.md) zu erstellen, die in Ihr kanalübergreifendes Reporting einfließen werden.
