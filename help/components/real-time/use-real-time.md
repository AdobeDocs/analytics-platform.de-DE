---
description: Erfahren Sie, wie Sie Echtzeitberichte in Analysis Workspace verwenden.
title: Verwenden von Echtzeitberichten
feature: Filters, Segments
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
source-git-commit: 24834f6a1424a885c6f7b3dcf0ad84375e21b462
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 5%

---


# Verwenden von Echtzeitberichten

{{release-limited-testing}}

Um Echtzeitberichte zu verwenden, aktivieren Sie den Umschalter **[!UICONTROL Echtzeit-Aktualisierung]** in einem der folgenden Bereiche in Ihrem Workspace-Projekt:



* [Leeres Bedienfeld](/help/analysis-workspace/c-panels/blank-panel.md)
* [Freiform-Bedienfeld](/help/analysis-workspace/c-panels/freeform-panel.md)
* ...

Es wird eine Meldung mit dem Zeitstempel der letzten Aktualisierung der Daten angezeigt. Beispiel: [!UICONTROL  *Letzte Aktualisierung um 19:55*].

Wählen Sie aus dem Dropdown-Menü den Echtzeitzeitraum aus, über den Sie einen Bericht erstellen möchten. Verfügbare Optionen sind:

* [!UICONTROL Letzte 15 Minuten]
* [!UICONTROL Letzte 30 Minuten]
* [!UICONTROL Letzte Stunde]
* [!UICONTROL Letzte 8 Stunden]
* [!UICONTROL Letzte 24 Stunden]

Alle Visualisierungen werden jetzt jede Minute für maximal 30 Minuten aktualisiert, während die Browser-Registerkarte mit aktiviertem Bedienfeld „Echtzeit-Aktualisierung“ aktiv ist.

![Echtzeit-Aktualisierung](assets/real-time-refresh.gif)

Nach 30 Minuten oder sobald die Browser-Registerkarte inaktiv wird, wird **[!UICONTROL Umschalter &quot;]** aktualisieren“ automatisch deaktiviert und Echtzeit-Updates werden angehalten.
