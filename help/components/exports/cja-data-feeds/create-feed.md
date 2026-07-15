---
title: Erstellen eines Daten-Feeds
description: Erfahren Sie, wie ein Daten-Feed erstellt wird und welche Dateiinformationen Adobe zur Verfügung gestellt werden müssen.
hide: true
feature: Components
autotag-review: '2026-05-19T08:45:44.870Z'
TQID: 'https://experienceleague.adobe.com/QgBD7vCkw4YA568XOLlwTnw8eZVZybXr3DFbM1ZKYDw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 0cc15e1c3dcbd8609a47954af8602ad617c67a51
workflow-type: tm+mt
source-wordcount: 2774
ht-degree: 28%

---

# Erstellen eines Daten-Feeds

{{release-limited-testing}}

Stellen Sie Adobe beim Erstellen eines Daten-Feeds Folgendes zur Verfügung:

* Informationen über das Ziel, an das Rohdatendateien gesendet werden sollen

* Die Daten, die in jede Datei aufgenommen werden sollen

* Die Häufigkeit, mit der Daten gesendet werden (einschließlich der Verarbeitungsverzögerung zur Erfassung verspäteter Treffer)

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
>abstract="Steuert, wie weit Customer Journey Analytics bei der Verarbeitung der Daten-Feed-Bereitstellung zurückblickt.<br/>Mit dieser Einstellung wird das Häufigkeitsfenster (Stunde oder Tag) nicht geändert. Der Lookback-Datumsbereich kann jedoch Auswirkungen auf die bereitgestellten Daten haben. Die Segmentqualifikation, die Sitzungsberechnung, einige abgeleitete Feldtransformationen und die Dimensionspersistenz werden alle vom Lookback-Datumsbereich beeinflusst."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_user-agent"
>title=""
>abstract="Benutzeragentendaten und Gerätesuchdaten können nicht in derselben Daten-Feed-Konfiguration vorhanden sein."

<!-- markdownlint-enable MD034 -->

1. Melden Sie sich mit Ihren Adobe ID-Anmeldeinformationen bei [experiencecloud.adobe.com](https://experiencecloud.adobe.com) an.

1. Wählen Sie [!UICONTROL **Customer Journey Analytics**] im App-Umschalter ![App](/help/assets/icons/Apps.svg) oben rechts in der Benutzeroberfläche aus.

1. Navigieren Sie in der oberen Navigationsleiste zu [!UICONTROL **Komponenten**] > [!UICONTROL **Daten-Feeds**].

1. Wählen [!UICONTROL **Erstellen**] in der oberen rechten Ecke des Bildschirms aus.

   Oder wählen Sie, wenn zuvor keine Daten-Feeds erstellt wurden [!UICONTROL **in**] leeren Tabelle die Option „Daten-Feed erstellen“ aus.

   Eine Seite wird mit den folgenden Registerkarten angezeigt: [!UICONTROL **Details**], [!UICONTROL **Datenstruktur**] und [!UICONTROL **Versand**].

   ![Neue Daten-Feed-Seite](assets/data-feed-new.png)

1. Füllen Sie auf [!UICONTROL **Registerkarte**] Details“ die folgenden Felder aus:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Name**] | Der Name des Daten-Feeds. Namen müssen in der ausgewählten Datenansicht eindeutig sein und können bis zu 255 Zeichen lang sein. <!--[Learn more](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique)--> |
   | [!UICONTROL **Tags**] | Wenden Sie beliebige Tags auf den Daten-Feed an, um die Kategorisierung zu erleichtern. <!--You can filter on tags as described in [Filter and search the list of data feeds](/help/export/analytics-data-feed/df-manage-feeds.md#filter-and-search-the-list-of-data-feeds) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).--> |
   | [!UICONTROL **Beschreibung**] | Geben Sie eine Beschreibung für den Daten-Feed an. Die von Ihnen hinzugefügte Beschreibung ist beim Bearbeiten des Daten-Feeds sichtbar. |
   | [!UICONTROL **Datenansicht**] | Wählen Sie die Datenansicht aus, die die zu exportierenden Daten enthält.<p>Beachten Sie bei der Auswahl einer Datenansicht Folgendes:</p> <ul><li>Wenn mehrere Daten-Feeds für dieselbe Datenansicht erstellt werden, muss jeder Daten-Feed unterschiedliche Spaltendefinitionen haben.</li><li>Die Liste der verfügbaren Spalten hängt vom Anmeldeunternehmen ab, zu dem die ausgewählte Datenansicht gehört. Wenn Sie die Datenansicht ändern, kann sich die Liste der verfügbaren Spalten ändern. </li></ul> |

1. Wählen Sie [!UICONTROL **Weiter**] aus.

1. Stellen [!UICONTROL **auf der Registerkarte**] Datenstruktur) sicher, dass im Feld **[!UICONTROL Datenansicht“ die richtige]** ausgewählt ist.

1. Suchen Sie [!UICONTROL **Dropdown-Menü**] Segmente“ nach beliebigen Segmenten und wählen Sie diese aus, um die in Ihrem Feed enthaltenen Daten zu filtern.

   Wenn Sie mehrere Segmente anwenden, werden sie mit einem AND-Operator verbunden. (Um Segmente mit einem OR-Operator zu verbinden, müssen Sie zunächst ein neues Segment in Segment Builder erstellen und dann das neue Segment auf den Daten-Feed anwenden.)

1. Fügen Sie Komponenten zur Daten-Feed-Konfiguration hinzu. Suchen Sie in der linken Leiste alle Komponenten, die Sie einbeziehen möchten, und ziehen Sie sie dann auf die Arbeitsfläche, um Ihre Datenstruktur zu erstellen. Sie können mehrere Komponenten auswählen, indem Sie die **[!UICONTROL Umschalttaste]** gedrückt halten oder indem Sie die **[!UICONTROL Befehlstaste]** (macOS) bzw. die **[!UICONTROL Strg-Taste]** (Windows) gedrückt halten.

   >[!NOTE]
   >
   >Benutzeragentendaten und Gerätesuchdaten können nicht in derselben Daten-Feed-Konfiguration vorhanden sein. Beim Versuch, widersprüchliche Komponenten hinzuzufügen, wird ein Fehler angezeigt. Weitere Informationen finden Sie unter [Konfigurieren der Gerätesuche](https://experienceleague.adobe.com/de/docs/experience-platform/datastreams/configure#geolocation-device-lookup) in [Erstellen und Konfigurieren von &#x200B;](https://experienceleague.adobe.com/de/docs/experience-platform/datastreams/configure)) im Datenerfassungshandbuch.


   Verwenden Sie die folgenden Informationen, um Dimensionen zu verstehen, die immer enthalten sind, Dimensionen, die nicht enthalten sein können, und Metriken, die ersetzt werden müssen:

   +++ Dimensionen, die immer in Daten-Feeds enthalten sind

   Die folgenden Dimensionen sind standardmäßig in jedem Daten-Feed enthalten und können nicht entfernt werden:

   | Name der Dimension | Anmerkungen | Daten-Feeds | Sonstige Berichte |
   |---|---|---|---|
   | Zeitstempel UTC | Datum und Uhrzeit des Ereignisses, dargestellt in UTC-Zeitzone. Unterstützt die Granularität von Subsekunden (Mikrosekunden). | Obligatorisch | Nicht verfügbar |
   | Zeilen-ID | Die eindeutige Kennung für jede im Daten-Feed enthaltene Zeile. | Obligatorisch | Nicht verfügbar |
   | Sitzungs-ID | Die eindeutige Kennung für jede Sitzung, die im Daten-Feed enthalten ist. | Obligatorisch | Nicht verfügbar |
   | Personen-ID | Die Personenkennung für die Datenansicht und die Verbindung | Obligatorisch | Optionaler Standard |
   | Konto-ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Konto-ID bei Verwendung des Konto-Containers | Obligatorisch | Optionaler Standard |

   +++

   +++ Dimensionen, die nicht in Daten-Feeds enthalten sein können

   Customer Journey Analytics-Standarddimensionen können nicht in Daten-Feeds enthalten sein. In der folgenden Tabelle sind diese Dimensionen aufgeführt:

   | Name der Dimension | Anmerkungen | Daten-Feeds |
   |---|---|---|
   | 5 Minuten | Intervall von fünf Minuten, in dem Ereignisse aufgetreten sind (abgerundet) | Nicht verfügbar |
   | 15 Minuten | Intervall von 15 Minuten, in dem Ereignisse aufgetreten sind (abgerundet) | Nicht verfügbar |
   | 30 Minuten | Intervall von 30 Minuten, in dem Ereignisse aufgetreten sind (abgerundet) | Nicht verfügbar |
   | Tag | Tag, an dem ein Ereignis aufgetreten ist | Nicht verfügbar |
   | Wochentag | Wochentag, an dem ein Ereignis aufgetreten ist | Nicht verfügbar |
   | Tag des Monats | Tag des Monats, an dem ein Ereignis aufgetreten ist | Nicht verfügbar |
   | Stunde | Stunde, in der ein Ereignis aufgetreten ist (abgerundet) | Nicht verfügbar |
   | Stunde des Tages | Uhrzeit, zu der ein Ereignis aufgetreten ist (abgerundet) | Nicht verfügbar |
   | Minute | Minute, in der ein Ereignis aufgetreten ist (abgerundet) | Nicht verfügbar |
   | Minute der Stunde | Minute der Stunde, in der ein Ereignis aufgetreten ist (abgerundet) | Nicht verfügbar |
   | Monat | Monat, in dem ein Ereignis aufgetreten ist | Nicht verfügbar |
   | Monat des Jahres | Monat des Jahres, in dem ein Ereignis aufgetreten ist | Nicht verfügbar |
   | Quartal | Quartal, in dem ein Ereignis aufgetreten ist | Nicht verfügbar |
   | Quartal des Jahres | Quartal des Jahres, in dem ein Ereignis aufgetreten ist | Nicht verfügbar |
   | Second | Zweites Ereignis eingetreten (abgerundet) | Nicht verfügbar |
   | Woche | Woche, in der ein Ereignis aufgetreten ist | Nicht verfügbar |
   | Woche des Jahres | Woche des Jahres, in dem ein Ereignis aufgetreten ist | Nicht verfügbar |
   | Jahr | Jahr, in dem ein Ereignis aufgetreten ist | Nicht verfügbar |

   +++

   +++ Metriken, die in Daten-Feeds ersetzt werden müssen

   Die folgenden Customer Journey Analytics-Metriken müssen ersetzt werden:

   | Metrikname | Anmerkungen | Daten-Feeds |
   |---|---|---|
   | Konten [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Basiert auf der in der Verbindung angegebenen Konto-ID | Nicht verfügbar. Anzahl der eindeutigen Konten-ID verwenden. |
   | Einkaufsgruppe [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Kaufen von Gruppen basierend auf der Käufergruppen-ID in der Verbindung | Nicht verfügbar. Anzahl der unterschiedlichen Einkaufsgruppen-IDs verwenden. |
   | Ereignisse | Anzahl der Zeilen aus allen Ereignisdatensätzen in einer Verbindung | Nicht verfügbar. Anzahl der eindeutigen Zeilen-ID verwenden. |
   | Globale Konten [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Basierend auf globaler Konto-ID in der Verbindung | Nicht verfügbar. Anzahl der eindeutigen globalen Konten-ID verwenden. |
   | Opportunities [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Opportunities basierend auf der Opportunity-ID in der Verbindung | Nicht verfügbar. Anzahl der eindeutigen Opportunity-ID verwenden. |
   | Personen | Basiert auf der in einer Verbindung angegebenen Personen-ID | Nicht verfügbar. Anzahl der eindeutigen Personen-ID verwenden. |
   | Konversationen | Anzahl der Unterhaltungen | Nicht verfügbar. Anzahl der verschiedenen Konversations-IDs verwenden. |
   | Sitzungsenden | Anzahl der Ereignisse, die das letzte Ereignis einer Sitzung waren | Nicht verfügbar |
   | Sitzungsstarts | Anzahl der Ereignisse, die das erste Ereignis einer Sitzung waren | Nicht verfügbar |
   | Sitzungen | Basiert auf den Sitzungseinstellungen der Datenansicht | Nicht verfügbar. Anzahl der eindeutigen Sitzungs-ID verwenden. |
   | Verbrachte Zeit (Sekunden) | Addiert die Zeit zwischen zwei verschiedenen Dimensionswerten | Nicht verfügbar |

   +++

   +++ Optionale Standardkomponenten

   | Name der Komponente | Typ | Anmerkungen | Daten-Feeds |
   |---|---|---|---|
   | Vormittag/Nachmittag | Zeitunterteilungsdimension | Vormittag oder Nachmittag | Nicht verfügbar |
   | Batch-ID | Dimension | Kennung für einen Experience Platform-Batch | Verfügbar |
   | Datensatz-ID | Dimension | Kennung für einen Experience Platform-Datensatz | Verfügbar |
   | Tag des Monats | Zeitunterteilungsdimension | 1-31 | Nicht verfügbar |
   | Wochentag | Zeitunterteilungsdimension | Montag bis Sonntag | Nicht verfügbar |
   | Tag des Jahres | Zeitunterteilungsdimension | 1-366 | Nicht verfügbar |
   | Ereignistiefe | Dimension | Numerischer Folgewert (1, 2, 3 usw.) Jeder Ereignisinteraktion innerhalb einer Sitzung zugewiesen<p>Wird zu Beginn jeder neuen Sitzung zurückgesetzt</p> | Verfügbar |
   | Stunde des Tages | Zeitunterteilungsdimension | 0-23 | Nicht verfügbar |
   | Monat des Jahres | Zeitunterteilungsdimension | Januar-Dezember | Nicht verfügbar |
   | Erstmalige Sitzungen | Metrik | Die erste definierte Sitzung einer Person im Reporting-Fenster | Nicht verfügbar |
   | Rückkehrende Sitzungen | Metrik | Sitzungen, die nicht die Erstsitzung einer Person waren | Nicht verfügbar |
   | Personen-ID-Namespace | Dimension | Typ der ID, aus der die Personen-ID besteht (z. B. E-Mail- oder Cookie-ID) | Verfügbar |
   | Globale Konto-ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimension | Globale Konto-ID bei Verwendung des Containers für globale Konten | Verfügbar |
   | Opportunity-ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimension | Opportunity-ID bei Verwendung des Opportunity-Containers | Verfügbar |
   | Einkaufsgruppen-ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimension | Einkaufsgruppen-ID bei Verwendung des Einkaufsgruppen-Containers | Verfügbar |
   | Quartal des Jahres | Zeitunterteilungsdimension | Q1, Q2, Q3, Q4 | Nicht verfügbar |
   | Sitzung wiederholen | Metrik | Sitzungen, die nicht die allererste Sitzung einer Person waren | Nicht verfügbar |
   | Sitzungstyp | Dimension | Zwei Werte: Erstmalig oder Wiederkehrend | Nicht verfügbar |
   | Aufgewendete Zeit pro Ereignis | Dimension | Sammelt die Metrik Aufgewendete Zeit in Ereignis-Buckets | Nicht verfügbar |
   | Aufgewendete Zeit pro Sitzung | Dimension | Fasst die Metrik Aufgewendete Zeit in Sitzungs-Buckets zusammen | Nicht verfügbar |
   | Aufgewendete Zeit pro Person | Dimension | Fasst die Metrik Aufgewendete Zeit in Behältern des Typs Person zusammen | Nicht verfügbar |
   | Wochenende/Wochentag | Zeitunterteilungsdimension | Wochenende oder Wochentag | Nicht verfügbar |

   +++


1. Geben [!UICONTROL **auf der Registerkarte**] Versand“ die folgenden Informationen an:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Feed-Typ**] | Wählen Sie den Feed-Typ aus, den Sie erstellen möchten:<ul><li>[!UICONTROL **Live-Feed**]: Exportiert aktuelle und zukünftige Daten.</li><li>[!UICONTROL **Aufstockungs-Feed**]: Exportiert historische Daten zwischen zwei früheren Datumsangaben.</li></ul> |
   | [!UICONTROL **Startdatum**] | Geben Sie das Datum an, an dem der Daten-Feed beginnen soll. Um sofort mit der Verarbeitung von Daten-Feeds für historische Daten zu beginnen, stellen Sie sicher, dass [!UICONTROL **Aufstockungs-Feed**] ausgewählt ist, und setzen Sie dieses Datum auf ein beliebiges Datum in der Vergangenheit, wenn Daten erfasst werden. Das Startdatum basiert auf der Zeitzone der Datenansicht. |
   | [!UICONTROL **Enddatum**] | Geben Sie das Datum an, an dem der Daten-Feed beendet werden soll. Das Enddatum basiert auf der Zeitzone der Datenansicht. |
   | [!UICONTROL **Häufigkeit**] | Legen Sie fest, wie oft der Daten-Feed gesendet werden soll. Ereignisse mit Zeitstempeln, die in das Häufigkeitsfenster fallen, werden in den Daten-Feed-Versand aufgenommen. Die Felder [!UICONTROL **Lookback**] Datumsbereich und [!UICONTROL **Verarbeitungsverzögerung**] können sich auch darauf auswirken, welche Ereignisse für die von Ihnen gewählte Versandfrequenz in die Daten aufgenommen werden.<p>Wählen Sie für Live-Feeds aus, ob die Daten einer Stunde oder die Daten eines Tages enthalten sein sollen. Aufstockungs-Feeds müssen täglich sein.</p><ul><li>**Täglich**: Feeds enthalten Daten eines ganzen Tages von Mitternacht bis Mitternacht in der Zeitzone der Datenansicht. Verwenden Sie diese Option für Aufstockungs-Feeds oder für Live-Feeds.</li><li>**Stündlich**: Feeds enthalten Daten für eine einzige Stunde. Verwenden Sie diese Option für Live-Feeds.</li></ul> |
   | [!UICONTROL **Lookback-Datumsbereich**] | Steuert, wie weit Customer Journey Analytics bei der Verarbeitung der Daten-Feed-Bereitstellung zurückblickt. <p>Diese Einstellung ändert nicht das Häufigkeitsfenster (Stunde oder Tag), das den Zeitrahmen der Ereignisse definiert, die in die Daten-Feed-Ausgabe aufgenommen werden sollen. Der Lookback-Datumsbereich kann jedoch die bereitgestellten Daten wie folgt beeinflussen: </p><ul><li>**Segmentqualifikation**: Wenn ein Segment auf Ihre Daten-Feed-Definition angewendet wird, bestimmen alle Ereignisse innerhalb des Lookback-Datumsbereichs, ob eine Person qualifiziert ist. Die Container-Einstellung des Segments bestimmt den Umfang. (Mögliche Container sind: Person, Sitzung oder Ereignis. B2B hat die folgenden zusätzlichen Container: Globales Konto, Konto, Opportunity, Einkaufsgruppe.)  <p>Wenn beispielsweise ein Personen-Container verwendet wird und die Person für den Datumsbereich „Lookback“ qualifiziert ist, sind auch alle Ereignisse dieser Person im Häufigkeitsfenster qualifiziert.</p></li><li>**Sitzungsberechnung**: Sitzungsgrenzen werden anhand von Daten innerhalb des Lookback-Datumsbereichs berechnet.</li><li>**Abgeleitete Feldtransformationen**: Alle abgeleiteten Feldfunktionen, die auf Container verweisen, verwenden den Lookback-Datumsbereich in Daten-Feed-Exporten.</li><li>**Dimension-Persistenz**: Wenn Sie sich dafür entscheiden, die Persistenz für eine einzelne Dimension festzulegen, wählen Sie auch eine Gültigkeit aus, um zu bestimmen, wie lange ein Dimensionselement über das Ereignis hinaus bestehen bleibt, für das es festgelegt ist. <p>Der Lookback-Datumsbereich wirkt sich auf die Persistenz der Dimensionen aus, wenn die Gültigkeit auf eine der folgenden Optionen in der Datenansicht eingestellt ist:</p><ul><li>Für jede Dimension in der Daten-Feed-Definition, die [!UICONTROL **Reporting-Fenster**] als Ablaufdatum verwendet, wird der Lookback-Datumsbereich zum neuen Reporting-Fenster.</li><li>Für jede Dimension in der Daten-Feed-Definition, die [!UICONTROL **Benutzerdefinierte Zeit**] als Ablaufdatum verwendet, wird die benutzerdefinierte Zeit ignoriert und der Lookback-Datumsbereich wird für die Gültigkeitsdauer der Dimension verwendet, wenn die ausgewählte benutzerdefinierte Zeit über den Datumsbereich des Lookback hinausgeht.<p>Weitere Informationen zum Festlegen der Persistenz für Dimensionen in der Datenansicht finden Sie unter [Persistenzkomponenteneinstellungen](/help/data-views/component-settings/persistence.md).</p></li></ul> |
   | [!UICONTROL **Verarbeitungsverzögerung**] | Wählen Sie die Wartezeit, bevor eine Daten-Feed-Datei verarbeitet wird. Alle verspätet eintreffenden Treffer, die während der Verarbeitungsverzögerung eintreten, werden im Daten-Feed berücksichtigt. <p>Verarbeitungsverzögerungen sind aus verschiedenen Gründen nützlich, z. B. um mobilen Implementierungen die Möglichkeit zu geben, dass Offline-Geräte online gehen und Daten senden, oder um die Server-seitigen Prozesse Ihres Unternehmens bei der Verwaltung zuvor verarbeiteter Dateien zu berücksichtigen. </p><p>Sie können einen Feed um 2, 3, 4 oder 8 Stunden verzögern.<p>Sitzungen müssen nach dem Abbruch der Verarbeitungsverzögerung beginnen, um einbezogen zu werden; Sitzungen, die vor dem Abbruch beginnen und innerhalb der Verarbeitungsverzögerung enden, sind nicht enthalten.</p> |
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
   | [!UICONTROL **Nach Abschluss benachrichtigen**] | Geben Sie eine oder mehrere E-Mail-Adressen an, an die eine Benachrichtigung gesendet werden soll, nachdem der Daten-Feed erfolgreich gesendet wurde oder nicht gesendet werden kann. Mehrere E-Mail-Adressen müssen durch ein Komma getrennt werden. |
   | [!UICONTROL **Manifest aktivieren**] | Wählen Sie aus, ob bei jeder Daten-Feed-Bereitstellung eine Manifestdatei enthalten sein soll. Die Manifestdatei enthält Informationen für jede Datei, die im Daten-Feed enthalten ist. |

1. Wählen Sie **[!UICONTROL Speichern]** aus.


