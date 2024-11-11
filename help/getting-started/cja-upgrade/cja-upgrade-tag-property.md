---
title: Erstellen einer Tag-Eigenschaft und Hinzufügen der Web SDK-Erweiterung
description: Erfahren Sie, wie Sie eine Tag-Eigenschaft erstellen und die Web SDK-Erweiterung hinzufügen
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: ccc6df56771cd9f83bbd7a8570e32d7ed63a0ced
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 22%

---

# Erstellen eines Tags für Ihre Eigenschaft

>[!NOTE]
> 
>Führen Sie die Schritte auf dieser Seite erst aus, nachdem Sie alle vorherigen Aktualisierungsschritte ausgeführt haben. Sie können die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die für Ihr Unternehmen dynamisch generierten Aktualisierungsschritte mit dem Fragebogen [Adobe Analytics to Customer Journey Analytics Upgrade Fragenkatalog](https://gigazelle.github.io/cja-ttv/) ausführen.
>
>Nachdem Sie die Schritte auf dieser Seite ausgeführt haben, fahren Sie mit den empfohlenen Aktualisierungsschritten oder den dynamisch generierten Aktualisierungsschritten fort.

Sie können die Funktion Tags in Adobe Experience Platform verwenden, um Code auf Ihrer Site zur Datenerfassung zu implementieren. Mit dieser Tag-Management-Lösung können Sie Code zusammen mit anderen Tagging-Anforderungen bereitstellen. Tags ermöglichen die nahtlose Integration mit Adobe Experience Platform über die Adobe Experience Platform Web SDK-Erweiterung.

Die folgenden Informationen beschreiben die Erstellung eines Tags für Ihre Eigenschaft. Weitere Informationen finden Sie unter [Web SDK Tag-Erweiterung konfigurieren](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) in der Experience Platform-Dokumentation. Das Web SDK enthält den nativen [!UICONTROL Adobe Experience Cloud ID-Dienst], sodass Sie die ID-Diensterweiterung nicht zu Ihrem -Tag hinzufügen müssen.

Eine Eigenschaft ist im Wesentlichen ein Container, den Sie bei der Bereitstellung von Tags auf Ihrer Site mit Erweiterungen, Regeln, Datenelementen und Bibliotheken füllen. Viele Benutzer erstellen eine Eigenschaft für jede Website (oder Gruppe eng verwandter Sites), auf der sie denselben Tag-Satz bereitstellen möchten. Weitere Informationen zu Eigenschaften finden Sie unter [Eigenschaften](https://experienceleague.adobe.com/en/docs/experience-platform/tags/admin/companies-and-properties) in der Dokumentation zur Experience Platform-Datenerfassung.

So erstellen Sie ein Tag für Ihre Eigenschaft:

1. Melden Sie sich mit Ihren Adobe ID-Anmeldedaten bei experience.adobe.com an.

1. Gehen Sie in Adobe Experience Platform zu **[!UICONTROL Datenerfassung]** > **[!UICONTROL Tags]**.

1. Wählen Sie **[!UICONTROL Neue Eigenschaft]** aus.

   Benennen Sie das Tag, wählen Sie **[!UICONTROL Web]** aus und geben Sie einen Domain-Namen ein. Wählen Sie **[!UICONTROL Speichern]** aus, um fortzufahren.

   ![Erstellen einer Eigenschaft](assets/create-property.png)

1. Führen Sie die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oder die dynamisch generierten Aktualisierungsschritte](https://gigazelle.github.io/cja-ttv/) aus.[

