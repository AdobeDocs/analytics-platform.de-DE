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
source-git-commit: d556740383075b2ee4652a78d3d37d5bbc5f2225
workflow-type: tm+mt
source-wordcount: '1099'
ht-degree: 100%

---

# Handbuch zu Adobe Customer Journey Analytics {#using}

+ [Handbuch zu Adobe Customer Journey Analytics](../getting-started/cja-landing.md)
+ [KI-Assistent für Adobe Customer Journey Analytics](../ai-assistant.md)
+ [KI-Assistent für die Datenanalyse für Adobe Customer Journey Analytics](../data-analysis-ai.md)

+ Versionshinweise {#releases}
   + [Neueste Version](../release-notes/latest.md)
   + [Versionen 2024](../release-notes/2024.md)
   + [Versionen 2023](../release-notes/2023.md)
   + [Versionen 2022](../release-notes/2022.md)
   + [Versionen von 2021](../release-notes/2021.md)
   + [Versionen von 2020](../release-notes/2020.md)
   + [Strategie zur Veröffentlichung von Funktionen](../release-notes/releases.md)
   + [Aktualisierungen der Dokumentation](../release-notes/doc-changes.md)

+ Erste Schritte {#cja-overview}
   + [Überblick über Customer Journey Analytics](../getting-started/cja-overview.md)
   + [Schnellstartanleitung](../getting-started/cja-getting-started.md)
   + [Landingpage](../getting-started/landing.md)
   + [Landingpage (alt)](../getting-started/cja-landing-old.md)
   + [Häufig gestellte Fragen](../getting-started/cja-faq.md)
   + [Vergleichen von Customer Journey Analytics mit BI-Lösungen](../getting-started/cja-vs-bi.md)

+ Customer Journey Analytics und Adobe Analytics {#compare-aa-cja}
   + Aktualisierung auf Customer Journey Analytics {#upgrade-to-cja}
      + [Erste Schritte](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)
      + [Auswählen des Aktualisierungspfads](/help/getting-started/cja-upgrade/cja-upgrade-path.md)
      + [Senden von Daten an Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)
      + [Beibehalten historischer Daten](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)
      + [Empfohlener Prozess](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)
      + [Informationen zur Analytics-Implementierung](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md)
      + [Erstellen von Lookup-Datensätzen für Klassifizierungen](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)
      + [Überwachen der Datenaufnahme](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md)
      + [Erstellen eines abgeleiteten Marketing-Kanal-Felds](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)
      + [Implementieren des Loader-Tags für die Web SDK-Erweiterung](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md)
      + [Erstellen eines Tags für die Eigenschaft](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)
      + [Hinzufügen der Web SDK-Erweiterung zum Tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)
      + [Hinzufügen von XDM-Datenerfassungslogik zum Tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md)
      + [Planen Ihres Schemas](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)
      + [Erstellen Ihres Schemas](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)
      + [Verwenden Ihres vorhandenen Schemas](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)
      + [Erstellen eines Datensatzes](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md)
      + [Erstellen eines Datenspeichers](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)
      + [Hinzufügen von Platform as a Service](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md)
      + [Erstellen einer Verbindung](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)
      + [Erstellen einer Datenansicht](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)
      + [Validieren des Datenflusses](/help/getting-started/cja-upgrade/cja-upgrade-validate.md)
      + [Schnellerer Weg zum Upgrade: Migration zum Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-shortcut-websdk.md)
      + [Erstellen eines XDM-Schemas für den Analytics-Quell-Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)
      + [Erstellen der Analytics-Quell-Connector- und Zuordnungsfelder](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)
      + [Hinzufügen des Datensatzes des Analytics-Quell-Connectors zur Verbindung](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)
      + [Ausschließliche Verwendung des Analytics-Quell-Connectors](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)
      + [Wechsel vom Analytics-Quell-Connector zum Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)
      + [AppMeasurement-Datenerfassung deaktivieren](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md)
   + Vergleich mit Adobe Analytics {#cja-aa-comparison}
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
   + [Übersicht über die Datenaufnahme](../data-ingestion/data-ingestion.md)
   + Kurzanleitungen zur Aufnahme und Verwendung von Daten{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + Experience Platform Edge Network {#edge-network}
         + [Web SDK](../data-ingestion/aepwebsdk.md)
         + [Mobile SDK](../data-ingestion/aepmobilesdk.md)
         + [Server-API](../data-ingestion/serverapi.md)
      + [Batch-Daten](../data-ingestion/batch.md)
      + [Streaming-Daten](../data-ingestion/streaming.md)
      + [Quell-Connectoren](../data-ingestion/sources.md)

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

+ Tools {#tools}
   + Asset-Übertragung {#asset-transfer}
      + [Übertragen von Assets](../tools/asset-transfer/transfer-assets.md)
   + Produktnutzung {#product-usage}
      + [Überblick](../tools/product-usage/usage-overview.md)
      + [Dateneinstellungen](../tools/product-usage/data-settings.md)
      + [Opt-out-Einstellungen](../tools/product-usage/opt-out-settings.md)

+ Workspace-Projekte {#cja-workspace}
   + [Analysis Workspace – Übersicht](../analysis-workspace/home.md)
   + [Grundlegende Analyse durchführen](../analysis-workspace/perform-basic-analysis.md)
   + [Durchführen einer erweiterten Analyse](../analysis-workspace/perform-adv-analysis.md)
   + Projekte {#build-workspace-project}
      + [Überblick](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [Erstellen von Projekten](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [Öffnen von Projekten](/help/analysis-workspace/build-workspace-project/open-projects.md)
      + [Projekte speichern](../analysis-workspace/build-workspace-project/save-projects.md)
      + Ordner in Analysis Workspace {#workspace-folders}
         + [Über Ordner](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [Erstellen von Ordnern und Unterordnern](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [Verwalten von Ordnern](../analysis-workspace/build-workspace-project/workspace-folders/manage-folders.md)
         + [Hinzufügen oder Verschieben von Projekten zu Ordnern](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
      + [Hotkeys (Tastaturbefehle)](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [Farbpaletten](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [Anzeigen der Dichte](../analysis-workspace/build-workspace-project/view-density.md)
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
         + [Filtern und Sortieren von Tabellen](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
         + [Arbeitsbereichs-Summen](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + Kohortentabelle {#cohort-table}
         + [Überblick](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [Konfigurieren](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [Anwendungsfälle](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + Fallout {#fallout}
         + [Überblick](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [Konfigurieren](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [Interdimensionaler Fallout](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [Anwenden von Filtern](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
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
      + [Horizontales Säulendiagramm](../analysis-workspace/visualizations/bullet-graph.md)
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
      + [Baumdiagramm](../analysis-workspace/visualizations/treemap.md)
      + [Venn](../analysis-workspace/visualizations/venn.md)
   + Bedienfelder {#panels}
      + [Überblick](../analysis-workspace/c-panels/panels.md)
      + [Leeres Bedienfeld](../analysis-workspace/c-panels/blank-panel.md)
      + [Attribution](../analysis-workspace/c-panels/attribution.md)
      + [Experimentieren](../analysis-workspace/c-panels/experimentation.md)
      + [Freiform](../analysis-workspace/c-panels/freeform-panel.md)
      + [Medien-Zielgruppendurchschnitt pro Minute](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)
      + [Gleichzeitige Medienbetrachtende](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + [Bei der Medienwiedergabe verbrachte Zeit](../analysis-workspace/c-panels/media-playback-time-spent.md)
      + [Nächstes oder vorheriges Objekt](../analysis-workspace/c-panels/next-previous.md)
      + [Quick Insights](../analysis-workspace/c-panels/quickinsight.md)
   + Kuratieren, Freigeben und Planen von Projekten {#curate-share}
      + [Überblick](../analysis-workspace/curate-share/send-schedule-files.md)
      + [Kuratieren von Projekten](../analysis-workspace/curate-share/curate.md)
      + [Freigeben von Projekten](../analysis-workspace/curate-share/share-projects.md)
      + [Erstellen von freigebbaren Links](../analysis-workspace/curate-share/shareable-links.md)
      + [Schreibgeschützte Projekte](../analysis-workspace/curate-share/view-only-projects.md)
   + Export {#export}
      + [Überblick](../analysis-workspace/export/export-project-overview.md)
      + [Download](../analysis-workspace/export/download-send.md)
      + [An andere senden](../analysis-workspace/export/t-schedule-report.md)
      + [Exportieren in die Cloud](../analysis-workspace/export/export-cloud.md)
   + Anomalieerkennung {#anomaly-detection}
      + [Überblick](../analysis-workspace/c-anomaly-detection/anomaly-detection.md)
      + [Anzeigen von Anomalien](../analysis-workspace/c-anomaly-detection/view-anomalies.md)
      + [Statistische Verfahren](../analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)
   + Prognose {#forecasting}
      + [Überblick](../analysis-workspace/c-forecast/forecasting.md)
      + [Anzeigen von Prognosen](../analysis-workspace/c-forecast/view-forecasts.md)
      + [Statistische Verfahren](../analysis-workspace/c-forecast/statistics-forecasting.md)
   + [Inhaltsverzeichnis ](../analysis-workspace/build-workspace-project/project-table-of-contents.md)
   + [Benutzervoreinstellungen](../analysis-workspace/user-preferences.md)
   + Häufig gestellte Fragen zu Arbeitsbereichen und mehr {#workspace-faq}
      + [Häufig gestellte Fragen](../analysis-workspace/workspace-faq/faq.md)
      + [Fehlermeldungen](../analysis-workspace/workspace-faq/error-messages.md)
      + [Einschränkungen](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [Administrationsanforderungen](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Barrierefreiheit](../analysis-workspace/workspace-faq/aw-accessibility.md)

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
   + [Timeline](../guided-analysis/types/timeline.md)
   + [Trends](../guided-analysis/types/trends.md)
   + [Anwendungsfälle für Branchen](../guided-analysis/industry-use-cases.md)
   + [Häufig gestellte Fragen](../guided-analysis/faq.md)

+ Komponenten {#cja-components}
   + [Überblick](../components/overview.md)
   + [Verwenden von Komponenten in Analysis Workspace](../components/use-components-in-workspace.md)
   + [Komponentenbeschreibungen hinzufügen](../components/add-component-descriptions.md)
   + Anmerkungen {#annotations}
      + [Anmerkungen – Übersicht](../components/annotations/overview.md)
      + [Erstellen von Anmerkungen](../components/annotations/create-annotations.md)
      + [Verwalten von Anmerkungen](../components/annotations/manage-annotations.md)
      + [Anzeigen von Anmerkungen](../components/annotations/view-annotations.md)
      + [Anmerkungen für Mobilgeräte](../components/annotations/mobile-annotations.md)
   + [Geplante Projekte](../components/scheduled-projects-manager.md)
   + Zielgruppen {#audiences}
      + [Überblick über Zielgruppen](../components/audiences/audiences-overview.md)
      + [Erstellen und Veröffentlichen von Zielgruppen](../components/audiences/publish.md)
      + [Verwalten von Audiences](../components/audiences/manage.md)
   + Dimensionen {#dimensions}
      + [Dimensionen – Übersicht](../components/dimensions/overview.md)
      + [Dimensionsvorschau](../components/dimensions/view-dimensions.md)
      + [Dimensionen aufschlüsseln](../components/dimensions/t-breakdown-fa.md)
      + [Dimensionen für die Zeitunterteilung](../components/dimensions/time-parting-dimensions.md)
      + [Dimensionen hoher Kardinalität](../components/dimensions/high-cardinality.md)
   + [Metriken](../components/apply-create-metrics.md)
   + Filter {#cja-filters}
      + [Überblick](../components/filters/filters-overview.md)
      + [Erstellen von Filtern](../components/filters/create-filters.md)
      + [Erstellen von Filtern](../components/filters/filter-builder.md)
      + [Schnellfilter](../components/filters/quick-filters.md)
      + [Sequenzielle Filter](../components/filters/seg-sequential-build.md)
      + [Freigeben von Filtern](../components/filters/filters-share.md)
      + [Taggen von Filtern](../components/filters/filters-tag.md)
      + [Filtern der Filterliste](../components/filters/filters-filter.md)
      + [Filter als Favoriten markieren](../components/filters/filters-favorite.md)
      + [Genehmigen von Filtern](../components/filters/filters-approve.md)
      + [Kopieren von Filtern](../components/filters/filters-copy.md)
      + [Filter verwalten](../components/filters/manage-filters.md)
      + [Operatoren](../components/filters/operators.md)
   + Berechnete Metriken {#cja-calcmetrics}
      + [Überblick](../components/calc-metrics/calc-metr-overview.md)
      + Workflow bei berechneten Metriken {#cm-workflow}
         + [Erstellen von berechneten Metriken](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Bilden berechneter Metriken](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Metriken suchen](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [Metriktyp und Attribution](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Erstellen einer Teilnahmemetrik](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [Gefilterte Metriken](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Filter stapeln und ersetzen](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Berechnete Metriken filtern](../components/calc-metrics/cm-workflow/cm-filter.md)
         + [Berechnete Metriken als Favoriten markieren](../components/calc-metrics/cm-workflow/cm-favorite.md)
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
      + [Anwendungsfälle](/help/components/c-intelligent-alerts/alerts-use-cases.md)
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

+ Report Builder {#cja-reportbuilder}
   + [Überblick](../report-builder/report-buider-overview.md)
   + [Einrichten von Report Builder](../report-builder/report-builder-setup.md)
   + [Datenblock erstellen](../report-builder/create-a-data-block.md)
   + [Report Builder-Hub](../report-builder/report-builder-hub.md)
   + [Datenansicht auswählen](../report-builder/select-data-view.md)
   + [Auswählen eines Datumsbereichs](../report-builder/select-date-range.md)
   + [Arbeiten mit Filtern](../report-builder/work-with-filters.md)
   + [Filtern von Dimensionen](../report-builder/filter-dimensions.md)
   + [Verwalten von Datenblöcken](../report-builder/manage-reportbuilder.md)
   + [Erstellen von Zeitplänen für Arbeitsmappen](../report-builder/schedule-reportbuilder.md)
   + [Eingeschränkte Beschriftungen](../report-builder/restricted-labels.md)
   + [Report Builder-Einstellungen](../report-builder/report-builder-settings.md)

+ Berichterstellung für Activity Manager {#reporting-activity-manager}
   + [Überblick](../reporting-activity-manager/reporting-activity-overview.md)
   + [Anzeigen von Berichtsaktivität](../reporting-activity-manager/reporting-activity.md)
   + [Abbrechen von Berichtsanfragen](../reporting-activity-manager/reporting-activity-cancel-requests.md)

+ Stitching {#stitching}
   + [Überblick](/help/stitching/overview.md)
   + [Feldbasierte Zuordnung](/help/stitching/fbs.md)
   + [Diagrammbasierte Zuordnung](/help/stitching/gbs.md)
   + [Zuordnung verwenden](/help/stitching/use-stitching.md)
   + [Erstellen und Verwalten von zugeordneten Datensätzen](/help/stitching/stitching-ui.md)
   + [Häufig gestellte Fragen](/help/stitching/faq.md)

+ Adobe-Integrationen {#integrations}
   + [Überblick](/help/integrations/overview.md)
   + [Integrieren von Adobe Analytics](/help/integrations/aa.md)
   + [Integrieren von Target](/help/integrations/at.md)
   + [Integrieren von Journey Optimizer-Daten](/help/integrations/ajo.md)
   + [Integrieren von Entscheidungs-Management-Daten](/help/integrations/ajo-od.md)
   + [Integrieren von Kunden-KI](/help/integrations/customer-ai.md)

+ Data Governance {#cja-privacy}
   + [Data Governance](../privacy/privacy-overview.md)
   + [Administratorprotokoll](../privacy/audit-log.md)
   + [Vom Kunden verwaltete Schlüssel](../privacy/cmk.md)

+ Anwendungsfälle {#cja-usecases}
   + [Anwendungsfälle für Customer Journey Analytics](../use-cases/cja-usecases.md)
   + Google Analytics-Daten {#ga}
      + [Migrieren von Daten aus Google Analytics](../use-cases/ga/overview.md)
      + [Aufnehmen von historischen Daten aus Google Analytics](../use-cases/ga/backfill.md)
      + [Konfigurieren des Streaming-Vorgangs von Google Analytics-Daten](../use-cases/ga/streaming.md)
      + [Bericht zu Google Analytics-Daten](../use-cases/ga/report.md)
   + Datenaufnahme {#data-ingestion}
      + [Aufnehmen und Verwenden von Marketo Engage-Daten](../use-cases/data-ingestion/marketo.md)
      + [Aufnehmen und Verwenden von Experience Platform-Zielgruppen](../use-cases/data-ingestion/ingest-aep-segments.md)
   + Datenansichten {#data-views}
      + [Anwendungsfälle von Datenansichten](/help/use-cases/data-views/data-views-usecases.md)
      + [Verwenden von Bindungsdimensionen und Metriken](/help/use-cases/data-views/binding-dimensions-metrics.md)
      + [Verwenden von Zusammenfassungsdaten](/help/use-cases/data-views/summary-data.md)
      + [Anwendungsfälle für BI-Erweiterungen](/help/use-cases/data-views/bi-extension-usecases.md)
   + Datenexport {#data-export}
      + [Überblick](../use-cases/data-export/overview.md)
      + [BI-Erweiterung](../use-cases/data-export/bi-extension.md)
      + [Exportieren von Datensätzen](../use-cases/data-export/export-datasets.md)
      + [Exportieren einer vollständigen Tabelle](../use-cases/data-export/export-full-table.md)
      + [Abfrage-Service- und Export-Datensätze](../use-cases/data-export/queryservice-export-datasets.md)
   + B2B {#b2b}
      + [Beispiel für ein B2B-Projekt](../use-cases/b2b/example.md)
   + Kanalübergreifende Daten {#cross-channel}
      + [Kanalübergreifendes Analysieren von Daten](../use-cases/cross-channel/cross-channel.md)
      + [Importieren von Callcenter- und Web-Daten](../use-cases/cross-channel/call-center.md)
   + Adobe Analytics-Daten {#aa-data}
      + [Verwenden von Marketing-Kanal-Dimensionen](../use-cases/aa-data/marketing-channels.md)
      + [Kombinieren von Report Suites mit verschiedenen Schemata](../use-cases/aa-data/combine-report-suites.md)
   + Komplexe Daten {#complex-data}
      + [Verwenden von Objekt-Arrays](../use-cases/object-arrays.md)
   + Stitching {#stitching}
      + [Gemeinsam verwendete Geräte](/help/use-cases/stitching/shared-devices.md)
   + Abgeleitete Felder {#derived-fields}
      + [Bericht über Ziele](../use-cases/goals-using-derived-fields.md)

+ Labs {#labs}
   + [Labs-Benutzerhandbuch](../labs/labs.md)

+ Fehlerbehebung {#troubleshooting}
   + [Vergleichen von Daten](../troubleshooting/compare.md)
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
   + [Anzeigen und Verwalten der Nutzung](../technotes/estimate-usage.md)

+ [Customer Journey Analytics-API](https://developer.adobe.com/cja-apis/docs/)
