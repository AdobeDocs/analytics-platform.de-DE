---
title: Verwenden zwischengespeicherter Ergebnisse für schnelleres Laden in Analysis Workspace
description: Aktivieren Sie eine Projekteinstellung in Analysis Workspace, bei der Ergebnisse 12 Stunden lang zwischengespeichert werden, sodass Projekte sofort geladen werden. Sie können jederzeit aktualisieren, um die neuesten Daten anzuzeigen.
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
source-git-commit: 32dfb7790f57293ea297bdcb8319c3d3b187a2ae
workflow-type: tm+mt
source-wordcount: '1336'
ht-degree: 0%
---

# Verwenden zwischengespeicherter Ergebnisse in Workspace-Projekten

>[!CONTEXTUALHELP]
>id="project_cached_results"
>title="Verwenden zwischengespeicherter Ergebnisse für schnelleres Laden"
>abstract="Wenn diese Option aktiviert ist, werden Ergebnisse sofort 12 Stunden lang geladen, nachdem ein Projekt zum ersten Mal von einer Benutzerin oder einem Benutzer geöffnet oder nach einem Zeitplan bereitgestellt wurde. Jeder, der das Projekt in dieser Zeit öffnet, sieht dieselben Ergebnisse, auch wenn weiterhin Daten im Hintergrund fließen. Um die neuesten Ergebnisse zu laden, aktualisieren Sie einzelne Bedienfelder oder das gesamte Projekt."

{{release-limited-testing}}

Sie können Analysis Workspace-Projekte so konfigurieren, dass zwischengespeicherte Ergebnisse für ein 12-Stunden-Fenster angezeigt werden, sodass die Ergebnisse für alle Personen sofort geladen werden können, die das Projekt nach dem ersten Laden öffnen.

Projekte können entweder von einem Benutzer, der das Projekt öffnet, oder über einen geplanten Projektversand geladen werden.

## Grundlegendes zu zwischengespeicherten Ergebnissen in einem Projekt

### Wenn Ergebnisse zwischengespeichert werden

Beim ersten Laden des Projekts werden die Ergebnisse mit normaler Geschwindigkeit geladen und Analysis Workspace speichert sie für ein 12-Stunden-Fenster zwischen. Dies geschieht, wenn:

* Jemand öffnet das Projekt

* Das Projekt wird für einen geplanten Versand ausgeführt

Wenn beispielsweise die Bereitstellung eines Projekts für 6:00 Uhr geplant ist, werden die Ergebnisse bis 18:00 Uhr zwischengespeichert. Jeder, der das Projekt zwischen 6:00 und 18:00 Uhr öffnet, sieht, dass die Ergebnisse sofort geladen werden, auch die erste Person, die es öffnet.

Nach 12 Stunden laufen die zwischengespeicherten Ergebnisse ab. Beim nächsten Laden des Projekts, unabhängig davon, ob es ein Benutzer öffnet oder ein geplanter Versand ausgeführt wird, werden die Ergebnisse mit normaler Geschwindigkeit geladen und ein neues 12-Stunden-Fenster wird gestartet.

### Welche Ergebnisse zwischengespeichert werden

#### Das Projekt wird zunächst mit seiner ursprünglichen Konfiguration zwischengespeichert

Analysis Workspace speichert die Ergebnisse des Projekts in der ursprünglich konfigurierten Form zwischen, einschließlich der ausgewählten Datenansichten, angewendeten Segmente, Datumsbereiche, Dropdown-Auswahlfelder für Bedienfelder usw. Jeder, der das Projekt öffnet, sieht diese zwischengespeicherten Ergebnisse.

Wenn jemand die Projektkonfiguration ändert, während er das zwischengespeicherte Projekt anzeigt, werden die Ergebnisse normal geladen (nicht sofort), und [eine neue Projektvariante wird zwischengespeichert](#project-variations-are-cached-as-the-project-is-modified).

#### Projektvarianten werden zwischengespeichert, wenn das Projekt geändert wird

Eine neue Variante des Projekts wird erstellt, wenn jemand seine ursprüngliche Konfiguration ändert, z. B. durch Auswahl eines Elements aus einem Dropdown-Menü des Bedienfelds, Anwenden eines Segments, Ändern eines Datumsbereichs oder Ändern der ausgewählten Datenansicht.

Beim ersten Mal wird eine neue Variante mit normaler Geschwindigkeit geladen. Danach werden die Ergebnisse ebenfalls zwischengespeichert, sodass jeder, der dieselbe Variante lädt, die Ergebnisse sofort sieht.

Beachten Sie Folgendes:

* Analysis Workspace speichert jede Variante eines Projekts zwischen, das jemand lädt. Es werden nicht alle möglichen Varianten eines Projekts zwischengespeichert.

* Durch das Zwischenspeichern einer neuen Variante werden bereits zwischengespeicherte Ergebnisse nicht überschrieben oder ungültig gemacht. Das ursprüngliche Projekt wird zusammen mit anderen Varianten, die geladen wurden, zwischengespeichert.

>[!BEGINSHADEBOX]

**Beispielszenario**

Angenommen, ein Projekt zur Leistung der globalen Kampagne umfasst Segmente für verschiedene Regionen und ist für die Bereitstellung um 6:00 Uhr geplant:

| Zeit | Aktion | Belastungsgeschwindigkeit |
| --- | --- | --- |
| 6:00 Uhr | Geplante Projektbereitstellung | Normal (Ergebnisse werden für die zukünftige Verwendung zwischengespeichert) |
| 07:06 | Benutzer A öffnet das Projekt | Sofort |
| 07:07 | Benutzer A wendet das Amerikas-Segment an | Normal (Ergebnisse werden für die zukünftige Verwendung zwischengespeichert) |
| 08:01 | Benutzer B öffnet das Projekt | Sofort |
| 08:05 | Benutzer B wendet das Amerikas-Segment an | Sofort |
| 08:12 | Benutzer B wendet das EMEA-Segment an | Normal (Ergebnisse werden für die zukünftige Verwendung zwischengespeichert) |

>[!ENDSHADEBOX]

### Änderungen, die dazu führen, dass zwischengespeicherte Ergebnisse beim nächsten Laden des Projekts aktualisiert werden

Die folgenden Änderungen an der zugrunde liegenden Konfiguration eines Projekts führen dazu, dass Analysis Workspace die Ergebnisse aktualisiert, wenn das Projekt das nächste Mal geöffnet wird, auch wenn das 12-Stunden-Fenster noch nicht abgelaufen ist:

* Änderungen an einer Komponente in der Datenansicht, z. B. das Bearbeiten einer Dimension oder der [&#x200B; (Komponenteneinstellungen](/help/data-views/component-settings/overview.md)

* Änderungen an einem [&#x200B; Feld](/help/data-views/derived-fields/derived-fields.md)

* Änderungen an einer im Projekt verwendeten Segmentdefinition

Die Ergebnisse werden mit normaler Geschwindigkeit geladen und dann zwischengespeichert, wodurch ein neues 12-Stunden-Fenster gestartet wird.

### Wer zwischengespeicherte Ergebnisse sieht

Zwischengespeicherte Ergebnisse werden standardmäßig für alle Benutzer angezeigt, die:

* Hat Zugriff auf das Projekt

* Hat Zugriff auf die im Projekt verwendeten Datenansichten

* Lädt eine Variante des Projekts, die bereits zwischengespeichert wird, z. B. eine Variante mit denselben Segmenten oder Dropdown-Auswahlfeldern (weitere Informationen finden Sie unter [Welche Ergebnisse werden zwischengespeichert](#what-results-are-cached))

Wenn Sie zwischengespeicherte Ergebnisse anzeigen, können Sie die neuesten Daten anzeigen, indem Sie [die Ergebnisse manuell aktualisieren](#manually-refresh-results-on-cached-projects).

### Wann zwischengespeicherte Ergebnisse für ein Projekt deaktiviert bleiben sollen

Einige Projekte hängen von den Ergebnissen ab, damit sie bei jedem Öffnen die neuesten Daten widerspiegeln. Dies ist häufig bei Projekten der Fall, die stark auf Daten vom selben Tag, verspätet eintreffende Daten oder [Lookup-Datensätze](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md) angewiesen sind, die häufig aktualisiert werden.

Lassen Sie die zwischengespeicherten Ergebnisse in Ihrem Projekt deaktiviert, wenn die meisten Personen, die auf das Projekt zugreifen, Folgendes anzeigen müssen:

* **Daten des aktuellen Tages**

  Wenn ein Projekt um 7:00 Uhr zwischengespeichert wird, enthalten die Ergebnisse keine Daten, die nach 7:00 Uhr eingehen, bis die zwischengespeicherten Ergebnisse um 19:00 Uhr ablaufen.

* **Verspätete Daten sofort**

  Verspätet eintreffende Daten enthalten Zeitstempel aus einem früheren Zeitraum, treffen jedoch nach Ablauf dieses Zeitraums ein. Beispielsweise können [Batch-Daten](/help/data-ingestion/batch.md) von einem Callcenter am nächsten Tag hochgeladen werden oder eine Mobile App sendet Ereignisse, die im Offline-Modus gespeichert wurden. Zwischengespeicherte Ergebnisse enthalten diese Daten erst, wenn sie ablaufen.

* **Aktualisierte Suchwerte**

  Zwischengespeicherte Ergebnisse zeigen die vorherigen Suchwerte, z. B. alte Produktnamen, bis zu ihrem Ablauf an.

>[!NOTE]
>
>Wenn diese Anforderungen nur gelegentlich auftreten, aktivieren Sie zwischengespeicherte Ergebnisse und [aktualisieren Sie das Projekt manuell](#manually-refresh-results-on-cached-projects) wenn Sie die neuesten Daten benötigen.

## Aktivieren zwischengespeicherter Ergebnisse für ein Projekt

Jeder, der Projekteinstellungen aktualisieren kann, kann zwischengespeicherte Ergebnisse aktivieren. Dazu gehören der Projektbesitzer und alle anderen, die die Rolle **[!UICONTROL Original bearbeiten]** für das Projekt besitzen. Weitere Informationen zu Projektrollen finden Sie unter [Freigeben einer bestimmten Projektrolle](/help/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role).

>[!IMPORTANT]
>
>Zwischengespeicherte Ergebnisse eignen sich möglicherweise nicht gut, wenn Sie aktuelle Daten, verspätet eintreffende Daten oder aktualisierte Suchwerte sofort anzeigen müssen. Bevor Sie diese Einstellung aktivieren, überprüfen Sie [Wann können zwischengespeicherte Ergebnisse für ein Projekt deaktiviert bleiben](#when-to-leave-cached-results-disabled-on-a-project).

Im Workspace-Projekt, in dem Sie zwischengespeicherte Ergebnisse für ein schnelleres Laden aktivieren möchten:

1. Navigieren Sie **[!UICONTROL Projekte]** > **[!UICONTROL Projektinformationen und -einstellungen]**.

1. Wählen Sie **[!UICONTROL Zwischengespeicherte Ergebnisse für schnelleres Laden verwenden]**.

1. Wählen Sie **[!UICONTROL Speichern]** aus.

## Anzeigen, wenn zwischengespeicherte Ergebnisse in einem Projekt angezeigt werden

Ein Zeitstempel wird oben im Projekt angezeigt, wenn zwischengespeicherte Ergebnisse angezeigt werden. Der Zeitstempel gibt an, ob alle Ergebnisse zwischengespeichert werden oder nur einige Ergebnisse:

* **[!UICONTROL Anzeige der Ergebnisse ab] [_Datum und Uhrzeit_]**: Alle Bedienfelder im Projekt zeigen zwischengespeicherte Ergebnisse aus dem angezeigten Datum und der angezeigten Uhrzeit.

* **[!UICONTROL Anzeige einiger Ergebnisse ab] [_Datum und Uhrzeit_]**: Einige Bedienfelder zeigen zwischengespeicherte Ergebnisse aus dem angezeigten Datum und der angezeigten Uhrzeit an, während andere kürzlich aktualisiert wurden.

![Zeitstempel eines zwischengespeicherten Projekts](assets/project-cache-timestamp.png)

In Bedienfeldern wird außerdem ein Zeitstempel angezeigt, der angibt, wann die Ergebnisse zwischengespeichert wurden:

* **[!UICONTROL Anzeige der Ergebnisse ab] [_Datum und Uhrzeit_]**: Das Bedienfeld zeigt zwischengespeicherte Ergebnisse aus dem angezeigten Datum und der angezeigten Uhrzeit an.

  >[!NOTE]
  >
  >Diese Option ist während der Alpha-Phase der Veröffentlichung nicht verfügbar.

## Ergebnisse für zwischengespeicherte Projekte manuell aktualisieren

Nur die im Projekt angezeigten Ergebnisse werden zwischengespeichert. Die zugrunde liegenden Ereignisdaten fließen weiterhin wie gewohnt in Customer Journey Analytics ein.

Um die neuesten Daten anzuzeigen, bevor zwischengespeicherte Ergebnisse ablaufen, können Sie die Ergebnisse für ein Projekt jederzeit während des 12-Stunden-Fensters manuell aktualisieren. Wenn Sie das gesamte Projekt aktualisieren, beginnt ein neues 12-Stunden-Fenster, und alle, die das Projekt während dieses Fensters öffnen, sehen die aktualisierten Ergebnisse.

In dem Workspace-Projekt, in dem Sie die neuesten Daten anzeigen möchten, können Sie die Ergebnisse für das gesamte Projekt oder für ein einzelnes Bedienfeld aktualisieren.

### Ergebnisse für das gesamte Projekt aktualisieren

So laden Sie die neuesten Ergebnisse für alle Bereiche und starten ein neues 12-Stunden-Fenster:

1. Wählen Sie **[!UICONTROL Symbol]** Aktualisieren![Aktualisieren](/help/assets/icons/Refresh.svg) oben im Projekt neben dem Zeitstempel des Projekts aus.

### Ergebnisse für ein einzelnes Bedienfeld aktualisieren

>[!NOTE]
>
>Diese Option ist während der Alpha-Phase der Veröffentlichung nicht verfügbar.

So laden Sie die neuesten Ergebnisse nur für einen einzelnen Bereich:

1. Wählen Sie das Symbol **[!UICONTROL Aktualisieren]** ![Aktualisieren](/help/assets/icons/Refresh.svg) neben dem Zeitstempel eines Bedienfelds aus.

