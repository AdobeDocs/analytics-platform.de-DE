---
description: Verwalten von Protokollen für bestehende Exporte
keywords: Analysis Workspace
title: Fehlerbehebung bei fehlgeschlagenen Exporten
feature: Components
hide: true
hidefromtoc: true
source-git-commit: 24e9e4151360597b099a7985a4566b3ca7bfff00
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 3%

---

# Fehlerbehebung bei fehlgeschlagenen Exporten

Wenn Sie [vollständige Tabellen aus Analysis Workspace in Cloud-Ziele exportieren](/help/analysis-workspace/export/export-cloud.md)können Sie den Status dieser Exporte über die beiden folgenden [Registerkarte &quot;Exporte&quot;](/help/components/exports/manage-exports.md) und von [Registerkarte &quot;Protokolle&quot;](/help/components/exports/manage-export-logs.md). Fehlgeschlagene Exporte zeigen den Status von [!UICONTROL **Fehlgeschlagen**].

Exporte können aus verschiedenen Gründen fehlschlagen. In der folgenden Tabelle werden einige der häufigsten Ursachen beschrieben, mit Aktionen, die Sie ausführen können, um die Fehler zu beheben:

| Grund für das Fehlschlagen | Vorgeschlagene Aktion | Weitere Informationen |
|---------|----------|---------|
| Ungültige Position- oder Kontoinformationen | Stellen Sie sicher, dass Ihre Anmeldedaten und andere Informationen für das Cloud-Konto und den Speicherort, in den Sie exportieren, korrekt sind. | [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md) und [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md). |
| Eine Dimension oder Metrik im Bericht wurde aus der Datenansicht entfernt | Wenden Sie sich an Ihren Systemadministrator, um zu sehen, welche Komponenten aus der Datenansicht entfernt wurden. Möglicherweise müssen Sie beim Export eine andere Datenansicht verwenden oder nicht mehr verfügbare Komponenten aus der Tabelle entfernen. | [Customer Journey Analytics-Daten in die Cloud exportieren](/help/analysis-workspace/export/export-cloud.md) |
| Eine Data Governance-Richtlinie, die von Ihrem Unternehmen durchgesetzt wird, verhindert, dass Komponenten in Ihrer Tabelle exportiert werden | Wenden Sie sich an Ihren Systemadministrator, um zu sehen, welche Komponenten für den Export eingeschränkt sind. Entfernen Sie die eingeschränkten Komponenten vor dem Export. | *Filtern nach Data Governance-Richtlinien in Datenansichten* Abschnitt in [Beschriftungen und Richtlinien](/help/data-views/data-governance.md) |