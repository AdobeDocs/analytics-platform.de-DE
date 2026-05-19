---
title: Komponenteneinstellungen für Zusammenfassungsdatengruppen
description: Details und Informationen zur Konfiguration von Dimensionen aus Datensätzen, um sicherzustellen, dass Sie Berichte über Zusammenfassungsdaten ordnungsgemäß erstellen können.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c39ee568-97f6-4925-ae18-3d4a9dfdb6f5
autotag-review: '2026-05-19T09:00:37.763Z'
TQID: 'https://experienceleague.adobe.com/t1TH-tkHBNCfmC8hgk-IntYmYdRrS0enf2YEyRExCo4'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 378
ht-degree: 89%

---

# Komponenteneinstellungen für [!UICONTROL Zusammenfassungsdatengruppen] {#summary-data-group-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_summarydatagroup"
>title="Zusammenfassungsdatengruppe"
>abstract="Eine Zusammenfassungsdatengruppe erzeugt eine Verbindung zwischen allen Dimensionen in der Gruppierung und wird verwendet, um Dimensionen aus Zusammenfassungsdatensätzen mit anderen Dimensionen für die Berichterstattung zu kombinieren."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_summarydatagroup_hideinreporting"
>title="In Berichten verbergen"
>abstract="Wenn Sie diese Option auswählen, wird **[!UICONTROL Komponente in Berichten verbergen]** für diese Dimension aktiviert und verhindert, dass die Komponente in Analysis Workspace und anderen Reporting-Tools von Customer Journey Analytics angezeigt wird."

<!-- markdownlint-enable MD034 -->



Eine Zusammenfassungsdatengruppe erzeugt eine Verbindung zwischen allen Dimensionen in der Gruppierung und wird verwendet, um Dimensionen aus Zusammenfassungsdatensätzen mit anderen Dimensionen für die Berichterstattung zu kombinieren.

![Komponenteneinstellungen für Zusammenfassungsdatengruppen](/help/data-views/assets/summary-data-group.png)

So erstellen Sie eine Gruppierung von Dimensionen:

1. Wählen Sie eine Dimension aus.
1. Wählen Sie ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Zusammenfassungsdatengruppe]**.
1. Aktivieren Sie **[!UICONTROL Gruppierung erstellen]**.
1. Wählen Sie eine Dimension aus dem Dropdown-**&#x200B;** Dimensionaus, die Sie mit der ausgewählten Dimension aus dem ersten Schritt gruppieren möchten. Beachten Sie, dass nur Dimensionen, die Sie bereits zur Datenansicht hinzugefügt haben, über das Dropdown-Menü verfügbar sind.
1. Optional können Sie **[!UICONTROL In Berichten verbergen]** aktivieren, um die gruppierte Dimension in Berichten auszublenden. Die Aktivierung dieser Option ähnelt der separaten Konfiguration von **[!UICONTROL In Berichten verbergen]** für die gruppierte Dimension. Weitere Informationen finden Sie unter [Komponenteneinstellungen](overview.md).
1. Um der Gruppierung optional zusätzliche Dimensionen hinzuzufügen, wählen Sie ![Add](/help/assets/icons/Add.svg) **[!UICONTROL Dimension zu Gruppe hinzufügen]**.<br/>Sie können bis zu neun Dimensionen hinzufügen, da eine Zusammenfassungsdatengruppe auf zehn Dimensionen begrenzt ist.

## Identische Komponenteneinstellungen

Beim Gruppieren von Dimensionen müssen Sie sicherstellen, dass die Einstellungen für [!UICONTROL Unterzeichenfolge], [!UICONTROL Verhalten (Kleinbuchstaben)] und [!UICONTROL Werte einschließen/ausschließen] für jede der Dimensionen, die Teil der Gruppe sind, identisch sind. Andernfalls kann jede Dimension der Gruppe vor der Gruppierung möglicherweise andere Ergebnisse zurückgeben.
Zum Beispiel:

1. Sie haben eine Zusammenfassungsdatengruppe für `campaign_code` (Teil der Zusammenfassungsdaten) und `tracking_code` (Teil der Ereignisdaten) erstellt.
1. Sie haben [!UICONTROL Verhalten (Kleinbuchstaben)] auf die Dimension `campaign_code`, aber nicht auf die Dimension `tracking_code` angewendet.

Werte in `tracking_code` werden möglicherweise anders als über `campaign_code` angezeigt.

>[!IMPORTANT]
>
>Stellen Sie sicher, dass Sie eine Gruppierung von Dimensionen nur aus einer Dimension durchführen und keine Gruppierung aus mehreren Dimensionen anwenden. Wenn Sie beispielsweise eine Gruppierung durch das Hinzufügen von Dimension `campaign_name` zu Dimension `tracking_code` erstellen, wird dadurch nicht auch eine Gruppierung für die Dimension `campaign_name` erstellt.
>
