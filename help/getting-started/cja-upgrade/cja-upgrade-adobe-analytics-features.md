---
title: Weitere Informationen zur Unterstützung von Adobe Analytics-Funktionen beim Upgrade auf Customer Journey Analytics
description: Erfahren mehr über die Unterstützung von Adobe Analytics-Funktionen beim Upgrade auf Customer Journey Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 92053109-f80d-47ab-b011-c28a5411149c
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 100%

---

# Weitere Informationen zur Unterstützung von Adobe Analytics-Funktionen beim Upgrade auf Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-migrate-projects"
>title="Komponenten und Projekte"
>abstract="Zu den Komponenten von Adobe Analytics gehören: Projekte (mit den zugehörigen Freiformtabellen und Visualisierungen), Segmente und berechnete Metriken."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map"
>title="Activity Map-Überlagerung und Linktracking"
>abstract="Eine Browser-Erweiterung, mit der Sie Linktracking-Daten als Überlagerung auf Ihrer Site anzeigen können."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map-support"
>title="Unterstützung für Activity Map-Überlagerung ist noch nicht verfügbar"
>abstract="Unterstützung für Activity Map-Überlagerung ist in Customer Journey Analytics noch nicht verfügbar. Es ist geplant, dass sie in Zukunft verfügbar sein wird."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-classification"
>title="Klassifizierungsdaten"
>abstract="Gruppieren oder kategorisieren Sie Daten als separate Dimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channels"
>title="Marketing-Kanäle"
>abstract="Erstellen Sie Regeln, die kategorisieren, wie Kundschaft zu Ihrer Site gelangt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds"
>title="Daten-Feeds"
>abstract="Exportieren Sie Rohdaten aus Adobe Analytics zur Verwendung in externen Tools und Prozessen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-warehouse"
>title="Data Warehouse"
>abstract="Exportieren Sie verarbeitete Daten aus Adobe Analytics im Tabellenformat."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-streaming-media"
>title="Streaming-Mediendaten"
>abstract="Ein Add-on für Adobe Analytics und Customer Journey Analytics, das auf die Datenerfassung von Medien wie Audio, Video oder Streaming-Inhalten spezialisiert ist."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-component-migration"
>title="Migrieren von Projekten und Komponenten"
>abstract="Migrieren Sie Adobe Analytics-Projekte und alle enthaltenen Komponenten zu Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

In der folgenden Liste sind nur die Adobe Analytics-Funktionen aufgeführt, die beim Upgrade auf Customer Journey Analytics berücksichtigt werden müssen. Eine umfassende Liste der Adobe Analytics-Funktionen, die vollständig, teilweise oder nicht in Customer Journey Analytics unterstützt werden, finden Sie unter [Unterstützung der Customer Journey Analytics-Funktion](/help/getting-started/aa-vs-cja/cja-aa.md).

Überlegen Sie, welche der folgenden Adobe Analytics-Funktionen Sie nach dem Upgrade auf Customer Journey Analytics weiterhin verwenden möchten:

| Adobe Analytics-Funktion | Entsprechende Funktion in Customer Journey Analytics |
|---------|----------|
| [Komponenten und Projekte aus Adobe Analytics](https://experienceleague.adobe.com/de/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) | [Migrieren von Projekten und zugehörigen Komponenten nach Customer Journey Analytics](https://experienceleague.adobe.com/de/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration). |
| [Activity Map-Überlagerung und Linktracking](https://experienceleague.adobe.com/de/docs/analytics/analyze/activity-map/overview) | Noch nicht verfügbar |
| [Klassifizierungsdaten](https://experienceleague.adobe.com/de/docs/analytics/components/classifications/c-classifications) | Lookup-Datensätze sind die Methode zum Klassifizieren von Daten in Customer Journey Analytics.<p>[Erstellen Sie einen Lookup-Datensatz für jede Dimension mit Klassifizierungsdaten.](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)</p> |
| [Marketing-Kanäle](https://experienceleague.adobe.com/de/docs/analytics/components/marketing-channels/c-getting-started-mchannel) | Abgeleitete Felder werden in einer Datenansicht erstellt. <p>[Erstellen eines abgeleiteten Marketing-Kanal-Felds.](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)</p> |
| [Daten-Feeds](https://experienceleague.adobe.com/de/docs/analytics/export/analytics-data-feed/data-feed-overview) | Experience Platform und Customer Journey Analytics bieten eine Reihe von Funktionen, die entweder unabhängig voneinander oder kombiniert die verschiedenen Exportanforderungen erfüllen können. Zu diesen Funktionen gehören das [Experience Platform Data Access-API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=de), [Experience Platform-Ziele](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=de), der [vollständige Tabellenexport in Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) und die [BI-Tools-Integration](/help/data-views/bi-extension.md).<p>Weitere Informationen zu Exportoptionen finden Sie unter [Anwendungsfälle für den Datenexport](/help/use-cases/data-export/overview.md).</p> |
| [Data Warehouse](https://experienceleague.adobe.com/de/docs/analytics/export/data-warehouse/data-warehouse) | [Der vollständige Tabellenexport von Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) ist die Weiterentwicklung von Data Warehouse-Berichten in Adobe Analytics, mit vielen neuen, häufig angeforderten Funktionen, die heute nicht in Data Warehouse verfügbar sind. |
| [Streaming-Mediendaten](https://experienceleague.adobe.com/de/docs/media-analytics/using/media-overview) | Streaming-Mediendaten sind über den Analytics-Quell-Connector als Teil des Bedienfelds „Gleichzeitige Medienbetrachter“ und des Bedienfelds „Bei Medienwiedergabe verbrachte Zeit“ in Workspace verfügbar. |
