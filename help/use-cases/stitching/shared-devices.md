---
title: Freigegebene Geräte
description: Erläuterung der Handhabung gemeinsam genutzter Geräte mithilfe von Stitching und anderen Verfahren.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
role: Admin
source-git-commit: c1ed707f63db87566331783ea24f33cc69721af9
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 6%

---


# Freigegebene Geräte

Dieser Artikel bietet Kontext auf gemeinsam genutzten Geräten, wie Daten von gemeinsam genutzten Geräten mithilfe von Stitching verarbeitet und gemindert werden können und wie die Belichtung freigegebener Geräte in Ihren Daten mithilfe von Query Service verstanden werden kann.

## Was ist ein freigegebenes Gerät?

Ein gemeinsam genutztes Gerät ist ein Gerät, das von mehr als einer Person verwendet wird. Häufige Szenarien sind Geräte wie Tablets, Geräte, die in Kiosks verwendet werden, oder Computergeräte, die von Agenten in Callcentern gemeinsam genutzt werden.

Wenn zwei Personen dasselbe Gerät verwenden und beide einen Kauf tätigen, können Beispielereignisdaten wie folgt aussehen:

| Zeitstempel | Seitenname | Geräte-ID | E-Mail |
|---|---|---|---|
| 12.05.2023 12:01 | Startseite | `1234` | |
| 2023-05-12 12:02 | Produktseite | `1234` | |
| 2023-05-12 12:03 | Auftragserfolg | `1234` | `ryan@a.com` |
| 2023-05-12 12:07 | Produktseite | `1234` | |
| 12.05.2023 12:08 | Auftragserfolg | `1234` | `cassidy@a.com` |

Die Bestellerfolgs- (Kauf-)Ereignisse weisen die Daten der richtigen E-Mail zu. Wie sich diese Zuweisung auf Ihre Analyse auswirkt, hängt davon ab, wie Sie die Analyse durchführen:

- Gerätezentrierter Ansatz: Analyse, die mit der Geräte-ID durchgeführt wird. Bei diesem Ansatz werden sowohl authentifizierte als auch nicht authentifizierte Daten in die Analyse einbezogen. Dieser Ansatz ermöglicht jedoch keine personenbezogene Analyse.
- Personenzentrierter Ansatz: Analyse, die unter Verwendung der E-Mail-Adresse oder einer anderen Personen-ID durchgeführt wird. Bei diesem Ansatz werden nur authentifizierte Ereignisse in die Analyse aufgenommen. Dieser Ansatz liefert kein vollständiges Bild der Journey, einschließlich Akquise

## Verbessern der personenbezogenen Analyse

Um die personenorientierte Analyse freigegebener Geräte zu verbessern, haben Sie zwei Möglichkeiten: Sie können die Zuordnung verwenden oder Sie können die Funktion zum Zurücksetzen der ECID implementieren. Beide Ansätze werden in den folgenden Abschnitten ausführlicher erläutert.

### Stitching

Der Stitching-Prozess befasst sich mit dem Mangel des personenorientierten Ansatzes. Durch die Zuordnung wird die ausgewählte Personen-ID (in den Beispieldaten die E-Mail) zu Ereignissen hinzugefügt, bei denen diese Kennung nicht vorhanden ist. Die Zuordnung nutzt eine Zuordnung zwischen Geräte-IDs und Personen-IDs, um sicherzustellen, dass sowohl authentifizierter als auch nicht authentifizierter Traffic in der Analyse verwendet werden kann, sodass er personenbezogen bleibt. Weitere Informationen finden Sie unter [Stitching](/help/stitching/overview.md) .

Durch die Zuordnung können freigegebene Gerätedaten entweder mithilfe der Attribution &quot;last-auth&quot;oder der Attribution &quot;device-split&quot;zugeordnet werden. Implementierungsänderungen über das Zurücksetzen der ECID können jedoch auch für freigegebene Geräte gelten.


#### Last-auth-Attribution

Last-auth ordnet alle unbekannten Aktivitäten von einem gemeinsam genutzten Gerät dem Benutzer zu, der sich zuletzt authentifiziert hat. Letztauth wird in Audience Manager verwendet und ist der bevorzugte Ansatz für Anwendungsfälle des Echtzeit-Kundendatenprofils. Der Experience Platform Identity-Dienst erstellt das Diagramm basierend auf der Attribution der letzten Autoren und wird als solches beim grafikbasierten Stitching verwendet. Weitere Informationen finden Sie unter [Übersicht über die Regeln für die Verknüpfung von Identitätsdiagrammen](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/overview) .

Bei Verwendung der Attribution &quot;last-auth&quot;beim Stitching lösen zugeordnete IDs auf, wie in der folgenden Tabelle dargestellt.

| Zeitstempel | Seitenname | Geräte-ID | E-Mail | Angeheftete ID |
|---|---|---|---|---|
| 12.05.2023 12:01 | Startseite | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:02 | Produktseite | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:03 | Auftragserfolg | `1234` | `ryan@a.com` | `cassidy@a.com` |
| 2023-05-12 12:07 | Produktseite | `1234` | | `cassidy@a.com` |
| 12.05.2023 12:08 | Auftragserfolg | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 13.05.2023 11:08 | Startseite | `1234` | | `cassidy@a.com` |


#### Device-split

Die Device-Split-Aktivität ordnet anonyme Aktivitäten von einem gemeinsam genutzten Gerät dem Benutzer in nächster Nähe zur anonymen Aktivität zu. Die Device-Split wird derzeit beim feldbasierten Stitching verwendet. Die Geräteaufteilung ist der bevorzugte Ansatz für analytische Anwendungsfälle, da die Geräteaufteilung der nächstbekannten Person sowohl nicht authentifizierte als auch authentifizierte Aktivitäten zuordnet. Die Device-Split wird derzeit beim feldbasierten Stitching verwendet.

Bei der Verwendung der Attribution der Geräteaufteilung bei der Zuordnung lösen zugeordnete IDs auf, wie in der folgenden Tabelle dargestellt.

| Zeitstempel | Seitenname | Geräte-ID | E-Mail | Angeheftete ID |
|---|---|---|---|---|
| 12.05.2023 12:01 | Startseite | `1234` | | `ryan@a.com` |
| 2023-05-12 12:02 | Produktseite | `1234` | | `ryan@a.com` |
| 2023-05-12 12:03 | Auftragserfolg | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Produktseite | `1234` | | `ryan@a.com` |
| 12.05.2023 12:08 | Auftragserfolg | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 13.05.2023 11:08 | Startseite | `1234` | | `cassidy@a.com` |


### ECID-Zurücksetzung

Wie der Name schon sagt, implementiert das ECID-Zurücksetzen Funktionen, die die ECID auf einem vorab festgelegten Trigger zurücksetzen, in den meisten Fällen ein Anmelde- oder Abmeldeereignis. Mit dieser Implementierung erhält ein einzelnes Gerät jedes Mal, wenn der vordefinierte Trigger ausgelöst wird, eine neue ECID. Dieses Zurücksetzen zwingt das Gerät im Wesentlichen dazu, aus Datensicht immer wieder ein *neues Gerät* zu werden. Das Zurücksetzen der ECID hilft auch, zu verhindern, dass freigegebene Geräte auch in den Daten angezeigt werden. Es sind keine zusätzlichen Algorithmen erforderlich, Sie sind jedoch dafür verantwortlich, das ECID-Zurücksetzungssignal im Rahmen Ihrer Adobe-Datenerfassungsimplementierung zu implementieren.


Bei Verwendung des ECID-Resets lösen zugeordnete IDs auf, wie in der folgenden Tabelle dargestellt.

| Zeitstempel | Seitenname | Geräte-ID | E-Mail | Angeheftete ID |
|---|---|---|---|---|
| 12.05.2023 12:01 | Startseite | `1234` | | `ryan@a.com` |
| 2023-05-12 12:02 | Produktseite | `1234` | | `ryan@a.com` |
| 2023-05-12 12:03 | Auftragserfolg | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Produktseite | 5678 | | `cassidy@a.com` |
| 12.05.2023 12:08 | Auftragserfolg | 5678 | `cassidy@a.com` | `cassidy@a.com` |
| 13.05.2023 11:08 | Startseite | 5678 | | `cassidy@a.com` |

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

   Legen Sie für die identifizierten freigegebenen Geräte fest, wie viele Ereignisse von der Gesamtzahl diesen Geräten zugeordnet werden können. Dies bietet Einblicke in die Auswirkungen freigegebener Geräte auf Ihre Daten und die Auswirkungen auf die Analyse.

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


