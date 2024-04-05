---
title: Hohe Kardinalitätsdimensionen
description: Erläutert, wie Customer Journey Analytics Dimensionen mit vielen eindeutigen Werten verarbeitet
feature: Dimensions
solution: Customer Journey Analytics
exl-id: 17b275a5-c2c2-48ee-b663-e7fe76f79456
role: User
source-git-commit: aaab21ef817e3acf67ca83cb6f9258b812625c8e
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 6%

---

# Hohe Kardinalitätsdimensionen

Bei Verwendung einer Dimension, die viele eindeutige Werte enthält, kann der resultierende Bericht zu viele eindeutige Dimensionselemente enthalten, die angezeigt oder berechnet werden können. Ergebnisse werden abgeschnitten, indem Dimensionselemente entfernt werden, die als am wenigsten wichtig erachtet werden. Diese Optimierungen erfolgen zur Gewährleistung der Projekt- und Produktleistung.

Wenn Sie einen Bericht mit zu vielen eindeutigen Werten anfordern, zeigt Analysis Workspace in der Dimensionsüberschrift einen Indikator an, der angibt, dass nicht alle Dimensionselemente einbezogen werden. Beispiel: &quot;Zeilen: 1-50 von mehr als 22.343.156&quot;. Das Keyword &quot;Mehr als&quot;zeigt an, dass eine Optimierung auf den Bericht angewendet wurde, um die wichtigsten Dimensionselemente zurückzugeben.

![Freiformtabelle in Workspace mit dem Keyword &quot;Mehr als&quot;, um 1-50 von mehr als 22.343.156 anzuzeigen](assets/high-cardinality.png)

## Festlegen der anzuzeigenden Dimensionselemente

Customer Journey Analytics verarbeitet Berichte zum Zeitpunkt ihrer Ausführung und verteilt den kombinierten Datensatz an mehrere Server. Die Daten pro Verarbeitungsserver werden nach Personen-ID gruppiert, d. h., ein einzelner Verarbeitungsserver enthält alle Daten für eine bestimmte Person. Sobald ein Server die Verarbeitung abgeschlossen hat, übergibt er seine Untergruppe verarbeiteter Daten an einen Aggregator-Server. Alle Teilmengen verarbeiteter Daten werden kombiniert und in Form eines Workspace-Berichts zurückgegeben.

Wenn ein einzelner Server Daten verarbeitet, die einen eindeutigen Schwellenwert überschreiten, werden die Ergebnisse abgeschnitten, bevor die verarbeitete Teilmenge der Daten zurückgegeben wird. Abgeschnittene Dimensionselemente werden basierend auf der Metrik bestimmt, die für die Sortierung verwendet wird.

Wenn es sich bei der Sortiermetrik um eine berechnete Metrik handelt, verwendet der Server die Metriken innerhalb der berechneten Metrik, um zu bestimmen, welche Dimensionselemente abgeschnitten werden sollen. Da berechnete Metriken mehrere Metriken unterschiedlicher Wichtigkeit enthalten können, können die Ergebnisse weniger präzise sein. Beispielsweise werden bei der Berechnung von &quot;Umsatz pro Person&quot;der Gesamtbetrag der Einnahmen und die Gesamtzahl der Personen zurückgegeben und aggregiert, bevor die Division durchgeführt wird. Daher wählt jeder einzelne Verarbeitungsserver, welche Elemente entfernt werden sollen, ohne zu wissen, wie sich ihre Ergebnisse auf die Gesamtsortierung auswirken.

Auch wenn einige einzelne Dimensionselemente in Berichten mit hoher Kardinalität fehlen, sind die Spaltensummen genau und nicht auf abgeschnittenen Daten basieren. Die Funktion &quot;Distinct Count&quot;(Distinct zählen) in berechneten Metriken wird auch nicht von abgeschnittenen Dimensionselementen beeinflusst.

## Best Practices für Dimensionen mit hoher Kardinalität

Die beste Möglichkeit, um Dimensionen mit hoher Kardinalität aufzunehmen, besteht darin, die Anzahl der Dimensionselemente zu begrenzen, die ein Bericht verarbeitet. Da alle Berichte zum Zeitpunkt ihrer Anforderung verarbeitet werden, können Sie die Berichtsparameter an die sofortigen Ergebnisse anpassen. Adobe empfiehlt eine der folgenden Optimierungen für Dimensionen mit hoher Kardinalität:

* Verwenden Sie eine [Filter](/help/components/filters/create-filters.md). Filter werden angewendet, wenn jeder Server eine Untergruppe von Daten verarbeitet.
* Verwenden Sie eine Suche. Aus dem Suchbegriff ausgeschlossene Dimension-Elemente werden aus den Berichtsergebnissen entfernt, sodass es wahrscheinlicher wird, dass Sie die gewünschten Dimensionselemente sehen.
* Verwenden Sie eine Lookup-Datensatzdimension. Lookup-Datensatzdimensionen kombinieren Elemente von Ereignis-Datensatzdimensionen, die die Anzahl der zurückgegebenen eindeutigen Werte begrenzen.
* Verwenden Sie die [Ein-/Ausschließen](/help/data-views/component-settings/include-exclude-values.md) Komponenteneinstellung im Datenansichtsmanager.
* Kürzen Sie den Datumsbereich der Anforderung. Wenn sich im Laufe der Zeit viele eindeutige Werte ansammeln, kann die Verkürzung des Datumsbereichs des Workspace-Berichts die Anzahl der eindeutigen Werte einschränken, die Server verarbeiten können.
* Verwenden Sie [Vollständiger Tabellenexport](/help/analysis-workspace/export/export-cloud.md) , um alle Zeilen der Tabelle zurückzugeben.
