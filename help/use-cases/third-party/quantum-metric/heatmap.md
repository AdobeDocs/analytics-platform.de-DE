---
title: Verwenden von Quantum Metric-Heatmaps mit Customer Journey Analytics
description: Die Interaktion auf Seitenebene besser verstehen und Seiten basierend auf dem Verbraucherverhalten mithilfe von Quantum Metric-Heatmap-Daten optimieren.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: d861135f-42a4-45ac-8b11-41f151bfce92
source-git-commit: 25a2c549c27918f80202bde4cd30e305f4a295f3
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 1%

---

# Verwenden von Quantum Metric-Heatmaps mit Customer Journey Analytics

Durch die Verknüpfung von Quantum Metric Heatmapping mit CJA-Daten können Sie die Interaktion auf Seitenebene besser verstehen und Seiten basierend auf dem Verbraucherverhalten optimieren. Workspace kann verwendet werden, um Verbraucherbenutzerflüsse zu verstehen und zu sehen, welchen Pfaden Verbraucherinnen und Verbraucher von einer Seite zur nächsten folgen. Anschließend können Sie auf Hyperlink-Seiten-URLs klicken, um zu visualisieren, wie Heatmap-Benutzer mit dem Inhalt interagieren. Durch die Verknüpfung von Quantum Metric Heatmapping mit CJA können Sie nun Interaktionen auf Seitenebene mit Geschäftsergebnissen verknüpfen und Ihre Analyse auf die nächste Ebene bringen.

Die Tabelle gibt alle Sitzungen in diesem Segment zurück, und Sie können auf eine beliebige Sitzung klicken, um sie in QM weiter zu erkunden.  Weitere Informationen zu Quantum Metric Session Replay finden Sie unter https://www.quantummetric.com/platform/session-replay

## Voraussetzungen

Sie müssen Anspruch auf das **UX Ops**-Paket von Quantum Metric haben, um auf die Heatmap-Funktionen von Quantum Metric zugreifen zu können.

## Schritt 1: Erstellen Sie eine Freiformtabelle in Workspace und konfigurieren Sie sie so, dass Sitzungs-ID-Werte direkte Links zur Quantum-Metrik sind.

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
1. Testen Sie einen der Links, um zu sehen, ob er in der URL geöffnet wird, wobei die Quantum Metric-Erweiterung sichtbar ist. Diese Links werden in einer neuen Registerkarte geöffnet, sodass Ihr Workspace-Projekt geöffnet bleibt.

## Schritt 2: Heatmaps durch Anklicken von Links in Customer Journey Analytics anzeigen

Nachdem Sie eine Seite gefunden haben, auf der Sie Heatmapping erforschen möchten, können Sie sie auf das gewünschte Bedienfeld anwenden. Die Tabelle gibt eine URL zurück, mit der Sie Heatmaps, Bildlauftiefen und Schlüsselzonen für die Interaktion mit Quantum Metric untersuchen können. Weitere Informationen finden [ unter „Quantum Metric ](https://www.quantummetric.com/platform/interaction-heatmaps) - Produktübersicht“. Sie können sich auch an Ihren Kundenbetreuer von Quantum Metric wenden oder eine Anfrage über das [Quantum Metric Customer Request Portal) ](https://community.quantummetric.com/s/public-support-page).
