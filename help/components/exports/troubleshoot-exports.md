---
description: Verwalten von Protokollen für vorhandene Exporte
keywords: Analysis Workspace
title: Fehlerbehebung bei fehlgeschlagenen Exporten
feature: Components
exl-id: fbc25150-4390-40a2-9f17-aadf254258ad
role: User
TQID: https://experienceleague.adobe.com/pKXaX-DMxsFn9Y39AjqL1VGaSM--WFda9fuD7zJLgoI
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 390
ht-degree: 7%

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

* Unternehmensname
