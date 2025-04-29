---
title: Diagrammbasierte Zuordnung
description: Erklärung der diagrammbasierten Zuordnung
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: ea5c9114-1fc3-4686-b184-2850acb42b5c
source-git-commit: 98432804b71805c3714423dff577bbf80d5c92d1
workflow-type: tm+mt
source-wordcount: '1540'
ht-degree: 7%

---

# Diagrammbasierte Zuordnung


Bei der diagrammbasierten Zuordnung geben Sie einen Ereignis-Datensatz sowie die persistente ID (Cookie) und den Namespace der vorübergehenden ID (Personen-ID) für diesen Datensatz an. Diagrammbasiertes Stitching erstellt eine neue Spalte für die zusammengefügte ID im neuen zusammengefügten Datensatz. und verwendet dann die persistente ID, um das Identitätsdiagramm mithilfe des angegebenen Namespace aus dem Experience Platform Identity Service abzufragen und die zugeordnete ID zu aktualisieren.

![Diagrammbasiertes Stitching](/help/stitching/assets/gbs.png)

## IdentityMap

Diagrammbasiertes Stitching unterstützt die Verwendung der [`identityMap` Feldergruppe ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity) folgenden Szenarien:

- Verwendung der primären Identität in `identityMap` Namespace zum Definieren der persistenten ID:
   - Wenn mehrere primäre Identitäten in verschiedenen Namespaces gefunden werden, werden die Identitäten in den Namespaces lexigrafisch sortiert und die erste Identität wird ausgewählt.
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

  Im folgenden Beispiel führen die Namespaces und Identitäten zu einer sortierten Identitätsliste für den ausgewählten Namespace (ECID) und schließlich zur ausgewählten Identität.

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

- **Live-Zuordnung**: Versucht, jeden ankommenden Treffer (Ereignis) zuzuordnen. Dabei wird die persistente ID verwendet, um die vorübergehende ID für den ausgewählten Namespace durch Abfrage des Identitätsdiagramms nachzuschlagen. Wenn die vorübergehende ID von der Suche aus verfügbar ist, wird diese vorübergehende ID sofort zugeordnet.

- **Wiederholungszuordnung**: *Wiederholt* Daten basierend auf aktualisierten Identitäten aus dem Identitätsdiagramm. In diesem Schritt werden Treffer von zuvor unbekannten Geräten (persistente IDs) zugeordnet, da das Identitätsdiagramm die Identität für einen Namespace aufgelöst hat. Die Wiederholung wird durch zwei Parameter bestimmt: **Häufigkeit** und **Lookback-Fenster**. Adobe bietet die folgenden Kombinationen dieser Parameter:
   - **Täglicher Lookback in täglicher Häufigkeit**: Daten werden täglich mit einem 24-Stunden-Lookback-Fenster wiederholt. Diese Option bietet den Vorteil, dass Wiederholungen viel häufiger vorkommen. Nicht authentifizierte Besucher müssen sich jedoch an dem Tag authentifizieren, an dem sie Ihre Website besuchen.
   - **Wöchentlicher Lookback in einem wöchentlichen Intervall**: Die Daten werden einmal wöchentlich mit einem wöchentlichen Lookback-Fenster wiederholt (siehe [Optionen](#options)). Diese Option bietet den Vorteil, dass nicht authentifizierte Sitzungen über einen weniger eng gefasst Zeitraum für die Authentifizierung verfügen. Nicht zugeordnete Daten, die weniger als eine Woche alt sind, werden jedoch erst bei der nächsten wöchentlichen Wiederholung erneut verarbeitet.
   - **Vierzehntägiger Lookback in wöchentlicher Häufigkeit**: Die Daten werden einmal wöchentlich mit einem zweiwöchentlichen Lookback-Fenster wiederholt (siehe [Optionen](#options)). Diese Option bietet den Vorteil, dass nicht authentifizierte Sitzungen über einen weniger eng gefasst Zeitraum für die Authentifizierung verfügen. Nicht zugeordnete Daten, die weniger als zwei Wochen alt sind, werden jedoch erst bei der nächsten wöchentlichen Wiederholung erneut verarbeitet.
   - **Monatlicher Lookback mit wöchentlicher Häufigkeit**: Daten werden wöchentlich mit einem monatlichen Lookback-Fenster wiederholt (siehe [Optionen](#options)). Diese Option bietet den Vorteil, dass nicht authentifizierte Sitzungen über einen weniger eng gefasst Zeitraum für die Authentifizierung verfügen. Nicht zugeordnete Daten, die weniger als einen Monat alt sind, werden jedoch erst bei der nächsten wöchentlichen Wiederholung erneut verarbeitet.

- **Datenschutz**: Wenn datenschutzbezogene Anfragen empfangen werden, muss zusätzlich zum Entfernen der angeforderten Identität aus dem Quelldatensatz jede Zuordnung dieser Identität zu nicht authentifizierten Ereignissen rückgängig gemacht werden. Außerdem muss die Identität aus dem Identitätsdiagramm entfernt werden, um eine zukünftige diagrammbasierte Zuordnung für diese spezifische Identität zu verhindern.

  >[!IMPORTANT]
  >
  >Der Unstitching-Prozess im Rahmen von Datenschutzanfragen ändert sich Anfang 2025. Der aktuelle Unstitching-Prozess ordnet Ereignisse anhand der neuesten Version bekannter Identitäten neu zu. Diese Neuzuweisung von Ereignissen an eine andere Identität kann unerwünschte rechtliche Folgen haben. Um diese Bedenken zu beheben, werden Ereignisse, die Gegenstand der Datenschutzanfrage sind, ab 2025 durch den neuen Prozess zur Aufhebung der Zuordnung mit der persistenten ID aktualisiert.
  > 

Daten, die über das Lookback-Fenster hinausgehen, werden nicht wiederholt. Ein Besucher muss sich innerhalb eines gegebenen Lookback-Fensters authentifizieren, damit ein nicht authentifizierter Besuch und ein authentifizierter Besuch gemeinsam identifiziert werden können. Sobald ein Gerät erkannt wurde, wird es von diesem Zeitpunkt an live zugeordnet.

Betrachten Sie die folgenden beiden Identitätsdiagramme für persistente ID-`246` und -`3579`, wie diese Identitätsdiagramme im Laufe der Zeit aktualisiert werden und wie sich diese Aktualisierungen auf die Schritte beim diagrammbasierten Stitching auswirken.

![Identitätsdiagramm 246](assets/identity-graph-246.svg)
![Identitätsdiagramm 3579](assets/identity-graph-3579.svg)

Sie können ein Identitätsdiagramm im Zeitverlauf für ein bestimmtes Profil mit dem [Identitätsdiagramm-Viewer](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer) anzeigen. Siehe auch [Verknüpfungslogik für Identity Service](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-linking-logic), um ein besseres Verständnis der beim Verknüpfen von Identitäten verwendeten Logik zu erhalten.

### Schritt 1: Echtes Zusammenfügen

Bei der Live-Zuordnung wird versucht, jedes Ereignis bei der Erfassung mit den zu diesem Zeitpunkt bekannten Informationen aus dem Identitätsdiagramm zu verknüpfen.

+++ Details

| | Zeit | Persistente ID<br/>`ECID` | namespace<br/>`Email` ![graph](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Zugeordnete ID (nach Live-Zuordnung) |
|--:|---|---|---|---|
| 1 | 12.05.2023 11:00 | `246` | `246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `246` |
| 2 | 12.05.2023 14:00 | `246` | `246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 12.05.2023 15:00 | `246` | `246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 12.05.2023 17:00 Uhr | `3579` | `3579` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `3579` |
| 5 | 12.05.2023 19:00 | `3579` | `3579` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 13.05.2023 15:00 | `246` | `246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 13.05.2023 16:30 | `246` | `246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

Sie können sehen, wie für jedes Ereignis die zugeordnete ID aufgelöst wird. Basiert auf der Zeit, der persistenten ID und der Suche des Identitätsdiagramms für den angegebenen Namespace (zur gleichen Zeit).
Wenn die Suche auf mehr als eine zusammengefügte ID aufgelöst wird (wie bei Ereignis 7), wird die lexikografische erste ID ausgewählt, die vom Identitätsdiagramm zurückgegeben wird (`a.b@yahoo.co.uk` im Beispiel).

+++

### Schritt 2: Wiederholungszuordnung

In regelmäßigen Abständen (je nach ausgewähltem Lookback-Fenster) berechnet die Wiederholungszuordnung historische Daten basierend auf der neuesten Version des Identitätsdiagramms zum Zeitpunkt des Intervalls neu.

+++ Details

Bei einer Wiederholungszuordnung um 16:30 Uhr 2023-05-13 mit einer 24-Stunden-Konfiguration des Lookback-Fensters werden einige Ereignisse aus der Stichprobe erneut zugeordnet (angegeben durch ![Replay](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)).

| | Zeit | Persistente ID<br/>`ECID` | namespace<br/>`Email` ![graph](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Zugeordnete ID<br/>(nach Live-Zuordnung) | Zusammengefügte ID<br/>(nach 24 Stunden Wiederholung) |
|---|---|---|---|---|---|
| 2 | 12.05.2023 14:00 | `246` | `246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 12.05.2023 15:00 | `246` | `246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 12.05.2023 17:00 Uhr | `3579` | `3579` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 12.05.2023 19:00 | `3579` | `3579` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 13.05.2023 15:00 | `246` | `246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 13.05.2023 16:30 | `246` | `246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


Bei der Wiederholungszuordnung um 16:30 Uhr 2023-05-13 mit einer 7-tägigen Lookback-Fensterkonfiguration werden alle Ereignisse aus der Stichprobe erneut zugeordnet.


| | Zeit | Persistente ID<br/>`ECID` | namespace<br/>`Email` ![graph](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Zugeordnete ID<br/>(nach Live-Zuordnung) | Zusammengefügte ID<br/>(nach Wiederholung 7 Tage) |
|---|---|---|---|---|---|
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 1 | 12.05.2023 11:00 | `246` | `246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `246` | `a.b@yahoo.co.uk` |
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 2 | 12.05.2023 14:00 | `246` | `246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 3 | 12.05.2023 15:00 | `246` | `246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 12.05.2023 17:00 Uhr | `3579` | `3579` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 12.05.2023 19:00 | `3579` | `3579` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 13.05.2023 15:00 | `246` | `246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 13.05.2023 16:30 | `246` | `246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

### Schritt 3: Datenschutzanfrage

Wenn Sie eine Datenschutzanfrage erhalten, wird die zugeordnete ID in allen Datensätzen für den betroffenen Benutzer der Datenschutzanfrage gelöscht.

+++ Details

Die folgende Tabelle enthält dieselben Daten wie oben, zeigt jedoch die Auswirkungen, die eine Datenschutzanfrage (z. B. 2023-05-13 18:00 Uhr) für die Beispielereignisse hat.

| | Zeit | Persistente ID<br/>`ECID` | namespace<br/>`Email` ![graph](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Zusammengefügte ID (nach Datenschutzanfrage) |
|--:|---|---|---|---|
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 1 | 12.05.2023 11:00 | `246` | `246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 2 | 12.05.2023 14:00 | `246` | `246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 3 | 12.05.2023 15:00 | `246` | `246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 4 | 12.05.2023 17:00 Uhr | `3579` | `3579` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 5 | 12.05.2023 19:00 | `3579` | `3579` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| 6 <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 13.05.2023 15:00 | `246` | `246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| 7 <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 13.05.2023 16:30 | `246` | `246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## Voraussetzungen

Die folgenden Voraussetzungen gelten speziell für das diagrammbasierte Stitching:

- Der Ereignisdatensatz in Adobe Experience Platform, auf den Sie eine Zuordnung anwenden möchten, muss eine Spalte aufweisen, die einen Besucher in jeder Zeile identifiziert, die **persistente ID**. Beispielsweise eine Besucher-ID, die von einer Adobe Analytics AppMeasurement-Bibliothek generiert wurde, oder eine vom Experience Platform Identity Service generierte ECID.
- Die persistente ID muss auch [als Identität definiert) ](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/ui/fields/identity) Schema sein.
- Das Identitätsdiagramm aus Experience Platform Identity Service muss über einen Namespace verfügen (z. B. `Email` oder `Phone`), den Sie beim Zusammenfügen verwenden möchten, um die **vorübergehende ID** aufzulösen. Weitere Informationen finden Sie unter {](https://experienceleague.adobe.com/de/docs/experience-platform/identity/home)}Experience Platform Identity Service.[

>[!NOTE]
>
>Für **diagrammbasierte** benötigen Sie keine Real-time Customer Data Platform-Lizenz. Das Paket **Prime** oder höher von Customer Journey Analytics enthält die erforderlichen Experience Platform Identity Service-Berechtigungen.


## Einschränkungen

Die folgenden Einschränkungen gelten speziell für das diagrammbasierte Stitching:

- Zeitstempel werden bei der Abfrage der vorübergehenden ID unter Verwendung des angegebenen Namespace nicht berücksichtigt. Es ist also möglich, dass eine persistente ID mit einer vorübergehenden ID aus einem Datensatz verknüpft ist, der einen früheren Zeitstempel hat.
- In Szenarien mit gemeinsam genutzten Geräten, in denen der Namespace im Diagramm mehrere Identitäten enthält, wird die erste lexikografische Identität verwendet. Wenn Namespace-Beschränkungen und -Prioritäten im Rahmen der Veröffentlichung von Diagrammverknüpfungsregeln konfiguriert werden, wird die Identität des letzten authentifizierten Benutzers verwendet. Weitere Informationen finden [ unter ](/help/use-cases/stitching/shared-devices.md) Geräte .
- Es gibt eine feste Grenze von drei Monaten, bis Identitäten im Identitätsdiagramm aufgestockt werden. Sie würden Identitäten zum Aufstocken verwenden, falls Sie keine Experience Platform-Anwendung wie Real-time Customer Data Platform zum Ausfüllen des Identitätsdiagramms verwenden.
- Es [ die „Leitplanken ](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails) Identity Service“. Siehe beispielsweise die folgenden [statischen Beschränkungen](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails#static-limits):
   - Maximale Anzahl von Identitäten in einem Diagramm: 50.
   - Maximale Anzahl von Links zu einer Identität für eine einzelne Batch-Aufnahme: 50.
   - Maximale Anzahl von Identitäten in einem XDM-Datensatz für die Diagrammaufnahme: 20.
   - Mindestanzahl von Identitäten in einem XDM-Eintrag für die Diagrammaufnahme: 2.
