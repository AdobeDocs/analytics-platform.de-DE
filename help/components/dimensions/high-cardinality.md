---
title: Dimensionen hoher Kardinalität
description: Erläutert, wie Customer Journey Analytics Dimensionen mit vielen eindeutigen Werten verarbeitet.
feature: Dimensions
solution: Customer Journey Analytics
exl-id: 17b275a5-c2c2-48ee-b663-e7fe76f79456
role: User
TQID: https://experienceleague.adobe.com/cDOJq7Dc6x301enIo7h-cm8pGphmnvQAihnLoYGIr-A
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 622
ht-degree: 11%

---

# Dimensionen hoher Kardinalität

Bei Verwendung einer Dimension, die viele eindeutige Werte enthält, kann der resultierende Bericht zu viele eindeutige Dimensionselemente enthalten, um sie anzuzeigen oder zu berechnen. Die Ergebnisse werden abgeschnitten, indem Dimensionselemente entfernt werden, die als am wenigsten wichtig erachtet werden. Diese Optimierungen werden vorgenommen, um die Projekt- und Produktleistung zu erhalten.

Wenn Sie einen Bericht anfordern, der eine Dimension mit zu vielen eindeutigen Werten enthält, zeigt Analysis Workspace einen Indikator im Dimensions-Header an, der besagt, dass nicht alle Dimensionselemente enthalten sind. Beispiel: **[!UICONTROL : 1-50 von mehr als 22.343.156]**. Das **[!UICONTROL -Schlüsselwort]** more than“ zeigt an, dass der Bericht optimiert wurde, um die wichtigsten Dimensionselemente zurückzugeben.

![Freiformtabelle in Workspace mit dem Keyword „more than“, um 1-50 von mehr als 22.343.156 anzuzeigen](assets/high-cardinality.png)

## Bestimmen, welche Dimensionselemente angezeigt werden sollen

Customer Journey Analytics verarbeitet Berichte zum Zeitpunkt ihrer Ausführung und verteilt den kombinierten Datensatz an mehrere Server. Die Größe der Datenanfrage und die Menge der verfügbaren Adobe-Hardware sind zwei von vielen Faktoren, die die Bestimmung der Anzahl der Server unterstützen, die einem Bericht zugewiesen sind. Da Server dynamisch zugewiesen und in der Benutzeroberfläche nicht sichtbar sind, gibt es keine Möglichkeit, die Anzahl der Server anzuzeigen oder zu steuern, die einen Bericht verarbeiten.

Die Daten pro Verarbeitungs-Server werden nach Personen-ID gruppiert, d. h., ein einzelner Verarbeitungs-Server enthält alle Daten für eine bestimmte Person. Sobald ein Server die Verarbeitung abgeschlossen hat, übergibt er seine Teilmenge der verarbeiteten Daten an einen Aggregator-Server. Alle Teilmengen verarbeiteter Daten werden kombiniert und in Form eines Workspace-Berichts zurückgegeben.

Wenn ein einzelner Server Daten verarbeitet, die einen eindeutigen Schwellenwert überschreiten, werden die Ergebnisse gekürzt, bevor die verarbeitete Teilmenge der Daten zurückgegeben wird. Abgeschnittene Dimensionselemente werden basierend auf der Metrik bestimmt, die für die Sortierung verwendet wird.

Wenn es sich bei der Sortiermetrik um eine berechnete Metrik handelt, verwendet der Server die Metriken innerhalb der berechneten Metrik, um zu bestimmen, welche Dimensionselemente abgeschnitten werden sollen. Da berechnete Metriken mehrere Metriken unterschiedlicher Bedeutung enthalten können, können die Ergebnisse weniger genau sein. Beispielsweise werden bei der Berechnung des „Umsatzes pro Person“ der Gesamtbetrag der Einnahmen und die Gesamtzahl der Personen zurückgegeben und vor der Teilung aggregiert. Daher wählt jeder einzelne Verarbeitungs-Server aus, welche Elemente entfernt werden sollen, ohne zu wissen, wie sich die Ergebnisse auf die Sortierung insgesamt auswirken.

Obwohl einige einzelne Dimensionselemente in Berichten mit hoher Kardinalität fehlen können, sind die Spaltensummen korrekt und basieren nicht auf abgeschnittenen Daten. Die Funktion [[!UICONTROL Ungefährer Distinct Count]](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct) der berechneten Metrik ist ebenfalls nicht von abgeschnittenen Dimensionselementen betroffen.

## Best Practices für Dimensionen mit hoher Kardinalität

Die beste Möglichkeit, Dimensionen mit hoher Kardinalität zu berücksichtigen, besteht darin, die Anzahl der Dimensionselemente zu begrenzen, die ein Bericht verarbeitet. Da alle Berichte zum Zeitpunkt ihrer Anforderung verarbeitet werden, können Sie die Berichtsparameter für sofortige Ergebnisse anpassen. Adobe empfiehlt eine der folgenden Optimierungen für Dimensionen mit hoher Kardinalität:

* Verwenden Sie ein [Segment](/help/components/segments/seg-create.md). Segmente gelten zu dem Zeitpunkt, zu dem jeder Server eine Teilmenge von Daten verarbeitet.
* Verwenden Sie eine Suche. Dimension-Elemente, die vom Suchbegriff ausgeschlossen sind, werden aus den Berichtsergebnissen entfernt, sodass die Wahrscheinlichkeit höher ist, dass die gewünschten Dimensionselemente angezeigt werden.
* Verwenden Sie eine Lookup-Datensatzdimension. Lookup-Datensatzdimensionen kombinieren Elemente von Ereignis-Datensatzdimensionen, die die Anzahl der zurückgegebenen eindeutigen Werte begrenzen.
* Verwenden Sie die [Einschließen/ausschließen](/help/data-views/component-settings/include-exclude-values.md) im Datenansichts-Manager.
* Kürzen Sie den Datumsbereich der Anfrage. Wenn im Laufe der Zeit viele eindeutige Werte gesammelt werden, kann eine Verkürzung des Datumsbereichs des Workspace-Berichts die Anzahl der eindeutigen Werte für die zu verarbeitenden Server einschränken.
* Erwägen Sie [vollständigen Tabellenexport](/help/analysis-workspace/export/export-cloud.md), um alle Zeilen der Tabelle zurückzugeben.
* Wenn die Anzahl der eindeutigen Werte der primäre Fokus ist, verwenden Sie die [[!UICONTROL &#x200B; Metrikfunktion „Ungefährer &#x200B;]](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct)&quot;.
