---
title: Implementieren des Loader-Tags für die Web SDK-Erweiterung
description: Erfahren Sie, wie Sie das Loader-Tag für die Web SDK-Erweiterung implementieren
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 471ecd60-6e1e-4889-93bd-c654b35d40dc
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 49%

---

# Implementieren des Loader-Tags für die Web SDK-Erweiterung {#upgrade-tag-loader}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-loader"
>title="Implementieren des Loader-Tags auf Ihrer Site"
>abstract="Arbeiten Sie mit Ihrem Website-Entwicklungs-Team zusammen, um das Loader-Tag auf jeder Seite Ihrer Site zu installieren.<br><br>Wie lange diese Aufgabe dauert, hängt stark von der Reaktionszeit des Engineering-Teams ab, mit dem Sie den Code bereitstellen. Einige Organisationen mit äußerst anpassungsfähigen Engineering-Teams können diesen Schritt in Tagen abschließen, während Engineering-Teams mit großem Aufgabenrückstand möglicherweise einen Monat oder länger brauchen."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Befolgen Sie die Schritte auf dieser Seite erst, nachdem Sie alle vorherigen Upgrade-Schritte abgeschlossen haben. Sie können die [empfohlenen Upgrade-Schritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die Upgrade-Schritte ausführen, die für Ihr Unternehmen mit dem Fragebogen [Upgrade von Adobe Analytics auf Customer Journey Analytics dynamisch generiert ](https://gigazelle.github.io/cja-ttv/).
>
>Nachdem Sie die Schritte auf dieser Seite abgeschlossen haben, folgen Sie den empfohlenen Upgrade-Schritten oder den dynamisch generierten Upgrade-Schritten.

Sie müssen Ihr Tag auf der Website installieren, die Sie verfolgen möchten, was bedeutet, dass Sie Code in das Kopfzeilen-Tag der Vorlage Ihrer Website einfügen müssen.

Im folgenden Prozess wird beschrieben, wie Sie den Code abrufen, der auf Ihr -Tag verweist. Weitere Informationen finden Sie in den [Implementierungshandbüchern für Tags und ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/implementation-guides)) in der Dokumentation zu Experience Platform.

Gehen Sie folgendermaßen vor, um Code abzurufen, der auf Ihr Tag verweist:

1. Melden Sie sich mit Ihren Adobe ID-Anmeldeinformationen bei experience.adobe.com an.

1. Navigieren Sie in Adobe Experience Platform **[!UICONTROL Datenerfassung]** > **[!UICONTROL Tags]**.

1. Wählen Sie auf **[!UICONTROL Seite]** Tag-Eigenschaften“ das neu erstellte Tag aus der Liste der Eigenschaften aus, um es zu öffnen.

1. Wählen Sie **[!UICONTROL Umgebungen]** in der linken Leiste aus.

1. Wählen Sie in der Umgebungsliste die jeweilige Installieren-Schaltfläche (Kästchen) aus.

   Wählen Sie im Dialog [!UICONTROL Web-Installationsanleitung] die Schaltfläche „Kopieren“ neben dem Skriptcode aus, der wie folgt aussehen sollte:

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![Umgebung](assets/environment.png)

1. Wählen Sie **[!UICONTROL Schließen]** aus.

   Anstelle des Codes für die Entwicklungsumgebung hätten Sie auch eine andere Umgebung (Staging, Produktion) auswählen können, je nachdem, wo Sie das Adobe Experience Platform Web SDK bereitstellen möchten.

   Weitere Informationen finden Sie in [Umgebungen](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=de?).

1. Fahren Sie mit den [empfohlenen Upgrade-Schritten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oder den [dynamisch generierten Upgrade-Schritten](https://gigazelle.github.io/cja-ttv/) fort.
