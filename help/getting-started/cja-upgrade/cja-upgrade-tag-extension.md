---
title: Erstellen einer Tag-Eigenschaft und Hinzufügen der Web-SDK-Erweiterung
description: Erfahren Sie, wie Sie eine Tag-Eigenschaft erstellen und die Web-SDK-Erweiterung hinzufügen
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 382d2b00-939a-4fff-be02-7a98d457a455
autotag-review: '2026-05-19T08:18:58.656Z'
TQID: 'https://experienceleague.adobe.com/8Wld534ijt7cmJnlbq4cB7tURTb8hch99Z6FIrhzAcQ'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
    internal-label: Upgrade
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
    internal-label: Basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 92%
---
# Hinzufügen der Web SDK-Erweiterung zum Tag {#upgrade-tag-extension}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-extension"
>title="Hinzufügen der Platform Web SDK-Erweiterung zur Tag-Eigenschaft"
>abstract="Fügen Sie Ihrer Tag-Eigenschaft die Adobe Experience Platform Web SDK-Erweiterung hinzu. Das Hinzufügen der Web SDK-Erweiterung zu Ihrer Tag-Eigenschaft ist optimiert und dauert nur wenige Minuten."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Sie können die Tags-Funktion in Adobe Experience Platform verwenden, um Code zur Datenerfassung auf Ihrer Website zu implementieren. Mit dieser Tag-Management-Lösung können Sie Code zusammen mit anderen Tagging-Anforderungen bereitstellen. Tags ermöglichen die nahtlose Integration mit Adobe Experience Platform über die Adobe Experience Platform Web SDK-Erweiterung.

Im Folgenden wird beschrieben, wie Sie Ihrem Tag die Web SDK-Erweiterung hinzufügen. Ergänzende Informationen finden Sie unter [Konfigurieren der Tag-Erweiterung des Web SDK](https://experienceleague.adobe.com/de/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) in der Dokumentation zu Experience Platform. Der Web SDK umfasst den Experience Platform Identity Service. Sie müssen also die Erweiterung [!UICONTROL Experience Cloud ID Service] nicht zu Ihrem Tag hinzufügen.

Nachdem Sie ein [Tag erstellt](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md) haben, müssen Sie es mit der Adobe Experience Platform Web SDK-Erweiterung konfigurieren. Dadurch wird sichergestellt, dass Sie Daten (über Ihren Datenstrom) an Adobe Experience Platform senden können.

So fügen Sie Ihrem Tag die Web SDK-Erweiterung hinzu:

1. Melden Sie sich mit Ihren Adobe ID-Anmeldeinformationen bei experiencecloud.adobe.com an.

1. Navigieren Sie in Adobe Experience Platform zu **[!UICONTROL Datenerfassung]** > **[!UICONTROL Tags]**.

1. Wählen Sie das neu erstellte Tag aus der Liste der [!UICONTROL Tag-Eigenschaften] aus, um es zu öffnen.

1. Wählen Sie **[!UICONTROL Erweiterungen]** in der linken Leiste aus.

1. Wählen Sie **[!UICONTROL Katalog]** in der oberen Leiste aus.

1. Suchen Sie nach der **[!UICONTROL Adobe Experience Platform Web SDK-Erweiterung]** oder scrollen Sie zu ihr und wählen Sie **[!UICONTROL Installieren]** aus, um sie zu installieren.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. Wählen Sie Ihre Sandbox und Ihren zuvor erstellten Datenstrom für Ihre [!UICONTROL Produktionsumgebung] und (optional) Ihre [!UICONTROL Staging-Umgebung] und Ihre [!UICONTROL Entwicklungsumgebung] aus.

   ![Konfigurieren der AEP Web SDK-Erweiterung](assets/aepwebsk-extension-datastreams.png)

1. Wählen Sie **[!UICONTROL Speichern]** aus.

{{upgrade-final-step}}
