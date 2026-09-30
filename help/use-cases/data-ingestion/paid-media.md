---
title: Paid-Media-Daten in Customer Journey Analytics aufnehmen
description: Erfahren Sie, wie Sie Paid-Media-Daten über Adobe Experience Platform-Quell-Connectoren aufnehmen und in Customer Journey Analytics Verbindungen, Datenansichten und Metriken vorbereiten.
solution: Customer Journey Analytics
feature: Use Cases
hold: true
role: Admin
source-git-commit: 7cd3764ebbab83530ebb42f2041aee4bd390d168
workflow-type: tm+mt
source-wordcount: '1589'
ht-degree: 0%
---

# Aufnehmen und Verwenden von Paid-Media-Daten

Zu den Paid-Media-Daten gehören die Anzeigenleistung und Metadaten von Plattformen wie [!DNL Meta Ads], [!DNL Google Ads], [!DNL TikTok] und [!DNL LinkedIn]. In diesem Handbuch wird erläutert, wie Sie diese Daten in Adobe Experience Platform aufnehmen und in Customer Journey Analytics für Berichte und Analysen verfügbar machen.

Paid-Media-Daten durchlaufen in der Regel drei Phasen:

1. Advertising-Plattformen stellen Kampagnen-, Anzeigen-, Asset- und Leistungsdaten bereit.
1. Adobe Experience Platform nimmt diese Daten über einen Quell-Connector auf und speichert sie in den Standard-Paid-Media-Datensätzen.
1. Customer Journey Analytics stellt die Datensätze über eine Verbindung und eine Datenansicht bereit, damit Sie die Daten in Workspace analysieren können.

Paid-Media-Daten werden über Experience Platform-Quell-Connectoren erfasst. Sie können beispielsweise den [!DNL Meta Ads]-Connector in der Kategorie Advertising verwenden. Wenn Sie eine unterstützte Quelle verbinden, stellt Adobe die standardmäßigen Paid-Media-Datensätze auf der Grundlage des globalen Paid-Media-Schemas und der Feldergruppen bereit.

## Voraussetzungen

Stellen Sie sicher, dass Sie in Experience Platform über folgenden Zugriff verfügen:

* Berechtigung zum Anzeigen und Verwalten von Quellen.
* Eine Sandbox zum Arbeiten.
* Berechtigung zum Erstellen von Schemata, Datensätzen und Datenflüssen.

Wenn Sie [!DNL Meta Ads] als Quelle verwenden, stellen Sie sicher, dass auch die folgenden Voraussetzungen erfüllt sind:

* Ein [!DNL Meta Business Manager] mit mindestens einem aktiven Werbekonto, das Kampagnen, Anzeigen, Anzeigen und Assets enthält.
* Eine [!DNL Meta] App, die für die [!DNL Graph API] und [!DNL Marketing API] autorisiert, in der [!DNL Meta] Developer Console konfiguriert und mit [!DNL Business Manager] verknüpft ist.
* Genehmigte `ads_read` und `ads_management` Bereiche für die App.
* Zugriff auf Advertiser-Ebene oder höher für den Benutzer, der die Verbindung autorisiert.
* Zugriff auf die beabsichtigten Werbekonten in der [!DNL Meta]-Benutzeroberfläche überprüft.

Die Authentifizierung beim Connector verwendet [!DNL OAuth 2.0]. Während des Setups melden Sie sich an und gewähren Zugriff auf den Connector. Da Zugriffs-Token ablaufen, sollten Sie darauf vorbereitet sein, die Verbindung erneut zu autorisieren, wenn die Gewährung widerrufen wird.

## Paid-Media-Datenmodell

Paid-Media-Daten verwenden ein Sternschema. Ein [Zusammenfassungsmetrik-Datensatz](#summary-metrics-dataset) dient als Faktentabelle, und sechs Lookup-Datensätze stellen die zugehörigen Dimensionen bereit. Die Lookup-Datensätze werden mit dem Zusammenfassungsmetriken-Datensatz nach Entitäts-`GUID` und nativen ID-Werten für Konten, Kampagnen, Anzeigengruppen, Anzeigen, Assets und Erlebnisse verbunden.

Die Lookup-Datensätze verwenden zwei gemeinsame Bausteine:

* **Objekt-IDs**: Speichert Konto-, Anzeigen-, Anzeigengruppen-, Asset-, Kampagnen- und Erlebnisobjekte. Jedes Objekt enthält einen von Adobe generierten globalen Schlüssel und eine plattformnative ID.
* **Paid Media Core-Metadaten**: Speichert allgemeine beschreibende Felder wie Name, Status, Ziel, Optimierungsziel, Gebotsstrategie, Budgettyp, Budgetwerte, Währung, Zeitzone, Serving-Status, Daten, Werbenetzwerk, Kanal, Hierarchiepfad, Netzwerk und Portfolio-IDs.

In der folgenden Tabelle sind die sechs Lookup-Datensätze zusammengefasst.

| Lookup-Datensatz | Wichtige Inhalte |
|---|---|
| Konto-Suche | Metadaten auf Kontoebene wie Name, Währung, Zeitzone, Status, Ausgabenlimit und Erstellungsdaten |
| Kampagnensuche | Kampagneneinstellungen für Budget, Planung, Targeting, Konversionsverfolgung, Attribution, Platzierungen, hochgestufte Objekte, Ziel und Katalog- oder Store-IDs |
| Anzeigengruppen-Suche | Anzeigengruppen-Metadaten wie Kampagnenverknüpfung, Status, Budget, Optimierungsziele und Zielgruppenbestimmung |
| Anzeigensuche | Kreative Details zur Anzeige wie Assets, Varianten, Dimensionen, Tracking-URLs, call to action, Textkörper, Titel, Ziel-URL, Versandstatus und Prüfungsstatus |
| Asset-Suche | Asset-Eigenschaften wie Dimensionen, Dateidetails, Bildeigenschaften, Medien-URLs, Nutzungsmetadaten, Videometadaten, Beschreibung, Untertyp, Titel und Typ |
| Erlebnissuche | Kreative Gruppierungen auf Erlebnisebene wie Erlebnis-ID, Assets, Titel, Beschreibung und call to action |

### Datensatz für Zusammenfassungsmetriken

Der Datensatz mit Zusammenfassungsmetriken für bezahlte Medien ist der zentrale Zusammenfassungsdatensatz. Jede Zeile stellt normalerweise eine Entität für einen Tag dar und enthält einen Zeitstempel, eine Kennung, einen Ereignistyp, Entitäts-IDs und denormalisierte Namen für das Reporting.

Der Datensatz mit Zusammenfassungsmetriken kann die folgenden Metrikgruppen enthalten:

* **Kernleistung**: Impressionen, Klicks, Clickthrough-Rate, Interaktionen, Interaktionsrate, Konversionen, Konversionsrate, Konversionswert, Leads, Link-Klicks, Downloads und App-Installationen oder -Öffnungen.
* **Kosten und Budget**: tägliche Ausgaben, zugewiesenes und verbleibendes Budget, Geschwindigkeit, Überschreitung oder Unterschreitung, Durchschnittskostenmetriken und Gebotsbeträge.
* **Video**: Videoansichten, Meilensteine mit der Ansichtsrate und durchschnittliche Anzeigedauer.
* **Impression share**: Impressionsanteil, Top-Impressionsanteil und Metriken zum Anteil verlorener Impressionen.
* **Konversionsdetails**: Konversionstypen, Aktionen zum Hinzufügen zum Warenkorb, Checkouts, Aufrufe, Weganfragen, Lead-Formular-Aktivität und andere konversionsbezogene Ereignisse.
* **Social Engagement**: Likes, Kommentare und Follows.
* **Attribution und Pfad**: Details zum Attributionsmodell, Konfidenz, Gewichtungen, Pfadmetriken und Kanalbeitrag.
* **Qualität und Betrug**: Qualitätsbewertungen, Betrugsindikatoren, ungültige Traffic-Raten und Metriken zur Markensicherheit.
* **Dimensionsaufschlüsselungen**: Kanal, Werbenetzwerk, Gerätetyp, Altersgruppe, Geschlecht, Land, Stadt, Sprache, Wochentag, Zielgruppenkategorie, kreatives Format und Aufschlüsselungstyp.

### Standarddatensätze

Wenn Sie eine Paid-Media-Quelle verbinden, stellt Adobe zwölf standardmäßige Paid-Media-Datensätze bereit, die auf den globalen Paid-Media-Schemaklassen und Feldergruppen basieren. Zu diesen Datensätzen gehören die sechs Lookup-Datensätze, der Zusammenfassungsmetriken-Datensatz und unterstützende Datensätze. Alle 12 Datensätze müssen vorhanden sein, damit die Paid-Media-Daten nachgelagert korrekt aufgelöst werden.

* Paid Media-Kampagnensuche
* Paid Media Asset Lookup
* Paid Media Experience Lookup
* Paid Media-Anzeigensuche
* Paid Media AdGroup Lookup
* Paid Media-Konto-Suche
* Bezahlte Medien und demografische Suche
* Zusammenfassung der Paid Media-Erlebnisplatzierung
* Paid Media und geografische Zusammenfassung
* Paid Media-Anzeigenzusammenfassung (Zusammenfassungsmetriken)
* Übersicht über bezahlte Medien-Assets
* Zusammenfassung der Paid Media Asset-Demografie

## Paid-Media-Daten in Adobe Experience Platform aufnehmen

Verwenden Sie den folgenden Prozess, um eine Quelle zu verbinden und Paid-Media-Daten in Experience Platform aufzunehmen:

1. Vergewissern Sie sich, dass Sie über die erforderlichen Experience Platform-Quellberechtigungen und Ad-Platform-Zugriff verfügen.
1. Navigieren Sie in Experience Platform zu **[!UICONTROL Quellen]** > **[!UICONTROL Katalog]** > **[!UICONTROL Advertising]**.
1. Wählen Sie den gewünschten Connector aus, z. B. **[!DNL Meta Ads]**, und klicken Sie dann auf **[!UICONTROL Einrichten]**.
1. Authentifizieren Sie sich bei [!DNL OAuth 2.0], indem Sie sich mit einem Benutzer anmelden, der über den erforderlichen Zugriff auf Advertiser-Ebene verfügt.
1. Wählen Sie die Werbekonten, Entitäten und insight-Daten aus, die Sie aufnehmen möchten.
1. Bestätigen Sie die Zielgruppen-Zuordnungen zum globalen Paid-Media-Schema und stellen Sie sicher, dass die Lookup-Datensätze und der Zusammenfassungsmetriken-Datensatz korrekt bereitgestellt wurden.
1. Geben Sie Datenflusseinstellungen ein, bestätigen Sie die Zieldatensätze und konfigurieren Sie den Aufnahmezeitplan.
1. Speichern Sie den Datenfluss und überwachen Sie die Ausführungen unter **[!UICONTROL Quellen]** > **[!UICONTROL Datenflüsse]**.
1. Überprüfen Sie, ob die standardmäßigen Paid-Media-Datensätze vorhanden sind und Daten enthalten.

Validieren Sie die aufgenommenen Daten, bevor Sie zu Customer Journey Analytics wechseln:

* Bestätigen Sie, dass die `GUID` der Entität und die nativen ID-Werte über die Zusammenfassungsmetriken und Lookup-Datensätze hinweg konsistent ausgefüllt werden.
* Vergewissern Sie sich, dass jede Zeile mit Zusammenfassungsmetriken einen Zeitstempel enthält.
* Vergewissern Sie sich, dass wichtige Reporting-Felder wie Kampagne, Kanal und Netzwerk, Impressionen, Klicks, Ausgaben, Region und Gerätetyp Werte enthalten.
* Vergewissern Sie sich, dass die Währungs- und Zeitzonenwerte in den relevanten Konten konsistent sind.

## Übertragen von Paid-Media-Daten in Customer Journey Analytics

Customer Journey Analytics berichtet nicht direkt über Experience Platform-Datensätze. Stattdessen stellen Sie die Datensätze über eine Verbindung bereit und erstellen dann eine Datenansicht, die die Dimensionen, Metriken und Logik definiert, die im Reporting verwendet werden.

### Erstellen oder Aktualisieren einer Verbindung

Verwenden Sie den folgenden Prozess, um eine Verbindung zu erstellen oder zu aktualisieren:

1. Erstellen oder [&#x200B; Sie in Customer Journey Analytics eine bestehende Verbindung](/help/connections/create-connection.md).
1. Stellen Sie sicher, dass Sie die Sandbox auswählen, die die Paid-Media-Datensätze enthält.
1. Fügen Sie den Datensatz mit Zusammenfassungsmetriken als Zusammenfassungsdaten hinzu.
1. Fügen Sie jeden Lookup-Datensatz als Lookup-Datensatz hinzu und verbinden Sie den Datensatz mit den Zusammenfassungsdaten durch die entsprechenden Entitätskennungen für Konto, Kampagne, Anzeigengruppe, Anzeige, Asset und Erlebnis.
1. Optional können Sie Clickstream-Ereignisdaten hinzufügen, wenn Sie aggregierte Paid-Media-Daten mit freigegebenen Metadaten wie IDs, Trackingcodes oder `UTM` verknüpfen möchten.
1. Überprüfen Sie [Datensatzspezifische Einstellungen](/help/connections/create-connection.md#dataset-settings) für jeden Datensatz.
1. Speichern Sie die Verbindung und bestätigen Sie, dass die Verbindung beginnt, Daten aufzustocken.

Paid-Media-Daten sind aggregierte Daten und basieren nicht auf der Identitätszuordnung auf Personenebene. Die Entitätskennungen in der Zusammenfassungstabelle werden verwendet, um sie mit ähnlichen Identitäten in den Suchtabellen zu verbinden.

### Datenansicht erstellen

Nachdem die Verbindung fertig ist, müssen Sie eine oder mehrere Datenansichten für die Verbindung erstellen oder bearbeiten:


1. Erstellen [&#x200B; bearbeiten Sie in Customer Journey Analytics eine oder mehrere Datenansichten](/help/data-views/create-dataview.md):
1. Standardeinstellungen wie Zeitzone und Währung definieren.
1. Fügen Sie die Komponenten hinzu, die Sie für die gebührenpflichtige Medienanalyse benötigen.

Fügen Sie Komponenten wie die folgenden hinzu:

* **Dimensionen**: Kampagne, Kanal, Anzeigennetzwerk, Anzeigengruppe, Anzeige, Asset, Konto, Region und Gerätetyp.
* **Metriken**: Impressionen, Klicks, Klickrate, Ausgaben, Konversionen, Konversionswert, Interaktionen und relevante Video- oder Impression-Share-Metriken.
* **Abgeleitete Felder**: Normalisieren oder Klassifizieren von Dimensionen mithilfe der [Parsing](/help/data-views/derived-fields/derived-fields.md#url-parse)-, [Regular Expressions](/help/data-views/derived-fields/derived-fields.md#regex-replace)- oder [Lookup](/help/data-views/derived-fields/derived-fields.md#lookup)-Logik, um konsistente Kanal- und Kampagnenwerte in Werbenetzwerken zu erzeugen.
* **Zusammenfassungsgruppierung**: [Kombinieren Sie verwandte Werte aus mehreren Datensätzen zu einer einzigen Reporting-Dimension](/help/data-views/component-settings/summary-data-group.md) z. B. einer einheitlichen Dimension für gebührenpflichtige Kanäle.
* **Berechnete Metriken**: Definieren wiederverwendbarer Effizienzmetriken wie CPC, CPM, CPA, CTR und Konversionsrate.

## Überprüfen

Validieren Sie die Implementierung anhand der folgenden Checkliste.

### Adobe Experience Platform-Prüfungen

* Vergewissern Sie sich, dass Quellberechtigungen und der Zugriff auf die Anzeigenplattform vorhanden sind.
* Überprüfen Sie, ob der Connector authentifiziert ist und der Datenfluss planmäßig ausgeführt wird.
* Vergewissern Sie sich, dass alle zwölf Standarddatensätze vorhanden und ausgefüllt sind.
* Vergewissern Sie sich, dass die Schemas die globalen Paid-Media-Klassen und -Feldergruppen verwenden.
* Vergewissern Sie sich, dass die Felder „Join-Schlüssel“, „Zeitstempel“ und „Schlüssel-Reporting“ ausgefüllt sind.

### Customer Journey Analytics-Prüfungen

* Vergewissern Sie sich, dass die Verbindung den Zusammenfassungsmetrik-Datensatz und die sechs Lookup-Datensätze enthält.
* Vergewissern Sie sich, dass die Datenansicht die erforderlichen Werbedimensionen und Paid-Media-Metriken enthält.
* Bestätigen Sie, dass abgeleitete Felder die Kanal- und Kampagnenwerte erwartungsgemäß normalisieren.
* Bestätigen Sie, dass die Gruppierungsübersicht bei Bedarf Daten aus verschiedenen Netzwerken zusammenfasst.
* Vergewissern Sie sich, dass für die von Ihrem Unternehmen verwendeten Verhältnisse berechnete Metriken definiert sind.
* Vergewissern Sie sich, dass die Workspace-Berichterstellung mit der Quell-Anzeigenplattform-Berichterstellung übereinstimmt.


>[!MORELIKETHIS]
>
>[Quell-Connector für Meta Ads](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/advertising/meta-ads)
>
