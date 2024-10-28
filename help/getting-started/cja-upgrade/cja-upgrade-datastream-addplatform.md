---
title: Erstellen eines Schemas für Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 30%

---

# Hinzufügen von Platform als Dienst zu Ihrem Datenspeicher

>[!NOTE]
>
>Diese Dokumentation sollte verwendet werden, nachdem der Fragebogen [Adobe Analytics zum Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/) ausgefüllt wurde.
> 
>Führen Sie die Schritte auf dieser Seite nur aus, nachdem Sie alle vorherigen Schritte ausgeführt haben, die dynamisch für Ihr Unternehmen generiert wurden.
>
>Nachdem Sie die Schritte auf dieser Seite ausgeführt haben, führen Sie die Aktualisierungsschritte aus, die für Ihr Unternehmen dynamisch vom Fragenkatalog [Adobe Analytics auf Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/) generiert wurden.

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

1. Führen Sie die Aktualisierungsschritte aus, die für Ihr Unternehmen dynamisch vom Fragenkatalog [Adobe Analytics zu Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/) generiert wurden.
