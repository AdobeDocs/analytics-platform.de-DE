---
title: Erstellen eines Daten-Feeds
description: Erfahren Sie, wie ein Daten-Feed erstellt wird und welche Dateiinformationen Adobe zur Verfügung gestellt werden müssen.
hide: true
feature: Components
source-git-commit: 54a7f59847b752a4e898b488a90520e8b31d3622
workflow-type: tm+mt
source-wordcount: '2439'
ht-degree: 19%

---

# Erstellen eines Daten-Feeds

Stellen Sie Adobe beim Erstellen eines Daten-Feeds Folgendes zur Verfügung:

* Informationen über das Ziel, an das Rohdatendateien gesendet werden sollen

* Die Daten, die in jede Datei aufgenommen werden sollen

* Die Häufigkeit, mit der der Daten-Feed gesendet werden soll (einschließlich des Lookback-Fensters, wenn Sie verspätete Treffer einbeziehen möchten)

Bevor Sie einen Daten-Feed erstellen, müssen Sie über grundlegende Kenntnisse zu Daten-Feeds verfügen und sicherstellen, dass Sie alle Voraussetzungen erfüllen. Weitere Informationen finden Sie unter [Datenfeeds – Überblick](data-feed-overview.md).

## Erstellen oder Konfigurieren eines Daten-Feeds {#create-and-configure-data-feed}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_export_file"
>title="Manifest"
>abstract="Wählen Sie aus, ob bei jeder Daten-Feed-Bereitstellung eine Manifestdatei enthalten sein soll. Manifestdateien enthalten Informationen für jede im Daten-Feed enthaltene Datei. Beim Senden von Daten-Feed-Daten in einem einzelnen Paket können Sie auch eine Finish-Datei einschließen. Manifestdateien werden jedoch empfohlen. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_notify"
>title="Benachrichtigen bei Abschluss"
>abstract="Geben Sie eine oder mehrere E-Mail-Adressen an, an die nach dem Versenden des Daten-Feeds eine Benachrichtigung gesendet werden soll. Mehrere E-Mail-Adressen müssen durch ein Komma getrennt werden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_lookback_date_range"
>title="Lookback-Datumsbereich"
>abstract="Steuert, wie weit Customer Journey Analytics bei der Verarbeitung der Daten-Feed-Bereitstellung zurückblickt.<br/>Mit dieser Einstellung wird das Häufigkeitsfenster (Stunde oder Tag) nicht geändert. Der Lookback-Datumsbereich kann jedoch Auswirkungen auf die bereitgestellten Daten haben. Die Segmentqualifikation, die Sitzungsberechnung und die Dimensionspersistenz sind alle vom Lookback-Datumsbereich betroffen."

<!-- markdownlint-enable MD034 -->

<!-- added help for Dynamic lookups to this page: help/export/analytics-data-feed/c-df-contents/dynamic-lookups.md -->

1. Melden Sie sich mit Ihren Adobe ID-Anmeldeinformationen bei [experiencecloud.adobe.com](https://experiencecloud.adobe.com) an.

1. Wählen Sie oben rechts das 9-Quadrat-Symbol und dann [!UICONTROL **Customer Journey Analytics**] aus.

1. Navigieren Sie in der oberen Navigationsleiste zu [!UICONTROL **Admin**] > [!UICONTROL **Daten-Feeds**].

1. Wählen [!UICONTROL **Daten-Feed erstellen**] aus.

   Eine Seite wird mit den folgenden Registerkarten angezeigt: [!UICONTROL **Details**], [!UICONTROL **Datenstruktur**] und [!UICONTROL **Versand**].

   ![Neue Daten-Feed-Seite](assets/data-feed-new.png)

1. Füllen Sie [!UICONTROL **Abschnitt**] Details“ die folgenden Felder aus:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Name**] | Der Name des Daten-Feeds. Namen müssen innerhalb der ausgewählten Report Suite eindeutig sein und können bis zu 255 Zeichen lang sein. <!--[Learn more](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique)--> |
   | [!UICONTROL **Tags**] | Wenden Sie beliebige Tags auf den Daten-Feed an, um die Kategorisierung zu erleichtern. <!--You can filter on tags as described in [Filter and search the list of data feeds](/help/export/analytics-data-feed/df-manage-feeds.md#filter-and-search-the-list-of-data-feeds) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).--> |
   | [!UICONTROL **Beschreibung**] | Geben Sie eine Beschreibung für den Daten-Feed an. Die von Ihnen hinzugefügte Beschreibung ist beim Bearbeiten des Daten-Feeds sichtbar. |
   | [!UICONTROL **Datenansicht**] | Wählen Sie die Datenansicht aus, die die zu exportierenden Daten enthält. |

1. Geben [!UICONTROL **im Abschnitt**] Datenformatierung“ die folgenden Informationen an:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Komprimierungsformat**] | Der verwendete Komprimierungstyp. **Gzip** gibt Dateien im Format `.tar.gz` aus. **Zip** gibt Dateien im Format `.zip` aus. |
   | [!UICONTROL **Verpackungstyp**] | Wählen Sie für die meisten Daten-Feeds [!UICONTROL **Mehrere Dateien**] aus. Mit dieser Option werden Ihre Daten in unkomprimierte 2-GB-Chunks unterteilt. (Wenn die Option [!UICONTROL **Mehrere Dateien**] ausgewählt ist und die unkomprimierten Daten für das Berichtsfenster weniger als 2 GB betragen, wird eine Datei gesendet.) Wenn Sie **Einzeldatei** auswählen, wird die `hit_data.tsv` in einer einzelnen, potenziell umfangreichen Datei ausgegeben. |
   | [!UICONTROL **Manifestdatei**] | Wählen Sie aus, ob bei jeder Daten-Feed-Bereitstellung eine Manifestdatei enthalten sein soll. <p>Sie können aus den folgenden Optionen wählen:</p><ul><li>**[!UICONTROL Manifestdatei]**: Enthält Informationen für jede Datei, die im Daten-Feed enthalten ist.</li><li>**[!UICONTROL Datei beenden (alt)]**: Gibt an, dass der Daten-Feed erfolgreich abgeschlossen wurde. Es sind keine weiteren Informationen enthalten. Diese Option eignet sich für bestehende Feeds, die diese Option ursprünglich verwendet haben und erneut verarbeitet werden müssen. Sie ist nur verfügbar, wenn Daten-Feed-Daten in einem einzigen Paket gesendet werden. </li><li>**[!UICONTROL None]**: Keine Datei enthalten</li></ul> |
   | [!UICONTROL **Manifest senden, auch wenn keine Daten vorhanden sind**] | Bestimmt, ob Adobe eine Manifestdatei <!--[manifest file](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md#feed-manifest)--> an das Ziel senden soll, wenn für ein Feed-Intervall keine Daten erfasst werden. Wenn Sie **Manifestdatei** auswählen, erhalten Sie eine Manifestdatei ähnlich der folgenden, wenn keine Daten erfasst werden:<p>`text`</p><p>`Datafeed-Manifest-Version: 1.0`</p><p>`Lookup-Files: 0`</p><p>`Data-Files: 0`</p><p> `Total-Records: 0`</p> |
   | [!UICONTROL **Ersetzen Sie Betriebssystemzeichenfolgen**] | Beim Erfassen von Daten können einige Zeichen (z. B. neue Zeilen) Probleme verursachen. Wählen Sie diese Option, um diese Zeichen aus den Feed-Dateien zu entfernen.<p>Diese Option erkennt die folgenden in Kundendaten eingebetteten Zeichenfolgensequenzen und ersetzt sie durch ein Leerzeichen:</p> <ul><li>**Windows:** CRLF, CR oder TAB</li><li>**Mac und Linux:** \n, \r oder \t</li></ul> |
   | [!UICONTROL **Dynamische Suchen aktivieren**] | Dynamische Suchen ermöglichen es Ihnen, zusätzliche Suchdateien in Ihrem Daten-Feed zu erhalten, die sonst nicht verfügbar sind. Mit dieser Einstellung können die folgenden Lookup-Tabellen mit jeder Daten-Feed-Datei gesendet werden:<ul><li> **Betreibername**</li><li>**Attribute für Mobilgeräte**</li><li>**Betriebssystemtyp**</li></ul><!--<p>For more information, see [Dynamic lookups](/help/export/analytics-data-feed/c-df-contents/dynamic-lookups.md).</p>--> |
   | **Zulassen von verspäteten Treffern** | Historische Daten können eingehen, nachdem die Verarbeitung eines Daten-Feed-Auftrags für eine bestimmte Stunde oder einen bestimmten Tag beendet wurde, z. B. über Treffer mit Zeitstempeln oder Datenquellen.<p>Wählen Sie diese Option aus, um Daten einzuschließen, die nach Abschluss des Daten-Feed-Auftrags innerhalb der festgelegten Reporting-Frequenz (in der Regel täglich oder stündlich) eingegangen sind. Wenn diese Option aktiviert ist, prüft das System bei jeder Verarbeitung eines Daten-Feeds alle eingegangenen verspäteten Treffer und bündelt diese mit der nächsten gesendeten Daten-Feed-Datei.</p><!--<p>For more information, see [Late-arriving hits](/help/export/analytics-data-feed/c-df-contents/late-arriving-hits.md).</p>--> |
   | **Lookback-Fenster** (für verspätete Treffer) | Diese Option wird angezeigt, wenn die Option **[!UICONTROL Verspätete Treffer zulassen]** aktiviert ist. Wählen Sie das Lookback-Fenster aus, um den Zeitrahmen der enthaltenen späten Treffer zu begrenzen. Wählen Sie **[!UICONTROL Unbegrenzt]** aus, wenn Sie alle verspäteten Treffer unabhängig von der Verspätung zulassen möchten. Sie können ein voreingestelltes Intervall auswählen, z. B. **[!UICONTROL 1 Stunde]**, **[!UICONTROL 2 Stunden]**, **[!UICONTROL 1 Woche]**, **[!UICONTROL 2 Wochen]** usw. Oder wählen Sie **[!UICONTROL Benutzerdefiniertes Lookback-Fenster]** und geben Sie dann im Feld **[!UICONTROL Benutzerdefiniertes Lookback]** ein Lookback-Fenster mit bis zu 26.280 Stunden an. |

1. Stellen Sie [!UICONTROL **Abschnitt**] Datenstruktur) sicher, dass im Feld **[!UICONTROL Datenansicht“ die richtige]** ausgewählt ist. <p>Beachten Sie bei der Auswahl einer Datenansicht Folgendes:</p> <ul><li>Wenn mehrere Daten-Feeds für dieselbe Datenansicht erstellt werden, muss jeder Daten-Feed unterschiedliche Spaltendefinitionen haben.</li><li>Die Liste der verfügbaren Spalten hängt vom Anmeldeunternehmen ab, zu dem die ausgewählte Datenansicht gehört. Wenn Sie die Datenansicht ändern, kann sich die Liste der verfügbaren Spalten ändern. </li></ul>

1. Verwenden Sie eine oder beide der folgenden Methoden, um zu bestimmen, welche Datenspalten in den Feed aufgenommen werden sollen:

   * **Spalten einzeln hinzufügen:** Wählen Sie im Abschnitt **[!UICONTROL Verfügbar]** auf der linken Seite alle Spalten aus, die Sie einbeziehen möchten, und klicken Sie dann auf **[!UICONTROL Einschließen]**. Alle Datenspalten in Adobe Analytics sind verfügbar. Sie können mehrere Spalten auswählen, indem Sie **[!UICONTROL Umschalt]** gedrückt halten oder **[!UICONTROL Befehl]** (in macOS) oder **[!UICONTROL Strg]** (in Windows) gedrückt halten. Klicken Sie auf **[!UICONTROL Alle hinzufügen]**, um alle Spalten in einen Daten-Feed einzubeziehen.

     Hinzugefügte Spalten werden im Abschnitt **[!UICONTROL Enthalten]** auf der rechten Seite angezeigt.

   * **Spaltenvorlage hinzufügen:** Wählen Sie im Feld **[!UICONTROL Spaltenvorlagen]** eine hinzuzufügende Spaltenvorlage aus. Eine Spaltenvorlage ist eine vordefinierte Gruppe von Spalten, und Adobe bietet standardmäßig mehrere Spalten.

     Alle in der Vorlage enthaltenen Spalten werden im Bereich **[!UICONTROL Enthalten]** auf der rechten Seite angezeigt.

1. (Optional) Um eine Spaltenvorlage zu erstellen, die auf dem aktuell erstellten Daten-Feed basiert, wählen Sie **[!UICONTROL Als Vorlage speichern]**, geben Sie einen Namen für die Vorlage an und klicken Sie auf **[!UICONTROL Speichern]**. Diese Option ist nützlich, wenn Sie zusätzliche Daten-Feeds mit denselben Spalten erstellen möchten.

   ![Erstellen einer Spaltenvorlage beim Erstellen eines Daten-Feeds](assets/data-feed-template-create2.png)

1. (Optional) Um eine Liste der enthaltenen Spalten im CSV-Format herunterzuladen, wählen Sie **[!UICONTROL Spalten herunterladen]** aus. Diese Option kann für Daten-Feeds mit einer großen Anzahl von Spalten nützlich sein.

1. Geben [!UICONTROL **im Abschnitt**] Versand“ die folgenden Informationen an:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Feed-Typ**] | Wählen Sie den Feed-Typ aus, den Sie erstellen möchten:<ul><li>[!UICONTROL **Live-Feed**]: Exportiert aktuelle und zukünftige Daten.</li><li>[!UICONTROL **Aufstockungs-Feed**]: Exportiert historische Daten zwischen zwei früheren Datumsangaben.</li></ul> |
   | [!UICONTROL **Startdatum**] | Geben Sie das Datum an, an dem der Daten-Feed beginnen soll. Um sofort mit der Verarbeitung von Daten-Feeds für historische Daten zu beginnen, stellen Sie sicher, dass [!UICONTROL **Aufstockungs-Feed**] ausgewählt ist, und setzen Sie dieses Datum auf ein beliebiges Datum in der Vergangenheit, wenn Daten erfasst werden. Das Startdatum basiert auf der Zeitzone der Datenansicht. |
   | [!UICONTROL **Enddatum**] | Geben Sie das Datum an, an dem der Daten-Feed beendet werden soll. Das Enddatum basiert auf der Zeitzone der Datenansicht. |
   | [!UICONTROL **Häufigkeit**] | Legen Sie fest, wie oft der Daten-Feed gesendet werden soll. Ereignisse mit Zeitstempeln, die in das Häufigkeitsfenster fallen, werden in den Daten-Feed-Versand aufgenommen. Die Felder [!UICONTROL **Lookback**] Datumsbereich und [!UICONTROL **Verarbeitungsverzögerung**] können sich auch darauf auswirken, welche Ereignisse für die von Ihnen gewählte Versandfrequenz in die Daten aufgenommen werden.<p>Wählen Sie diese Option aus, um Daten für eine Stunde oder für einen Tag einzubeziehen:</p><ul><li>**Täglich**: Feeds enthalten Daten eines ganzen Tages von Mitternacht bis Mitternacht in der Zeitzone der Datenansicht. Verwenden Sie diese Option für Aufstockungs-Feeds oder für Live-Feeds.</li><li>**Stündlich**: Feeds enthalten Daten für eine einzige Stunde. Verwenden Sie diese Option für Live-Feeds.</li></ul> |
   | [!UICONTROL **Lookback-Datumsbereich**] | Steuert, wie weit Customer Journey Analytics bei der Verarbeitung der Daten-Feed-Bereitstellung zurückblickt. <p>Diese Einstellung ändert nicht das Häufigkeitsfenster (Stunde oder Tag), das den Zeitrahmen der Ereignisse definiert, die in die Daten-Feed-Ausgabe aufgenommen werden sollen. Der Lookback-Datumsbereich kann jedoch die bereitgestellten Daten wie folgt beeinflussen: </p><ul><li>**Segmentqualifikation**: Wenn ein Segment auf Ihre Daten-Feed-Definition angewendet wird, bestimmen alle Ereignisse innerhalb des Lookback-Datumsbereichs, ob eine Person qualifiziert ist. Die Container-Einstellung des Segments bestimmt den Umfang. (Mögliche Container sind: Person, Sitzung oder Ereignis. B2B hat die folgenden zusätzlichen Container: Globales Konto, Konto, Opportunity, Einkaufsgruppe.)  <p>Wenn beispielsweise ein Personen-Container verwendet wird und die Person für den Datumsbereich „Lookback“ qualifiziert ist, sind auch alle Ereignisse dieser Person im Häufigkeitsfenster qualifiziert.</p></li><li>**Sitzungsberechnung**: Sitzungsgrenzen werden anhand von Daten innerhalb des Lookback-Datumsbereichs berechnet.</li><li>**Dimension-Persistenz**: Wenn Sie sich dafür entscheiden, die Persistenz für eine einzelne Dimension festzulegen, wählen Sie auch eine Gültigkeit aus, um zu bestimmen, wie lange ein Dimensionselement über das Ereignis hinaus bestehen bleibt, für das es festgelegt ist. <p>Der Lookback-Datumsbereich wirkt sich auf die Persistenz der Dimensionen aus, wenn die Gültigkeit auf eine der folgenden Optionen in der Datenansicht eingestellt ist:</p><ul><li>Für jede Dimension in der Daten-Feed-Definition, die [!UICONTROL **Reporting-Fenster**] als Ablaufdatum verwendet, wird der Lookback-Datumsbereich zum neuen Reporting-Fenster.</li><li>Für jede Dimension in der Daten-Feed-Definition, die [!UICONTROL **Benutzerdefinierte Zeit**] als Ablaufdatum verwendet, wird die benutzerdefinierte Zeit ignoriert und der Lookback-Datumsbereich wird für die Gültigkeitsdauer der Dimension verwendet, wenn die ausgewählte benutzerdefinierte Zeit über den Datumsbereich des Lookback hinausgeht.<p>Weitere Informationen zum Festlegen der Persistenz für Dimensionen in der Datenansicht finden Sie unter [Persistenzkomponenteneinstellungen](/help/data-views/component-settings/persistence.md).</p></li></ul> |
   | [!UICONTROL **Verarbeitungsverzögerung**] | Wählen Sie aus, ob eine bestimmte Zeitdauer gewartet werden soll, bevor eine Daten-Feed-Datei verarbeitet wird. Eine Verzögerung kann nützlich sein, um mobilen Implementierungen die Möglichkeit zu geben, dass Offlinegeräte online gehen und Daten senden können. Sie kann auch verwendet werden, um die serverseitigen Prozesse Ihrer Organisation bei der Verwaltung zuvor verarbeiteter Dateien zu berücksichtigen. In den meisten Fällen ist keine Verzögerung erforderlich. Sie können einen Feed um bis zu 8 Stunden (480 Minuten) oder sogar länger verzögern, wenn Sie einen benutzerdefinierten Zeitraum auswählen (9.999 Minuten Verzögerung oder etwa 1 Woche).<p>Wenn keine Verzögerung festgelegt ist, werden nur die Ereignisse, die in das Häufigkeitsfenster (letzter Tag oder letzte Stunde) fallen, in den Feed eingeschlossen. |

1. Konfigurieren Sie [!UICONTROL **Abschnitt**] Ziel“ das Ziel, an das die Daten gesendet werden sollen.

   >[!NOTE]
   >
   >Beachten Sie bei der Konfiguration eines Berichtsziels Folgendes:
   >
   ><!--* Adobe recommends using a cloud account for your report destination. [Legacy FTP and SFTP accounts](/help/components/locations/configure-import-accounts.md) are available, but are not recommended.-->
   >* Alle zuvor konfigurierten Cloud-Konten stehen für Daten-Feeds zur Verfügung. Sie können Cloud-Konten über den Standort-Manager unter [Komponenten > Exporte > Speicherort-Konten](/help/components/exports/cloud-export-accounts.md) konfigurieren.
   >
   >* Cloud-Konten sind mit Ihrem Customer Journey Analytics-Benutzerkonto verknüpft. Andere Benutzer können von Ihnen konfigurierte Cloud-Konten nur verwenden oder anzeigen, wenn Sie sie für alle Benutzer in Ihrer Organisation verfügbar machen.
   >
   >* Sie können alle Speicherorte bearbeiten, die Sie über den Standort-Manager unter [Komponenten > Exporte > Speicherorte](/help/components/exports/cloud-export-locations.md) erstellen.

   Füllen Sie die folgenden Felder aus:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Konto**] | Führen Sie einen der folgenden Schritte aus:<ul><li>**Vorhandenes Konto verwenden:** Wählen Sie das Dropdown-Menü neben dem Feld **[!UICONTROL Konto]** aus. Oder geben Sie den Kontonamen ein und wählen Sie ihn dann aus dem Dropdown-Menü aus. <p>Konten stehen Ihnen nur zur Verfügung, wenn Sie sie konfiguriert haben oder wenn sie für eine Organisation freigegeben wurden, der Sie angehören.</p></li><li>**Neues Konto erstellen:** Wählen Sie **[!UICONTROL Neu hinzufügen]** unter dem Feld **[!UICONTROL Konto]** aus. Informationen zum Konfigurieren des Kontos finden Sie unter [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md).</li></ul> |
   | [!UICONTROL **Ort**] | Führen Sie einen der folgenden Schritte aus:<ul><li>**Vorhandenen Speicherort verwenden:** Wählen Sie das Dropdown-Menü neben dem Feld **[!UICONTROL Speicherort]** aus. Oder geben Sie den Ortsnamen ein und wählen Sie ihn dann aus dem Dropdown-Menü aus.</li><li>**Neuen Speicherort erstellen:** Wählen Sie **[!UICONTROL Neu hinzufügen]** unter dem Feld **[!UICONTROL Speicherort]** aus. Informationen zum Konfigurieren des Speicherorts finden Sie unter [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md).</li></ul> |
   | [!UICONTROL **Nach Abschluss benachrichtigen**] | Geben Sie eine oder mehrere E-Mail-Adressen an, an die eine Benachrichtigung gesendet werden soll, nachdem der Daten-Feed erfolgreich gesendet wurde oder nicht gesendet werden kann. Mehrere E-Mail-Adressen müssen durch ein Komma getrennt werden. |
   | [!UICONTROL **Manifest aktivieren**] | Wählen Sie aus, ob bei jeder Daten-Feed-Bereitstellung eine Manifestdatei enthalten sein soll. <p>Sie können aus den folgenden Optionen wählen:</p><ul><li>**[!UICONTROL Manifestdatei]**: Enthält Informationen für jede Datei, die im Daten-Feed enthalten ist.</li><li>**[!UICONTROL Datei beenden (alt)]**: Gibt an, dass der Daten-Feed erfolgreich abgeschlossen wurde. Es sind keine weiteren Informationen enthalten. Diese Option eignet sich für bestehende Feeds, die diese Option ursprünglich verwendet haben und erneut verarbeitet werden müssen. Sie ist nur verfügbar, wenn Daten-Feed-Daten in einem einzigen Paket gesendet werden. </li><li>**[!UICONTROL None]**: Keine Datei enthalten</li></ul> |

1. Wählen Sie **[!UICONTROL Speichern]** aus.

## Spaltenvorlagen verwalten

Mit Vorlagen können Sie dieselben Spalten für zukünftige Daten-Feeds wiederverwenden, die Sie erstellen.

Bei der Verwaltung von Vorlagen können Sie neue Vorlagen erstellen, bereits erstellte Vorlagen verwenden, Vorlagen kopieren, Vorlagen bearbeiten und Vorlagen löschen.

**[!UICONTROL Admin]** > **[!UICONTROL Daten-Feeds]** > **[!UICONTROL Vorlagen verwalten]**

![Spaltenvorlagen verwalten](assets/data-feed-template-manage.png)

### Erstellen einer Spaltenvorlage

Beim Erstellen mehrerer Daten-Feeds, die dieselben Spalten verwenden, empfiehlt Adobe die Erstellung von Spaltenvorlagen. Alle von Ihnen erstellten Spaltenvorlagen stehen allen Personen in Ihrem Unternehmen zur Verfügung.

So erstellen Sie eine Spaltenvorlage:

1. Navigieren Sie in Adobe Analytics [!UICONTROL **Admin**] > [!UICONTROL **Daten-Feeds**] > **[!UICONTROL Vorlagen verwalten]**.

1. Wählen Sie **[!UICONTROL Neue Vorlage erstellen]** aus, um eine neue Spaltenvorlage zu erstellen.

   ![Spaltenvorlage erstellen](assets/data-feed-template-create.png)

1. Geben Sie im Feld **[!UICONTROL Vorlagenname]** einen Namen für die Vorlage an.

1. Wählen **[!UICONTROL im Abschnitt &quot;]**&quot; auf der linken Seite alle Spalten aus, die Sie einbeziehen möchten, und klicken Sie dann auf **[!UICONTROL Einschließen]**. Alle verfügbaren Datenspalten in Adobe Analytics sind verfügbar. Sie können mehrere Spalten auswählen, indem Sie **[!UICONTROL Umschalt]** gedrückt halten oder **[!UICONTROL Befehl]** (in macOS) oder **[!UICONTROL Strg]** (in Windows) gedrückt halten. Klicken Sie auf **[!UICONTROL Alle hinzufügen]**, um alle Spalten in einen Daten-Feed einzubeziehen.

   Hinzugefügte Spalten werden im Abschnitt **[!UICONTROL Enthalten]** auf der rechten Seite angezeigt.

1. Wählen Sie **[!UICONTROL Speichern]** aus.

### Bearbeiten einer Spaltenvorlage

1. Navigieren Sie in Adobe Analytics [!UICONTROL **Admin**] > [!UICONTROL **Daten-Feeds**] > **[!UICONTROL Vorlagen verwalten]**.

1. Wählen Sie die Vorlage aus, die Sie bearbeiten möchten, und klicken Sie dann auf **[!UICONTROL Bearbeiten]**.

1. Nehmen Sie beliebige Änderungen vor und klicken Sie dann auf **[!UICONTROL Speichern]**.

### Kopieren einer Spaltenvorlage

1. Navigieren Sie in Adobe Analytics [!UICONTROL **Admin**] > [!UICONTROL **Daten-Feeds**] > **[!UICONTROL Vorlagen verwalten]**.

1. Wählen Sie die Vorlage aus, die Sie kopieren möchten, und klicken Sie dann auf **[!UICONTROL Kopieren]**.

1. Geben Sie im Feld **[!UICONTROL Vorlagenname]** einen Namen für die Vorlage an.

1. Nehmen Sie alle weiteren Änderungen vor und klicken Sie dann auf **[!UICONTROL Speichern]**.

### Spaltenvorlagen löschen

1. Navigieren Sie in Adobe Analytics [!UICONTROL **Admin**] > [!UICONTROL **Daten-Feeds**] > **[!UICONTROL Vorlagen verwalten]**.

1. Wählen Sie mindestens eine Vorlage aus, die Sie löschen möchten, und klicken Sie auf **[!UICONTROL Löschen]**.


<!-- why would you want to do this? -->


<!--
I don't think we need anything after this, but saving here just in case:

1. In the [!UICONTROL **Feed Information**] section, complete the following fields:
   
   | Field | Function |
   |---------|----------|
   | [!UICONTROL **Name**] | The name of the data feed. Must be unique within the selected report suite, and can be up to 255 characters in length. [Learn more](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique) |
   | [!UICONTROL **Report suite**] | The report suite that the data feed is based on. If multiple data feeds are created for the same report suite, they must have different column definitions. Only source report suites support data feeds; virtual report suites are not supported. |
   | [!UICONTROL **Email when complete**] | The email address to be notified when a feed finishes processing. The email address must be properly formatted. |
   | [!UICONTROL **Feed interval**] | Select **Daily** for backfill or historical data. Daily feeds contain a full day's worth of data, from midnight to midnight in the report suite's time zone. Select **Hourly** for continuing data (Daily is also available for continuing feeds if you prefer). Hourly feeds contain a single hour's worth of data. |
   | [!UICONTROL **Delay processing**] | Wait a given amount of time before processing a data feed file. A delay can be useful to give mobile implementations an opportunity for offline devices to come online and send data. It can also be used to accommodate your organization's server-side processes in managing previously processed files. In most cases, no delay is needed. A feed can be delayed by up to 120 minutes. |
   | [!UICONTROL **Start & end dates**] | The start date indicates the date when you want the data feed to begin. To immediately begin processing data feeds for historical data, set this date to any date in the past when data is being collected. The start and end dates are based on the report suite's time zone. |
   | [!UICONTROL **Continuous feed**] | This checkbox removes the end date, allowing a feed to run indefinitely. When a feed finishes processing historical data, a feed waits for data to finish collecting for a given hour or day. Once the current hour or day concludes, processing begins after the specified delay. |
   
1. In the [!UICONTROL **Destination**] section, in the [!UICONTROL **Type**] drop-down menu, select the destination where you want the data to be sent. 

   >[!NOTE]
   >
   >Consider the following when configuring a report destination:
   >
   >* We recommend using a cloud account for your report destination. [Legacy FTP and SFTP accounts](#legacy-destinations) are available, but are not recommended.
   >* Any cloud accounts that you previously configured are available to use for Data Feeds. You can configure cloud accounts in any of the following ways:
   >
   >   * When configuring cloud accounts for [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) 
   >   
   >   * When [importing Adobe Analytics classification data](/help/components/locations/locations-manager.md) (Any locations that are configured for importing classification data cannot be used.)
   >   
   >   * From the Locations manager, in [Components > Locations](/help/components/locations/configure-import-accounts.md) 
   >
   >* Cloud accounts are associated with your Adobe Analytics user account. Other users cannot use or view cloud accounts that you configure.
   >
   >* You can edit any locations that you create from the Locations manager in [Components > Locations](/help/components/locations/configure-import-accounts.md)

   ![Data feed destination drop-down menu](assets/datafeed-destinations-dropdown.png)

   Use any of the following destination types when creating a data feed. For configuration instructions, expand the destination type. (Additional [legacy destinations](#legacy-destinations) are also available, but are not recommended.)

   +++Amazon S3

   You can send feeds directly to Amazon S3 buckets. This destination type requires only your Amazon S3 account and the location (bucket). 

   Adobe Analytics uses cross-account authentication to upload files from Adobe Analytics to the specified location in your Amazon S3 instance.

   When using Amazon S3 with Data Feeds, only SSE-S3 encryption is supported.

   To configure an Amazon S3 bucket as the destination for a data feed:

   1. Begin creating a data feed as described in [Create and configure a data feed](#create-and-configure-a-data-feed).
   
   1. In the [!UICONTROL **Destination**] section, in the [!UICONTROL **Type**] drop-down menu, select [!UICONTROL **Amazon S3**].

      ![Amazon S3 destination](assets/datafeed-destination-amazons3.png)

   1. Select [!UICONTROL **Select location**].

      The Amazon S3 Export Locations page is displayed.

   1. (Conditional) If an Amazon S3 account (and a location on that account) has already been configured in Adobe Analytics, you can use it as your data feed destination: 

      >[!NOTE]
      >
      >Accounts are available to you only if you configured them or if they were shared with an organization you are a part of.
   
      1. Select the account from the [!UICONTROL **Select account**] drop-down menu.

         Any cloud accounts that were configured in any of the following areas of Adobe Analytics are available to use:
      
         * When importing Adobe Analytics classification data, as described in [Schema](/help/components/classifications/sets/manage/schema.md).
      
           However, any locations that are configured for importing classification data cannot be used. Instead, add a new destination as described below.

         * When configuring accounts and locations in the Locations area, as described in [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md) and [Configure cloud import and export locations](/help/components/locations/configure-import-locations.md).
   
      1. Select the location from the [!UICONTROL **Select location**] drop-down menu.

      1. Select [!UICONTROL **Save**] > [!UICONTROL **Save**].

      The destination is now configured to send data to the Amazon S3 location that you specified.
   
   1. (Conditional) If you have not previously added an Amazon S3 account:

      1. Select [!UICONTROL **Add account**], then specify the following information:
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Account name**] | A name for the account. This can be any name you choose. |
         | [!UICONTROL **Account description**] | A description for the account. |
         | [!UICONTROL **Role ARN**] | You must provide a Role ARN (Amazon Resource Name) that Adobe can use to gain access to the Amazon S3 account. To do this, you create an IAM permission policy for the source account, attach the policy to a user, and then create a role for the destination account. For specific information, see [this AWS documentation](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
         | [!UICONTROL **User ARN**] | The User ARN (Amazon Resource Name) is provided by Adobe. You must attach this user to the policy you created. |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Add location**], then specify the following information:
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Name**] | A name for the account.  |
         | [!UICONTROL **Description**] | A description for the account. |
         | [!UICONTROL **Bucket**] | The bucket within your Amazon S3 account where you want Adobe Analytics data to be sent. <p>Ensure that the User ARN that was provided by Adobe has the `S3:PutObject` permission in order to upload files to this bucket. This permission allows the User ARN to upload initial files and overwrite files for subsequent uploads.</p><p>Bucket names must meet specific naming rules. For example, they must be between 3 to 63 characters long, can consist only of lowercase letters, numbers, dots (.), and hyphens (-), and must begin and end with a letter or number. [A complete list of naming rules are available in the AWS documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html). </p> |
         | [!UICONTROL **Prefix**] | The folder within the bucket where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, `folder_name/` |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Create**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the Amazon S3 location that you specified.

      1. (Conditional) If you need to manage the destination (account and location) that you just created, it is available in the [Locations manager](/help/components/locations/locations-manager.md).
   
   +++

   +++Azure RBAC

   You can send feeds directly to an Azure container by using RBAC authentication. This destination type requires an Application ID, Tenant ID, and Secret. 

   To configure an Azure RBAC account as the destination for a data feed:

   1. If you haven't already, create an Azure application that Adobe Analytics can use for authentication, then grant access permissions in access control (IAM). 
   
      For information, refer to the [Microsoft Azure documentation about how to create an Azure Active Directory application](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal). 
   
   1. In the Adobe Analytics admin console, in the [!UICONTROL **Destination**] section, in the [!UICONTROL **Type**] drop-down menu, select [!UICONTROL **Azure RBAC**].

      ![Azure RBAC destination](assets/datafeed-destination-azurerbac.png)

   1. Select [!UICONTROL **Select location**].

      The Azure RBAC Export Locations page is displayed.

   1. (Conditional) If an Azure RBAC account (and a location on that account) has already been configured in Adobe Analytics, you can use it as your data feed destination: 

      >[!NOTE]
      >
      >Accounts are available to you only if you configured them or if they were shared with an organization you are a part of.
   
      1. Select the account from the [!UICONTROL **Select account**] drop-down menu.

      Any cloud accounts that you configured in any of the following areas of Adobe Analytics are available to use:
      
         * When importing Adobe Analytics classification data, as described in [Schema](/help/components/classifications/sets/manage/schema.md).
      
           However, any locations that are configured for importing classification data cannot be used. Instead, add a new destination as described below.

         * When configuring accounts and locations in the Locations area, as described in [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md) and [Configure cloud import and export locations](/help/components/locations/configure-import-locations.md).

      1. Select the location from the [!UICONTROL **Select location**] drop-down menu.

      1. Select [!UICONTROL **Save**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the Azure RBAC location that you specified.

   1. (Conditional) If you have not previously added an Azure RBAC account:

      1. Select [!UICONTROL **Add account**], then specify the following information:
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Account name**] | A name for the Azure RBAC account. This name displays in the [!UICONTROL **Select account**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Account description**] | A description for the Azure RBAC account. This description displays in the [!UICONTROL **Select account**] drop-down field and can be any name you choose.  |
         | [!UICONTROL **Application ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Tenant ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Secret**] | Copy the secret from the Azure application that you created. In Microsoft Azure, this information is located on the **Certificates & secrets** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Add location**], then specify the following information: 
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Name**] | A name for the location. This name displays in the [!UICONTROL **Select location**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Description**] | A description for the location. This description displays in the [!UICONTROL **Select location**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Account**] | The Azure storage account. |
         | [!UICONTROL **Container**] | The container within the account you specified where you want Adobe Analytics data to be sent. Ensure that you grant permissions to upload files to the Azure application that you created earlier. |
         | [!UICONTROL **Prefix**] | The folder within the container where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, `folder_name/`<p>Make sure the Application ID that you specified when configuring the Azure RBAC account has been granted the `Storage Blob Data Contributor` role in order to access the container (folder).</p> <p>For more information, see [Azure built-in roles](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p> |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Create**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the Azure RBAC location that you specified.

      1. (Conditional) If you need to manage the destination (account and location) that you just created, it is available in the [Locations manager](/help/components/locations/locations-manager.md).
   
   +++

   +++Azure SAS

   You can send feeds directly to an Azure container by using SAS authentication. This destination type requires an Application ID, Tenant ID, Key vault URI, Key vault secret name, and secret. 

   To configure Azure SAS as the destination for a data feed:

   1. If you haven't already, create an Azure application that Adobe Analytics can use for authentication. 
   
      For information, refer to the [Microsoft Azure documentation about how to create an Azure Active Directory application](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal). 
   
   1. In the Adobe Analytics admin console, in the [!UICONTROL **Destination**] section, select [!UICONTROL **Azure SAS**].

      ![Azure SAS destination](assets/datafeed-destination-azuresas.png)

   1. Select [!UICONTROL **Select location**].

      The Azure SAS Export Locations page is displayed.

   1. (Conditional) If an Azure SAS account (and a location on that account) has already been configured in Adobe Analytics, you can use it as your data feed destination: 

      >[!NOTE]
      >
      >Accounts are available to you only if you configured them or if they were shared with an organization you are a part of.
   
      1. Select the account from the [!UICONTROL **Select account**] drop-down menu.

         Any cloud accounts that you configured in any of the following areas of Adobe Analytics are available to use:
      
         * When importing Adobe Analytics classification data, as described in [Schema](/help/components/classifications/sets/manage/schema.md).
      
           However, any locations that are configured for importing classification data cannot be used. Instead, add a new destination as described below.

         * When configuring accounts and locations in the Locations area, as described in [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md) and [Configure cloud import and export locations](/help/components/locations/configure-import-locations.md).

      1. Select the location from the [!UICONTROL **Select location**] drop-down menu.

      1. Select [!UICONTROL **Save**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the Azure SAS location that you specified.
   
   1. (Conditional) If you have not previously added an Azure SAS account:

      1. Select [!UICONTROL **Add account**], then specify the following information:
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Account name**] | A name for the Azure SAS account. This name displays in the [!UICONTROL **Select account**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Account description**] | A description for the Azure SAS account. This description displays in the [!UICONTROL **Select account**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Application ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Tenant ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Key vault URI**] | <p>The path to the SAS URI in Azure Key Vault. To configure Azure SAS, you need to store an SAS URI as a secret using Azure Key Vault. For information, see the [Microsoft Azure documentation about how to set and retrieve a secret from Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>After the key vault URI is created:<ul><li>Add an access policy on the Key Vault in order to grant permission to the Azure application that you created.<p>For information, see the [Microsoft Azure documentation about how to assign a Key Vault access policy](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p><p>Or</p><p>If you want to grant an access role directly without creating an access policy, see the [Microsoft Azure documentation about how to assign Azure roles using Azure portal](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal). This adds the role assignment for the application ID to access the key vault URI. </p></li><li>Make sure the Application ID has been granted the `Key Vault Certificate User` built-in role in order to access the key vault URI.</br><p>For more information, see [Azure built-in roles](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p></li></ul> |
         | [!UICONTROL **Key vault secret name**] | The secret name you created when adding the secret to Azure Key Vault. In Microsoft Azure, this information is located in the Key Vault you created, on the **Key Vault** settings pages. For information, see the [Microsoft Azure documentation about how to set and retrieve a secret from Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
         | [!UICONTROL **Secret**] | Copy the secret from the Azure application that you created. In Microsoft Azure, this information is located on the **Certificates & secrets** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Add location**], then specify the following information: 
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Name**] | A name for the location. This name displays in the [!UICONTROL **Select location**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Description**] | A description for the location. This description displays in the [!UICONTROL **Select location**] drop-down field and can be any name you choose. |
         | [!UICONTROL **Container**] | The container within the account you specified where you want Adobe Analytics data to be sent. |
         | [!UICONTROL **Prefix**] | The folder within the container where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, `folder_name/`<p>Make sure that the SAS URI store that you specified in the Key Vault secret name field when configuring the Azure SAS account has the `Write` permission. This allows the SAS URI to create files in your Azure container. <p>If you want the SAS URI to also overwrite files, make sure that the SAS URI store has the `Delete` permission.</p><p>For more information, see [Blob storage resources](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources) in the Azure Blob Storage documentation.</p> |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Create**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the Azure SAS location that you specified.

      1. (Conditional) If you need to manage the destination (account and location) that you just created, it is available in the [Locations manager](/help/components/locations/locations-manager.md).
   
   +++

   +++Google Cloud Platform

   You can send feeds directly to Google Cloud Platform (GCP) buckets. This destination type requires only your GCP account name and the location (bucket) name. 
   
   Adobe Analytics uses cross-account authentication to upload files from Adobe Analytics to the specified location in your GCP instance.

   To configure a GCP bucket as the destination for a data feed:

   1. In the Adobe Analytics admin console, in the [!UICONTROL **Destination**] section, select [!UICONTROL **Google Cloud Platform**].

      ![Google Cloud Platform destination](assets/datafeed-destination-gcp.png)

   1. Select [!UICONTROL **Select location**].

      The GCP Export Locations page is displayed.

   1. (Conditional) If a Google Cloud Platform account (and a location on that account) has already been configured in Adobe Analytics, you can use it as your data feed destination: 

      >[!NOTE]
      >
      >Accounts are available to you only if you configured them or if they were shared with an organization you are a part of.
   
      1. Select the account from the [!UICONTROL **Select account**] drop-down menu.

         Any cloud accounts that you configured in any of the following areas of Adobe Analytics are available to use:
      
         * When importing Adobe Analytics classification data, as described in [Schema](/help/components/classifications/sets/manage/schema.md).
      
           However, any locations that are configured for importing classification data cannot be used. Instead, add a new destination as described below.

         * When configuring accounts and locations in the Locations area, as described in [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md) and [Configure cloud import and export locations](/help/components/locations/configure-import-locations.md).

      1. Select the location from the [!UICONTROL **Select location**] drop-down menu.

      1. Select [!UICONTROL **Save**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the Google Cloud Platform location that you specified.
   
   1. (Conditional) If you have not previously added a GCP account:

      1. Select [!UICONTROL **Add account**], then specify the following information:
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Account name**] | A name for the account. This can be any name you choose. |
         | [!UICONTROL **Account description**] | A description for the account. |
         | [!UICONTROL **Project ID**] | Your Google Cloud project ID. See the [Google Cloud documentation about getting a project ID](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Add location**], then specify the following information:
   
         |Field | Function |
         |---------|----------|
         | [!UICONTROL **Principal**] | The Principal is provided by Adobe. You must grant permission to receive feeds to this principal. |
         | [!UICONTROL **Name**] | A name for the account.  |
         | [!UICONTROL **Description**] | A description for the account. |
         | [!UICONTROL **Bucket**] | The bucket within your GCP account where you want Adobe Analytics data to be sent. <p>Ensure that you have granted either of the following permissions to the Principal provided by Adobe: (For information about granting permissions, see [Add a principal to a bucket-level policy](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) in the Google Cloud documentation.)<ul><li>`roles/storage.objectCreator`: Use this permission if you  want to limit the Principal to only create files in your GCP account. </br>**Important:** If you use this permission with scheduled reporting, you must use a unique file name for each new scheduled export. Otherwise, the report generation will fail because the Principal does not have access to overwrite existing files.</li><li>(Recommended) `roles/storage.objectUser`: Use this permission if you want the Principal to have access to view, list, update, and delete files in your GCP account.</br>This permission allows the Principal to overwrite existing files for subsequent uploads, without the need to auto-generate unique file names for each new scheduled export.</li></ul><p>If your organization is using [Organization policy constraints](https://cloud.google.com/storage/docs/org-policy-constraints) to allow only the Google Cloud Platform account in your allow list, you need the following Adobe-owned Google Cloud Platform organization ID: <ul><li>`DISPLAY_NAME`: `adobe.com`</li><li>`ID`: `178012854243`</li><li>`DIRECTORY_CUSTOMER_ID`: `C02jo8puj`</li></ul> </p> |
         | [!UICONTROL **Prefix**] | The folder within the bucket where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, `folder_name/` |

         {style="table-layout:auto"}

      1. Select [!UICONTROL **Create**] > [!UICONTROL **Save**].

         The destination is now configured to send data to the GCP location that you specified.

      1. (Conditional) If you need to manage the destination (account and location) that you just created, it is available in the [Locations manager](/help/components/locations/locations-manager.md).
   
   +++

1. In the  [!UICONTROL **Data Column Definitions**] section, select the latest [!UICONTROL **All Adobe Columns**] template in the drop-down menu, then complete the following fields:
   
   |Field | Function |
   |---------|----------|
   | [!UICONTROL **Remove escaped characters**] | When collecting data, some characters (such as newlines) can cause issues. Check this box if you would like these characters removed from feed files. |
   | [!UICONTROL **Compression format**] | The type of compression used. **Gzip** outputs files in `.tar.gz` format. **Zip** outputs files in `.zip` format. |
   | [!UICONTROL **Packaging type**] | Select [!UICONTROL **Multiple files**] for most data feeds. This option paginates your data into uncompressed 2GB chunks. (If the [!UICONTROL **Multiple files**] option is selected and uncompressed data for the reporting window is less than 2GB, one file is sent.) Selecting **Single file** outputs the `hit_data.tsv` file in a single, potentially massive file. |
   | [!UICONTROL **Manifest**] | Determines whether Adobe should deliver a [manifest file](c-df-contents/datafeeds-contents.md#feed-manifest) to the destination when no data is collected for a feed interval. If you select **Manifest File**, you receive a manifest file similar to the following when no data is collected:<p>`text`</p><p>`Datafeed-Manifest-Version: 1.0`</p><p>`Lookup-Files: 0`</p><p>`Data-Files: 0`</p><p> `Total-Records: 0`</p> |
   | [!UICONTROL **Column templates**] | When creating many data feeds, Adobe recommends creating a column template. Selecting a column template automatically includes the specified columns in the template. Adobe also provides several templates by default. |
   | [!UICONTROL **Available columns**] | All available data columns in Adobe Analytics. Click [!UICONTROL Add all] to include all columns in a data feed. |
   | [!UICONTROL **Included columns**] | The columns to include in a data feed. Click [!UICONTROL Remove all] to remove all columns from a data feed. |
   | [!UICONTROL **Download CSV**] | Downloads a CSV file containing all included columns. |

1. Select [!UICONTROL **Save**] in the top-right.

    Historical data processing begins immediately. When data finishes processing for a day, the file is sent to the destination that you configured.

    For information about how to access the data feed and to get a better understanding of its contents, see [Data feed contents - overview](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md).

## Legacy destinations

>[!IMPORTANT]
>
>The destinations described in this section are legacy, and are not recommended. Instead, use one of the following destinations when creating a data feed: Amazon S3, Google Cloud Platform, Azure RBAC, or Azure SAS. See [Create and configure a data feed](#create-and-configure-a-data-feed) for detailed information about each of these recommended destinations. 


The following information provides configuration information for each of the legacy destinations:

### FTP

Data feed data can be delivered to an Adobe or customer-hosted FTP location. Requires an FTP host, username, and password. Use the path field to place feed files in a folder. Folders must already exist; feeds throw an error if the specified path does not exist.

Use the following information when completing the available fields:

* [!UICONTROL **Host**]: Enter the desired FTP destination URL. For example, `ftp://ftp.omniture.com`.
* [!UICONTROL **Path**]: Can be left blank
* [!UICONTROL **Username**]: Enter the username to log in to the FTP site.
* [!UICONTROL **Password and confirm password**]: Enter the password to log in to the FTP site.

### SFTP

SFTP support for data feeds is available. Requires an SFTP host, username, and the destination site to contain a valid RSA or DSA public key. You can download the appropriate public key when creating the feed.

### S3

You can send feeds directly to Amazon S3 buckets. This destination type requires a Bucket name, an Access Key ID, and a Secret Key. See [Amazon S3 bucket naming requirements](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) within the Amazon S3 docs for more information.

The user you provide for uploading data feeds must have the following [permissions](https://docs.aws.amazon.com/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

  >[!NOTE]
  >
  >For each upload to an Amazon S3 bucket, [!DNL Analytics] adds the bucket owner to the BucketOwnerFullControl ACL, regardless of whether the bucket has a policy that requires it. For more information, see "[What is the BucketOwnerFullControl setting for Amazon S3 data feeds?](df-faq.md#BucketOwnerFullControl)"

The following 16 standard AWS regions are supported (using the appropriate signature algorithm where necessary):

* us-east-2
* us-east-1
* us-west-1
* us-west-2
* ap-south-1
* ap-northeast-2
* ap-southeast-1
* ap-southeast-2
* ap-northeast-1
* ca-central-1
* eu-central-1
* eu-west-1
* eu-west-2
* eu-west-3
* eu-north-1
* sa-east-1

>[!NOTE]
>
>The cn-north-1 region is not supported.

### Azure Blob

Data feeds support Azure Blob destinations. Requires a container, account, and a key. Amazon automatically encrypts the data at rest. When you download the data, it gets decrypted automatically. See [Create a storage account](https://docs.microsoft.com/en-us/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) within the Microsoft Azure docs for more information.

>[!NOTE]
>
>You must implement your own process to manage disk space on the feed destination. Adobe does not delete any data from the server.

-->
