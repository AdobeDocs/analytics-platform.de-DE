---
description: Erläutert die Erstellung einer Metrik, die anzeigt, welche Marketing-Kanäle bei der Bestelloptimierung helfen.
title: Erstellen einer komplexeren berechneten Metrik
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
TQID: https://experienceleague.adobe.com/T5hA3-IeRUfDR53RL6TnJUslUI7XxRSZN2KpPKAz7k0
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 3%

---

# Erstellen einer komplexeren berechneten Metrik

In diesem Artikel wird ein komplexeres Beispiel für eine berechnete Metrik erläutert. Diese berechnete Metrik zeigt an, welche Marketing-Kanäle bei Bestellungen helfen. Dieser Typ der berechneten Metrik kann an jede Dimension oder jedes Erfolgsereignis angepasst werden.

1. Beginnen Sie mit dem Erstellen einer berechneten Metrik, wie in [Metriken erstellen](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) beschrieben.

1. Benennen Sie im Generator für berechnete Metriken die Metrik `Assisted Online Orders` oder etwas Ähnliches.

1. Wählen Sie die Metrik **[!UICONTROL Online-Bestellungen]** aus den Komponenten **[!UICONTROL Metriken]** und ziehen Sie die Metrik in den Bereich **[!UICONTROL Definition]**.

   1. Wählen Sie ![ Metrik ](/help/assets/icons/Setting.svg)Einstellung“ aus.
   1. Wählen Sie **[!UICONTROL Nicht standardmäßiges Zuordnungsmodell verwenden]** aus.
   1. Passen Sie das Attributionsmodell im **[!UICONTROL Spalten-Attributionsmodell]** an.
      1. Wählen Sie **[!UICONTROL Benutzerdefiniert]** für **[!UICONTROL Modell]** aus. Legen Sie **[!UICONTROL Starter]** auf `0`, **[!UICONTROL Player]** auf `100` und **[!UICONTROL Closer]** auf `0` fest.
      1. Wählen Sie **[!UICONTROL Besucher]** für **[!UICONTROL Container]** aus.
      1. Wählen Sie **[!UICONTROL 30 Tage]** für **[!UICONTROL Lookback-Fenster]**.

      1. Wählen Sie **[!UICONTROL Anwenden]** aus.

      ![Spalten-Attributionsmodell](assets/complex-calculated-metric.png)

1. Wählen **[!UICONTROL Speichern]**, um die berechnete Metrik zu speichern.

So verwenden Sie die berechnete Metrik:

1. Erstellen Sie in Analysis Workspace eine Freiformtabelle mit der Dimension **[!UICONTROL Marketing]** Kanal“, **[!UICONTROL Online-Bestellungen]** und Ihrer neuen Metrik **[!UICONTROL Unterstützte Online-Bestellungen]**.

   ![Bestellungen über den Marketing-Kanal](assets/marketing-channel-assists.png)

1. (Optional) Geben Sie die Metrik für andere Benutzer in Ihrer Organisation frei, wie unter [Freigeben berechneter Metriken](/help/components/calc-metrics/cm-workflow/cm-sharing.md) beschrieben.

Auf diese Weise lässt sich leicht erkennen, welche Marketing-Kanäle bei Fahrerbestellungen geholfen haben. Alternativ können Sie in einer Freiformtabelle eine beliebige Metrik auswählen und im Kontextmenü das Attributionsmodell direkt in der Tabelle anpassen.
