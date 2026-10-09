---
title: Erstellen eines Daten-Feeds
description: Erfahren Sie, wie ein Daten-Feed erstellt wird und welche Dateiinformationen Adobe zur Verfügung gestellt werden müssen.
hide: true
feature: Components
autotag-review: '2026-05-19T08:45:44.870Z'
TQID: 'https://experienceleague.adobe.com/QgBD7vCkw4YA568XOLlwTnw8eZVZybXr3DFbM1ZKYDw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: d7614102d54af57a3a084c8550041f8e04f4bc37
workflow-type: tm+mt
source-wordcount: '3881'
ht-degree: 12%
---
# Erstellen eines Daten-Feeds

{{release-limited-testing}}

Stellen Sie Adobe beim Erstellen eines Daten-Feeds Folgendes zur Verfügung:

* Informationen über das Ziel, an das Rohdatendateien gesendet werden sollen

* Die Daten, die in jede Datei aufgenommen werden sollen

* Die Häufigkeit, mit der Daten gesendet werden (einschließlich der Verarbeitungsverzögerung zur Erfassung verspäteter Ereignisse)

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
>title="Benachrichtigen über Probleme bei Abschluss oder Ablauf"
>abstract="Geben Sie eine oder mehrere E-Mail-Adressen an, an die bei Abschluss oder Ablauf des Daten-Feeds bzw. bei Auftreten von Problemen eine Benachrichtigung gesendet werden soll. Trennen Sie mehrere E-Mail-Adressen durch ein Komma."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_frequency_granularity"
>title="Häufigkeit und Granularität"
>abstract="**Versandfrequenz** (Live-Feeds): Wie oft der Daten-Feed bereitgestellt wird. Stündliche Sendungen enthalten Daten für eine Stunde, tägliche Sendungen enthalten Daten für einen Tag. Der Lookback-Datumsbereich und die Verarbeitungsverzögerung können sich auch darauf auswirken, welche Ereignisse einbezogen werden.<p>**Granularität** (Aufstockungs-Feeds): Das Zeitintervall, das zum Aufteilen historischer Daten verwendet wird. Jeder Block enthält Daten für einen Tag und wird so schnell wie möglich bereitgestellt, nicht einmal pro Tag. Dieses Feld ist immer auf Täglich festgelegt und kann nicht geändert werden.</p>"

<!-- markdownlint-enable MD034 -->

1. Melden Sie sich mit Ihren Adobe ID-Anmeldeinformationen bei [experiencecloud.adobe.com](https://experiencecloud.adobe.com) an.

1. Wählen Sie [!UICONTROL **Customer Journey Analytics**] im App-Umschalter ![App](/help/assets/icons/Apps.svg) oben rechts in der Benutzeroberfläche aus.

1. Navigieren Sie in der oberen Navigationsleiste zu [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Daten-Feeds**] aus.

1. Wählen [!UICONTROL **Erstellen**] in der oberen rechten Ecke des Bildschirms aus.

   Oder wählen Sie, wenn zuvor keine Daten-Feeds erstellt wurden [!UICONTROL **in**] leeren Tabelle die Option „Daten-Feed erstellen“ aus.

   Eine Seite wird mit den folgenden Registerkarten angezeigt: [!UICONTROL **Details**], [!UICONTROL **Datenstruktur**] und [!UICONTROL **Versand**].

   ![Neue Daten-Feed-Seite](assets/data-feed-new.png)

1. Füllen Sie auf [!UICONTROL **Registerkarte**] Details“ die folgenden Felder aus:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Name**] | Der Name des Daten-Feeds. Namen müssen in der ausgewählten Datenansicht eindeutig sein und können bis zu 255 Zeichen lang sein. <!--[Learn more](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique)--> |
   | [!UICONTROL **Tags**] | Wenden Sie beliebige Tags auf den Daten-Feed an, um die Kategorisierung zu erleichtern. <!--You can filter on tags as described in [Filter and search the list of data feeds](/help/export/analytics-data-feed/df-manage-feeds.md#filter-and-search-the-list-of-data-feeds) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).--> |
   | [!UICONTROL **Beschreibung**] | Geben Sie eine Beschreibung für den Daten-Feed ein (bis zu 500 Zeichen). Die von Ihnen hinzugefügte Beschreibung ist beim Bearbeiten des Daten-Feeds sichtbar. |
   | [!UICONTROL **Datenansicht**] | Wählen Sie die Datenansicht aus, die die zu exportierenden Daten enthält.<p>Beachten Sie bei der Auswahl einer Datenansicht Folgendes:</p> <ul><li>Wenn mehrere Daten-Feeds für dieselbe Datenansicht erstellt werden, muss jeder Daten-Feed unterschiedliche Spaltendefinitionen haben.</li><li>Die Liste der verfügbaren Spalten hängt vom Anmeldeunternehmen ab, zu dem die ausgewählte Datenansicht gehört. Wenn Sie die Datenansicht ändern, kann sich die Liste der verfügbaren Spalten ändern. </li></ul> |

1. Wählen Sie [!UICONTROL **Weiter**] aus.

1. Stellen [!UICONTROL **auf der Registerkarte**] Datenstruktur) sicher, dass im Feld **[!UICONTROL Datenansicht“ die richtige]** ausgewählt ist.

   <!--add screenshot-->

1. Suchen Sie [!UICONTROL **Dropdown-Menü**] Segmente“ nach beliebigen Segmenten und wählen Sie diese aus, um die in Ihrem Feed enthaltenen Daten zu filtern.

   Wenn Sie mehrere Segmente anwenden, werden sie mit einem AND-Operator verbunden. Um Segmente mit einem OR-Operator zu verbinden, müssen Sie zunächst ein neues Segment in Segment Builder erstellen und dann das neue Segment auf den Daten-Feed anwenden.

   Segmente, die Sie hier anwenden, kommen zu Segmenten hinzu, die möglicherweise bereits in Ihrer Datenansicht angewendet werden.

1. (Optional) Suchen Sie in der linken Leiste mithilfe des Felds **Suche** nach bestimmten Komponenten. Oder wählen Sie das Symbol **Sortieren** (Symbol ![Komponenten sortieren](/help/assets/icons/SortOrderDown.svg), um eine der folgenden Sortieroptionen anzuwenden:

   | Option | Funktion |
   | --------- | ---------- |
   | [!UICONTROL **Empfohlen**] | Sortiert Komponenten nach den am Anfang der Liste empfohlenen Komponenten. Komponenten, die am häufigsten und zuletzt von Ihnen oder anderen in Ihrem Unternehmen verwendet werden, werden weiter oben in der Liste angezeigt. |
   | [!UICONTROL **Alphabetisch**] | Sortiert Komponenten alphabetisch. |
   | [!UICONTROL **Kategorisch**] | Sortiert Komponenten ähnlich wie [!UICONTROL **Empfohlen**] mit dem Unterschied, dass berechnete Metriken und Standardmetriken separat gruppiert werden, anstatt zusammengemischt zu werden. |

1. Fügen Sie Komponenten zur Daten-Feed-Konfiguration hinzu. In der linken Leiste werden nur Komponenten angezeigt, die für Daten-Feeds gültig sind.

   * **Drag-and-Drop**: Ziehen Sie Komponenten aus der linken Leiste auf die Arbeitsfläche. Halten Sie **[!UICONTROL Umschalt]** oder halten Sie **[!UICONTROL Befehl]** (macOS) oder **[!UICONTROL Strg]** (Windows) gedrückt, um mehrere Komponenten gleichzeitig auszuwählen und zu ziehen.
   * **Plus-Schaltfläche**: Wählen Sie in der linken Leiste das Symbol Plus ![Hinzufügen](/help/assets/icons/Add.svg) neben einer beliebigen Komponente aus, um sie zur Arbeitsfläche hinzuzufügen.
   * **[!UICONTROL Alle anzeigen]**: Wählen Sie **[!UICONTROL Alle anzeigen]** unten in der Komponentenliste aus, um ein Dialogfeld mit allen verfügbaren Komponenten zu öffnen. Aktivieren Sie das Kontrollkästchen neben jeder Komponente, die Sie hinzufügen möchten, und klicken Sie dann auf **[!UICONTROL Auswahl hinzufügen]**. Wenn ein Suchbegriff oder Filter-Tag in der linken Leiste aktiv ist, wird auch eine **[!UICONTROL Alle hinzufügen]**-Schaltfläche angezeigt, über die Sie alle gefilterten Ergebnisse gleichzeitig hinzufügen können.

   Wenn Sie eine Komponente hinzufügen, die zu einem XDM-Array-Feld gehört (z. B. einem Adobe Journey Optimizer-Vorschlagsfeld), wird sie auf der Arbeitsfläche als ausblendbare verschachtelte Gruppe und nicht als flaches Element angezeigt. Die Gruppe spiegelt die zugrunde liegende Datenstruktur wider und gibt sie als verschachteltes Array in der exportierten Datei aus.

   <!--add screenshot-->

   Einige Komponenten sind erforderlich, werden nicht unterstützt oder weisen Einschränkungen in Daten-Feeds auf. Weitere Informationen finden Sie [Komponentenverfügbarkeit in Daten-Feeds](/help/components/exports/cja-data-feeds/df-components.md).

1. (Optional) Ordnen Sie Komponenten auf der Arbeitsfläche neu an, indem Sie sie ziehen. Die von Ihnen definierte Reihenfolge wird als Spaltenreihenfolge in der exportierten Daten-Feed-Datei beibehalten.

1. (Optional) Ändern Sie die Spaltengröße auf der Arbeitsfläche, indem Sie den Spaltenrahmen ziehen.

   Spaltenbreiten werden in einem Cookie gespeichert und bleiben erhalten, wenn Sie das nächste Mal im selben Browser zu diesem Daten-Feed zurückkehren.

1. (Optional) Ändern Sie die Komponenten-ID, die in der Daten-Feed-Ausgabe angezeigt wird.

   1. Bewegen Sie den Mauszeiger über eine Komponente auf der Arbeitsfläche und klicken Sie dann auf das Informationssymbol.

   1. Geben Sie im Feld Komponenten-ID eine neue Komponenten-ID an.

      <!--add screenshot-->

1. (Optional) Verwenden Sie die Bedienfelder **[!UICONTROL Feed]** Zusammenfassung und **[!UICONTROL Schemavorschau]** auf der rechten Seite der Seite, um Ihre Datenstruktur zu überprüfen, bevor Sie fortfahren:

   * Die **[!UICONTROL Feed-Zusammenfassung]** zeigt die Live-Anzahl aller hinzugefügten Komponenten, Spalten, Dimensionen und Metriken an.
   * Die **[!UICONTROL Schemavorschau]** zeigt eine JSON-Darstellung des Daten-Feed-Schemas, das beim Hinzufügen oder Neuanordnen von Komponenten aktualisiert wird.
   * Mit der Schaltfläche **[!UICONTROL Beispielzeilen]** wird ein Dialogfeld geöffnet, in dem Beispielausgabezeilen angezeigt werden, damit Sie überprüfen können, ob die Struktur korrekt aussieht. Dieses Dialogfeld zeigt nur Beispieldaten und spiegelt nicht Ihre tatsächlichen Daten wider.

   <!--add screenshot-->

1. Wählen Sie auf der [!UICONTROL **Versand**] im Abschnitt [!UICONTROL **Planung**] den Feed-Typ aus, den Sie erstellen möchten (Live oder Aufstockung), und geben Sie dann das Reporting-Fenster, die Häufigkeit und andere Konfigurationsoptionen an:

   <!--add screenshot-->

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Feed-Typ**] | Wählen Sie den Feed-Typ aus, den Sie erstellen möchten:<ul><li>[!UICONTROL **Live-Feed**]: Exportiert aktuelle und zukünftige Daten.</li><li>[!UICONTROL **Aufstockungsfeed**]: Exportiert historische Daten. </li></ul> |
   | [!UICONTROL **Startdatum**] | Das Datum, an dem der Daten-Feed beginnt. Bei Live-Feeds muss dies heute oder ein Datum in der Zukunft sein. Bei Aufstockungs-Feeds muss es sich um ein vergangenes Datum im Datenaufbewahrungsfenster der Datenansicht handeln. Das Startdatum basiert auf der Zeitzone der Datenansicht. |
   | [!UICONTROL **Ablaufdatum**] <br/>Nur für Live-Feeds verfügbar | Das Datum, an dem der Daten-Feed abläuft und nicht mehr ausgeführt wird. Das Datum basiert auf der Zeitzone der Datenansicht. |
   | [!UICONTROL **Enddatum**]<br/> Nur für Aufstockungs-Feeds verfügbar | Das Datum, an dem der Daten-Feed endet. Das Enddatum darf nicht in der Zukunft liegen. Das Datum basiert auf der Zeitzone der Datenansicht. |
   | [!UICONTROL **Häufigkeit**]<br/> Nur für Live-Feeds verfügbar | Legen Sie fest, wie oft der Daten-Feed gesendet werden soll. Ereignisse mit Zeitstempeln, die in das Häufigkeitsfenster fallen, werden in den Daten-Feed-Versand aufgenommen. Die Felder [!UICONTROL **Lookback**] Datumsbereich und [!UICONTROL **Verarbeitungsverzögerung**] können sich auch darauf auswirken, welche Ereignisse für die von Ihnen gewählte Versandfrequenz in die Daten aufgenommen werden.<p>Wählen Sie diese Option aus, um Daten aus einer Stunde oder aus Daten aus einem Tag aufzunehmen.</p><ul><li>**Täglich**: Feeds enthalten Daten eines ganzen Tages von Mitternacht bis Mitternacht in der Zeitzone der Datenansicht.</li><li>**Stündlich**: Feeds enthalten Daten für eine einzige Stunde.</li></ul> |
   | [!UICONTROL **Granularität**]<br/> Nur für Aufstockungs-Feeds verfügbar | Das Zeitintervall, das zum Aufteilen historischer Daten in Blöcke verwendet wird. Jeder Chunk enthält Daten eines ganzen Tages von Mitternacht bis Mitternacht in der Zeitzone der Datenansicht. <p>Die Granularität bestimmt, wie die Daten gruppiert werden, und nicht, wie oft sie bereitgestellt werden. Aufstockungsdaten werden so schnell wie möglich bereitgestellt, nicht einmal pro Tag.</p><p>Dieses Feld ist immer auf &quot;[!UICONTROL **&quot; festgelegt**] kann nicht geändert werden.</p> |
   | [!UICONTROL **Lookback-Datumsbereich**] | Steuert, wie weit Customer Journey Analytics bei der Verarbeitung der Daten-Feed-Bereitstellung zurückblickt. Der Standardwert ist 30 Tage.<p>Das Häufigkeitsfenster (Stunde oder Tag) bestimmt, welche Ereignisse im Daten-Feed enthalten sind, während der **Lookback-Datumsbereich** den erforderlichen historischen Kontext bereitstellt, um diese Ereignisse korrekt zu klassifizieren.</p><p>Segmentqualifikation, Dimensionspersistenz, Sitzungsberechnung und Transformationen abgeleiteter Felder können sich auf alle eingeschlossenen Ereignisse auswirken.</p> <p>Bevor Sie diese Option konfigurieren, lesen Sie die Details und Beispiele im folgenden Abschnitt [Grundlegendes zum Lookback-Datumsbereich](#data-feed-lookback-date-range).</p> |
   | [!UICONTROL **Verarbeitungsverzögerung**] | Wählen Sie die Zeitspanne aus, die Customer Journey Analytics wartet, bevor eine Daten-Feed-Datei verarbeitet wird. Alle spät eintreffenden Ereignisse, die während der Verarbeitungsverzögerung eintreten, sind im Daten-Feed enthalten. <p>Die minimale Verarbeitungsverzögerung beträgt 2 Stunden, aber einige Datentypen erfordern eine längere Verzögerung. Die ausgewählte Verzögerung hängt von den Datentypen in Ihrer Verbindung ab, z. B. Streaming-, Batch-, zugeordnete, Lookup- oder Profildaten.</p><p>Wählen Sie eine Verzögerung aus, die lang genug ist, damit die langsamsten Daten in Ihrer Verbindung die Verarbeitung abschließen. Wenn die Verzögerung zu kurz ist, werden Daten, die noch verarbeitet werden, nicht in die Daten-Feed-Datei aufgenommen.</p><p>Bevor Sie diese Option konfigurieren, lesen Sie die Details und Beispiele im folgenden Abschnitt [Grundlegendes zur Verarbeitungsverzögerung](#data-feed-processing-delay).</p> |
   | [!UICONTROL **Komprimierungsformat**] | Wählen Sie das Komprimierungsformat für die Parquet-Ausgabedateien aus, die an Ihr Cloud-Ziel gesendet werden. Wählen Sie aus den folgenden Formaten:<ul><li>[!UICONTROL **Snappy**]: Schnelle Komprimierung und Dekomprimierung bei moderaten Dateigrößen. Wird von modernen Datenplattformen wie BigQuery, Snowflake und Apache Spark weithin unterstützt.</li><li>[!UICONTROL **GZip**]: Grob kompatibel, auch mit Tools, die Snappy nicht nativ unterstützen. Empfohlen, wenn Ihre nachgelagerte Pipeline einen weithin anerkannten Komprimierungsstandard erfordert.</li><li>[!UICONTROL **Z Standard (Zstd)**]: Hohe Komprimierungseffizienz mit schneller Dekomprimierung. Geeignet, wenn die Minimierung der Dateigröße eine Priorität ist und Ihre Tools Zstd unterstützen.</li></ul> |

1. Konfigurieren Sie auf [!UICONTROL **Registerkarte**] im Abschnitt [!UICONTROL **Ziel**] das Ziel, an das die Daten gesendet werden sollen.

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
   | [!UICONTROL **Anzeigen von Zielen für alle Benutzer**] | Wenn Sie Systemadministrator sind, können Sie diese Option aktivieren, um Ziele anzuzeigen, die von allen Benutzern in Ihrer Organisation erstellt wurden. Wenn diese Option deaktiviert ist, werden nur von Ihnen erstellte Ziele angezeigt. |
   | [!UICONTROL **Konto**] | Führen Sie einen der folgenden Schritte aus:<ul><li>**Vorhandenes Konto verwenden:** Wählen Sie das Dropdown-Menü neben dem Feld **[!UICONTROL Konto]** aus. Oder geben Sie den Kontonamen ein und wählen Sie ihn dann aus dem Dropdown-Menü aus. <p>Konten stehen Ihnen nur zur Verfügung, wenn Sie sie konfiguriert haben oder wenn sie für eine Organisation freigegeben wurden, der Sie angehören.</p></li><li>**Neues Konto erstellen:** Wählen Sie **[!UICONTROL Konto hinzufügen]** im **[!UICONTROL Konto]** Dropdown-Menü aus. Informationen zum Konfigurieren des Kontos finden Sie unter [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md).</li></ul> |
   | [!UICONTROL **Ort**] | Führen Sie einen der folgenden Schritte aus:<ul><li>**Vorhandenen Speicherort verwenden:** Wählen Sie das Dropdown-Menü neben dem Feld **[!UICONTROL Speicherort]** aus. Oder geben Sie den Ortsnamen ein und wählen Sie ihn dann aus dem Dropdown-Menü aus.</li><li>**Neuen Speicherort erstellen:** Wählen Sie **[!UICONTROL Speicherort hinzufügen]** im **[!UICONTROL Speicherort]** Dropdown-Menü aus. Informationen zum Konfigurieren des Speicherorts finden Sie unter [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md).</li></ul> |
   | [!UICONTROL **Nach Abschluss per E-Mail benachrichtigen**] | Geben Sie eine oder mehrere E-Mail-Adressen an, an die eine Benachrichtigung gesendet werden soll, nachdem der Daten-Feed erfolgreich gesendet wurde oder nicht gesendet werden kann. Mehrere E-Mail-Adressen müssen durch ein Komma getrennt werden. |
   | [!UICONTROL **Manifest aktivieren**] | Wählen Sie aus, ob bei jeder Daten-Feed-Bereitstellung eine Manifestdatei enthalten sein soll. Die Manifestdatei enthält Informationen für jede Datei, die im Daten-Feed enthalten ist. |

1. Wählen Sie **[!UICONTROL Speichern]** aus.

## Grundlegendes zum Lookback-Datumsbereich {#data-feed-lookback-date-range}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_lookback_date_range"
>title="Lookback-Datumsbereich"
>abstract="Steuert, wie weit Customer Journey Analytics bei der Verarbeitung jeder Bereitstellung zurückblickt.<p>Das Häufigkeitsfenster (Stunde oder Tag) bestimmt, welche Ereignisse im Daten-Feed enthalten sind, während der **Lookback-Datumsbereich** den erforderlichen historischen Kontext bereitstellt, um diese Ereignisse korrekt zu klassifizieren.</p><p>Segmentqualifikation, Dimensionspersistenz, Sitzungsberechnung und Transformationen abgeleiteter Felder können sich auf alle eingeschlossenen Ereignisse auswirken.</p><p>Ein längerer Lookback-Zeitraum verbessert die Genauigkeit, ein kürzerer Lookback-Zeitraum verbessert die Leistung.</p>"

<!-- markdownlint-enable MD034 -->

Der Lookback-Datumsbereich steuert, wie weit Customer Journey Analytics bei der Verarbeitung jedes Daten-Feed-Versands zurückblickt.

Ereignisse müssen weiterhin Zeitstempel aufweisen, die in das Häufigkeitsfenster (Stunde oder Tag) fallen, damit sie in den Versand einbezogen werden. Die Daten, die in den **Lookback-Datumsbereich** fallen, bieten jedoch den erforderlichen historischen Kontext, um diese Ereignisse korrekt zu klassifizieren.

Beachten Sie beim Konfigurieren dieser Option die folgenden wichtigen Konzepte:

* Ein längerer Lookback-Datumsbereich führt in der Regel zu genaueren Daten; ein kürzerer Bereich führt zu einer besseren Versandleistung.
* Der Lookback-Datumsbereich funktioniert zusammen mit dem Häufigkeitsfenster ähnlich wie der Datumsbereich des Analysis Workspace-Berichts. Es gibt jedoch [wesentliche Unterschiede](/help/components/exports/cja-data-feeds/df-comparison-workspace.md#differences). Diese Unterschiede können zu Datendiskrepanzen zwischen Workspace-Berichten und Daten-Feed-Sendungen führen.

Segmentqualifikation, Sitzungsberechnung, Dimensionspersistenz und abgeleitete Feldtransformationen werden bei der Verarbeitung von Daten im Lookback-Datumsbereich jeweils berücksichtigt:

### Segmentqualifikation

Wenn ein Segment auf Ihre Daten-Feed-Definition angewendet wird, bestimmen Daten innerhalb des Lookback-Datumsbereichs, welche Ereignisse, Sitzungen oder Personen für das Segment qualifiziert sind. Die Container-Einstellung des Segments bestimmt den Umfang. (Mögliche Container sind: Person, Sitzung oder Ereignis. B2B umfasst die folgenden zusätzlichen Container: Globales Konto, Konto, Opportunity, Einkaufsgruppe.)

>[!BEGINSHADEBOX]

**Beispiel:**

Angenommen, Sie möchten einen Daten-Feed erstellen, um das Verhalten von Benutzern zu verstehen, die Teil einer bestimmten Marketing-Kampagne sind, nämlich Campaign B.

Zu diesem Zweck wenden Sie ein Segment mit dem Namen _Benutzer in Campaign B_ auf den Daten-Feed an und geben an, dass nur die Ereignisse, die mit Benutzern in diesem Segment verknüpft sind, in den Daten-Feed aufgenommen werden sollen.

In diesem Fall werden Benutzer nur dann in den Daten-Feed aufgenommen, wenn sie **beide** der folgenden Bedingungen erfüllen:

* Der Benutzer hatte ein Ereignis mit einem Zeitstempel, das sich im Datenfeed-Häufigkeitsfenster befindet (die angegebene Stunde oder der angegebene Tag des Daten-Feeds).
* Der Benutzer hat sich für das Segment _Campaign B_ **irgendwann innerhalb des Lookback-Datumsbereichs)**.

  Für ein qualifizierendes Ereignis, das vor 9 Tagen aufgetreten ist, bedeutet dies, dass der Benutzer **wäre**) in den Daten-Feed aufgenommen würde, wenn der Lookback-Datumsbereich auf 30 Tage festgelegt wäre, der Benutzer **wäre aber nicht** Daten-Feed eingeschlossen, wenn der Lookback-Datumsbereich auf 7 Tage festgelegt wäre.

>[!ENDSHADEBOX]

### Sitzungsberechnung

Die Sitzungsgrenzen werden anhand aller Ereignisse im Lookback-Datumsbereich berechnet, nicht nur anhand der Ereignisse im Versandfenster. Eine Sitzung, die vor dem Versandfenster gestartet wurde, wird weiterhin als dieselbe Sitzung erkannt.

Die Sitzungs-ID basiert auf der Person, der Sitzungsstartzeit und den Sitzungseinstellungen in Ihrer Datenansicht. Eine Sitzung behält die gleiche Sitzungs-ID für alle Sendungen bei, sodass Sie Ereignisse aus einer Sitzung verbinden können, die mehrere stündliche oder tägliche Sendungen umfasst.

Beachten Sie beim Arbeiten mit Sitzungen in Daten-Feeds Folgendes:

* Wenn eine Sitzung vor dem Lookback-Datumsbereich gestartet wurde, sind die früheren Ereignisse nicht verfügbar, sodass die Sitzungswerte von Analysis Workspace abweichen können. Weitere Informationen finden Sie unter [Grundlegendes zu Datendiskrepanzen zwischen Daten-Feeds und Analysis Workspace](/help/components/exports/cja-data-feeds/df-comparison-workspace.md).
* Durch Ändern der Sitzungseinstellungen in der Datenansicht werden Sitzungs-IDs geändert. Die Sitzungs-IDs in späteren Sendungen stimmen nicht mit den Sitzungs-IDs in früheren Sendungen überein.

### Dimension-Persistenz

Wenn Sie die Persistenz für eine einzelne Dimension festlegen, legen Sie auch eine Gültigkeit fest, um zu bestimmen, wie lange das Dimensionselement über das Ereignis hinaus bestehen bleibt, für das es festgelegt ist.

Der Lookback-Datumsbereich wirkt sich auf die Persistenz der Dimensionen aus, wenn die Gültigkeit auf eine der folgenden Optionen in der Datenansicht eingestellt ist:

* [!UICONTROL **Fenster „Personenberichterstattung“**]: Der Datumsbereich des Lookback wird zum neuen Berichtsfenster für jede Dimension in der Daten-Feed-Definition, die das [!UICONTROL **Fenster „Personenberichterstattung“**] als Ablaufdatum verwendet.
* [!UICONTROL **Benutzerdefinierte Zeit**]: Wenn die ausgewählte benutzerdefinierte Zeit über den Lookback-Datumsbereich hinausgeht, wird die benutzerdefinierte Zeit ignoriert, und der Lookback-Datumsbereich wird für den Ablauf der Dimension für jede Dimension in der Daten-Feed-Definition verwendet, die [!UICONTROL **Benutzerdefinierte Zeit**] als Ablauf verwendet. Werte, die vor dem Lookback-Datumsbereich aufgetreten sind, werden nicht berücksichtigt.

  Weitere Informationen zum Festlegen der Persistenz für Dimensionen in der Datenansicht finden Sie unter [Persistenzkomponenteneinstellungen](/help/data-views/component-settings/persistence.md).

Um die genauesten Daten zu erhalten, sollten Sie den Datumsbereich des Lookback auf einen Wert festlegen, der gleich oder größer dem Persistenzwert ist, der für Dimensionen in Ihren Daten festgelegt ist. Beachten Sie jedoch, dass ein kürzerer Lookback-Datumsbereich zu einer besseren Leistung für Daten-Feed-Sendungen führt.

>[!BEGINSHADEBOX]

**Beispiel:**

Angenommen, Sie möchten in Ihrem Daten-Feed wissen, welche Marketing-Kampagnen-Benutzer ursprünglich gesehen haben, bevor sie zu Ihrer Site kamen.

Hierzu legen Sie die Persistenz für die Dimension Kampagnen mit Original als Zuordnungsmodell fest.

In diesem Fall wird die ursprüngliche Kampagne nur dann in der Daten-Feed-Ausgabe angezeigt, wenn Benutzende **beide** der folgenden Bedingungen erfüllen:

* Der Benutzer hatte ein Ereignis mit einem Zeitstempel, das sich im Datenfeed-Häufigkeitsfenster befindet (die angegebene Stunde oder der angegebene Tag des Daten-Feeds).

* Der Benutzer hat sich für die ursprüngliche Kampagne qualifiziert **manchmal innerhalb des Lookback-Datumsbereichs**.

  Wenn sich der Benutzer vor 9 Tagen für die ursprüngliche Kampagne qualifiziert hat, **die ursprüngliche Kampagne** ist enthalten) im Daten-Feed, wenn der Datumsbereich des Lookback auf 30 Tage festgelegt ist, aber die ursprüngliche Kampagne **ist nicht enthalten** im Daten-Feed, wenn der Datumsbereich des Lookback auf 7 Tage festgelegt ist.

>[!ENDSHADEBOX]

### Abgeleitete Feldtransformationen

Alle abgeleiteten Feldfunktionen, die auf Container verweisen, verwenden den Lookback-Datumsbereich in Daten-Feed-Exporten. Welche Datumsfunktionen sind in abgeleiteten Feldern vorhanden? <!--Not sure how this applies.-->

## Informationen zur Verarbeitungsverzögerung {#data-feed-processing-delay}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_processing_delay"
>title="Verarbeitungsverzögerung"
>abstract="Die Zeit, die Customer Journey Analytics wartet, bevor eine Daten-Feed-Datei verarbeitet wird. Alle spät eintreffenden Ereignisse, die während der Verarbeitungsverzögerung eintreten, sind im Daten-Feed enthalten.<p>Die minimale Verarbeitungsverzögerung beträgt 2 Stunden, aber einige Datentypen erfordern eine längere Verzögerung. Wählen Sie eine Verzögerung aus, die lang genug ist, damit die langsamsten Daten in Ihrer Verbindung im Experience Platform Data Lake ankommen und in Customer Journey Analytics aufgenommen werden. Wenn die Verzögerung zu kurz ist, werden Daten, die noch verarbeitet werden, nicht in die Daten-Feed-Datei aufgenommen.</p><p>Das Zusammenfügen kann bis zu 4 Stunden dauern. Fügen Sie daher für alle zugeordneten Daten 4 Stunden zur Verzögerung hinzu.</p>"

<!-- markdownlint-enable MD034 -->

### Funktionsweise der Verarbeitungsverzögerung

Die Verarbeitungsverzögerung ist die Zeit, die Customer Journey Analytics wartet, bevor eine Daten-Feed-Datei verarbeitet wird. Alle spät eintreffenden Ereignisse, die während der Verarbeitungsverzögerung eintreten, sind im Daten-Feed enthalten.

Verarbeitungsverzögerungen sind aus verschiedenen Gründen erforderlich, z. B. um die Pipeline-Latenz zu berücksichtigen, um mobilen Implementierungen die Möglichkeit zu geben, dass Offline-Geräte online gehen und Daten senden, oder um die Server-seitigen Prozesse Ihres Unternehmens bei der Verwaltung zuvor verarbeiteter Dateien zu berücksichtigen.

Die minimale Verarbeitungsverzögerung beträgt 2 Stunden, aber einige Datentypen erfordern eine längere Verzögerung.

>[!BEGINSHADEBOX]

**Beispiel:**

Angenommen, ein stündlicher Daten-Feed umfasst Daten von 13:00 bis 14:00 Uhr und die Verarbeitungsverzögerung beträgt 2 Stunden. Die Verarbeitung für diese Daten-Feed-Datei beginnt um 16:00 Uhr und umfasst alle Daten, die vor Beginn der Verarbeitung eingegangen sind.

>[!ENDSHADEBOX]

### Auf Ihren Daten basierende Verarbeitungsverzögerung auswählen

Verschiedene Datentypen benötigen unterschiedlich viel Zeit, bis sie in Customer Journey Analytics verfügbar sind. Die Daten durchlaufen zwei Verarbeitungsphasen, wobei die Zeit für jede Phase addiert wird.

Wählen Sie eine Verarbeitungsverzögerung aus, die lang genug ist, damit die langsamsten Daten in Ihrer Verbindung beide Phasen abschließen. Wenn die Verzögerung zu kurz ist, werden Daten, die noch verarbeitet werden, nicht in die Daten-Feed-Datei aufgenommen.

#### Phase 1: Daten gelangen in den Data Lake von Experience Platform

Die Ankunftszeiten variieren je nach Art der Daten, die Sie erfassen. Wählen Sie eine Verzögerung aus, die dem erfassten Datentyp entspricht.

* **Ereignisdatensätze aus der Edge Network- oder Streaming-Aufnahme**: Normalerweise gelangen Daten innerhalb von 60 Minuten im Data Lake an (siehe [Latenzen](/help/technotes/guardrails.md#latencies)).

* **Analytics-Quell-Connector** Datensätze: Daten gelangen normalerweise innerhalb von 2,25 Stunden in den Data Lake (siehe [Latenzen](/help/technotes/guardrails.md#latencies)).

  <!--When using the Analytics Source Connector, the minimum processing delay increases from 2 hours to 6 hours (?) to account for the source connector data. (checking to see if this is feasible) -->

* **Datensätze aus anderen Quell-Connectoren**: Die Latenz variiert je nach Quell-Connector und nach dem Zeitpunkt des Batch-Versands. Die Upstream-Verarbeitung in Experience Platform, z. B. die Datenvorbereitung, kann mehr Zeit hinzufügen.

* **Lookup-Datensätze**: Die Zeit, während der Daten im Data Lake eintreffen, hängt davon ab, wie oft Daten hochgeladen werden. Suchdaten werden in der Regel als vollständige Kopie einer Datenbank hochgeladen, in der sich nur ein kleiner Prozentsatz der Datensätze geändert hat. Laden Sie Suchdaten in kleineren Batches hoch, um die Verarbeitungszeit zu verkürzen.

  Kleine Uploads werden in der Regel innerhalb der minimalen Verzögerung verarbeitet.

  Große Uploads (z. B. ein wöchentlicher Upload von Millionen von Datensätzen) werden mit einer niedrigeren Priorität verarbeitet und können 3 bis 4 Stunden länger dauern. Bei großen Uploads werden die Ereignisdaten nicht verzögert, aber die Suchwerte spiegeln möglicherweise nicht die neuesten Aktualisierungen wider.

* **Profildatensätze**: Die Zeit, während der Daten im Data Lake eintreffen, hängt davon ab, wie oft Daten hochgeladen werden. Profildaten werden in der Regel in großen Batches aufgenommen, z. B. als tägliche Momentaufnahme der vollständigen Profiltabelle. Hochladen von Profildaten in kleineren Batches, um die Verarbeitungszeit zu verkürzen.

  Kleine Uploads werden in der Regel innerhalb der minimalen Verzögerung verarbeitet.

  Große Uploads (z. B. ein wöchentlicher Upload von Millionen von Datensätzen) werden mit einer niedrigeren Priorität verarbeitet und können 3 bis 4 Stunden länger dauern. Bei großen Uploads werden die Ereignisdaten nicht verzögert, aber die Profilwerte spiegeln möglicherweise nicht die neuesten Aktualisierungen wider.

#### Phase 2: Daten werden aus dem Data Lake in Customer Journey Analytics aufgenommen

Dies kann bis zu 90 Minuten dauern (siehe [Latenzen](/help/technotes/guardrails.md#latencies)).

* **Zusammengefügte Datensätze**: Beim Zusammenfügen können bis zu 4 Stunden hinzugefügt werden (siehe [Latenzen](/help/technotes/guardrails.md#latencies)). Wenn für die Verbindung das Stitching aktiviert ist, setzen Sie die Verzögerung auf mindestens 6 Stunden und möglicherweise 8 Stunden. Daten, die durch eine Zusammenfügungs-Wiederholung aktualisiert werden, sind im Allgemeinen nicht in den Daten-Feed-Dateien enthalten, die bereits verarbeitet wurden.

  Wenn das Zusammenfügen aktiviert ist, erhöht sich die minimale Verarbeitungsverzögerung von 2 auf 6 Stunden, um die zusammengefügten Daten zu berücksichtigen.

>[!BEGINSHADEBOX]

**Beispiel:**

Wenn Ihre Verbindung mehrere Datentypen enthält, wählen Sie eine Verzögerung aus, die den langsamsten Daten entspricht. Im folgenden Beispiel sind dies etwa 8 Stunden.

Beim Zusammenfügen können bis zu 4 Stunden für die Aufnahme in Customer Journey Analytics hinzugefügt werden. Fügen Sie daher für alle zugeordneten Daten 4 Stunden zur Verzögerung hinzu.

| Datenquelle | Phase 1: Ankunft im Data Lake | Phase 2: Aufnahme in Customer Journey Analytics | Gesamt |
| --- | --- | --- | --- |
| Edge Network- oder Streaming-Aufnahme | 60 Minuten | 90 Minuten <p>ohne Stitching</p> | 2,5 Stunden |
| Analytics-Quell-Connector | 2,25 Stunden | 90 Minuten + 4 Stunden zum Zusammennähen <p>mit Stitching</p> | 7,75 Stunden |

>[!ENDSHADEBOX]


