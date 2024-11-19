---
title: Überwachen der Datensatzaufnahme bei der Aktualisierung auf Customer Journey Analytics
description: Erfahren Sie, wie Sie die Erfassung von Datensätzen bei der Aktualisierung auf Customer Journey Analytics überwachen
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: a5425eccff643cd45fd630172b0113e646b2a9cc
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# Überwachen der Datensatzaufnahme bei der Aktualisierung auf Customer Journey Analytics

>[!NOTE]
> 
>Führen Sie die Schritte auf dieser Seite erst aus, nachdem Sie alle vorherigen Aktualisierungsschritte ausgeführt haben. Sie können die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die für Ihr Unternehmen dynamisch generierten Aktualisierungsschritte mit dem Fragebogen [Adobe Analytics to Customer Journey Analytics Upgrade Fragenkatalog](https://gigazelle.github.io/cja-ttv/) ausführen.
>
>Nachdem Sie die Schritte auf dieser Seite ausgeführt haben, fahren Sie mit den empfohlenen Aktualisierungsschritten oder den dynamisch generierten Aktualisierungsschritten fort.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Nachdem Sie Ihre Web SDK-Implementierung konfiguriert haben, müssen Sie die Status einzelner Batches überprüfen, um sicherzustellen, dass Daten in den Datensatz aufgenommen werden.

1. Wählen Sie in der Experience Platform-Benutzeroberfläche im linken Navigationsbereich **[!UICONTROL Monitoring]** aus.

   Das Monitoring-Dashboard wird angezeigt. In diesem Dashboard können Sie den Status eingehender Daten aus der Batch- oder Streaming-Erfassung anzeigen.

   <!-- insert screenshot -->

1. Wählen Sie **[!UICONTROL Batch End-to-End]** aus, um eine Liste der Batches anzuzeigen.

   Wenn keine Batches angezeigt werden, überprüfen Sie Ihre Web SDK-Implementierung, um sicherzustellen, dass die Daten korrekt an Adobe gesendet werden.

   <!-- insert screenshot -->

1. Wählen Sie die Batch-Kennung für einen bestimmten Datensatz aus und überprüfen Sie dann, ob **[!UICONTROL Erfolg]** im Feld **[!UICONTROL Status]** angezeigt wird.

   Wenn im Feld **[!UICONTROL Status]** der Wert **[!UICONTROL Fehlgeschlagen]** angezeigt wird, überprüfen Sie Ihre Web SDK-Implementierung, um sicherzustellen, dass die Daten korrekt an Adobe gesendet werden.

   Wiederholen Sie diesen Schritt, um den Status jedes Batches zu überprüfen.




