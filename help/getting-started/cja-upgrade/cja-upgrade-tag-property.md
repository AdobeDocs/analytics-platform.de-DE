---
title: Erstellen einer Tag-Eigenschaft und Hinzufügen der Web SDK-Erweiterung
description: Erfahren Sie, wie Sie eine Tag-Eigenschaft erstellen und die Web SDK-Erweiterung hinzufügen
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 156df830-541d-4c92-9c49-98f346e040a7
source-git-commit: cb6a439def7bf0fab1768fdd1c7d909b76b995d6
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 24%

---

# Erstellen eines Tags für die Eigenschaft

>[!NOTE]
> 
>Befolgen Sie die Schritte auf dieser Seite erst, nachdem Sie alle vorherigen Upgrade-Schritte abgeschlossen haben. Sie können die [empfohlenen Upgrade-Schritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die Upgrade-Schritte ausführen, die für Ihr Unternehmen mit dem [Fragebogen für das Upgrade von Adobe Analytics auf Customer Journey Analytics dynamisch generiert wurden](https://gigazelle.github.io/cja-ttv/).
>
>Nachdem Sie die Schritte auf dieser Seite abgeschlossen haben, folgen Sie den empfohlenen Upgrade-Schritten oder den dynamisch generierten Upgrade-Schritten.

Sie können die Tags-Funktion in Adobe Experience Platform verwenden, um Code zum Erfassen von Daten auf Ihrer Site zu implementieren. Mit dieser Tag-Management-Lösung können Sie Code zusammen mit anderen Tagging-Anforderungen bereitstellen. Tags ermöglichen die nahtlose Integration mit Adobe Experience Platform über die Adobe Experience Platform Web SDK-Erweiterung.

Die folgenden Informationen beschreiben, wie Sie ein Tag für Ihre Eigenschaft erstellen. Weitere Informationen finden Sie unter [Konfigurieren der Tag-Erweiterung „Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) in der Experience Platform-Dokumentation. Der Web-SDK enthält nativ den [!UICONTROL Adobe Experience Cloud ID]Service, sodass Sie die ID-Service-Erweiterung nicht zu Ihrem Tag hinzufügen müssen.

Eine Eigenschaft ist im Wesentlichen ein Container, den Sie bei der Bereitstellung von Tags auf Ihrer Site mit Erweiterungen, Regeln, Datenelementen und Bibliotheken füllen. Viele Benutzer erstellen eine Eigenschaft für jede Website (oder Gruppe eng verwandter Sites), auf der sie denselben Satz von Tags bereitstellen möchten. Weitere Informationen zu Eigenschaften finden Sie unter [Eigenschaften](https://experienceleague.adobe.com/en/docs/experience-platform/tags/admin/companies-and-properties) in der Dokumentation zum Experience Platform von Datenerfassungen.

So erstellen Sie ein Tag für Ihre Eigenschaft:

1. Melden Sie sich mit Ihren Adobe ID-Anmeldeinformationen bei experience.adobe.com an.

1. Navigieren Sie in Adobe Experience Platform **[!UICONTROL Datenerfassung]** > **[!UICONTROL Tags]**.

1. Wählen Sie **[!UICONTROL Neue Eigenschaft]** aus.

   Benennen Sie das Tag, wählen Sie **[!UICONTROL Web]** aus und geben Sie einen Domain-Namen ein. Wählen Sie **[!UICONTROL Speichern]** aus, um fortzufahren.

   ![Erstellen einer Eigenschaft](assets/create-property.png)

1. Fahren Sie mit den [empfohlenen Upgrade-Schritten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oder den [dynamisch generierten Upgrade-Schritten](https://gigazelle.github.io/cja-ttv/) fort.
