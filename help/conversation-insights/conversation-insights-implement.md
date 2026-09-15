---
title: Implementieren von Conversation Insights
description: Erfahren Sie, wie Sie Ihr Agentenprogramm oder Ihren Service für Konversationseinblicke instrumentieren.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: b29ee2f04a1775dca6a8fd93c3ac3050b67f0ceb
workflow-type: tm+mt
source-wordcount: '2257'
ht-degree: 7%
---
# Implementieren von Conversation Insights

Um Unterhaltungsdaten als XDM-Erlebnisereignisse zu generieren und sicherzustellen, dass diese Unterhaltungserlebnisereignisse als Datensätze in Adobe Experience Platform landen, instrumentieren Sie Ihre Agenten-Anwendung oder Ihren Service, um Konversationserkenntnisse zu verwenden.

Dieser Artikel dokumentiert die erforderlichen Implementierungsschritte.

>[!PREREQUISITES]
>
>* Sie müssen über eine Experience Platform-Umgebung (Organisation und Sandbox) verfügen, um die Daten zu erfassen.
>* Ihre Adobe-Organisation muss für die Feldergruppen „Experimenteller Agent“ und „Konversation“ aktiviert sein.
>

## Schema und Datensätze

Konfigurieren Sie Datensätze für die primären Konversationsereignisse: Aufforderung, Antwort, Feedback. Diese Datensätze können auf demselben Schema (z. B. einem generischen Conversation Insights-Schema) oder auf einzelnen Schemata basieren.
Sie können separate Datensätze für Eingabeaufforderungen, Antworten und Feedback definieren oder Daten zu Datensätzen kombinieren. Verwenden Sie beispielsweise einen Datensatz für Eingabeaufforderungen und Antworten und einen anderen Datensatz für Feedback. Oder verwenden Sie einen einzigen Datensatz für alle Konversationsereignisse.

Das für die Eingabeaufforderung, Antwort und Feedback-Datensätze verwendete Schema muss das XDM-Erlebnisereignis-Basisschema um die erforderlichen Feldergruppen erweitern. und kann das XDM-Erlebnisereignis-Basisschema um zusätzliche Feldergruppen erweitern.

### Agent-Informationsfeldgruppe

Die Feldergruppe **[!UICONTROL Agenteninformationen]** ist eine erforderliche Feldergruppe und verwendet das `agenticExperience`.

+++ Details

| Feldpfad (Punktnotation) | Typ | Beispielwert | Hinweise |
|---|---|---|---|
| `conciergeID` | string | `"concierge-abc123"` | **Neu.** Eindeutige Kennung für den Concierge |
| `name` | string | `"Brand Concierge"` | Name des Concierge, der eine Reihe von Agents kombiniert |
| `version` | string | `"1.0.0"` | Die Concierge-Version, die eine Reihe von Agents kombiniert |
| `environment` | string | `"prod"` | Umgebung, aus der dieses Ereignis stammt (dev, stage, prod) |
| `mode` | string | `"release"` | Modus, in dem sich der Agent befindet (Test, Vorschau, Freigabe) |
| `agents[]` | array | Siehe Agent-Objekt unten | Array der verwendeten Agenten |
| `agents[].agentID` | string | `"agent-001"` | **Neu.** Eindeutige Kennung für den Agenten, referenziert durch `skills[].agentID` unten |
| `agents[].name` | string | `"Chatbot Assistant"` | Agent-Name |
| `agents[].version` | string | `"2.1.3"` | Agent-Version |
| `agents[].score` | number | `0.92` | Agent-Konfidenzwert in den zurückgegebenen Werten |
| `agents[].skills[]` | array | Siehe Skill-Objekt unten | **Veraltet** - Verwenden Sie stattdessen das `skills[]`-Array der obersten Ebene unten, das die vollständige Liste der Aufrufe zu Kenntnissen besitzt und jedes über `agentID` mit seinem Agenten verknüpft |
| `agents[].skills[].name` | string | `"Intent Recognition"` | Qualifikationsname (veraltetes Array) |
| `agents[].skills[].version` | string | `"1.0.0"` | SKILL version (veraltetes Array) |
| `agents[].skills[].score` | number | `0.95` | SKILL Confidence Score (0-1) (veraltetes Array) |
| `agents[].skills[].parameters[]` | array | Siehe Parameter unten | Parameter, die an die Qualifikation gesendet werden (Schlüssel-Wert-Paare) (veraltetes Array) |
| `agents[].skills[].parameters[].key` | string | `"language"` | Parameterschlüssel |
| `agents[].skills[].parameters[].value` | string | `"en-US"` | Parameterwert |
| `skills[]` | array | Siehe SKILL Invocation-Objekt weiter unten | **Neu, experimentell.** Vollständige, sortierte Liste der Skill-Aufrufe für dieses Erlebnis für alle Agenten. Ersetzt das veraltete Array pro Agent `agents[].skills[]` |
| `skills[].skillID` | string | `"skill-intent-recognition"` | Kennung der Qualifikationsdefinition, die aufgerufen wurde |
| `skills[].skillInvocationID` | string | `"inv-9f2a-001"` | Eindeutige Kennung für diesen individuellen SKILL-Aufruf, auch konsistent mit erneuten Sendungen. Deduplizierungsschlüssel beim Zusammenführen von Qualifikations-Arrays nachgelagert |
| `skills[].name` | string | `"Intent Recognition"` | Name der aufgerufenen Kenntnisse |
| `skills[].version` | string | `"1.0.0"` | Version der aufgerufenen Kenntnisse |
| `skills[].agentID` | string | `"agent-001"` | Kennung des Agenten, der diese Qualifikation aufgerufen hat, korreliert mit `agents[].agentID`. Die Gruppierung wichtiger Konsumenten verwendet , um Fähigkeiten innerhalb eines Agenten zu sortieren, da Subagenten parallel ausgeführt werden |
| `skills[].invocationSource` | string | `"main"` | Ob durch die Hauptagentenschleife (`main`) oder einen Subagenten (`subagent`) aufgerufen |
| `skills[].score` | number | `0.95` | Punktzahl, die sich aus dem Abgleichen der Qualifikation ergibt |
| `skills[].failed` | boolean | `false` | Markierung, die angibt, dass die Ausführung der Qualifikation fehlgeschlagen ist |
| `skills[].errorReason` | string | `"timeout"` | Grund für fehlgeschlagene Kenntnisse, wenn `failed` wahr ist |
| `skills[].sequenceNumber` | Ganzzahl | `1` | Monoton steigender Index dieser Qualifikationsaufrufe innerhalb einer einzelnen Agentenausführung - nicht global, da Subagenten parallel ausgeführt werden. Die Verbraucher bestellen nach `agentID`, dann `sequenceNumber`, dann `timestamp` als Tiebreak. Optional |
| `skills[].timestamp` | Zeichenfolge (Datum-Uhrzeit) | `"2026-09-11T00:03:15Z"` | Zeitpunkt, zu dem die Qualifikation aufgerufen wurde, ISO 8601 UTC. Nach dem `sequenceNumber` verwendeter Bestellschlüssel. Die Hersteller sollten dies immer befüllen |
| `skills[].skillSource` | string | `"inline"` | Wie die Qualifikationsdefinition an die Laufzeit übermittelt wurde: `inline` (inline in den Kontext geladen) oder `deferred` (bei Bedarf geladen) |
| `skills[].executionContext` | string | `"inline"` | Wo die Qualifikation relativ zum aufrufenden Agenten ausgeführt wird: `inline` oder `forked` (läuft in einem gespaltenen Subagenten-Kontext) |
| `skills[].reasoning.narration` | string | `"Recognized an intent to verify a geography fact"` | Eine natürliche Erklärung, warum diese Fähigkeit genannt wurde |
| `skills[].parameters[]` | array | Siehe Parameter unten | An die Qualifikation übergebene Parameter |
| `skills[].parameters[].key` | string | `"language"` | Parameterschlüssel |
| `skills[].parameters[].value` | string | `"en-US"` | Parameterwert |

+++

Um Ereignisse zu implementieren, die die Feldgruppe Agenteninformationen mit Daten weitergeben, sollten Sie Folgendes sicherstellen:

* Agent-Konfiguration

  * Jeder Agent verfügt über eine eindeutige Kombination aus AgentID, Name und Version.
  * Agent-Scores werden zwischen `0.0` und `1.0` normalisiert.
  * Verwenden Sie die `agentID`, um Agenten durch einen Aufruf der Kenntnisse zu referenzieren.

* Aufruf von Skills

  * Geben Sie nur einen Eintrag pro Qualifikationsaufruf für alle Agenten aus, anstatt Kenntnisse unter jedem Agenten zu verschachteln.
  * Füllen Sie die skillInvocationID, damit nachgelagerte Zusammenfügungen doppelte erneut bereitgestellte Ereignisse entfernen können.
  * Sorgfältige Bestellung der Verbraucher. Nach `agentID` gruppieren, dann nach `sequenceNumber` sortieren und dann auf `timestamp` zurückfallen. Die Sortierung ist erforderlich, da Subagenten parallel ausgeführt werden können
  * Verwenden Sie `invocationSource` und `executionContext`, um zwischen Primär- und Subagenten-Fähigkeiten und Inline- und Gabelausführung zu unterscheiden.
  * Verwenden Sie nicht das veraltete `agents[].skills[]`-Array. Wenn Sie das -Array in der Vergangenheit verwendet haben, behandeln Sie das -Array als schreibgeschütztes Objekt.

* SKILL Parameters

  * Parameter verwenden den XDM-Schlüssel-Wert-Datentyp von Adobe und verwenden gängige Parametertypen für Spracheinstellungen, Schwellenwerte und Modellkonfigurationen. Beispiel: `"key":"language", "value":"en-US"`.

+++ Beispielverwendung der Feldergruppe Agenteninformationen . 

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffe",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"agent.interaction",
  "identityMap":{
    "ECID":[
      {
        "id": "12345678901234567890123456789012345678",
        "primary": true
      }
    ]
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      {
        "agentID":"agent-001",
        "name":"Chatbot Assistant",
        "version":"2.1.3",
        "score":0.92
      },
      {
        "agentID":"agent-002",
        "name":"Voice Assistant",
        "version":"3.0.0",
        "score":0.88
      }
    ],
    "skills":[
      {
        "skillID":"skill-intent-recognition",
        "skillInvocationID":"inv-9f2a-001",
        "name":"Intent Recognition",
        "version":"1.0.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.95,
        "failed":false,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:14Z",
        "skillSource":"inline",
        "executionContext":"inline",
        "reasoning":{
          "narration":"Recognized an intent to verify a geography fact"
        },
        "parameters":[
          { "key":"language", "value":"en-US" },
          { "key":"confidenceThreshold", "value":"0.8" }
        ]
      },
      {
        "skillID":"skill-faq-retrieval",
        "skillInvocationID":"inv-9f2a-002",
        "name":"FAQ Retrieval",
        "version":"1.2.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.89,
        "failed":false,
        "sequenceNumber":2,
        "timestamp":"2026-09-11T00:03:15Z",
        "skillSource":"inline",
        "executionContext":"forked",
        "parameters":[
          { "key":"maxResults", "value":"5" }
        ]
      },
      {
        "skillID":"skill-speech-recognition",
        "skillInvocationID":"inv-9f2a-003",
        "name":"Speech Recognition",
        "version":"2.0.1",
        "agentID":"agent-002",
        "invocationSource":"main",
        "score":0.91,
        "failed":false,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:15Z",
        "skillSource":"deferred",
        "executionContext":"inline",
        "parameters":[
          { "key":"languageModel", "value":"general" },
          { "key":"noiseSuppression", "value":"true" }
        ]
      }
    ]
  }
}
```

+++


### Feldergruppe „Konversationsereignis“

Die **[!UICONTROL Konversationsereignis]**-Feldergruppe ist eine erforderliche Feldergruppe und verwendet das `conversation`.

Das Konversationsobjekt erfasst Daten für:

#### Konversation

Eine eindeutige `conversationID` identifiziert eine Konversation. Beispiel: `conversationID = "conv-001"`. Das Schema unterstützt auch `conversationName`. Ein für Menschen lesbarer Name, der den Gesamtkontext der Konversation beschreibt, z. B.: `France Geography Q&A`.

Die `conversationID` ermöglicht es, alle verwandten Turns-Ereignisse in demselben Konversationserlebnis zu gruppieren.

#### abbiegen

Ein Zug ist ein Interaktionszyklus innerhalb eines Gesprächs.

`turnID` Eine eindeutige `turnID` identifiziert eine Wendung. Beispiel:

`conversationID = "conv-001"`
`turnID = "turn-001"`

Dieselben `conversationID` und `turnID` werden verwendet, um die Eingabeaufforderung, die Antwort und das Feedback zu korrelieren, die mit diesem Zug verbunden sind. Diese Korrelation funktioniert über Datensätze hinweg, die separat bereitgestellt werden oder in verschiedenen Datensätzen enden.


#### Eingabeaufforderung

Eine Eingabeaufforderung ist die Eingabe, die an den Agenten gesendet wird. In den meisten Kundenszenarien ist diese Eingabe die Frage, Anfrage, Anweisung oder Nachricht des Benutzers.

In der Eingabeaufforderung wird die folgende Darstellung verwendet: `conversation.prompt`

Wichtige Eingabeaufforderungsfelder sind:

| Feld | Bedeutung |
|---|---|
| `prompt.source` | Wer oder was die Eingabeaufforderung hervorgebracht hat, in der Regel Endbenutzer. |
| `prompt.raw[]` | Ein oder mehrere Raw-Inhaltssegmente. |
| `prompt.raw[].text` | Der eigentliche Eingabeaufforderungstext oder -inhalt. |
| `prompt.raw[].purpose` | Der Zweck des Inhalts, z. B. Benutzereingabe oder Link. |

Eine Eingabeaufforderung kann mehrere Rohsegmente enthalten. Beispiel: Ein Benutzer gibt Text ein und fügt eine URL hinzu.

* `Prompt`
  * `"What is the capital of France"`
  * `"https://example.com/france"`


#### Antwort

Eine Antwort ist der Inhalt, der vom Agenten oder einer anderen antwortenden Partei zurückgegeben wird.

`conversation.response` Ein eindeutiges `responseID` stellt die Antwort dar.

Wichtige Antwortfelder sind:

| Feld | Bedeutung |
|---|---|
| `response.source` | Wer oder was die Antwort hervorgebracht hat. |
| `response.raw[]` | Ein oder mehrere Segmente für Antwort-Inhalt |
| `response.raw[].text` | Der Antworttext oder -inhalt. |
| `response.raw[].purpose` | Der Zweck des Inhaltssegments. |

Zu den dokumentierten Quelltypen gehören:

| Quelle | Bedeutung |
|---|----|
| `bot` | Automatisierte Agentenantwort. |
| `canned` | Vordefinierte oder vorlagenbasierte Antwort. |
| `concierge` | Reaktion menschlicher Erreger. |
| `end-user` | Nutzergenerierte Inhalte, sofern zutreffend. |

#### Feedback

Feedback ist die explizite Bewertung oder Reaktion des Benutzers auf die Interaktion.

Die Feedback-Struktur umfasst: `conversation.feedback`.

Beispiele:

* `feedback.raw[].text: "Great help"`
* feedback.rating.score: 1
* feedback.rating.classification: „Daumen hoch“
* `feedback.rating.reasons[]: ["Accurate", "Quick response"]`

Der dokumentierte Bewertungsbereich reicht von `-1.0` bis `1.0`.

Ein Feedback-Ereignis kann als reines Feedback-Ereignis dargestellt werden, indem Folgendes verwendet wird: `eventType = "conversation.feedback"`.

Wenn das Feedback für eine bestimmte Drehung gilt, bewahren Sie die entsprechenden `conversationID` und `turnID` auf, damit der Konversationsmischer das Feedback mit der relevanten Interaktion verknüpfen kann.


#### Signal

Ein Signal ist eine strukturierte analytische Beobachtung über Konversationsinhalte. Der Signalextraktionsdienst extrahiert Signale.

Ein Signal weist die folgenden Felder auf.

| Feld | Bedeutung |
|---|----|
| `scope` | Der Eingangsbereich, der zum Ableiten des Signals verwendet wird, z. B. „An“ oder „Konversation bis dato“. |
| `name` | Die Signalkennung, z. B. Motive, Absichten, Töne oder Sentiment. Herstellerdefinierte Signalnamen werden ebenfalls unterstützt. |
| `type` | Der Werttyp: Zeichenfolge, Zahl oder Boolescher Wert. |
| `values[]` | Ein oder mehrere dem Signal zugeordnete Werte. |
| `stringValue` | Ein Zeichenfolgensignalwert, z. B. Intent, Ton oder Betreff. |
| `numberValue` | Ein numerischer Signalwert, z. B. eine Sentiment-Bewertung. |
| `booleanValue` | Ein Wert für true/false Signal. |
| `confidence` | Optionales Herstellervertrauen in den Signalwert, normalerweise zwischen 0 und 1. |
| `qualifiers[]` | Optionale Deskriptoren, die einem Signalwert Kontext hinzufügen. |
| `metadata[]` | Optionale, vom Produzenten definierte Schlüssel/Wert-Metadaten. |


Der Signalextraktions-Service füllt das `signals` für den Signaldatensatz.

Der vorherige `signals[].attributes.{subjects,intents,tones,sentiment}`-Container wird nicht mehr unterstützt.

#### Konversation

Unten finden Sie die vollständigen Details eines Konversationsobjekts.

+++ Details 

| Feldpfad (Punktnotation) | Typ | Beispielwert | Hinweise |
|---|---|---|---|
| `conversationID` | string | `"conv-001"` | Gruppiert mehrere Kurven |
| `conversationName` | string | `"France Geography Q&A"` | **Neu.** Name, der einem Gespräch mit dem allgemeinen Kontext gegeben wurde |
| `turnID` | string | `"turn-001"` | Eindeutige ID für diesen Zug |
| `prompt.source` | string | `"end-user"` | Source der Eingabeaufforderung, andere Optionen können einen zwischengespeicherten Wert, einen eingesparten Wert usw. umfassen. |
| `prompt.raw[]` | array | Siehe Rohobjekt unten | Rohdaten der Eingabeaufforderung |
| `prompt.raw[].text` | string | `"What is the capital of France?"` | Tatsächlicher Textinhalt |
| `prompt.raw[].purpose` | string | `"User Input"` | Zweck dieses Textsegments |
| `response.source` | string | `"bot"` | Source der Antwort |
| `response.raw[]` | array | Siehe Rohobjekt unten | Rohe Antwortdaten |
| `response.raw[].text` | string | `"The capital of France is Paris."` | Inhalt des Antworttextes |
| `response.raw[].purpose` | string | `"main"` | Zweck des Antwortsegments. Andere Optionen können Links, Bilder usw. sein. |
| `feedback.source` | string | `"end-user"` | Source des Feedbacks |
| `feedback.raw[]` | array | Siehe Rohobjekt unten | Rohe Feedback-Daten |
| `feedback.raw[].text` | string | `"Great help"` | Feedback-Text |
| `feedback.raw[].purpose` | string | `"free-form text"` | Zweck des Feedback-Segments, andere Optionen können Screenshots, Medien usw. sein. |
| `feedback.rating.score` | number | `1` | Numerischer Bewertungswert von -1,0 bis 1,0 |
| `feedback.rating.classification` | string | `"Thumbs Up"` | Klassifizierung der Alterseinstufung |
| `feedback.rating.reasons[]` | array | `["Accurate", "Quick response"]` | Array von Bewertungsgründen |
| `signals[]` | array | Siehe Signalobjekt unten | Abgeleitete Signale, die auf diesem Ereignis und der bisherigen Konversation basieren. Jeder Eintrag ist ein einzelnes benanntes Signal mit eigenem Umfang |
| `signals[].scope` | string | `"turn"` | Umfang der Eingänge, aus denen dieser Signalsatz abgeleitet wird (Kurve, Konversation bis dato, letzte n-Windungen, Feedback) |
| `signals[].attributes` | Objekt | Siehe Attribute unten | **Veraltet.** Container für Signalattribute. Jedes Attribut ist ein Objekt mit Werten darin. Damit soll der erwarteten Notwendigkeit Rechnung getragen werden, eine Population von ML/Agent-Informationen zu unterstützen, die zur Erzeugung des Signals verwendet werden. |
| `signals[].attributes.subjects` | Objekt | Siehe Themen unten | **Veraltet.** Container für Betreffzeile |
| `signals[].attributes.subjects.values[]` | array | Siehe Betreffwerte unten | **Veraltet.** Array von Betreffwerten |
| `signals[].attributes.subjects.values[].phrase` | string | `"product pricing"` | **Veraltet.** Eine Wortgruppe oder ein Keyword, die bzw. das aus der im Umfang enthaltenen Eingabe extrahiert wurde |
| `signals[].attributes.subjects.values[].qualifiers[]` | array | `["important", "urgent"]` | **Veraltet.** Liste der Kriterien für die Phrase |
| `signals[].attributes.intents` | Objekt | Siehe Absichten unten | **Veraltet.** Absichtscontainer |
| `signals[].attributes.intents.values[]` | array | `["make a purchase", "learn more"]` | **Veraltet.** Aus der erfassten Eingabe abgeleitete Absichten |
| `signals[].attributes.tones` | Objekt | Siehe Töne unten | **Veraltet.** Tonbehälter |
| `signals[].attributes.tones.values[]` | array | `["thrilled", "contemplative"]` | **Veraltet.** Aus der erfassten Eingabe abgeleitete Töne |
| `signals[].attributes.sentiment` | Objekt | Siehe Sentiment unten | **Veraltet.** Sentiment-Container |
| `signals[].attributes.sentiment.value` | number | `0.71` | **Veraltet.** Punktzahl von -1 (negativ) bis 1 (positiv) für Sentiment |
| `signals[].name` | string | `"sentiment"` | **Neu** (ersetzt den veralteten `attributes`-Container). Kennung für dieses Signal, z. B. „Subjekte“, „Absichten“, „Töne“, &quot;Sentiment&quot; oder ein beliebiger herstellerdefinierter Name — Produzenten können neue Signaltypen ohne Schemaänderung hinzufügen |
| `signals[].type` | string | `"number"` | **Neu.** Datentyp der Werte dieses Signals (`string`, `number` oder `boolean`) - gibt den Verbrauchern an, welches eingegebene Wertefeld bei jedem Eintrag von `values[]` ausgefüllt wird |
| `signals[].values[]` | array | Siehe Objektwerte weiter unten | Ein oder mehrere Werte für dieses Signal |
| `signals[].values[].stringValue` | string | `"curious"` | Wird gefüllt, wenn `type` „Zeichenfolge“ ist - ein kategorialer Wert wie z. B. Intent, Ton oder extrahierte Phrase |
| `signals[].values[].numberValue` | number | `0.71` | Wird befüllt, wenn `type` „Zahl“ ist - z. B. ein Sentiment-Wert von -1 bis 1 oder eine Intensität. |
| `signals[].values[].booleanValue` | boolean | `true` | Wird befüllt, wenn `type` „boolesch“ ist - eine true/false-Markierung |
| `signals[].values[].confidence` | number | `0.9` | **Neu.** Konfidenz, die der Hersteller diesem Wert zuweist, von 0 bis 1 |
| `signals[].values[].qualifiers[]` | array | `["important", "urgent"]` | Zusätzliche Deskriptoren für diesen Wert, ähnlich wie Keywords, aber aussagekräftiger |
| `signals[].values[].metadata[]` | array | Siehe Parameter unten | **Neu.** Herstellerdefinierte Metadaten für diesen Wert als Schlüssel/Wert-Paare, z. B. Kontext zu dem ML/Agent, der das Signal generiert hat |

+++




### Zusätzliche Feldergruppen

Sie können dem Schema, das Sie für Eingabeaufforderungen, Antworten und Feedback-Datensätze verwenden, optionale Feldergruppen hinzufügen. Beispiel:

* **Web-**) Feldergruppe. Um Details der Web-Seite zu erfassen, in die die Konversation eingebettet wurde.
* **Commerce-**: Feldergruppe. So erfassen Sie die Produktdetails des empfohlenen Produkts, das im Rahmen des Gesprächs erwähnt wird.



Der Kunde ist für die Erstellung der Quell-Konversationsereignisse verantwortlich. Adobe Platform führt anschließend eine Signalextraktion und Datenmischung durch. Der Kunde muss die Signalextraktions- oder Mischdienste nicht implementieren.

In diesem Dokument werden die Eingabeanforderungen für das MVP für Konversationserkenntnisse und die aktuelle Aktualisierung des Agentenschemas behandelt. Sie enthält keine Funktionen von Conversation Insights 1.0 oder Anforderungen für spätere Versionen.

### Ereignistyp

Für jedes Konversationsereignis müssen Sie einen der folgenden Werte für `eventType` (Zeichenfolge) festlegen:

| Wert | Erklärung |
|---|---|
| `conversation turn` | Vollständige Konversation mit Eingabeaufforderung und Antwort |
| `conversation recommendation` | Konversationsbasierte Empfehlung |
| `conversation feedback` | Nur-Feedback-Ereignis |


### Typ der Quelle

Sie müssen einen der folgenden Werte für `source` für jedes `prompt`, `response` oder `feedback` Objekt in einem Ereignis festlegen:

| Wert | Beschreibung |
|---|---|
| `end-user` | Benutzereingabe |
| `bot` | Automatisierte Agentenantwort |
| `canned` | Vordefinierte/vorlagenbasierte Antwort |
| `concierge` | menschliche Reaktion |

### Art des Zwecks (Rohtext)

Sie müssen einen der folgenden Werte für das `purpose`-Attribut für ein beliebiges Element des `raw`-Objekts in einem `prompt`-, `response`- oder `feedback` festlegen.

| Wert | Beschreibung |
|---|---|
| `User Input` | Primäre Benutzereingabe |
| `main` | Hauptantwortinhalt |
| `advertisement` | Werbeinhalte |
| `citation` | Referenz-/Quell-Links |
| `link` | Externe Links |
| `image` | Bildreferenzen |
| `enum picker` | Strukturierte Feedback-Auswahl |


### Beispiel

Unten finden Sie ein Beispiel für die Verwendung der Feldergruppe „Konversationsereignis“ in verschiedenen Szenarien.

+++ Details 

>[!BEGINTABS]

>[!TAB Beispiel für ein Turn-Ereignis]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827fff",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "turnID": "int-001",
    "prompt": {
      "source": "end-user",
      "raw": [
        { "text": "What is the capital of France? This link says it is Lyon.", "purpose": "User Input" },
        { "text": "https://wrong.geography.com/france", "purpose": "link" }
      ]
    }
  }
}
```

>[!TAB Beispiel für ein Antwortereignis]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffd",
  "timestamp":"2026-09-11T00:03:16Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "turnID": "int-001",
    "response": {
      "source": "concierge",
      "raw": [
        { "text": "The capital of France is Paris.", "purpose": "main" },
        { "text": "Would you like to plan a trip to Paris?", "purpose": "advertisement" },
        { "text": "https://en.wikipedia.org/wiki/France", "purpose": "citation" }
      ]
    }
  }
}
```

>[!TAB Beispiel für Feedback-]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffb",
  "timestamp":"2026-09-12T00:03:15Z",
  "eventType":"conversation.feedback",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "feedback": {
      "source": "end-user",
      "raw": [
        { "text": "Great help", "purpose": "text box" }
      ],
      "rating": {
        "score": 1,
        "classification": "Thumbs Up",
        "reasons": ["Accurate", "Quick response"]
      }
    }
  }
}
```

>[!TAB Beispiel für Produktempfehlungen]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffa",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.recommendation",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-xyz789",
    "name":"Product Concierge",
    "version":"1.0.0",
    "environment":"prod",
    "mode":"release",
    "agents":[
      { "agentID":"agent-010", "name":"Product Advisor", "version":"1.0.0", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "turnID": "int-099",
    "prompt": {
      "source": "end-user",
      "raw": [
        { "text": "What product do you recommend for a new user trying to create a poster?", "purpose": "User Input" }
      ]
    },
    "response": {
      "source": "concierge",
      "raw": [
        { "text": "To create a poster, we would recommend Adobe Express - https://express.adobe.com.", "purpose": "main" },
        { "text": "https://express.adobe.com", "purpose": "link" }
      ]
    }
  },
  "productListItems": [
    { "SKU": "express" }
  ]
}
```

>[!ENDTABS]

+++

## Datenerfassung

Verwenden Sie die folgende Datenerfassungsstrategie für Konversationseinblicke.


### Ereignistypen

Ihr Agent-Programm oder Service sendet ein Ereignis so bald wie möglich. Stellen Sie sicher, dass die App oder der Service nicht auf eine Antwort wartet, bevor die Eingabeaufforderung mit den zum Zeitpunkt des Ereignisses verfügbaren Informationen an gesendet wird.

Diese Empfehlung impliziert Folgendes:

* Eingabeaufforderungs-, Antwort- und Feedback-Objekte werden unabhängig voneinander ausgefüllt und sollten nicht gezwungen werden, Teil eines einzelnen Ereignisses zu sein.
* Es werden mehrere Ereignisse mit demselben `conversationID` und denselben `turnID` über Datensätze hinweg erwartet.

### Ereigniskorrelation

Die Agentenanwendung oder der Service muss stabile Kennungen für alle zugehörigen Ereignisse beibehalten.

| Feldpfad | Beschreibung |
|---|---|
| `conversation.conversationID` | Eindeutige Kennung für die gesamte Konversation. |
| `conversation.turnID` | Eindeutige Kennung für einen einzelnen Zug innerhalb des Gesprächs. |
| `_id` | Kennung des Erlebnisereignis-Datensatzes. |
| `timestamp` | Zeitpunkt, zu dem das Ereignis aufgetreten ist. |
| `eventType` | Identifiziert den Typ des Konversationsereignisses. |

* Für alle Ereignisse, die zur selben Konversation gehören, muss dieselbe `conversationID` verwendet werden.

* Derselbe `turnID` muss für die Eingabeaufforderung, die Antwort und jedes Feedback verwendet werden, das mit derselben Runde verknüpft ist. In den Eingabeaufforderungen-, Antwort- und Feedback-Datensätzen können mehrere Ereignisse mit demselben `turnID` vorhanden sein.

Die Agentanwendung oder der Service generiert IDs, die bei weiteren Zustellversuchen oder erneuten Sendungen stabil bleiben. Dies ermöglicht die nachgelagerte Verarbeitung, um Ereignisse korrekt zu verknüpfen und unbeabsichtigte doppelte Ereignisse zu vermeiden.

## Signalextraktion

Die Signalextraktion erfolgt nach der Datenerfassung. Die Agentanwendung oder der Service füllen keine zusätzlichen Signale aus.

+++ Beispiel-Drehereignis mit Signalen

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827fff",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id":"12345678901234567890123456789012345678", "primary":true }
    ]
  },
  "web":{
    "webPageDetails":{ "URL":"https://www.adobe.com", "name":"Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ],
    "skills":[
      {
        "skillID":"skill-intent-recognition",
        "skillInvocationID":"inv-9f2a-001",
        "name":"Intent Recognition",
        "version":"1.0.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.95,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:14Z",
        "skillSource":"inline",
        "executionContext":"inline"
      }
    ]
  },
  "conversation":{
    "conversationID":"conv-001",
    "conversationName":"France Geography Q&A",
    "turnID":"int-001",
    "signals":[
      {
        "scope":"turn",
        "name":"subjects",
        "type":"string",
        "values":[
          { "stringValue":"capital of France", "confidence":0.93, "qualifiers":["geographical","factual-question"] },
          { "stringValue":"Lyon", "confidence":0.87, "qualifiers":["incorrect","misinformation"] }
        ]
      },
      {
        "scope":"turn",
        "name":"intents",
        "type":"string",
        "values":[
          { "stringValue":"seek-information" },
          { "stringValue":"verify-facts" }
        ]
      },
      {
        "scope":"turn",
        "name":"tones",
        "type":"string",
        "values":[
          { "stringValue":"curious" },
          { "stringValue":"uncertain" }
        ]
      },
      {
        "scope":"turn",
        "name":"sentiment",
        "type":"number",
        "values":[
          { "numberValue":0.1 }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"subjects",
        "type":"string",
        "values":[
          { "stringValue":"unreliable source", "qualifiers":["external-link","potentially-misleading"] },
          { "stringValue":"geography knowledge", "qualifiers":["educational","basic-facts"] }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"intents",
        "type":"string",
        "values":[
          { "stringValue":"fact-checking" },
          { "stringValue":"learn-correct-information" }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"tones",
        "type":"string",
        "values":[
          { "stringValue":"questioning" },
          { "stringValue":"seeking-clarification" }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"sentiment",
        "type":"number",
        "values":[
          { "numberValue":0.3 }
        ]
      }
    ],
    "prompt":{
      "source":"end-user",
      "raw":[
        { "text":"What is the capital of France? This link says it is Lyon.", "purpose":"User Input" },
        { "text":"https://wrong.geography.com/france", "purpose":"link" }
      ]
    }
  }
}
```

+++

## Datenmischung

Der Conversation Blender-Service führt Ereignisse aus Eingabeaufforderungs-, Antwort-, Feedback- und Signalereignis-Datensätzen in einem dedizierten Blended Conversation-Ereignisdatensatz zusammen. Dieser Datensatz wird in Customer Journey Analytics als Teil einer Verbindung verwendet. Die Komponenten in diesem Datensatz werden zu den Datenansichten hinzugefügt, die Sie für eine Conversation Insights-Konfiguration angegeben haben.
