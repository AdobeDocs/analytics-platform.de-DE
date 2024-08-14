---
title: Zusammenfassungsdaten
description: Details und Informationen zur Verwendung und Konfiguration von Zusammenfassungsdaten in einer Datenansicht.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 9517d698acf41a25fa972ced32faa75de540a080
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 4%

---


# Zusammenfassungsdaten

{{release-limited-testing}}

Zusammenfassungsdaten sind Zeitreihendaten, die nicht an eine individuelle Personen-ID gebunden sind. Zusammenfassungsdaten stellen aggregierte Daten auf einer anderen Aggregationsebene dar, z. B. Kampagnen. Sie können diese Daten im Customer Journey Analytics verwenden, um verschiedene Anwendungsfälle zu unterstützen. Beispielsweise Daten, die ein Datum und einen einzelnen Metrikwert enthalten, oder Daten, die mehrere Dimensionen und Metriken enthalten.

Diese Zusammenfassungsdaten können dann verwendet werden, um allgemeine Leistungsindikatoren darzustellen oder Analysen durchzuführen. Beispiele für Zusammenfassungsdaten sind Werbeimpressionen, E-Mail-Öffnungen, Werbeausgaben, Kosten des guten Verkaufs, S&amp;P-Indizes und mehr. Sie können auch Zusammenfassungsdaten verwenden, um Ziele stündlich oder täglich hochzuladen.

>[!NOTE]
>
>Zusammenfassungsdaten sind Zeitreihendaten aus einem Zusammenfassungsdatensatz. Dieser Zusammenfassungsdatensatz basiert auf einem Schema, das die Klasse &quot;XDM-Zusammenfassungsmetriken&quot;als Basisklasse verwendet.
>Es werden nur stündliche oder tägliche Zeitreihendaten unterstützt.

>[!TIP]
>
>Sie können eine Verbindung konfigurieren, eine Datenansicht anzeigen und anschließend einen Bericht für die Zusammenfassungsdaten **nur** erstellen. Es ist nicht erforderlich, zusätzliche Ereignis-, Profil- oder Suchdaten als Teil Ihrer Konfiguration zu haben.


## Beispiel

Ein Beispiel für die Verwendung von Zusammenfassungsdaten ist die Kombination von zusammengefassten Kampagnendaten mit Clickstream-Daten auf der Site zur Berichterstellung.

### Zusammenfassungsdaten

Ihre Zusammenfassungsdaten enthalten die folgenden Daten einer Werbekampagne.

| Kampagnencode | Impressions | Kosten |
|---|---:|---:|
| abc123 | 1.250 | 1.500 $ |
| def456 | 775 | 650 $ |
| ghi789 | 500 | 500$ |


### Ereignisdaten

Ihre Clickstream-Daten auf der Site enthalten die folgenden Ereignisse.

| Trackingcode | Clickthrough-Rate | Umsatz |
|---|---:|---:|
| abc123 | 1.250 | 7.200 $ |
| def456 | 775 | 1.250 $ |
| ghi789 | 500 | 750 $ |

### Kombinierte Daten

Wie in [Datensatz mit kombinierten Ereignissen](/help/connections/combined-dataset.md) erläutert, erstellt Customer Journey Analytics beim Definieren einer Verbindung einen Datensatz mit kombinierten Ereignissen. Wenn Sie Ihre Datenansicht für Dimensionen konfigurieren, die aus einem Zusammenfassungsdatensatz stammen, stehen Optionen zum Gruppieren und Ausblenden von Dimensionen als Vorbereitung für Berichte in Workspace zur Verfügung. Insbesondere für Zusammenfassungsdaten werden die Zusammenfassungsdaten anhand der Konfiguration der [Zusammenfassungsdatengruppenkomponente](component-settings/summary-data-group.md) mit Ereignisdaten kombiniert.

| Trackingcode | Kampagnencode | Impressions | Kosten | Clickthrough-Rate | Umsatz |
|---|---|--:|--:|--:|--:|
| abc123 | abc123 | 1.250 | 1.500 $ | 1.250 | 7.200 $ |
| def456 | def123 | 775 | 650 $ | 775 | 1.250 $ |
| ghi789 | ghi789 | 500 | 500$ | 500 | 750 $ |



### Berichterstellung

Durch die Kombination der zusammengefassten Ereignisdaten mit den Clickstream-Daten auf der Site können Sie in Workspace einen Bericht zur Rendite aus Werbeausgaben (ROAS) erstellen.

| Trackingcode | Impressions | Kosten | Clickthrough-Rate | Umsatz | ROAS |
|---|--:|--:|--:|--:|:--|
| abc123 | 1.250 | 1.500 $ | 1.250 | 7.200 $ | 4,80 |
| def456 | 775 | 650 $ | 775 | 1.250 $ | 1,92 |
| ghi789 | 500 | 500$ | 500 | 750 $ | 1,50 |


Ein detaillierter Artikel zur Verwendung, Berichterstellung und Analyse von Zusammenfassungsdaten in Customer Journey Analytics finden Sie im Anwendungsfall [Zusammenfassungsdaten erfassen und melden](/help/use-cases/data-views/summary-data.md) .


## Voraussetzungen

Damit Zusammenfassungsdaten in Ihren Berichten und Analysen richtig verwendet werden können, müssen einige Voraussetzungen erfüllt sein. Die folgenden Abschnitte beschreiben diese Voraussetzungen.

### Granularität und Zeitzone

Beim Konfigurieren des Datensatzes, der die Zusammenfassungsdaten in Customer Journey Analytics enthält, stellen Sie fest, dass die Granularität automatisch aus den Daten abgeleitet wird. Die Auswahlen für die Dropdown-Liste **[!UICONTROL Zeitstempel]** und **[!UICONTROL Zeitzone]** sind deaktiviert, da beide von der Schemadefinition abgeleitet werden.

#### Granularität

Sie können die stündliche und tägliche Granularität Ihrer Zusammenfassungsdaten nicht in einem Datensatz (oder mit verschiedenen Datensätzen) mit einem Zusammenfassungsdatenschema mischen. Wenn Sie beispielsweise über tägliche und stündliche Zusammenfassungsdaten für Werbekampagnen-Daten verfügen, benötigen Sie zwei Schemata: eines für die täglichen und eines für die stündlichen Zusammenfassungsdaten. Laden Sie dann die relevanten granularen Daten in Datensätze hoch, die mit dem entsprechenden Schema verknüpft sind (z. B. Hochladen stündlicher Daten in einen Datensatz, der mit dem Datenschema der stündlichen Zusammenfassung verknüpft ist).

#### Zeitzone

Die Zeitzone Ihrer Zusammenfassungsdaten wird auf der Ebene des Zusammenfassungsschemas unter Experience Platform definiert. Die Zeitzone gilt nur für stündlich granulare Daten.

- Für die tägliche Granularität nimmt Experience Platform UTC an, es sei denn, der Zeitzonenversatz ist im Zeitstempel enthalten. Beim Hinzufügen des Zusammenfassungsdatensatzes mit den täglichen Zusammenfassungsdaten ignoriert Customer Journey Analytics die im Schema festgelegte Zeitzonendefinition und berücksichtigt den mit dem Zeitstempel verknüpften Tag aus den Daten im Datensatz.
- Für die Granularität &quot;Stündlich&quot;berücksichtigt Customer Journey Analytics bei der Interpretation des Zeitstempels die Zeitzone, die im Zusammenfassungsdatenschema in Experience Platform konfiguriert ist. Die nachstehende Tabelle enthält einige Beispiele für diese Interpretation.

  | Zeitstempel <br/>Quelldaten | Zeitzone<br/>schema | Zeitstempel<br/>Erlebnis<br/>Plattform | Zeitzone<br/> data<br/>view | Zeitstempel<br/>Kunde<br/>Journey<br>Analytics |
  |---|---|---|:---|---|
  | 29.7.2024:00:00 | *default GMT* | 29.7.2024:00:00 | GMT | 29.7.2024:00:00 |
  | 29.7.2024:00:00 | *default GMT* | 29.7.2024:00:00 | PST | 28.7.2024:00:00 |
  | 2024-07-30T01:00:00-05:00 | *default GMT* | 2024-07-30T06:00:00 | GMT | 2024-07-30T06:00:00 |
  | 2024-07-30T01:00:00-05:00 | *default GMT* | 2024-07-30T06:00:00 | PST | 29.7.2024:00:00 |
  | 02.08.2024 | *default GMT* | 2024-08-02T00:00:00 | IST | 08.08.2024:00:00 |
  | 29.7.2024:00:00 | `America/`<br/>`Los_Angeles` | 28.7.2024:00:00 | PST | 28.7.2024:00:00 |
  | 2024-07-30T01:00:00-05:00 | `Australia/`<br/>`Sydney` | 2024-07-30T17:00:00 | CET | 2024-07-30T08:00:00 |

  Bei Zeitzonen mit einem Zeitversatz von 30 Minuten (z. B. IST, India Standard Time) wird der 30-minütige Versatz bei der Berichterstellung für Zusammenfassungsdaten verworfen. Beispiel: 12:30 wird als 12:00 gemeldet.


Um sicherzustellen, dass die richtige Zeitzone für Ihre stündlichen granularen Zusammenfassungsdaten verwendet wird, müssen Sie sicherstellen, dass das für Zusammenfassungsdaten verwendete Schema die richtige Zeitzone konfiguriert hat.

Um die Granularität und Zeitzone für Ihr Zusammenfassungsdatenschema zu konfigurieren, müssen Sie den folgenden API-Aufruf verwenden, da keine entsprechende Benutzeroberfläche verfügbar ist.

```shell
curl -X POST \
https://platform.adobe.io/data/foundation/schemaregistry/tenant/descriptors \
 -H "Authorization: Bearer {$ACCESS_TOKEN}" \
 -H 'Content-Type: application/json' \
 -H 'x-api-key: {$API_KEY}' \
 -H 'x-gw-ims-org-id: {$ORG_ID}' \
 -H 'x-sandbox-name: {$SANDBOX_NAME}' \
 -d '{  
    "@type": "xdm:descriptorTimeSeriesGranularity",
    "xdm:sourceSchema": "{$SCHEMA_ID}",
    "xdm:sourceVersion": 1,
    "xdm:granularity": "{$GRANULARITY}",
    "xdm:ianaTimezone": "{$TIMEZONE}" 
 }'
```

| Variable | Wert |
|---|---|
| `$ACCESS_TOKEN`<br/>`$API_KEY`<br/>`$ORG_ID`<br/>`$SANDBOX_NAME` | Weitere Informationen zum Angeben von Werten für diese Variablen finden Sie unter [Authentifizieren und Zugreifen auf Experience Platform-APIs](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/api-authentication) . |
| `$SCHEMA_ID` | Die ID Ihres Schemas finden Sie in der Experience Platform-Benutzeroberfläche. Wählen Sie Ihr Zusammenfassungsschema aus der Liste der Schemas aus und suchen Sie im rechten Bereich nach der **[!UICONTROL API-Nutzung]** > **[!UICONTROL Schema-ID]** . Verwenden Sie diese ID als Wert. |
| `$GRANULARITY` | Geben Sie `hour` oder `day` als Wert an. |
| `$TIMEZONE` | Geben Sie den richtigen Wert für die Zeitzonen-ID in der Spalte &quot;TZ-Kennung&quot;in der [Liste der tz-Datenbankzeitzonen](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) an. Beispiel: `America/Los_Angeles`. |

## Einstellungen der Komponente

Stellen Sie sicher, dass die Komponenteneinstellungen für eine Zusammenfassungsdatengruppe identisch sind. Weitere Informationen finden Sie unter [Einstellungen der Datengruppen-Komponente &quot;Zusammenfassung&quot;](component-settings/summary-data-group.md#same-component-settings) .

>[!MORELIKETHIS]
>
>Im Artikel [Zusammenfassungsdaten aufnehmen und verwenden](/help/use-cases/data-views/summary-data.md) finden Sie ein detailliertes Anwendungsbeispiel zur Verwendung und Berichterstellung für Zusammenfassungsdaten.
