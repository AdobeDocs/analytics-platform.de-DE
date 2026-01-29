---
title: Unterschiedliche Werte zählen Dimensionen
description: Anwendungsfall zum Zählen unterschiedlicher Werte für Dimensionen für die BI-Erweiterung in verschiedenen BI-Tools in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '950'
ht-degree: 0%

---

# Unterschiedliche Werte zählen Dimensionen


In diesem Anwendungsbeispiel möchten Sie die eindeutige Anzahl der Produktnamen abrufen, über die im Januar 2023 berichtet wurde.

+++ Customer Journey Analytics

Um einen Bericht über eine bestimmte Anzahl von Produktnamen zu erstellen, richten Sie eine berechnete Metrik in Customer Journey Analytics mit **[!UICONTROL Titel]** `Product Name (Count Distinct)` und **[!UICONTROL Externe ID]** `product_name_count_distinct` ein.

Berechnete Metrik ![Customer Journey Analytics-Produktname (Distincr Count)](../assets/cja-calc-metric-distinct-count-product-names.png)

Anschließend können Sie diese Metrik in einem Beispiel-Bedienfeld **[!UICONTROL Anzahl unterschiedlicher Dimension]** Werte für den Anwendungsfall verwenden:

![Unterschiedliche Customer Journey Analytics-Zählungswerte](../assets/cja-count-distinct-dimension-values.png)

+++

+++ BI-Tools

>[!PREREQUISITES]
>
>Stellen Sie sicher, [ Sie für das BI-Tool, für das Sie diesen Anwendungsfall ausprobieren möchten, (eine erfolgreiche Verbindung, Datenansichten auflisten ](connect-and-validate.md) eine Datenansicht verwenden) validiert haben.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. Um sicherzustellen, dass der Datumsbereich für alle Visualisierungen gilt, ziehen Sie **[!UICONTROL daterangeday]** aus dem Bereich **[!UICONTROL Daten]** auf **[!UICONTROL Filter]** dieser Seite.
   1. Wählen Sie **[!UICONTROL daterangeday is (All)]** unter **[!UICONTROL Filter auf dieser Seite]** aus.
   1. Wählen Sie **[!UICONTROL Erweiterte]**) als **[!UICONTROL Filtertyp]**.
   1. Definieren Sie den Filter für **[!UICONTROL Elemente anzeigen, wenn der Wert]** **[!UICONTROL auf oder nach]** `1/1/2023` **[!UICONTROL Und]****[!UICONTROL vor]** `2/1/2023` liegt.
   1. Wählen Sie **[!UICONTROL Filter anwenden]** aus.

1. Im Bereich **[!UICONTROL Daten]**:
   1. Wählen Sie **[!UICONTROL datarangeday]** aus.
   1. Wählen Sie **[!UICONTROL sum cm_product_name_count_distinct]** aus, wobei es sich um die in Customer Journey Analytics definierte berechnete Metrik handelt.

1. Um das vertikale Balkendiagramm in eine Tabelle zu ändern, stellen Sie sicher, dass Sie das Diagramm ausgewählt haben, und wählen Sie **[!UICONTROL Tabelle]** aus dem Bereich **[!UICONTROL Visualisierungen]** aus.

   Ihr Power BI-Desktop sollte wie folgt aussehen.

   ![Power BI Desktop Multiple Count Distinct-Tabelle](../assets/uc7-powerbi-table.png)

1. Wählen Sie die Tabellenvisualisierung aus. Wählen Sie im Kontextmenü die Optionen **[!UICONTROL Kopieren]** > **[!UICONTROL Visuell kopieren]** aus.
1. Fügen Sie die Visualisierung mithilfe von **[!UICONTROL Strg+V]** ein. Die genaue Kopie der Visualisierung überschneidet sich mit der ursprünglichen Visualisierung. Verschieben Sie sie nach rechts im Berichtsbereich.
1. Um die kopierte Visualisierung von einer Tabelle auf eine Karte zu ändern, wählen Sie **[!UICONTROL Karte]** unter **[!UICONTROL Visualisierungen]** aus.

   Ihr Power BI-Desktop sollte wie folgt aussehen.

   ![Power BI Desktop Multiple Count Distinct-Tabelle](../assets/uc7-powerbi-final.png)

Alternativ können Sie die Funktion „Distinct Count“ von Power BI verwenden.

1. Wählen Sie die Dimension **[!UICONTROL product_name]** aus.
1. Wenden Sie die Funktion **[!UICONTROL Anzahl (Distinct)]** auf die Dimension **[!UICONTROL product_name]** in **[!UICONTROL Columns]** an.

   ![Power BI-Anzahl unterschiedlich](../assets/uc7-powerbi-alternative.png)



>[!TAB Tableau Desktop]

1. Wählen Sie unten **[!UICONTROL Registerkarte Blatt 1]** aus, um aus **[!UICONTROL Datenquelle]** zu wechseln. In der Ansicht **[!UICONTROL Blatt 1]**:
   1. Ziehen Sie den **[!UICONTROL Daterange]** aus der Liste **[!UICONTROL Tabellen]** im Bereich **[!UICONTROL Daten]** und legen Sie den Eintrag auf dem Regal **[!UICONTROL Filter]** ab.
   1. Wählen Sie im Dialogfeld **[!UICONTROL Filterfeld \[Datumsbereich\]]** die Option **[!UICONTROL Datumsbereich]** und wählen Sie **[!UICONTROL Weiter >]**.
   1. Wählen Sie im **[!UICONTROL Filter \[Daterange\]]** die Option **[!UICONTROL Datumsbereich]** und anschließend `01/01/2023` - `31/1/2023` aus. Wählen Sie **[!UICONTROL Übernehmen]** und **[!UICONTROL OK]** aus.
   1. Ziehen Sie **[!UICONTROL cm Product Name Count Distinct]** in **[!UICONTROL Rows]**. Der Wert ändert sich in **[!UICONTROL SUM(CM Product Name Count Distinct)]**. Dieses Feld ist die berechnete Metrik, die Sie in Customer Journey Analytics definiert haben.
   1. Ziehen Sie **[!UICONTROL DateRangeDay]** und legen Sie neben **[!UICONTROL Spalten]** ab. Wählen Sie **[!UICONTROL DateRangeDay]** und wählen Sie im Dropdown-Menü **[!UICONTROL Day]** aus.
   1. Um die Visualisierungslinien einer Tabelle zu ändern, wählen Sie **[!UICONTROL Texttabelle]** unter **[!UICONTROL Anzeigen]** aus.
   1. Wählen Sie **[!UICONTROL Zeilen und Spalten austauschen]** in der Symbolleiste aus.
   1. Wählen **[!UICONTROL Breite anpassen]** aus dem Dropdown **[!UICONTROL Menü]** Anpassen“.

      Ihr Tableau-Desktop sollte wie folgt aussehen.

      ![Tableau Desktop-Filter mit mehreren Dimension-Rankings](../assets/uc7-tableau-data.png)

1. Wählen Sie **[!UICONTROL Duplizieren]** aus dem **[!UICONTROL Blatt 1]** Kontextmenü, um ein zweites Blatt zu erstellen.
1. Wählen Sie **[!UICONTROL Umbenennen]** aus dem Kontextmenü der Registerkarte **[!UICONTROL Blatt 1]**, um das Blatt in `Data` umzubenennen.
1. Wählen Sie **[!UICONTROL Umbenennen]** aus dem Kontextmenü der Registerkarte **[!UICONTROL Blatt 1 (2)]** aus, um das Blatt in `Card` umzubenennen.

1. Stellen Sie sicher, dass Sie die Ansicht **[!UICONTROL Karte]** ausgewählt haben.
1. Wählen Sie **[!UICONTROL DAY(DateRangeDay)]** und wählen Sie im Dropdown-Menü **[!UICONTROL Month]**. Der Wert ändert sich in **[!UICONTROL MONTH(DateRangeDay)]**.
1. Wählen Sie **[!UICONTROL SUM(CM Product Name Count Distinct)]** in **[!UICONTROL Marks]** und wählen Sie aus dem Dropdown-Menü **[!UICONTROL Format]**.
1. Um die Schriftgröße zu ändern, wählen Sie im Bereich **[!UICONTROL Format SUM(CM Product Name Count Distinct)]** die Option **[!UICONTROL Font]** in **[!UICONTROL Default]** und wählen Sie **[!UICONTROL 72]** für die Schriftgröße aus.
1. Um die Zahl auszurichten, wählen Sie **[!UICONTROL Automatisch]** neben **[!UICONTROL Ausrichtung]** und setzen **[!UICONTROL Horizontal]** auf Zentriert.
1. Um ganze Zahlen zu verwenden, wählen Sie **[!UICONTROL 123.456]** neben **[!UICONTROL Zahlen]** und wählen Sie **[!UICONTROL Zahl (Benutzerdefiniert)]**. Legen Sie **[!UICONTROL Dezimalstellen]** auf `0` fest.

   Ihr Tableau-Desktop sollte wie folgt aussehen.

   ![Tableau Desktop-Filter mit mehreren Dimension-Rankings](../assets/uc7-tableau-card.png)

1. Wählen Sie **[!UICONTROL Schaltfläche]** Neues Dashboard) unten aus, um eine neue Ansicht **[!UICONTROL Dashboard 1]** zu erstellen. In der Ansicht **[!UICONTROL Dashboard 1]**:
   1. Ziehen Sie das Blatt **[!UICONTROL Karte]** aus dem **[!UICONTROL Blätter]**-Regal auf die Ansicht **[!UICONTROL Dashboard 1]**, auf der *Blätter hier ablegen* steht.
   1. Ziehen Sie das Blatt **[!UICONTROL Daten]** aus dem **[!UICONTROL Blätter]**-Regal unter das Blatt **[!UICONTROL Karte]** auf der Ansicht **[!UICONTROL Dashboard 1]**.

   Ihre Ansicht **[!UICONTROL Dashboard 1]** sollte wie folgt aussehen.

   ![Tableau Desktop Dashboard 1](../assets/uc7-tableau-final.png)


Alternativ können Sie die Funktion Anzahl der verschiedenen Elemente von Tableau Desktop verwenden.

1. Verwenden Sie **[!UICONTROL Produktname]** anstelle von **[!UICONTROL cm Product Name Count Distinct]**.
1. Anwenden **[!UICONTROL Kennzahl]** > **[!UICONTROL Anzahl (Distinct)]** auf **[!UICONTROL Produktname]** in **[!UICONTROL Marks]**.

   ![Tableau-Anzahl unterschiedlich](../assets/uc7-tableau-alternative.png)


>[!TAB Looker]

1. Achten Sie in der **[!UICONTROL Explore]**-Oberfläche von Looker darauf, dass Sie über ein sauberes Setup verfügen. Wenn nicht, wählen Sie ![Einstellung](/help/assets/icons/Setting.svg) **[!UICONTROL Felder und Filter entfernen]**.
1. Wählen Sie **[!UICONTROL + Filter]** unter **[!UICONTROL Filter]** aus.
1. Im Dialogfeld **[!UICONTROL Filter hinzufügen]**:
   1. Wählen Sie **[!UICONTROL ‣ CC-Datenansicht]**
   1. Wählen Sie aus der Liste der Felder **[!UICONTROL ‣ DateRange]** und **[!UICONTROL DateRange]** aus.
      ![Looker-Filter](../assets/uc2-looker-filter.png)
1. Geben Sie den Filter **[!UICONTROL CC Datenansicht Datumsbereich]** als **[!UICONTROL liegt im Bereich]** **[!UICONTROL 2023/01/]****[!UICONTROL bis (davor)]** **[!UICONTROL 2023/02/01]** an.
1. Im Abschnitt **[!UICONTROL ‣ CC-Datenansicht]** in der linken Leiste:
   1. Wählen **[!UICONTROL dateRange]**, dann **[!UICONTROL date]** aus.
   1. Wählen Sie **[!UICONTROL Aggregate ‣ Count]**) aus dem Kontextmenü **⋮ Mehr** unter **[!UICONTROL Produktname]**.
      ![Kontextmenü für Looker-Produktnamen](../assets/uc7-looker-count-distinct.png)
1. Wählen Sie **[!UICONTROL Ausführen]** aus.
1. Wählen Sie **[!UICONTROL ‣ Visualisierung]** und wählen Sie 6︎⃣ in der Symbolleiste aus, um eine Visualisierung mit einem Wert anzuzeigen.

Es sollte eine Visualisierung und eine Tabelle ähnlich wie unten dargestellt angezeigt werden.

![Looker-Anzahl unterschiedlich](../assets/uc7-looker-result.png)


>[!TAB Jupyter-Notebook]

1. Geben Sie die folgenden Anweisungen in eine neue Zelle ein.

   ```
   data = %sql SELECT COUNT(DISTINCT(product_name)) AS `Product Name` \
      FROM cc_data_view \
      WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01';
   display(data)
   ```

1. Ausführen der Zelle. Es sollte eine ähnliche Ausgabe wie im folgenden Screenshot angezeigt werden.

   ![Jupyter Notebook-Ergebnisse](../assets/uc7-jupyter-results.png)


>[!TAB RStudio]

1. Geben Sie die folgenden Anweisungen zwischen ` ```{r} ` und ` ``` ` in einen neuen Block ein.

   ```R
   ## Count Distinct
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01") %>%
      summarise(product_name_count_distinct = n_distinct(product_name))
   print(df)
   ```

1. Führt den Block aus. Es sollte eine ähnliche Ausgabe wie im folgenden Screenshot angezeigt werden.

   ![RStudio Ergebnisse](../assets/uc7-rstudio-results.png)


>[!ENDTABS]

+++

