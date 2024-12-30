---
title: Datenansicht im Customer Journey Analytics erstellen
description: Erfahren Sie mehr über den empfohlenen Pfad beim Upgrade von Adobe Analytics auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 832f3f9a-1836-43ac-8185-f22ae0ded3aa
source-git-commit: daa07b603caa613ca49b61c2e8e461d558459f57
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 23%

---

# Datenansicht im Customer Journey Analytics erstellen

>[!NOTE]
> 
>Befolgen Sie die Schritte auf dieser Seite erst, nachdem Sie alle vorherigen Upgrade-Schritte abgeschlossen haben. Sie können die [empfohlenen Upgrade-Schritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die Upgrade-Schritte ausführen, die für Ihr Unternehmen mit dem [Fragebogen für das Upgrade von Adobe Analytics auf Customer Journey Analytics dynamisch generiert wurden](https://gigazelle.github.io/cja-ttv/).
>
>Nachdem Sie die Schritte auf dieser Seite abgeschlossen haben, folgen Sie den empfohlenen Upgrade-Schritten oder den dynamisch generierten Upgrade-Schritten.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-views/create-dataview.md -->

Das Erstellen einer Datenansicht beinhaltet entweder das Erstellen von Metriken und Dimensionen aus Schemaelementen oder die Verwendung von Standardkomponenten. Die meisten Schemaelemente können je nach den Anforderungen Ihres Unternehmens entweder eine Dimension oder eine Metrik sein. Nachdem Sie ein Schemaelement in eine Datenansicht gezogen haben, werden rechts Optionen angezeigt, mit denen Sie anpassen können, wie die Dimension oder Metrik in Customer Journey Analytics funktioniert.

Erstellen einer Datenansicht:

1. Melden Sie sich bei [Customer Journey Analytics](https://analytics.adobe.com) an und gehen Sie zur Registerkarte **[!UICONTROL Datenansichten]**.

1. Wählen **[!UICONTROL Neue Datenansicht erstellen]**. Sie können auch eine vorhandene Datenansicht aus der Liste der Datenansichten auswählen und diese bearbeiten.

1. Geben [!UICONTROL **auf der Registerkarte**] einen Namen für die Datenansicht an und konfigurieren Sie die grundlegenden Einstellungen, Komponenten und Kalenderoptionen.

   Detaillierte Informationen zu den einzelnen Feldern finden Sie unter [Konfigurieren](/help/data-views/create-dataview.md#configure) in [Erstellen oder Bearbeiten einer Datenansicht](/help/data-views/create-dataview.md).

   ![Konfigurieren der Datenansicht](assets/dataview-configure.png)

1. Wählen Sie die Registerkarte [!UICONTROL **Komponenten**] aus.

   Auf [!UICONTROL **Registerkarte**] Komponenten“ legen Sie die Komponenten einer Datenansicht fest, d. h. Sie können Metriken und Dimensionen aus Schemaelementen erstellen. Sie können auch Standardkomponenten verwenden.

   ![Registerkarte „Komponenten“](assets/dataview-components.png)

1. Ziehen Sie auf der Registerkarte [!UICONTROL **Komponenten**] Schemaelemente aus der linken Leiste in den Abschnitt [!UICONTROL **Metriken**] oder den Abschnitt [!UICONTROL **Dimensionen**]. Die Schemaelemente, die Sie hinzufügen, werden zu Metriken oder Dimensionen in der Datenansicht.

   Detaillierte Informationen zu den Optionen, die beim Hinzufügen von Komponenten zu einer Datenansicht verfügbar sind, finden Sie unter [Komponenten](/help/data-views/create-dataview.md#components) in [Erstellen oder Bearbeiten einer Datenansicht](/help/data-views/create-dataview.md).

1. Wählen Sie die Registerkarte [!UICONTROL **Einstellungen**] aus. Von hier aus können Sie Filter konfigurieren, die auf Ihre gesamte Datenansicht angewendet werden, und Sitzungs-Timeouts und -Metriken konfigurieren.

   Detaillierte Informationen zu den Optionen, die beim Konfigurieren der Einstellungen für eine Datenansicht verfügbar sind, finden Sie unter [Einstellungen](/help/data-views/create-dataview.md#settings) in [Erstellen oder Bearbeiten einer Datenansicht](/help/data-views/create-dataview.md).

1. Wählen **[!UICONTROL Speichern]**, um die Konfiguration für Ihre Datenansicht zu speichern.

1. Nachdem alle gewünschten Einstellungen angegeben wurden, wählen Sie **[!UICONTROL Speichern und beenden]**.

1. Fahren Sie mit den [empfohlenen Upgrade-Schritten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oder den [dynamisch generierten Upgrade-Schritten](https://gigazelle.github.io/cja-ttv/) fort.
