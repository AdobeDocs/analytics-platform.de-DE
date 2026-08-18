---
title: Erstellen eines Daten-Feeds
description: Erfahren Sie, wie ein Daten-Feed erstellt wird und welche Dateiinformationen Adobe zur Verfügung gestellt werden müssen.
hide: true
feature: Components
autotag-review: '2026-05-19T08:45:44.870Z'
TQID: 'https://experienceleague.adobe.com/QgBD7vCkw4YA568XOLlwTnw8eZVZybXr3DFbM1ZKYDw'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: de8748a1dddbc0ddaadca4c805c9b4aba99a4267
workflow-type: tm+mt
source-wordcount: 4036
ht-degree: 20%

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
>title="Benachrichtigung bei Problemen, bei Abschluss und bei Ablauf"
>abstract="Geben Sie eine oder mehrere E-Mail-Adressen an, an die eine Benachrichtigung gesendet werden soll, wenn der Daten-Feed abgeschlossen wurde, abläuft oder Probleme auftreten. Trennen Sie mehrere E-Mail-Adressen durch ein Komma."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_processing_delay"
>title="Verarbeitungsverzögerung"
>abstract="Die Zeit, die auf verspätete Ereignisse gewartet wird, bevor eine Daten-Feed-Datei verarbeitet wird. Alle verspätet eintreffenden Treffer, die während des Verarbeitungsverzögerungszeitraums eintreten, werden im Daten-Feed berücksichtigt. <p>Verarbeitungsverzögerungen sind aus verschiedenen Gründen nützlich, z. B. um mobilen Implementierungen die Möglichkeit zu geben, dass Offline-Geräte online gehen und Daten senden, oder um die Server-seitigen Prozesse Ihres Unternehmens bei der Verwaltung zuvor verarbeiteter Dateien zu berücksichtigen.</p><p>Sitzungen müssen nach dem Abbruch der Verarbeitungsverzögerung beginnen, um einbezogen zu werden; Sitzungen, die vor dem Abbruch beginnen und innerhalb der Verarbeitungsverzögerung enden, sind nicht enthalten.</p><p>Customer Journey Analytics bestimmt dynamisch die optimale Verzögerung, basierend darauf, wie lange spät eintreffende Ereignisse für Ihren Feed normalerweise dauern. Sie können die Verzögerung jedoch manuell auf 2, 3, 4 oder 8 Stunden einstellen.</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_user-agent"
>title=""
>abstract="Benutzeragentendaten und Gerätesuchdaten können nicht in derselben Daten-Feed-Konfiguration vorhanden sein."

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

1. Fügen Sie Komponenten zur Daten-Feed-Konfiguration hinzu. In der linken Leiste werden nur Komponenten angezeigt, die für Daten-Feeds gültig sind.

   * **Drag-and-Drop**: Ziehen Sie Komponenten aus der linken Leiste auf die Arbeitsfläche. Halten Sie **[!UICONTROL Umschalt]** oder halten Sie **[!UICONTROL Befehl]** (macOS) oder **[!UICONTROL Strg]** (Windows) gedrückt, um mehrere Komponenten gleichzeitig auszuwählen und zu ziehen.
   * **Plus-Schaltfläche**: Wählen Sie in der linken Leiste das Symbol Plus ![Hinzufügen](/help/assets/icons/Add.svg) neben einer beliebigen Komponente aus, um sie zur Arbeitsfläche hinzuzufügen.
   * **[!UICONTROL Alle anzeigen]**: Wählen Sie **[!UICONTROL Alle anzeigen]** unten in der Komponentenliste aus, um ein Dialogfeld mit allen verfügbaren Komponenten zu öffnen. Aktivieren Sie das Kontrollkästchen neben jeder Komponente, die Sie hinzufügen möchten, und klicken Sie dann auf **[!UICONTROL Auswahl hinzufügen]**. Wenn ein Suchbegriff oder Filter-Tag in der linken Leiste aktiv ist, wird auch eine **[!UICONTROL Alle hinzufügen]**-Schaltfläche angezeigt, über die Sie alle gefilterten Ergebnisse gleichzeitig hinzufügen können.

   Wenn Sie eine Komponente hinzufügen, die zu einem XDM-Array-Feld gehört (z. B. einem Adobe Journey Optimizer-Vorschlagsfeld), wird sie auf der Arbeitsfläche als ausblendbare verschachtelte Gruppe und nicht als flaches Element angezeigt. Die Gruppe spiegelt die zugrunde liegende Datenstruktur wider und gibt sie als verschachteltes Array in der exportierten Datei aus.

   <!--add screenshot-->

   +++ Dimensionen, die immer in Daten-Feeds enthalten sind

   Die folgenden Dimensionen sind standardmäßig in jedem Daten-Feed enthalten und können nicht entfernt werden:

   | Name der Dimension | Anmerkungen | Daten-Feeds | Sonstige Berichte |
   |---|---|---|---|
   | Zeitstempel – UTC | Datum und Uhrzeit des Ereignisses, dargestellt in UTC-Zeitzone. Unterstützt die Granularität von Subsekunden (Mikrosekunden). | Obligatorisch | Nicht verfügbar |
   | Zeilen-ID | Die eindeutige Kennung für jede Zeile, die im Daten-Feed enthalten ist. | Obligatorisch | Nicht verfügbar |
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

   +++ Dimensionen, die nicht zusammen in Daten-Feeds verwendet werden können

   >[!IMPORTANT]
   >
   >Bestimmte Dimensionen können nicht zusammen in Experience Platform-Datensätzen verwendet werden und können daher nicht in denselben Daten-Feed aufgenommen werden.
   >
   >Wenn Sie sich dafür entscheiden, entweder die **Benutzeragent**- oder **Mobile ID**-Dimensionen in Ihren Daten-Feed aufzunehmen, können die unten aufgeführten Dimensionen nicht zum Daten-Feed hinzugefügt werden.
   >
   >Wenn Sie die Web-SDK verwenden, wird diese Einschränkung in Datenströmen erzwungen, bevor Daten in einem Experience Platform-Datensatz eingehen. Weitere Informationen finden Sie unter [Konfigurieren der Gerätesuche](https://experienceleague.adobe.com/de/docs/experience-platform/datastreams/configure#geolocation-device-lookup) in [Erstellen und Konfigurieren von ](https://experienceleague.adobe.com/de/docs/experience-platform/datastreams/configure)) im Datenerfassungshandbuch.

   Die folgenden Dimensionen können nicht zusammen mit den Dimensionen **Benutzeragent** oder **Mobile ID** verwendet werden:

   * Browser-Typ
   * Browser
   * Mobilgerätehersteller
   * Mobilgerätetyp
   * Mobilgerät - Audio-Unterstützung
   * Mobil-DRM
   * Mobil Java VM
   * Mobile Informationsdienste
   * Mobilgerät - Bildunterstützung
   * Mobilgerät - Farbtiefe
   * Mobile Netzprotokolle
   * Mobilgerätenummer
   * Maximale mobile E-Mail-Länge
   * Mobilgerät – Mail-Design
   * Mobiles PTT
   * Mobilgerät – Bildschirmbreite
   * Maximale mobile Browser-URL-Länge
   * Mobile-Betriebssystem (veraltet)
   * Mobilgerät – Bildschirmhöhe
   * Mobilgerät - Video-Unterstützung
   * Mobilgerät - Cookie-Unterstützung
   * Maximale mobile Lesezeichenlänge
   * Mobilgerät – Bildschirmgröße
   * Mobilgerätename
   * Betriebssystemtypen
   * Betriebssysteme

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

1. (Optional) Ordnen Sie Komponenten auf der Arbeitsfläche neu an, indem Sie sie ziehen. Die von Ihnen definierte Reihenfolge wird als Spaltenreihenfolge in der exportierten Daten-Feed-Datei beibehalten.

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
   | [!UICONTROL **Häufigkeit**] | Legen Sie fest, wie oft der Daten-Feed gesendet werden soll. Ereignisse mit Zeitstempeln, die in das Häufigkeitsfenster fallen, werden in den Daten-Feed-Versand aufgenommen. Die Felder [!UICONTROL **Lookback**] Datumsbereich und [!UICONTROL **Verarbeitungsverzögerung**] können sich auch darauf auswirken, welche Ereignisse für die von Ihnen gewählte Versandfrequenz in die Daten aufgenommen werden.<p>Wählen Sie für Live-Feeds aus, ob die Daten einer Stunde oder die Daten eines Tages enthalten sein sollen. Bei Aufstockungs-Feeds ist dieses Feld auf &quot;**&quot;** und kann nicht geändert werden.</p><ul><li>**Täglich**: Feeds enthalten Daten eines ganzen Tages von Mitternacht bis Mitternacht in der Zeitzone der Datenansicht. <p>Diese Option ist für Aufstockungs-Feeds erforderlich und optional für Live-Feeds.</p></li><li>**Stündlich**: Feeds enthalten Daten für eine einzige Stunde. <p>Diese Option ist nur für Live-Feeds verfügbar.</p></li></ul> |
   | [!UICONTROL **Lookback-Datumsbereich**] | Steuert, wie weit Customer Journey Analytics bei der Verarbeitung der Daten-Feed-Bereitstellung zurückblickt. Der Standardwert ist 30 Tage. <p>Der Lookback-Datumsbereich wirkt sich auf die Segmentqualifizierung, die Sitzungsberechnung, die Transformationen abgeleiteter Felder und die Dimensionspersistenz aus. <p>Bevor Sie diese Option konfigurieren, lesen Sie die Details und Beispiele im folgenden Abschnitt [Grundlegendes zum Lookback-Datumsbereich](#understand-the-lookback-date-range).</p> |
   | [!UICONTROL **Verarbeitungsverzögerung**] | Wählen Sie die Wartezeit, bevor eine Daten-Feed-Datei verarbeitet wird. Der Standardwert ist 2 Stunden. Alle spät eintreffenden Ereignisse, die während der Verarbeitungsverzögerung eintreten, sind im Daten-Feed enthalten. <p>Verarbeitungsverzögerungen sind aus verschiedenen Gründen nützlich, z. B. um mobilen Implementierungen die Möglichkeit zu geben, dass Offline-Geräte online gehen und Daten senden, oder um die Server-seitigen Prozesse Ihres Unternehmens bei der Verwaltung zuvor verarbeiteter Dateien zu berücksichtigen. </p><p>Sitzungen müssen nach dem Abbruch der Verarbeitungsverzögerung beginnen, um einbezogen zu werden; Sitzungen, die vor dem Abbruch beginnen und innerhalb der Verarbeitungsverzögerung enden, sind nicht enthalten.</p><p>Customer Journey Analytics bestimmt dynamisch die optimale Verzögerung, basierend darauf, wie lange spät eintreffende Ereignisse für Ihren Feed normalerweise dauern. Sie können die Verzögerung jedoch manuell auf 2, 3, 4 oder 8 Stunden einstellen.</p> |
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

## Verstehen des Lookback-Datumsbereichs {#data-feed-lookback-date-range}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_lookback_date_range"
>title="Lookback-Datumsbereich"
>abstract="Steuert, wie weit Customer Journey Analytics bei der Verarbeitung der Daten-Feed-Bereitstellung zurückblickt. Diese Einstellung ähnelt dem Datumsbereich für die Berichterstellung in Analysis Workspace, weist jedoch wichtige Unterschiede auf:<ul><li>Ereignisse werden im Daten-Feed eingeschlossen, wenn sie Zeitstempel haben, die in das Häufigkeitsfenster und nicht in den Lookback-Datumsbereich fallen. (In Analysis Workspace werden Ereignisse in einen Bericht aufgenommen, wenn sie Zeitstempel haben, die in den Berichtsdatumsbereich fallen.)</li><li>Ereignisse mit Zeitstempeln, die innerhalb des Lookback-Datumsbereichs (aber außerhalb des Häufigkeitsfensters) liegen, können durch Segmentqualifikation, Sitzungsberechnung, abgeleitete Feldtransformationen und Dimensionspersistenz weiterhin beeinflussen, welche Daten im Feed angezeigt werden.</li><p>Ein längerer Lookback-Datumsbereich führt in der Regel zu genaueren Ereignissen. Ein kürzerer Bereich führt zu einer besseren Versandleistung.</p>"

<!-- markdownlint-enable MD034 -->



Der Lookback-Datumsbereich steuert, wie weit Customer Journey Analytics bei der Verarbeitung des Daten-Feed-Versands zurückblickt. Der Standardwert ist 30 Tage.

Beachten Sie beim Konfigurieren dieser Option die folgenden wichtigen Konzepte:

* Ein längerer Lookback-Datumsbereich führt in der Regel zu genaueren Daten; ein kürzerer Bereich führt zu einer besseren Versandleistung.
* Der Lookback-Datumsbereich in Daten-Feeds ähnelt dem Berichtsdatumsbereich in Analysis Workspace, es gibt jedoch [wesentliche Unterschiede](/help/components/exports/cja-data-feeds/df-comparison-workspace.md#differences). Diese Unterschiede können zu Datendiskrepanzen zwischen Workspace-Berichten und Daten-Feed-Sendungen führen.
* Der Lookback-Datumsbereich ändert das Häufigkeitsfenster (Stunde oder Tag) nicht, das den Zeitrahmen der Ereignisse definiert, die in die Daten-Feed-Ausgabe aufgenommen werden sollen.
* Daten, die in den Lookback-Datumsbereich fallen, können die Inhalte des Daten-Feeds (Häufigkeitsfenster) beeinflussen, je nach den Faktoren, die in den folgenden Abschnitten beschrieben werden.

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

Sitzungsgrenzen werden anhand von Daten innerhalb des Lookback-Datumsbereichs berechnet. Vielleicht ist dies wichtiger in Bezug darauf, was die Sitzungs-ID ist? Könnte sich dies auf die Sitzungs-ID auswirken? Dies kann sich auf vieles auswirken, z. B. auf die sitzungsbasierte Persistenz.

### Abgeleitete Feldtransformationen

Alle abgeleiteten Feldfunktionen, die auf Container verweisen, verwenden den Lookback-Datumsbereich in Daten-Feed-Exporten. Welche Datumsfunktionen sind in abgeleiteten Feldern vorhanden? Ich bin mir nicht sicher, wie das zutrifft.

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

  Wenn sich der Benutzer vor 9 Tagen für die ursprüngliche Kampagne qualifiziert hat, **die ursprüngliche Kampagne in den Daten** Feed aufgenommen), wenn der Datumsbereich des Lookback auf 30 Tage festgelegt wäre, aber die ursprüngliche Kampagne **nicht einbezogen** im Daten-Feed, wenn der Datumsbereich des Lookback auf 7 Tage festgelegt wäre.

>[!ENDSHADEBOX]




