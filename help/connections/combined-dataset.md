---
title: Kombinierte Ereignis-Datensätze
description: Erfahren Sie, wie Customer Journey Analytics durch die Kombination von Datensätzen eine Verbindung herstellt.
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

Wenn Sie eine Verbindung erstellen, kombiniert Customer Journey Analytics alle Ereignis-Datensätze zu einem Datensatz. Dieser kombinierte Ereignis-Datensatz wird von Customer Journey Analytics für die Berichterstellung verwendet (zusammen mit Profil- und Lookup-Datensätzen). Wenn Sie mehrere Ereignis-Datensätze in eine Verbindung einschließen:

* Die Daten für Felder in Datensätzen, die auf dem **gleichen Schemapfad** basieren, werden in einer einzigen Spalte im kombinierten Datensatz zusammengeführt.
* Die für jeden Datensatz angegebene Spalte &quot;Personen-ID&quot;wird unabhängig von ihrem Namen **in einer einzigen Spalte im kombinierten Datensatz mit** zusammengeführt. Diese Spalte bildet die Grundlage für die Identifizierung von Einzelpersonen in der Customer Journey Analytics.
* Zeilen werden anhand des Zeitstempels verarbeitet.
* Ereignisse werden auf die Millisekunden-Ebene aufgelöst.

## Beispiel

Siehe folgendes Beispiel. Sie haben zwei Ereignis-Datensätze mit jeweils unterschiedlichen Feldern, die unterschiedliche Daten enthalten.

>[!NOTE]
>
>Adobe Experience Platform speichert normalerweise einen Zeitstempel in UNIX® Millisekunden. Zur besseren Lesbarkeit werden in diesem Beispiel Datum und Uhrzeit verwendet.

| example_id | timestamp | string_color | string_animal | metric_a |
| --- | --- | --- | --- | ---: |
| user_310 | 1. Januar 7:02 | Rot | Fuchs | |
| user_310 | 1. Januar 7:04 | | | 2 |
| user_310 | 1. Januar 7:08 | Blau | | 3 |
| user_847 | 12.01:31 | | Schildkröte | 4 |
| user_847 | 12.01:44 | | | 2 |

| distinct_id | timestamp | string_color | string_shape | metric_b |
| --- | --- | --- | --- | ---: |
| user_847 | 12.01:26 | Gelb | Kreis | 8,5 |
| user_847 | 14. Januar:01 | Rot | | |
| alternateid_656 | 2. Januar 8:58 | Rot | Square | 4.2 |
| alternateid_656 | 2. Januar 21:03 | | Dreieck | 3,1 |

Wenn Sie eine Verbindung mit diesen beiden Ereignis-Datensätzen erstellen und

* `example_id` als Personen-ID für den ersten Datensatz und
* `different_id` als Personen-ID für den zweiten Datensatz,

der folgende kombinierte Datensatz wird für die Berichterstellung verwendet.

| id | timestamp | string_color | string_animal | string_shape | metric_a | metric_b |
| --- | --- | --- | --- | --- | ---: | ---: |
| user_310 | 1. Januar 7:02 | Rot | Fuchs | | | |
| user_310 | 1. Januar 7:04 | | | | 2 | |
| user_310 | 1. Januar 7:08 | Blau | | | 3 | |
| user_847 | 12.01:26 | Gelb | | Kreis | | 8,5 |
| user_847 | 12.01:31 | | Schildkröte | | 4 | |
| user_847 | 12.01:44 | | | | 2 | |
| user_847 | 14. Januar:01 | Rot | | | | |
| alternateid_656 | 2. Januar 8:58 | Rot | | Square | | 4.2 |
| alternateid_656 | 2. Januar 21:03 | | | Dreieck | | 3,1 |

Um die Bedeutung von Schemapfaden zu veranschaulichen, beachten Sie dieses Szenario. Im ersten Datensatz basiert `string_color` auf dem Schemapfad `_experience.whatever.string_color` und im zweiten Datensatz auf dem Schemapfad `_experience.somethingelse.string_color`. In diesem Szenario werden die Daten **nicht** in eine Spalte im resultierenden kombinierten Datensatz zusammengeführt. Stattdessen ergibt sich aus zwei `string_color` -Spalten im kombinierten Datensatz:

| id | timestamp | _experience.<br/>was auch immer.<br/>string_color | _experience.<br/>etwas Anderes.<br/>string_color | string_animal | string_shape | metric_a | metric_b |
|---|---|---|---|---|---|---:|---:|
| user_310 | 1. Januar 7:02 | Rot | | Fuchs | | | |
| user_310 | 1. Januar 7:04 | | | | | 2 | |
| user_310 | 1. Januar 7:08 | Blau | | | | 3 | |
| user_847 | 12.01:26 | | Gelb | | Kreis | | 8,5 |
| user_847 | 12.01:31 | | | Schildkröte |  | 4 | |
| user_847 | 12.01:44 | | | | | 2 | |
| user_847 | 14. Januar:01 | | Rot | | | | |
| alternateid_656 | 2. Januar 8:58 | | Rot | | Square | | 4.2 |
| alternateid_656 | 2. Januar 21:03 | | | | Dreieck | | 3,1 |

Dieser „kombinierte Ereignis-Datensatz“ wird für das Reporting verwendet. Es spielt keine Rolle, aus welchem Datensatz eine Zeile stammt. Customer Journey Analytics behandelt alle Daten so, als befänden sie sich im selben Datensatz. Wenn in beiden Datensätzen eine übereinstimmende Personen-ID angezeigt wird, werden sie als dieselbe eindeutige Person betrachtet. Wenn eine übereinstimmende Personen-ID in beiden Datensätzen mit einem Zeitstempel innerhalb von 30 Minuten angezeigt wird, werden sie als Teil derselben Sitzung betrachtet. Felder mit identischen Schemapfaden werden zusammengeführt.

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
>Wenn ein zusammengeführtes Feld ein Suchschlüssel für einen Ereignis-Datensatz in der Verbindung ist, reichert der zugehörige Lookup-Datensatz **alle** Werte dieses Felds an. Es spielt keine Rolle, aus welchem Ereignis-Datensatz eine Zeile stammt, da die Lookup-Beziehung mit dem Pfad des freigegebenen Schemas verknüpft ist.

## Kanalübergreifende Analyse

Die nächste Ebene der Kombination von Datensätzen ist die kanalübergreifende Analyse, bei der Datensätze aus verschiedenen Kanälen anhand einer gemeinsamen Kennung (Personen-ID) kombiniert werden. Die kanalübergreifende Analyse kann von der Funktion zum Zuordnen profitieren. So können Sie die Personen-ID eines Datensatzes neu zuweisen, damit der Datensatz ordnungsgemäß aktualisiert wird, um eine nahtlose Kombination mehrerer Datensätze zu ermöglichen. Beim Zuordnen werden Benutzerdaten aus authentifizierten und nicht authentifizierten Sitzungen untersucht, um eine zugeordnete ID zu generieren.

Mithilfe der kanalübergreifenden Analyse können Sie Fragen beantworten, z. B.:

* Wie viele Personen beginnen ihr Erlebnis auf einem Kanal und beenden es auf einem anderen?
* Wie viele Menschen interagieren mit meiner Marke? Wie viele und welche Gerätetypen verwenden sie? Wie überschneiden sich diese?
* Wie oft beginnen Personen mit einer Aufgabe auf einem Mobilgerät und wechseln dann zu einem Desktop-PC, um die Aufgabe abzuschließen? Führen Kampagnen-Clickthroughs, die auf einem Gerät landen, irgendwo anders zur Konversion?
* Wie ändert sich mein Verständnis von Kampagneneffizienz, wenn ich geräteübergreifende Journey berücksichtige? Wie ändert sich meine Trichteranalyse?
* Welche sind die häufigsten Pfade, die Benutzer beim Wechsel von einem Gerät zum anderen verwenden? Wo steigen sie aus? Wo schließen sie ihre Aktion erfolgreich ab?
* Wie unterscheidet sich das Verhalten von Benutzern mit mehreren Geräten von Benutzern mit nur einem Gerät?


Weiterführende Informationen zur kanalübergreifenden Analyse finden Sie im jeweiligen Anwendungsbeispiel:

* [Kanalübergreifende Analyse](../use-cases/cross-channel/cross-channel.md)

Eine ausführlichere Diskussion der Stitching-Funktion finden Sie unter:

* [Stitching-Übersicht](/help/stitching/overview.md)
* [Häufig gestellte Fragen](/help/stitching/faq.md)

