---
title: Übersicht über die Zielgruppenanalyse
description: Erfahren Sie mehr über das Analysieren von Zielgruppen aus RTCDP in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 840bf65d186178fb944041ff486e95ba60dc6037
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 4%

---

# Übersicht über die Zielgruppenanalyse

<!-- add hidden text in this article when this feature releases: /help/components/audiences/audiences-overview.md and this article: /help/analysis-workspace/templates/use-templates.md-->

>[!NOTE]
>
>Verstehen Sie den Unterschied zwischen Zielgruppenanalyse und Zielgruppenveröffentlichung:
>
>* **Zielgruppenanalyse**: Ermöglicht die Aufnahme von Zielgruppenzugehörigkeitsdaten aus Experience Platform-Profildatensätzen in eine Customer Journey Analytics-Verbindung.
>* **Zielgruppenveröffentlichung**: Ermöglicht das Erstellen und Veröffentlichen von in Customer Journey Analytics gefundenen Zielgruppen in Adobe Experience Platform zum Kunden-Targeting und zur Personalisierung. Weitere Informationen zur Zielgruppenveröffentlichung finden Sie unter [Zielgruppenveröffentlichung - Übersicht](/help/components/audiences/audiences-overview.md).

Mit der Zielgruppenanalyse können Sie Zielgruppenzugehörigkeitsdaten aus Experience Platform-Profildatensätzen in eine Customer Journey Analytics-Verbindung aufnehmen. Zielgruppen werden als neue Dimensionen zur Verwendung in Analysis Workspace verfügbar.

Die folgende Abbildung und die zugehörige Tabelle zeigen eine allgemeine Darstellung davon, wie eine Zielgruppenanalysekonfiguration in Customer Journey Analytics Experience Platform-Zielgruppendaten in Analysis Workspace verfügbar macht:

![Zielgruppenanalyse - Übersicht](assets/audience-analysis-overview.png)

| Nummer | Funktion | Funktion |
|---------|----------|---------|
| 1 | Konfiguration der Zielgruppenanalyse | Die Konfigurationsschnittstelle in Customer Journey Analytics, die zur Konfiguration der Zielgruppenanalyse verwendet wird. |
| 2 | Sandbox | Muss den Profildatensatz enthalten, den Sie zu Ihrer Verbindung hinzufügen möchten. |
| 3 | Profildatensatz | Muss die Experience Platform-Zielgruppendaten enthalten, die Sie analysieren möchten. Dieser Profildatensatz wird der ausgewählten Verbindung hinzugefügt. |
| 4 | Zusammenführungsrichtlinie | Die Zusammenführungsrichtlinie, die mit den Experience Platform-Zielgruppen verknüpft ist, die Sie analysieren möchten. |
| 5 | Profildaten | Die Profildaten, die mit der ausgewählten Zusammenführungsrichtlinie verknüpft sind. Diese Daten sind in Experience Platform-Datensätzen verfügbar. |
| 6 | Neuer Lookup-Datensatz | Stellt Anzeigenamen für die neuen Zielgruppendimensionen bereit, die erstellt werden. <p>Der Lookup-Datensatz wird automatisch erstellt und zusammen mit dem von Ihnen ausgewählten Profildatensatz zur Verbindung hinzugefügt.</p> |
| 7 | Verbindung | Die Verbindung, zu der Sie den ausgewählten Profildatensatz hinzufügen möchten. |
| 8 | Neue Zielgruppendimensionen | Neue Zielgruppendimensionen<!--and metrics?--> die die Experience Platform-Zielgruppen darstellen, die in dem von Ihnen ausgewählten Profildatensatz enthalten sind und in Analysis Workspace für das Reporting verfügbar sind. Diese Dimensionen werden automatisch erstellt. |
| 9 | Datenansichten | Die ausgewählten Datenansichten, die mit Ihrer Verbindung verknüpft sind. Dies sind die Datenansichten, die Sie bei der Analyse von Experience Platform-Zielgruppendaten in Analysis Workspace verwenden möchten. Diese Datenansichten werden für das Reporting automatisch mit Experience Platform-Zielgruppendaten konfiguriert. |

## Zielgruppenanalyse konfigurieren

Bei der Konfiguration der Zielgruppenanalyse wählen Sie die Sandbox und die Zusammenführungsrichtlinie aus, die mit den Experience Platform-Zielgruppen verknüpft sind, die Sie analysieren möchten. Customer Journey Analytics erstellt einen neuen Lookup-Datensatz und fügt dann den Lookup-Datensatz und den Profildatensatz automatisch zur ausgewählten Verbindung hinzu.

>[!NOTE]
>
>Audiences stehen in Customer Journey Analytics-Datenansichten am Tag nach der Erstellung der Zielgruppenanalysekonfiguration zur Verfügung.

Weitere Informationen finden Sie unter [Konfigurieren der Zielgruppenanalyse](/help/connections/audience-analysis/audience-analysis-configure.md).

## Verwalten von Zielgruppenanalysekonfigurationen

Sie können Zielgruppenanalysekonfigurationen verwalten, nachdem sie erstellt wurden. Sie können Konfigurationen anzeigen, bearbeiten und löschen.

Informationen zum Verwalten vorhandener Zielgruppenanalysekonfigurationen finden Sie unter [Verwalten von Zielgruppenanalysekonfigurationen](/help/connections/audience-analysis/audience-analysis-manage.md).

## Analysieren von Zielgruppendaten in Customer Journey Analytics

Wenn Zielgruppendaten in Customer Journey Analytics verfügbar sind, können Sie verwertbare Einblicke in das Verhalten von Zielgruppenmitgliedern über verschiedene Kanäle hinweg erhalten.

Sie können beispielsweise das Verhalten einzelner Kundinnen und Kunden verfolgen, die in derselben E-Mail-Promotion enthalten waren. Wenn die Zielgruppe in Customer Journey Analytics verfügbar ist, können Sie die folgenden Arten von Informationen zu jedem Zielgruppenmitglied anzeigen:

* Clickthroughs von der E-Mail zur Site, die letztendlich zu einem Kauf führten

* Zielgruppenmitglieder, die schließlich einen Kauf im Geschäft getätigt haben

Weitere Informationen finden Sie unter [&#x200B; von Experience Platform-Zielgruppen in Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).

## Rollen- und Berechtigungsanforderungen für die Zielgruppenanalyse

Die folgenden Customer Journey Analytics-Rollen und Experience Platform-Berechtigungen sind für die Zielgruppenanalyse erforderlich:

| Funktion | Anforderungen an Customer Journey Analytics-Rollen oder -Berechtigungen | Experience Platform-Berechtigungsanforderungen |
|---------|----------|----------|
| [Erstellen von Zielgruppenanalysekonfigurationen](/help/connections/audience-analysis/audience-analysis-configure.md) | Systemadministrator | <ul><li>Datensätze: Leseberechtigungen</li><li>Schemata: Lesen, Schreiben</li><li>Identity-Namespaces: Lesen</li></ul> |
| [Anzeigen von Zielgruppenanalysedimensionen in der Datenansicht](/help/connections/audience-analysis/audience-analysis-configure.md#view-audience-dimensions-in-the-data-view) | Produktprofil-Administrator für das Produktprofil, dem die Datenansicht zugewiesen ist <p>Weitere Informationen finden Sie unter [Zugriffssteuerung](/help/technotes/access-control.md).</p> | k. A. |
| Verwenden von Zielgruppenanalysedimensionen in Analysis Workspace | Zugriff auf eine Datenansicht, in der die Zielgruppenanalysedimensionen hinzugefügt wurden | k. A. |










