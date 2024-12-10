---
title: Diagrammbasierte Zuordnung
description: Erläuterung der diagrammbasierten Stitching
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
source-git-commit: 4ce1b22cce3416b8a82e5c56e605475ae6c27d88
workflow-type: tm+mt
source-wordcount: '1361'
ht-degree: 7%

---

# Diagrammbasierte Zuordnung


Bei der diagrammbasierten Zuordnung geben Sie einen Ereignis-Datensatz sowie die beständige ID (Cookie) und den Namespace der vorübergehenden ID (Personen-ID) für diesen Datensatz an. Durch die Diagrammbasierte Zuordnung wird eine neue Spalte für die zugeordnete ID im neuen zugeordneten Datensatz erstellt. Anschließend verwendet die beständige ID, um das Identitätsdiagramm mithilfe des angegebenen Namespace vom Experience Platform Identity-Dienst abzurufen, um die zugeordnete ID zu aktualisieren.

![Graph-based-Stitching](/help/stitching/assets/gbs.png)

## So funktioniert das grafikbasierte Stitching

Durch die Zuordnung werden mindestens zwei Durchgänge an Daten in einem bestimmten Datensatz durchgeführt.

- **Live-Stitching**: versucht, jeden eingehenden Treffer (Ereignis) zuzuordnen, indem die beständige ID verwendet wird, um die vorübergehende ID für den ausgewählten Namespace nachzuschlagen, indem das Identitätsdiagramm abgefragt wird. Wenn die vorübergehende ID aus der Suche verfügbar ist, wird diese vorübergehende ID sofort zugeordnet.

- **Wiederholte Zuordnung wiedergeben**: *wiederholt* Daten basierend auf aktualisierten Identitäten aus dem Identitätsdiagramm. In dieser Phase werden Treffer von zuvor unbekannten Geräten (beständigen IDs) zugeordnet, da das Identitätsdiagramm die Identität für einen Namespace aufgelöst hat. Die Wiederholung wird durch zwei Parameter bestimmt: **frequency** und **Lookback-Fenster**. Adobe bietet die folgenden Kombinationen dieser Parameter:
   - **Täglicher Lookback mit täglicher Häufigkeit**: Die Daten werden täglich mit einem 24-Stunden-Lookback-Fenster wiederholt. Diese Option bietet den Vorteil, dass Wiederholungen viel häufiger vorkommen. Nicht authentifizierte Besucher müssen sich jedoch an dem Tag authentifizieren, an dem sie Ihre Website besuchen.
   - **Wöchentliches Lookback mit wöchentlicher Häufigkeit**: Die Daten werden einmal wöchentlich mit einem wöchentlichen Lookback-Fenster wiederholt (siehe [options](#options)). Diese Option bietet den Vorteil, dass nicht authentifizierte Sitzungen über einen weniger eng gefasst Zeitraum für die Authentifizierung verfügen. Nicht zugeordnete Daten, die weniger als eine Woche alt sind, werden jedoch erst bei der nächsten wöchentlichen Wiederholung erneut verarbeitet.
   - **Zweiwöchiges Lookback mit wöchentlicher Häufigkeit**: Daten werden wöchentlich einmal mit einem zweiwöchigen Lookback-Fenster wiederholt (siehe [options](#options)). Diese Option bietet den Vorteil, dass nicht authentifizierte Sitzungen über einen weniger eng gefasst Zeitraum für die Authentifizierung verfügen. Nicht zugeordnete Daten, die weniger als zwei Wochen alt sind, werden jedoch erst bei der nächsten wöchentlichen Wiederholung erneut verarbeitet.
   - **Monatlicher Lookback mit wöchentlicher Häufigkeit**: Daten werden wöchentlich mit einem monatlichen Lookback-Fenster wiederholt (siehe [options](#options)). Diese Option bietet den Vorteil, dass nicht authentifizierte Sitzungen über einen weniger eng gefasst Zeitraum für die Authentifizierung verfügen. Nicht zugeordnete Daten, die weniger als einen Monat alt sind, werden jedoch erst bei der nächsten wöchentlichen Wiederholung erneut verarbeitet.

- **Datenschutz**: Wenn datenschutzbezogene Anfragen empfangen werden, muss nicht nur die angeforderte Identität aus dem Quelldatensatz entfernt werden, sondern auch die Zuordnung dieser Identität zu nicht authentifizierten Ereignissen rückgängig gemacht werden. Außerdem muss die Identität aus dem Identitätsdiagramm entfernt werden, um das zukünftige grafikbasierte Stitching für diese spezifische Identität zu verhindern.

  >[!IMPORTANT]
  >
  >Die Aufhebung der Zuordnung als Teil von Datenschutzanfragen wird Anfang 2025 geändert. Der aktuelle Auftrennungsprozess löst Ereignisse anhand der neuesten Version bekannter Identitäten zurück. Diese Umbenennung von Ereignissen zu einer anderen Identität könnte unerwünschte rechtliche Folgen haben. Um diese Bedenken auszuräumen, aktualisiert der neue Auftrennungsprozess ab 2025 Ereignisse, die Gegenstand der Datenschutzanfrage sind, mit der beständigen ID.
  > 

Daten, die über das Lookback-Fenster hinausgehen, werden nicht wiederholt. Ein Besucher muss sich in einem gegebenen Lookback-Fenster authentifizieren, damit ein nicht authentifizierter Besuch und ein authentifizierter Besuch gemeinsam identifiziert werden können. Sobald ein Gerät erkannt wurde, wird es von diesem Punkt an live zugeordnet.

Betrachten Sie die folgenden beiden Identitätsdiagramme für die beständige ID `246` und `3579`, wie diese Identitätsdiagramme im Laufe der Zeit aktualisiert werden und wie sich diese Aktualisierungen auf die Schritte beim grafikbasierten Stitching auswirken.

![Identitätsdiagramm 246](assets/identity-graph-246.svg)
![Identitätsdiagramm 3579](assets/identity-graph-3579.svg)

Mit dem [Identitätsdiagramm-Viewer](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer) können Sie ein Identitätsdiagramm für ein bestimmtes Profil im Zeitverlauf anzeigen. Siehe auch [Logik zur Verknüpfung des Identitätsdienstes](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-linking-logic) , um ein besseres Verständnis der Logik zu erhalten, die beim Verknüpfen von Identitäten verwendet wird.

### Schritt 1: Live-Stitching

Die Live-Zuordnung versucht, jedes Ereignis bei der Erfassung bekannten Informationen zu diesem Zeitpunkt aus dem Identitätsdiagramm zuzuordnen.

+++ Details

| | Zeit | Beständige ID<br/>`ECID` | Namespace<br/>`Email` ![Diagramm](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Zugeordnete ID (nach der Live-Zuordnung) |
|--:|---|---|---|---|
| 1 | 12.05.2023 11:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `246` |
| 2 | 2023-05-12 14:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 12.05.2023 17:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `3579` |
| 5 | 12.05.2023 19:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 13.05.2023 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 13.05.2023 16:30 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

Sie können sehen, wie die zugeordnete ID für jedes Ereignis aufgelöst wird. Basierend auf der Zeit, der beständigen ID und der Suche des Identitätsdiagramms für den angegebenen Namespace (zur selben Zeit).
Wenn die Suche zu mehr als einer zugewiesenen ID aufgelöst wird (z. B. Ereignis 7), wird die vom Identitätsdiagramm zurückgegebene lexikografische erste ID ausgewählt (`a.b@yahoo.co.uk` im Beispiel).

+++

### Schritt 2: Wiederholungszuordnung

In regelmäßigen Abständen (je nach ausgewähltem Lookback-Fenster) berechnet die Wiederholungszuordnung historische Daten basierend auf der neuesten Version des Identitätsdiagramms zum Zeitpunkt des Intervalls neu.

+++ Details

Da eine Wiederholungszuordnung zwischen 2023-05-13 16:30 Uhr mit einer 24-Stunden-Lookback-Fensterkonfiguration erfolgt, werden einige Ereignisse aus dem Beispiel neu zugeordnet (gekennzeichnet durch ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)).

| | Zeit | Beständige ID<br/>`ECID` | Namespace<br/>`Email` ![Diagramm](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Zugeordnete ID<br/> (nach der Live-Zuordnung) | Verbundene ID<br/> (nach 24 Stunden Wiederholung) |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 12.05.2023 17:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 12.05.2023 19:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 13.05.2023 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 13.05.2023 16:30 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


Da die Wiederholungszuordnung 2023-05-13 16:30 Uhr mit einer 7-tägigen Lookback-Fensterkonfiguration erfolgt, werden alle Ereignisse aus dem Beispiel erneut zugeordnet.


| | Zeit | Beständige ID<br/>`ECID` | Namespace<br/>`Email` ![Diagramm](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Zugeordnete ID<br/> (nach der Live-Zuordnung) | Zugeordnete ID<br/> (nach der Wiederholung 7 Tage) |
|---|---|---|---|---|---|
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 1 | 12.05.2023 11:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `246` | `a.b@yahoo.co.uk` |
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 2 | 2023-05-12 14:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 12.05.2023 17:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 12.05.2023 19:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 13.05.2023 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Wiederholen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 13.05.2023 16:30 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

### Schritt 3: Datenschutzanfrage

Wenn Sie eine Datenschutzanfrage erhalten, wird die zugeordnete ID in allen Datensätzen für den Benutzer gelöscht, der der Datenschutzanfrage unterliegt.

+++ Details

Die folgende Tabelle stellt dieselben Daten wie oben dar, zeigt jedoch den Effekt, den eine Datenschutzanfrage (z. B. 2023-05-13 18:00 Uhr) für die Beispielereignisse hat.

| | Zeit | Beständige ID<br/>`ECID` | Namespace<br/>`Email` ![Diagramm](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Zugeordnete ID (nach Datenschutzanfrage) |
|--:|---|---|---|---|
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 1 | 12.05.2023 11:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 2 | 2023-05-12 14:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 3 | 2023-05-12 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 4 | 12.05.2023 17:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 5 | 12.05.2023 19:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 6 | 13.05.2023 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 7 | 13.05.2023 16:30 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## Voraussetzungen

Die folgenden Voraussetzungen gelten speziell für das grafikbasierte Stitching:

- Der Ereignisdatensatz in Adobe Experience Platform, auf den Sie die Zuordnung anwenden möchten, muss über eine Spalte verfügen, die einen Besucher in jeder Zeile identifiziert, die **beständige ID**. Beispielsweise eine Besucher-ID, die von einer Adobe Analytics-AppMeasurement-Bibliothek generiert wurde, oder eine ECID, die vom Experience Platform Identity-Dienst generiert wurde.
- Die beständige ID muss auch [als Identität definiert](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/ui/fields/identity) im Schema sein.
- Das Identitätsdiagramm vom Experience Platform Identity Service muss über einen Namespace verfügen (z. B. `Email` oder `Phone`), den Sie beim Stitching verwenden möchten, um die **vorübergehende ID** aufzulösen. Weitere Informationen finden Sie unter [Experience Platform Identity Service](https://experienceleague.adobe.com/de/docs/experience-platform/identity/home) .

>[!NOTE]
>
>Sie benötigen **nicht** eine Real-time Customer Data Platform-Lizenz für das grafikbasierte Stitching. Das Paket **Prime** oder höher von Customer Journey Analytics enthält die erforderlichen Experience Platform Identity Service-Berechtigungen.


## Einschränkungen

Die folgenden Einschränkungen gelten speziell für das grafikbasierte Stitching:

- Zeitstempel werden bei der Abfrage nach der vorübergehenden ID unter Verwendung des angegebenen Namespace nicht berücksichtigt. So ist es möglich, dass eine beständige ID mit einer vorübergehenden ID aus einem Datensatz mit einem früheren Zeitstempel verknüpft wird.
- Keine Unterstützung für freigegebene Geräte Wenn mehrere Identitäten zurückgegeben werden, wird durch Abfrage des Identitätsdiagramms mithilfe eines Namespace die erste lexikografische Identität verwendet.
- Das Aufstocken von Identitäten in das Identitätsdiagramm ist auf drei Monate begrenzt. Sie würden Identitäten aufstocken, falls Sie keine Experience Platform-Anwendung wie Real-time Customer Data Platform verwenden, um das Identitätsdiagramm zu füllen.
- Es gelten die Limits des [Identitätsdienstes](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails). Siehe beispielsweise die folgenden [statischen Beschränkungen](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails#static-limits):
   - Maximale Anzahl von Identitäten in einem Diagramm: 50.
   - Maximale Anzahl der Links zu einer Identität für eine Batch-Erfassung: 50.
   - Maximale Anzahl von Identitäten in einem XDM-Datensatz für die Diagrammaufnahme: 20.
   - Mindestanzahl von Identitäten in einem XDM-Datensatz für die Diagrammaufnahme: 2.
