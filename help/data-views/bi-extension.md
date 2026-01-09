---
title: Customer Journey Analytics-BI-Erweiterung
description: Erfahren Sie, wie Sie mit Power BI oder Tableau Desktop mithilfe der Customer Journey Analytics-BI-Erweiterung auf Datenansichten zugreifen können.
solution: Customer Journey Analytics
feature: BI Extension
role: Admin
exl-id: ab7e1f15-ead9-46b7-94b7-f81802f88ff5
source-git-commit: 0d8da0f61e6494801ed3a09823b2f3b7c1bed7a9
workflow-type: tm+mt
source-wordcount: '3249'
ht-degree: 89%

---

# Customer Journey Analytics-BI-Erweiterung

{{select-package}}

Der [!DNL Customer Journey Analytics BI extension] ermöglicht SQL-Zugriff auf [Datenansichten](./data-views.md), die Sie in Customer Journey Analytics definiert haben. Ihre Dateningenieurinnen und -ingenieure sowie Ihre Datenanalytikerinnen und -analytiker sind möglicherweise besser mit Power BI, Tableau Desktop oder anderen Business Intelligence- und Visualisierungs-Tools (im Folgenden „BI-Tools“ genannt) vertraut. Sie können jetzt Berichte und Dashboards basierend auf denselben Datenansichten erstellen, die Benutzerinnen und Benutzer von Customer Journey Analytics beim Erstellen ihrer Analysis Workspace-Projekte verwenden.

Der [Abfrage-Service](https://experienceleague.adobe.com/de/docs/experience-platform/query/home) von Adobe Experience Platform ist die SQL-Schnittstelle zu Daten, die im Data Lake von Experience Platform verfügbar sind. Wenn der [!DNL Customer Journey Analytics BI extension] aktiviert ist, wird die Funktionalität von [!DNL Query Service] erweitert, damit Ihre Datenansichten von Customer Journey Analytics als Tabellen oder Ansichten in einer [!DNL Query Service]-Sitzung zu sehen sind. Daher profitieren Business-Intelligence-Tools, die [!DNL Query Service] als Ihre PostgresSQL-Schnittstelle verwenden, nahtlos von dieser erweiterten Funktion.

Die wichtigsten Vorteile sind:

* Es ist nicht erforderlich, eine äquivalente Darstellung von Datenansichten aus Customer Journey Analytics im BI-Tool selbst zu erstellen. <br/>Unter [Datenansichten](data-views.md) finden Sie weitere Informationen zur Funktionalität von Datenansichten, um zu verstehen, was neu erstellt werden muss.
* Mehr Konsistenz bei Reporting und Analyse zwischen BI-Tools und Customer Journey Analytics.
* Kombinieren Sie Customer Journey Analytics-Daten mit anderen Datenquellen, die bereits in BI-Tools verfügbar sind.

## Voraussetzungen

Um diese Funktion zu verwenden, können Sie befristete oder unbefristete Anmeldedaten verwenden, um BI-Tools mit der [!DNL Customer Journey Analytics BI extension] zu verbinden. Das [Handbuch zu Anmeldedaten](https://experienceleague.adobe.com/de/docs/experience-platform/query/ui/credentials) enthält weitere Informationen zum Festlegen befristeter oder unbefristeter Anmeldeinformationen.
Im Folgenden finden Sie zusätzliche Schritte zum Einrichten der erforderlichen Berechtigungen.
<!---   Enable the [!UICONTROL Customer Journey Analytics BI extension] in your Experience Platform organization. -->

### Ablaufende Anmeldeinformationen

Um ablaufende Anmeldeinformationen zu verwenden, können Sie wie folgt vorgehen:

* Zugriff auf Experience Platform und Customer Journey Analytics gewähren.
* Gewähren Sie Produktadministratorzugriff auf Customer Journey Analytics, damit Sie Verbindungen und Datenansichten anzeigen, bearbeiten, aktualisieren oder löschen können.

Oder Sie können:

* Zugriff auf die Datenansichten gewähren, auf die Sie zugreifen möchten.
* Zugriff auf die Customer Journey Analytics-BI-Erweiterung gewähren.

### Unbefristete Anmeldedaten

So verwenden Sie unbefristete Anmeldedaten:

* Erstellen Sie [unbefristete Anmeldedaten in Experience Platform](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/bi-extension#non-expiring-credentials).
* Gewähren Sie Zugriff auf die nicht ablaufenden Anmeldeinformationen, indem Sie die unter &quot;[&#x200B; Anmeldeinformationen“ &#x200B;](#Expiring-credentials) Schritte ausführen.

Unter [Customer Journey-Zugriffssteuerung](../technotes/access-control.md) finden Sie weitere Informationen, insbesondere zu [Zusätzlichen Produktadministratorberechtigungen](../technotes/access-control.md#product-admin-additional-permissions) und [Customer Journey Analytics-Berechtigungen in der Admin Console](../technotes/access-control.md#customer-journey-analytics-permissions-in-admin-console).


## Nutzung

Um die Funktion [!DNL Customer Journey Analytics BI extension] zu verwenden, können Sie SQL entweder direkt verwenden oder das Drag-and-Drop-Erlebnis verwenden, das im jeweiligen BI-Tool verfügbar ist.

### SQL

Sie können die Funktion direkt in SQL-Anweisungen verwenden, indem Sie entweder den Abfrage-Editor oder einen standardmäßigen Client der Befehlszeilenschnittstelle (CLI) von Postgres verwenden.

+++ Abfrage-Editor

In Adobe Experience Platform:

1. Wählen Sie **[!UICONTROL ** Abfragen **]** unter **[!UICONTROL **&#x200B; DATEN-MANAGEMENT &#x200B;**]** in der linken Leiste aus.

1. Wählen Sie ![Abfrage erstellen](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL **&#x200B; Abfrage erstellen &#x200B;**]** aus.

1. Wählen Sie die `cja` für Ihre Sandbox aus der Liste der Datenbanken im Dropdown **[!UICONTROL Menü]** Datenbank“ aus. Zum Beispiel `prod:cja`.

1. Um die Abfrage auszuführen, geben Sie Ihre SQL-Anweisung ein und wählen Sie die Schaltfläche ![Wiedergabe](assets/Smock_Play_18_N.svg) (oder drücken Sie `[SHIFT]` + `[ENTER]`).

+++


+++ PostgresSQL-CLI

1. Suchen und Kopieren Ihrer PostgresSQL-Anmeldedaten in Adobe Experience Platform:

   1. Wählen Sie **[!UICONTROL ** Abfragen **]** aus der linken Leiste (unter **[!UICONTROL **&#x200B; DATEN-MANAGEMENT &#x200B;**]**) aus.

   1. Wählen Sie **[!UICONTROL **&#x200B; Anmeldeinformationen &#x200B;**]** aus der oberen Leiste aus.

   1. Wählen Sie die `cja` für Ihre Sandbox aus der Liste der Datenbanken im Dropdown **[!UICONTROL Menü]** Datenbank“ aus. Zum Beispiel `prod:cja`.

   1. Um die Befehlszeichenfolge zu kopieren, verwenden Sie ![Kopieren](assets/Smock_Copy_18_N.svg) im Abschnitt **[!UICONTROL **&#x200B; PSQL-Befehl &#x200B;**]**.

1. Öffnen Sie ein Befehls- oder Terminal-Fenster.

1. Um sich anzumelden und Ihre Abfragen auszuführen, fügen Sie die Befehlszeichenfolge in Ihr Terminal ein.

+++

Weitere Informationen finden Sie in der [Anleitung zur Benutzeroberfläche des Abfrage-Editors](https://experienceleague.adobe.com/de/docs/experience-platform/query/ui/user-guide).


### BI-Tools

Derzeit wird die [!DNL Customer Journey Analytics BI extension] für die unten aufgeführten Tools unterstützt und getestet. Andere BI-Tools, die die PSQL-Oberfläche verwenden, funktionieren möglicherweise ebenfalls, werden aber noch nicht offiziell unterstützt.

+++ Power BI

1. Suchen der Details Ihrer PostgresSQL-Anmeldedaten in Adobe Experience Platform:

   1. Wählen Sie **[!UICONTROL ** Abfragen **]** aus der linken Leiste (unter **[!UICONTROL **&#x200B; DATEN-MANAGEMENT &#x200B;**]**) aus.

   1. Wählen Sie **[!UICONTROL **&#x200B; Anmeldeinformationen &#x200B;**]** aus der oberen Leiste aus.

   1. Wählen Sie die `cja` für Ihre Sandbox aus der Liste der Datenbanken im Dropdown **[!UICONTROL Menü]** Datenbank“ aus. Zum Beispiel `prod:cja`.

   1. Verwenden Sie ![Kopieren](assets/Smock_Copy_18_N.svg), um jeden Parameter der Postgres-Anmeldeinformationen ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Datenbank], [!UICONTROL Benutzername] und andere) zu kopieren, wenn sie in Power BI benötigt werden.

1. In Power BI:

   1. Wählen Sie im Hauptfenster **[!UICONTROL **&#x200B; Daten abrufen &#x200B;**]** aus der oberen Symbolleiste aus.

   1. Wählen Sie **[!UICONTROL Mehr...]** in der linken Leiste aus. 

   1. Suchen Sie im Bildschirm **Daten abrufen** nach `PostgresSQL` und wählen Sie die **[!UICONTROL **&#x200B; PostgresSQL-Datenbank &#x200B;**]** aus der Liste aus.

   1. Im Dialogfeld **[!UICONTROL **&#x200B; PostgresSQL-Datenbank &#x200B;**]**:

      1. Fügen Sie den Parameter **[!UICONTROL ** Host **]** aus den [!UICONTROL Anmeldeinformationen] von Experience Platform-Abfragen in das Textfeld **[!UICONTROL **&#x200B; Server &#x200B;**]** ein.

      1. Fügen Sie den Parameter **[!UICONTROL ** Datenbank **]** aus den [!UICONTROL Anmeldedaten] von Experience Platform-Abfragen in das Textfeld **[!UICONTROL **&#x200B; Datenbank &#x200B;**]** ein.

         Fügen Sie `?FLATTEN` zum Parameter **[!UICONTROL **&#x200B; Datenbank &#x200B;**]** hinzu, damit er sich beispielsweise liest wie `prod:cja?FLATTEN`. Weitere Informationen finden Sie unter [Reduzieren verschachtelter Datenstrukturen für die Verwendung mit BI-Tools von Drittanbietern](https://experienceleague.adobe.com/de/docs/experience-platform/query/key-concepts/flatten-nested-data).

      1. Wenn Sie zur Wahl des Modus **[!UICONTROL Datenkonnektivität]** aufgefordert werden, wählen Sie **[!UICONTROL DirectQuery]** aus.

      1. Sie werden aufgefordert, **[!UICONTROL Benutzername]** und **[!UICONTROL Passwort]** einzugeben. Verwenden Sie die entsprechenden Parameter aus den [!UICONTROL Anmeldeinformationen] von Experience Platform-Abfragen.


   1. Nach erfolgreicher Anmeldung sehen Sie die Datenansichtstabellen von Customer Journey Analytics im **[!UICONTROL **&#x200B; Navigator &#x200B;**]** von Power BI. 

   1. Wählen Sie die Datenansichtstabellen aus, die Sie verwenden möchten, und wählen Sie dann **[!UICONTROL **&#x200B; Laden &#x200B;**]** aus.

   Alle Dimensionen und Metriken, die mit einer oder mehreren ausgewählten Tabellen verknüpft sind, werden im rechten Bereich angezeigt und können in Ihren Visualisierungen verwendet werden.

   Weitere Informationen finden Sie unter [Verbinden von Power BI mit dem Abfrage-Service](https://experienceleague.adobe.com/de/docs/experience-platform/query/clients/power-bi). Ein ausführliches Beispiel finden Sie unter [Anwendungsfälle für BI-Erweiterungen](/help/use-cases/data-views/bi-extension-usecases.md).

+++

+++Tableau Desktop

1. Suchen der Details Ihrer PostgresSQL-Anmeldedaten in Adobe Experience Platform:

   1. Wählen Sie **[!UICONTROL ** Abfragen **]** aus der linken Leiste (unter **[!UICONTROL **&#x200B; DATEN-MANAGEMENT &#x200B;**]**) aus.

   1. Wählen Sie **[!UICONTROL **&#x200B; Anmeldeinformationen &#x200B;**]** aus der oberen Leiste aus.

   1. Wählen Sie die `cja` für Ihre Sandbox aus der Liste der Datenbanken im Dropdown **[!UICONTROL Menü]** Datenbank“ aus. Zum Beispiel `prod:cja`.

   1. Verwenden Sie ![Kopieren](assets/Smock_Copy_18_N.svg), um jeden Parameter der Postgres-Anmeldedaten ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Datenbank], [!UICONTROL Benutzername] und andere) bei Bedarf in Tableau Desktop zu kopieren.

1. In Tableau Desktop:

   1. Wählen Sie **[!UICONTROL ** Mehr **]** aus **[!UICONTROL **&#x200B; Zu einem Server &#x200B;**]** in der linken Leiste aus.

   1. Wählen Sie **[!UICONTROL **&#x200B; PostgresSQL &#x200B;**]** aus der Liste aus.

   1. Im Dialogfeld [!UICONTROL PostgresSQL]:

      1. Fügen Sie den Parameter **[!UICONTROL ** Host **]** aus den [!UICONTROL Anmeldedaten] von Experience Platform-Abfragen in das Textfeld **[!UICONTROL **&#x200B; Server &#x200B;**]** ein.

      1. Fügen Sie den Parameter **[!UICONTROL ** Port **]** aus den [!UICONTROL Anmeldedaten] von Experience Platform-Abfragen in das Textfeld **[!UICONTROL **&#x200B; Port &#x200B;**]** ein.

      1. Fügen Sie den Parameter **[!UICONTROL ** Datenbank **]** aus den [!UICONTROL Anmeldedaten] von Experience Platform-Abfragen in das Textfeld **[!UICONTROL **&#x200B; Datenbank &#x200B;**]** ein.

         Fügen Sie `%3FFLATTEN` zum Parameter **[!UICONTROL **&#x200B; Datenbank &#x200B;**]** hinzu, damit er sich beispielsweise liest wie `prod:cja%3FFLATTEN`. Weitere Informationen finden Sie unter [Reduzieren verschachtelter Datenstrukturen für die Verwendung mit BI-Tools von Drittanbietern](https://experienceleague.adobe.com/de/docs/experience-platform/query/key-concepts/flatten-nested-data).

      1. Wählen Sie **[!UICONTROL ** Benutzername und Passwort **]** aus der Liste **[!UICONTROL **&#x200B; Authentifizierung &#x200B;**]** aus.

      1. Fügen Sie den Parameter **[!UICONTROL ** Benutzername **]** aus den [!UICONTROL Anmeldeinformationen] von Experience Platform-Abfragen in das Textfeld **[!UICONTROL **&#x200B; Benutzername &#x200B;**]** ein.

      1. Fügen Sie den Parameter **[!UICONTROL ** Passwort **]** aus den [!UICONTROL Anmeldeinformationen] von Experience Platform-Abfragen in das Textfeld **[!UICONTROL **&#x200B; Passwort &#x200B;**]** ein.

      1. Wählen Sie **[!UICONTROL **&#x200B; Anmelden &#x200B;**]** aus.

   1. Datenansichten von Customer Journey Analytics werden als Tabellen in der Liste **[!UICONTROL **&#x200B; Tabellen &#x200B;**]** angezeigt.

   1. Ziehen Sie die Tabellen, die Sie verwenden möchten, auf die Arbeitsfläche.

   Sie können jetzt mit den Daten aus den Datenansichtstabellen arbeiten, um Ihre Berichte und Visualisierungen zu erstellen.

   Weitere Informationen finden Sie unter [Verbinden von Tableau mit dem Abfrage-Service](https://experienceleague.adobe.com/de/docs/experience-platform/query/clients/tableau). Ein ausführliches Beispiel finden Sie unter [Anwendungsfälle für BI-Erweiterungen](/help/use-cases/data-views/bi-extension-usecases.md).

+++

+++ Looker

1. Suchen der Details Ihrer PostgresSQL-Anmeldedaten in Adobe Experience Platform:

   1. Wählen Sie **[!UICONTROL ** Abfragen **]** aus der linken Leiste (unter **[!UICONTROL **&#x200B; DATEN-MANAGEMENT &#x200B;**]**) aus.

   1. Wählen Sie **[!UICONTROL **&#x200B; Anmeldeinformationen &#x200B;**]** aus der oberen Leiste aus.

   1. Wählen Sie die `cja` für Ihre Sandbox aus der Liste der Datenbanken im Dropdown **[!UICONTROL Menü]** Datenbank“ aus. Zum Beispiel `prod:cja`.

   1. Verwenden Sie ![Kopieren](assets/Smock_Copy_18_N.svg), um jeden Parameter der Postgres-Anmeldedaten ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Datenbank], [!UICONTROL Benutzername] und andere) bei Bedarf in Looker zu kopieren.

1. In Looker:

   1. Wählen Sie **[!UICONTROL Admin]** in der linken Leiste aus.
   1. Wählen Sie **[!UICONTROL Verbindungen]** aus.
   1. Wählen Sie **[!UICONTROL Datensätze hinzufügen]** aus.
   1. Fügen Sie im Bildschirm **[!UICONTROL Datenbank mit Looker verbinden]** die entsprechenden Werte ein, wenn Sie Ihre neue Verbindung einrichten. Stellen Sie sicher, dass Sie **[!UICONTROL PostgreSQL 9.5+]** als Dialekt auswählen.
   1. Wählen Sie **[!UICONTROL Testen]** aus, um Ihre Verbindung zu testen.
   1. Klicken Sie bei Erfolg auf **[!UICONTROL Aktualisieren]**, um Ihre Verbindung zu speichern.

   Sie können jetzt mit den Daten aus den Datenansichtstabellen arbeiten, um Ihre Berichte und Visualisierungen zu erstellen.

   Weitere Informationen finden Sie unter [Verbinden von Looker mit dem Abfrage-Service](https://experienceleague.adobe.com/de/docs/experience-platform/query/clients/looker). Ein ausführliches Beispiel finden Sie unter [Anwendungsfälle für BI-Erweiterungen](/help/use-cases/data-views/bi-extension-usecases.md).

+++

+++ Jupyter Notebook

1. Suchen der Details Ihrer PostgresSQL-Anmeldedaten in Adobe Experience Platform:

   1. Wählen Sie **[!UICONTROL ** Abfragen **]** aus der linken Leiste (unter **[!UICONTROL **&#x200B; DATEN-MANAGEMENT &#x200B;**]**) aus.

   1. Wählen Sie **[!UICONTROL **&#x200B; Anmeldeinformationen &#x200B;**]** aus der oberen Leiste aus.

   1. Wählen Sie die `cja` für Ihre Sandbox aus der Liste der Datenbanken im Dropdown **[!UICONTROL Menü]** Datenbank“ aus. Zum Beispiel `prod:cja`.

   1. Verwenden Sie ![Kopieren](assets/Smock_Copy_18_N.svg), um jeden Parameter der Postgres-Anmeldedaten ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Datenbank], [!UICONTROL Benutzername] und andere) zu kopieren, wenn sie in Jupyter Notebook werden.

1. In Jupyter Notebook:

   1. Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken verwenden.
   1. Verwenden Sie beim Einrichten und Ausführen der Verbindung die richtigen Werte.
   1. Testen Sie die Verbindung, indem Sie eine entsprechende Abfrage ausführen.

   Nach erfolgreicher Ausführung können Sie mit den Daten arbeiten, um Ihre Berichte und Visualisierungen zu erstellen.

   Weitere Informationen finden Sie unter [Verbinden von Jupyter Notebook mit dem Abfrage-Service](https://experienceleague.adobe.com/de/docs/experience-platform/query/clients/jupyter-notebook). Ein ausführliches Beispiel finden Sie unter [Anwendungsfälle für BI-Erweiterungen](/help/use-cases/data-views/bi-extension-usecases.md).

+++

+++ RStudio

1. Suchen der Details Ihrer PostgresSQL-Anmeldedaten in Adobe Experience Platform:

   1. Wählen Sie **[!UICONTROL ** Abfragen **]** aus der linken Leiste (unter **[!UICONTROL **&#x200B; DATEN-MANAGEMENT &#x200B;**]**) aus.

   1. Wählen Sie **[!UICONTROL **&#x200B; Anmeldeinformationen &#x200B;**]** aus der oberen Leiste aus.

   1. Wählen Sie die `cja` für Ihre Sandbox aus der Liste der Datenbanken im Dropdown **[!UICONTROL Menü]** Datenbank“ aus. Zum Beispiel `prod:cja`.

   1. Verwenden Sie ![Kopieren](assets/Smock_Copy_18_N.svg), um jeden Parameter der Postgres-Anmeldedaten ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Datenbank], [!UICONTROL Benutzername] und andere) zu kopieren, wenn sie in Jupyter Notebook werden.

1. In RStudio:

   1. Stellen Sie sicher, dass Sie die erforderlichen Bibliotheken verwenden.
   1. Verwenden Sie beim Einrichten und Ausführen der Verbindung die richtigen Werte.
   1. Testen Sie die Verbindung, indem Sie eine entsprechende Abfrage ausführen.

   Nach erfolgreicher Ausführung können Sie mit den Daten arbeiten, um Ihre Berichte und Visualisierungen zu erstellen.

   Weitere Informationen finden Sie unter [Verbinden von RStudio mit dem Abfrage-Service](https://experienceleague.adobe.com/de/docs/experience-platform/query/clients/rstudio). Ein ausführliches Beispiel (in dem stattdessen das RPostgres-Paket verwendet wird) finden Sie unter [Anwendungsfälle für BI-Erweiterungen](/help/use-cases/data-views/bi-extension-usecases.md).

+++

Siehe [Verbinden von Clients mit dem Abfrage-Service](https://experienceleague.adobe.com/de/docs/experience-platform/query/clients/overview), um einen Überblick und weitere Informationen über die verschiedenen verfügbaren Tools zu erhalten.

Unter [Anwendungsfälle](/help/use-cases/data-views/bi-extension-usecases.md) erfahren Sie, wie Sie eine Reihe von Anwendungsfällen mit der Customer Journey Analytics-BI-Erweiterung durchführen.

## Funktionalität

Standardmäßig wird für Ihre Datenansichten ein tabellensicherer Name aus ihrem Anzeigenamen generiert. Beispielsweise hat die Datenansicht mit dem Namen [!UICONTROL Meine Web-Daten] den Anzeigenamen `my_web_data_view`. Sie können einen bevorzugten Namen definieren, der in Ihrem BI-Tool für Ihre Datenansicht verwendet werden soll. Weitere Informationen finden Sie unter [Datenansichtseinstellungen](create-dataview.md#settings).

Wenn Sie die Datenansichts-IDs als Tabellennamen verwenden möchten, können Sie beim Verbinden die optionale Einstellung für `CJA_USE_IDS` auf Ihren Datenbanknamen festlegen. Zum Beispiel zeigt `prod:cja?CJA_USE_IDS` Ihre Datenansichten mit Namen wie `dv_ABC123` an.

### Data Governance

Einstellungen in Bezug auf die Data Governance in Customer Journey Analytics werden von Adobe Experience Platform übernommen. Die Integration zwischen Customer Journey Analytics und Adobe Experience Platform Data Governance ermöglicht die Kennzeichnung sensibler Daten von Customer Journey Analytics und die Durchsetzung von Datenschutzrichtlinien.

Datenschutz-Label und -richtlinien, die für von Experience Platform genutzte Datensätze erstellt wurden, können im Datenansichts-Workflow von Customer Journey Analytics angezeigt werden. Daher zeigen Daten, die mit der [!DNL Customer Journey Analytics BI extension] abgefragt wurden, die entsprechenden Warnungen oder Fehler an, wenn sie nicht den definierten Datenschutzbeschriftungen und Richtlinien entsprechen.

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

Standardmäßig verwendet das Schema Ihrer Datenansichten verschachtelte Strukturen wie die ursprünglichen XDM-Schemata. Die Integration unterstützt auch die Option `FLATTEN`. Mit dieser Option können Sie erzwingen, dass das Schema für die Datenansichten (und jede andere Tabelle in der Sitzung) reduziert wird. Die Reduzierung ermöglicht eine einfachere Verwendung in BI-Tools, die keine strukturierten Schemata unterstützen. Weitere Informationen finden Sie unter [Arbeiten mit verschachtelten Datenstrukturen im Abfrage-Service](https://experienceleague.adobe.com/de/docs/experience-platform/query/key-concepts/flatten-nested-data).


### Standardwerte und Einschränkungen

Die folgenden zusätzlichen Standardwerte und Einschränkungen gelten für die Verwendung der BI-Erweiterung:

* Die BI-Erweiterung erfordert eine Zeilenbegrenzung für die Abfrageergebnisse. Der Standardwert ist 50. Sie können diesen jedoch in SQL mit `LIMIT n` überschreiben, wobei `n` 1 - 50000 ist.
* Die BI-Erweiterung erfordert einen Datumsbereich, um die für Berechnungen verwendeten Zeilen zu begrenzen. Der Standardwert ist die letzten 30 Tage. Sie können diesen jedoch in Ihrer SQL-`WHERE`-Klausel überschreiben, indem Sie die speziellen Spalten [`timestamp`](#timestamp) oder [`daterange`](#date-range) verwenden.
* Die BI-Erweiterung erfordert Aggregatabfragen. Sie können kein SQL wie `SELECT * FROM ...` verwenden, um die rohen, zugrunde liegenden Zeilen abzurufen. Ihre Aggregatabfragen sollten auf allgemeiner Ebene Folgendes verwenden:
   * Auswählen von Gesamtsummen mit `SUM` und/oder `COUNT`.<br/> Zum Beispiel `SELECT SUM(metric1), COUNT(*) FROM ...`
   * Auswählen von Metriken, die nach einer Dimension aufgeschlüsselt sind. <br/>Zum Beispiel `SELECT dimension1, SUM(metric1), COUNT(*) FROM ... GROUP BY dimension1`
   * Auswählen unterschiedlicher Metrikwerte.<br/>Zum Beispiel `SELECT DISTINCT dimension1 FROM ...`

     Weitere Informationen finden Sie unter [Unterstütztes SQL](#supported-sql).


### Unterstützte SQL

Die vollständige Referenz dazu, welcher SQL-Typ unterstützt wird, finden Sie unter [SQL-Referenz für den Abfrage-Service](https://experienceleague.adobe.com/de/docs/experience-platform/query/sql/overview).

Beispiele für SQL, das Sie verwenden können, finden Sie in der folgenden Tabelle.

+++ Beispiele

<table style="table-layout:auto">
    <thead>
        <tr>
            <th>Muster</th>
            <th>Beispiel</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Schema-Erkennung </td>
            <td>
                <pre><code>SELECT * FROM dv1 WHERE 1=0</code></pre>
            </td>
        </tr>
        <tr>
            <td>Mit Rangfolge oder Aufschlüsselung </td>
            <td>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02' AND
  filterId = '12345'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02' AND
  AND (dim2 = 'A' OR dim3 IN ('X', 'Y', 'Z'))
GROUP BY dim1</code></pre>
            </td>
        </tr>
        <tr>
            <td><code>HAVING</code> Klausel </td>
            <td>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1
HAVING m1 > 100</code></pre>
            </td>
        </tr>
        <tr>
            <td>Eindeutige, obere 
Dimensionswerte </td>
            <td>
                <pre><code>SELECT DISTINCT dim1 FROM dv1</code></pre>
                <pre><code>SELECT dim1 AS dv1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1 AS dv1
FROM dv1
WHERE `timestamp` >= '2022-01-01' AND `timestamp` < '2022-01-02'
GROUP BY dim1
ORDER BY SUM(metric1)
LIMIT 15</code></pre>
            </td>
        </tr>
        <tr>
            <td>Metriksummen </td>
            <td>
                <pre><code>SELECT SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'</code></pre>
            </td>
        </tr>
        <tr>
            <td>Aufschlüsselungen
mehrere Dimensionen
und obere eindeutige Werte </td>
            <td>
                <pre><code>SELECT dim1, dim2, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1, dim2</code></pre>
                <pre><code>SELECT dim1, dim2, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY 1, 2
ORDER BY 1, 2</code></pre>
                <pre><code>SELECT DISTINCT dim1, dim2
FROM dv1</code></pre>
            </td>
        </tr>
        <tr>
            <td>Unterauswahl:
Zusätzliche Ergebnisse
filtern </td>
            <td>
                <pre><code>SELECT dim1, m1
FROM (
  SELECT dim1, SUM(metric1) AS m1
  FROM dv1
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'</br>  GROUP BY dim1
)
WHERE dim1 in ('A', 'B')</code></pre>
            </td>
        </tr>
        <tr>
            <td>Unterauswahl:
Abfrage über
Datenansichten </td>
            <td>
                <pre><code>SELECT key, SUM(m1) AS total
FROM (
  SELECT dim1 AS key, SUM(metric1) AS m1
  FROM dv1
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  GROUP BY dim1
<br>
  UNION
<br>
  SELECT dim2 AS key, SUM(m1) AS m1
  FROM dv2
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  GROUP BY dim2
)
GROUP BY key
ORDER BY total</code></pre>
            </td>
        </tr>
        <tr>
            <td>Unterauswahl: 
Geschichtete Quelle, 
Filterung 
und Aggregation </td>
            <td>Geschichtet, mit den Unterauswahlen:
<pre><code>SELECT rows.dim1, SUM(rows.m1) AS total
FROM (
  SELECT _.dim1,_.m1
  FROM (
    SELECT * FROM dv1
    WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  ) _
  WHERE _.dim1 in ('A', 'B', 'C')
) rows
GROUP BY 1
ORDER BY total</code></pre>
Ebenen, die CTE WITH verwenden:
<pre><code>WITH rows AS (
  WITH _ AS (
    SELECT * FROM data_ares
    WHERE `timestamp` BETWEEN '2021-01-01' AND '2021-02-01'
  )
  SELECT _.item, _.units FROM _
  WHERE _.item IS NOT NULL
)
SELECT rows.item, SUM(rows.units) AS units
FROM rows WHERE rows.item in ('A', 'B', 'C')
GROUP BY rows.item</code></pre>
        </td>
        </tr>
        <tr>
            <td>Wählt aus, wo die
Metriken vor
den Dimensionen erscheinen oder mit
den Dimensionen gemischt werden </td>
            <td>
                <pre><code>SELECT SUM(metric1) AS m1, dim1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY 2</code></pre>
            </td>
        </tr>
    </tbody>
</table>

+++

### Dimensionen

Sie können jede der Dimensionen auswählen, die standardmäßig verfügbar oder in der Datenansicht definiert sind. Sie wählen eine Dimension anhand ihrer ID aus.

### Metriken

Folgende Metriken stehen zur Auswahl:

* Metriken, die standardmäßig verfügbar sind;
* Metriken, die in der Datenansicht definiert wurden;
* berechnete Metriken, die mit der Datenansicht kompatibel sind, auf die die Benutzerin bzw. der Benutzer Zugriff hat.

Sie wählen eine Metrik anhand ihrer ID aus, die in einen `SUM(metric)`-Ausdruck eingeschlossen ist, wie Sie es mit jeder SQL-Quelle tun würden.

Sie können:

* `SELECT COUNT(*)` oder `COUNT(1)` verwenden, um die Metrik Vorfälle zu erhalten.
* `SELECT COUNT(DISTINCT dimension)` oder `SELECT APPROX_COUNT_DISTINCT(dimension)` verwenden, um die ungefähren eindeutigen Werte einer Dimension zu zählen. Details finden Sie unter [Zählen von eindeutigen Werten](#counting-distinct-values).
* [Inline-Berechnungen](#inline-calculations) verwenden, um Metriken spontan zu kombinieren und/oder mathematisch zu verarbeiten.

#### Zählen von eindeutigen Werten

Aufgrund der zugrunde liegenden Funktionsweise von Customer Journey Analytics ist die einzige Dimension, für die Sie die Anzahl der eindeutigen Werte genau bestimmen können, die Dimension `adobe_personid`. Die folgenden SQL-Ausdrücke `SELECT COUNT(DISTINCT adobe_personid)` oder `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` geben den Wert der Standardmetrik Personen zurück, die der Anzahl der eindeutigen Personen entspricht. Bei anderen Dimensionen wird eine ungefähre Zählung der eindeutigen Personen zurückgegeben.

#### Bedingte Metriken

Sie können eine `IF`- oder `CASE`-Klausel in die `SUM`- oder `COUNT`-Funktionen einbetten, um eine zusätzliche Segmentierung hinzuzufügen, die für eine ausgewählte Metrik spezifisch ist. Das Hinzufügen dieser Klauseln ähnelt dem Anwenden eines Segments auf eine Metrikspalte in einer Workspace-Berichtstabelle.

Beispiele:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN metric1 END) AS m1
```

#### Inline-Berechnungen

Sie können zusätzliche Mathematik auf Metrikausdrücke in `SELECT` anwenden. Statt die Mathematik in einer berechneten Metrik zu definieren, kann diese Mathematik verwendet werden. In der folgenden Tabelle ist aufgeführt, welche Arten von Ausdrücken unterstützt werden.

| Operator oder Funktion | Details |
|---|---|
| `+`, `-`, `*`, `/`, und `%` | Addieren, subtrahieren, multiplizieren, dividieren und modulo/Rest |
| `-X` oder `+X` | Ändern des Zeichens oder einer Metrik, wobei X der Metrikausdruck ist |
| `PI()` | Konstante π |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH` und `TANH` | Unäre mathematische Funktionen |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Binäre mathematische Funktionen |

{style="table-layout:auto"}

### Sonderspalten

#### Zeitstempel

Die spezielle Spalte `timestamp` wird verwendet, um die Datumsbereiche für die Abfrage bereitzustellen. Ein Datumsbereich kann durch einen `BETWEEN`-Ausdruck oder ein mit `AND` verbundenes Paar aus den Überprüfungen `timestamp` `>`, `>=`, `<`, `<=` definiert werden.
`timestamp` ist optional, und falls kein vollständiger Bereich angegeben wird, werden die Standardwerte verwendet:

* Wenn nur ein Minimum angegeben wird (`timestamp > X` oder ` timestamp >= X`), reicht der Bereich von X bis jetzt.
* Wenn nur ein Maximum angegeben wird (`timestamp < X` oder `timestamp <= X`), reicht der Bereich von X bis die 30 Tage vor X.
* Wenn nichts angegeben wird, umfasst der Bereich die letzten 30 Tage bis jetzt.

Der Zeitstempelbereich wird in der Rangfolgenanfrage in ein globales Segment für den Datumsbereich konvertiert.
Das Zeitstempelfeld kann auch als Datums-/Uhrzeitfunktion verwendet werden, um den Zeitstempel des Ereignisses zu analysieren und zu kürzen.

#### Datumsbereich

Die `daterange` Spalte funktioniert ähnlich wie `timestamp`. Die Segmentierung ist jedoch auf volle Tage beschränkt. `daterange` ist ebenfalls optional und hat denselben Standardbereich wie `timestamp`.
Das Feld `daterange` kann auch in Datums-/Uhrzeitfunktionen verwendet werden, um das Datum des Ereignisses zu analysieren und ggf. zu kürzen.

Die `daterangeName` Spalte kann verwendet werden, um Ihre Abfrage mithilfe eines benannten Datumsbereichs wie `Last Quarter` zu segmentieren.

>[!NOTE]
>
>Power BI unterstützt keine Metriken vom Typ `daterange`, die weniger als einen Tag umfassen (Stunde, 30 Minuten, 5 Minuten usw.).
>

#### Segment-ID

Die Spalte Speziell `filterId` ist optional und wird verwendet, um ein extern definiertes Segment auf die Abfrage anzuwenden. Das Anwenden eines extern definierten Segments auf eine Abfrage ähnelt dem Ziehen eines Segments in einen Bereich in Workspace. Es können mehrere Segment-IDs verwendet werden, indem sie `AND` werden.

Neben `filterId` können Sie `filterName` verwenden, um den Namen eines Segments anstelle der ID zu verwenden.

### Klausel „Where“

Die Klausel `WHERE` wird in drei Schritten umgesetzt:

1. Suche des Datumsbereichs aus dem Sonderfeld `timestamp`, `daterange` oder `daterangeName`.

1. Suchen Sie alle extern definierten `filterId` oder `filterName`, die in das Segment aufgenommen werden sollen.

1. Wandeln Sie die verbleibenden Ausdrücke in Ad-hoc-Segmente um.

Die Umsetzung erfolgt durch Parsen der ersten Ebene von `AND`s in der `WHERE`-Klausel. Jeder Ausdruck mit `AND` auf oberster Ebene muss mit einem der oben genannten übereinstimmen. Alles, was tiefer als die erste Ebene von `AND`s liegt oder wenn die `WHERE`-Klausel `OR`s auf der obersten Ebene verwendet, wird als Ad-hoc-Segment gehandhabt.

### Sortierreihenfolge

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
| [Umwandeln](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` oder <br/> `` `timestamp`::string `` | Typumwandlung wird derzeit nicht unterstützt, aber es wird kein Fehler ausgegeben. Die `CAST`-Funktion wird ignoriert. |
| [Zeitstempel](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Parsen einer Uhrzeitzeichenfolge als Zeitstempel zur Verwendung innerhalb einer `WHERE`-Klausel. |
| [Bis Zeitstempel](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Parsen einer Uhrzeitzeichenfolge als Zeitstempel für die Verwendung innerhalb einer `WHERE`-Klausel, wobei optional ein Format für diese Zeitzeichenfolge angegeben werden kann. |
| [Datum](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Parsen einer Datumszeichenfolge als Zeitstempel zur Verwendung innerhalb einer `WHERE`-Klausel. |
| [Bis Datum](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Parsen einer Datumszeichenfolge als Zeitstempel für die Verwendung innerhalb einer `WHERE`-Klausel, wobei optional ein Format für diese Datumszeichenfolge angegeben werden kann. |

{style="table-layout:auto"}

### Unterstützung für Dimensionsfunktionen

Diese Funktionen können für Dimensionen in der `WHERE`- oder `SELECT`-Klausel oder in bedingten Metriken verwendet werden.

**Zeichenfolgen-Funktionen**

| Funktion | Beispiel | Details |
|---|---|---|
| [Kleinschreibung](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. |

{style="table-layout:auto"}

**Funktionen für Datum/Uhrzeit**

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
| [Date (part)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld. Verwenden Sie die Element-ID anstelle des Werts für einige Teile dieser Funktion, wo Sie die Nummer und nicht den Anzeigenamen benötigen.<br/>Unterstützte Zeichenfolgenteile sind: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`o der `'MINUTE'`. |
| [Datum (gekürzt)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Generiert eine dynamische Dimensionsidentität für das übergebene Feld.<br/>Folgende Zeichenfolgengranularitäten werden unterstützt: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` oder `'MINUTE'`. |

{style="table-layout:auto"}

### Teilweise Unterstützung

Einige SQL-Funktionen werden von der BI-Erweiterung nur teilweise unterstützt und geben nicht dieselben Ergebnisse zurück, die Sie bei anderen Datenbanken sehen.  Diese spezifische Funktion wird in SQL verwendet, das von verschiedenen BI-Tools generiert wurde, für die die BI-Erweiterung keine exakte Übereinstimmung aufweist. Daher konzentriert sich die BI-Erweiterung auf eine begrenzte Implementierung, die die minimale Verwendung von BI-Tools abdeckt, ohne Fehler auszulösen. Weitere Informationen finden Sie in der Tabelle unten.

| Funktion | Beispiel | Details |
|---|---|---|
| MIN() und MAX() | ``MIN(daterange)`` oder <br/> ``MAX(daterange)`` | `MIN()` für `timestamp`, `daterange` oder eines der Elemente vom Typ `daterangeX` wie `daterangeday` gibt die letzten zwei Jahre zurück.<br/><br/> `MAX()` für `timestamp`, `daterange` oder eines der Elemente vom Typ `daterangeX` wie `daterangeday` gibt das aktuelle Datum/die aktuelle Uhrzeit zurück.<br/><br/>`MIN()` oder `MAX()` für eine andere Dimension, Metrik oder einen anderen Ausdruck gibt 0 zurück. |

{style="table-layout:auto"}
