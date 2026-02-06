---
title: Diagrammbasierte Zuordnung
description: Erläutert das Konzept und die Funktionsweise des diagrammbasierten Stitching.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: ea5c9114-1fc3-4686-b184-2850acb42b5c
source-git-commit: 4c5376171afe7ee830c52cc1066d0645a1adbc5d
workflow-type: tm+mt
source-wordcount: '1741'
ht-degree: 4%

---

# Grafikbasierte Zuordnung

Bei der diagrammbasierten Zuordnung geben Sie einen Ereignis-Datensatz, die persistente ID (Cookie) für diesen Datensatz und den Namespace der gewünschten Personen-ID aus dem Identitätsdiagramm an. Diagrammbasierte Zuordnung versucht, die Personen-ID-Informationen für die Customer Journey Analytics-Datenanalyse bei jedem Ereignis verfügbar zu machen. Die persistente ID wird verwendet, um das Identitätsdiagramm vom Experience Platform Identity Service abzufragen und die Personen-ID aus dem angegebenen Namespace abzurufen.

Wenn die Personen-ID-Informationen für ein Ereignis nicht abgerufen werden können, wird stattdessen die persistente ID für dieses (nicht *)* verwendet. Daher enthält in einer [Datenansicht](/help/data-views/data-views.md) die mit einer [Verbindung“ verknüpft ist, &#x200B;](/help/connections/overview.md) den Datensatz enthält, der für das Zusammenfügen aktiviert ist, die Datenansichtskomponente für die Personen-ID entweder den Personen-ID-Wert oder den beständigen ID-Wert auf der Ereignisebene.


![Diagrammbasiertes Stitching](/help/stitching/assets/gbs.svg)

## IdentityMap

Diagrammbasiertes Stitching unterstützt die Verwendung der [`identityMap` Feldergruppe &#x200B;](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/schema/composition#identity) folgenden Szenarien:

- Verwendung der primären Identität in `identityMap` Namespaces zur Definition der persistenten ID:
   - Wenn mehrere primäre Identitäten in verschiedenen Namespaces gefunden werden, werden die Identitäten in den Namespaces lexikografisch sortiert, und die erste Identität wird ausgewählt.
   - Wenn mehrere primäre Identitäten in einem einzigen Namespace gefunden werden, wird die erste lexikografische primäre Identität ausgewählt, die verfügbar ist.

  Im folgenden Beispiel führen die Namespaces und Identitäten zu einer sortierten primären Identitätsliste und schließlich zur ausgewählten Identität.

  <table style="table-layout:auto">
     <tr>
       <th>Namespaces</th>
       <th>Liste der Identitäten</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>&nbsp;]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table style="table-layout:auto">
    <tr>
      <th>Sortierte Identitätsliste</th>
      <th>Ausgewählte Identität</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>PrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-2", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-1", "namespace": "ECID"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "namespace": "ECID"}<br/>]<br/>NonPrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-1", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-3", "namespace": "ECID"}<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ccid-2",<br/>"namespace": "CCID"</code></pre></td>
    </tr>
  </table>

- Verwendung `identityMap` Namespace zum Definieren der persistenten ID:
   - Wenn mehrere Werte für persistentID in einem `identityMap` Namespace gefunden werden, wird die erste lexikografische verfügbare Identität verwendet.

  Im folgenden Beispiel haben Sie ECID als zu verwendenden Namespace ausgewählt. Diese Auswahl führt zu einer sortierten Identitätsliste und schließlich zur ausgewählten Identität.

  <table style="table-layout:auto">
     <tr>
       <th>Namespaces</th>
       <th>Liste der Identitäten</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table style="table-layout:auto">
    <tr>
      <th>Sortierte Identitätsliste</th>
      <th>Ausgewählte Identität</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;"id": "ecid-1",<br/>&nbsp;&nbsp;"id": "ecid-2",<br/>&nbsp;&nbsp;"id": "ecid-3"<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ecid-1",<br/>"namespace": "ECID"</code></pre></td>
    </tr>
  </table>


## Funktionsweise des diagrammbasierten Stitching

Beim Zusammenfügen werden in einem Datensatz mindestens zwei Durchläufe an Daten durchgeführt.

- **Live-Zuordnung**: Versucht, jeden ankommenden Treffer (Ereignis) zuzuordnen, indem die persistente ID verwendet wird, um die Personen-ID für den ausgewählten Namespace durch Abfrage des Identitätsdiagramms nachzuschlagen. Wenn die Personen-ID von der Suche aus verfügbar ist, wird diese Personen-ID sofort zugeordnet.

- **Wiederholungszuordnung**: *Wiederholt* Daten basierend auf aktualisierten Identitäten aus dem Identitätsdiagramm. In diesem Schritt werden Treffer von zuvor unbekannten Geräten (persistente IDs) zugeordnet, da das Identitätsdiagramm die Identität für einen Namespace aufgelöst hat. Zwei Parameter bestimmen die Wiederholung: **Häufigkeit** und **Lookback-Fenster**. Adobe bietet die folgenden Kombinationen dieser Parameter:
   - **Täglicher Lookback in täglicher Häufigkeit**: Daten werden täglich mit einem 24-Stunden-Lookback-Fenster wiederholt. Diese Option bietet den Vorteil, dass Wiederholungen deutlich häufiger auftreten. Nicht authentifizierte Profile müssen sich jedoch am selben Tag authentifizieren, an dem sie Ihre Site besuchen.
   - **Wöchentlicher Lookback in einem wöchentlichen Intervall**: Die Daten werden einmal wöchentlich mit einem wöchentlichen Lookback-Fenster wiederholt (siehe [Optionen](#options)). Diese Option bietet den Vorteil, dass nicht authentifizierte Sitzungen über einen weniger eng gefasst Zeitraum für die Authentifizierung verfügen. Nicht zugeordnete Daten, die weniger als eine Woche alt sind, werden jedoch erst bei der nächsten wöchentlichen Wiederholung erneut verarbeitet.
   - **Vierzehntägiger Lookback in wöchentlicher Häufigkeit**: Die Daten werden einmal wöchentlich mit einem zweiwöchentlichen Lookback-Fenster wiederholt (siehe [Optionen](#options)). Diese Option bietet den Vorteil, dass nicht authentifizierte Sitzungen über einen weniger eng gefasst Zeitraum für die Authentifizierung verfügen. Nicht zugeordnete Daten, die weniger als zwei Wochen alt sind, werden jedoch erst bei der nächsten wöchentlichen Wiederholung erneut verarbeitet.
   - **Monatlicher Lookback mit wöchentlicher Häufigkeit**: Daten werden wöchentlich mit einem monatlichen Lookback-Fenster wiederholt (siehe [Optionen](#options)). Diese Option bietet den Vorteil, dass nicht authentifizierte Sitzungen über einen weniger eng gefasst Zeitraum für die Authentifizierung verfügen. Nicht zugeordnete Daten, die weniger als einen Monat alt sind, werden jedoch erst bei der nächsten wöchentlichen Wiederholung erneut verarbeitet.

- **Datenschutz**: Wenn datenschutzbezogene Anfragen empfangen werden, muss zusätzlich zum Entfernen der angeforderten Identität aus dem Quelldatensatz jede Zuordnung dieser Identität zu nicht authentifizierten Ereignissen rückgängig gemacht werden. Außerdem muss die Identität aus dem Identitätsdiagramm entfernt werden, um eine zukünftige diagrammbasierte Zuordnung für diese spezifische Identität zu verhindern.

  >[!IMPORTANT]
  >
  >Der Unstitching-Prozess im Rahmen von Datenschutzanfragen ändert sich Anfang 2025. Der aktuelle Unstitching-Prozess ordnet Ereignisse anhand der neuesten Version bekannter Identitäten neu zu. Diese Neuzuweisung von Ereignissen an eine andere Identität kann unerwünschte rechtliche Folgen haben. Um diese Bedenken zu beheben, werden Ereignisse, die Gegenstand der Datenschutzanfrage sind, ab 2025 durch den neuen Prozess zur Aufhebung der Zuordnung mit der persistenten ID aktualisiert.
  > 

Daten, die über das Lookback-Fenster hinausgehen, werden nicht wiederholt. Ein Profil muss innerhalb eines gegebenen Lookback-Fensters authentifiziert werden, damit ein nicht authentifizierter Besuch und ein authentifizierter Besuch gemeinsam identifiziert werden können. Sobald ein Gerät erkannt wurde, wird es von diesem Zeitpunkt an live zugeordnet.

Betrachten Sie die folgenden beiden Identitätsdiagramm-Aktualisierungen im Laufe der Zeit für Besucher A (mit persistenter ID `246`) und Besucher B (mit persistenter ID `3579`) und wie sich diese Aktualisierungen auf die Schritte beim diagrammbasierten Stitching auswirken.

![Identitätsdiagramm 3579](assets/identity-graphs.svg)

Sie können ein Identitätsdiagramm im Zeitverlauf für ein bestimmtes Profil mit dem [Identitätsdiagramm-Viewer](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer) anzeigen. Siehe auch [Verknüpfungslogik für Identity Service](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-linking-logic), um ein besseres Verständnis der beim Verknüpfen von Identitäten verwendeten Logik zu erhalten.

### Schritt 1: Echtes Zusammenfügen

Bei der Live-Zuordnung wird versucht, jedes Ereignis bei der Erfassung mit den zu diesem Zeitpunkt bekannten Informationen aus dem Identitätsdiagramm zu verknüpfen.

+++ Details

| | Zeit | Persistente ID<br/>`ECID` | namespace<br/>`Email` ![DataMapping](/help/assets/icons/DataMapping.svg) | Resultierende ID (nach der Echtzeit-Zuordnung) |
|--:|---|---|---|---|
| 1 | 12.05.2023 11 :00 | `246` | `246` ![Zweig1](/help/assets/icons/Branch1.svg) *undefiniert* | `246` |
| 2 | 12.05.2023 14 :00 | `246` | `246` ![Zweig1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 12.05.2023 15 :00 | `246` | `246` ![Zweig1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 12.05.2023 17 :00 | `3579` | `3579` ![Zweig1](/help/assets/icons/Branch1.svg) *undefiniert* | `3579` |
| 5 | 12.05.2023 19:00 | `3579` | `3579` ![Zweig1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 13.05.2023 15:00 | `246` | `246` ![Zweig1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 13.05.2023 16:30 | `246` | `246` ![Zweig1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![Zweig1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

Sie können sehen, wie für jedes Ereignis die resultierende ID aufgelöst wird. Basierend auf der Zeit, der persistenten ID und der Suche des Identitätsdiagramms für den angegebenen Personen-ID-Namespace.
Wenn die Suche auf mehr als eine resultierende ID aufgelöst wird (wie bei Ereignis 7), wird die lexikografische erste ID ausgewählt, die vom Identitätsdiagramm zurückgegeben wird (`a.b@yahoo.co.uk` im Beispiel).

+++

### Schritt 2: Wiederholungszuordnung

In regelmäßigen Abständen (je nach ausgewähltem Lookback-Fenster) berechnet die Wiederholungszuordnung historische Daten basierend auf der neuesten Version des Identitätsdiagramms zum Zeitpunkt des Intervalls neu.

+++ Details

Bei einer Wiederholungszuordnung vom 13.05.2023 16:30 mit einer 24-Stunden-Lookback-Fensterkonfiguration werden einige Ereignisse aus dem Beispiel erneut zugeordnet (angegeben durch ![Replay](/help/assets/icons/Replay.svg)).

| | Zeit | Persistente ID<br/>`ECID` | namespace<br/>`Email` ![DataMapping](/help/assets/icons/DataMapping.svg) | Ergebene ID<br/>(nach der Echtzeit-Zuordnung) | Ergebnis ID<br/>(nach 24 Stunden Wiederholung) |
|---|---|---|---|---|---|
| 2 | 12.05.2023 14 :00 | `246` | `246` ![Zweig1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 12.05.2023 15 :00 | `246` | `246` ![Zweig1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![Wiederholen](/help/assets/icons/Replay.svg) 4 | 12.05.2023 17 :00 | `3579` | `3579` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Wiederholen](/help/assets/icons/Replay.svg) 5 | 12.05.2023 19:00 | `3579` | `3579` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Wiederholen](/help/assets/icons/Replay.svg) 6 | 13.05.2023 15:00 | `246` | `246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Wiederholen](/help/assets/icons/Replay.svg) 7 | 13.05.2023 16:30 | `246` | `246` ![Zweig1](/help/assets/icons/Branch1.svg)`a.b@yahoo.co.uk`<br/>`246` ![Zweig1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


Mit der Wiederholungszuordnung vom 13.05.2023 16:30 werden bei einer 7-tägigen Lookback-Fensterkonfiguration alle Ereignisse aus der Stichprobe erneut zugeordnet.


| | Zeit | Persistente ID<br/>`ECID` | namespace<br/>`Email` ![DataMapping](/help/assets/icons/DataMapping.svg) | Ergebene ID<br/>(nach der Echtzeit-Zuordnung) | Ergebnis ID<br/>(nach Wiederholung 7 Tage) |
|---|---|---|---|---|---|
| ![Wiederholen](/help/assets/icons/Replay.svg) 1 | 12.05.2023 11 :00 | `246` | `246` ![Zweig1](/help/assets/icons/Branch1.svg) *undefiniert* | `246` | `a.b@yahoo.co.uk` |
| ![Wiederholen](/help/assets/icons/Replay.svg) 2 | 12.05.2023 14 :00 | `246` | `246` ![Zweig1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Wiederholen](/help/assets/icons/Replay.svg) 3 | 12.05.2023 15 :00 | `246` | `246` ![Zweig1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Wiederholen](/help/assets/icons/Replay.svg) 4 | 12.05.2023 17 :00 | `3579` | `3579` ![Zweig1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Wiederholen](/help/assets/icons/Replay.svg) 5 | 12.05.2023 19:00 | `3579` | `3579` ![Zweig1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Wiederholen](/help/assets/icons/Replay.svg) 6 | 13.05.2023 15:00 | `246` | `246` ![Zweig1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Wiederholen](/help/assets/icons/Replay.svg) 7 | 13.05.2023 16:30 | `246` | `246` ![Zweig1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![Zweig1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

### Schritt 3: Datenschutzanfrage

Wenn Sie eine Datenschutzanfrage erhalten, wird die daraus resultierende ID in allen Datensätzen für den betroffenen Benutzer der Datenschutzanfrage gelöscht.

+++ Details

Die folgende Tabelle enthält dieselben Daten wie oben, zeigt jedoch die Auswirkungen, die eine Datenschutzanfrage (z. B. 2023-05-13 18:00) für die Beispielereignisse hat.

| | Zeit | Persistente ID<br/>`ECID` | namespace<br/>`Email` ![DataMapping](/help/assets/icons/DataMapping.svg) | Ergebnis-ID (nach Datenschutzanfrage) |
|--:|---|---|---|---|
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 1 | 12.05.2023 11 :00 | `246` | `246` ![Zweig1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 2 | 12.05.2023 14 :00 | `246` | `246`![Verzweigung1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 3 | 12.05.2023 15 :00 | `246` | `246` ![Zweig1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 4 | 12.05.2023 17 :00 | `3579` | `3579` ![Zweig1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 5 | 12.05.2023 19:00 | `3579` | `3579` ![Zweig1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 6 | 13.05.2023 15:00 | `246` | `246` ![Zweig1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 7 | 13.05.2023 16:30 | `246` | `246` ![Zweig1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![Zweig1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## Voraussetzungen

Die folgenden Voraussetzungen gelten speziell für das diagrammbasierte Stitching:

- Der Ereignisdatensatz in Adobe Experience Platform, auf den Sie eine Zuordnung anwenden möchten, muss eine Spalte aufweisen, die ein Profil in jeder Zeile identifiziert, die **persistente ID**. Beispielsweise eine Besucher-ID, die von einer Adobe Analytics AppMeasurement-Bibliothek generiert wurde, oder eine vom Experience Platform Identity Service generierte ECID.
- Das Identitätsdiagramm von Experience Platform Identity Service muss auf Sandbox-Ebene eingerichtet werden, bevor die diagrammbasierte Zuordnung aktiviert werden kann.
   - Das Identitätsdiagramm muss über einen Namespace verfügen (z. B. `Email` oder `Phone`), den Sie beim Zusammenfügen zum Auflösen der Personen-ID verwenden möchten.
   - Das Identitätsdiagramm muss mit Identitätsinformationen aus allen relevanten Datensätzen (vom Typ *Ereignis* oder *Profil* gefüllt werden, die mindestens zwei nützliche Namespaces mit ID-Werten enthalten.
   - Alle Datensätze, die solche relevanten Identitäten enthalten, müssen [für die Aufnahme von Identitätsdiagrammdaten aktiviert](faq.md#enable-a-dataset-for-the-identity-service). Durch diese Aktivierung wird sichergestellt, dass eingehende Identitäten im Laufe der Zeit aus allen erforderlichen Quellen zum Diagramm hinzugefügt werden.
   - Wenn Sie bereits seit einiger Zeit das Echtzeit-Kundendatenprofil oder Adobe Journey Optimizer verwenden, sollte das Diagramm bis zu einem gewissen Grad bereits eingerichtet sein.<br/>Wenn auch für den Datensatz, der für diagrammbasiertes Stitching aktiviert ist, eine historische Stitching-Aufstockung erforderlich ist, sollte das Diagramm bereits historische Identitäten für den gesamten Zeitraum enthalten, um die gewünschten Stitching-Ergebnisse zu erhalten.
- Wenn Sie die diagrammbasierte Zuordnung verwenden möchten und davon ausgehen, dass der Ereignis-Datensatz zum Identitätsdiagramm beitragen wird, sollten Sie [den Datensatz für den Identity Service aktivieren](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service).
- Die persistente ID und Personen-ID können mit &quot;[&quot; verwendet &#x200B;](#identitymap). Oder die persistente ID und Personen-ID können Felder aus dem XDM-Schema sein. In diesem Fall müssen die Felder [als Identität definiert) &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity?lang=en) Schema sein.

>[!NOTE]
>
>Für **diagrammbasierte** benötigen Sie keine Real-time Customer Data Platform-Lizenz. Das Paket **Prime** oder höher von Customer Journey Analytics enthält die erforderlichen Experience Platform Identity Service-Berechtigungen.


## Einschränkungen

Die folgenden Einschränkungen gelten speziell für das diagrammbasierte Stitching:

- Zeitstempel werden bei der Abfrage der Personen-ID unter Verwendung des angegebenen Namespace nicht berücksichtigt. Es ist also möglich, dass eine persistente ID mit einer Personen-ID aus einem Datensatz verknüpft ist, der einen früheren Zeitstempel hat.
- In Szenarien mit gemeinsam genutzten Geräten, in denen der Namespace im Diagramm mehrere Identitäten enthält, wird die erste lexikografische Identität verwendet. Wenn Namespace-Beschränkungen und -Prioritäten im Rahmen der Veröffentlichung von Diagrammverknüpfungsregeln konfiguriert werden, wird die Identität des letzten authentifizierten Benutzers verwendet. Weitere Informationen finden [&#x200B; unter &#x200B;](/help/use-cases/stitching/shared-devices.md) Geräte .
- Es gibt eine feste Grenze von drei Monaten, bis Identitäten im Identitätsdiagramm aufgestockt werden. Sie würden Identitäten zum Aufstocken verwenden, falls Sie keine Experience Platform-Anwendung wie Real-time Customer Data Platform zum Ausfüllen des Identitätsdiagramms verwenden.
- Es [&#x200B; die „Leitplanken &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails) Identity Service“. Siehe beispielsweise die folgenden [statischen Beschränkungen](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails#static-limits):
   - Maximale Anzahl von Identitäten in einem Diagramm: 50.
   - Maximale Anzahl von Links zu einer Identität für eine einzelne Batch-Aufnahme: 50.
   - Maximale Anzahl von Identitäten in einem XDM-Datensatz für die Diagrammaufnahme: 20.
   - Mindestanzahl von Identitäten in einem XDM-Eintrag für die Diagrammaufnahme: 2.
