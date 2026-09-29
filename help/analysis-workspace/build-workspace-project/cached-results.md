---
title: Verwenden zwischengespeicherter Ergebnisse für schnelleres Laden in Analysis Workspace
description: Aktivieren Sie in Analysis Workspace eine Projekteinstellung, bei der Abfrageergebnisse für 12 Stunden zwischengespeichert werden, sodass Projekte sofort geladen werden. Sie können jederzeit aktualisieren, um die neuesten Daten anzuzeigen.
feature: Workspace Basics
hide: true
exl-id: 6d7b9d34-ec7e-45ec-98cc-0fd4cbfd43d3
role: User
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
    internal-label: Workspace basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 6bcbf10e6bff660f57f598f6cf75b43eb75c7db3
workflow-type: tm+mt
source-wordcount: '844'
ht-degree: 0%
---

# Verwenden zwischengespeicherter Ergebnisse in Workspace-Projekten

>[!CONTEXTUALHELP]
>id="project_cached_results"
>title="Verwenden zwischengespeicherter Ergebnisse für schnelleres Laden"
>abstract="Wenn diese Option aktiviert ist, werden Ergebnisse für 12 Stunden schneller geladen, nachdem ein Projekt zum ersten Mal von einer Benutzerin oder einem Benutzer geöffnet oder nach einem Zeitplan bereitgestellt wurde. Jeder, der das Projekt in dieser Zeit öffnet, sieht dieselben Ergebnisse, auch wenn weiterhin Daten im Hintergrund fließen. Um die neuesten Ergebnisse zu laden, aktualisieren Sie einzelne Bedienfelder oder das gesamte Projekt."

Sie können Analysis Workspace-Projekte so konfigurieren, dass zwischengespeicherte Ergebnisse für ein 12-Stunden-Fenster angezeigt werden, sodass die Ergebnisse für alle Personen sofort geladen werden können, die das Projekt nach dem ersten Laden öffnen.

Projekte können entweder von einem Benutzer, der das Projekt öffnet, oder über einen geplanten Projektversand geladen werden.

>[!NOTE]
>
>Nur die Abfrageergebnisse werden zwischengespeichert. Die zugrunde liegenden Ereignisdaten fließen weiterhin wie gewohnt in Customer Journey Analytics ein.
>
>Um die neuesten Daten anzuzeigen, bevor zwischengespeicherte Ergebnisse ablaufen, können Sie [die Ergebnisse manuell aktualisieren](#manually-refresh-results-on-cached-projects).

## Grundlegendes zu zwischengespeicherten Ergebnissen in einem Projekt

### Wenn Ergebnisse zwischengespeichert werden

Bei der ersten Ausführung des Projekts führt Analysis Workspace die Abfrage wie gewohnt aus und speichert die Ergebnisse für ein 12-Stunden-Fenster zwischen. Dies geschieht, wenn jemand das Projekt öffnet oder wenn das Projekt für einen geplanten Versand ausgeführt wird. Wenn beispielsweise die Bereitstellung eines Projekts für 6:00 Uhr geplant ist, werden die Ergebnisse bis 18:00 Uhr zwischengespeichert. Jeder, der das Projekt zwischen 6:00 und 18:00 Uhr öffnet, sieht, dass die Ergebnisse sofort geladen werden, auch die erste Person, die es öffnet.

Nach 12 Stunden laufen die zwischengespeicherten Ergebnisse ab. Die nächste Abfrage für das Projekt, unabhängig davon, ob ein Benutzer sie öffnet oder ein geplanter Versand ausgeführt wird, wird mit normaler Geschwindigkeit geladen und startet ein neues 12-Stunden-Fenster.

### Wer kann zwischengespeicherte Ergebnisse sehen?

Zwischengespeicherte Ergebnisse werden für alle freigegeben, die Zugriff auf das Projekt und die im Projekt verwendeten Datenansichten haben.

### Welche Ergebnisse zwischengespeichert werden

Analysis Workspace speichert jede ausgeführte Abfrage zwischen, jedoch nicht jede mögliche Version eines Projekts. Wenn jemand die Abfrage ändert, z. B. indem er ein Element aus einem Dropdown-Menü des Bedienfelds auswählt oder ein Segment anwendet, führt Analysis Workspace eine neue Abfrage aus. Die neue Abfrage wird beim ersten Mal mit normaler Geschwindigkeit geladen. Danach werden die Ergebnisse ebenfalls zwischengespeichert.

Durch das Caching einer neuen Abfrage werden bereits zwischengespeicherte Ergebnisse nicht überschrieben oder ungültig gemacht. Die ursprüngliche Projektansicht wird zusammen mit anderen Varianten, die ausgeführt wurden, zwischengespeichert.

>[!BEGINSHADEBOX]

**Beispielszenario**

Angenommen, ein Projekt zur Leistung der globalen Kampagne umfasst Segmente für verschiedene Regionen und ist für die Bereitstellung um 6:00 Uhr geplant:

| Zeit | Aktion | Belastungsgeschwindigkeit |
| --- | --- | --- |
| 6:00 Uhr | Geplante Projektbereitstellung | Normal (Ergebnisse werden für die zukünftige Verwendung zwischengespeichert) |
| 07:06 | Benutzer A öffnet das Projekt | Schnell |
| 07:06 | Benutzer A wendet das Amerikas-Segment an | Normal (Ergebnisse werden für die zukünftige Verwendung zwischengespeichert) |
| 08:01 | Benutzer B öffnet das Projekt | Schnell |
| 08:01 | Benutzer B wendet das Amerikas-Segment an | Schnell |
| 08:01 | Benutzer B wendet das EMEA-Segment an | Normal (Ergebnisse werden für die zukünftige Verwendung zwischengespeichert) |

>[!ENDSHADEBOX]

## Aktivieren zwischengespeicherter Ergebnisse für ein Projekt

Jeder, der Projekteinstellungen aktualisieren kann, kann zwischengespeicherte Ergebnisse aktivieren. Dazu gehören der Projektbesitzer und alle anderen, die die Rolle **[!UICONTROL Original bearbeiten]** für das Projekt besitzen. Weitere Informationen zu Projektrollen finden Sie unter [Freigeben einer bestimmten Projektrolle](/help/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role).

Im Workspace-Projekt, in dem Sie zwischengespeicherte Ergebnisse für ein schnelleres Laden aktivieren möchten:

1. Navigieren Sie **[!UICONTROL Projekte]** > **[!UICONTROL Projektinformationen und -einstellungen]**.
1. Wählen Sie **[!UICONTROL Zwischengespeicherte Ergebnisse für schnelleres Laden verwenden]**.
1. Wählen Sie **[!UICONTROL Speichern]** aus.

## Anzeigen von Daten-Zeitstempeln für zwischengespeicherte Projekte

Wenn ein Projekt so konfiguriert ist, dass zwischengespeicherte Ergebnisse verwendet werden, wird oben im Projekt ein Zeitstempel angezeigt, der anzeigt, wann die Ergebnisse zwischengespeichert wurden:

* **[!UICONTROL Anzeigen von Daten &#x200B;]Datum [_Uhrzeit_]**: Alle Bedienfelder im Projekt zeigen zwischengespeicherte Ergebnisse aus dem angezeigten Datum und der angezeigten Uhrzeit an.
* **[!UICONTROL Anzeigen einiger Daten &#x200B;]Datum [_Uhrzeit_]**: Einige Bedienfelder zeigen zwischengespeicherte Ergebnisse aus dem angezeigten Datum und der angezeigten Uhrzeit an, während andere kürzlich aktualisiert wurden.

In Bedienfeldern wird außerdem ein Zeitstempel angezeigt, der angibt, wann die Ergebnisse zwischengespeichert wurden:

* **[!UICONTROL Anzeige von Daten &#x200B;]Datum [_Uhrzeit_]**: Das Bedienfeld zeigt zwischengespeicherte Ergebnisse aus dem angezeigten Datum und der angezeigten Uhrzeit an.

## Ergebnisse für zwischengespeicherte Projekte manuell aktualisieren

Sie können die Ergebnisse eines Projekts jederzeit während des 12-Stunden-Fensters manuell aktualisieren, um die neuesten Daten anzuzeigen. Wenn Sie das gesamte Projekt aktualisieren, beginnt ein neues 12-Stunden-Fenster, und alle, die das Projekt während dieses Fensters öffnen, sehen die aktualisierten Ergebnisse.

In dem Workspace-Projekt, in dem Sie die neuesten Daten anzeigen möchten, können Sie die Ergebnisse für das gesamte Projekt oder für ein einzelnes Bedienfeld aktualisieren.

### Ergebnisse für das gesamte Projekt aktualisieren

So laden Sie die neuesten Ergebnisse für alle Bereiche und starten ein neues 12-Stunden-Fenster:

1. Wählen **[!UICONTROL oben]** Projekt neben dem Zeitstempel des Projekts die Option „Aktualisieren“ aus.

### Ergebnisse für ein einzelnes Bedienfeld aktualisieren

>[!NOTE]
>
>Diese Option ist während der Alpha-Phase der Veröffentlichung nicht verfügbar.

So laden Sie die neuesten Ergebnisse nur für einen einzelnen Bereich:

1. Wählen **[!UICONTROL Aktualisieren]** neben dem Zeitstempel eines Bedienfelds aus.

