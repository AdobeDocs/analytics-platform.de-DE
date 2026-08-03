---
title: Markensichtbarkeit-Integration
description: Integrieren von Markensichtbarkeit mit Customer Journey Analytics
feature: Experience Platform Integration
role: User
source-git-commit: e90a8d978f8d910f426dcb0fbf28881724d0f5a7
workflow-type: tm+mt
source-wordcount: '2543'
ht-degree: 3%

---


# Adobe Brand Visibility-Integration

[Adobe Brand Visibility](https://experienceleague.adobe.com/de/docs/llm-optimizer/using/home){target="_blank"} ist eine generative KI-First-Anwendung für die Optimierung von generativen Modulen, die Marken dabei hilft, ihre Sichtbarkeit, Genauigkeit und ihren Einfluss in KI-gestützten Suchumgebungen zu verbessern. Markensichtbarkeit bietet Einblicke in das Markenpräsenz in KI-generierte Antworten, bietet präskriptive Inhaltsempfehlungen und automatisiert Optimierungskorrekturen.

KI ist zu einem primären Erkennungskanal geworden. Agenten für große Sprachmodelle (LLM) wie ChatGPT, Claude, Copilot und Perplexity crawlen Markeninhalte.

>[!PREREQUISITES]
>
>Sie müssen über ein gebührenpflichtiges Markensichtbarkeit-Angebot verfügen, das über den verwalteten Connector bereitgestellt und mit Ihrer Experience Platform-Konfiguration verbunden ist.


>[!IMPORTANT]
>
>Im Rahmen dieser Integration findet in den Vereinigten Staaten eine zeitweilige Verarbeitung von Markensichtbarkeit-Daten statt. Die Daten werden letztendlich in der von Ihnen festgelegten Region gespeichert, wie in Ihrem Customer Journey Analytics-Vertrag konfiguriert.


## Anwendungsfälle

Die Integration zwischen Customer Journey Analytics und Markensichtbarkeit bietet zwei Möglichkeiten:

* **Eingehende Integration**: Verwenden Sie Markensichtbarkeit-Daten in Customer Journey Analytics, um den LLM-gesteuerten Traffic (Bot-Crawler, RAG-Anfragen, Agentenaktivität) neben vorhandenen Web-, Mobile- und anderen Datentypen zu messen. Sie können zum Beispiel:

  * Messen Sie den LLM-gesteuerten Traffic anhand der Agentenquelle neben herkömmlichen Kanälen.

  * Identifizieren Sie Inhalte, die stark von LLMs genutzt werden, aber bei der menschlichen Konversion unterdurchschnittlich abschneiden.

  * Erkennen, wo LLM-Agent-Anforderungen über kritische Pfade hinweg fehlschlagen.

  * Vergleichen Sie die LLM-Bot-Nachfrage für eine Seite mit den Konversionen und dem Umsatz dieser Seite in Ihren Web-Daten, abgeglichen auf der URL- und Host-Ebene.

* **Ausgehende Integration**: Senden Sie Customer Journey Analytics-Leistungsdaten an Markensichtbarkeit, damit Sie die KI-Sichtbarkeit für die LLM-Quellen optimieren können, die Ihnen wertvollen Traffic senden, z. B. ChatGPT oder Perplexity. Sie können zum Beispiel:

  * Erfahren Sie, welche LLM-Quellen menschliche Besucher senden, die anschließend konvertieren oder Umsatz generieren. Customer Journey Analytics misst dies anhand des referenzierten Web-Traffics und nicht anhand des Bot-Datensatzes.
  * Ordnen Sie die LLM-Quellen nach dem nachgelagerten Wert der von ihnen gesendeten menschlichen Besucher. Konzentrieren Sie dann Ihre Arbeit mit der KI-Sichtbarkeit auf die Quellen, die die besten Ergebnisse erzielen.


## Eingehende Integration

LLM-Traffic gelangt auf zwei Arten zu Ihrer Site. Customer Journey Analytics misst jede Richtung aus einer anderen Datenquelle.

Der erste Weg ist eine Person, die eine KI-Antwort liest und sich dann zu Ihrer Site durchklickt. Bei diesem Besuch wird dieselbe JavaScript ausgeführt, die auch die restlichen Web-Daten erfasst. Ihre bestehenden Customer Journey Analytics-Web-Daten umfassen daher den Besuch und die Referrer-Domain, von der der Benutzer an Sie gesendet wurde, z. B. chatgpt.com. Customer Journey Analytics kennzeichnet diese Besuche nicht eigenständig als KI-Traffic. Um sie zu identifizieren und zu gruppieren, erstellen Sie ein abgeleitetes Feld für die Verbindung, das mit den KI-verweisenden Domains übereinstimmt, und erstellen Sie dann Segmente und Berichte für dieses Feld. Siehe [Abgeleitete ](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/derived-fields){target="_blank"}. Sie benötigen den Markensichtbarkeit-Datensatz für diesen Traffic an Personen nicht.

Die zweite Möglichkeit ist ein Bot oder Agent, der Ihre Seiten direkt anfordert. Dazu gehören Crawler, die einen KI-Index erstellen, und Live-Abrufe, die auftreten, wenn ein Benutzer eine Eingabeaufforderung an einen KI-Assistenten sendet. Bei diesen Anfragen wird keine JavaScript ausgeführt, sodass die vorhandenen Web-Daten sie nicht aufzeichnen. Der Markensichtbarkeit-Datensatz erfasst diesen Traffic von der CDN-Ebene. Im Rest dieses Abschnitts wird dieser Datensatz beschrieben.

### Integrieren des Datensatzes in Customer Journey Analytics

Der verwaltete Markensichtbarkeit-Connector stellt die Daten als Zusammenfassungsdatensatz für Experience Platform bereit. Um ihn in Customer Journey Analytics zu messen, führen Sie selbst zwei Einrichtungsschritte aus:

1. Erstellen Sie eine Verbindung, die den Markensichtbarkeit-Datensatz enthält. Siehe [Erstellen oder Bearbeiten einer Verbindung](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-connections/create-connection){target="_blank"}.
2. Erstellen Sie eine Datenansicht für diese Verbindung. Die Datenansicht stellt die folgenden Dimensionen und Metriken in Analysis Workspace zur Verfügung. Siehe [Erstellen oder Bearbeiten einer Datenansicht](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/create-dataview){target="_blank"}.

Der Datensatz:

* Verwendet [Zusammenfassungsdatensätze](/help/data-views/summary-data.md) die auf der Klasse XDM Summary Metrics basieren.
* Sammelt Daten nach URL und Host, Uhrzeit und Anfrageeigenschaften wie Bot-Typ, CDN-Anbieter und Status.

>[!NOTE]
>
>Der Markensichtbarkeit-Datensatz enthält aggregierte Daten. Sie enthält keine personenbezogenen Daten wie Benutzerkennung, Eingabeaufforderungen oder Antworten.
>

Da es sich um einen Zusammenfassungsdatensatz handelt, können Sie ihn als Lookup-Datensatz behandeln und ihn mit einem Ereignis-Datensatz auf einem Full-URL-Schlüssel verbinden.

Markensichtbarkeit stellt diesen Schlüssel für Sie in der Dimension **CDN URL** bereit. Er kombiniert den Host und den angeforderten Pfad zu einer einzigen normalisierten vollständigen URL, ähnlich wie Customer Journey Analytics Web-Daten speichert. Ob der Join erfolgreich ist, hängt von Ihrer eigenen Datenerfassung ab. Ihr Ereignis-Datensatz benötigt ein entsprechendes vollständiges URL-Feld oder ein Feld, das Sie analysieren und normalisieren können, sodass es mit der von Markensichtbarkeit bereitgestellten URL übereinstimmt. Wenn beide Seiten dieselbe vollständige URL erhalten, stimmt der Markensichtbarkeit-Eintrag mit der entsprechenden Seite in Ihren Web-Daten überein.

### Über den Datensatz

Markensichtbarkeit liest Server-seitig CDN-Zugriffsprotokolle und extrahiert Datensätze, bei denen es sich bei der anfragenden Partei um einen Bot oder einen automatisierten Agenten handelt. Da die Daten von der CDN-Ebene stammen, erfasst Markensichtbarkeit Anfragen von Bots, die kein JavaScript-Tag auslösen. Standard-Web-Analyse-Tools übersehen diesen Traffic vollständig.

Der Datensatz verwendet die **CDN Requests Summary** Feldergruppe. Jedes Feld befindet sich unter einem `cdn` Objekt, sodass die Feldnamen in den Tabellen unten die Form `cdn.<name>` haben, z. B. `cdn.url` und `cdn.botType`.

Jeder Datensatz beschreibt eine Kombination aus Host, URL-Pfad, Bot-Typ, CDN-Provider, Status-Code, Referrer, weitergeleitetem Host und Zeit bis zum ersten Byte für eine Stunde. Wenn dieselbe Kombination mehrmals pro Stunde angezeigt wird, kombiniert Customer Journey Analytics diese Datensätze zu einer Zeile und erhöht die Anzahl der Anfragen. Verwenden Sie die Metrik **CDN Request Count** zur Messung des Volumens. Zeilenanzahl nicht verwenden.

### Dimensionen

Die folgenden Dimensionen können als Komponenten in einer Datenansicht verwendet werden, sobald Sie eine Verbindung eingerichtet haben, die einen Markensichtbarkeit-Datensatz enthält. Die Spalte **Feld** zeigt das Quellfeld in der Feldergruppe „CDN-Anfragen - Zusammenfassung“ an.

| Dimension | Feld | Beschreibung |
|-----------|-------|-------------|
| CDN-URL | `cdn.url` | Die normalisierte vollständige URL für die Anfrage, die als Join-Schlüssel vorgesehen ist. Markensichtbarkeit kombiniert den Host und den angeforderten Pfad in einer einzigen URL und normalisiert sie so, dass sie mit dem vollständigen URL-Formular übereinstimmt, das Customer Journey Analytics für Web-Daten speichert. Verwenden Sie diese Dimension, um den Markensichtbarkeit-Lookup-Datensatz mit einem Ereignis-Datensatz zu verbinden, der ein entsprechendes vollständiges URL-Feld hat. Sie enthält den Host und den Pfad, aber nicht das Schema. |
| CDN-URL-Pfad | `cdn.path` | Der Pfad der Roh-URL und die vom Agenten angeforderte Abfragezeichenfolge, wie vom CDN bereitgestellt. Enthält weder das Schema noch den Host. Verwenden Sie diese Option, wenn Sie den exakten angeforderten Pfad anstelle des normalisierten Join-Schlüssels benötigen. |
| CDN-Host | `cdn.host` | Der Hostname, der die Anfrage erhalten hat, z. B. www.example.com. Dieser Host ist auch Teil des CDN-URL-Join-Schlüssels. Ein Datensatz kann mehrere Hosts enthalten, wenn eine Organisation mehrere Subdomains im selben CDN-Konto hat. |
| CDN-Bot-Typ | `cdn.botType` | Markensichtbarkeit-Klassifizierung des anfragenden Agenten. Die Werte umfassen klassische Such-Crawler, KI-Index-Crawler und KI-Live-Fetch-Agenten. Die vollständige Taxonomie finden [ in den ](#bot-agent-categories)Bot-Agentenkategorien“ unten. |
| CDN-Benutzeragent | `cdn.userAgent` | Die unformatierte Benutzeragenten-Zeichenfolge aus dem CDN-Protokoll. Nützlich für die Unterscheidung von Untertypen innerhalb einer Bot-Klassifizierung oder für die Validierung der Klassifizierung, die durch Markensichtbarkeit zugewiesen wird. |
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

Wenn das Markensichtbarkeit einen Benutzeragenten nicht mit einem erkannten Muster abgleichen kann, wird der Wert `Unknown` zugewiesen. Sie können die Dimension **CDN User Agent** verwenden, um zu ermitteln, welcher Agent diese Anfragen gestellt hat.

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

### Metrik

Die folgenden Metriken können als Komponenten in einer Datenansicht verwendet werden, sobald Sie eine Verbindung eingerichtet haben, die einen Markensichtbarkeit-Datensatz enthält. Die Spalte **Feld** zeigt das Quellfeld in der Feldergruppe „CDN-Anfragen - Zusammenfassung“ an.

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
