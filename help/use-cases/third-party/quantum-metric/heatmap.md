---
title: Verwenden von Quantum Metric-Heatmaps mit Customer Journey Analytics
description: Die Interaktion auf Seitenebene besser verstehen und Seiten basierend auf dem Verbraucherverhalten mithilfe von Quantum Metric-Heatmap-Daten optimieren.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: d861135f-42a4-45ac-8b11-41f151bfce92
source-git-commit: a0f82948895f3eac86cf00df1dec8abc2f723fc2
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 1%

---

# Verwenden von Quantum Metric-Heatmaps mit Customer Journey Analytics

Durch die Verknüpfung von Quantum Metric Heatmapping mit CJA-Daten können Sie die Interaktion auf Seitenebene besser verstehen und Seiten basierend auf dem Verbraucherverhalten optimieren. Workspace kann verwendet werden, um Verbraucherbenutzerflüsse zu verstehen und zu sehen, welchen Pfaden Verbraucherinnen und Verbraucher von einer Seite zur nächsten folgen. Anschließend können Sie auf Hyperlink-Seiten-URLs klicken, um zu visualisieren, wie Heatmap-Benutzer mit dem Inhalt interagieren.

Die Tabelle gibt alle Sitzungen in diesem Segment zurück, und Sie können auf eine beliebige Sitzung klicken, um sie in QM weiter zu erkunden.  Weitere Informationen zu Quantum Metric Session Replay finden Sie unter https://www.quantummetric.com/platform/session-replay

## Voraussetzungen

In diesem Anwendungsfall müssen Sie die Sitzungs-ID der Quantum-Metrik zusammen mit dem Rest Ihrer Implementierung erfassen. Unter [Erfassen von Quantum Metric-Sitzungs-IDs in Customer Journey Analytics](collect-session-id.md) erfahren Sie, wie Sie Ihre Implementierung ändern können.

Sie müssen Anspruch auf das **UX Ops**-Paket von Quantum Metric haben, um auf die Heatmap-Funktionen von Quantum Metric zugreifen zu können.

## Erstellen Sie eine Freiformtabelle in Workspace und konfigurieren Sie sie so, dass Sitzungs-ID-Werte direkte Links zu Quantum Metric sind.

1. Melden Sie sich bei &quot;[.adobe.com“ ](https://experience.adobe.com).
1. Navigieren Sie zu Customer Journey Analytics und wählen Sie **[!UICONTROL Workspace]** im oberen Menü.
1. Wählen Sie ein vorhandenes Projekt aus oder erstellen Sie ein Projekt.
1. Erstellen Sie eine [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Ziehen Sie die Dimension Seiten-URL auf die Workspace-Arbeitsfläche.
1. Klicken Sie mit der rechten Maustaste auf die Spaltenüberschrift der Dimension und wählen Sie **[!UICONTROL Hyperlinks für alle Dimensionselemente erstellen]** aus.
1. Wählen Sie **[!UICONTROL Benutzerdefinierte URL erstellen]** aus.
1. Fügen Sie die folgende URL-Struktur ein:

   ```
   $value?qm-visible=true
   ```

1. Klicken Sie auf **[!UICONTROL Erstellen]**.

1. Klicken Sie auf Erstellen und testen Sie dann einen der Links, um zu sehen, ob er in der URL geöffnet wird, während die QM-Erweiterung geöffnet wird. Hinweis - Es wird in einer separaten Registerkarte geöffnet, sodass Sie Ihre Arbeit nicht verlieren.


## Anzeigen von Heatmaps durch Klicken auf Links in Customer Journey Analytics

Nachdem Sie eine Seite gefunden haben, für die Sie Heatmapping erforschen möchten, können Sie sie auf das Bedienfeld anwenden, in dem sich Ihre URL befindet. Die Tabelle gibt eine URL zurück, mit der Sie Heatmaps für die betreffende Seite, Bildlauftiefe und Schlüsselzonen für die Interaktion untersuchen können.  Weitere Informationen zu Quantum Metric Heatmaps finden Sie unter https://www.quantummetric.com/platform/interaction-heatmaps


