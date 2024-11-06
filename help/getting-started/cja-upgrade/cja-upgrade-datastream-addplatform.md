---
title: Erstellen eines Schemas für Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 31%

---

# Hinzufügen von Platform als Dienst zu Ihrem Datenspeicher

>[!NOTE]
> 
>Führen Sie die Schritte auf dieser Seite erst aus, nachdem Sie alle vorherigen Aktualisierungsschritte ausgeführt haben. Sie können die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die für Ihr Unternehmen dynamisch generierten Aktualisierungsschritte mit dem Fragebogen [Adobe Analytics to Customer Journey Analytics Upgrade Fragenkatalog](https://gigazelle.github.io/cja-ttv/) ausführen.
>
>Nachdem Sie die Schritte auf dieser Seite ausgeführt haben, fahren Sie mit den empfohlenen Aktualisierungsschritten oder den dynamisch generierten Aktualisierungsschritten fort.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Bevor Sie die in diesem Abschnitt beschriebenen Schritte durchführen, sollte bereits ein Datenspeicher vorhanden sein. Wann und wie der Datastream erstellt wurde, hängt von Ihrer Adobe Analytics-Implementierung ab, wie folgt:

* Wenn Ihre Adobe Analytics-Implementierung das Web SDK oder die Web SDK-Erweiterung verwendet, war der Datastraam vor dem Upgrade-Prozess für Ihre Adobe Analytics-Umgebung verfügbar.

* Bei anderen Adobe Analytics-Implementierungen ist das Erstellen eines Datenspeichers Teil des Aktualisierungsprozesses, wie unter [Erstellen eines Datenspeichers zur Verwendung mit Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md) beschrieben.

Wenn der Datenspeicher verfügbar ist, müssen Sie Platform als Dienst hinzufügen:

1. Wählen Sie in der Adobe Experience Platform-Benutzeroberfläche die Option **[!UICONTROL Datenströme]** in [!UICONTROL DATENERFASSUNG] in der linken Leiste.

1. Wählen Sie den zuvor konfigurierten Datenspeicher aus. <!--true?-->

1. Wählen Sie **[!UICONTROL Service hinzufügen]** aus.

1. Im Bildschirm [!UICONTROL Service hinzufügen]:

   1. Wählen Sie **[!UICONTROL Adobe Experience Platform]** in der Liste [!UICONTROL Service] aus.

   1. Achten Sie darauf, dass **[!UICONTROL Aktiviert]** ausgewählt ist.

   1. Wählen Sie Ihren Datensatz aus der Liste [!UICONTROL Ereignisdatensatz] aus.

      ![Datenstrom-AEP-Service](./assets/datastream-aep-service.png)

   1. Lassen Sie die anderen Einstellungen unverändert und wählen Sie **[!UICONTROL Speichern]** aus, um den Datenstrom zu speichern.

   Ihr Datenstrom ist jetzt so konfiguriert, dass die auf Ihrer Website erfassten Daten an Ihren Datensatz in Adobe Experience Platform weitergeleitet werden.

   Weitere Informationen um Konfigurieren eines Datenstroms und zum Umgang mit sensiblen Daten finden Sie unter [Übersicht über Datenströme](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=de).

1. Führen Sie die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oder die dynamisch generierten Aktualisierungsschritte](https://gigazelle.github.io/cja-ttv/) aus.[
