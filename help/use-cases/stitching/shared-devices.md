---
title: Gemeinsam verwendete Geräte
description: Erläuterung der Handhabung gemeinsam genutzter Geräte mithilfe von Stitching und anderen Verfahren.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a7d14968-33a2-46a8-8e32-fb6716650d0a
source-git-commit: 81d1c6abbda63c4ac8cdcc96d1b730974b137ad9
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 7%

---

# Gemeinsam verwendete Geräte

Dieser Artikel bietet Kontext auf gemeinsam genutzten Geräten, wie Daten von gemeinsam genutzten Geräten mithilfe von [Stitching](/help/stitching/overview.md) verarbeitet und gemindert werden können und wie die Belichtung freigegebener Geräte in Ihren Daten mithilfe von Query Service nachvollzogen werden kann.

## Was ist ein freigegebenes Gerät?

Ein gemeinsam genutztes Gerät ist ein Gerät, das von mehr als einer Person verwendet wird. Häufige Szenarien sind Geräte wie Tablets, Geräte, die in Kiosks verwendet werden, oder Computergeräte, die von Agenten in Callcentern gemeinsam genutzt werden.

Wenn zwei Personen dasselbe Gerät verwenden und beide einen Kauf tätigen, können Beispielereignisdaten wie folgt aussehen:

| Ereignis | Zeitstempel | Seitenname | Geräte-ID | E-Mail |
|--:|---|---|---|---|
| 1 | 12.05.2023 12:01 | Startseite | `1234` | |
| 2 | 2023-05-12 12:02 | Produktseite | `1234` | |
| 3 | 2023-05-12 12:03 | Auftragserfolg | `1234` | `ryan@a.com` |
| 4 | 2023-05-12 12:07 | Produktseite | `1234` | |
| 5 | 12.05.2023 12:08 | Auftragserfolg | `1234` | `cassidy@a.com` |

Wie Sie aus dieser Tabelle sehen können, beginnt nach der Authentifizierung bei den Ereignissen 3 und 5 eine Verknüpfung zwischen einer Geräte-ID und einer Personen-ID. Um die Auswirkungen von Marketing-Maßnahmen auf der Ebene der Person zu verstehen, müssen diese nicht authentifizierten Ereignisse der richtigen Person zugeordnet werden.

<!--
The order success (purchase) events assign the data accurately to the correct email. How this assignment impacts your analysis depends on how you perform analysis:

- Device centric approach: analysis performed using the Device ID. With this approach, both authenticated and unauthenticated data are included in analysis. However, this approach does not allow for a more person based analysis. 
- Person centric approach: analysis performed using the email address or other person identifier. With this approach, only authenticated events are included in the analysis. This approach doesn't provide a complete picture of the customer journey, including acquisition

-->

## Verbessern der personenbezogenen Analyse

Der Stitching-Prozess behebt dieses Attributionsproblem, indem die ausgewählte Personen-ID (in den Beispieldaten die E-Mail) zu Ereignissen hinzugefügt wird, bei denen diese Kennung nicht vorhanden ist. Die Zuordnung nutzt eine Zuordnung zwischen Geräte-IDs und Personen-IDs, um sicherzustellen, dass sowohl authentifizierter als auch nicht authentifizierter Traffic in der Analyse verwendet werden kann, sodass er personenbezogen bleibt. Weitere Informationen finden Sie unter [Stitching](/help/stitching/overview.md) .

Durch die Zuordnung können freigegebene Gerätedaten entweder mithilfe der Attribution &quot;last-auth&quot;oder der Attribution &quot;device-split&quot;zugeordnet werden. Alle Versuche, einem bekannten Benutzer nicht authentifizierte Ereignisse zuzuordnen, sind nicht deterministisch.


### Last-auth-Attribution

Last-auth ordnet alle unbekannten Aktivitäten von einem gemeinsam genutzten Gerät dem Benutzer zu, der sich zuletzt authentifiziert hat. Der Experience Platform Identity-Dienst erstellt das Diagramm basierend auf der Attribution der letzten Autoren und wird als solches beim grafikbasierten Stitching verwendet. Weitere Informationen finden Sie unter [Übersicht über die Regeln für die Verknüpfung von Identitätsdiagrammen](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/overview) .

Wenn die Attribution &quot;last-auth&quot;zum Stitching verwendet wird, werden zugeordnete IDs aufgelöst, wie in der folgenden Tabelle dargestellt.

| Zeitstempel | Seitenname | Geräte-ID | E-Mail | Angeheftete ID |
|---|---|---|---|---|
| 12.05.2023 12:01 | Startseite | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:02 | Produktseite | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:03 | Auftragserfolg | `1234` | `ryan@a.com` | `cassidy@a.com` |
| 2023-05-12 12:07 | Produktseite | `1234` | | `cassidy@a.com` |
| 12.05.2023 12:08 | Auftragserfolg | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 13.05.2023 11:08 | Startseite | `1234` | | `cassidy@a.com` |


### Device-split

Die Device-Split-Aktivität ordnet anonyme Aktivitäten von einem gemeinsam genutzten Gerät dem Benutzer in nächster Nähe zur anonymen Aktivität zu. Die Device-Split wird derzeit beim feldbasierten Stitching verwendet.

Wenn beim Stitching die Attribution zwischen Geräten verwendet wird, werden zugeordnete IDs aufgelöst, wie in der folgenden Tabelle dargestellt.

| Zeitstempel | Seitenname | Geräte-ID | E-Mail | Angeheftete ID |
|---|---|---|---|---|
| 12.05.2023 12:01 | Startseite | `1234` | | `ryan@a.com` |
| 2023-05-12 12:02 | Produktseite | `1234` | | `ryan@a.com` |
| 2023-05-12 12:03 | Auftragserfolg | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Produktseite | `1234` | | `ryan@a.com` |
| 12.05.2023 12:08 | Auftragserfolg | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 13.05.2023 11:08 | Startseite | `1234` | | `cassidy@a.com` |


<!--

### ECID reset 

As the name implies, ECID reset implements functionality that resets the ECID on a predetermined trigger, in most cases a login or logout event. With this implementation, a single device gets a new ECID every time the predetermined trigger fires. Essentially, this reset forces the device to become a *new device* over and again from a data perspective. The ECID reset also helps to prevent shared devices from even showing up in the data. No additional algorithms are required, but you have the responsibility to implement the ECID reset signal as part of your Adobe data collection implementation.


When using ECID reset, Stitched IDs resolve as shown in the table below. 

| Timestamp | Page name | Device ID | Email | Stitched ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Home page | `1234` | | `ryan@a.com`| 
| 2023-05-12 12:02 | Product page  | `1234` | |`ryan@a.com` | 
| 2023-05-12 12:03 | Order success | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Product page  | 5678  | | `cassidy@a.com` | 
| 2023-05-12 12:08 | Order success | 5678 |  `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Home page | 5678 | | `cassidy@a.com` |

-->

## Gemeinsame Geräteerkennung

Berücksichtigen Sie verschiedene Faktoren, um richtig zu verstehen, wie weit verbreitete gemeinsam genutzte Geräte in Ihrem Unternehmen sind. Darüber hinaus können Sie anhand des Gesamtbeitrags von Ereignissen von freigegebenen Geräten die Auswirkungen auf die für die Analyse verwendeten gesamten Ereignisdaten nachvollziehen.

Um die Belichtung des gemeinsam genutzten Geräts zu verstehen, können Sie über die Durchführung der folgenden Abfragen nachdenken.

1. **Identifizieren freigegebener Geräte**

   Um die Anzahl der gemeinsam genutzten Geräte zu verstehen, führen Sie eine Abfrage durch, bei der die Geräte-IDs mit zwei oder mehr Personen-IDs gezählt werden. Dies hilft dabei, Geräte zu identifizieren, die von mehreren Personen verwendet werden.

   ```sql
   SELECT COUNT(*)
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
         COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
     FROM /* INSERT DATASET HERE */
     GROUP BY 1
   )
   WHERE transient_count > 1; 
   ```


2. **Zuordnung von Ereignissen zu freigegebenen Geräten**

   Legen Sie für die identifizierten freigegebenen Geräte fest, wie viele Ereignisse von der Gesamtzahl diesen Geräten zugeordnet werden können. Diese Attribution bietet Einblicke in die Auswirkungen freigegebener Geräte auf Ihre Daten und die Auswirkungen auf die Analyse.

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

3. **Anonyme Ereignisse auf freigegebenen Geräten identifizieren**

   Identifizieren Sie unter den Ereignissen, die freigegebenen Geräten zugeordnet sind, wie viele keine Personen-ID besitzen, und geben Sie anonyme Ereignisse an. Der von Ihnen gewählte Algorithmus (z. B. last-auth, device-split oder ECID-reset) zur Verbesserung der Datenqualität wirkt sich auf diese anonymen Ereignisse aus.

   ```sql
   SELECT COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) shared_persistent_ids_anon_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null))) * 100 AS shared_persistent_ids_anon_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

4. **Berechnung der Exposition aufgrund einer Fehlklassifizierung des Ereignisses**

   Schließlich ist zu beurteilen, mit welchem Risiko jeder Kunde aufgrund einer Fehleinstufung von Ereignissen konfrontiert sein könnte. Berechnen Sie den Prozentsatz anonymer Ereignisse über die Gesamtereignisse für jedes gemeinsam genutzte Gerät. Dies hilft dabei, die potenziellen Auswirkungen auf die Genauigkeit von Kundendaten zu verstehen.

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```
