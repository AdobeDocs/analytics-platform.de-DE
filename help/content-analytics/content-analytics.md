---
title: Übersicht über Content Analytics
description: Erfahren Sie mehr über den Wert und die Terminologie von Content Analytics und lernen Sie, wie Content Analytics funktioniert.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
TQID: https://experienceleague.adobe.com/x5FpRmZ-Wv6pPxYBEAyDzRqUSUpmwHFwbi55FwVKT5A
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad5685a0-8296-4a0c-814c-658c10b4af12id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c4147b6e-073b-4d3c-9ab1-d60f2f4434efid: d095671a-1355-40aa-8b5f-06c33c68080bid: e0eb8757-182f-49f3-94a4-1587d16f5094id: e1e0219c-f879-479f-8427-888ed2a6e9c2id: eb30f47f-d87a-400f-8f78-63ce7979ff56id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: d9715c3da9893e1c47b702acb4daef5e666bedd7
workflow-type: tm+mt
source-wordcount: 905
ht-degree: 55%

---


# Überblick über Content Analytics

Mit Content Analytics können Marketing-Fachleute nachvollziehen, wie sich Inhalte auf die von einem Unternehmen definierten wichtigsten Leistungsindikatoren auswirken. Zusätzlich zu den Verhaltensdaten erfasst Content Analytics Daten darüber, wie Inhalte genutzt werden und wie sich Inhalte auf die Auswirkungen auswirken. Reagieren Kundinnen und Kunden beispielsweise besser auf einen bestimmten Tonfall, eine bestimmte Farbpalette oder bestimmte Themen? Diese Informationen sowie speziell entwickelte Reporting-Workflows und Vorlagen können Ihnen dabei helfen, noch bessere Analysen durchzuführen und tiefere Einblicke in Customer Journey-Daten in Customer Journey Analytics zu erhalten.

Content Analytics verwendet eine auf KI und maschinellem Lernen basierende **Featurisierungs-Services**, um Inhalte in Komponenten und Attribute aufzuschlüsseln. Durch die Erstellung eines strukturierten Metadatenprofils für alle Ihre Inhalte können Sie analysieren, welche Inhalte und welche Attribute dieser Inhalte Geschäftsergebnisse fördern.

Zusätzlich zur Erstellung dieses strukturierten Metadatenprofils bietet Content Analytics einen **Identity Service** der Assets und Erlebnisse mithilfe einer einzigen Kennung identifiziert. Der Identity Service kann erkennen, wenn dasselbe Asset an mehr als einer Stelle angezeigt wird. In diesem Fall werden die Instanzen dieses Assets als das gleiche Asset behandelt, was eine ganzheitlichere Ansicht der Nutzung und des Konsums der Inhalte ermöglicht.

## Wert

Content Analytics bietet zunehmend Mehrwert:

1. **Inhaltsnutzung**: Mit Content Analytics erhalten Sie Erkenntnisse dazu, welche Assets Impressions erhalten und wo Assets Impressions erhalten. Diese Einblicke helfen Ihnen zu erkennen, ob Assets in Ihren Web- und Mobile-Eigenschaften nicht oder übermäßig verwendet werden.
1. **Interaktionen mit Inhalten**: Content Analytics kann Erkenntnisse zu Interaktionen bieten, z. B. die durchschnittliche Clickthrough-Rate für Assets mit bestimmten Attributen. Diese Einblicke helfen Ihnen, festzustellen, ob bestimmte Arten von Erlebnissen weiterhin effektiv sind.
1. Content-Journey: Darüber hinaus können Sie in Kombination mit allen anderen in Experience Platform verfügbaren Daten zusätzliche Einblicke in Ihre Content-Journey erhalten, z. B. ob bestimmte Inhalte zusätzlich zur Interaktion zu Konversionen führen. Zum Beispiel, ob bestimmte Inhalte zusätzlich zur Interaktion zu Konversionen führen. Und mit diesem Wissen können Sie den ROI für verschiedene Inhaltstypen bestimmen.
1. **Inhaltspersonalisierung**: Mit der Content Analytics können Sie letztendlich anhand Ihrer Erkenntnisse handeln und diese Erkenntnisse verwenden, um zu bestimmen, wie Sie Geld für Inhalte ausgeben. Sollte ich beispielsweise bestimmte Inhaltstypen an bestimmte Zielgruppen senden? Welche Inhalte bieten mir Möglichkeiten zur gezielten Personalisierung?

## Terminologie

Content Analytics verwendet die folgenden Schlüsselbegriffe:

![Assets und Erlebnisse](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **Erlebnis**: Ein Erlebnis ist der gesamte Text auf einer Web-Seite, der anhand der URL reproduzierbar ist, die der ursprüngliche Benutzer für den Besuch der Web-Seite verwendet hat. Oder die Kombination aus Text, Assets und Klick auf Aktionen in einer Mobile App. Jedes Erlebnis erhält eine eindeutige Kennung.
* **Asset**: Ein Asset ist ein individuelles und einzigartiges Inhaltselement, z. B. ein Bild. Jedes Asset erhält außerdem eine eindeutige Kennung und eine Wahrnehmungs-ID. Eine Wahrnehmungs-ID ist eine Kennung, die für visuell identische Assets freigegeben wird. Perzeptive IDs helfen, Assets zu deduplizieren, die eine andere Asset-URL und daher eine andere Asset-ID haben können, aber wahrnehmbar identisch sind.
* **Attribut**: Ein Attribut ist ein beschreibendes Metadatenelement, das mit einem Erlebnis oder Asset verknüpft ist. Beispiele für ein Attribut sind: Stil der Fotografie, Lesbarkeit, Überzeugungsstrategie, Objektfarbe und Hintergrundfarbe.

## Funktionsweise

Content Analytics verwendet Web- und mobile Bildansichtsdaten aus Experience Platform-Ereignisdatensätzen [Erfassen von Inhaltsereignisdaten](config/datacollection.md). Für diese Inhaltserlebnisereignisse müssen die Daten mit Experience Platform Edge Network erfasst werden (Web SDK, Mobile SDK, Server-API). Verhaltensdaten können mit dem Web SDK, Mobile SDK oder dem Analytics Source Connector erfasst werden.

![Content Analytics – Funktionsweise](assets/aca-overview-new.gif)

1. Wenn ein(e) Benutzende(r) eine Website oder [ App besucht (für Content Analytics konfiguriert](config/configuration.md) zeichnet das Experience Platform Web oder Mobile SDK Impressionen und Interaktionen mit Inhalten auf.
1. Der Identity and Feature Service verarbeitet diese Interaktionen. Dieser Prozess umfasst einen Abrufdienst, der die öffentlich zugänglichen Versionen der konfigurierten URLs, die die Interaktionen definieren, erneut aufruft. Bei allen abgerufenen URLs bewirkt der Identity Service eine eindeutige Identifizierung der Erlebnisse und Assets. Der Feature Service wendet KI-/ML-Services an, um Erlebnis- und Asset-Metadaten und -Attribute zu ermitteln.
1. Die Ergebnisse dieser Services ([Komponenten, Attribute und Identitäten](/help/content-analytics/report/components.md)) werden verwendet, um die relevanten spezifischen Content Analytics-Datensätze in Experience Platform zu aktualisieren.
1. Sie können die Content Analytics-Daten zusammen mit Verhaltensdaten und anderen Lookup-Daten in einer Customer Journey Analytics-Einrichtung ([Connection](/help/connections/overview.md), [Data view](/help/data-views/data-views.md) und [Workspace](/help/analysis-workspace/home.md)) verwenden. Dieses Setup bildet die Grundlage für die einzigartigen Einblicke auf Makroebene in Ihren Inhalt. <br/>Mit der [Content Analytics-Vorlage können Sie Ihre Content Analytics-Berichte und -Analysen schnell ](/help/content-analytics/report/report.md#template).


>[!NOTE]
>
>Content Analytics nutzt KI/ML-Services, die zu ungenauen oder irreführenden Ergebnissen führen können. Daher sollten Sie auf Ihr eigenes Urteilsvermögen vertrauen, um KI/ML-generierte Ausgaben zu überprüfen und zu validieren.
>
>Sie können die Registerkarte **[!UICONTROL Feedback]** verwenden, die in der Hauptbenutzeroberfläche unter ![InfoOutline](/help/assets/icons/InfoOutline.svg) verfügbar ist, um Feedback zu den KI/ML-generierten Ausgaben zu geben.
>

>[!NOTE]
>
>Wenn Sie das Privacy and Security Shield-Add-on lizenziert haben, beachten Sie, dass die DULE-Kennzeichnung oder kundenverwaltete Schlüssel keine Erlebnisse und Assets abdecken, die Content Analytics unterliegen. Außerdem ist Content Analytics kein HIPAA-fähiger Dienst.
>

>[!IMPORTANT]
>
>Content Analytics unterstützt nur Funktionen auf Englisch.
>


>[!MORELIKETHIS]
>
>[Content Analytics-Berichte](report/report.md)
>[Konfigurieren von Content Analytics](config/configuration.md)
>[Berechnen von Bounces und Bounce-Raten in Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/adobe-analytics-3/calculating-bounces-bounce-rate-in-adobe-customer-journey-analytics-options-and-implications-12722)
>

