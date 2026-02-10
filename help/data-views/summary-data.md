---
title: Zusammenfassungsdaten
description: Erfahren Sie mehr über die Details und Informationen zur Verwendung und Konfiguration von Zusammenfassungsdaten in einer Datenansicht.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: 417443ae-a1ab-483b-a8fd-cff5ee8b6263
source-git-commit: 4f1299595077a1756a6ad0c4f5ef5e0247ab4973
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 96%

---

# Zusammenfassungsdaten

Zusammenfassungsdaten sind Zeitreihendaten, die nicht an eine einzelne Personen-ID gebunden sind. Zusammenfassungsdaten stellen aggregierte Daten auf einer anderen Aggregationsebene dar, z. B. Kampagnen. Sie können diese Daten im Customer Journey Analytics verwenden, um verschiedene Anwendungsfälle zu unterstützen. Beispielsweise Daten, die ein Datum und einen einzelnen Metrikwert enthalten, oder Daten, die mehrere Dimensionen und Metriken enthalten.

Diese Zusammenfassungsdaten können dann zur Darstellung allgemeiner Leistungsindikatoren oder zur Durchführung von Analysen verwendet werden. Beispiele für Zusammenfassungsdaten sind Werbeimpressionen, E-Mail-Öffnungen, Werbeausgaben, Kosten für verkaufte Waren, S&amp;P-Indizes und mehr. Sie können Zusammenfassungsdaten auch verwenden, um Ziele stündlich oder täglich hochzuladen.

>[!NOTE]
>
>Zusammenfassungsdaten sind Zeitreihendaten aus einem Zusammenfassungsdatensatz. Dieser Zusammenfassungsdatensatz basiert auf einem Schema, das die Klasse „XDM-Zusammenfassungsmetriken“ als Basisklasse verwendet.
>Es werden nur Zeitreihendaten unterstützt, die auf „stündlich“ oder „täglich“ basieren.

>[!TIP]
>
>Sie können eine Verbindung und eine Datenansicht konfigurieren und anschließend Berichte zu **ausschließlich** Zusammenfassungsdaten erstellen. Es sind keine zusätzlichen Ereignis-, Profil- oder Lookup-Daten als Teil Ihrer Konfiguration erforderlich.


## Beispiel

Ein Beispiel für die Verwendung von Zusammenfassungsdaten ist die Kombination von zusammengefassten Daten zu Werbekampagnen mit Clickstream-Daten auf der Site für das Reporting.

### Zusammenfassungsdaten

Ihre Zusammenfassungsdaten enthalten die folgenden Daten zu Werbekampagnen.

| Kampagnen-Code | Impressionen | Kosten |
|---|---:|---:|
| abc123 | 1.250 | 1.500 $ |
| def456 | 775 | 650 $ |
| ghi789 | 500 | 500 $ |


### Ereignisdaten

Ihre Clickstream-Daten auf der Site enthalten die folgenden Ereignisse.

| Trackingcode | Klickrate | Umsatz |
|---|---:|---:|
| abc123 | 1.250 | 7.200 $ |
| def456 | 775 | 1.250 $ |
| ghi789 | 500 | 750 $ |

### Kombinierte Daten

Wie in [Kombinierter Ereignisdatensatz](/help/connections/combined-dataset.md) erläutert, erstellt Customer Journey Analytics beim Definieren einer Verbindung einen allgemein kombinierten Ereignisdatensatz. Wenn Sie Ihre Datenansicht für Dimensionen konfigurieren, die aus einem Zusammenfassungsdatensatz stammen, stehen Optionen zum Gruppieren und Ausblenden von Dimensionen zur Vorbereitung des Reportings in Workspace zur Verfügung. Speziell für Zusammenfassungsdaten werden die Zusammenfassungsdaten mit Ereignisdaten kombiniert, basierend auf der Konfiguration [Komponenten von Zusammenfassungsdatengruppen](component-settings/summary-data-group.md).

| Trackingcode | Kampagnen-Code | Impressionen | Kosten | Klickrate | Umsatz |
|---|---|--:|--:|--:|--:|
| abc123 | abc123 | 1.250 | 1.500 $ | 1.250 | 7.200 $ |
| def456 | def123 | 775 | 650 $ | 775 | 1.250 $ |
| ghi789 | ghi789 | 500 | 500 $ | 500 | 750 $ |



### Reporting

Durch die Kombination der zusammengefassten Ereignisdaten und der Clickstream-Daten auf der Site können Sie in Workspace Berichte über Rendite auf Werbeausgaben (Return on Ad Spend, ROAS) erstellen.

| Trackingcode | Impressionen | Kosten | Klickrate | Umsatz | ROAS |
|---|--:|--:|--:|--:|:--|
| abc123 | 1.250 | 1.500 $ | 1.250 | 7.200 $ | 4,80 |
| def456 | 775 | 650 $ | 775 | 1.250 $ | 1,92 |
| ghi789 | 500 | 500 $ | 500 | 750 $ | 1,50 |


### Lookup-Daten

Wenn Sie einen Bericht mit einer Dimension erstellen möchten, die in einem zusätzlichen Lookup-Datensatz definiert ist (z. B. Kampagnenname), müssen Sie die folgenden zusätzlichen Schritte ausführen:

1. Erstellen Sie ein neues abgeleitetes Feld, das die [Lookup](/help/data-views/derived-fields/derived-fields.md#lookup)-Funktion verwendet, um den Kampagnennamen aus dem Lookup-Datensatz zu suchen. In der Definition der [Lookup](/help/data-views/derived-fields/derived-fields.md#lookup)-Funktion verwenden Sie die Übereinstimmung zwischen Kampagnen-Code und Trackingcode, um nach dem Kampagnennamen zu suchen.
1. Fügen Sie das neu erstellte abgeleitete Feld als Dimensionskomponente zu Ihrer Datenansicht hinzu.
1. Konfigurieren Sie die Dimensionskomponente „Kampagnenname“ (aus dem Lookup-Datensatz) so, dass sie eine Gruppierung von Zusammenfassungsdaten mit dem neu erstellten abgeleiteten Feld aufweist.

Im Anwendungsfall [Aufnehmen von und Berichterstellung für Zusammenfassungsdaten](/help/use-cases/data-views/summary-data.md) finden Sie einen detaillierten Artikel darüber, wie Sie Zusammenfassungsdaten in Customer Journey Analytics verwenden und analysieren und darüber berichten können.


## Voraussetzungen

Für eine ordnungsgemäße Verwendung von Zusammenfassungsdaten in Ihren Berichten und Analysen gilt eine Reihe von Voraussetzungen. In den folgenden Abschnitten werden diese Voraussetzungen detailliert beschrieben.

### Granularität und Zeitzone

Beim Konfigurieren des Datensatzes mit den Zusammenfassungsdaten in Customer Journey Analytics wird die Granularität automatisch aus den Daten abgeleitet. Die Auswahlmöglichkeiten für **[!UICONTROL Zeitstempel]** und **[!UICONTROL Zeitzone]** Dropdown-Menü sind deaktiviert, da beide von der Schemadefinition abgeleitet sind.

#### Granularität

Die stündliche und tägliche Granularität Ihrer Zusammenfassungsdaten in einem Datensatz (oder mit verschiedenen Datensätzen) können nicht mit einem einzigen Zusammenfassungsdatenschema gemischt und zugeordnet werden. Wenn Sie beispielsweise über tägliche und stündliche granulare Zusammenfassungsdaten für Werbekampagnendaten verfügen, benötigen Sie zwei Schemata: eines für die täglichen und eines für die stündlichen Zusammenfassungsdaten. Laden Sie dann die relevanten granularen Daten in Datensätze hoch, die mit dem entsprechenden Schema verknüpft sind (laden Sie beispielsweise stündliche Daten in einen Datensatz hoch, der mit dem Schema für stündliche Zusammenfassungsdaten verknüpft ist).

#### Zeitzone

Die Zeitzone der Zusammenfassungsdaten wird auf der Zusammenfassungsschemaebene in Experience Platform definiert. Die Zeitzone gilt nur für stündliche granulare Daten.

- Für die tägliche Granularität geht Experience Platform von UTC aus, es sei denn, im Zeitstempel ist ein Zeitzonenversatz enthalten. Beim Hinzufügen des Zusammenfassungsdatensatzes mit den Daten der täglichen Zusammenfassung ignoriert Customer Journey Analytics die im Schema festgelegte Zeitzonendefinition und berücksichtigt den mit dem Zeitstempel aus den Daten im Datensatz verknüpften Tag.
- Für die stündliche Granularität berücksichtigt Customer Journey Analytics bei der Interpretation des Zeitstempels die Zeitzone, die im Schema für Zusammenfassungsdaten in Experience Platform konfiguriert ist. Die nachstehende Tabelle enthält einige Beispiele für diese Interpretation.

  | Zeitstempel-<br/>Quelldaten | Zeitzonen-<br/>schema | Zeitstempel<br/>Experience<br/>Platform | Zeitzone<br/> Daten-<br/>ansicht | Zeitstempel<br/>Customer<br/>Journey<br>Analytics |
  |---|---|---|:---|---|
  | 2024-07-29T01:00:00 | *standardmäßig GMT* | 2024-07-29T01:00:00 | GMT | 2024-07-29T01:00:00 |
  | 2024-07-29T01:00:00 | *standardmäßig GMT* | 2024-07-29T01:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | *standardmäßig GMT* | 2024-07-30T06:00:00 | GMT | 2024-07-30T06:00:00 |
  | 2024-07-30T01:00:00-05:00 | *standardmäßig GMT* | 2024-07-30T06:00:00 | PST | 2024-07-29T23:00:00 |
  | 2024-08-02 | *standardmäßig GMT* | 2024-08-02T00:00:00 | IST | 2024-08-02T05:00:00 |
  | 2024-07-29T01:00:00 | `America/`<br/>`Los_Angeles` | 2024-07-28T18:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | `Australia/`<br/>`Sydney` | 2024-07-30T17:00:00 | CET | 2024-07-30T08:00:00 |

  Bei Zeitzonen mit einem Versatz von 30 Minuten (z. B. IST, India Standard Time) wird der 30-Minuten-Versatz beim Reporting von Zusammenfassungsdaten ignoriert. Beispiel: 12:30 wird als 12 % :00.


Um sicherzustellen, dass die richtige Zeitzone für Ihre stündlichen granularen Zusammenfassungsdaten verwendet wird, müssen Sie sicherstellen, dass die richtige Zeitzone für das Schema konfiguriert ist, das für Zusammenfassungsdaten verwendet wird.

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
| `$ACCESS_TOKEN`<br/>`$API_KEY`<br/>`$ORG_ID`<br/>`$SANDBOX_NAME` | Weitere Informationen zum Spezifizieren von Werten für diese Variablen finden Sie unter [Authentifizieren von und Zugreifen auf Experience Platform-APIs](https://experienceleague.adobe.com/de/docs/experience-platform/landing/platform-apis/api-authentication). |
| `$SCHEMA_ID` | Die ID Ihres Schemas finden Sie in der Benutzeroberfläche von Experience Platform. Wählen Sie Ihr Zusammenfassungsschema aus der Liste der Schemata aus und suchen Sie im rechten Panel nach **[!UICONTROL API-Nutzung]** > **[!UICONTROL Schema-ID]**. Verwenden Sie diese ID als Wert. |
| `$GRANULARITY` | Geben Sie `hour` oder `day` als Wert an. |
| `$TIMEZONE` | Geben Sie den richtigen Wert für die Zeitzonenkennung aus der Spalte Zeitzonenkennung in der [Liste der Zeitzonen Zeitzonendatenbank](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) an. Beispiel: `America/Los_Angeles`. |

## Komponenteneinstellungen

Stellen Sie sicher, dass die Komponenteneinstellungen für eine Zusammenfassungsdatengruppe identisch sind. Weitere Informationen finden Sie in den [Einstellungen für die Komponenten von Zusammenfassungsdatengruppen](component-settings/summary-data-group.md#same-component-settings).

>[!MORELIKETHIS]
>
>- Ein detailliertes Anwendungsfallbeispiel für das Verwenden und Melde von Zusammenfassungsdaten finden Sie im Artikel [Verwenden von Zusammenfassungsdaten](/help/use-cases/data-views/summary-data.md).
>- Blog: [Wie Zusammenfassungsdaten Adobe Customer Journey Analytics-Datensätze verbessern](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/how-summary-data-enhances-adobe-customer-journey-analytics/ba-p/704635?profile.language=de)

