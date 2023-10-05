---
description: Verwalten von Protokollen für bestehende Exporte
keywords: Analysis Workspace
title: Fehlerbehebung bei fehlgeschlagenen Exporten
feature: Components
exl-id: fbc25150-4390-40a2-9f17-aadf254258ad
source-git-commit: 2c9dfdf36e47b9467077310a31dc2c6258137d35
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 8%

---

# Fehlerbehebung bei fehlgeschlagenen Exporten

{{release-limited-testing}}

Wenn Sie [vollständige Tabellen aus Analysis Workspace in Cloud-Ziele exportieren](/help/analysis-workspace/export/export-cloud.md)können Sie den Status dieser Exporte über die beiden folgenden [Registerkarte &quot;Exporte&quot;](/help/components/exports/manage-exports.md) und von [Registerkarte &quot;Protokolle&quot;](/help/components/exports/manage-export-logs.md). Fehlgeschlagene Exporte zeigen den Status von [!UICONTROL **Fehlgeschlagen**].

## Häufige Fehler und Aktionen

Exporte können aus verschiedenen Gründen fehlschlagen. In der folgenden Tabelle werden einige der häufigsten Ursachen beschrieben, mit Aktionen, die Sie ausführen können, um die Fehler zu beheben:

| Grund für das Fehlschlagen | Vorgeschlagene Aktion | Weitere Informationen |
|---------|----------|---------|
| Ungültige Position- oder Kontoinformationen | Stellen Sie sicher, dass Ihre Anmeldedaten und andere Informationen für das Cloud-Konto und den Speicherort, in den Sie exportieren, korrekt sind. | [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md) und [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md). |
| Eine Dimension oder Metrik im Bericht wurde aus der Datenansicht entfernt | Wenden Sie sich an Ihren Systemadministrator, um zu sehen, welche Komponenten aus der Datenansicht entfernt wurden. Möglicherweise müssen Sie beim Export eine andere Datenansicht verwenden oder nicht mehr verfügbare Komponenten aus der Tabelle entfernen. | [Customer Journey Analytics-Berichte in die Cloud exportieren](/help/analysis-workspace/export/export-cloud.md) |
| Zeilenlimit überschritten | Je nach Lizenztyp können Sie maximal 3 Millionen, 30 Millionen, 150 Millionen oder 300 Millionen Zeilen exportieren. Aktualisieren Sie die exportierte Tabelle, um die Anzahl der Zeilen insgesamt zu reduzieren. | [Customer Journey Analytics-Berichte in die Cloud exportieren](/help/analysis-workspace/export/export-cloud.md) |
| Geplanter Exportablauf | Der geplante Export, den Sie konfiguriert haben, ist abgelaufen. Aktualisieren Sie die Gültigkeit des Exports. | [Verwalten von Exporten](/help/components/exports/manage-exports.md) |
| Dimension nicht unterstützt | <p>Dimensionen, die die folgenden Kriterien erfüllen, werden im vollständigen Tabellenexport nicht unterstützt:</p> <ul><li>Verwendet ein Objekt-Array</li><li>Hat Persistenz aktiviert<li>Verwendet keine Bindungsdimension</li> | <ul><li>[Verwenden von Objekt-Arrays](/help/use-cases/object-arrays.md)</li><li>[Persistenz-Komponenteneinstellungen](/help/data-views/component-settings/persistence.md)<li>[Bindungsdimensionen und Metriken in Customer Journey Analytics verwenden](/help/use-cases/data-views/binding-dimensions-metrics.md)</li> |
| Eine Data Governance-Richtlinie, die von Ihrem Unternehmen durchgesetzt wird, verhindert, dass Komponenten in Ihrer Tabelle exportiert werden | Wenden Sie sich an Ihren Systemadministrator, um zu sehen, welche Komponenten für den Export eingeschränkt sind. Entfernen Sie die eingeschränkten Komponenten vor dem Export. | *Filtern nach Data Governance-Richtlinien in Datenansichten* Abschnitt in [Beschriftungen und Richtlinien](/help/data-views/data-governance.md) |

## Wenden Sie sich an die Adobe-Kundenunterstützung

Wenn weiterhin Probleme auftreten, wenden Sie sich an die Adobe-Kundenunterstützung. Stellen Sie bei der Kontaktaufnahme mit der Kundenunterstützung bezüglich eines fehlgeschlagenen Exports sicher, dass Ihnen die folgenden Informationen zur Verfügung stehen:

* Exportname

* Export-ID

* Instanz-ID

* Name der Datenansicht

* Standort

* Konto

* Verbindung

* Firmenname
