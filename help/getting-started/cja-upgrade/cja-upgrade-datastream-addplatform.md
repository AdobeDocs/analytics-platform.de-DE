---
title: Erstellen eines Schemas für Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad für das Upgrade von Adobe Analytics auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: c6d49ca4-3d04-4c0f-accd-8666a587109d
autotag-review: '2026-05-19T08:12:37.701Z'
TQID: 'https://experienceleague.adobe.com/ncFpZWJRFzOg8eFg6OF7TfAw6fZRhSdKi6W-LxPUAGg'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 280
ht-degree: 100%

---

# Platform als Dienst zu Ihrem Datenstrom hinzufügen {#upgrade-addplatform-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-addplatform-datastream"
>title="Adobe Experience Platform als Dienst zum Datenstrom hinzufügen"
>abstract="Ein Datenstrom benötigt einen oder mehrere Dienste, an die Daten gesendet werden. Richten Sie Adobe Experience Platform als Dienst in Ihrem Datenstrom ein.<br><br>Das Hinzufügen von Diensten zu einem Datenstrom ist ein einfacher Prozess und dauert nur wenige Minuten."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Bevor Sie die Schritte in diesem Abschnitt abschließen, sollte bereits ein Datenstrom vorhanden sein. Wann und wie der Datenstrom erstellt wurde, hängt wie folgt von Ihrer Adobe Analytics-Implementierung ab:

* Wenn Ihre Adobe Analytics-Implementierung das Web-SDK oder die Web-SDK-Erweiterung verwendet, war der Datenstrom bereits vor dem Upgrade-Prozess für Ihre Adobe Analytics-Umgebung verfügbar.

* Bei anderen Adobe Analytics-Implementierungen ist die Erstellung eines Datenstroms Teil des Upgrade-Prozesses, wie unter [Erstellen eines Datenstroms zur Verwendung mit Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md) beschrieben.

Wenn der Datenstrom verfügbar ist, müssen Sie Platform als Dienst hinzufügen:

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
