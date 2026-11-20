---
title: Vergleich mit Adobe Analytics
description: Übersicht über den Vergleich von Customer Journey Analytics mit Adobe Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: bde36283-86af-4b1a-9cbe-e251676b2951
role: User
autotag-review: '2026-05-19T09:13:47.721Z'
TQID: 'https://experienceleague.adobe.com/MU9ywSyInHtsdzqvxO3yxTSY5bcDvdhnTUkhAgDHmZ4'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
    internal-label: Upgrade
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
    internal-label: Basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 1f480cda20e0b2d54dd42b909bfa8bf8a2bc0c95
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 52%
---
# Vergleich mit Adobe Analytics

In diesem Abschnitt der Dokumentation wird erläutert, wie Sie Adobe Customer Journey Analytics und Adobe Analytics vergleichen sowie die Unterschiede zwischen ihnen verstehen können.

Der grundlegende Unterschied zwischen den beiden Lösungen besteht in der Breite der Daten, die Sie bei der Erstellung Ihrer Berichte und Analysen berücksichtigen können.

In Customer Journey Analytics kann *jede* Datenquelle Teil der Daten sein, die Sie für die Reporting und Analyse verwenden. Adobe Analytics ist in erster Linie auf Online-Daten ausgerichtet, die von Websites und mobilen Apps erfasst werden. Adobe Analytics bietet Funktionen zum Importieren von Daten aus anderen Quellen, aber der Hauptzweck dieser Funktion ist es, mehr Kontext rund um die oben genannten Online-Daten bereitzustellen.

## Datenerfassung

Customer Journey Analytics beruht auf Daten, die in Adobe Experience Platform-Datensätzen gespeichert sind. Sie haben mehrere Möglichkeiten, Daten in diesen Datensätzen zu erfassen und in Experience Platform aufzunehmen. Diese Optionen werden im Abschnitt [Datenaufnahme - Übersicht](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-data-ingestion/data-ingestion) beschrieben.

Adobe Analytics erfasst letztendlich Daten innerhalb der Lösung selbst. Auch hier haben Sie mehrere Möglichkeiten, diese Daten zu erfassen, die im [Adobe Analytics-Implementierungshandbuch](https://experienceleague.adobe.com/de/docs/analytics/implementation/home) beschrieben werden.

Sie können Ihre Report Suite-Daten aus Adobe Analytics mit dem [Analytics-Quell-Connector](https://experienceleague.adobe.com/de/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) in Customer Journey Analytics verwenden. Dieser Connector nimmt Daten, die in Adobe Analytics erfasst werden, in Experience Platform auf. Anschließend können Sie in Customer Journey Analytics eine Verbindung zu diesem Datensatz erstellen. Siehe [Verwenden von Report Suite-Daten aus Adobe Analytics in Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja), um weitere Informationen zu erhalten.

Die Daten in Ihrer Adobe Analytics Report Suite sind unabhängig von den Daten, die in den Adobe Experience Platform-Datensätzen gespeichert sind, aus denen Ihre Customer Journey Analytics-Verbindung besteht. Daher empfiehlt Adobe, die Daten auf jeder Plattform separat auszuwerten, anstatt zu erwarten, dass beide Plattformen dieselben Werte widerspiegeln.

## Datenverarbeitung

Bevor Sie Berichte zu Daten erstellen können, müssen diese Daten häufig verarbeitet werden, um sicherzustellen, dass die Daten ordnungsgemäß für das Reporting verwendet werden können. Datenverarbeitung kann zeitgleich mit der Erfassung oder mit der Berichterstellung erfolgen.

Im Allgemeinen ist Customer Journey Analytics so konzipiert, dass es mit den erfassten und gespeicherten Daten in Experience Platform-Datensätzen zum Zeitpunkt der Berichterstellung funktioniert. Customer Journey Analytics bietet eine leistungsstarke Funktionalität zur Verarbeitung zum Zeitpunkt der Berichterstellung, um sicherzustellen, dass die Daten für Berichte und Analysen bereit sind. [Abgeleitete Felder](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/derived-fields) und [Komponenteneinstellungen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/overview) können geändert und rückwirkend auf historische Daten angewendet werden. Wenn Sie Daten zuordnen, transformieren und validieren müssen, bevor sie in Experience Platform aufgenommen werden, können Sie die Funktion [Datenvorbereitung](https://experienceleague.adobe.com/de/docs/experience-platform/data-prep/home) von Experience Platform verwenden.

In Adobe Analytics erfolgt der Großteil dieser Datenverarbeitung unmittelbar nach der Datenerfassung. Marketing-Kanalregeln, Verarbeitungsregeln, eVar-Persistenz und andere Nachbearbeitungslogiken werden zu diesem Zeitpunkt angewendet und sind in der Report Suite dauerhaft. Änderungen an diesen Konfigurationen wirken sich erst ab diesem Zeitpunkt auf neue eingehende Daten aus.

Siehe [Vergleich der Datenverarbeitung zwischen Adobe Analytics und Customer Journey Analytics](data-processing-comparisons.md) und [Verarbeitungsregeln, VISTA und Klassifizierungen im Vergleich zur Datenvorbereitung](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep), um weitere Informationen zu erhalten.


## Terminologie

Customer Journey Analytics bietet Ihnen Flexibilität bei der Definition von Dimensionen und Metriken, was durch die Flexibilität ermöglicht wird, die die zugrunde liegenden, auf dem Experience-Datenmodell (XDM) basierenden Schemata bieten. Wenn Adobe Analytics beispielsweise Besucher, Besuche und Treffer verwendet, verwendet Customer Journey Analytics Personen, Sitzungen und Ereignisse (Sie können die Namen nach Belieben ändern).

Siehe [Vergleich der Terminologie für Analytics-Daten, die über den Analytics Source Connector übergeben werden](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology), um weitere Informationen zu den Unterschieden in der Terminologie zu erhalten.


## Virtuelle Reporting-Umgebungen und Sandboxes

Adobe Analytics basiert auf dem Konzept der Virtual Report Suites, mit denen Sie Ihre erfassten Daten segmentieren und den Zugriff auf diese segmentierten Daten steuern können.

Customer Journey Analytics hat ein ähnliches Konzept, das „Datenansichten“ genannt wird. Datenansichten sind Container, mit denen Sie bestimmen können, wie Daten aus einer Verbindung interpretiert werden. Sie sind äußerst flexibel, um Dimensionen und Metriken zur Vorbereitung auf Ihre Berichte und Analysen zu spezifizieren und zu konfigurieren.

Experience Platform bietet Sandboxes, die als Container mit Daten und Programmen für eine bestimmte Umgebung fungieren. Die Funktionalität einer Sandbox ist nicht mit einer Virtual Report Suite in Adobe Analytics oder einer Datenansicht in Customer Journey Analytics verbunden. Adobe Analytics selbst hat keine Abhängigkeit oder Beziehung zu Experience Platform-Sandboxes. Customer Journey Analytics unterstützt zwar Experience Platform-Sandboxes, allerdings gibt es einige Aspekte zu bedenken.

Weitere Informationen finden Sie unter [Virtual Report Suites, Datenansichten, Adobe Experience Platform-Sandboxes und der Analytics Source Connector](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc).


## Identitäten

Customer Journey Analytics unterstützt die Identitäten, die Sie als Teil der Schemata definieren, denen die Datensätze entsprechen, die Ihre Daten enthalten. Identitäten sind also ein grundlegendes Konzept von Experience Platform, das Customer Journey Analytics beim Einrichten einer [Verbindung](../../connections/overview.md) verwendet (durch Definition der Personen-ID für jeden Datensatz) und beim Anwenden der [Zuordnung](../../stitching/overview.md) für die kanalübergreifende Analyse. Eine wichtige Identität, die von den Experience Platform SDKs und der API verwendet wird, ist die ECID.

Adobe Analytics verwendet einen klarer definierten Satz von Identitätsfeldern, z. B. die Adobe Analytics-ID (AAID). Bei Verwendung des Analytics-Quell-Connectors erhalten diese Adobe Analytics-Identitätsfelder eine besondere Behandlung. Weitere Informationen sind zu finden unter [AAID, ECID, AACUSTOMID und der Analytics Source Connector](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc).


## Dimensionen hoher Kardinalität

Customer Journey Analytics speichert ganze Dimensionswerte, und es gibt keine Begrenzung dafür, wie viele eindeutige Werte eine Dimension umfassen kann. Im Gegensatz dazu verwendet Adobe Analytics 32-Bit-Hashes, um Dimensionswerte zuzuordnen und so das Reporting und die Speicherung zu optimieren. Dieses Verhalten kann zu Hash[Kollisionen &#x200B;](https://experienceleague.adobe.com/en/docs/analytics/implementation/validate/hash-collisions) Berichten führen. Adobe Analytics fasst Werte auch im Zeileneintrag [Geringer Traffic](https://experienceleague.adobe.com/en/docs/analytics/technotes/low-traffic) zusammen, sobald der eindeutige Grenzwert erreicht ist. Segmente, die diese Dimensionen verwenden, können Diskrepanzen zwischen Adobe Analytics- und Customer Journey Analytics-Berichten anzeigen.

## Unterstützte Funktionen

Einen Überblick über Adobe Analytics-Funktionen und deren Unterstützung durch Customer Journey Analytics finden Sie unter [Customer Journey Analytics-Funktionsunterstützung](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa).
