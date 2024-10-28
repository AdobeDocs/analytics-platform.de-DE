---
title: Erstellen eines Schemas für Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 35%

---

# Erstellen eines Datenspeichers zur Verwendung mit Customer Journey Analytics

>[!NOTE]
>
>Diese Dokumentation sollte verwendet werden, nachdem der Fragebogen [Adobe Analytics zum Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/) ausgefüllt wurde.
> 
>Führen Sie die Schritte auf dieser Seite nur aus, nachdem Sie alle vorherigen Schritte ausgeführt haben, die dynamisch für Ihr Unternehmen generiert wurden.
>
>Nachdem Sie die Schritte auf dieser Seite ausgeführt haben, führen Sie die Aktualisierungsschritte aus, die für Ihr Unternehmen dynamisch vom Fragenkatalog [Adobe Analytics auf Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/) generiert wurden.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Ein Datenstrom stellt die Server-seitige Konfiguration bei der Implementierung der Adobe Experience Platform Web- und Mobile-SDKs dar. Beim Erfassen von Daten mit den Adobe Experience Platform SDKs werden Daten an das Adobe Experience Platform Edge Network gesendet. Es ist der Datastream, der bestimmt, an welche Dienste diese Daten weitergeleitet werden.

Im vorliegenden Beispiel möchten Sie, dass die auf der Website erfassten Daten an Ihren Datensatz in Adobe Experience Platform gesendet werden.

Gehen Sie folgendermaßen vor, um einen Datenstrom einzurichten:

1. Wählen Sie in Adobe Experience Platform in der linken Leiste [!UICONTROL DATENERFASSUNG] **[!UICONTROL Datastreams]** aus.

1. Wählen Sie **[!UICONTROL Neuer Datenstrom]** aus.

1. Benennen und beschreiben Sie Ihren Datenstrom. Wählen Sie Ihr Schema in der Liste [!UICONTROL Ereignisschema] aus.

   ![Neuer Datenstrom](assets/new-datastream.png)

1. Wählen Sie **[!UICONTROL Speichern]** aus.

1. Führen Sie die Aktualisierungsschritte aus, die für Ihr Unternehmen dynamisch vom Fragenkatalog [Adobe Analytics zu Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/) generiert wurden.

