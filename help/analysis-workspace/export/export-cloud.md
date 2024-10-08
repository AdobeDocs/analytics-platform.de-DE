---
description: Erfahren Sie, wie Sie ein Analysis Workspace-Projekt an einen Cloud-Speicherort exportieren.
keywords: Analysis Workspace
title: Customer Journey Analytics-Berichte in die Cloud exportieren
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
source-git-commit: de04792035aa7c235751019ee9f9fe5b74b9b102
workflow-type: tm+mt
source-wordcount: '2205'
ht-degree: 4%

---

# Customer Journey Analytics-Berichte in die Cloud exportieren

Sie können vollständige Workspace-Tabellen aus Customer Journey Analytics exportieren und Exporte an bestimmte Cloud-Ziele senden.

Es sind auch andere Methoden zum Exportieren von Customer Journey Analytics-Berichten verfügbar, wie unter [Exportübersicht](/help/analysis-workspace/export/export-project-overview.md) beschrieben.

## Vollständiger Tabellenexport

Sie können vollständige Tabellen aus Analysis Workspace in Cloud-Anbieter wie Google, Azure, Amazon und Adobe exportieren.

[Vorteile des Exports vollständiger Tabellen in die Cloud](#advantages-of-exporting-to-the-cloud) sind die Möglichkeit, Millionen von Zeilen zu exportieren, berechnete Metriken einzuschließen, die Ausgabe von Strukturdaten in verketteten Werten zu strukturieren und mehr.

Beachten Sie beim Exportieren vollständiger Tabellen Folgendes:

* Bevor Sie in die Cloud exportieren, stellen Sie sicher, dass Ihre Tabellen, Ihre Umgebung und Ihre Berechtigungen die [Exportanforderungen](#export-requirements) erfüllen.

* Einige [Funktionen](#unsupported-features) und [Komponenten](#unsupported-components) werden beim Exportieren vollständiger Tabellen in die Cloud nicht unterstützt.

Verwenden Sie beim Exportieren vollständiger Tabellen in die Cloud den folgenden Prozess:

1. [Konfigurieren eines Cloud-Kontos](/help/components/exports/cloud-export-accounts.md)

1. [Speicherort für das Konto konfigurieren](/help/components/exports/cloud-export-locations.md)

1. [Eine vollständige Tabelle aus Workspace exportieren](#export-full-tables-from-analysis-workspace)

1. [Zugreifen auf Daten in der Cloud](#view-exported-data-and-manifest-file) und [Verwalten von Exporten in Adobe](/help/components/exports/manage-exports.md)

![Der in den Schritten 1 bis 4 beschriebene vollständige Tabellenexport-Prozess.](assets/export-full-table-process.png)

## Vollständige Tabellen aus Analysis Workspace exportieren

>[!NOTE]
>
>Bevor Sie Daten wie in diesem Abschnitt beschrieben exportieren, erfahren Sie mehr über den vollständigen Tabellenexport im Abschnitt [Vollständigen Tabellenexport verstehen](#understand-full-table-export) weiter oben.

So exportieren Sie vollständige Tabellen aus Analysis Workspace:

1. Falls noch nicht geschehen, konfigurieren Sie ein Exportkonto und einen Speicherort, wie unter [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md) beschrieben.

1. Klicken Sie in Analysis Workspace mit der rechten Maustaste auf die Freiformtabelle, die die zu exportierenden Daten enthält.

1. Wählen Sie [!UICONTROL **Gesamte Tabelle exportieren**] aus.

   ![Das Dropdown-Menü Freiformtabelle mit der Markierung &quot;Vollständige Tabelle exportieren&quot;](assets/export-full-table.png)

1. Geben Sie im Dialogfeld [!UICONTROL **Neuer vollständiger Tabellenexport**] die folgenden Informationen an:

   | Feldname | Funktion |
   |---------|----------|
   | Name | Geben Sie einen Namen für den Export an. Dieser Name wird in der Liste der Exporte angezeigt. |
   | Tags | Sie können ein vorhandenes Tag auf den Export anwenden oder ein neues Tag erstellen und anwenden. <p>Um ein vorhandenes Tag auf den Export anzuwenden, wählen Sie beliebige Tags aus dem Dropdownmenü aus. Alle Tags in Ihrem Unternehmen können auf <!-- double-check this --> angewendet werden.</p> <p>Um ein neues Tag zu erstellen, geben Sie den Namen des neuen Tags ein und drücken Sie dann die Eingabetaste.</p><p>Beachten Sie beim Anwenden von Tags auf einen Export Folgendes: <ul><li>Von Ihnen angewendete Tags können in der Exporttabelle nach gefiltert oder gesucht werden.</li> <li>Auf ein Projekt angewendete Tags werden beim Exportieren einer vollständigen Tabelle nicht automatisch angewendet, wie unter &quot;Konfigurieren von Spalten auf der Exportseite&quot;in [Verwalten von Exporten](/help/components/exports/manage-exports.md) beschrieben. (Wenn [ein vollständiges Projekt für den Export planen](/help/analysis-workspace/export/t-schedule-report.md), werden alle Tags, die auf das Projekt angewendet werden, automatisch auf den Export angewendet.) <!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></li></ul> |
   | Beschreibung | Fügen Sie dem Export eine Beschreibung hinzu. Sie können Beschreibungen bei der Anzeige von Exporten als Spalte auf der Seite [Exporte](/help/components/exports/manage-exports.md) anzeigen. |
   | Datenansicht | Wählen Sie die Datenansicht aus, die die Komponenten enthält, die Sie in den Export einbeziehen möchten. Das Dropdown-Menü Datenansicht befindet sich in der oberen linken Ecke des Dialogfelds und kann über das Datenansichtssymbol![Datenansichtssymbol](assets/data-view-icon.png) identifiziert werden.  <p>**Hinweis:** Wenn Sie eine Datenansicht auswählen, in der Komponenten fehlen, die bereits in Ihrer Datentabelle enthalten sind, werden Sie aufgefordert, die Datentabelle zu löschen und sie mithilfe von Komponenten, die in der ausgewählten Datenansicht enthalten sind, erneut zu erstellen. </p> |
   | Lookback-Fenster | Wählen Sie den Zeitrahmen für die Berichterstellung aus, der in jede Exportdatei aufgenommen werden soll. Zu den Optionen gehören [!UICONTROL **Heute**], [!UICONTROL **Gestern**], [!UICONTROL **Letzte 7 Tage**], [!UICONTROL **Letzte 30 Tage**], [!UICONTROL **Diese Woche**] und [!UICONTROL **diesen Monat**]. <p>Diese Option wird nicht angezeigt, wenn die [!UICONTROL **Exportfrequenz**] auf [!UICONTROL **Jetzt senden (einmal)**] gesetzt ist. |
   |  Datentabelle | Zeigt die Freiformtabelle an, die Sie exportieren. Sie können die Datentabelle ändern, indem Sie Komponenten aus dem linken Bereich in die Tabelle ziehen. Die Tabelle wird beim Hinzufügen von Komponenten zur Arbeitsfläche dynamisch aktualisiert.  <p>Alle Segmente, die auf die vollständige Tabelle im Projekt angewendet wurden, werden oben in jeder einzelnen Spalte in der Tabelle angezeigt.</p> |
   | Leeren | Löscht den Inhalt der Datentabelle. Auf diese Weise können Sie direkt im Dialogfeld Neuer vollständiger Tabellenexport mit der Erstellung einer neuen Tabelle beginnen. |
   | Exporthäufigkeit | Legen Sie den Zeitplan fest, wie oft der Export erfolgen soll. <p>Sie können [!UICONTROL **Jetzt senden (einmal)**] auswählen, um den Export nur einmal zu senden. Wenn Sie diese Option auswählen, wird der Export sofort gestartet.<p>Sie haben auch die Möglichkeit, den Export nach einem festgelegten Zeitplan durchzuführen. Beim Versand nach einem Zeitplan sind unter anderem die Optionen [!UICONTROL **Täglich**], [!UICONTROL **Wöchentlich**], [!UICONTROL **Monatlich nach Tag der Woche**], [!UICONTROL **Monatlich nach Tag des Monats**], [!UICONTROL **Jährlich nach Tag des Monats**] und [!UICONTROL **Jährlich nach spezifischem Datum**] verfügbar. </p><p>Beachten Sie bei der Auswahl einer Exportfrequenz Folgendes:</p><ul><li>Die Optionen im Feld [!UICONTROL **Lookback-Fenster**] ändern sich je nachdem, was Sie hier auswählen.<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>Je nach gewählter Option werden weitere Konfigurationsfelder angezeigt.</li></ul> |
   | Starten am | Tag und Uhrzeit, zu der der geplante Export beginnen soll. <p>Diese Option ist nur verfügbar, wenn Sie eine geplante Exportfrequenz auswählen.</p> |
   | Beenden am | Der Tag und die Uhrzeit, zu der der geplante Export abläuft. Der geplante Export wird nicht mehr nach dem von Ihnen festgelegten Datum und der festgelegten Uhrzeit ausgeführt. <p>Diese Option ist nur verfügbar, wenn Sie eine geplante Exportfrequenz auswählen.</p> |
   | Dateiformat | Wählen Sie aus, ob die exportierten Daten im .csv - oder .json -Format vorliegen sollen. |
   | Konto | Wählen Sie das Cloud-Exportkonto aus, an das die Daten gesendet werden sollen. <p>Oder wenn Sie noch kein Cloud-Konto konfiguriert haben, das Sie verwenden möchten, können Sie ein neues Konto konfigurieren:<ol><li>Wählen Sie [!UICONTROL **Konto hinzufügen**] aus und geben Sie dann die folgenden Informationen an:<ul><li>[!UICONTROL **Name des Standortkontos**]: Geben Sie einen Namen für das Standortkonto an. Dieser Name wird beim Erstellen eines Standorts angezeigt </li><li>[!UICONTROL **Beschreibung des Standortkontos**]: Geben Sie eine kurze Beschreibung des Kontos ein, um es von anderen Konten desselben Kontotyps zu unterscheiden.</li><li>[!UICONTROL **Kontotyp**]: Wählen Sie den Typ des Cloud-Kontos aus, in das Sie exportieren. Verfügbare Kontotypen sind Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake und AEP Data Landing Zone.</li></ul><li>Um die Konfiguration Ihres Kontos abzuschließen, fahren Sie mit dem folgenden Link fort, der dem von Ihnen ausgewählten [!UICONTROL **Kontotyp**] entspricht:<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[Amazon S3-Rolle ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | Name des Speicherorts | Wählen Sie den Speicherort für das Konto aus, an den die Exportdaten gesendet werden sollen.<p>Wenn Sie den Speicherort, den Sie für das ausgewählte Konto verwenden möchten, noch nicht konfiguriert haben, können Sie auch einen neuen Speicherort konfigurieren:<ol><li>Wählen Sie [!UICONTROL **Position hinzufügen**] und geben Sie dann die folgenden Informationen an: <ul><li>[!UICONTROL **Name**]: Der Name des Standorts.</li><li>[!UICONTROL **Beschreibung**]: Geben Sie eine kurze Beschreibung des Standorts ein, um ihn von anderen Positionen im Konto zu unterscheiden.</li><li>[!UICONTROL **Standortkonto**]: Wählen Sie das Konto aus, in dem Sie den Standort erstellen möchten.</li></ul><li>Um die Konfiguration Ihres Standorts abzuschließen, fahren Sie mit dem unten stehenden Link fort, der dem Kontotyp entspricht, den Sie im Feld [!UICONTROL **Standortkonto**] ausgewählt haben:<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone).</li><li>[Amazon S3-Rolle ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |

   {style="table-layout:auto"}

1. Wählen Sie [!UICONTROL **Speichern**] aus, um den Export zu speichern.

   Die Daten werden an das Cloud-Konto gesendet, das Sie in der von Ihnen festgelegten Häufigkeit angegeben haben.

1. (Optional) Nachdem Sie den Export erstellt haben, können Sie ihn nun oder nach einem festgelegten Zeitplan auf der Seite [Exporte](/help/components/exports/manage-exports.md) anzeigen und verwalten und in den [Exportlogs](/help/components/exports/manage-export-logs.md) anzeigen.</p>

## Verwalten von Exporten

Nachdem die Daten aus Analysis Workspace exportiert wurden, können Sie bestehende Exporte bearbeiten, erneut exportieren, duplizieren, taggen oder löschen, wie unter [Exporte verwalten](/help/components/exports/manage-exports.md) beschrieben.

## Exportierte Daten und Manifestdatei anzeigen

### Exportierte Daten

Exportierte Daten sind als komprimierte Datei in dem von Ihnen konfigurierten Cloud-Ziel verfügbar, wie unter [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md) und [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md) beschrieben.

Der Dateiname der komprimierten Datei lautet wie folgt, je nachdem, ob Sie CSV oder JSON als Dateiformat ausgewählt haben:

* `cja-export-{reportInstanceId}-{idx}.csv.gz`

* `cja-export-{reportInstanceId}-{idx}.json.gz`

>[!NOTE]
>
>Sie wählen beim Exportieren der Tabelle das Dateiformat im Feld [!UICONTROL **Dateiformat**] aus, wie unter [Gesamte Tabellen aus Analysis Workspace exportieren](#export-full-tables-from-analysis-workspace) beschrieben.

### Manifestdatei 

Eine Manifestdatei mit dem Dateinamen &quot;`cja-export-{reportInstanceId}-{idx}.json.gz`&quot; ist bei jedem erfolgreichen Exportversand mit mindestens einer Datei enthalten. Mit der Manifestdatei können Sie überprüfen, ob alle Dateien erfolgreich bereitgestellt wurden. Er enthält die folgenden Informationen:

* Eine Liste aller Dateien, die bereitgestellt wurden

* Die MD5-Prüfsumme jeder Datei

<!-- add in  what the file name, structure, and file format will be -->

## Vorteile des Exports in die Cloud

Durch das Exportieren von Customer Journey Analytics-Daten in die Cloud haben Sie folgende Möglichkeiten:

* Exportieren Sie in einen freigegebenen Speicherort, z. B. Adobe Experience Platform Data Landing Zone, Google Cloud Platform, Microsoft Azure, Amazon S3 oder Snowflake.

* Speichern Sie große Mengen historischer Daten.

  Diese Art von Daten kann verwendet werden, um langfristige Trends zu erkennen, um Business Intelligence zu gewinnen und letztlich zu einer besseren Entscheidungsfindung in Unternehmen zu führen.

* Exportieren Sie vollständige Tabellen mit Tausenden oder Millionen Zeilen (3 Millionen, 30 Millionen, 150 Millionen oder 300 Millionen Zeilen, je nach Lizenztyp). Andere Exportmethoden erlauben maximal 50.000 Zeilen.

* Schließen Sie berechnete Metriken in die exportierten Customer Journey Analytics ein.

* Strukturdatenausgabe als verkettete Werte.

* Exportieren Sie einmalige oder planmäßige Exporte. (Auch mit [anderen Exportoptionen](/help/analysis-workspace/export/export-project-overview.md) verfügbar.)

* Exportieren Sie Dateien im CSV- oder JSON-Format. (Auch mit [anderen Exportoptionen](/help/analysis-workspace/export/export-project-overview.md) verfügbar.)

* Exportieren Sie Tabellen, die mehrere Dimensionen enthalten.

## Exportanforderungen {#export-requirements}

### Mindestanforderungen

Stellen Sie sicher, dass Ihre Tabellen, Ihre Umgebung und Ihre Berechtigungen die folgenden Anforderungen erfüllen:

* **Tabellen:** Alle Tabellen müssen mindestens eine Dimension in der Zeile und eine Metrik in jeder Spalte enthalten, damit sie bei einem vollständigen Tabellenexport unterstützt werden.

* **Umgebung:** Stellen Sie sicher, dass die von Customer Journey Analytics verwendeten [IP-Adressen](/help/technotes/ip-addresses.md) und [Domänen](/help/technotes/domains.md) über die Firewall ihres Unternehmens zugelassen sind.

* **Berechtigungen:** In der Adobe Admin Console müssen Benutzer ein Produktprofil mit der Berechtigung [!UICONTROL **Vollständiger Tabellenexport**] zugewiesen bekommen, damit sie vollständige Tabellen exportieren können. Informationen zum Zuweisen einer Berechtigung zu einem Produktprofil in der Admin Console finden Sie unter [Berechtigung zum Customer Journey Analytics in Admin Console](/help/technotes/access-control.md).

  >[!NOTE]
  >
  >  Benutzer, denen die [Produkt-Admin-Rolle](/help/technotes/access-control.md#product-admin-role) zugewiesen wurde, haben immer Zugriff auf den Export vollständiger Tabellen. Diesen Benutzern muss keine Berechtigung für den [!UICONTROL **vollständigen Tabellenexport**] zugewiesen werden.


### Nicht unterstützte Funktionen

Die folgenden Funktionen werden nicht unterstützt und automatisch aus dem Export in vollständige Tabellen entfernt:

* Prozentsatz
* Gesamt
* Suchfilter
* Statische Zeilen
* Datumsausrichtung
* Dynamische Dimensionen

  Weitere Informationen finden Sie unter [Dynamische und statische Dimensionselemente in Freiformtabellen](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).
* Dimensionen der ersten Aufschlüsselung werden konvertiert und in der Zeile der exportierten Tabelle als sekundäre Dimension hinzugefügt. Alle anderen Aufschlüsselungen sind nicht in der Tabelle enthalten.
* Die Sortierung wird für die meisten Datensätze nicht unterstützt. Daten können für kleine Datensätze sortiert werden.

### Nicht unterstützte Komponenten

Die folgenden Komponenten werden nicht unterstützt und Analysis Workspace fordert Sie auf, sie bei einem vollständigen Tabellenexport aus der Tabelle zu entfernen:

* Berechnete Metriken, die grundlegende oder erweiterte Funktionen in der Metrikdefinition verwenden (weitere Informationen finden Sie unter [Grundlegende Funktionen](/help/components/calc-metrics/cm-functions.md) und [Erweiterte Funktionen](/help/components/calc-metrics/cm-adv-functions.md) )
* Komponenten, die von einem Administrator nicht exportiert werden konnten (weitere Informationen finden Sie im Abschnitt [Beschriftungen und Richtlinien](/help/data-views/data-governance.md) des Abschnitts *Filter für Data Governance-Richtlinien in Datenansichten* ).
* Jede Dimension, die alle der folgenden Kriterien erfüllt:
   * wurde aus einem Feld erstellt, das Teil eines [Array von Objekten](/help/use-cases/object-arrays.md) ist (ähnlich wie Variablen mit mehreren Werten in Adobe Analytics)
   * Ist [persistence aktiviert](/help/data-views/component-settings/persistence.md)
   * Verwendet keine [Bindungsdimension](/help/use-cases/data-views/binding-dimensions-metrics.md)
* Mehr als 5 Dimensionen und 5 Metriken pro Bericht (bis zu 5 Dimensionen und 5 Metriken werden unterstützt)
* In Tabellenspalten:
   * Datumsbereiche
   * Dimensionen
* In Tabellenzeilen:
   * Berechnete Metriken 
   * Metriken
   * Datumsbereiche
   * Filter

### Attributionsverhalten

Der vollständige Tabellenexport unterstützt berechnete Metriken, die ein nicht standardmäßiges Attributionsmodell verwenden (wie im Abschnitt *Nicht standardmäßiges Attributionsmodell verwenden* in den [Spalteneinstellungen](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) beschrieben).

Wenn in einem Bericht ein nicht standardmäßiges Attributionsmodell verwendet wird, wird das im Bericht verwendete Zuordnungsmodell entweder ignoriert oder beibehalten, je nachdem, ob der Bericht eine einzelne Dimension oder mehrere Dimensionen aufweist:

* **Für Berichte, die die Metrikzuordnung in einer einzelnen Dimension enthalten:** [Metrikzuordnung](/help/data-views/component-settings/attribution.md) überschreibt das [Zuordnungsmodell](/help/data-views/component-settings/persistence.md), wie es normalerweise bei der Verwendung der Metrikzuordnung der Fall ist.

  Beispielsweise überschreibt die Attribution einer &quot;Erstkontakt&quot;-Metrik die Dimension &quot;Zuletzt verwendet&quot;.

* **Für Berichte, die die Metrikzuordnung für mehrere Dimensionen gleichzeitig enthalten:** [Die Metrikzuordnung](/help/data-views/component-settings/attribution.md) wird zusätzlich zur Dimension [Zuordnungsmodell](/help/data-views/component-settings/persistence.md) angewendet.

  Beispielsweise wird zusätzlich zur Dimensionszuordnung &quot;Letztkontakt&quot;eine Metrikzuordnung angewendet. Darüber hinaus wird die Metrikzuordnung auf nach der Zuweisung zugewiesene Dimensionselement-Paare so angewendet, als wären sie einzelne Dimensionselemente, anstatt auf jedes Dimensionselement unabhängig voneinander, wie dies normalerweise in einer Freiformtabelle geschieht.

  >[!NOTE]
  >
  >Mehrdimensionale Berichte werden nur beim Exportieren von Daten in die Cloud unterstützt, wie in diesem Artikel beschrieben.

## Vergleich des vollständigen Tabellenexports (in Customer Journey Analytics) mit Data Warehouse (in Adobe Analytics)

Wenn Sie zuvor Data Warehouse zum Exportieren von Adobe Analytics-Daten verwendet haben, können Sie anhand der folgenden Tabelle die Unterschiede zwischen dem Exportieren von vollständigen Tabellen in Customer Journey Analytics und dem Exportieren von Daten mit Data Warehouse in Adobe Analytics nachvollziehen.


| Funktion | Vollständiger Tabellenexport in Customer Journey Analytics | Data Warehouse in Adobe Analytics |
|---------|----------|---------|
| Benutzerspezifischen Bericht erstellen | Ja | Ja |
| Berechnete Metriken  | Ja | Nein |
| Segmente  | Ja | Begrenzt |
| Dimensionen | Maximal 5 | Unbegrenzt |
| Metriken | Maximal 5 | Unbegrenzt |
| Berichtszeilen | Limit von 3 Millionen, 30 Millionen, 150 Millionen oder 300 Millionen je nach Tier | Unbegrenzt |
| Anzahl der Berichte | Unbegrenzt | Unbegrenzt |
| Ad-hoc-Versand (einmalig) | Ja | Ja |
| Planen eines wiederkehrenden Versands | Ja | Ja |
| Email delivery | Nein | Ja |
| FTP/SFTP | Nein | Unterstützung älterer Versionen |
| Azure | Ja | Ja |
| Amazon S3 | Ja | Ja |
| Google Cloud Platform | Ja | Ja |
| Snowflake | Ja | Nein |
| Bereitstellungshäufigkeit | Täglich | Stündlich |
