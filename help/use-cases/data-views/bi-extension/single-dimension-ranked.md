---
title: Einzelne Dimension-Rangfolge
description: Rang eines Anwendungsfalls für die BI-Erweiterung in verschiedenen BI-Tools in Customer Journey Analytics mit einer Dimension
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 1%

---

# Rangfolge einzelner Dimensionen


In diesem Anwendungsbeispiel möchten Sie eine Tabelle und eine einfache Balkenvisualisierung anzeigen, die die Käufe und Käufe von Produktnamen für das Jahr 2023 anzeigt.

+++ Customer Journey Analytics

Ein Beispiel **[!UICONTROL Bedienfeld „Single Dimension Ranked]** für den Anwendungsfall:

Visualisierung mit einer Rangansicht für ![Customer Journey Analytics-Dimension](../assets/cja-single-dimension-ranked.png)

+++

+++ BI-Tools

>[!PREREQUISITES]
>
>Stellen Sie sicher, [ Sie für das BI-Tool, für das Sie diesen Anwendungsfall ausprobieren möchten, (eine erfolgreiche Verbindung, Datenansichten auflisten ](connect-and-validate.md) eine Datenansicht verwenden) validiert haben.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. Im Bereich **[!UICONTROL Daten]**:
   1. Wählen Sie **[!UICONTROL daterange]** aus.
   1. Wählen Sie **[!UICONTROL product_name]** aus.
   1. Wählen Sie **[!UICONTROL sum_purchase_venue]** aus.
   1. Wählen Sie **[!UICONTROL Summenkäufe]** aus.

   Eine leere Tabelle wird angezeigt, in der nur die Spaltenüberschriften für das ausgewählte Element angezeigt werden. Zur besseren Sichtbarkeit vergrößern Sie die Visualisierung.

1. Im Bereich **[!UICONTROL Filter]**:

   1. Wählen Sie **[!UICONTROL daterange is (All)]** unter **[!UICONTROL Filter auf dieser visuellen]**) aus.
   1. Wählen Sie **[!UICONTROL Relatives Datum]** als **[!UICONTROL Filtertyp]** aus.
   1. Definieren Sie den Filter für **[!UICONTROL Elemente anzeigen, wenn der Wert]****[!UICONTROL in den letzten]**`1` **[!UICONTROL Kalenderjahren)]**.
   1. Wählen Sie **[!UICONTROL Filter anwenden]** aus.

   Die Tabelle wird mit dem angewendeten Filter &quot;**[!UICONTROL &quot; aktualisiert]**.

1. Im Bereich **[!UICONTROL Visualisierung]**:

   1. Verwenden Sie ![CrossSize](/help/assets/icons/CrossSize75.svg), um **[!UICONTROL daterange]** aus **[!UICONTROL Columns]** zu entfernen.
   1. Ziehen Sie **[!UICONTROL Summe der Käufe_Umsatz]** per Drag-and-Drop unter **[!UICONTROL Summe der]** in **[!UICONTROL Spalten]**.

1. Visualisierung in der Tabelle:

   1. Wählen Sie **[!UICONTROL Summe aus Purchase_Revenue]**, um die Produktnamen in absteigender Reihenfolge des Bestellumsatzes zu sortieren. Ihr Power BI-Desktop sollte wie folgt aussehen.

   ![Power BI-Desktop-Anwendungsfall 5 - Tabellenstatus](../assets/uc5-pbi-table.png)

1. Im Bereich **[!UICONTROL Filter]**:

   1. Wählen Sie **[!UICONTROL product_name is (All)]**.
   1. Setzen Sie **[!UICONTROL Filtertyp]** auf **[!UICONTROL Top N]**.
   1. Definieren Sie den Filter für **[!UICONTROL Elemente anzeigen]** **[!UICONTROL Oben]** `10` **[!UICONTROL Nach Wert]**.
   1. Ziehen Sie &quot;**[!UICONTROL _Revenue]** per Drag-and-Drop in **[!UICONTROL By value]** **[!UICONTROL Datenfelder hier hinzufügen]**.
   1. Wählen Sie **[!UICONTROL Filter anwenden]** aus.

   Die Tabelle wird mit Werten für den Kaufumsatz aktualisiert, synchron mit der Freiformtabellen-Visualisierung in Analysis Workspace.

1. Im Bereich **[!UICONTROL Visualisierungen]**:

   1. Wählen Sie die **[!UICONTROL Liniendiagramm und gestapeltes Säulendiagramm]** aus.

   Eine Liniendiagramm- und gestapelte Spaltendiagramm-Visualisierung ersetzt die Tabelle, wobei dieselben Daten wie die Tabelle verwendet werden.

1. Ziehen Sie **[!UICONTROL Bestellungen]** per Drag-and **[!UICONTROL Drop auf die]** Linie y im Bereich **[!UICONTROL Visualisierungen]**.

   Das Liniendiagramm und das gestapelte Säulendiagramm werden aktualisiert. Ihr Power BI-Desktop sollte wie folgt aussehen.

   ![Diagramm zu Power BI-Desktop-Anwendungsfall 5](../assets/uc5-pbi-chart.png)

1. Visualisierung des Linien- und gestapelten Säulendiagramms:

   1. Wählen Sie ![Mehr](/help/assets/icons/More.svg) aus.
   1. Wählen Sie im Kontextmenü die Option **[!UICONTROL Als Tabelle anzeigen]** aus.

   Die Hauptansicht wird aktualisiert, um sowohl eine Linienvisualisierung als auch eine Tabelle anzuzeigen.

   ![Power BI-Desktop-Anwendungsfall: 2. Visualisierung des endgültigen täglichen Trends](../assets/uc5-pbi-final.png)

>[!TAB Tableau Desktop]

1. Wählen Sie unten **[!UICONTROL Registerkarte Blatt 1]** aus, um aus **[!UICONTROL Datenquelle]** zu wechseln. In der Ansicht **[!UICONTROL Blatt 1]**:
   1. Ziehen Sie den **[!UICONTROL Daterange]** aus der Liste **[!UICONTROL Tabellen]** im Bereich **[!UICONTROL Daten]** und legen Sie den Eintrag auf dem Regal **[!UICONTROL Filter]** ab.
   1. Wählen Sie im Dialogfeld **[!UICONTROL Filterfeld \[Datumsbereich\]]** die Option **[!UICONTROL Datumsbereich]** und wählen Sie **[!UICONTROL Weiter >]**.
   1. Wählen Sie im Dialogfeld **[!UICONTROL Filter \[Daterange\]]** die Option **[!UICONTROL Datumsbereich]** und geben Sie einen Zeitraum von `01/01/2023` bis `31/12/2023` an. Wählen Sie **[!UICONTROL Übernehmen]** und **[!UICONTROL OK]** aus.

      ![Tableau Desktop-Filter](../assets/uc5-tableau-filter.png)

   1. Ziehen Sie **[!UICONTROL Produktname]** per Drag-and-Drop aus der Liste **[!UICONTROL Tabellen]** in den Bereich **[!UICONTROL Daten]** und legen Sie den Eintrag im Feld neben **[!UICONTROL Zeilen]** ab.
   1. Ziehen Sie &quot;**[!UICONTROL Bestellungen]** per Drag-and **[!UICONTROL Drop aus der Liste Tabellen (*Kennzahlennamen*)]** in den Bereich **[!UICONTROL Daten]** und legen Sie den Eintrag im Feld neben **[!UICONTROL Zeilen]** ab. Der Wert wird automatisch in **[!UICONTROL SUM(Purchases)]**.
   1. Ziehen Sie &quot;**[!UICONTROL Umsatz]** per Drag-and-Drop aus der Liste **[!UICONTROL Tabellen (*Kennzahlennamen*)]** in den Bereich **[!UICONTROL Daten]** und legen Sie den Eintrag in das Feld neben **[!UICONTROL Spalten]** und links von **[!UICONTROL SUM(Purchases)]** ab. Der Wert wird automatisch in **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Um beide Diagramme in absteigender Reihenfolge des Einkaufsumsatzes zu bestellen, bewegen Sie den Mauszeiger über den **[!UICONTROL Kaufumsatz]** und wählen Sie das Symbol Sortieren aus.
   1. Um die Anzahl der Einträge in den Diagrammen zu begrenzen, wählen Sie **[!UICONTROL SUM(Kaufumsatz)]** in **[!UICONTROL Zeilen]** und aus dem Dropdown-Menü **[!UICONTROL Filter]** aus.
   1. Wählen Sie im **[!UICONTROL Filter \[Kaufumsatz\]]** die Option **[!UICONTROL Wertebereich]** und geben Sie die entsprechenden Werte ein. Beispiel: `1,000,000` - `2,000,000`. Wählen Sie **[!UICONTROL Übernehmen]** und **[!UICONTROL OK]** aus.
   1. Um die beiden Balkendiagramme in ein Doppelkombinationsdiagramm zu konvertieren, wählen Sie **[!UICONTROL SUM(Bestellungen)]** in **[!UICONTROL Zeilen]** und wählen Sie im Dropdown-Menü **[!UICONTROL Doppelachse]** aus. Die Balkendiagramme werden in ein Streudiagramm umgewandelt.
   1. So ändern Sie das Streudiagramm in ein Balkendiagramm:
      1. Wählen Sie **[!UICONTROL SUM(Purchases]** im Bereich **[!UICONTROL Marks]** und wählen Sie **[!UICONTROL Line]** aus dem Dropdown-Menü aus.
      1. Wählen Sie **[!UICONTROL SUM(Purchase Revenue)]** im Bereich **[!UICONTROL Marks]** und wählen Sie **[!UICONTROL Bar]** aus dem Dropdown-Menü aus.

   Ihr Tableau-Desktop sollte wie folgt aussehen.

   ![Tableau Desktop Graph](../assets/uc5-tableau-graph.png)

1. Wählen Sie **[!UICONTROL Duplizieren]** aus dem **[!UICONTROL Blatt 1]** Kontextmenü, um ein zweites Blatt zu erstellen.
1. Wählen Sie **[!UICONTROL Umbenennen]** aus dem Kontextmenü der Registerkarte **[!UICONTROL Blatt 1]**, um das Blatt in `Data` umzubenennen.
1. Wählen Sie **[!UICONTROL Umbenennen]** aus dem Kontextmenü der Registerkarte **[!UICONTROL Blatt 1 (2)]** aus, um das Blatt in `Graph` umzubenennen.
1. Stellen Sie sicher, dass **[!UICONTROL Daten]**-Blatt ausgewählt ist.
   1. Klicken Sie **[!UICONTROL oben]** auf „Anzeigen“ und wählen Sie **[!UICONTROL Texttabelle]** (Visualisierung oben links) aus, um den Inhalt der beiden Diagramme in eine Tabelle zu ändern.
   1. Um den Kaufumsatz in absteigender Reihenfolge zu bestellen, bewegen Sie den Mauszeiger über **[!UICONTROL Kaufumsatz]** in der Tabelle und wählen Sie ![SortOrderDown](/help/assets/icons/SortOrderDown.svg) aus.
   1. Wählen **[!UICONTROL Gesamte Ansicht]** aus dem **[!UICONTROL -]**-Menü aus.

   Ihr Tableau-Desktop sollte wie folgt aussehen.

   ![Tableau Desktop-Daten](../assets/uc5-tableau-data.png)

1. Wählen Sie **[!UICONTROL Schaltfläche]** Neues Dashboard) unten aus, um eine neue Ansicht **[!UICONTROL Dashboard 1]** zu erstellen. In der Ansicht **[!UICONTROL Dashboard 1]**:
   1. Ziehen Sie das Blatt **[!UICONTROL Graph]** aus dem **[!UICONTROL Blätter]**-Regal auf die Ansicht **[!UICONTROL Dashboard 1]** mit dem Titel *Blätter hier ablegen*.
   1. Ziehen Sie das **[!UICONTROL Daten]**-Blatt aus dem **[!UICONTROL Blätter]**-Regal unter das **[!UICONTROL Diagramm]**-Blatt auf die Ansicht **[!UICONTROL Dashboard 1]**.
   1. Wählen Sie das **[!UICONTROL Daten]**-Blatt in der Ansicht aus und ändern Sie **[!UICONTROL Gesamte Ansicht]** so **[!UICONTROL Breite festlegen]**.

   Ihre Ansicht **[!UICONTROL Dashboard 1]** sollte wie folgt aussehen.

   ![Tableau Desktop Dashboard 1](../assets/uc5-tableau-dashboard.png)



>[!TAB Looker]

1. Achten Sie in der **[!UICONTROL Explore]**-Oberfläche von Looker darauf, dass Sie über ein sauberes Setup verfügen. Wenn nicht, wählen Sie ![Einstellung](/help/assets/icons/Setting.svg) **[!UICONTROL Felder und Filter entfernen]**.
1. Wählen Sie **[!UICONTROL + Filter]** unter **[!UICONTROL Filter]** aus.
1. Im Dialogfeld **[!UICONTROL Filter hinzufügen]**:
   1. Wählen Sie **[!UICONTROL ‣ CC-Datenansicht]**
   1. Wählen Sie aus der Liste der Felder **[!UICONTROL ‣ DateRange]** und **[!UICONTROL DateRange]** aus.
      ![Looker-Filter](../assets/uc2-looker-filter.png)
1. Geben Sie den Filter **[!UICONTROL CC Datenansicht Datumsbereich]** als **[!UICONTROL liegt im Bereich]** **[!UICONTROL 2023/01/01]****[!UICONTROL bis (davor)]** **[!UICONTROL 2024/01/01]** an.
1. Wählen Sie **[!UICONTROL Abschnitt ‣CC-Datenansicht]** in der linken Leiste **[!UICONTROL Produktname]** aus.
1. Im Abschnitt **[!UICONTROL ‣ Benutzerdefinierte Felder]** in der linken Leiste:
   1. Wählen Sie **[!UICONTROL Benutzerdefinierte Kennzahl]** aus dem Dropdown-Menü **[!UICONTROL + Hinzufügen]** aus.
   1. Im Dialogfeld **[!UICONTROL Benutzerdefinierte Kennzahl erstellen]**:
      1. Wählen **[!UICONTROL im Dropdown]** Menü **[!UICONTROL Feld zur Messung]** die Option „Kaufumsatz“ aus.
      1. Wählen Sie **[!UICONTROL Summe]** aus **[!UICONTROL Dropdown-Menü Kennzahlentyp]** aus.
      1. Geben Sie einen benutzerdefinierten Feldnamen für „Name **[!UICONTROL ein]**. Beispiel: `Purchase Revenue`.
      1. Wählen Sie die **[!UICONTROL Felddetails]** aus.
      1. Wählen Sie **[!UICONTROL Dezimalstellen]** aus dem Dropdown-Menü **[!UICONTROL Format]** aus und stellen Sie sicher, dass `0` in **[!UICONTROL Dezimalstellen]** eingegeben wird.
         ![Benutzerdefiniertes Metrikfeld für Looker](../assets/uc5-looker-customfield.png)
      1. Wählen Sie **[!UICONTROL Speichern]** aus.
   1. Wählen Sie **[!UICONTROL Benutzerdefinierte Kennzahl]** erneut aus dem Dropdown-Menü **[!UICONTROL + Hinzufügen]** aus. Im Dialogfeld **[!UICONTROL Benutzerdefinierte Kennzahl erstellen]**:
      1. Wählen **[!UICONTROL aus]** Dropdown-Menü **[!UICONTROL Zu messendes Feld]** die Option „Bestellungen“ aus.
      1. Wählen Sie **[!UICONTROL Summe]** aus **[!UICONTROL Dropdown-Menü Kennzahlentyp]** aus.
      1. Geben Sie einen benutzerdefinierten Feldnamen für „Name **[!UICONTROL ein]**. Beispiel: `Sum of Purchases`.
      1. Wählen Sie die **[!UICONTROL Felddetails]** aus.
      1. Wählen Sie **[!UICONTROL Dezimalstellen]** aus dem Dropdown-Menü **[!UICONTROL Format]** aus und stellen Sie sicher, dass `0` in **[!UICONTROL Dezimalstellen]** eingegeben wird.
      1. Wählen Sie **[!UICONTROL Speichern]** aus.
   1. Beide Felder werden automatisch zur Datenansicht hinzugefügt.
1. Wählen Sie **[!UICONTROL + Filter]** aus, um einen weiteren **[!UICONTROL Filter]** hinzuzufügen und die Daten zu begrenzen.
1. Wählen **[!UICONTROL Dialogfeld „Filter hinzufügen]** die Option **[!UICONTROL ‣ Benutzerdefinierte Felder]** und dann **[!UICONTROL Umsatz]**.
1. Treffen Sie die entsprechenden Auswahlen und geben Sie die vorgeschlagenen Werte ein, sodass der Filter liest **[!UICONTROL zwischen einschließlich]** `1000000` **[!UICONTROL AND]** `2000000`.
1. Wählen Sie **[!UICONTROL Ausführen]** aus.
1. Wählen Sie **[!UICONTROL ‣ Visualisierung]** aus, um die Linienvisualisierung anzuzeigen.
1. Wählen Sie **[!UICONTROL Bearbeiten]** in **[!UICONTROL Visualisierung]** aus, um die Visualisierung zu aktualisieren. Im Popup-Dialogfeld:
   1. Wählen Sie die Registerkarte **[!UICONTROL Serie]** aus.
   1. Scrollen Sie nach unten, um **[!UICONTROL Bestellungen]** anzuzeigen, und ändern Sie **[!UICONTROL Typ]** in **[!UICONTROL Zeile]**.
   1. Wählen Sie die Registerkarte **[!UICONTROL Y]** aus.
   1. Ziehen Sie **[!UICONTROL Bestellungen]** aus dem Container **[!UICONTROL Links 1]** an die Stelle, an der er **[!UICONTROL *Reihe hierher ziehen, um eine neue linke Achse zu erstellen *]**. Diese Aktion erstellt einen**[!UICONTROL  Left 2 ]**-Container.
      ![Looker-Visualisierungskonfiguration](../assets/uc5-looker-visualization.png)
   1. Wählen Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg) neben **[!UICONTROL Bearbeiten]** aus, um das Popup-Dialogfeld auszublenden

Es sollte eine Visualisierung und eine Tabelle ähnlich wie unten dargestellt angezeigt werden.

![Looker-Ergebnis - täglicher Trend](../assets/uc5-looker-result.png)


>[!TAB Jupyter-Notebook]

1. Geben Sie die folgenden Anweisungen in eine neue Zelle ein.

   ```
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_name AS `Product Name`, SUM(purchase_revenue) AS `Purchase Revenue`, SUM(purchases) AS `Purchases` \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01' \
               GROUP BY 1 \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby('Product Name', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.barplot(x='Purchase Revenue', y='Product Name', data=df)
   plt.show()
   display(data)
   ```

1. Ausführen der Zelle. Es sollte eine ähnliche Ausgabe wie im folgenden Screenshot angezeigt werden.

   ![Jupyter Notebook-Ergebnisse](../assets/uc5-jupyter-results.png)


>[!TAB RStudio]

1. Geben Sie die folgenden Anweisungen zwischen ` ```{r} ` und ` ``` ` in einen neuen Block ein.

   ```R
   library(tidyr)
   
   ## Single dimension ranked
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2024-01-01") %>%
      group_by(product_name) %>%
      summarise(purchase_revenue = sum(purchase_revenue), purchases = sum(purchases)) %>%
      arrange(product_name, .by_group = FALSE)
   dfV <- df %>%
      head(5)
   ggplot(dfV, aes(x = purchase_revenue, y = product_name)) +
      geom_col(position = "dodge") +
      geom_text(aes(label = purchase_revenue), vjust = -0.5)
   print(df)
   ```

1. Führt den Block aus. Es sollte eine ähnliche Ausgabe wie im folgenden Screenshot angezeigt werden.

   ![RStudio Ergebnisse](../assets/uc5-rstudio-results.png)

>[!ENDTABS]

+++

