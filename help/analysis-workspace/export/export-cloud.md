---
description: Erfahren Sie, wie Sie ein Analysis Workspace-Projekt an einen Cloud-Speicherort exportieren.
keywords: Analysis Workspace
title: Exportieren von Customer Journey Analytics-Berichten in die Cloud
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
source-git-commit: 18a1cfcddfc8b2d1c70af57518c0b8d848b4ca5d
workflow-type: tm+mt
source-wordcount: '2226'
ht-degree: 3%

---

# Exportieren von Customer Journey Analytics-Berichten in die Cloud

Sie können vollständige Workspace-Tabellen vom Customer Journey Analytics exportieren und Exporte an bestimmte Cloud-Ziele senden.

Es sind auch andere Methoden zum Exportieren von Customer Journey Analytics-Berichten verfügbar, wie unter [Exportübersicht](/help/analysis-workspace/export/export-project-overview.md) beschrieben.

## Vollständiger Tabellenexport

Sie können vollständige Tabellen aus Analysis Workspace an Cloud-Anbieter wie Google, Azure, Amazon und Adobe exportieren.

[Vorteile des Exports vollständiger Tabellen in die Cloud](#advantages-of-exporting-to-the-cloud) umfassen die Möglichkeit zum Exportieren von Millionen von Zeilen, einschließlich berechneter Metriken, Strukturdatenausgabe in verketteten Werten und mehr.

Beachten Sie beim Exportieren vollständiger Tabellen Folgendes:

* Stellen Sie vor dem Export in die Cloud sicher, dass Ihre Tabellen, Ihre Umgebung und Ihre Berechtigungen die [Exportanforderungen“ ](#export-requirements).

* Einige [Funktionen](#unsupported-features) und [Komponenten](#unsupported-components) werden beim Exportieren vollständiger Tabellen in die Cloud nicht unterstützt.

Verwenden Sie den folgenden Prozess beim Exportieren vollständiger Tabellen in die Cloud:

1. [Konfigurieren eines Cloud-Kontos](/help/components/exports/cloud-export-accounts.md)

1. [Speicherort für das Konto konfigurieren](/help/components/exports/cloud-export-locations.md)

1. [Exportieren einer vollständigen Tabelle aus Workspace](#export-full-tables-from-analysis-workspace)

1. [Zugriff auf Daten in der Cloud](#view-exported-data-and-manifest-file) und [Exporte in Adobe verwalten](/help/components/exports/manage-exports.md)

![Der vollständige Tabellenexport-Prozess, der in den Schritten 1 bis 4 beschrieben wird.](assets/export-full-table-process.png)

## Exportieren vollständiger Tabellen aus Analysis Workspace

>[!NOTE]
>
>Bevor Sie Daten wie in diesem Abschnitt beschrieben exportieren, erfahren Sie mehr über den vollständigen Tabellenexport im Abschnitt [Verstehen des vollständigen ](#understand-full-table-export)) weiter oben.

So exportieren Sie vollständige Tabellen aus Analysis Workspace:

1. Falls noch nicht geschehen, konfigurieren Sie ein Exportkonto und einen Speicherort, wie unter [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md) beschrieben.

1. Klicken Sie in Analysis Workspace mit der rechten Maustaste auf die Freiformtabelle, die die zu exportierenden Daten enthält.

1. Wählen Sie [!UICONTROL **Vollständige Tabelle exportieren**].

   ![Das Dropdown-Menü der Freiformtabelle mit hervorgehobener Option „Vollständige Tabelle exportieren“](assets/export-full-table.png)

1. Geben [!UICONTROL **im Dialogfeld Neuer vollständiger**] die folgenden Informationen an:

   | Feldname | Funktion |
   |---------|----------|
   | Name | Geben Sie einen Namen für den Export an. Dieser Name wird in der Exportliste angezeigt. |
   | Tags | Sie können ein vorhandenes Tag auf den Export anwenden oder ein neues Tag erstellen und anwenden. <p>Um ein vorhandenes Tag auf den Export anzuwenden, wählen Sie beliebige Tags aus dem Dropdown-Menü aus. Alle Tags in Ihrem Unternehmen können angewendet werden<!-- double-check this -->.</p> <p>Um ein neues Tag zu erstellen, geben Sie den Namen des neuen Tags ein und drücken Sie dann die Eingabetaste.</p><p>Beachten Sie beim Anwenden von Tags auf einen Export Folgendes: <ul><li>Tags, die Sie anwenden, können nach in der Exporttabelle gefiltert oder danach gesucht werden.</li> <li>Tags, die auf ein Projekt angewendet werden, werden beim Exportieren einer vollständigen Tabelle nicht automatisch angewendet, wie unter „Konfigurieren von Spalten auf der Seite „Exporte“ in [Exporte verwalten](/help/components/exports/manage-exports.md) beschrieben. (Alternativ werden bei [Planung eines vollständigen Projekts für den Export](/help/analysis-workspace/export/t-schedule-report.md) alle auf das Projekt angewendeten Tags automatisch auf den Export angewendet.) <!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></li></ul> |
   | Beschreibung | Fügen Sie dem Export eine Beschreibung hinzu. Sie können die Beschreibungen auf der Seite „Exporte“ als Spalte [, wenn Sie ](/help/components/exports/manage-exports.md) Exporte anzeigen. |
   | Datenansicht | Wählen Sie die Datenansicht aus, die die Komponenten enthält, die Sie in den Export einbeziehen möchten. Das Dropdown-Menü für die Datenansicht befindet sich in der oberen linken Ecke des Dialogfelds und kann durch das Symbol für die Datenansicht ![ das Symbol für die Datenansicht ](assets/data-view-icon.png) werden.  <p>**Hinweis:** Wenn Sie eine Datenansicht auswählen, in der Komponenten fehlen, die bereits in Ihrer Datentabelle enthalten sind, werden Sie aufgefordert, die Datentabelle zu löschen und sie mithilfe von Komponenten, die in der ausgewählten Datenansicht enthalten sind, neu zu erstellen. </p> |
   | Lookback-Fenster | Wählen Sie den Berichtszeitrahmen aus, der in jede Exportdatei aufgenommen werden soll. Die Optionen umfassen [!UICONTROL **Heute**], [!UICONTROL **Gestern**], [!UICONTROL **Letzte 7 Tage**], [!UICONTROL **Letzte 30 Tage**], [!UICONTROL **Diese Woche**] und [!UICONTROL **Diesen Monat**]. <p>Diese Option wird nicht angezeigt, wenn [!UICONTROL **Exporthäufigkeit**] auf [!UICONTROL **Jetzt senden (einmal)**] festgelegt ist. |
   |  Datentabelle | Zeigt die zu exportierende Freiformtabelle an. Sie können die Datentabelle ändern, indem Sie Komponenten aus dem linken Bereich in die Tabelle ziehen. Die Tabelle wird beim Hinzufügen von Komponenten zur Arbeitsfläche dynamisch aktualisiert.  <p>Alle Segmente, die auf die vollständige Tabelle im Projekt angewendet wurden, werden oben in jeder einzelnen Spalte in der Tabelle angezeigt.</p> |
   | Leeren | Löscht den Inhalt der Datentabelle. Auf diese Weise können Sie direkt im Dialogfeld Neue vollständige Tabelle exportieren mit dem Erstellen einer neuen Tabelle beginnen. |
   | Exporthäufigkeit | Legen Sie fest, wie oft der Export erfolgen soll. <p>Sie können [!UICONTROL **Jetzt senden (einmal)**] wählen, um den Export nur einmal zu senden. Bei Auswahl dieser Option wird der Export sofort gestartet.<p>Sie können auch festlegen, dass der Export nach einem festgelegten Zeitplan gesendet wird. Beim Versand nach einem Zeitplan umfassen die Optionen [!UICONTROL **täglich**], [!UICONTROL **wöchentlich**], [!UICONTROL **monatlich nach Wochentag**], [!UICONTROL **monatlich nach Tag des Monats**], [!UICONTROL **jährlich nach Tag des Monats**] und [!UICONTROL **jährlich nach einem bestimmten Datum**]. </p><p>Beachten Sie bei der Auswahl einer Exportfrequenz Folgendes:</p><ul><li>Die Optionen im Feld [!UICONTROL **Lookback**] ändern sich je nachdem, was Sie hier auswählen.<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>Je nach ausgewählter Option werden zusätzliche Konfigurationsfelder angezeigt.</li></ul> |
   | Start am | Der Tag und die Uhrzeit, an dem der geplante Export beginnen soll. <p>Diese Option ist nur bei Auswahl einer geplanten Exportfrequenz verfügbar.</p> |
   | Endet am | Der Tag und die Uhrzeit, an dem bzw. zu der der geplante Export abläuft. Der geplante Export läuft nicht mehr nach dem von Ihnen festgelegten Datum und der von Ihnen festgelegten Uhrzeit. <p>Diese Option ist nur bei Auswahl einer geplanten Exportfrequenz verfügbar.</p> |
   | Dateiformat | Wählen Sie aus, ob die exportierten Daten im .csv- oder .json-Format vorliegen sollen. |
   | Konto | Wählen Sie das Cloud-Exportkonto aus, an das die Daten gesendet werden sollen. <p>Wenn Sie noch kein Cloud-Konto konfiguriert haben, das Sie verwenden möchten, können Sie auch ein neues Konto konfigurieren:<ol><li>Wählen Sie [!UICONTROL **Konto hinzufügen**] aus und geben Sie dann die folgenden Informationen an:<ul><li>[!UICONTROL **Speicherort-Kontoname**]: Geben Sie einen Namen für das Speicherort-Konto an. Dieser Name wird beim Erstellen eines Speicherorts angezeigt </li><li>[!UICONTROL **Beschreibung des Standortkontos**] Geben Sie eine kurze Beschreibung des Kontos an, um es von anderen Konten desselben Kontotyps zu unterscheiden.</li><li>[!UICONTROL **Kontotyp**]: Wählen Sie den Typ des Cloud-Kontos aus, in das Sie exportieren. Verfügbare Kontotypen sind Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake und AEP Data Landing Zone.</li></ul><li>Um die Konfiguration Ihres Kontos abzuschließen, fahren Sie mit dem unten stehenden Link fort, der dem von [!UICONTROL **ausgewählten**] entspricht:<ul><li>[AEP-Data Landing Zone](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[Amazon S3-Rollen-ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | Name des Speicherorts | Wählen Sie den Speicherort auf dem Konto aus, an den die Exportdaten gesendet werden sollen.<p>Falls Sie den Speicherort, den Sie für das ausgewählte Konto verwenden möchten, noch nicht konfiguriert haben, können Sie auch einen neuen Speicherort konfigurieren:<ol><li>Klicken Sie [!UICONTROL **Speicherort hinzufügen**] und geben Sie die folgenden Informationen an: <ul><li>[!UICONTROL **Name**]: Der Name des Speicherorts.</li><li>[!UICONTROL **Beschreibung**]: Geben Sie eine kurze Beschreibung des Speicherorts an, um ihn von anderen Speicherorten im Konto zu unterscheiden.</li><li>[!UICONTROL **Speicherort-Konto**]: Wählen Sie das Konto aus, in dem Sie den Speicherort erstellen möchten.</li></ul><li>Um die Konfiguration Ihres Standorts abzuschließen, fahren Sie mit dem folgenden Link fort, der dem Kontotyp entspricht, den Sie im Feld [!UICONTROL **Standortkonto**] ausgewählt haben:<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone).</li><li>[Amazon S3-Rollen-ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |

   {style="table-layout:auto"}

1. Klicken Sie [!UICONTROL **Speichern**], um den Export zu speichern.

   Die Daten werden mit der von Ihnen angegebenen Häufigkeit an das von Ihnen angegebene Cloud-Konto gesendet.

1. (Optional) Unabhängig davon, ob Sie den Export jetzt oder nach einem festgelegten Zeitplan senden, können Sie ihn nach der Erstellung auf der Seite „Exporte[ anzeigen und verwalten ](/help/components/exports/manage-exports.md) in den [Exportprotokollen](/help/components/exports/manage-export-logs.md) anzeigen.</p>

## Verwalten von Exporten

Nachdem Daten aus Analysis Workspace exportiert wurden, können Sie bestehende Exporte bearbeiten, erneut exportieren, duplizieren, taggen oder löschen, wie in [Exporte verwalten](/help/components/exports/manage-exports.md) beschrieben.

## Exportierte Daten und Manifestdatei anzeigen

### Exportierte Daten

Exportierte Daten sind als komprimierte Datei in dem von Ihnen konfigurierten Cloud-Ziel verfügbar, wie unter [Konfigurieren von Cloud-](/help/components/exports/cloud-export-accounts.md) und [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md) beschrieben.

Der Dateiname der komprimierten Datei lautet wie folgt, je nachdem, ob Sie CSV oder JSON als Dateiformat ausgewählt haben:

* `cja-export-{reportInstanceId}-{idx}.csv.gz`

* `cja-export-{reportInstanceId}-{idx}.json.gz`

>[!NOTE]
>
>Sie wählen das Dateiformat im Feld [!UICONTROL **Dateiformat**] beim Exportieren der Tabelle aus, wie unter [Exportieren vollständiger Tabellen aus Analysis Workspace](#export-full-tables-from-analysis-workspace) beschrieben.

### Manifestdatei 

Eine Manifestdatei mit dem Dateinamen `cja-export-{reportInstanceId}-{idx}.json.gz` ist in jedem erfolgreichen Exportversand enthalten, der mindestens eine Datei enthält. Mit der Manifestdatei können Sie bestätigen, dass alle Dateien erfolgreich bereitgestellt wurden. Sie enthält folgende Informationen:

* Eine Liste aller zugestellten Dateien

* Die MD5-Prüfsumme jeder Datei

<!-- add in  what the file name, structure, and file format will be -->

## Vorteile des Exports in die Cloud

Das Exportieren von Customer Journey Analytics-Daten in die Cloud ermöglicht Folgendes:

* Exportieren Sie an einen freigegebenen Speicherort, z. B. Adobe Experience Platform Data Landing Zone, Google Cloud Platform, Microsoft Azure, Amazon S3 oder Snowflake.

* Speichern großer Mengen historischer Daten.

  Diese Art von Daten kann verwendet werden, um langfristige Trends zu erkennen, um Business Intelligence zu erhalten und letztendlich zu einer besseren geschäftlichen Entscheidungsfindung zu führen.

* Exportieren Sie vollständige Tabellen, die Tausende oder Millionen von Zeilen enthalten (3 Millionen, 30 Millionen, 150 Millionen oder 300 Millionen Zeilen, je nach Lizenztyp). Andere Exportmethoden erlauben maximal 50.000 Zeilen.

* Schließen Sie berechnete Metriken in die exportierten Customer Journey Analytics-Daten ein.

* Strukturieren Sie die Datenausgabe als verkettete Werte.

* Einmalige oder geplante Exporte (Auch verfügbar mit [anderen Exportoptionen](/help/analysis-workspace/export/export-project-overview.md).)

* Exportieren Sie Dateien im CSV- oder JSON-Format. (Auch verfügbar mit [anderen Exportoptionen](/help/analysis-workspace/export/export-project-overview.md).)

* Exportieren Sie Tabellen, die mehrere Dimensionen enthalten.

## Exportanforderungen {#export-requirements}

### Mindestanforderungen

Stellen Sie sicher, dass Ihre Tabellen, Ihre Umgebung und Ihre Berechtigungen die folgenden Anforderungen erfüllen:

* **Tabellen:** Alle Tabellen müssen mindestens eine Dimension in der Zeile und eine Metrik in jeder Spalte enthalten, damit sie durch einen vollständigen Tabellenexport unterstützt werden.

* **Umgebung:** Stellen Sie sicher, dass [IP-Adressen](/help/technotes/ip-addresses.md) und [Domains](/help/technotes/domains.md), die vom Customer Journey Analytics verwendet werden, durch die Firewall ihrer Organisation zugelassen werden.

* **Berechtigungen:** In der Adobe Admin Console muss Benutzenden ein Produktprofil zugewiesen werden, das über die Berechtigung [!UICONTROL **Vollständiger Tabellenexport**] verfügt, um vollständige Tabellen exportieren zu können. Informationen zum Zuweisen einer Berechtigung zu einem Produktprofil in der Admin Console finden Sie unter [Berechtigung zum Customer Journey Analytics in Admin Console](/help/technotes/access-control.md).

  >[!NOTE]
  >
  >  Benutzende mit der [Produktadministrator-Rolle](/help/technotes/access-control.md#product-admin-role) haben immer Zugriff auf den Export vollständiger Tabellen. Diese Benutzenden müssen nicht über die Berechtigung [!UICONTROL **Export vollständiger Tabellen**] verfügen.


### Nicht unterstützte Funktionen

Die folgenden Funktionen werden nicht unterstützt und automatisch aus vollständigen Tabellenexporten entfernt:

* Prozentsatz
* Gesamt
* Suchfilter
* Statische Zeilen
* Datumsausrichtung
* Dynamische Dimensionen

  Weitere Informationen finden Sie unter [Dynamische und statische Dimensionselemente in Freiformtabellen](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).
* Die Dimensionen in der ersten Aufschlüsselung werden konvertiert und als sekundäre Dimension in der Zeile der exportierten Tabelle hinzugefügt. Alle anderen Aufschlüsselungen sind nicht in der Tabelle enthalten
* Die Sortierung wird für die meisten Datensätze nicht unterstützt. Daten können für kleine Datensätze sortiert werden

### Nicht unterstützte Komponenten

Die folgenden Komponenten werden nicht unterstützt und Analysis Workspace fordert Sie auf, sie aus Ihrer Tabelle zu entfernen, wenn Sie einen vollständigen Tabellenexport durchführen:

* Berechnete Metriken, die grundlegende oder erweiterte Funktionen in der Metrikdefinition verwenden (weitere Informationen finden Sie unter [Grundfunktionen](/help/components/calc-metrics/cm-functions.md) und [Erweiterte ](/help/components/calc-metrics/cm-adv-functions.md))
* Komponenten, die von einem Administrator bzw. einer Administratorin eingeschränkt wurden, können nicht exportiert werden (weitere Informationen finden Sie *Abschnitt* Filtern von Data Governance-Richtlinien in [Kennzeichnungen und ](/help/data-views/data-governance.md))
* Jede Dimension, die alle folgenden Kriterien erfüllt:
   * wurde aus einem Feld erstellt, das Teil eines [Arrays von Objekten](/help/use-cases/object-arrays.md) ist (ähnlich wie Variablen mit mehreren Werten in Adobe Analytics)
   * Hat [Persistenz aktiviert](/help/data-views/component-settings/persistence.md)
   * Verwendet keine [Bindungsdimension](/help/use-cases/data-views/binding-dimensions-metrics.md)
* Mehrere Dimensionen, die aus Feldern stammen, die auf verschiedene [Objekt-Arrays](/help/use-cases/object-arrays.md) verweisen. (Mehrere Dimensionen, die auf dasselbe Array von Objekten verweisen, sind zulässig.)
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

Der vollständige Tabellenexport unterstützt berechnete Metriken, die ein nicht standardmäßiges Attributionsmodell verwenden (wie im Abschnitt *Verwenden eines nicht standardmäßigen Attributionsmodells* in [Spalteneinstellungen](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) beschrieben.

Wenn in einem Bericht ein nicht standardmäßiges Attributionsmodell verwendet wird, wird das im Bericht verwendete Zuordnungsmodell entweder ignoriert oder beibehalten, je nachdem, ob der Bericht eine einzelne Dimension oder mehrere Dimensionen aufweist:

* **Bei Berichten, die eine Metrikattribution in einer einzigen Dimension enthalten:** [Metrikattribution](/help/data-views/component-settings/attribution.md) überschreibt das [Zuordnungsmodell](/help/data-views/component-settings/persistence.md) wie normalerweise bei der Verwendung der Metrikattribution.

  Beispielsweise überschreibt eine Metrikattribution „Erstkontakt“ eine Dimensionszuordnung „Zuletzt verwendet“.

* **Für Berichte, die eine Metrikattribution auf mehreren Dimensionen gleichzeitig enthalten:** [Metrikattribution](/help/data-views/component-settings/attribution.md) wird zusätzlich zum [Zuordnungsmodell](/help/data-views/component-settings/persistence.md) angewendet.

  Beispielsweise wird zusätzlich zur Zuordnung der Dimension „Zuletzt verwendet“ eine Metrikattribution „Erstkontakt“ angewendet. Darüber hinaus wird die Metrik-Attribution auf nach der Zuordnung zugewiesene Dimensionselement-Paare angewendet, als ob es sich um einzelne Dimensionselemente handelte, und nicht wie normalerweise in einer Freiformtabelle, unabhängig auf jedes Dimensionselement.

  >[!NOTE]
  >
  >Mehrdimensionale Berichte werden nur beim Exportieren von Daten in die Cloud unterstützt, wie in diesem Artikel beschrieben.

## Vergleich des vollständigen Tabellenexports (in Customer Journey Analytics) in Data Warehouse (in Adobe Analytics)

Wenn Sie zuvor Data Warehouse zum Exportieren von Adobe Analytics-Daten verwendet haben, können Sie in der folgenden Tabelle die Unterschiede zwischen dem Exportieren vollständiger Tabellen auf Customer Journey Analytics und dem Exportieren von Daten mit Data Warehouse auf Adobe Analytics verstehen.


| Funktion | Vollständiger Tabellenexport in Customer Journey Analytics | Data Warehouse in Adobe Analytics |
|---------|----------|---------|
| Erstellen eines benutzerdefinierten Berichts | Ja | Ja |
| Berechnete Metriken  | Ja | Nein |
| Segmente  | Ja | Begrenzt |
| Dimensionen | Limit von 5 | Unbegrenzt |
| Metriken | Limit von 5 | Unbegrenzt |
| Berichtszeilen | Limit von 3 Millionen, 30 Millionen, 150 Millionen oder 300 Millionen, je nach Stufe | Unbegrenzt |
| Anzahl der Berichte | Unbegrenzt | Unbegrenzt |
| Ad-hoc-Versand (einmal) | Ja | Ja |
| Planen eines wiederkehrenden Versands | Ja | Ja |
| Email-Versand | Nein | Ja |
| FTP/SFTP | Nein | Legacy-Support |
| Azure | Ja | Ja |
| Amazon S3 | Ja | Ja |
| Google Cloud Platform | Ja | Ja |
| Snowflake | Ja | Nein |
| Bereitstellungshäufigkeit | Täglich | Stündlich |
