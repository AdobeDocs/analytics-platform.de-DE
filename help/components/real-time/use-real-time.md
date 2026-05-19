---
description: Erfahren Sie, wie Sie Echtzeitberichte in Analysis Workspace verwenden.
title: Verwenden von Echtzeitberichten
feature: Real-time Reporting
role: User
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
autotag-review: '2026-05-19T08:47:15.932Z'
TQID: 'https://experienceleague.adobe.com/t20pdV4qS-FIBGrxOXAD5xAD58f4gtN74uheJ94sK4s'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: d1779026-aeed-458e-a1c7-839d4acac922
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 239
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

Es wird eine Meldung mit dem Zeitstempel der letzten Aktualisierung der Daten angezeigt. Beispiel: [!UICONTROL &#x200B; *Letzte Aktualisierung um 19:550 Uhr*].

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
