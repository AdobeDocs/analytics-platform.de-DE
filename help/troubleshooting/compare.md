---
title: Vergleichen von Analytics Source Connector-Daten mit Adobe Analytics
description: Verstehen Sie Datenunterschiede, wenn Sie ähnliche Berichte in Adobe Analytics und Customer Journey Analytics anzeigen.
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
keywords: abfrage-Service;Abfrage-Service;SQL-Syntax
source-git-commit: d96404479aabe6020566e693245879b5ad4fad9c
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 4%

---

# Vergleichen von Analytics Source Connector-Daten mit Adobe Analytics

Wenn Ihr Unternehmen Customer Journey Analytics einsetzt, können Sie einige Datenunterschiede zwischen Adobe Analytics und Customer Journey Analytics feststellen. Diese Unterschiede sind normal und können aus verschiedenen Gründen auftreten. Customer Journey Analytics wurde entwickelt, um Ihnen die Möglichkeit zu geben, einige der Einschränkungen bei Ihren Daten in Adobe Analytics zu verbessern. Diese Flexibilität kann zu Unterschieden bei der Interpretation von Daten durch Customer Journey Analytics führen. In diesem Artikel erfahren Sie, wie Customer Journey Analytics und Adobe Analytics mit Ihren Daten umgehen.

Auf dieser Seite wird davon ausgegangen, dass Sie Adobe Analytics-Daten mithilfe des [Analytics-Quell-Connectors](https://experienceleague.adobe.com/de/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) in Adobe Experience Platform aufgenommen und dann [Verbindung](/help/connections/overview.md) und [Datenansicht](/help/data-views/data-views.md) in Customer Journey Analytics erstellt haben.

![Der Datenfluss von Adobe Analytics über den Daten-Connector zu Adobe Experience Platform und zu Customer Journey Analytics mithilfe von CJA-Verbindungen.](assets/compare.png)

Betrachten Sie die folgenden möglichen Gründe, warum die Daten zwischen verschiedenen Reporting-Plattformen unterschiedlich sein können:

* **Verschiedene Datensätze oder Report Suites**: Stellen Sie sicher, dass die Report Suite in Adobe Analytics und die Report Suite, von der der Source-Connector Daten ableitet, identisch sind.
* **Kalendereinstellungen**: Report Suites in Adobe Analytics enthalten eine Zeitzone und andere Kalendereinstellungen, die Sie konfigurieren können. Ebenso haben Datenansichten in Customer Journey Analytics eine separate Einstellung, die Sie steuern können. Stellen Sie sicher, dass diese Einstellungen zwischen Produkten übereinstimmen, wenn Parität gewünscht wird.
* **Zusätzliche Datensätze**: Customer Journey Analytics bietet die Möglichkeit, mehrere Datensätze in eine Verbindung aufzunehmen. Zu diesen Unterschieden gehören zusätzliche Ereignis-, Profil- oder Lookup-Datensätze. Diese Funktion ist ein wichtiges Unterscheidungsmerkmal zwischen Adobe Analytics und Customer Journey Analytics und ermöglicht insight die Aufnahme kanalübergreifender Daten.
* **Zusammengefügte Datensätze**: Adobe bietet die Möglichkeit, Personen-IDs zwischen zwei Datensätzen zu analysieren, was zu einem neuen Datensatz mit zusammengefügten IDs führt. Diese [zusammengefügten Datensätze](/help/stitching/overview.md) enthalten zusätzliche Daten, die über die Angebote einer Adobe Analytics Report Suite hinausgehen.
* **Datenquellen**: Customer Journey Analytics umfasst keine [&#x200B; (Datenquellen), &#x200B;](https://experienceleague.adobe.com/en/docs/analytics/import/data-sources/overview) in eine Adobe Analytics Report Suite hochgeladen wurden, einschließlich Zusammenfassungsdatenquellen oder Transaktions-ID-Datenquellen.
* **Einstellungen für Dimension und Metriken**: Innerhalb einer Datenansicht enthält jede Dimension und Metrik ihre eigenen Einstellungen, die Ihr Unternehmen ändern kann. Diese Änderungen gelten zum Zeitpunkt der Berichtsausführung und werden daher rückwirkend angewendet. Die Einstellungen für Dimension und Metriken in Adobe Analytics ändern die Art und Weise, wie Daten erfasst werden, sodass diese Änderungen ab diesem Zeitpunkt gelten. Wenn Sie Komponenteneinstellungen in einem der Produkte geändert haben, können diese Berichtsunterschiede verursachen. Wenn Sie sich auf eine bestimmte Dimension konzentrieren, stellen Sie sicher, dass die Einstellungen für Attribution und Persistenz zwischen Adobe Analytics und Customer Journey Analytics übereinstimmen.

  >[!TIP]
  >
  >Adobe empfiehlt dringend, dass Dimensionen in Adobe Analytics die Zuordnung &quot;[!UICONTROL Zuletzt verwendet (Letzte)] verwenden. Diese Zuordnungseinstellung ermöglicht eine deutlich höhere Attributionsflexibilität in Customer Journey Analytics.

* **Besuchsdefinition**: Zusätzlich zu den Einstellungen für einzelne Dimensionen und Metriken enthält die Datenansicht selbst Einstellungen, die die Interpretation von Besucherdaten grundlegend ändern. Sie können beispielsweise ein Segment auf eine gesamte Datenansicht anwenden (ähnlich wie bei einer [Virtual Report Suite](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-about) in Adobe Analytics). Sie können auch die Definition einer Besuchsdauer ändern oder automatisch einen neuen Besuch bei einem beliebigen Ereignis starten. Jede dieser Einstellungen kann sich erheblich auf die Unterschiede bei der Berichterstellung zwischen Customer Journey Analytics und Adobe Analytics auswirken.

## Überprüfen der Datensatzanzahl zwischen Produkten

Wenn alle oben genannten Einstellungen ähnlich aussehen und Sie zumindest die Anzahl der Datensätze zwischen den Produkten überprüfen möchten, können Sie die folgenden Schritte verwenden:

1. Adobe Experience Platform Führen Sie in [Abfrage-Services](https://experienceleague.adobe.com/de/docs/experience-platform/query/home) die folgende Abfrage zu Datensätzen insgesamt nach Zeitstempeln aus:

   ```sql
   SELECT
     Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) AS Day,
     Count(_id) AS Records
   FROM  {dataset}
   WHERE   timestamp >= from_utc_timestamp('{fromDate}','UTC')
     AND timestamp < from_utc_timestamp('{toDate}','UTC')
     AND timestamp IS NOT NULL
     AND enduserids._experience.aaid.id IS NOT NULL
   GROUP BY Day
   ORDER BY Day;
   ```

1. Generieren [&#x200B; in Adobe Analytics &#x200B;](https://experienceleague.adobe.com/de/docs/analytics/export/analytics-data-feed/data-feed-overview)Daten-Feeds) Feed-Dateien für den gewünschten Datumsbereich. Zählen Sie die Anzahl der Zeilen innerhalb jeder Datei, indem Sie die folgenden Zeilen identifizieren und ausschließen:

   * `exclude_hit` ist nicht `0` (Daten werden in beiden Produkten aus Analysis Workspace ausgeschlossen)
   * `hit_source` ist `0`, `3`, `5`, `7`, `8`, `9` oder `10` (Datenquellen und andere Nicht-Trefferdaten)
   * `page_event` ist `53` oder `63` (Keep-Alive-Treffer für Streaming-Medien)

   Zeilen, die einem der oben genannten Kriterien entsprechen, sind vom Aufnahme-Workflow des Analytics Source Connectors ausgeschlossen und sollten daher auch beim Zählen von Daten-Feed-Zeilen ausgeschlossen werden.

1. Die Gesamtzahl der Datensätze in Abfrage-Services sollte mit der Anzahl der Zeilen in einem Daten-Feed für denselben Zeitraum übereinstimmen.
