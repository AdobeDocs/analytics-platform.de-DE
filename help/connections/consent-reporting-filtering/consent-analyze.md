---
title: Analysieren von Einverständnisrichtliniendaten in Customer Journey Analytics
description: Erfahren Sie, wie Sie Dimensionen, Metriken und Vorlagen von Einverständnisrichtlinien verwenden, um Berichte über die Zugehörigkeit zu einer Besucherzustimmung in Analysis Workspace zu erstellen.
solution: Customer Journey Analytics
feature: Privacy
role: Admin, User
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 385
ht-degree: 2%

---

# Analysieren von Einverständnisrichtliniendaten

Sie können Daten zu Einverständnisrichtlinien aus Experience Platform-Profildatensätzen in eine Customer Journey Analytics-Verbindung aufnehmen.

Nachdem Sie [Konfiguration für Einverständnisberichte und -filter erstellt haben](/help/connections/consent-reporting-filtering/consent-configure.md) werden die Einverständnisrichtlinien-Daten als neue Komponenten in den Datenansichten unter der konfigurierten Verbindung verfügbar. Sie können diese Komponenten überall in Analysis Workspace verwenden, wenn Sie Zugriff auf eine Datenansicht haben, in der sie vorhanden sind.

## Komponenten der Einverständnisrichtlinie

Einverständnisberichte fügen den Datenansichten die folgenden Komponenten hinzu. Diese Komponenten lesen aus dem Feld `consentPoliciesIDMap` in Ihrem Profildatensatz, und Richtliniennamen und -beschreibungen stammen aus dem Einverständnisrichtlinien-Suchdatensatz.

### Dimensionen

| Dimension | Beschreibung |
|---------|----------|
| **[!UICONTROL Einverständnisrichtlinien-ID]** | Die Kennung einer Einverständnisrichtlinie, der ein Besucher entspricht. |
| **[!UICONTROL Richtlinienname]** | Der Anzeigename der Einverständnisrichtlinie aus dem Einverständnisrichtlinien-Lookup-Datensatz. |
| **[!UICONTROL Richtlinienbeschreibung]** | Die Beschreibung der Einverständnisrichtlinie aus dem Einverständnisrichtlinien-Lookup-Datensatz. |

### Metriken

| Metrik | Beschreibung |
|---------|----------|
| **[!UICONTROL Besucher mit Einverständnis]** | Die Anzahl der Besucherinnen und Besucher, die einer Einverständnisrichtlinie entsprechen. |
| **[!UICONTROL Ereignisse mit Einverständnis]** | Die Anzahl der Ereignisse, die Besuchern zugeordnet sind, die einer Einverständnisrichtlinie entsprechen. |
| **[!UICONTROL Eindeutige Einverständnisrichtlinien]** | Die Anzahl der verschiedenen Einverständnisrichtlinien, die im Reporting-Fenster dargestellt werden. |

### Abgeleitetes Feld

Ein abgeleitetes Feld verweist auf das `consentPoliciesIDMap` Feld, um Einverständnisrichtlinien-IDs zu extrahieren. Sie können dieses abgeleitete Feld als Grundlage für zusätzliche einverständnisbasierte Dimensionen verwenden. Weitere Informationen zu abgeleiteten Feldern finden Sie unter [Abgeleitete Felder](/help/data-views/derived-fields/derived-fields.md).

## Verwenden von Einverständnisrichtlinien-Komponenten in Analysis Workspace

So berichten Sie über die Zugehörigkeit zu einer Einverständnisrichtlinie:

1. Öffnen Sie in Analysis Workspace ein Projekt, das eine Datenansicht verwendet, die für das Einverständnisbericht konfiguriert ist.

1. Ziehen Sie im Bedienfeld Komponenten eine Einverständnisrichtlinien-Dimension wie **[!UICONTROL Richtlinienname]** in eine Freiformtabelle.

1. Fügen Sie der Tabelle eine Einverständnismetrik wie **[!UICONTROL Besucher mit]**&quot; hinzu.

1. Schlüsseln Sie die Ergebnisse nach einer anderen Dimension auf, z. B. Seite oder Kanal, um zu verstehen, wie sich einvernehmliche Besucherinnen und Besucher verhalten.

## Verwenden der Vorlage für die Einverständnisrichtlinien-Analyse

Wenn eine Datenansicht für das Reporting zu Einverständnissen konfiguriert ist, stellt Customer Journey Analytics automatisch eine Vorlage für die Einverständnisrichtlinien-Analyse in Analysis Workspace zur Verfügung. Diese Vorlage bietet einen Ausgangspunkt für Berichte zur Mitgliedschaft in der Einverständnisrichtlinie für Besucher.

Informationen zum Zugriff auf Vorlagen finden Sie unter [Zugriff auf Vorlagen und deren Ausführung](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template).
