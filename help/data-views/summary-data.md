---
title: Zusammenfassungsdaten
description: Details und Informationen zur Verwendung und Konfiguration von Zusammenfassungsdaten in einer Datenansicht.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: 417443ae-a1ab-483b-a8fd-cff5ee8b6263
source-git-commit: 6cd4fadc28117ed88b68d17274ab8de2b0edff10
workflow-type: tm+mt
source-wordcount: '1135'
ht-degree: 7%

---

# Zusammenfassungsdaten

Zusammenfassungsdaten sind Zeitreihendaten, die nicht an eine einzelne Personen-ID gebunden sind. Zusammenfassungsdaten stellen aggregierte Daten auf einer anderen Aggregationsebene dar, z. B. Kampagnen. Sie können diese Daten im Customer Journey Analytics verwenden, um verschiedene Anwendungsfälle zu unterstützen. Beispielsweise Daten, die ein Datum und einen einzelnen Metrikwert enthalten, oder Daten, die mehrere Dimensionen und Metriken enthalten.

Diese Zusammenfassungsdaten können dann zur Darstellung allgemeiner Leistungsindikatoren oder zur Durchführung von Analysen verwendet werden. Beispiele für Zusammenfassungsdaten sind Werbeeindrücke, E-Mail-Öffnungen, Werbeausgaben, Umsatzkosten, S&amp;P-Indizes und mehr. Sie können auch Zusammenfassungsdaten verwenden, um Ziele oder Ziele stündlich oder täglich hochzuladen.

>[!NOTE]
>
>Zusammenfassungsdaten sind Zeitreihendaten aus einem zusammenfassenden Datensatz. Dieser zusammenfassende Datensatz basiert auf einem Schema, das die Klasse XDM Summary Metrics als Basisklasse verwendet.
>Es werden nur stündliche oder tägliche Zeitreihendaten unterstützt.

>[!TIP]
>
>Sie können eine Verbindung und eine Datenansicht konfigurieren und anschließend Berichte zu (**)** erstellen. Es sind keine zusätzlichen Ereignis-, Profil- oder Lookup-Daten als Teil Ihrer Konfiguration erforderlich.


## Beispiel

Ein Beispiel für die Verwendung von Zusammenfassungsdaten ist die Kombination von zusammengefassten Daten von Werbekampagnen mit Clickstream-Daten auf der Site für das Reporting.

### Zusammenfassungsdaten

Ihre Zusammenfassungsdaten enthalten die folgenden Daten zu Werbekampagnen.

| Kampagnen-Code | Impressions | Kosten |
|---|---:|---:|
| ABC123 | 1.250 | 1 500 $ |
| DEF456 | 775 | 650 $ |
| GHI789 | 500 | 500 $ |


### Ereignisdaten

Ihre Clickstream-Daten auf der Site enthalten die folgenden Ereignisse.

| Trackingcode | Clickthrough-Rate | Umsatz |
|---|---:|---:|
| ABC123 | 1.250 | 7 200 $ |
| DEF456 | 775 | 1 250 $ |
| GHI789 | 500 | 750 $ |

### Kombinierte Daten

Wie in [Kombinierter Ereignisdatensatz](/help/connections/combined-dataset.md) erläutert, erstellt Customer Journey Analytics beim Definieren einer Verbindung einen kombinierten Ereignis-Datensatz. Wenn Sie Ihre Datenansicht für Dimensionen konfigurieren, die aus einem zusammenfassenden Datensatz stammen, stehen Optionen zum Gruppieren und Ausblenden von Dimensionen zur Vorbereitung des Reportings in Workspace zur Verfügung. Speziell für Zusammenfassungsdaten werden die Zusammenfassungsdaten mit Ereignisdaten kombiniert, basierend auf der Konfiguration [Zusammenfassungsdatengruppen-Komponente](component-settings/summary-data-group.md).

| Trackingcode | Kampagnen-Code | Impressions | Kosten | Clickthrough-Rate | Umsatz |
|---|---|--:|--:|--:|--:|
| ABC123 | ABC123 | 1.250 | 1 500 $ | 1.250 | 7 200 $ |
| DEF456 | DEF123 | 775 | 650 $ | 775 | 1 250 $ |
| GHI789 | GHI789 | 500 | 500 $ | 500 | 750 $ |



### Berichterstellung

Durch die Kombination der zusammengefassten Ereignisdaten und der Clickstream-Daten auf der Site können Sie in Workspace Berichte über den Return on Ad Spend (ROAS) erstellen.

| Trackingcode | Impressions | Kosten | Clickthrough-Rate | Umsatz | ROAS |
|---|--:|--:|--:|--:|:--|
| ABC123 | 1.250 | 1 500 $ | 1.250 | 7 200 $ | 4,80 |
| DEF456 | 775 | 650 $ | 775 | 1 250 $ | 1,92 |
| GHI789 | 500 | 500 $ | 500 | 750 $ | 1,50 |


### Lookup data

Wenn Sie einen Bericht mit einer Dimension erstellen möchten, die in einem zusätzlichen Lookup-Datensatz definiert ist (z. B. Kampagnenname), müssen Sie die folgenden zusätzlichen Schritte ausführen:

1. Erstellen Sie ein neues abgeleitetes Feld, das die [Lookup](/help/data-views/derived-fields/derived-fields.md#lookup)-Funktion verwendet, um den Kampagnennamen aus dem Lookup-Datensatz zu suchen. In der Definition der Funktion [Lookup](/help/data-views/derived-fields/derived-fields.md#lookup) verwenden Sie die Übereinstimmung zwischen Kampagnen-Code und Trackingcode, um den Kampagnennamen zu suchen.
1. Fügen Sie das neu erstellte abgeleitete Feld als Dimensionskomponente zu Ihrer Datenansicht hinzu.
1. Konfigurieren Sie die Dimensionskomponente „Kampagnenname“ (aus dem Lookup-Datensatz) so, dass sie eine Gruppierung von Zusammenfassungsdaten mit dem neu erstellten abgeleiteten Feld aufweist.

Siehe [Aufnehmen und Erstellen von Berichten zu ](/help/use-cases/data-views/summary-data.md), Anwendungsfall für einen detaillierten Artikel zur Verwendung, Berichterstellung und Analyse von Zusammenfassungsdaten im Customer Journey Analytics.


## Voraussetzungen

Für eine ordnungsgemäße Verwendung von Zusammenfassungsdaten in Ihren Berichten und Analysen gelten eine Reihe von Voraussetzungen. In den folgenden Abschnitten werden diese Voraussetzungen detailliert beschrieben.

### Granularität und Zeitzone

Beim Konfigurieren des Datensatzes, der die Zusammenfassungsdaten auf Customer Journey Analytics enthält, wird die Granularität automatisch von den Daten abgeleitet. Die Auswahlen für **[!UICONTROL Zeitstempel]** und **[!UICONTROL Zeitzone]** Dropdown-Liste sind deaktiviert, da beide von der Schemadefinition abgeleitet sind.

#### Granularität

Die stündliche und tägliche Granularität Ihrer Zusammenfassungsdaten in einem Datensatz (oder mit verschiedenen Datensätzen) kann nicht mit einem einzigen Zusammenfassungsdatenschema gemischt und zugeordnet werden. Wenn Sie beispielsweise über tägliche und stündliche granulare Zusammenfassungsdaten für Werbekampagnendaten verfügen, benötigen Sie zwei Schemata: eines für die tägliche und eines für die stündliche Zusammenfassungsdaten. Laden Sie dann die relevanten granularen Daten in Datensätze hoch, die mit dem entsprechenden Schema verknüpft sind (laden Sie beispielsweise stündliche Daten in einen Datensatz hoch, der mit dem Schema für stündliche Zusammenfassungsdaten verknüpft ist).

#### Zeitzone

Die Zeitzone der Zusammenfassungsdaten wird auf der Zusammenfassungsschemaebene in Experience Platform definiert. Die Zeitzone gilt nur für stündliche granulare Daten.

- Für die tägliche Granularität geht Experience Platform von UTC aus, es sei denn, im Zeitstempel ist ein Zeitzonenversatz enthalten. Beim Hinzufügen des Zusammenfassungsdatensatzes mit den Daten der täglichen Zusammenfassung ignoriert Customer Journey Analytics die im Schema festgelegte Zeitzonendefinition und berücksichtigt den mit dem Zeitstempel aus den Daten im Datensatz verknüpften Tag.
- Für die Granularität „Stündlich“ berücksichtigt Customer Journey Analytics bei der Interpretation des Zeitstempels die Zeitzone, die im Zusammenfassungsdatenschema auf Experience Platform konfiguriert ist. Die nachstehende Tabelle enthält einige Beispiele für diese Interpretation.

  | Zeitstempel <br/>Quelldaten | timezone<br/>schema | timestamp<br/>experience<br/>platform | Zeitzone<br/> data<br/>view | Zeitstempel<br/>Kunde<br/>Journey<br>Analytics |
  |---|---|---|:---|---|
  | 29.07.2024 T01:00:00 | *Standard-GMT* | 29.07.2024 T01:00:00 | GMT | 29.07.2024 T01:00:00 |
  | 29.07.2024 T01:00:00 | *Standard-GMT* | 29.07.2024 T01:00:00 | PST | 28.07.2024:00:1800 |
  | 30.07.2024:00:01.00-05:00 | *Standard-GMT* | 30.07.2024 T06:00:00 | GMT | 30.07.2024 T06:00:00 |
  | 30.07.2024:00:01.00-05:00 | *Standard-GMT* | 30.07.2024 T06:00:00 | PST | 29.07.2024 T23:00:00 |
  | 02.08.2024 | *Standard-GMT* | 02.08.2024:00:000 | IST | 02.08.2024:00:00 |
  | 29.07.2024 T01:00:00 | `America/`<br/>`Los_Angeles` | 28.07.2024:00:1800 | PST | 28.07.2024:00:1800 |
  | 30.07.2024:00:01.00-05:00 | `Australia/`<br/>`Sydney` | 30.07.2024 T17:00:00 | CET | 30.07.2024 T08:00:00 |

  Bei Zeitzonen mit einem 30-Minuten-Offset (z. B. IST, India Standard Time) wird der 30-Minuten-Offset beim Reporting von Zusammenfassungsdaten ignoriert. Beispiel: 12:30 Uhr wird als 12:00 Uhr gemeldet.


Um sicherzustellen, dass die richtige Zeitzone für Ihre stündlichen granularen Zusammenfassungsdaten verwendet wird, müssen Sie sicherstellen, dass für das Schema, das für Zusammenfassungsdaten verwendet wird, die richtige Zeitzone konfiguriert ist.

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
| `$ACCESS_TOKEN`<br/>`$API_KEY`<br/>`$ORG_ID`<br/>`$SANDBOX_NAME` | Weitere [ zum Angeben von Werten für diese Variablen finden Sie ](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/api-authentication) „Authentifizieren und Zugreifen auf Experience Platform-APIs“. |
| `$SCHEMA_ID` | Sie finden die ID Ihres Schemas in der Experience Platform-Benutzeroberfläche. Wählen Sie Ihr Zusammenfassungsschema aus der Liste der Schemata aus und suchen Sie im rechten Bedienfeld **[!UICONTROL API]** > **[!UICONTROL Schema-ID]**. Verwenden Sie diese ID als Wert. |
| `$GRANULARITY` | Geben Sie `hour` oder `day` als Wert an. |
| `$TIMEZONE` | Geben Sie den richtigen Wert für die Zeitzonenkennung aus der Spalte TZ-Kennung in der [Liste der Zeitzonen der tz-Datenbank](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) an. Beispiel: `America/Los_Angeles`. |

## Komponenteneinstellungen

Stellen Sie sicher, dass die Komponenteneinstellungen für eine Datenzusammenfassung identisch sind. Weitere [ finden Sie unter ](component-settings/summary-data-group.md#same-component-settings) der Datengruppen-Zusammenfassungskomponenten .

>[!MORELIKETHIS]
>
>Ein detailliertes Anwendungsbeispiel für [ Verwendung von Zusammenfassungsdaten und ](/help/use-cases/data-views/summary-data.md) Berichten zu Zusammenfassungsdaten finden Sie im Artikel „Verwenden von Zusammenfassungsdaten“.
