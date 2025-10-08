---
git-repo: https://github.com/AdobeDocs/analytics-platform.de-DE
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Handbuch zu Customer Journey Analytics
user-guide-description: Hier erhalten Sie Informationen zu Adobe Customer Journey Analytics und Erläuterungen zur Nutzung von Analysis Workspace mit Daten aus Experience Platform.
breadcrumb-title: Handbuch zu Customer Journey Analytics
source-git-commit: 6b4cb13dcea9830573b517c1d1121095ac27983f
workflow-type: tm+mt
source-wordcount: '1297'
ht-degree: 99%

---

# Handbuch zu Adobe Customer Journey Analytics {#using}

+ [Handbuch zu Adobe Customer Journey Analytics](../getting-started/cja-landing.md)

+ Versionshinweise  {#releases}
   + [Neueste Version](../release-notes/latest.md)
   + [Vorab veröffentlichte Versionshinweise](../release-notes/pre-release-notes.md)
   + [Versionen 2025](../release-notes/2025.md)
   + [Versionen 2024](../release-notes/2024.md)
   + [Versionen 2023](../release-notes/2023.md)
   + [Versionen 2022](../release-notes/2022.md)
   + [Versionen von 2021](../release-notes/2021.md)
   + [Versionen von 2020](../release-notes/2020.md)
   + [Strategie zur Veröffentlichung von Funktionen](../release-notes/releases.md)
   + [Aktualisierungen der Dokumentation](../release-notes/doc-changes.md)

+ Erste Schritte {#cja-overview}
   + Customer Journey Analytics {#cja-b2c-overview}
      + [Überblick](../getting-started/cja-overview.md)
      + [Schnellstartanleitung](../getting-started/cja-getting-started.md)
      + [Landingpage](../getting-started/landing.md)
      + [Häufig gestellte Fragen](../getting-started/cja-faq.md)
      + [Vergleichen mit BI-Lösungen](../getting-started/cja-vs-bi.md)
      + [KI-Assistent](../ai-assistant.md)
      + [Data Insights Agent](../data-analysis-ai.md)
   + Customer Journey Analytics B2B Edition {#cja-b2b}
      + [Überblick](/help/getting-started/cja-b2b-edition.md)
      + [B2B-Konzepte und -Funktionen](/help/getting-started/cja-b2b-concepts-features.md)
      + [Schnellstartanleitung](/help/getting-started/cja-b2b-quick-start-guide.md)
      + [Übergangshandbuch](/help/getting-started/cja-b2b-transition.md)

+ Aktualisieren und Vergleichen {#compare-aa-cja}
   + Upgrade auf Customer Journey Analytics {#upgrade-to-cja}
      + [Erste Schritte](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)
      + [Auswählen des Aktualisierungspfads](/help/getting-started/cja-upgrade/cja-upgrade-path.md)
      + [Senden von Daten an Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)
      + [Beibehalten historischer Daten](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)
      + [Empfohlener Upgrade-Prozess](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)
      + Planen und Erstellen eines Schemas {#schema}
         + [Planen Ihres Schemas](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)
         + [Erstellen Ihres Schemas](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)
         + [Verwenden Ihres vorhandenen Schemas](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)
      + Erstellen eines Datenstroms {#create-datastream}
         + [Erstellen eines Datenstroms](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)
         + [Hinzufügen von Platform as a Service](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md)
      + Erstellen von Datensätzen {#create-datasets}
         + [Erstellen eines Datensatzes](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md)
         + [Erstellen von Lookup-Datensätzen für Klassifizierungen](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)
         + [Überwachen der Datenaufnahme](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md)
      + Implementieren des Web SDK mit Tags {#create-tags}
         + [Erstellen eines Tags für die Eigenschaft](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)
         + [Hinzufügen der Web SDK-Erweiterung zum Tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)
         + [Implementieren des Loader-Tags für die Web-SDK-Erweiterung](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md)
         + [Hinzufügen von XDM-Datenerfassungslogik zum Tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md)
      + [Manuelles Implementieren des Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-manual.md)
      + [Implementieren des Web SDK mit dem API](/help/getting-started/cja-upgrade/cja-upgrade-api.md)
      + [Erstellen einer Verbindung](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)
      + [Erstellen einer Datenansicht](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)
      + [Erstellen eines abgeleiteten Marketing-Kanal-Felds](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)
      + [Validieren des Datenflusses](/help/getting-started/cja-upgrade/cja-upgrade-validate.md)
      + [Einrichten einer Streaming-Mediensammlung](/help/getting-started/cja-upgrade/cja-upgrade-streaming-media.md)
      + Beibehalten historischer Daten mit dem Analytics-Quell-Connector {#historical-data-source-connector}
         + [Erstellen eines XDM-Schemas für den Analytics-Quell-Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)
         + [Erstellen des Analytics-Quell-Connectors und Zuordnen von Feldern](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)
         + [Hinzufügen des Analytics-Quell-Connector-Datensatzes zur Verbindung](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)
      + [Bestimmen des Deaktivierungszeitpunkts für Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md)
      + [Deaktivieren von Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md)
      + Alternative Upgrade-Methoden {#alternative-upgrade-methods}
         + [Verwenden der AppMeasurement-Datenerfassung](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)
         + [Senden der Datenschicht](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)
         + [Analytics-Quell-Connector](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)
      + Andere Upgrade-Szenarien {#other-upgrade-scenarios}
         + [Wechsel vom Analytics-Quell-Connector zum Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)
         + [Upgrade von einer anderen Lösung als Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-third-party-solution.md)
      + Zusätzliche Informationen {#additional-information}
         + [Informationen zur Analytics-Implementierung](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md)
         + [Unterstützung von Adobe Analytics-Funktionen beim Upgrade](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)
         + [Customer Journey Analytics-Funktionen](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md)
         + [Web SDK-Implementierungsoptionen](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md)
         + [Konfigurieren des Adobe Analytics Web SDK für Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)
         + [Verwenden der Personalisierung mit Adobe Journey Optimizer](/help/getting-started/cja-upgrade/cja-upgrade-personalization-journeyoptimizer.md)
   + Vergleichen mit Adobe Analytics {#cja-aa-comparison}
      + [Überblick](../getting-started/aa-vs-cja/overview.md)
      + [Verwenden von Adobe Analytics-Daten](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Funktionsunterstützung](../getting-started/aa-vs-cja/cja-aa.md)
      + [Vergleichen der Terminologie](../getting-started/aa-vs-cja/terminology.md)
      + [Vergleichen der Datenverarbeitung](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [Umgebungen](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Analysenverarbeitung und Datenvorbereitung](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [Analytics-IDs](../getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [Weiterentwicklung von Adobe Analytics](../getting-started/aa-to-cja.md)
   + [Benutzerhandbuch für Adobe Analytics-Benutzende](../getting-started/aa-to-cja-user.md)

+ Datenaufnahme {#cja-data-ingestion}
   + [Überblick](../data-ingestion/data-ingestion.md)
   + Schnellstartanleitungen zur Aufnahme und Verwendung von Daten{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + Experience Platform Edge Network {#edge-network}
         + [Web SDK](../data-ingestion/aepwebsdk.md)
         + [Mobile SDK](../data-ingestion/aepmobilesdk.md)
         + [Server-API](../data-ingestion/serverapi.md)
      + [Batch-Daten](../data-ingestion/batch.md)
      + [Streaming-Daten](../data-ingestion/streaming.md)
      + [Quell-Connectoren](../data-ingestion/sources.md)
      + [Ad-hoc-Daten](/help/data-ingestion/adhoc.md)

+ Datenspiegelung {#cja-data-mirror}
   + [Überblick](/help/data-mirror/data-mirror.md)
   + Konfigurieren {#configure}
      + [Native Data-Warehouse-Lösungen](/help/data-mirror/datawarehouse.md)
      + [Experience Platform](/help/data-mirror/aep.md)
      + [Customer Journey Analytics](/help/data-mirror/cja.md)
   + [Datenspiegelung – Schnellstartanleitung](/help/data-mirror/model-based.md)

+ Verbindungen {#cja-connections}
   + [Verbindungen – Übersicht](../connections/overview.md)
   + [Erstellen oder Bearbeiten einer Verbindung](../connections/create-connection.md)
   + [Verwalten von Verbindungen](../connections/manage-connections.md)
   + [Kombinierte Ereignis-Datensätze](../connections/combined-dataset.md)
   + [Standardsuchen](../connections/standard-lookups.md)
   + [B2B-Suchen](../connections/transform-datasets-b2b-lookups.md)

+ Datenansichten {#cja-dataviews}
   + [Überblick über Datenansichten](../data-views/data-views.md)
   + [Erstellen oder Bearbeiten einer Datenansicht](../data-views/create-dataview.md)
   + [Sitzungseinstellungen](../data-views/session-settings.md)
   + Komponenteneinstellungen {#component-settings}
      + [Übersicht über Komponenteneinstellungen](../data-views/component-settings/overview.md)
      + [Attribution](../data-views/component-settings/attribution.md)
      + [Verhalten](../data-views/component-settings/behavior.md)
      + [Format](../data-views/component-settings/format.md)
      + [Werte einschließen/ausschließen](../data-views/component-settings/include-exclude-values.md)
      + [Deduplizierung einer Metrik](../data-views/component-settings/metric-deduplication.md)
      + [Keine Wertoptionen](../data-views/component-settings/no-value-options.md)
      + [Persistenz](../data-views/component-settings/persistence.md)
      + [Teilzeichenfolge](../data-views/component-settings/substring.md)
      + [Zusammenfassungsdatengruppe](../data-views/component-settings/summary-data-group.md)
      + [Bucketing von Werten](../data-views/component-settings/value-bucketing.md)
   + [Standardkomponentenreferenz](../data-views/component-reference.md)
   + [BI-Erweiterung](../data-views/bi-extension.md)
   + [Abgeleitete Felder](../data-views/derived-fields/derived-fields.md)
   + [Zusammenfassungsdaten](../data-views/summary-data.md)
   + [Labels und Richtlinien](../data-views/data-governance.md)
   + Freigegebene Metriken und Dimensionen{#shared-metrics-dimensions}
      + [Überblick](/help/data-views/shared-metrics-dimensions/smd-overview.md)
      + [Editor](/help/data-views/shared-metrics-dimensions/shared-component-editor.md)

+ Tools {#tools}
   + Asset-Übertragung {#asset-transfer}
      + [Übertragen von Assets](../tools/asset-transfer/transfer-assets.md)
   + Produktnutzung {#product-usage}
      + [Überblick](../tools/product-usage/usage-overview.md)
      + [Dateneinstellungen](../tools/product-usage/data-settings.md)
      + [Opt-out-Einstellungen](../tools/product-usage/opt-out-settings.md)

+ Workspace-Projekte {#cja-workspace}
   + [Überblick über Analysis Workspace](../analysis-workspace/home.md)
   + [Grundlegende Analyse durchführen](../analysis-workspace/perform-basic-analysis.md)
   + [Durchführen einer erweiterten Analyse](../analysis-workspace/perform-adv-analysis.md)
   + Projekte {#build-workspace-project}
      + [Überblick](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [Schneller Projektstart](/help/analysis-workspace/build-workspace-project/starter-projects.md)
      + [Erstellen von Projekten](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [Öffnen von Projekten](/help/analysis-workspace/build-workspace-project/open-projects.md)
      + [Kommentar zu Projekten](/help/analysis-workspace/build-workspace-project/comment-projects.md)
      + [Speichern von Projekten](../analysis-workspace/build-workspace-project/save-projects.md)
      + [Inhaltsverzeichnis](../analysis-workspace/build-workspace-project/project-table-of-contents.md)
      + Ordner in Workspace {#workspace-folders}
         + [Überblick](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [Erstellen von Ordnern](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [Verwalten von Ordnern](../analysis-workspace/build-workspace-project/workspace-folders/manage-folders.md)
         + [Hinzufügen oder Verschieben von Projekten](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
      + [Hotkeys](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [Farbpaletten](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [Anzeigen der Dichte](../analysis-workspace/build-workspace-project/view-density.md)
      + [Debugger](../analysis-workspace/build-workspace-project/debugger.md)
   + Vorlagen {#templates}
      + [Verwenden von Vorlagen](../analysis-workspace/templates/use-templates.md)
      + [Erstellen und Verwalten von Vorlagen](../analysis-workspace/templates/create-templates.md)
   + Visualisierungen {#visualizations}
      + [Überblick](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [Verwalten von Datenquellen](../analysis-workspace/visualizations/t-sync-visualization.md)
      + [Intelligente Beschriftungen](../analysis-workspace/visualizations/intelligent-captions.md)
      + Freiformtabelle {#freeform-table}
         + [Überblick](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + [Erstellen von Hyperlinks](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)
         + Spalten- und Zeileneinstellungen {#column-row-settings}
            + [Spalteneinstellungen](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [Zeileneinstellungen](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [Dynamische und statische Elemente](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [Filtern und Sortieren](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
         + [Gesamt](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + Kohortentabelle {#cohort-table}
         + [Überblick](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [Konfigurieren](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [Anwendungsfälle](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + Fallout {#fallout}
         + [Überblick](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [Konfigurieren](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [Interdimensionaler Fallout](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [Anwenden von Segmenten](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + Fluss {#flow}
         + [Überblick](../analysis-workspace/visualizations/c-flow/flow.md)
         + [Konfigurieren](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [Interdimensionale Flüsse](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + Journey-Arbeitsfläche {#journey-canvas}
         + [Überblick](../analysis-workspace/visualizations/journey-canvas/journey-canvas.md)
         + [Konfigurieren](../analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)
         + [Fehlerbehebung](../analysis-workspace/visualizations/journey-canvas/journey-canvas-troubleshooting.md)
      + [Bereich (gestapelt)](../analysis-workspace/visualizations/area.md)
      + [Balken (gestapelt)](../analysis-workspace/visualizations/bar.md)
      + [Bullet](../analysis-workspace/visualizations/bullet-graph.md)
      + [Kombination](../analysis-workspace/visualizations/combo-charts.md)
      + [Ringdiagramm](../analysis-workspace/visualizations/donut.md)
      + [Histogramm](../analysis-workspace/visualizations/histogram.md)
      + [Horizontalbalken (gestapelt)](../analysis-workspace/visualizations/horizontal-bar.md)
      + [Zusammenfassung einer Schlüsselmetrik](../analysis-workspace/visualizations/key-metric.md)
      + [Linie](../analysis-workspace/visualizations/line.md)
      + [Zuordnung](/help/analysis-workspace/visualizations/map.md)
      + [Streuung](../analysis-workspace/visualizations/scatterplot.md)
      + [Abschnittskopfzeile](/help/analysis-workspace/visualizations/section-header.md)
      + [Zusammenfassungszahl und -änderung](../analysis-workspace/visualizations/summary-number-change.md)
      + [Text](../analysis-workspace/visualizations/text.md)
      + [Baumkarte](../analysis-workspace/visualizations/treemap.md)
      + [Venn](../analysis-workspace/visualizations/venn.md)
   + Bedienfelder {#panels}
      + [Überblick](../analysis-workspace/c-panels/panels.md)
      + [Leeres Panel](../analysis-workspace/c-panels/blank-panel.md)
      + [Attribution](../analysis-workspace/c-panels/attribution.md)
      + [Experimentieren](../analysis-workspace/c-panels/experimentation.md)
      + [Freiform](../analysis-workspace/c-panels/freeform-panel.md)
      + [Medien-Zielgruppendurchschnitt pro Minute](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)
      + [Gleichzeitige Medienbetrachtende](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + [Verbrachte Zeit bei der Medienwiedergabe](../analysis-workspace/c-panels/media-playback-time-spent.md)
      + [Nächstes oder vorheriges Objekt](../analysis-workspace/c-panels/next-previous.md)
      + [Quick Insights](../analysis-workspace/c-panels/quickinsight.md)
   + Kuratieren und Freigeben {#curate-share}
      + [Überblick](../analysis-workspace/curate-share/send-schedule-files.md)
      + [Kuratieren von Projekten](../analysis-workspace/curate-share/curate.md)
      + [Freigeben von Projekten](../analysis-workspace/curate-share/share-projects.md)
      + [Erstellen von freigebbaren Links](../analysis-workspace/curate-share/shareable-links.md)
      + [Schreibgeschützte Projekte](../analysis-workspace/curate-share/view-only-projects.md)
      + [Erstellen von Präsentationen](/help/analysis-workspace/curate-share/generate-presentations.md)
   + Exportieren {#export}
      + [Überblick](../analysis-workspace/export/export-project-overview.md)
      + [Herunterladen](../analysis-workspace/export/download-send.md)
      + [Senden und Planen](../analysis-workspace/export/t-schedule-report.md)
      + [Exportieren in die Cloud](../analysis-workspace/export/export-cloud.md)
   + Attribution {#attribution}
      + [Attribution – Überblick](../analysis-workspace/attribution/overview.md)
      + [Modell, Container und Lookback-Fenster](../analysis-workspace/attribution/models.md)
      + [Algorithmische Attribution](../analysis-workspace/attribution/algorithmic.md)
      + [Best Practices](../analysis-workspace/attribution/best-practices.md)
      + [Häufig gestellte Fragen](../analysis-workspace/attribution/faq.md)
   + Anomalieerkennung {#anomaly-detection}
      + [Überblick](../analysis-workspace/c-anomaly-detection/anomaly-detection.md)
      + [Anzeigen von Anomalien](../analysis-workspace/c-anomaly-detection/view-anomalies.md)
      + [Statistische Verfahren](../analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)
   + Prognose {#forecasting}
      + [Überblick](../analysis-workspace/c-forecast/forecasting.md)
      + [Anzeigen von Prognosen](../analysis-workspace/c-forecast/view-forecasts.md)
      + [Statistische Verfahren](../analysis-workspace/c-forecast/statistics-forecasting.md)
   + [Benutzervoreinstellungen](../analysis-workspace/user-preferences.md)
   + Häufig gestellte Fragen zu Workspace und mehr {#workspace-faq}
      + [Häufig gestellte Fragen](../analysis-workspace/workspace-faq/faq.md)
      + [Optimieren der Leistung](../analysis-workspace/workspace-faq/optimizing-performance.md)
      + [Fehler und Fehlerbehebung](../analysis-workspace/workspace-faq/error-messages.md)
      + [Einschränkungen](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [Voraussetzungen](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Barrierefreiheit](../analysis-workspace/workspace-faq/aw-accessibility.md)

+ Content Analytics {#content-analytics}
   + [Überblick](/help/content-analytics/content-analytics.md)
   + Bericht {#report}
      + [Überblick](/help/content-analytics/report/report.md)
      + [Komponenten](/help/content-analytics/report/components.md)
   + Konfiguration {#configuration}
      + [Überblick](/help/content-analytics/config/configuration.md)
      + [Geführte Konfiguration](/help/content-analytics/config/guided.md)
      + [Manuelle Konfiguration](/help/content-analytics/config/manual.md)
      + [Datenerfassung](/help/content-analytics/config/datacollection.md)

+ Analytics-Dashboards {#cja-dashboards}
   + [Überblick](../mobile-app/home.md)
   + [Kuratoraufgaben](../mobile-app/curator.md)
   + [Erstellen mobiler Scorecards](../mobile-app/create-scorecard.md)
   + [Verwalten mobiler Scorecards](../mobile-app/manage-scorecard.md)
   + [Einrichten von Führungskräften für die Verwendung von Dashboards](../mobile-app/set-up-execs.md)
   + [Schnellstarthandbuch für ausführende Benutzer](../mobile-app/executive.md)

+ Geführte Analyse {#guided-analysis}
   + [Überblick](../guided-analysis/overview.md)
   + [Aktives Wachstum](../guided-analysis/types/active-growth.md)
   + [Konversions-Trends](../guided-analysis/types/conversion-trends.md)
   + [Interaktion](../guided-analysis/types/engagement.md)
   + [Wirkung der ersten Verwendung](../guided-analysis/types/first-use-impact.md)
   + [Häufigkeit](../guided-analysis/types/frequency.md)
   + [Trichter](../guided-analysis/types/funnel.md)
   + [Nettowachstum](../guided-analysis/types/net-growth.md)
   + [Auswirkungen der Version](../guided-analysis/types/release-impact.md)
   + [Kundentreue](../guided-analysis/types/retention.md)
   + [Zeitleiste](../guided-analysis/types/timeline.md)
   + [Trends](../guided-analysis/types/trends.md)
   + [Anwendungsfälle für Branchen](../guided-analysis/industry-use-cases.md)
   + [Häufig gestellte Fragen](../guided-analysis/faq.md)

+ Komponenten {#cja-components}
   + [Überblick](../components/overview.md)
   + [Verwenden von Komponenten](../components/use-components-in-workspace.md)
   + [Hinzufügen von Komponentenbeschreibungen](../components/add-component-descriptions.md)
   + Anmerkungen {#annotations}
      + [Überblick](../components/annotations/overview.md)
      + [Erstellen von Anmerkungen](../components/annotations/create-annotations.md)
      + [Verwalten von Anmerkungen](../components/annotations/manage-annotations.md)
      + [Anzeigen von Anmerkungen](../components/annotations/view-annotations.md)
      + [Anmerkungen zu mobilen Scorecards](../components/annotations/mobile-annotations.md)
   + Zielgruppen {#audiences}
      + [Überblick über Zielgruppen](../components/audiences/audiences-overview.md)
      + [Erstellen und Veröffentlichen von Zielgruppen](../components/audiences/publish.md)
      + [Verwalten von Zielgruppen](../components/audiences/manage.md)
   + Dimensionen {#dimensions}
      + [Überblick](../components/dimensions/overview.md)
      + [Dimensionsvorschau](../components/dimensions/view-dimensions.md)
      + [Dimensionen aufschlüsseln](../components/dimensions/t-breakdown-fa.md)
      + [Dimensionen für die Zeitunterteilung](../components/dimensions/time-parting-dimensions.md)
      + [Dimensionen hoher Kardinalität](../components/dimensions/high-cardinality.md)
   + [Metriken](../components/apply-create-metrics.md)
   + Segmente {#segments}
      + [Überblick](/help/components/segments/seg-overview.md)
      + [Erstellen von Segmenten](/help/components/segments/seg-create.md)
      + [Aufbauen von Segmenten](/help/components/segments/seg-builder.md)
      + [Schnellsegmente](/help/components/segments/seg-quick.md)
      + [Sequenzielle Segmente](/help/components/segments/seg-sequential-build.md)
      + [Freigeben von Segmenten](/help/components/segments/seg-share.md)
      + [Taggen von Segmente](/help/components/segments/seg-tag.md)
      + [Filtern der Segmentliste](/help/components/segments/seg-filter.md)
      + [Markieren von Segmenten als Favoriten](/help/components/segments/seg-favorite.md)
      + [Genehmigen von Segmenten](/help/components/segments/seg-approve.md)
      + [Segmente kopieren](/help/components/segments/seg-copy.md)
      + [Verwalten von Segmenten](/help/components/segments/seg-manage.md)
      + [Operatoren](/help/components/segments/seg-operators.md)
      + [Segmente verwenden](/help/components/segments/seg-use.md)
   + Berechnete Metriken {#cja-calcmetrics}
      + [Überblick](../components/calc-metrics/calc-metr-overview.md)
      + Workflow {#cm-workflow}
         + [Erstellen von berechneten Metriken](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Suchen von Metriken](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [Erstellen berechneter Metriken](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Ein einfaches Beispiel](../components/calc-metrics/cm-workflow/cm-pvv.md)
         + [Ein komplexeres Beispiel](../components/calc-metrics/cm-workflow/cm-orders-participation.md)
         + [Metriktyp und Attribution](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Beitragsmetriken](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [Segmentierte Metriken](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Segmente stapeln und ersetzen](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Berechnete Metriken filtern](../components/calc-metrics/cm-workflow/cm-filter.md)
         + [Markieren berechneter Metriken als Favoriten](../components/calc-metrics/cm-workflow/cm-favorite.md)
         + [Kopieren von berechneten Metriken](../components/calc-metrics/cm-workflow/cm-copy.md)
         + [Funktionen verwenden](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Berechnete Metriken taggen](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Berechnete Metriken genehmigen](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [Berechnete Metriken freigeben](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Berechnete Metriken verwalten](../components/calc-metrics/cm-workflow/cm-manager.md)
         + [Beispiele](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
      + [Vorlagen für berechnete Metriken](../components/calc-metrics/default-calcmetrics.md)
      + [Grundlegende Funktionen](../components/calc-metrics/cm-functions.md)
      + [Erweiterte Funktionen](../components/calc-metrics/cm-adv-functions.md)
   + Datumsbereiche {#cja-date-ranges}
      + [Überblick](../components/date-ranges/overview.md)
      + [Erstellen von Datumsbereichen](../components/date-ranges/create.md)
      + [Verwalten von Datumsbereichen](../components/date-ranges/manage.md)
      + [Datumsvergleich](../components/date-ranges/time-comparison.md)
      + [Beispiele](../components/date-ranges/custom-date-ranges.md)
   + Warnhinweise {#alerts}
      + [Überblick](/help/components/c-intelligent-alerts/intelligent-alerts.md)
      + [Erstellen von Warnhinweisen](/help/components/c-intelligent-alerts/alert-builder.md)
      + [Verwalten von Warnhinweisen](/help/components/c-intelligent-alerts/alert-manager.md)
      + [Funktionsvergleich](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)
      + [Anwendungsszenarien](/help/components/c-intelligent-alerts/alerts-use-cases.md)
   + Exporte {#exports}
      + [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md)
      + [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md)
      + [Verwalten von Cloud-Exportspeicherorten](/help/components/exports/manage-export-locations.md)
      + [Verwalten von Exporten](/help/components/exports/manage-exports.md)
      + [Verwalten von Exportprotokollen](/help/components/exports/manage-export-logs.md)
      + [Fehlerbehebung bei Exporten](/help/components/exports/troubleshoot-exports.md)
   + Datenwörterbuch {#data-dictionary}
      + [Überblick](../components/data-dictionary/data-dictionary-overview.md)
      + [Komponenteninformationen im Datenwörterbuch anzeigen](../components/data-dictionary/view-data-dictionary.md)
      + [Bearbeiten von Komponenteneinträgen im Datenwörterbuch](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [Überwachen des Zustands des Datenwörterbuchs](../components/data-dictionary/monitor-data-dictionary-health.md)
   + Echtzeit-Reporting {#real-time-reporting}
      + [Überblick](/help/components/real-time/real-time.md)
      + [Verwenden von Echtzeit-Reporting](/help/components/real-time/use-real-time.md)
   + [Geplante Projekte](../components/scheduled-projects-manager.md)
+ Report Builder {#cja-reportbuilder}
   + [Überblick](../report-builder/rb-overview.md)
   + [Einrichten von Report Builder](../report-builder/report-builder-setup.md)
   + [Erstellen eines Datenblocks](../report-builder/create-a-data-block.md)
   + [Report Builder-Hub](../report-builder/report-builder-hub.md)
   + [Auswählen einer Datenansicht](../report-builder/select-data-view.md)
   + [Auswählen eines Datumsbereichs](../report-builder/select-date-range.md)
   + [Arbeiten mit Segmenten](../report-builder/work-with-filters.md)
   + [Filterdimensionen](../report-builder/filter-dimensions.md)
   + [Verwalten von Datenblöcken](../report-builder/manage-reportbuilder.md)
   + [Arbeitsmappen für E-Mails planen](../report-builder/schedule-reportbuilder.md)
   + [Arbeitsmappen für Cloud-Exporte planen](../report-builder/report-builder-export.md)
   + [Arbeitsmappen-Zeitpläne verwalten](/help/report-builder/manage-schedules-reportbuilder.md)
   + [Eingeschränkte Labels](../report-builder/restricted-labels.md)
   + [Report Builder-Einstellungen](../report-builder/report-builder-settings.md)


+ Reporting Activity Manager {#reporting-activity-manager}
   + [Überblick](../reporting-activity-manager/reporting-activity-overview.md)
   + [Anzeigen der Berichtsaktivität](../reporting-activity-manager/reporting-activity.md)
   + [Abbrechen von Berichtsanfragen](../reporting-activity-manager/reporting-activity-cancel-requests.md)

+ Zuordnung {#stitching}
   + [Überblick](/help/stitching/overview.md)
   + [Feldbasierte Zuordnung](/help/stitching/fbs.md)
   + [Diagrammbasierte Zuordnung](/help/stitching/gbs.md)
   + [Zuordnung verwenden](/help/stitching/use-stitching.md)
   + [Zuordnung verwenden](/help/stitching/use-stitching-ui.md)
   + [Erstellen und Verwalten zugeordneter Datensätze](/help/stitching/stitching-ui.md)
   + [Validieren der Zuordnung](/help/stitching/validate.md)
   + [Häufig gestellte Fragen](/help/stitching/faq.md)

+ Adobe-Integrationen {#integrations}
   + [Überblick](/help/integrations/overview.md)
   + [Integrieren von Adobe Analytics](/help/integrations/aa.md)
   + [Integrieren von Target](/help/integrations/at.md)
   + [Integrieren von Journey Optimizer-Daten](/help/integrations/ajo.md)
   + [Integrieren von Entscheidungs-Management-Daten](/help/integrations/ajo-od.md)
   + [Integrieren von Kunden-KI](/help/integrations/customer-ai.md)
   + [Integrieren von Adobe Advertising](/help/integrations/advertising.md)

+ Data Governance {#cja-privacy}
   + [Data Governance](../privacy/privacy-overview.md)
   + [Administratorprotokoll](../privacy/audit-log.md)
   + [Vom Kunden verwaltete Schlüssel](../privacy/cmk.md)

+ Anwendungsszenarien {#cja-usecases}
   + [Anwendungsszenarien für Customer Journey Analytics](../use-cases/cja-usecases.md)
   + Adobe Analytics-Daten {#aa-data}
      + [Verwenden von Marketing-Kanal-Dimensionen](../use-cases/aa-data/marketing-channels.md)
      + [Kombinieren von Report Suites mit verschiedenen Schemata](../use-cases/aa-data/combine-report-suites.md)
   + B2B {#b2b}
      + [Beispiel für ein personenbasiertes B2B-Projekt](../use-cases/b2b/example.md)
      + B2B Edition {#b2b-edition}
         + [Überblick über Anwendungsfälle](/help/use-cases/b2b/b2b-edition/use-cases-overview.md)
         + [Einrichten](/help/use-cases/b2b/b2b-edition/setup.md)
         + [Optimieren des Konto-Marketings](/help/use-cases/b2b/b2b-edition/optimize-account-marketing.md)
         + [Wachstum wichtiger Konten](/help/use-cases/b2b/b2b-edition/grow-key-accounts.md)
         + [Fördern von Produktwert](/help/use-cases/b2b/b2b-edition/build-product-value.md)
   + Komplexe Daten {#complex-data}
      + [Verwenden von Objekt-Arrays](../use-cases/object-arrays.md)
   + Kanalübergreifende Daten {#cross-channel}
      + [Kanalübergreifendes Analysieren von Daten](../use-cases/cross-channel/cross-channel.md)
      + [Importieren von Callcenter- und Web-Daten](../use-cases/cross-channel/call-center.md)
   + Datenexport {#data-export}
      + [Überblick](../use-cases/data-export/overview.md)
      + [BI-Erweiterung](../use-cases/data-export/bi-extension.md)
      + [Exportieren von Datensätzen](../use-cases/data-export/export-datasets.md)
      + [Exportieren einer vollständigen Tabelle](../use-cases/data-export/export-full-table.md)
      + [Abfrage-Service- und Export-Datensätze](../use-cases/data-export/queryservice-export-datasets.md)
   + Datenaufnahme {#data-ingestion}
      + [Aufnehmen und Verwenden von Marketo Engage-Daten](../use-cases/data-ingestion/marketo.md)
      + [Aufnehmen und Verwenden von Experience Platform-Zielgruppen](../use-cases/data-ingestion/ingest-aep-segments.md)
   + Datenansichten {#data-views}
      + [Anwendungsfälle von Datenansichten](/help/use-cases/data-views/data-views-usecases.md)
      + [Verwenden von Bindungsdimensionen und Metriken](/help/use-cases/data-views/binding-dimensions-metrics.md)
      + [Verwenden von Zusammenfassungsdaten](/help/use-cases/data-views/summary-data.md)
      + [Anwendungsfälle für BI-Erweiterungen](/help/use-cases/data-views/bi-extension-usecases.md)
   + Abgeleitete Felder {#derived-fields}
      + [Bericht über Ziele](../use-cases/goals-using-derived-fields.md)
   + Produktanalyse {#product-analysis}
      + [Produktanalyse](/help/use-cases/product-analysis.md)
   + Zuordnung {#stitching}
      + [Gemeinsam verwendete Geräte](/help/use-cases/stitching/shared-devices.md)
   + Drittanbieterdaten {#third-party}
      + [Überblick](/help/use-cases/third-party/overview.md)
      + Google Analytics {#ga}
         + [Migrieren von Daten aus Google Analytics](/help/use-cases/third-party/ga/overview.md)
         + [Aufnehmen von historischen Daten aus Google Analytics](/help/use-cases/third-party/ga/backfill.md)
         + [Konfigurieren des Streaming-Vorgangs von Google Analytics-Daten](/help/use-cases/third-party/ga/streaming.md)
         + [Bericht zu Google Analytics-Daten](/help/use-cases/third-party/ga/report.md)
      + Quantum Metric {#qm}
         + [Überblick](/help/use-cases/third-party/quantum-metric/qm-overview.md)
         + [Verbinden von Sitzungswiederholungen](/help/use-cases/third-party/quantum-metric/tie-session-replays.md)
         + [Verwenden von Heatmaps](/help/use-cases/third-party/quantum-metric/heatmap.md)
         + [Hinzufügen von Reibungsereignissen](/help/use-cases/third-party/quantum-metric/friction-events.md)
         + [Quell-Connector](/help/use-cases/third-party/quantum-metric/source-connector.md)

+ Labs {#labs}
   + [Labs-Benutzerhandbuch](../labs/labs.md)

+ Fehlerbehebung {#troubleshooting}
   + [Vergleichen von Source Connector-Daten](../troubleshooting/compare.md)
   + [Konsistenz von Metriken und Zielgruppen](../troubleshooting/consistency-rcdp-cja.md)
   + [Fehlen von Berechtigungen](../troubleshooting/lack-of-permissions.md)

+ Technische Hinweise {#technotes}
   + [Zugriffssteuerung](../technotes/access-control.md)
   + [Rechenzentren](../technotes/data-centers.md)
   + [Auswirkungen des Löschens](../technotes/deletion.md)
   + [Domains](../technotes/domains.md)
   + [Glossar](../technotes/glossary.md)
   + [Leitlinien](../technotes/guardrails.md)
   + [IP-Adressen](../technotes/ip-addresses.md)
   + [Optimieren der Leistung](../technotes/optimizing-performance.md)
   + [Verwalten der Nutzung](../technotes/estimate-usage.md)

+ [Customer Journey Analytics-API](https://developer.adobe.com/cja-apis/docs/)
