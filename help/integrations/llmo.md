---
title: LLM Optimizer-Integration
description: Integrieren von LLM Optimizer mit Customer Journey Analytics
feature: Experience Platform Integration
role: User
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
source-git-commit: 3aa4e0c98e9a3e4163dad992e598638892fc88cd
workflow-type: tm+mt
source-wordcount: 2539
ht-degree: 3%

---


# LLM Optimizer-Integration

[Adobe LLM Optimizer](https://experienceleague.adobe.com/de/docs/llm-optimizer/using/home){target="_blank"} ist eine generative KI-First-Anwendung für die Optimierung von generativen Modulen, die Marken dabei hilft, ihre Sichtbarkeit, Genauigkeit und ihren Einfluss in KI-gestützten Suchumgebungen zu verbessern. LLM Optimizer bietet Einblicke in das Markenpräsenz in KI-generierte Antworten, bietet präskriptive Inhaltsempfehlungen und automatisiert Optimierungskorrekturen.

KI ist zu einem primären Erkennungskanal geworden. LLM-Agenten wie ChatGPT, Claude, Copilot und Perplexity crawlen Markeninhalte.

>[!PREREQUISITES]
>
>Sie müssen über ein gebührenpflichtiges LLM Optimizer-Angebot verfügen, das über den verwalteten Connector bereitgestellt und mit Ihrer Experience Platform-Konfiguration verbunden wird.


>[!IMPORTANT]
>
>Im Rahmen dieser Integration erfolgt eine zeitweilige Verarbeitung von LLM Optimizer-Daten in den Vereinigten Staaten. Die Daten werden letztendlich in der von Ihnen festgelegten Region gespeichert, wie in Ihrem Customer Journey Analytics-Vertrag konfiguriert.


## Anwendungsfälle

Sie können von der Integration zwischen Customer Journey Analytics und LLM Optimizer auf zwei Arten profitieren:

* **Eingehende Integration**: Verwenden Sie LLM Optimizer-Daten in Customer Journey Analytics, um den LLM-gesteuerten Traffic (Bot-Crawler, RAG-Anfragen, Agentenaktivität) neben vorhandenen Web-, Mobile- und anderen Datentypen zu messen. Sie können zum Beispiel:

  * Messen Sie den LLM-gesteuerten Traffic anhand der Agentenquelle neben herkömmlichen Kanälen.

  * Identifizieren Sie Inhalte, die stark von LLMs genutzt werden, aber bei der menschlichen Konversion unterdurchschnittlich abschneiden.

  * Erkennen, wo LLM-Agent-Anforderungen über kritische Pfade hinweg fehlschlagen.

  * Vergleichen Sie die LLM-Bot-Nachfrage für eine Seite mit den Konversionen und dem Umsatz dieser Seite in Ihren Web-Daten, abgeglichen auf der URL- und Host-Ebene.

* **Ausgehende Integration**: Senden Sie Customer Journey Analytics-Leistungsdaten an LLM Optimizer, damit Sie die KI-Sichtbarkeit für die LLM-Quellen optimieren können, die Ihnen wertvollen Traffic senden, z. B. ChatGPT oder Perplexity. Sie können zum Beispiel:

  * Erfahren Sie, welche LLM-Quellen menschliche Besucher senden, die anschließend konvertieren oder Umsatz generieren. Customer Journey Analytics misst dies anhand des referenzierten Web-Traffics und nicht anhand des Bot-Datensatzes.
  * Ordnen Sie die LLM-Quellen nach dem nachgelagerten Wert der von ihnen gesendeten menschlichen Besucher. Konzentrieren Sie dann Ihre Arbeit mit der KI-Sichtbarkeit auf die Quellen, die die besten Ergebnisse erzielen.


## Eingehende Integration

LLM-Traffic gelangt auf zwei Arten zu Ihrer Site. Customer Journey Analytics misst jede Richtung aus einer anderen Datenquelle.

Der erste Weg ist eine Person, die eine KI-Antwort liest und sich dann zu Ihrer Site durchklickt. Bei diesem Besuch wird dieselbe JavaScript ausgeführt, die auch die restlichen Web-Daten erfasst. Ihre bestehenden Customer Journey Analytics-Web-Daten umfassen daher den Besuch und die Referrer-Domain, von der der Benutzer an Sie gesendet wurde, z. B. chatgpt.com. Customer Journey Analytics kennzeichnet diese Besuche nicht eigenständig als KI-Traffic. Um sie zu identifizieren und zu gruppieren, erstellen Sie ein abgeleitetes Feld für die Verbindung, das mit den KI-verweisenden Domains übereinstimmt, und erstellen Sie dann Segmente und Berichte für dieses Feld. Siehe [Abgeleitete &#x200B;](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/derived-fields){target="_blank"}. Für diesen Traffic durch Personen ist kein LLM Optimizer-Datensatz erforderlich.

Die zweite Möglichkeit ist ein Bot oder Agent, der Ihre Seiten direkt anfordert. Dazu gehören Crawler, die einen KI-Index erstellen, und Live-Abrufe, die auftreten, wenn ein Benutzer eine Eingabeaufforderung an einen KI-Assistenten sendet. Bei diesen Anfragen wird keine JavaScript ausgeführt, sodass die vorhandenen Web-Daten sie nicht aufzeichnen. Der LLM Optimizer-Datensatz erfasst diesen Traffic von der CDN-Ebene. Im Rest dieses Abschnitts wird dieser Datensatz beschrieben.

### Integrieren des Datensatzes in Customer Journey Analytics

Der LLM Optimizer Managed Connector stellt die Daten als Zusammenfassungsdatensatz für Experience Platform bereit. Um ihn in Customer Journey Analytics zu messen, führen Sie selbst zwei Einrichtungsschritte aus:

1. Erstellen Sie eine Verbindung, die den LLM Optimizer-Datensatz enthält. Siehe [Erstellen oder Bearbeiten einer Verbindung](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-connections/create-connection){target="_blank"}.
2. Erstellen Sie eine Datenansicht für diese Verbindung. Die Datenansicht stellt die folgenden Dimensionen und Metriken in Analysis Workspace zur Verfügung. Siehe [Erstellen oder Bearbeiten einer Datenansicht](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/create-dataview){target="_blank"}.

Der Datensatz:

* Verwendet [Zusammenfassungsdatensätze](/help/data-views/summary-data.md) die auf der Klasse XDM Summary Metrics basieren.
* Sammelt Daten nach URL und Host, Uhrzeit und Anfrageeigenschaften wie Bot-Typ, CDN-Anbieter und Status.

>[!NOTE]
>
>Der LLM Optimizer-Datensatz enthält aggregierte Daten. Sie enthält keine personenbezogenen Daten wie Benutzerkennung, Eingabeaufforderungen oder Antworten.
>

Da es sich um einen Zusammenfassungsdatensatz handelt, können Sie ihn als Lookup-Datensatz behandeln und ihn mit einem Ereignis-Datensatz auf einem Full-URL-Schlüssel verbinden.

LLM Optimizer stellt diesen Schlüssel für Sie in der Dimension **CDN-URL** bereit. Er kombiniert den Host und den angeforderten Pfad zu einer einzigen normalisierten vollständigen URL, ähnlich wie Customer Journey Analytics Web-Daten speichert. Ob der Join erfolgreich ist, hängt von Ihrer eigenen Datenerfassung ab. Ihr Ereignis-Datensatz benötigt ein entsprechendes vollständiges URL-Feld oder ein Feld, das Sie analysieren und normalisieren können, sodass es mit der von LLM Optimizer bereitgestellten URL übereinstimmt. Wenn beide Seiten dieselbe vollständige URL erhalten, stimmt der LLM Optimizer-Eintrag mit der entsprechenden Seite in Ihren Web-Daten überein.

### Über den Datensatz

LLM Optimizer liest Server-seitig CDN-Zugriffsprotokolle und extrahiert Datensätze, bei denen die anfragende Partei ein Bot oder ein automatisierter Agent ist. Da die Daten von der CDN-Ebene stammen, erfasst LLM Optimizer Anfragen von Bots, die kein JavaScript-Tag auslösen. Standard-Web-Analyse-Tools übersehen diesen Traffic vollständig.

Der Datensatz verwendet die **CDN Requests Summary** Feldergruppe. Jedes Feld befindet sich unter einem `cdn` Objekt, sodass die Feldnamen in den Tabellen unten die Form `cdn.<name>` haben, z. B. `cdn.url` und `cdn.botType`.

Jeder Datensatz beschreibt eine Kombination aus Host, URL-Pfad, Bot-Typ, CDN-Provider, Status-Code, Referrer, weitergeleitetem Host und Zeit bis zum ersten Byte für eine Stunde. Wenn dieselbe Kombination mehrmals pro Stunde angezeigt wird, kombiniert Customer Journey Analytics diese Datensätze zu einer Zeile und erhöht die Anzahl der Anfragen. Verwenden Sie die Metrik **CDN Request Count** zur Messung des Volumens. Zeilenanzahl nicht verwenden.

### Dimensionen

Die folgenden Dimensionen können als Komponenten in einer Datenansicht verwendet werden, sobald Sie eine Verbindung eingerichtet haben, die einen LLM Optimizer-Datensatz enthält. Die Spalte **Feld** zeigt das Quellfeld in der Feldergruppe „CDN-Anfragen - Zusammenfassung“ an.

| Dimension | Feld | Beschreibung |
|-----------|-------|-------------|
| CDN-URL | `cdn.url` | Die normalisierte vollständige URL für die Anfrage, die als Join-Schlüssel vorgesehen ist. LLM Optimizer kombiniert den Host und den angeforderten Pfad in einer einzigen URL und normalisiert sie so, dass sie mit dem vollständigen URL-Formular übereinstimmt, das Customer Journey Analytics für Web-Daten speichert. Verwenden Sie diese Dimension, um den LLM Optimizer-Lookup-Datensatz mit einem Ereignis-Datensatz zu verbinden, der ein entsprechendes vollständiges URL-Feld hat. Sie enthält den Host und den Pfad, aber nicht das Schema. |
| CDN-URL-Pfad | `cdn.path` | Der Pfad der Roh-URL und die vom Agenten angeforderte Abfragezeichenfolge, wie vom CDN bereitgestellt. Enthält weder das Schema noch den Host. Verwenden Sie diese Option, wenn Sie den exakten angeforderten Pfad anstelle des normalisierten Join-Schlüssels benötigen. |
| CDN-Host | `cdn.host` | Der Hostname, der die Anfrage erhalten hat, z. B. www.example.com. Dieser Host ist auch Teil des CDN-URL-Join-Schlüssels. Ein Datensatz kann mehrere Hosts enthalten, wenn eine Organisation mehrere Subdomains im selben CDN-Konto hat. |
| CDN-Bot-Typ | `cdn.botType` | Klassifizierung des anfragenden Agenten durch LLM Optimizer. Die Werte umfassen klassische Such-Crawler, KI-Index-Crawler und KI-Live-Fetch-Agenten. Die vollständige Taxonomie finden [&#x200B; in den &#x200B;](#bot-agent-categories)Bot-Agentenkategorien“ unten. |
| CDN-Benutzeragent | `cdn.userAgent` | Die unformatierte Benutzeragenten-Zeichenfolge aus dem CDN-Protokoll. Nützlich für die Unterscheidung von Untertypen innerhalb einer Bot-Klassifizierung oder für die Validierung der von LLM Optimizer zugewiesenen Klassifizierung. |
| CDN-HTTP-Status | `cdn.status` | Der HTTP-Antwort-Status-Code. Gibt an, ob der Bot den angeforderten Inhalt erhalten hat. Siehe [Status-Codes](#status-codes) unten für Interpretationsanleitungen, die speziell für KI-Traffic gelten. |
| CDN-Anbieter | `cdn.cdnProvider` | Welches CDN die Anfrage verarbeitet hat. Werte sind `akamai`, `byocdn-akamai`, `byocdn-fastly` und `byocdn-cloudfront`. Das `byocdn-` Präfix gibt den Protokollerfassungspfad an, nicht einen anderen CDN-Anbieter. Ein Datensatz kann mehrere Werte enthalten, wenn eine Organisation Hosts hinter verschiedenen CDN-Konfigurationen hat. |
| CDN-Referrer | `cdn.referer` | Der Wert der HTTP-Referer-Kopfzeile aus dem CDN-Protokoll. Oft leer für Bot-Traffic. Wenn vorhanden, kann es angeben, welches KI-Produkt oder welche Domain den Abruf ausgelöst hat. Beispiel: chat.openai.com. |
| CDN-Weiterleitungs-Host | `cdn.xForwardedHost` | Der Header-Wert für X-Forwarded-Host, falls vorhanden. Relevant, wenn die Anfrage vor dem Erreichen des Ursprungs über einen Reverse-Proxy oder eine CDN-Abschirmschicht weitergeleitet wurde. |
| CDN-Ereignisdatum | Abgeleitet vom Zeitstempel des Datensatzes | Der Datumsteil des stündlichen Batch-Zeitstempels für diesen Datensatz. |
| CDN-Ereignisstunde | Abgeleitet vom Zeitstempel des Datensatzes | Der Stundenteil des stündlichen Batch-Zeitstempels für diesen Datensatz. |

### Bot-Agentenkategorien

Die Dimension **CDN Bot Type** organisiert Agenten in drei Kategorien. Jede Kategorie beantwortet eine andere analytische Frage.

**Classic Search Crawler** Indexinhalte für herkömmliche Suchmaschinen. Verwenden Sie diese Kategorie, um zu messen, wie sichtbar Ihre Inhalte für traditionelle Suchmaschinen sind.

| Bot-Typwert | Anbieter | Beschreibung |
|---|---|---|
| `GoogleBot` | Google | Googles Hauptsuchindex-Crawler. Dient auch Google Discover und Google News. |
| `BingBot` | Microsoft | In: Bing’s Search Index Crawler. Außerdem wird der Web-Basisindex von Microsoft Copilot befüllt. |

**KI-Index-Crawler** crawlen Inhalte zum Erstellen oder Aktualisieren des Trainings-Korpus oder Suchindex eines KI-Produkts. Diese Crawler bereiten die Wissensdatenbank eines Modells vor und reagieren nicht auf eine Live-Benutzeranfrage. Wenn eine URL ein hohes Crawler-Volumen hat, halten KI-Anbieter diese Inhalte für indizierenswert. Wenn eine URL ein geringes Crawler-Volumen, aber ein hohes Live-Abrufvolumen aufweist, nutzt das Modell das zwischengespeicherte Wissen, anstatt neue Inhalte abzurufen.

| Bot-Typwert | Anbieter | Beschreibung |
|---|---|---|
| `GPTBot` | OpenAI | OpenAIs primäre Crawler für Modellschulungsdaten und Wissensdatenbankerstellung. |
| `OAI-SearchBot` | OpenAI | OpenAI-Crawler für das Websuchprodukt von ChatGPT. Anders als GPTBot. Dieser Agent erstellt den Echtzeit-Suchindex, nicht den Trainings-Corpus. |
| `ClaudeBot` | menschenliebend | Anthropics primäre Crawler für Modelltrainingsdaten. |
| `Claude-SearchBot` | menschenliebend | Crawler von Anthropic für Claudes Such- und Abrufindex. Unterscheidet sich von ClaudeBot. |
| `PerplexityBot` | Verwirrung | Index-Crawler der Ratlosigkeit. Perplexity verwendet diesen Agenten, um den Korpus für die Antworterstellung zu erstellen. |

**AI-Live-**: Tritt auf, wenn ein echter Benutzer eine Eingabeaufforderung an einen KI-Assistenten sendet und der Assistent die Seite live abruft, bevor er reagiert. Verwenden Sie diese Kategorie, um die direkte Benutzernachfrage zu messen, die über KI-Assistenten eingeht.

| Bot-Typwert | Anbieter | Beschreibung |
|---|---|---|
| `ChatGPT-User` | OpenAI | Ein Benutzer hat ChatGPT eine Frage gestellt. ChatGPT hat diese URL abgerufen, um sie zu lesen und ihre Antwort zu erhalten. |
| `ChatGPT Clients` | OpenAI | Die Mobile App ChatGPT (iOS und Android) führt einen Live-Abruf durch. Die Benutzeragenten-Zeichenfolge enthält die App-Version und das Gerät. |
| `Claude-User` | menschenliebend | Ein Benutzer oder eine Anwendung, der/die Claude live nutzt, hat diese URL abgerufen. Die user-agent-Zeichenfolge kann das spezifische Claude-Produkt identifizieren, z. B. Claude-Code. |
| `Perplexity-User` | Verwirrung | Ein Benutzer stellte „Perplexität“ eine Frage. Diese URL wurde von der Unübersichtlichkeit abgerufen, um ihre Antwort zu verfälschen. |
| `Google-NotebookLM` | Google | Ein Benutzer hat Google NotebookLM geöffnet und diese Domain bezogen. NotebookLM ruft jede erreichbare URL innerhalb einer Quell-Domain ab. |
| `Google-ai-mode` | Google | Die Funktion KI-Übersichten von Google Search hat diese URL abgerufen, um sie in ein von KI generiertes Antwortfeld in die Suchergebnisse aufzunehmen. |
| `Gemini-Deep-Research` | Google | Ein Benutzer führte eine Gemini Deep Research Session durch. Deep Research führt viele sequenzielle Abrufe aus mehreren Quellen durch, um einen Forschungsbericht zu erstellen. |
| `GoogleAgent-URLContext` | Google | Ein Benutzer gab eine URL für Gemini frei und stellte Fragen zu dieser Seite. Gemini hat die URL live abgerufen, um Fragen zu diesem spezifischen Inhalt zu beantworten. |
| `Amzn-User` | Amazon | Ein Amazon Alexa- oder Amazon AI-Agent hat diese URL live abgerufen. Wird normalerweise in Referenz- und Dokumentationsinhalten angezeigt. |
| `MistralAI-User` | Mistral | Ein Live-Abruf von einem Mistral-gestützten Produkt oder API-Verbraucher. |

Wenn LLM Optimizer einen Benutzeragenten nicht mit einem erkannten Muster abgleichen kann, wird der Wert `Unknown` zugewiesen. Sie können die Dimension **CDN User Agent** verwenden, um zu ermitteln, welcher Agent diese Anfragen gestellt hat.

### Status-Codes

HTTP-Status-Codes in diesem Datensatz geben an, ob der KI-Agent den angeforderten Inhalt erhalten hat.

| Status | Name | Interpretation |
|--------|------|----------------|
| 200 | OK | Der Bot erhielt die vollständige Antwort. Der Inhalt war für die KI verfügbar. |
| 304 | Nicht geändert | Der Bot hat bestätigt, dass sich der Inhalt nicht geändert hat und seine zwischengespeicherte Version verwendet. Der Inhalt war verfügbar. |
| 301 | Dauerhaft verschoben | Der Bot wurde an eine neue URL umgeleitet. Jede Umleitung fügt eine zusätzliche Hin- und Rückfahrt hinzu. Ein hohes 301-Volumen bei häufig crawlen URLs bedeutet, dass die Umleitung auf CDN-Ebene aufgelöst werden sollte. |
| 302 | gefunden (temporäre Umleitung) | Latenzstrafe wie 301. Im Gegensatz zu 301 signalisiert es keine dauerhafte Verschiebung, sodass Bots weiterhin die ursprüngliche URL erreichen. |
| 403 | Verboten | Das CDN oder der Ursprung hat den Bot blockiert. Dies kann absichtlich sein, z. B. durch robots.txt-Regeln oder WAF-Richtlinien, oder unbeabsichtigt, z. B. durch zu weit gefasste Ratenbeschränkungen. Wenn KI-Abrufe blockiert werden, kann dieser Inhalt nicht in KI-Antworten angezeigt werden. |
| 404 | Nicht gefunden | URL existiert nicht. Ein hohes Volumen von 404 bei KI-Agententypen deutet darauf hin, dass der Index der KI veraltete URLs enthält. Verwenden Sie den 410-Status, um den Crawler mitzuteilen, eine URL dauerhaft aus ihrem Index zu entfernen. |
| 429 | Zu viele Anfragen | Der Bot wurde durch die CDN-Rate eingeschränkt. Anhaltende 429-Fehler bei Live-Fetch-Agententypen bedeuten, dass Benutzende, die KI-Assistenten Fragen zu Ihren Inhalten stellen, unvollständige oder fehlende Antworten erhalten. |
| 504 | Gateway-Zeitüberschreitung | Das CDN hörte auf, auf eine Antwort des Ursprungs zu warten. Der Inhalt hat die KI nicht erreicht. Wenn für eine Seite eine Zeitüberschreitung auftritt, kann die KI nicht auf ihren Inhalt zugreifen und ihn nicht in eine Antwort einschließen. Ein hohes Volumen von 504 bei Live-Fetch-Agententypen stellt ein Risiko für die direkte KI-Sichtbarkeit dar. |

### Metriken

Die folgenden Metriken können als Komponenten in einer Datenansicht verwendet werden, sobald Sie eine Verbindung eingerichtet haben, die einen LLM Optimizer-Datensatz enthält. Die Spalte **Feld** zeigt das Quellfeld in der Feldergruppe „CDN-Anfragen - Zusammenfassung“ an.

| Metrik | Feld | Beschreibung |
|--------|-------|-------------|
| CDN-Anfragenanzahl | `cdn.requests` | Die Gesamtzahl der CDN-Anfragen, zusammengefasst aus dem Anfragefeld über alle Zeilen hinweg. Verwenden Sie diese Metrik immer, um das Volumen zu messen. Zeilenanzahl nicht verwenden. |
| CDN-Fehleranzahl | `cdn.status`, `cdn.requests` | Die Anzahl der Anfragen, die einen HTTP-Status-Code 4xx oder 5xx zurückgegeben haben. |
| CDN-Fehlerrate | Abgeleitet von CDN-Fehleranzahl | Die Fehleranzahl als Prozentsatz der gesamten Anfragen. |
| Durchschn. CDN-Zeit bis zum ersten Byte | `cdn.timeToFirstByte` | Die durchschnittliche Zeit in Millisekunden ab dem Zeitpunkt, zu dem das CDN eine Anfrage empfangen hat, bis zum ersten Byte der Antwort. CDN-zwischengespeicherte Antworten dauern in der Regel weniger als 50 ms. Die von der Quelle gesendeten Antworten betragen normalerweise 300 ms bis 700 ms. KI-Live-Fetch-Agenten weisen häufig deutlich höhere Werte auf, die mit einer Zeitüberschreitung oder sehr langsamen Ursprungsreaktionen korrespondieren. Hohe Durchschnittswerte für Live-Fetch-Agententypen sind es wert, als Risiko für die KI-Sichtbarkeit untersucht zu werden. |

### Datensatzgrenzen

Dieser Datensatz erfasst nur Traffic von Bots aus CDN-Zugriffsprotokollen. Sie enthält nicht Folgendes:

* **Benutzersitzungen, Konversionen oder Interaktionsdaten.** Ein Benutzer, der auf eine KI-Antwort klickt, führt die JavaScript auf Ihrer Seite aus, sodass der Besuch in Ihren vorhandenen Web-Daten erfolgt und nicht in diesem Datensatz. Sie können beide Datensätze in Customer Journey Analytics importieren und sie für dieselbe URL und denselben Host vergleichen.
* **Beliebige Personenkennung wie ECID.** Aus diesem Datensatz kann kein Join auf Personenebene erstellt werden. Der Join wird auf URL- und Host-Ebene ausgeführt.
* **Granularität der Subsekundenzeit.** Der Zeitstempel ist stündlich. Sie können den Traffic nicht innerhalb einer Stunde in Minuten oder Sekunden unterteilen.
* **Seiteninhalt oder gerenderte HTML.** Dieser Datensatz zeichnet die Tatsache des Abrufs und dessen Ergebnis auf, nicht das, was die KI von der Seite gelesen hat.
* **Konversionsdaten.** Dieser Datensatz sagt Ihnen nicht, ob eine KI-Antwort eine Person veranlasst hat, Ihre Site zu besuchen oder zu konvertieren. Es enthält aggregierte CDN-Zusammenfassungsdaten, keine personenbasierten Ereignisdaten, sodass keine Anfrage mit einer einzelnen Person oder Sitzung verknüpft wird.

## Ausgehende Integration

Noch festzulegen.


<!-- 

# LLM Optimizer integration

[Adobe LLM Optimizer](https://experienceleague.adobe.com/en/docs/llm-optimizer/using/home){target="_blank"} is a generative AI-first application for Generative Engine Optimization, designed to help brands enhance their visibility, accuracy, and influence in AI-driven search environments. LLM Optimizer provides insights into brand presence in AI-generated answers, offers prescriptive content recommendations, and automates optimization fixes.

AI has become a primary discovery channel. LLM agents, such as ChatGPT, Claude, Copilot, and Perplexity, crawl and reference brand content. 

>[!PREREQUISITES]
>
>You must have an LLM Optimizer paid offering provisioned and connected to your Experience Platform configuration through the managed connector.


>[!IMPORTANT]
>
>As part of this integration, some temporary processing of LLM Optimizer data occurs in the United States. Data is ultimately stored in your designated region as configured in your Customer Journey Analytics contract.


## Use cases

You can benefit from the integration between Customer Journey Analytics and LLM Optimizer in two ways:

* **Inbound integration**: Use LLM Optimizer data in Customer Journey Analytics to measure LLM-driven traffic (bot crawlers, RAG requests, agent activity) alongside existing web, mobile, and other types of data. For example, to address the following use cases:
  
  * Measure LLM-driven traffic by agent source alongside traditional channels.
  
  * Identify content that is heavily consumed by LLMs but underperforms in human conversion.
  
  * Detect where LLM-agent requests fail across critical paths.

  * Correlate LLM activity with downstream business outcomes (revenue, conversions, engagement).
  
* **Outbound integration**: Use Customer Journey Analytics performance data inside LLM Optimizer so AI visibility can be optimized for real business outcomes. For example, to address the following use cases:

  * Evaluate how each LLM agent correlates with revenue, conversions, and engagement.
  * Identify which LLM agents are associated with stronger downstream performance. Which LLM agents are associated with higher engagement or conversion rates.


## Inbound integration

To ingest LLM Optimizer data into Customer Journey Analytics, use the LLM Optimizer datasets available in Experience Platform. The ingestion method:

* Uses [summary datasets](/help/data-views/summary-data.md) that are based on the XDM Summary Schema class.
* Buckets data by URL/host, time, and request characteristics such as bot type, CDN provider, and status.

>[!NOTE]
>
>The LLM Optimizer dataset contains aggregated data that does not contain any PII, such as user identifiers, prompts, or responses.
>

You use the LLM Optimizer dataset in a connection. Because the dataset is a summary dataset, you can use the dataset as a lookup dataset and potentially join to an event dataset on a full-URL key.

LLM Optimizer provides this key for you in the **CDN URL** dimension. The key combines the host and the requested path into a single normalized full URL, similar to how Customer Journey Analytics stores web data. This join-key field facilitates the join. The outcome depends on your Customer Journey Analytics implementation and whether your event dataset has a page URL field that matches the URL representation LLM Optimizer provides. When both sides resolve to the same full URL, the LLM Optimizer record matches the corresponding page in your web data.

### About the dataset

LLM Optimizer reads CDN access logs on the server side and extracts records where the requesting party is a bot or automated agent. Because the data comes from the CDN layer, LLM Optimizer captures requests from bots that do not execute any JavaScript tag. Standard web analytics tools miss this traffic entirely.

Each record describes one combination of host, URL path, bot type, CDN provider, status code, referrer, forwarded host, and time to first byte for one hour. When the same combination appears multiple times hourly, Customer Journey Analytics combines those records into one row and increases the request count. Use the **CDN Request Count** metric to measure volume. Do not use row count.

### Dimensions

The following dimensions are available to use as components in a data view once you have set up a connection that includes an LLM Optimizer dataset.

| Dimension | Description |
|-----------|-------------|
| CDN URL | The normalized full URL for the request, intended as the join key. LLM Optimizer combines the host and the requested path into a single URL and normalizes it to match the full-URL form that Customer Journey Analytics stores for web data. Use this dimension to join the LLM Optimizer lookup dataset to an event dataset that has an equivalent full-URL field. It includes the host and path, but not the scheme. |
| CDN URL Path | The raw URL path and query string that the agent requested, as delivered by the CDN. Does not include the scheme or host. Use this when you need the exact requested path rather than the normalized join key. |
| CDN Host | The hostname that received the request, for example, www.example.com. This host is also part of the CDN URL join key. A dataset can contain multiple hosts when an organization has multiple subdomains on the same CDN account. |
| CDN Bot Type | LLM Optimizer's classification of the requesting agent. Values cover classic search crawlers, AI index crawlers, and AI live-fetch agents. See the [Bot agent categories](#bot-agent-categories) below for the full taxonomy. |
| CDN User Agent | The raw user-agent string from the CDN log. Useful for distinguishing sub-types within a bot classification, or for validating the classification assigned by LLM Optimizer. |
| CDN HTTP Status | The HTTP response status code. Indicates whether the bot received the content it requested. See the [Status codes](#status-codes) below for interpretation guidance specific to AI traffic. |
| CDN Provider | Which CDN handled the request. Values are `akamai`, `byocdn-akamai`, `byocdn-fastly`, and b`yocdn-cloudfront`. The `byocdn-` prefix indicates the log collection pathway, not a different CDN vendor. A dataset can contain multiple values when an organization has hosts behind different CDN configurations. |
| CDN Referrer | The HTTP Referer header value from the CDN log. Often empty for bot traffic. When present, it can indicate which AI product or domain triggered the fetch. For example, chat.openai.com. |
| CDN Forwarded Host | The X-Forwarded-Host header value, if present. Relevant when the request passed through a reverse proxy or CDN shield layer before reaching the origin. |
| CDN Event Date | The date part of the hourly batch timestamp for this record. |
| CDN Event Hour | The hour part of the hourly batch timestamp for this record. |

### Bot agent categories

The **CDN Bot Type** dimension organizes agents into three categories. Each category answers a different analytical question.

**Classic search crawlers** index content for traditional search engines. Use this category to measure how visible your content is to traditional search engines.

| Bot type value | Vendor | Description |
|---|---|---|
| `GoogleBot` | Google | Google's main search index crawler. Also serves Google Discover and Google News. |
| `BingBot` | Microsoft | Bing's search index crawler. Also feeds Microsoft Copilot's web grounding index. |

**AI index crawlers** crawl content to build or update an AI product's training corpus or search index. These crawlers are preparing a model's knowledge base, not responding to a live user request. When a URL has high crawler volume, AI vendors consider that content worth indexing. When a URL has low crawler volume but high live-fetch volume, the model draws from cached knowledge rather than fetching fresh content.

| Bot type value | Vendor | Description |
|---|---|---|
| `GPTBot` | OpenAI | OpenAI's primary crawler for model training data and knowledge base construction. |
| `OAI-SearchBot` | OpenAI | OpenAI's crawler for ChatGPT's web search product. Distinct from GPTBot. This agent builds the real-time search index, not the training corpus. |
| `ClaudeBot` | Anthropic | Anthropic's primary crawler for model training data. |
| `Claude-SearchBot` | Anthropic | Anthropic's crawler for Claude's search and retrieval index. Distinct from ClaudeBot. |
| `PerplexityBot` | Perplexity | Perplexity's index crawler. Perplexity uses this agent to build the corpus for its answer generation. |

**AI live fetches** occur when a real user submits a prompt to an AI assistant and the assistant fetches the page live before responding. Use this category to measure direct user demand arriving through AI assistants.

| Bot type value | Vendor | Description |
|---|---|---|
| `ChatGPT-User` | OpenAI | A user asked ChatGPT a question. ChatGPT fetched this URL to read it and form its answer. |
| `ChatGPT Clients` | OpenAI | The ChatGPT mobile app (iOS and Android) doing a live fetch. The user-agent string includes the app version and device. |
| `Claude-User` | Anthropic | A user or application using Claude live-fetched this URL. The user-agent string may identify the specific Claude product, e.g., claude-code. |
| `Perplexity-User` | Perplexity | A user asked Perplexity a question. Perplexity fetched this URL to ground its answer. |
| `Google-NotebookLM` | Google | A user opened Google NotebookLM and sourced this domain. NotebookLM fetches every reachable URL within a sourced domain. |
| `Google-ai-mode` | Google | Google Search's AI Overviews feature fetched this URL to include it in an AI-generated answer panel in search results. |
| `Gemini-Deep-Research` | Google | A user ran a Gemini Deep Research session. Deep Research makes many sequential fetches across multiple sources to compile a research report. |
| `GoogleAgent-URLContext` | Google | A user shared a URL with Gemini and asked questions about that page. Gemini fetched the URL live to answer questions about that specific content. |
| `Amzn-User` | Amazon | An Amazon Alexa or Amazon AI agent live-fetched this URL. Typically appears on reference and documentation content. |
| `MistralAI-User` | Mistral | A live fetch from a Mistral-powered product or API consumer. |

When LLM Optimizer cannot match a user-agent to a recognized pattern, it assigns the value `Unknown`. You can use the **CDN User Agent** dimension to identify what agent made those requests.

### Status codes

HTTP status codes in this dataset indicate whether the AI agent received the content it requested.

| Status | Name | Interpretation |
|--------|------|----------------|
| 200 | OK | The bot received the full response. The content was available for the AI to use. |
| 304 | Not Modified | The bot confirmed the content has not changed and used its cached version. The content was available. |
| 301 | Moved Permanently | The bot was redirected to a new URL. Each redirect adds an extra round-trip. High 301 volume on frequently crawled URLs means the redirect should be resolved at the CDN level. |
| 302 | Found (Temporary Redirect) | Same latency penalty as 301. Unlike 301, it does not signal a permanent move, so bots will keep hitting the original URL. |
| 403 | Forbidden | The CDN or origin blocked the bot. This can be intentional, e.g., through robots.txt rules or WAF policy, or unintentional, e.g., through overly broad rate limits. When AI fetches are blocked, that content cannot appear in AI answers. |
| 404 | Not Found | The URL does not exist. High 404 volume on AI agent types indicates the AI's index contains stale URLs. Use the 410 status to tell crawlers to remove a URL from their index permanently. |
| 429 | Too Many Requests | The CDN rate-limited the bot. Sustained 429 errors on live-fetch agent types mean that users asking AI assistants questions about your content will receive incomplete or missing responses. |
| 504 | Gateway Timeout | The CDN stopped waiting for the origin to respond. The content did not reach the AI. When a page times out, the AI cannot access its content and cannot include it in an answer. High 504 volume on live-fetch agent types is a direct AI visibility risk. |

### Metrics

The following metrics are available to use as components in a data view once you have set up a connection that includes an LLM Optimizer dataset.

| Metric | Description |
|--------|-------------|
| CDN Request Count | The total count of CDN requests, summed from the requests field across all rows. Always use this metric to measure volume. Do not use row count. |
| CDN Error Count | The count of requests that returned a 4xx or 5xx HTTP status code. |
| CDN Error Rate | The error count as a percentage of total requests. |
| CDN Avg Time to First Byte | The average time in milliseconds from when the CDN received a request to the first byte of the response. CDN-cached responses are typically under 50ms. Responses served from the origin are typically 300ms to 700ms. AI live-fetch agents often show much higher values, which correspond to timed-out or very slow origin responses. High average values on live-fetch agent types are worth investigating as an AI visibility risk. |

### Dataset boundaries

This dataset captures only bot traffic from CDN access logs. It does not contain the following:

* **Human sessions, conversions, or engagement data.** Human sessions are in your existing web analytics dataset. To correlate AI demand with human outcomes, join the two datasets in CJA at the URL and host level.
* **Any person identifier such as ECID.** You cannot make a person-level join from this dataset. The join works at the URL and host level.
* **Sub-second time granularity.** The timestamp is hourly. You cannot break down traffic within an hour into minutes or seconds.
* **Page content or rendered HTML.** This dataset records the fact of the fetch and its outcome, not what the AI read from the page.
* **Conversion data.** Whether an AI answer led a user to visit the site or convert is not in this dataset. That analysis requires joining to human session data in CJA.

## Outbound integration

To be determined.

-->