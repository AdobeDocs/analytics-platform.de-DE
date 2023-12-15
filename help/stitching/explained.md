---
title: Funktionsweise von Stitching
description: Konzept des Stitching
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 506838a0-0fe3-4b5b-bb9e-2ff20feea8bc
source-git-commit: 2c650cf688112be1e6bf16c0863e743d61f9c35c
workflow-type: tm+mt
source-wordcount: '1109'
ht-degree: 20%

---

# Funktionsweise von Stitching

Die Zuordnung führt mindestens zwei Durchgänge an Daten in einem bestimmten Datensatz durch:

* **Live-Stitching**: versucht, jeden Treffer (Ereignis) beim Eintreten zuzuordnen. Treffer von Geräten, die dem Datensatz &quot;neu&quot;sind (sich noch nie authentifiziert haben), werden normalerweise nicht auf dieser Ebene zugeordnet. Treffer von bereits erkannten Geräten werden sofort zugeordnet.

* **Wiederholungszuordnung**: wiederholt Daten basierend auf eindeutigen Kennungen (vorübergehenden IDs), die gelernt wurden. In dieser Phase werden Treffer von zuvor unbekannten Geräten (beständigen IDs) zugeordnet (zu vorübergehenden IDs). Adobe bietet zwei Wiederholungsintervalle:
   * **Täglich**: Die Daten werden täglich mit einem 24-Stunden-Lookback-Fenster wiederholt. Diese Option bietet den Vorteil, dass Wiederholungen viel häufiger vorkommen. Nicht authentifizierte Besucher müssen sich jedoch an dem Tag authentifizieren, an dem sie Ihre Website besuchen.
   * **Wöchentlich**: Die Daten werden einmal pro Woche mit einem 7-tägigen Lookback-Fenster wiederholt. Diese Option bietet den Vorteil, dass nicht authentifizierte Sitzungen über einen weniger eng gefasst Zeitraum für die Authentifizierung verfügen. Nicht zugeordnete Daten, die weniger als eine Woche alt sind, werden jedoch erst bei der nächsten wöchentlichen Wiederholung erneut verarbeitet.

* **Datenschutz (optional)**: Wenn datenschutzbezogene Anfragen empfangen werden, muss neben der Entfernung der angeforderten Identität auch die Zuordnung dieser Identität zu nicht authentifizierten Ereignissen rückgängig gemacht werden.

Daten, die über das Lookback-Fenster hinausgehen, werden nicht wiederholt. Ein Besucher muss sich innerhalb eines gegebenen Lookback-Fensters authentifiziert haben, damit ein nicht authentifizierter Besuch und ein authentifizierter Besuch gemeinsam identifiziert werden können. Sobald ein Gerät erkannt wurde, wird es von diesem Punkt an live zugeordnet.

## Schritt 1: Live-Stitching

Die Live-Zuordnung versucht, jedes Ereignis bei der Erfassung bekannten Geräten und Kanälen zuzuordnen. Im folgenden Beispiel zeichnet Bob verschiedene Ereignisse als Teil eines Ereignis-Datensatzes auf.

*Daten, wie sie am Tag der Erfassung erscheinen:*

| Ereignis-   | Zeitstempel | Beständige ID (Cookie-ID) | Verlaufs-ID (Anmelde-ID) | Zugeordnete ID (nach der Live-Zuordnung) |
|---|---|---|---|---|
| 1 | 12.05.2023 12:01 | 246 ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **246** |
| 2 | 2023-05-12 12:02 | 246 | Bob ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |
| 3 | 2023-05-12 12:03 | 246 | Bob ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | 246 | – | **Bob** |
| 5 | 2023-05-12 12:05 | 246 | Bob ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | 246 | – | **Bob** | |
| 7 | 2023-05-12 12:07 | 246 | Bob ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |
| 8 | 2023-05-12 12:03 | 3579 ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **3579** |
| 9 | 2023-05-12 12:09 | 3579 ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **3579** |
| 10 | 2023-05-12 12:02 | 81911 ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **81911** |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | 81911 | – | **Bob** |
| | | **3 Geräte** | | **4 Personen**:<br/>246, Bob, 3579, 81911 |

Sowohl nicht authentifizierte als auch authentifizierte Ereignisse auf neuen Geräten werden (vorübergehend) als separate Personen gezählt. Nicht authentifizierte Ereignisse auf erkannten Geräten werden live zugeordnet.

Die Attribution funktioniert, wenn die identifizierende benutzerdefinierte Variable mit einem Gerät verknüpft ist. Im obigen Beispiel werden alle Ereignisse mit Ausnahme der Ereignisse 1, 8, 9 und 10 live zugeordnet (sie verwenden alle die `Bob` Kennung). Die Live-Zuordnung &quot;löst&quot;die zugeordnete ID für die Ereignisse 4, 6 und 12 auf.

Verzögerte Daten (Daten mit einem Zeitstempel über 24 Stunden) werden nach bestem Wissen und Gewissen verarbeitet, wobei die Zuordnung aktueller Daten für die höchste Qualität priorisiert wird.

## Schritt 2: Wiederholungszuordnung

In regelmäßigen Abständen (einmal pro Woche oder einmal pro Tag, je nach ausgewähltem Lookback-Fenster) berechnet die Wiederholungszuordnung historische Daten basierend auf Geräten, die sie jetzt erkennt, neu. Wenn ein Gerät anfänglich Daten sendet, ohne authentifiziert zu sein, und sich dann anmeldet, werden diese nicht authentifizierten Ereignisse bei der Wiederholungszuordnung der richtigen Person zugeordnet. Die folgende Tabelle stellt dieselben Daten wie oben dar, zeigt jedoch unterschiedliche Zahlen basierend auf der Wiederholung der Daten.

*Dieselben Daten nach der Wiederholung:*

| Ereignis-   | Zeitstempel | Beständige ID (Cookie-ID) | Verlaufs-ID (Anmelde-ID) | Zugeordnete ID (nach der Live-Zuordnung) | Zugeordnete ID (nach der Wiederholung) |
|---|---|---|---|---|---|
| 1 | 12.05.2023 12:01 | 246 | – | 246 | **Bob** |
| 2 | 2023-05-12 12:02 | 246 | Bob ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob ![Nach oben](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | 246 | Bob ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob |
| 4 | 2023-05-12 12:04 | 246 | – | **Bob** | Bob |
| 5 | 2023-05-12 12:05 | 246 | Bob ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob |
| 6 | 2023-05-12 12:06 | 246 | – | **Bob** | Bob |
| 7 | 2023-05-12 12:07 | 246 | Bob ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob |
| 8 | 2023-05-12 12:03 | 3579 ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **3579** | **3579** |
| 9 | 2023-05-12 12:09 | 3579 ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **3579** | **3579** |
| 10 | 2023-05-12 12:02 | 81911 | – | 81911 | **Bob** |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob ![Nach oben](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | 81911 | – | **Bob** | Bob |
| | | **3 Geräte** | | **4 Personen**:<br/>246, Bob, 3579, 81911 | **2 Personen**:<br/>Bob, 3579 |

{style="table-layout:auto"}

Die Attribution funktioniert, wenn die identifizierende benutzerdefinierte Variable mit einem Gerät verknüpft ist. Im obigen Beispiel werden die Ereignisse 1 und 10 als Ergebnis der Wiederholung zugeordnet, wobei nur die Ereignisse 8 und 9 aufgetrennt bleiben. und die (kumulative) Personenzahl auf 2 zu reduzieren.

## Schritt 3: Datenschutzanfrage

Wenn Sie eine Datenschutzanfrage erhalten, wird die Zeile mit den ursprünglichen Benutzerinformationen entfernt, zusammen mit allen zugewiesenen IDs, die dieselben Personeninformationen enthalten. Die folgende Tabelle stellt dieselben Daten wie oben dar, zeigt jedoch die Auswirkungen einer Datenschutzanfrage für Bob auf die Daten nach deren Verarbeitung. Die Zeilen, in denen Bob authentifiziert wurde, werden entfernt (2, 3, 5, 7 und 11) sowie Bob als vorübergehende ID für andere Zeilen entfernt.

*Dieselben Daten nach einer Datenschutzanfrage für Bob:*

| Ereignis-   | Zeitstempel | Beständige ID (Cookie-ID) | Verlaufs-ID (Anmelde-ID) | Zugeordnete ID (nach der Live-Zuordnung) | Zugeordnete ID (nach der Wiederholung) | Verlaufs-ID (Anmelde-ID) | Zugeordnete ID (nach Datenschutzanfrage) |
|---|---|---|---|---|---|---|---|
| 1 | 12.05.2023 12:01 | 246 | – | 246 | **Bob** | – | 246 |
| 2 | 2023-05-12 12:02 | 246 | Bob ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob ![Nach oben](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 3 | 2023-05-12 12:03 | 246 | Bob ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 4 | 2023-05-12 12:04 | 246 | – | **Bob** | Bob | – | 246 |
| 5 | 2023-05-12 12:05 | 246 | Bob ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 6 | 2023-05-12 12:06 | 246 | – | **Bob** | Bob | – | 246 |
| 7 | 2023-05-12 12:07 | 246 | Bob ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 8 | 2023-05-12 12:03 | 3579 ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **3579** | **3579** | – | 3579 |
| 9 | 2023-05-12 12:09 | 3579 ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **3579** | **3579** | – | 3579 |
| 10 | 2023-05-12 12:02 | 81911 | – | 81911 | **Bob** | – | 81911 |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob ![Nach oben](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 81911 |
| 12 | 2023-05-12 12:12 | 81911 | – | **Bob** | Bob | – | 81911 |
| | | **3 Geräte** | | **4 Personen**:<br/>246, Bob, 3579, 81911 | **2 Personen**:<br/>Bob, 3579 |  | **3 Personen**:<br/>246, 3579, 81911 |


<!--
| Timestamp | Web dataset Persistent ID | Web dataset Transient ID | Call center person ID | Person ID used (stitched ID) | Explanation of hit | People metric (cumulative) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob visits your site on a desktop, unauthenticated | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob logs in on desktop | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob calls customer service | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob accesses your site on a mobile device, unauthenticated | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob logs in via mobile | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob calls customer service again | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob visits your site on a desktop again, unauthenticated | `1` (Bob) |
-->

## Zusammenfassung

* Beim Stitching werden Ereignisse von bekannten Geräten sofort zugeordnet, Ereignisse von neuen oder nicht erkannten Geräten werden jedoch nicht sofort zugeordnet.
* Die Daten werden in regelmäßigen Abständen wiederholt und ändern die historischen Daten in der Verbindung basierend auf Geräten, die sie zu identifizieren gelernt hat.
* Die Echtzeit-Zuordnung und die Wiederholungszuordnung werden für einen Datensatz durchgeführt. Das Ergebnis ist ein neuer, höher gelegener Datensatz, der bei der Kombination mit anderen Datensätzen (z. B. Callcenter-Daten) besser verwendet werden kann, um kanalübergreifende Analysen durchzuführen.
* Datenschutzanfragen entfernen Identitäten, die in nicht authentifizierte Zeilen übertragen wurden.
