---
title: Vergleichen von Customer Journey Analytics mit BI-Lösungen
description: Vergleichen von Customer Journey Analytics mit BI-Lösungen
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: ae66cd06-7ec1-4174-a3cf-939c3a66b840
source-git-commit: eb9b749a5c61da3b4b5d2eeeed93bf5e4702a415
workflow-type: tm+mt
source-wordcount: '1649'
ht-degree: 95%

---

# Vergleichen von Customer Journey Analytics mit BI-Lösungen

Mit dem aktuellen Fokus auf Kundenerlebnisse benötigen Marken fortschrittliche Lösungen, um die ganzheitliche Customer Journey besser zu verstehen. Wenn Sie diese vollständige Journey verstehen, können Sie wertvolle Einblicke darin gewinnen, wie Online- und Offline-Kanäle die Kundschaft ansprechen und so Konversionen, Kundenbindung und Loyalität steigern. Eine Customer Journey in diesem Zusammenhang kann die einfache Online-Bestellung einer Mahlzeit in einer Sushi-Restaurantkette sein. Oder der Kauf eines neuen Autos, bei dem die Kundin oder der Kunde eine Online-Recherche mit Besuchen im Ausstellungsraum und einem endgültigen persönlichen Kauf kombiniert.

Viele Organisationen haben ihre kanalübergreifenden Daten in einem Data Lake oder Data Warehouse konsolidiert. Business Intelligence(BI)-Tools werden auf Basis dieser Datenspeicher verwendet, um Berichte, Visualisierungen und Einblicke bereitzustellen, die das Geschäft benötigt, um die Customer Journey zu verstehen. Häufig dient diese Kombination von Lösungen und Tools von Natur aus einem allgemeinen Zweck und ist nicht explizit auf die Kundschaft ausgerichtet. Customer Journey Analytics konzentriert sich auf die Unterstützung der Verantwortlichen für das Kundenerlebnis, z. B. Expertinnen und Experten im Marketing, in der Datenanalyse und in der Datenwissenschaft. Das Tool ermöglicht es ihnen, die Customer Journey in Echtzeit im vollen Kontext über alle Kanäle hinweg zu visualisieren, und das ohne die Einschränkungen, die viele andere BI-Tools haben.

In diesem Abschnitt der Dokumentation werden die grundlegenden Unterschiede zwischen Customer Journey Analytics und häufig verwendeten BI-Tools erläutert. Zunächst wird der allgemeine Workflow zum Erreichen des oben genannten Ziels – die Customer Journey zu verstehen – untersucht. Anschließend werden weitere Details dazu bereitgestellt, wie Daten auf unterschiedliche Weise von Customer Journey Analytics und BI-Tools gespeichert, erfasst und abgefragt werden. Schließlich werden die Unterschiede bezüglich der Visualisierungsfunktionen erklärt.

## Traditioneller BI-Workflow

Ein häufiges Hindernis bei herkömmlichen Ansätzen zur Analyse von Customer Journeys besteht darin, dass sie nicht kundenzentriert sind. Jedes Team erfasst Daten in Silos und analysiert und optimiert Erlebnisse basierend auf den Daten, auf die es Zugriff hat.

![Traditioneller BI-Workflow, wie in diesem Abschnitt beschrieben](./assets/biworkflow.png)

Wenn Sie verstehen möchten, wie eine bestimmte digitale Kampagne eine Offline-Aktion beeinflusst, die in einem anderen Datensilo gespeichert ist, senden Sie eine Anfrage an die Warteschlange des BI-Teams. Das BI-Team schreibt die erforderliche Abfrage, um die Daten zu gewinnen und zu transformieren. Nachdem die Rohdaten abgerufen wurden, erstellt das BI-Team die Visualisierung. Die Daten werden für Sie freigegeben, und Sie nutzen Ihre Zeit dafür, die Einblicke durchzukämmen und Daten für die Aktivierung in anderen Systemen zu extrahieren.

Jeder dieser Schritte kann Stunden, Tage oder sogar Wochen dauern. Wenn Folgefragen oder Probleme mit den abgefragten Daten auftreten, kann es noch mehr Zeit dauern, bis diese Fragen behandelt werden, und der Kreislauf geht weiter. Für die laufende Analyse, Untersuchung und Kenntnis der Customer Journey ist dieser Vorgang ineffizient und nicht skalierbar. Außerdem befassen sich BI-Teams normalerweise mit mehr als nur Customer-Journey-bezogenen Fragen.

## Customer Journey Analytics: Demokratisierter Workflow für Online- und Offline-Daten

Customer Journey Analytics bietet eine Umgebung, in der kanalübergreifende Online- und Offline-Daten auf übergeordneter Kundenebene allein dazu miteinander verbunden werden, um die Customer Journey zu verstehen. Es ist eine Ersteinrichtung erforderlich, um die Daten zu [verbinden](/help/connections/overview.md) und dafür [Ansichten zu definieren](/help/data-views/data-views.md), die Sie als relevant erachten. Nach Abschluss stehen diese Daten jedoch jederzeit für die laufende Analyse und Untersuchung zur Verfügung. Sie können schrittweise Einblicke in die Customer Journeys gewinnen und diese verstehen. Durch die Demokratisierung von kombinierten Online- und Offline-Daten können Sie Fragen in Beziehung auf eine Customer Journey in Sekundenschnelle beantworten.

![Customer Journey Analytics-Workflow, wie in diesem Abschnitt beschrieben](./assets/cjaworkflow.png)

Sie können Customer Journey Analytics verwenden, um Fragen mithilfe der visuellen Analysis Workspace-Umgebung zu stellen und praktisch unmittelbar Erkenntnisse zu erhalten. Kanalübergreifende Daten und Berichte sind sofort verfügbar, ohne dass ein SQL-Code erforderlich ist. Zusätzliche Abfragen und Analysen können durch einfaches Ziehen und Ablegen in der Benutzeroberfläche mit vollständig korrelierten Daten durchgeführt werden. Sie können weiterhin Fragen stellen und fortschreitend weitere nötige Details in Erfahrung bringen. Sie können dann sofort auf die Einblicke reagieren, die Sie entdecken, z. B. Zielgruppen für die Aktivierung und Orchestration freigeben.

## Die leistungsstarke Reporting-Engine von Customer Journey Analytics

Customer Journey Analytics verwendet eine eigene leistungsstarke Architektur, die die Analyse auf hunderte oder sogar tausende Server verteilt, um Daten in Analysis Workspace innerhalb von Sekunden anzuzeigen. Zu den bedeutenden Eigenschaften dieser Verarbeitungsarchitektur gehören unter anderem:

* **Optimiert für individuelle kundenbezogene Abfragen**: Technisch betrachtet speichert Customer Journey Analytics die Daten in einer verteilten Reporting-Engine, die umfassend das Caching nutzt. Diese Engine ist auf responsive Abfragen von Ereignisdaten auf individueller Ebene ausgerichtet und daher perfekt auf kundenbezogene Abfragen optimiert. Die Reporting-Engine speichert Daten in spaltenorientierten Bitmap-Indizes, die eine schnelle, spontane Berechnung der aggregierten Metriken ermöglichen. Sie verfügt über eine umfangreiche Segmentierungs-Engine, die eine leistungsstarke Segmentierung/Zielgruppenanalyse ermöglicht. Sie besitzt außerdem ein grundlegendes Verständnis der Sequenz zwischen Datenpunkten, das bei der Analyse des Verhaltens über diese Datenpunkte hinweg (in der Reihenfolge, in der Dinge aufgetreten sind) und für die Zuweisung der Attribution mithilfe verschiedener, komplexer Modelle nützlich ist.

* **Schnelle Anwendung komplexer Pfade und Segmente**: Die Reporting-Engine arbeitet mit teilweise sortierten, hierarchischen Datensätzen (z. B. Person -> Sitzungen -> Ereignisse). Alle Daten für ein Objekt der obersten Ebene (einzelne Profile) befinden sich auf einem einzigen Verarbeitungsknoten, um präzise Ergebnisse zu erzielen. Diese Partitionierung ermöglicht die schnelle Anwendung komplexer Pfade und Segmente. Komplexe Vorgänge wie Sitzungserstellung, Attribution, zustandsorientierte Persistenz von Datenattributen und komplexe Datenbearbeitungsoptionen werden skaliert und mit kurzer Berichtszeit ausgeführt. In der BI-Welt erfordern diese Arten von Vorgängen normalerweise, dass für jeden Anwendungsfall neue OLAP-Cubes erstellt werden. Die Reporting-Engine von Customer Journey Analytics ermöglicht den ungehinderten Zugriff auf den gesamten Datensatz bei jeder Abfrage, was zu vollständig korrelierten Daten führt, ohne dass vorzeitiges Cubing erforderlich ist.

* **Effiziente Abfrage komplexer Datenströme**: Einer der größten Unterschiede der Reporting-Engine gegenüber herkömmlichen SQL- und NoSQL-Datenbanken besteht in der Fähigkeit, Vorhersagen auf Basis sequenzorientierter Beziehungen auf einer grundlegenden Ebene zu bestimmen. Diese grundlegenden Abfragevorgänge können sich auf den Datensatzstrom beziehen, der aus vielen verzahnten (und sogar verschachtelten) Sequenzen besteht. Sie führen eine Abfrage für all diese miteinander verknüpften Datenströme durch, mit der Effizienz eines einzigen, fortlaufenden Sequenzvorgangs.

* **Entwickelt für die schnelle Beantwortung großer Abfragen**: Die Reporting-Engine hat keinen so allgemeinen Zweck wie herkömmliche Big-Data-Systeme. Sie wurde dagegen speziell für die Beantwortung von Abfragen entwickelt, die Millionen oder sogar Milliarden von Datensätzen (Ereignisdaten/Erlebnisereignisse) umfassen, was im Allgemeinen in weniger als einer Sekunde geschieht. Im Gegensatz zu anderen Big-Data-Systemen erfolgt dies nicht durch die Nutzung von Datenstichproben oder durch Vorberechnung der Antworten auf alle Fragen, die Sie potenziell stellen könnten. Stattdessen können die Antworten schnell genug berechnet werden, um die interaktive Abfrage von Anwendungsfällen zu unterstützen. Dieses spezielle Design der Reporting-Engine von Customer Journey Analytics macht die Daten schnell zur laufenden Analyse und Untersuchung verfügbar, sodass Sie schrittweise Erkenntnisse und Einsichten zur Customer Journeys gewinnen können.

* **Funktioniert als Headless BI-Lösung**: Sie definieren Ihre Dimensionen, Metriken und Segmente an einem Ort, und dann kann jeder Customer Journey Analytics-Client (einschließlich unserer öffentlichen Customer Journey Analytics-API) auf diese Komponenten zugreifen. Dadurch werden komplexe Abfragen von Endbenutzenden abstrahiert und es wird sichergestellt, dass die Ergebnisse unabhängig vom verwendeten Berichts- oder Visualisierungs-Client identisch sind.

## Einzigartige Visualisierungsfunktionen von Customer Journey Analytics

Die Reporting-Engine ist von grundlegender Bedeutung für Customer Journey Analytics, denn sie erlaubt es Ihnen, schrittweise mit allen Customer-Journey-Daten innerhalb dieser Reporting-Engine zu interagieren und darauf zu reagieren. Customer Journey Analytics verfügt über einen umfangreichen Satz an Komponenten, mit denen Sie dies visuell und per Drag-and-Drop erreichen können. Mit BI-Visualisierungs-Tools können Sie innerhalb der Grenzen von in SQL vorbereiteten Daten (wie durch die IT definiert) Erkundungen anstellen. Mit Customer Journey Analytics können Sie Daten in beliebig viele Teile zerlegen, ohne zur IT zurückkehren zu müssen, um eine weitere SQL-Ansicht erstellen zu lassen.

„Schrittweise“ ist hier ein Schlüsselkonzept: Im Gegensatz zu den meisten Visualisierungen in BI-Tools können Sie mit der visuellen Drag-and-Drop-Benutzeroberfläche in Customer Journey Analytics Ihre Daten kontinuierlich für Ihre spezifischen Anforderungen aufteilen: Sie können interaktiv visuelle Abfragen mit relevanten Metriken, Dimensionen, Filtern (Segmenten), Berechnungen, Timelines, Anmerkungen und anderen Analysewerten erstellen.

In diese Visualisierungskomponenten integriert sind intelligente Funktionen wie:

* **Virtual Analyst-Funktionen** wie [Anomalieerkennung](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md), die prädiktive Algorithmen und maschinelles Lernen nutzen, um Einblicke in ungewöhnliche Verhaltensweisen in Ihren Daten zu liefern.

* **Erweiterte Analysefunktionen**, die sich speziell auf Erkenntnisse zur Customer Journey konzentrieren, wie [Flussdiagramme](/help/analysis-workspace/visualizations/c-flow/flow.md), [Attributionsbedienfeld](/help/analysis-workspace/c-panels/attribution.md), [Fallout-Diagramme](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) und [Dimensionsaufschlüsselungen](/help/components/dimensions/t-breakdown-fa.md). Beispiele für sofort einsatzbereite Visualisierungen sind:

   * [Kundenbindungsanalyse über Kohorten-/Latenztabellen](/help/analysis-workspace/visualizations/cohort-table/cohort-use-cases.md), bei der Sie Metriken/Dimensionen einfach per Drag-und-Drop in einen Builder ziehen und in weniger als 30 Sekunden fertig sind,

   * [Fallout](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md)/[Fluss](/help/analysis-workspace/visualizations/c-flow/create-flow.md)-Visualisierungen. Einrichtung in weniger als einer Minute.

* **Segmentierungsfunktion in jedem Schritt Ihrer progressiven Exploration**: wann immer Sie dies für sinnvoll halten, können Sie Ihre Zielgruppe wieder in Experience Platform veröffentlichen und von dort an einem der unterstützten Ziele veröffentlichen.

* **Sessionization**, die vollständig [anpassbar](/help/data-views/component-settings/persistence.md) ist: Sie bestimmen, wann eine Sitzung als Teil eines Kanals in einer Customer Journey beginnt und endet.

* **Kuratierung und Demokratisierung**: Mit den in Customer Journey Analytics erstellten Dashboards ist Folgendes möglich:

   * Für andere Personen in der Organisation zur fortlaufenden Untersuchung [kuratiert](/help/analysis-workspace/curate-share/curate.md),
   * mit [Report Builder](/help/report-builder/report-buider-overview.md) (einem speziellen Plug-in) nach Excel exportiert,
   * in verschiedenen Formaten, einschließlich [PDF](/help/analysis-workspace/export/download-send.md), [CSV](/help/analysis-workspace/export/download-send.md) und über eine [dedizierte Mobile App](/help/mobile-app/home.md), an diejenigen [freigegeben](/help/analysis-workspace/curate-share/share-projects.md), die an den endgültigen Berichten und/oder Visualisierungen interessiert sind.

Ein Vergleich der Visualisierungsfunktionen von Customer Journey Analytics mit den Möglichkeiten von BI-Tools ist aufgrund der Vielfalt der verfügbaren Visualisierungen schwierig. Einige BI-Tools verfügen über fortschrittlichere Visualisierungen, aber Customer Journey Analytics konzentriert sich auf interaktive und interoperable Visualisierungen von Customer Journeys, die es Ihnen ermöglichen, die Daten innerhalb von Sekunden aufzuschlüsseln, ohne dass Sie für jede zusätzliche Abfrage „bezahlen“ müssen.


## Zusammenfassung

Customer Journey Analytics unterscheidet sich von BI-Tools durch die nahtlose Integration einer hochgradig optimierten, auf die Customer Journey ausgerichteten Reporting-Engine mit benutzerfreundlichen Tools und Komponenten, um Analysen durchzuführen und Berichte sowie erweiterte Visualisierungen zu erstellen. Und das alles von einer einzigen Benutzeroberfläche aus, ohne dass Sie zwischen Abfrage-Engine und Visualisierungsumgebung hin und her wechseln müssen.
