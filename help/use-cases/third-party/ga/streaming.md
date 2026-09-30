---
title: Konfigurieren von Streaming-Google-Analytics-Daten
description: Erfahren Sie, wie Sie Ihre Implementierung einrichten, um eine Google-Datenschicht nach Adobe Experience Platform zu senden.
exl-id: 58854f4b-ae28-424e-a2cf-0e76219cb802
feature: Use Cases
role: Admin
autotag-review: '2026-05-19T09:49:39.181Z'
TQID: 'https://experienceleague.adobe.com/xav7bGdbGLjYXm70GJBSxnDMfNDZpYp5qij1IqkaZSY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: e1bd5a34-b16e-477b-84cc-247fa0793f4b
    internal-label: Analytics integration
  - id: bf2b169f-d8b2-488a-97b9-f3bc9532e35c
    internal-label: Use cases
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
source-wordcount: '259'
ht-degree: 90%
---
# Konfigurieren von Streaming-Google-Analytics-Daten

Auf dieser Seite wird beschrieben, wie Sie Ihre Live-Daten von Google Analytics in Adobe Experience Platform aufnehmen und so in einer Datenansicht in Customer Journey Analytics auf diesen Datensatz verweisen können. Sie können die Schritte auf dieser Seite mit [der Aufnahme von historischen Google Analytics-Daten in Adobe Experience Platform](backfill.md) kombinieren, wodurch ein Datensatz mit historischen Daten generiert wird. Kombinieren Sie einen Streaming-Datensatz mit einem Aufstockungsdatensatz, um eine lückenlose Ansicht historischer und aktueller Daten in Customer Journey Analytics zu erhalten.

Die Konfiguration der Datenerfassung umfasst die folgenden Schritte:

1. Implementieren von [Tags für Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=de). Siehe [Schnellstartanleitung](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=de), um eine einfache Implementierung einzurichten.
1. Installieren der [Google Data Layer-Erweiterung](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html?lang=de). Diese Erweiterung ist eine Alternative zur Installation der Web SDK-Erweiterung und ist speziell für eine Google-Datenschicht konzipiert.
1. [Erstellen eines Datenstroms](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=de) in der Adobe Experience Platform-Datenerfassung. Konfigurieren Sie den Datenstrom so, dass Daten an Adobe Experience Platform gesendet werden. Aktuell müssen Sie jedes Google-Datenschichtobjekt dem entsprechenden XDM-Feld hier zuordnen. Adobe plant, diesen Zuordnungs-Workflow in Zukunft zu vereinfachen.

Nachdem Sie die gewünschten Tags auf Ihrer Site implementiert und veröffentlicht haben, können Sie mit [Verbindung erstellen](/help/connections/create-connection.md) und dann [Datenansicht erstellen](/help/data-views/create-dataview.md) fortfahren.
