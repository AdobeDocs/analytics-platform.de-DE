---
title: Gemeinsam verwendete Geräte
description: Erläuterung des Umgangs mit gemeinsam genutzten Geräten mithilfe von Stitching und anderen Techniken.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a7d14968-33a2-46a8-8e32-fb6716650d0a
source-git-commit: 9118a3c20158b1a0373fab1b41595aa7b07075f6
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 7%

---

# Gemeinsam verwendete Geräte

In diesem Artikel erhalten Sie Informationen zum Kontext auf freigegebenen Geräten sowie dazu, wie Sie Daten von freigegebenen Geräten mithilfe von [Stitching](/help/stitching/overview.md) verarbeiten und minimieren können und wie Sie die Offenlegung freigegebener Geräte in Ihren Daten mithilfe des Abfrage-Service verstehen können.

## Was ist ein gemeinsam genutztes Gerät?

Ein gemeinsam genutztes Gerät ist ein Gerät, das von mehr als einer Person verwendet wird. Häufige Szenarien sind Geräte wie Tablets, Geräte, die in Kiosken verwendet werden, oder Computer-Geräte, die von Agenten in einem Callcenter gemeinsam genutzt werden.

Wenn zwei Personen dasselbe Gerät verwenden und beide einen Kauf tätigen, können die Beispielereignisdaten wie folgt aussehen:

| Ereignis | Zeitstempel | Seitenname | Geräte-ID | E-Mail |
|--:|---|---|---|---|
| 1 | 12.05.2023 12:01 | Startseite | `1234` | |
| 2 | 12.05.2023 12:02 | Produktseite | `1234` | |
| 3 | 12.05.2023 12:03 | Auftragserfolg | `1234` | `ryan@a.com` |
| 4 | 12.05.2023 12:07 | Produktseite | `1234` | |
| 5 | 12.05.2023 12:08 | Auftragserfolg | `1234` | `cassidy@a.com` |

Wie Sie aus dieser Tabelle sehen können, beginnt sich nach der Authentifizierung bei den Ereignissen 3 und 5 eine Verknüpfung zwischen einer Geräte-ID und einer Personen-ID zu bilden. Um die Auswirkungen von Marketing-Maßnahmen auf der Personenebene zu verstehen, müssen diese nicht authentifizierten Ereignisse der richtigen Person zugeordnet werden.

<!--
The order success (purchase) events assign the data accurately to the correct email. How this assignment impacts your analysis depends on how you perform analysis:

- Device centric approach: analysis performed using the Device ID. With this approach, both authenticated and unauthenticated data are included in analysis. However, this approach does not allow for a more person based analysis. 
- Person centric approach: analysis performed using the email address or other person identifier. With this approach, only authenticated events are included in the analysis. This approach doesn't provide a complete picture of the customer journey, including acquisition

-->

## Personenzentrierte Analyse verbessern

Der Zuordnungsprozess behebt dieses Attributionsproblem, indem die ausgewählte Personenkennung (in den Beispieldaten die E-Mail) zu Ereignissen hinzugefügt wird, bei denen diese Kennung nicht vorhanden ist. Bei der Zuordnung wird eine Zuordnung zwischen Geräte-IDs und Personen-IDs genutzt, um sicherzustellen, dass sowohl authentifizierter als auch nicht authentifizierter Traffic bei der Analyse verwendet werden kann, sodass der Personen-Schwerpunkt erhalten bleibt. Weitere Informationen finden [ unter ](/help/stitching/overview.md).

Bei der Zuordnung können freigegebene Gerätedaten entweder anhand der Attribution der letzten Authentifizierung oder anhand der Attribution auf Geräteaufteilung zugeordnet werden. Alle Versuche, nicht authentifizierte Ereignisse einem bekannten Benutzer zuzuordnen, sind nicht deterministisch.


### Attribution der letzten Authentifizierung

Last-auth schreibt alle unbekannten Aktivitäten eines gemeinsam genutzten Geräts dem Benutzer zu, der sich zuletzt authentifiziert hat. Der Experience Platform Identity Service erstellt das Diagramm basierend auf der Attribution der letzten Authentifizierung und wird als solche beim diagrammbasierten Stitching verwendet. Weitere [ finden Sie unter ](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/identity-optimization-algorithm#identity-optimization-algorithm-details) für Identitätsdiagramme .

Wenn die Attribution der letzten Authentifizierung beim Zusammenfügen verwendet wird, werden zusammengefügte IDs aufgelöst, wie in der folgenden Tabelle dargestellt.

| Zeitstempel | Seitenname | Geräte-ID | E-Mail | Angeheftete ID |
|---|---|---|---|---|
| 12.05.2023 12:01 | Startseite | `1234` | | `cassidy@a.com` |
| 12.05.2023 12:02 | Produktseite | `1234` | | `cassidy@a.com` |
| 12.05.2023 12:03 | Auftragserfolg | `1234` | `ryan@a.com` | `cassidy@a.com` |
| 12.05.2023 12:07 | Produktseite | `1234` | | `cassidy@a.com` |
| 12.05.2023 12:08 | Auftragserfolg | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 13.05.2023 11:08 | Startseite | `1234` | | `cassidy@a.com` |


### Device-split

Device-split schreibt anonyme Aktivität von einem gemeinsam genutzten Gerät dem neuesten bekannten Benutzer zu, der in der Vergangenheit gesucht hat. Device-split wird derzeit beim feldbasierten Stitching verwendet.

Wenn die Attribution „Device-Split“ beim Zusammenfügen verwendet wird, werden zusammengefügte IDs aufgelöst, wie in der folgenden Tabelle dargestellt.

| Zeitstempel | Seitenname | Geräte-ID | E-Mail | Angeheftete ID |
|---|---|---|---|---|
| 12.05.2023 12:01 | Startseite | `1234` | | `ryan@a.com` |
| 12.05.2023 12:02 | Produktseite | `1234` | | `ryan@a.com` |
| 12.05.2023 12:03 | Auftragserfolg | `1234` | `ryan@a.com` | `ryan@a.com` |
| 12.05.2023 12:07 | Produktseite | `1234` | | `ryan@a.com` |
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

## Freigegebene Geräteaufnahme

Beachten Sie mehrere Faktoren, um richtig zu verstehen, wie weit verbreitet freigegebene Geräte in Ihrer Organisation sind. Wenn Sie den Gesamtbeitrag von Ereignissen von gemeinsam genutzten Geräten verstehen, können Sie außerdem die Auswirkungen auf die für die Analyse verwendeten Gesamtereignisdaten besser verstehen.

Um zu verstehen, wie das freigegebene Gerät verfügbar ist, können Sie die folgenden Abfragen durchführen.

1. **Identifizieren freigegebener Geräte**

   Führen Sie eine Abfrage durch, um die Anzahl der freigegebenen Geräte zu verstehen, die die Geräte-IDs mit zwei oder mehr verknüpften Personen-IDs zählt. Dies hilft bei der Identifizierung von Geräten, die von mehreren Personen verwendet werden.

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

   Bestimmen Sie für die identifizierten freigegebenen Geräte, wie viele Ereignisse in der Gesamtzahl diesen Geräten zugeordnet werden können. Diese Attribution bietet Einblicke in die Auswirkungen freigegebener Geräte auf Ihre Daten und die Auswirkungen auf die Analyse.

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

3. **Identifizieren anonymer Ereignisse auf freigegebenen Geräten**

   Identifizieren Sie unter den Ereignissen, die freigegebenen Geräten zugeordnet wurden, wie viele keine Personen-ID aufweisen, was auf anonyme Ereignisse hinweist. Der Algorithmus, den Sie zur Verbesserung der Datenqualität auswählen (z. B. last-auth, device-split oder ECID-reset), wirkt sich auf diese anonymen Ereignisse aus.

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

4. **Berechnung der Exposition aufgrund einer Fehlklassifizierung von Ereignissen**

   Bewerten Sie abschließend das Risiko, dem jeder Kunde aufgrund einer Fehlklassifizierung von Ereignissen ausgesetzt sein könnte. Berechnen Sie den Prozentsatz der anonymen Ereignisse über die Gesamtzahl der Ereignisse für jedes freigegebene Gerät. Auf diese Weise lassen sich die potenziellen Auswirkungen auf die Genauigkeit von Kundendaten besser verstehen.

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
