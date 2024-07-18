---
title: Auswirkungen des Löschens
description: Das passiert, wenn Sie Verbindungen, Datensätze oder Stapel in Customer Journey Analytics oder Adobe Experience Platform löschen.
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: 39e4c17336d3648cbf20cace535668d14510186f
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 71%

---

# Auswirkungen des Löschens

Beachten Sie Folgendes, bevor Sie Verbindungen, Datensätze oder Stapel in Customer Journey Analytics oder Adobe Experience Platform löschen:

| Wenn Sie... | Auswirkung |
| --- | --- |
| Löschen einer Verbindung in [!UICONTROL Customer Journey Analytics] | Eine Fehlermeldung weist darauf hin, dass<ul><li>für die gelöschte Verbindung erstellte Datenansichten nicht mehr funktionieren.</li><li> Ebenso funktionieren alle Arbeitsbereich-Projekte nicht mehr, die von den Datenansichten der gelöschten Verbindung abhängig sind.</li></ul>Beachten Sie, dass Sie keine Customer Journey Analytics-Verbindungen löschen können, die mit Adobe Experience Platform-Sandboxes verbunden sind, für die Sie keine Berechtigungen haben. Selbst wenn Sie über Berechtigungen für die Datenansichten verfügen, die auf diesen Verbindungen basieren, können Sie die Verbindungen erst löschen, wenn Ihnen Berechtigungen für die zugrunde liegenden Adobe Experience Platform-Sandboxes erteilt wurden. |
| Datensatz in [!UICONTROL Adobe Experience Platform] löschen | Durch das Löschen eines Datensatzes in Adobe Experience Platform wird der Datenfluss von diesem Datensatz zu allen Verbindungen, die diesen Datensatz enthalten, angehalten. Alle Daten aus diesem Datensatz werden automatisch aus den zugehörigen Customer Journey Analytics-Verbindungen gelöscht. |
| Löschen eines Datensatzes in [!UICONTROL Customer Journey Analytics] | Wenn Sie einen Datensatz aus einer Verbindung in Customer Journey Analytics löschen, funktionieren Datenansichten und Projekte, die auf diesen Datensatz angewiesen sind, nicht mehr. |
| Löschen von einem Batch aus einem Datensatz (in [!UICONTROL Adobe Experience Platform]) | Wenn ein Batch aus einem [!UICONTROL Adobe Experience Platform]-Datensatz gelöscht wird, wird derselbe Batch aus allen [!UICONTROL Customer Journey Analytics]-Verbindungen entfernt, die diesen Batch enthalten. [!UICONTROL Customer Journey Analytics] wird über Batches benachrichtigt, die in [!UICONTROL Adobe Experience Platform] gelöscht wurden. |
| Löschen von einem Batch, **während er** in [!UICONTROL Customer Journey Analytics] aufgenommen wird | Wenn in dem Datensatz nur ein Batch vorhanden ist, erscheinen keine Daten oder nur teilweise Daten aus diesem Batch in [!UICONTROL Customer Journey Analytics]. Die Aufnahme wird zurückgesetzt. Wenn es in dem Datensatz beispielsweise 5 Batches gibt und 3 davon bereits aufgenommen wurden, als der Datensatz gelöscht wurde, erscheinen die Daten dieser 3 Batches in [!UICONTROL Customer Journey Analytics]. |
| Lookup-Datensätze in [!UICONTROL Adobe Experience Platform] löschen | Das Löschen von Datensätzen ist zwar für andere Quell-Connectoren möglich, wird aber derzeit für den [Analytics Classifications Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html?lang=de) nicht unterstützt. Wenn Sie einen Datensatz versehentlich löschen, wenden Sie sich an die Kundenunterstützung von Adobe. |
