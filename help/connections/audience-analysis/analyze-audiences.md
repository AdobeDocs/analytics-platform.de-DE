---
title: Analysieren von Experience Platform-Zielgruppen in Customer Journey Analytics
description: Erfahren Sie, wie Sie Experience Platform-Zielgruppen in Customer Journey Analytics analysieren.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 3654d452f2bc4fec5f53854307536b3b8679eac3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# Analysieren von Experience Platform-Zielgruppen in Customer Journey Analytics {#analyze-audiences-RTCDP}

Sie können mit der Analyse von Experience Platform-Zielgruppen in Customer Journey Analytics beginnen, nachdem Sie [eine Zielgruppenanalysekonfiguration erstellt haben](/help/connections/audience-analysis/audience-analysis-configure.md) wenn Zielgruppendaten als neue Dimensionen in Analysis Workspace verfügbar sind.

In Customer Journey Analytics ist eine Vorlage für die Zielgruppenübersicht verfügbar.

Informationen zum Zugriff auf die Vorlage „Zielgruppenübersicht“ finden Sie unter [Zugriff auf und Ausführen einer Vorlage](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template) unter [Verwenden von Vorlagen](/help/analysis-workspace/templates/use-templates.md).

Die Vorlage Zielgruppenübersicht enthält die folgenden Bedienfelder:

## Bedienfeld „Nutzungsübersicht“

Zeigt Daten für alle Zielgruppen mit Nutzungsereignissen an, die mit der ausgewählten Datenansicht verknüpft sind. Daten zur Zielgruppenzugehörigkeit werden täglich aus Experience Platform aktualisiert. Daten werden immer für gestern angezeigt. Daher führt eine Änderung des Datumsbereichs des Bedienfelds zu ungenauen Daten.

Verwenden Sie die Tabelle im Bedienfeld, um das Verhalten der Zielgruppe besser zu verstehen. Ziehen Sie die Dimension Zielgruppenbeschreibung aus der ausgewählten Datenansicht und fügen Sie sie als Aufschlüsselung hinzu. Oder verwenden Sie eine andere Interaktionsdimension (z. B. Seite, Aktion usw.) als Aufschlüsselung.

## Bedienfeld „Ursprünge der Top-Zielgruppe“

Zeigt an, wo die Zielgruppe erstellt wurde, ob in RTCDP, Customer Journey Analytics usw.

Anhand der Tabelle in diesem Bedienfeld können Sie besser verstehen, wie sich die Herkunft der Zielgruppe auf andere Faktoren auswirken könnte. Ziehen Sie die Dimension Zielgruppenname aus der ausgewählten Datenansicht und fügen Sie sie als Aufschlüsselung hinzu. Oder verwenden Sie eine andere Interaktionsdimension (z. B. Seite, Aktion usw.) als Aufschlüsselung.

## Bedienfeld zur Zielgruppenüberschneidung

Zeigt Daten für alle Zielgruppen mit Nutzungsereignissen an, die mit der ausgewählten Datenansicht verknüpft sind. Daten werden immer für gestern angezeigt. Daher führt eine Änderung des Datumsbereichs des Bedienfelds zu ungenauen Daten.

Wählen Sie bis zu drei Zielgruppen in der Tabelle in diesem Bedienfeld aus, um zu sehen, wie sie sich im entsprechenden Venn-Diagramm überschneiden.

## Nutzung der ausgestiegenen Zielgruppe

Zeigt Daten für alle ausgeschlossenen Zielgruppen mit Nutzungsereignissen an, die mit der ausgewählten Datenansicht verknüpft sind. Daten werden immer für gestern angezeigt. Daher führt eine Änderung des Datumsbereichs des Bedienfelds zu ungenauen Daten. „Ausgestiegene Zielgruppen“ sind Zielgruppen, in denen Personen mit Datennutzungsereignissen gestern den Computer verlassen oder ihn verlassen haben.

Verwenden Sie die Tabelle in diesem Bedienfeld, um das Verhalten der Zielgruppe besser zu verstehen. Ziehen Sie die Dimension Vorhandene Zielgruppenbeschreibung aus der ausgewählten Datenansicht und fügen Sie sie als Aufschlüsselung hinzu. Oder verwenden Sie eine andere Interaktionsdimension oder Metrik (z. B. Seite, Aktion usw.) als Aufschlüsselung.

## Bedienfeld für die am häufigsten beendeten Zielgruppenursprünge

Zeigt an, wo jede existierende Zielgruppe ursprünglich erstellt wurde, ob in RTCDP, Customer Journey Analytics usw.

Anhand der Tabelle in diesem Bedienfeld können Sie besser verstehen, wie sich die Herkunft der Zielgruppe auf andere Faktoren auswirken könnte. Ziehen Sie die Dimension Ausgetretener Zielgruppenname aus der ausgewählten Datenansicht und fügen Sie sie als Aufschlüsselung hinzu. Oder verwenden Sie eine andere Interaktionsdimension oder Metrik (z. B. Seite, Aktion usw.) als Aufschlüsselung.








