---
title: Customer Journey Analytics Connections - Übersicht
description: Erfahren Sie mehr über Verbindungen in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
autotag-review: '2026-05-19T08:50:38.470Z'
TQID: 'https://experienceleague.adobe.com/bD6BGFGwJkHr3w4GYXoOCVH2l49csOvsaYLgqTAL41I'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 294
ht-degree: 88%

---

# Verbindungen – Übersicht

Mit Verbindungen können Customer Journey Analytics-Produktadmins definieren, welche [!DNL &#x200B; Experience Platform]-Datenquellen aufgenommen werden, z. B. Ereignis-, Lookup-, Profil- und Zusammenfassungsdatensätze. Verbindungen bilden die Grundlage von Customer Journey Analytics und bestimmen die Verfügbarkeit von Daten (Feldern), die Sie in einer [Datenansicht](/help/data-views/data-views.md) als Dimension oder Metriken definieren können.

>[!IMPORTANT]
>
>Sie können mehrere [!DNL Experience Platform]-Datensätze zu einer Verbindung zusammenfassen.


## Workflow „Verbindungen“

![Workflow „Verbindungen“](assets/connection-workflow.png)

>[!BEGINSHADEBOX]

Siehe ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Verbinden mit Datenquellen](https://experienceleague.adobe.com/de/docs/customer-journey-analytics-learn/tutorials/connections/connecting-customer-journey-analytics-to-data-sources-in-platform){target="_blank"} für ein Demovideo.

>[!ENDSHADEBOX]

Der Workflow „Verbindungen“ bietet Ihnen allgemein die folgenden Möglichkeiten:

| Schnittstelle | Beschreibung |
|:---:|---|
| ➊ | [Verwalten Sie Verbindungen und die allgemeine Nutzung](manage-connections.md) von Customer Journey Analytics über den Verbindungs-Manager. |
| ➋ | [Überprüfen Sie Details einer Verbindung](manage-connections.md#connection-details), z. B. aufgenommene, übersprungene oder gelöschte Datensatzeinträge. |
| ➌ | [Erstellen oder bearbeiten Sie die Konfiguration einer Verbindung](create-connection.md#create-or-edit-a-connection), z. B. eines rollierenden Datenfensters, der zu verwendenden Sandbox, der Datensätze, die Teil der Verbindung sind, usw. |
| ➍ | [Fügen Sie Datensätzen zu einer Verbindung hinzu](create-connection.md#add-datasets). Ihre Verbindung sollte mindestens einen Ereignis- oder Zusammenfassungsdatensatz aufweisen, kann jedoch eine Vielzahl von Ereignis-, Profil-, Lookup- und Zusammenfassungsdatensätzen enthalten. |
| ➎ | [Konfigurieren Sie die Einstellungen](create-connection.md#dataset-settings) für Datensätze, die Sie hinzufügen. Sie können festlegen, wie verschiedene Datensätze basierend auf einer gemeinsamen personenbasierten oder [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}-kontobasierten Kennung verknüpft werden. |
| ➏ | [Bearbeiten Sie die Einstellungen für einen vorhandenen Datensatz](create-connection.md#edit-a-dataset). Sie können die Datensatzeinstellungen zu einem späteren Zeitpunkt jederzeit erneut aufrufen. |



## Zugriffssteuerung

Der Zugriff auf das Verbindungs-Management sollte auf eine zentrale Management-Gruppe beschränkt sein. Verbindungskonfigurationen haben vertragliche Auswirkungen auf die Volumenzuweisungen von Daten, die in Customer Journey Analytics eingehen.

>[!MORELIKETHIS]
>
>[Zugriffssteuerung](/help/technotes/access-control.md)

