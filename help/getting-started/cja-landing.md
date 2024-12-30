---
title: Handbuch zu Customer Journey Analytics
description: Landingpage von Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: 8b90f74d64ef35f4a9f0f1177dab27c9680ccb4c
workflow-type: tm+mt
source-wordcount: '824'
ht-degree: 100%

---

# Handbuch zu Customer Journey Analytics

Diese technische Dokumentation bietet Hilfe zur Selbsthilfe für Customer Journey Analytics. Mit Customer Journey Analytics können Sie Ihre Kundendaten von beliebigen Kanälen (sowohl online als auch offline) in Adobe Experience Platform importieren. Anschließend haben Sie die Möglichkeit, diese Daten so zu analysieren wie heute Ihre vorhandenen digitalen Daten mit Analysis Workspace.

Mit Customer Journey Analytics können Sie steuern, wie Sie Ihre Online- und Offline-Daten in Analysis Workspace mit jeder beliebigen Kunden-ID verbinden. Dadurch können Sie Aufgaben wie Attribution, Filterung, Fluss- und Fallout-Analysen usw. durchführen, und das kundendatenübergreifend.

## Neue Funktionen

Werfen Sie einen Blick auf die neuesten Verbesserungen in Customer Journey Analytics und die Dokumentation! Eine umfassende Liste der Funktionen, Verbesserungen und Fehlerbehebungen finden Sie in den detaillierten [Versionshinweisen](../release-notes/latest.md). Besuchen Sie die [Seite zu den Dokumentationsaktualisierungen](../release-notes/doc-changes.md), um über die neuesten Änderungen auf dem Laufenden zu bleiben.

>[!BEGINTABS]

>[!TAB KI-Assistent]

Der KI-Assistent ist eine Dialogerfahrung, die es Fachleuten ermöglicht, Aufgaben schnell auszuführen – unabhängig davon, ob sie Konzepte verstehen, Probleme beheben oder nach Informationen suchen wollen. Er ermöglicht es auch Nichtexpertinnen und -experten, Expertenaufgaben durchzuführen, und erhöht die allgemeine Qualität der Arbeit.

[![Bild](assets/learn-more-button.svg)](/help/ai-assistant.md)


>[!TAB Geführte Analyse]

Die geführte Analyse ist jetzt direkt in Analysis Workspace verfügbar, sodass Benutzende Dashboards mit umfassenden Einblicken aus Bedienfeldern, Visualisierungen und geführten Analysen erstellen können.

[![Bild](assets/learn-more-button.svg)](/help/guided-analysis/overview.md)

>[!TAB Warnhinweise]

Warnhinweise ermöglichen es Ihnen, sich über geänderte Prozentsätze oder bestimmte Datenpunkte benachrichtigen zu lassen. Beispielsweise können Sie eine Vorschau anzeigen, wie oft ein Warnhinweis ausgelöst wird, Warnhinweise per E-Mail oder SMS versenden oder gestapelte Warnhinweise erstellen.

[![Bild](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)

>[!TAB Zusammenfassungsdaten]

Ermöglicht das Einbinden von Zeitreihendaten, die über keine Personen-ID verfügen. Diese Zeitreihendaten können zur Unterstützung verschiedener Anwendungsfälle verwendet werden, z. B.

- Darstellung von Leistungsindikatoren auf hoher Ebene als Teil von oder neben den Daten auf Ereignisebene.
- Hochladen von Zielen oder Zielvorgaben auf stündlicher oder täglicher Basis und anschließendes Positionieren dieser Ziele oder Zielvorgaben anhand von Metriken auf Ereignisebene.

[![Bild](assets/learn-more-button.svg)](/help/data-views/summary-data.md)

>[!TAB Grafikbasierte Zuordnung*]

Durch die grafikbasierte Zuordnung können Sie das Identitätsdiagramm des Identity Service von Experience Platform verwenden, um eine bessere Ansicht der Customer Journey zu erhalten, indem Sie: <ul><li>Datensätze mit verschiedenen Kennungen verknüpfen, ohne zusätzliche Daten extrahieren, transformieren und laden zu müssen, um eine einzelne Kennung widerzuspiegeln.</li> <li>Die Abdeckung der bevorzugten oder goldenen Identität für einen einzelnen Datensatz durch die gemeinsame Nutzung von Identitäten über Datensätze hinweg verbessern.</li><li>Die in Real-time Customer Data Platform und Journey Optimizer erstellten Profile mit Personen in Customer Journey Analytics abstimmen.</li></ul>

[![Bild](assets/learn-more-button.svg)](/help/stitching/overview.md#graph-based-stitching)

*_Für grafikbasierte Zuordnung ist das Prime-Paket erforderlich._*

>[!TAB B2B-Suchen]

Im Rahmen der Konfiguration einer Verbindung können Sie Datensätze für bestimmte B2B-Suchschemata transformieren, um personenbasierte Suchen nach B2B-Daten besser zu unterstützen.

[![Bild](assets/learn-more-button.svg)](/help/connections/transform-datasets-b2b-lookups.md)

>[!TAB Abgeleitete Felder]

Neue abgeleitete Feldfunktionen (mathematische Funktionen, Weiter oder Zurück, Zusammenfassen, Deduplizieren) und zusätzliche Funktionsvorlagen (wie Bounces, benutzerfreundlicher Datensatzname, Weihnachtszeit, monatliche Ziele, einfache Bot-Erkennung und andere) sind jetzt verfügbar.

[![Bild](assets/learn-more-button.svg)](/help/data-views/derived-fields/derived-fields.md)

>[!TAB BI-Erweiterung*]

Die BI-Erweiterung ermöglicht SQL-Zugriff auf Datenansichten, die Sie in Customer Journey Analytics definiert haben. Sie können jetzt Ihr bevorzugtes BI-Tool verwenden, um Berichte und Dashboards auf Basis derselben Datenansichten zu erstellen, die Customer Journey Analytics-Benutzende für ihre Analysis Workspace-Projekte verwenden. [Anwendungsfälle](/help/use-cases/data-views/bi-extension-usecases.md) werden bereitgestellt.

[![Bild](assets/learn-more-button.svg)](/help/data-views/bi-extension.md)

*_Sie müssen mindestens über das Select-Paket verfügen, um die BI-Erweiterung verwenden zu können._*


>[!ENDTABS]

## Beginnen Sie mit den Grundlagen

Lesen Sie zunächst das Material in den unten stehenden Links, um sich mit den Funktionen und Möglichkeiten von Customer Journey Analytics vertraut zu machen.

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
    <a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/aa-vs-cja.png"></a>
    <div><strong>Über Online-Daten hinaus</strong><br/>Erfahren Sie, wie sich Customer Journey Analytics von Adobe Analytics unterscheidet, welche Funktionen freigegeben werden und wie Sie Ihre Analytics-Daten verwenden können.</div>
    </td>
    <td>
    <a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/data-ingestion.png"></a>
    <div><strong>Datenaufnahme und -verwendung</strong><br/>Erfahren Sie mehr über die verfügbaren Optionen zur Datenaufnahme in Experience Platform und zur Verwendung dieser Daten für Analysen und Berichte in Customer Journey Analytics.</div>
    </td>
    <td>
    <a href="/help/guided-analysis/overview.md"><img src="./assets/product-analytics.png"></a>
    <div><strong>Geführte Analyse</strong><br/>Erfahren Sie, wie Sie mit Workflows Daten und Erkenntnisse über das Produkterlebnis von Kundschaft gewinnen können. Produkt Analytics über geführte Analyse …
    </div>
    </td>
    <td>
    <a href="/help/analysis-workspace/home.md"><img src="./assets/workspace.png"></a>
    <div><strong>Analysis Workspace</strong><br/>Nutzen Sie Analysis Workspace, um grundlegende und erweiterte Analysen, wie Attribution, Fluss- und Fallout-Diagramme oder Dimensionsaufschlüsselungen durchzuführen.</div>
    </td>
  </tr>
  <tr style="border: 0;">
    <td align="center"><a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/guided-analysis/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/analysis-workspace/home.md"><img src="./assets/learn-more-button.svg"></a></td>
    </tr>
</table>


## Dokumentation

Lernen Sie die Unterschiede zwischen Customer Journey Analytics und Adobe Analytics kennen. Erfahren Sie außerdem, wie Sie Ihre Daten in die Lösung aufnehmen und dann vorbereiten, anzeigen, analysieren und demokratisieren können, um daraus Analysen und Berichte zu erstellen.

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
      <img src="./assets/analytics.svg" width="35px"><br/>
      <strong>Vergleich mit Adobe Analytics</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">Übersicht</a> - <a href="/help/getting-started/aa-to-cja.md">Entwicklung</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">Verwenden von Adobe Analytics-Daten</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">Funktionsunterstützung</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">Terminologie</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">Datenverarbeitung</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
      <strong>Verbindungen</strong><br/><a href="/help/connections/overview.md">Übersicht</a> - <a href="/help/connections/create-connection.md">Erstellen</a> - <a href="/help/connections/manage-connections.md">Verwalten</a> - <a href="/help/stitching/overview.md">Zuordnung</a> - <a href="/help/connections/combined-dataset.md">Kombinierte Ereignis-Datensätze</a> - <a href="/help/connections/standard-lookups.md">Standardsuche</a>
    </td>
     <td>
      <img src="./assets/dataviews.svg" width="35px"><br/>
      <strong>Datenansichten</strong><br/><a href="/help/data-views/data-views.md">Übersicht</a> – <a href="/help/data-views/create-dataview.md">Erstellen oder bearbeiten</a> – <a href="/help/data-views/session-settings.md">Sitzungseinstellungen</a> – <a href="/help/data-views/derived-fields/derived-fields.md">Abgeleitete Felder</a> – <a href="/help/data-views/summary-data.md">Zusammenfassungsdaten</a> – <a href="/help/data-views/component-reference.md">Komponentenverweis</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>Workspace-Projekt</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> – <a href="/help/analysis-workspace/perform-basic-analysis.md">Allgemeine</a> und <a href="/help/analysis-workspace/perform-adv-analysis.md">erweiterte Analyse</a> – <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">Projekte</a> – <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">Visualisierungen</a> – <a href="/help/analysis-workspace/c-panels/freeform-panel.md">Bedienfelder</a>
    </td>
    <td>
      <img src="./assets/guided-analysis.svg" width="35px"><br/>
      <strong>Geführte Analyse</strong><br/><a href="/help/guided-analysis/overview.md">Übersicht</a> – <a href="/help/guided-analysis/types/active-growth.md">Benutzerwachstum</a> – <a href="/help/guided-analysis/types/trends.md">Trends</a> – <a href="/help/guided-analysis/types/funnel.md">Trichter</a> – <a href="/help/guided-analysis/types/release-impact.md">Auswirkung</a> – <a href="/help/guided-analysis/industry-use-cases.md">Branchenanwendungsfälle</a>
    </td>
    <td>
      <img src="./assets/share.svg" width="35px"><br/>
      <strong>Freigabe, Export, Integration</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">Projekte</a> – <a href="/help/mobile-app/home.md">Analytics-Dashboards</a> – <a href="/help/report-builder/report-buider-overview.md">Report Builder</a> – <a href="/help/components/exports/manage-exports.md">Cloud-Export</a> – <a href="/help/integrations/overview.md">Integrationen</a>
    </td>
  </tr>
</table>

## Zusätzliche Ressourcen

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/de/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">Tutorials</a> – <a href="https://helpx.adobe.com/de/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Customer Journey Analytics – Produktbeschreibung</a> – <a href="https://helpx.adobe.com/de/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Adobe Analytics (Customer Journey Analytics-Add-on) – Produktbeschreibung</a> – <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">Customer Journey Analytics-APIs</a> – <a href="/help/ai-assistant.md">KI-Assistent</a>
</td>
<td><strong>Datenaufnahme</strong><br/><a href="/help/data-ingestion/data-ingestion.md">Übersicht</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">Web-SDK</a> - <a href="/help/data-ingestion/aepmobilesdk.md">Mobile SDK</a> - <a href="/help/data-ingestion/batch.md">Batch</a> - <a href="/help/data-ingestion/streaming.md">Streaming</a> - <a href="/help/data-ingestion/sources.md">Quellen</a> - <a href="/help/data-ingestion/serverapi.md">Server-API</a>
</td>
</tr>
</table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>Bleiben Sie auf dem Laufenden, tragen Sie zur Community bei und verbessern Sie Ihr Erlebnis mit Customer Journey Analytics!</b><br>Besuchen Sie die Adobe Analytics-Community, um die Funktionalität mit anderen Benutzenden zu erörtern. <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?lang=de">Werden Sie noch heute Teil der Community!</a></td></tr></tbody></table>
