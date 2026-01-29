---
title: Verwenden von Datumsbereichsnamen zum Filtern
description: Verwenden Sie Datumsbereichsnamen, um den Anwendungsfall für die BI-Erweiterung in verschiedenen BI-Tools in Customer Journey Analytics zu filtern.
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 1%

---

# Verwenden von Datumsbereichsnamen zum Filtern

In diesem Anwendungsfall möchten Sie einen Datumsbereich verwenden, den Sie in Customer Journey Analytics definiert haben, um die Vorfälle (Ereignisse) des letzten Jahres zu filtern und darüber zu berichten.

+++ Customer Journey Analytics

Um Berichte in einem Datumsbereich zu erstellen, richten Sie in Customer Journey Analytics einen Datumsbereich mit dem **&#x200B;**&#x200B;Titel`Last Year 2023` ein.

![Customer Journey Analytics Verwenden Sie Datumsbereichsnamen, um zu filtern](../assets/cja-daterange.png)

Anschließend können Sie diesen Datumsbereich in einem Beispiel im Bedienfeld **[!UICONTROL Verwenden von Datumsbereichsnamen zum Filtern]** für den Anwendungsfall verwenden:

![Unterschiedliche Customer Journey Analytics-Zählungswerte](../assets/cja-using-date-range-filter-names-to-filter.png)

Beachten Sie, dass der in der Freiformtabellen-Visualisierung definierte Datumsbereich den auf das Bedienfeld angewendeten Datumsbereich überschreibt.

+++

+++ BI-Tools

>[!PREREQUISITES]
>
>Stellen Sie sicher, [&#x200B; Sie für das BI-Tool, für das Sie diesen Anwendungsfall ausprobieren möchten, (eine erfolgreiche Verbindung, Datenansichten auflisten &#x200B;](connect-and-validate.md) eine Datenansicht verwenden) validiert haben.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. Im Bereich **[!UICONTROL Daten]**:
   1. Wählen Sie **[!UICONTROL daterangemonth]** aus.
   1. Wählen Sie **[!UICONTROL daterangeName]** aus.
   1. Wählen Sie **[!UICONTROL Summenvorfälle]** aus.

   Es wird eine Visualisierung mit **[!UICONTROL Fehler beim Abrufen von Daten für dieses visuelle Element]** angezeigt.

1. Im Bereich **[!UICONTROL Filter]**:

   1. Wählen Sie **[!UICONTROL daterangeName is (All)]** unter **[!UICONTROL Filter auf diesem visuellen Element]** aus.
   1. Wählen Sie **[!UICONTROL Standardfilter]** als **[!UICONTROL Filtertyp]**.
   1. Wählen Sie unter **[!UICONTROL Feld]** die Option **[!UICONTROL Letztes Jahr 2023]** aus. Dies ist der Name Ihres in Customer Journey Analytics definierten Datumsbereichs.
   1. Wählen Sie ![CrossSize](/help/assets/icons/CrossSize75.svg) aus, um **[!UICONTROL daterangeName]** aus **[!UICONTROL Columns]** zu entfernen.

   Die Tabelle wird mit dem angewendeten Filter **[!UICONTROL daterangeName]** aktualisiert. Ihr Power BI-Desktop sollte wie folgt aussehen.

   ![Power BI-Desktop, der Datumsbereichsnamen zum Filtern verwendet](../assets/uc8-powerbi-final.png)

>[!TAB Tableau Desktop]

1. Wählen Sie unten **[!UICONTROL Registerkarte Blatt 1]** aus, um aus **[!UICONTROL Datenquelle]** zu wechseln. In der Ansicht **[!UICONTROL Blatt 1]**:
   1. Ziehen Sie den Eintrag **[!UICONTROL Daterange Name]** aus der Liste **[!UICONTROL Tabellen]** in die Ablage **[!UICONTROL Filter]**.
   1. Stellen Sie im Dialogfeld **[!UICONTROL Filter \[Daterange-Name\]]** sicher, **[!UICONTROL Aus Liste auswählen]** ausgewählt ist, und wählen Sie **[!UICONTROL Letztes Jahr 2023]** aus der Liste aus. Wählen Sie **[!UICONTROL Übernehmen]** und **[!UICONTROL OK]** aus.
   1. Ziehen Sie **[!UICONTROL Daterangemonth]**-Eintrag aus der Liste **[!UICONTROL Tabellen]** und legen Sie den Eintrag im Feld neben **[!UICONTROL Zeilen]** ab. Wählen Sie **[!UICONTROL DateMonth]** und wählen Sie **[!UICONTROL Month]**. Der Wert ändert sich in **[!UICONTROL MONTH(daterangemonth)]**.
   1. Ziehen Sie **[!UICONTROL Eintrag]** Vorfälle“ aus der Liste **[!UICONTROL Tabellen]** und legen Sie den Eintrag im Feld neben **[!UICONTROL Spalten]** ab. Der Wert ändert sich in **[!UICONTROL SUM(Occurrences)]**.
   1. Wählen Sie **[!UICONTROL Texttabelle]** unter **[!UICONTROL Anzeigen]** aus.
   1. Wählen Sie **[!UICONTROL Zeilen und Spalten austauschen]** in der Symbolleiste aus.
   1. Wählen **[!UICONTROL Breite anpassen]** aus dem Dropdown **[!UICONTROL Menü]** Anpassen“.

      Ihr Tableau-Desktop sollte wie folgt aussehen.

      ![Tableau Desktop-Filter mit mehreren Dimension-Rankings](../assets/uc8-tableau-final.png)

>[!TAB Looker]

1. Achten Sie in der **[!UICONTROL Explore]**-Oberfläche von Looker darauf, dass Sie über ein sauberes Setup verfügen. Wenn nicht, wählen Sie ![Einstellung](/help/assets/icons/Setting.svg) **[!UICONTROL Felder und Filter entfernen]**.
1. Wählen Sie **[!UICONTROL + Filter]** unter **[!UICONTROL Filter]** aus.
1. Im Dialogfeld **[!UICONTROL Filter hinzufügen]**:
   1. Wählen Sie **[!UICONTROL ‣ CC-Datenansicht]**
   1. Wählen Sie aus der Liste der Felder **[!UICONTROL ‣ Datumsbereichsname]** aus.
1. Geben Sie den Filter **[!UICONTROL Cc-Datenansicht - Datumsbereichsname]** wie **&#x200B;**&#x200B;an und wählen Sie **[!UICONTROL Letztes Jahr 2023]** aus der Werteliste aus.
1. Im Abschnitt **[!UICONTROL ‣ CC-Datenansicht]** in der linken Leiste:
   1. Wählen **[!UICONTROL daterange month]**, dann **[!UICONTROL month]**.
   1. Wählen Sie **[!UICONTROL Count]** unter **[!UICONTROL MEASURES]** in der linken Leiste (unten) aus.
1. Wählen Sie **[!UICONTROL Ausführen]** aus.
1. Wählen Sie **[!UICONTROL ‣ Visualisierung]** aus.

Es sollte eine Visualisierung und eine Tabelle ähnlich wie unten dargestellt angezeigt werden.

![Looker-Anzahl unterschiedlich](../assets/uc8-looker-result.png)


>[!TAB Jupyter-Notebook]

1. Geben Sie die folgenden Anweisungen in eine neue Zelle ein.

   ```python
   data = %sql SELECT daterangeName FROM cc_data_view;
   style = {'description_width': 'initial'}
   daterange_name = widgets.Dropdown(
      options=[d for d, in data],
      description='Date Range Name:',
      style=style
   )
   display(daterange_name)
   ```

1. Ausführen der Zelle. Es sollte eine ähnliche Ausgabe wie im folgenden Screenshot angezeigt werden.

   ![Jupyter Notebook-Ergebnisse](../assets/uc8-jupyter-input.png)

1. Wählen **[!UICONTROL Fischereierzeugnisse]** aus dem Dropdown-Menü aus.

1. Geben Sie die folgenden Anweisungen in eine neue Zelle ein.

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT daterangemonth AS Month, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterangeName = '{daterange_name.value}' \
               GROUP BY 1 \
               ORDER BY Month ASC
   df = data.DataFrame()
   df = df.groupby('Month', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.lineplot(x='Month', y='Events', data=df)
   plt.show()
   display(data)
   ```

1. Ausführen der Zelle. Es sollte eine ähnliche Ausgabe wie im folgenden Screenshot angezeigt werden.

   ![Jupyter Notebook-Ergebnisse](../assets/uc8-jupyter-results.png)


>[!TAB RStudio]

1. Geben Sie die folgenden Anweisungen zwischen ` ` ``{r} ` und ` `` ` ` in einen neuen Block ein. Stellen Sie sicher, dass Sie den entsprechenden Datumsbereichsnamen verwenden. Zum Beispiel `Last Year 2023`.

   ```R
   ## Monthly Events for Last Year
   df <- dv %>%
      filter(daterangeName == "Last Year 2023") %>%
      group_by(daterangemonth) %>%
      count() %>%
      arrange(daterangemonth, .by_group = FALSE)
   ggplot(df, aes(x = daterangemonth, y = n)) +
      geom_line(color = "#69b3a2") +
      ylab("Events") +
      xlab("Hour")
   print(df)
   ```

1. Führt den Block aus. Es sollte eine ähnliche Ausgabe wie im folgenden Screenshot angezeigt werden.

   ![RStudio Ergebnisse](../assets/uc8-rstudio-results.png)

>[!ENDTABS]

+++

