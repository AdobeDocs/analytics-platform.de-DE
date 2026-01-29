---
title: Beschränkungen
description: Beschränkt den Anwendungsfall für die BI-Erweiterung in verschiedenen BI-Tools in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 1%

---

# Beschränkungen


In diesem Anwendungsbeispiel möchten Sie einen Bericht über die fünf häufigsten Vorkommen von Produktnamen im Jahr 2023 erstellen.

+++ Customer Journey Analytics

Ein Beispiel **[!UICONTROL Limit]**-Bedienfeld für den Anwendungsfall:

![Bedienfeld &quot;Customer Journey Analytics-Limit“](../assets/cja-limit.png)

+++

+++ BI-Tools

>[!PREREQUISITES]
>
>Stellen Sie sicher, [&#x200B; Sie für das BI-Tool, für das Sie diesen Anwendungsfall ausprobieren möchten, (eine erfolgreiche Verbindung, Datenansichten auflisten &#x200B;](connect-and-validate.md) eine Datenansicht verwenden) validiert haben.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. Im Bereich **[!UICONTROL Daten]**:
   1. Wählen Sie **[!UICONTROL daterange]** aus.
   1. Wählen Sie **[!UICONTROL product_name]** aus.
   1. Wählen Sie **[!UICONTROL Summenvorfälle]** aus.

1. Im Bereich **[!UICONTROL Filter]**:
   1. Wählen Sie **[!UICONTROL daterange is (All)]** aus **[!UICONTROL Filter auf dieser visuellen]**.
   1. Wählen Sie **[!UICONTROL Relatives Datum]** als **[!UICONTROL Filtertyp]** aus.
   1. Definieren Sie den Filter für **[!UICONTROL Elemente anzeigen, wenn der Wert]**&#x200B;**[!UICONTROL in den letzten]**`1` **[!UICONTROL Kalenderjahren)]**.
   1. Wählen Sie **[!UICONTROL Filter anwenden]** aus.
   1. Wählen Sie **[!UICONTROL product_name is (All)]** aus **[!UICONTROL Filter auf dieser visuellen]**.
   1. Wählen Sie **[!UICONTROL Top N]** als **[!UICONTROL Filtertyp]**.
   1. Wählen Sie **[!UICONTROL Elemente anzeigen]** **[!UICONTROL Oben]** `5` **[!UICONTROL Nach Wert]**.
   1. Ziehen Sie **[!UICONTROL Summenvorfälle]** per Drag-and-Drop aus dem Bereich **[!UICONTROL Daten]** und legen Sie sie auf **[!UICONTROL Datenfelder hier hinzufügen]** ab.
   1. Wählen Sie **[!UICONTROL Filter anwenden]** aus.

1. Im Bereich Visualisierung :
   * Wählen Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg) aus, um den Datumsbereich aus den Spalten zu entfernen.

   Ihr Power BI-Desktop sollte wie folgt aussehen.

   ![Power BI-Desktop, der Datumsbereichsnamen zum Filtern verwendet](../assets/uc12-powerbi-final.png)

Die von Power BI Desktop mit der BI-Erweiterung ausgeführte Abfrage enthält eine `limit`, jedoch nicht die erwartete. Die Begrenzung auf die fünf häufigsten Vorkommen wird von Power BI Desktop mithilfe expliziter Ergebnisse für Produktnamen erzwungen.

```sql
select "_"."product_name",
    "_"."a0"
from 
(
    select "rows"."product_name" as "product_name",
        sum("rows"."occurrences") as "a0"
    from 
    (
        select "_"."daterangeName",
            "_"."daterange",
            "_"."filterId",
            "_"."filterName",
            "_"."timestamp",
            "_"."affiliate_name",
            "_"."affiliate_url",
            "_"."commerce.order.priceTotal",
            "_"."customer_city",
            "_"."customer_region",
            "_"."daterangeday",
            "_"."daterangefifteenminute",
            "_"."daterangefiveminute",
            "_"."daterangehour",
            "_"."daterangeminute",
            "_"."daterangemonth",
            "_"."daterangequarter",
            "_"."daterangesecond",
            "_"."daterangethirtyminute",
            "_"."daterangeweek",
            "_"."daterangeyear",
            "_"."hitdatetime",
            "_"."page_name",
            "_"."page_url",
            "_"."product_category",
            "_"."product_name",
            "_"."product_short_review",
            "_"."product_subCategory",
            "_"."referrer_url",
            "_"."search_engine",
            "_"."search_keywords",
            "_"."store_city",
            "_"."store_name",
            "_"."store_region",
            "_"."store_type",
            "_"."timepartdayofmonth",
            "_"."timepartdayofweek",
            "_"."timepartdayofyear",
            "_"."timeparthourofday",
            "_"."timepartminuteofhour",
            "_"."timepartmonthofyear",
            "_"."timepartquarterofyear",
            "_"."timepartweekofyear",
            "_"."cm_session_end_rate_defaultmetric",
            "_"."cm_session_person_defaultmetric",
            "_"."cm_session_start_rate_defaultmetric",
            "_"."cm_timespent_person_defaultmetric",
            "_"."cm_timespent_session_defaultmetric",
            "_"."cm_product_name_count_distinct",
            "_"."ad_views",
            "_"."adobe_sessionends",
            "_"."adobe_sessionstarts",
            "_"."adobe_timespent",
            "_"."exchange_buybacks",
            "_"."exchange_cost",
            "_"."exchange_purchases",
            "_"."exchange_revenue",
            "_"."occurrences",
            "_"."page_views",
            "_"."product_quantity",
            "_"."product_reviews",
            "_"."product_views",
            "_"."purchase_revenue",
            "_"."purchases",
            "_"."visitors",
            "_"."visits"
        from "public"."cc_data_view" "_"
        where (("_"."product_name" in ('Saltwater Monofilament Line', 'Pop-Up Beach Tent', 'Instant Pop-Up Tent', 'Envelop Sleeping Bag', 'Waterproof Tackle Bag')) and "_"."daterange" < date '2024-01-01') and "_"."daterange" >= date '2023-01-01'
    ) "rows"
    group by "product_name"
) "_"
where not "_"."a0" is null
limit 1000001
```

>[!TAB Tableau Desktop]

1. Wählen Sie unten **[!UICONTROL Registerkarte Blatt 1]** aus, um aus **[!UICONTROL Datenquelle]** zu wechseln. In der Ansicht **[!UICONTROL Blatt 1]**:
   1. Ziehen Sie **[!UICONTROL Daterange]**-Eintrag aus der Liste **[!UICONTROL Tabellen]** in die Ablage **[!UICONTROL Filter]**.
   1. Wählen Sie im Dialogfeld **[!UICONTROL Filterfeld \[Datumsbereich\]]** die Option **[!UICONTROL Datumsbereich]** und wählen Sie **[!UICONTROL Weiter >]**.
   1. Wählen Sie im Dialogfeld **[!UICONTROL Filter \[Daterange\]]** die Option **[!UICONTROL Relative Datumsangaben]**, **[!UICONTROL Jahre]** und **[!UICONTROL Vorherige Jahre]**. Wählen Sie **[!UICONTROL Übernehmen]** und **[!UICONTROL OK]** aus.
   1. Ziehen Sie **[!UICONTROL Produktname]** aus der Liste **[!UICONTROL Tabellen]** in **[!UICONTROL Zeilen]**.
   1. Ziehen Sie **[!UICONTROL Eintrag]** Vorfälle“ aus der Liste **[!UICONTROL Tabellen]** und legen Sie den Eintrag im Feld neben **[!UICONTROL Spalten]** ab. Der Wert ändert sich in **[!UICONTROL SUM(Occurrences)]**.
   1. Wählen Sie **[!UICONTROL Texttabelle]** unter **[!UICONTROL Anzeigen]** aus.
   1. Wählen **[!UICONTROL Breite anpassen]** aus dem Dropdown **[!UICONTROL Menü]** Anpassen“.
   1. Wählen Sie **[!UICONTROL Produktname]** in **[!UICONTROL Zeilen]** aus. Wählen **[!UICONTROL Filter]** aus dem Dropdown-Menü aus.
      1. Wählen **[!UICONTROL Dialogfeld \[Produktname\]]** die Registerkarte **[!UICONTROL Oben]** aus.
      1. Wählen Sie **[!UICONTROL Nach Feld:]** **[!UICONTROL Oben]** `5`**[!UICONTROL nach Vorfällen]**&#x200B;**[!UICONTROL Summe]**.
      1. Wählen Sie **[!UICONTROL Übernehmen]** und **[!UICONTROL OK]** aus.

         ![AlertRed](/help/assets/icons/AlertRed.svg) Sie bemerken, dass die Tabelle verschwindet. Die Auswahl der fünf häufigsten Produktnamen nach Vorkommen funktioniert **nicht** mit diesem Filter ordnungsgemäß.
      1. Wählen Sie den **[!UICONTROL Produktnamen]** in der **[!UICONTROL Filter]**-Bibliothek und wählen Sie im Dropdown-Menü **[!UICONTROL Entfernen]**. Die Tabelle wird erneut angezeigt.
   1. Wählen Sie **[!UICONTROL SUM(Vorfälle)]** im **[!UICONTROL Marks]**-Regal aus. Wählen **[!UICONTROL Filter]** aus dem Dropdown-Menü aus.
      1. Wählen Sie im **[!UICONTROL Filter \[Vorfälle\]]** die Option **[!UICONTROL Mindestens]** aus.
      1. Geben Sie `47.799` als Wert ein. Dieser Wert stellt sicher, dass nur die fünf wichtigsten Elemente in der Tabelle angezeigt werden. Wählen Sie **[!UICONTROL Übernehmen]** und **[!UICONTROL OK]** aus.

         Ihr Tableau-Desktop sollte wie folgt aussehen.

         ![Tableau Desktop Limits](../assets/uc12-tableau-final.png)

Wie oben gezeigt, schlägt diese von Tableau Desktop ausgeführte Abfrage beim Definieren eines Filters für die häufigsten 5 Vorkommnisse für Produktnamen fehl.

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok"
FROM "public"."cc_data_view" "cc_data_view"
  INNER JOIN (
  SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
    SUM("cc_data_view"."occurrences") AS "$__alias__0"
  FROM "public"."cc_data_view" "cc_data_view"
  GROUP BY 1
  ORDER BY 2 DESC,
    1 ASC
  LIMIT 5
) "t0" ON (CAST("cc_data_view"."product_name" AS TEXT) = "t0"."product_name")
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1
```

Die von Tableau Desktop beim Definieren eines Top-5-Filters auf Vorfälle ausgeführte Abfrage wird unten angezeigt. Das Limit ist in der Abfrage nicht sichtbar und wird Client-seitig angewendet.

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1
```

>[!TAB Looker]

1. Aktualisieren Sie Ihre Verbindung in der **[!UICONTROL Erkunden]**-Benutzeroberfläche von Looker. Wählen Sie ![Einstellung](/help/assets/icons/Setting.svg) **[!UICONTROL Cache löschen und aktualisieren]** aus.
1. Achten Sie in der **[!UICONTROL Explore]**-Oberfläche von Looker darauf, dass Sie über ein sauberes Setup verfügen. Wenn nicht, wählen Sie ![Einstellung](/help/assets/icons/Setting.svg) **[!UICONTROL Felder und Filter entfernen]**.
1. Wählen Sie **[!UICONTROL + Filter]** unter **[!UICONTROL Filter]** aus.
1. Im Dialogfeld **[!UICONTROL Filter hinzufügen]**:
   1. Wählen Sie **[!UICONTROL ‣ CC-Datenansicht]**
   1. Wählen Sie aus der Liste der Felder **[!UICONTROL ‣ DateRange]** und **[!UICONTROL DateRange]** aus.
      ![Looker-Filter](../assets/uc2-looker-filter.png)
1. Geben Sie den Filter **[!UICONTROL CC Datenansicht Datumsbereich]** als **[!UICONTROL liegt im Bereich]** **[!UICONTROL 2023/01/01]**&#x200B;**[!UICONTROL bis (davor)]** **[!UICONTROL 2024/01/01]** an.
1. Im Abschnitt **[!UICONTROL ‣ CC-Datenansicht]** in der linken Leiste:
   1. Wählen Sie **[!UICONTROL Produktname]** aus.
   1. Wählen Sie **[!UICONTROL Count]** unter **[!UICONTROL MEASURES]** in der linken Leiste (unten) aus.
1. Wählen Sie **[!UICONTROL ↓]** (**[!UICONTROL absteigend, Sortierreihenfolge: 1]**) in der Spalte **[!UICONTROL Kaufumsatz]** aus.
1. Wählen Sie **[!UICONTROL ↓]** (**[!UICONTROL absteigend, Sortierreihenfolge: 1]**) in der Spalte **[!UICONTROL Kaufumsatz]** aus.
1. Wählen Sie **[!UICONTROL Ausführen]** aus.
1. Wählen Sie **[!UICONTROL ‣ Visualisierung]** aus.

Es sollte eine Visualisierung und eine Tabelle ähnlich wie unten dargestellt angezeigt werden.

![Looker-Anzahl unterschiedlich](../assets/uc12-looker-result.png)

Die Abfrage, die von Looker mithilfe der BI-Erweiterung generiert wird, enthält `FETCH NEXT 5 ROWS ONLY`, was bedeutet, dass das Limit über Looker und die BI-Erweiterung ausgeführt wird.

```sql
-- Looker Query Context '{"user_id":6,"history_slug":"a8f3b1ebd5712413ca1ae695090f70db","instance_slug":"71d4667f0b76c0011463658f45c3f7a3"}' 
SELECT
    cc_data_view."product_name"  AS "cc_data_view.product_name",
    COUNT(*) AS "cc_data_view.count"
FROM
    "public"."cc_data_view" AS "cc_data_view"
WHERE ((( cc_data_view."daterange"  ) >= (DATE_TRUNC('day', DATE '2023-01-31')) AND ( cc_data_view."daterange"  ) < (DATE_TRUNC('day', DATE '2024-01-01'))))
GROUP BY
    1
ORDER BY
    2 DESC
FETCH NEXT 5 ROWS ONLY
```


>[!TAB Jupyter-Notebook]

1. Geben Sie die folgenden Anweisungen in eine neue Zelle ein.

   ```python
   data = %sql SELECT product_name AS `Product Name`, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
               GROUP BY 1 \
               ORDER BY `Events` DESC \
               LIMIT 5;
   display(data)
   ```

1. Ausführen der Zelle. Es sollte eine ähnliche Ausgabe wie im folgenden Screenshot angezeigt werden.

   ![Jupyter Notebook-Ergebnisse](../assets/uc12-jupyter-results.png)

Die Abfrage wird von der BI-Erweiterung ausgeführt, wie in Jupyter Notebook definiert.

>[!TAB RStudio]

1. Geben Sie die folgenden Anweisungen zwischen ` ` ``{r} ` und ` `` ` ` in einen neuen Block ein.

   ```R
   ## Dimension 1 Limited
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2024-01-01") %>%
      group_by(product_name) %>%
      count() %>%
      arrange(desc(n), .by_group = FALSE) %>%
      head(5)
   print(df)
   ```

1. Führt den Block aus. Es sollte eine ähnliche Ausgabe wie im folgenden Screenshot angezeigt werden.

   ![RStudio Ergebnisse](../assets/uc12-rstudio-results.png)

Die Abfrage, die von RStudio mithilfe der BI-Erweiterung generiert wird, enthält `LIMIT 5`, was bedeutet, dass die Beschränkung über RStudio und die BI-Erweiterung angewendet wird.

```sql
SELECT "product_name", COUNT(*) AS "n"
FROM (
  SELECT "cc_data_view".*
  FROM "cc_data_view"
  WHERE ("daterange" >= '2023-01-01' AND "daterange" < '2024-01-01')
) AS "q01"
GROUP BY "product_name"
ORDER BY "n" DESC
LIMIT 5
```

>[!ENDTABS]

+++
