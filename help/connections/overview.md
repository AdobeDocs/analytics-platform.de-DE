---
title: Customer Journey Analytics-Verbindungen – Übersicht
description: Erfahren Sie mehr über Verbindungen in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 836c793ae74185728af03636b0ba3e838f46f05d
workflow-type: ht
source-wordcount: '251'
ht-degree: 100%

---

# Verbindungen – Übersicht

Mit Verbindungen können Customer Journey Analytics-Produktadmins Verbindungen zu verschiedenen [!DNL  Experience Platform]-Datenquellen herstellen, z. B. zu Ereignis-, Lookup-, Profil- und Zusammenfassungsdatensätzen. Diese Verbindungen ermöglichen die Integration von Daten aus einer Verbindung in eine abgeleitete Datenansicht. Verbindungen sind die Grundlage von Customer Journey Analytics und werden aus [!DNL Experience Platform]-Quelldatensätzen erstellt. 

>[!IMPORTANT]
>
>Sie können mehrere [!DNL Experience Platform]-Datensätze zu einer Verbindung zusammenfassen.


## Workflow „Verbindungen“

![Workflow „Verbindungen“](assets/connection-workflow.png)

<!-- Outdated interface 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/v/35111/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

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

