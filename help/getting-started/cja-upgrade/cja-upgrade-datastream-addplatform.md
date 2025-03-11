---
title: Erstellen eines Schemas für Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad beim Upgrade von Adobe Analytics auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: c6d49ca4-3d04-4c0f-accd-8666a587109d
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 55%

---

# Hinzufügen von Platform als Service zu Ihrem Datenstrom {#upgrade-addplatform-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-addplatform-datastream"
>title="Hinzufügen von Adobe Experience Platform als Service zum Datenstrom"
>abstract="Ein Datenstrom benötigt einen oder mehrere Services, an die Daten versendet werden können. Richten Sie Adobe Experience Platform als Service in Ihrem Datenstrom ein.<br><br>Das Hinzufügen von Services zu einem Datenstrom ist ein einfacher Prozess, der nur wenige Minuten dauert."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Ein Datenstrom sollte bereits vorhanden sein, bevor Sie die Schritte in diesem Abschnitt abschließen. Wann und wie der Datenstrom erstellt wurde, hängt wie folgt von Ihrer Adobe Analytics-Implementierung ab:

* Wenn Ihre Adobe Analytics-Implementierung die Web-SDK oder die Web-SDK-Erweiterung verwendet, war der Datenstrom vor dem Upgrade-Prozess für Ihre Adobe Analytics-Umgebung verfügbar.

* Bei anderen Adobe Analytics-Implementierungen ist die Erstellung eines Datenstroms Teil des Upgrade-Prozesses, wie unter [Erstellen eines Datenstroms zur Verwendung mit Customer Journey Analytics&quot; ](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

Wenn der Datenstrom verfügbar ist, müssen Sie Platform als Service hinzufügen:

1. Wählen Sie in der Adobe Experience Platform-Benutzeroberfläche die Option **[!UICONTROL Datenströme]** in [!UICONTROL DATENERFASSUNG] in der linken Leiste.

1. Wählen Sie den zuvor konfigurierten Datenstrom aus. <!--true?-->

1. Wählen Sie **[!UICONTROL Service hinzufügen]** aus.

1. Im Bildschirm [!UICONTROL Service hinzufügen]:

   1. Wählen Sie **[!UICONTROL Adobe Experience Platform]** in der Liste [!UICONTROL Service] aus.

   1. Achten Sie darauf, dass **[!UICONTROL Aktiviert]** ausgewählt ist.

   1. Wählen Sie Ihren Datensatz aus der Liste [!UICONTROL Ereignisdatensatz] aus.

      ![Datenstrom-AEP-Service](./assets/datastream-aep-service.png)

   1. Lassen Sie die anderen Einstellungen unverändert und wählen Sie **[!UICONTROL Speichern]** aus, um den Datenstrom zu speichern.

   Ihr Datenstrom ist jetzt so konfiguriert, dass die auf Ihrer Website erfassten Daten an Ihren Datensatz in Adobe Experience Platform weitergeleitet werden.

   Weitere Informationen um Konfigurieren eines Datenstroms und zum Umgang mit sensiblen Daten finden Sie unter [Übersicht über Datenströme](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=de).

{{upgrade-final-step}}
