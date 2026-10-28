---
title: Paid-Media-Daten mit Web-Daten in Customer Journey Analytics verbinden
description: Daten der Paid Media-Zusammenfassung mit Website-Ereignissen in Adobe Customer Journey Analytics verbinden, um Anzeigenausgaben, Klicks, Bestellungen, Umsatz und den Ertrag der Anzeigenausgaben zu vergleichen.
solution: Customer Journey Analytics
feature: Use Cases
hide: true
role: Admin
source-git-commit: 11bc93e0adabd8e8109bda1734e1a098ce8bef1e
workflow-type: tm+mt
source-wordcount: '3907'
ht-degree: 3%
---
# Paid-Media-Daten mit Web-Daten verbinden

Dieses Anwendungsbeispiel veranschaulicht, wie Sie in [!DNL Adobe Customer Journey Analytics] Daten über Zusammenfassungen bezahlter Medien mit Ereignisdaten über das Verhalten einer Website verbinden können.


Durch das Verbinden Ihrer Werbekonten (Meta, Google Ads und andere) mit Experience Platform erhalten Sie zusammengefasste Paid-Media-Daten in Customer Journey Analytics: tägliche Impressionen, Klicks, Ausgaben und über das Anzeigennetzwerk berichtete Konversionen pro Konto, Kampagne, Anzeigengruppe, Anzeige, Erlebnis und Asset. Mit Customer Journey Analytics erfassen Sie Ihre eigenen verhaltensbezogenen Ereignisdaten auf der Site mit der Web-SDK: Seitenansichten, Bestellungen, Umsatz.

Wenn Sie die beiden Datentypen in einer einzigen Workspace-Freiformtabelle verbinden, können Sie die Anzeigenleistung mit der Aktivität auf Ihrer Website vergleichen. Verwenden Sie freigegebene Kampagnen-, Anzeigengruppen- und Anzeigenkennungen, um Berichte zu Impressionen, Klicks und Ausgaben zusammen mit bezahlten Landingpages, Bestellungen und Umsatz in [!DNL Analysis Workspace] zu erstellen.

| Datenquelle | Beispielmetriken |
|---|---|
| Zusammenfassungsdaten zu bezahlten Medien | Vom Werbenetzwerk gemeldete Impressionen, Klicks, Ausgaben, Konversionen und Konversionswerte. |
| Verhaltensereignisse der Website | Bezahlte Landingpages, Seitenansichten, Bestellungen und Umsatz gemessen auf Ihrer Website |
| Berechnete Metriken | Landingpage-Rate, Web-Konversionsrate, Web-Rendite auf Werbeausgaben, Kosten pro Webbestellung und Netzwerk-/Web-Konversionslücke |

Die Kombination dieser beiden Datentypen ermöglicht es Ihnen, Daten vor einem Klick (aus Ihren Anzeigen) und Daten nach einem Klick (aus Ihrer Website) zu vergleichen.

In diesem Handbuch werden Szenarien für Verbindungen behandelt, die von [!DNL Adobe Content Analytics] Konfigurationen und von Ihnen selbst konfigurierten Verbindungen verwaltet werden.

## Funktionsweise

Die folgende Abbildung zeigt, wie Zusammenfassungsdaten von bezahlten Medien und Verhaltensereignisdaten von Websites über eine Customer Journey Analytics-Verbindung aufgenommen werden.

Die Datenansicht ist für das Analysieren und Ausrichten der Daten verantwortlich, sodass Sie Workspace verwenden können, um ordnungsgemäß Berichte über die Daten zu erstellen.

![Paid Media-Joins](./assets/paid-media-web-join.png){zoomable="yes"}

Paid-Media-Zusammenfassungsdatensätze enthalten tägliche Metriken ohne Personen-ID. Website-Ereignis-Datensätze enthalten Verhaltensereignisse mit Zeitstempel und eine Personenkennung. Eine Zusammenfassungsdatengruppe verknüpft Dimensionen aus diesen Datensätzen, sodass gleiche Dimensionswerte in derselben Berichtszeile angezeigt werden.

>[!IMPORTANT]
>
>Dieser Join richtet aggregierte Zusammenfassungsdaten und Web-Ereignisse für das Reporting aus. Es verknüpft keine Ad-Impression oder Klick mit einer einzelnen Person. Anzeigennetzwerk-Konversionen behalten die Berichtsmethode des Netzwerks bei. Bestellungen und Umsatz von Websites verwenden die Attributionseinstellungen, die Sie in diesem Handbuch konfigurieren.

## Grundlagen zum Reporting-Join

Eine Verknüpfung ist nur auf Ebenen möglich, deren IDs in den URLs der Landingpage oder in den Feldern für vorhandene Ereignisse angezeigt werden. Beispielsweise unterstützt das Tagging auf Kampagnenebene das Reporting auf Kampagnenebene, nicht jedoch das Reporting auf Anzeigenebene. Joins auf Erlebnis- und Asset-Ebene erfordern zusätzliche URL-Parameter und liegen außerhalb des Rahmens dieses Handbuchs.

Siehe [Zusammenfassungsdaten](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/summary-data) und [Zusammenfassungsdatengruppen-Komponenteneinstellungen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/summary-data-group) als Referenz.

### Join-Schlüssel auswählen

Paid-Media-Datensätze liefern sowohl Netzwerk-IDs als auch von Adobe generierte GUIDs (Globally Unique Identifiers).

| Kennung | Beispiel | Zweck |
|---|---|---|
| Netzwerk-ID | Kampagnen-ID `123456789` | Abgleich einer von einer Landingpage-URL erfassten ID mit einer Paid-Media-Zusammenfassungsdimension |
| GUID | `meta_111111111_123456789` | Identifizieren einer Paid-Media-Entität mithilfe des Netzwerks, Kontos und der Entitätshierarchie |

Die GUID-Struktur ist `{adNetwork}_{accountID}[_{campaignID}[_{adGroupID}[_{adID}]]]`. Bezahlte Medienkomponenten, die von [!DNL Adobe Content Analytics] verwaltet werden, verwenden diese GUIDs.

In diesem Handbuch werden Netzwerk-IDs für Web-Joins verwendet, da die Makros für Kampagnen-, Anzeigengruppen- und Anzeigen-URLs nicht alle Informationen enthalten, die zur Rekonstruktion einer GUID erforderlich sind. Diese Zusammenfassungsfelder verwenden:

| Berichterstellungsebene | Feld Netzwerk-ID | GUID-Feld |
|---|---|---|
| Kampagne | `paidMedia.campaignID` | `paidMedia.campaignGUID` |
| Anzeigengruppe | `paidMedia.adGroupID` | `paidMedia.adGroupGUID` |
| Anzeige | `paidMedia.adID` | `paidMedia.adGUID` |

Das Netzwerkfeld ist `paidMedia.adNetwork`. Beispielwerte sind `meta` und `google_ads`. Abgeleitete Feldausgaben müssen genau mit den Werten in Ihren Datensätzen übereinstimmen.

>[!NOTE]
>
>Eine Zusammenfassungsdatengruppe ordnet Dimensionswerte zu, keine Kombination aller Dimensionen in Ihrer Tabelle. Bestätigen Sie, dass Ihre ausgewählten IDs Entitäten in den Konten und Netzwerken, über die Sie Berichte erstellen, eindeutig identifizieren. Namensbasierte Gruppen können verschiedene Entitäten kombinieren, die einen gemeinsamen Namen haben.

## Voraussetzungen

Vergewissern Sie sich, dass Folgendes vorliegt:

* [!DNL Customer Journey Analytics] Auswählen oder höher mit Zugriff auf die hier verwendeten abgeleiteten Feldfunktionen: [URL Parse](/help/data-views/derived-fields/derived-fields.md#url-parse), [Case When](/help/data-views/derived-fields/derived-fields.md#case-when), [Regex Replace](/help/data-views/derived-fields/derived-fields.md#regex-replace) und [Lookup](/help/data-views/derived-fields/derived-fields.md#lookup).
* [!DNL Adobe Experience Platform] Berechtigungen zum Verwalten von Schemata, Datensätzen und Datenströmen in der Ziel-Sandbox sowie zum Zugriff auf Datensätze und den Abfrage-Service zur Überprüfung.
* [!DNL Customer Journey Analytics] Berechtigung zum Bearbeiten der Zielverbindung und der Datenansicht.
* Paid-Media-Quell-Connectoren, die in derselben Sandbox konfiguriert sind und Zusammenfassungs- und Lookup-Datensätze aufnehmen. Einen Beispiel-Connector finden Sie unter [Meta Ads-Quelle](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/advertising/meta-ads).
* Website-Ereignisse, die die vollständige Landingpage-URL erfassen, einschließlich der Abfragezeichenfolge oder gleichwertiger Felder mit den Netzwerk-IDs.


### Anzeigen-Tagging

Identifizieren Sie die Abfrageparameter, die Ihre Kampagnen-, Anzeigengruppen- und Anzeigen-IDs enthalten. Vorhandenes ID-basiertes Tagging kann ohne Änderungen an den Anzeigenplattformen verwendet werden.

| Tagging-Muster | Kampagnenparameter | Anzeigengruppenparameter | Anzeigenparameter |
|---|---|---|---|
| Meta-IDs in der Website-URL | <code>campaign_id={{campaign.id}}</code> | <code>adset_id={{adset.id}}</code> | <code>ad_id={{ad.id}}</code> |
| Meta-IDs in UTM-Parametern | <code>utm_campaign={{campaign.id}}</code> | <code>utm_term={{adset.id}}</code> | <code>utm_content={{ad.id}}</code> |
| Google Ads-IDs in UTM-Parametern | <code>utm_campaign={campaignid}</code> | <code>utm_term={adgroupid}</code> | <code>utm_content={creative}</code> |

Beim Meta-UTM-Tagging kann ein Quellwert wie `utm_source=fb` das Netzwerk identifizieren. Verwenden Sie für das UTM-Tagging von Google Ads einen Quellwert wie `utm_source=google`.

Einige [!DNL Adobe Advertising] Integrationen verwenden einen `s_kwcid` Wert mit diesem Layout:

```text
AL!<id>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}!{campaignid}!{adgroupid}
```

Die Parsing-Regeln weiter unten in diesem Handbuch gelten nur für dieses Layout. Überprüfen Sie die tatsächlichen Landingpage-URLs, bevor Sie sie verwenden.

Wenn Sie keinen Zugriff auf die Anzeigenplattformen haben, überprüfen Sie die URLs für die Landingpage in Ihrem Web-Datensatz. Sie können auch diese Paid-Media-Suchfelder überprüfen:

* Google Ads-Kontosuche: `additionalDetails` Einträge mit den Namen `google_ads_tracking_url_template` und `google_ads_final_url_suffix`.
* Meta-Anzeigensuche: `paidMedia.adDetails.creative.paidMediaCreative.destinationURL`.

Makros in gespeicherten Ziel-URLs können prozentual kodiert werden. Validieren Sie die erweiterten IDs in tatsächlichen Website-Ereignissen, anstatt davon auszugehen, dass eine gespeicherte URL die endgültige Landing-URL darstellt.

>[!IMPORTANT]
>
>Kampagnennamen, z. B. `utm_campaign=fall_sale`, stimmen nicht mit Kampagnen-IDs überein. Nur auf Ebenen verbinden, die tatsächliche IDs enthalten. Wenn IDs fehlen, wenden Sie sich an Ihr Anzeigenbetriebs-Team, um die Tagging-Kennzeichnung für künftigen Traffic zu aktualisieren. Diese Einrichtung kann keine fehlenden IDs für frühere Besuche rekonstruieren.

### Ausgangspunkt

Öffnen Sie die Datenansicht, die Sie verwenden möchten, und überprüfen Sie die Komponenten, um den Ausgangspunkt zu bestimmen.

| | Ausgangspunkt | Vorhandene Konfiguration | Zu befolgende Schritte |
|---|---|---|---|
| A | Content Analytics mit Web- oder mobilen und bezahlten Medien | Paid-Media-Datensätze und -Komponenten sowie Content Analytics-Ereignis- und Lookup-Datensätze | Fügen Sie bei Bedarf Ihren Website-Ereignis-Datensatz hinzu und konfigurieren Sie dann die aus dem Web abgeleiteten Felder und Berichtsgruppen |
| B | Content Analytics nur mit bezahlten Medien | Paid-Media-Datensätze und -Komponenten; Datensätze für die Suche nach freigegebenen Inhalten können ebenfalls vorhanden sein | Fügen Sie Ihren Website-Ereignis-Datensatz hinzu und konfigurieren Sie dann die aus dem Web abgeleiteten Felder und Berichtsgruppen |
| C | Bezahlte Medien ohne Content Analytics-Bereitstellung | Paid-Media-Datensätze sind in Experience Platform vorhanden, aber die Verbindung und die Datenansicht enthalten nicht die Paid-Media-Konfiguration | Fügen Sie die Website- und Paid-Media-Datensätze hinzu und erstellen Sie dann die Paid-Media- und Web-Komponenten |
| D | Content Analytics ohne bezahlte Medien | Nur Content Analytics-Komponenten | Aktivieren Sie den Paid-Media-Kanal in der Content Analytics-Konfiguration und folgen Sie dann dem Pfad der vorhandenen Konfiguration . |

Entfernen oder ändern Sie keine vom System bereitgestellten Datensätze oder schreibgeschützten Komponenten beim Erweitern einer von Content Analytics verwalteten Verbindung.

## Erfassen von Verhaltensereignissen für Websites

Überspringen Sie die Erstellung von Schemas, Datensätzen und Datenstroms, wenn Ihre Website bereits die erforderlichen Ereignisse an einen in Customer Journey Analytics verwendeten Datensatz sendet. Bestätigen Sie, dass `web.webPageDetails.URL` die Abfragezeichenfolge der Landingpage enthält.

### Erstellen des Schemas und Datensatzes

1. Wählen Sie in Experience Platform die Ziel-Sandbox aus.
1. Gehen Sie zu **[!UICONTROL Daten-Management]** > **[!UICONTROL Schemata]** und wählen Sie **[!UICONTROL Schema erstellen]**.
1. Wählen Sie **[!UICONTROL Manuell]** und die `XDM ExperienceEvent`.
1. Benennen Sie das Schema, z. B. `Web Behavioral Events`.
1. Fügen Sie die für Ihre Implementierung erforderlichen Feldergruppen hinzu.

   | Feldergruppe | Erforderliche Daten |
   |---|---|
   | AEP Web SDK ExperienceEvent | Seiten-URL, Seitenansichten, Referrer und anderer Web-Kontext |
   | Commerce-Details | Bestellanzahl, Bestellwert, Währung, Kauf-ID und Produktdetails |
   | Details zum Kampagnen-Marketing, optional | Trackingcodes, wenn Ihre Implementierung sie separat erfasst |
   | IdentityMap, falls noch nicht vorhanden | Die Personenkennung, z. B. ECID |

1. Speichern Sie das Schema. Für diesen Reporting-Anwendungsfall ist keine Profilaktivierung erforderlich.
1. Wechseln Sie **[!UICONTROL Daten-Management]** > **[!UICONTROL Datensätze]** > **[!UICONTROL Datensatz erstellen]** > **[!UICONTROL Datensatz aus Schema erstellen]**.
1. Wählen Sie das Schema aus und erstellen Sie einen Datensatz mit dem Namen , z. B. `Web Behavioral Events`. Lassen Sie **[!UICONTROL Profil]** deaktiviert, es sei denn, es ist ein anderer Anwendungsfall erforderlich.

### Konfigurieren des Datenstroms und der Web-SDK

1. Navigieren Sie **[!UICONTROL Datenerfassung]** > **[!UICONTROL Datenströme]** > **[!UICONTROL Neuer Datenstrom]**.
1. Benennen Sie den Datenstrom und wählen Sie Ihr Ereignisschema als Zuordnungsschema aus.
1. Speichern Sie und wählen Sie dann **[!UICONTROL Service hinzufügen]** > **[!UICONTROL Adobe Experience Platform]**.
1. Wählen Sie die Sandbox und den Ereignis-Datensatz aus und klicken Sie auf **[!UICONTROL Speichern]**.
1. Verwenden Sie die Datenstrom-ID, um die [Experience Platform Web SDK zu ](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/js-overview).

Folgendes erfassen:

* Erfassen Sie auf jeder Seite eine Seitenansicht, wobei die vollständige URL in `web.webPageDetails.URL` und `web.webPageDetails.pageViews.value` auf `1` festgelegt ist.
* Kaufereignisse mit `commerce.purchases.value`, die auf `1`, plus `commerce.order.priceTotal`, `commerce.order.currencyCode` und `commerce.order.purchaseID` eingestellt sind.
* Eine für Ihre Customer Journey Analytics-Verbindung geeignete Personenkennung.

UTM-Parameter müssen nicht im Website-Code analysiert werden. Die in diesem Handbuch abgeleiteten Felder analysieren URLs zum Zeitpunkt des Berichts. Wenn Ihre Implementierung die IDs bereits in dedizierten Feldern erfasst, verwenden Sie stattdessen diese Felder.

### Aufnahme überprüfen

Überprüfen Sie die Datensatzaktivität auf eine erfolgreiche Aufnahme. Führen Sie im Abfrage-Service die folgende Abfrage aus und ersetzen Sie `web_behavioral_events` durch den SQL-Tabellennamen Ihres Datensatzes:

```sql
SELECT timestamp, eventType, web.webPageDetails.URL
FROM web_behavioral_events
WHERE web.webPageDetails.URL RLIKE '[?&](campaign_id|utm_campaign|s_kwcid)='
ORDER BY timestamp DESC
LIMIT 20;
```

Vergewissern Sie sich, dass die zurückgegebenen URLs erweiterte Netzwerk-IDs enthalten. Wenn bezahlter Traffic vorhanden ist, die Abfrage jedoch keine Zeilen zurückgibt, überprüfen Sie die letzten Landing URLs und passen Sie das Parametermuster an Ihr Tagging an.

## Konfigurieren der Verbindung

Um den Web-Ereignis-Datensatz in Customer Journey Analytics aufzunehmen, müssen Sie den Datensatz zur entsprechenden Verbindung hinzufügen. Dadurch wird sichergestellt, dass die Web-Verhaltensereignisse zusammen mit den Paid-Media-Datensätzen für die Analyse verfügbar sind.

### Hinzufügen des Website-Ereignisdatensatzes

1. Navigieren Sie in Customer Journey Analytics **[!UICONTROL Daten-Management]** > **[!UICONTROL Verbindungen]**.
1. Bearbeiten Sie die Verbindung, die Ihre Paid-Media-Datensätze enthält.
1. Wählen Sie **[!UICONTROL Datensätze hinzufügen]** und wählen Sie den Website-Ereignis-Datensatz aus.
1. Konfigurieren Sie den Datensatz:

   | Einstellung | Wert |
   |---|---|
   | Personen-ID | `identityMap` mit dem ECID-Namespace oder dem Personen-ID-Feld Ihrer Implementierung |
   | Zeitstempel | `timestamp` |
   | Datenquellentyp | Web-Daten |
   | Alle neuen Daten importieren | Aktiviert |
   | Aufstockung aller vorhandenen Daten | Aktiviert für den benötigten historischen Zeitraum |

1. Fügen Sie den Datensatz hinzu und speichern Sie die Verbindung.

### Paid-Media-Datensätze hinzufügen, falls noch nicht konfiguriert

>[!IMPORTANT]
>
>Überspringen Sie diesen Abschnitt für Verbindungen, bei denen Content Analytics Paid-Media-Datensätze verwaltet.


Fügen Sie mindestens die Anzeigenzusammenfassung für bezahlte Medien und die Datensätze Paid Media, Paid Media-Kampagne, Paid Media-Anzeigengruppe und Paid Media-Anzeigensuche hinzu.

| Datensatz | Typ | Schlüsselkonfiguration |
|---|---|---|
| Paid Media-Anzeigenzusammenfassung | Zusammenfassung | Verwenden Sie die tägliche Zeitstempelkonfiguration des Schemas, aktivieren Sie den Import neuer Daten und die erforderliche Aufstockung. |
| Paid Media-Konto-Suche | Lookup | Schlüssel: `paidMedia.accountGUID`; übereinstimmendes Feld in Anzeigenzusammenfassung: `paidMedia.accountGUID`. |
| Paid Media-Kampagnensuche | Lookup | Schlüssel: `paidMedia.campaignGUID`; übereinstimmendes Feld in Anzeigenzusammenfassung: `paidMedia.campaignGUID`. |
| Paid Media AdGroup Lookup | Lookup | Schlüssel: `paidMedia.adGroupGUID`; übereinstimmendes Feld in Anzeigenzusammenfassung: `paidMedia.adGroupGUID`. |
| Paid Media-Anzeigensuche | Lookup | Schlüssel: `paidMedia.adGUID`; übereinstimmendes Feld in Anzeigenzusammenfassung: `paidMedia.adGUID`. |

Vergewissern Sie sich, dass der Verbindungs-Editor die vorgesehenen übereinstimmenden Felder vor dem Speichern verfügbar macht. Bei der Namensanreicherung weiter unten in diesem Handbuch werden explizit abgeleitete Feldsuchregeln verwendet.

Fügen Sie andere verfügbare Zusammenfassungsdatensätze nur hinzu, wenn Sie deren Aufschlüsselungen benötigen, z. B. Geografie, Demografie, Platzierung oder Leistung.

## Datenansicht konfigurieren

Öffnen Sie **[!UICONTROL Daten]** > **[!UICONTROL Datenansichten]** und wählen Sie Ihre Datenansicht aus. Erstellen Sie bei Bedarf eine Datenansicht mit der konfigurierten Verbindung.

Verwenden Sie für eine neue Datenansicht GMT, um Website-Ereignisse an den Tagen für bezahlte Medien im Rahmen der UTC auszurichten, und behalten Sie das standardmäßige 30-minütige Sitzungs-Timeout bei, es sei denn, Ihre Reporting-Anforderungen weichen voneinander ab. Das Ändern der Zeitzone einer vorhandenen Datenansicht wirkt sich auf die anderen Berichte aus. Bewerten Sie diese Auswirkungen, bevor Sie sie ändern.

### Paid-Media-Metriken hinzufügen, falls noch nicht konfiguriert

Überspringen Sie diesen Schritt, wenn diese Metriken oder Dimensionen bereits vorhanden sind. Fügen Sie die folgenden Felder aus der **[!UICONTROL Paid Media-Anzeigenzusammenfassung“]**:

| Name der Komponente | Schemafeld | Format |
|---|---|---|
| **Metriken** | | |
| Impressions \| Anzeigenzusammenfassung | `paidMedia.metrics.impressions` | Dezimal |
| Klicks \| Anzeigenzusammenfassung | `paidMedia.metrics.clicks` | Dezimal |
| Ausgaben \| Anzeigenzusammenfassung | `paidMedia.metrics.spend` | Währung |
| Konversionen \| Anzeigenzusammenfassung | `paidMedia.metrics.conversions` | Dezimal |
| Konversionswert \| Anzeigenzusammenfassung | `paidMedia.metrics.conversionValue` | Währung |
| **Dimensionen** | | |
| Anzeigennetzwerk | `paidMedia.adNetwork` | Zeichenfolge |
| Konto-GUID | `paidMedia.accountGUID` | Zeichenfolge |
| Kampagnen-GUID | `paidMedia.campaignGUID` | Zeichenfolge |
| AdGroup-GUID | `paidMedia.adGroupGUID` | Zeichenfolge |
| Anzeigen-GUID | `paidMedia.adGUID` | Zeichenfolge |

Die Währungsformatierung selbst ermöglicht keine Abstimmung der verschiedenen Quellwährungen. Bestätigen Sie die Währungsbasis, bevor Sie Ausgaben und Einnahmen vergleichen.

Verwenden Sie abgeleitete Felder, um beschreibende Namen für die Dimension „GUIDs“ zu erstellen. Verwenden Sie eine [Lookup](/help/data-views/derived-fields/derived-fields.md#lookup)-Regel, um einen beschreibenden Namen für die GUIDs-Dimension anzuwenden.  Beispiel: Lookup **[!UICONTROL paidMedia.accountGUID (Paid Media Ad Summary)]** mithilfe des Lookup-Datensatzes **[!UICONTROL Paid Media Account Lookup]** mit übereinstimmender `paidMedia.accountGUID` und zurückzugebendem Wert: `paidMedia.accountDetails.accountName`.


### Erstellen des vom Web-Netzwerk abgeleiteten Felds

Wählen Sie **[!UICONTROL Abgeleitetes Feld erstellen]** und benennen Sie das Feld `PM Network (Web)`. Alle [URL-Parse](/help/data-views/derived-fields/derived-fields.md#url-parse)-Regeln unten lesen das `web.webPageDetails.URL`-Feld des Website-Datensatzes, hier als Seiten-URL bezeichnet.

Regeln in dieser Reihenfolge hinzufügen:

| Regel | Funktion | Konfiguration |
|---|---|---|
| 1 | [URL-Parsen](/help/data-views/derived-fields/derived-fields.md#url-parse) | Seiten-URL. Wert der Abfragezeichenfolge für `utm_source` abrufen. |
| 2 | [URL-Parsen](/help/data-views/derived-fields/derived-fields.md#url-parse) | Seiten-URL. Wert der Abfragezeichenfolge für `s_kwcid` abrufen. |
| 3 | [URL-Parsen](/help/data-views/derived-fields/derived-fields.md#url-parse) | Seiten-URL. Wert der Abfragezeichenfolge für `gclid` abrufen. |
| 4 | [URL-Parsen](/help/data-views/derived-fields/derived-fields.md#url-parse) | Seiten-URL. Wert der Abfragezeichenfolge für `fbclid` abrufen. |
| 5 | [Wenn](/help/data-views/derived-fields/derived-fields.md#case-when) | Wenden Sie die folgenden Bedingungen an. |

Konfigurieren Sie die endgültige [Wenn](/help/data-views/derived-fields/derived-fields.md#case-when)-Regel:

1. Wenn Regel 2 oder Regel 3 festgelegt ist, geben Sie `google_ads` zurück.
1. Andernfalls, wenn Regel 4 festgelegt ist oder Regel 1 `fb`, `facebook`, `ig`, `instagram` oder `meta` entspricht, `meta` zurückgeben.
1. Andernfalls, wenn Regel 1 gleich `google` ist, `google_ads` zurückgeben.
1. Fügen Sie Zuordnungen für andere Netzwerke erst hinzu, nachdem Sie deren Werte in `paidMedia.adNetwork` bestätigt haben.
1. Andernfalls wird kein Wert zurückgegeben.

Um eine feste Ausgabe einzugeben, öffnen Sie die Werteauswahl, wählen Sie **[!UICONTROL Benutzerdefinierter Zeichenfolgenwert]** aus und geben Sie die Zeichenfolge ein.

Diese Klassifizierungsregeln basieren auf Tags, nicht auf dem Nachweis, dass ein Besuch von einer bezahlten Anzeige stammt. Beispielsweise kann ein Quellparameter allein auch für nicht bezahlte Links angezeigt werden. Passen Sie die Bedingungen an Ihre Tagging-Konventionen an, bevor Sie das Feld als Paid Traffic-Klassifikator verwenden.

### Erstellen der abgeleiteten Web-ID-Felder

Erstellen Sie ein abgeleitetes Feld pro Berichtebene. Die folgende Struktur behandelt die drei zuvor beschriebenen Tagging-Muster:

| Regel | Funktion | Konfiguration |
|---|---|---|
| 1 | [URL-Parsen](/help/data-views/derived-fields/derived-fields.md#url-parse) | Lesen des ebenenspezifischen Meta-Parameters aus der Seiten-URL |
| 2 | [URL-Parsen](/help/data-views/derived-fields/derived-fields.md#url-parse) | Lesen des ebenenspezifischen UTM-Parameters von der Seiten-URL |
| 3 | [URL-Parsen](/help/data-views/derived-fields/derived-fields.md#url-parse) | `s_kwcid` aus Seiten-URL lesen |
| 4 | [Regex ersetzen](/help/data-views/derived-fields/derived-fields.md#regex-replace) | Anwenden des ebenenspezifischen Ausdrucks auf Regel 3; Ausgabe `$1` |
| 5 | [Wenn](/help/data-views/derived-fields/derived-fields.md#case-when) | Wenn Regel 3 festgelegt ist, Regel 4 zurückgeben; andernfalls, wenn Regel 1 festgelegt ist, Regel 1 zurückgeben; andernfalls Regel 2 zurückgeben |

Verwenden Sie die folgenden Werte:

| Abgeleitetes Feld | Meta-Parameter | UTM-Parameter | regulärer Ausdruck |
|---|---|---|---|
| **PM Kampagnen-ID (Web)** | `campaign_id` | `utm_campaign` | `^.*!([^!]*)![^!]*$` |
| **PM Anzeigengruppen-ID (Web)** | `adset_id` | `utm_term` | `^.*!([^!]*)$` |
| **PM-Werbe-ID (Web)** | `ad_id` | `utm_content` | `^[^!]*![^!]*![^!]*!([^!]*)!.*$` |

Wählen Sie im letzten Fall [Wenn](/help/data-views/derived-fields/derived-fields.md#case-when)-Regel die frühere Regelausgabe aus der Werteauswahl aus, anstatt sie als literale Zeichenfolgen einzugeben.

Der Kampagnenausdruck extrahiert den vorletzten `s_kwcid`, der Anzeigengruppenausdruck extrahiert den letzten Wert und der Anzeigenausdruck den vierten Wert. Diese Positionen hängen von dem zuvor gezeigten Layout ab.

Verwenden Sie **[!UICONTROL Endgültige Ausgabe]** um zu bestätigen, dass die Ergebnisse mit den IDs in der Anzeigenzusammenfassung für bezahlte Medien übereinstimmen. Behalten Sie keine `s_kwcid` Parsing-Verzweigung bei, wenn Ihre URLs ein anderes Layout verwenden. Wenn Ihre URLs nur UTM-Parameter verwenden, lassen Sie die nicht verwendeten Regeln weg und aktualisieren Sie die nachfolgenden Regelverweise entsprechend.

Jedes abgeleitete Feld unterstützt bis zu fünf [URL-Parseregeln](/help/data-views/derived-fields/derived-fields.md#url-parse) und eine [Regex-Ersetzungsregel](/help/data-views/derived-fields/derived-fields.md#regex-replace). Eine ID pro abgeleitetem Feld beibehalten.

### Erstellen der Metrik für bezahlte Landingpages

Erstellen Sie ein abgeleitetes Feld mit dem Namen `Paid Media Landings (Web)` unter Verwendung von `PM Campaign ID (Web)` als Eingabe.

Der Builder erweitert die Regeln des Eingabefelds um das neue Feld. Fügen Sie nach diesen Regeln eine Wenn[Regel hinzu](/help/data-views/derived-fields/derived-fields.md#case-when) die den benutzerdefinierten numerischen Wert `1`, wenn die Ausgabe der Kampagnen-ID festgelegt ist, und ansonsten keinen Wert zurückgibt. Fügen Sie das Ergebnis als Metrik hinzu.

Diese Metrik zählt Ereignisse, die eine Kampagnen-ID tragen. Diese Metrik stellt Landings nur dar, wenn Ihre Implementierung diese ID-tragende URL beim Landing Event sendet und nicht bei wiederholten oder nicht verwandten Ereignissen.

>[!NOTE]
>
>Erweiterte abgeleitete Feldregeln sind Kopien. Wenn Sie ein ID-Feld ändern, überprüfen und aktualisieren Sie auch die entsprechenden Felder Landing Name und Name . Wenn Sie Parsing-Regeln ausgelassen haben, verweisen Sie auf die tatsächliche endgültige ID-Regel, anstatt anzunehmen, dass es sich um Regel 5 handelt.

### Optionale Webnamenfelder hinzufügen

Um Berichte nach Namen zu erstellen, erstellen Sie die folgenden abgeleiteten Felder mit einer [Lookup-Regel](/help/data-views/derived-fields/derived-fields.md#lookup) nach den erweiterten Web-ID-Regeln:

| Abgeleitetes Feld | Eingabe | Lookup-Datensatz | Übereinstimmendes Feld | Rückgabefeld |
|---|---|---|---|---|
| PM-Kampagnenname (Web) | Endgültige Ausgabe der PM-Kampagnen-ID (Web) | Paid Media-Kampagnensuche | `paidMedia.campaignID` | `paidMedia.metadata.name` |
| Name der PM-Anzeigengruppe (Web) | Endgültige Ausgabe der PM-Anzeigengruppen-ID (Web) | Paid Media AdGroup Lookup | `paidMedia.adGroupID` | `paidMedia.metadata.name` |
| PM-Anzeigename (Web) | Endgültige Ausgabe der PM-Werbe-ID (Web) | Paid Media-Anzeigensuche | `paidMedia.adID` | `paidMedia.metadata.name` |

Wählen Sie die endgültige ID-Regel als das Feld aus, auf das die Suche angewendet werden soll. Überprüfen Sie die Namen in der endgültigen Ausgabevorschau, bevor Sie die Felder als Dimensionen hinzufügen. Wenn das erforderliche Übereinstimmungsfeld nicht verfügbar ist, verwenden Sie stattdessen das ID-basierte Reporting.

Namen werden als Text zugeordnet. Verwenden Sie ID-Dimensionen, wenn verschiedene Entitäten einen gemeinsamen Namen haben.

### Web-Komponenten hinzufügen und Attribution konfigurieren

Fügen Sie die Web-ID und die aus dem Netzwerk abgeleiteten Felder als Dimensionen hinzu. Fügen Sie die optionalen Namensfelder hinzu, wenn Sie sie erstellt haben. Behalten Sie die Komponenteneinstellungen bei den Standardeinstellungen, sodass sie den Zusammenfassungsdimensionen entsprechen, die Sie ihren Gruppen hinzufügen.

Vergewissern Sie sich, dass Ihre Datenansicht die benötigten Web-Komponenten enthält:

| Komponente | Typ | Schemafeld |
|---|---|---|
| Seiten-URL | Dimension | `web.webPageDetails.URL` |
| Seitenname | Dimension | `web.webPageDetails.name` |
| Referrer-URL | Dimension | `web.webReferrer.URL` |
| Ereignistyp | Dimension | `eventType` |
| Produkt-SKU | Dimension | `productListItems.SKU` |
| Produktname | Dimension | `productListItems.name` |
| Seitenansichten | Metrik | `web.webPageDetails.pageViews.value` |
| Zu Warenkorb hinzufügen | Metrik | `commerce.productListAdds.value` |
| Bestellungen | Metrik | `commerce.purchases.value` |
| Umsatz | Metrik | `commerce.order.priceTotal` |

Fügen Sie das abgeleitete Feld Paid Landings als Metrik hinzu und konfigurieren Sie dann separate Auftrags- und Umsatzmetriken:

1. Duplizieren Sie **[!UICONTROL Bestellungen]** und benennen Sie die `Orders (Web)`. Wenn **[!UICONTROL Bestellungen]** nicht vorhanden ist, fügen Sie `commerce.purchases.value` direkt hinzu.
1. Duplizieren Sie **[!UICONTROL Umsatz]** und benennen Sie die `Revenue (Web)`. Wenn **[!UICONTROL Umsatz]** nicht vorhanden ist, fügen Sie `commerce.order.priceTotal` direkt hinzu.
1. Format **[!UICONTROL Bestellungen (Web)]** als Dezimalstelle mit null Dezimalstellen und **[!UICONTROL Umsatz (Web)]** als Währung.
1. Öffnen Sie für beide Metriken **[!UICONTROL Attribution]** und aktivieren Sie **[!UICONTROL Standardattribution überschreiben]**.
1. Wählen Sie das **[!UICONTROL Letztkontakt]**-Modell und **[!UICONTROL Sitzungs]**-Container aus.

Die ursprünglichen Metriken **[!UICONTROL Bestellungen]** und **[!UICONTROL Umsatz]** unverändert lassen, um vorhandene Berichte beizubehalten. Für dieses Setup ist eine explizite Aktivierung der Überschreibung erforderlich, auch wenn die angezeigten Standardeinstellungen zu entsprechen scheinen.

Für die Konversionszuweisung bei wiederkehrenden Besuchen sollten Sie stattdessen einen **[!UICONTROL Person]**-Container und ein entsprechendes Lookback-Fenster in Betracht ziehen. Siehe [Anwendungsfall für Zusammenfassungsdaten](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/data-views/summary-data).

Verwenden Sie die Metrikattribution, anstatt den Web-ID-Dimensionen Persistenz hinzuzufügen. Um zu vermeiden, dass die Anzahl der als Landingpages interpretierten Elemente ansteigt, sollten die IDs nicht für spätere Ereignisse beibehalten werden, da dadurch geändert wird, welche Ereignisse in den Kampagnenzeilen angezeigt werden.

### Zusammenfassungsseitige Join-Dimensionen erstellen

Fügen Sie separate Dimensionen aus der Paid-Media-Anzeigenübersicht für die Web-Joins hinzu:

| Name der Komponente | Schemafeld |
|---|---|
| Netzwerk hinzufügen (verbunden) | `paidMedia.adNetwork` |
| Kampagnen-ID (Netzwerk) | `paidMedia.campaignID` |
| Anzeigengruppen-ID (Netzwerk) | `paidMedia.adGroupID` |
| Werbe-ID (Netzwerk) | `paidMedia.adID` |

Bearbeiten oder duplizieren Sie keine schreibgeschützten, vorlagenverwalteten Paid-Media-Komponenten. Erstellen Sie die oben genannten separaten Komponenten von den Schemafeldern.

Wenn Sie optionale Web-Namensfelder erstellt haben, erstellen Sie auch diese zusammenfassungsseitigen abgeleiteten Lookup-Felder:

| Name der Komponente | Eingabe aus der Anzeigenzusammenfassung | Lookup-Datensatz | Übereinstimmendes Feld | Rückgabefeld |
|---|---|---|---|---|
| Kampagnenname (beigetreten) | `paidMedia.campaignGUID` | Paid Media-Kampagnensuche | `paidMedia.campaignGUID` | `paidMedia.metadata.name` |
| Name der Anzeigengruppe (Mitglied) | `paidMedia.adGroupGUID` | Paid Media AdGroup Lookup | `paidMedia.adGroupGUID` | `paidMedia.metadata.name` |
| Anzeigenname (verbunden) | `paidMedia.adGUID` | Paid Media-Anzeigensuche | `paidMedia.adGUID` | `paidMedia.metadata.name` |

Verwenden Sie eine GUID aus dem Zusammenfassungsdatensatz als Eingabe für jede Suche. Eine Dimension, die direkt aus einem Lookup-Datensatz übernommen wird, erfüllt nicht die Anforderung für eine Zusammenfassungsdimension in einer Zusammenfassungsdatengruppe.

### Erstellen von Zusammenfassungsdatengruppen

Erstellen Sie jede Gruppe in der Web-Dimension, die Sie in Berichten verwenden möchten. Fügen Sie die entsprechende Zusammenfassungsdimension hinzu und blenden Sie dieses hinzugefügte Element im Reporting aus.

| Web-Dimension: Gruppe hier erstellen | Zusammenfassungsdimension: als ausgeblendetes Element hinzufügen |
|---|---|
| PM-Netzwerk (Web) | Netzwerk hinzufügen (verbunden) |
| PM-Kampagnen-ID (Web) | Kampagnen-ID (Netzwerk) |
| PM-Anzeigengruppen-ID (Web) | Anzeigengruppen-ID (Netzwerk) |
| PM-Werbe-ID (Web) | Werbe-ID (Netzwerk) |
| PM-Kampagnenname (Web), optional | Kampagnenname (beigetreten) |
| PM-Anzeigengruppenname (Web), optional | Name der Anzeigengruppe (Mitglied) |
| PM-Anzeigename (Web), optional | Anzeigenname (verbunden) |

Für jede Zeile:

1. Wählen Sie die Dimension Web aus.
1. Öffnen Sie **[!UICONTROL Zusammenfassungsdatengruppe]** und aktivieren Sie **[!UICONTROL Gruppierung erstellen]**.
1. Fügen Sie die Dimension Zusammenfassung hinzu.
1. Aktivieren **[!UICONTROL In Berichten ausblenden]** für das hinzugefügte Zusammenfassungselement. Lassen Sie die Web-Dimension sichtbar.
1. Bestätigen Sie, dass Komponenteneinstellungen, einschließlich Kleinbuchstaben, Teilzeichenfolge und Ein-/Ausschlussregeln, über Mitglieder hinweg übereinstimmen.

Jede Gruppe unterstützt bis zu 10 Dimensionen. Um Metriken aus einem anderen Zusammenfassungsdatensatz einzubeziehen, fügen Sie die entsprechende Zusammenfassungsdimension dieses Datensatzes zu derselben Gruppe wie ein ausgeblendetes Mitglied hinzu.

>[!IMPORTANT]
>
>Verwenden Sie die Web-Dimension als Reporting-Dimension und erstellen Sie die Gruppe für diese Dimension. Die umgekehrte Anordnung kann zusammenfassende Metriken ohne die entsprechenden Web-Metriken anzeigen.

Speichern Sie die Datenansicht.

### Erstellen von berechneten Metriken

Gehen Sie in Workspace zu **[!UICONTROL Komponenten]** > **[!UICONTROL Berechnete]** und erstellen Sie die folgenden Metriken mithilfe der konfigurierten Datenansicht:

| Name | Definition | Format |
|---|---|---|
| Landegeschwindigkeit | Bezahlte Medienlandungen (Web) / Klicks \| Anzeigenzusammenfassung | Prozent |
| Web-Konversionsrate | Bestellungen (Web) / Paid Media Landings (Web) | Prozent |
| Web-ROAS | Umsatz (Web) / Ausgaben \| Anzeigenübersicht | Dezimalzahl, zwei Stellen |
| Kosten pro Webbestellung | Ausgaben \| Anzeigenübersicht / Bestellungen (Web) | Währung |
| Netzwerk- vs. Web-Konversionslücke | Konversionen \| Anzeigenzusammenfassung - Bestellungen (Web) | Dezimal, Null Stellen |

Überprüfen Sie die Zeilen mit null Nennern, bevor Sie Verhältnismetriken interpretieren. Eine Netzwerk-Web-Konversionslücke weist für sich genommen nicht auf einen Fehler hin: Die beiden Quellen können sich in Attributions-, Mess- und Berichtsfenstern unterscheiden.

## Erstellen und Validieren des Berichts

1. Erstellen Sie ein Workspace-Projekt mithilfe der konfigurierten Datenansicht.
1. Wählen Sie einen Datumsbereich mit Daten aus beiden Quellen aus. Lassen Sie Verzögerungen bei der Aufnahme bezahlter Medien zu; Zusammenfassungsdaten können Website-Ereignisse um einen Tag verzögern.
1. Fügen Sie eine Freiformtabelle mit **[!UICONTROL PM-Kampagnen-ID (Web]** als Zeilendimension oder **[!UICONTROL PM-Kampagnenname (Web) hinzu]** wenn Sie Namensgruppen konfiguriert haben.
1. Hinzufügen **[!UICONTROL Impressions | Anzeigenzusammenfassung]**, **[!UICONTROL Klicks | Anzeigenzusammenfassung]**, **[!UICONTROL Ausgaben | Anzeigenzusammenfassung]**, **[!UICONTROL Konversionen | Anzeigenzusammenfassung]**, **[!UICONTROL Paid Media Landings | Anzeigenzusammenfassung]**, **[!UICONTROL Bestellungen (Web)]**, **[!UICONTROL Umsatz (Web)]** und die berechneten Metriken.
1. Schlüsseln Sie eine Kampagnenzeile nach der Web-Anzeigengruppe und den Anzeigendimensionen auf. Bestätigen Sie, dass sowohl Zusammenfassungs- als auch Web-Metriken auf jeder konfigurierten Ebene gefüllt werden.
1. Fügen Sie eine zweite Tabelle mit **[!UICONTROL PM Network (Web)]**, um die Gesamtwerte auf Netzwerkebene und die Zeile ohne Wert zu überprüfen.

   ![Paid-Media- und Web-Daten-Workspace-Projekt](./assets/paid-media-and-web-data-workspace.png)

   ![Paid Media- und Web Data Workspace-Projekt ohne Daten](./assets/paid-media-and-web-data-workspace-no-value.png)

Prüfen Sie Folgendes, bevor Sie den Bericht freigeben:

* Die IDs der Landing Events stimmen mit den IDs der Paid Media Ad Summary überein.
* Paid-Media-Metriken und Web-Metriken werden in denselben Zeilen angezeigt.
* Bestellungen und Einnahmen erhalten die vorgesehene Sitzungs- oder Personenzuordnung.
* Es werden keine Wertzeilen verstanden. Sie können nicht übereinstimmende Zusammenfassungsdaten oder Web-Aktivitäten ohne Paid-Media-IDs enthalten.
* Unterschiede zwischen Landing-to-Click entsprechen Ihrer Einrichtung der Sammlung, der Einverständnisbehandlung und den Reporting-Fenstern. Es wird keine allgemeine Übereinstimmungsrate erwartet.

### Fehlerbehebung bei Abweichungen

| Symptom | Überprüfung und Abhilfemaßnahmen |
|---|---|
| Zusammenfassungsmetriken werden ausgefüllt, aber alle Web-Metriken sind null | Bestätigen Sie, dass Zeilen Web-Dimensionen verwenden und dass für diese Dimensionen Gruppen erstellt wurden. Überprüfen Sie dann die Landing URLs auf tatsächliche IDs anstelle von Namen. |
| Web-Metriken werden befüllt, aber eine Zusammenfassungsebene ist leer | Bestätigen Sie, dass sich die Zusammenfassungsdimension der Ebene in der entsprechenden Gruppe befindet und dass für die ausgewählten Daten passende Paid-Media-Daten vorhanden sind. |
| Namen fehlen in den Webzeilen | Überprüfen Sie das Eingabe- und Übereinstimmungsfeld für die Suche in der endgültigen Ausgabevorschau. ID-Gruppen verwenden, wenn keine Namensanreicherung verfügbar ist. |
| Web-IDs enthalten literale oder kodierte Makros | Bitten Sie das Ad Operations-Team, die Ziel-URL zu überprüfen und sicherzustellen, dass das Netzwerk die Makros vor der Landingpage erweitert. |
| Google Ads-IDs stimmen nicht überein | Überprüfen Sie das tatsächliche `s_kwcid`-Layout oder die UTM-Parameter und aktualisieren Sie die Parsing-Regeln. |
| Netzwerkwerte werden aufgeteilt, z. B. `facebook` und `meta` | Stellen Sie sicher, dass die vom Netzwerk abgeleitete Feldausgabe genau `paidMedia.adNetwork`. |
| Eine ID wird in separaten Zeilen angezeigt | Überprüfen Sie, ob die Einstellungen über gruppierte Dimensionen hinweg übereinstimmen, und überprüfen Sie die zugrunde liegenden Zeichenfolgenwerte. |
| Website-Aktivität scheint um einen Tag verschoben | Vergleichen Sie die Zeitzone der Datenansicht mit den Tagesgrenzen der UTC-Zusammenfassung. |
| Bestellungen oder Umsatz sind null oder unerwartet niedrig unter Kampagnen | Aktivieren Sie explizit die Überschreibung der Metrik-Attribution und bestätigen Sie deren Modell-, Container- und Lookback-Einstellungen. |
| Bezahlte Landungen sind unerwartet hoch | Vergewissern Sie sich, dass nur Landing Events den gezählten Kampagnenparameter enthalten. Wiederholte ID-tragende Ereignisse tragen ebenfalls zu dieser Metrik bei. |
| Unterschiedliche Kampagnen teilen sich eine Namenszeile | Verwenden Sie ID-basierte Berichte, um Entitäten mit identischen Namen zu unterscheiden. |
