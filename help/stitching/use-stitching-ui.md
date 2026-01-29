---
title: Zuordnung verwenden
description: Verwendung von Stitching
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
badgePremium: label="Beta" type="Informative"
source-git-commit: 92754044cad67627987b0912367eddc48d1aee89
workflow-type: tm+mt
source-wordcount: '938'
ht-degree: 3%

---

# Zuordnung verwenden

Sie können das Zusammenfügen mit einem oder mehreren Ereignisdatensätzen aktivieren, die Sie im Rahmen Ihrer Verbindung konfiguriert haben. Das von Ihnen lizenzierte Customer Journey Analytics-Paket bestimmt die Anzahl der Ereignisdatensätze, die Sie für das Zusammenfügen aktivieren können.

Sie können das Zusammenfügen als Teil der [Datensatzeinstellungen](/help/connections/create-connection.md#dataset-settings) für einen Ereignisdatensatz aktivieren, wenn Sie [Verbindung erstellen](/help/connections/create-connection.md) oder [Verbindung bearbeiten](/help/connections/manage-connections.md#edit-a-connection).

## Voraussetzungen

So aktivieren Sie die Zuordnung für einen Ereignis-Datensatz in der Connections-Benutzeroberfläche:

* Das Schema, auf dem der Datensatz basiert, sollte Folgendes enthalten:

   * Mehrere Felder, die als Identität konfiguriert sind und es Ihnen ermöglichen, verschiedene Werte für eine persistente ID und eine Personen-ID auszuwählen.
   * Mindestens ein Feld, das als primäre Identität mit einem zugehörigen Namespace markiert ist, falls Sie Identity Map verwenden möchten, und der primäre Identity-Namespace für die persistente ID oder Personen-ID.

* Wenn Sie die diagrammbasierte Zuordnung verwenden möchten und davon ausgehen, dass der Ereignis-Datensatz zum Identitätsdiagramm beitragen wird (da der Datensatz relevante Personen-IDs neben persistenten IDs enthält), sollten [den Datensatz für den Identity Service aktivieren](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service).

## Vorflugkontrollen

Wenn Sie die Voraussetzungen erfüllen, sollten Sie einige Preflight-Prüfungen für die Daten im Ereignis-Datensatz durchführen, bevor Sie die Identitätszuordnung aktivieren:

* Stellen Sie sicher, dass Identitäten im Schema für den Ereignis-Datensatz ordnungsgemäß markiert sind. [Siehe Übersicht über Identity-Namespaces](https://experienceleague.adobe.com/de/docs/experience-platform/identity/features/namespaces).
* Identitätsabdeckung sowohl für persistente ID als auch für Personen-ID überprüfen:
   * Persistente ID: Abfragen von Daten von 7 Tagen, wenn Ihr Feld für persistente ID nicht null ist, und durch eine Abfrage von 7 Tagen Daten für alle Ereignisse in Ihrem Datensatz teilen. Dieser Prozentsatz sollte über 95 % liegen.

     Beispiel einer Abfrage, die Sie zur Überprüfung verwenden können:

     ```sql
     SELECT
       COUNT(*) AS total_events,
       COUNT({PERSISTENT_ID_FIELD}) AS events_with_persistentid,
       ROUND(COUNT({PERSISTENT_ID_FIELD}) / COUNT(*), 2) AS percent_with_persistentid_not_null
     FROM 
       {DATASET_TABLE_NAME}
     WHERE
       TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
       AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
     ```

     Dabei gilt:

      * `{PERSISTENT_ID_FIELD}` ist das Feld für die persistente ID. Beispiel: `identityMap.ecid[0]`.
      * `{DATASET_TABLE_NAME}` ist der Tabellenname für den Ereignis-Datensatz.
      * `{FORMAT_STRING}` ist die Formatzeichenfolge für das Zeitstempelfeld. Beispiel: `MM/DD/YY HH12:MI AM`.
      * `{START_DATE} `ist das Startdatum. Beispiel: `2024-01-01 00:00:00`.
      * `{END_DATE}` ist das Enddatum im Standardformat. Beispiel: `2024-01-08 00:00:00`.


   * Personen-ID - Abfrage von Daten von sieben Tagen, wenn das Feld für Ihre Personen-ID nicht null ist, dividiert durch eine Abfrage von sieben Tagen für Daten für alle Ereignisse in Ihrem Datensatz. Dieser Prozentsatz sollte über 5 % liegen.

     Beispiel einer Abfrage, die Sie zur Überprüfung verwenden können:

     ```sql
     SELECT
       COUNT(*) AS total_events,
       COUNT({PERSON_ID_FIELD}) AS events_with_personid,
       ROUND(COUNT({PERSON_ID_FIELD}) / COUNT(*), 2) AS percent_with_personid_not_null
     FROM 
       {DATASET_TABLE_NAME}
     WHERE
       TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
       AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
     ```

     Dabei gilt:

      * `{PERSON_ID_FIELD}` ist das Feld für die Personen-ID. Beispiel: `identityMap.crmId[0]`.
      * `{DATASET_TABLE_NAME}` ist der Tabellenname für den Ereignis-Datensatz.
      * `{FORMAT_STRING}` ist die Formatzeichenfolge für das Zeitstempelfeld. Beispiel: `MM/DD/YY HH12:MI AM`.
      * `{START_DATE}` ist das Startdatum. Beispiel: `2024-01-01 00:00:00`.
      * `{END_DATE}` ist das Enddatum im Standardformat. Beispiel: `2024-01-08 00:00:00`.



## Aktivieren der Identitätszuordnung

>[!NOTE]
>
>Wenn **[!UICONTROL Identitätszuordnung aktivieren]** in der Verbindungsschnittstelle nicht verfügbar ist, verwenden Sie das [Anfrageverfahren zum Aktivieren der Zuordnung](/help/stitching/use-stitching.md) für einen Datensatz.



Um das Zusammenfügen zu aktivieren, gehen Sie im Abschnitt Ereignisdatensatz des Dialogfelds **[!UICONTROL Datensätze hinzufügen]** oder **[!UICONTROL Datensatz bearbeiten]** folgendermaßen vor:

![Optionen für die Identitätszuordnung beim Aktivieren der Identitätszuordnung](assets/identity-stitching-ui.png)

1. Wählen Sie **[!UICONTROL Identitätszusammenfügung aktivieren]** aus.

   Wenn Sie die Zuordnung für einen vorhandenen Ereignisdatensatz aktivieren, zeigt das Dialogfeld **[!UICONTROL Personen-ID ändern]** die Auswirkungen einer Änderung der Personen-ID aufgrund der Verwendung der Zuordnung an. Wählen Sie **[!UICONTROL Weiter]** aus, um fortzufahren.

   Das **[!UICONTROL „Identitätszuordnung aktivieren]** fasst die Auswirkungen des Zuordnens von Identitäten zusammen. Wählen Sie **[!UICONTROL Weiter]** aus, um fortzufahren.

1. Wählen Sie eine persistente ID aus **[!UICONTROL Dropdown-Menü]** Persistente ID“ aus.

   Wenn Sie **[!UICONTROL Identitätszuordnung]** für die persistente ID auswählen, müssen Sie einen Namespace auswählen. Sie haben zwei Möglichkeiten:

   * Aktivieren Sie **[!UICONTROL Primären Identity-Namespace verwenden]**, um den primären Identity-Namespace zu verwenden.
   * Wählen Sie einen Namespace aus dem **[!UICONTROL Namespace]** Dropdown-Menü aus.

1. Wählen Sie eine Personen-ID aus **[!UICONTROL Dropdown]** Menü „Personen-ID“ aus.

   Wenn Sie **[!UICONTROL Identitätszuordnung]** für die Personen-ID auswählen, müssen Sie einen Namespace auswählen. Sie haben zwei Möglichkeiten:

   * Aktivieren Sie **[!UICONTROL Primären Identity-Namespace verwenden]**, um den primären Identity-Namespace zu verwenden.
   * Wählen Sie einen Namespace aus dem **[!UICONTROL Namespace]** Dropdown-Menü aus.


   Wenn Sie **[!UICONTROL Identitätsdiagramm]** für die Personen-ID (zur Verwendung des [Diagrammbasierten Stitching](/help/stitching/gbs.md)) auswählen, müssen Sie einen Namespace auswählen.

   >[!NOTE]
   >
   >Stellen Sie sicher, dass Sie berechtigt sind, das Identitätsdiagramm zu verwenden.
   >

   Zuvor wird ein Dialogfeld **[!UICONTROL Änderung am Identitätsdiagramm]** angezeigt, um sicherzustellen, dass Sie [die Einrichtung des Identitätsdiagramms für den Datensatz abgeschlossen haben](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) bevor Sie das Identitätsdiagramm zum Zusammenfügen verwenden. Wählen Sie **[!UICONTROL Weiter]** aus, um fortzufahren.

   * Wählen Sie einen Namespace aus dem **[!UICONTROL Namespace]** Dropdown-Menü aus.


1. Wählen Sie ein Lookback-Fenster aus **[!UICONTROL Dropdown-Menü]** Lookback-Fenster“. Die verfügbaren Optionen hängen vom Customer Journey Analytics-Paket ab, zu dem Sie berechtigt sind.

Nachdem Sie eine Verbindung gespeichert haben, wird der Zuordnungsprozess für Datensätze, die für das Zuordnen aktiviert sind, gestartet, wenn die Aufnahme von Daten für diese Datensätze beginnt.

>[!CAUTION]
>
>Bei Datensätzen, die für das Zusammenfügen in der Verbindungsschnittstelle aktiviert sind, wird der Aufstockungsstatus sofort und fälschlicherweise als ![Status grün](/help/assets/icons/StatusGreen.svg) **[!UICONTROL _x _Aufstockungen abgeschlossen]**&#x200B;für die Anzahl der abgeschlossenen Aufstockungen gemeldet. Verwenden Sie andere Möglichkeiten, um zu überprüfen, ob Daten aus dem zusammengefügten Datensatz aufgestockt werden.
>


## Einschränkungen

Zusätzlich zu den [feldbasierten Stitching-Einschränkungen](/help/stitching/fbs.md#limitations) und [graphbasierten Stitching-Einschränkungen](/help/stitching/gbs.md#limitations) gelten die folgenden Einschränkungen, wenn Sie das Stitching in der Verbindungsschnittstelle aktivieren:

* Sie können einen Ereignis-Datensatz nur einmal als Teil einer einzelnen Verbindung zuordnen. Sie können denselben Ereignisdatensatz nicht mehrmals definieren und für jede Instanz eine separate Stitching-Konfiguration verwenden. Wenn Sie verschiedene Zuordnungskonfigurationen auf denselben Datensatz anwenden möchten, verwenden Sie für jede Konfiguration eine separate Verbindung.


## Migration

Das in der Verbindungsschnittstelle aktivierte Stitching kann ohne Probleme mit dem anforderungsbasierten Stitching gleichzeitig verwendet werden.

Sie haben beispielsweise Web-basierte zugeordnete Datensätze im Data Lake aufgrund früherer oder aktueller Zuordnungsanfragen. Sie können zugeordnete Daten aus einem Callcenter-Datensatz über die Schnittstelle Verbindungen hinzufügen, um diese Daten mit den Web-basierten Daten zu kombinieren.

Schließlich migriert Adobe Ihre anforderungsbasierten zugeordneten Datensätze automatisch zum neuen Zuordnungssatz im -Erlebnis.
