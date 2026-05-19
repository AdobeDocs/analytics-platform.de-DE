---
title: Erstellen eines Schemas für Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad für das Upgrade von Adobe Analytics auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d686dcdd-08d5-4e8f-8f0d-76c8c7b0427f
autotag-review: '2026-05-19T08:12:18.647Z'
TQID: 'https://experienceleague.adobe.com/ti9UiQzAa9wBCCH-44dmUxTzojuh5ZHu9YJ9HNC8OHI'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d00e9f03-e50b-4162-b143-0c0817c937c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 100%

---

# Erstellen eines Datensatzes zur Verwendung mit Customer Journey Analytics {#upgrade-create-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-create"
>title="Datensatz in Adobe Experience Platform erstellen"
>abstract="Ein Datensatz ist ein Speicherort, an dem sich erfasste Daten befinden. Erstellen Sie diesen Speicherort in Adobe Experience Platform.<br><br>Die Erstellung eines Datensatzes unter Berücksichtigung eines Schemas dauert nur wenige Minuten."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Ein Datensatz ist das Konstrukt, das die Daten speichert und verwaltet, die Sie in Adobe Experience Platform erfassen.

So erstellen Sie einen Datensatz:

1. Wählen Sie in Adobe Experience Platform in der linken Leiste in [!UICONTROL Daten-Management] die Option **[!UICONTROL Datensätze]** aus.

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

   Im [Handbuch zur Datensatz-Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=de) können Sie nachlesen, wie ein Datensatz angezeigt, in der Vorschau angesehen, erstellt und gelöscht werden kann. SIe finden ebenfalls Informationen dazu, wie ein Datensatz für das Echtzeit-Kundenprofil aktiviert wird.

{{upgrade-final-step}}
