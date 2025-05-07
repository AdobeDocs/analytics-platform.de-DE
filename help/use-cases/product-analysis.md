---
title: Produktanalyse in Customer Journey Analytics
description: Erfahren Sie, welche Funktionen Sie in Customer Journey Analytics verwenden können, um Produktanalysen effektiv durchzuführen.
exl-id: b185a2ed-18c8-4fb3-8c69-693d5fee0e67
source-git-commit: 40e6fbd49a92690253855e314e9999da28a7d2f6
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 1%

---

# Produktanalyse in Customer Journey Analytics

Bei der Produktanalyse geht es darum zu verstehen, wie Benutzende in jeder Phase ihres Journey mit Ihrem Produkt interagieren. Sie umfasst die Analyse von Daten, um Erkenntnisse über das Benutzerverhalten, die Produktleistung und die Wachstumschancen zu gewinnen. Eine effektive Produktanalyse hilft Teams, fundierte Entscheidungen zu treffen, um die Benutzererlebnisse zu verbessern, die Interaktion zu fördern und Geschäftsziele zu erreichen.

Customer Journey Analytics bietet Teams Tools zur Analyse und Optimierung von Produkterlebnissen mit folgenden Funktionen:

* **Produktdaten skaliert verwalten** Einfaches Aufnehmen, Transformieren und Verwalten von Produktdaten, um Ihre Geschäftsanforderungen zu erfüllen und zuverlässige Einblicke zu gewährleisten.
* **Messung von Akquise und Aktivierung**: Verfolgen Sie, wie neue Benutzer Ihr Produkt entdecken und mit Ereignissen interagieren, die den ersten Wert fördern.
* **Interaktion und Akzeptanz messen**: Verstehen, wie Benutzer den Produkttrichter durchlaufen, Reibungspunkte identifizieren und die Akzeptanz wichtiger Funktionen verfolgen.
* **Kundenbindung und Abwanderung messen** Analysieren Sie die Benutzerbindung im Laufe der Zeit, identifizieren Sie Indikatoren für Abwanderung und entwickeln Sie Strategien, um Abbrüche zu reduzieren und die Kundentreue zu steigern.
* **Action Product Insights**: Verwandeln Sie datengesteuerte Insights in umsetzbare Strategien, um das Anwendererlebnis zu verbessern und ein nachhaltiges Produktwachstum zu fördern.
* **Teilen Sie Erkenntnisse mit Ihrer Organisation**: Kommunizieren Sie wichtige Erkenntnisse teamübergreifend, um die Bemühungen aufeinander abzustimmen, die Zusammenarbeit zu fördern und sicherzustellen, dass alle auf gemeinsame Produkt- und Geschäftsziele hinarbeiten.

Durch die Nutzung dieser Funktionen ermöglicht Customer Journey Analytics es Ihnen, das volle Potenzial Ihres Produkts zu erschließen und einen nahtlosen, datengesteuerten Ansatz zur Steigerung des Benutzer- und Geschäftserfolgs zu erstellen.

## Verwalten von Produktdaten im benötigten Umfang

Präzise Produktdaten sind der Eckpfeiler einer effektiven Produktanalyse. Die Datenaufnahme bezieht sich auf den Prozess der Instrumentierung und Erfassung von Produktdaten, während das Daten-Management die Transformation und Pflege dieser Daten umfasst, um sicherzustellen, dass sie Ihren analytischen Anforderungen entsprechen.

Mit den folgenden Funktionen in Adobe Experience Platform und Customer Journey Analytics können Sie Ihre Produktdaten skaliert aufnehmen und verwalten:

* Adobe Experience Platform
   * [Datensätze&#x200B;](https://experienceleague.adobe.com/de/docs/experience-platform/catalog/datasets/overview)
   * [Datenvorbereitung&#x200B;](https://experienceleague.adobe.com/de/docs/experience-platform/data-prep/home)
   * [Daten-Distiller&#x200B;](https://experienceleague.adobe.com/de/docs/experience-platform/query/data-distiller/overview)
* Customer Journey Analytics
   * [Verbindungen&#x200B;](/help/connections/overview.md)
   * [Datenansichten](/help/data-views/data-views.md) einschließlich [abgeleiteter Felder&#x200B;](/help/data-views/derived-fields/derived-fields.md)
   * [Segmente&#x200B;](/help/components/filters/filters-overview.md)
   * [Berechnete Metriken](/help/components/calc-metrics/calc-metr-overview.md)
   * [Geführte Analyse&#x200B;: Zeitleiste&#x200B;](/help/guided-analysis/types/timeline.md)

## Erfassen und Aktivieren von Maßnahmen

Das Produktwachstum hängt von umsetzbaren Einblicken aus der oberen Hälfte des Trichters ab, die neue Benutzende anziehen, Konversionspfade offenbaren und Reibungen entlang des Journey beseitigen.

* Die Akquise verfolgt neue Benutzer, die zu Ihrem Produkt kommen, einschließlich der Art und Weise, wie sie ankommen und welche Bemühungen am effektivsten oder am wenigsten effektiv sind.
* Activation überwacht neue Benutzer, die mit Ihrem ersten Wertereignis interagieren, das entsprechend Ihren spezifischen Zielen definiert wird.

![Aktives Wachstum](/help/guided-analysis/assets/active.png)

![Interaktionsanalyse](/help/guided-analysis/assets/feature-matrix.png)

Mit den folgenden Funktionen in Customer Journey Analytics können Sie Akquise und Aktivierung effektiv messen:

* [Geführte Analyse&#x200B;: Aktives Wachstum](/help/guided-analysis/types/active-growth.md)
* [Geführte Analyse: Nettowachstum](/help/guided-analysis/types/net-growth.md)
* [Geführte Analyse: Trends](/help/guided-analysis//types/trends.md)
* [Attributionsbedienfeld&#x200B;](/help/analysis-workspace/c-panels/attribution.md)
* [Freiformtabelle](/help/analysis-workspace/c-panels/freeform-panel.md) die die Dimension „Marketing-Kanal“ enthält (Erstellen mithilfe eines [abgeleiteten Felds](/help/data-views/derived-fields/derived-fields.md))

## Interaktion und Einführung von Maßnahmen

Die Akquise neuer Benutzer erweitert den oberen Rand Ihres Produkttrichters. Die Interaktion konzentriert sich darauf, diese Benutzer weiter den Trichter hinunter zu führen und Hindernisse für ihren Erfolg zu beseitigen. Ihr Erfolg ist ein direkter Antrieb für Ihren Geschäftserfolg.

Mit den folgenden Funktionen in Customer Journey Analytics können Sie die Interaktion mit und die Akzeptanz von Produkten verfolgen:

* [Geführte Analyse: Interaktion](/help/guided-analysis/types/engagement.md)
* [Geführte Analyse: Trends](/help/guided-analysis/types/trends.md)
* [Geführte Analyse: Häufigkeit](/help/guided-analysis/types/frequency.md)
* [Geführte Analyse: Trichter](/help/guided-analysis/types/funnel.md)
* [Geführte Analyse: Konversionstrends](/help/guided-analysis/types/conversion-trends.md)
* [Geführte Analyse: Auswirkungen der Version](/help/guided-analysis/types/release-impact.md)
* [Geführte Analyse: Auswirkung der ersten Verwendung&#x200B;](/help/guided-analysis/types/first-use-impact.md)
* [Geführte Analyse: Zeitleiste](/help/guided-analysis/types/timeline.md)
* [Freiformtabellen&#x200B;](/help/analysis-workspace/c-panels/freeform-panel.md)
* [Fluss](/help/analysis-workspace/visualizations/c-flow/flow.md)

## Messung von Kundenbindung und Abwanderung

Die Kundenbindung misst, wie viele Benutzer nach der ersten Akquise und Aktivierung weiterhin mit dem Produkt interagieren. Leistungsstarke Produkte gewährleisten eine stabile, loyale Benutzerbasis, indem sie die Interaktion mit den Funktionen maximieren, die am stärksten mit der weiteren Nutzung korrelieren. Ein zurückgehaltener Benutzer kehrt zurück und interagiert im Laufe der Zeit mit dem Produkt, während ein abgewanderter Benutzer dies nicht tut. Produkt-Teams verfolgen die Kundenbindung, um die Funktionen zu identifizieren, die die fortlaufende Interaktion fördern, und entwerfen Interventionen, die die Benutzer auf das Kundenverhalten umstellen.

![Retentionsanalyse](/help/guided-analysis/assets/retention.png)

Mit den folgenden Funktionen in Customer Journey Analytics können Sie die Kundenbindung und Abwanderung effektiv verfolgen:

* [Geführte Analyse: ](/help/guided-analysis/types/retention.md)&#x200B;
* [Geführte Analyse: Aktives Wachstum](/help/guided-analysis/types/active-growth.md)
* [Geführte Analyse: Nettowachstum](/help/guided-analysis/types/net-growth.md)
* [Kohortentabelle&#x200B;](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)

## Umsetzbare Produkteinblicke

Erkenntnisse liefern nur dann einen Wert, wenn sie die Aktion steuern. Konvertieren Sie Analytics-Ergebnisse in Aktionen, die das Benutzererlebnis verbessern und das langfristige Produktwachstum unterstützen.

Mit den folgenden Funktionen in Experience Cloud können Sie effektiv auf Einblicke reagieren:

* [Erstellen und Veröffentlichen von Zielgruppen](/help/components/audiences/publish.md)&#x200B; zur Aktivierung über Customer Journey Analytics
* Zielgruppen über Experience Cloud-Produkte aktivieren:
   * [Führen Sie ](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/content-management/content-experiment/get-started-experiment) in AJO und Adobe Target aus und messen Sie mithilfe des Bedienfelds [Experimentieren“ die Wirkung von Varianten in Customer Journey Analytics](/help/analysis-workspace/c-panels/experimentation.md)
   * [Bereitstellen von In-App-Interaktionen](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/channels/in-app/get-started-in-app) für Benutzende in AJO
* [Aktivieren von Zielgruppen](https://experienceleague.adobe.com/de/docs/experience-platform/destinations/ui/activate/activation-overview) für externe Ziele mit Adobe Real-Time CDP&#x200B;

## Freigeben von Einblicken für die Organisation&#x200B;

Kommunikation wichtiger Ergebnisse über Teams hinweg, um die Bemühungen aufeinander abzustimmen, die Zusammenarbeit zu fördern und sicherzustellen, dass alle auf gemeinsame Produkt- und Geschäftsziele hinarbeiten.

![Geführte Analyse in Workspace](assets/guided-analysis-workspace.png)

Mit den folgenden Funktionen in Customer Journey Analytics können Sie Einblicke effektiv freigeben:

* [Teilen](/help/analysis-workspace/curate-share/share-projects.md) Geführte Analyseansichten, die auf bestimmte Geschäftsfragen zugeschnitten sind, sodass Verbraucher ihre nächste Frage selbst beantworten können
* Kombinieren Sie geführte Analysen, Bedienfelder und Visualisierungen in einem umfassenden Dashboard in [Analysis Workspace](/help/analysis-workspace/home.md)
* Erstellen Sie [ mobile Scorecard ](/help/mobile-app/home.md) wichtigen Produkteinblicken für Führungskräfte und andere Verbraucher unterwegs
