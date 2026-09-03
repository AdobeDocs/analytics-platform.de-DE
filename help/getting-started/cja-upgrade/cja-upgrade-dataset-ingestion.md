---
title: Überwachen der Datensatzaufnahme beim Upgrade auf Customer Journey Analytics
description: Erfahren Sie, wie Sie historische Daten beim Upgrade auf Customer Journey Analytics überwachen können
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
autotag-review: '2026-05-19T08:10:42.746Z'
TQID: 'https://experienceleague.adobe.com/tAPQiUUPilyH50PlqwefoZjw14QDN9ER1D6EKsMAR9w'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 224
ht-degree: 100%

---

# Überwachen der Datensatzaufnahme beim Upgrade auf Customer Journey Analytics {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="Validieren von Daten im Datensatz"
>abstract="Nachdem Sie nun Ihre Implementierung konfiguriert haben, können Sie mit dem Datensatz-Aktivitäts-Manager die aufgenommenen und fehlgeschlagenen Batches anzeigen. Wenn Sie hauptsächlich aufgenommene Batches sehen, ist dieser Schritt abgeschlossen. Wenn Sie in erster Linie fehlgeschlagene Batches oder gar keine Batches sehen, überprüfen Sie Ihre Implementierung, um sicherzustellen, dass die Daten korrekt an Adobe gesendet werden."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Nachdem Sie Ihre Web SDK- oder API-Implementierung konfiguriert haben, müssen Sie die Status der einzelnen Batches überprüfen, um sicherzustellen, dass Daten in den Datensatz aufgenommen werden.

1. Wählen Sie in der Benutzeroberfläche von Experience Platform im linken Navigationsbereich auf **[!UICONTROL Monitoring]**.

   Das Dashboard „Monitoring“ wird angezeigt. Auf dem Dashboard können Sie die Status von aus der Batch- oder Streaming-Aufnahme eingehenden Daten anzeigen.

   <!-- insert screenshot -->

1. Wählen Sie **[!UICONTROL Batch End-to-End]** aus, um eine Liste der Batches anzuzeigen.

   Wenn keine Batches angezeigt werden, überprüfen Sie Ihre Implementierung, um sicherzustellen, dass Daten korrekt an Adobe gesendet werden.

   <!-- insert screenshot -->

1. Wählen Sie die Batch-ID für einen bestimmten Datensatz aus und überprüfen Sie dann, ob **[!UICONTROL Erfolg]** im Feld **[!UICONTROL Status]** angezeigt wird.

   Wenn **[!UICONTROL Fehlgeschlagen]** im Feld **[!UICONTROL Status]** angezeigt wird, überprüfen Sie Ihre Implementierung, um sicherzustellen, dass die Daten korrekt an Adobe gesendet werden.

   Wiederholen Sie diesen Schritt, um den Status von jedem Batch zu überprüfen.

{{upgrade-final-step}}

