---
title: Vergleich mit Adobe Analytics
description: Übersicht über den Vergleich von Customer Journey Analytics mit Adobe Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: bde36283-86af-4b1a-9cbe-e251676b2951
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: ht
source-wordcount: '777'
ht-degree: 100%

---

# Vergleich mit Adobe Analytics

In diesem Abschnitt der Dokumentation wird erläutert, wie Sie Adobe Customer Journey Analytics und Adobe Analytics vergleichen sowie die Unterschiede zwischen ihnen verstehen können.

Der grundlegende Unterschied zwischen den beiden Lösungen besteht in der Breite der Daten, die Sie bei der Erstellung Ihrer Berichte und Analysen berücksichtigen können.

In Customer Journey Analytics kann *jede* Datenquelle Teil der Daten sein, die Sie für die Reporting und Analyse verwenden. Adobe Analytics ist in erster Linie auf Online-Daten ausgerichtet, die über Websites und mobile Apps erfasst werden. Adobe Analytics bietet zwar Möglichkeiten, Daten aus anderen Quellen zu importieren, doch der Hauptzweck besteht darin, den zuvor erwähnten Online-Daten mehr Kontext zu geben.

## Datenerfassung

Customer Journey Analytics beruht auf Daten, die in Adobe Experience Platform-Datensätzen gespeichert sind. Sie haben mehrere Möglichkeiten, Daten in diesen Datensätzen zu erfassen und in Experience Platform aufzunehmen. Diese Optionen werden im Abschnitt [Datenaufnahme – Übersicht](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/data-ingestion.html?lang=de) beschrieben.

Adobe Analytics erfasst letztendlich Daten innerhalb der Lösung selbst. Auch hier haben Sie mehrere Möglichkeiten, diese Daten zu erfassen, die im [Implementierungshandbuch für Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=de) genauer beschrieben werden.

Sie können Ihre Report Suite-Daten aus Adobe Analytics mit dem [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de) in Customer Journey Analytics verwenden. Dieser Connector nimmt Daten, die in Adobe Analytics erfasst werden, in Experience Platform auf. Anschließend können Sie eine Verbindung zu diesem Datensatz im Customer Journey Analytics erstellen. Siehe [Verwenden von Report Suite-Daten aus Adobe Analytics in Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=de), um weitere Informationen zu erhalten.


## Datenverarbeitung

Bevor Sie Berichte zu Daten erstellen können, müssen diese Daten häufig verarbeitet werden, um sicherzustellen, dass die Daten ordnungsgemäß für das Reporting verwendet werden können. Datenverarbeitung kann zeitgleich mit der Erfassung oder mit der Berichterstellung erfolgen.

Im Allgemeinen kann Customer Journey Analytics mit den Daten verwendet werden, die zeitgleich zur Berichterstellung in einem Experience Platform-Datensatz erfasst und gespeichert wurden. Customer Journey Analytics bietet eine leistungsstarke Funktionalität zur Verarbeitung zum Zeitpunkt der Berichterstellung, um sicherzustellen, dass die Daten für Berichte und Analysen bereit sind. Wenn Sie Daten vor der Erfassung in Experience Platform zuordnen, transformieren und validieren müssen, können Sie die Funktionalität [Datenvorbereitung](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de) von Experience Platform verwenden.

In Adobe Analytics erfolgt der Großteil dieser Datenverarbeitung unmittelbar nach der Datenerfassung.

Siehe [Vergleich der Datenverarbeitung zwischen Adobe Analytics und Customer Journey Analytics](data-processing-comparisons.md) und [Verarbeitungsregeln, VISTA und Klassifizierungen im Vergleich zur Datenvorbereitung](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=de), um weitere Informationen zu erhalten.


## Terminologie

Customer Journey Analytics gibt Ihnen eine Flexibilität bei der Definition von Dimensionen und Metriken, was durch die Flexibilität ermöglicht wird, die die zugrunde liegenden Schemata bieten, welche auf dem Experience-Datenmodell (XDM) basieren. Dort wo Adobe Analytics beispielsweise Besucherinnen und Besucher, Besuche und Treffer verwendet, verwendet Customer Journey Analytics Personen, Sitzungen und Ereignisse als gleichwertige Konzepte (aber Sie können die Benennung nach Bedarf ändern).

Siehe [Vergleich der Terminologie für Analytics-Daten, die über den Analytics Source Connector übergeben werden](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology.html?lang=de), um weitere Informationen zu den Unterschieden in der Terminologie zu erhalten.


## Virtuelle Reporting-Umgebungen und Sandboxes

Adobe Analytics basiert auf dem Konzept von Virtual Report Suites, mit denen Sie Ihre erfassten Daten segmentieren und den Zugriff auf diese segmentierten Daten steuern können.

Customer Journey Analytics hat ein ähnliches Konzept, das „Datenansichten“ genannt wird. Datenansichten sind Container, mit denen Sie bestimmen können, wie Daten aus einer Verbindung interpretiert werden. Sie sind äußerst flexibel, um Dimensionen und Metriken zur Vorbereitung auf Ihre Berichte und Analysen zu spezifizieren und zu konfigurieren.

Experience Platform bietet Sandboxes, die als Container mit Daten und Anwendungen für eine bestimmte Umgebung betrachtet werden können. Die Funktionalität einer Sandbox ist nicht mit einer Virtual Report Suite in Adobe Analytics oder einer Datenansicht in Customer Journey Analytics verbunden. Adobe Analytics selbst hat keine Abhängigkeit oder Beziehung zu Experience Platform-Sandboxes. Customer Journey Analytics unterstützt zwar Experience Platform-Sandboxes, allerdings gibt es einige Aspekte zu bedenken.

Weitere Informationen finden Sie unter [Virtual Report Suites, Datenansichten, Adobe Experience Platform-Sandboxes und der Analytics Source Connector](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=de).


## Identitäten

Customer Journey Analytics unterstützt die Identitäten, die Sie als Teil der Schemata definieren, denen die Datensätze entsprechen, die Ihre Daten enthalten. Identitäten sind also ein grundlegendes Konzept von Experience Platform, das Customer Journey Analytics beim Einrichten einer [Verbindung](../../connections/overview.md) verwendet (durch Definition der Personen-ID für jeden Datensatz) und beim Anwenden der [Zuordnung](../../stitching/overview.md) für die kanalübergreifende Analyse. Eine wichtige Identität, die von den SDKs und der API von Experience Platform verwendet wird, ist die Experience Cloud-ID (ECID).

Adobe Analytics verwendet einen stärker definitiven Satz von Identitätsfeldern, z. B. die Adobe Analytics-ID (AAID). Bei Verwendung des Analytics-Quell-Connectors werden diese Adobe Analytics-Identifizierungsfelder besonders behandelt. Weitere Informationen sind zu finden unter [AAID, ECID, AACUSTOMID und der Analytics Source Connector](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=de).


## Unterstützte Funktionen

Eine Übersicht über die Adobe Analytics-Funktionen und die Unterstützung dieser Funktionen durch Customer Journey Analytics finden Sie unter [Unterstützung von Customer Journey Analytics-Funktionen](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa.html?lang=de).
