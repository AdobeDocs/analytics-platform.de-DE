---
title: Customer Journey Analytics-Verbindungen – Übersicht
description: Erfahren Sie mehr über Verbindungen in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: dc3a109f162adfe48f621ba3ece95fedead3c6e1
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 55%

---

# Verbindungen – Übersicht

Verbindungen ermöglichen es Customer Journey Analytics-Produktadministratoren, Verbindungen mit verschiedenen [!DNL Adobe Experience Platform] Datenquellen wie Ereignis-, Lookup- und Profildatensätze. Diese Verbindungen ermöglichen die Integration von Daten aus einer Verbindung in eine abgeleitete Datenansicht. Verbindungen sind die Grundlage von CJA und werden aus erstellt. [!DNL Experience Platform] Quelldatensätze. Über den Zugriff auf Verbindungen können Sie auch den Connections-Manager anzeigen, in dem Sie die zugrunde liegenden Datensätze, aus denen die Verbindung besteht, anzeigen sowie wichtige Bearbeitungs- und Konfigurationsoptionen vornehmen können.

Unsere Empfehlung war, den Zugriff auf das Verbindungs-Management auf eine zentrale Management-Gruppe zu beschränken. Konfigurationen auf Verbindungsebene haben vertragliche Auswirkungen auf die Volumenzuweisungen von Daten, die in Customer Journey Analytics eingehen.

Im Folgenden finden Sie eine Videoübersicht:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## Erforderliche Berechtigungen

Um eine Customer Journey Analytics-Verbindung zu erstellen, benötigen Sie die folgenden Berechtigungen in [Adobe Admin Console](https://helpx.adobe.com/de/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html):

Adobe Experience Platform:
* Datenmodellierung: Schemas anzeigen, Schemas verwalten
* Daten-Management: Datensätze anzeigen, Datensätze verwalten
* Datenaufnahme: Quellen verwalten
* Anzeigen von Identity-Namespaces

Customer Journey Analytics
* Produktadministratorzugriff

>[!IMPORTANT]
>
>Sie können mehrere [!DNL Experience Platform]-Datensätze zu einer Verbindung zusammenfassen.
