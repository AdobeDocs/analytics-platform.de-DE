---
title: Zuordnen von Adobe Analytics-Daten-Feed-Spalten zu Customer Journey Analytics
description: Ermitteln Sie, wie Sie eine bestimmte Daten-Feed-Spalte in Adobe Analytics verwenden und ihre grobe Entsprechung in Ihrer Customer Journey Analytics-Implementierung bestimmen können.
feature: Components
hide: true
exl-id: 81d6e79e-8324-4726-9a48-10177b0a91b1
source-git-commit: efa2cada4b26d71cce22c0d0e8662b6dd04f38f4
workflow-type: tm+mt
source-wordcount: '3768'
ht-degree: 47%

---

# Zuordnen von Adobe Analytics-Daten-Feed-Spalten zu Customer Journey Analytics

Eine 1::1-Zuordnung zwischen Daten-Feed-Spalten von Adobe Analytics und Customer Journey Analytics ist nicht möglich. Die beiden Produkte unterscheiden sich grundlegend, und die Implementierung der einzelnen Organisationen kann erheblich variieren.

Diese Referenz hilft Dateningenieuren, Adobe Analytics-Daten-Feed-Spalten zu bewerten und die nächstgelegenen Customer Journey Analytics-Entsprechungen für ihre Workflows zu identifizieren.

>[!NOTE]
>
>Diese Referenz enthält nur Spalten, die von Adobe auf der Grundlage der [Analytics-Daten-Feed-Spaltenreferenz) als aktuell &#x200B;](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference) werden. Wenn Sie eine Analytics-Daten-Feed-Spalte haben, die nicht in dieser Tabelle aufgeführt ist und die Sie aktiv verwenden, finden Sie im Lösungs-Design-Dokument Ihres Unternehmens die beste Entsprechung in Customer Journey Analytics.

+++**`accept_language`**

Führt alle unterstützten Sprachen, wie im HTTP-Header Accept-Language angegeben, in einer Bildanforderung auf.

+++

+++**`adload`**

Medien-Anzeigenladevorgänge

{{cja-df-post}}

+++

+++**`aemassetid`**

Mehrwert-Variable, die den Asset-IDs (GUIDs) eines Satzes von Adobe Experience Manager-Assets entspricht. Erhöht Impressionsereignisse.

{{cja-df-post}}

+++

+++**`aemassetsource`**

Identifiziert die Quelle des Asset-Ereignisses. Wird in Adobe Experience Manager verwendet.

{{cja-df-post}}
+++

+++**`aemclickedassetid`**

Asset-ID eines Adobe Experience Manager-Assets. Erhöht Klickereignisse.

{{cja-df-post}}

+++

+++**`amo_cid`**

Die AMO-ID-Dimension, die in Adobe Advertising-Integrationen verwendet wird.

{{cja-df-post}}

+++

+++**`amo_ef_id`**

Die AMO-EF-ID-Dimension, die in Adobe Advertising-Integrationen verwendet wird.

{{cja-df-post}}

+++

+++**`browser`**

Eine numerische ID, die den Browser darstellt.

{{cja-df-lookup}}

+++

+++**`browser_height`**

Die Dimension Browser-Höhe .

{{cja-df-post}}

+++

+++**`browser_width`**

Die Browser-Breite

{{cja-df-post}}

+++

+++**`campaign`**

Die Dimension Trackingcode .

{{cja-df-post}}

+++

+++**`carrier`**

Gibt den Mobilnetzbetreiber an.

{{cja-df-lookup}}

{{cja-df-ua}}

+++

+++**`channel`**

Die Dimension Site-Abschnitte .

{{cja-df-post}}

+++

+++**`ch_hdr`**

Client-Hinweise, die über die Kopfzeile der HTTP-Anfrage erfasst werden.

In Adobe Analytics wurden Client-Hinweise als verkettete Zeichenfolge in diese Spalte aufgenommen. Es gilt als modernerer Ansatz als die `user_agent`.

{{cja-df-ua}}

+++

+++**`ch_js`**

Client-Hinweise, die über die JavaScript-API für Client-Hinweise von Benutzeragenten erfasst werden.

In Adobe Analytics wurden Client-Hinweise als verkettete Zeichenfolge in diese Spalte aufgenommen. Es gilt als modernerer Ansatz als die `user_agent`.

Sie können diese Daten mithilfe der [`highEntropyUserAgentHints`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/configure/context) Kontextzeichenfolge bei der Konfiguration der Web-SDK erfassen. Anstelle einer langen verketteten Zeichenfolge werden mehrere XDM-Felder ausgefüllt:

* **Betriebssystemversion**: `xdm.environment.browserDetails.userAgentClientHints.platformVersion`
* **Architektur**: `xdm.environment.browserDetails.userAgentClientHints.architecture`
* **Gerätemodell**: `xdm.environment.browserDetails.userAgentClientHints.model`
* **Bitness**: `xdm.environment.browserDetails.userAgentClientHints.bitness`
* **Browser-Anbieter**: `xdm.environment.browserDetails.userAgentClientHints.vendor`
* **Browser-Name**: `xdm.environment.browserDetails.userAgentClientHints.brand`
* **Browser-Version**: `xdm.environment.browserDetails.userAgentClientHints.version`

Weitere Informationen finden [&#x200B; unter &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/collection/use-cases/client-hints)-Client-Hinweise für Benutzeragenten .

{{cja-df-ua}}

+++

+++**`clickmaplink`**

Die Dimension Activity Map-Link .

{{cja-df-post}}

{{cja-df-na}}

Diese Spalte gilt nicht, da Customer Journey Analytics Activity Map noch nicht unterstützt.

+++

+++**`clickmaplinkbyregion`**

Die Dimension Activity Map-Link nach Region.

{{cja-df-post}}

{{cja-df-na}}

Diese Spalte gilt nicht, da Customer Journey Analytics Activity Map noch nicht unterstützt.

+++

+++**`clickmappage`**

Die Dimension Activity Map-Seite .

{{cja-df-post}}

{{cja-df-na}}

Diese Spalte gilt nicht, da Customer Journey Analytics Activity Map noch nicht unterstützt.

+++

+++**`clickmapregion`**

Die Dimension Activity Map-Region .

{{cja-df-post}}

{{cja-df-na}}

Diese Spalte gilt nicht, da Customer Journey Analytics Activity Map noch nicht unterstützt.

+++

+++**`code_ver`**

API- oder Client SDK-Version, die für das Kompilieren und Senden der Bildanforderung verwendet wird.

+++

+++**`color`**

Farbtiefe-ID basierend auf dem Wert der `c_color`.

{{cja-df-lookup}}

+++

+++**`connection_type`**

Numerische ID, die die Dimension Verbindungstyp darstellt.

{{cja-df-lookup}}

+++

+++**`cookies`**

Die Dimension Cookie-Unterstützung .<br>Y: aktiviert<br>N: deaktiviert<br>U: unbekannt

{{cja-df-post}}

+++

+++**`country`**

Numerische ID, die das Land der Besucherin bzw. des Besuchers darstellt. Verweist auf die Suchtabelle `country.tsv`.

{{cja-df-lookup}}

+++

+++**`currency`**

Der während der Transaktion verwendete Währungscode. Festgelegt über `currencyCode`.

`xdm.commerce.order.currencyCode`

{{cja-df-post}}

+++

+++**`ct_connect_type`**

Verknüpft mit der Spalte `connection_type`. Die häufigsten Werte sind LAN/WLAN, Mobilnetzbetreiber und Modem.

+++

+++**`curr_factor`**

Bestimmt die Dezimalstelle für die Währung. Wird für die Währungsumrechnung verwendet. Beispielsweise verwendet USD zwei Dezimalstellen, daher wäre dieser Spaltenwert `2`.

+++

+++**`curr_rate`**

Der Wechselkurs zum Zeitpunkt der Transaktion. Adobe arbeitet mit XE zusammen, um den Wechselkurs des aktuellen Tages zu ermitteln.

+++

+++**`customer_perspective`**

Bestimmt, ob der Treffer ein mobiler Hintergrundtreffer ist.

{{cja-df-post}}

{{cja-df-na}}

Customer Journey Analytics verfügt über kein natives Konzept des Ereignistyps, bei dem Treffer basierend auf dem Kontext des Treffers automatisch eingeschlossen oder ausgeschlossen werden. Mithilfe von `xdm.eventType` können Sie bestimmen, welche Ereignisse in den meisten Berichten ein- und ausgeschlossen werden sollen.

+++

+++**`cust_hit_time_gmt`**

Nur für Report Suites mit aktiviertem Zeitstempel. Der mit dem Treffer gesendete Zeitstempel in UNIX®-Zeit.

Customer Journey Analytics hat kein Konzept von Zeitstempeln im Vergleich zu Report Suites ohne Zeitstempel. Verwenden Sie stattdessen `xdm.timestamp` und passen Sie die Komponenteneinstellungen nach Bedarf an.

{{cja-df-post}}

+++

+++**`cust_visid`**

Die benutzerdefinierte Besucher-ID, sofern sie über `visitorID` festgelegt wurde.

Customer Journey Analytics unterstützt eine beliebige Anzahl von Identitäten mithilfe von [`identityMap`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/profile/identitymap). Wenn Ihr Unternehmen benutzerdefinierte Identitäten verwendet, ist dies wahrscheinlich innerhalb der Identitätszuordnung.

{{cja-df-post}}

+++

+++**`c_color`**

Bit-Tiefe der Farbpalette. Wird im Rahmen der Berechnung der Dimension Farbtiefe verwendet. AppMeasurement verwendet die JavaScript-Funktion `screen.colorDepth()`.

+++

+++**`daily_visitor`**

Markierung, die bestimmt, ob es sich bei dem Treffer um eine neue tägliche Besucherin oder einen neuen täglichen Besucher handelt.

+++

+++**`dataprivacyconsentoptin`**

Die Dimension Einverständnisverwaltungs-Opt-in . Pro Treffer können mehrere Werte vorhanden sein, getrennt durch einen senkrechten Strich (`\|`). Gültige Werte sind `DMP` und `SELL`.

Wenn Ihr Unternehmen über eine Datenverwaltungsplattform verfügt, füllt es wahrscheinlich die gewünschten XDM-Felder für diese Dimension.

+++

+++**`dataprivacyconsentoptout`**

Die Dimension Einverständnisverwaltungs-Opt-out . Pro Treffer können mehrere Werte vorhanden sein, getrennt durch einen senkrechten Strich (`\|`). Gültige Werte sind `SSF`, `DMP` und `SELL`.

Wenn Ihr Unternehmen über eine Datenverwaltungsplattform verfügt, füllt es wahrscheinlich die gewünschten XDM-Felder für diese Dimension.

+++

+++**`date_time`**

Die Uhrzeit des Treffers in lesbarem Format, basierend auf der Zeitzone der Report Suite.

Sie können `xdm.timestamp` verwenden und die Komponenteneinstellung **[!UICONTROL Datum]** oder **[!UICONTROL Datum-Uhrzeit]** [Format](/help/data-views/component-settings/format.md) anwenden.

+++

+++**`domain`**

Die Dimension Domain . Basierend auf dem Internetzugangspunkt der Besuchenden.

Aktivieren **[!UICONTROL Netzwerksuche]** beim [Konfigurieren eines Datenstroms](https://experienceleague.adobe.com/de/docs/experience-platform/datastreams/configure). Das XDM-Feld wird `xdm.environment.domain`, wenn es in Ihrem Schema enthalten ist.

+++

+++**`duplicated_from`**

Wird nur in Report Suites mit VISTA-Regeln zur Trefferkopie verwendet. Gibt an, von welcher Report Suite der Treffer kopiert wurde.

{{cja-df-na}}

Diese Spalte gilt nicht, da Customer Journey Analytics kein Konzept von VISTA-Regeln hat.

+++

+++**`duplicate_events`**

Listet jedes Ereignis auf, das als Duplikat gezählt wurde.

{{cja-df-na}}

Customer Journey Analytics hat kein einzelnes Feld, das als Deduplizierungs-Markierung für alle Metriken dient. Stattdessen enthält jede Metrik ihre eigenen [Metrik-Deduplizierungs-Komponenteneinstellungen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication). Daher gibt es in Customer Journey Analytics kein entsprechendes Feld für diese Daten-Feed-Spalte in Adobe Analytics.

+++

+++**`duplicate_purchase`**

Markierung, die bestimmt, ob das Kaufereignis für diesen Treffer ignoriert wird, weil es ein Duplikat ist.

Es gibt zwar keine direkte Übersetzung für diese Analytics-Daten-Feed-Spalte, aber die Funktion, Käufe zu deduplizieren, ist noch vorhanden. Bei Verwendung der Feldergruppe [[!UICONTROL Commerce-]](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details)Details&#39; können Sie [Metrik-Deduplizierung - Komponenteneinstellungen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication) festlegen, bei die **[!UICONTROL Deduplizierungs-ID]** `xdm.commerce.purchases.id` ist.

Wenn eine direkte Übersetzung erforderlich ist, wenn Sie eine Markierung für doppelte Käufe benötigen, können Sie ein [Abgeleitetes Feld](/help/data-views/derived-fields/derived-fields.md) mithilfe der Funktion **Deduplizieren** im Regelsatz verwenden.

+++

+++**`ef_id`**

Die EF-ID, die in Adobe Advertising-Integrationen verwendet wird.

{{cja-df-post}}

+++

+++**`evar1 - evar250`**

Benutzerdefinierte Variablen 1–250. Wird in eVar-Dimensionen verwendet. Jede Organisation verwendet eVars anders. Weitere Informationen darüber, wie Ihr Unternehmen die entsprechenden eVars ausfüllt, finden Sie in einem Lösungsentwurfsdokument, das speziell auf Ihr Unternehmen zugeschnitten ist.

{{cja-df-post}}

+++

+++**`event_list`**

Kommagetrennte Liste numerischer IDs, die die durch den Treffer ausgelösten Ereignisse darstellen. Umfasst sowohl Commerce-Ereignisse als auch benutzerdefinierte Ereignisse 1-1000. Verwendet die `event.tsv`-Suche.

Diese Spalte wird je nach Ihrer Implementierung wahrscheinlich Dutzenden von separaten Metriken zugeordnet. Adobe empfiehlt den folgenden Prozess, um jede entsprechende Metrik in Customer Journey Analytics ihrem numerischen Wert zuzuordnen, der in dieser Analytics-Daten-Feed-Spalte dargestellt wird:

1. Verwenden Sie die `event.tsv` Suche, um jeden numerischen Wert seinem Metriknamen zuzuordnen.
1. Verwenden Sie Ihr Lösungsentwurfsdokument, um jeden Analytics-Ereignisnamen dem entsprechenden Metriknamen in Customer Journey Analytics zuzuordnen.
1. Wählen Sie die zugeordnete Komponente in der Datenansichts-Benutzeroberfläche aus und notieren Sie sich die Komponenten-ID. Wenn die Komponenten-ID zu umfangreich ist, können Sie das Feld für die Daten-Feed-Alias-ID ausfüllen und stattdessen diese verwenden.
1. Wiederholen Sie den Vorgang für jede Metrik, die Ihr Unternehmen verwendet.

{{cja-df-post}}

Wenn Ihr Schema die [[!UICONTROL Commerce Details]](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details)-Feldergruppe verwendet, sind einige Metriken möglicherweise direkt den folgenden XDM-Feldern zugeordnet:

* **Checkouts**: `xdm.commerce.checkouts.value`
* **Hinzufügungen zum Warenkorb**: `xdm.commerce.productListAdds.value`
* **Öffnung des Warenkorbs**: `xdm.commerce.productListOpens.value`
* **Entnahmen aus dem Warenkorb**: `xdm.commerce.productListRemovals.value`
* **Warenkorbansichten**: `xdm.commerce.productListViews.value`
* **Produktansichten**: `xdm.commerce.productViews.value`
* **Bestellungen**: `xdm.commerce.purchases.value`

Einige Metriken verwenden möglicherweise die Ereignis-Serialisierung, wodurch Adobe Analytics die volle Kontrolle über die Deduplizierung ermöglicht. Sie können die Komponenteneinstellung [Metrik-Deduplizierung](/help/data-views/component-settings/metric-deduplication.md) verwenden, um eine Deduplizierungsparität zu erzielen.

* Wenn Ihre Metrik nach Besuch in Adobe Analytics dedupliziert wird, können Sie in den Komponenteneinstellungen dieser Metrik den Deduplizierungsbereich auf Sitzung festlegen.
* Wenn Ihre Metrik nach Ereignis-ID in Adobe Analytics dedupliziert wird, enthält das XDM-Objekt für diese Metrik wahrscheinlich sowohl ein `value`- als auch ein `id`. Wenn Ihr Schema die Feldergruppe [[!UICONTROL Commerce-Details]](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details) verwendet, befinden sich diese Metriken wahrscheinlich in diesen XDM-Feldern, für die Sie in den Komponenteneinstellungen der **[!UICONTROL das Feld]** Deduplizierungs-ID) festlegen können:

   * **Checkouts**: `xdm.commerce.checkouts.id`
   * **Hinzufügungen zum Warenkorb**: `xdm.commerce.productListAdds.id`
   * **Öffnung des Warenkorbs**: `xdm.commerce.productListOpens.id`
   * **Entnahmen aus dem Warenkorb**: `xdm.commerce.productListRemovals.id`
   * **Warenkorbansichten**: `xdm.commerce.productListViews.id`
   * **Produktansichten**: `xdm.commerce.productViews.id`

Wenn Sie die Metrik Bestellungen deduplizieren möchten, lesen Sie den Abschnitt `duplicate_purchase`.

+++

+++**`exclude_hit`**

Markierung, die bestimmt, ob der Treffer aus dem Reporting ausgeschlossen wird. Die Spalte `visit_num` wird bei ausgenommenen Hits nicht erhöht.

Customer Journey Analytics berücksichtigt „ausgeschlossene Treffer“ nicht standardmäßig. Sie können diese Funktion jedoch neu erstellen, wenn Sie über ein XDM-Feld verfügen, das bestimmte Treffer kennzeichnet, die ausgeschlossen werden sollen:

1. Stellen Sie sicher, dass das XDM-Feld, das ausgeschlossene Treffer kennzeichnet, als Komponente enthalten ist (Dimension oder Metrik, je nachdem, wie Sie dieses Flag eingerichtet haben). Die Auswahl [Komponente in Berichten ausblenden](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/overview) ist wahrscheinlich für dieses Feld von Vorteil.
1. Wählen [&#x200B; in den Einstellungen &#x200B;](/help/data-views/session-settings.md) Datenansicht das Dropdown-Menü **[!UICONTROL Segment hinzufügen]** und wählen Sie **[!UICONTROL Segment erstellen]**.
1. Erstellen Sie ein Segment, das alle Ereignisse ausschließt, bei denen die Ausschlusstrefferkomponente vorhanden ist oder Werte enthält, die ausgeschlossen werden sollen.
1. Wählen **[!UICONTROL sowohl]** Segment als auch in der Datenansicht „Speichern“ aus.

Ausgeschlossene Treffer sind jetzt nicht in Customer Journey Analytics-Berichten vorhanden, aber weiterhin in Daten-Feed-Exporten verfügbar.

+++

+++**`first_hit_pagename`**

Die ursprüngliche Dimension der Einstiegsseite. Der Name der ursprünglichen Entrypage des Besuchers.

+++

+++**`first_hit_page_url`**

Die allererste URL des Besuchers.

+++

+++**`first_hit_referrer`**

Die allererste verweisende URL des Besuchers.

+++

+++**`first_hit_ref_domain`**

Die Dimension Ursprünglich verweisende Domain . Basierend auf `first_hit_referrer`. Die allererste verweisende Domain des Besuchers.

+++

+++**`first_hit_ref_type`**

Eine numerische ID, die den Referrer-Typ des allerersten Referrers des Besuchers darstellt.

{{cja-df-lookup}}

+++

+++**`first_hit_time_gmt`**

Zeitstempel des allerersten Treffers der Besucherin oder des Besuchers in UNIX®-Zeit.

+++

+++**`geo_city`**

Name der Stadt, aus der der Treffer stammt, basierend auf der IP-Adresse. Wird in der Dimension Städte verwendet.

+++

+++**`geo_country`**

Abkürzung für das Land, aus dem der Treffer stammt, basierend auf der IP-Adresse. Wird in der Dimension Länder verwendet.

+++

+++**`geo_dma`**

Numerische ID des demografischen Bereichs, aus dem der Treffer stammt, basierend auf der IP-Adresse. Wird in der US-DMA-Dimension verwendet.

+++

+++**`geo_region`**

Name des Bundeslands oder der Region des Treffers, basierend auf der IP-Adresse. Wird in der Dimension Regionen verwendet.

+++

+++**`geo_zip`**

Die Postleitzahl, von der der Treffer stammt, basierend auf der IP. Hilft beim Ausfüllen der Dimension Postleitzahl . Siehe auch `zip`.

+++

+++**`hitid_high`**

Wird mit `hitid_low` zur Identifizierung eines Treffers verwendet.

+++

+++**`hitid_low`**

Wird mit `hitid_high` zur Identifizierung eines Treffers verwendet.

+++

+++**`hit_source`**

Quelle, aus der der Treffer stammt. Die Trefferquellen 1 und 2 werden in Rechnung gestellt. <br>1: Standardbildanforderung ohne Zeitstempel <br>2: Standardbildanforderung mit Zeitstempel <br>3: Live-Datenquellen-Upload mit Zeitstempeln <br>4: Nicht verwendet <br>5: Generischer Datenquellen-Upload <br>6: Nicht mehr verwendet; Full Processing Data Source Upload <br>7: TransactionID Data Source Upload <br>8: Nicht mehr verwendet; Frühere Versionen von Adobe Advertising Data Sources <br>9: Nicht mehr verwendet; Adobe Social-Zusammenfassungsmetriken <br>10: Server-seitige Weiterleitung von Audience Manager verwendet

+++

+++**`hit_time_gmt`**

Der Zeitstempel des Zeitpunkts, wo der Adobe-Datenerfassungs-Server den Treffer erhielt, basierend auf der UNIX®-Zeit.

+++

+++**`hourly_visitor`**

Markierung, die bestimmt, ob es sich bei dem Treffer um eine neue stündliche Besucherin oder einen neuen stündlichen Besucher handelt.

+++

+++**`ip`**

IPv4-Adresse basierend auf der HTTP-Kopfzeile der Bildanforderung. Sich gegenseitig ausschließend für `ipv6`; wenn diese Spalte eine nicht verschleierte IP-Adresse enthält, ist `ipv6` leer.

+++

+++**`ipv6`**

Die komprimierte IPv6-Adresse, falls verfügbar. Sich gegenseitig ausschließend für `ip`; wenn diese Spalte eine nicht verschleierte IP-Adresse enthält, ist `ip` leer.

+++

+++**`javascript`**

Eine Lookup-ID der JavaScript-Version, basierend auf `j_jscript`.

{{cja-df-lookup}}

+++

+++**`java_enabled`**

Die Dimension Java enabled . <br>Y: Aktiviert <br>N: Deaktiviert <br>U: Unbekannt

{{cja-df-post}}

+++

+++**`j_jscript`**

Vom Browser unterstützte JavaScript-Version.

+++

+++**`language`**

Eine numerische ID, die die Sprache des Besuchers darstellt.

{{cja-df-lookup}}

+++

+++**`last_hit_time_gmt`**

Zeitstempel (in UNIX®-Zeit) des vorherigen Treffers. Wird zur Berechnung der Dimension Tage seit dem letzten Besuch verwendet.

+++

+++**`last_purchase_num`**

Die Dimension Kundenloyalität . Die Anzahl der vorherigen Käufe des Besuchers. <br>0: Keine vorherigen Käufe (kein Kunde) <br>1: 1 vorheriger Kauf (neuer Kunde) <br>2: 2 vorherige Käufe (Bestandskunde) <br>3: 3 oder mehr vorherige Käufe (treuer Kunde)

+++

+++**`last_purchase_time_gmt`**

Wird in der Dimension Tage seit letztem Kauf verwendet. Zeitstempel (in UNIX®-Zeit) des letzten Kaufs. Bei Erstkäufen und Besuchern, die zuvor noch nichts gekauft haben, ist dieser Wert `0`.

+++

+++**`latlon1`**

Standort (bis 10 km)

+++

+++**`latlon23`**

Standort (bis 100 m)

+++

+++**`latlon45`**

Standort (bis 1 m)

+++

+++**`mcvisid`**

Experience Cloud-Besucher-ID. 128-Bit-Zahl bestehend aus zwei verketteten 64-Bit-Zahlen verteilt auf 19 Ziffern.

+++

+++**`mc_audiences`**

Liste der Segment-IDs von Audience Manager, zu denen der Besucher gehört. Die Spalte `post_mc_audiences` ändert das Trennzeichen in `--**--`.

{{cja-df-post}}

+++

+++**`mobileaction`**

Mobile Aktion. Wird automatisch erfasst, wenn in mobilen Implementierungen `trackAction` aufgerufen wird. Ermöglicht automatisches Action Pathing in der App.

{{cja-df-post}}

+++

+++**`mobileappid`**

ID der Mobile App. Speichert den Namen und die Version der App im folgenden Format: `[AppName] [BundleVersion]`. 

`xdm.application.name` + `xdm.application.version`

{{cja-df-post}}

+++

+++**`mobileappperformanceappid`**

Wird im Apteligent-Daten-Connector verwendet. Die in Apteligent verwendete App-ID.

+++

+++**`mobileappperformancecrashid`**

Wird im Apteligent-Daten-Connector verwendet. Die in Apteligent verwendete Absturz-ID.

+++

+++**`mobileappstoreobjectid`**

Wird im [!DNL Appfigures]-Daten-Connector verwendet. App Store-Objekt-ID.

+++

+++**`mobilebeaconmajor`**

Mobile Services – Haupt-Beacon

+++

+++**`mobilebeaconminor`**

Mobile Services – Neben-Beacon

+++

+++**`mobilebeaconproximity`**

Mobile Services – Beacon-Nähe

+++

+++**`mobilebeaconuuid`**

Mobile Services-Beacon UUID

+++

+++**`mobilecampaigncontent`**

Der Name oder die ID des Inhalts, der den Link angezeigt hat. Erfasst durch App-Akquise.

{{cja-df-post}}

+++

+++**`mobilecampaignmedium`**

Marketing-Medium, z. B. ein Banner oder eine E-Mail. Erfasst durch App-Akquise.

{{cja-df-post}}

+++

+++**`mobilecampaignname`**

Name der Kampagne, der zusätzlich in der Kampagnenvariable gespeichert wird. Erfasst durch App-Akquise.

{{cja-df-post}}

+++

+++**`mobilecampaignsource`**

Ursprünglicher Referrer, z. B. ein Newsletter oder ein Social Media-Netzwerk. Erfasst durch App-Akquise.

{{cja-df-post}}

+++

+++**`mobilecampaignterm`**

Bezahlte Suchbegriffe oder andere Begriffe, die Sie mit dieser Akquise verfolgen möchten. Erfasst durch App-Akquise.

{{cja-df-post}}

+++

+++**`mobiledayofweek`**

Nummer des Wochentags, an dem die App gestartet wurde.

{{cja-df-post}}

+++

+++**`mobiledayssincefirstuse`**

Anzahl der Tage, die seit dem ersten Ausführen der App vergangen sind.

{{cja-df-post}}

+++

+++**`mobiledayssincelastuse`**

Anzahl der Tage, die vergangen sind, seitdem die App das letzte Mal ausgeführt wurde.

{{cja-df-post}}

+++

+++**`mobiledeeplinkid`**

Erfasst mit der Kontextdatenvariablen `a.deeplink.id`. Wird in Akquise-Berichten als Identifikator für mobilen Akquise-Link verwendet.

+++

+++**`mobiledevice`**

Mobilgerätname. Unter iOS als kommagetrennte 2-Ziffern-Zeichenfolge gespeichert. Die erste Ziffer steht für die Gerätegeneration, die zweite für die Gerätefamilie.

{{cja-df-post}}

+++

+++**`mobilehourofday`**

Gibt die Stunde des Tages an, zu der die App gestartet wurde. Angaben im 24-Stunden-Format.

{{cja-df-post}}

+++

+++**`mobileinstalldate`**

Installationsdatum der Mobile App. Stellt das Datum zur Verfügung, an dem eine Person die Mobile App erstmalig geöffnet hat.

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilelaunchnumber`**

Wird immer dann erhöht, wenn die Mobile App gestartet wird.

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilemessagebuttonname`**

Erfasst mit der Kontextdatenvariablen `a.message.button.id`. Wird für In-App-Nachrichten verwendet, um die Schaltfläche zu identifizieren, mit der die Nachricht geschlossen wurde.

{{cja-df-post}}

+++

+++**`mobilemessageid`**

In-App-Nachrichten-ID

{{cja-df-post}}

+++

+++**`mobilemessageonline`**

In-App-Online-Nachricht

{{cja-df-post}}

+++

+++**`mobilemessagepushoptin`**

Erfasst mit der Kontextdatenvariablen `a.push.optin`. Setzen Sie sie auf „true“, wenn sich der Benutzer für Push-Nachrichten anmeldet; andernfalls ist der Wert „false“.

{{cja-df-post}}

+++

+++**`mobilemessagepushpayloadid`**

Erfasst mit der Kontextdatenvariablen `a.push.payloadid`. Wird in Push-Nachrichten als Payload-ID verwendet.

{{cja-df-post}}

+++

+++**`mobileosversion`**

Betriebssystemversion der Mobile Services

{{cja-df-post}}

+++

+++**`mobileplaceaccuracy`**

Erfasst mit der Kontextdatenvariablen `a.loc.acc`. Gibt die Genauigkeit des GPS in Metern zum Erfassungszeitpunkt an.

+++

+++**`mobileplacecategory`**

Erfasst mit der Kontextdatenvariablen `a.loc.category`. Beschreibt die Kategorie eines bestimmten Orts.

+++

+++**`mobileplaceid`**

Erfasst mit der Kontextdatenvariablen `a.loc.id`. Kennung für einen bestimmten Zielpunkt.

+++

+++**`mobilepushoptin`**

Mobile Services-Push-Opt-in

{{cja-df-post}}

+++

+++**`mobilepushpayloadid`**

Mobile Services-Push-Payload-ID

{{cja-df-post}}

+++

+++**`mobilerelaunchcampaigncontent`**

Startinhalte für Mobile Services

+++

+++**`mobilerelaunchcampaignmedium`**

Startmedium für Mobile Services

+++

+++**`mobilerelaunchcampaignsource`**

Startquelle für Mobile Services

+++

+++**`mobilerelaunchcampaignterm`**

Startbedingung für Mobile Services

+++

+++**`mobilerelaunchcampaigntrackingcode`**

Erfasst mit der Kontextdatenvariablen `a.launch.campaign.trackingcode`. Wird bei der Akquise als Trackingcode für die Startkampagne verwendet.

+++

+++**`mobileresolution`**

Auflösung des Mobilgeräts. `[Width] x [Height]` in Pixel.

{{cja-df-post}}

+++

+++**`mobile_id`**
Die numerische Geräte-ID, wenn der Benutzer ein Mobilgerät verwendet.

{{cja-df-lookup}}

+++

+++**`monthly_visitor`**

Markierung, die bestimmt, ob die Besucherin oder der Besucher im aktuellen Monat eindeutig ist.

+++

+++**`mvvar1`** – **`mvvar3`**

Listenvariablenwerte. Enthält eine durch Trennzeichen getrennte Liste benutzerdefinierter Werte in Abhängigkeit von der Implementierung. Die Spalten `post_mvvar1` - `post_mvvar3` ersetzen das ursprüngliche Trennzeichen durch `--**--`.

{{cja-df-post}}

+++

+++**`mvvar1_instances`** – **`mvvar3_instances`**

Die Werte der Listenvariablen, die beim aktuellen Treffer festgelegt wurden. Ersetzt das ursprüngliche Trennzeichen durch `--**--`. Die Spalten `post` enthalten normalerweise keine Daten.

{{cja-df-post}}

+++

+++**`new_visit`**

Markierung, die bestimmt, ob es sich bei dem aktuellen Treffer um einen neuen Besuch handelt. Wird von Adobe nach 30-minütiger Inaktivität während eines Besuchs festgelegt.

+++

+++**`os`**

Numerische ID, die das Betriebssystem der oder des Besuchenden darstellt. Basierend auf der Spalte `user_agent`.

{{cja-df-lookup}}

Beim [Konfigurieren eines Datenstroms](https://experienceleague.adobe.com/de/docs/experience-platform/datastreams/configure) können Sie die **[!UICONTROL Gerätesuche“]**. Aktivieren Sie das Kontrollkästchen **[!UICONTROL Betriebssystem]**, falls aktiviert. Dadurch werden automatisch die folgenden XDM-Felder ausgefüllt, wenn Sie diese Felder in Ihr Schema aufgenommen haben:

* **Betriebssystemanbieter**: `xdm.environment.operatingSystemVendor`
* **Betriebssystemname**: `xdm.environment.operatingSystem`
* **Betriebssystemversion**: `xdm.environment.operatingSystemVersion`

{{cja-df-ua}}

+++

+++**`pagename`**

Die Dimension Seite . Wenn die Variable `pagename` leer ist, verwendet Analytics stattdessen `page_url`.

{{cja-df-post}}

+++

+++**`pagename_no_url`**

Ähnlich wie `pagename`, allerdings ohne Fallback auf `page_url`. Nur die Spalte `post` ist verfügbar.

{{cja-df-post}}

+++

+++**`page_event`**

Der Typ des Treffers, der in der Bildanforderung gesendet wird (Standardtreffer, Downloadlink, benutzerspezifischer Link, Exitlink).

{{cja-df-post}}

{{cja-df-lookup}}

+++

+++**`page_event_var1`**

Wird nur bei Bildanforderungen für Linktracking verwendet. Die URL des angeklickten Downloadlinks, Exitlinks oder benutzerspezifischen Links.

{{cja-df-post}}

+++

+++**`page_event_var2`**

Wird nur bei Bildanforderungen für Linktracking verwendet. Benutzerdefinierter Name des Links (falls angegeben). Legt den benutzerspezifischen Link, den Downloadlink oder den Exitlink abhängig vom Wert in `page_event` fest.

{{cja-df-post}}

+++

+++**`page_type`**

Die Dimension Seiten nicht gefunden , die normalerweise für 404 Seiten verwendet wird.

{{cja-df-post}}

+++

+++**`page_url`**

**`page_url`**: Die URL des Treffers. Verwendet einen Datentyp von Text.<br>**`post_page_url`**: Für Bildanforderungen zum Linktracking entfernt (`tl()`).

{{cja-df-post}}

+++

+++**`paid_search`**

Markierung, die bestimmt, ob der Treffer mit Paid-Search-Erkennung übereinstimmt.

+++

+++**`persistent_cookie`**

Wird in der Dimension Unterstützung persistenter Cookies verwendet. Gibt an, ob der Benutzer Cookies unterstützt, die nicht nach jedem Treffer gelöscht werden.

{{cja-df-post}}

+++

+++**`pointofinterest`**

Name des Mobile Services-Zielpunkts

{{cja-df-post}}

+++

+++**`pointofinterestdistance`**

Entfernung der Mobile Services zur Zielpunktmitte

{{cja-df-post}}

+++

+++**`product_list`**

Seitenvariable `products`. Hilft beim Ausfüllen verschiedener Dimensionen und Metriken, einschließlich Kategorie, Produkt, Einheiten und Umsatz.

{{cja-df-post}}

+++

+++**`prop1`** – **`prop75`**

Benutzerdefinierte Traffic-Variablen 1 bis 75. Wird in Propenabmessungen verwendet.

{{cja-df-post}}

+++

+++**`purchaseid`**

Eindeutige Kennung für einen Kauf, so wie durch das Festlegen der Variable `purchaseID` bestimmt. Von der Spalte `duplicate_purchase` verwendet.

`xdm.commerce.order.purchaseID`

{{cja-df-post}}

+++

+++**`quarterly_visitor`**

Markierung, die bestimmt, ob es sich bei dem Treffer um eine neue Quartals-Besucherin oder einen neuen Quartals-Besucher handelt.

+++

+++**`referrer`**

Die Dimension Referrer . Beachten Sie, dass während `referrer` einen Datentyp von varchar(255) verwendet, `post_referrer` einen Datentyp von varchar(244) verwendet.

{{cja-df-post}}

+++

+++**`ref_domain`**

Die Dimension Referrer Domain . Basierend auf der Spalte `referrer`.

+++

+++**`ref_type`**


Numerische ID, die den Referenztyp für den Treffer darstellt. Wird in der Dimension Referrer-Typ verwendet.<br>1: Innerhalb der Website<br>2: Andere Websites<br>3: Suchmaschinen<br>4: Festplatte<br>5: USENET<br>6: Eingegeben/Mit Lesezeichen versehen (kein Referrer)<br>7: E-Mail<br>8: Kein JavaScript<br>9: Soziale Netzwerke<br>10: Konversationelle KI-Tools

+++

+++**`resolution`**

Numerische ID, die die Auflösung des Bildschirms darstellt. Wird in der Dimension Monitor Resolution verwendet.

{{cja-df-lookup}}

+++

+++**`search_engine`**

Numerische ID, die die Suchmaschine darstellt, über die die Besucherin oder der Besucher auf Ihre Site gelangt ist. Wird in Suchmaschinendimensionen verwendet.

{{cja-df-post}}

{{cja-df-lookup}}

+++

+++**`search_page_num`**

Wird von der Dimension „Rangansicht aller Suchseiten“ verwendet. Gibt an, auf welcher Seite der Suchergebnisse Ihre Site angezeigt wurde, ehe die Person sich zu Ihrer Site durchgeklickt hat.

+++

+++**`secondary_hit`**

Markierung, die bestimmt, ob der Treffer ein sekundärer Treffer ist. Diese Markierung stammt normalerweise aus dem Multi-Suite-Tagging und aus VISTA-Regeln, die Treffer kopieren.

+++

+++**`sourceid`**

Quell-ID

+++

+++**`stats_server`**

Nicht verwendet. Interner Adobe-Server, der den Treffer verarbeitet hat.

+++

+++**`s_kwcid`**

Die Keyword-ID, die in Adobe Advertising-Integrationen verwendet wird.

{{cja-df-post}}

+++

+++**`s_resolution`**

Rohwert der Bildschirmauflösung. Erfasst mit der JavaScript-Funktion `screen.width x screen.height`.

+++

+++**`tnt`**

Wird in Adobe Target-Integrationen verwendet. Stellt alle Tests dar, für die er derzeit qualifiziert ist. Das Format ist: `TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`.

{{cja-df-post}}

+++

+++**`tnt_action`**

Wird in Adobe Target-Integrationen verwendet. Stellt alle Tests dar, für die der Treffer qualifiziert ist.

{{cja-df-post}}

+++

+++**`tnt_instances`**

Wird in Adobe Target-Integrationen verwendet. Target-Instanzvariable.

+++

+++**`transactionid`**

Eine eindeutige Kennung, bei der verschiedene Datenpunkte später über Datenquellen hochgeladen werden können. Erfasst mithilfe der Variablen `transactionID`.

`xdm.commerce.order.payments[0].transactionID`

{{cja-df-post}}

+++

+++**`truncated_hit`**

Eine Markierung, die angibt, dass die Bildanforderung abgeschnitten wurde (ein Teiltreffer wurde empfangen). <br>Y: Treffer abgeschnitten; Teiltreffer erhalten <br>N: Treffer nicht abgeschnitten; vollständigen Treffer erhalten

+++

+++**`t_time_info`**

Lokale Zeit des Besuchers. Das Format ist: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)`

{{cja-df-post}}

+++

+++**`userid`**

Nicht verwendet. Die numerische ID für die Report Suite-ID. Verwenden Sie stattdessen `username`.

+++

+++**`username`**

Die Report Suite-ID für den Treffer.

+++

+++**`user_agent`**

Benutzeragenten-Zeichenfolge, die im HTTP-Header der Bildanforderung gesendet wird.

+++

+++**`user_hash`**

Nicht verwendet. Hash der Report Suite-ID. Verwenden Sie stattdessen `username`.

+++

+++**`user_server`**

Wird in der Dimension Server verwendet.

{{cja-df-post}}

+++

+++**`va_closer_detail`**

Die Dimension Detail des Letztkontakts.

+++

+++**`va_closer_id`**

Eine numerische ID, die die Dimension Letztkontakt-Kanal identifiziert.

{{cja-df-lookup}}

+++

+++**`va_finder_detail`**

Die Dimension Erstkontakt-Detail .

+++

+++**`va_finder_id`**

Eine numerische ID, die die Dimension „Erstkontakt-Kanal“ identifiziert.

{{cja-df-lookup}}

+++

+++**`va_instance_event`**

Eine Markierung, die Marketing-Kanal-Instanzen identifiziert.

+++

+++**`va_new_engagement`**

Eine Markierung, die neue Interaktionen für Marketing-Kanäle identifiziert.

+++

+++**`video`**

Die Dimension Services für Inhalts-Streaming-Medien .

{{cja-df-post}}

+++

+++**`videoad`**

Die Dimension Services für Anzeigen-Streaming-Medien .

{{cja-df-post}}

+++

+++**`videoadinpod`**

Die Dimension In-Pod-Position der Streaming-Medien-Services .

{{cja-df-post}}

+++

+++**`videoadlength`**

Die Dimension Anzeigenlänge (Variable) für Streaming-Medien-Services .

{{cja-df-post}}

+++

+++**`videoadname`**

Die Dimension Anzeigename (Variable) für Streaming-Medien-Services .

{{cja-df-post}}

+++

+++**`videoadplayername`**

Die Dimension Player-Name für Streaming-Mediendienste .

{{cja-df-post}}

+++

+++**`videoadpod`**

Die Dimension Pod-Streaming-Mediendienste .

{{cja-df-post}}

+++

+++**`videoadvertiser`**

Die Dimension Advertiser-Streaming-Mediendienste .

{{cja-df-post}}

+++

+++**`videoaudioalbum`**

Die Dimension Album-Streaming-Mediendienste .

+++

+++**`videoaudioartist`**

Die Dimension Künstler-Streaming-Mediendienste .

+++

+++**`videoaudioauthor`**

Die Dimension Streaming-Mediendienste erstellen .

+++

+++**`videoaudiolabel`**

Die Dimension Streaming-Mediendienste beschriften .

+++

+++**`videoaudiopublisher`**

Die Dimension Publisher-Streaming-Mediendienste .

+++

+++**`videoaudiostation`**

Die Dimension Stations-Streaming-Mediendienste .

+++

+++**`videocampaign`**

Die Dimension Kampagnen-ID Streaming-Mediendienste .

{{cja-df-post}}

+++

+++**`videochannel`**

Die Dimension Inhaltskanal-Streaming-Medien-Services .

{{cja-df-post}}

+++

+++**`videochapter`**

Die Dimension Kapitel Streaming-Mediendienste .

{{cja-df-post}}

+++

+++**`videocontenttype`**

Die Dimension Inhaltstyp-Streaming-Medien-Services .

{{cja-df-post}}

+++

+++**`videodaypart`**

Die Dimension Day-Teil-Streaming-Mediendienste .

{{cja-df-post}}

+++

+++**`videoepisode`**

Die Dimension Streaming-Mediendienste der Folge.

{{cja-df-post}}

+++

+++**`videofeedtype`**

Die Dimension Medien-Feed-Typ Streaming-Medien-Services .

{{cja-df-post}}

+++

+++**`videogenre`**

Die Dimension Genre-Streaming-Mediendienste . Diese Dimension erlaubt mehrere Werte im selben Treffer, getrennt durch ein Komma.

{{cja-df-post}}

+++

+++**`videolength`**

Die Dimension Inhaltslänge (Variable) für Streaming-Medien-Services .

{{cja-df-post}}

+++

+++**`videomvpd`**

Die Dimension MVPD-Streaming-Mediendienste .

{{cja-df-post}}

+++

+++**`videoname`**

Die Dimension Inhaltsname (Variable) für Streaming-Medien-Services .

{{cja-df-post}}

+++

+++**`videonetwork`**

Die Dimension Netzwerk-Streaming-Mediendienste .

{{cja-df-post}}

+++

+++**`videopath`**

Die Dimension Medienpfad - Streaming-Mediendienste .

{{cja-df-post}}

+++

+++**`videoplayername`**

Die Dimension Name des Content-Players für Streaming-Medien-Services .

{{cja-df-post}}

+++

+++**`videoqoebitrateaverageevar`**

Die Dimension Durchschnittliche Bitrate für Streaming-Medien-Services .

{{cja-df-post}}

+++

+++**`videoqoebitratechangecountevar`**

Die Bitrate ändert die Dimension Streaming-Mediendienste .

{{cja-df-post}}

+++

+++**`videoqoebuffercountevar`**

Die Dimension Pufferereignisse für Streaming-Mediendienste .

{{cja-df-post}}

+++

+++**`videoqoebuffertimeevar`**

Die Dimension Gesamtdauer der Pufferung für Streaming-Mediendienste.

{{cja-df-post}}

+++

+++**`videoqoedroppedframecountevar`**

Die Dimension Abgelegte Frames Streaming-Mediendienste .

{{cja-df-post}}

+++

+++**`videoqoeerrorcountevar`**

Die Dimension Fehler bei Streaming-Mediendiensten .

+++
{{cja-df-post}}


+++**`videoqoeextneralerrors`**

Die Dimension Externe Fehler-IDs Streaming-Mediendienste . Diese Dimension erlaubt mehrere Werte im selben Treffer.

+++

+++**`videoqoeplayersdkerrors`**

Die Dimension Player-SDK-Fehler-IDs Streaming-Mediendienste . Diese Dimension erlaubt mehrere Werte im selben Treffer.

{{cja-df-post}}

+++

+++**`videoqoetimetostartevar`**

Die Dimension Zeit zum Starten von Streaming-Mediendiensten .

{{cja-df-post}}

+++

+++**`videoseason`**

Die Dimension Staffel der Streaming-Mediendienste .

{{cja-df-post}}

+++

+++**`videosegment`**

Die Dimension Inhaltssegment-Streaming-Medien-Services .

{{cja-df-post}}

+++

+++**`videosessionid`**

Die Dimension Mediensitzungs-ID für Streaming-Mediendienste .

{{cja-df-post}}

+++

+++**`videoshow`**

Die Dimension Streaming-Mediendienste anzeigen .

{{cja-df-post}}

+++

+++**`videoshowtype`**

Die Dimension Sendungstyp Streaming-Medien-Services .

{{cja-df-post}}

+++

+++**`videostreamtype`**

Die Dimension Stream-Typ Streaming-Medien-Services .

+++

+++**`visid_high`**

Wird mit `visid_low` zur eindeutigen Identifizierung von Besuchenden verwendet.

{{cja-df-post}}

+++

+++**`visid_low`**

Wird mit `visid_high` zur eindeutigen Identifizierung von Besuchenden verwendet.

{{cja-df-post}}

+++

+++**`visid_new`**

Markierung, die bestimmt, ob der Treffer eine neu generierte Besucher-ID enthält.

+++

+++**`visid_timestamp`**

Wurde eine Besucher-ID neu generiert, wird der Zeitstempel (in UNIX®-Zeit) der Generierung der Besucher-ID bereitgestellt.

+++

+++**`visid_type`**

Nicht zur externen Verwendung; intern von Adobe für Verarbeitungsoptimierungen verwendet. Numerische ID, die die Methode zur Identifizierung der oder des Besuchenden darstellt.<br>`0`: Benutzerspezifische Besucher-ID oder unbekannt/nicht anwendbar<br>`1`: IP- und Benutzeragenten-Fallback<br>`2`: HTTP-Kopfzeile mobiler Teilnehmer <br>`3`: Alter Cookie-Wert (`s_vi`) <br>`4`: Fallback-Cookie-Wert (`s_fid`) <br>`5`: Identity Service

{{cja-df-post}}

+++

+++**`visit_keywords`**

Die Suchbegriffdimension. Diese Spalte verwendet eine nicht standardmäßige Zeichenbeschränkung von varchar(244), um die von Adobe verwendete Backend-Logik zu berücksichtigen. Die nachbearbeitete Spalte ist `**post_keywords**`, nicht `**post_visit_keywords**`.

{{cja-df-post}}

+++

+++**`visit_num`**

Die Dimension Besuchsnummer . Beginnt bei 1 und erhöht sich bei jedem neuen Besuch eines Besuchers.

+++

+++**`visit_page_num`**

Die Dimension Treffertiefe . Erhöht sich um 1 für jeden von Besuchenden generierten Treffer. Setzt jeden Besuch zurück.

+++

+++**`visit_referrer`**

Die erste verweisende Stelle des Besuchs.

+++

+++**`visit_ref_domain`**

Basierend auf der Spalte `visit_referrer`. Die allererste verweisende Domain des Besuchs.

+++

+++**`visit_ref_type`**

Eine numerische ID, die den Referrer-Typ des ersten Referrers des Besuchs darstellt.

{{cja-df-lookup}}

+++

+++**`visit_search_engine`**

Eine numerische ID, die die erste Suchmaschine des Besuchs darstellt.

{{cja-df-lookup}}

+++

+++**`visit_start_pagename`**

Seite des ersten Treffers des Besuchs.

+++

+++**`visit_start_page_url`**

URL des ersten Treffers des Besuchs.

+++

+++**`visit_start_time_gmt`**

Zeitstempel (in UNIX®-Zeit) des ersten Treffers des Besuchs.

+++

+++**`weekly_visitor`**

Markierung, die bestimmt, ob es sich bei dem Treffer um eine neue wöchentliche Besucherin oder einen neuen wöchentlichen Besucher handelt.

+++

+++**`yearly_visitor`**

Markierung, die bestimmt, ob es sich bei dem Treffer um eine neue jährliche Besucherin oder einen neuen jährlichen Besucher handelt.

+++

+++**`zip`**

Hilft beim Ausfüllen der Dimension Postleitzahl . Siehe auch `geo_zip`.

{{cja-df-post}}

+++
