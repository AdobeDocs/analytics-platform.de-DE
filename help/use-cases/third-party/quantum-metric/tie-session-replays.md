---
title: Quantum Metric-Sitzungswiederholungen an Daten in Customer Journey Analytics binden
description: Quantum Metric-Sitzungswiederholungen mit CJA-Daten zum besseren Verständnis des „Warum“ hinter „dem Was“.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 94dad68426a08ffa34ded7905567fbea307b1de4
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 1%

---

# Quantum Metric-Sitzungswiederholungen an Daten in Customer Journey Analytics binden

Durch die Verknüpfung von Quantum Metric-Sitzungswiederholungen mit CJA-Daten können Kunden das „Warum“ hinter „dem Was“ besser verstehen.  Workspace kann verwendet werden, um Sitzungen mit Reibung zu ermitteln. Anschließend können Sie auf per Hyperlink verknüpfte Sitzungs-IDs klicken, um die Sitzungswiederholung in Quantum Metric zu untersuchen.  Diese Daten ermöglichen die Anzeige des Verhaltens innerhalb einer Sitzung und ein besseres Verständnis dessen, was die Reibung der Verbraucher antreibt.  Durch Sitzungswiederholungen im Zusammenhang mit CJA können Sie wichtige Zusammenhänge im Kundenverhalten in Ihrem Erlebnis erfassen.

## Voraussetzungen

In diesem Anwendungsfall müssen Sie die Sitzungs-ID der Quantum-Metrik zusammen mit dem Rest Ihrer Implementierung erfassen. Unter [Erfassen von Quantum Metric-Sitzungs-IDs in Customer Journey Analytics](collect-session-id.md) erfahren Sie, wie Sie Ihre Implementierung ändern können.

## Schritt 1: Konfigurieren von Workspace für die Sitzungs-ID-Dimension

Erstellen Sie eine Freiformtabelle in Workspace und konfigurieren Sie sie so, dass Sitzungs-ID-Werte direkte Links zu Quantum Metric sind.

1. Melden Sie sich bei &quot;[.adobe.com“ ](https://experience.adobe.com).
1. Navigieren Sie zu Customer Journey Analytics und wählen Sie **[!UICONTROL Workspace]** im oberen Menü.
1. Wählen Sie ein vorhandenes Projekt aus oder erstellen Sie ein Projekt.
1. Erstellen Sie eine [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Ziehen Sie die Dimension Sitzungs-ID auf die Workspace-Arbeitsfläche.
1. Klicken Sie mit der rechten Maustaste auf die Spaltenüberschrift der Dimension und wählen Sie **[!UICONTROL Hyperlinks für alle Dimensionselemente erstellen]** aus.
1. Wählen Sie **[!UICONTROL Benutzerdefinierte URL erstellen]** aus.
1. Fügen Sie die folgende URL-Struktur ein:

   ```
   https://adobe.quantummetric.com/#/replay/cookie:$value
   ```

1. Klicken Sie auf **[!UICONTROL Erstellen]**.

Jede Sitzungs-ID ist jetzt ein klickbarer Link. Diese Links führen Sie zu Quantum Metric in einer neuen Registerkarte, wo Sie diese bestimmte Sitzung detaillierter analysieren können. Weitere [ zum Hinzufügen von Hyperlinks zu Analysis Workspace-Dimensionselementen finden Sie unter ](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)Erstellen von Hyperlinks in einer Freiformtabelle“.

## Schritt 2: Anzeigen von Sitzungen in Customer Journey Analytics

Nachdem Sie den Workspace-Bericht mit klickbaren Links erstellt haben, können Sie in Customer Journey Analytics Filter verwenden, um interessante Sitzungen zu identifizieren, die Sie in Quantum Metric weiter analysieren können.
Die Tabelle gibt alle Sitzungen in diesem Segment zurück, und Sie können auf eine beliebige Sitzung klicken, um sie in QM weiter zu erkunden.  Weitere Informationen zur Quantum Metric-Sitzungswiederholung finden Sie unter [https://www.quantummetric.com/platform/session-replay](https://www.quantummetric.com/platform/session-replay)

