---
title: Einstellungen für Zusammenfassungsdatengruppen
description: Details und Informationen zur Konfiguration von Dimensionen aus Datensätzen, um sicherzustellen, dass Sie ordnungsgemäß Berichte über Zusammenfassungsdaten erstellen können.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c39ee568-97f6-4925-ae18-3d4a9dfdb6f5
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 25%

---

# Komponenteneinstellungen für [!UICONTROL Zusammenfassungsdatengruppen] {#summary-data-group-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_summarydatagroup"
>title="Zusammenfassungsdatengruppe"
>abstract="Eine Zusammenfassungsdatengruppe erstellt eine Verknüpfung zwischen allen Dimensionen in der Gruppierung und wird verwendet, um Dimensionen aus Zusammenfassungsdatensätzen mit anderen Dimensionen für Berichte zu kombinieren."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_summarydatagroup_hideinreporting"
>title="In Berichten verbergen"
>abstract="Wenn Sie diese Option auswählen, wird **[!UICONTROL Komponente in Berichten verbergen]** für diese Dimension aktiviert und verhindert, dass die Komponente in Analysis Workspace und anderen Reporting-Tools von Customer Journey Analytics angezeigt wird."

<!-- markdownlint-enable MD034 -->



Eine Zusammenfassungsdatengruppe erstellt eine Verknüpfung zwischen allen Dimensionen in der Gruppierung und wird verwendet, um Dimensionen aus Zusammenfassungsdatensätzen mit anderen Dimensionen für Berichte zu kombinieren.

![Zusammenfassungsdatengruppen-Komponenteneinstellungen](/help/data-views/assets/summary-data-group.png)

So erstellen Sie eine Gruppierung von Dimensionen:

1. Dimension auswählen.
1. Wählen Sie ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Datengruppe Zusammenfassung]**.
1. Aktivieren Sie **[!UICONTROL Gruppierung erstellen]**.
1. Wählen Sie eine Dimension aus der Dropdown ]**Liste**[!UICONTROL  Dimension aus, die Sie mit der ausgewählten Dimension aus dem ersten Schritt gruppieren möchten. Beachten Sie, dass nur Dimensionen, die Sie bereits zur Datenansicht hinzugefügt haben, in der Dropdown-Liste verfügbar sind.
1. Optional können Sie **[!UICONTROL In Berichten ausblenden]** aktivieren, um die gruppierte Dimension in Berichten auszublenden. Die Aktivierung dieser Option ähnelt der Konfiguration von **[!UICONTROL In Berichten ausblenden]** für die gruppierte Dimension separat. Siehe [Komponenteneinstellungen](overview.md) für weitere Informationen.
1. Um der Gruppierung optional zusätzliche Dimensionen hinzuzufügen, wählen Sie ![Hinzufügen](/help/assets/icons/Add.svg) **[!UICONTROL Dimension zur Gruppe hinzufügen]**.<br/>Sie können bis zu neun Dimensionen hinzufügen, da eine Datengruppe mit einer Zusammenfassung eine Beschränkung von zehn Dimensionen hat.

## Gleiche Komponenteneinstellungen

Beim Gruppieren von Dimensionen müssen Sie sicherstellen, dass die Einstellungen für [!UICONTROL Teilzeichenfolge], [!UICONTROL Verhalten (Kleinbuchstaben)] und [!UICONTROL Ausschlusswerte einschließen] für jede der Dimensionen, die Teil der Gruppe sind, identisch sind. Andernfalls kann jede Dimension der Gruppe vor der Gruppierung möglicherweise andere Ergebnisse zurückgeben.
z. B.:

1. Sie haben eine Zusammenfassungsdatengruppe für `campaign_code` (Teil der Zusammenfassungsdaten) und `tracking_code` (Teil der Ereignisdaten) erstellt.
1. Sie haben [!UICONTROL Verhalten (Kleinbuchstaben)] auf die `campaign_code`, aber nicht auf die `tracking_code` angewendet.

Werte in `tracking_code` können möglicherweise anders als `campaign_code` angezeigt werden.

>[!IMPORTANT]
>
>Stellen Sie sicher, dass Sie eine Gruppierung von Dimensionen nur aus einer Dimension durchführen und keine Gruppierung aus mehreren Dimensionen anwenden. Wenn Sie beispielsweise eine Gruppierung erstellen, indem Sie die Dimension `campaign_name` zur Dimension `tracking_code` hinzufügen, erstellen Sie nicht auch eine Gruppierung für die Dimension `campaign_name` .
>
