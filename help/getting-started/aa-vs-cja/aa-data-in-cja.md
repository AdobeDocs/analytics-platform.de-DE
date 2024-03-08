---
title: Verwenden von Daten aus Adobe Analytics Report Suites in Customer Journey Analytics
description: Konfigurieren von Adobe Analytics Report Suites für die Aufnahme in Adobe Experience Platform und Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 100%

---

# Verwenden von Daten aus Adobe Analytics Report Suites in Customer Journey Analytics

Adobe Analytics-Kundinnen und -Kunden können ihre Report Suites in Adobe Experience Platform und Customer Journey Analytics einfach mit dem [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) nutzen. Im Folgenden wird erörtert, wie man dazu vorgehen kann.

>[!IMPORTANT]
>
>Sie müssen über das **Select**-Paket verfügen, um Datenanalysen für mehrere Report Suites durchzuführen. Wenden Sie sich an Ihr Admin-Team, wenn Sie sich nicht sicher sind, welches Customer Journey Analytics-Paket Sie besitzen.

## Vorbereitung

Bei der Vorbereitung auf die Verwendung der Report Suites aus Adobe Analytics in Adobe Experience Platform und Customer Journey Analytics sollten Sie verschiedene Maßnahmen ergreifen, um Ihre Daten für einen nahtlosen Wechsel zu Customer Journey Analytics vorzubereiten. Weitere Informationen finden Sie auf der folgenden Seite:

* [Umstieg von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/aa-to-cja.md)

## Einrichten der Report Suites für die Aufnahme in Adobe Experience Platform und Customer Journey Analytics

Sobald Sie Ihre Daten vorbereitet haben, können Sie mit der Konfiguration der Report Suites für Adobe Experience Platform und Customer Journey Analytics beginnen.

1. **Erstellen Sie einen Datenfluss für jede Report Suite, die Sie in Adobe Experience Platform und Customer Journey Analytics verwenden möchten.** Der [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) ist das Tool, das Ihnen das [Erstellen einer Verbindung](/help/connections/create-connection.md) (auch als Datenfluss bezeichnet) zwischen Adobe Analytics und Adobe Experience Platform ermöglicht. Zum Herstellen eines Datenflusses für jede Report Suite, die in Adobe Experience Platform verwendet werden soll, sollten Sie den Quell-Connector verwenden. Durch den Datenfluss wird eine Kopie Ihrer Report Suite-Daten hergestellt, wobei das Schema in [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=de) konvertiert wurde, damit die Daten von Adobe Experience Platform-Anwendungen, einschließlich Customer Journey Analytics, verwendet werden können.<p>Jede Report Suite, die über den Quell-Connector mit einem Datenfluss konfiguriert wurde, wird als separater Datensatz im Adobe Experience Platform Data Lake gespeichert. In jeden Datenfluss werden automatisch 13 Monate historischer Report Suite-Daten eingeschlossen. Neue Daten werden laufend nach Adobe Experience Platform übertragen. (Hinweis: Die Aufstockung in Nicht-Produktions-Sandboxes ist ab dem 26. April 2023 auf 3 Monate beschränkt.) Mit dem Analytics-Quell-Connector müssen Sie sich nicht im Voraus um die Erstellung des Schemas kümmern. Für Adobe Analytics wird automatisch ein standardisiertes Schema erstellt. Das Adobe Experience Platform-Tool zur [Datenvorbereitung](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de) kann jedoch verwendet werden, um dieses Schema zu erweitern, bevor die Daten im Data Lake gespeichert und Customer Journey Analytics zur Verfügung gestellt werden. Beachten Sie, dass bestimmte Datentypen vom Quell-Connector herausgefiltert werden und nicht in dem Datensatz im Adobe Experience Platform Data Lake vorhanden sein werden. Zwischen Data Lake und Customer Journey Analytics können andere Zeilen herausgefiltert werden. Weitere Informationen finden Sie unter [Vergleich von Adobe Analytics-Daten mit Customer Journey Analytics-Daten](/help/troubleshooting/compare.md).
1. **Verwenden Sie die Datenvorbereitung, um Report Suites in Customer Journey Analytics zu kombinieren.** Die Datenvorbereitung kann für viele Arten der Datenumwandlung verwendet werden. Adobe Analytics-Daten wird häufig zur Beseitigung von Unterschieden bei den Eigenschafts- und/oder eVar-Zuordnungen über mehrere Report Suites hinweg eingesetzt, sodass Report Suites innerhalb von Customer Journey Analytics einfach kombiniert werden können. Weitere Details finden Sie unter [Kombinieren von Report Suites mit unterschiedlichen Schemata](/help/use-cases/aa-data/combine-report-suites.md).
1. **Aktivieren Sie die Zuordnungsfunktion** nach Bedarf. Beim Kombinieren mehrerer Datensätze in Customer Journey Analytics können die Zuordnungsfunktionen dabei helfen, verschiedene ID-Namespaces zu einer einzigen zugeordneten ID aufzulösen, was eine einzige Sicht auf die Kundin bzw. den Kunden über alle Geräte und Kanäle hinweg erlaubt. Weitere Informationen finden Sie unter [Zuordnung – Übersicht](../../stitching/overview.md).
1. **Erstellen Sie eine oder mehrere Customer Journey Analytics-Verbindungen.** Sobald die Datensätze für Ihre Report Suites im Adobe Experience Platform Data Lake verfügbar sind, können Sie eine oder mehrere [Customer Journey Analytics-Verbindungen](/help/connections/overview.md) erstellen, um diese Datensätze in Customer Journey Analytics zu übernehmen. Innerhalb einer Verbindung können Report Suite-Daten mit anderen Datentypen kombiniert werden, sodass Sie eine echte kanalübergreifende Darstellung der Kundenerlebnisse erstellen können.
1. **Erstellen Sie eine oder mehrere Customer Journey Analytics-Datenansichten.** Eine [Datenansicht](/help/data-views/data-views.md) ist ein für Customer Journey Analytics spezifischer Container, mit dem Sie bestimmen können, wie Daten aus einer Customer Journey Analytics-Verbindung interpretiert werden. Datenansichten verfügen über viele leistungsstarke [Konfigurationsoptionen](/help/data-views/create-dataview.md), mit denen Sie die Daten, die Sie den Benutzenden in [Analysis Workspace](/help/analysis-workspace/home.md) präsentieren, anpassen können.

## Vergleich von Customer Journey Analytics und Adobe Analytics

Customer Journey Analytics und Adobe Analytics weisen eine Reihe von Ähnlichkeiten auf. Beispielsweise bieten sowohl Customer Journey Analytics als auch Adobe Analytics die Leistungskraft von Analysis Workspace für eine freie und blitzschnelle Analyse. Da Customer Journey Analytics jedoch eine Anwendung innerhalb von Adobe Experience Platform ist und Adobe Experience Platform für die Datenaufnahme nutzt, unterscheiden sich Customer Journey Analytics und Adobe Analytics in einer Reihe wichtiger Aspekte. Die folgenden Artikel sind hilfreich, um diese Unterschiede zu verstehen:

* [Vergleich von Adobe Analytics-Daten mit Customer Journey Analytics-Daten](/help/troubleshooting/compare.md)
* [Unterstützung der Customer Journey Analytics-Funktionen](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Vergleich der Terminologie für Analytics-Daten, die durch den Analytics-Quell-Connector übergeben werden](/help/getting-started/aa-vs-cja/terminology.md)
* [Vergleich der Datenverarbeitung zwischen Reporting-Funktionen von Adobe Analytics und Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [Virtual Report Suites, Datenansichten, Adobe Experience Platform-Sandboxes und der Analytics-Quell-Connector](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [Verarbeitungsregeln, VISTA und Klassifizierungen versus Datenvorbereitung](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID, ECID, AACUSTOMID und der Analytics-Quell-Connector](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
