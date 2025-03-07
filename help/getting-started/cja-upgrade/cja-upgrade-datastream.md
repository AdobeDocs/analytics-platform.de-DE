---
title: Erstellen eines Schemas für Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad beim Upgrade von Adobe Analytics auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 51%

---

# Erstellen eines Datenstroms für Customer Journey Analytics {#upgrade-create-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-datastream-create"
>title="Erstellen eines Datenstroms in Adobe Experience Platform"
>abstract="Ein Datenstrom ist ein Zwischenspeicherort, über den Ihre Daten an alle konfigurierten Services weitergegeben werden. Erstellen Sie diesen Speicherort in Adobe Experience Platform.<br><br>Die Ersterstellung eines Datenstroms in der Platform-Oberfläche dauert nur wenige Minuten."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Ein Datenstrom stellt die Server-seitige Konfiguration bei der Implementierung der Adobe Experience Platform Web- und Mobile-SDKs dar. Beim Erfassen von Daten mit den Adobe Experience Platform SDKs werden Daten an das Adobe Experience Platform Edge Network gesendet. Es ist der Datenstrom, der bestimmt, an welche Services diese Daten weitergeleitet werden.

Im vorliegenden Beispiel möchten Sie den Datenstrom so konfigurieren, dass die erfassten Daten an Ihren Datensatz in Adobe Experience Platform gesendet werden.

>[!NOTE]
>
>Die folgenden Schritte sind nur für Adobe Analytics-Implementierungen erforderlich, die AppMeasurement oder die Analytics-Erweiterung (Tags) verwenden.
>
>Wenn Ihre Adobe Analytics-Implementierung die Web-SDK oder die Web-SDK-Erweiterung verwendet, ist der Datenstrom bereits in Ihrer Adobe Analytics-Umgebung vorhanden.

Gehen Sie folgendermaßen vor, um einen Datenstrom einzurichten:

1. Wählen Sie in Adobe Experience Platform **[!UICONTROL Datenströme]** in [!UICONTROL DATENERFASSUNG] in der linken Leiste aus.

1. Wählen Sie **[!UICONTROL Neuer Datenstrom]** aus.

1. Benennen und beschreiben Sie Ihren Datenstrom. Wählen Sie Ihr Schema in der Liste [!UICONTROL Ereignisschema] aus.

   ![Neuer Datenstrom](assets/new-datastream.png)

1. Wählen Sie **[!UICONTROL Speichern]** aus.

{{upgrade-final-step}}
