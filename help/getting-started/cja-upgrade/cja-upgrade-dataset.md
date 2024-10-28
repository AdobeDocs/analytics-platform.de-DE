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
source-wordcount: '284'
ht-degree: 30%

---

# Erstellen eines Datensatzes zur Verwendung mit Customer Journey Analytics

>[!NOTE]
>
>Diese Dokumentation sollte verwendet werden, nachdem der Fragebogen [Adobe Analytics zum Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/) ausgefüllt wurde.
> 
>Führen Sie die Schritte auf dieser Seite nur aus, nachdem Sie alle vorherigen Schritte ausgeführt haben, die dynamisch für Ihr Unternehmen generiert wurden.
>
>Nachdem Sie die Schritte auf dieser Seite ausgeführt haben, führen Sie die Aktualisierungsschritte aus, die für Ihr Unternehmen dynamisch vom Fragenkatalog [Adobe Analytics auf Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/) generiert wurden.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Nach dem Erstellen eines XDM-Schemas müssen Sie jetzt das Konstrukt definieren, um diese Daten zu speichern und zu verwalten, was in Adobe Experience Platform über einen Datensatz erfolgt.

So erstellen Sie einen Datensatz:

1. Wählen Sie in Adobe Experience Platform in der linken Leiste **[!UICONTROL Datensätze]** in [!UICONTROL DATENVERWALTUNG] aus.

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

   Weitere Informationen zum Anzeigen, Anzeigen einer Vorschau, Erstellen und Löschen eines Datensatzes finden Sie im [Benutzerhandbuch zu Datensätzen](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=de) . Sie können auch erfahren, wie Sie einen Datensatz für das Echtzeit-Kundenprofil aktivieren.

1. Führen Sie die Aktualisierungsschritte aus, die für Ihr Unternehmen dynamisch vom Fragenkatalog [Adobe Analytics zu Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/) generiert wurden.

