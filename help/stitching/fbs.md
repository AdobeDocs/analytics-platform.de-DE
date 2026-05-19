---
title: Feldbasierte Zuordnung
description: Erläutert das Konzept und die Funktionsweise des feldbasierten Stitching.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: e5cb55e7-aed0-4598-a727-72e6488f5aa8
TQID: https://experienceleague.adobe.com/xqNEj5V-fQTo-8j5S9Ad-5ZezRjjr8kdt2Xmx0U8xDI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: d682e1e729402bff7a3f6e3625402f57deee21ad
workflow-type: tm+mt
source-wordcount: 1902
ht-degree: 82%

---

# Feldbasierte Zuordnung

Bei der feldbasierten Zuordnung geben Sie einen Ereignis-Datensatz sowie die persistente ID (Cookie) und Personen-ID für diesen Datensatz an. Bei der feldbasierten Zuordnung wird versucht, die Personen-ID-Informationen für die Customer Journey Analytics-Datenanalyse bei allen anonymen Ereignissen mit einer bestimmten persistenten ID verfügbar zu machen.  Diese Informationen werden aus den Zeilen abgerufen, die eine Personen-ID für diese bestimmte persistente ID haben.

Wenn die Personen-ID-Informationen für ein Ereignis nicht abgerufen werden können, wird stattdessen die persistente ID für dieses (nicht *)* verwendet. Daher enthält in einer [Datenansicht](/help/data-views/data-views.md) die mit einer [Verbindung“ verknüpft ist, &#x200B;](/help/connections/overview.md) den Datensatz enthält, der für das Zusammenfügen aktiviert ist, die Personen-ID-Komponente entweder den Personen-ID-Wert oder den beständigen ID-Wert auf der Ereignisebene.

Sie können das feldbasierte Stitching verwenden, wenn Sie Customer Journey Analytics als eigenständige Lösung verwenden (ohne Zugriff auf den Experience Platform Identity Service und das zugehörige Identitätsdiagramm). Oder wenn Sie das verfügbare Identitätsdiagramm nicht verwenden möchten.

![Feldbasierte Zuordnung](/help/stitching/assets/fbs.png)


## IdentityMap

Die feldbasierte Zuordnung unterstützt die Verwendung der [`identityMap`-Feldergruppe](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/schema/composition#identity) in folgenden Szenarien:

- Verwendung der primären Identität in `identityMap`-Namespaces zur Definition der persistenten ID:
   - Wenn mehrere primäre Identitäten in verschiedenen Namespaces gefunden werden, werden die Identitäten in den Namespaces lexikografisch sortiert, und die erste Identität wird ausgewählt.
   - Wenn mehrere primäre Identitäten in einem einzigen Namespace gefunden werden, wird die lexikografisch erste primäre Identität ausgewählt, die verfügbar ist.

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


- Verwendung des `identityMap`-Namespace zum Definieren der persistenten ID, der Personen-ID oder beider:
   - Wenn in einem `identityMap`-Namespace mehrere Werte für eine persistente ID oder Personen-ID gefunden werden, wird der lexikografisch erste verfügbare Wert verwendet.
   - Namespaces für persistente ID und Personen-ID müssen sich gegenseitig ausschließen.

  Im folgenden Beispiel haben Sie „ECID“ als zu verwendenden Namespace ausgewählt. Diese Auswahl führt zu einer sortierten Identitätsliste und schließlich zur ausgewählten Identität.

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

## Funktionsweise der Zuordnung

Beim Zuordnen werden in einem Datensatz mindestens zwei Datendurchläufe durchgeführt.

- **Live-Zuordnung:**: Versucht, bei Eingang jeden Treffer (Ereignis) zuzuordnen. Treffer von Geräten, die *neu* im Datensatz sind (sich noch nie authentifiziert haben), werden in der Regel nicht auf dieser Ebene zugeordnet. Treffer von bereits erkannten Geräten werden sofort zugeordnet.

- **Wiederholte Zuordnung:** *Wiederholt* Daten basierend auf eindeutigen Kennungen (Personen-IDs). In diesem Schritt werden Treffer von zuvor unbekannten Geräten (persistente IDs) zugeordnet (zu Personen-IDs). Zwei Parameter bestimmen die Wiederholung: **Häufigkeit** und **Lookback-Fenster**. Adobe bietet die folgenden Kombinationen dieser Parameter:
   - **Täglicher Lookback mit täglicher Häufigkeit:** Daten werden täglich mit einem 24-Stunden-Lookback-Fenster wiederholt. Diese Option bietet den Vorteil, dass Wiederholungen viel häufiger vorkommen. Nicht authentifizierte Personen müssen sich jedoch am selben Tag authentifizieren, an dem sie Ihre Website besuchen.
   - **Wöchentlicher Lookback in wöchentlicher Häufigkeit:** Die Daten werden einmal wöchentlich mit einem wöchentlichen Lookback-Fenster wiederholt (siehe [Optionen](overview.md#options)). Diese Option bietet den Vorteil, dass nicht authentifizierte Sitzungen über einen weniger eng gefassten Zeitraum für die Authentifizierung verfügen. Nicht zugeordnete Daten, die weniger als eine Woche alt sind, werden jedoch erst bei der nächsten wöchentlichen Wiederholung erneut verarbeitet.
   - **Vierzehntägiger Lookback mit wöchentlicher Häufigkeit:** Die Daten werden einmal wöchentlich mit einem zweiwöchentlichen Lookback-Fenster wiederholt (siehe [Optionen](overview.md#)). Diese Option bietet den Vorteil, dass nicht authentifizierte Sitzungen über einen weniger eng gefassten Zeitraum für die Authentifizierung verfügen. Nicht zugeordnete Daten, die weniger als zwei Wochen alt sind, werden jedoch erst bei der nächsten wöchentlichen Wiederholung erneut verarbeitet.
   - **Monatlicher Lookback mit wöchentlicher Häufigkeit:** Daten werden wöchentlich mit einem monatlichen Lookback-Fenster wiederholt (siehe [Optionen](overview.md#options)). Diese Option bietet den Vorteil, dass nicht authentifizierte Sitzungen über einen weniger eng gefassten Zeitraum für die Authentifizierung verfügen. Nicht zugeordnete Daten, die weniger als einen Monat alt sind, werden jedoch erst bei der nächsten wöchentlichen Wiederholung erneut verarbeitet.

- **Datenschutz**: Wenn datenschutzbezogene Anfragen empfangen werden, muss neben dem Entfernen der angeforderten Identität auch jede Zuordnung dieser Identität zu nicht authentifizierten Ereignissen rückgängig gemacht werden.

  >[!IMPORTANT]
  >
  >Das Verfahren zur Aufhebung der Zuordnung im Rahmen von Datenschutzanfragen ändert sich Anfang 2025. Das aktuelle Verfahren ordnet Ereignisse anhand der neuesten Version bekannter Identitäten neu zu. Diese Neuzuweisung von Ereignissen an eine andere Identität kann unerwünschte rechtliche Folgen haben. Um diesen Bedenken zu begegnen, werden Ereignisse, die Gegenstand der Datenschutzanfrage sind, ab 2025 durch das neue Verfahren zur Aufhebung der Zuordnung mit der persistenten ID aktualisiert.
  > 


Daten, die über das Lookback-Fenster hinausgehen, werden nicht wiederholt. Ein Profil muss innerhalb eines gegebenen Lookback-Fensters authentifiziert werden, damit ein nicht authentifizierter Besuch und ein authentifizierter Besuch gemeinsam identifiziert werden können. Sobald ein Gerät erkannt wurde, wird dieses Gerät von diesem Punkt an live zugeordnet.

### Schritt 1: Live-Zuordnung

Die Live-Zuordnung versucht bei der Erfassung, jedes Ereignis bekannten Geräten und Kanälen zuzuordnen.

+++ Details

Betrachten Sie das folgende Beispiel, bei dem Bob verschiedene Ereignisse als Teil eines Ereignisdatensatzes aufzeichnet.

*Daten, wie sie am Tag der Erfassung auftraten:*

| Ereignis | Zeitstempel | Persistente ID (Cookie-ID) | Personen-ID | Resultierende ID (nach der Echtzeit-Zuordnung) |
|---|---|---|---|---|
| 1 | 12.05.2023 12:01 | `246` ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | - | **`246`** |
| 2 | 12.05.2023 12:02 | `246` | `Bob` ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 3 | 12.05.2023 12:03 | `246` | `Bob` ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | `Bob` ![Pfeil nach unten](/help/assets/icons/ArrowDown.svg) |
| 4 | 12.05.2023 12:04 | `246` | - | **`Bob`** |
| 5 | 12.05.2023 12:05 | `246` | `Bob` ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | `Bob` ![Pfeil nach unten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 12.05.2023 12:06 | `246` | - | **`Bob`** |
| 7 | 12.05.2023 12:07 | `246` | `Bob` ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 8 | 12.05.2023 12:03 | `3579` ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 9 | 12.05.2023 12:09 | `3579` ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 10 | 12.05.2023 12:02 | `81911` ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | - | **`81911`** |
| 11 | 12.05.2023 12:05 | `81911` | `Bob` ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | `Bob` ![Pfeil nach unten](/help/assets/icons/ArrowDown.svg) |
| 12 | 12.05.2023 12:12 | `81911` | - | **`Bob`** |
| | | **3 Geräte** | | **4 Personen:**<br/>`246`, `Bob`, `3579`, `81911` |

Sowohl nicht authentifizierte als auch authentifizierte Ereignisse auf neuen Geräten werden (vorübergehend) als separate Personen gezählt. Nicht authentifizierte Ereignisse auf erkannten Geräten werden live zugeordnet.

Die Attribution funktioniert, wenn die Identifizierung der benutzerdefinierten Variablen an ein Gerät gebunden ist. Im obigen Beispiel werden alle Ereignisse mit Ausnahme der Ereignisse 1, 8, 9 und 10 live zugeordnet (sie verwenden alle die Kennung `Bob`). Die Live-Zuordnung „löst“ die resultierende ID für Ereignis 4, 6 und 12 auf.

Verzögerte Daten (Daten mit einem Zeitstempel älter als 24 Stunden) werden „nach bestem Bemühen“ verarbeitet, wobei die Zuordnung aktueller Daten für die höchste Qualität priorisiert wird.

+++ 

### Schritt 2: Wiederholte Zuordnung

In regelmäßigen Abständen (einmal pro Woche oder einmal pro Tag, je nach ausgewähltem Lookback-Fenster) berechnet die wiederholte Zuordnung historische Daten erneut basierend auf Geräten, die es jetzt erkennt. Wenn ein nicht authentifiziertes Gerät anfänglich Daten sendet und sich dann anmeldet, verknüpft die wiederholte Zuordnung diese nicht authentifizierten Ereignisse mit der richtigen Person.

+++ Details

Die folgende Tabelle stellt dieselben Daten wie oben dar, zeigt jedoch unterschiedliche Zahlen basierend auf der Wiederholung der Daten.

*Dieselben Daten nach der Wiederholung:*

| Ereignis | Zeitstempel | Persistente ID (Cookie-ID) | Personen-ID | Resultierende ID (nach der Echtzeit-Zuordnung) | Resultierende ID (nach der Wiederholung) |
|---|---|---|---|---|---|
| 1 | 12.05.2023 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 12.05.2023 12:02 | `246` | `Bob` ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![Pfeil nach oben](/help/assets/icons/ArrowUp.svg) |
| 3 | 12.05.2023 12:03 | `246` | `Bob` ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | `Bob` | Bob |
| 4 | 12.05.2023 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 12.05.2023 12:05 | `246` | `Bob` ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | `Bob` ![Pfeil nach unten](/help/assets/icons/ArrowDown.svg) | `Bob` |
| 6 | 12.05.2023 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 12.05.2023 12:07 | `246` | `Bob` ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` |
| 8 | 12.05.2023 12:03 | `3579` ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 9 | 12.05.2023 12:09 | `3579` ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 10 | 12.05.2023 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 12.05.2023 12:05 | `81911` | `Bob` ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | `Bob` ![Pfeil nach unten](/help/assets/icons/ArrowDown.svg) | `Bob` ![Pfeil nach oben](/help/assets/icons/ArrowUp.svg) |
| 12 | 12.05.2023 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3 Geräte** | | **4 Personen:**<br/>`246`, `Bob`, `3579`, `81911` | **2 Personen:**:<br/>`Bob`, `3579` |

{style="table-layout:auto"}

Die Attribution funktioniert, wenn die Identifizierung der benutzerdefinierten Variablen an ein Gerät gebunden ist. Im obigen Beispiel werden Ereignis 1 und 10 als Ergebnis der Wiederholung zugeordnet, sodass nur Ereignis 8 und 9 nicht zugeordnet sind und die Metrik für Personen (kumulativ) auf 2 reduziert wird.

+++ 

### Schritt 3: Datenschutzanfrage

Wenn Sie eine Datenschutzanfrage erhalten, werden alle Kennungsinformationen, die vom Zuordnungsprozess zum Wert der Personen-ID festgelegt wurden, in allen Datensätzen zu einem persistenten ID-Wert für den Benutzer bzw. die Benutzerin, der bzw. die Gegenstand der Datenschutzanfrage ist, aktualisiert.

+++ Details

Die folgende Tabelle stellt dieselben Daten wie oben dar, zeigt jedoch die Auswirkungen, die eine Datenschutzanfrage für Bob nach der Verarbeitung auf die Daten hat. Die Zeilen, in denen Bob authentifiziert ist, werden entfernt (2, 3, 5, 7 und 11), außerdem wird Bob als Personen-ID für andere Zeilen entfernt.

*Dieselben Daten nach einer Datenschutzanfrage für Bob:*

| Ereignis | Zeitstempel | Persistente ID (Cookie-ID) | Personen-ID | Resultierende ID (nach der Echtzeit-Zuordnung) | Resultierende ID (nach der Wiederholung) | Personen-ID | Ergebnis-ID (nach Datenschutzanfrage) |
|---|---|---|---|---|---|---|---|
| 1 | 12.05.2023 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 12.05.2023 12:02 | `246` | Bob ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![Pfeil nach oben](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | ![Löschsymbol](/help/assets/icons/RemoveCircle.svg) | `246` |
| 3 | 12.05.2023 12:03 | `246` | Bob ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | `Bob` ![Pfeil nach unten](/help/assets/icons/ArrowDown.svg) | `Bob` | ![Löschsymbol](/help/assets/icons/RemoveCircle.svg) | `246` |
| 4 | 12.05.2023 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 12.05.2023 12:05 | `246` | Bob ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | `Bob` ![Pfeil nach unten](/help/assets/icons/ArrowDown.svg) | `Bob` | ![Löschsymbol](/help/assets/icons/RemoveCircle.svg) | `246` |
| 6 | 12.05.2023 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 12.05.2023 12:07 | `246` | `Bob` ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` | ![Löschsymbol](/help/assets/icons/RemoveCircle.svg) | `246` |
| 8 | 12.05.2023 12:03 | `3579` ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 12.05.2023 12:09 | `3579` ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 12.05.2023 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 12.05.2023 12:05 | `81911` | `Bob` ![Pfeil nach rechts](/help/assets/icons/ArrowRight.svg) | `Bob` ![Pfeil nach unten](/help/assets/icons/ArrowDown.svg) | `Bob` ![Pfeil nach oben](/help/assets/icons/ArrowUp.svg) | ![Löschsymbol](/help/assets/icons/RemoveCircle.svg) | `81911` |
| 12 | 12.05.2023 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3 Geräte** | | **4 Personen:**<br/>246, `Bob`, `3579`, `81911` | **2 Personen:**<br/>Bob, `3579` |  | **3 Personen:**<br/>`246`, `3579`, `81911` |

+++ 

## Voraussetzungen

Die folgenden Voraussetzungen gelten speziell für feldbasierte Zuordnung:

- Der Ereignisdatensatz in Adobe Experience Platform, auf den Sie eine Zuordnung anwenden möchten, muss zwei Spalten aufweisen, die die Identifizierung von Profilen erleichtern:

   - Eine **persistente ID**, eine Kennung, die in jeder Zeile vorhanden ist. Beispielsweise eine Besucher-ID, die von einer Adobe Analytics AppMeasurement-Bibliothek generiert wurde, oder eine vom Adobe Experience Platform Identity Service generierte ECID.
   - Eine **Personen-ID**, eine Kennung, die nur in einigen Zeilen vorhanden ist. Beispielsweise ein gehashter Benutzername oder eine gehashte E-Mail-Adresse, wenn sich ein Profil authentifiziert. Sie können praktisch jede gewünschte Kennung verwenden. Beim Zuordnen wird davon ausgegangen, dass dieses Feld die tatsächlichen Informationen der Personen-ID enthält. Um die besten Ergebnisse beim Zuordnen zu erzielen, sollte eine Personen-ID mindestens einmal für jede persistente ID innerhalb der Ereignisse des Datensatzes gesendet werden. Wenn Sie diesen Datensatz in eine Customer Journey Analytics-Verbindung einbeziehen möchten, sollten die anderen Datensätze auch eine ähnliche gemeinsame Kennung haben.

<!--
- Both columns (persistent ID and person ID) must be defined as an identity field with an identity namespace in the schema for the dataset you want to stitch. When using identity stitching in Real-time Customer Data Platform, using the [`identityMap` field group](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity), you still need to add identity fields with an identity namespace. This identification of identity fields is required as Customer Journey Analytics stitching does not support the `identityMap` field group. When adding an identity field in the schema, while also using the `identityMap` field group, do not set the additional identity field as a primary identity. Setting an additional identity field as primary identity interferes with the `identityMap` field group used for Real-time Customer Data Platform.

-->

## Einschränkungen

Die folgenden Einschränkungen gelten speziell für die feldbasierte Zuordnung:

- Die aktuellen Funktionen zur Neuzuweisung sind auf einen Schritt beschränkt (persistente ID zu Personen-ID). Eine mehrstufige Neuzuweisung wird nicht unterstützt, beispielsweise persistente ID zu Personen-ID und dann zu einer anderen Personen-ID.
- Wenn mehrere Personen ein Gerät gemeinsam nutzen und die Gesamtzahl der Transitionen zwischen den Benutzern 50.000 überschreitet, stoppt Customer Journey Analytics das Zusammenfügen von Daten für dieses Gerät.
- Benutzerdefinierte ID-Maps, die in Ihrem Unternehmen verwendet werden, werden nicht unterstützt.
- Bei der Zuordnung ist die Groß-/Kleinschreibung zu beachten. Für Datensätze, die über den Analytics-Quell-Connector generiert werden, empfiehlt Adobe die Prüfung aller VISTA-Regeln oder Verarbeitungsregeln, die für das Personen-ID-Feld gelten. Mit dieser Prüfung wird sichergestellt, dass keine dieser Regeln neue Formen derselben ID einführt. So sollten Sie beispielsweise sicherstellen, dass keine VISTA- oder Verarbeitungsregeln dafür sorgen, dass im Feld für die Personen-ID nur für einen Teil der Ereignisse Kleinschreibung verwendet wird.
- Bei der Zuordnung werden Felder nicht kombiniert oder verkettet.
- Das Feld für die Personen-ID sollte nur einen ID-Typ enthalten (IDs aus einem einzigen Namespace). Das Feld für die Personen-ID sollte beispielsweise keine Kombination aus Anmelde-IDs und E-Mail-IDs enthalten.
- Wenn mehrere Ereignisse mit demselben Zeitstempel für dieselbe persistente ID auftreten, jedoch unterschiedliche Werte im Feld für die Personen-ID vorliegen, wird bei der Zuordnung die ID nach alphabetischer Reihenfolge ausgewählt. Wenn also eine persistente ID A zwei Ereignisse mit demselben Zeitstempel hat und eines der Ereignisse „Bob“ und das andere „Ann“ angibt, wählt die Zuordnung „Ann“ aus.
- Seien Sie vorsichtig bei Szenarien, in denen die Personen-IDs Platzhalterwerte enthalten, z. B. `Undefined`. Weitere Informationen finden Sie unter [Häufig gestellte Fragen](faq.md).
- Sie können nicht denselben Namespace sowohl für die persistente ID als auch für die Personen-ID verwenden. Die Namespaces müssen sich gegenseitig ausschließen.
