---
title: Verwenden abgeleiteter Felder in Daten-Feeds
description: Erfahren Sie, wie Sie abgeleitete Felder in Daten-Feeds verwenden.
hide: true
feature: Components
source-git-commit: a9f53472d57a3a26004bd5ca583a43134bbdba7e
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 2%

---

# Verwenden abgeleiteter Felder in Daten-Feeds

{{release-limited-testing}}

Mit (abgeleiteten Feldern) können Sie [ Daten-Feed-Daten ](/help/data-views/derived-fields/derived-fields.md).

Viele abgeleitete Feldfunktionen führen Umwandlungen durch, die Sie auch mithilfe von SQL anwenden können, z. B. das Ersetzen von Werten, das Kombinieren von Feldern oder das Konvertieren des Datentyps eines Felds, sodass die gewählte Methode manchmal bevorzugt wird.

## Abgeleitete Felder im Vergleich zu SQL

In der folgenden Tabelle werden die Vor- und Nachteile der Verwendung abgeleiteter Felder oder SQL verglichen.

| Methode | Vorteile | Nachteile |
| --- | --- | --- |
| **Abgeleitete Felder** | <ul><li>Dieselbe Logik gilt konsistent sowohl für Analysis Workspace als auch für Ihre Daten-Feed-Ausgabe, da abgeleitete Felder neben Standarddimensionen und Metriken als Komponenten in Ihr Daten-Feed-Schema aufgenommen werden.</li><li>Einige Umwandlungen, insbesondere solche, die von einer Bereichseinstellung abhängen oder eine URL analysieren, sind in SQL schwer zu replizieren.</li></ul> | Dies verursacht zusätzlichen Verarbeitungsaufwand, der sich auf die Leistung der Daten-Feed-Bereitstellung auswirken kann.<!--Under a future usage-based pricing model, this could also add cost.--> |
| **SQL** | <ul><li>Nicht beschränkt durch die Funktions- und Operatorbeschränkungen, die für abgeleitete Felder gelten.</li><li>Hat keine Auswirkungen auf die Leistung der Daten-Feed-Bereitstellung.</li></ul> | <ul><li>Logik gilt in Analysis Workspace nicht, daher müssen Sie sie dort separat duplizieren.</li><li>Einige Umwandlungen, insbesondere solche, die von einer Bereichseinstellung abhängen oder eine URL analysieren, sind schwer oder nicht praktikabel zu replizieren.</li></ul> |

{style="table-layout:auto"}

## Abgeleitete Feldfunktionen

In der folgenden Tabelle werden die einzelnen abgeleiteten Feldfunktionen beschrieben. Es wird zudem erläutert, ob sich diese am besten für ein abgeleitetes Feld oder für SQL eignen und welche Überlegungen vor der Verwendung zu beachten sind.

| Abgeleitete Feldfunktion | Schwierigkeiten bei der Replikation mit SQL | Best fit (Abgeleitetes Feld oder SQL) | Zu beachten |
| --- | --- | --- | --- |
| [**Wenn**](/help/data-views/derived-fields/derived-fields.md#casewhen)<br/> Bedingungen basierend auf Kriterien aus einem oder mehreren Feldern anwendet, legt den Ausgabewert fest, basierend auf der Übereinstimmung der Bedingung. | Einfach zu moderieren | Entweder | In SQL reproduzierbar, aber durch die Verwendung eines abgeleiteten Felds wird dieselbe Logik konsistent sowohl in Analysis Workspace als auch in der Daten-Feed-Ausgabe angewendet. Dies ist besonders nützlich, wenn eine große Anzahl von Regeln involviert ist, z. B. eine Marketing-Kanal-Klassifizierung. |
| [**Classify**](/help/data-views/derived-fields/derived-fields.md#classify)<br/> Definiert einen Satz von Werten, die in einem neuen abgeleiteten Feld durch entsprechende Werte ersetzt werden. | Einfach zu moderieren | Entweder | In SQL reproduzierbar, aber durch die Verwendung eines abgeleiteten Felds wird dieselbe Logik konsistent sowohl in Analysis Workspace als auch in der Daten-Feed-Ausgabe angewendet. |
| [**Verketten**](/help/data-views/derived-fields/derived-fields.md#concatenate)<br/> Kombiniert Feldwerte mithilfe definierter Trennzeichen (z. B. Seitenname und Marketing-Kanal) zu einem einzigen neuen abgeleiteten Feld. | Einfach zu moderieren | Entweder | Spiegelt die Funktionalität zum Hinzufügen mehrerer Dimensionsspalten zu einer Freiformtabelle wider, die auf den vollständigen Tabellenexport beschränkt ist. Ein abgeleitetes Feld stellt eine ähnliche Ausgabe in einem Daten-Feed zur Verfügung. |
| [**Datumsmathematik**](/help/data-views/derived-fields/derived-fields.md#datemath)<br/> Gibt die Differenz zwischen zwei Datums- oder Datums-/Uhrzeitfeldern (z. B. Tage zwischen einem Buchungs- und einem Check-in-Datum) mit einem Ereignis-, Sitzungs- oder Personenbereich zurück. | diffizil | Abgeleitetes Feld | Komplex in SQL zu replizieren. Diese Funktion hängt von einer Bereichseinstellung ab. Weitere Informationen finden Sie unter [Wie sich Bereichseinstellungen in Funktionen auf Daten-Feeds auswirken](#scope-settings). |
| [**Deduplizieren**](/help/data-views/derived-fields/derived-fields.md#dedup)<br/> Verhindert, dass ein Wert mehrmals gezählt wird, mit einem Bereich von Person oder Sitzung (z. B. Deduplizieren einer Buchungsbestätigungs-ID). | diffizil | Abgeleitetes Feld | Diese Funktion hängt von einer Bereichseinstellung ab. Weitere Informationen finden Sie unter [Wie sich Bereichseinstellungen in Funktionen auf Daten-Feeds auswirken](#scope-settings). |
| [**Depth**](/help/data-views/derived-fields/derived-fields.md#depth)<br/> Gibt die Tiefe eines Felds zurück, ähnlich der standardmäßigen Dimension „Ereignistiefe“ (z. B. interne Suchtiefe). | diffizil | Abgeleitetes Feld | Verwendet Sitzung als Umfang und kann nicht konfiguriert werden. <!-- Open question as of 2026-09-09: does the Depth counter carry over across an hourly/daily feed boundary using lookback-window context, or does it restart? Pending confirmation from engineering (Ron Fulkerson / Nate Purser). --> Wie sich der Zähler verhält, wenn eine Sitzung eine Feed-Delivery-Grenze überschreitet, wird noch vom Engineering bestätigt. Diese Funktion hängt von einer Bereichseinstellung ab. Weitere Informationen finden Sie unter [Wie sich Bereichseinstellungen in Funktionen auf Daten-Feeds auswirken](#scope-settings). |
| [**Suchen und Ersetzen**](/help/data-views/derived-fields/derived-fields.md#find-and-replace)<br/> Sucht alle Werte in einem ausgewählten Feld und ersetzt sie durch einen anderen Wert. | Einfach zu moderieren | Entweder | In SQL reproduzierbar, aber durch die Verwendung eines abgeleiteten Felds wird dieselbe Logik konsistent sowohl in Analysis Workspace als auch in der Daten-Feed-Ausgabe angewendet. |
| [**Lookup**](/help/data-views/derived-fields/derived-fields.md#lookup)<br/> Sucht mithilfe eines übereinstimmenden Schlüssels einen Wert aus einem Lookup-Datensatz und gibt ihn in einem neuen, abgeleiteten Feld zurück. | Einfach zu moderieren | Entweder | SQL funktioniert, wenn bereits eine Lookup-Tabelle vorhanden ist. |
| [**Kleinbuchstaben**](/help/data-views/derived-fields/derived-fields.md#lowercase)<br/> Wandelt Werte von einem Feld in Kleinbuchstaben um. | Einfach zu moderieren | Entweder | In SQL reproduzierbar, aber durch die Verwendung eines abgeleiteten Felds wird dieselbe Logik konsistent sowohl in Analysis Workspace als auch in der Daten-Feed-Ausgabe angewendet. |
| [**Mathematisch**](/help/data-views/derived-fields/derived-fields.md#math)<br/> Wendet grundlegende mathematische Operatoren (Hinzufügen, Subtrahieren, Multiplizieren, Dividieren oder Erhöhen auf eine Potenz) auf numerische Felder an, die von Treffer zu Treffer ausgewertet werden. | Einfach zu moderieren | Entweder | In SQL reproduzierbar, aber durch die Verwendung eines abgeleiteten Felds wird dieselbe Logik konsistent sowohl in Analysis Workspace als auch in der Daten-Feed-Ausgabe angewendet. |
| [**Felder zusammenführen**](/help/data-views/derived-fields/derived-fields.md#merge)<br/>&#x200B;Überprüft, ob das erste von zwei oder mehr Feldern einen Wert enthält; verwendet andernfalls das nächste Feld usw. | Einfach zu moderieren | Entweder | Keine |
| [**Nächster oder vorheriger**](/help/data-views/derived-fields/derived-fields.md#next-previous)<br/> Löst den nächsten oder vorherigen Wert eines Felds der Tabelle „Besuch“ oder „Ereignis“ mit einem Bereich von Person oder Sitzung auf. | diffizil | Abgeleitetes Feld | Diese Funktion hängt von einer Bereichseinstellung ab. Weitere Informationen finden Sie unter [Wie sich Bereichseinstellungen in Funktionen auf Daten-Feeds auswirken](#scope-settings). |
| [**Regex Ersetzen**](/help/data-views/derived-fields/derived-fields.md#regex-replace)<br/> Ersetzt einen Wert aus einem Feld mithilfe eines regulären Ausdrucks. | Einfach zu moderieren | Entweder | In SQL reproduzierbar, aber durch die Verwendung eines abgeleiteten Felds wird dieselbe Logik konsistent sowohl in Analysis Workspace als auch in der Daten-Feed-Ausgabe angewendet. |
| [**Aufspaltung**](/help/data-views/derived-fields/derived-fields.md#split)<br/> Teilt einen Wert aus einem Feld in ein neues abgeleitetes Feld auf (z. B. Konvertieren einer durch Trennzeichen getrennten Liste in ein Array). | Einfach zu moderieren | Entweder | In SQL reproduzierbar, aber durch die Verwendung eines abgeleiteten Felds wird dieselbe Logik konsistent sowohl in Analysis Workspace als auch in der Daten-Feed-Ausgabe angewendet. |
| [**Zusammenfassen**](/help/data-views/derived-fields/derived-fields.md#summarize)<br/> Wendet Aggregationsfunktionen (z. B. Summe, Anzahl oder am häufigsten) auf ein Feld mit einem Ereignis-, Sitzungs- oder Personenbereich an. | diffizil | Abgeleitetes Feld | Diese Funktion hängt von einer Bereichseinstellung ab. Weitere Informationen finden Sie unter [Wie sich Bereichseinstellungen in Funktionen auf Daten-Feeds auswirken](#scope-settings). |
| [**Trim**](/help/data-views/derived-fields/derived-fields.md#trim)<br/> Trimmt Leerzeichen, Sonderzeichen oder eine bestimmte Anzahl von Zeichen vom Anfang oder Ende eines Felds. | Einfach zu moderieren | Entweder | In SQL reproduzierbar, aber durch die Verwendung eines abgeleiteten Felds wird dieselbe Logik konsistent sowohl in Analysis Workspace als auch in der Daten-Feed-Ausgabe angewendet. |
| [**Typecast**](/help/data-views/derived-fields/derived-fields.md#typecast)<br/>&#x200B;Ändert den Datentyp eines Felds, um es für zusätzliche Umwandlungen verfügbar zu machen. | Einfach zu moderieren | Entweder | In SQL reproduzierbar, aber durch die Verwendung eines abgeleiteten Felds wird dieselbe Logik konsistent sowohl in Analysis Workspace als auch in der Daten-Feed-Ausgabe angewendet. |
| [**URL Parse**](/help/data-views/derived-fields/derived-fields.md#urlparse)<br/> Analysiert Teile einer URL, einschließlich Protokoll, Host, Pfad, Abfragezeichenfolgenparameter oder Hash-Wert. | diffizil | Abgeleitetes Feld | SQL erfordert ein benutzerdefiniertes Zeichenfolgen-Parsing, um dieselben Komponenten zu extrahieren. |

{style="table-layout:auto"}

### Wie sich Bereichseinstellungen in Funktionen auf Daten-Feeds auswirken {#scope-settings}

[!UICONTROL **Date Math**], [!UICONTROL **Deduplicate**], [!UICONTROL **Next oder Previous**] und [!UICONTROL **Summarize**] hängen jeweils von einer [!UICONTROL **Scope**]-Einstellung von Event, Session oder Person ab (die verfügbaren Optionen variieren je nach Funktion). [!UICONTROL **Tiefe**] hat kein konfigurierbares Feld für den Umfang, ist jedoch an die Sitzung gebunden, ähnlich der standardmäßigen Dimension „Ereignistiefe“. Jedes Feld mit einem Bereich schreibt denselben Wert in jede Zeile innerhalb dieses Bereichs. Dieser Wert hängt von den Daten innerhalb des Lookback-Datumsbereichs ab.
<!-- Open question as of 2026-09-09: is the lookback date range boundary anchored to a fixed point (e.g., midnight), or does it float with the feed run time, and is this configurable? Pending confirmation from Ron Fulkerson. -->

Da der Lookback-Datumsbereich bei jedem Daten-Feed-Versand nach vorne verschoben wird, kann dasselbe Feld bei einem späteren Versand einen anderen Wert zurückgeben, auch für Ereignisse, die bereits aufgetreten sind.

Das Risiko steigt mit der Größe des Umfangs: Der Umfang einer Person ist mit mehr Risiko verbunden als der Sitzungsumfang, da die Historie einer Person innerhalb eines Feed-Durchgangs keine natürliche Zeitgrenze hat.

## Abgeleitete Feldfunktionsvorlagen

[Funktionsvorlagen für abgeleitete Felder](/help/data-views/derived-fields/derived-fields.md#templates) ermöglichen es Ihnen, schnell ein abgeleitetes Feld für einen bestimmten Anwendungsfall zu erstellen, z. B. zum Erstellen von Marketing-Kanälen, zum Erkennen von Bots oder zum Extrahieren eines UTM-Parameters aus einer URL. Da eine Vorlage aus einer Kette vordefinierter Regeln erstellt wird, ist es fast immer vorzuziehen, eine Vorlage zu verwenden, anstatt dieselbe Logik von Grund auf in SQL zu reproduzieren.

Wenn eine Vorlage eine Funktion enthält, die von einer Bereichseinstellung abhängig ist, erbt die Vorlage die Bereichsvorsicht dieser Funktion. Siehe [Wie sich Bereichseinstellungen in Funktionen auf Daten-Feeds auswirken](#scope-settings).

