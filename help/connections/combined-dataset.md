---
title: Kombinierte Ereignis-Datensätze
description: Erfahren Sie, wie Customer Journey Analytics durch die Kombination von Datensätzen eine Verbindung herstellt.
exl-id: 9f678225-a9f3-4134-be38-924b8de8d57f
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 60%

---


# Kombinierte Ereignis-Datensätze

Wenn Sie eine Verbindung erstellen, kombiniert Customer Journey Analytics alle Schemas und Datensätze zu einem Datensatz. Dieser &quot;kombinierte Ereignis-Datensatz&quot;wird von Customer Journey Analytics für die Berichterstellung verwendet. Wenn Sie mehrere Schemata oder Datensätze in eine Verbindung einschließen:

* Schemata werden kombiniert. Doppelte Schemafelder werden zusammengeführt.
* Die Spalte „Personen-ID“ jedes Datensatzes wird unabhängig von ihrem Namen in eine Spalte zusammengefasst. Diese Spalte bildet die Grundlage für die Identifizierung von Einzelpersonen in der Customer Journey Analytics.
* Zeilen werden anhand des Zeitstempels verarbeitet.
* Ereignisse werden auf die Millisekunden-Ebene aufgelöst.

## Beispiel

Siehe folgendes Beispiel. Sie haben zwei Ereignis-Datensätze mit jeweils unterschiedlichen Feldern, die unterschiedliche Daten enthalten.

>[!NOTE]
>
>Adobe Experience Platform speichert Zeitstempel normalerweise in Unix-Millisekunden. Zur besseren Lesbarkeit werden in diesem Beispiel Datum und Uhrzeit verwendet.

| `example_id` | `timestamp` | `string_color` | `string_animal` | `metric_a` |
| --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` | |
| `user_310` | `1 Jan 7:04 AM` | | | `2` |
| `user_310` | `1 Jan 7:08 AM` | `Blue` | | `3` |
| `user_847` | `2 Jan 12:31 PM` | | `Turtle` | `4` |
| `user_847` | `2 Jan 12:44 PM` | | | `2` |

| `different_id` | `timestamp` | `string_color` | `string_shape` | `metric_b` |
| --- | --- | --- | --- | --- |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | `Circle` | `8.5` |
| `user_847` | `2 Jan 1:01 PM` | `Red` | | |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | `Square` | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` | | `Triangle` | `3.1` |

Wenn Sie eine Verbindung mit diesen beiden Ereignis-Datensätzen erstellen, wird die folgende Tabelle für das Reporting verwendet.

| `id` | `timestamp` | `string_color` | `string_animal` | `string_shape` | `metric_a` | `metric_b` |
| --- | --- | --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` | | | |
| `user_310` | `1 Jan 7:04 AM` | | | | `2` | |
| `user_310` | `1 Jan 7:08 AM` | `Blue` | | | `3` | |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | | `Circle` | | `8.5` |
| `user_847` | `2 Jan 12:31 PM` | | `Turtle` | | `4` | |
| `user_847` | `2 Jan 12:44 PM` | | | | `2` | |
| `user_847` | `2 Jan 1:01 PM` | `Red` | | | | |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | | `Square` | | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` | | | `Triangle` | | `3.1` |

Dieser „kombinierte Ereignis-Datensatz“ wird für das Reporting verwendet. Es spielt keine Rolle, aus welchem Datensatz eine Zeile stammt. Customer Journey Analytics behandelt alle Daten so, als ob sie sich im selben Datensatz befinden. Wenn in beiden Datensätzen eine übereinstimmende Personen-ID angezeigt wird, werden sie als dieselbe eindeutige Person betrachtet. Wenn eine übereinstimmende Personen-ID mit einem Zeitstempel innerhalb von 30 Minuten in beiden Datasets erscheint, werden sie als Teil derselben Sitzung betrachtet.

Dieses Konzept gilt auch für die Attribution. Es spielt keine Rolle, aus welchem Datensatz eine Zeile stammt. Die Attribution funktioniert genau so, als ob alle Ereignisse aus einem einzigen Datensatz stammen. Anhand dem Beispiel der oben stehenden Tabellen:

Wenn Ihre Verbindung nur die erste Tabelle und nicht die zweite Tabelle enthält, wird beim Abrufen eines Berichts unter Verwendung der `string_color`-Dimension und der `metric_a`-Metrik und der Attribution „Letztkontakt“ Folgendes angezeigt:

| string_color | metric_a |
| --- | --- |
| Nicht angegeben | 6 |
| Blau | 3 |
| Rot | 2 |

Wenn Sie jedoch beide Tabellen in Ihrer Verbindung eingeschlossen haben, ändert sich die Attribution, da `user_847` in beiden Datensätzen enthalten ist. Eine Zeile aus den zweiten Datensatz weist `metric_a` „Gelb“ zu. Diese Zuordnung wurde im vorherigen Fall nicht angegeben:

| string_color | metric_a |
| --- | --- |
| Gelb | 6 |
| Blau | 3 |
| Rot | 2 |

## Kanalübergreifende Analyse

Die nächste Ebene der Kombination von Datensätzen ist die kanalübergreifende Analyse, bei der Datensätze aus verschiedenen Kanälen anhand einer gemeinsamen Kennung (Personen-ID) kombiniert werden. Die kanalübergreifende Analyse kann von der Funktion zum Zuordnen profitieren. So können Sie die Personen-ID eines Datensatzes neu zuweisen, damit der Datensatz ordnungsgemäß aktualisiert wird, um eine nahtlose Kombination mehrerer Datensätze zu ermöglichen. Beim Zuordnen werden Benutzerdaten aus authentifizierten und nicht authentifizierten Sitzungen untersucht, um eine zugeordnete ID zu generieren.

Mithilfe der kanalübergreifenden Analyse können Sie Fragen beantworten, z. B.:

* Wie viele Personen beginnen ihr Erlebnis auf einem Kanal und beenden es auf einem anderen?
* Wie viele Menschen interagieren mit meiner Marke? Wie viele und welche Gerätetypen verwenden sie? Wie überschneiden sich diese?
* Wie oft beginnen Personen mit einer Aufgabe auf einem Mobilgerät und wechseln dann zu einem Desktop-PC, um die Aufgabe abzuschließen? Führen Kampagnen-Clickthroughs, die auf einem Gerät landen, irgendwo anders zur Konversion?
* Wie ändert sich mein Verständnis von Kampagneneffizienz, wenn ich geräteübergreifende Journey berücksichtige? Wie ändert sich meine Trichteranalyse?
* Welche sind die häufigsten Pfade, die Benutzer beim Wechsel von einem Gerät zum anderen verwenden? Wo steigen sie aus? Wo schließen sie ihre Aktion erfolgreich ab?
* Wie unterscheidet sich das Verhalten von Benutzern mit mehreren Geräten von Benutzern mit nur einem Gerät?


Weiterführende Informationen zur kanalübergreifenden Analyse finden Sie im entsprechenden Anwendungsbeispiel:

* [Kanalübergreifende Analyse](../use-cases/cross-channel/cross-channel.md)

Eine ausführlichere Funktion zum Stitching finden Sie unter:

* [Stitching-Übersicht](/help/stitching/overview.md)
* [Funktionsweise von Stitching](../stitching/explained.md)
* [Häufig gestellte Fragen](/help/stitching/faq.md)

