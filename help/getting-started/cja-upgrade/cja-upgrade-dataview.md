---
title: Erstellen einer Datenansicht unter Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 23%

---

# Erstellen einer Datenansicht unter Customer Journey Analytics

>[!NOTE]
> 
>Führen Sie die Schritte auf dieser Seite erst aus, nachdem Sie alle vorherigen Aktualisierungsschritte ausgeführt haben. Sie können die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die für Ihr Unternehmen dynamisch generierten Aktualisierungsschritte mit dem Fragebogen [Adobe Analytics to Customer Journey Analytics Upgrade Fragenkatalog](https://gigazelle.github.io/cja-ttv/) ausführen.
>
>Nachdem Sie die Schritte auf dieser Seite ausgeführt haben, fahren Sie mit den empfohlenen Aktualisierungsschritten oder den dynamisch generierten Aktualisierungsschritten fort.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-views/create-dataview.md -->

Das Erstellen einer Datenansicht beinhaltet entweder das Erstellen von Metriken und Dimensionen aus Schemaelementen oder die Verwendung von Standardkomponenten. Die meisten Schemaelemente können je nach den Anforderungen Ihres Unternehmens entweder eine Dimension oder eine Metrik sein. Nachdem Sie ein Schemaelement in eine Datenansicht gezogen haben, werden rechts Optionen angezeigt, mit denen Sie anpassen können, wie die Dimension oder Metrik in Customer Journey Analytics funktioniert.

So erstellen Sie eine Datenansicht:

1. Melden Sie sich bei [Customer Journey Analytics](https://analytics.adobe.com) an und gehen Sie zur Registerkarte **[!UICONTROL Datenansichten]**.

1. Wählen Sie **[!UICONTROL Neue Datenansicht erstellen]** aus. Sie können auch eine vorhandene Datenansicht aus der Liste der Datenansichten auswählen und diese bearbeiten.

1. Geben Sie auf der Registerkarte [!UICONTROL **Konfigurieren**] einen Namen für die Datenansicht an und konfigurieren Sie die grundlegenden Einstellungen, Komponenten und Kalenderoptionen.

   Detaillierte Informationen zu den einzelnen Feldern finden Sie unter [Konfigurieren](/help/data-views/create-dataview.md#configure) in [Erstellen oder Bearbeiten einer Datenansicht](/help/data-views/create-dataview.md).

   ![Konfigurieren der Datenansicht](assets/dataview-configure.png)

1. Wählen Sie die Registerkarte [!UICONTROL **Komponenten**] aus.

   Auf der Registerkarte [!UICONTROL **Komponenten**] legen Sie die Komponenten einer Datenansicht fest. Dies bedeutet, dass Sie Metriken und Dimensionen aus Schemaelementen erstellen können. Sie können auch Standardkomponenten verwenden.

   ![Registerkarte „Komponenten“](assets/dataview-components.png)

1. Ziehen Sie aus der Registerkarte [!UICONTROL **Komponenten**] Schemaelemente aus der linken Leiste in den Bereich [!UICONTROL **Metriken**] oder den Abschnitt [!UICONTROL **Dimensionen**] . Die Schemaelemente, die Sie hinzufügen, werden zu Metriken oder Dimensionen in der Datenansicht.

   Ausführliche Informationen zu den verfügbaren Optionen beim Hinzufügen von Komponenten zu einer Datenansicht finden Sie unter [Komponenten](/help/data-views/create-dataview.md#components) in [Erstellen oder Bearbeiten einer Datenansicht](/help/data-views/create-dataview.md).

1. Wählen Sie die Registerkarte [!UICONTROL **Einstellungen**] aus. Von hier aus können Sie Filter konfigurieren, die auf Ihre gesamte Datenansicht angewendet werden, und Sitzungs-Timeout und Metriken konfigurieren.

   Ausführliche Informationen zu den verfügbaren Optionen beim Konfigurieren von Einstellungen für eine Datenansicht finden Sie unter [Einstellungen](/help/data-views/create-dataview.md#settings) in [Erstellen oder Bearbeiten einer Datenansicht](/help/data-views/create-dataview.md).

1. Wählen Sie **[!UICONTROL Speichern]** aus, um die Konfiguration für Ihre Datenansicht zu speichern.

1. Nachdem alle gewünschten Einstellungen angegeben wurden, wählen Sie **[!UICONTROL Speichern und beenden]**.

1. Führen Sie die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oder die dynamisch generierten Aktualisierungsschritte](https://gigazelle.github.io/cja-ttv/) aus.[

