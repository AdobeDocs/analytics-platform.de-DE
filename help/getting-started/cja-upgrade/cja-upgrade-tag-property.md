---
title: Erstellen einer Tag-Eigenschaft und Hinzufügen der Web SDK-Erweiterung
description: Erfahren Sie, wie Sie eine Tag-Eigenschaft erstellen und die Web SDK-Erweiterung hinzufügen
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 156df830-541d-4c92-9c49-98f346e040a7
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 45%

---

# Erstellen eines Tags für die Eigenschaft {#upgrade-tag-property}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-property"
>title="Erstellen einer Tag-Eigenschaft in der Adobe Experience Platform-Datenerfassung"
>abstract="Tags zu verwenden, ist typischerweise der Standard für die Datenerfassung. Erstellen Sie ein Tag in der Adobe Experience Platform-Benutzeroberfläche, damit Sie Datenerfassungsvariablen jederzeit aktualisieren können.<br><br>Die Erstellung einer Tag-Eigenschaft kann mit mehreren Klicks und innerhalb weniger Minuten abgeschlossen werden."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Sie können die Tags-Funktion in Adobe Experience Platform verwenden, um Code zum Erfassen von Daten auf Ihrer Site zu implementieren. Mit dieser Tag-Management-Lösung können Sie Code zusammen mit anderen Tagging-Anforderungen bereitstellen. Tags ermöglichen die nahtlose Integration mit Adobe Experience Platform über die Adobe Experience Platform Web SDK-Erweiterung.

Die folgenden Informationen beschreiben, wie Sie ein Tag für Ihre Eigenschaft erstellen. Weitere Informationen finden Sie unter [Konfigurieren der Tag-Erweiterung „Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) in der Dokumentation zu Experience Platform. Der Web-SDK enthält nativ den [!UICONTROL Adobe Experience Cloud ID]Service, sodass Sie die ID-Service-Erweiterung nicht zu Ihrem Tag hinzufügen müssen.

Eine Eigenschaft ist im Wesentlichen ein Container, den Sie bei der Bereitstellung von Tags auf Ihrer Site mit Erweiterungen, Regeln, Datenelementen und Bibliotheken füllen. Viele Benutzer erstellen eine Eigenschaft für jede Website (oder Gruppe eng verwandter Sites), auf der sie denselben Satz von Tags bereitstellen möchten. Weitere Informationen zu Eigenschaften finden Sie unter [Eigenschaften](https://experienceleague.adobe.com/en/docs/experience-platform/tags/admin/companies-and-properties) in der Dokumentation zur Datenerfassung in Experience Platform.

So erstellen Sie ein Tag für Ihre Eigenschaft:

1. Melden Sie sich mit Ihren Adobe ID-Anmeldeinformationen bei experience.adobe.com an.

1. Navigieren Sie in Adobe Experience Platform **[!UICONTROL Datenerfassung]** > **[!UICONTROL Tags]**.

1. Wählen Sie **[!UICONTROL Neue Eigenschaft]** aus.

   Benennen Sie das Tag, wählen Sie **[!UICONTROL Web]** aus und geben Sie einen Domain-Namen ein. Wählen Sie **[!UICONTROL Speichern]** aus, um fortzufahren.

   ![Erstellen einer Eigenschaft](assets/create-property.png)

{{upgrade-final-step}}
