---
title: Anwendungsbeispiele für die BI-Erweiterung im Customer Journey Analytics
description: Mehrere Anwendungsfälle, die zeigen, wie die BI-Erweiterung in verschiedenen BI-Tools unter Customer Journey Analytics verwendet wird
solution: Customer Journey Analytics
feature: Data Views
role: User
hide: true
hidefromtoc: true
source-git-commit: d65171873f68835de0628b95158f01713eaacb6b
workflow-type: tm+mt
source-wordcount: '2575'
ht-degree: 1%

---

# Anwendungsfälle für BI-Erweiterungen

Dieser Artikel enthält eine Reihe von Anwendungsfällen, die veranschaulichen, wie die Funktionalität der BI-Erweiterung über verschiedene BI-Tools hinweg verwendet werden kann.

Die folgenden Anwendungsfälle werden dokumentiert:

1. [Datenansichten verbinden und auflisten](#connect-and-list-data-views).
1. [Täglicher Trend](#daily-trend).
1. [Stündlicher Trend](#hourly-trend).
1. [Monatlicher Trend](#monthly-trend).
1. [Einzelne Dimension mit Rangansicht ](#single-dimension-ranked).
1. [Mehrere Dimensionen wurden nach Rang sortiert](#multiple-dimension-ranked).
1. [Zählen Sie unterschiedliche Dimensionswerte](#count-distinct-dimension-values).
1. [Verwenden Sie Datumsbereichsnamen, um ](#use-date-range-names-to-filter) zu filtern.
1. [Verwenden Sie Filternamen, um zu filtern](#use-filter-names-to-filter).
1. [Verwenden Sie Dimensionswerte zum Filtern von ](#use-dimension-values-to-filter).
1. [Sortieren](#sort).
1. [Beschränkungen](#limits).
1. [Zum FLATTEN oder nicht](#to-flatten-or-not).
1. [Dimension- und Metriktransformationen](#dimension-and-metric-transformations).
1. [Visualisierungen und Interaktionen](#visualizations-and-interactions).

Für jeden Anwendungsfall sind Anweisungen für die folgenden BI-Tools im Abschnitt **Details** verfügbar:

* Power BI Desktop (Version 2.136.1478.0 64-Bit (September 2024))
* Tableau-Desktop (Version 2024.1.5 (20241.24.0705.0334) 64-Bit)

Die Anweisungen beziehen sich auf eine Beispieldatenansicht mit dem Namen **[!UICONTROL public.cc_data_view]**, zwei Beispieldimensionen (**[!UICONTROL Produktname]** und **[!UICONTROL Produktkategorie]**) und zwei Beispielmetriken (**[!UICONTROL Einkäufe]** und **[!UICONTROL Kaufumsatz]**). Wenn Sie die Anweisungen durchgehen, ändern Sie diese Beispielobjekte gegebenenfalls für Ihre spezifische Umgebung.


## Datenansichten verbinden und auflisten

In diesem Anwendungsbeispiel wird die Verbindung vom BI-Tool zum Customer Journey Analytics eingerichtet und die verfügbaren Datenansichten aufgelistet, um die Verbindung erfolgreich zu testen.

+++ Details

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. Greifen Sie über die Experience Platform Query Service-Benutzeroberfläche auf die erforderlichen Anmeldeinformationen und Parameter zu.

   1. Navigieren Sie zu Ihrer Experience Platform-Sandbox.
   1. Wählen Sie ![Abfragen](/help/assets/icons/DataSearch.svg) **[!UICONTROL Abfragen]** in der linken Leiste aus.
   1. Wählen Sie die Registerkarte **[!UICONTROL Anmeldedaten]** in der Benutzeroberfläche **[!UICONTROL Abfragen]** aus.
   1. Wählen Sie `prod:cja` aus dem Dropdown-Menü **[!UICONTROL Datenbank]** aus.

      ![Anmeldedaten des Abfragedienstes](assets/queryservice-credentials.png)

1. Öffnen Sie Power BI Desktop.
1. Wählen Sie in der Hauptbenutzeroberfläche **[!UICONTROL Daten aus anderen Quellen abrufen]** aus.
1. Im Dialogfeld **[!UICONTROL Daten abrufen]** :
   ![Power BI PostgreSQL-Datenbank](assets/powerbi-postgresql.png)
   1. Suchen Sie nach der PostgreSQL-Datenbank ]**und wählen Sie sie aus.**[!UICONTROL 
   1. Wählen Sie **[!UICONTROL Verbinden]** aus.
1. Im Dialogfeld **[!UICONTROL PostgreSQL-Datenbank]** :
   ![Power BI Desktop Server- und Datenbankeinstellungen](assets/powerbi-serverdatabase.png)
   1. Verwenden Sie ![Kopieren](/help/assets/icons/Copy.svg) , um die Werte **[!UICONTROL Host]** und **[!UICONTROL Port]** aus der Experience Platform **[!UICONTROL Abfrage]** **[!UICONTROL Ablaufberechtigungen]** zu kopieren und einzufügen, getrennt durch `:` als Wert für **[!UICONTROL Server]**. Beispiel: `examplecompany.platform-query.adobe.io:80`.
   1. Verwenden Sie ![Kopieren](/help/assets/icons/Copy.svg) , um den Wert **[!UICONTROL Database]** aus der Experience Platform **[!UICONTROL Abfrage]** **[!UICONTROL Ablaufberechtigungen]** zu kopieren und einzufügen. Fügen Sie `?FLATTEN` zum Wert hinzu, den Sie einfügen. Zum Beispiel `prod:cja?FLATTEN`.
   1. Wählen Sie **[!UICONTROL DirectQuery]** als [!UICONTROL Datenkonnektivitätsmodus] aus.
   1. Wählen Sie **[!UICONTROL OK]** aus.
1. Im Dialogfeld **[!UICONTROL PostgreSQL-Datenbank]** - **[!UICONTROL Datenbank]** :
   ![Power BI Desktop User and Password](assets/powerbi-userpassword.png)
   1. Kopieren Sie mithilfe von ![Kopieren](/help/assets/icons/Copy.svg) die Werte **[!UICONTROL Benutzername]** und **[!UICONTROL Kennwort]** aus dem Feld Experience Platform **[!UICONTROL Abfrage]** **[!UICONTROL Ablaufberechtigungen]** in den Feldern **[!UICONTROL Benutzername]** und **[!UICONTROL Kennwort]**. Wenn Sie eine [nicht ablaufende Berechtigung](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect) verwenden, verwenden Sie das Kennwort Ihrer nicht ablaufenden Berechtigung.
   1. Stellen Sie sicher, dass das Dropdown-Menü für **[!UICONTROL Auswählen, welche Ebene diese Einstellungen auf]** anwenden soll, auf den zuvor definierten **[!UICONTROL Server]** festgelegt ist.
   1. Wählen Sie **[!UICONTROL Verbinden]** aus.
1. Im Dialogfeld **[!UICONTROL Navigator]** werden die Datenansichten abgerufen. Dieser Abruf kann einige Zeit in Anspruch nehmen. Nach dem Abrufen:
   ![Power BI Desktop Server-Ladedaten](assets/powerbi-navigator-load.png)
   1. Wählen Sie **[!UICONTROL public.cc_data_view]** aus der Liste im linken Bereich aus.
   1. Wählen Sie **[!UICONTROL laden]** aus.
1. Nach einiger Zeit werden die verfügbaren Metriken und Dimensionen im Bereich **[!UICONTROL Daten]** angezeigt.
   ![Laden der Power BI Desktop Server-Daten](assets/powerbi-navigator-loaded.png)


>[!TAB Tableau-Desktop]

1. Greifen Sie über die Experience Platform Query Service-Benutzeroberfläche auf die erforderlichen Anmeldeinformationen und Parameter zu.

   1. Navigieren Sie zu Ihrer Experience Platform-Sandbox.
   1. Wählen Sie ![Abfragen](/help/assets/icons/DataSearch.svg) **[!UICONTROL Abfragen]** in der linken Leiste aus.
   1. Wählen Sie die Registerkarte **[!UICONTROL Anmeldedaten]** in der Benutzeroberfläche **[!UICONTROL Abfragen]** aus.
   1. Wählen Sie `prod:cja` aus dem Dropdown-Menü **[!UICONTROL Datenbank]** aus.

      ![Anmeldedaten des Abfragedienstes](assets/queryservice-credentials.png)

1. Öffnen Sie Tableau.
1. Wählen Sie **[!UICONTROL PostgreSQL]** aus der linken Leiste unter **[!UICONTROL Auf einen Server]** aus. Wenn nicht verfügbar, wählen Sie **[!UICONTROL Mehr...]** und dann **[!UICONTROL PostgreSQL]** aus den **[!UICONTROL installierten Connectoren]**.
   ![Tableau-Connectoren](assets/tableau-connectors.png)
1. Im Dialogfeld **[!UICONTROL PostgreSQL]** auf der Registerkarte **[!UICONTROL Allgemein]**:
   ![Dialogfeld &quot;Anmelden für Tableau&quot;](assets/tableau-signin.png)
   1. Verwenden Sie ![Kopieren](/help/assets/icons/Copy.svg) , um den **[!UICONTROL Host]** aus der Experience Platform **[!UICONTROL Abfrage]** **[!UICONTROL Ablaufberechtigungen]** zu kopieren und in den **[!UICONTROL Server]** einzufügen.
   1. Verwenden Sie ![Kopieren](/help/assets/icons/Copy.svg) , um den **[!UICONTROL Port]** aus der Experience Platform **[!UICONTROL Abfrage]** **[!UICONTROL Ablaufberechtigungen]** zu kopieren und in den **[!UICONTROL Port]** einzufügen.
   1. Verwenden Sie ![Kopieren](/help/assets/icons/Copy.svg) , um die **[!UICONTROL Datenbank]** aus der Experience Platform **[!UICONTROL Abfrage]** **[!UICONTROL Ablaufberechtigungen]** zu kopieren und in die **[!UICONTROL Datenbank]** einzufügen. Fügen Sie `%3FFLATTEN` zum Wert hinzu, den Sie einfügen. Beispiel: `prod:cja%3FFLATTEN`.
   1. Wählen Sie **[!UICONTROL Benutzername und Kennwort]** aus dem Dropdown-Menü **[!UICONTROL Authentifizierung]**.
   1. Verwenden Sie ![Kopieren](/help/assets/icons/Copy.svg) , um den **[!UICONTROL Benutzernamen]** aus der Experience Platform **[!UICONTROL Abfrage]** **[!UICONTROL Ablaufberechtigungen]** zu kopieren und in den **[!UICONTROL Benutzernamen]** einzufügen.
   1. Verwenden Sie ![Kopieren](/help/assets/icons/Copy.svg) , um das **[!UICONTROL Kennwort]** aus der Experience Platform **[!UICONTROL Abfrage]** **[!UICONTROL Ablaufberechtigungen]** zu kopieren und in das **[!UICONTROL Kennwort]** einzufügen. Wenn Sie eine [nicht ablaufende Berechtigung](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect) verwenden, verwenden Sie das Kennwort Ihrer nicht ablaufenden Berechtigung.
   1. Stellen Sie sicher, dass **[!UICONTROL SSL erforderlich]** aktiviert ist.
   1. Wählen Sie **[!UICONTROL Anmelden]** aus.

   Es wird ein Dialogfeld **[!UICONTROL Progressing Request]** angezeigt, während Tableau Desktop die Verbindung validiert.
1. Im Hauptfenster sehen Sie in der Data Source-Ansicht im linken Bereich:
   * Der Name der Verbindung unter **[!UICONTROL Verbindungen]**.
   * Der Name der Datenbank unter **[!UICONTROL Datenbank]**.
   * Eine Liste von Tabellen unter **[!UICONTROL Tabelle]**.
     ![Tableau verbunden](assets/tableau-connected.png)
   1. Ziehen Sie den Eintrag **[!UICONTROL cc_data_view]** und legen Sie den Eintrag in der Hauptansicht ab, in der **[!UICONTROL Tabellen hierher ziehen]** steht.
1. Im Hauptfenster werden jetzt Details zur Datenansicht **[!UICONTROL cc_data_view]** angezeigt.
   ![Tableau verbunden](assets/tableau-validation.png)

>[!ENDTABS]

+++


## Täglicher Trend

In diesem Anwendungsfall möchten Sie eine Tabelle und eine einfache Linienvisualisierung anzeigen, die einen täglichen Trend der Vorkommen vom 1. Januar 2023 bis zum 31. Januar 2023 anzeigt.

+++ Details

>[!PREREQUISITES]
>
>Stellen Sie sicher, dass Sie eine [erfolgreiche Verbindung validiert haben und Datenansichten](#connect-and-list-data-views) für das BI-Tool auflisten können, für das Sie diesen Anwendungsfall ausprobieren möchten.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. Im Bereich **[!UICONTROL Daten]** :
   1. Wählen Sie die Dimension **[!UICONTROL daterangeday]** aus.
   1. Wählen Sie die Metrik **[!UICONTROL Vorkommen]** aus.

   Es wird eine Tabelle mit den Vorkommen für den aktuellen Monat angezeigt. Vergrößern Sie die Tabellenvisualisierung, um eine bessere Sichtbarkeit zu erzielen.

1. Im Bereich **[!UICONTROL Filter]** :

   1. Wählen Sie den Tag **[!UICONTROL daterangeday is (All)]** aus **[!UICONTROL Filtern auf dieser visuellen Seite]** aus.
   1. Wählen Sie **[!UICONTROL Erweiterte Filterung]** als **[!UICONTROL Filtertyp]** aus.
   1. Definieren Sie den Filter auf **[!UICONTROL Elemente anzeigen , wenn der Wert]** **[!UICONTROL auf oder nach]** `1/1/2023` **[!UICONTROL und]** **[!UICONTROL vor]** `1/2/2023.` liegt. Mit dem Kalendersymbol können Sie Datumsangaben auswählen.
   1. Wählen Sie **[!UICONTROL Filter anwenden]**.

   Die Tabelle wird mit dem angewendeten Filter **[!UICONTROL daterangeday]** aktualisiert.

1. Im Bereich **[!UICONTROL Visualisierungen]** :

   1. Wählen Sie die Visualisierung **[!UICONTROL Liniendiagramm]** aus.

   Eine Liniendiagrammvisualisierung ersetzt die Tabelle, wobei dieselben Daten wie die Tabelle verwendet werden.

   ![Power BI Desktop-Anwendungsfall 2 Datumsbereichfilter](assets/uc2-pbi-filter-daterange.png)

1. In der Liniendiagrammvisualisierung:

   1. Wählen Sie ![Mehr](/help/assets/icons/More.svg) aus.
   1. Wählen Sie im Kontextmenü **[!UICONTROL Als Tabelle anzeigen]** aus.

   Die Hauptansicht wird aktualisiert und zeigt sowohl eine Linienvisualisierung als auch eine Tabelle an.

   ![Power BI-Desktop-Nutzungsszenario 2 Endgültige Trend-Visualisierung pro Tag](assets/uc2-pbi-filter-final.png)

>[!TAB Tableau-Desktop]

1. Wählen Sie unten die Registerkarte **[!UICONTROL Blatt 1]** aus, um von **[!UICONTROL Datenquelle]** zu wechseln. In der Ansicht **[!UICONTROL Tabellenblatt 1]**:
   1. Ziehen Sie den Eintrag **[!UICONTROL Daterange]** aus der Liste **[!UICONTROL Tabellen]** in den Bereich **[!UICONTROL Daten]** und legen Sie den Eintrag in die Regale **[!UICONTROL Filter]**.
   1. Wählen Sie im Dialogfeld **[!UICONTROL Filterfeld \[Datumsbereich\]]** die Option **[!UICONTROL Datumsbereich]** aus und wählen Sie **[!UICONTROL Weiter >]**.
   1. Wählen Sie im Dialogfeld **[!UICONTROL Filter \[Datumsbereich]]** die Option **[!UICONTROL Datumsbereich]** aus und geben Sie einen Zeitraum von `01/01/2023` - `01/02/2023` an.

      ![Tableau-Desktop-Filter](assets/uc2-tableau-filter.png)

   1. Ziehen Sie **[!UICONTROL Daterangeday]** aus der Liste **[!UICONTROL Tabellen]** in den Bereich **[!UICONTROL Daten]** und legen Sie den Eintrag im Feld neben **[!UICONTROL Spalten]** ab.
      * Wählen Sie **[!UICONTROL Tag]** aus dem Dropdown-Menü **[!UICONTROL Daterangeday]** aus, damit der Wert auf **[!UICONTROL TAG(Daterangeday)]** aktualisiert wird.
   1. Ziehen Sie **[!UICONTROL Vorfälle]** aus der Liste **[!UICONTROL Tabellen (*Messnamen*)]** in den Bereich **[!UICONTROL Daten]** und legen Sie den Eintrag im Feld neben **[!UICONTROL Zeilen]** ab.
      * Die Werte werden automatisch in **[!UICONTROL SUM(Vorfälle)]** konvertiert.
   1. Ändern Sie **[!UICONTROL Standard]** in **[!UICONTROL Gesamte Ansicht]** aus dem Dropdown-Menü in der Symbolleiste.

      Ihre Tabellenansicht 1 sollte wie unten dargestellt aussehen.

      ![Tableau-Desktop-Diagramm](assets/uc2-tableau-graph.png)

1. Wählen Sie im Kontextmenü der Registerkarte **[!UICONTROL Blatt 1]** die Option **[!UICONTROL Duplizieren]** aus, um ein zweites Blatt zu erstellen.
1. Wählen Sie im Kontextmenü der Registerkarte **[!UICONTROL Blatt 1]** die Option **[!UICONTROL Umbenennen]** aus, um das Blatt in `Graph` umzubenennen.
1. Wählen Sie im Kontextmenü der Registerkarte **[!UICONTROL Blatt 1 (2)]** die Option **[!UICONTROL Umbenennen]** aus, um das Blatt in `Data` umzubenennen.
1. Stellen Sie sicher, dass das Blatt **[!UICONTROL Daten]** ausgewählt ist. In der Datenansicht:
   1. Wählen Sie oben rechts **[!UICONTROL Einblenden]** und dann **[!UICONTROL Texttabelle]** (obere linke Visualisierung) aus, um den Inhalt der Datenansicht in eine Tabelle zu ändern.
   1. Ziehen Sie **[!UICONTROL TAG(Daterangeday)]** aus **[!UICONTROL Spalten]** in **[!UICONTROL Zeilen]**.
   1. Ändern Sie **[!UICONTROL Standard]** in **[!UICONTROL Gesamte Ansicht]** aus dem Dropdown-Menü in der Symbolleiste.

      Ihre Ansicht **[!UICONTROL Daten]** sollte wie unten dargestellt aussehen.

      ![Tableau-Desktop-Daten](assets/uc2-tableau-data.png)

1. Wählen Sie die Registerkarte **[!UICONTROL Neues Dashboard]** (unten) aus, um eine neue Ansicht vom Typ **[!UICONTROL Dashboard 1]** zu erstellen. In der Ansicht **[!UICONTROL Dashboard 1]** :
   1. Ziehen Sie das Blatt **[!UICONTROL Diagramm]** aus dem Regal **[!UICONTROL Tabellen]** und legen Sie es in die Ansicht **[!UICONTROL Dashboard 1]**, in der *Tabellen hier ablegen* gelesen wird.
   1. Ziehen Sie das Blatt **[!UICONTROL Daten]** aus dem Regal **[!UICONTROL Tabellen]** unter das Blatt **[!UICONTROL Diagramm]** und legen Sie es in die Ansicht **[!UICONTROL Dashboard 1]**.
   1. Wählen Sie das Blatt **[!UICONTROL Daten]** in der Ansicht aus und ändern Sie **[!UICONTROL Gesamte Ansicht]** in **[!UICONTROL Breite korrigieren]**.

      Ihre Ansicht **[!UICONTROL Dashboard 1]** sollte wie unten dargestellt aussehen.

      ![Tableau-Desktop-Dashboard 1](assets/uc2-tableau-dashboard.png)

>[!ENDTABS]

+++


## Stündlicher Trend

In diesem Anwendungsfall möchten Sie eine Tabelle und eine einfache Linienvisualisierung anzeigen, die einen stündlichen Trend der Vorkommen für den 1. Januar 2023 anzeigt.

+++ Details

>[!PREREQUISITES]
>
>Stellen Sie sicher, dass Sie eine [erfolgreiche Verbindung validiert haben und Datenansichten](#connect-and-list-data-views) für das BI-Tool auflisten können, für das Sie diesen Anwendungsfall ausprobieren möchten.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

![Alert](/help/assets/icons/Alert.svg) Power BI versteht **nicht**, wie Datumszeitspalten verarbeitet werden. Daher werden Dimensionen wie **[!UICONTROL daterangehour]** und **[!UICONTROL daterangeminute]** nicht unterstützt.

>[!TAB Tableau-Desktop]

1. Wählen Sie unten die Registerkarte **[!UICONTROL Blatt 1]** aus, um von **[!UICONTROL Datenquelle]** zu wechseln. In der Ansicht **[!UICONTROL Tabellenblatt 1]**:
   1. Ziehen Sie den Eintrag **[!UICONTROL Daterange]** aus der Liste **[!UICONTROL Tabellen]** in den Bereich **[!UICONTROL Daten]** und legen Sie den Eintrag in die Regale **[!UICONTROL Filter]**.
   1. Wählen Sie im Dialogfeld **[!UICONTROL Filterfeld \[Datumsbereich\]]** die Option **[!UICONTROL Datumsbereich]** aus und wählen Sie **[!UICONTROL Weiter >]**.
   1. Wählen Sie im Dialogfeld **[!UICONTROL Filter \[Datumsbereich]]** die Option **[!UICONTROL Datumsbereich]** aus und geben Sie einen Zeitraum von `01/01/2023` - `02/01/2023` an.

      ![Tableau-Desktop-Filter](assets/uc3-tableau-filter.png)

   1. Ziehen Sie **[!UICONTROL Daterangehour]** aus der Liste **[!UICONTROL Tabellen]** in den Bereich **[!UICONTROL Daten]** und legen Sie den Eintrag im Feld neben **[!UICONTROL Spalten]** ab.
      * Wählen Sie **[!UICONTROL Mehr]** > **[!UICONTROL Stunden]** aus dem Dropdown-Menü **[!UICONTROL Daterangeday]** aus, damit der Wert auf **[!UICONTROL STUNDE(Daterangeday)]** aktualisiert wird.
   1. Ziehen Sie **[!UICONTROL Vorfälle]** aus der Liste **[!UICONTROL Tabellen (*Messnamen*)]** in den Bereich **[!UICONTROL Daten]** und legen Sie den Eintrag im Feld neben **[!UICONTROL Zeilen]** ab.
      * Die Werte werden automatisch in **[!UICONTROL SUM(Vorfälle)]** konvertiert.
   1. Ändern Sie **[!UICONTROL Standard]** in **[!UICONTROL Gesamte Ansicht]** aus dem Dropdown-Menü in der Symbolleiste.

      Ihre Tabellenansicht 1 sollte wie unten dargestellt aussehen.

      ![Tableau-Desktop-Diagramm](assets/uc3-tableau-graph.png)

1. Wählen Sie im Kontextmenü der Registerkarte **[!UICONTROL Blatt 1]** die Option **[!UICONTROL Duplizieren]** aus, um ein zweites Blatt zu erstellen.
1. Wählen Sie im Kontextmenü der Registerkarte **[!UICONTROL Blatt 1]** die Option **[!UICONTROL Umbenennen]** aus, um das Blatt in `Graph` umzubenennen.
1. Wählen Sie im Kontextmenü der Registerkarte **[!UICONTROL Blatt 1 (2)]** die Option **[!UICONTROL Umbenennen]** aus, um das Blatt in `Data` umzubenennen.
1. Stellen Sie sicher, dass das Blatt **[!UICONTROL Daten]** ausgewählt ist. In der Datenansicht:
   1. Wählen Sie oben rechts **[!UICONTROL Einblenden]** und dann **[!UICONTROL Texttabelle]** (obere linke Visualisierung) aus, um den Inhalt der Datenansicht in eine Tabelle zu ändern.
   1. Ziehen Sie **[!UICONTROL STUNDE(Daterangeday)]** aus **[!UICONTROL Spalten]** in **[!UICONTROL Zeilen]**.
   1. Ändern Sie **[!UICONTROL Standard]** in **[!UICONTROL Gesamte Ansicht]** aus dem Dropdown-Menü in der Symbolleiste.

      Ihre Ansicht **[!UICONTROL Daten]** sollte wie unten dargestellt aussehen.

      ![Tableau-Desktop-Daten](assets/uc3-tableau-data.png)

1. Wählen Sie die Registerkarte **[!UICONTROL Neues Dashboard]** (unten) aus, um eine neue Ansicht vom Typ **[!UICONTROL Dashboard 1]** zu erstellen. In der Ansicht **[!UICONTROL Dashboard 1]** :
   1. Ziehen Sie das Blatt **[!UICONTROL Diagramm]** aus dem Regal **[!UICONTROL Tabellen]** und legen Sie es in die Ansicht **[!UICONTROL Dashboard 1]**, in der *Tabellen hier ablegen* gelesen wird.
   1. Ziehen Sie das Blatt **[!UICONTROL Daten]** aus dem Regal **[!UICONTROL Tabellen]** unter das Blatt **[!UICONTROL Diagramm]** und legen Sie es in die Ansicht **[!UICONTROL Dashboard 1]**.
   1. Wählen Sie das Blatt **[!UICONTROL Daten]** in der Ansicht aus und ändern Sie **[!UICONTROL Gesamte Ansicht]** in **[!UICONTROL Breite korrigieren]**.

      Ihre Ansicht **[!UICONTROL Dashboard 1]** sollte wie unten dargestellt aussehen.

      ![Tableau-Desktop-Dashboard 1](assets/uc3-tableau-dashboard.png)


>[!ENDTABS]

+++


## Monatlicher Trend

In diesem Anwendungsfall möchten Sie eine Tabelle und eine einfache Linienvisualisierung anzeigen, die einen monatlichen Trend der Vorkommen für den 1. Januar 2023 bis zum 1. Januar 2024 anzeigt.

+++ Details

>[!PREREQUISITES]
>
>Stellen Sie sicher, dass Sie eine [erfolgreiche Verbindung validiert haben und Datenansichten](#connect-and-list-data-views) für das BI-Tool auflisten können, für das Sie diesen Anwendungsfall ausprobieren möchten.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. Im Bereich **[!UICONTROL Daten]** :
   1. Wählen Sie die Dimension **[!UICONTROL daterangemonth]** aus.
   1. Wählen Sie die Metrik **[!UICONTROL Vorkommen]** aus.

   Es wird eine Tabelle mit den Vorkommen für den aktuellen Monat angezeigt. Vergrößern Sie die Tabellenvisualisierung, um eine bessere Sichtbarkeit zu erzielen.

1. Im Bereich **[!UICONTROL Filter]** :

   1. Wählen Sie den Wert **[!UICONTROL daterangemonth is (All)]** aus **[!UICONTROL Filtern für diese visuelle Anzeige]** aus.
   1. Wählen Sie **[!UICONTROL Erweiterte Filterung]** als **[!UICONTROL Filtertyp]** aus.
   1. Definieren Sie den Filter auf **[!UICONTROL Elemente anzeigen , wenn der Wert]** **[!UICONTROL auf oder nach]** `1/1/2023` **[!UICONTROL und]** **[!UICONTROL vor]** `1/1/2024.` liegt. Mit dem Kalendersymbol können Sie Datumsangaben auswählen.
   1. Wählen Sie **[!UICONTROL Filter anwenden]**.

   Die Tabelle wird mit dem angewendeten Filter **[!UICONTROL daterangeday]** aktualisiert.

1. Im Bereich **[!UICONTROL Visualisierungen]** :

   1. Wählen Sie die Visualisierung **[!UICONTROL Liniendiagramm]** aus.

   Eine Liniendiagrammvisualisierung ersetzt die Tabelle, wobei dieselben Daten wie die Tabelle verwendet werden.

   ![Power BI Desktop-Anwendungsfall 2 Datumsbereichfilter](assets/uc4-pbi-filter-daterange.png)

1. In der Liniendiagrammvisualisierung:

   1. Wählen Sie ![Mehr](/help/assets/icons/More.svg) aus.
   1. Wählen Sie im Kontextmenü **[!UICONTROL Als Tabelle anzeigen]** aus.

   Die Hauptansicht wird aktualisiert und zeigt sowohl eine Linienvisualisierung als auch eine Tabelle an.

   ![Power BI-Desktop-Nutzungsszenario 2 Endgültige Trend-Visualisierung pro Tag](assets/uc4-pbi-filter-final.png)

>[!TAB Tableau-Desktop]

1. Wählen Sie unten die Registerkarte **[!UICONTROL Blatt 1]** aus, um von **[!UICONTROL Datenquelle]** zu wechseln. In der Ansicht **[!UICONTROL Tabellenblatt 1]**:
   1. Ziehen Sie den Eintrag **[!UICONTROL Daterange]** aus der Liste **[!UICONTROL Tabellen]** in den Bereich **[!UICONTROL Daten]** und legen Sie den Eintrag in die Regale **[!UICONTROL Filter]**.
   1. Wählen Sie im Dialogfeld **[!UICONTROL Filterfeld \[Datumsbereich\]]** die Option **[!UICONTROL Datumsbereich]** aus und wählen Sie **[!UICONTROL Weiter >]**.
   1. Wählen Sie im Dialogfeld **[!UICONTROL Filter \[Datumsbereich]]** die Option **[!UICONTROL Datumsbereich]** aus und geben Sie einen Zeitraum von `01/01/2023` - `01/01/2024` an.

      ![Tableau-Desktop-Filter](assets/uc4-tableau-filter.png)

   1. Ziehen Sie **[!UICONTROL Daterangeday]** aus der Liste **[!UICONTROL Tabellen]** in den Bereich **[!UICONTROL Daten]** und legen Sie den Eintrag im Feld neben **[!UICONTROL Spalten]** ab.
      * Wählen Sie **[!UICONTROL MONTH]** aus dem Dropdown-Menü **[!UICONTROL Daterangeday]** aus, damit der Wert auf **[!UICONTROL MONTH(Daterangeday)]** aktualisiert wird.
   1. Ziehen Sie **[!UICONTROL Vorfälle]** aus der Liste **[!UICONTROL Tabellen (*Messnamen*)]** in den Bereich **[!UICONTROL Daten]** und legen Sie den Eintrag im Feld neben **[!UICONTROL Zeilen]** ab.
      * Die Werte werden automatisch in **[!UICONTROL SUM(Vorfälle)]** konvertiert.
   1. Ändern Sie **[!UICONTROL Standard]** in **[!UICONTROL Gesamte Ansicht]** aus dem Dropdown-Menü in der Symbolleiste.

      Ihre Tabellenansicht 1 sollte wie unten dargestellt aussehen.

      ![Tableau-Desktop-Diagramm](assets/uc4-tableau-graph.png)

1. Wählen Sie im Kontextmenü der Registerkarte **[!UICONTROL Blatt 1]** die Option **[!UICONTROL Duplizieren]** aus, um ein zweites Blatt zu erstellen.
1. Wählen Sie im Kontextmenü der Registerkarte **[!UICONTROL Blatt 1]** die Option **[!UICONTROL Umbenennen]** aus, um das Blatt in `Graph` umzubenennen.
1. Wählen Sie im Kontextmenü der Registerkarte **[!UICONTROL Blatt 1 (2)]** die Option **[!UICONTROL Umbenennen]** aus, um das Blatt in `Data` umzubenennen.
1. Stellen Sie sicher, dass das Blatt **[!UICONTROL Daten]** ausgewählt ist. In der Datenansicht:
   1. Wählen Sie oben rechts **[!UICONTROL Einblenden]** und dann **[!UICONTROL Texttabelle]** (obere linke Visualisierung) aus, um den Inhalt der Datenansicht in eine Tabelle zu ändern.
   1. Ziehen Sie **[!UICONTROL MONTH(Daterangeday)]** aus **[!UICONTROL Spalten]** in **[!UICONTROL Zeilen]**.
   1. Ändern Sie **[!UICONTROL Standard]** in **[!UICONTROL Gesamte Ansicht]** aus dem Dropdown-Menü in der Symbolleiste.

      Ihre Ansicht **[!UICONTROL Daten]** sollte wie unten dargestellt aussehen.

      ![Tableau-Desktop-Daten](assets/uc4-tableau-data.png)

1. Wählen Sie die Registerkarte **[!UICONTROL Neues Dashboard]** (unten) aus, um eine neue Ansicht vom Typ **[!UICONTROL Dashboard 1]** zu erstellen. In der Ansicht **[!UICONTROL Dashboard 1]** :
   1. Ziehen Sie das Blatt **[!UICONTROL Diagramm]** aus dem Regal **[!UICONTROL Tabellen]** und legen Sie es in die Ansicht **[!UICONTROL Dashboard 1]**, in der *Tabellen hier ablegen* gelesen wird.
   1. Ziehen Sie das Blatt **[!UICONTROL Daten]** aus dem Regal **[!UICONTROL Tabellen]** unter das Blatt **[!UICONTROL Diagramm]** und legen Sie es in die Ansicht **[!UICONTROL Dashboard 1]**.
   1. Wählen Sie das Blatt **[!UICONTROL Daten]** in der Ansicht aus und ändern Sie **[!UICONTROL Gesamte Ansicht]** in **[!UICONTROL Breite korrigieren]**.

      Ihre Ansicht **[!UICONTROL Dashboard 1]** sollte wie unten dargestellt aussehen.

      ![Tableau-Desktop-Dashboard 1](assets/uc4-tableau-dashboard.png)

>[!ENDTABS]

+++


## Einzelne Dimension in Rang

Zusammenfassung des Anwendungsfalls

+++ Details

>[!PREREQUISITES]
>
>Stellen Sie sicher, dass Sie eine [erfolgreiche Verbindung validiert haben und Datenansichten](#connect-and-list-data-views) für das BI-Tool auflisten können, für das Sie diesen Anwendungsfall ausprobieren möchten.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Schritte

>[!TAB Tableau-Desktop]

Schritte

>[!ENDTABS]

+++


## Rangansicht mehrerer Dimensionen

Zusammenfassung des Anwendungsfalls

+++ Details

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Schritte

>[!TAB Tableau-Desktop]

Schritte

>[!ENDTABS]

+++


## Zählen von eindeutigen Dimensionswerten

Zusammenfassung des Anwendungsfalls

+++ Details

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Schritte

>[!TAB Tableau-Desktop]

Schritte

>[!ENDTABS]

+++



## Filtern von Datumsbereichsnamen

Zusammenfassung des Anwendungsfalls

+++ Details

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Schritte

>[!TAB Tableau-Desktop]

Schritte

>[!ENDTABS]

+++



## Filternamen zum Filtern verwenden

Zusammenfassung des Anwendungsfalls

+++ Details

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Schritte

>[!TAB Tableau-Desktop]

Schritte

>[!ENDTABS]

+++



## Verwenden von Dimensionswerten zum Filtern

Zusammenfassung des Anwendungsfalls

+++ Details

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Schritte

>[!TAB Tableau-Desktop]

Schritte

>[!ENDTABS]

+++



## Sortieren

Zusammenfassung des Anwendungsfalls

+++ Details

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Schritte

>[!TAB Tableau-Desktop]

Schritte

>[!ENDTABS]

+++



## Beschränkungen

Zusammenfassung des Anwendungsfalls

+++ Details

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Schritte

>[!TAB Tableau-Desktop]

Schritte

>[!ENDTABS]

+++



## Zum FLATTEN oder nicht

Zusammenfassung des Anwendungsfalls

+++ Details

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Schritte

>[!TAB Tableau-Desktop]

Schritte

>[!ENDTABS]

+++



## Dimension- und Metriktransformationen

Zusammenfassung des Anwendungsfalls

+++ Details

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Schritte

>[!TAB Tableau-Desktop]

Schritte

>[!ENDTABS]

+++



## Visualisierungen und Interaktionen

Zusammenfassung des Anwendungsfalls

+++ Details

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Schritte

>[!TAB Tableau-Desktop]

Schritte

>[!ENDTABS]

+++


