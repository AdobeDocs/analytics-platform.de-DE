---
title: Feldbasierte Zuordnung
description: Erklärung der feldbasierten Zuordnung
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: e5cb55e7-aed0-4598-a727-72e6488f5aa8
source-git-commit: 9b0aceba409bcb8ace39c55a7b0243ebb54ce86e
workflow-type: tm+mt
source-wordcount: '1705'
ht-degree: 15%

---

# Feldbasierte Zuordnung

Bei der feldbasierten Zuordnung geben Sie einen Ereignis-Datensatz sowie die persistente ID (Cookie) und vorübergehende ID (Personen-ID) für diesen Datensatz an. Die feldbasierte Zuordnung erstellt eine neue zugeordnete ID-Spalte im neuen zugeordneten Datensatz und aktualisiert diese zugeordnete ID-Spalte basierend auf Zeilen, die eine vorübergehende ID für diese bestimmte persistente ID haben. <br/>Sie können das feldbasierte Stitching verwenden, wenn Sie Customer Journey Analytics als eigenständige Lösung verwenden (ohne Zugriff auf den Experience Platform Identity Service und das zugehörige Identitätsdiagramm). Oder wenn Sie das verfügbare Identitätsdiagramm nicht verwenden möchten.

![Feldbasiertes Stitching](/help/stitching/assets/fbs.png)

## Funktionsweise des feldbasierten Stitching

Beim Zusammenfügen werden in einem Datensatz mindestens zwei Durchläufe an Daten durchgeführt.

- **Live-Zuordnung**: Versucht, jeden ankommenden Treffer (Ereignis) zuzuordnen. Treffer von Geräten, die „neu“ im Datensatz sind (sich noch nie authentifiziert haben), werden in der Regel nicht auf dieser Ebene zugeordnet. Treffer von bereits erkannten Geräten werden sofort zugeordnet.

- **Wiederholungszuordnung**: Gibt Daten basierend auf eindeutigen Kennungen (vorübergehenden IDs) wieder, die das Team gelernt hat. In diesem Schritt werden Treffer von zuvor unbekannten Geräten (persistente IDs) zugeordnet (zu vorübergehenden IDs). Die Wiederholung wird durch zwei Parameter bestimmt: **Häufigkeit** und **Lookback-Fenster**. Adobe bietet die folgenden Kombinationen dieser Parameter:
   - **Täglicher Lookback in täglicher Häufigkeit**: Daten werden täglich mit einem 24-Stunden-Lookback-Fenster wiederholt. Diese Option bietet den Vorteil, dass Wiederholungen viel häufiger vorkommen. Nicht authentifizierte Besucher müssen sich jedoch an dem Tag authentifizieren, an dem sie Ihre Website besuchen.
   - **Wöchentlicher Lookback in einem wöchentlichen Intervall**: Die Daten werden einmal wöchentlich mit einem wöchentlichen Lookback-Fenster wiederholt (siehe [Optionen](#options)). Diese Option bietet den Vorteil, dass nicht authentifizierte Sitzungen über einen weniger eng gefasst Zeitraum für die Authentifizierung verfügen. Nicht zugeordnete Daten, die weniger als eine Woche alt sind, werden jedoch erst bei der nächsten wöchentlichen Wiederholung erneut verarbeitet.
   - **Vierzehntägiger Lookback in wöchentlicher Häufigkeit**: Die Daten werden einmal wöchentlich mit einem zweiwöchentlichen Lookback-Fenster wiederholt (siehe [Optionen](#options)). Diese Option bietet den Vorteil, dass nicht authentifizierte Sitzungen über einen weniger eng gefasst Zeitraum für die Authentifizierung verfügen. Nicht zugeordnete Daten, die weniger als zwei Wochen alt sind, werden jedoch erst bei der nächsten wöchentlichen Wiederholung erneut verarbeitet.
   - **Monatlicher Lookback mit wöchentlicher Häufigkeit**: Daten werden wöchentlich mit einem monatlichen Lookback-Fenster wiederholt (siehe [Optionen](#options)). Diese Option bietet den Vorteil, dass nicht authentifizierte Sitzungen über einen weniger eng gefasst Zeitraum für die Authentifizierung verfügen. Nicht zugeordnete Daten, die weniger als einen Monat alt sind, werden jedoch erst bei der nächsten wöchentlichen Wiederholung erneut verarbeitet.

- **Datenschutz**: Wenn datenschutzbezogene Anfragen empfangen werden, muss neben dem Entfernen der angeforderten Identität auch jede Zuordnung dieser Identität zu nicht authentifizierten Ereignissen rückgängig gemacht werden.

  >[!IMPORTANT]
  >
  >Der Unstitching-Prozess im Rahmen von Datenschutzanfragen ändert sich Anfang 2025. Der aktuelle Unstitching-Prozess ordnet Ereignisse anhand der neuesten Version bekannter Identitäten neu zu. Diese Neuzuweisung von Ereignissen an eine andere Identität kann unerwünschte rechtliche Folgen haben. Um diese Bedenken zu beheben, werden Ereignisse, die Gegenstand der Datenschutzanfrage sind, ab 2025 durch den neuen Prozess zur Aufhebung der Zuordnung mit der persistenten ID aktualisiert.
  > 


Daten, die über das Lookback-Fenster hinausgehen, werden nicht wiederholt. Ein Besucher muss sich innerhalb eines gegebenen Lookback-Fensters authentifizieren, damit ein nicht authentifizierter Besuch und ein authentifizierter Besuch gemeinsam identifiziert werden können. Sobald ein Gerät erkannt wurde, wird es von diesem Zeitpunkt an live zugeordnet.

### Schritt 1: Echtes Zusammenfügen

Bei der Live-Zuordnung wird versucht, jedes Ereignis bei der Erfassung bekannten Geräten und Kanälen zuzuordnen.

+++ Details

Betrachten Sie das folgende Beispiel, bei dem Bob verschiedene Ereignisse als Teil eines Ereignisdatensatzes aufzeichnet.

*Daten, wie sie am Tag ihrer Erfassung erschienen sind:*

| Ereignis | Zeitstempel | Persistente ID (Cookie-ID) | Vorübergehende ID (Anmelde-ID) | Zugeordnete ID (nach Live-Zuordnung) |
|---|---|---|---|---|
| 1 | 12.05.2023 12:01 | `246` ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **`246`** |
| 2 | 12.05.2023 12:02 | `246` | `Bob` ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 3 | 12.05.2023 12:03 | `246` | `Bob` ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 12.05.2023 12:04 | `246` | – | **`Bob`** |
| 5 | 12.05.2023 12:05 | `246` | `Bob` ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 12.05.2023 12:06 | `246` | – | **`Bob`** |
| 7 | 12.05.2023 12:07 | `246` | `Bob` ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 8 | 12.05.2023 12:03 | `3579` ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **`3579`** |
| 9 | 12.05.2023 12:09 | `3579` ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **`3579`** |
| 10 | 12.05.2023 12:02 | `81911` ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **`81911`** |
| 11 | 12.05.2023 12:05 | `81911` | `Bob` ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 12.05.2023 12:12 | `81911` | – | **`Bob`** |
| | | **3-Geräte** | | **4 Personen**:<br/>`246`, `Bob`, `3579`, `81911` |

Sowohl nicht authentifizierte als auch authentifizierte Ereignisse auf neuen Geräten werden (vorübergehend) als separate Personen gezählt. Nicht authentifizierte Ereignisse auf erkannten Geräten werden live zugeordnet.

Die Attribution funktioniert, wenn die Identifizierung der benutzerdefinierten Variablen an ein Gerät gebunden ist. Im obigen Beispiel sind alle Ereignisse außer den Ereignissen 1, 8, 9 und 10 live zugeordnet (sie verwenden alle die `Bob`). Die Live-Zuordnung „löst“ die zugeordnete ID für Ereignis 4, 6 und 12 auf.

Verzögerte Daten (Daten mit einem Zeitstempel über 24 Stunden) werden nach bestem Bemühen verarbeitet, wobei die Zuordnung aktueller Daten für die höchste Qualität priorisiert wird.

+++

### Schritt 2: Wiederholungszuordnung

In regelmäßigen Abständen (einmal pro Woche oder einmal pro Tag, je nach ausgewähltem Lookback-Fenster) berechnet die Wiederholungszuordnung historische Daten neu, basierend auf Geräten, die sie jetzt erkennt. Wenn ein nicht authentifiziertes Gerät anfänglich Daten sendet und sich dann anmeldet, werden diese nicht authentifizierten Ereignisse durch die Wiederholungszuordnung an die richtige Person gebunden.

+++ Details

Die folgende Tabelle stellt dieselben Daten wie oben dar, zeigt jedoch unterschiedliche Zahlen basierend auf der Wiederholung der Daten.

*Dieselben Daten nach der Wiederholung:*

| Ereignis | Zeitstempel | Persistente ID (Cookie-ID) | Vorübergehende ID (Anmelde-ID) | Zugeordnete ID (nach Live-Zuordnung) | Zusammengefügte ID (nach der Wiederholung) |
|---|---|---|---|---|---|
| 1 | 12.05.2023 12:01 | `246` | – | `246` | **`Bob`** |
| 2 | 12.05.2023 12:02 | `246` | `Bob` ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![Pfeil nach ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 12.05.2023 12:03 | `246` | `Bob` ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 4 | 12.05.2023 12:04 | `246` | – | **`Bob`** | `Bob` |
| 5 | 12.05.2023 12:05 | `246` | `Bob` ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 6 | 12.05.2023 12:06 | `246` | – | **`Bob`** | `Bob` |
| 7 | 12.05.2023 12:07 | `246` | `Bob` ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` |
| 8 | 12.05.2023 12:03 | `3579` ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **`3579`** | **`3579`** |
| 9 | 12.05.2023 12:09 | `3579` ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **`3579`** | **`3579`** |
| 10 | 12.05.2023 12:02 | `81911` | – | `81911` | **`Bob`** |
| 11 | 12.05.2023 12:05 | `81911` | `Bob` ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![Pfeil nach ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 12.05.2023 12:12 | `81911` | – | **`Bob`** | `Bob` |
| | | **3-Geräte** | | **4 Personen**:<br/>`246`, `Bob`, `3579`, `81911` | **2 Personen**:<br/>`Bob`, `3579` |

{style="table-layout:auto"}

Die Attribution funktioniert, wenn die Identifizierung der benutzerdefinierten Variablen an ein Gerät gebunden ist. Im obigen Beispiel werden Ereignis 1 und 10 als Ergebnis der Wiederholung zugeordnet, sodass nur Ereignis 8 und 9 nicht zugeordnet sind. und die Metrik für Personen (kumulativ) auf 2 reduzieren.

+++

### Schritt 3: Datenschutzanfrage

Wenn Sie eine Datenschutzanfrage erhalten, wird die zugeordnete ID in allen Datensätzen für den betroffenen Benutzer der Datenschutzanfrage gelöscht.

+++ Details

Die folgende Tabelle stellt dieselben Daten wie oben dar, zeigt jedoch die Auswirkungen, die eine Datenschutzanfrage für Bob nach der Verarbeitung auf die Daten hat. Die Zeilen, in denen Bob authentifiziert ist, werden entfernt (2, 3, 5, 7 und 11), zusammen mit dem Entfernen von Bob als vorübergehende ID für andere Zeilen.

*Dieselben Daten nach einer Datenschutzanfrage für Bob:*

| Ereignis | Zeitstempel | Persistente ID (Cookie-ID) | Vorübergehende ID (Anmelde-ID) | Zugeordnete ID (nach Live-Zuordnung) | Zusammengefügte ID (nach der Wiederholung) | Vorübergehende ID (Anmelde-ID) | Zusammengefügte ID (nach Datenschutzanfrage) |
|---|---|---|---|---|---|---|---|
| 1 | 12.05.2023 12:01 | `246` | – | `246` | **`Bob`** | – | `246` |
| 2 | 12.05.2023 12:02 | `246` | Bob ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![Pfeil nach ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 3 | 12.05.2023 12:03 | `246` | Bob ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 4 | 12.05.2023 12:04 | `246` | – | **`Bob`** | `Bob` | – | `246` |
| 5 | 12.05.2023 12:05 | `246` | Bob ![Pfeil rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 6 | 12.05.2023 12:06 | `246` | – | **`Bob`** | `Bob` | – | `246` |
| 7 | 12.05.2023 12:07 | `246` | `Bob` ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 8 | 12.05.2023 12:03 | `3579` ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **`3579`** | **`3579`** | – | `3579` |
| 9 | 12.05.2023 12:09 | `3579` ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | – | **`3579`** | **`3579`** | – | `3579` |
| 10 | 12.05.2023 12:02 | `81911` | – | `81911` | **`Bob`** | – | `81911` |
| 11 | 12.05.2023 12:05 | `81911` | `Bob` ![Pfeil nach rechts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![Pfeil nach ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `81911` |
| 12 | 12.05.2023 12:12 | `81911` | – | **`Bob`** | `Bob` | – | `81911` |
| | | **3-Geräte** | | **4 Personen**:<br/>246, `Bob`, `3579`, `81911` | **2 Personen**:<br/>, `3579` |  | **3 Personen**:<br/>`246`, `3579`, `81911` |

+++

## Voraussetzungen

Die folgenden Voraussetzungen gelten speziell für feldbasiertes Stitching:

- Der Ereignisdatensatz in Adobe Experience Platform, auf den Sie eine Zuordnung anwenden möchten, muss zwei Spalten aufweisen, die die Identifizierung der Besuchenden erleichtern:

   - Eine **persistente ID**, eine Kennung, die in jeder Zeile verfügbar ist. Beispielsweise eine Besucher-ID, die von einer Adobe Analytics AppMeasurement-Bibliothek generiert wurde, oder eine vom Adobe Experience Platform Identity Service generierte ECID.
   - Eine **vorübergehende ID**, eine Kennung, die nur für einige Zeilen verfügbar ist. Beispiel: ein/e gehashte/r Benutzername oder E-Mail-Adresse, wenn sich ein Besucher authentifiziert. Sie können praktisch jede Kennung verwenden, die Ihnen gefällt. Beim Zusammenfügen wird berücksichtigt, dass dieses Feld die tatsächlichen Personen-ID-Informationen enthält. Um die besten Ergebnisse beim Zusammenfügen zu erzielen, sollte eine vorübergehende ID mindestens einmal innerhalb der Ereignisse des Datensatzes für jede persistente ID gesendet werden. Wenn Sie diesen Datensatz in eine Customer Journey Analytics-Verbindung einbeziehen möchten, ist es vorzuziehen, dass die anderen Datensätze auch eine ähnliche gemeinsame Kennung haben.

- Beide Spalten (persistente ID und vorübergehende ID) müssen als Identitätsfeld mit einem Identity-Namespace im Schema für den Datensatz definiert werden, den Sie zuordnen möchten. Bei Verwendung der Identitätszuordnung in Real-time Customer Data Platform mithilfe der [`identityMap` Feldergruppe ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity) Sie dennoch Identitätsfelder mit einem Identity-Namespace hinzufügen. Diese Identifizierung von Identitätsfeldern ist erforderlich, da das Customer Journey Analytics-Zusammenfügen die `identityMap` Feldergruppe nicht unterstützt. Legen Sie beim Hinzufügen eines Identitätsfelds zum Schema und gleichzeitiger Verwendung der `identityMap` Feldergruppe das zusätzliche Identitätsfeld nicht als primäre Identität fest. Wenn Sie ein zusätzliches Identitätsfeld als primäre Identität festlegen, wird die für Real-time Customer Data Platform verwendete `identityMap`-Feldergruppe beeinträchtigt.

## Einschränkungen

Die folgenden Einschränkungen gelten speziell für das feldbasierte Stitching:

- Die aktuellen Funktionen zur Neuzuweisung sind auf einen Schritt beschränkt (beständige ID auf vorübergehende ID). Eine mehrstufige Neuzuweisung wird nicht unterstützt, beispielsweise beständige ID zu vorübergehender ID und dann zu einer weiteren vorübergehenden ID.
- Wenn ein Gerät von mehreren Personen gemeinsam genutzt wird und die Gesamtzahl der Transitionen zwischen Benutzerinnen und Benutzern 50.000 überschreitet, stoppt Customer Journey Analytics das Zusammenfügen von Daten für dieses Gerät.
- Benutzerdefinierte ID-Maps, die in Ihrem Unternehmen verwendet werden, werden nicht unterstützt.
- Beim Zusammenfügen wird zwischen Groß- und Kleinschreibung unterschieden. Für Datensätze, die über den Analytics-Quell-Connector generiert werden, empfiehlt Adobe, alle VISTA-Regeln oder Verarbeitungsregeln zu lesen, die für das Feld für die vorübergehende ID gelten. Durch diese Überprüfung wird sichergestellt, dass keine dieser Regeln neue Formen derselben ID einführt. So sollten Sie beispielsweise sicherstellen, dass keine VISTA- oder Verarbeitungsregeln dafür sorgen, dass im Feld für die vorübergehende ID nur für einen Teil der Ereignisse Kleinschreibung verwendet wird.
- Beim Zusammenfügen werden keine Felder kombiniert oder verkettet.
- Das Feld Vorübergehende ID sollte einen einzelnen ID-Typ (IDs aus einem einzelnen Namespace) enthalten. Das Feld für die vorübergehende ID sollte beispielsweise keine Kombination aus Anmelde-IDs und E-Mail-IDs enthalten.
- Wenn mehrere Ereignisse mit demselben Zeitstempel für dieselbe persistente ID auftreten, aber unterschiedliche Werte im Feld für die vorübergehende ID aufweisen, wird die ID beim Zusammenfügen basierend auf der alphabetischen Reihenfolge ausgewählt. Wenn also die persistente ID „A“ zwei Ereignisse mit demselben Zeitstempel enthält und eines der Ereignisse Bob und das andere Ann angibt, wird beim Zusammenfügen Ann ausgewählt.
- Seien Sie vorsichtig bei Szenarien, in denen die vorübergehenden IDs Platzhalterwerte enthalten, z. B. `Undefined`. Weitere Informationen finden [ in ](faq.md) FAQs.
