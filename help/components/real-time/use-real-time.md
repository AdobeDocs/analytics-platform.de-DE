---
description: Erfahren Sie, wie Sie Echtzeitberichte in Analysis Workspace verwenden.
title: Verwenden von Echtzeitberichten
feature: Real-time Reporting
role: User
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
source-git-commit: 0e5a64e78e5a471f8b7c9fc32fdbae2b2e70230a
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 12%

---

# Verwenden von Echtzeit-Reporting {#use-real-time-reporting}

>[!CONTEXTUALHELP]
>id="workspace_panel_realtime_refresh"
>title="Echtzeitaktualisierung"
>abstract="Aktivieren Sie diese Option, um Daten und Visualisierungen in diesem Panel in Echtzeit zu aktualisieren."

Um Echtzeitberichte zu verwenden, aktivieren Sie den Umschalter **[!UICONTROL Echtzeit-Aktualisierung]** in einem der folgenden Bereiche in Ihrem Workspace-Projekt:

* [Leeres Panel](/help/analysis-workspace/c-panels/blank-panel.md)
* [Freiform](/help/analysis-workspace/c-panels/freeform-panel.md)
* [Attribution](/help/analysis-workspace/c-panels/attribution.md)
* [Nächstes oder vorheriges Objekt](/help/analysis-workspace/c-panels/next-previous.md)

Es wird eine Meldung mit dem Zeitstempel der letzten Aktualisierung der Daten angezeigt. Beispiel: [!UICONTROL  *Letzte Aktualisierung um 19:550 Uhr*].

Wählen Sie aus dem Dropdown-Menü den Echtzeitzeitraum aus, über den Sie einen Bericht erstellen möchten. Verfügbare Optionen sind:

* [!UICONTROL Letzte 15 Minuten]
* [!UICONTROL Letzte 30 Minuten]
* [!UICONTROL Letzte Stunde]
* [!UICONTROL Letzte 8 Stunden]
* [!UICONTROL Letzte 24 Stunden]

Alle Visualisierungen im Bedienfeld werden jetzt jede Minute für maximal 30 Minuten aktualisiert, während die Browser-Registerkarte mit dem Bedienfeld „Echtzeit-Aktualisierung aktiviert“ aktiv ist.

Unten finden Sie ein Beispiel für einen Schnappschuss eines **[!UICONTROL Echtzeitberichts]** der die **[!UICONTROL Gesamtumsatz/Stunde]** Balkenvisualisierung und **[!UICONTROL Gesamtumsatz/Stunde]** Freiformtabelle aktualisiert, wenn die Zeit von **[!UICONTROL *06:26pm*]** bis **[!UICONTROL *06:27 PM *]**.

![Echtzeit-Aktualisierung](assets/real-time-refresh.gif)

Nach 30 Minuten oder sobald die Browser-Registerkarte inaktiv wird, wird der Umschalter **[!UICONTROL Echtzeit-]**) automatisch deaktiviert und Echtzeit-Updates werden angehalten.

Sobald der Umschalter Aktualisierung in Echtzeit deaktiviert ist, kehrt das Bedienfeld (und alle darin enthaltenen Visualisierungen) zurück zu [Verwenden der standardmäßigen Berichtsdaten und -funktionen von Customer Journey Analytics](real-time.md#how-it-works).
