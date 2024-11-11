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
source-wordcount: '341'
ht-degree: 23%

---

# Hinzufügen der Web SDK-Erweiterung zu Ihrem -Tag

>[!NOTE]
> 
>Führen Sie die Schritte auf dieser Seite erst aus, nachdem Sie alle vorherigen Aktualisierungsschritte ausgeführt haben. Sie können die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die für Ihr Unternehmen dynamisch generierten Aktualisierungsschritte mit dem Fragebogen [Adobe Analytics to Customer Journey Analytics Upgrade Fragenkatalog](https://gigazelle.github.io/cja-ttv/) ausführen.
>
>Nachdem Sie die Schritte auf dieser Seite ausgeführt haben, fahren Sie mit den empfohlenen Aktualisierungsschritten oder den dynamisch generierten Aktualisierungsschritten fort.

Sie können die Funktion Tags in Adobe Experience Platform verwenden, um Code auf Ihrer Site zur Datenerfassung zu implementieren. Mit dieser Tag-Management-Lösung können Sie Code zusammen mit anderen Tagging-Anforderungen bereitstellen. Tags ermöglichen die nahtlose Integration mit Adobe Experience Platform über die Adobe Experience Platform Web SDK-Erweiterung.

Im Folgenden wird beschrieben, wie Sie die Web SDK-Erweiterung zu Ihrem -Tag hinzufügen. Weitere Informationen finden Sie unter [Web SDK Tag-Erweiterung konfigurieren](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) in der Experience Platform-Dokumentation. Das Web SDK enthält den nativen [!UICONTROL Adobe Experience Cloud ID-Dienst], sodass Sie die ID-Diensterweiterung nicht zu Ihrem -Tag hinzufügen müssen.

Nachdem Sie [ein Tag ](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md) erstellt haben, müssen Sie es mit der Adobe Experience Platform Web SDK-Erweiterung konfigurieren. Dadurch wird sichergestellt, dass Sie Daten (über Ihren Datastream) an Adobe Experience Platform senden können.

So fügen Sie Ihrem -Tag die Web SDK-Erweiterung hinzu:

1. Melden Sie sich mit Ihren Adobe ID-Anmeldedaten bei experience.adobe.com an.

1. Gehen Sie in Adobe Experience Platform zu **[!UICONTROL Datenerfassung]** > **[!UICONTROL Tags]**.

1. Wählen Sie das neu erstellte Tag aus der Liste der [!UICONTROL Tag-Eigenschaften] aus, um es zu öffnen.

1. Wählen Sie **[!UICONTROL Erweiterungen]** in der linken Leiste aus.

1. Wählen Sie **[!UICONTROL Katalog]** in der oberen Leiste aus.

1. Suchen Sie nach der Erweiterung **[!UICONTROL Adobe Experience Platform Web SDK extension]** oder scrollen Sie zu ihr und wählen Sie dann **[!UICONTROL Install]** aus, um sie zu installieren.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. Wählen Sie Ihre Sandbox und Ihren zuvor erstellten Datenstrom für Ihre [!UICONTROL Produktionsumgebung] und (optional) Ihre [!UICONTROL Staging-Umgebung] und Ihre [!UICONTROL Entwicklungsumgebung] aus.

   ![Konfigurieren der AEP Web SDK-Erweiterung](assets/aepwebsk-extension-datastreams.png)

1. Wählen Sie **[!UICONTROL Speichern]** aus.

1. Führen Sie die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oder die dynamisch generierten Aktualisierungsschritte](https://gigazelle.github.io/cja-ttv/) aus.[