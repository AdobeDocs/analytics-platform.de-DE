---
title: Operatoren
description: Bestimmen, wie eine Komponente mit einem Wert innerhalb eines Segments interagiert
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
feature: Filters, Segments
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 54%

---

# Operatoren

Mit Segment Builder können Sie Werte für Komponenten mithilfe ausgewählter Operatoren vergleichen und beschränken. Es gibt zwei Kategorien von Benutzern: [[!UICONTROL Standard]](#standard-operators) und [[!UICONTROL Eindeutige Zählung]](#distinct-count-operators).

## Standardoperatoren

| Operator | Beschreibung |
| --- | --- |
| **[!UICONTROL gleich]** | Gibt Elemente mit einer exakten Entsprechung für numerische oder Zeichenfolgenwerte wieder. Verwenden Sie bei Verwendung von Platzhalterzeichen den Operator „stimmt überein mit“. |
| **[!UICONTROL nicht gleich]** | Gibt alle Elemente zurück, die keine exakte Übereinstimmung mit dem eingegebenen Wert enthalten.  Wenn Sie Platzhalterzeichen verwenden, stimmt der Operator nicht überein mit dem Operator. |
| **[!UICONTROL Entspricht einem von]** | Gibt alle Elemente getrennt durch ein Komma zurück, die mit den eingegebenen Werten der Unterzeichenfolgen übereinstimmen. |
| **[!UICONTROL enthält]** | Gibt Elemente zurück, die mit den Unterzeichenfolgen der eingegebenen Werte vergleichbar sind. Wenn der Wert für eine Dimension Seitenname beispielsweise `Search` enthält, stimmt dieser Operator mit allen Seiten überein, deren Name die Teilzeichenfolge `Search` enthält, einschließlich `Search Results`, `Search` und `Searching`. Bei diesem Operator wird zwischen Groß- und Kleinschreibung unterschieden. |
| **[!UICONTROL enthält nicht]** | Alle Elemente, die dem eingegebenen Wert entsprechen, werden aus den Ergebnissen ausgeschlossen. Wenn beispielsweise der Wert für eine Dimension Seitenname keine `Search` enthält, schließt dieser Operator alle Seiten aus, deren Name die Teilzeichenfolge `Search` enthält, einschließlich `Search Results`, `Search` und `Searching`. |
| **[!UICONTROL enthält alle von]** | Gibt Elemente zurück, die alle Unterzeichenfolgen (durch ein Leerzeichen getrennt) in beliebiger Reihenfolge enthalten. Wenn Sie beispielsweise `Search Results` als Wert für diesen Operator angeben, stimmen `Search Results` und `Results of Search` überein, jedoch nicht `Search` oder `Results` unabhängig voneinander. Dieser Operator unterstützt bis zu 100 durch Leerzeichen getrennte Wörter. |
| **[!UICONTROL enthält nicht alle von]** | Alle Elemente, die mit jedem eingegebenen Wert übereinstimmen, werden aus den Ergebnissen ausgeschlossen. Wenn Sie beispielsweise `Search Results` als Wert für diesen Operator angeben, werden `Search Results` und `Results of Search` ausgeschlossen, jedoch nicht `Search` oder `Results`. Dieser Operator unterstützt bis zu 100 durch Leerzeichen getrennte Wörter. |
| **[!UICONTROL enthält beliebige von]** | Gibt Elemente zurück, die eine der angegebenen Unterzeichenfolgen enthalten. Wenn Sie beispielsweise `Search Results` als Wert für diesen Operator angeben, stimmen `Search Results`, `Results of Search`, `Search` und `Results` überein. Dieser Operator unterstützt bis zu 100 durch Leerzeichen getrennte Wörter. |
| **[!UICONTROL enthält keinen von]** | Alle Elemente, die mit einer Unterzeichenfolge übereinstimmen, werden aus den Ergebnissen ausgeschlossen. Wenn Sie beispielsweise `Search Results` als Wert für diesen Operator angeben, werden `Search Results`, `Results of Search`, `Search` und `Results` ausgeschlossen. Dieser Operator unterstützt bis zu 100 durch Leerzeichen getrennte Wörter. |
| **[!UICONTROL beginnt mit]** | Gibt Elemente zurück, die mit dem Zeichen oder der Zeichenfolge des angegebenen Werts beginnen. |
| **[!UICONTROL beginnt nicht mit]** | Gibt alle Elemente zurück, die nicht mit den Zeichen oder Zeichenfolgen des angegebenen Werts beginnen. |
| **[!UICONTROL endet mit]** | Gibt Elemente zurück, die mit dem Zeichen oder der Zeichenfolge des angegebenen Werts enden. |
| **[!UICONTROL endet nicht mit]** | Gibt alle Elemente zurück, die nicht mit den Zeichen oder Zeichenfolgen des angegebenen Werts enden. |
| **[!UICONTROL stimmt überein mit]** | Gibt Elemente zurück, die genau basierend auf einem gegebenen numerischen oder Zeichenfolgenwert mit Elementen übereinstimmen. Unterstützt Platzhalter mit einem Sternchen (`*`). Bei diesem Operator wird zwischen Groß- und Kleinschreibung unterschieden. Beispiel:<ul><li>`a*e` stimmt überein mit `ae`, `abcde`, `adobe` und `a whole sentence`.</li><li>`adob*` stimmt überein mit `adobe`, `adobe analytics` und `adobo recipe`</li><li>`*dobe` stimmt überein mit `dobe`, `adobe` und `cute little dobe`.</li></ul> |
| **[!UICONTROL stimmt nicht überein mit]** | Alle Elemente, die mit der Zeichenfolge übereinstimmen, werden ausgeschlossen. Unterstützt Platzhalter mit einem Sternchen (`*`). |
| **[!UICONTROL vorhanden]** | Gibt Elemente zurück, wenn der Wert nicht null ist. |
| **[!UICONTROL nicht vorhanden]** | Gibt Elemente zurück, wenn der Wert null ist. |

## Distinct Count-Operatoren

Sie können nach einer bestimmten Anzahl von Elementen innerhalb einer Dimension segmentieren. Sie können beispielsweise Segmente für Personen erstellen, die mehr als 5 verschiedene Produkte oder Besuche angesehen haben, bei denen mehr als 5 verschiedene Seiten angezeigt wurden.

| Operator | Beschreibung |
| --- | --- |
| **[!UICONTROL gleich]** | Gibt Dimensionselemente zurück, deren eindeutige Anzahl dem eingegebenen Wert entspricht. |
| **[!UICONTROL nicht gleich]** | Gibt Dimensionselemente zurück, deren eindeutige Anzahl nicht dem eingegebenen Wert entspricht. |
| **[!UICONTROL größer als]** | Gibt Dimensionselemente zurück, deren eindeutige Anzahl größer als der eingegebene Wert ist. |
| **[!UICONTROL kleiner als]** | Gibt Dimensionselemente zurück, deren eindeutige Anzahl kleiner als der eingegebene Wert ist. |
| **[!UICONTROL größer als oder gleich]** | Gibt Dimensionselemente zurück, deren eindeutige Anzahl größer als der eingegebene Wert ist oder damit übereinstimmt. |
| **[!UICONTROL kleiner als oder gleich]** | Gibt Dimensionselemente zurück, deren eindeutige Anzahl kleiner als der eingegebene Wert ist oder damit übereinstimmt. |
