---
title: Automatische Konfiguration für bezahlte Medien in Content Analytics
description: Erfahren Sie mehr über die automatische Konfiguration von Datensätzen, Verbindungen, Datenansichten und mehr.
solution: Customer Journey Analytics
feature: Content Analytics
hold: true
role: Admin
source-git-commit: e9274ad7899537837723e2eb9cd842c5449530ff
workflow-type: tm+mt
source-wordcount: '2309'
ht-degree: 2%
---
# Automatische Konfiguration für bezahlte Medien

Wenn Sie den Paid-Media-Kanal in Content Analytics aktivieren und die Konfiguration speichern, aktualisiert Adobe die ausgewählten Verbindungs- und Datenansichten mit der Berichtskonfiguration für die Paid-Media-Datensätze. Sie müssen die Standarddimensionen, Metriken, Lookup-Logik oder Zusammenfassungsdatengruppen nicht selbst neu erstellen.

Es werden drei Ebenen von Objekten erstellt:

| Objekte | Enthält | Zweck |
| --- | --- | --- |
| Zusammenfassungsdatensätze | Advertising-Netzwerkleistungsdaten auf Anzeigen-, Erlebnis-Platzierungs- oder Asset-Ebene, wobei separate demografische/geografische Aufschlüsselungen unterstützt werden. | Ermöglicht die Messung des Versands, der Klicks, der Ausgaben und der Ergebnisse von Werbenetzwerken |
| Metadaten- und Attributsuchdatensätze | Konto-, Kampagnen-, Anzeigengruppen-, Anzeigen-, Erlebnis- und Asset-Details; Content Analytics-Kreativattribute. | Ermöglicht Ihnen, Berichte mit erkennbaren Namen, kreativen Details, Miniaturen und Inhaltsattributen zu erstellen, anstatt Kennungen zu verwenden. |
| Komponenten und Konfiguration der Datenansicht | Dimensionen, Metriken, berechnete Metriken, abgeleitete Felder und Zusammenfassungsdatengruppen. | Mit können Sie Workspace-Analysen erstellen, ohne die Beziehungen zwischen diesen Datensätzen manuell neu erstellen zu müssen. |

Durch die Aktivierung von Paid Media werden die Paid-Media-Daten nicht automatisch mit den Bestellungen, Buchungen oder dem Umsatz Ihrer Site verbunden. Die Korrelation zwischen Ihren Erlebnisereignisdaten und Paid-Media-Daten erfordert eine kundenspezifische Tracking-Key-Zuordnung und Reporting-Konfiguration.

## Zusammenfassungsdatensätze

Die folgende Abbildung zeigt, wie Zusammenfassungsdatensätze generiert werden, wenn Sie den Paid-Media-Kanal in Content Analytics für ein oder mehrere Ihrer Werbenetzwerke aktivieren. Die relevanten APIs aus den verfügbaren Werbenetzwerken werden verwendet, um Erlebnis-, Asset- und Anzeigendaten herunterzuladen und in möglicherweise sechs zusammenfassende Datensätze umzuwandeln.

![Generierung von Zusammenfassungsdatensätzen über bezahlte Medien](/help/content-analytics/assets/paid-media-generation-of-datasets.png)

Das spezifische Anzeigennetzwerk bestimmt, welche Zusammenfassungsdatensätze erstellt werden. Nicht jedes Anzeigennetzwerk, für das Sie einen Quell-Connector konfiguriert haben, generiert alle sechs möglichen Zusammenfassungsdatensätze. In der folgenden Tabelle finden Sie eine Übersicht über die Zusammenfassungsdatensätze mit den folgenden Informationen:

* Name des Zusammenfassungsdatensatzes, Ereignistyp und Komponenten-Suffix
* Entität
* Aufschlüsselung
* Welche Datensätze werden für ![ folgenden Netzwerke ausgefüllt ](/help/assets/icons2/Checkmark.svg)Häkchen):
  * ![MetaSolid](/help/assets/icons2/MetaSolid.svg) Meta
  * ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) Google
  * ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) Pinterest
  * ![Snapchat](/help/assets/icons2/Snapchat.svg) Snapchat
  * ![TikTok](/help/assets/icons2/TikTok.svg) TikTok

    >[!AVAILABILITY]
    >
    >Pinterest, Snapchat und TikTok befinden sich in der eingeschränkten Testphase der Veröffentlichung und sind möglicherweise noch nicht in Ihrer Umgebung verfügbar. Diese Anmerkung wird entfernt, wenn die Funktionen allgemein verfügbar sind. Informationen zum Customer Journey Analytics-Veröffentlichungsprozess finden Sie unter [Customer Journey Analytics-Funktionsversionen](/help/release-notes/releases.md)
    >


* Was jede Zeile in einem Zusammenfassungsdatensatz darstellt.

| Zusammenfassung Datensatz<br/>Ereignis-Typ<br/>Komponenten-Suffix | Entity<br/>Breakdown | ![MetaMulti](/help/assets/icons2/MetaSolid.svg) | ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) | ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) | ![Snapchat](/help/assets/icons2/Snapchat.svg) | ![TikTok](/help/assets/icons2/TikTok.svg) | Jede Zeile stellt Folgendes dar |
|---|---|:---:|:---:|:---:|:---:|:---:|---|
| `paidmedia_ad_summary` <br/> `ad.summary`<br/>`\| Ad Summary` | <br/> | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | Die tägliche Leistung einer Anzeige ohne demografische oder geografische Aufschlüsselungen. |
| `paidmedia_ad_demographics` <br/> `ad.demographics`<br/>`\| Ad Demo` | Anzeigen<br/>Alter, Geschlecht | ![Häkchen](/help/assets/icons2/Checkmark.svg) | | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | Die tägliche Leistung einer Anzeige <br/> nach Alter und Geschlecht. |
| `paidmedia_ad_geography` <br/> `ad.geography`<br/>`\| Ad Geo` | Ad<br/>country, Region | ![Häkchen](/help/assets/icons2/Checkmark.svg) | | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | Die tägliche Leistung einer Anzeige <br/> nach Land und Region. |
| `paidmedia_experience_placement` <br/> `ad.experience.placement`<br>`\| Experience Placement` | Experience<br>Platform, Position | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | Tägliche Leistung, <br/> mit dem kreativen Erlebnis einer Anzeige verbunden ist<br/> aufgeschlüsselt nach Plattform und Position. |
| `paidmedia_asset_summary` <br/>`ad.asset.summary`<br/>`\| Asset Summary` | Asset<br/>none | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | | | ![Häkchen](/help/assets/icons2/Checkmark.svg) | Tägliche Leistung auf Asset<br/>Ebene im Anzeigen-/Kampagnenkontext <br/> demografischer oder geografischer Aufschlüsselung. |
| `paidmedia_assets_demographics` <br/> `ad.asset.demographics`<br/>`\| Asset Demo` | Asset<br/>Alter, Geschlecht | ![Häkchen](/help/assets/icons2/Checkmark.svg) | | | | | Tägliche Leistung auf Asset<br/>Ebene im Anzeigenkontext/im Kampagnenkontext, <br/> nach Alter und Geschlecht aufgeschlüsselt. |


Diese Tabelle beschreibt die Datensatzabdeckung, keine Garantie dafür, dass jedes Metrik- oder Metadatenfeld von einem bestimmten Netzwerk ausgefüllt wird. Überprüfen Sie die für Ihre Analyse erforderlichen Felder. Ein nicht verfügbares Feld oder eine nicht unterstützte Aufschlüsselung ist nicht dasselbe wie ein gemessener Nullwert für ein Feld.

Separate Lookup-Datensätze beschreiben Konto, Kampagne, Anzeigengruppe, Anzeige, Erlebnis und Asset. Sie stellen Namen und Metadaten mithilfe von Entitäts-GUIDs bereit. Es gibt keine Eins-zu-eins-Paarung zwischen den Zusammenfassungsdatensätzen und den sechs Lookup-Datensätzen.

Durch die Gruppierung von Zusammenfassungsdaten werden äquivalente Dimensionen zusammengeführt. Die Gruppierung ergibt nicht die sechs Leistungsmetriken insgesamt.

## Komponenten

Nach der Aktivierung generiert der Content Analytics-Kanal für bezahlte Medien auch eine Reihe von Datenansichtskomponenten. Diese Komponenten werden mit einem Komponenten-Suffix versehen, um ähnliche benannte Komponenten voneinander zu unterscheiden.

### Metrik

Verschiedene Anzeigennetzwerke geben unterschiedliche Leistungsaufschlüsselungen zurück. Content Analytics behält diese Unterscheidungen bei, anstatt jede Version einer Metrik als austauschbar zu behandeln.

Beispiel:

| Komponente | Bedeutung | Angemessene Startanalyse |
| --- | --- | --- |
| Klicks \| Anzeigenzusammenfassung | Klicks, die auf der Nicht-Aufschlüsselungsebene der Anzeige gemeldet werden | Kampagnen- oder Anzeigenleistung |
| Klicks \| Asset-Zusammenfassung | Klicks auf Asset-Ebene | Creative-Asset-Performance |
| Klicks \| Anzeigen-Geo | Klicks aus dem AD-Geography-Bericht | Leistung nach Land oder Region |
| Klicks \| Erlebnis-Platzierung | Klicks aus dem Experience-Platzierungs-Bericht | Creative-Leistung nach Platzierung |

Jede Klicks-Metrik-Komponente liefert einen anderen Berichtskontext. Sie können diese Metrikkomponenten nicht in einer Gesamtsumme summieren. Dieselbe zugrunde liegende Werbeaktivität kann in mehr als einem Zusammenfassungsdatensatz dargestellt werden.

### Dimensionen

Jeder Zusammenfassungsdatensatz enthält IDs und GUIDs. Die ID ist die Identität (für Konto, Kampagne, Anzeigengruppe, Anzeige, Erlebnis und Asset), die vom Werbenetzwerk bereitgestellt wird, und ist eindeutig **innerhalb** der Werbenetzwerkdaten. Die GUID ist eine von Adobe bereitgestellte Identität (für Konto, Kampagne, Anzeigengruppe, Anzeige, Erlebnis und Asset) und ist **Anzeigennetzwerken**. IDs und GUIDs werden verwendet, um die entsprechenden Namen und Metadaten zu suchen.

### Abgeleitete Felder

Abgeleitete Felder sind Teil der automatischen Berichtskonfiguration. Abgeleitete Felder übersetzen Kennungen in Namen und Metadaten, stellen kreative Attribute zur Verfügung und unterstützen die entsprechenden Dimensionen, die in Berichtsquellen verwendet werden. Sie erstellen keine zusätzliche Werbeaktivität und weisen nicht automatisch eine Website-Konversion zu.

Verwenden Sie dieselbe Aufschlüsselung für die Metriken innerhalb einer Analyse und die von dieser Aufschlüsselung unterstützten Dimensionen. Beachten Sie, dass demografische und geografische Gesamtwerte nicht unbedingt den Gesamtwerten ohne Aufschlüsselung für ein Werbenetzwerk entsprechen und nicht auf einen Aufnahmefehler hindeuten.

## Reporting und Analyse

Nachdem Sie die Einrichtung und Aufnahme bezahlter Content Analytics-Medien abgeschlossen haben, können Sie mit der Berichterstellung und Analyse beginnen. In der folgenden Tabelle finden Sie einige Beispiele. Verwenden Sie, sofern verfügbar, die kanonisch gruppierten Dimensionen und wählen Sie Metriken aus der entsprechenden Berichterstellungsebene.

| Geschäftsfrage | Startebene | Zeilen und Aufschlüsselungen | Starten von Metriken | Wichtige Grenze |
| --- | --- | --- | --- | --- |
| Wie entwickeln sich meine Kampagnen und Anzeigen? | Anzeigenzusammenfassung | Kampagnenname, Anzeigengruppenname, Anzeigenname; optional Anzeigennetzwerk und Kontoname | Impressionen \| Anzeigenübersicht, Klicks \| Anzeigenübersicht, Ausgaben \| Anzeigenübersicht, Übereinstimmung mit CTR und CPC | Verwenden Sie eine Ebene für Versand-/Ausgabensummen; überprüfen Sie die Währung, bevor Sie Konten kombinieren |
| Welche Kreativ-Assets erhalten die stärkste Resonanz? | Asset-Zusammenfassung | Asset-Name (bezahlte Medien), Asset-Identität; optional Anzeigennetzwerk | Impressionen \| Asset-Zusammenfassung, Klicks \| Asset-Zusammenfassung, Clickthrough-Rate \| Asset-Zusammenfassung | Dies ist die vom Netzwerk gemeldete Asset-Leistung und kein Nachweis für eine spätere Konversion vor Ort |
| Welche Bildmerkmale sind mit der Leistung verbunden? | Asset-Zusammenfassung | Asset-Tags, Asset-Objekte, Asset-Personenkategorien, Asset-Szenen oder andere verfügbare Asset-Attribute | Asset-Zusammenfassungs-Impressionen, -Klicks und CTR | Attributextraktion muss verfügbar sein; Attributkategorien mit mehreren Werten können sich überschneiden |
| Welche Messaging-Merkmale sind mit gebührenpflichtiger Leistung verbunden? | Erlebnisplatzierung | Erlebnis-Keywords, Erlebnis-Töne, Erlebnis-Überzeugungsstrategien oder andere verfügbare Erlebnisattribute; optional Plattform und Platzierung | Impressions \| Erlebnisplatzierung, Klicks \| Erlebnisplatzierung, übereinstimmender CTR | Erfordert ausgefüllte Erlebnisattribute. Die Ergebnisse sind platzierungsspezifisch und beschreiben den Zusammenhang, nicht die kausalen Auswirkungen |
| Welche Platzierungen funktionieren am besten? | Erlebnisplatzierung | Erlebnisname, Plattform, Platzierung | Impressions \| Erlebnisplatzierung, Klicks \| Erlebnisplatzierung, übereinstimmender CTR | Platzierungsdefinitionen und verfügbare Werte variieren je nach Werbenetzwerk |
| Wie lassen sich Anzeigen/Assets/Erlebnisse in Meta und Google vergleichen? | Anzeigenzusammenfassung, Asset-Zusammenfassung oder Erlebnisplatzierung, die für die Frage ausgewählt wurden | Fügen Sie das Netzwerk mit der entsprechenden Kampagnen-, Asset- oder Erlebnisdimension hinzu | Gleiche Ebene und Metrikdefinition für beide Netzwerke | Nur Felder vergleichen, die von beiden Netzwerken ausgefüllt werden. Google füllt nicht die drei demografischen/geografischen Zusammenfassungen in diesem Modell. |

Diese Berichte können Zuordnungen zwischen kreativen Attributen und Leistung aufdecken, aber nicht beweisen, dass ein Attribut ein Ergebnis verursacht hat.

Vermeiden Sie inkompatible Kombinationen: Asset-Name (bezahlte Medien) mit Anzeigenzusammenfassungsmetriken ist kein Ersatz für einen Asset-Bericht. Verwenden Sie Asset-Zusammenfassungsmetriken für die Asset-Analyse und Ad-Geography-Metriken für die Regionsanalyse. Leere oder Null-Zellen aus einer inkompatiblen Paarung sollten nicht als Beweis für fehlende Aktivität interpretiert werden.

### Beispiele

Im Folgenden finden Sie Beispiele für die Berichterstellung und Analyse der Paid-Media-Leistung und für die Kombination von Erlebnis- und Asset-Daten aus Content Analytics mit Paid-Media-Daten.

#### Anzeigenkampagnenleistung

Sie möchten einen Bericht über die Kampagnenleistung auf Anzeigenebene erstellen. Verwenden Sie in Analysis Workspace den Kampagnennamen als Dimension (Zeilen) und verwenden Sie die Metriken wie in der folgenden Tabelle beschrieben. Jede Metrik hat dasselbe Komponenten-Suffix.

| Metrik | Berichterstellungsebene |
| --- | --- |
| Impressionen | Anzeigenzusammenfassung |
| Klicks | Anzeigenzusammenfassung |
| Ausgaben | Anzeigenzusammenfassung |
| Clickthrough-Rate | Anzeigenzusammenfassung |
| Kosten pro Klick | Anzeigenzusammenfassung |

Optional können Sie den Kampagnennamen nach Anzeigenamen aufschlüsseln, aber behalten Sie alle fünf Spalten auf der Ebene der Anzeigenzusammenfassung bei.

Um einzelne Assets zu untersuchen, verwenden Sie eine separate Tabelle mit dem Asset-Namen (bezahlte Medien) und den entsprechenden Spalten mit der Asset-Zusammenfassung. Addieren Sie nicht die Summen der beiden Tabellen.

#### Identifizieren von Anzeigen mit der besten Leistung

Sie möchten wissen, wo Ihre Meta-Anzeigen am besten abschneiden?

Verwenden Sie zur Untersuchung zusätzliche Aufschlüsselungen für Geografie und Demografie. Verwenden Sie den Kampagnennamen oder Anzeigenamen als Dimension und verwenden Sie die Metriken wie in der folgenden Tabelle beschrieben. Jede Metrik hat dasselbe Komponenten-Suffix.

| Metrik | Berichterstellungsebene |
| --- | --- |
| Impressionen | Geografie hinzufügen |
| Klicks | Geografie hinzufügen |
| Ausgaben | Anzeigenzusammenfassung |
| Clickthrough-Rate | Geografie hinzufügen |
| Kosten pro Klick | Anzeigenzusammenfassung |


#### Paid-Media-Daten mit Erlebnisereignisdaten verbinden

Verbinden Sie Paid Media Performance mit Verhaltensdaten auf der Site, um zu verstehen, wie Kampagnen und Anzeigen mit Website-Interaktion, Konversionen und Umsatz verbunden sind. Vergleichen Sie beispielsweise Klicks auf das Werbenetzwerk und Ausgaben mit Bestellungen, die Besuchen aus derselben Kampagne zugeordnet wurden.

Schließen Sie zum Konfigurieren dieser Berichte die Paid-Media-Zusammenfassungsdatensätze und Ihren Vor-Ort-Ereignisdatensatz in dieselbe Customer Journey Analytics-Verbindung ein. Erfassen Sie stabile Kampagnen-, Anzeigen- oder unterstützte Asset-Kennungen aus Landingpage-URL-Parametern oder vorhandenen Ereignisfeldern. Verwenden Sie nach Bedarf abgeleitete Felder, um diese Werte zu analysieren und den entsprechenden Paid-Media-IDs zuzuordnen, wobei der erforderliche Netzwerk- und Kontenkontext beibehalten wird. Bezeichner als Zeichenfolgen beibehalten. Um die übereinstimmenden Ereignis- und Zusammenfassungsdimensionen zu verknüpfen, konfigurieren Sie eine Zusammenfassungsdatengruppe in der Datenansicht. Durch die Aktivierung des Kanals für bezahlte Medien wird dieses implementierungsspezifische URL-Tracking und -Mapping nicht automatisch konfiguriert.


| Tracking-Option | Zu beachten |
|---|---|
| Meta Ads | Konfigurieren Sie Ziel-URL-Parameter mithilfe dynamischer Kennungen wie `campaign.id`, `adset.id` und `ad.id`, sofern unterstützt. Erfassen Sie die aufgelösten Werte auf Ihrer Website. Durch Aktivierung des Connectors werden diese Parameter nicht automatisch zu Ihren Werbe-URLs hinzugefügt. |
| Google Ads | |
| Einzelne Assets | Für das Reporting auf Asset-Ebene zu nachgelagerten Ergebnissen ist eine erfasste Kennung erforderlich, die dem spezifischen Asset zugeordnet wird, das mit dem Klick verbunden ist. Ein benutzerdefinierter URL-Parameter kann dies unterstützen, wenn das Anzeigenformat ein Asset-spezifisches Tracking zulässt. Eine Anzeigenkennung allein kann nicht mehrere Assets innerhalb einer Anzeige unterscheiden, und ein statischer Asset-Parameter, der auf eine gesamte Multi-Asset-Anzeige angewendet wird, identifiziert nicht, welches Asset mit dem Klick verknüpft war. |

Verwenden Sie in Analysis Workspace **[!UICONTROL Anzeigenzusammenfassung]** Metriken für Kampagnen- oder Anzeigenvergleiche und **[!UICONTROL Asset-Zusammenfassung]** Metriken für unterstützte Asset-Vergleiche. Wenden Sie ein Attributionsmodell und ein Lookback-Fenster auf die Konversionsmetriken auf der Site an, die Ihre Berichtsfrage widerspiegeln.

Beachten Sie Folgendes:

* Bezahlte Mediendaten sind aggregierte Zusammenfassungsdaten ohne Personen-ID. Das Verhalten auf der Site besteht aus Ereignisdaten.
* Das Gruppieren übereinstimmender Dimensionen unterstützt Berichte über diese Quellen hinweg, stimmt jedoch nicht mit individuellen Anzeigennetzwerkkonversionen auf Website-Konversionen überein oder führt Stitching auf Personenebene durch.
* Der Vergleich zeigt einen Zusammenhang, keinen kausalen Anstieg.
* Die Ergebnisse können aufgrund von Konversionsdefinitionen, Attributionsfenstern, View-Through- oder modellierten Konversionen, Einverständnis und Berichtsdaten oder Zeitzonen unterschiedlich sein.
* Validieren der Quelle von Besuchen mit Kampagnen-Tags, wenn Tracking-Parameter kanalübergreifend wiederverwendet werden.


#### Kampagnenleistung mit Bestellungen vor Ort vergleichen

Eine Landingpage-URL kann mehrere Tracking-Parameter enthalten. In diesem Beispiel wird die Kampagnen-ID in `utm_id` verwendet, um die Kampagnenausgaben mit den Bestellungen auf der Website zu vergleichen.

https://www.example.com/offer?utm_source=facebook&utm_medium=paid_social&utm_campaign=autumn_offer&utm_id=120218706543980215

Der für diesen Vergleich verwendete Parameter: `utm_id=120218706543980215`. Die anderen Parameter beschreiben die Quelle, das Medium und die Kampagnentitel, werden jedoch nicht als übereinstimmendes Feld verwendet, das in diesem Beispiel verwendet wird.

Wenn die URL in Website-Ereignisdaten erfasst wird und sowohl der Website-Ereignisdatensatz als auch die Paid-Media-Datensätze Teil derselben Customer Journey Analytics-Verbindung sind:

1. Identifizieren Sie die Kampagne. Verwenden Sie ein abgeleitetes Feld, um `utm_id` aus der URL zu lesen und ihren Wert der entsprechenden Kampagnenkennung in den Paid-Media-Daten zuzuordnen.
1. Gruppieren Sie die übereinstimmenden Dimensionen. Fügen Sie in der Datenansicht die Dimension Website-Kampagne zur `Summary Data Group` der Dimension Bezahlte Kampagne hinzu, wobei alle vorhandenen Elemente erhalten bleiben.
1. Ausgaben und Bestellungen vergleichen. Verwenden Sie in Analysis Workspace die Dimension Gruppierte Kampagne als Zeilen einer Freiformtabelle. Hinzufügen `Ad Summary` Ausgaben- und Website-`Orders` als Spalten. Legen Sie das Attributionsmodell und das Lookback-Fenster für `Orders` fest.


Die Freiformtabelle zeigt die Ausgaben für Werbung und Netzwerke zusammen mit den Bestellungen der Website an, die jeder Kampagne zugeordnet wurden. Zwei Kampagnen mit ähnlichen Werbeausgaben weisen eine unterschiedliche Anzahl von nachgelagerten Website-Aktionen auf. Verwenden Sie diesen Vergleich, um Kampagnen und Landingpage-Erlebnisse für weitere Untersuchungen oder Tests zu identifizieren, anstatt die Leistung nur anhand von Werbemetriken zu bewerten.

Im Beispiel wird eine Kampagnen-ID verwendet, aber derselbe Ansatz kann Anzeigengruppen-, Anzeigen- oder Asset-Kennungen verwenden, wenn übereinstimmende Werte erfasst werden können. Mit Content Analytics-Attributen wie **[!UICONTROL Asset-Vordergrundfarben]** können Sie kreative Eigenschaften mit der Paid-Media-Leistung vergleichen. Wenn Asset-spezifische Tracking- und übereinstimmende Attributdimensionen für beide Quellen konfiguriert sind, können Sie diesen Vergleich auf zugewiesene Website-Bestellungen erweitern und die Ergebnisse für kreative Tests verwenden.

#### Kombinieren der Asset-Leistung mit Web-Daten

Wenn Sie Berichte und Analysen zur Asset-Leistung in Bezug auf Ihre Paid-Media-Investitionen erstellen möchten, sollten Sie einen bestimmten Asset-UTM-Parameter in Ihrer Paid-Media-Konfiguration für das Werbenetzwerk hinzufügen. Fügen Sie beispielsweise neben dynamischen Standardparametern wie s`ite_source_name`, `campaign.id`, `adset.id` oder `placement` statische benutzerdefinierte Parameter wie `aca_asset_id=999999` hinzu.

Dieser benutzerdefinierte Parameter wird zur Landingpage-URL hinzugefügt. Beispiel: https://www.example.com/home.html?utm_content=120241705099850539%2Caca_asset_id%3D9999999%2Caca_placement%3DFacebook_Desktop_Feed&amp;aca_id_2=8888888&amp;utm_medium=paid&amp;utm_source=fb&amp;utm_id=120241705099830539&amp;utm_term=120241705099840539&amp;utm_campaign=120241705099830539

Sie haben jetzt eine Beziehung zwischen einem Asset auf einer Seite und Ihren Paid-Media-Daten. Verwenden Sie diese Beziehung in Analysis Workspace, um zu sehen, wie Content Analytics-Asset **[!UICONTROL Metadaten (z. B. „Asset-Vordergrundfarben]**) zum Erfolg von Paid-Media-Kampagnen beitragen.


<!--

Do we need to include the tables from the Wiki?

## Reference

The following table lists paid media fields, their XDM paths, provisioned components, and reporting visibility.

+++ Paid media fields

| Field name | XDM path | ACA Paid Media component | Provisioning status | Reporting visibility |
| --- | --- | --- | --- | --- |
| Ad Network | `paidMedia.adNetwork` | Ad Network (dimension) | existing | visible through shared grouping: Ad Network |
| Channel | `paidMedia.channel` | Content Channel (dimension)<br/>Content Channel (shared dimension) | existing | visible through shared grouping: Content Channel |
| Account GUID | `paidMedia.accountGUID` | Account GUID (dimension) | existing | visible through shared grouping: Account GUID |
| Campaign GUID | `paidMedia.campaignGUID` | Campaign GUID (dimension) | existing | visible through shared grouping: Campaign GUID |
| Ad Group GUID | `paidMedia.adGroupGUID` | AdGroup GUID (dimension) | existing | visible through shared grouping: AdGroup GUID |
| Ad GUID | `paidMedia.adGUID` | Ad GUID (dimension) | existing | visible through shared grouping: Ad GUID |
| Experience GUID | `paidMedia.experienceGUID` | Experience GUID \| Ad Summary (dimension)<br/>Experience Id (shared dimension) | existing | visible through shared grouping: Experience Id |
| Asset GUID | `paidMedia.assetGUID` | Asset GUID \| Ad Summary (dimension)<br/>Asset Id (shared dimension) | existing | visible through shared grouping: Asset Id |
| Name | `paidMedia.metadata.name` | Ad Name (derived field)<br/>Ad Name (shared dimension)<br/>AdGroup Name (derived field)<br/>AdGroup Name (shared dimension)<br/>Asset Name (Paid Media) (derived field)<br/>Asset Name (Paid Media) (shared dimension)<br/>Campaign Name (derived field)<br/>Campaign Name (shared dimension)<br/>Experience Name (derived field)<br/>Experience Name (shared dimension) | existing | visible through shared grouping: Ad Name, AdGroup Name, Asset Name (Paid Media), Campaign Name, Experience Name |
| Status | `paidMedia.metadata.status` | Ad Status (derived field)<br/>Ad Status (shared dimension)<br/>Ad Group Status (derived field)<br/>Ad Group Status (shared dimension)<br/>Campaign Status (derived field)<br/>Campaign Status (shared dimension) | curated net-new | visible through shared grouping: Ad Status, Ad Group Status, Campaign Status |
| Serving Status | `paidMedia.metadata.servingStatus` | | excluded | missing provisioned component |
| Updated Time | `paidMedia.metadata.updatedTime` | | excluded | missing provisioned component |
| Account Name | `paidMedia.accountDetails.accountName` | Account Name (derived field)<br/>Account Name (shared dimension) | existing | visible through shared grouping: Account Name |
| Currency | `paidMedia.accountDetails.currency` | Account Currency (derived field)<br/>Account Currency (shared dimension) | curated net-new | visible through shared grouping: Account Currency |
| Timezone | `paidMedia.accountDetails.timezone` | Account Timezone (derived field)<br/>Account Timezone (shared dimension) | curated net-new | visible through shared grouping: Account Timezone |
| Account Type | `paidMedia.accountDetails.accountType` | Account Type (derived field)<br/>Account Type (shared dimension) | curated net-new | visible through shared grouping: Account Type |
| Business Name | `paidMedia.accountDetails.businessName` | Account Business Name (derived field)<br/>Account Business Name (shared dimension) | curated net-new | visible through shared grouping: Account Business Name |
| Campaign Type | `paidMedia.campaignDetails.campaignType` | Campaign Type (derived field)<br/>Campaign Type (shared dimension) | curated net-new | visible through shared grouping: Campaign Type |
| Objective | `paidMedia.campaignDetails.objective` | Campaign Objective (derived field)<br/>Campaign Objective (shared dimension) | curated net-new | visible through shared grouping: Campaign Objective |
| Is Automated Campaign | `paidMedia.campaignDetails.isAutomatedCampaign` | Campaign Is Automated \| Ad Summary (derived field) | curated net-new | hidden |
| Bid Strategy | `paidMedia.campaignDetails.budgetSettings.bidStrategy` | Campaign Bid Strategy (derived field)<br/>Campaign Bid Strategy (shared dimension) | curated net-new | visible through shared grouping: Campaign Bid Strategy |
| Budget Type | `paidMedia.campaignDetails.budgetSettings.budgetType` | Campaign Budget Type (derived field)<br/>Campaign Budget Type (shared dimension) | curated net-new | visible through shared grouping: Campaign Budget Type |
| Daily Budget | `paidMedia.campaignDetails.budgetSettings.dailyBudget` | Campaign Daily Budget (derived field)<br/>Campaign Daily Budget (shared dimension) | curated net-new | visible through shared grouping: Campaign Daily Budget |
| Lifetime Budget | `paidMedia.campaignDetails.budgetSettings.lifetimeBudget` | Campaign Lifetime Budget (derived field)<br/>Campaign Lifetime Budget (shared dimension) | curated net-new | visible through shared grouping: Campaign Lifetime Budget |
| Campaign Budget Optimization | `paidMedia.campaignDetails.budgetSettings.isCampaignBudgetOptimization` | Campaign Budget Optimization \| Ad Summary (derived field) | curated net-new | hidden |
| Catalog ID | `paidMedia.campaignDetails.catalogId` | Campaign Catalog ID \| Ad Summary (derived field) | curated net-new | hidden |
| Start Time | `paidMedia.campaignDetails.startTime` | Campaign Start Time (derived field)<br/>Campaign Start Time (shared dimension) | curated net-new | visible through shared grouping: Campaign Start Time |
| End Time | `paidMedia.campaignDetails.endTime` | Campaign End Time (derived field)<br/>Campaign End Time (shared dimension) | curated net-new | visible through shared grouping: Campaign End Time |
| Ad Group Type | `paidMedia.adGroupDetails.adGroupType` | Ad Group Type (derived field)<br/>Ad Group Type (shared dimension) | curated net-new | visible through shared grouping: Ad Group Type |
| Bid Strategy Type | `paidMedia.adGroupDetails.budgetSettings.bidStrategyType` | Ad Group Bid Strategy Type (derived field)<br/>Ad Group Bid Strategy Type (shared dimension) | curated net-new | visible through shared grouping: Ad Group Bid Strategy Type |
| Optimization Goal | `paidMedia.adGroupDetails.optimizationSettings.optimizationGoal` | Ad Group Optimization Goal (derived field)<br/>Ad Group Optimization Goal (shared dimension) | curated net-new | visible through shared grouping: Ad Group Optimization Goal |
| Delivery Status | `paidMedia.adGroupDetails.deliverySettings.deliveryStatus` | Ad Group Delivery Status \| Ad Summary (derived field) | curated net-new | hidden |
| Start Time | `paidMedia.adGroupDetails.startTime` | Ad Group Start Time (derived field)<br/>Ad Group Start Time (shared dimension) | curated net-new | visible through shared grouping: Ad Group Start Time |
| End Time | `paidMedia.adGroupDetails.endTime` | Ad Group End Time (derived field)<br/>Ad Group End Time (shared dimension) | curated net-new | visible through shared grouping: Ad Group End Time |
| Ad Type | `paidMedia.adDetails.adType` | Ad Type (derived field)<br/>Ad Type (shared dimension) | curated net-new | visible through shared grouping: Ad Type |
| Delivery Status | `paidMedia.adDetails.deliveryStatus` | Ad Delivery Status (derived field)<br/>Ad Delivery Status (shared dimension) | curated net-new | visible through shared grouping: Ad Delivery Status |
| Review Status | `paidMedia.adDetails.reviewStatus` | Ad Review Status (derived field)<br/>Ad Review Status (shared dimension) | curated net-new | visible through shared grouping: Ad Review Status |
| Creative Type | `paidMedia.adDetails.creative.paidMediaCreative.creativeType` | Ad Creative Type (derived field)<br/>Ad Creative Type (shared dimension) | curated net-new | visible through shared grouping: Ad Creative Type |
| Title | `paidMedia.adDetails.creative.paidMediaCreative.title` | Ad Title (derived field)<br/>Ad Title (shared dimension) | curated net-new | visible through shared grouping: Ad Title |
| Call to Action | `paidMedia.adDetails.creative.paidMediaCreative.callToAction` | Ad Call to Action (derived field)<br/>Ad Call to Action (shared dimension) | curated net-new | visible through shared grouping: Ad Call to Action |
| Destination URL | `paidMedia.adDetails.creative.paidMediaCreative.destinationURL` | Ad Destination URL (derived field)<br/>Ad Destination URL (shared dimension) | curated net-new | visible through shared grouping: Ad Destination URL |
| Display URL | `paidMedia.adDetails.creative.paidMediaCreative.displayURL` | Ad Display URL (derived field)<br/>Ad Display URL (shared dimension) | curated net-new | visible through shared grouping: Ad Display URL |
| Experience Type | `paidMedia.experienceDetails.experienceType` | Experience Type (derived field)<br/>Experience Type (shared dimension) | curated net-new | visible through shared grouping: Experience Type |
| Landing Page URL | `paidMedia.experienceDetails.landingPageURL` | Experience Landing Page URL (derived field)<br/>Experience Landing Page URL (shared dimension) | curated net-new | visible through shared grouping: Experience Landing Page URL |
| Call To Action | `paidMedia.experienceDetails.callToAction` | Experience Call to Action (derived field)<br/>Experience Call to Action (shared dimension) | curated net-new | visible through shared grouping: Experience Call to Action |
| Card Count | `paidMedia.experienceDetails.carouselProperties.cardCount` | Experience Card Count \| Ad Summary (derived field) | curated net-new | hidden |
| Asset Type | `paidMedia.assetDetails.assetType` | Asset Type (derived field)<br/>Asset Type (shared dimension) | curated net-new | visible through shared grouping: Asset Type |
| Permalink URL | `paidMedia.assetDetails.mediaProperties.permalinkURL` | Asset Permalink URL \| Ad Summary (derived field) | curated net-new | hidden |
| Width | `paidMedia.assetDetails.dimensions.width` | Asset Width (derived field)<br/>Asset Width (shared dimension) | curated net-new | visible through shared grouping: Asset Width |
| Height | `paidMedia.assetDetails.dimensions.height` | Asset Height (derived field)<br/>Asset Height (shared dimension) | curated net-new | visible through shared grouping: Asset Height |
| Aspect Ratio | `paidMedia.assetDetails.dimensions.aspectRatio` | Asset Aspect Ratio (derived field)<br/>Asset Aspect Ratio (shared dimension) | curated net-new | visible through shared grouping: Asset Aspect Ratio |
| Orientation | `paidMedia.assetDetails.dimensions.orientation` | Asset Orientation \| Ad Summary (derived field)<br/>Asset Orientation (shared dimension) | curated net-new | visible through shared grouping: Asset Orientation |
| MIME Type | `paidMedia.assetDetails.fileProperties.mimeType` | Asset MIME Type \| Ad Summary (derived field) | curated net-new | hidden |
| Impressions | `paidMedia.metrics.impressions` | Impressions \| Ad Summary (metric) | existing | visible |
| Clicks | `paidMedia.metrics.clicks` | Clicks \| Ad Summary (metric) | existing | visible |
| Spend | `paidMedia.metrics.spend` | Spend \| Ad Summary (metric) | existing | visible |
| Reach | `paidMedia.metrics.reach` | Reach \| Ad Summary (metric) | curated net-new | visible |
| Conversions | `paidMedia.metrics.conversions` | Conversions \| Ad Summary (metric) | curated net-new | visible |
| Conversion Value | `paidMedia.metrics.conversionValue` | Conversion Value \| Ad Summary (metric) | curated net-new | visible |
| Video Views | `paidMedia.metrics.videoViews` | Video Views \| Ad Summary (metric) | curated net-new | visible |
| Engagements | `paidMedia.metrics.engagements` | Engagements \| Ad Summary (metric) | curated net-new | visible |
| Post-Click Conversions | `paidMedia.conversionMetrics.postClickConversions` | Post-Click Conversions \| Ad Summary (metric) | curated net-new | visible |
| Post-View Conversions | `paidMedia.conversionMetrics.postViewConversions` | Post-View Conversions \| Ad Summary (metric) | curated net-new | visible |
| Purchases | `paidMedia.conversionMetrics.conversionsByType.purchases` | Purchases \| Ad Summary (metric) | curated net-new | visible |
| Add to Cart | `paidMedia.conversionMetrics.conversionsByType.addToCart` | Add to Cart \| Ad Summary (metric) | curated net-new | visible |
| Leads | `paidMedia.conversionMetrics.conversionsByType.leads` | Leads \| Ad Summary (metric) | curated net-new | visible |
| Registrations | `paidMedia.conversionMetrics.conversionsByType.registrations` | Registrations \| Ad Summary (metric) | curated net-new | visible |
| Downloads | `paidMedia.conversionMetrics.conversionsByType.downloads` | Downloads \| Ad Summary (metric) | curated net-new | visible |
| Subscriptions | `paidMedia.conversionMetrics.conversionsByType.subscriptions` | Subscriptions \| Ad Summary (metric) | curated net-new | visible |
| Landing Page View | `paidMedia.conversionMetrics.conversionsByType.landingPageView` | Landing Page Views \| Ad Summary (metric) | curated net-new | visible |
| Total Order Value | `paidMedia.conversionMetrics.totalOrderValue` | Total Order Value \| Ad Summary (metric) | curated net-new | visible |
| Video Plays | `paidMedia.videoMetrics.videoPlays` | Video Plays \| Ad Summary (metric) | curated net-new | visible |
| Video Completions | `paidMedia.videoMetrics.videoCompletions` | Video Completions \| Ad Summary (metric) | curated net-new | visible |
| Link Clicks | `paidMedia.extendedMetrics.linkClicks` | Link Clicks \| Ad Summary (metric) | curated net-new | visible |
| Outbound Clicks | `paidMedia.extendedMetrics.outboundClicks` | Outbound Clicks \| Ad Summary (metric) | curated net-new | visible |
| App Installs | `paidMedia.extendedMetrics.appInstalls` | App Installs \| Ad Summary (metric) | curated net-new | visible |
| Lead Submissions | `paidMedia.extendedMetrics.leadSubmissions` | Lead Submissions \| Ad Summary (metric) | curated net-new | visible |
| Device Type | `paidMedia.dimensionalBreakdowns.deviceType` | | excluded | removed in source range |
| Placement | `paidMedia.dimensionalBreakdowns.placement` | Placement (dimension) | curated net-new | visible through shared grouping: Placement |
| Platform | `paidMedia.dimensionalBreakdowns.platform` | Platform (dimension) | curated net-new | visible through shared grouping: Platform |
| Country | `paidMedia.dimensionalBreakdowns.country` | Country (dimension) | curated net-new | visible through shared grouping: Country |
| Region | `paidMedia.dimensionalBreakdowns.region` | Region (dimension) | curated net-new | visible through shared grouping: Region |
| Other connector-populated fields | See field tables | No named component | excluded | not surfaced |

+++

### Identifiers

| Field name | Description | XDM path | ACA Paid Media component | ACA context label | Meta | Google Ads | Pinterest | Snapchat | TikTok |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Record ID | *Unique record URI, inherited from data/record.* | `@id` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta:{entity}:{ids}`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads:{entity}:{ids}`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (pinterest:&lt;entity&gt;: source-derived composite record ID; GUIDs use pinterest_; writer later emits this as _id.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (snapchat:&lt;entity&gt;: source-derived composite record ID; GUIDs use snapchat_; writer later emits this as _id.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (tiktok:&lt;entity&gt;: source-derived composite record ID; GUIDs use tiktok_; summary IDs omit dimension values; writer emits _id.) |
| Entity Type | The type of paid media entity | `entityType` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) |
| Ad Network | The advertising platform/network | `paidMedia.adNetwork` | Ad Network (dimension) | Ad Network | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads`) | ⚪ (Fixed routing discriminator (pinterest); not a source attribute.) | ⚪ (Fixed routing discriminator (snapchat); not a source attribute.) | ⚪ (Fixed routing discriminator (tiktok); not a source attribute.) |
| Network | Alias of adNetwork for migration from GenStudio templates | `paidMedia.network` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ⚪ (Fixed routing discriminator (pinterest); not a source attribute.) | ⚪ (Fixed routing discriminator (snapchat); not a source attribute.) | ⚪ (Fixed routing discriminator (tiktok); not a source attribute.) |
| Channel | Content channel indicating the source of the data (e.g., Web, Mobile, PaidMedia). Used as a reporting dimension for cross-channel breakdowns. | `paidMedia.channel` | Content Channel (dimension)<br/>Content Channel (shared dimension) | Content Channel (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`PaidMedia`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`PaidMedia`) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) |
| Hierarchy Path | Full hierarchical path showing parent-child relationships (e.g., account_id/campaign_id/adgroup_id/ad_id) | `paidMedia.hierarchyPath` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account ID | Unique identifier for the ad account within the network | `paidMedia.accountID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account GUID | Unique identifier for the ad account across all networks | `paidMedia.accountGUID` | Account GUID (dimension) | Account Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta_` prefix) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads_` prefix) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Campaign ID | Unique identifier for the campaign within the network | `paidMedia.campaignID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Campaign GUID | Unique identifier for the campaign across all networks | `paidMedia.campaignGUID` | Campaign GUID (dimension) | Campaign Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad Group ID | Unique identifier for the ad group/ad set/ad squad within the network | `paidMedia.adGroupID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad Group GUID | Unique identifier for the ad group/ad set/ad squad across all networks | `paidMedia.adGroupGUID` | AdGroup GUID (dimension) | AdGroup Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad ID | Unique identifier for the individual ad within the network | `paidMedia.adID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad GUID | Unique identifier for the individual ad across all networks | `paidMedia.adGUID` | Ad GUID (dimension) | Ad Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Experience ID | Unique identifier for creative experience (multi-asset compositions) within the network | `paidMedia.experienceID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Ad ID on Experience lookup and summaries; null on Ad lookup; asset reverse join recovers ad ID when metadata matches.) |
| Experience GUID | Unique identifier for creative experience (multi-asset compositions) across all networks | `paidMedia.experienceGUID` | Experience GUID \| Ad Summary (dimension)<br/>Experience Id (shared dimension) | Experience Id (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Asset ID | Unique identifier for creative assets (images, videos, etc.) within the network | `paidMedia.assetID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Asset GUID | Unique identifier for creative assets (images, videos, etc.) across all networks | `paidMedia.assetGUID` | Asset GUID \| Ad Summary (dimension)<br/>Asset Id (shared dimension) | Asset Id (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account GUID | Account GUID (class entityIDs hierarchy) | `entityIDs.account.accountGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Account ID | Account ID (class entityIDs hierarchy) | `entityIDs.account.accountID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Campaign GUID | Campaign GUID (class entityIDs hierarchy) | `entityIDs.campaign.campaignGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Campaign ID | Campaign ID (class entityIDs hierarchy) | `entityIDs.campaign.campaignID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group GUID | Ad Group GUID (class entityIDs hierarchy) | `entityIDs.adGroup.adGroupGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group ID | Ad Group ID (class entityIDs hierarchy) | `entityIDs.adGroup.adGroupID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad GUID | Ad GUID (class entityIDs hierarchy) | `entityIDs.ad.adGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad ID | Ad ID (class entityIDs hierarchy) | `entityIDs.ad.adID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Experience GUID | Experience GUID (class entityIDs hierarchy) | `entityIDs.experience.experienceGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Experience ID | Experience ID (class entityIDs hierarchy) | `entityIDs.experience.experienceID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Asset GUID | Asset GUID (class entityIDs hierarchy) | `entityIDs.asset.assetGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Asset ID | Asset ID (class entityIDs hierarchy) | `entityIDs.asset.assetID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group Name | Display name of the ad group/ad set/ad squad. Mirrors metadata.name from the ad group lookup. | `paidMedia.denormalizedNames.adGroupName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Ad group name"))`) | | |
| Ad Name | Display name of the individual ad. Mirrors metadata.name from the ad lookup. | `paidMedia.denormalizedNames.adName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Ad name"))`) | | |
| Campaign Name | Display name of the campaign. Mirrors metadata.name from the campaign lookup. | `paidMedia.denormalizedNames.campaignName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Campaign name"))`) | | |

-->
