---
title: Customer Journey Analytics BI-Erweiterung
description: Erfahren Sie, wie Sie mit Power BI oder Tableau mithilfe der Customer Journey Analytics BI-Erweiterung auf Datenansichten zugreifen können.
solution: Customer Journey Analytics
feature: BI Extension
role: Admin
exl-id: ab7e1f15-ead9-46b7-94b7-f81802f88ff5
source-git-commit: 79efab0baf9c44603a7aad7383f42a9d9c0b63cb
workflow-type: tm+mt
source-wordcount: '2931'
ht-degree: 65%

---

# Customer Journey Analytics BI-Erweiterung

{{select-package}}

Der [!DNL Customer Journey Analytics BI extension] ermöglicht SQL-Zugriff auf [Datenansichten](./data-views.md), die Sie in Customer Journey Analytics definiert haben. Ihre Dateningenieurinnen und -ingenieure sowie Ihre Datenanalytikerinnen und -analytiker sind möglicherweise besser mit Power BI, Tableau oder anderen Business Intelligence- und Visualisierungs-Tools (im Folgenden „BI-Tools“ genannt) vertraut. Sie können jetzt Berichte und Dashboards basierend auf denselben Datenansichten erstellen, die Benutzerinnen und Benutzer von Customer Journey Analytics beim Erstellen ihrer Analysis Workspace-Projekte verwenden.

Der [Abfrage-Service](https://experienceleague.adobe.com/de/docs/experience-platform/query/home) von Adobe Experience Platform ist die SQL-Schnittstelle zu Daten, die im Data Lake von Experience Platform verfügbar sind. Wenn der [!DNL Customer Journey Analytics BI extension] aktiviert ist, wird die Funktionalität von [!DNL Query Service] erweitert, damit Ihre Datenansichten von Customer Journey Analytics als Tabellen oder Ansichten in einer [!DNL Query Service]-Sitzung zu sehen sind. Daher profitieren Business-Intelligence-Tools, die [!DNL Query Service] als Ihre PostgresSQL-Schnittstelle verwenden, nahtlos von dieser erweiterten Funktion.

Die wichtigsten Vorteile sind:

* Es ist nicht erforderlich, eine äquivalente Darstellung von Datenansichten aus Customer Journey Analytics im BI-Tool selbst zu erstellen. <br/>Weitere Informationen zur Funktion von Datenansichten finden Sie unter [Datenansichten](data-views.md) , um zu verstehen, was neu erstellt werden muss.
* Mehr Konsistenz bei Reporting und Analyse zwischen BI-Tools und Customer Journey Analytics.
* Kombinieren Sie Customer Journey Analytics-Daten mit anderen Datenquellen, die bereits in BI-Tools verfügbar sind.

## Voraussetzungen

Um diese Funktion verwenden zu können, müssen Sie über Folgendes verfügen:

<!---   Enable the [!UICONTROL Customer Journey Analytics BI extension] in your Experience Platform organization. -->

* Gewährter Zugriff auf Experience Platform und Customer Journey Analytics.
* Produktadministratorzugriff auf Customer Journey Analytics gewährt, damit Sie Verbindungen und Datenansichten anzeigen, bearbeiten, aktualisieren oder löschen können.
* Gewährter Zugriff auf die Datenansichten, auf die Sie zugreifen möchten.
* Gewährter Zugriff auf die CJA BI-Erweiterung.
* Verwenden Sie das Ablaufdatum für nicht ablaufende Anmeldedaten, um BI-Tools mit dem [!DNL Customer Journey Analytics BI extension] zu verbinden. Das [Berechtigungshandbuch](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials) enthält weitere Informationen zum Festlegen ablaufender oder nicht ablaufender Anmeldeinformationen.

Weitere Informationen finden Sie unter [Zugriffssteuerung für Kunden-Journey](../technotes/access-control.md), insbesondere die zusätzlichen Berechtigungen [Produktadministrator](../technotes/access-control.md#product-admin-additional-permissions) und [Customer Journey Analytics-Berechtigungen in der Admin Console](../technotes/access-control.md#customer-journey-analytics-permissions-in-admin-console).


## Nutzung

Um die Funktion [!DNL Customer Journey Analytics BI extension] zu verwenden, können Sie SQL entweder direkt verwenden oder das Drag-and-Drop-Erlebnis verwenden, das im jeweiligen BI-Tool verfügbar ist.

### SQL

Sie können die Funktion direkt in SQL-Anweisungen verwenden, indem Sie entweder den Abfrageeditor oder einen standardmäßigen Client der Befehlszeilenschnittstelle (CLI) von Postgres verwenden.

+++ Abfrageeditor

In Adobe Experience Platform:

1. Wählen Sie **[!UICONTROL ** Abfragen **]** unter **[!UICONTROL ** DATEN-MANAGEMENT **]** in der linken Leiste aus.

1. Wählen Sie ![Abfrage erstellen](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Abfrage erstellen **]** aus.

1. Wählen Sie die `cja` **[!UICONTROL ** Datenbank **]** aus.

1. Um die Abfrage auszuführen, geben Sie Ihre SQL-Anweisung ein und wählen Sie die Schaltfläche ![Abspielen](assets/Smock_Play_18_N.svg) (oder drücken Sie `[SHIFT]` + `[ENTER]`).

+++


+++ PostgresSQL-CLI

1. Suchen und kopieren Sie Ihre PostgresSQL-Anmeldeinformationen in Adobe Experience Platform:

   1. Wählen Sie **[!UICONTROL ** Abfragen **]** aus der linken Leiste (unter **[!UICONTROL ** DATEN-MANAGEMENT **]**) aus.

   1. Wählen Sie **[!UICONTROL ** Anmeldeinformationen **]** aus der oberen Leiste aus.

   1. Wählen Sie die `cja` **[!UICONTROL ** Datenbank **]** aus.

   1. Verwenden Sie zum Kopieren der Befehlszeichenfolge ![Kopieren](assets/Smock_Copy_18_N.svg) im Abschnitt **[!UICONTROL ** PSQL-Befehl **]** .

1. Öffnen Sie einen Befehl oder ein Terminal-Fenster.

1. Um sich anzumelden und mit der Ausführung Ihrer Abfragen zu beginnen, fügen Sie die Befehlszeichenfolge in Ihr Terminal ein.

+++

Weitere Informationen finden Sie im [UI-Handbuch für den Abfrage-Editor](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/user-guide) .


### BI-Tools

Derzeit wird [!DNL Customer Journey Analytics BI extension] nur für Power BI und Tableau unterstützt und getestet. Andere BI-Tools, die die PSQL-Oberfläche verwenden, funktionieren möglicherweise ebenfalls, werden jedoch noch nicht offiziell unterstützt.

+++ Power BI

1. Suchen Sie die Details Ihrer PostgresSQL-Anmeldedaten in Adobe Experience Platform:

   1. Wählen Sie **[!UICONTROL ** Abfragen **]** aus der linken Leiste (unter **[!UICONTROL ** DATEN-MANAGEMENT **]**) aus.

   1. Wählen Sie **[!UICONTROL ** Anmeldeinformationen **]** aus der oberen Leiste aus.

   1. Wählen Sie die `cja` **[!UICONTROL ** Datenbank **]** aus.

   1. Verwenden Sie ![Kopieren](assets/Smock_Copy_18_N.svg), um jeden Parameter der Postgres-Anmeldeinformationen ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Datenbank], [!UICONTROL Benutzername] und andere) zu kopieren, wenn sie in Power BI benötigt werden.

1. In Power BI:

   1. Wählen Sie im Hauptfenster **[!UICONTROL ** Daten abrufen **]** aus der oberen Symbolleiste aus.

   1. Wählen Sie **[!UICONTROL Mehr…]** in der linken Leiste aus.

   1. Suchen Sie im Bildschirm **Daten abrufen** nach `PostgresSQL` und wählen Sie die **[!UICONTROL ** PostgresSQL-Datenbank **]** aus der Liste aus.

   1. Im Dialogfeld **[!UICONTROL ** PostgresSQL-Datenbank **]**:

      1. Fügen Sie den Parameter **[!UICONTROL ** Host **]** aus Experience Platform Queries [!UICONTROL Credentials] in das Textfeld **[!UICONTROL ** Server **]** ein.

      1. Fügen Sie den Parameter **[!UICONTROL ** Database **]** aus Experience Platform Queries [!UICONTROL Credentials] in das Textfeld **[!UICONTROL ** Database **]** ein.

         Fügen Sie `?FLATTEN` zum Parameter **[!UICONTROL ** Datenbank **]** hinzu, damit er sich beispielsweise liest wie `prod:cja?FLATTEN`. Weitere Informationen finden Sie unter [Reduzieren verschachtelter Datenstrukturen für die Verwendung mit BI-Tools von Drittanbietern](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data).

      1. Wenn Sie nach dem Modus **[!UICONTROL Data Connectivity]** gefragt werden, wählen Sie **[!UICONTROL DirectQuery]** aus.

      1. Sie werden aufgefordert, **[!UICONTROL Benutzername]** und **[!UICONTROL Passwort]** einzugeben. Verwenden Sie die entsprechenden Parameter aus den [!UICONTROL Anmeldeinformationen] von Experience Platform-Abfragen.


   1. Nach erfolgreicher Anmeldung werden die Customer Journey Analytics-Datenansichtstabellen in Power BIs **[!UICONTROL ** Navigator **]** angezeigt.

   1. Wählen Sie die Datenansichtstabellen aus, die Sie verwenden möchten, und wählen Sie dann **[!UICONTROL ** Laden **]** aus.

   Alle Dimensionen und Metriken, die mit einer oder mehreren ausgewählten Tabellen verknüpft sind, werden im rechten Bereich angezeigt und können in Ihren Visualisierungen verwendet werden.

   Weitere Informationen sind unter [Verbinden von Power BI mit dem Abfrage-Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/power-bi) zu finden.

+++

+++Tableau

1. Suchen Sie die Details Ihrer PostgresSQL-Anmeldedaten in Adobe Experience Platform:

   1. Wählen Sie **[!UICONTROL ** Abfragen **]** aus der linken Leiste (unter **[!UICONTROL ** DATEN-MANAGEMENT **]**) aus.

   1. Wählen Sie **[!UICONTROL ** Anmeldeinformationen **]** aus der oberen Leiste aus.

   1. Wählen Sie die ` cja` **[!UICONTROL ** Datenbank **]** aus.

   1. Verwenden Sie ![Kopieren](assets/Smock_Copy_18_N.svg), um jeden Parameter der Postgres-Anmeldedaten ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Datenbank], [!UICONTROL Benutzername] und andere) bei Bedarf in Tableau zu kopieren.

1. In Tableau:

   1. Wählen Sie **[!UICONTROL ** Mehr **]** aus **[!UICONTROL ** Zu einem Server **]** in der linken Leiste aus.

   1. Wählen Sie **[!UICONTROL ** PostgresSQL **]** aus der Liste aus.

   1. Im Dialogfeld [!UICONTROL PostgresSQL]:

      1. Fügen Sie den Parameter **[!UICONTROL ** Host **]** aus Experience Platform-Abfragen [!UICONTROL Anmeldeinformationen] in das Textfeld **[!UICONTROL ** Server **]** ein.

      1. Fügen Sie den Parameter **[!UICONTROL ** Port **]** aus den Experience Platform-Abfragen [!UICONTROL Anmeldeinformationen] in das Textfeld **[!UICONTROL ** Port **]** ein.

      1. Fügen Sie den Parameter **[!UICONTROL ** Database **]** aus Experience Platform Queries [!UICONTROL Credentials] in das Textfeld **[!UICONTROL ** Database **]** ein.

         Fügen Sie `%3FFLATTEN` zum Parameter **[!UICONTROL ** Datenbank **]** hinzu, damit er sich beispielsweise liest wie `prod:cja%3FFLATTEN`. Weitere Informationen finden Sie unter [Reduzieren verschachtelter Datenstrukturen für die Verwendung mit BI-Tools von Drittanbietern](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data).

      1. Wählen Sie **[!UICONTROL ** Benutzername und Passwort **]** aus der Liste **[!UICONTROL ** Authentifizierung **]** aus.

      1. Fügen Sie den Parameter **[!UICONTROL ** Benutzername **]** aus den [!UICONTROL Anmeldeinformationen] von Experience Platform-Abfragen in das Textfeld **[!UICONTROL ** Benutzername **]** ein.

      1. Fügen Sie den Parameter **[!UICONTROL ** Kennwort **]** aus den Experience Platform-Abfragen [!UICONTROL Anmeldeinformationen] in das Textfeld **[!UICONTROL ** Kennwort **]** ein.

      1. Wählen Sie die Option **[!UICONTROL ** Anmelden **]** aus.

   1. Customer Journey Analytics-Datenansichten werden als Tabellen in der Liste **[!UICONTROL ** Tabelle **]** angezeigt.

   1. Ziehen Sie die Tabellen, die Sie verwenden möchten, auf die Arbeitsfläche.

   Sie können jetzt mit den Daten aus den Datenansichtstabellen arbeiten, um Ihre Berichte und Visualisierungen zu erstellen.

   Weitere Informationen erhalten Sie unter [Verbinden von Tableau mit dem Abfrage-Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/tableau).

+++

Siehe [Verbinden von Clients mit dem Abfrage-Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/overview), um einen Überblick und weitere Informationen über die verschiedenen verfügbaren Tools zu erhalten.

## Funktionalität

Standardmäßig wird für Ihre Datenansichten ein tabellensicherer Name aus ihrem Anzeigenamen generiert. Beispielsweise hat die Datenansicht mit dem Namen [!UICONTROL Meine Webdatenansicht] den Ansichtsnamen `my_web_data_view`. Sie können einen bevorzugten Namen definieren, der in Ihrem BI-Tool für Ihre Datenansicht verwendet werden soll. Weitere Informationen finden Sie unter [Datenansichtseinstellungen](create-dataview.md#settings) .

Wenn Sie die Datenansichts-IDs als Tabellennamen verwenden möchten, können Sie beim Verbinden die optionale Einstellung für `CJA_USE_IDS` auf Ihren Datenbanknamen festlegen. Zum Beispiel zeigt `prod:cja?CJA_USE_IDS` Ihre Datenansichten mit Namen wie `dv_ABC123` an.

### Data Governance

Einstellungen in Bezug auf die Data Governance in Customer Journey Analytics werden von Adobe Experience Platform übernommen. Die Integration zwischen Customer Journey Analytics und Adobe Experience Platform Data Governance ermöglicht die Kennzeichnung sensibler Daten von Customer Journey Analytics und die Durchsetzung von Datenschutzrichtlinien.

Datenschutzbeschriftungen und -richtlinien, die für von Experience Platform genutzte Datensätze erstellt wurden, können im Datenansichts-Workflow von Customer Journey Analytics angezeigt werden. Daher zeigen mit dem [!DNL Customer Journey Analytics BI extension] abgefragte Daten geeignete Warnungen oder Fehler, wenn sie nicht den definierten Datenschutzbezeichnungen und Richtlinien entsprechen.

#### Standardeinstellungen und Einschränkungen

Die folgenden zusätzlichen Standardeinstellungen und Einschränkungen gelten aus Gründen der Data Governance.

* Die BI-Erweiterung erfordert eine Zeilenbegrenzung für die Abfrageergebnisse. Der Standardwert ist 50, aber Sie können dies in SQL mit `LIMIT n` überschreiben, wobei `n` 1 - 50000 ist.
* Die BI-Erweiterung erfordert einen Datumsbereich, um die für Berechnungen verwendeten Zeilen zu beschränken. Die Standardeinstellung ist die letzten 30 Tage. Sie können dies jedoch in Ihrer SQL `WHERE`-Klausel mit den speziellen Spalten [`timestamp`](#timestamp) oder [`daterange`](#date-range) überschreiben (siehe weitere Dokumentation).
* Die BI-Erweiterung erfordert aggregierte Abfragen. Sie können SQL nicht wie `SELECT * FROM ...` verwenden, um die rohen, zugrunde liegenden Zeilen abzurufen. Auf hoher Ebene sollten Ihre Aggregat-Abfragen Folgendes verwenden:
   * Wählen Sie die Summen mit `SUM` und/oder `COUNT` aus.<br/> Beispiel: `SELECT SUM(metric1), COUNT(*) FROM ...`
   * Wählen Sie Metriken, die nach einer Dimension aufgeschlüsselt sind. <br/>Beispiel: `SELECT dimension1, SUM(metric1), COUNT(*) FROM ... GROUP BY dimension1`
   * Wählen Sie unterschiedliche Metrikwerte aus.<br/>Beispiel: `SELECT DISTINCT dimension1 FROM ...`

     Weitere Informationen finden Sie unter [Unterstützte SQL](#supported-sql).

### Auflisten von Datenansichten

In der standardmäßigen PostgresSQL-CLI können Sie Ihre Ansichten mithilfe von `\dv` auf folgende Arten anzeigen:

```sql
prod:all=> \dv
                       List of relations
 Schema |                    Name                    | Type |  Owner             
--------+--------------------------------------------+------+----------
 public | my_web_data_view                           | view | postgres
 public | my_mobile_data_view                        | view | postgres
```

### Verschachtelt oder reduziert

Standardmäßig verwendet das Schema Ihrer Datenansichten verschachtelte Strukturen wie die ursprünglichen XDM-Schemata. Die Integration unterstützt auch die Option `FLATTEN`. Mit dieser Option können Sie erzwingen, dass das Schema für die Datenansichten (und jede andere Tabelle in der Sitzung) reduziert wird. Die Reduzierung ermöglicht eine einfachere Verwendung in BI-Tools, die keine strukturierten Schemata unterstützen. Weitere Informationen finden Sie unter [Arbeiten mit verschachtelten Datenstrukturen im Abfrage-Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data).

### Unterstützte SQL

Die vollständige Referenz dazu, welcher SQL-Typ unterstützt wird, finden Sie unter [SQL-Referenz für den Abfrage-Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/overview).

Beispiele für SQL, die Sie verwenden können, finden Sie in der folgenden Tabelle.

+++ Beispiele

| Muster | Beispiel |
|---|---|
| Schema-Erkennung | <pre>SELECT * FROM dv1 WHERE 1=0</pre> |
| Rangansicht oder Verteilung | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  filterId = &#39;12345&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  AND (dim2 = &#39;A&#39; OR dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>GROUP BY dim1</pre> |
| `HAVING`-Klausel | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>HAVING m1 > 100</pre> |
| Eindeutige, obere <br/>Dimensionswerte | <pre>SELECT DISTINCT dim1 FROM dv1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` >= &#39;2022-01-01&#39; AND \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>ORDER BY SUM(metric1)<br/>LIMIT 15</pre> |
| Metriksummen | <pre>SELECT SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</pre> |
| Mehrere Dimensionen<br/>Aufschlüsselungen<br/>und obere eindeutige Werte | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 1, 2<br/>ORDER BY 1, 2</pre><pre>SELECT DISTINCT dim1, dim2<br/>FROM dv1</pre> |
| Unterauswahl:<br/>Zusätzliche<br/>Ergebnisse filtern | <pre>SELECT dim1, m1<br/>FROM (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</br>  GROUP BY dim1<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| Unterauswahl:<br/>Abfrage über<br/>Datenansichten hinweg | <pre>SELECT key, SUM(m1) AS total<br/>FROM (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim1<br/><br/>  UNION<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  FROM dv2<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim2<br/>GROUP BY key<br/>ORDER BY total</pre> |
| Unterauswahl: <br/>Ebenenquelle, <br/>Filterung, <br/>und Aggregation | Geschichtet, mit den Unterauswahlen:<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>FROM (<br/>  SELECT \_.dim1,\_.m1<br/>  FROM (<br/>    SELECT \* FROM dv1<br/>    WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  ) \_<br/>  WHERE \_.dim1 in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) rows<br/>GROUP BY 1<br/>ORDER BY total</pre><br/>Ebenen, die CTE WITH verwenden:<br/><pre>MIT DEN Zeilen ALS (<br/> MIT \_ AS (<br/>)    SELECT * FROM data_ares<br/>    WO \`timestamp\` ZWISCHEN &#39;2021-01-01&#39; UND &#39;2021-02-01&#39;<br/> )<br/> WÄHLEN SIE \_.item, \_.unit VON \_<br/> WOBEI \_.item NICHT NULL IST<br/>)<br/>SELECT rows.item, SUM(rows.unit) Einheiten<br/>AUS Zeilen, WOBEI Zeilen.Element in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>GRUPPIEREN NACH Zeilen.item</pre> |
| Wählt aus, wo die<br/>Metriken vor<br/> den Dimensionen erscheinen oder mit<br/>den Dimensionen gemischt werden | <pre>SELECT SUM(metric1) AS m1, dim1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 2</pre> |

{style="table-layout:auto"}

+++

### Dimensionen

Sie können jede der Dimensionen auswählen, die standardmäßig verfügbar oder in der Datenansicht definiert sind. Sie wählen eine Dimension anhand ihrer ID aus.

### Metriken

Folgende Metriken stehen zur Auswahl:

* Jede der standardmäßig verfügbaren Metriken;
* Definiert in der Datenansicht;
* Berechnete Metriken, die mit der Datenansicht kompatibel sind, auf die der Benutzer Zugriff hat.

Sie wählen eine Metrik anhand ihrer ID aus, die in einen `SUM(metric)`-Ausdruck eingeschlossen ist, wie Sie es mit jeder SQL-Quelle tun würden.

Sie können:

* `SELECT COUNT(*)` oder `COUNT(1)` verwenden, um die Metrik „Vorfälle“ zu erhalten.
* `SELECT COUNT(DISTINCT dimension)` oder `SELECT APPROX_COUNT_DISTINCT(dimension)` verwenden, um die ungefähren eindeutigen Werte einer Dimension zu zählen. Siehe Details unter [Zählen von eindeutigen Werten](#counting-distinct-values).
* [Inline-Berechnungen](#inline-calculations): Kombinieren von Metriken ohne Zwischenschritte und/oder Mathematik.

#### Zählung unterschiedlicher Werte

Aufgrund der zugrunde liegenden Funktionsweise von Customer Journey Analytics ist die einzige Dimension, für die Sie die Anzahl der eindeutigen Werte genau bestimmen können, die Dimension `adobe_personid`. Die folgenden SQL-Anweisungen `SELECT COUNT(DISTINCT adobe_personid)` oder `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` geben den Wert der standardmäßigen Personenmetrik zurück, d. h. die Anzahl unterschiedlicher Personen. Bei anderen Dimensionen wird eine ungefähre Zählung der eindeutigen Personen zurückgegeben.

#### Bedingte Metriken

Sie können die Klausel `IF` oder `CASE` in der Funktion `SUM` oder `COUNT` einbetten, um eine zusätzliche Filterung hinzuzufügen, die spezifisch für eine ausgewählte Metrik ist. Das Hinzufügen dieser Klauseln ähnelt dem Anwenden eines Filters auf eine Metrikspalte in einer Workspace-Berichtstabelle.

Beispiele:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN metric1 END) AS m1
```

#### Inline-Berechnungen

Sie können zusätzliche Mathematik auf Metrikausdrücke in Ihrem `SELECT` anwenden. Diese Mathematik kann verwendet werden, anstatt die Mathematik in einer berechneten Metrik zu definieren. In der folgenden Tabelle ist aufgeführt, welche Arten von Ausdrücken unterstützt werden.

| Operator oder Funktion | Details |
|---|---|
| `+`, `-`, `*`, `/`, und `%` | Addieren, subtrahieren, multiplizieren, dividieren und modulo/Rest |
| `-X` oder `+X` | Ändern des Zeichens oder einer Metrik, wobei X der Metrikausdruck ist |
| `PI()` | Konstante π |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH` und `TANH` | Unäre mathematische Funktionen |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Binäre mathematische Funktionen |

{style="table-layout:auto"}

### Spezielle Spalten

#### Zeitstempel

Die spezielle Spalte `timestamp` wird verwendet, um die Datumsbereiche für die Abfrage bereitzustellen. Ein Datumsbereich kann durch einen `BETWEEN`-Ausdruck oder ein mit `AND` verbundenes Paar aus den Überprüfungen `timestamp` `>`, `>=`, `<`, `<=` definiert werden.
`timestamp` ist optional, und falls kein vollständiger Bereich angegeben wird, werden die Standardwerte verwendet:

* Wenn nur ein Minimum angegeben wird (`timestamp > X` oder ` timestamp >= X`), reicht der Bereich von X bis jetzt.
* Wenn nur ein Maximalwert (`timestamp < X` oder `timestamp <= X`) angegeben wird, liegt der Bereich zwischen X minus 30 Tagen und X.
* Wenn nichts angegeben wird, liegt der Bereich von jetzt abzüglich 30 Tagen bis jetzt.

Der Zeitstempelbereich wird in einen globalen Datumsbereich-Filter in RankedRequest konvertiert.
Das Zeitstempelfeld kann auch in Datums-/Uhrzeitfunktionen verwendet werden, um den Zeitstempel des Ereignisses zu analysieren oder abzuschneiden.

#### Datumsbereich

Die Sonderspalte `daterange` ähnelt `timestamp`; die Filterung ist jedoch auf volle Tage beschränkt. `daterange` ist ebenfalls optional und hat denselben Standardbereich wie `timestamp`.
Das Feld `daterange` kann auch in Datums-/Uhrzeitfunktionen verwendet werden, um das Ereignisdatum zu analysieren oder abzuschneiden.

Mit der speziellen Spalte `daterangeName` können Sie Ihre Abfrage nach einem benannten Datumsbereich wie `Last Quarter` filtern.

>[!NOTE]
>
>Power BI unterstützt keine `daterange` -Metriken, die weniger als einen Tag betragen (Stunde, 30 Minuten, 5 Minuten usw.).
>

#### Filter-ID

Die spezielle Spalte `filterId` ist optional und wird verwendet, um einen extern definierten Filter auf die Abfrage anzuwenden. Das Anwenden eines extern definierten Filters auf eine Abfrage ähnelt dem Ziehen eines Filters auf ein Bedienfeld in Workspace. Mehrere Filter-IDs können von `AND` verwendet werden.

Zusammen mit `filterId` können Sie mit `filterName` den Namen eines Filters anstelle der ID verwenden.

### Wo

Die `WHERE`-Klausel wird in drei Schritten verarbeitet:

1. Suchen Sie den Datumsbereich aus den speziellen Feldern `timestamp`, `daterange` oder `daterangeName`.

1. Suchen Sie nach extern definierten `filterId`s oder `filterName`s, die in die Filterung einbezogen werden sollen.

1. Umwandeln der verbleibenden Ausdrücke in Ad-hoc-Filter.

Die Umsetzung erfolgt durch Parsen der ersten Ebene von `AND`s in der `WHERE`-Klausel. Jeder Ausdruck der obersten Ebene mit dem Wert `AND` muss mit einem der oben genannten Werte übereinstimmen. Alles, was tiefer als die erste Ebene der `AND`-Operatoren ist, oder, wenn die `WHERE`-Klausel auf der obersten Ebene `OR`-Operatoren verwendet, wird als Ad-hoc-Filter behandelt.

### Sortierreihenfolge

Standardmäßig sortiert die Abfrage die Ergebnisse nach der ersten ausgewählten Metrik in absteigender Reihenfolge. Sie können die Standardsortierreihenolge überschreiben, indem Sie `ORDER BY ... ASC` oder `ORDER BY ... DESC` angeben. Wenn Sie `ORDER BY` verwenden, müssen Sie in der ersten ausgewählten Metrik `ORDER BY` angeben.

Sie können die Reihenfolge auch umdrehen, indem Sie `-` (Minus) vor der Metrik verwenden. Die beiden folgenden Anweisungen ergeben dieselbe Reihenfolge:

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### Allgemeine Funktionsunterstützung

| Funktion | Beispiel | Details |
|---|---|---|
| [cast](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` oder <br/> `` `timestamp`::string `` | Typumwandlung wird derzeit nicht unterstützt, aber es wird kein Fehler ausgegeben. Die `CAST`-Funktion wird ignoriert. |
| [Zeitstempel](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Parsen einer Uhrzeitzeichenfolge als Zeitstempel zur Verwendung innerhalb einer `WHERE`-Klausel. |
| [Auf Zeitstempel](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Parsen einer Uhrzeitzeichenfolge als Zeitstempel für die Verwendung innerhalb einer `WHERE`-Klausel, wobei optional ein Format für diese Zeitzeichenfolge angegeben werden kann. |
| [Datum](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Parsen einer Datumszeichenfolge als Zeitstempel zur Verwendung innerhalb einer `WHERE`-Klausel. |
| [Bis date](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Parsen einer Datumszeichenfolge als Zeitstempel für die Verwendung innerhalb einer `WHERE`-Klausel, wobei optional ein Format für diese Datumszeichenfolge angegeben werden kann. |

{style="table-layout:auto"}

### Unterstützung von Dimension-Funktionen

Diese Funktionen können für Dimensionen in der `WHERE`- oder `SELECT`-Klausel oder in bedingten Metriken verwendet werden.

**Zeichenfolgen-Funktionen**

| Funktion | Beispiel | Details |
|---|---|---|
| [Lower](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. |

{style="table-layout:auto"}

**Datums-/Uhrzeitfunktionen**

| Funktion | Beispiel | Details |
|---|---|---|
| [Jahr](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. |
| [Monat](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. |
| [Tag](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. |
| [Wochentag](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. Verwenden Sie die Element-ID anstelle des Werts, wo Sie die Nummer und nicht den Anzeigenamen benötigen. |
| [Tag des Jahres](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. |
| [Woche](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. |
| [Quartal](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. |
| [Stunde](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. Verwenden Sie die Element-ID anstelle des Werts, wo Sie die Nummer und nicht den Anzeigenamen benötigen. |
| [Minute](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. |
| [Extract](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. Verwenden Sie die Element-ID anstelle des Werts für einige Teile dieser Funktion, wo Sie die Nummer und nicht den Anzeigenamen benötigen.<br/>Folgende Teile werden unterstützt:<br>-Suchbegriffe: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>-Zeichenfolgen: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` oder `'MINUTE'`. |
| [Datum (Teil)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. Verwenden Sie die Element-ID anstelle des Werts für einige Teile dieser Funktion, wo Sie die Nummer und nicht den Anzeigenamen benötigen.<br/>Unterstützte Zeichenfolgenteile sind: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`o der `'MINUTE'`. |
| [Datum (abgeschnitten)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld.<br/>Folgende Zeichenfolgengranularitäten werden unterstützt: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` oder `'MINUTE'`. |

{style="table-layout:auto"}
