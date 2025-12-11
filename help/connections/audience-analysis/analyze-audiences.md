---
title: Analysieren von Experience Platform-Zielgruppen in Customer Journey Analytics
description: Erfahren Sie, wie Sie Experience Platform-Zielgruppen in Customer Journey Analytics analysieren.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 996d7d7bb0c0da566a926f9a3a4c465baca69a9a
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# Analysieren von Experience Platform-Zielgruppen in Customer Journey Analytics {#analyze-audiences-RTCDP}

Nach dem [Erstellen einer Zielgruppenanalysekonfiguration](/help/connections/audience-analysis/audience-analysis-configure.md) werden Zielgruppendaten als neue Dimensionen in den Datenansichten verfügbar, in denen Sie sie für die Erstellung konfigurieren. Sie können die neuen Zielgruppendimensionen überall in Analysis Workspace verwenden, wenn Sie Zugriff auf eine Datenansicht haben, in der die Zielgruppenanalysedimensionen hinzugefügt wurden.

## Verwenden der Vorlage „Zielgruppenübersicht“

In Customer Journey Analytics ist eine Vorlage für die Zielgruppenübersicht verfügbar.

<!-- Can you also use the new audience dimensions in any project, regardless of whether it's a template? I assume so -->

<!-- What are the names of the new dimensions? Are they customized to whatever your audience names are in AEP, or are they always the same? Are they the dimensions available in the Audience overview template? (Audience Name, Audience Origin, Exited Audience Name, Exited Audience Origin; Audience Description, Exited Audience Description). Metrics included (Distinct Audiences) -->

Informationen zum Zugriff auf die Vorlage „Zielgruppenübersicht“ finden Sie unter [Zugriff auf und Ausführen einer Vorlage](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template) unter [Verwenden von Vorlagen](/help/analysis-workspace/templates/use-templates.md).

Die Vorlage Zielgruppenübersicht enthält die folgenden Bedienfelder:

## Bedienfeld „Nutzungsübersicht“

Zeigt Daten für alle Zielgruppen mit Nutzungsereignissen an, die mit der ausgewählten Datenansicht verknüpft sind. Daten zur Zielgruppenzugehörigkeit werden täglich aus Experience Platform aktualisiert. Daten werden immer für gestern angezeigt. Daher führt eine Änderung des Datumsbereichs des Bedienfelds zu ungenauen Daten.

Verwenden Sie die Tabelle in diesem Bedienfeld, um das Verhalten der Zielgruppe besser zu verstehen. Ziehen Sie die Dimension Zielgruppenbeschreibung aus der ausgewählten Datenansicht und fügen Sie sie als Aufschlüsselung hinzu. Oder verwenden Sie eine andere Interaktionsdimension (z. B. Seite, Aktion usw.) als Aufschlüsselung.

## Bedienfeld „Ursprünge der Top-Zielgruppe“

Zeigt an, wo die Zielgruppe erstellt wurde, ob in RTCDP, Customer Journey Analytics usw.

Anhand der Tabelle in diesem Bedienfeld können Sie besser verstehen, wie sich die Herkunft der Zielgruppe auf andere Faktoren auswirken könnte. Ziehen Sie die Dimension Zielgruppenname aus der ausgewählten Datenansicht und fügen Sie sie als Aufschlüsselung hinzu. Oder verwenden Sie eine andere Interaktionsdimension (z. B. Seite, Aktion usw.) als Aufschlüsselung.

## Bedienfeld zur Zielgruppenüberschneidung

Zeigt Daten für alle Zielgruppen mit Nutzungsereignissen an, die mit der ausgewählten Datenansicht verknüpft sind. Daten werden immer für gestern angezeigt. Daher führt eine Änderung des Datumsbereichs des Bedienfelds zu ungenauen Daten.

Wählen Sie bis zu drei Zielgruppen in der Tabelle in diesem Bedienfeld aus, um zu sehen, wie sie sich im entsprechenden Venn-Diagramm überschneiden.

## Ausgetretenes Bedienfeld zur Zielgruppennutzung

Zeigt Daten für alle ausgeschlossenen Zielgruppen mit Nutzungsereignissen an, die mit der ausgewählten Datenansicht verknüpft sind. Daten werden immer für gestern angezeigt. Daher führt eine Änderung des Datumsbereichs des Bedienfelds zu ungenauen Daten. „Ausgestiegene Zielgruppen“ sind Zielgruppen, in denen Personen mit Datennutzungsereignissen gestern den Computer verlassen oder ihn verlassen haben.

Verwenden Sie die Tabelle in diesem Bedienfeld, um das Verhalten der Zielgruppe besser zu verstehen. Ziehen Sie die Dimension Ausgetretene Zielgruppenbeschreibung aus der ausgewählten Datenansicht und fügen Sie sie als Aufschlüsselung hinzu. Oder verwenden Sie eine andere Interaktionsdimension oder Metrik (z. B. Seite, Aktion usw.) als Aufschlüsselung.

## Bedienfeld für die am häufigsten beendeten Zielgruppenursprünge

Zeigt an, wo jede existierende Zielgruppe ursprünglich erstellt wurde, ob in RTCDP, Customer Journey Analytics usw.

Anhand der Tabelle in diesem Bedienfeld können Sie besser verstehen, wie sich die Herkunft der Zielgruppe auf andere Faktoren auswirken könnte. Ziehen Sie die Dimension Ausgetretener Zielgruppenname aus der ausgewählten Datenansicht und fügen Sie sie als Aufschlüsselung hinzu. Oder verwenden Sie eine andere Interaktionsdimension oder Metrik (z. B. Seite, Aktion usw.) als Aufschlüsselung.








