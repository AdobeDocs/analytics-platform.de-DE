---
title: Überwachen der Datensatzaufnahme beim Upgrade auf Customer Journey Analytics
description: Erfahren Sie, wie Sie die Datensatzaufnahme beim Upgrade auf Customer Journey Analytics überwachen
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 33%

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

Nachdem Sie Ihre Web SDK- oder API-Implementierung konfiguriert haben, müssen Sie die Status einzelner Batches überprüfen, um sicherzustellen, dass Daten in den Datensatz aufgenommen werden.

1. Wählen Sie in der Benutzeroberfläche von Experience Platform **[!UICONTROL Überwachung]** im linken Navigationsbereich aus.

   Das Überwachungs-Dashboard wird angezeigt. In diesem Dashboard können Sie den Status eingehender Daten aus der Batch- oder Streaming-Aufnahme anzeigen.

   <!-- insert screenshot -->

1. Wählen Sie **[!UICONTROL Batch End-to-End]** aus, um eine Liste der Batches anzuzeigen.

   Wenn keine Batches angezeigt werden, überprüfen Sie Ihre Implementierung, um sicherzustellen, dass Daten korrekt an Adobe gesendet werden.

   <!-- insert screenshot -->

1. Wählen Sie die Batch-ID für einen bestimmten Datensatz aus und überprüfen Sie dann, ob **[!UICONTROL Erfolg]** im Feld **[!UICONTROL Status]** angezeigt wird.

   Wenn **[!UICONTROL Fehlgeschlagen]** im Feld **[!UICONTROL Status]** angezeigt wird, überprüfen Sie Ihre Implementierung, um sicherzustellen, dass die Daten korrekt an Adobe gesendet werden.

   Wiederholen Sie diesen Schritt, um den Status jedes Stapels zu überprüfen.

{{upgrade-final-step}}

