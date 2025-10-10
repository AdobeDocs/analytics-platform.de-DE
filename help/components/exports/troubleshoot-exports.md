---
description: Verwalten von Protokollen für vorhandene Exporte
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

Wenn Sie [vollständige Tabellen aus Analysis Workspace in Cloud-Ziele exportieren](/help/analysis-workspace/export/export-cloud.md) können Sie den Status dieser Exporte sowohl auf der Registerkarte [Exporte](/help/components/exports/manage-exports.md) als auch auf der Registerkarte [Protokolle](/help/components/exports/manage-export-logs.md) einsehen. Fehlgeschlagene Exporte haben den Status [!UICONTROL **Fehlgeschlagen**].

## Häufige Fehler und Aktionen

Exporte können aus verschiedenen Gründen fehlschlagen. In der folgenden Tabelle werden einige der häufigsten Gründe mit Maßnahmen beschrieben, die Sie ergreifen können, um die Fehler zu beheben:

| Grund für das Fehlschlagen | Vorgeschlagene Aktion | Weitere Informationen |
|---------|----------|---------|
| Ungültige Speicherort- oder Kontoinformationen | Stellen Sie sicher, dass Ihre -Anmeldeinformationen und andere Informationen für das Cloud-Konto und den Speicherort, an die Sie exportieren, korrekt sind. | [Konfigurieren von Cloud](/help/components/exports/cloud-export-accounts.md)Exportkonten und [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md). |
| Eine Dimension oder Metrik im Bericht wurde aus der Datenansicht entfernt | Wenden Sie sich an Ihren Systemadministrator, um zu sehen, welche Komponenten aus der Datenansicht entfernt wurden. Möglicherweise müssen Sie eine andere Datenansicht in Ihrem Export verwenden oder Komponenten aus Ihrer Tabelle entfernen, die nicht mehr verfügbar sind. | [Exportieren von Customer Journey Analytics-Berichten in die Cloud](/help/analysis-workspace/export/export-cloud.md) |
| Zeilenbegrenzung überschritten | Je nach Lizenztyp können Sie maximal 3 Millionen, 30 Millionen, 150 Millionen oder 300 Millionen Zeilen exportieren. Aktualisieren Sie die exportierte Tabelle, um die Anzahl der gesamten Zeilen zu reduzieren. | [Exportieren von Customer Journey Analytics-Berichten in die Cloud](/help/analysis-workspace/export/export-cloud.md) |
| Geplanter Exportablauf | Der konfigurierte geplante Export ist abgelaufen. Aktualisieren Sie die Gültigkeit des Exports. | [Exporte verwalten](/help/components/exports/manage-exports.md) |
| Dimension nicht unterstützt | <p>Dimensionen, die alle folgenden Kriterien erfüllen, werden im vollständigen Tabellenexport nicht unterstützt:</p> <ul><li>wurde aus einem Feld erstellt, das Teil eines Arrays von -Objekten ist</li><li>Hat Persistenz aktiviert<li>Verwendet keine Bindungsdimension</li> | <ul><li>[Verwenden von Objekt-Arrays](/help/use-cases/object-arrays.md)</li><li>[Persistenz - Komponenteneinstellungen](/help/data-views/component-settings/persistence.md)<li>[Verwenden von Bindungsdimensionen und Metriken in Customer Journey Analytics](/help/use-cases/data-views/binding-dimensions-metrics.md)</li> |
| Eine von Ihrem Unternehmen durchgesetzte Data-Governance-Richtlinie verhindert, dass Komponenten in Ihrer Tabelle exportiert werden | Wenden Sie sich an Ihren Systemadministrator, um zu erfahren, welche Komponenten nicht exportiert werden dürfen. Entfernen Sie die eingeschränkten Komponenten vor dem Exportieren. | *Filter zu Data Governance-Richtlinien in Datenansichten* Abschnitt in [Kennzeichnungen und Richtlinien](/help/data-views/data-governance.md) |

## Wenden Sie sich an die Adobe-Kundenunterstützung

Wenn weiterhin Probleme auftreten, wenden Sie sich an die Adobe-Kundenunterstützung. Wenn Sie sich bezüglich eines fehlgeschlagenen Exports an die Kundenunterstützung wenden, stellen Sie sicher, dass Sie über die folgenden Informationen verfügen:

* Exportname

* Export-ID

* Instanz-ID

* Name der Datenansicht

* Standort

* Konto

* Verbindung

* Firmenname
