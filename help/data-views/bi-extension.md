---
title: Customer Journey Analytics BI-Erweiterung
description: Erfahren Sie, wie Sie mit Power BI oder Tableau Desktop mithilfe der Customer Journey Analytics BI-Erweiterung auf Datenansichten zugreifen können.
solution: Customer Journey Analytics
feature: BI Extension
role: Admin
exl-id: ab7e1f15-ead9-46b7-94b7-f81802f88ff5
source-git-commit: 5fa4d47bcd42e4e392a7075076895826cf7061b1
workflow-type: tm+mt
source-wordcount: '3618'
ht-degree: 53%

---

# Customer Journey Analytics BI-Erweiterung

{{select-package}}

Der [!DNL Customer Journey Analytics BI extension] ermöglicht SQL-Zugriff auf [Datenansichten](./data-views.md), die Sie in Customer Journey Analytics definiert haben. Ihre Dateningenieure und Analysten sind möglicherweise besser mit Power BI, Tableau Desktop oder anderen Business Intelligence- und Visualisierungs-Tools (auch als BI-Tools bezeichnet) vertraut. Sie können jetzt Berichte und Dashboards basierend auf denselben Datenansichten erstellen, die Benutzerinnen und Benutzer von Customer Journey Analytics beim Erstellen ihrer Analysis Workspace-Projekte verwenden.

Der [Abfrage-Service](https://experienceleague.adobe.com/de/docs/experience-platform/query/home) von Adobe Experience Platform ist die SQL-Schnittstelle zu Daten, die im Data Lake von Experience Platform verfügbar sind. Wenn der [!DNL Customer Journey Analytics BI extension] aktiviert ist, wird die Funktionalität von [!DNL Query Service] erweitert, damit Ihre Datenansichten von Customer Journey Analytics als Tabellen oder Ansichten in einer [!DNL Query Service]-Sitzung zu sehen sind. Daher profitieren Business-Intelligence-Tools, die [!DNL Query Service] als Ihre PostgresSQL-Schnittstelle verwenden, nahtlos von dieser erweiterten Funktion.

Die wichtigsten Vorteile sind:

* Es ist nicht erforderlich, eine äquivalente Darstellung von Datenansichten aus Customer Journey Analytics im BI-Tool selbst zu erstellen. <br/>Siehe [Datenansichten](data-views.md) für weitere Informationen zur Funktionalität von Datenansichten, um zu verstehen, was neu erstellt werden muss.
* Mehr Konsistenz bei Reporting und Analyse zwischen BI-Tools und Customer Journey Analytics.
* Kombinieren Sie Customer Journey Analytics-Daten mit anderen Datenquellen, die bereits in BI-Tools verfügbar sind.

## Voraussetzungen

Um diese Funktion zu verwenden, können Sie ablaufende oder nicht ablaufende Anmeldeinformationen verwenden, um BI-Tools mit dem [!DNL Customer Journey Analytics BI extension] zu verbinden. Das [Handbuch zu Anmeldeinformationen](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials) enthält weitere Informationen zum Festlegen ablaufender Anmeldeinformationen oder nicht ablaufender Anmeldeinformationen.
Im Folgenden finden Sie zusätzliche Schritte zum Einrichten von CJA-Berechtigungen
<!---   Enable the [!UICONTROL Customer Journey Analytics BI extension] in your Experience Platform organization. -->

### Ablaufende Anmeldeinformationen

Um ablaufende Anmeldeinformationen zu verwenden, können Sie:

* Gewähren von Zugriff auf Experience Platform und Customer Journey Analytics.
* Gewähren Sie Produktadministratorzugriff auf Customer Journey Analytics, damit Sie Verbindungen und Datenansichten anzeigen, bearbeiten, aktualisieren oder löschen können.

Oder Sie können:

* Gewähren Sie Zugriff auf die Datenansichten, auf die Sie zugreifen möchten.
* Gewähren des Zugriffs auf die Customer Journey Analytics BI-Erweiterung.

### Nicht ablaufende Anmeldedaten

So verwenden Sie nicht ablaufende Anmeldeinformationen:

* Erstellen Sie unbefristete Anmeldedaten in Experience Platform.
* Gewähren Sie Zugriff auf die nicht ablaufenden Anmeldeinformationen, indem Sie die unter &quot;[ Anmeldeinformationen“ ](#Expiring-credentials) Schritte ausführen.

Siehe [Kunden-Journey-Zugriffssteuerung](../technotes/access-control.md) für weitere Informationen, insbesondere die [Produktadministrator-zusätzlichen Berechtigungen](../technotes/access-control.md#product-admin-additional-permissions) und [Customer Journey Analytics-Berechtigungen in der Admin Console](../technotes/access-control.md#customer-journey-analytics-permissions-in-admin-console).


## Nutzung

Um die Funktion [!DNL Customer Journey Analytics BI extension] zu verwenden, können Sie SQL entweder direkt verwenden oder das Drag-and-Drop-Erlebnis verwenden, das im jeweiligen BI-Tool verfügbar ist.

### SQL

Sie können die Funktion direkt in SQL-Anweisungen verwenden, indem Sie entweder den Abfrageeditor oder einen standardmäßigen Client der Befehlszeilenschnittstelle (CLI) von Postgres verwenden.

+++ Abfrageeditor

In Adobe Experience Platform:

1. Wählen Sie **[!UICONTROL ** Abfragen **]** unter **[!UICONTROL ** DATEN-MANAGEMENT **]** in der linken Leiste aus.

1. Wählen Sie ![Abfrage erstellen](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Abfrage erstellen **]** aus.

1. Wählen Sie die `cja` für Ihre Sandbox aus der Liste der Datenbanken im Dropdown-Menü **[!UICONTROL Datenbank]** aus. Zum Beispiel `prod:cja`.

1. Um die Abfrage auszuführen, geben Sie Ihre SQL-Anweisung ein und wählen Sie die ![Play](assets/Smock_Play_18_N.svg)-Schaltfläche (oder drücken Sie `[SHIFT]` + `[ENTER]`).

+++


+++ PostgresSQL-CLI

1. Suchen und Kopieren Ihrer PostgresSQL-Anmeldeinformationen in Adobe Experience Platform:

   1. Wählen Sie **[!UICONTROL ** Abfragen **]** aus der linken Leiste (unter **[!UICONTROL ** DATEN-MANAGEMENT **]**) aus.

   1. Wählen Sie **[!UICONTROL ** Anmeldeinformationen **]** aus der oberen Leiste aus.

   1. Wählen Sie die `cja` für Ihre Sandbox aus der Liste der Datenbanken im Dropdown-Menü **[!UICONTROL Datenbank]** aus. Zum Beispiel `prod:cja`.

   1. Um die Befehlszeichenfolge zu kopieren, verwenden Sie ![Kopieren](assets/Smock_Copy_18_N.svg) im Abschnitt **[!UICONTROL ** PSQL-Befehl **]**.

1. Öffnen Sie ein Befehls- oder Terminal-Fenster.

1. Um sich anzumelden und mit der Ausführung Ihrer Abfragen zu beginnen, fügen Sie die Befehlszeichenfolge in Ihr Terminal ein.

+++

Weitere Informationen finden Sie [ Handbuch zur Benutzeroberfläche ](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/user-guide) Abfrage-Editors .


### BI-Tools

Derzeit wird die [!DNL Customer Journey Analytics BI extension] für die unten aufgeführten Tools unterstützt und getestet. Andere BI-Tools, die die PSQL-Schnittstelle verwenden, funktionieren möglicherweise ebenfalls, werden jedoch noch nicht offiziell unterstützt.

+++ Power BI

1. Nachschlagen der Details Ihrer PostgresSQL-Anmeldeinformationen in Adobe Experience Platform:

   1. Wählen Sie **[!UICONTROL ** Abfragen **]** aus der linken Leiste (unter **[!UICONTROL ** DATEN-MANAGEMENT **]**) aus.

   1. Wählen Sie **[!UICONTROL ** Anmeldeinformationen **]** aus der oberen Leiste aus.

   1. Wählen Sie die `cja` für Ihre Sandbox aus der Liste der Datenbanken im Dropdown-Menü **[!UICONTROL Datenbank]** aus. Zum Beispiel `prod:cja`.

   1. Verwenden Sie ![Kopieren](assets/Smock_Copy_18_N.svg), um jeden Parameter der Postgres-Anmeldeinformationen ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Datenbank], [!UICONTROL Benutzername] und andere) zu kopieren, wenn sie in Power BI benötigt werden.

1. In Power BI:

   1. Wählen Sie im Hauptfenster **[!UICONTROL ** Daten abrufen **]** aus der oberen Symbolleiste aus.

   1. Wählen Sie **[!UICONTROL Mehr…]** in der linken Leiste aus.

   1. Suchen Sie im Bildschirm **Daten abrufen** nach `PostgresSQL` und wählen Sie die **[!UICONTROL ** PostgresSQL-Datenbank **]** aus der Liste aus.

   1. Im Dialogfeld **[!UICONTROL ** PostgresSQL-Datenbank **]**:

      1. Fügen Sie den **[!UICONTROL ** Host **]**-Parameter aus den Experience Platform-[!UICONTROL  (]) in das Textfeld **[!UICONTROL ** Server **]** ein.

      1. Fügen Sie den **[!UICONTROL ** Datenbank **]**-Parameter aus den Experience Platform-[!UICONTROL  (]) in das Textfeld **[!UICONTROL ** Datenbank **]** ein.

         Fügen Sie `?FLATTEN` zum Parameter **[!UICONTROL ** Datenbank **]** hinzu, damit er sich beispielsweise liest wie `prod:cja?FLATTEN`. Weitere Informationen finden Sie unter [Reduzieren verschachtelter Datenstrukturen für die Verwendung mit BI-Tools von Drittanbietern](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data).

      1. Wenn Sie nach dem Modus **[!UICONTROL Datenverbindung]** gefragt werden, wählen Sie **[!UICONTROL DirectQuery]** aus.

      1. Sie werden aufgefordert, **[!UICONTROL Benutzername]** und **[!UICONTROL Passwort]** einzugeben. Verwenden Sie die entsprechenden Parameter aus den [!UICONTROL Anmeldeinformationen] von Experience Platform-Abfragen.


   1. Nach erfolgreicher Anmeldung werden die Customer Journey Analytics-Datenansichtstabellen in Power BIs (**[!UICONTROL **) **]**.

   1. Wählen Sie die Datenansichtstabellen aus, die Sie verwenden möchten, und wählen Sie dann **[!UICONTROL ** Laden **]** aus.

   Alle Dimensionen und Metriken, die mit einer oder mehreren ausgewählten Tabellen verknüpft sind, werden im rechten Bereich angezeigt und können in Ihren Visualisierungen verwendet werden.

   Weitere Informationen finden [ unter „Verbinden von Power BI mit ](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/power-bi) Service“. Siehe auch [Anwendungsfälle für BI-Erweiterungen](/help/use-cases/data-views/bi-extension-usecases.md) für ein detailliertes Beispiel.

+++

+++Tableau Desktop

1. Nachschlagen der Details Ihrer PostgresSQL-Anmeldeinformationen in Adobe Experience Platform:

   1. Wählen Sie **[!UICONTROL ** Abfragen **]** aus der linken Leiste (unter **[!UICONTROL ** DATEN-MANAGEMENT **]**) aus.

   1. Wählen Sie **[!UICONTROL ** Anmeldeinformationen **]** aus der oberen Leiste aus.

   1. Wählen Sie die `cja` für Ihre Sandbox aus der Liste der Datenbanken im Dropdown-Menü **[!UICONTROL Datenbank]** aus. Zum Beispiel `prod:cja`.

   1. Verwenden Sie ![Kopieren](assets/Smock_Copy_18_N.svg), um alle Postgres-Anmeldedaten-Parameter ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Datenbank], [!UICONTROL Benutzername] und andere) bei Bedarf in Tableau Desktop zu kopieren.

1. In Tableau Desktop:

   1. Wählen Sie **[!UICONTROL ** Mehr **]** aus **[!UICONTROL ** Zu einem Server **]** in der linken Leiste aus.

   1. Wählen Sie **[!UICONTROL ** PostgresSQL **]** aus der Liste aus.

   1. Im Dialogfeld [!UICONTROL PostgresSQL]:

      1. Fügen Sie den **[!UICONTROL ** Host **]**-Parameter aus den Experience Platform[!UICONTROL Abfragen] in das Textfeld **[!UICONTROL ** Server **]** ein.

      1. Fügen Sie den **[!UICONTROL ** Port **]** aus den Experience Platform-Abfragen [!UICONTROL Anmeldeinformationen] in das Textfeld **[!UICONTROL ** Port **]** ein.

      1. Fügen Sie den **[!UICONTROL ** Datenbank **]**-Parameter aus Experience Platform-Abfragen [!UICONTROL Anmeldeinformationen] in das Textfeld **[!UICONTROL ** Datenbank **]** ein.

         Fügen Sie `%3FFLATTEN` zum Parameter **[!UICONTROL ** Datenbank **]** hinzu, damit er sich beispielsweise liest wie `prod:cja%3FFLATTEN`. Weitere Informationen finden Sie unter [Reduzieren verschachtelter Datenstrukturen für die Verwendung mit BI-Tools von Drittanbietern](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data).

      1. Wählen Sie **[!UICONTROL ** Benutzername und Passwort **]** aus der Liste **[!UICONTROL ** Authentifizierung **]** aus.

      1. Fügen Sie den Parameter **[!UICONTROL ** Benutzername **]** aus den [!UICONTROL Anmeldeinformationen] von Experience Platform-Abfragen in das Textfeld **[!UICONTROL ** Benutzername **]** ein.

      1. Fügen Sie den **[!UICONTROL ** Password **]** aus Experience Platform-Abfragen [!UICONTROL Anmeldeinformationen] in das Textfeld **[!UICONTROL ** Password **]** ein.

      1. Wählen Sie **[!UICONTROL ** Anmelden **]** aus.

   1. Customer Journey Analytics-Datenansichten werden in der Liste „Tabelle **[!UICONTROL ** als **]** angezeigt.

   1. Ziehen Sie die Tabellen, die Sie verwenden möchten, auf die Arbeitsfläche.

   Sie können jetzt mit den Daten aus den Datenansichtstabellen arbeiten, um Ihre Berichte und Visualisierungen zu erstellen.

   Weitere Informationen finden [ unter „Verbinden von Tableau mit ](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/tableau) Service“. Siehe auch [Anwendungsfälle für BI-Erweiterungen](/help/use-cases/data-views/bi-extension-usecases.md) für ein detailliertes Beispiel.

+++

+++ Looker

1. Nachschlagen der Details Ihrer PostgresSQL-Anmeldeinformationen in Adobe Experience Platform:

   1. Wählen Sie **[!UICONTROL ** Abfragen **]** aus der linken Leiste (unter **[!UICONTROL ** DATEN-MANAGEMENT **]**) aus.

   1. Wählen Sie **[!UICONTROL ** Anmeldeinformationen **]** aus der oberen Leiste aus.

   1. Wählen Sie die `cja` für Ihre Sandbox aus der Liste der Datenbanken im Dropdown-Menü **[!UICONTROL Datenbank]** aus. Zum Beispiel `prod:cja`.

   1. Verwenden Sie ![Kopieren](assets/Smock_Copy_18_N.svg), um alle Postgres-Anmeldedaten-Parameter ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Datenbank], [!UICONTROL Benutzername] und andere) bei Bedarf in Looker zu kopieren.

1. In Looker:

   1. Wählen **[!UICONTROL Admin]** in der linken Leiste aus.
   1. Wählen Sie **[!UICONTROL Verbindungen]** aus.
   1. Wählen Sie **[!UICONTROL Verbindung hinzufügen]** aus.
   1. Fügen **[!UICONTROL im Bildschirm „Datenbank mit Looker verbinden]** die entsprechenden Werte ein, wenn Sie Ihre neue Verbindung einrichten. Stellen Sie sicher **[!UICONTROL dass Sie „PostgreSQL 9.5+]**&quot; als Dialekt auswählen.
   1. Wählen Sie **[!UICONTROL Test]** aus, um Ihre Verbindung zu testen.
   1. Klicken Sie bei Erfolg auf **[!UICONTROL Aktualisieren]**, um Ihre Verbindung zu speichern.

   Sie können jetzt mit den Daten aus den Datenansichtstabellen arbeiten, um Ihre Berichte und Visualisierungen zu erstellen.

   Weitere Informationen finden [ unter „Verbinden von Looker ](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/looker) Query Service“. Siehe auch [Anwendungsfälle für BI-Erweiterungen](/help/use-cases/data-views/bi-extension-usecases.md) für ein detailliertes Beispiel.

+++

+++ Jupyter Notebook

1. Nachschlagen der Details Ihrer PostgresSQL-Anmeldeinformationen in Adobe Experience Platform:

   1. Wählen Sie **[!UICONTROL ** Abfragen **]** aus der linken Leiste (unter **[!UICONTROL ** DATEN-MANAGEMENT **]**) aus.

   1. Wählen Sie **[!UICONTROL ** Anmeldeinformationen **]** aus der oberen Leiste aus.

   1. Wählen Sie die `cja` für Ihre Sandbox aus der Liste der Datenbanken im Dropdown-Menü **[!UICONTROL Datenbank]** aus. Zum Beispiel `prod:cja`.

   1. Verwenden Sie ![Kopieren](assets/Smock_Copy_18_N.svg), um alle Postgres-Anmeldedaten-Parameter ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username] und andere) bei Bedarf in Jupyter Notebook zu kopieren.

1. In Jupyter Notebook:

   1. Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken verwenden.
   1. Verwenden Sie beim Einrichten und Ausführen der Verbindung die entsprechenden Werte.
   1. Testen Sie die Verbindung, indem Sie eine entsprechende Abfrage ausführen.

   Nach erfolgreicher Ausführung können Sie mit den Daten arbeiten, um Ihre Berichte und Visualisierungen zu erstellen.

   Weitere Informationen finden [ unter „Verbinden von Jupyter-](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/jupyter-notebook) mit dem Abfrage-Service“. Siehe auch [Anwendungsfälle für BI-Erweiterungen](/help/use-cases/data-views/bi-extension-usecases.md) für ein detailliertes Beispiel.

+++

+++ RStudio

1. Nachschlagen der Details Ihrer PostgresSQL-Anmeldeinformationen in Adobe Experience Platform:

   1. Wählen Sie **[!UICONTROL ** Abfragen **]** aus der linken Leiste (unter **[!UICONTROL ** DATEN-MANAGEMENT **]**) aus.

   1. Wählen Sie **[!UICONTROL ** Anmeldeinformationen **]** aus der oberen Leiste aus.

   1. Wählen Sie die `cja` für Ihre Sandbox aus der Liste der Datenbanken im Dropdown-Menü **[!UICONTROL Datenbank]** aus. Zum Beispiel `prod:cja`.

   1. Verwenden Sie ![Kopieren](assets/Smock_Copy_18_N.svg), um alle Postgres-Anmeldedaten-Parameter ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username] und andere) bei Bedarf in Jupyter Notebook zu kopieren.

1. In RStudio:

   1. Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken verwenden.
   1. Verwenden Sie beim Einrichten und Ausführen der Verbindung die entsprechenden Werte.
   1. Testen Sie die Verbindung, indem Sie eine entsprechende Abfrage ausführen.

   Nach erfolgreicher Ausführung können Sie mit den Daten arbeiten, um Ihre Berichte und Visualisierungen zu erstellen.

   Weitere Informationen finden [ unter „Verbinden von RStudio mit ](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/rstudio) Service“. Siehe auch [Anwendungsfälle für BI-Erweiterungen](/help/use-cases/data-views/bi-extension-usecases.md) für ein detailliertes Beispiel (bei dem stattdessen das RPostgres-Paket verwendet wird).

+++

Siehe [Verbinden von Clients mit dem Abfrage-Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/overview), um einen Überblick und weitere Informationen über die verschiedenen verfügbaren Tools zu erhalten.

Siehe [Anwendungsfälle](/help/use-cases/data-views/bi-extension-usecases.md), wie Sie eine Reihe von Anwendungsfällen mit der Customer Journey Analytics BI-Erweiterung durchführen.

## Funktionalität

Standardmäßig wird für Ihre Datenansichten ein tabellensicherer Name aus ihrem Anzeigenamen generiert. Beispielsweise hat die Datenansicht mit dem Namen [!UICONTROL Meine Web-Datenansicht] den Ansichtsnamen `my_web_data_view`. Sie können einen bevorzugten Namen definieren, der in Ihrem BI-Tool für Ihre Datenansicht verwendet werden soll. Weitere Informationen [ Sie unter ](create-dataview.md#settings)Datenansichtseinstellungen“.

Wenn Sie die Datenansichts-IDs als Tabellennamen verwenden möchten, können Sie beim Verbinden die optionale Einstellung für `CJA_USE_IDS` auf Ihren Datenbanknamen festlegen. Zum Beispiel zeigt `prod:cja?CJA_USE_IDS` Ihre Datenansichten mit Namen wie `dv_ABC123` an.

### Data Governance

Einstellungen in Bezug auf die Data Governance in Customer Journey Analytics werden von Adobe Experience Platform übernommen. Die Integration zwischen Customer Journey Analytics und Adobe Experience Platform Data Governance ermöglicht die Kennzeichnung sensibler Daten von Customer Journey Analytics und die Durchsetzung von Datenschutzrichtlinien.

Datenschutzbeschriftungen und -richtlinien, die für von Experience Platform genutzte Datensätze erstellt wurden, können im Datenansichts-Workflow von Customer Journey Analytics angezeigt werden. Daher zeigen Daten, die mit dem [!DNL Customer Journey Analytics BI extension] abgefragt werden, geeignete Warnungen oder Fehler an, wenn sie nicht den definierten Datenschutzkennzeichnungen und -richtlinien entsprechen.

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


### Standardwerte und Einschränkungen

Die folgenden zusätzlichen Standardwerte und Einschränkungen gelten für die Verwendung der BI-Erweiterung:

* Die BI-Erweiterung erfordert eine Zeilenbegrenzung für die Abfrageergebnisse. Der Standardwert ist 50, aber Sie können dies in SQL mit `LIMIT n` überschreiben, wobei `n` 1 - 50000 ist.
* Die BI-Erweiterung erfordert einen Datumsbereich, um die für Berechnungen verwendeten Zeilen zu begrenzen. Der Standardwert ist die letzten 30 Tage, Sie können dies jedoch in Ihrer SQL-`WHERE`-Klausel überschreiben, indem Sie die speziellen [`timestamp`](#timestamp) oder [`daterange`](#date-range) Spalten verwenden.
* Die BI-Erweiterung erfordert Aggregatabfragen. Sie können keine SQL-ähnlichen `SELECT * FROM ...` verwenden, um die rohen, zugrunde liegenden Zeilen abzurufen. Ihre Aggregatabfragen sollten auf allgemeiner Ebene Folgendes verwenden:
   * Gesamtsummen mit `SUM` und/oder `COUNT` auswählen.<br/> Beispiel: `SELECT SUM(metric1), COUNT(*) FROM ...`
   * Wählen Sie Metriken aus, die nach einer Dimension aufgeschlüsselt sind. <br/>Zum Beispiel `SELECT dimension1, SUM(metric1), COUNT(*) FROM ... GROUP BY dimension1`
   * Unterschiedliche Metrikwerte auswählen.<br/>Zum Beispiel `SELECT DISTINCT dimension1 FROM ...`

     Weitere Informationen finden Sie unter [Unterstützte SQL](#supported-sql).


### Unterstützte SQL

Die vollständige Referenz dazu, welcher SQL-Typ unterstützt wird, finden Sie unter [SQL-Referenz für den Abfrage-Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/overview).

In der folgenden Tabelle finden Sie Beispiele für die SQL, die Sie verwenden können.

+++ Beispiele

| Muster | Beispiel |
|---|---|
| Schema-Erkennung | <pre>SELECT * FROM dv1 WHERE 1=0</pre> |
| Rangfolge oder Aufschlüsselung | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  filterId = &#39;12345&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  AND (dim2 = &#39;A&#39; OR dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>GROUP BY dim1</pre> |
| `HAVING` | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>HAVING m1 > 100</pre> |
| Eindeutige, obere <br/>Dimensionswerte | <pre>SELECT DISTINCT dim1 FROM dv1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` >= &#39;2022-01-01&#39; AND \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>ORDER BY SUM(metric1)<br/>LIMIT 15</pre> |
| Metriksummen | <pre>SELECT SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</pre> |
| Mehrere Dimensionen<br/>Aufschlüsselungen<br/>und obere eindeutige Werte | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 1, 2<br/>ORDER BY 1, 2</pre><pre>SELECT DISTINCT dim1, dim2<br/>FROM dv1</pre> |
| subselect:<br/>filter additional<br/>results | <pre>SELECT dim1, m1<br/>FROM (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</br>  GROUP BY dim1<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| subselect:<br/>queryAcross<br/>data views | <pre>SELECT key, SUM(m1) AS total<br/>FROM (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim1<br/><br/>  UNION<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  FROM dv2<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim2<br/>GROUP BY key<br/>ORDER BY total</pre> |
| Unterauswahl: <br/>Quelle mit mehreren Ebenen, <br/>Filtern<br/> und Aggregation | Geschichtet, mit den Unterauswahlen:<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>FROM (<br/>  SELECT \_.dim1,\_.m1<br/>  FROM (<br/>    SELECT \* FROM dv1<br/>    WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  ) \_<br/>  WHERE \_.dim1 in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) rows<br/>GROUP BY 1<br/>ORDER BY total</pre><br/>Ebenen, die CTE WITH verwenden:<br/><pre>MIT ZEILEN ALS (<br/> MIT \_ AS (<br/>    SELECT * FROM data_ares<br/>    WO \`timestamp\` BETWEEN &#39;2021-01-01&#39; AND &#39;2021-02-01&#39;<br/> )<br/> SELECT \_.item, \_.units FROM \_<br/> WO \_.item NICHT NULL IST<br/>)<br/>SELECT rows.item, SUM(rows.units) AS units<br/>FROM rows.item IN (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>GROUP BY rows.item</pre> |
| Wählt aus, wo die<br/>Metriken vor<br/> den Dimensionen erscheinen oder mit<br/>den Dimensionen gemischt werden | <pre>SELECT SUM(metric1) AS m1, dim1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 2</pre> |

{style="table-layout:auto"}

+++

### Dimensionen

Sie können jede der Dimensionen auswählen, die standardmäßig verfügbar oder in der Datenansicht definiert sind. Sie wählen eine Dimension anhand ihrer ID aus.

### Metriken

Folgende Metriken stehen zur Auswahl:

* Standardmäßig verfügbare Metriken;
* Wird in der Datenansicht definiert.
* Berechnete Metriken, die mit der Datenansicht kompatibel sind, auf die der Benutzer Zugriff hat.

Sie wählen eine Metrik anhand ihrer ID aus, die in einen `SUM(metric)`-Ausdruck eingeschlossen ist, wie Sie es mit jeder SQL-Quelle tun würden.

Sie können:

* `SELECT COUNT(*)` oder `COUNT(1)` verwenden, um die Metrik „Vorfälle“ zu erhalten.
* `SELECT COUNT(DISTINCT dimension)` oder `SELECT APPROX_COUNT_DISTINCT(dimension)` verwenden, um die ungefähren eindeutigen Werte einer Dimension zu zählen. Weitere Informationen finden Sie unter [Eindeutige Werte zählen](#counting-distinct-values).
* [Inline-Berechnungen](#inline-calculations) um Metriken im laufenden Betrieb zu kombinieren und/oder zu rechnen.

#### Unterschiedliche Werte zählen

Aufgrund der zugrunde liegenden Funktionsweise von Customer Journey Analytics ist die einzige Dimension, für die Sie die Anzahl der eindeutigen Werte genau bestimmen können, die Dimension `adobe_personid`. Die folgenden SQL-Anweisungen `SELECT COUNT(DISTINCT adobe_personid)` oder `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` geben den Wert der Metrik „Standard-Personen“ zurück, d. h. die Anzahl unterschiedlicher Personen. Bei anderen Dimensionen wird eine ungefähre Zählung der eindeutigen Personen zurückgegeben.

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

Sie können zusätzliche mathematische Berechnungen auf Metrikausdrücke in Ihrer `SELECT` anwenden. Diese Mathematik kann verwendet werden, anstatt die Mathematik in einer berechneten Metrik zu definieren. In der folgenden Tabelle sind die unterstützten Ausdruckstypen aufgeführt.

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
* Wenn nur ein Maximum angegeben wird (`timestamp < X` oder `timestamp <= X`), reicht der Bereich von X minus 30 Tage bis X.
* Wenn nichts angegeben wird, beträgt der Bereich von jetzt abzüglich 30 Tage bis jetzt.

Der Zeitstempelbereich wird in der RankedRequest in einen globalen Filter für den Datumsbereich konvertiert.
Das Zeitstempelfeld kann auch in Datums-/Uhrzeitfunktionen verwendet werden, um den Ereignis-Zeitstempel zu analysieren oder zu kürzen.

#### Datumsbereich

Die Spalte `daterange` funktioniert ähnlich wie `timestamp`. Die Filterung ist jedoch auf volle Tage beschränkt. `daterange` ist ebenfalls optional und hat denselben Standardbereich wie `timestamp`.
Das `daterange` Feld kann auch in Datums-/Uhrzeitfunktionen verwendet werden, um das Ereignisdatum zu analysieren oder zu kürzen.

Die Spalte `daterangeName` kann verwendet werden, um Ihre Abfrage mithilfe eines benannten Datumsbereichs wie `Last Quarter` zu filtern.

>[!NOTE]
>
>Power BI unterstützt keine `daterange` Metriken, die weniger als einen Tag umfassen (Stunde, 30 Minuten, 5 Minuten usw.).
>

#### Filter-ID

Die spezielle Spalte `filterId` ist optional und wird verwendet, um einen extern definierten Filter auf die Abfrage anzuwenden. Das Anwenden eines extern definierten Filters auf eine Abfrage ähnelt dem Ziehen eines Filters auf ein Bedienfeld in Workspace. Es können mehrere Filter-IDs verwendet werden, indem sie `AND` werden.

Zusammen mit `filterId` können Sie `filterName` verwenden, um den Namen eines Filters anstelle der ID zu verwenden.

### Where-Klausel

Die `WHERE`-Klausel wird in drei Schritten behandelt:

1. Suchen Sie den Datumsbereich aus den `timestamp`-, `daterange`- oder `daterangeName` Spezialfeldern.

1. Suchen Sie nach extern definierten `filterId` oder `filterName`, die in die Filterung aufgenommen werden sollen.

1. Umwandeln der verbleibenden Ausdrücke in Ad-hoc-Filter.

Die Umsetzung erfolgt durch Parsen der ersten Ebene von `AND`s in der `WHERE`-Klausel. Jeder `AND`-ed-Ausdruck der obersten Ebene muss mit einem der oben genannten übereinstimmen. Alles, was tiefer als die erste Ebene der `AND`-Operatoren ist, oder, wenn die `WHERE`-Klausel auf der obersten Ebene `OR`-Operatoren verwendet, wird als Ad-hoc-Filter behandelt.

### Sortierreihenfolge

Standardmäßig sortiert die Abfrage die Ergebnisse nach der ersten ausgewählten Metrik in absteigender Reihenfolge. Sie können die Standardsortierreihenolge überschreiben, indem Sie `ORDER BY ... ASC` oder `ORDER BY ... DESC` angeben. Wenn Sie `ORDER BY` verwenden, müssen Sie in der ersten ausgewählten Metrik `ORDER BY` angeben.

Sie können die Reihenfolge auch umdrehen, indem Sie `-` (Minus) vor der Metrik verwenden. Die beiden folgenden Anweisungen ergeben dieselbe Reihenfolge:

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### Unterstützung allgemeiner Funktionen

| Funktion | Beispiel | Details |
|---|---|---|
| [Guss](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` oder <br/> `` `timestamp`::string `` | Typumwandlung wird derzeit nicht unterstützt, aber es wird kein Fehler ausgegeben. Die `CAST`-Funktion wird ignoriert. |
| [Zeitstempel](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Parsen einer Uhrzeitzeichenfolge als Zeitstempel zur Verwendung innerhalb einer `WHERE`-Klausel. |
| [Zum Zeitstempel](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Parsen einer Uhrzeitzeichenfolge als Zeitstempel für die Verwendung innerhalb einer `WHERE`-Klausel, wobei optional ein Format für diese Zeitzeichenfolge angegeben werden kann. |
| [Datum](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Parsen einer Datumszeichenfolge als Zeitstempel zur Verwendung innerhalb einer `WHERE`-Klausel. |
| [Bis heute](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Parsen einer Datumszeichenfolge als Zeitstempel für die Verwendung innerhalb einer `WHERE`-Klausel, wobei optional ein Format für diese Datumszeichenfolge angegeben werden kann. |

{style="table-layout:auto"}

### Dimension-Funktionsunterstützung

Diese Funktionen können für Dimensionen in der `WHERE`- oder `SELECT`-Klausel oder in bedingten Metriken verwendet werden.

**Zeichenfolgen-Funktionen**

| Funktion | Beispiel | Details |
|---|---|---|
| [lower](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. |

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
| [Extrahieren](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. Verwenden Sie die Element-ID anstelle des Werts für einige Teile dieser Funktion, wo Sie die Nummer und nicht den Anzeigenamen benötigen.<br/>Folgende Teile werden unterstützt:<br>-Suchbegriffe: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>-Zeichenfolgen: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` oder `'MINUTE'`. |
| [Datum (Teil)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. Verwenden Sie die Element-ID anstelle des Werts für einige Teile dieser Funktion, wo Sie die Nummer und nicht den Anzeigenamen benötigen.<br/>Unterstützte Zeichenfolgenteile sind: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`o der `'MINUTE'`. |
| [Datum (abgeschnitten)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld.<br/>Folgende Zeichenfolgengranularitäten werden unterstützt: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` oder `'MINUTE'`. |

{style="table-layout:auto"}

### Teilweise Unterstützung

Einige SQL-Funktionen werden von der BI-Erweiterung nur teilweise unterstützt und geben nicht dieselben Ergebnisse zurück, die Sie bei anderen Datenbanken sehen.  Diese spezifische Funktion wird in SQL verwendet, die von verschiedenen BI-Tools generiert wurde, für die die BI-Erweiterung keine exakte Übereinstimmung aufweist. Daher konzentriert sich die BI-Erweiterung auf eine begrenzte Implementierung, die die minimale Verwendung von BI-Tools abdeckt, ohne Fehler auszulösen. Weitere Informationen finden Sie in der Tabelle unten.

| Funktion | Beispiel | Details |
|---|---|---|
| MIN() UND MAX() | ``MIN(daterange)`` oder <br/> ``MAX(daterange)`` | `MIN()` von `timestamp`, `daterange` oder einem der `daterangeX` wie `daterangeday` wird vor 2 Jahren zurückkehren.<br/><br/> `MAX()` am `timestamp`, `daterange` oder einem der `daterangeX` wie `daterangeday` wird das aktuelle Datum mit der aktuellen Uhrzeit zurückgegeben.<br/><br/>`MIN()` oder `MAX()` für eine andere Dimension, Metrik oder einen anderen Ausdruck geben 0 zurück. |

{style="table-layout:auto"}
