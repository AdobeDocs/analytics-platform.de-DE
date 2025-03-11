---
title: Erstellen einer Datenansicht in Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad beim Upgrade von Adobe Analytics auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 832f3f9a-1836-43ac-8185-f22ae0ded3aa
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 45%

---

# Erstellen einer Datenansicht in Customer Journey Analytics {#upgrade-create-dataview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataview"
>title="Erstellen einer Datenansicht in Customer Journey Analytics"
>abstract="Eine Datenansicht ist ein für Customer Journey Analytics spezifischer Container, mit dem Sie bestimmen können, wie die aus einer Verbindung stammenden Daten interpretiert werden sollen.<br><br>Während die Ersterstellung der Datenansicht nur einige Minuten dauert, kann es mehrere Tage in Anspruch nehmen, jede Dimension und Metrik mit den gewünschten Komponenteneinstellungen zu konfigurieren. Diese Einstellungen werden rückwirkend angepasst, sodass Ihre Organisation sie im Laufe der Zeit verfeinern kann."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

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

1. Ziehen Sie [!UICONTROL **der Registerkarte**] Schemaelemente aus der linken Leiste in den Abschnitt [!UICONTROL **Metriken**] oder den Abschnitt [!UICONTROL **Dimensionen**]. Die Schemaelemente, die Sie hinzufügen, werden zu Metriken oder Dimensionen in der Datenansicht.

   Detaillierte Informationen zu den Optionen, die beim Hinzufügen von Komponenten zu einer Datenansicht verfügbar sind, finden Sie unter [Komponenten](/help/data-views/create-dataview.md#components) in [Erstellen oder Bearbeiten einer Datenansicht](/help/data-views/create-dataview.md).

1. Wählen Sie die Registerkarte [!UICONTROL **Einstellungen**] aus. Von hier aus können Sie Filter konfigurieren, die auf Ihre gesamte Datenansicht angewendet werden, und Sitzungs-Timeouts und -Metriken konfigurieren.

   Detaillierte Informationen zu den Optionen, die beim Konfigurieren der Einstellungen für eine Datenansicht verfügbar sind, finden Sie unter [Einstellungen](/help/data-views/create-dataview.md#settings) in [Erstellen oder Bearbeiten einer Datenansicht](/help/data-views/create-dataview.md).

1. Wählen **[!UICONTROL Speichern]**, um die Konfiguration für Ihre Datenansicht zu speichern.

1. Nachdem alle gewünschten Einstellungen angegeben wurden, wählen Sie **[!UICONTROL Speichern und beenden]**.

{{upgrade-final-step}}
