---
title: Komponenteneinstellungen für Zusammenfassungsdaten
description: Details und Informationen zum Konfigurieren von Dimensionen aus Datensätzen, um sicherzustellen, dass Sie ordnungsgemäß über Zusammenfassungsdaten berichten können.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: cba5904191b0602557903b5b9f32a2b793c8207d
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 9%

---

# [!UICONTROL Komponenteneinstellungen der Zusammenfassungsdatengruppe]

Eine Zusammenfassungsdatengruppe erzeugt eine Verbindung zwischen allen Dimensionen in der Gruppierung und wird verwendet, um Dimensionen aus Zusammenfassungsdatensätzen mit anderen Dimensionen für die Berichterstattung zu kombinieren.

![Komponenteneinstellungen der Zusammenfassungsdatengruppe](/help/data-views/assets/summary-data-group.png)

So erstellen Sie eine Dimensiongruppierung:

1. Wählen Sie eine Dimension aus.
1. Wählen Sie ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Zusammenfassungsdatengruppe]** aus.
1. Aktivieren Sie **[!UICONTROL Gruppierung erstellen]**.
1. Wählen Sie aus der Dropdownliste **[!UICONTROL Dimension]** eine Dimension aus, die Sie mit der ausgewählten Dimension gruppieren möchten. Beachten Sie, dass in der Dropdown-Liste nur Dimensionen verfügbar sind, die Sie der Datenansicht bereits hinzugefügt haben.
1. Aktivieren Sie optional **[!UICONTROL In Berichten ausblenden]** , um die gruppierte Dimension aus der Berichterstellung auszublenden. Die Aktivierung dieser Option ähnelt der Konfiguration von **[!UICONTROL In der Berichterstellung ausblenden]** für die gruppierte Dimension. Weitere Informationen finden Sie unter [Komponenteneinstellungen](overview.md) .
1. Um der Gruppierung optional weitere Dimensionen hinzuzufügen, wählen Sie ![Hinzufügen](/help/assets/icons/Add.svg) **[!UICONTROL Dimension zur Gruppe hinzufügen]** aus.<br/>Sie können bis zu neun Dimensionen hinzufügen, da eine Zusammenfassungsdatengruppe maximal zehn Dimensionen hat.

## Gleiche Komponenteneinstellungen

Beim Gruppieren von Dimensionen müssen Sie sicherstellen, dass die Einstellungen für [!UICONTROL Unterzeichenfolge], [!UICONTROL Verhalten (Kleinbuchstaben)] und [!UICONTROL Ausschlusswerte einschließen] für die einzelnen Dimensionen, die Teil der Gruppe sind, identisch sind. Andernfalls kann jede Dimension der Gruppe vor der Gruppierung unterschiedliche Ergebnisse zurückgeben.
Zum Beispiel:

1. Sie haben eine Zusammenfassungsdatengruppe für `campaign_code` (Teil der Zusammenfassungsdaten) und `tracking_code` (Teil Ihrer Ereignisdaten) erstellt.
1. Sie haben [!UICONTROL Verhalten (Kleinbuchstaben)] auf die Dimension `campaign_code`, nicht aber auf die Dimension `tracking_code` angewendet.

Werte in `tracking_code` können sich möglicherweise von `campaign_code` unterscheiden.

>[!IMPORTANT]
>
>Stellen Sie sicher, dass Sie nur Dimensionen aus einer Dimension gruppieren und keine Gruppierung aus mehreren Dimensionen anwenden. Wenn Sie beispielsweise eine Gruppierung durch Hinzufügen der Dimension `campaign_name` zur Dimension `tracking_code` erstellen, erstellen Sie keine Gruppierung für die Dimension `campaign_name` .
>


