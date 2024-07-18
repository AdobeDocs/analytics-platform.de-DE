---
description: Verwalten von Protokollen für bestehende Exporte
keywords: Analysis Workspace
title: Fehlerbehebung bei fehlgeschlagenen Exporten
feature: Components
exl-id: fbc25150-4390-40a2-9f17-aadf254258ad
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 8%

---

# Fehlerbehebung bei fehlgeschlagenen Exporten

Wenn Sie [ vollständige Tabellen aus Analysis Workspace in Cloud-Ziele exportieren](/help/analysis-workspace/export/export-cloud.md), können Sie den Status dieser Exporte sowohl auf der Registerkarte [Exporte](/help/components/exports/manage-exports.md) als auch auf der Registerkarte [Protokolle](/help/components/exports/manage-export-logs.md) anzeigen. Fehlgeschlagene Exporte zeigen den Status [!UICONTROL **Fehlgeschlagen**] an.

## Häufige Fehler und Aktionen

Exporte können aus verschiedenen Gründen fehlschlagen. In der folgenden Tabelle werden einige der häufigsten Ursachen beschrieben, mit Aktionen, die Sie ausführen können, um die Fehler zu beheben:

| Grund für das Fehlschlagen | Vorgeschlagene Aktion | Weitere Informationen |
|---------|----------|---------|
| Ungültige Speicherort- oder Kontoinformationen | Stellen Sie sicher, dass Ihre Anmeldedaten und andere Informationen für das Cloud-Konto und den Speicherort, in den Sie exportieren, korrekt sind. | [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md) und [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md). |
| Eine Dimension oder Metrik im Bericht wurde aus der Datenansicht entfernt | Wenden Sie sich an Ihren Systemadministrator, um zu sehen, welche Komponenten aus der Datenansicht entfernt wurden. Möglicherweise müssen Sie beim Export eine andere Datenansicht verwenden oder nicht mehr verfügbare Komponenten aus der Tabelle entfernen. | [Exportieren von Customer Journey Analytics-Berichten in die Cloud](/help/analysis-workspace/export/export-cloud.md) |
| Zeilenlimit überschritten | Je nach Lizenztyp können Sie maximal 3 Millionen, 30 Millionen, 150 Millionen oder 300 Millionen Zeilen exportieren. Aktualisieren Sie die exportierte Tabelle, um die Anzahl der Zeilen insgesamt zu reduzieren. | [Exportieren von Customer Journey Analytics-Berichten in die Cloud](/help/analysis-workspace/export/export-cloud.md) |
| Geplanter Exportablauf | Der geplante Export, den Sie konfiguriert haben, ist abgelaufen. Aktualisieren Sie die Gültigkeit des Exports. | [Exporte verwalten](/help/components/exports/manage-exports.md) |
| Dimension nicht unterstützt | <p>Eine Dimension, die alle der folgenden Kriterien erfüllt, wird im vollständigen Tabellenexport nicht unterstützt:</p> <ul><li>wurde aus einem Feld erstellt, das Teil eines Arrays von Objekten ist</li><li>Hat Persistenz aktiviert<li>Verwendet keine Bindungsdimension</li> | <ul><li>[Verwenden von Objekt-Arrays](/help/use-cases/object-arrays.md)</li><li>[Einstellungen der Persistenz-Komponente](/help/data-views/component-settings/persistence.md)<li>[Bindungsdimensionen und Metriken in Customer Journey Analytics](/help/use-cases/data-views/binding-dimensions-metrics.md) verwenden</li> |
| Eine Data Governance-Richtlinie, die von Ihrem Unternehmen durchgesetzt wird, verhindert, dass Komponenten in Ihrer Tabelle exportiert werden | Wenden Sie sich an Ihren Systemadministrator, um zu sehen, welche Komponenten für den Export eingeschränkt sind. Entfernen Sie die eingeschränkten Komponenten vor dem Export. | *Filtern nach Data Governance-Richtlinien in Datenansichten* im Abschnitt [Beschriftungen und Richtlinien](/help/data-views/data-governance.md) |

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
