---
description: Erfahren Sie, wie Sie ein Analysis Workspace-Projekt an einen Cloud-Speicherort exportieren.
keywords: Analysis Workspace
title: Exportieren von Customer Journey Analytics-Berichten in die Cloud
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
source-git-commit: a7bd67894b02174d980a730086f89df97b524356
workflow-type: tm+mt
source-wordcount: '2285'
ht-degree: 99%

---

# Exportieren von Customer Journey Analytics-Berichten in die Cloud {#full-table-export}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-full-table-export"
>title="Erstellen vollständiger Tabellenexporte ähnlich wie in Data Warehouse"
>abstract="Vollständige Tabellenexporte sind verfügbar, sobald Daten in Analysis Workspace angezeigt werden. Sie können vollständige Tabellenexporte nach Bedarf erstellen oder planen.<br><br>Das Erstellen vollständiger Tabellenexporte dauert nur einige Minuten, wenn Sie bereits wissen, welche Daten in den Export aufgenommen werden sollen."

<!-- markdownlint-enable MD034 -->

Sie können vollständige Workspace-Tabellen aus Customer Journey Analytics exportieren und Exporte an bestimmte Cloud-Ziele senden.

Es sind auch andere Methoden zum Exportieren von Customer Journey Analytics-Berichten verfügbar, wie unter [Exportübersicht](/help/analysis-workspace/export/export-project-overview.md) beschrieben.

## Informationen zum vollständigen Tabellenexport

Sie können vollständige Tabellen aus Analysis Workspace zu Cloud-Anbietern wie Google, Azure, Amazon und Adobe exportieren.

[Zu den Vorteilen des Exports vollständiger Tabellen in die Cloud](#advantages-of-exporting-to-the-cloud) zählen die Möglichkeit, Millionen von Zeilen einschließlich berechneter Metriken, Strukturdatenausgaben in verketteten Werten und mehr zu exportieren.

Berücksichtigen Sie beim Exportieren vollständiger Tabellen Folgendes:

* Stellen Sie vor dem Export in die Cloud sicher, dass Ihre Tabellen, Ihre Umgebung und Ihre Berechtigungen die [Exportanforderungen](#export-requirements) erfüllen.

* Einige [Funktionen](#unsupported-features) und [Komponenten](#unsupported-components) werden beim Exportieren vollständiger Tabellen in die Cloud nicht unterstützt.

Verwenden Sie den folgenden Prozess beim Exportieren vollständiger Tabellen in die Cloud:

1. [Konfigurieren eines Cloud-Kontos](/help/components/exports/cloud-export-accounts.md)

1. [Konfigurieren eines Speicherorts für das Konto](/help/components/exports/cloud-export-locations.md)

1. [Exportieren einer vollständigen Tabelle aus Workspace](#export-full-tables-from-analysis-workspace)

1. [Zugriff auf Daten in der Cloud](#view-exported-data-and-manifest-file) und [Verwaltung der Exporte in Adobe](/help/components/exports/manage-exports.md)

![Der in Schritt 1 bis 4 beschriebene vollständige Prozess zum Tabellenexport.](assets/export-full-table-process.png)

## Exportieren vollständiger Tabellen aus Analysis Workspace

>[!NOTE]
>
>Bevor Sie Daten wie in diesem Abschnitt beschrieben exportieren, lesen Sie oben im Abschnitt [Informationen zum vollständigen Tabellenexport](#understand-full-table-export) mehr über den vollständigen Tabellenexport.

So exportieren Sie vollständige Tabellen aus Analysis Workspace:

1. Falls noch nicht geschehen, konfigurieren Sie ein Exportkonto und einen Speicherort, wie unter [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md) beschrieben.

1. Klicken Sie in Analysis Workspace mit der rechten Maustaste auf die Freiformtabelle mit den zu exportierenden Daten.

1. Wählen Sie [!UICONTROL **Vollständige Tabelle exportieren**] aus.

   ![Das Dropdown-Menü der Freiformtabelle mit hervorgehobener Option Vollständige Tabelle exportieren.](assets/export-full-table.png)

1. Geben Sie im Dialogfeld [!UICONTROL **Neuer vollständiger Tabellenexport**] die folgenden Informationen an:

   | Feldname | Funktion |
   |---------|----------|
   | Name | Geben Sie einen Namen für den Export an. Dieser Name wird in der Liste der Exporte angezeigt. |
   | Tags | Sie können ein vorhandenes Tag auf den Export anwenden oder ein neues Tag erstellen und anwenden. <p>Um ein vorhandenes Tag auf den Export anzuwenden, wählen Sie beliebige Tags aus dem Dropdown-Menü aus. Alle Tags in Ihrem Unternehmen können angewendet werden<!-- double-check this -->.</p> <p>Geben Sie zum Erstellen eines neuen Tags den Namen des neuen Tags ein und drücken Sie dann die Eingabetaste.</p><p>Beachten Sie beim Anwenden von Tags auf einen Export Folgendes: <ul><li>Es ist möglich, in der Exporttabelle Tags, die Sie verwenden, zu filtern, oder nach diesen zu suchen.</li> <li>Tags, die auf ein Projekt angewendet werden, werden beim Exportieren einer vollständigen Tabelle nicht automatisch angewendet, wie unter „Konfigurieren von Spalten auf der Seite „Exporte“ in [Exporte verwalten](/help/components/exports/manage-exports.md) beschrieben. (Alternativ werden beim [Planen eines vollständigen Projekts für den Export](/help/analysis-workspace/export/t-schedule-report.md) alle auf das Projekt angewendeten Tags automatisch auf den Export angewendet.) <!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></li></ul> |
   | Beschreibung | Fügen Sie eine Beschreibung zu dem Export hinzu. Beim Anzeigen von Exporten können Sie die Beschreibungen als Spalte auf der [Seite Exporte](/help/components/exports/manage-exports.md) anzeigen. |
   | Datenansicht | Wählen Sie die Datenansicht mit den Komponenten aus, die Sie in den Export einbeziehen möchten. Das Dropdown-Menü für die Datenansicht befindet sich in der oberen linken Ecke des Dialogfelds und kann durch das Symbol für die Datenansicht ![data view icon](assets/data-view-icon.png) identifiziert werden.  <p>**Hinweis:** Wenn Sie eine Datenansicht auswählen, in der Komponenten fehlen, die bereits in Ihrer Datentabelle enthalten sind, werden Sie aufgefordert, die Datentabelle zu löschen und sie mithilfe von Komponenten neu zu erstellen, die in der ausgewählten Datenansicht enthalten sind. </p> |
   | Lookback-Fenster | Wählen Sie den Berichtszeitrahmen aus, der in jede Exportdatei aufgenommen werden soll. Die Optionen umfassen [!UICONTROL **Heute**], [!UICONTROL **Gestern**], [!UICONTROL **Letzte 7 Tage**], [!UICONTROL **Letzte 30 Tage**], [!UICONTROL **Diese Woche**] und [!UICONTROL **Diesen Monat**]. <p>Diese Option wird nicht angezeigt, wenn [!UICONTROL **Exporthäufigkeit**] auf [!UICONTROL **Jetzt senden (einmalig)**] festgelegt ist. |
   | Datentabelle | Zeigt die Freiformtabelle an, die exportiert wird. Sie können die Datentabelle ändern, indem Sie Komponenten aus dem linken Panel in die Tabelle ziehen. Die Tabelle wird dynamisch aktualisiert, wenn Sie Komponenten zur Arbeitsfläche hinzufügen.  <p>Alle Segmente, die auf die vollständige Tabelle im Projekt angewendet wurden, werden oben in jeder einzelnen Spalte in der Tabelle angezeigt.</p> |
   | Leeren | Löscht den Inhalt der Datentabelle. Auf diese Weise können Sie direkt im Dialogfeld „Neuer vollständiger Tabellenexport“ mit dem Erstellen einer neuen Tabelle beginnen. |
   | Exporthäufigkeit | Legen Sie fest, wie oft der Export erfolgen soll. <p>Sie können [!UICONTROL **Jetzt senden (einmalig)**] wählen, um den Export nur einmal zu senden. Bei Auswahl dieser Option wird der Export sofort gestartet.<p>Sie können alternativ festlegen, dass der Export gemäß einem festgelegten Zeitplan gesendet wird. Zu den Optionen beim Versand gemäß Zeitplan zählen [!UICONTROL **Täglich**], [!UICONTROL **Wöchentlich**], [!UICONTROL **Monatlich am Wochentag**], [!UICONTROL **Monatlich am Tag des Monats**], [!UICONTROL **Jährlich am Tag des Monats**] und [!UICONTROL **Jährlich an einem bestimmten Datum**]. </p><p>Beachten Sie bei der Auswahl einer Exporthäufigkeit Folgendes:</p><ul><li>Die Optionen im Feld [!UICONTROL **Lookback-Fenster**] ändern sich je nachdem, was Sie hier auswählen.<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>Je nach ausgewählter Option werden zusätzliche Konfigurationsfelder angezeigt.</li></ul> |
   | Startet am | Der Tag und die Uhrzeit, an dem bzw. zu der der geplante Export beginnen soll. <p>Diese Option ist nur bei Auswahl einer geplanten Exporthäufigkeit verfügbar.</p> |
   | Endet am | Der Tag und die Uhrzeit, an dem bzw. zu der der geplante Export abläuft. Der geplante Export wird nach dem von Ihnen festgelegten Datum und der von Ihnen festgelegten Uhrzeit nicht mehr ausgeführt. <p>Diese Option ist nur bei Auswahl einer geplanten Exporthäufigkeit verfügbar.</p> |
   | Dateiformat | Wählen Sie aus, ob die Daten im .csv- oder .json-Format exportiert werden sollen. |
   | Konto | Wählen Sie das Cloud-Exportkonto aus, an das die Daten gesendet werden sollen. <p>Wenn Sie noch kein Cloud-Konto konfiguriert haben, das Sie verwenden möchten, können Sie auch ein neues Konto konfigurieren:<ol><li>Wählen Sie [!UICONTROL **Konto hinzufügen**] aus und geben Sie dann die folgenden Informationen an:<ul><li>[!UICONTROL **Name des Standortkontos**]: Geben Sie einen Namen für das Standortkonto an. Dieser Name wird beim Erstellen eines Speicherorts angezeigt. </li><li>[!UICONTROL **Beschreibung des Standortkontos**]: Geben Sie eine kurze Beschreibung des Kontos ein, um es von anderen Konten desselben Kontotyps zu unterscheiden.</li><li>[!UICONTROL **Kontotyp**]: Wählen Sie den Typ des Cloud-Kontos aus, in das Sie exportieren. Verfügbare Kontotypen sind Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake und AEP Data Landing Zone.</li></ul><li>Um die Konfiguration Ihres Kontos abzuschließen, fahren Sie mit dem unten stehenden Link fort, der dem von Ihnen ausgewählten [!UICONTROL **Kontotyp**] entspricht:<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | Name des Speicherorts | Wählen Sie den Speicherort in dem Konto aus, an den die Exportdaten gesendet werden sollen.<p>Falls Sie den Speicherort, den Sie für das ausgewählte Konto verwenden möchten, noch nicht konfiguriert haben, können Sie auch einen neuen Speicherort konfigurieren:<ol><li>Wählen Sie [!UICONTROL **Speicherort hinzufügen**] aus und geben Sie dann die folgenden Informationen an: <ul><li>[!UICONTROL **Name:**] Der Name des Speicherorts.</li><li>[!UICONTROL **Beschreibung**]: Geben Sie eine kurze Beschreibung des Speicherorts an, um ihn von anderen Speicherorten im Konto zu unterscheiden.</li><li>[!UICONTROL **Standortkonto**]: Wählen Sie das Konto aus, in dem Sie den Speicherort erstellen möchten.</li></ul><li>Um die Konfiguration Ihres Speicherorts abzuschließen, fahren Sie mit dem untenstehenden Link fort, der dem Kontotyp entspricht, den Sie im Feld [!UICONTROL **Standortkonto**] ausgewählt haben:<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone).</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |

   {style="table-layout:auto"}

1. Wählen Sie auf [!UICONTROL **Speichern**] aus, um den Export zu speichern.

   Die Daten werden mit der von Ihnen angegebenen Häufigkeit an das von Ihnen angegebene Cloud-Konto gesendet.

1. (Optional) Unabhängig davon, ob Sie den Export jetzt oder nach einem festgelegten Zeitplan senden, können Sie ihn nach der Erstellung auf der [Seite Exporte](/help/components/exports/manage-exports.md) anzeigen und verwalten und in den [Exportprotokollen](/help/components/exports/manage-export-logs.md) anzeigen.</p>

## Verwalten von Exporten

Nachdem Daten aus Analysis Workspace exportiert wurden, können Sie bestehende Exporte bearbeiten, erneut exportieren, duplizieren, taggen oder löschen, wie in [Verwalten von Exporten](/help/components/exports/manage-exports.md) beschrieben.

## Anzeigen von exportierten Daten und der Manifestdatei

### Exportierte Daten

Exportierte Daten sind als komprimierte Datei in dem von Ihnen konfigurierten Cloud-Ziel verfügbar, wie in [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md) und [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md) beschrieben.

Abhängig davon, ob Sie CSV oder JSON als Dateiformat ausgewählt haben, lautet der Dateiname der komprimierten Datei wie folgt:

* `cja-export-{reportInstanceId}-{idx}.csv.gz`

* `cja-export-{reportInstanceId}-{idx}.json.gz`

>[!NOTE]
>
>Sie wählen das Dateiformat im Feld [!UICONTROL **Dateiformat**] beim Exportieren der Tabelle aus, wie in [Exportieren vollständiger Tabellen aus Analysis Workspace](#export-full-tables-from-analysis-workspace) beschrieben.

### Manifestdatei

Eine Manifestdatei mit dem Dateinamen `cja-export-{reportInstanceId}-{idx}.json.gz` ist in jedem erfolgreichen Exportversand enthalten, der mindestens eine Datei enthält. Mit der Manifestdatei können Sie bestätigen, dass alle Dateien erfolgreich bereitgestellt wurden. Sie enthält die folgenden Informationen:

* Eine Liste aller zugestellten Dateien

* Die MD5-Prüfsumme jeder Datei

<!-- add in  what the file name, structure, and file format will be -->

## Vorteile des Exports in die Cloud

Das Exportieren von Customer Journey Analytics-Daten in die Cloud ermöglicht Ihnen Folgendes:

* Exportieren Sie an einen gemeinsamen Speicherort, z. B. Adobe Experience Platform Data Landing Zone, Google Cloud Platform, Microsoft Azure, Amazon S3 oder Snowflake.

* Speichern Sie große Mengen historischer Daten.

  Diese Art von Daten kann verwendet werden, um langfristige Trends zu erkennen, um Business Intelligence zu erhalten und letztendlich zu einer besseren geschäftlichen Entscheidungsfindung zu führen.

* Exportieren Sie vollständige Tabellen, die Tausende oder Millionen von Zeilen enthalten ( je nach Lizenztyp 3 Millionen, 30 Millionen, 150 Millionen oder 300 Millionen Zeilen). Andere Exportmethoden erlauben maximal 50.000 Zeilen.

* Schließen Sie berechnete Metriken in die exportierten Customer Journey Analytics-Daten ein.

* Strukturieren Sie die Datenausgabe als verkettete Werte.

* Exportieren Sie einmalig oder gemäß einem Zeitplan. (Auch verfügbar mit [anderen Exportoptionen](/help/analysis-workspace/export/export-project-overview.md).)

* Exportieren Sie Dateien im CSV- oder JSON-Format. (Auch verfügbar mit [anderen Exportoptionen](/help/analysis-workspace/export/export-project-overview.md).)

* Exportieren Sie Tabellen, die mehrere Dimensionen enthalten.

## Exportanforderungen {#export-requirements}

### Mindestanforderungen

Stellen Sie sicher, dass Ihre Tabellen, Ihre Umgebung und Ihre Berechtigungen die folgenden Anforderungen erfüllen:

* **Tabellen:** Alle Tabellen müssen mindestens eine Dimension in der Zeile und eine Metrik in jeder Spalte enthalten, damit sie mit einem vollständigen Tabellenexport unterstützt werden.

* **Umgebung:** Stellen Sie sicher, dass die von Customer Journey Analytics verwendeten [IP-Adressen](/help/technotes/ip-addresses.md) und [Domains](/help/technotes/domains.md) durch die Firewall ihrer Organisation zugelassen werden.

* **Berechtigungen:** In der Adobe Admin Console muss Benutzenden ein Produktprofil zugewiesen werden, das über die Berechtigung [!UICONTROL **Vollständiger Tabellenexport**] verfügt, um vollständige Tabellen exportieren zu können. Informationen zum Zuweisen einer Berechtigung zu einem Produktprofil in der Admin Console finden Sie unter [Berechtigung für Customer Journey Analytics in der Admin Console](/help/technotes/access-control.md).

  >[!NOTE]
  >
  >  Benutzende, denen die [Rolle Produktadmin](/help/technotes/access-control.md#product-admin-role) zugewiesen ist, haben immer Zugriff auf den Export vollständiger Tabellen. Diese Benutzenden müssen nicht über die Berechtigung [!UICONTROL **Vollständiger Tabellenexport**] verfügen.


### Nicht unterstützte Funktionen

Die folgenden Funktionen werden nicht unterstützt und automatisch aus vollständigen Tabellenexporten entfernt:

* Prozentsatz
* Gesamt
* Suchfilterung
* Statische Zeilen
* Datumsausrichtung
* Metriken aus Zusammenfassungsdatensätzen
* Dynamische Dimensionen

  Weitere Informationen finden Sie unter [Dynamische und statische Dimensionselemente in Freiformtabellen](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).
* Dimensionen in der ersten Aufschlüsselung werden konvertiert und als sekundäre Dimension in der Zeile der exportierten Tabelle hinzugefügt. Alle anderen Aufschlüsselungen werden nicht in die Tabelle aufgenommen
* Die Sortierung wird für die meisten Datensätze nicht unterstützt. Daten können für kleine Datensätze sortiert werden

### Nicht unterstützte Komponenten

Die folgenden Komponenten werden nicht unterstützt und Analysis Workspace fordert Sie auf, sie aus Ihrer Tabelle zu entfernen, wenn Sie einen vollständigen Tabellenexport durchführen:

* Berechnete Metriken, die grundlegende oder erweiterte Funktionen in der Metrikdefinition verwenden (weitere Informationen finden Sie unter [Grundlegende Funktionen](/help/components/calc-metrics/cm-functions.md) und [Erweiterte Funktionen](/help/components/calc-metrics/cm-adv-functions.md))
* Komponenten, die von einer bzw. einem Admin eingeschränkt wurden, können nicht exportiert werden (weitere Informationen finden Sie im Abschnitt *Filtern nach Data Governance-Richtlinien in Datenansichten* unter [Beschriftungen und Richtlinien](/help/data-views/data-governance.md))
* Jede Dimension, die alle der folgenden Kriterien erfüllt:
   * Wurde aus einem Feld erstellt, das Teil eines [Arrays von Objekten](/help/use-cases/object-arrays.md) ist (ähnlich wie Variablen mit mehreren Werten in Adobe Analytics)
   * Hat [Persistenz aktiviert](/help/data-views/component-settings/persistence.md)
   * Verwendet keine [Bindungsdimension](/help/use-cases/data-views/binding-dimensions-metrics.md)
* Mehrere Dimensionen, die aus Feldern stammen, die auf verschiedene [Arrays von Objekten](/help/use-cases/object-arrays.md) verweisen. (Mehrere Dimensionen, die auf dasselbe Array von Objekten verweisen, sind zulässig.)
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

Der vollständige Tabellenexport unterstützt berechnete Metriken, die ein nicht standardmäßiges Attributionsmodell verwenden (wie im Abschnitt *Verwenden eines nicht standardmäßigen Attributionsmodells* in [Spalteneinstellungen](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) beschrieben).

Wenn ein nicht standardmäßiges Attributionsmodell in einem Bericht verwendet wird, wird das im Bericht verwendete Zuordnungsmodell entweder ignoriert oder beibehalten, je nachdem, ob der Bericht eine einzelne Dimension oder mehrere Dimensionen umfasst:

* **Bei Berichten, die eine Metrikattribution in einer einzigen Dimension enthalten: die** [Metrikattribution](/help/data-views/component-settings/attribution.md) überschreibt das [Zuordnungsmodell](/help/data-views/component-settings/persistence.md) entsprechend der normalen Vorgehensweise bei Verwendung der Metrikattribution.

  Beispielsweise überschreibt eine Metrikattribution „Erstkontakt“ eine Dimensionszuordnung „Zuletzt verwendet“.

* **Bei Berichten, die eine Metrikattribution in mehreren Dimensionen enthalten: die** [Metrikattribution](/help/data-views/component-settings/attribution.md) wird zusätzlich zum [Zuordnungsmodell](/help/data-views/component-settings/persistence.md) der Dimension angewendet.

  Beispielsweise wird eine Metrikattribution „Erstkontakt“ zusätzlich zur Dimensionszuordnung „Zuletzt verwendet“ angewendet. Darüber hinaus wird die Metrikattribution nach der Zuordnung auf Dimensionselementpaare angewendet, als würde es sich um einzelne Dimensionselemente handeln, und nicht auf jedes Dimensionselement einzeln, wie es normalerweise in einer Freiformtabelle der Fall ist.

  >[!NOTE]
  >
  >Berichte mit mehreren Dimensionen werden nur beim Exportieren von Daten in die Cloud unterstützt, wie in diesem Artikel beschrieben.

## Vergleich des vollständigen Tabellenexports (in Customer Journey Analytics) nach Data Warehouse (in Adobe Analytics)

Wenn Sie Data Warehouse zuvor zum Exportieren von Adobe Analytics-Daten verwendet haben, können Sie anhand der folgenden Tabelle die Unterschiede zwischen dem Exportieren vollständiger Tabellen in Customer Journey Analytics und dem Exportieren von Daten mit Data Warehouse in Adobe Analytics besser verstehen.


| Funktion | Vollständiger Tabellenexport in Customer Journey Analytics | Data Warehouse in Adobe Analytics |
|---------|----------|---------|
| Erstellen eines benutzerspezifischen Berichts | Ja | Ja |
| Berechnete Metriken | Ja | Nein |
| Segmente | Ja | Begrenzt |
| Dimensionen | Limit von 5 | Unbegrenzt |
| Metriken | Limit von 5 | Unbegrenzt |
| Berichtszeilen | Je nach Stufe ein Limit von 3 Millionen, 30 Millionen, 150 Millionen oder 300 Millionen | Unbegrenzt |
| Anzahl der Berichte | Unbegrenzt | Unbegrenzt |
| Ad-hoc-Versand (einmalig) | Ja | Ja |
| Planen eines wiederkehrenden Versands | Ja | Ja |
| E-Mail-Versand | Nein | Ja |
| FTP / SFTP | Nein | Unterstützung der Vorgängerversion |
| Azure | Ja | Ja |
| Amazon S3 | Ja | Ja |
| Google Cloud Platform | Ja | Ja |
| Snowflake | Ja | Nein |
| Bereitstellungshäufigkeit | Täglich | Stündlich |
