---
title: Konversation - Einblicke - Übersicht
description: Erfahren Sie mehr über den Wert und die Terminologie von Conversation Insights und lernen Sie, wie Conversation Insights funktioniert.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: 8e446c15e998e660b42a09681fe78b885711e41f
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 1%
---
# Conversation Insights

Mit Conversation Insights können Sie Konversationen aus den Agentenerlebnissen analysieren, die Sie Ihren Kunden anbieten. Diese Agentenerlebnisse können auf großen Sprachmodellen (LLM) oder auf menschlichen Konversationen basieren. Conversation Insights analysiert die Konversationen in großem Maßstab und bietet Kontext für diese Konversationen innerhalb der vollständigen Kunden-Journey. Mithilfe von Conversation Insights sind Sie in der Lage, die Auswirkungen von Agenten auf tatsächliche Benutzerergebnisse zu verstehen.

Conversation Insights behandelt Probleme, die auftreten können. z. B.:

* Sie haben keine insight darüber, was passiert, wenn Kunden mit Agenten (LLM oder Menschen) im Kontext des Journey interagieren.
* Sie sind nicht in der Lage, Folgendes zu verstehen:
  * Was Agenten Kunden in großem Maßstab erzählen.
  * Interaktion von Kunden mit Agenten in großem Maßstab.
  * Wie wirken sich diese Interaktionen insgesamt auf KPIs aus?
* Sie erstellen agentische Erlebnisse, um sich ändernden Benutzerpräferenzen Rechnung zu tragen.

Mit Conversation Insights können Sie Folgendes verstehen:

* Was Agenten den Benutzern mitteilen.
* Was Benutzende von Agenten anfragen.
* Auswirkungen der Konversationen auf Ihre KPIs.

Sie können feststellen, wie Ihre Agenten die Richtlinien einhalten, wie genau die Agenten die Markenrichtlinien einhalten und ob die Kosten für die Ausführung von Agenten durch das Ergebnis gerechtfertigt sind.


## Konzepte

Auf einer hohen Ebene in Conversation Insights [ eine ](#conversation) von korrelierten [Wendungen](#turn). Jeder Zug kann unabhängig über Ereignisse [Eingabeaufforderung](#prompt), [Antwort](#response) und [Feedback](#feedback) verfügen. [Signale](#signal) sind strukturierte Beobachtungen, die aus der Konversation abgeleitet werden, während der gemischte Datensatz die Quellereignisse und Signale für das Reporting zusammenführt.

Conversation Insights analysiert Interaktionen von Agenten auf zwei Ebenen:

* [Konversationsebene](#conversation) Die vollständige Interaktion zwischen einem Benutzer und einem Agenten, die mehrere Runden enthält.
* [Turn](#turn)-Ebene: Ein Interaktionszyklus innerhalb dieser Konversation, bestehend aus einer Benutzeraufforderung und einer Agentenantwort.

Die Agent-Anwendung oder der Service gibt konversationsbezogene Erlebnisereignisse in Experience Platform aus. Eingabeaufforderungs-, Antwort- und Feedback-Ereignisdaten können unabhängig voneinander eintreffen. Platform-Services korrelieren und verschmelzen diese Ereignisse zu einem Turn-Level-Datensatz, reichern die Daten optional mit extrahierten Signalen an und stellen die resultierenden Daten für Customer Journey Analytics-Berichte zur Verfügung.

### Konversation

Eine Konversation ist die vollständige Interaktion zwischen einem Benutzer und einem Agenten. Es kann eine oder mehrere Windungen enthalten.

Eine Konversation ist die Container- oder Gruppierungsebene. Dieser Container ist für Fragen nützlich, z. B.:

* Wie viele Gespräche fanden statt?
* Was war das Hauptthema eines Gesprächs?
* Wie hat sich Sentiment in einem Gespräch verändert?
* Welche Gespräche führten schließlich zu einer Konversion?

Weitere Informationen zur Implementierung finden Sie im [Konversation](./conversation-insights-implementation.md#conversation)-Objekt in der Dokumentation [Konversationseinblicke implementieren](./conversation-insights-implementation.md).

### abbiegen

Ein Zug ist ein Interaktionszyklus innerhalb eines Gesprächs.

Eine typische Wendung besteht aus

* Benutzeraufforderung
* Agent-Antwort
* (optional) Benutzer-Feedback

Der Zug ist das primäre Analyseobjekt für Berichtszwecke. Der Conversation Blender-Service kombiniert die verfügbaren Eingabeaufforderungen, Antwort-, Feedback- und Signalinformationen in Turn-Level-Aufzeichnungen.

Weitere Informationen zur Implementierung finden Sie im [Turn](./conversation-insights-implementation.md#turn)-Objekt in der Dokumentation [Implementieren von Konversationserkenntnissen](./conversation-insights-implementation.md) .

### Eingabeaufforderung

Eine Eingabeaufforderung ist die Eingabe, die an den Agenten gesendet wird. In den meisten Kundenszenarien ist diese Eingabe die Frage, Anfrage, Anweisung oder Nachricht des Benutzers.

Eine Eingabeaufforderung kann mehrere Rohsegmente enthalten. Beispiel: Ein Benutzer gibt Text ein und fügt eine URL hinzu.

* `Prompt`
  * `"What is the capital of France"`
  * `"https://example.com/france"`

Die Eingabeaufforderung ist die primäre Eingabe, aus der Conversation Insights analytische Informationen ableiten kann, z. B.:

* Die Absicht des Benutzers
* Thema oder Thema
* Der Ton des Benutzers
* Die Sentiment des Benutzers
* Andere unterstützte Signale

Weitere Informationen zur Implementierung finden Sie im [Eingabeaufforderung](./conversation-insights-implementation.md#prompt)-Objekt in der Dokumentation [Implementieren von Konversationseinblicken](./conversation-insights-implementation.md).

### Antwort

Eine Antwort ist der Inhalt, der vom Agenten oder einer anderen antwortenden Partei zurückgegeben wird.

Eine Antwort enthält oft verschiedene Inhaltstypen. Beispiel:

* Hauptantwort
* Zitierung oder Referenz
* Link
* Bild
* Werbeinhalte

Diese Unterscheidung ist nützlich, da die Analyse die Hauptantwort von unterstützenden Links, Zitaten, Anzeigen oder anderen Antwortkomponenten trennen muss.

Weitere Informationen zur Implementierung finden Sie im [Antwort](./conversation-insights-implementation.md#response)-Objekt in der Dokumentation [Implementieren von Konversationseinblicken](./conversation-insights-implementation.md).

### Feedback

Feedback ist die explizite Bewertung oder Reaktion des Benutzers auf die Interaktion.

Das Feedback kann Folgendes enthalten:

* Freiform-Feedback-Text
* Eine numerische Bewertung
* Klassifizierung der Alterseinstufung
* Ein oder mehrere Gründe für die Bewertung

Feedback muss nicht unbedingt gleichzeitig mit der Eingabeaufforderung oder der Antwort verfügbar sein. Sie können das Feedback zu einem späteren Zeitpunkt über die Agentenanwendung oder den Service senden, nachdem der Benutzer die Antwort ausgewertet hat.

Weitere Informationen zur Implementierung finden Sie im [Feedback](./conversation-insights-implementation.md#feedback)-Objekt in der Dokumentation [Implementieren von ](./conversation-insights-implementation.md) .

### Signal

Ein Signal ist eine strukturierte analytische Beobachtung über Konversationsinhalte. Der Signalextraktionsdienst extrahiert Signale.

Weitere Informationen zur Implementierung finden Sie im [Signal](./conversation-insights-implementation.md#signal)-Objekt in der Dokumentation [Implementieren von Konversationserkenntnissen](./conversation-insights-implementation.md) .


### Agent

Um die Agentenanwendung oder den Service zu identifizieren, sind für jedes Conversation Insights-Ereignis (Eingabeaufforderung, Antwort, Feedback, Signal) Agenteninformationen erforderlich.

#### SKILL Invocations

Wenn Ihr Agent-Erlebnisprogramm den Aufruf von Fähigkeiten unterstützt, die während der Verarbeitung aufgerufene Funktionen darstellen, können Sie diese Fähigkeitsaufrufe als Teil der Feldergruppe für Agenteninformationen hinzufügen.

Weitere Informationen zur Implementierung finden Sie in der [Agenteninformationen](./conversation-insights-implementation.md#agentic-information-field-group) in der Dokumentation [Implementieren von ](./conversation-insights-implementation.md)&quot;.

## Funktionsweise

Conversation Insights basiert auf drei Kernfunktionen:

* **Datenerfassung**: Ermöglicht es Benutzenden zu verstehen, wie gut LLM und Agenten ihre Aufgaben ausführen. Die Datenerfassung ist erforderlich, um alle erforderlichen Datenpunkte zu erfassen.
* **Signalextraktion und Konversationsmischung**: Wandelt die unstrukturierten Eingabeaufforderungen und Antworten (auch als „Turns“ bezeichnet) in berichtbare Datenpunkte um, z. B. Intent und Sentiment. Damit Anwender in großem Umfang Berichte zu diesen Datenpunkten erstellen können.
* **Reporting**: Um die Effektivität und den ROI eines Agenten zu ermitteln, analysieren Sie Konversationen im großen Maßstab im Kontext des Kunden-Journey.

Der Gesamtprozess der Datenerfassung, Signalextraktion und Konversationsmischung ist unten dargestellt.

![Konversation Insights Wie es funktioniert Illustration](assets/conversation-insights.png){zoomable="yes"}

| | Beschreibung |
|---|---|
| 1 | Sie instrumentieren Ihr Agentprogramm oder Ihren Service, um Ereignisse zu erstellen, die Eingabeaufforderungen ![CommentText](/help/assets/icons2/CommentText.svg), Antworten ![CommentReply](/help/assets/icons2/CommentReply.svg) und Feedback-![ (Feedback](/help/assets/icons2/Feedback.svg)-Datensätze enthalten.<br/>Weitere Informationen zum Instrumentieren der Agentenanwendung oder des Services finden Sie in der [Implementierungsdokumentation](./conversation-insights-implementation.md). |
| 2 | Der Signalextraktions-Service extrahiert Signale aus den Eingabeaufforderungen ![CommentText](/help/assets/icons2/CommentText.svg), Antworten ![CommentReply](/help/assets/icons2/CommentReply.svg) und Feedback-Datensätzen ![Feedback](/help/assets/icons2/Feedback.svg) als Signalereignisse ![OnAir](/help/assets/icons/OnAir.svg) und speichert diese Signalereignisse in einem neuen Datensatz.<br>Dieser Schritt wird als Teil der Definition einer „Conversation [&quot;-Konfiguration ](./conversation-insights-configure.md). |
| 3 | Der Conversation Blender-Service blendet die Ereignisse aus den ![CommentText](/help/assets/icons2/CommentText.svg), Antworten ![CommentReply](/help/assets/icons2/CommentReply.svg), Feedback ![Feedback](/help/assets/icons2/Feedback.svg) und Signalen ![OnAir](/help/assets/icons/OnAir.svg)-Ereignisdatensätzen zusammen und gibt die blended ![Merge](/help/assets/icons/Merge.svg)events in einen neuen Datensatz aus.<br>Dieser Schritt wird als Teil der Definition einer „Conversation [&quot;-Konfiguration ](./conversation-insights-configure.md). |
| 4 | Der gemischte ![Zusammenführen](/help/assets/icons/Merge.svg)-Datensatz wird Teil der Verbindung und die Komponenten, die in dem Schema definiert sind, das für den gemischten Datensatz verwendet wird, werden Teil der Datenansicht.<br>Dieser Schritt wird als Teil der Definition einer „Conversation [&quot;-Konfiguration ](./conversation-insights-configure.md). |

