---
title: Erstellen eines Schemas für Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad für das Upgrade von Adobe Analytics auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
autotag-review: '2026-05-19T08:13:03.106Z'
TQID: 'https://experienceleague.adobe.com/vzavQGq0OyhXTpSkqe3nnXQEW0Nax9RXt4SwTRwa4UU'
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 100%
---
# Erstellen eines Datenstroms zur Verwendung mit Customer Journey Analytics {#upgrade-create-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-datastream-create"
>title="Erstellen eines Datenstroms in Adobe Experience Platform"
>abstract="Ein Datenstrom ist ein Zwischenspeicherort, der Ihre Daten an alle konfigurierten Services weiterleitet. Erstellen Sie diesen Speicherort in Adobe Experience Platform.<br><br>Die Ersterstellung eines Datenstroms in der Platform-Oberfläche dauert nur wenige Minuten."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Ein Datenstrom stellt die Server-seitige Konfiguration bei der Implementierung der Adobe Experience Platform Web- und Mobile-SDKs dar. Beim Erfassen von Daten mit den Adobe Experience Platform SDKs werden Daten an das Adobe Experience Platform Edge Network gesendet. Dabei bestimmt der Datenstrom, an welche Dienste diese Daten weitergeleitet werden.

Konfigurieren Sie den Datenstrom in Ihrem Setup so, dass die erfassten Daten an Ihren Datensatz in Adobe Experience Platform gesendet werden.

>[!NOTE]
>
>Die folgenden Schritte sind nur für Adobe Analytics-Implementierungen erforderlich, die AppMeasurement oder die Analytics-Erweiterung (Tags) verwenden.
>
>Wenn Ihre Adobe Analytics-Implementierung das Web-SDK oder die Web-SDK-Erweiterung verwendet, ist der Datenstrom bereits in Ihrer Adobe Analytics-Umgebung vorhanden.

Gehen Sie folgendermaßen vor, um einen Datenstrom einzurichten:

1. Wählen Sie in Adobe Experience Platform die Option **[!UICONTROL Daten-Streams]** unter [!UICONTROL DATENERFASSUNG] in der linken Leiste.

1. Wählen Sie **[!UICONTROL Neuer Datenstrom]** aus.

1. Benennen und beschreiben Sie Ihren Datenstrom. Wählen Sie Ihr Schema in der Liste [!UICONTROL Ereignisschema] aus.

   ![Neuer Datenstrom](assets/new-datastream.png)

1. Wählen Sie **[!UICONTROL Speichern]** aus.

{{upgrade-final-step}}
