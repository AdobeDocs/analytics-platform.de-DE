---
title: Erstellen einer Datenansicht in Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad für das Upgrade von Adobe Analytics auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 832f3f9a-1836-43ac-8185-f22ae0ded3aa
TQID: https://experienceleague.adobe.com/rQL8R2D1JeIabt-iQSyYGY74N5JkP3hTN-x2kj-swXU
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 402
ht-degree: 95%

---

# Erstellen einer Datenansicht in Customer Journey Analytics {#upgrade-create-dataview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataview"
>title="Erstellen einer Datenansicht in Customer Journey Analytics"
>abstract="Eine Datenansicht ist ein für Customer Journey Analytics spezifischer Container, mit dem Sie bestimmen können, wie die aus einer Verbindung stammenden Daten interpretiert werden sollen.<br><br>Während die anfängliche Erstellung der Datenansicht nur einige Minuten in Anspruch nimmt, kann es mehrere Tage dauern, jede Dimension und Metrik mit den gewünschten Komponenteneinstellungen zu konfigurieren. Diese Einstellungen werden rückwirkend angepasst, sodass Ihre Organisation sie im Laufe der Zeit verfeinern kann."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-views/create-dataview.md -->

Das Erstellen einer Datenansicht beinhaltet entweder das Erstellen von Metriken und Dimensionen aus Schemaelementen oder die Verwendung von Standardkomponenten. Die meisten Schemaelemente können je nach den Anforderungen Ihres Unternehmens entweder eine Dimension oder eine Metrik sein. Nachdem Sie ein Schemaelement in eine Datenansicht gezogen haben, werden rechts Optionen angezeigt, mit denen Sie anpassen können, wie die Dimension oder Metrik in Customer Journey Analytics funktioniert.

So erstellen Sie eine Datenansicht:

1. Melden Sie sich bei [Customer Journey Analytics](https://analytics.adobe.com) an und wählen Sie **[!UICONTROL Datenansichten]**, optional unter **[!UICONTROL Daten-Management]**, im oberen Menü aus.

1. Wählen Sie **[!UICONTROL Neue Datenansicht erstellen]** aus. Sie können auch eine vorhandene Datenansicht aus der Liste der Datenansichten auswählen und diese bearbeiten.

1. Geben Sie auf der Registerkarte [!UICONTROL **Konfigurieren**] einen Namen für die Datenansicht an und konfigurieren Sie die grundlegenden Einstellungen, Komponenten und Kalenderoptionen.

   Detaillierte Informationen zu den einzelnen Feldern finden Sie im Abschnitt [Konfigurieren](/help/data-views/create-dataview.md#configure) unter [Erstellen oder Bearbeiten einer Datenansicht](/help/data-views/create-dataview.md).

   ![Konfigurieren der Datenansicht](assets/dataview-configure.png)

1. Wählen Sie die Registerkarte [!UICONTROL **Komponenten**] aus.

   Auf der Registerkarte [!UICONTROL **Komponenten**] legen Sie die Komponenten einer Datenansicht fest, d. h., Sie können Metriken und Dimensionen aus Schemaelementen erstellen. Sie können auch Standardkomponenten verwenden.

   ![Registerkarte Komponenten](assets/dataview-components.png)

1. Ziehen Sie auf der Registerkarte [!UICONTROL **Komponenten**] Schemaelemente aus der linken Leiste in den Abschnitt [!UICONTROL **Metriken**] oder den Abschnitt [!UICONTROL **Dimensionen**]. Die Schemaelemente, die Sie hinzufügen, werden in der Datenansicht zu Metriken oder Dimensionen.

   Detaillierte Informationen zu den Optionen, die beim Hinzufügen von Komponenten zu einer Datenansicht verfügbar sind, finden Sie im Abschnitt [Komponenten](/help/data-views/create-dataview.md#components) unter [Erstellen oder Bearbeiten einer Datenansicht](/help/data-views/create-dataview.md).

1. Wählen Sie die Registerkarte [!UICONTROL **Einstellungen**] aus. Von hier aus können Sie Segmente konfigurieren, die auf Ihre gesamte Datenansicht angewendet werden, und Sitzungs-Timeouts und -Metriken konfigurieren.

   Detaillierte Informationen zu den Optionen, die beim Konfigurieren der Einstellungen für eine Datenansicht verfügbar sind, finden Sie im Abschnitt [Einstellungen](/help/data-views/create-dataview.md#settings) unter [Erstellen oder Bearbeiten einer Datenansicht](/help/data-views/create-dataview.md).

1. Wählen Sie **[!UICONTROL Speichern]** aus, um die Konfiguration für Ihre Datenansicht zu speichern.

1. Nachdem alle gewünschten Einstellungen angegeben wurden, wählen Sie **[!UICONTROL Speichern und fertigstellen]** aus.

{{upgrade-final-step}}
