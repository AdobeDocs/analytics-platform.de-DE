---
title: Überwachen der Datensatzaufnahme beim Upgrade auf Customer Journey Analytics
description: Erfahren Sie, wie Sie die Datensatzaufnahme beim Upgrade auf Customer Journey Analytics überwachen.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: f71f5b863a024d882a116a5fd3bf0fc433e5fe99
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# Überwachen der Datensatzaufnahme beim Upgrade auf Customer Journey Analytics

>[!NOTE]
> 
>Befolgen Sie die Schritte auf dieser Seite erst, nachdem Sie alle vorherigen Upgrade-Schritte abgeschlossen haben. Sie können die [empfohlenen Upgrade-Schritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die Upgrade-Schritte ausführen, die für Ihr Unternehmen mit dem [Fragebogen für das Upgrade von Adobe Analytics auf Customer Journey Analytics dynamisch generiert wurden](https://gigazelle.github.io/cja-ttv/).
>
>Nachdem Sie die Schritte auf dieser Seite abgeschlossen haben, folgen Sie den empfohlenen Upgrade-Schritten oder den dynamisch generierten Upgrade-Schritten.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Nachdem Sie Ihre Web SDK-Implementierung konfiguriert haben, müssen Sie die Status einzelner Batches überprüfen, um sicherzustellen, dass Daten in den Datensatz aufgenommen werden.

1. Wählen Sie in der Experience Platform-Benutzeroberfläche **[!UICONTROL Überwachung]** im linken Navigationsbereich aus.

   Das Überwachungs-Dashboard wird angezeigt. In diesem Dashboard können Sie den Status eingehender Daten aus der Batch- oder Streaming-Aufnahme anzeigen.

   <!-- insert screenshot -->

1. Wählen Sie **[!UICONTROL Batch End-to-End]** aus, um eine Liste der Batches anzuzeigen.

   Wenn keine Batches angezeigt werden, überprüfen Sie Ihre Web SDK-Implementierung, um sicherzustellen, dass Daten korrekt an Adobe gesendet werden.

   <!-- insert screenshot -->

1. Wählen Sie die Batch-ID für einen bestimmten Datensatz aus und überprüfen Sie dann, ob **[!UICONTROL Erfolg]** im Feld **[!UICONTROL Status]** angezeigt wird.

   Wenn **[!UICONTROL Fehlgeschlagen]** im Feld **[!UICONTROL Status]** angezeigt wird, überprüfen Sie Ihre Web SDK-Implementierung, um sicherzustellen, dass die Daten korrekt an Adobe gesendet werden.

   Wiederholen Sie diesen Schritt, um den Status jedes Stapels zu überprüfen.

1. Fahren Sie mit den [empfohlenen Upgrade-Schritten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oder den [dynamisch generierten Upgrade-Schritten](https://gigazelle.github.io/cja-ttv/) fort.
