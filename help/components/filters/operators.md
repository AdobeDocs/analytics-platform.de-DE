---
title: Filteroperatoren
description: Bestimmen Sie, wie eine Komponente mit einem Wert in einem Filter interagiert.
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
feature: Filters
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 93%

---

# Filteroperatoren

Mit dem Filter-Builder können Sie Werte mithilfe ausgewählter Operatoren vergleichen und beschränken. Es gibt zwei Kategorien von Benutzern: [!UICONTROL Standard] und [!UICONTROL Eindeutige Zählung].

## Standardoperatoren

| Operator | Beschreibung |
| --- | --- |
| gleich | Gibt Elemente mit einer exakten Entsprechung für numerische oder Zeichenfolgenwerte wieder. Benutzen Sie bei Verwendung von Platzhalterzeichen den Operator „stimmt überein mit“. |
| ist nicht gleich | Gibt alle Elemente zurück, die keine exakte Übereinstimmung mit dem eingegebenen Wert enthalten.  Benutzen Sie bei Verwendung von Platzhalterzeichen den Operator „stimmt nicht überein mit“. |
| entspricht einem der folgenden Werte | Gibt alle Elemente getrennt durch ein Komma zurück, die mit den eingegebenen Werten der Unterzeichenfolgen übereinstimmen. |
| enthält | Gibt Elemente zurück, die mit den Unterzeichenfolgen der eingegebenen Werte vergleichbar sind. Wenn die Regel für eine Zeichenfolgendimension beispielsweise `"Search"` enthält, stimmt sie mit allen Seiten überein, die die Unterzeichenfolge `"Search"` enthalten, einschließlich `"Search Results"`, `"Search"` und `"Searching"`. Bei diesem Operator wird zwischen Groß- und Kleinschreibung unterschieden. |
| „Enthält nicht“ | Alle Elemente, die dem eingegebenen Wert entsprechen, werden aus den Ergebnissen ausgeschlossen. Wenn beispielsweise die Regel für eine Zeichenfolgendimension `"Search"` nicht enthält, werden alle Seiten ausgeschlossen, die die Unterzeichenfolge `"Search"` enthalten, einschließlich `"Search Results"`, `"Search"` und `"Searching"`. |
| enthält alle von | Gibt Elemente zurück, die alle Unterzeichenfolgen (durch ein Leerzeichen getrennt) in beliebiger Reihenfolge enthalten. Wenn Sie beispielsweise `"Search Results"` mit diesem Operator eingeben, stimmen `"Search Results"` und `"Results of Search"` überein, jedoch nicht `"Search"` oder `"Results"` unabhängig voneinander. Dieser Operator unterstützt bis zu 100 durch Leerzeichen getrennte Wörter. |
| enthält nicht alle von | Alle Elemente, die mit jedem eingegebenen Wert übereinstimmen, werden aus den Ergebnissen ausgeschlossen. Wenn Sie beispielsweise `"Search Results"` mit diesem Operator eingeben, werden `"Search Results"` und `"Results of Search"` ausgeschlossen, jedoch nicht `"Search"` oder `"Results"`. Dieser Operator unterstützt bis zu 100 durch Leerzeichen getrennte Wörter. |
| enthält beliebige von | Gibt Elemente zurück, die eine der angegebenen Unterzeichenfolgen enthalten. Wenn Sie beispielsweise `"Search Results"` mit diesem Operator eingeben, stimmen `"Search Results"`, `"Results of Search"`, `"Search"` und `"Results"` überein. Dieser Operator unterstützt bis zu 100 durch Leerzeichen getrennte Wörter. |
| enthält keinen von | Alle Elemente, die mit einer Unterzeichenfolge übereinstimmen, werden aus den Ergebnissen ausgeschlossen. Wenn Sie beispielsweise `"Search Results"` eingeben, werden `"Search Results"`, `"Results of Search"`, `"Search"` und `"Results"` ausgeschlossen. Dieser Operator unterstützt bis zu 100 durch Leerzeichen getrennte Wörter. |
| beginnt mit | Gibt Elemente zurück, die mit dem Zeichen oder der Zeichenfolge des eingegebenen Werts beginnen. |
| beginnt nicht mit | Gibt alle Elemente zurück, die nicht mit dem Zeichen oder der Zeichenfolge der eingegebenen Werte beginnen. |
| endet mit | Gibt Elemente zurück, die mit dem Zeichen oder der Zeichenfolge des eingegebenen Werts enden. |
| endet nicht mit | Gibt alle Elemente zurück, die nicht mit dem Zeichen oder der Zeichenfolge der eingegebenen Werte enden. |
| stimmt überein mit | Gibt Elemente mit einer exakten Entsprechung für gegebene numerische oder Zeichenfolgenwerte wieder. Unterstützt Platzhalter mit einem Sternchen (`*`). Bei diesem Operator wird zwischen Groß- und Kleinschreibung unterschieden. Beispiel:<ul><li>`a*e` stimmt überein mit `ae`, `abcde`, `adobe` und `a whole sentence`.</li><li>`adob*` stimmt überein mit `adobe`, `adobe analytics` und `adobo recipe`</li><li>`*dobe` stimmt überein mit `dobe`, `adobe` und `cute little dobe`.</li></ul> |
| stimmt nicht überein mit | Alle Elemente, die mit der Zeichenfolge übereinstimmen, werden ausgeschlossen. Unterstützt Platzhalter mit einem Sternchen (`*`). |
| vorhanden | Gibt Elemente zurück, wenn der Wert nicht null ist. |
| nicht vorhanden | Gibt Elemente zurück, wenn der Wert null ist. |

## Distinct Count-Operatoren

Sie können nach einer bestimmten Anzahl von Elementen innerhalb einer Dimension filtern. Sie können beispielsweise Filter für Personen erstellen, die mehr als 5 verschiedene Produkte oder Besuche angesehen haben, bei denen mehr als 5 verschiedene Seiten angezeigt wurden.

| Operator | Beschreibung |
| --- | --- |
| gleich | Gibt Dimensionselemente zurück, deren eindeutige Anzahl dem eingegebenen Wert entspricht. |
| ist nicht gleich | Gibt Dimensionselemente zurück, deren eindeutige Anzahl nicht dem eingegebenen Wert entspricht. |
| größer als | Gibt Dimensionselemente zurück, deren eindeutige Anzahl größer als der eingegebene Wert ist. |
| kleiner als | Gibt Dimensionselemente zurück, deren eindeutige Anzahl kleiner als der eingegebene Wert ist. |
| größer als oder gleich | Gibt Dimensionselemente zurück, deren eindeutige Anzahl größer als der eingegebene Wert ist oder damit übereinstimmt. |
| kleiner als oder gleich | Gibt Dimensionselemente zurück, deren eindeutige Anzahl kleiner als der eingegebene Wert ist oder damit übereinstimmt. |
