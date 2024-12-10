---
title: Feldbasierte Zuordnung
description: Erläuterung des feldbasierten Stitching
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
source-git-commit: 4ce1b22cce3416b8a82e5c56e605475ae6c27d88
workflow-type: tm+mt
source-wordcount: '1705'
ht-degree: 15%

---

# Feldbasierte Zuordnung

Beim feldbasierten Stitching geben Sie einen Ereignis-Datensatz sowie die beständige ID (Cookie) und die vorübergehende ID (Personen-ID) für diesen Datensatz an. Beim feldbasierten Stitching wird im neuen zugeordneten Datensatz eine neue Spalte für die zugeordnete ID erstellt und diese Spalte für die zugeordnete ID basierend auf Zeilen mit einer vorübergehenden ID für diese bestimmte beständige ID aktualisiert. <br/>Sie können feldbasiertes Stitching verwenden, wenn Sie Customer Journey Analytics als eigenständige Lösung verwenden (ohne Zugriff auf den Experience Platform Identity-Dienst und das zugehörige Identitätsdiagramm). Oder wenn Sie das verfügbare Identitätsdiagramm nicht verwenden möchten.

![Feldbasiertes Stitching](/help/stitching/assets/fbs.png)

## Funktionsweise der feldbasierten Zuordnung

Durch die Zuordnung werden mindestens zwei Durchgänge an Daten in einem bestimmten Datensatz durchgeführt.

- **Live-Stitching**: versucht, jeden Treffer (Ereignis) beim Eintreten zuzuordnen. Treffer von Geräten, die dem Datensatz &quot;neu&quot;sind (sich noch nie authentifiziert haben), werden normalerweise nicht auf dieser Ebene zugeordnet. Treffer von bereits erkannten Geräten werden sofort zugeordnet.

- **Wiederholungszuordnung wiedergeben**: wiederholt Daten basierend auf eindeutigen Kennungen (vorübergehenden IDs), die gelernt wurden. In dieser Phase werden Treffer von zuvor unbekannten Geräten (beständigen IDs) zugeordnet (zu vorübergehenden IDs). Die Wiederholung wird durch zwei Parameter bestimmt: **frequency** und **Lookback-Fenster**. Adobe bietet die folgenden Kombinationen dieser Parameter:
   - **Täglicher Lookback mit täglicher Häufigkeit**: Die Daten werden täglich mit einem 24-Stunden-Lookback-Fenster wiederholt. Diese Option bietet den Vorteil, dass Wiederholungen viel häufiger vorkommen. Nicht authentifizierte Besucher müssen sich jedoch an dem Tag authentifizieren, an dem sie Ihre Website besuchen.
   - **Wöchentliches Lookback mit wöchentlicher Häufigkeit**: Die Daten werden einmal wöchentlich mit einem wöchentlichen Lookback-Fenster wiederholt (siehe [options](#options)). Diese Option bietet den Vorteil, dass nicht authentifizierte Sitzungen über einen weniger eng gefasst Zeitraum für die Authentifizierung verfügen. Nicht zugeordnete Daten, die weniger als eine Woche alt sind, werden jedoch erst bei der nächsten wöchentlichen Wiederholung erneut verarbeitet.
   - **Zweiwöchiges Lookback mit wöchentlicher Häufigkeit**: Daten werden wöchentlich einmal mit einem zweiwöchigen Lookback-Fenster wiederholt (siehe [options](#options)). Diese Option bietet den Vorteil, dass nicht authentifizierte Sitzungen über einen weniger eng gefasst Zeitraum für die Authentifizierung verfügen. Nicht zugeordnete Daten, die weniger als zwei Wochen alt sind, werden jedoch erst bei der nächsten wöchentlichen Wiederholung erneut verarbeitet.
   - **Monatlicher Lookback mit wöchentlicher Häufigkeit**: Daten werden wöchentlich mit einem monatlichen Lookback-Fenster wiederholt (siehe [options](#options)). Diese Option bietet den Vorteil, dass nicht authentifizierte Sitzungen über einen weniger eng gefasst Zeitraum für die Authentifizierung verfügen. Nicht zugeordnete Daten, die weniger als einen Monat alt sind, werden jedoch erst bei der nächsten wöchentlichen Wiederholung erneut verarbeitet.

- **Datenschutz**: Wenn datenschutzbezogene Anfragen empfangen werden, muss nicht nur die angeforderte Identität entfernt werden, sondern auch die Zuordnung dieser Identität zu nicht authentifizierten Ereignissen rückgängig gemacht werden.

  >[!IMPORTANT]
  >
  >Die Aufhebung der Zuordnung als Teil von Datenschutzanfragen wird Anfang 2025 geändert. Der aktuelle Auftrennungsprozess löst Ereignisse anhand der neuesten Version bekannter Identitäten zurück. Diese Umbenennung von Ereignissen zu einer anderen Identität könnte unerwünschte rechtliche Folgen haben. Um diese Bedenken auszuräumen, aktualisiert der neue Auftrennungsprozess ab 2025 Ereignisse, die Gegenstand der Datenschutzanfrage sind, mit der beständigen ID.
  > 


Daten, die über das Lookback-Fenster hinausgehen, werden nicht wiederholt. Ein Besucher muss sich in einem gegebenen Lookback-Fenster authentifizieren, damit ein nicht authentifizierter Besuch und ein authentifizierter Besuch gemeinsam identifiziert werden können. Sobald ein Gerät erkannt wurde, wird es von diesem Punkt an live zugeordnet.

### Schritt 1: Live-Stitching

Die Live-Zuordnung versucht, jedes Ereignis bei der Erfassung bekannten Geräten und Kanälen zuzuordnen.

+++ Details

Im folgenden Beispiel zeichnet Bob verschiedene Ereignisse als Teil eines Ereignis-Datensatzes auf.

*Daten, wie sie am Tag der Erfassung erschienen:*

| Ereignis | Zeitstempel | Beständige ID (Cookie-ID) | Verlaufs-ID (Anmelde-ID) | Zugeordnete ID (nach der Live-Zuordnung) |
|---|---|---|---|---|
| 1 | 12.05.2023 12:01 | `246` ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | `246` | – | **`Bob`** |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | – | **`Bob`** |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | – | **`Bob`** |
| | | **3 Geräte** | | **4 Personen**:<br/>`246`, `Bob`, `3579`, `81911` |

Sowohl nicht authentifizierte als auch authentifizierte Ereignisse auf neuen Geräten werden (vorübergehend) als separate Personen gezählt. Nicht authentifizierte Ereignisse auf erkannten Geräten werden live zugeordnet.

Die Attribution funktioniert, wenn die identifizierende benutzerdefinierte Variable an ein Gerät gebunden ist. Im obigen Beispiel werden alle Ereignisse mit Ausnahme der Ereignisse 1, 8, 9 und 10 live zugeordnet (sie verwenden alle die Kennung `Bob` ). Die Live-Zuordnung &quot;löst&quot;die zugeordnete ID für die Ereignisse 4, 6 und 12 auf.

Verzögerte Daten (Daten mit einem Zeitstempel über 24 Stunden) werden nach bestem Wissen und Gewissen verarbeitet, wobei die Zuordnung aktueller Daten für die höchste Qualität priorisiert wird.

+++

### Schritt 2: Wiederholungszuordnung

In regelmäßigen Abständen (einmal pro Woche oder einmal pro Tag, je nach ausgewähltem Lookback-Fenster) berechnet die Wiederholungszuordnung historische Daten basierend auf Geräten, die sie jetzt erkennt, neu. Wenn ein Gerät anfänglich Daten sendet, ohne authentifiziert zu sein, und sich dann anmeldet, werden diese nicht authentifizierten Ereignisse bei der Wiederholungszuordnung der richtigen Person zugeordnet.

+++ Details

Die folgende Tabelle stellt dieselben Daten wie oben dar, zeigt jedoch unterschiedliche Zahlen basierend auf der Wiederholung der Daten.

*Dieselben Daten nach der Wiederholung:*

| Ereignis | Zeitstempel | Beständige ID (Cookie-ID) | Verlaufs-ID (Anmelde-ID) | Zugeordnete ID (nach der Live-Zuordnung) | Zugeordnete ID (nach der Wiederholung) |
|---|---|---|---|---|---|
| 1 | 12.05.2023 12:01 | `246` | – | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![Pfeil nach oben](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 4 | 2023-05-12 12:04 | `246` | – | **`Bob`** | `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | – | **`Bob`** | `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | – | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![Pfeil nach oben](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | – | **`Bob`** | `Bob` |
| | | **3 Geräte** | | **4 Personen**:<br/>`246`, `Bob`, `3579`, `81911` | **2 Personen**:<br/>`Bob`, `3579` |

{style="table-layout:auto"}

Die Attribution funktioniert, wenn die identifizierende benutzerdefinierte Variable an ein Gerät gebunden ist. Im obigen Beispiel werden die Ereignisse 1 und 10 als Ergebnis der Wiederholung zugeordnet, wobei nur die Ereignisse 8 und 9 aufgetrennt bleiben. und die (kumulative) Personenzahl auf 2 zu reduzieren.

+++

### Schritt 3: Datenschutzanfrage

Wenn Sie eine Datenschutzanfrage erhalten, wird die zugeordnete ID in allen Datensätzen für den Benutzer gelöscht, der der Datenschutzanfrage unterliegt.

+++ Details

Die folgende Tabelle stellt dieselben Daten wie oben dar, zeigt jedoch die Auswirkungen einer Datenschutzanfrage für Bob auf die Daten nach deren Verarbeitung. Die Zeilen, in denen Bob authentifiziert ist, werden entfernt (2, 3, 5, 7 und 11) sowie Bob als vorübergehende ID für andere Zeilen entfernt.

*Dieselben Daten nach einer Datenschutzanfrage für Bob:*

| Ereignis | Zeitstempel | Beständige ID (Cookie-ID) | Verlaufs-ID (Anmelde-ID) | Zugeordnete ID (nach der Live-Zuordnung) | Zugeordnete ID (nach der Wiederholung) | Verlaufs-ID (Anmelde-ID) | Zugeordnete ID (nach Datenschutzanfrage) |
|---|---|---|---|---|---|---|---|
| 1 | 12.05.2023 12:01 | `246` | – | `246` | **`Bob`** | – | `246` |
| 2 | 2023-05-12 12:02 | `246` | Bob ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![Pfeil nach oben](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 3 | 2023-05-12 12:03 | `246` | Bob ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 4 | 2023-05-12 12:04 | `246` | – | **`Bob`** | `Bob` | – | `246` |
| 5 | 2023-05-12 12:05 | `246` | Bob ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 6 | 2023-05-12 12:06 | `246` | – | **`Bob`** | `Bob` | – | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **`3579`** | **`3579`** | – | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **`3579`** | **`3579`** | – | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | – | `81911` | **`Bob`** | – | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![Pfeil nach oben](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | – | **`Bob`** | `Bob` | – | `81911` |
| | | **3 Geräte** | | **4 Personen**:<br/>246, `Bob`, `3579`, `81911` | **2 Personen**:<br/>Bob, `3579` |  | **3 Personen**:<br/>`246`, `3579`, `81911` |

+++

## Voraussetzungen

Die folgenden Voraussetzungen gelten speziell für feldbasiertes Stitching:

- Der Ereignisdatensatz in Adobe Experience Platform, auf den Sie die Zuordnung anwenden möchten, muss über zwei Spalten verfügen, mit denen Besucher identifiziert werden können:

   - Eine **beständige ID**, eine Kennung, die in jeder Zeile verfügbar ist. Beispielsweise eine Besucher-ID, die von einer Adobe Analytics-AppMeasurement-Bibliothek generiert wurde, oder eine ECID, die vom Adobe Experience Platform Identity-Dienst generiert wurde.
   - Eine **vorübergehende ID**, eine Kennung, die nur für einige Zeilen verfügbar ist. Beispiel: ein/e gehashte/r Benutzername oder E-Mail-Adresse, wenn sich ein Besucher authentifiziert. Sie können praktisch jede beliebige Kennung verwenden. Beim Stitching wird dieses Feld für die tatsächlichen Personen-ID-Informationen berücksichtigt. Für optimale Zuordnungsergebnisse sollte für jede beständige ID mindestens einmal innerhalb der Ereignisse des Datensatzes eine vorübergehende ID gesendet werden. Wenn Sie diesen Datensatz in eine Customer Journey Analytics-Verbindung einschließen möchten, sollten die anderen Datensätze ebenfalls eine ähnliche gemeinsame Kennung aufweisen.

- Beide Spalten (beständige ID und vorübergehende ID) müssen als Identitätsfeld mit einem Identitäts-Namespace im Schema für den Datensatz definiert werden, den Sie zuordnen möchten. Bei Verwendung der Identitätszuordnung in Real-time Customer Data Platform müssen Sie mithilfe der [`identityMap`-Feldergruppe](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity) weiterhin Identitätsfelder mit einem Identitäts-Namespace hinzufügen. Diese Identifizierung von Identitätsfeldern ist erforderlich, da das Customer Journey Analytics-Stitching die Feldergruppe `identityMap` nicht unterstützt. Legen Sie beim Hinzufügen eines Identitätsfelds zum Schema und bei Verwendung der Feldergruppe `identityMap` das zusätzliche Identitätsfeld nicht als primäre Identität fest. Das Festlegen eines zusätzlichen Identitätsfelds als primäre Identität behindert die für Real-time Customer Data Platform verwendete Feldgruppe `identityMap` .

## Einschränkungen

Die folgenden Einschränkungen gelten speziell für feldbasiertes Stitching:

- Die aktuellen Funktionen zur Neuzuweisung sind auf einen Schritt beschränkt (beständige ID auf vorübergehende ID). Eine mehrstufige Neuzuweisung wird nicht unterstützt, beispielsweise beständige ID zu vorübergehender ID und dann zu einer weiteren vorübergehenden ID.
- Wenn ein Gerät von mehreren Personen gemeinsam genutzt wird und die Gesamtzahl der Übergänge zwischen Benutzern 50.000 überschreitet, stoppt Customer Journey Analytics die Zuordnung von Daten für dieses Gerät.
- Benutzerdefinierte ID-Maps, die in Ihrem Unternehmen verwendet werden, werden nicht unterstützt.
- Beim Stitching wird zwischen Groß- und Kleinschreibung unterschieden. Für Datensätze, die über den Analytics-Quell-Connector generiert werden, empfiehlt Adobe die Überprüfung aller VISTA-Regeln oder Verarbeitungsregeln, die für das vorübergehende ID-Feld gelten. Diese Überprüfung stellt sicher, dass keine dieser Regeln neue Formen derselben ID einführt. So sollten Sie beispielsweise sicherstellen, dass keine VISTA- oder Verarbeitungsregeln dafür sorgen, dass im Feld für die vorübergehende ID nur für einen Teil der Ereignisse Kleinschreibung verwendet wird.
- Beim Stitching werden keine Felder kombiniert oder verkettet.
- Das Feld für die vorübergehende ID sollte einen einzelnen ID-Typ (IDs aus einem einzelnen Namespace) enthalten. Das Feld für die vorübergehende ID sollte beispielsweise keine Kombination aus Anmelde-IDs und E-Mail-IDs enthalten.
- Wenn mehrere Ereignisse mit demselben Zeitstempel für dieselbe beständige ID auftreten, aber unterschiedliche Werte im Feld der vorübergehenden ID vorhanden sind, wird bei der Zuordnung die ID basierend auf der alphabetischen Reihenfolge ausgewählt. Wenn also eine beständige ID A zwei Ereignisse mit demselben Zeitstempel aufweist und eines der Ereignisse &quot;Bob&quot;und das andere &quot;Ann&quot;angibt, wählt &quot;Zuordnen&quot;Ann.
- Seien Sie vorsichtig bei Szenarien, in denen die vorübergehenden IDs Platzhalterwerte enthalten, z. B. `Undefined`. Weitere Informationen finden Sie in den [FAQ](faq.md) .

