---
title: In Customer Journey Analytics verfügbare Komponenten Daten-Feeds
description: Erfahren Sie, welche Dimensionen und Metriken erforderlich, nicht unterstützt, eingeschränkt oder beim Erstellen von Customer Journey Analytics-Daten-Feeds ersetzt werden müssen.
hide: true
feature: Components
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
source-git-commit: d7614102d54af57a3a084c8550041f8e04f4bc37
workflow-type: tm+mt
source-wordcount: '1391'
ht-degree: 44%
---
# Komponentenverfügbarkeit in Daten-Feeds

{{release-limited-testing}}

Nicht alle Customer Journey Analytics-Komponenten können in Daten-Feeds verwendet werden. Einige Dimensionen sind in jedem Daten-Feed enthalten, einige Komponenten können nicht einbezogen werden und einige Metriken müssen durch einen Ersatz ersetzt werden.

Verwenden Sie die folgenden Informationen, um zu verstehen, welche Komponenten Sie beim [Erstellen eines Daten-Feeds) &#x200B;](/help/components/exports/cja-data-feeds/create-feed.md) können.

## Erforderliche Dimensionen {#required-dimensions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_required_dimensions"
>title="Erforderliche Dimensionen"
>abstract="Jeder Daten-Feed muss bestimmte Dimensionen enthalten, die durch ein Label **Erforderlich** neben dem Dimensionsnamen gekennzeichnet sind. Diese Dimensionen stellen die Mindeststruktur bereit, die für Analysen auf Ereignisebene erforderlich ist."

<!-- markdownlint-enable MD034 -->

Die folgenden Dimensionen sind standardmäßig in jedem Daten-Feed enthalten und können nicht entfernt werden:

| Name der Dimension | Anmerkungen | Daten-Feeds | Sonstige Berichte |
|---|---|---|---|
| Zeitstempel – UTC | Datum und Uhrzeit des Ereignisses, dargestellt in UTC-Zeitzone. Unterstützt die Granularität von Subsekunden (Mikrosekunden). | erforderlich | Nicht verfügbar |
| Zeilen-ID | Die eindeutige Kennung für jede Zeile, die im Daten-Feed enthalten ist. | erforderlich | Nicht verfügbar |
| Sitzungs-ID | Die eindeutige Kennung für jede Sitzung, die im Daten-Feed enthalten ist. | erforderlich | Nicht verfügbar |
| Personen-ID | Die Personenkennung für die Datenansicht und die Verbindung | erforderlich | Optionaler Standard |
| Konto-ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Konto-ID bei Verwendung des Konto-Containers | erforderlich | Optionaler Standard |

## Nicht unterstützte Dimensionen {#unsupported-dimensions}

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

## Nicht unterstützte Metriken {#unsupported-metrics}

Die folgenden Customer Journey Analytics-Standardmetriken können nicht in Daten-Feeds enthalten sein:

| Metrikname | Anmerkungen | Daten-Feeds |
|---|---|---|
| Adobe-Besucherprofil | | Nicht verfügbar |
| Adobe Opportunities Union | | Nicht verfügbar |
| Adobe Opportunities-Profil | | Nicht verfügbar |
| Adobe-Kontovereinigung | | Nicht verfügbar |
| Adobe-Kontoprofil | | Nicht verfügbar |
| Adobe-Einkaufsgruppengewerkschaft | | Nicht verfügbar |
| Adobe-Einkaufsgruppenprofil | | Nicht verfügbar |
| Adobe Global Accounts Union | | Nicht verfügbar |
| Globales Kontoprofil von Adobe | | Nicht verfügbar |
| Adobe Persons Union | | Nicht verfügbar |
| Adobe Persons Profile | | Nicht verfügbar |

## Dimensionen, die nicht zusammen verwendet werden können {#incompatible-dimensions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_user_agent"
>title=""
>abstract="Benutzer-Agent-Daten und Gerätesuchdaten können nicht in derselben Daten-Feed-Konfiguration vorhanden sein."

<!-- markdownlint-enable MD034 -->

>[!IMPORTANT]
>
>Bestimmte Dimensionen können nicht zusammen in Experience Platform-Datensätzen verwendet werden und können daher nicht in denselben Daten-Feed aufgenommen werden.
>
>Wenn Sie sich dafür entscheiden, entweder die **Benutzeragent**- oder **Mobile ID**-Dimensionen in Ihren Daten-Feed aufzunehmen, können die unten aufgeführten Dimensionen nicht zum Daten-Feed hinzugefügt werden.
>
>Wenn Sie die Web-SDK verwenden, wird diese Einschränkung in Datenströmen erzwungen, bevor Daten in einem Experience Platform-Datensatz eingehen. Weitere Informationen finden Sie unter [Konfigurieren der Gerätesuche](https://experienceleague.adobe.com/de/docs/experience-platform/datastreams/configure#geolocation-device-lookup) in [Erstellen und Konfigurieren von &#x200B;](https://experienceleague.adobe.com/de/docs/experience-platform/datastreams/configure)) im Datenerfassungshandbuch.

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
* Mobile Push To Talk
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

## Metriken, die einen Ersatz erfordern {#substitute-metrics}

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

## Optionale Standardkomponenten {#optional-standard-components}

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
