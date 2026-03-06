---
title: Zusammenfügung aktivieren
description: Aktivieren der Identitätszuordnung für Ereignis-Datensätze in Customer Journey Analytics. Erfahren Sie, wie Sie in der Verbindungs-Benutzeroberfläche persistente IDs, Personen-IDs und Wiederholungsfenster konfigurieren, um Daten zusammenzufügen.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: b7b2a1f3eb1c149caf65ab3e4321e4f4347695cc
workflow-type: tm+mt
source-wordcount: '1724'
ht-degree: 5%

---

# Aktivieren der Zuordnung

Sie können das Zusammenfügen mit einem oder mehreren Ereignisdatensätzen aktivieren, die Sie im Rahmen Ihrer Verbindung konfiguriert haben. Das von Ihnen lizenzierte Customer Journey Analytics-Paket bestimmt die Anzahl der Ereignisdatensätze, die Sie für das Zusammenfügen aktivieren können.

Sie aktivieren das Zusammenfügen als Teil der [Datensatzeinstellungen](/help/connections/create-connection.md#dataset-settings) für einen Ereignis-Datensatz, wenn Sie [Verbindung erstellen](/help/connections/create-connection.md) oder [Verbindung bearbeiten](/help/connections/manage-connections.md#edit-a-connection).

## Voraussetzungen

Sie müssen die Voraussetzungen für die von Ihnen angegebene Stitching-Methode überprüfen und erfüllen: [feldbasiertes Stitching](fbs.md#prerequisites) oder [grafisches Stitching](gbs.md#prerequisites).


## Vorflugkontrollen

Wenn Sie die Voraussetzungen erfüllen, sollten Sie einige Preflight-Prüfungen für die Daten im Ereignis-Datensatz durchführen, bevor Sie die Identitätszuordnung aktivieren:

* Wenn Sie XDM-Schemafelder für eine persistente ID oder Personen-ID verwenden, stellen Sie sicher, dass Identitäten im Schema für den Ereignis-Datensatz ordnungsgemäß markiert sind. [Siehe Übersicht über Identity-Namespaces](https://experienceleague.adobe.com/de/docs/experience-platform/identity/features/namespaces).
* Identitätsabdeckung sowohl für persistente ID als auch für Personen-ID überprüfen:

   * **Persistent ID**

     Abfragen von Daten von sieben Tagen, wenn Ihr persistentes ID-Feld nicht null ist, geteilt durch eine Abfrage von sieben Tagen mit Daten für alle Ereignisse in Ihrem Datensatz. Dieser Prozentsatz sollte über 95 % liegen.

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


   * **Personen-ID**
      * Stellen Sie bei diagrammbasiertem Stitching sicher, dass das Identitätsdiagramm Fragmente enthält, die ID-Werte aus dem ausgewählten persistenten ID-Namespace und dem Personen-ID-Namespace verknüpfen. Sie können einen Test ausführen, indem Sie zum [Experience Platform Identity Graph Viewer wechseln &#x200B;](https://experienceleague.adobe.com/de/docs/experience-platform/identity/features/identity-graph-viewer){target="_blank"} das Diagramm nach einigen Beispielwerten für persistente IDs abfragen. Überprüfen Sie, ob diese persistenten ID-Werte mit Personen-ID-Werten im Diagramm verknüpft sind.
      * Fragen Sie für das feldbasierte Stitching 7 Tage Daten ab, bei denen das Feld für Ihre Personen-ID nicht null ist, und teilen Sie dies durch eine Abfrage von 7 Tagen Daten für alle Ereignisse in Ihrem Datensatz. Dieser Prozentsatz sollte idealerweise über 5 % liegen.

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



## Aktivieren der Identitätszuordnung {#enable-identity-stitching}

Sie können die Identitätszuordnung aktivieren[&#x200B; wenn Sie &#x200B;](/help/connections/create-connection.md#add-datasets) Ereignis-Datensatz in [&#x200B; personenbasierten Verbindung hinzufügen oder &#x200B;](/help/connections/create-connection.md#edit-a-dataset) bearbeiten. Identitätszuordnung ist für kontobasierte Verbindungen nicht verfügbar.

>[!CONTEXTUALHELP]
>id="connection_changeto_identitygraph"
>title="Änderung am Identitätsdiagramm"
>abstract="Stellen Sie sicher, dass Sie die Einrichtung des Identitätsdiagramms abgeschlossen haben, bevor Sie das Identitätsdiagramm für die Zuordnung verwenden."
>additional-url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/stitching/gbs" text="Diagrammbasierte Zuordnung"

>[!CONTEXTUALHELP]
>id="connection_stitching_personid"
>title="Personen-ID"
>abstract="Wählen Sie eine Personen-ID (die eindeutige Kennung für eine Person) aus den verfügbaren Identitäten aus. Wenn Sie diagrammbasierte Zuordnung verwenden möchten, wählen Sie **[!UICONTROL Identitätsdiagramm]** aus."

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics"
>title="Zusammenfügen von Metriken"
>abstract="Die Zuordnungsmetriken werden anhand eines Beispielsatzes von Daten berechnet, die aus allen Daten stammen, die in den letzten sieben Tagen aufgenommen wurden.<br>Dieser Beispieldatensatz unterscheidet sich in der Regel von den Beispieldaten, die in der Tabelle **[!UICONTROL Vorschau]** verwendet werden."

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_gbs_personidcoverage"
>title="Personen-ID-Abdeckung"
>abstract="Die Abdeckung der ausgewählten Personen-ID, die während des Zuordnungsprozesses (Live und Wiederholung) zur Identifizierung verwendet wird.<br/>Für optimale Stitching-Ergebnisse sollte im Identitätsdiagramm für jede persistente ID eine Beziehung (persistente ID, Personen-ID) vorhanden sein."

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_fbs_personidcoverage"
>title="Personen-ID-Abdeckung"
>abstract="Die Abdeckung der ausgewählten Personen-ID, die während des Zuordnungsprozesses (Live und Wiederholung) zur Identifizierung verwendet wird.<br/>Für optimale Ergebnisse bei der Zuordnung sollte die Personen-ID (Benutzerinformationen) bei mindestens einem Ereignis für jede persistente ID (Geräteinformationen) gesendet werden."

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_persistentidcoverage"
>title="Abdeckung persistenter IDs"
>abstract="Dieser Wert wird während des Zuordnungsprozesses (Live und Wiederholung) zur Identifizierung verwendet, falls ein Personen-ID-Wert nicht erkannt werden kann. <br/>Ereignisse ohne persistente ID und ohne Personen-ID werden aus den Daten gelöscht. Um optimale Ergebnisse beim Zusammenfügen zu erzielen, sollte bei allen Ereignissen eine persistente ID vorhanden sein."


>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_badids"
>title="Fehlerhafte IDs"
>abstract="Ungültige IDs sind ID-Werte, die sich stark auf Berichtsdaten auswirken."
>additional-url="https://experienceleague.adobe.com/de/docs/experience-cloud-kcs/kbarticles/ka-16444" text="Fehlerhafte IDs"


### Datensatzeinstellungen

Um das Zusammenfügen zu aktivieren, gehen Sie im Abschnitt **[!UICONTROL Datensatzeinstellungen]** des Dialogfelds **[!UICONTROL Datensätze hinzufügen]** oder **[!UICONTROL Datensatz bearbeiten]** folgendermaßen vor:

![Optionen für die Identitätszuordnung beim Aktivieren der Identitätszuordnung](assets/identity-stitching-ui.png)

1. Wählen Sie **[!UICONTROL Identitätszusammenfügung aktivieren]** aus.

   Wenn Sie das Zusammenfügen für einen gespeicherten Ereignisdatensatz in der Verbindung aktivieren oder deaktivieren, zeigt **[!UICONTROL Dialogfeld „Personen-ID ändern]** die Auswirkungen einer Änderung der Personen-ID an. Wählen Sie **[!UICONTROL Weiter]** aus, um fortzufahren.

   Das **[!UICONTROL „Identitätszuordnung aktivieren]** fasst die Auswirkungen des Zuordnens von Identitäten zusammen. Wählen Sie **[!UICONTROL Weiter]** aus, um fortzufahren.

1. Wählen Sie eine persistente ID aus **[!UICONTROL Dropdown-Menü]** Persistente ID“ aus.

   Wenn Sie **[!UICONTROL Identitätszuordnung]** für die persistente ID auswählen, müssen Sie einen Namespace auswählen. Sie haben zwei Möglichkeiten:

   * Wählen Sie **[!UICONTROL Primären Identity-Namespace verwenden]** aus, um den primären Identity-Namespace zu verwenden.
   * Wählen Sie einen Namespace aus dem **[!UICONTROL Namespace]** Dropdown-Menü aus.

1. Wählen Sie eine Personen-ID aus **[!UICONTROL Dropdown]** Menü „Personen-ID“ aus.

   Wenn Sie **[!UICONTROL Identitätszuordnung]** für die Personen-ID auswählen, müssen Sie einen Namespace auswählen. Sie haben zwei Möglichkeiten:

   * Wählen Sie **[!UICONTROL Primären Identity-Namespace verwenden]** aus, um den primären Identity-Namespace zu verwenden.
   * Wählen Sie einen Namespace aus dem **[!UICONTROL Namespace]** Dropdown-Menü aus.


   Wenn Sie **[!UICONTROL Identitätsdiagramm]** für die Personen-ID (zur Verwendung des [Diagrammbasierten Stitching](/help/stitching/gbs.md)) auswählen, müssen Sie einen Namespace auswählen.

   >[!NOTE]
   >
   >Stellen Sie sicher, dass Sie berechtigt sind, das Identitätsdiagramm zu verwenden.
   >

   Zuvor wird das Dialogfeld **[!UICONTROL Änderung am Identitätsdiagramm]** angezeigt, um sicherzustellen, dass Sie die Einrichtung des Identitätsdiagramms für den Datensatz abgeschlossen haben. Diese Einrichtung ist Teil der [Diagrammbasierten Voraussetzungen](/help/stitching/gbs.md#prerequisites) bevor Sie das Identitätsdiagramm zum Zusammenfügen verwenden können. Wählen Sie **[!UICONTROL Weiter]** aus, um fortzufahren.

   * Wählen Sie einen Namespace aus dem **[!UICONTROL Namespace]** Dropdown-Menü aus.

1. Wählen Sie im Dropdown-Menü **[!UICONTROL Wiederholungsfenster]** ein Wiederholungsfenster aus. Die verfügbaren Optionen hängen vom Customer Journey Analytics-Paket ab, zu dem Sie berechtigt sind.

1. Wählen Sie **[!UICONTROL Weiter]** aus, um eine Vorschau des Ereignis-Datensatzes anzuzeigen, der zugeordnet werden soll.


### Datensatzvorschau

Zusätzlich zur standardmäßigen Benutzeroberfläche **[!UICONTROL Datensatzvorschau]** stehen beim [Hinzufügen](/help/connections/create-connection.md#add-datasets) oder [Bearbeiten](/help/connections/create-connection.md#edit-a-dataset) von Datensätzen in einer personenbasierten Verbindung zwei zusätzliche Informationsbereiche zur Verfügung.

>[!NOTE]
>Für Kunden, die Customer Journey Analytics auf AWS bereitgestellt haben, steht diese Funktion zur Veröffentlichung aus.
>

![Optionen für die Identitätszuordnung beim Aktivieren der Identitätszuordnung](assets/identity-stitching-ui-preview.png)

#### Zusammenfügen von Metriken



**[!UICONTROL Zuordnungsmetriken]** werden anhand eines Beispielsatzes von Daten berechnet, die aus allen Daten stammen, die in den letzten sieben Tagen aufgenommen wurden. Dieser Beispieldatensatz unterscheidet sich in der Regel von den Beispieldaten, die in der Tabelle **[!UICONTROL Vorschau]** verwendet werden. Zuordnungsmetriken bieten Details für:

* **[!UICONTROL Personen-ID-Abdeckung]**: Die Abdeckung der ausgewählten Personen-ID, die während des Zuordnungsprozesses (Live und Wiederholung) zur Identifizierung verwendet wird.
   * Für die besten feldbasierten Zuordnungsergebnisse sollte bei mindestens einem Ereignis für jede persistente ID (Geräteinformationen) eine Personen-ID (Benutzerinformationen) gesendet werden.
   * Für die besten diagrammbasierten Zuordnungsergebnisse sollte im Identitätsdiagramm für jede persistente ID eine Beziehung (persistente ID, Personen-ID) vorhanden sein.

  Die Personen-ID-Abdeckung wird als Prozentsatz angezeigt und mit den Empfehlungen bei einer stabilen Entwicklung oder in einer Produktionseinrichtung verglichen. Je höher dieser Abdeckungswert ist, desto bessere Stitching-Ergebnisse werden mit der ausgewählten Personen-ID erzielt.

* **[!UICONTROL Persistente ID-Abdeckung]**: Dieser Wert wird während des Zuordnungsprozesses (Live und Wiederholung) zur Identifizierung verwendet, falls ein Personen-ID-Wert nicht erkannt werden kann. Ereignisse ohne persistente ID und ohne Personen-ID werden aus den Daten gelöscht. Um optimale Ergebnisse beim Zusammenfügen zu erzielen, sollte bei allen Ereignissen eine persistente ID vorhanden sein.

  Die persistente ID-Abdeckung wird als Prozentsatz angezeigt und mit dem verglichen, was bei einer stabilen Entwicklung oder in einer Produktionseinrichtung als Minimum empfohlen wird.


#### Fehlerhafte IDs

>[!INFO]
>
>Fehlerhafte IDs werden in der Customer Journey Analytics-Benutzeroberfläche auch als BAVIDs bezeichnet.
> 

In Customer Journey Analytics ist eine ungültige ID ein Bezeichner:

* mit einem bestimmten ID-Wert, der entweder aus einem persistenten ID- oder einem Personen-ID-Feld in zusammenfügbaren Datensätzen stammt, **und**
* ist auf mehr als eine Million (1.000.000) Ereignisse in den Verbindungsdaten innerhalb eines Monats zurückzuführen.

Wenn ein ID-Wert als ungültige ID markiert wird, werden alle zukünftigen Ereignisse, die diesen ID-Wert enthalten, aus den Verbindungsdaten verworfen und nicht im Bericht angezeigt.

Beispiele für Anwendungsfälle mit ungültigen IDs:

* Das Feld Personen-ID enthält benutzerdefinierte Werte oder Platzhalterwerte (z. B. `undefined`). Solche Werte können sich auch auf [Zuordnung und Qualität der Berichtsdaten](/help/stitching/faq.md#undefined-person-id-values) auswirken.
* Wenn sich in einer feldbasierten Stitching-Konfiguration mehrere Personen ein Gerät teilen und die Gesamtzahl der Transitionen zwischen Benutzerinnen und Benutzern 50.000 überschreitet. In diesem Szenario stoppt der Zuordnungsprozess die Verwendung der Personen-ID-Informationen für dieses Gerät und verwendet stattdessen nur persistente ID-Informationen. Folglich werden alle Datensatzereignisse von diesem Gerät an Verbindungsdaten mit der persistenten ID-Identität gesendet, was mit hoher Wahrscheinlichkeit zu einer Situation mit schlechten IDs führt.


>[!NOTE]
>Die **[!UICONTROL Zuordnungsmetriken]** einschließlich **[!UICONTROL ungültiger IDs]** werden auf Grundlage eines begrenzten Satzes von Daten berechnet. Informationen zum Identifizieren fehlerhafter IDs für einen Datensatz, den Sie zum Zusammenfügen verwenden möchten, finden Sie in der Technote [Fehlerhafte IDs](/help/technotes/badids.md).
>


### Speichern

Nachdem Sie eine Verbindung gespeichert haben, wird der Zuordnungsprozess für aktivierte Datensätze gestartet, sobald die Aufnahme von Daten für diese Datensätze beginnt.

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

Schließlich migriert Adobe Ihre anforderungsbasierten zugeordneten Datensätze zum neuen Zuordnungssatz im -Erlebnis.
