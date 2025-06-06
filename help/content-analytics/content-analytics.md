---
title: Übersicht der Inhaltsanalyse
description: Ein Überblick über die Inhaltsanalyse
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: dd4adc5acd05aecf0a67072df6688a344e1ce5c9
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 94%

---

# Übersicht der Inhaltsanalyse

Mit der Inhaltsanalyse können Marketing-Fachleute nachvollziehen, wie sich Inhalte auf die von einem Unternehmen definierten wichtigsten Leistungsindikatoren auswirken. Zusätzlich zu den Verhaltensdaten erfasst Content Analytics Daten darüber, wie Inhalte konsumiert werden und wie Inhalte die Auswirkungen steuern. Reagieren Kundinnen und Kunden beispielsweise besser auf einen bestimmten Tonfall, eine bestimmte Farbpalette oder bestimmte Themen? Diese Informationen sowie speziell entwickelte Reporting-Workflows und Vorlagen können Ihnen dabei helfen, noch bessere Analysen durchzuführen und tiefere Einblicke in Customer Journey-Daten in Customer Journey Analytics zu erhalten.

Die Inhaltsanalyse verwendet eine auf KI und maschinellem Lernen basierende **Featurisierungs-Services**, um Inhalte in Komponenten und Attribute aufzuschlüsseln. Durch die Erstellung eines strukturierten Metadatenprofils für alle Ihre Inhalte können Sie analysieren, welche Inhalte und welche Attribute dieser Inhalte zu Geschäftsergebnissen führen.

Zusätzlich zur Erstellung dieses strukturierten Metadatenprofils bietet die Inhaltsanalyse einen **Identity Service** der Assets und Erlebnisse mithilfe einer einzigen Kennung identifiziert. Der Identity Service kann erkennen, wenn dasselbe Asset an mehr als einer Stelle angezeigt wird. In diesem Fall werden die Instanzen dieses Assets als das gleiche Asset behandelt, was eine ganzheitlichere Ansicht der Nutzung und des Konsums der Inhalte ermöglicht.

## Wert

Die Inhaltsanalyse bietet zunehmend Mehrwert:

1. **Inhaltsnutzung**: Mit der Inhaltsanalyse erhalten Sie Einblicke darüber, welche Assets Impressionen erhalten und wo Assets Impressionen erhalten. Diese Einblicke helfen Ihnen, zu erkennen, ob Assets in Ihren Web-Eigenschaften zu wenig oder zu häufig verwendet werden.
1. **Interaktionen mit Inhalten**: Die Inhaltsanalyse kann Einblicke in Interaktionen bieten, z. B. die durchschnittliche Clickthrough-Rate für Assets mit bestimmten Attributen. Diese Einblicke helfen Ihnen, festzustellen, ob bestimmte Arten von Erlebnissen weiterhin effektiv sind.
1. **Inhalts-Journeys**: Darüber hinaus können Sie in Kombination mit allen anderen in Experience Platform verfügbaren Daten zusätzliche Einblicke in Ihre Inhalts-Journeys erhalten. Zum Beispiel, ob bestimmte Inhalte zusätzlich zur Interaktion zu Konversionen führen. Und mit diesem Wissen können Sie den ROI für verschiedene Inhaltstypen bestimmen.
1. **Inhaltspersonalisierung**: Mit der Inhaltsanalyse können Sie letztendlich anhand Ihrer Einblicke handeln und diese Einblicke verwenden, um zu bestimmen, wie Sie Geld für Inhalte ausgeben. Sollte ich beispielsweise bestimmte Inhaltstypen an bestimmte Zielgruppen senden? Welche Inhalte bieten mir Möglichkeiten zur gezielten Personalisierung?

## Terminologie

Die Inhaltsanalyse verwendet die folgenden Schlüsselbegriffe:

![Assets und Erlebnisse](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **Erlebnis**: Ein Erlebnis ist der gesamte Text auf einer Web-Seite, der anhand der URL reproduzierbar ist, die die Person verwendet hat, die diese Web-Seite ursprünglich besucht hat. Jedes Erlebnis erhält eine eindeutige Kennung. Seitenänderungen, die Änderungen am HTML-Code der Seite nach sich ziehen, führen zu einem neuen Erlebnis.
* **Asset**: Ein Asset ist ein individuelles und einzigartiges Inhaltselement, z. B. ein Bild. Jedes Asset erhält außerdem eine eindeutige Kennung und eine Wahrnehmungs-ID. Eine Wahrnehmungs-ID ist eine Kennung, die für visuell identische Assets freigegeben wird. Wahrnehmungs-IDs helfen, Assets zu deduplizieren, die ggf. eine andere Asset-URL und daher auch eine andere Asset-ID aufweisen, aber identisch wahrgenommen werden.
* **Attribut**: Ein Attribut ist ein beschreibendes Metadatenelement, das mit einem Erlebnis oder Asset verknüpft ist. Beispiele für ein Attribut sind: Stil der Fotografie, Lesbarkeit, Überzeugungsstrategie, Objektfarbe und Hintergrundfarbe.

## Funktionsweise

Content Analytics verwendet Web-Bildansichtsdaten in Ereignisdatensätzen in Experience Platform, um [Inhaltsereignisdaten zu erfassen](config/datacollection.md). Außerdem wird diese Inhaltsdatenerfassung mit der (vorhandenen) Datenerfassungsimplementierung von Verhaltensdaten kombiniert.

![Inhaltsanalyse – Funktionsweise](assets/aca-overview.gif)

1. Wenn eine Benutzerin oder ein Benutzer eine [für Content Analytics konfigurierte](config/configuration.md) Site besucht, zeichnet das Experience Platform Web SDK Impressions und Interaktionen mit Inhalten auf.
1. Identity Service und Featurisierungs-Service verarbeiten diese Interaktionen. Dieser Prozess umfasst einen Abrufdienst, der die öffentlich zugänglichen Versionen der konfigurierten URLs, die die Interaktionen definieren, erneut aufruft. Bei allen abgerufenen URLs bewirkt der Identity Service eine eindeutige Identifizierung der Erlebnisse und Assets. Der Featurization Service wendet KI/ML-Services an, um Erlebnisse sowie Metadaten und Attribute von Assets zu ermitteln.
1. Die Ergebnisse dieser Services ([Komponenten, Attribute und Identitäten](/help/content-analytics/report/components.md)) werden verwendet, um die relevanten spezifischen Datensatze der Inhaltsanalyse in Experience Platform zu aktualisieren.
1. Sie können Daten der Inhaltsanalyse zusammen mit Verhaltens- und anderen Lookup-Daten in einem Customer Journey Analytics-Setup ([Verbindung](/help/connections/overview.md), [Datenansicht](/help/data-views/data-views.md) und [Arbeitsbereich](/help/analysis-workspace/home.md)) verwenden. Dieses Setup bildet die Grundlage für die einzigartigen Erkenntnisse zu Ihren Inhalten auf Makroebene. <br/>Um sofort mit Ihren Content Analytics-Berichten und -Analysen loszulegen, steht Ihnen die [Inhaltsanalysevorlage](/help/content-analytics/report/report.md#template) zur Verfügung.


>[!NOTE]
>
>Content Analytics nutzt KI/ML-Services, die zu ungenauen oder irreführenden Ergebnissen führen können. Daher sollten Sie auf Ihr eigenes Urteilsvermögen vertrauen, um KI/ML-generierte Ausgaben zu überprüfen und zu validieren.
>
>Sie können die Registerkarte **[!UICONTROL Feedback]** verwenden, die in der Hauptbenutzeroberfläche unter ![InfoOutline](/help/assets/icons/InfoOutline.svg) verfügbar ist, um Feedback zu den KI/ML-generierten Ausgaben zu geben.
>

>[!NOTE]
>
>Wenn Sie das Privacy and Security Shield-Add-on lizenziert haben, beachten Sie, dass (alle aus Erlebnissen und Assets generierten Daten) vorbehaltlich Content Analyticss nicht von der DULE-Kennzeichnung oder von kundenverwalteten Schlüsseln abgedeckt werden. Außerdem ist Content Analytics kein HIPAA-fähiger Service.
>


>[!MORELIKETHIS]
>
>[Reporting für die Inhaltsanalyse](report/report.md)
>&#x200B;>[Konfigurieren der Inhaltsanalyse](config/configuration.md)
>&#x200B;>[Berechnen von Bounces und Bounce-Raten in Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446?profile.language=de&lang=de#M454)
>

