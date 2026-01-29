---
title: Einschränkungen
description: Einschränkungen für die BI-Erweiterung in verschiedenen BI-Tools in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: cb0102923f10f39becd40cc4187d2e11fb8c4e2f
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 0%

---

# Einschränkungen


Jedes der unterstützten BI-Tools hat einige Einschränkungen bei der Arbeit mit der Customer Journey Analytics BI-Erweiterung.

+++ BI-Tools

>[!BEGINTABS]

>[!TAB Power BI Desktop]

* Die Filterung des erweiterten Datumsbereichs von Power BI Desktop ist exklusiv.  Wählen Sie für Ihr Enddatum ein Datum nach dem Tag aus, an dem Sie einen Bericht erstellen möchten. Beispiel: **[!UICONTROL ist an oder nach]** `1/1/2023` **[!UICONTROL und davor]** `1/2/2023`.
* Power BI Desktop **[!UICONTROL beim]** einer Verbindung standardmäßig auf „Importieren“. Stellen Sie sicher, dass Sie **[!UICONTROL Direktabfrage]** verwenden.
* Power BI Desktop stellt Datenumwandlungen über Power Query bereit.  Power Query funktioniert in erster Linie mit Verbindungen vom Typ Import . Viele Umwandlungen, wie z. B. Datums- oder Zeichenfolgen-Funktionen, geben einen Fehler aus, der besagt, dass Sie zu einer Verbindung vom Typ Import wechseln müssen.  Wenn Sie Daten zur Abfragezeit umwandeln müssen, sollten Sie abgeleitete Dimensionen und Metriken verwenden, damit Power BI die Umwandlungen nicht selbst durchführen muss.
* Power BI Desktop versteht nicht, wie Spalten vom Typ Datum/Uhrzeit verarbeitet werden, sodass die Dimensionen **[!UICONTROL daterange *X *]**&#x200B;wie&#x200B;**[!UICONTROL daterangehour &#x200B;]**&#x200B;und&#x200B;**[!UICONTROL daterangeminute &#x200B;]**&#x200B;nicht unterstützt werden.
* Power BI Desktop versucht standardmäßig, mehrere Verbindungen herzustellen, indem mehr Query Service-Sitzungen verwendet werden.  Gehen Sie zu den Power BI-Einstellungen für Ihr Projekt und deaktivieren Sie parallele Abfragen.
* Power BI Desktop übernimmt die Sortierung und Client-seitige Einschränkung. Power BI Desktop verfügt auch über verschiedene Semantiken für Top *X*-Filter, die gebundene Werte enthalten. Sie können also nicht dieselbe Sortierung und Begrenzung erstellen wie in Analysis Workspace.
* Frühere Versionen der Power BI-Desktop-Version vom Oktober 2024 unterbrechen PostgreSQL-Datenquellen. Stellen Sie sicher, dass Sie die in diesem Artikel erwähnte Version verwenden.

>[!TAB Tableau Desktop]

* Tableau Desktop Datumsbereich ist exklusiv. Wählen Sie für Ihr Enddatum ein Datum nach dem Tag aus, an dem Sie einen Bericht erstellen möchten.
* Wenn Sie eine Datums- oder Datums-/Uhrzeitdimension wie **[!UICONTROL Daterangemonth]** zu den Zeilen eines Blatts hinzufügen, umschließt Tableau Desktop das Feld standardmäßig in eine **[!UICONTROL YEAR()]**-Funktion.  Um zu erhalten, was Sie möchten, müssen Sie diese Dimension auswählen und aus dem Dropdown-Menü die Datumsfunktion auswählen, die Sie verwenden möchten.  Ändern Sie beispielsweise **[!UICONTROL Year]** auf **[!UICONTROL Month]**, wenn Sie &quot;**[!UICONTROL Month“]**.
* Die Begrenzung der Ergebnisse auf die Top *X* ist in Tableau Desktop nicht offensichtlich. Sie können die Ergebnisse explizit oder mit einem berechneten Feld und der Funktion **[!UICONTROL INDEX()]** einschränken.  Durch Hinzufügen eines Top *X*-Filters zu einer Dimension wird eine komplexe SQL mit einem inneren Join generiert, der nicht unterstützt wird.

>[!TAB Looker]

* Looker verfügt über eine Einstellung für die maximale Anzahl von Verbindungen pro Knoten, die zwischen 5 und 100 liegen muss.  Sie können diesen Wert nicht auf 1 setzen.  Diese Einstellung bedeutet, dass eine Looker-Verbindung immer mindestens 5 der verfügbaren Query Service-Sitzungen verwendet.
* Mit Looker können Sie ein Projekt mit einer Ansicht erstellen, die auf einer Customer Journey Analytics-Datenansicht basiert. Looker erstellt dann mithilfe von LookerML ein Modell basierend auf den Dimensionen und Metriken, die in der Datenansicht verfügbar sind.  Diese Projektansicht wird nicht automatisch entsprechend der Quelle aktualisiert.  Wenn Sie Änderungen oder Ergänzungen an den Dimensionen, Metriken, berechneten Metriken oder Segmenten der CJA-Datenansicht vornehmen, werden diese Änderungen nicht automatisch in Looker angezeigt.  Sie müssen die Projektansicht manuell aktualisieren oder ein neues Projekt erstellen.
* Das Benutzererlebnis des Lookers in Datums- oder Datums-/Uhrzeitfeldern wie **[!UICONTROL DateRange]** oder **[!UICONTROL DateRangeDay]** ist verwirrend.
* Der Datumsbereich des Lookers ist exklusiv anstatt inklusiv.  Der **[!UICONTROL bis (before)]** ist grau, sodass Sie diesen Aspekt verpassen könnten.  Für Ihren Endtag müssen Sie einen nach dem Tag auswählen, an dem Sie einen Bericht erstellen möchten.
* Looker behandelt Ihre Metriken nicht automatisch als Metriken.  Wenn Sie eine Metrik auswählen, versucht der Looker standardmäßig, die Metrik als Dimension in der Abfrage zu behandeln.  Um eine Metrik als Metrik zu behandeln, müssen Sie ein benutzerdefiniertes Feld wie oben dargestellt erstellen. Als Tastaturbefehl können Sie **[!UICONTROL ⋮]**, **[!UICONTROL Aggregat]** und dann **[!UICONTROL Summe]** auswählen.

>[!TAB Jupyter-Notebook]

* Der Hauptnachteil für Jupyter Notebook ist, dass das Tool keine Drag-and-Drop-Benutzeroberfläche wie andere BI-Tools hat. Sie können gute Visualisierungen erstellen, aber Sie müssen Code schreiben, um dies zu erreichen.

>[!TAB RStudio]

* R dplyr arbeitet mit einem flachen Schema, daher ist **[!UICONTROL Option &quot;]**&quot; erforderlich.
* Der Hauptnachteil für RStudio ist, dass das Tool keine Drag-and-Drop-Benutzeroberfläche wie andere BI-Tools hat. Sie können gute Visualisierungen erstellen, aber Sie müssen Code schreiben, um dies zu erreichen.

>[!ENDTABS]

+++
