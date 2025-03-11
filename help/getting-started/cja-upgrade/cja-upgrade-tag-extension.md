---
title: Erstellen einer Tag-Eigenschaft und Hinzufügen der Web SDK-Erweiterung
description: Erfahren Sie, wie Sie eine Tag-Eigenschaft erstellen und die Web SDK-Erweiterung hinzufügen
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 382d2b00-939a-4fff-be02-7a98d457a455
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 42%

---

# Hinzufügen der Web SDK-Erweiterung zum Tag {#upgrade-tag-extension}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-extension"
>title="Hinzufügen der Platform Web SDK-Erweiterung zu Ihrer Tag-Eigenschaft"
>abstract="Fügen Sie Ihrer Tag-Eigenschaft die Adobe Experience Platform Web SDK-Erweiterung hinzu. Der Vorgang zum Hinzufügen der Web SDK-Erweiterung zu Ihrer Tag-Eigenschaft ist optimiert und dauert nur wenige Minuten."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Sie können die Tags-Funktion in Adobe Experience Platform verwenden, um Code zum Erfassen von Daten auf Ihrer Site zu implementieren. Mit dieser Tag-Management-Lösung können Sie Code zusammen mit anderen Tagging-Anforderungen bereitstellen. Tags ermöglichen die nahtlose Integration mit Adobe Experience Platform über die Adobe Experience Platform Web SDK-Erweiterung.

Im Folgenden wird beschrieben, wie Sie Ihrem Tag die Web SDK-Erweiterung hinzufügen. Weitere Informationen finden Sie unter [Konfigurieren der Tag-Erweiterung „Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) in der Dokumentation zu Experience Platform. Der Web-SDK enthält nativ den [!UICONTROL Adobe Experience Cloud ID]Service, sodass Sie die ID-Service-Erweiterung nicht zu Ihrem Tag hinzufügen müssen.

Nachdem Sie [Tag erstellen](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md) müssen Sie es mit der Adobe Experience Platform Web SDK-Erweiterung konfigurieren. Dadurch wird sichergestellt, dass Sie Daten (über Ihren Datenstrom) an Adobe Experience Platform senden können.

So fügen Sie Ihrem Tag die Web SDK-Erweiterung hinzu:

1. Melden Sie sich mit Ihren Adobe ID-Anmeldeinformationen bei experience.adobe.com an.

1. Navigieren Sie in Adobe Experience Platform **[!UICONTROL Datenerfassung]** > **[!UICONTROL Tags]**.

1. Wählen Sie das neu erstellte Tag aus der Liste der [!UICONTROL Tag-Eigenschaften] aus, um es zu öffnen.

1. Wählen Sie **[!UICONTROL Erweiterungen]** in der linken Leiste aus.

1. Wählen Sie **[!UICONTROL Katalog]** in der oberen Leiste aus.

1. Suchen Sie nach der **[!UICONTROL Adobe Experience Platform Web SDK-Erweiterung]** oder scrollen Sie zu ihr und wählen Sie **[!UICONTROL Installieren]** aus, um sie zu installieren.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. Wählen Sie Ihre Sandbox und Ihren zuvor erstellten Datenstrom für Ihre [!UICONTROL Produktionsumgebung] und (optional) Ihre [!UICONTROL Staging-Umgebung] und Ihre [!UICONTROL Entwicklungsumgebung] aus.

   ![Konfigurieren der AEP Web SDK-Erweiterung](assets/aepwebsk-extension-datastreams.png)

1. Wählen Sie **[!UICONTROL Speichern]** aus.

{{upgrade-final-step}}
