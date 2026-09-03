---
title: Verwenden von Quantum Metric-Heatmaps mit Customer Journey Analytics
description: Die Interaktion auf Seitenebene besser verstehen und Seiten basierend auf dem Verbraucherverhalten mithilfe von Quantum Metric-Heatmap-Daten optimieren.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
exl-id: d861135f-42a4-45ac-8b11-41f151bfce92
autotag-review: '2026-05-19T09:50:41.180Z'
TQID: 'https://experienceleague.adobe.com/EvPGghY3E7eoiJb6TcWnaOhneS6oQJj4bcwU3K2v3Ng'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: e1bd5a34-b16e-477b-84cc-247fa0793f4b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 366
ht-degree: 1%

---

# Verwenden von Quantum Metric-Heatmaps mit Customer Journey Analytics

Durch die Verknüpfung von Quantum Metric Heatmapping mit CJA-Daten können Sie die Interaktion auf Seitenebene besser verstehen und Seiten basierend auf dem Verbraucherverhalten optimieren. Workspace kann verwendet werden, um Verbraucherbenutzerflüsse zu verstehen und zu sehen, welchen Pfaden Verbraucherinnen und Verbraucher von einer Seite zur nächsten folgen. Anschließend können Sie auf Hyperlink-Seiten-URLs klicken, um zu visualisieren, wie Heatmap-Benutzer mit dem Inhalt interagieren. Durch die Verknüpfung von Quantum Metric Heatmapping mit CJA können Sie nun Interaktionen auf Seitenebene mit Geschäftsergebnissen verknüpfen und Ihre Analyse auf die nächste Ebene bringen.

Die Tabelle gibt alle Sitzungen in diesem Segment zurück, und Sie können auf eine beliebige Sitzung klicken, um sie in QM weiter zu erkunden.  Weitere Informationen zu Quantum Metric Session Replay finden Sie unter https://www.quantummetric.com/platform/session-replay

## Voraussetzungen

Sie müssen Anspruch auf das **UX Ops**-Paket von Quantum Metric haben, um auf die Heatmap-Funktionen von Quantum Metric zugreifen zu können.

## Schritt 1: Konfigurieren von Links in Analysis Workspace

1. Melden Sie sich bei &quot;[.adobe.com“ &#x200B;](https://experience.adobe.com).
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

![Heatmap](assets/heatmap.png)

## Schritt 2: Heatmaps durch Anklicken von Links in Customer Journey Analytics anzeigen

Nachdem Sie eine Seite gefunden haben, auf der Sie Heatmapping erforschen möchten, können Sie sie auf das gewünschte Bedienfeld anwenden. Die Tabelle gibt eine URL zurück, mit der Sie Heatmaps, Bildlauftiefen und Schlüsselzonen für die Interaktion mit Quantum Metric untersuchen können. Weitere Informationen finden [&#x200B; unter „Quantum Metric &#x200B;](https://www.quantummetric.com/platform/interaction-heatmaps) - Produktübersicht“. Sie können sich auch an Ihren Kundenbetreuer von Quantum Metric wenden oder eine Anfrage über das [Quantum Metric Customer Request Portal) &#x200B;](https://community.quantummetric.com/s/public-support-page).
