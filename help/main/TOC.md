---
git-repo: https://github.com/AdobeDocs/analytics-platform.de-DE
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Handbuch für Customer Journey Analytics
user-guide-description: Hier erhalten Sie Informationen zu Adobe Customer Journey Analytics und Erläuterungen zur Nutzung von Analysis Workspace mit Daten aus Experience Platform.
breadcrumb-title: Handbuch für Customer Journey Analytics
source-git-commit: 3d090bd6fafe58f2e7024964a2b3ec91624c63cb
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 77%

---


# Adobe Customer Journey Analytics-Anleitung {#using}

+ [Adobe Customer Journey Analytics-Anleitung](../getting-started/cja-landing.md)
+ [KI-Assistent für Adobe Customer Journey Analytics](../ai-assistant.md)
+ Versionshinweise {#releases}
   + [Neueste Version](../release-notes/latest.md)
   + [Versionen 2024](../release-notes/2024.md)
   + [Versionen 2023](../release-notes/2023.md)
   + [Versionen 2022](../release-notes/2022.md)
   + [Versionen von 2021](../release-notes/2021.md)
   + [Versionen von 2020](../release-notes/2020.md)
   + [Feature Release-Strategie](../release-notes/releases.md)
   + [Aktualisierungen der Dokumentation](../release-notes/doc-changes.md)

+ Erste Schritte {#cja-overview}
   + [Überblick über Customer Journey Analytics](../getting-started/cja-overview.md)
   + [Schnellstartanleitung](../getting-started/cja-getting-started.md)
   + [Landingpage](../getting-started/landing.md)
   + [Landingpage (alt)](../getting-started/cja-landing-old.md)
   + [Häufig gestellte Fragen](../getting-started/cja-faq.md)
   + [Vergleichen von Customer Journey Analytics mit BI-Lösungen](../getting-started/cja-vs-bi.md)

+ Customer Journey Analytics und Adobe Analytics {#compare-aa-cja}
   + Upgrade auf Customer Journey Analytics {#upgrade-to-cja}
      + [Erste Schritte](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)
      + [Aktualisierungspfad auswählen](/help/getting-started/cja-upgrade/cja-upgrade-path.md)
      + [Daten an Platform senden](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)
      + [Verlaufsdaten beibehalten](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)
   + Vergleich mit Adobe Analytics {#cja-aa-comparison}
      + [Überblick](../getting-started/aa-vs-cja/overview.md)
      + [Verwenden von Adobe Analytics-Daten in Customer Journey Analytics](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Unterstützung der Customer Journey Analytics-Funktionen](../getting-started/aa-vs-cja/cja-aa.md)
      + [Vergleich der Terminologie für Analytics-Daten, die durch den Analytics-Quell-Connector übergeben werden](../getting-started/aa-vs-cja/terminology.md)
      + [Vergleich der Datenverarbeitung zwischen Adobe Analytics und Customer Journey Analytics](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [Virtuelle Reporting-Umgebungen und Sandbox-Umgebungen](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Verarbeitungsregeln, VISTA und Klassifizierungen versus Datenvorbereitung](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [AAID, ECID, AACUSTOMID und der Analytics-Quell-Connector](../getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [Weiterentwicklung von Adobe Analytics](../getting-started/aa-to-cja.md)
   + [Benutzerhandbuch für Adobe Analytics-Benutzende](../getting-started/aa-to-cja-user.md)

+ Datenaufnahme {#cja-data-ingestion}
   + [Datenaufnahme – Übersicht](../data-ingestion/data-ingestion.md)
   + Kurzanleitungen zur Aufnahme und Verwendung von Daten{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + Adobe Experience Platform Edge Network {#edge-network}
         + [Web SDK](../data-ingestion/aepwebsdk.md)
         + [Mobile SDK](../data-ingestion/aepmobilesdk.md)
         + [Server-API](../data-ingestion/serverapi.md)
      + [Batch-Daten](../data-ingestion/batch.md)
      + [Streaming-Daten](../data-ingestion/streaming.md)
      + [Quell-Connectoren](../data-ingestion/sources.md)

+ Verbindungen {#cja-connections}
   + [Verbindungen – Übersicht](../connections/overview.md)
   + [Erstellen oder Bearbeiten einer Verbindung](../connections/create-connection.md)
   + [Verbindungen verwalten](../connections/manage-connections.md)
   + [Kombinierte Ereignis-Datensätze](../connections/combined-dataset.md)
   + [Standardsuchen](../connections/standard-lookups.md)

+ Datenansichten {#cja-dataviews}
   + [Übersicht über die Datenansichten](../data-views/data-views.md)
   + [Erstellen oder Bearbeiten einer Datenansicht](../data-views/create-dataview.md)
   + [Sitzungseinstellungen](../data-views/session-settings.md)
   + Komponenteneinstellungen {#component-settings}
      + [Übersicht über Komponenteneinstellungen](../data-views/component-settings/overview.md)
      + [Attribution](../data-views/component-settings/attribution.md)
      + [Verhalten](../data-views/component-settings/behavior.md)
      + [Format](../data-views/component-settings/format.md)
      + [Werte einschließen/ausschließen](../data-views/component-settings/include-exclude-values.md)
      + [Deduplizierung von Metriken](../data-views/component-settings/metric-deduplication.md)
      + [Keine Wertoptionen](../data-views/component-settings/no-value-options.md)
      + [Persistenz](../data-views/component-settings/persistence.md)
      + [Teilzeichenfolge](../data-views/component-settings/substring.md)
      + [Wert-Bucketing](../data-views/component-settings/value-bucketing.md)
   + [Standardkomponentenreferenz](../data-views/component-reference.md)
   + [BI-Erweiterung](../data-views/bi-extension.md)
   + [Abgeleitete Felder](../data-views/derived-fields/derived-fields.md)
   + [Beschriftungen und Richtlinien](../data-views/data-governance.md)

+ Workspace-Projekte {#cja-workspace}
   + [Analysis Workspace – Übersicht](../analysis-workspace/home.md)
   + [Grundlegende Analyse durchführen](../analysis-workspace/perform-basic-analysis.md)
   + [Durchführen einer erweiterten Analyse](../analysis-workspace/perform-adv-analysis.md)
   + Projekte {#build-workspace-project}
      + [Übersicht über Projekte](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [Projekte erstellen](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [Projekte speichern](../analysis-workspace/build-workspace-project/save-projects.md)
      + Ordner in Analysis Workspace {#workspace-folders}
         + [Über Ordner in Analysis Workspace](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [Erstellen von Ordnern und Unterordnern](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [Löschen von Ordnern](../analysis-workspace/build-workspace-project/workspace-folders/delete-folders.md)
         + [Hinzufügen von Projekten](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
         + [Entfernen eines Projekts](../analysis-workspace/build-workspace-project/workspace-folders/remove-projects.md)
         + [Speichern eines neuen Projekts](../analysis-workspace/build-workspace-project/workspace-folders/save-new-project-folder.md)
      + [Hotkeys (Tastaturbefehle)](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [Farbpaletten](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [Dichte anzeigen](../analysis-workspace/build-workspace-project/view-density.md)
   + Visualisierungen {#visualizations}
      + [Visualisierungsübersicht](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [Datenquellen verwalten](../analysis-workspace/visualizations/t-sync-visualization.md)
      + Freiformtabelle {#freeform-table}
         + [Freiformtabelle](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + Spalten- und Zeileneinstellungen {#column-row-settings}
            + [Spalteneinstellungen](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [Zeileneinstellungen](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [Dynamische im Vergleich zu statischen Elementen](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [Filtern und Sortieren von Tabellen](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
         + [Arbeitsbereich-Summen](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + Kohortentabelle {#cohort-table}
         + [Was ist eine Kohortenanalyse?](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [Konfigurieren eines Kohortenanalyseberichts](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [Anwendungsfälle für die Kohortenanalyse](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + Fallout {#fallout}
         + [Fallout-Übersicht](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [Fallout-Visualisierung konfigurieren](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [Interdimensionaler Fallout](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [Filter in Fallout-Analyse anwenden](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + Fluss {#flow}
         + [Flussübersicht](../analysis-workspace/visualizations/c-flow/flow.md)
         + [Flussvisualisierung konfigurieren](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [Interdimensionale Flüsse](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + [Bereich und Bereich gestapelt](../analysis-workspace/visualizations/area.md)
      + [Balken und Balken gestapelt](../analysis-workspace/visualizations/bar.md)
      + [Lineardiagramm](../analysis-workspace/visualizations/bullet-graph.md)
      + [Kombinationsdiagramm](../analysis-workspace/visualizations/combo-charts.md)
      + [Ringdiagramm](../analysis-workspace/visualizations/donut.md)
      + [Histogramm](../analysis-workspace/visualizations/histogram.md)
      + [Horizontalbalken und Horizontalbalken gestapelt](../analysis-workspace/visualizations/horizontal-bar.md)
      + [Intelligente Beschriftungen](../analysis-workspace/visualizations/intelligent-captions.md)
      + [Zusammenfassung einer Schlüsselmetrik](../analysis-workspace/visualizations/key-metric.md)
      + [Linie](../analysis-workspace/visualizations/line.md)
      + [Streudiagramm](../analysis-workspace/visualizations/scatterplot.md)
      + [Sammelnummer und Sammeländerung](../analysis-workspace/visualizations/summary-number-change.md)
      + [Text](../analysis-workspace/visualizations/text.md)
      + [Baumdiagramm](../analysis-workspace/visualizations/treemap.md)
      + [Venn](../analysis-workspace/visualizations/venn.md)
   + Bedienfelder {#panels}
      + [Übersicht über Bedienfelder](../analysis-workspace/c-panels/panels.md)
      + [Attributionsbedienfeld](../analysis-workspace/c-panels/attribution.md)
      + [Leeres Bedienfeld](../analysis-workspace/c-panels/blank-panel.md)
      + [Experimentier-Bedienfeld](../analysis-workspace/c-panels/experimentation.md)
      + [Freiform-Bedienfeld](../analysis-workspace/c-panels/freeform-panel.md)
      + [Bedienfeld „Zielgruppendurchschnitt pro Minute“](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)
      + [Bedienfeld „Quick Insights“](../analysis-workspace/c-panels/quickinsight.md)
      + [Bedienfeld „Gleichzeitige Medienbetrachter“](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + [Panel „Verbrachte Zeit bei der Medienwiedergabe“](../analysis-workspace/c-panels/media-playback-time-spent.md)
   + Kuratieren, Freigeben und Planen von Projekten {#curate-share}
      + [Menü „Freigeben“](../analysis-workspace/curate-share/send-schedule-files.md)
      + [Kuratieren von Projekten](../analysis-workspace/curate-share/curate.md)
      + [Freigeben von Projekten](../analysis-workspace/curate-share/share-projects.md)
      + [Erstellen von freigebbaren Links](../analysis-workspace/curate-share/shareable-links.md)
      + [Schreibgeschützte Projekte](../analysis-workspace/curate-share/view-only-projects.md)
   + Export {#export}
      + [Exportübersicht](../analysis-workspace/export/export-project-overview.md)
      + [Download](../analysis-workspace/export/download-send.md)
      + [An andere senden](../analysis-workspace/export/t-schedule-report.md)
      + [In die Cloud exportieren](../analysis-workspace/export/export-cloud.md)
   + Anomalieerkennung {#anomaly-detection}
      + [Übersicht über die Anomalieerkennung](../analysis-workspace/c-anomaly-detection/anomaly-detection.md)
      + [Anomalien in Analysis Workspace anzeigen](../analysis-workspace/c-anomaly-detection/view-anomalies.md)
      + [In der Anomalieerkennung verwendete statistische Verfahren](../analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)
   + Prognosen {#forecasting}
      + [Prognosen - Übersicht](../analysis-workspace/c-forecast/forecasting.md)
      + [Prognosen in Analysis Workspace anzeigen](../analysis-workspace/c-forecast/view-forecasts.md)
      + [Statistische Verfahren, die beim Prognosedienst verwendet werden](../analysis-workspace/c-forecast/statistics-forecasting.md)
   + [Benutzervoreinstellungen](../analysis-workspace/user-preferences.md)
   + Häufig gestellte Fragen zu Workspace {#workspace-faq}
      + [Häufig gestellte Fragen](../analysis-workspace/workspace-faq/faq.md)
      + [Fehlermeldungen](../analysis-workspace/workspace-faq/error-messages.md)
      + [Analysis Workspace-Beschränkungen](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [Administrationsanforderungen](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Barrierefreiheit in Analysis Workspace](../analysis-workspace/workspace-faq/aw-accessibility.md)

+ Analytics-Dashboards {#cja-dashboards}
   + [Analytics-Dashboards – Übersicht](../mobile-app/home.md)
   + [Kuratoraufgaben](../mobile-app/curator.md)
   + [Erstellen einer mobilen Scorecard](../mobile-app/create-scorecard.md)
   + [Mobile Scorecards verwalten](../mobile-app/manage-scorecard.md)
   + [Einrichten von Führungskräften für die Verwendung von Dashboards](../mobile-app/set-up-execs.md)
   + [Schnellstarthandbuch für ausführende Benutzer](../mobile-app/executive.md)

+ Geführte Analyse {#guided-analysis}
   + [Überblick](../guided-analysis/overview.md)
   + Funktionsmatrix {#feature-matrix}
      + [Interaktion](../guided-analysis/types/engagement.md)
   + Trichter {#funnel}
      + [Friktionsansicht](../guided-analysis/types/friction.md)
      + [Ansicht &quot;Konversionstrends&quot;](../guided-analysis/types/conversion-trends.md)
   + Wirkung {#impact}
      + [Versionsansicht](../guided-analysis/types/release.md)
      + [Ansicht &quot;Erste Verwendung&quot;](../guided-analysis/types/first-use.md)
   + Treue {#retention}
      + [Bindungsrate](../guided-analysis/types/retention-rates.md)
   + Trends {#trends}
      + [Nutzungsansicht](../guided-analysis/types/usage.md)
      + [Frequenzansicht](../guided-analysis/types/frequency.md)
   + Benutzerwachstum {#user-growth}
      + [Aktive Ansicht](../guided-analysis/types/active.md)
      + [Netto-Wachstumsansicht](../guided-analysis/types/net-growth.md)
   + Benutzer-Stream {#streams}
      + [Timeline](../guided-analysis/types/timeline.md)
   + [Anwendungsfälle für Branchen](../guided-analysis/industry-use-cases.md)
   + [Häufig gestellte Fragen](../guided-analysis/faq.md)

+ Komponenten {#cja-components}
   + [Komponentenübersicht](../components/overview.md)
   + [Komponentenbeschreibungen hinzufügen](../components/add-component-descriptions.md)
   + Anmerkungen {#annotations}
      + [Anmerkungen – Übersicht](../components/annotations/overview.md)
      + [Erstellen von Anmerkungen](../components/annotations/create-annotations.md)
      + [Verwalten von Anmerkungen](../components/annotations/manage-annotations.md)
      + [Anzeigen von Anmerkungen](../components/annotations/view-annotations.md)
      + [Anmerkungen für Mobilgeräte](../components/annotations/mobile-annotations.md)
   + [Geplantes Projekt](../components/scheduled-projects-manager.md)
   + Zielgruppen {#audiences}
      + [Überblick über Zielgruppen](../components/audiences/audiences-overview.md)
      + [Erstellen und Veröffentlichen von Zielgruppen](../components/audiences/publish.md)
      + [Verwalten von Audiences](../components/audiences/manage.md)
   + Dimensionen {#dimensions}
      + [Dimensionen – Übersicht](../components/dimensions/overview.md)
      + [Dimensionsvorschau](../components/dimensions/view-dimensions.md)
      + [Dimensionen aufschlüsseln](../components/dimensions/t-breakdown-fa.md)
      + [Dimensionen für die Zeitunterteilung](../components/dimensions/time-parting-dimensions.md)
      + [Dimensionen mit sehr hoher Kardinalität](../components/dimensions/high-cardinality.md)
   + [Metriken](../components/apply-create-metrics.md)
   + Filter {#cja-filters}
      + [Filterübersicht](../components/filters/filters-overview.md)
      + [Filter erstellen](../components/filters/create-filters.md)
      + [Filter freigeben](../components/filters/filters-share.md)
      + [Filter taggen](../components/filters/filters-tag.md)
      + [Filtern der Filterliste](../components/filters/filters-filter.md)
      + [Filter als Favoriten markieren](../components/filters/filters-favorite.md)
      + [Filter genehmigen](../components/filters/filters-approve.md)
      + [Filter kopieren](../components/filters/filters-copy.md)
      + [Schnellfilter](../components/filters/quick-filters.md)
      + [Filter-Builder](../components/filters/filter-builder.md)
      + [Filter verwalten](../components/filters/manage-filters.md)
      + [Operatoren](../components/filters/operators.md)
   + Berechnete Metriken {#cja-calcmetrics}
      + [Übersicht über berechnete Metriken](../components/calc-metrics/calc-metr-overview.md)
      + Workflow bei berechneten Metriken {#cm-workflow}
         + [Workflow bei berechneten Metriken](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Metriken suchen](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [Erstellen von Metriken](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Metriktyp und Attribution](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Erstellen einer Beitragsmetrik](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [Gefilterte Metriken](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Filter stapeln und ersetzen](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Gefilterte und gewichtete Metriken](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [Berechnete Metriken filtern](../components/calc-metrics/cm-workflow/cm-filter.md)
         + [Berechnete Metriken als Favoriten markieren](../components/calc-metrics/cm-workflow/cm-favorite.md)
         + [Berechnete Metriken kopieren](../components/calc-metrics/cm-workflow/cm-copy.md)
         + [Funktionen verwenden](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Berechnete Metriken taggen](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Berechnete Metriken genehmigen](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [Berechnete Metriken freigeben](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Manager für berechnete Metriken](../components/calc-metrics/cm-workflow/cm-manager.md)
      + [Standardmäßig berechnete Metriken](../components/calc-metrics/default-calcmetrics.md)
      + [Grundlegende Funktionen](../components/calc-metrics/cm-functions.md)
      + [Erweiterte Funktionen](../components/calc-metrics/cm-adv-functions.md)
   + Kalender und Datumsbereiche {#cja-date-ranges}
      + [Übersicht über Kalender und Datumsbereiche](../components/date-ranges/calendar.md)
      + [Datumsbereich erstellen](../components/date-ranges/create.md)
      + [Datumsbereiche verwalten](../components/date-ranges/manage.md)
      + [Benutzerdefinierte Datumsbereiche erstellen](../components/date-ranges/custom-date-ranges.md)
      + [Datumsvergleich](../components/date-ranges/time-comparison.md)
   + Exporte {#exports}
      + [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md)
      + [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md)
      + [Verwalten von Cloud-Exportspeicherorten](/help/components/exports/manage-export-locations.md)
      + [Verwalten von Exporten](/help/components/exports/manage-exports.md)
      + [Verwalten von Exportprotokollen](/help/components/exports/manage-export-logs.md)
      + [Fehlerbehebung bei Exporten](/help/components/exports/troubleshoot-exports.md)
   + Datenwörterbuch {#data-dictionary}
      + [Datenwörterbuch – Überblick](../components/data-dictionary/data-dictionary-overview.md)
      + [Komponenteninformationen im Datenwörterbuch anzeigen](../components/data-dictionary/view-data-dictionary.md)
      + [Bearbeiten von Komponenteneinträgen im Datenwörterbuch](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [Überwachen des Zustands des Datenwörterbuchs](../components/data-dictionary/monitor-data-dictionary-health.md)

+ Report Builder {#cja-reportbuilder}
   + [Übersicht über Report Builder](../report-builder/report-buider-overview.md)
   + [Einrichten von Report Builder](../report-builder/report-builder-setup.md)
   + [Datenblock erstellen](../report-builder/create-a-data-block.md)
   + [Report Builder-Hub](../report-builder/report-builder-hub.md)
   + [Datenansicht auswählen](../report-builder/select-data-view.md)
   + [Datumsbereich auswählen](../report-builder/select-date-range.md)
   + [Arbeiten mit Filtern](../report-builder/work-with-filters.md)
   + [Dimensionen filtern](../report-builder/filter-dimensions.md)
   + [Verwalten von Datenblöcken](../report-builder/manage-reportbuilder.md)
   + [Erstellen von Zeitplänen für Arbeitsmappen](../report-builder/schedule-reportbuilder.md)
   + [Eingeschränkte Beschriftungen](../report-builder/restricted-labels.md)
   + [Report Builder-Einstellungen](../report-builder/report-builder-settings.md)

+ Berichterstellung für Activity Manager {#reporting-activity-manager}
   + [Überblick](../reporting-activity-manager/reporting-activity-overview.md)
   + [Anzeigen von Berichtsaktivität](../reporting-activity-manager/reporting-activity.md)
   + [Abbrechen von Berichtsanfragen](../reporting-activity-manager/reporting-activity-cancel-requests.md)

+ Stitching {#stitching}
   + [Überblick](../stitching/overview.md)
   + [Funktionsweise von Stitching](../stitching/explained.md)
   + [Erstellen und Verwalten von zugeordneten Datensätzen](../stitching/stitching-ui.md)
   + [Häufig gestellte Fragen](../stitching/faq.md)

+ Adobe-Integrationen {#integrations}
   + [Adobe-Lösungen mit Customer Journey Analytics integrieren - Übersicht](/help/integrations/overview.md)
   + [Integrieren von Adobe Analytics mit Customer Journey Analytics](/help/integrations/aa.md)
   + [Integrieren von Journey Optimizer-Daten mit Customer Journey Analytics](/help/integrations/ajo.md)
   + [Integrieren von Entscheidungsverwaltungsdaten mit Customer Journey Analytics](/help/integrations/ajo-od.md)
   + [Integrieren von Customer AI mit Customer Journey Analytics](/help/integrations/customer-ai.md)

+ Data Governance {#cja-privacy}
   + [Data Governance](../privacy/privacy-overview.md)
   + [Administratorprotokoll](../privacy/audit-log.md)
   + [Vom Kunden verwaltete Schlüssel](../privacy/cmk.md)

+ Anwendungsfälle {#cja-usecases}
   + [Anwendungsfälle für Customer Journey Analytics](../use-cases/cja-usecases.md)
   + Google Analytics-Daten {#ga}
      + [Übersicht über die Migration von Daten von Google Analytics zu Customer Journey Analytics](../use-cases/ga/overview.md)
      + [Aufnehmen von historischen Daten von Google Analytics in Platform](../use-cases/ga/backfill.md)
      + [Konfigurieren des Streaming-Vorgangs von Google Analytics-Daten in Platform](../use-cases/ga/streaming.md)
      + [Bericht zu Google Analytics-Daten in Customer Journey Analytics](../use-cases/ga/report.md)
   + Datenaufnahme {#data-ingestion}
      + [Marketo Engage-Daten in Adobe Experience Platform erfassen und in Customer Journey Analytics berichten](../use-cases/data-ingestion/marketo.md)
      + [Adobe Experience Platform-Zielgruppen in Customer Journey Analytics erfassen](../use-cases/data-ingestion/ingest-aep-segments.md)
   + Datenansichten {#data-views}
      + [Anwendungsfälle von Datenansichten](../use-cases/data-views/data-views-usecases.md)
      + [Verwenden von Bindungsdimensionen und Metriken](../use-cases/data-views/binding-dimensions-metrics.md)
   + Datenexport {#data-export}
      + [Überblick](../use-cases/data-export/overview.md)
      + [BI-Erweiterung](../use-cases/data-export/bi-extension.md)
      + [Exportieren von Datensätzen](../use-cases/data-export/export-datasets.md)
      + [Vollständige Tabelle exportieren](../use-cases/data-export/export-full-table.md)
      + [Query Service und Exportieren von Datensätzen](../use-cases/data-export/queryservice-export-datasets.md)
   + B2B {#b2b}
      + [Beispiel für ein B2B-Projekt](../use-cases/b2b/example.md)
      + [Hinzufügen von Daten der Kontoebene als Lookup-Datensatz](../use-cases/b2b/b2b.md)
   + Kanalübergreifende Daten {#cross-channel}
      + [Kanalübergreifendes Analysieren von Daten](../use-cases/cross-channel/cross-channel.md)
      + [Importieren von Callcenter- und Web-Daten](../use-cases/cross-channel/call-center.md)
   + Adobe Analytics-Daten {#aa-data}
      + [Verwenden von Marketing-Kanal-Dimensionen](../use-cases/aa-data/marketing-channels.md)
      + [Kombinieren von Report Suites mit verschiedenen Schemata](../use-cases/aa-data/combine-report-suites.md)
   + Komplexe Daten {#complex-data}
      + [Verwenden von Objekt-Arrays](../use-cases/object-arrays.md)
   + Abgeleitete Felder {#derived-fields}
      + [Verwenden abgeleiteter Felder für Berichte zu Zielen](../use-cases/goals-using-derived-fields.md)

+ Labs {#labs}
   + [Labs-Benutzerhandbuch](../labs/labs.md)

+ Fehlerbehebung {#troubleshooting}
   + [Vergleich von Adobe Analytics-Daten mit Customer Journey Analytics-Daten](../troubleshooting/compare.md)
   + [Konsistenz von Metriken und Zählungen der Zielgruppenzugehörigkeit zwischen Echtzeit-Kundendatenplattform und Customer Journey Analytics](../troubleshooting/consistency-rcdp-cja.md)
   + [Fehlende Berechtigungen](../troubleshooting/lack-of-permissions.md)

+ Technische Hinweise {#technotes}
   + [Zugriffssteuerung](../technotes/access-control.md)
   + [Rechenzentren](../technotes/data-centers.md)
   + [Auswirkungen des Löschens](../technotes/deletion.md)
   + [Domänen](../technotes/domains.md)
   + [Glossar](../technotes/glossary.md)
   + [Leitplanken](../technotes/guardrails.md)
   + [IP-Adressen](../technotes/ip-addresses.md)
   + [Customer Journey Analytics-Performance optimieren](../technotes/optimizing-performance.md)
   + [Anzeigen und Verwalten der Nutzung](../technotes/estimate-usage.md)

+ [Customer Journey Analytics-API](https://developer.adobe.com/cja-apis/docs/)
