---
title: Automatische Konfiguration für bezahlte Medien in Content Analytics
description: Erfahren Sie mehr über die automatische Konfiguration von Datensätzen, Verbindungen, Datenansichten und mehr.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
source-git-commit: 2727dce145b996192ac873dd43d5106b011ff736
workflow-type: tm+mt
source-wordcount: '1493'
ht-degree: 4%
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

![Generierung von Zusammenfassungsdatensätzen über bezahlte Medien](/help/content-analytics/assets/paid-media-generation-of-datasets.svg)

Welche Zusammenfassungsdatensätze erstellt werden, wird durch das spezifische Anzeigennetzwerk bestimmt. Nicht jedes Anzeigennetzwerk, für das Sie einen Quell-Connector konfiguriert haben, generiert alle sechs möglichen Zusammenfassungsdatensätze. In der folgenden Tabelle finden Sie eine Übersicht über die Zusammenfassungsdatensätze mit den folgenden Informationen:

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

| Zusammenfassung Datensatz<br/>Ereignis-Typ<br/>Komponenten-Suffix | Entität | Aufschlüsselung | ![MetaMulti](/help/assets/icons2/MetaSolid.svg) | ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) | ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) | ![Snapchat](/help/assets/icons2/Snapchat.svg) | ![TikTok](/help/assets/icons2/TikTok.svg) | Jede Zeile stellt Folgendes dar |
|---|---|---|:---:|:---:|:---:|:---:|:---:|---|
| `paidmedia_ad_summary` <br/> `ad.summary`<br/>`\| Ad Summary` | Anzeige | Keine | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | Die tägliche Leistung einer Anzeige ohne demografische oder geografische Aufschlüsselungen. |
| `paidmedia_ad_demographics` <br/> `ad.demographics`<br/>`\| Ad Demo` | Anzeige | Alter, Geschlecht | ![Häkchen](/help/assets/icons2/Checkmark.svg) | | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | Die tägliche Leistung einer Anzeige ist nach Alter und Geschlecht aufgeschlüsselt. |
| `paidmedia_ad_geography` <br/> `ad.geography`<br/>`\| Ad Geo` | Anzeige | Land, Region | ![Häkchen](/help/assets/icons2/Checkmark.svg) | | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | Die tägliche Leistung einer Anzeige nach Land und Region. |
| `paidmedia_experience_placement` <br/> `ad.experience.placement`<br>`\| Experience Placement` | Erlebnis | Plattform, Position | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | Tägliche Leistung in Verbindung mit dem kreativen Erlebnis einer Anzeige, aufgeschlüsselt nach Plattform und Position. |
| `paidmedia_asset_summary` <br/>`ad.asset.summary`<br/>`\| Asset Summary` | Asset | Keine | ![Häkchen](/help/assets/icons2/Checkmark.svg) | ![Häkchen](/help/assets/icons2/Checkmark.svg) | | | ![Häkchen](/help/assets/icons2/Checkmark.svg) | Tägliche Leistung auf Asset-Ebene im Anzeigen-/Kampagnenkontext, ohne demografische oder geografische Aufschlüsselung. |
| `paidmedia_assets_demographics` <br/> `ad.asset.demographics`<br/>`\| Asset Demo` | Asset | Alter, Geschlecht | ![Häkchen](/help/assets/icons2/Checkmark.svg) | | | | | Tägliche Leistung auf Asset-Ebene im Anzeigen-/Kampagnenkontext, aufgeschlüsselt nach Alter und Geschlecht. |


Diese Tabelle beschreibt die Datensatzabdeckung und ist keine Garantie dafür, dass jede Metrik oder jedes Metadatenfeld von einem bestimmten Netzwerk ausgefüllt wird. Überprüfen Sie die für Ihre Analyse erforderlichen Felder. Ein nicht verfügbares Feld oder eine nicht unterstützte Aufschlüsselung ist nicht dasselbe wie ein gemessener Nullwert für ein Feld.

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

Jede Klicks-Metrik-Komponente liefert einen anderen Berichtskontext. Sie können diese Metrikkomponenten nicht einfach in einem Gesamtwert zusammenfassen. Dieselbe zugrunde liegende Werbeaktivität kann in mehr als einem Zusammenfassungsdatensatz dargestellt werden.

### Dimensionen

Jeder Zusammenfassungsdatensatz enthält IDs und GUIDs. Die ID ist die Identität (für Konto, Kampagne, Anzeigengruppe, Anzeige, Erlebnis und Asset), die vom Werbenetzwerk bereitgestellt wird, und ist eindeutig **innerhalb** der Werbenetzwerkdaten. Die GUID ist eine von Adobe bereitgestellte Identität (für Konto, Kampagne, Anzeigengruppe, Anzeige, Erlebnis und Asset) und ist **über** Anzeigennetzwerke hinweg eindeutig. IDs und GUIDs werden verwendet, um die entsprechenden Namen und Metadaten zu suchen.

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

### Beispiel für die Anzeigenkampagnenleistung

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

### Beispiel für Netzwerke mit der besten Leistung von Anzeigen

Sie möchten wissen, wo Ihre Meta-Anzeigen am besten abschneiden?

Verwenden Sie zur Untersuchung zusätzliche Aufschlüsselungen für Geografie und Demografie. Verwenden Sie den Kampagnennamen oder Anzeigenamen als Dimension und verwenden Sie die Metriken wie in der folgenden Tabelle beschrieben. Jede Metrik hat dasselbe Komponenten-Suffix.

| Metrik | Berichterstellungsebene |
| --- | --- |
| Impressionen | Geografie hinzufügen |
| Klicks | Geografie hinzufügen |
| Ausgaben | Anzeigenzusammenfassung |
| Clickthrough-Rate | Geografie hinzufügen |
| Kosten pro Klick | Anzeigenzusammenfassung |


