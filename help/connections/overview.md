---
title: Customer Journey Analytics-Verbindungen – Übersicht
description: Erfahren Sie mehr über Verbindungen in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 836c793ae74185728af03636b0ba3e838f46f05d
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 10%

---

# Verbindungen – Übersicht

Verbindungen ermöglichen es Customer Journey Analytics-Produktadministratoren, Verbindungen mit verschiedenen [!DNL &#x200B; Experience Platform]-Datenquellen herzustellen, z. B. Ereignis-, Lookup-, Profil- und Zusammenfassungsdatensätze. Diese Verbindungen ermöglichen die Integration von Daten aus einer Verbindung in eine abgeleitete Datenansicht. Verbindungen bilden die Grundlage von Customer Journey Analytics und werden aus [!DNL Experience Platform] Quelldatensätzen erstellt.

>[!IMPORTANT]
>
>Sie können mehrere [!DNL Experience Platform]-Datensätze zu einer Verbindung zusammenfassen.


## Verbindungs-Workflow

![Verbindungs-Workflow](assets/connection-workflow.png)

<!-- Outdated interface 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/v/35111/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

Der Verbindungs-Workflow auf allgemeiner Ebene bietet Ihnen folgende Möglichkeiten:

| Schnittstelle | Beschreibung |
|:---:|---|
| ➊  | [Verwalten Sie Ihre Verbindungen und die Gesamtnutzung](manage-connections.md) von Customer Journey Analytics über den Verbindungs-Manager. |
| ➋  | [Überprüfen Sie die Details einer Verbindung](manage-connections.md#connection-details) z. B. aufgenommene, übersprungene oder gelöschte Datensätze. |
| ➌  | [Erstellen oder Bearbeiten der Konfiguration einer Verbindung](create-connection.md#create-or-edit-a-connection) z. B. eines rollierenden Datenfensters, der zu verwendenden Sandbox, der Datensätze, die Teil der Verbindung sind, und mehr. |
| ➍  | [Datensätze zu einer Verbindung hinzufügen](create-connection.md#add-datasets). Ihre Verbindung sollte mindestens einen Ereignis- oder Zusammenfassungsdatensatz haben, kann jedoch eine Vielzahl von Ereignis-, Profil-, Lookup- und Zusammenfassungsdatensätzen enthalten. |
| ➎  | [Konfigurieren der Einstellungen](create-connection.md#dataset-settings) für Datensätze, die Sie hinzufügen. Sie können festlegen, wie verschiedene Datensätze basierend auf einer gemeinsamen personenbasierten oder [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} kontobasierten Kennung verknüpft werden. |
| ➏  | [Bearbeiten Sie die Einstellungen für einen vorhandenen Datensatz](create-connection.md#edit-a-dataset). Sie können die Datensatzeinstellungen zu einem späteren Zeitpunkt jederzeit erneut aufrufen. |



## Zugangssteuerung

Der Zugriff auf die Verbindungsverwaltung sollte auf eine Kernverwaltungsgruppe beschränkt sein. Verbindungskonfigurationen haben vertragliche Auswirkungen auf die Volumenzuteilung für Daten, die in Customer Journey Analytics importiert werden.

>[!MORELIKETHIS]
>
>[Zugriffssteuerung](/help/technotes/access-control.md).

