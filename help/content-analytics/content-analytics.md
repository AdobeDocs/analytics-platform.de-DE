---
title: Übersicht über die Inhaltsanalyse
description: Ein Überblick über die Inhaltsanalyse
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hide: true
hidefromtoc: true
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: 8c257279353112df583b46d87ea17749a75867e2
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 0%

---

# Übersicht über die Inhaltsanalyse

>[!WARNING]
>
>Dieser Artikel ist eine vorläufige inoffizielle Entwurfsversion einer kommenden endgültigen Version und Teil der Inhaltsanalysedokumentation. Alle Inhalte unterliegen Änderungen und es können keinerlei rechtlichen Verpflichtungen aus der aktuellen Version dieses Artikels abgeleitet werden.
>

{{release-limited-testing}}

Mit der Inhaltsanalyse können Marketing-Fachleute verstehen, wie sich Inhalte auf die von einem Unternehmen definierten wichtigsten Leistungsindikatoren auswirken. Zusätzlich zu den Verhaltensdaten erfasst Content Analytics Daten darüber, wie Inhalte genutzt werden und wie sich Inhalte auf die Auswirkungen auswirken. Reagieren Kunden beispielsweise besser auf einen bestimmten Tonfall, eine bestimmte Farbpalette oder bestimmte Themen? Diese Informationen sowie speziell entwickelte Reporting-Workflows und Vorlagen können Ihnen dabei helfen, noch bessere Analysen durchzuführen und tiefere Einblicke in Kunden-Journey-Daten in Customer Journey Analytics zu erhalten.

Content Analytics verwendet eine auf KI und maschinellem Lernen basierende **Feature**), um Inhalte in Komponenten und Attribute aufzuteilen. Durch die Erstellung eines strukturierten Metadatenprofils für alle Ihre Inhalte können Sie analysieren, welche Inhalte und welche Attribute dieser Inhalte zu Geschäftsergebnissen führen.

Zusätzlich zur Erstellung dieses strukturierten Metadatenprofils bietet Content Analytics einen **Identity-Service** der Assets und Erlebnisse mithilfe einer einzigen Kennung identifiziert. Der Identity Service kann erkennen, wenn dasselbe Asset an mehr als einer Stelle angezeigt wird. In diesem Fall werden die beiden Instanzen der Assets als identisch behandelt, was eine ganzheitlichere Ansicht der Inhaltsnutzung und -nutzung ermöglicht.

## Wert

Inhaltsanalysen bieten einen Mehrwert auf steigender Ebene:

1. Content **Nutzung**: Mit Content Analytics erhalten Sie Einblicke darüber, welche Assets Impressionen erhalten und wo Assets Impressionen erhalten. Diese Einblicke helfen Ihnen zu erkennen, ob Assets in Ihren Web-Eigenschaften zu wenig oder zu häufig verwendet werden.
1. Inhalte **Interaktionen**: Inhaltsanalysen können Interaktionseinblicke bieten, wie z. B. die durchschnittliche Klickrate für Assets mit bestimmten Attributen. Diese Einblicke helfen Ihnen festzustellen, ob bestimmte Arten von Erlebnissen weiterhin effektiv sind.
1. Inhalt **Journey**: Darüber hinaus können Sie in Kombination mit allen anderen in Experience Platform verfügbaren Daten zusätzliche Einblicke in Ihre Inhalts-Journey erhalten. Zum Beispiel, ob bestimmte Inhalte zusätzlich zur Interaktion zu Konversionen führen. Und mit diesem Wissen können Sie den ROI für verschiedene Inhaltstypen bestimmen.
1. Content **Personalization**: Mit Content Analytics können Sie letztendlich anhand Ihrer Einblicke handeln und diese Einblicke verwenden, um zu bestimmen, wie Sie Geld für Inhalte ausgeben. Sollte ich beispielsweise bestimmte Inhaltstypen an bestimmte Zielgruppen senden? Welche Inhalte bieten mir Möglichkeiten zur Personalisierung?

## Terminologie

Content Analytics verwendet die folgenden Schlüsselbegriffe:

![Assets und Erlebnisse](/help/content-analytics/assets//content-analytics-experience-asset.png)

* **Erlebnis**: Ein Erlebnis ist der gesamte Text auf einer Web-Seite, der anhand der URL reproduzierbar ist, die der Benutzer verwendet hat, der diese Web-Seite ursprünglich besucht hat. Jedes Erlebnis erhält eine eindeutige Kennung.
* **Asset**: Ein Asset ist ein individuelles und eindeutiges Inhaltselement, z. B. ein Bild. Jedes Asset erhält außerdem eine eindeutige Kennung.
* **Attribut**: Ein Attribut ist ein beschreibendes Metadatenelement, das mit einem Erlebnis oder Asset verknüpft ist. Beispiele für ein Attribut sind: Stil der Fotografie, Lesbarkeit, Überzeugungsstrategie, Objektfarbe, Hintergrundfarbe.

## Funktionsweise

Content Analytics verwendet Web-Bildansichtsdaten, die in Ereignisdatensätzen in Experience Platform erfasst wurden. Diese Daten können mithilfe der verschiedenen verfügbaren Methoden erfasst werden: Experience Platform Edge Network (Web SDK, Server API) oder Analytics Source Connector.

![Inhaltsanalyse - Funktionsweise](assets/how-it-works.png)


1. Wenn ein(e) Benutzende(r) eine Website besucht, zeichnet die für Inhaltsanalysen konfigurierte Experience Platform Web SDK Interaktionen mit Inhalten auf.
1. Der Assembler-Service für Funktionen und der Identity Service verarbeiten die erneut besuchten Daten.
1. Die Ergebnisse dieser Services (Komponenten, Attribute und Identitäten) werden verwendet, um die relevanten spezifischen Inhaltsanalysedatensätze in Experience Platform zu aktualisieren.
1. Die Inhaltsanalysedaten können dann zusammen mit Verhaltensdaten und anderen Lookup-Datensätzen in einer Customer Journey Analytics-Konfiguration (Verbindung, Datenansicht und Workspace) verwendet werden. Diese Konfiguration bildet die Grundlage für die einzigartigen Einblicke auf Makroebene in Ihren Inhalt.

>[!NOTE]
>
>Content Analytics nutzt KI/ML. Die Ergebnisse (für die Darstellung von Erlebnissen und Assets) können ungenau sein.
>


>[!MORELIKETHIS]
>
>[Content Analytics-Reporting](report/report.md)
>[Konfigurieren von Inhaltsanalysen](config/configuration.md)
