---
title: Übersicht der Inhaltsanalyse
description: Ein Überblick über die Inhaltsanalyse
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: 28a0abd3415a167e6dd3de3b77bd49b78fc003cd
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 48%

---

# Übersicht der Inhaltsanalyse

{{release-limited-testing}}

Mit der Inhaltsanalyse können Marketing-Fachleute nachvollziehen, wie sich Inhalte auf die von einem Unternehmen definierten wichtigsten Leistungsindikatoren auswirken. Zusätzlich zu den Verhaltensdaten erfasst Content Analytics Daten darüber, wie Inhalte genutzt werden und wie sich Inhalte auf die Auswirkungen auswirken. Reagieren Kunden beispielsweise besser auf einen bestimmten Tonfall, eine bestimmte Farbpalette oder bestimmte Themen? Diese Informationen sowie speziell entwickelte Reporting-Workflows und Vorlagen können Ihnen dabei helfen, noch bessere Analysen durchzuführen und tiefere Einblicke in Customer Journey-Daten in Customer Journey Analytics zu erhalten.

Die Inhaltsanalyse verwendet eine auf KI und maschinellem Lernen basierende **Featurisierungs-Services**, um Inhalte in Komponenten und Attribute aufzuschlüsseln. Durch die Erstellung eines strukturierten Metadatenprofils für alle Ihre Inhalte können Sie analysieren, welche Inhalte und welche Attribute dieser Inhalte zu Geschäftsergebnissen führen.

Zusätzlich zur Erstellung dieses strukturierten Metadatenprofils bietet die Inhaltsanalyse einen **Identity Service** der Assets und Erlebnisse mithilfe einer einzigen Kennung identifiziert. Der Identity Service kann erkennen, wenn dasselbe Asset an mehr als einer Stelle angezeigt wird. In diesem Fall werden die Instanzen dieses Assets als dasselbe Asset behandelt, was eine ganzheitlichere Ansicht der Inhaltsnutzung und -nutzung ermöglicht.

## Wert

Die Inhaltsanalyse bietet zunehmend Mehrwert:

1. **Inhaltsnutzung**: Mit der Inhaltsanalyse erhalten Sie Einblicke darüber, welche Assets Impressionen erhalten und wo Assets Impressionen erhalten. Diese Einblicke helfen Ihnen, zu erkennen, ob Assets in Ihren Web-Eigenschaften zu wenig oder zu häufig verwendet werden.
1. **Interaktionen mit Inhalten**: Die Inhaltsanalyse kann Einblicke in Interaktionen bieten, z. B. die durchschnittliche Clickthrough-Rate für Assets mit bestimmten Attributen. Diese Einblicke helfen Ihnen, festzustellen, ob bestimmte Arten von Erlebnissen weiterhin effektiv sind.
1. **Inhalts-Journeys**: Darüber hinaus können Sie in Kombination mit allen anderen in Experience Platform verfügbaren Daten zusätzliche Einblicke in Ihre Inhalts-Journeys erhalten. Zum Beispiel, ob bestimmte Inhalte zusätzlich zur Interaktion zu Konversionen führen. Und mit diesem Wissen können Sie den ROI für verschiedene Inhaltstypen bestimmen.
1. **Inhaltspersonalisierung**: Mit der Inhaltsanalyse können Sie letztendlich anhand Ihrer Einblicke handeln und diese Einblicke verwenden, um zu bestimmen, wie Sie Geld für Inhalte ausgeben. Sollte ich beispielsweise bestimmte Inhaltstypen an bestimmte Zielgruppen senden? Welche Inhalte bieten mir Möglichkeiten zur gezielten Personalisierung?

## Terminologie

Die Inhaltsanalyse verwendet die folgenden Schlüsselbegriffe:

![Assets und Erlebnisse](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **Erlebnis**: Ein Erlebnis ist der gesamte Text auf einer Web-Seite, der anhand der URL reproduzierbar ist, die der ursprüngliche Benutzer verwendet hat, der die Web-Seite besucht hat. Jedes Erlebnis erhält eine eindeutige Kennung. Seitenänderungen, die zu Änderungen am HTML der Seite führen, führen zu einem neuen Erlebnis.
* **Asset**: Ein Asset ist ein individuelles und einzigartiges Inhaltselement, z. B. ein Bild. Jedes Asset erhält außerdem eine eindeutige Kennung und eine Wahrnehmungs-ID. Eine Wahrnehmungs-ID ist eine Kennung, die für visuell identische Assets freigegeben wird. Perzeptive IDs helfen, Assets zu deduplizieren, die eine andere Asset-URL und daher eine andere Asset-ID haben können, aber wahrnehmbar identisch sind.
* **Attribut**: Ein Attribut ist ein beschreibendes Metadatenelement, das mit einem Erlebnis oder Asset verknüpft ist. Beispiele für ein Attribut sind: Stil der Fotografie, Lesbarkeit, Überzeugungsstrategie, Objektfarbe und Hintergrundfarbe.

## Funktionsweise

Die Inhaltsanalyse verwendet Web-Bildansichtsdaten, die in Ereignisdatensätzen in Experience Platform erfasst wurden. Diese Daten können mithilfe der verschiedenen verfügbaren Methoden erfasst werden: Experience Platform Edge Network (Web-SDK, Server API) oder Analytics-Quell-Connector.

![Inhaltsanalyse - Funktionsweise](assets/aca-overview.gif)


1. Wenn ein(e) Benutzende(r) eine Website [für Content Analytics konfiguriert](config/configuration.md) zeichnet der Experience Platform Web SDK Impressionen und Interaktionen mit Inhalten auf.
1. Der Identity Service und der Feature Service verarbeiten diese Interaktionen. Dieser Prozess besteht aus einem Abrufdienst, der die öffentlich zugänglichen Versionen der konfigurierten URLs, die die Interaktionen definieren, erneut aufruft. Für alle abgerufenen URLs identifiziert der Identity Service die Erlebnisse und Assets eindeutig. Der Feature Service wendet KI-/ML-Services an, um Erlebnisse und Assets sowie Metadaten und Attribute zu ermitteln.
1. Die Ergebnisse dieser Services ([Komponenten, Attribute und Identitäten](/help/content-analytics/report/components.md)) werden verwendet, um die relevanten spezifischen Inhaltsanalysedatensätze in Experience Platform zu aktualisieren.
1. Die Inhaltsanalysedaten können Sie zusammen mit Verhaltensdaten und anderen Suchdaten in einer Customer Journey Analytics-Einrichtung verwenden ([Verbindung](/help/connections/overview.md), [Datenansicht](/help/data-views/data-views.md) und [Workspace](/help/analysis-workspace/home.md)). Dieses Setup bietet die Grundlage für die einzigartigen Einblicke auf Makroebene in Ihren Inhalt. <br/>Sie können Ihre Content Analytics-Berichte und -Analysen mithilfe der [Content Analytics-Vorlage starten](/help/content-analytics/report/report.md#template).

>[!NOTE]
>
>Content Analytics nutzt KI-/ML-Services, die zu ungenauen oder irreführenden Ergebnissen führen können. Daher sollten Sie Ihr Urteilsvermögen nutzen, um KI/ML-generierte Ausgaben zu überprüfen und zu validieren.
>
>Sie können die Registerkarte **[!UICONTROL Feedback]** verwenden, die unter ![InfoOutline](/help/assets/icons/InfoOutline.svg) auf der Hauptbenutzeroberfläche verfügbar ist, um Feedback zu den KI/ML-generierten Ausgaben zu geben.
>

>[!NOTE]
>
>Wenn Sie das Privacy and Security Shield-Add-on lizenziert haben, beachten Sie, dass (alle aus Erlebnissen und Assets generierten Daten) vorbehaltlich Content Analyticss nicht von der DULE-Kennzeichnung oder von kundenverwalteten Schlüsseln abgedeckt werden.
>

>[!NOTE]
>
>Content Analytics [sendet zusätzliche Ereignisse](config/datacollection.md#content-analytics-event) die sich höchstwahrscheinlich auf jede Absprungratendefinition auswirken, die auf der Anzahl der Ereignisse in einer Sitzung oder einer Seite basiert.
>

>[!MORELIKETHIS]
>
>[Reporting für die Inhaltsanalyse](report/report.md)
>[Konfigurieren der Inhaltsanalyse](config/configuration.md)
>[Berechnen von Bounces und Absprungraten in Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446#M454)
>

