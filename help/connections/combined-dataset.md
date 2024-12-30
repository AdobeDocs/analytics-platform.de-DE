---
title: Kombinierte Ereignis-Datensätze
description: Erfahren Sie, wie Customer Journey Analytics durch Kombinieren von Datensätzen eine Verbindung erstellt.
exl-id: 9f678225-a9f3-4134-be38-924b8de8d57f
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: aaf23560b69c90fdbaee3fa401b5fe58e6a4e5d1
workflow-type: tm+mt
source-wordcount: '919'
ht-degree: 34%

---


# Kombinierte Ereignis-Datensätze

Wenn Sie eine Verbindung erstellen, kombiniert Customer Journey Analytics alle Ereignis-Datensätze zu einem einzigen Datensatz. Dieser kombinierte Ereignis-Datensatz wird von Customer Journey Analytics für das Reporting verwendet (zusammen mit Profil- und Lookup-Datensätzen). Wenn Sie mehrere Ereignis-Datensätze in eine Verbindung einbeziehen:

* Die Daten für Felder in Datensätzen, die auf **Schemapfad basieren** werden im kombinierten Datensatz zu einer einzigen Spalte zusammengeführt.
* Die für jeden Datensatz angegebene Spalte mit der Personen-ID wird im kombinierten Datensatz (unabhängig vom **) zu einer einzigen Spalte**. Diese Spalte dient als Grundlage für die Identifizierung von eindeutigen Personen beim Customer Journey Analytics.
* Zeilen werden anhand des Zeitstempels verarbeitet.
* Ereignisse werden auf die Millisekunden-Ebene aufgelöst.

## Beispiel

Siehe folgendes Beispiel. Sie haben zwei Ereignis-Datensätze mit jeweils unterschiedlichen Feldern, die unterschiedliche Daten enthalten.

>[!NOTE]
>
>Adobe Experience Platform speichert in der Regel einen Zeitstempel in UNIX® Millisekunden. Zur besseren Lesbarkeit werden in diesem Beispiel Datum und Uhrzeit verwendet.

| example_id | timestamp | string_color | string_Animal | metric_a |
| --- | --- | --- | --- | ---: |
| user_310 | 1. Januar 7:02 | Rot | Fuchs | |
| user_310 | 1. Januar 7:04 | | | 2 |
| user_310 | 1. Januar 7:08 | Blau | | 3 |
| user_847 | 2. Januar 12:31 | | Schildkröte | 4 |
| user_847 | 2. Januar 12:44 | | | 2 |

| different_id | timestamp | string_color | string_Shape | metric_b |
| --- | --- | --- | --- | ---: |
| user_847 | 2. Januar 12:26 | Gelb | Kreis | 8,5 |
| user_847 | 2. Januar 13:01 | Rot | | |
| alternateid_656 | 2. Januar 20:58 | Rot | Square | 4.2 |
| alternateid_656 | 2. Januar 21:03 | | Dreieck | 3,1 |

Wenn Sie eine Verbindung mit diesen beiden Ereignis-Datensätzen erstellen und

* als Personen-ID für den ersten Datensatz `example_id` und
* als Personen-ID für den zweiten Datensatz `different_id`,

Der folgende kombinierte Datensatz wird für das Reporting verwendet.

| ID | timestamp | string_color | string_Animal | string_Shape | metric_a | metric_b |
| --- | --- | --- | --- | --- | ---: | ---: |
| user_310 | 1. Januar 7:02 | Rot | Fuchs | | | |
| user_310 | 1. Januar 7:04 | | | | 2 | |
| user_310 | 1. Januar 7:08 | Blau | | | 3 | |
| user_847 | 2. Januar 12:26 | Gelb | | Kreis | | 8,5 |
| user_847 | 2. Januar 12:31 | | Schildkröte | | 4 | |
| user_847 | 2. Januar 12:44 | | | | 2 | |
| user_847 | 2. Januar 13:01 | Rot | | | | |
| alternateid_656 | 2. Januar 20:58 | Rot | | Square | | 4.2 |
| alternateid_656 | 2. Januar 21:03 | | | Dreieck | | 3,1 |

Betrachten Sie dieses Szenario, um die Bedeutung von Schemapfaden zu veranschaulichen. Im ersten Datensatz basiert `string_color` auf dem Schemapfad `_experience.whatever.string_color` und im zweiten Datensatz auf dem Schemapfad `_experience.somethingelse.string_color`. In diesem Szenario werden die Daten **nicht** im resultierenden kombinierten Datensatz in einer Spalte zusammengeführt. Stattdessen sind das Ergebnis zwei `string_color` Spalten im kombinierten Datensatz:

| id | timestamp | _experience.<br/>Was auch immer.<br/>string_color | _experience.<br/>etwas Anderes.<br/>string_color | string_Animal | string_Shape | metric_a | metric_b |
|---|---|---|---|---|---|---:|---:|
| user_310 | 1. Januar 7:02 | Rot | | Fuchs | | | |
| user_310 | 1. Januar 7:04 | | | | | 2 | |
| user_310 | 1. Januar 7:08 | Blau | | | | 3 | |
| user_847 | 2. Januar 12:26 | | Gelb | | Kreis | | 8,5 |
| user_847 | 2. Januar 12:31 | | | Schildkröte |  | 4 | |
| user_847 | 2. Januar 12:44 | | | | | 2 | |
| user_847 | 2. Januar 13:01 | | Rot | | | | |
| alternateid_656 | 2. Januar 20:58 | | Rot | | Square | | 4.2 |
| alternateid_656 | 2. Januar 21:03 | | | | Dreieck | | 3,1 |

Dieser „kombinierte Ereignis-Datensatz“ wird für das Reporting verwendet. Es spielt keine Rolle, aus welchem Datensatz eine Zeile stammt. Customer Journey Analytics behandelt alle Daten so, als befände sie sich im selben Datensatz. Wenn in beiden Datensätzen eine übereinstimmende Personen-ID angezeigt wird, werden diese als dieselbe eindeutige Person betrachtet. Wenn in beiden Datensätzen eine übereinstimmende Personen-ID mit einem Zeitstempel innerhalb von 30 Minuten angezeigt wird, werden sie als Teil derselben Sitzung betrachtet. Felder mit identischen Schemapfaden werden zusammengeführt.

Dieses Konzept gilt auch für die Attribution. Es spielt keine Rolle, aus welchem Datensatz eine Zeile stammt. Die Attribution funktioniert genau so, als ob alle Ereignisse aus einem einzigen Datensatz stammen. Anhand dem Beispiel der oben stehenden Tabellen:

Wenn Ihre Verbindung nur die erste Tabelle und nicht die zweite Tabelle enthält, wird beim Abrufen eines Berichts unter Verwendung der `string_color`-Dimension und der `metric_a`-Metrik und der Attribution „Letztkontakt“ Folgendes angezeigt:

| string_color | metric_a |
| --- | ---: |
| Nicht angegeben | 6 |
| Blau | 3 |
| Rot | 2 |

Wenn Sie jedoch beide Tabellen in Ihrer Verbindung eingeschlossen haben, ändert sich die Attribution, da `user_847` in beiden Datensätzen enthalten ist. Eine Zeile aus den zweiten Datensatz weist `metric_a` „Gelb“ zu. Diese Zuordnung wurde im vorherigen Fall nicht angegeben:

| string_color | metric_a |
| --- | ---: |
| Gelb | 6 |
| Blau | 3 |
| Rot | 2 |

>[!NOTE]
>
>Wenn ein zusammengeführtes Feld ein Lookup-Schlüssel für einen Ereignis-Datensatz in der Verbindung ist, erweitert der zugehörige Lookup-Datensatz **alle** Werte dieses Felds. Es spielt keine Rolle, aus welchem Ereignis-Datensatz eine Zeile stammt, da die Lookup-Beziehung mit dem freigegebenen Schemapfad verknüpft ist.

## Kanalübergreifende Analyse

Die nächste Ebene zum Kombinieren von Datensätzen ist die kanalübergreifende Analyse, bei der Datensätze aus verschiedenen Kanälen basierend auf einer gemeinsamen Kennung (Personen-ID) kombiniert werden. Die kanalübergreifende Analyse kann von der Zuordnungsfunktion profitieren, mit der Sie die Personen-ID eines Datensatzes neu zuweisen können, sodass der Datensatz ordnungsgemäß aktualisiert wird, um eine nahtlose Kombination mehrerer Datensätze zu ermöglichen. Beim Zusammenfügen werden Benutzerdaten aus authentifizierten und nicht authentifizierten Sitzungen betrachtet, um eine zusammengefügte ID zu generieren.

Die kanalübergreifende Analyse ermöglicht Ihnen die Beantwortung von Fragen wie:

* Wie viele Personen beginnen ihr Erlebnis auf einem Kanal und beenden es auf einem anderen?
* Wie viele Menschen interagieren mit meiner Marke? Wie viele und welche Gerätetypen verwenden sie? Wie überschneiden sich diese?
* Wie oft beginnen Personen mit einer Aufgabe auf einem Mobilgerät und wechseln dann zu einem Desktop-PC, um die Aufgabe abzuschließen? Führen Kampagnen-Clickthroughs, die auf einem Gerät landen, zu einer Konversion an einem anderen Ort?
* Wie ändert sich mein Verständnis der Kampagneneffektivität, wenn ich geräteübergreifende Journey berücksichtige? Wie ändert sich meine Trichteranalyse?
* Welche sind die häufigsten Pfade, die Benutzer beim Wechsel von einem Gerät zum anderen verwenden? Wo steigen sie aus? Wo schließen sie ihre Aktion erfolgreich ab?
* Wie unterscheidet sich das Verhalten von Benutzern mit mehreren Geräten von Benutzern mit nur einem Gerät?


Weitere Informationen zur kanalübergreifenden Analyse finden Sie im entsprechenden Anwendungsfall:

* [Kanalübergreifende Analyse](../use-cases/cross-channel/cross-channel.md)

Eine ausführlichere Erläuterung der Zuordnungsfunktionen finden Sie unter:

* [Übersicht über das Zusammenfügen](/help/stitching/overview.md)
* [Häufig gestellte Fragen](/help/stitching/faq.md)

