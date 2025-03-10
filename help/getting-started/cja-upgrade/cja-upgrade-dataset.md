---
title: Erstellen eines Schemas für Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad beim Upgrade von Adobe Analytics auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d686dcdd-08d5-4e8f-8f0d-76c8c7b0427f
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 60%

---

# Erstellen eines Datensatzes für Customer Journey Analytics {#upgrade-create-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-create"
>title="Erstellen eines Datensatzes in Adobe Experience Platform"
>abstract="Ein Datensatz entspricht einem Speicherort, an dem sich erfasste Daten befinden. Erstellen Sie diesen Speicherort in Adobe Experience Platform.<br><br>Die Erstellung eines Datensatzes unter Berücksichtigung eines Schemas dauert nur wenige Minuten."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Ein Datensatz ist das Konstrukt, das die Daten speichert und verwaltet, die Sie in Adobe Experience Platform erfassen.

So erstellen Sie einen Datensatz:

1. Wählen Sie in Adobe Experience Platform in der linken Leiste die Option **[!UICONTROL Datensätze]** unter [!UICONTROL DATEN-MANAGEMENT].

1. Wählen Sie **[!UICONTROL Erstellen eines Datensatzes]** aus.

   ![Erstellen eines Datensatzes](assets/create-dataset.png)

1. Wählen Sie **[!UICONTROL Erstellen eines Datensatzes aus einem Schema]** aus.

   ![Erstellen eines Datensatzes aus einem Schema](assets/create-dataset-from-schema.png)

1. Wählen Sie das zuvor erstellte Schema und danach **[!UICONTROL Weiter]** aus.

1. Benennen Sie Ihren Datensatz und geben Sie (optional) eine Beschreibung ein.

   ![Benennen eines Datensatzes](assets/name-your-datatest.png)

1. Wählen Sie **[!UICONTROL Beenden]** aus.

1. Wählen Sie den Umschalter **[!UICONTROL Profil]** aus.

   Sie werden aufgefordert, den Datensatz für das Profil zu aktivieren. Nach der Aktivierung reichert der Datensatz das Echtzeit-Kundenprofil mit den aufgenommenen Daten an.

   >[!IMPORTANT]
   >
   >    Sie können einen Datensatz für ein Profil nur aktivieren, wenn das Schema, zu dem der Datensatz gehört, auch für das Profil aktiviert ist.

   ![Aktivieren eines Schemas für ein Profil](assets/aepwebsdk-dataset-profile.png)

   Weitere Informationen [ Anzeigen, Anzeigen, Erstellen und Löschen eines Datensatzes finden ](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=de) im Handbuch zur Datensatz-Benutzeroberfläche . Außerdem erfahren Sie, wie Sie einen Datensatz für das Echtzeit-Kundenprofil aktivieren.

{{upgrade-final-step}}
