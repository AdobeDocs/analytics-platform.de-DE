---
description: Erfahren Sie, wie Sie Echtzeitberichte in Analysis Workspace verwenden.
title: Verwenden von Echtzeitberichten
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
source-git-commit: 82aefce30834d6400d338896dc1968e37596393e
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 9%

---

# Verwenden von Echtzeitberichten

{{release-limited-testing}}

Um Echtzeitberichte zu verwenden, aktivieren Sie den Umschalter **[!UICONTROL Echtzeit-Aktualisierung]** in einem der folgenden Bereiche in Ihrem Workspace-Projekt:



* [Leeres Bedienfeld](/help/analysis-workspace/c-panels/blank-panel.md)
* [Freiform](/help/analysis-workspace/c-panels/freeform-panel.md)
* [Attribution](/help/analysis-workspace/c-panels/attribution.md)
* [Nächstes oder vorheriges Objekt](/help/analysis-workspace/c-panels/next-previous.md)
* [Quick Insights](/help/analysis-workspace/c-panels/quickinsight.md)

Es wird eine Meldung mit dem Zeitstempel der letzten Aktualisierung der Daten angezeigt. Beispiel: [!UICONTROL  *Letzte Aktualisierung um 19:55*].

Wählen Sie aus dem Dropdown-Menü den Echtzeitzeitraum aus, über den Sie einen Bericht erstellen möchten. Verfügbare Optionen sind:

* [!UICONTROL Letzte 15 Minuten]
* [!UICONTROL Letzte 30 Minuten]
* [!UICONTROL Letzte Stunde]
* [!UICONTROL Letzte 8 Stunden]
* [!UICONTROL Letzte 24 Stunden]

Alle Visualisierungen im Bedienfeld werden jetzt jede Minute für maximal 30 Minuten aktualisiert, während die Browser-Registerkarte mit dem Bedienfeld „Echtzeit-Aktualisierung aktiviert“ aktiv ist.

![Echtzeit-Aktualisierung](assets/real-time-refresh.gif)

Nach 30 Minuten oder sobald die Browser-Registerkarte inaktiv wird, wird **[!UICONTROL Umschalter &quot;]** aktualisieren“ automatisch deaktiviert und Echtzeit-Updates werden angehalten.
