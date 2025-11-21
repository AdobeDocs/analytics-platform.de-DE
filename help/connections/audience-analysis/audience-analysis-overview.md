---
title: Übersicht über die Zielgruppenanalyse
description: Erfahren Sie mehr über das Analysieren von Zielgruppen aus RTCDP in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 3654d452f2bc4fec5f53854307536b3b8679eac3
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 4%

---

# Übersicht über die Zielgruppenanalyse

<!-- add hidden text in this article when this feature releases: /help/components/audiences/audiences-overview.md -->

>[!NOTE]
>
>Die Zielgruppenanalyse unterscheidet sich von der Zielgruppenveröffentlichung, mit der Sie in Customer Journey Analytics entdeckte Zielgruppen erstellen und in Adobe Experience Platform veröffentlichen können, um sie zum Targeting und zur Personalisierung zu verwenden. Weitere Informationen zur Zielgruppenveröffentlichung finden Sie unter [Zielgruppenveröffentlichung - Übersicht](/help/components/audiences/audiences-overview.md).

Mit der Zielgruppenanalyse können Sie Zielgruppenzugehörigkeitsdaten aus Experience Platform-Profildatensätzen in eine Customer Journey Analytics-Verbindung aufnehmen. Zielgruppen werden als neue Dimensionen zur Verwendung in Analysis Workspace verfügbar.

Die folgende Abbildung und die zugehörige Tabelle zeigen eine allgemeine Darstellung davon, wie eine Zielgruppenanalysekonfiguration in Customer Journey Analytics Zielgruppendaten aus Experience Platform in Analysis Workspace verfügbar macht:

![Zielgruppenanalyse - Übersicht](assets/audience-analysis-overview.png)

| Nummer | Funktion | Funktion |
|---------|----------|---------|
| 1 | Konfiguration der Zielgruppenanalyse | Konfigurationsoberfläche in Customer Journey Analytics zum Konfigurieren der Zielgruppenanalyse. |
| 2 | Sandbox | Muss den Profildatensatz enthalten, den Sie zu Ihrer Verbindung hinzufügen möchten. |
| 3 | Profildatensatz | Muss die Experience Platform-Zielgruppendaten enthalten, die Sie analysieren möchten. Dieser Profildatensatz wird der ausgewählten Verbindung hinzugefügt. |
| 4 | Zusammenführungsrichtlinie | Die Zusammenführungsrichtlinie, die mit den Experience Platform-Zielgruppen verknüpft ist, die Sie analysieren möchten. |
| 5 | Profildaten | Die Profildaten, die mit der ausgewählten Zusammenführungsrichtlinie verknüpft sind. Diese Daten sind in Experience Platform-Datensätzen verfügbar. |
| 6 | Neuer Lookup-Datensatz | Stellt Anzeigenamen für die neuen Zielgruppendimensionen bereit, die erstellt werden. Der Lookup-Datensatz wird automatisch erstellt und zusammen mit dem von Ihnen ausgewählten Profildatensatz zur Verbindung hinzugefügt. |
| 7 | Verbindung | Die Verbindung, zu der Sie den ausgewählten Profildatensatz hinzufügen möchten. |
| 8 | Neue Zielgruppendimensionen | Neue Zielgruppendimensionen<!--and metrics?--> die die Experience Platform-Zielgruppen darstellen, die in dem von Ihnen ausgewählten Profildatensatz enthalten sind und in Analysis Workspace für das Reporting verfügbar sind. Diese Dimensionen werden automatisch erstellt. |
| 9 | Datenansichten | Die ausgewählten Datenansichten, die mit Ihrer Verbindung verknüpft sind. Dies sind die Datenansichten, die Sie bei der Analyse von Experience Platform-Zielgruppendaten in Analysis Workspace verwenden möchten. Diese Datenansichten werden für das Reporting automatisch mit Experience Platform-Zielgruppendaten konfiguriert. |
| 10 | Analysis Workspace | Der Bereich innerhalb von Customer Journey Analytics, in dem Sie Berichte erstellen, die die aufgenommenen Experience Platform-Zielgruppen enthalten. |

## Zielgruppenanalyse konfigurieren

Bei der Konfiguration der Zielgruppenanalyse wählen Sie die Sandbox und die Zusammenführungsrichtlinie aus, die mit den Experience Platform-Zielgruppen verknüpft sind, die Sie analysieren möchten. Customer Journey Analytics erstellt einen neuen Lookup-Datensatz und fügt dann den Lookup-Datensatz und den Profildatensatz automatisch zur ausgewählten Verbindung hinzu.

Weitere Informationen finden Sie unter [Konfigurieren der Zielgruppenanalyse](/help/connections/audience-analysis/audience-analysis-configure.md).

## Analysieren von Zielgruppendaten in Customer Journey Analytics

Wenn Zielgruppendaten in Customer Journey Analytics verfügbar sind, können Sie verwertbare Einblicke in das Verhalten von Zielgruppenmitgliedern über verschiedene Kanäle hinweg erhalten.

Sie können beispielsweise das Verhalten einzelner Kundinnen und Kunden verfolgen, die in derselben E-Mail-Promotion enthalten waren. Wenn die Zielgruppe in Customer Journey Analytics verfügbar ist, können Sie die folgenden Arten von Informationen zu jedem Zielgruppenmitglied anzeigen:

* Clickthroughs von der E-Mail zur Site, die letztendlich zu einem Kauf führten

* Zielgruppenmitglieder, die schließlich einen Kauf im Geschäft getätigt haben

Weitere Informationen finden Sie unter [ von Experience Platform-Zielgruppen in Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).










