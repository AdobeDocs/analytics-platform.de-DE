---
title: Komponenteneinstellungen für Zusammenfassungsdatengruppen
description: Details und Informationen zur Konfiguration von Dimensionen aus Datensätzen, um sicherzustellen, dass Sie Berichte über Zusammenfassungsdaten ordnungsgemäß erstellen können.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c39ee568-97f6-4925-ae18-3d4a9dfdb6f5
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '376'
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
