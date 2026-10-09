---
title: Markensichtbarkeit-Integration
description: Integrieren von Markensichtbarkeit mit Customer Journey Analytics
feature: Experience Platform Integration
role: User
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: fb3ebdba335ce2dde30d37b8aff4e8f201dc5d9f
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 3%
---

# Adobe Brand Visibility-Integration

[Adobe Brand Visibility](https://experienceleague.adobe.com/de/docs/brand-visibility/using/home){target="_blank"} ist eine generative KI-First-Anwendung für die Optimierung von generativen Modulen, die Marken dabei hilft, ihre Sichtbarkeit, Genauigkeit und ihren Einfluss in KI-gestützten Suchumgebungen zu verbessern. Markensichtbarkeit bietet Einblicke in das Markenpräsenz in KI-generierte Antworten, bietet präskriptive Inhaltsempfehlungen und automatisiert Optimierungskorrekturen.

KI ist zu einem primären Erkennungskanal geworden. Agenten für große Sprachmodelle (LLM) wie ChatGPT, Claude, Copilot und Perplexity crawlen Markeninhalte.

>[!NOTE]
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

Der erste Weg ist eine Person, die eine KI-Antwort liest und sich dann zu Ihrer Site durchklickt. Bei diesem Besuch wird dieselbe JavaScript ausgeführt, die auch die restlichen Web-Daten erfasst. Ihre bestehenden Customer Journey Analytics-Web-Daten umfassen daher den Besuch und die Referrer-Domain, von der der Benutzer an Sie gesendet wurde, z. B. chatgpt.com. Customer Journey Analytics kennzeichnet diese Besuche nicht eigenständig als KI-Traffic. Um sie zu identifizieren und zu gruppieren, erstellen Sie ein abgeleitetes Feld für die Verbindung, das mit den KI-verweisenden Domains übereinstimmt, und erstellen Sie dann Segmente und Berichte für dieses Feld. Siehe [Abgeleitete &#x200B;](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/derived-fields){target="_blank"}. Sie benötigen den Markensichtbarkeit-Datensatz für diesen Traffic an Personen nicht.

Die zweite Möglichkeit ist ein Bot oder Agent, der Ihre Seiten direkt anfordert. Dazu gehören Crawler, die einen KI-Index erstellen, und Live-Abrufe, die auftreten, wenn ein Benutzer eine Eingabeaufforderung an einen KI-Assistenten sendet. Bei diesen Anfragen wird keine JavaScript ausgeführt, sodass die vorhandenen Web-Daten sie nicht aufzeichnen. Der Markensichtbarkeit-Datensatz erfasst diesen Traffic von der CDN-Ebene. Im Rest dieses Abschnitts wird dieser Datensatz beschrieben.


### Integrieren des Datensatzes

Der verwaltete Markensichtbarkeit-Connector stellt die Daten als Zusammenfassungsdatensatz für Experience Platform bereit. Um ihn in Customer Journey Analytics zu messen, führen Sie selbst zwei Einrichtungsschritte aus:

1. Erstellen Sie eine Verbindung, die den Markensichtbarkeit-Datensatz enthält.
2. Erstellen Sie eine Datenansicht für diese Verbindung. Die Datenansicht stellt die folgenden Dimensionen und Metriken in Analysis Workspace zur Verfügung.

Der Datensatz:

* Verwendet [Zusammenfassungsdatensätze](/help/data-views/summary-data.md) die auf der Klasse XDM Summary Metrics basieren.
* Sammelt Daten nach URL und Host, Uhrzeit und Anfrageeigenschaften wie Bot-Typ, CDN-Anbieter und Status.

>[!NOTE]
>
>Der Markensichtbarkeit-Datensatz enthält aggregierte Daten. Sie enthält keine personenbezogenen Daten wie Benutzerkennung, Eingabeaufforderungen oder Antworten.
>

Da es sich um einen Zusammenfassungsdatensatz handelt, können Sie ihn als Lookup-Datensatz verwenden und ihn mit einem Ereignis-Datensatz über einen vollständigen URL-Schlüssel verbinden.

Markensichtbarkeit stellt diesen Schlüssel für Sie in der Dimension **CDN URL** bereit. Er kombiniert den Host und den angeforderten Pfad zu einer einzigen normalisierten vollständigen URL, ähnlich wie Customer Journey Analytics Web-Daten speichert. Ob der Join erfolgreich ist, hängt von Ihrer eigenen Datenerfassung ab. Ihr Ereignis-Datensatz benötigt ein entsprechendes vollständiges URL-Feld oder ein Feld, das Sie analysieren und normalisieren können, sodass es mit der von Markensichtbarkeit bereitgestellten URL übereinstimmt. Wenn beide Seiten dieselbe vollständige URL erhalten, stimmt der Markensichtbarkeit-Eintrag mit der entsprechenden Seite in Ihren Web-Daten überein.

Weitere Informationen finden Sie unter:

* [Einrichten und Konfigurieren der eingehenden Integration](/help/integrations/bv/configure.md)
* [Datensatzreferenz](/help/integrations/bv/reference.md)

## Ausgehende Integration

Informationen zur ausgehenden Integration finden Sie unter [Customer Journey Analytics-Integration](https://experienceleague.adobe.com/en/docs/brand-visibility/using/resources/customer-journey-analytics-integration){target="_blank"} in der Dokumentation zu Adobe Brand Visibility.
