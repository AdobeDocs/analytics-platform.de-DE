---
title: SQL-Connector
description: Erfahren Sie, wie Sie Abfrage-Service, Power BI und/oder Tableau verwenden können, um mithilfe des SQL-Connectors auf Datenansichten zuzugreifen.
solution: Customer Journey Analytics
feature: SQL Connector
hide: true
hidefromtoc: true
exl-id: 1827a637-6c0f-43f2-862a-928089340d30
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: ht
source-wordcount: '2789'
ht-degree: 100%

---

# SQL-Connector

{{release-limited-testing}}

{{select-package}}

Der [!DNL Customer Journey Analytics SQL Connector] ermöglicht SQL-Zugriff auf [Datenansichten](./data-views.md), die Sie in Customer Journey Analytics definiert haben. Ihre Dateningenieurinnen und -ingenieure sowie Ihre Datenanalytikerinnen und -analytiker sind möglicherweise besser mit Power BI, Tableau oder anderen Business Intelligence- und Visualisierungs-Tools (im Folgenden „BI-Tools“ genannt) vertraut. Sie können jetzt Berichte und Dashboards basierend auf denselben Datenansichten erstellen, die Benutzerinnen und Benutzer von Customer Journey Analytics beim Erstellen ihrer Analysis Workspace-Projekte verwenden.

Der [Abfrage-Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=de) von Adobe Experience Platform ist die SQL-Schnittstelle zu Daten, die im Data Lake von Experience Platform verfügbar sind. Wenn der [!DNL Customer Journey Analytics SQL Connector] aktiviert ist, wird die Funktionalität von [!DNL Query Service] erweitert, damit Ihre Datenansichten von Customer Journey Analytics als Tabellen oder Ansichten in einer [!DNL Query Service]-Sitzung zu sehen sind. Daher profitieren Business-Intelligence-Tools, die [!DNL Query Service] als Ihre PostgresSQL-Schnittstelle verwenden, nahtlos von dieser erweiterten Funktion.

Die wichtigsten Vorteile sind:

- Es ist nicht erforderlich, eine äquivalente Darstellung von Datenansichten aus Customer Journey Analytics im BI-Tool selbst zu erstellen. <br/>Siehe [Datenansicht](data-views.md) für weitere Informationen zur Funktionalität von Datenansichten, um zu verstehen, was neu erstellt werden muss.<br/>

- Mehr Konsistenz bei Reporting und Analyse zwischen BI-Tools und Customer Journey Analytics.

- Kombinieren Sie Customer Journey Analytics-Daten mit anderen Datenquellen, die bereits in BI-Tools verfügbar sind.

## Voraussetzungen

Um diese Funktion verwenden zu können, müssen Sie:

<!---   Enable the [!UICONTROL Customer Journey Analytics SQL Connector] in your Experience Platform organization. -->

- die Funktionalität für die relevanten Produktprofile, Benutzergruppen und/oder einzelnen Benutzenden konfigurieren.<br/>
Benutzende müssen Zugriff haben auf:
   - den Abfrage-Service von Experience Platform,
   - Workspace-Projekte von Customer Journey Analytics und
   - Datenansichten von Customer Journey Analytics, die sie verwenden möchten.

- Verwenden Sie ein Ablaufdatum für nicht ablaufende Anmeldeinformationen, um BI-Tools mit dem SQL-Connector von Customer Journey Analytics zu verbinden. Das [Handbuch zu Anmeldeinformationen](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=de) enthält weitere Informationen zum Festlegen ablaufender oder nicht ablaufender Anmeldeinformationen.

Weitere Informationen sind im Abschnitt „Verwaltung von Customer Journey Analytics“ unter [Zugriffssteuerung](../admin/cja-access-control.md) zu finden.


## Nutzung

Um die Funktion [!DNL Customer Journey Analytics SQL Connector] zu verwenden, können Sie SQL entweder direkt verwenden oder das Drag-and-Drop-Erlebnis verwenden, das im jeweiligen BI-Tool verfügbar ist.

### SQL

Sie können die Funktion direkt in SQL-Anweisungen verwenden, indem Sie entweder den Abfrageeditor oder einen standardmäßigen Client der Befehlszeilenschnittstelle (CLI) von Postgres verwenden.

+++ Abfrageeditor

In der Experience Platform-Benutzeroberfläche:

1. Wählen Sie **[!UICONTROL ** Abfragen **]** unter **[!UICONTROL ** DATEN-MANAGEMENT **]** in der linken Leiste aus.

2. Wählen Sie ![Abfrage erstellen](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Abfrage erstellen **]** aus.

3. Um die Abfrage auszuführen, geben Sie Ihre SQL-Anweisung ein und klicken Sie auf die Schaltfläche ![Wiedergabe](assets/Smock_Play_18_N.svg) (oder drücken Sie UMSCHALT + EINGABETASTE).

+++


+++ PostgresSQL-CLI

1. Suchen Sie in der Benutzeroberfläche von Experience Platform nach Ihren PostgresSQL-Anmeldeinformationen und kopieren Sie sie:

   1. Wählen Sie **[!UICONTROL ** Abfragen **]** aus der linken Leiste (unter **[!UICONTROL ** DATEN-MANAGEMENT **]**) aus.

   2. Wählen Sie **[!UICONTROL ** Anmeldeinformationen **]** aus der oberen Leiste aus.

   3. Um die Verbindungszeichenfolge zu kopieren, verwenden Sie ![Kopieren](assets/Smock_Copy_18_N.svg) im Abschnitt **[!UICONTROL ** PSQL-Befehle **]**.

2. Öffnen Sie Ihre PostgresSQL-CLI.

3. Um sich anzumelden und Ihre Abfragen auszuführen, fügen Sie die Verbindungszeichenfolge in die PostgresSQL-CLI ein.

+++

Siehe [Anleitung zur Benutzeroberfläche des Abfrageeditors](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=de) für weitere Informationen.


### BI-Tools

Derzeit wird der SQL-Connector von Customer Journey Analytics nur für Power BI und Tableau unterstützt und getestet. Andere BI-Tools, die die PSQL-Oberfläche verwenden, funktionieren möglicherweise ebenfalls, werden aber noch nicht offiziell unterstützt.

+++ Power BI

1. Suchen Sie in der Benutzeroberfläche von Adobe Experience Platform nach den Details Ihrer PostgresSQL-Anmeldeinformationen.

   1. Wählen Sie **[!UICONTROL ** Abfragen **]** aus der linken Leiste (unter **[!UICONTROL ** DATEN-MANAGEMENT **]**) aus.

   2. Wählen Sie **[!UICONTROL ** Anmeldeinformationen **]** aus der oberen Leiste aus.

   3. Verwenden Sie ![Kopieren](assets/Smock_Copy_18_N.svg), um jeden Parameter der Postgres-Anmeldeinformationen ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Datenbank], [!UICONTROL Benutzername] und andere) zu kopieren, wenn sie in Power BI benötigt werden.

2. In Power BI:

   1. Wählen Sie im Hauptfenster **[!UICONTROL ** Daten abrufen **]** aus der oberen Symbolleiste aus.

   2. Wählen Sie **[!UICONTROL ** Mehr…**]** in der linken Leiste aus.

   3. Suchen Sie im Bildschirm **Daten abrufen** nach `PostgresSQL` und wählen Sie die **[!UICONTROL ** PostgresSQL-Datenbank **]** aus der Liste aus.

   4. Im Dialogfeld **[!UICONTROL ** PostgresSQL-Datenbank **]**:

      1. Fügen Sie den Parameter **[!UICONTROL ** Host **]** aus den [!UICONTROL Anmeldeinformationen] von Experience Platform-Abfragen in das Textfeld **[!UICONTROL ** Server **]** ein.

      2. Fügen Sie den Parameter **[!UICONTROL ** Datenbank **]** aus den [!UICONTROL Anmeldedaten] von Experience Platform-Abfragen in das Textfeld **[!UICONTROL ** Datenbank **]** ein.

         Fügen Sie `?FLATTEN` zum Parameter **[!UICONTROL ** Datenbank **]** hinzu, damit er sich beispielsweise liest wie `prod:cja?FLATTEN`. Weitere Informationen finden Sie unter [Reduzieren verschachtelter Datenstrukturen für die Verwendung mit BI-Tools von Drittanbietern](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=de).

      3. Wenn Sie zur Wahl des **[!UICONTROL ** Datenkonnektivitätsmodus **]** aufgefordert werden, wählen Sie **[!UICONTROL ** DirectQuery **]** aus, um sicherzustellen, dass die Datenstrukturen ordnungsgemäß reduziert werden.

      4. Sie werden aufgefordert, **[!UICONTROL ** Benutzername **]** und **[!UICONTROL ** Passwort **]** einzugeben. Verwenden Sie die entsprechenden Parameter aus den [!UICONTROL Anmeldeinformationen] von Experience Platform-Abfragen.


   5. Nach erfolgreicher Anmeldung sehen Sie die Datenansichtstabellen von Customer Journey Analytics im **[!UICONTROL ** Navigator **]** von Power BI. Datenansichtstabellen werden anhand von `dv_` in ihrem Namen identifiziert.


   6. Wählen Sie die Datenansichtstabellen aus, die Sie verwenden möchten, und wählen Sie dann **[!UICONTROL ** Laden **]** aus.

   Alle Dimensionen und Metriken, die mit einer oder mehreren ausgewählten Tabellen verknüpft sind, werden im rechten Bereich angezeigt und können in Ihren Visualisierungen verwendet werden.

   Weitere Informationen sind unter [Verbinden von Power BI mit dem Abfrage-Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=de) zu finden.

+++

+++Tableau

1. Suchen Sie in der Benutzeroberfläche von Experience Platform nach den Details Ihrer PostgresSQL-Anmeldedaten.

   1. Wählen Sie **[!UICONTROL ** Abfragen **]** aus der linken Leiste (unter **[!UICONTROL ** DATEN-MANAGEMENT **]**) aus.

   2. Wählen Sie **[!UICONTROL ** Anmeldeinformationen **]** aus der oberen Leiste aus.

   3. Verwenden Sie ![Kopieren](assets/Smock_Copy_18_N.svg), um jeden Parameter der Postgres-Anmeldedaten ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Datenbank], [!UICONTROL Benutzername] und andere) bei Bedarf in Tableau zu kopieren.

2. In Tableau:

   1. Wählen Sie **[!UICONTROL ** Mehr **]** aus **[!UICONTROL ** Zu einem Server **]** in der linken Leiste aus.

   2. Wählen Sie **[!UICONTROL ** PostgresSQL **]** aus der Liste aus.

   3. Im Dialogfeld [!UICONTROL PostgresSQL]:

      1. Fügen Sie den Parameter **[!UICONTROL ** Host **]** aus den [!UICONTROL Anmeldeinformationen] von Experience Platform-Abfragen in das Textfeld **[!UICONTROL ** Server **]** ein.

      2. Fügen Sie den Parameter **[!UICONTROL ** Port **]** aus den [!UICONTROL Anmeldeinformationen] von Experience Platform-Abfragen in das Textfeld **[!UICONTROL ** Port **]** ein.

      3. Fügen Sie den Parameter **[!UICONTROL ** Datenbank **]** aus den [!UICONTROL Anmeldeinformationen] von Experience Platform-Abfragen in das Textfeld **[!UICONTROL ** Datenbank **]** ein.

         Fügen Sie `%3FFLATTEN` zum Parameter **[!UICONTROL ** Datenbank **]** hinzu, damit er sich beispielsweise liest wie `prod:cja%3FFLATTEN`. Weitere Informationen finden Sie unter [Reduzieren verschachtelter Datenstrukturen für die Verwendung mit BI-Tools von Drittanbietern](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=de).

      4. Wählen Sie **[!UICONTROL ** Benutzername und Passwort **]** aus der Liste **[!UICONTROL ** Authentifizierung **]** aus.

      5. Fügen Sie den Parameter **[!UICONTROL ** Benutzername **]** aus den [!UICONTROL Anmeldeinformationen] von Experience Platform-Abfragen in das Textfeld **[!UICONTROL ** Benutzername **]** ein.

      6. Fügen Sie den Parameter **[!UICONTROL ** Passwort **]** aus den [!UICONTROL Anmeldeinformationen] von Experience Platform-Abfragen in das Textfeld **[!UICONTROL ** Passwort **]** ein.

      7. Wählen Sie **[!UICONTROL ** Anmelden **]** aus.

   4. Datenansichten von Customer Journey Analytics werden als Tabellen in der **[!UICONTROL ** Tabellenliste **]** angezeigt. Datenansichtstabellen erhalten das Präfix `dv_`.

   5. Ziehen Sie die Tabellen, die Sie verwenden möchten, auf die Arbeitsfläche.

   Sie können jetzt mit den Daten aus den Datenansichtstabellen arbeiten, um Ihre Berichte und Visualisierungen zu erstellen.

   Weitere Informationen erhalten Sie unter [Verbinden von Tableau mit dem Abfrage-Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=de).

+++

Siehe [Verbinden von Clients mit dem Abfrage-Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=de), um einen Überblick und weitere Informationen über die verschiedenen verfügbaren Tools zu erhalten.

## Funktionalität

Standardmäßig wird für Ihre Datenansichten ein tabellensicherer Name aus ihrem Anzeigenamen generiert. Beispielsweise hat die Datenansicht mit dem Namen [!UICONTROL Meine Web-Daten] den Anzeigenamen `dv_my_web_data`.

Wenn Sie die Datenansichts-IDs als Tabellennamen verwenden möchten, können Sie beim Verbinden die optionale Einstellung für `CJA_USE_IDS` auf Ihren Datenbanknamen festlegen. Zum Beispiel zeigt `prod:all?CJA_USE_IDS` Ihre Datenansichten mit Namen wie `dv_ABC123` an.

### Data Governance

Einstellungen in Bezug auf die Data Governance in Customer Journey Analytics werden von Adobe Experience Platform übernommen. Die Integration zwischen Customer Journey Analytics und Adobe Experience Platform Data Governance ermöglicht die Kennzeichnung sensibler Daten von Customer Journey Analytics und die Durchsetzung von Datenschutzrichtlinien.

Datenschutzbeschriftungen und -richtlinien, die für von Experience Platform genutzte Datensätze erstellt wurden, können im Datenansichts-Workflow von Customer Journey Analytics angezeigt werden. Daher zeigen Daten, die mit dem SQL-Connector von Customer Journey Analytics abgefragt wurden, die entsprechenden Warnungen oder Fehler an, wenn sie nicht den definierten Datenschutzbeschriftungen und Richtlinien entsprechen.

### Auflisten von Datenansichten

In der standardmäßigen PostgresSQL-CLI können Sie Ihre Ansichten mithilfe von `\dv` auf folgende Arten anzeigen:

```sql
prod:all=> \dv
                                     List of relations
 Schema |                              Name                              | Type |  Owner             
--------+----------------------------------------------------------------+------+----------
 public | dv_adobe_analytics_spa                                         | view | postgres
 public | dv_adobe_analytics_spa_cja_adobe_users_only_                   | view | postgres
 public | dv_adobe_analytics_spa_cja_customers_only_                     | view | postgres
 public | dv_adobe_analytics_spa_core_aa_only_                           | view | postgres
 public | dv_adobe_analytics_spa_trad_aa_customers_only_                 | view | postgres
 public | dv_cja_audit_logs                                              | view | postgres
 public | dv_cja_connections_ui_prod_analytics_format_                   | view | postgres
 public | dv_cja_for_adobe_spark_usage                                   | view | postgres
 public | dv_cja_new_dimesnions                                          | view | postgres
 public | dv_cja_test_dimensions                                         | view | postgres
 public | dv_cja_usage_account_based_customers_only_                     | view | postgres
 public | dv_combined_trad_aa_apps                                       | view | postgres
 public | dv_customer_journey_analytics_sc_demo_users_                   | view | postgres
```

### Verschachtelt oder reduziert

Standardmäßig verwendet das Schema Ihrer Datenansichten verschachtelte Strukturen wie die ursprünglichen XDM-Schemata. Die Integration unterstützt auch die Option `FLATTEN`. Mit dieser Option können Sie erzwingen, dass das Schema für die Datenansichten (und jede andere Tabelle in der Sitzung) reduziert wird. Die Reduzierung ermöglicht eine einfachere Verwendung in BI-Tools, die keine strukturierten Schemata unterstützen. Weitere Informationen finden Sie unter [Arbeiten mit verschachtelten Datenstrukturen im Abfrage-Service](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=de).

### Unterstützte SQL

Die vollständige Referenz dazu, welcher SQL-Typ unterstützt wird, finden Sie unter [SQL-Referenz für den Abfrage-Service](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=de).

Beispiele für SQL, die Sie verwenden können, finden Sie in der folgenden Tabelle.

+++ Beispiele

| Muster | Beispiel |
|---|---|
| Schema-Erkennung | <pre>SELECT * FROM dv1 WHERE 1=0</pre> |
| Mit Ranking/Aufschlüsselung | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  filterId = &#39;12345&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  AND (dim2 = &#39;A&#39; OR dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>GROUP BY dim1</pre> |
| HAVING-Klausel | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>HAVING m1 > 100</pre> |
| Eindeutige, obere <br/>Dimensionswerte | <pre>SELECT DISTINCT dim1 FROM dv1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` >= &#39;2022-01-01&#39; AND \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>ORDER BY SUM(metric1)<br/>LIMIT 15</pre> |
| Metriksummen | <pre>SELECT SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</pre> |
| Mehrere Dimensionen<br/>Aufschlüsselungen<br/>und obere eindeutige Werte | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 1, 2<br/>ORDER BY 1, 2</pre><pre>SELECT DISTINCT dim1, dim2<br/>FROM dv1</pre> |
| Unterauswahl:<br/>Zusätzliches Ergebnis<br/>Filterung | <pre>SELECT dim1, m1<br/>FROM (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</br>  GROUP BY dim1<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| Unterauswahl:<br/>Verbinden mit<br/>Datensatz, der nicht vorhanden ist in<br/>Customer Journey Analytics | <pre>SELECT b.key, a.dim1, a.m1<br/>FROM (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim1<br/>) a<br/>LEFT JOIN lookups b ON a.dim1 = b.key</pre> |
| Unterauswahl:<br/>Abfrage über<br/>Datenansicht | <pre>SELECT key, SUM(m1) AS total<br/>FROM (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim1<br/><br/>  UNION<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  FROM dv2<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim2<br/>GROUP BY key<br/>ORDER BY total</pre> |
| Unterauswahl: <br/>Geschichtete Quelle, <br/>Filterung <br/>und Aggregation | Geschichtet, mit den Unterauswahlen:<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>FROM (<br/>  SELECT \_.dim1,\_.m1<br/>  FROM (<br/>    SELECT \* FROM dv1<br/>    WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  ) \_<br/>  WHERE \_.dim1 in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) rows<br/>GROUP BY 1<br/>ORDER BY total</pre><br/>Ebenen, die CTE WITH verwenden:<br/><pre>WITH rows AS (<br/>  WITH \_ AS (<br/>    SELECT * FROM data_ares<br/>    WHERE \`timestamp\` BETWEEN &#39;2021-01-01&#39; AND &#39;2021-02-01&#39;<br/>  )<br/>  SELECT _.item, _.units FROM _<br/>  WHERE _.item IS NOT NULL<br/>)<br/>SELECT rows.item, SUM(rows.units) AS units<br/>FROM rows WHERE rows.item in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>GROUP BY rows.item</pre> |
| Wählt aus, wo die<br/>Metriken vor<br/> den Dimensionen erscheinen oder mit<br/>den Dimensionen gemischt werden | <pre>SELECT SUM(metric1) AS m1, dim1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 2</pre> |

{style="table-layout:auto"}

+++

### Dimensionen

Sie können jede der Dimensionen auswählen, die standardmäßig verfügbar oder in der Datenansicht definiert sind. Sie wählen eine Dimension anhand ihrer ID aus.

### Metriken

Folgende Metriken stehen zur Auswahl:

- Metriken, die standardmäßig verfügbar sind,

- Metriken, die in der Datenansicht definiert wurden,

- berechnete Metriken, die mit der Datenansicht kompatibel sind, auf die die Benutzerin bzw. der Benutzer Zugriff hat.

Sie wählen eine Metrik anhand ihrer ID aus, die in einen `SUM(metric)`-Ausdruck eingeschlossen ist, wie Sie es mit jeder SQL-Quelle tun würden.

Sie können:

- `SELECT COUNT(*)` oder `COUNT(1)` verwenden, um die Metrik „Vorfälle“ zu erhalten.

- `SELECT COUNT(DISTINCT dimension)` oder `SELECT APPROX_COUNT_DISTINCT(dimension)` verwenden, um die ungefähren eindeutigen Werte einer Dimension zu zählen. Details finden Sie unter [Zählen von eindeutigen Werten](#counting-distincts).

- [Inline-Berechnungen](#inline-calculations) verwenden, um Metriken spontan zu kombinieren und/oder mathematisch zu verarbeiten.

#### Zählen von eindeutigen Werten

Aufgrund der zugrunde liegenden Funktionsweise von Customer Journey Analytics ist die einzige Dimension, für die Sie die Anzahl der eindeutigen Werte genau bestimmen können, die Dimension `adobe_personid`. Die folgenden SQL-Ausdrücke `SELECT COUNT(DISTINCT adobe_personid)` oder `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` geben den Wert der Standardmetrik „Personen“ zurück, die der Anzahl der eindeutigen Personen entspricht. Bei anderen Dimensionen wird eine ungefähre Zählung der eindeutigen Personen zurückgegeben.

#### Bedingte Metriken

Sie können die Klausel `IF` oder `CASE` in der Funktion `SUM` oder `COUNT` einbetten, um eine zusätzliche Filterung hinzuzufügen, die spezifisch für eine ausgewählte Metrik ist. Das Hinzufügen dieser Klauseln ähnelt dem Anwenden eines Filters auf eine Metrikspalte in einer Workspace-Berichtstabelle.

Beispiele:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### Inline-Berechnungen

Zusätzlich zu Metrikausdrücken können Sie `SELECT` anwenden, anstatt die Mathematik in einer berechneten Metrik zu definieren. In der folgenden Tabelle ist aufgeführt, welche Arten von Ausdrücken unterstützt werden.

| Operator oder Funktion | Details |
|---|---|
| `+`, `-`, `*`, `/`, und `%` | Addieren, subtrahieren, multiplizieren, dividieren und modulo/Rest |
| `-X` oder `+X` | Ändern des Zeichens oder einer Metrik, wobei X der Metrikausdruck ist |
| `PI()` | Konstante π |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH` und `TANH` | Unäre mathematische Funktionen |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Binäre mathematische Funktionen |

{style="table-layout:auto"}

### Sonderspalten

**Zeitstempel**

Die spezielle Spalte `timestamp` wird verwendet, um die Datumsbereiche für die Abfrage bereitzustellen. Ein Datumsbereich kann durch einen `BETWEEN`-Ausdruck oder ein mit `AND` verbundenes Paar aus den Überprüfungen `timestamp` `>`, `>=`, `<`, `<=` definiert werden.
`timestamp` ist optional, und falls kein vollständiger Bereich angegeben wird, werden die Standardwerte verwendet:

- Wenn nur ein Minimum angegeben wird (`timestamp > X` oder ` timestamp >= X`), reicht der Bereich von X bis jetzt.

- Wenn nur ein Maximum angegeben wird (`timestamp < X` oder `timestamp <= X`), umfasst der Bereich die 30 Tage vor X.

- Wenn nichts angegeben wird, umfasst der Bereich die letzten 30 Tage bis jetzt.

Der Zeitstempelbereich wird im RankedRequest in einen globalen Datumsbereich-Filter konvertiert.
Das Zeitstempelfeld kann auch als Datums-/Uhrzeitfunktion verwendet werden, um den Zeitstempel des Ereignisses zu analysieren und zu kürzen.

**Datumsbereich**

Die Sonderspalte `daterange` funktioniert ähnlich wie `timestamp`, die Filterung ist jedoch hier auf volle Tage beschränkt. `daterange` ist ebenfalls optional und hat denselben Standardbereich wie `timestamp`.
`daterange` kann auch als Datums-/Uhrzeitfunktion verwendet werden, um das Ereignisdatum zu analysieren und ggf. zu kürzen.

**filterId**

Die spezielle Spalte `filterId` ist optional und wird verwendet, um einen extern definierten Filter auf die Abfrage anzuwenden. Das Anwenden eines extern definierten Filters auf eine Abfrage ähnelt dem Ziehen eines Filters auf ein Bedienfeld in Workspace. Mehrere Filter-IDs können durch Verbinden mit `AND` bereitgestellt werden.

### WHERE-Klausel

Die WHERE-Klausel wird in drei Schritten umgesetzt:

1. Suche des Datumsbereichs aus dem speziellen Feld `timestamp`.

2. Suchen nach extern definierten `filterId`s, die in die Filterung einbezogen werden sollen.

3. Umwandeln der verbleibenden Ausdrücke in Ad-hoc-Filter.

Die Umsetzung erfolgt durch Parsen der ersten Ebene von `AND`s in der `WHERE`-Klausel. Jeder Ausdruck mit `AND` auf oberster Ebene muss mit einem der oben genannten übereinstimmen. Alles, was tiefer als die erste Ebene der `AND`-Operatoren ist, oder, wenn die `WHERE`-Klausel auf der obersten Ebene `OR`-Operatoren verwendet, wird als Ad-hoc-Filter behandelt.

### SORTIEREN NACH

Standardmäßig sortiert die Abfrage die Ergebnisse nach der ersten ausgewählten Metrik in absteigender Reihenfolge. Sie können die Standardsortierreihenolge überschreiben, indem Sie `ORDER BY ... ASC` oder `ORDER BY ... DESC` angeben. Wenn Sie `ORDER BY` verwenden, müssen Sie in der ersten ausgewählten Metrik `ORDER BY` angeben.

Sie können die Reihenfolge auch umdrehen, indem Sie `-` (Minus) vor der Metrik verwenden. Die beiden folgenden Anweisungen ergeben dieselbe Reihenfolge:

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### Unterstützung für allgemeine Funktionen

| Funktion | Beispiel | Details |
|---|---|---|
| [CAST(column AS type)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` oder <br/> `` `timestamp`::string `` | Typumwandlung wird derzeit nicht unterstützt, aber es wird kein Fehler ausgegeben. Die `CAST`-Funktion wird ignoriert. |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Parsen einer Uhrzeitzeichenfolge als Zeitstempel zur Verwendung innerhalb einer `WHERE`-Klausel. |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Parsen einer Uhrzeitzeichenfolge als Zeitstempel für die Verwendung innerhalb einer `WHERE`-Klausel, wobei optional ein Format für diese Zeitzeichenfolge angegeben werden kann. |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Parsen einer Datumszeichenfolge als Zeitstempel zur Verwendung innerhalb einer `WHERE`-Klausel. |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Parsen einer Datumszeichenfolge als Zeitstempel für die Verwendung innerhalb einer `WHERE`-Klausel, wobei optional ein Format für diese Datumszeichenfolge angegeben werden kann. |

{style="table-layout:auto"}

### Unterstützung für Dimensionsfunktionen

Diese Funktionen können für Dimensionen in der `WHERE`- oder `SELECT`-Klausel oder in bedingten Metriken verwendet werden.

**Zeichenfolgen-Funktionen**

| Funktion | Beispiel | Details |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. |

{style="table-layout:auto"}

**Funktionen für Datum/Uhrzeit**

| Funktion | Beispiel | Details |
|---|---|---|
| [YEAR(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. |
| [MONTH(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. |
| [DAY(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. |
| [DAYOFWEEK(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. Verwenden Sie die Element-ID anstelle des Werts, wo Sie die Nummer und nicht den Anzeigenamen benötigen. |
| [DAYOFYEAR(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. |
| [WEEK(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. |
| [QUARTER(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. |
| [HOUR(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. Verwenden Sie die Element-ID anstelle des Werts, wo Sie die Nummer und nicht den Anzeigenamen benötigen. |
| [MINUTE(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. |
| [EXTRACT(part FROM date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. Verwenden Sie die Element-ID anstelle des Werts für einige Teile dieser Funktion, wo Sie die Nummer und nicht den Anzeigenamen benötigen.<br/>Folgende Teile werden unterstützt:<br>-Suchbegriffe: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>-Zeichenfolgen: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` oder `'MINUTE'`. |
| [DATE_PART(part, date, or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. Verwenden Sie die Element-ID anstelle des Werts für einige Teile dieser Funktion, wo Sie die Nummer und nicht den Anzeigenamen benötigen.<br/>Unterstützte Zeichenfolgenteile sind: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`o der `'MINUTE'`. |
| [DATE_TRUNC(granularity, date, or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld.<br/>Folgende Zeichenfolgengranularitäten werden unterstützt: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` oder `'MINUTE'`. |

{style="table-layout:auto"}
