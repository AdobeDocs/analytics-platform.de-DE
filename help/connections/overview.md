---
title: Customer Journey Analytics-Verbindungen – Übersicht
description: Erfahren Sie mehr über Verbindungen in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 14cdc7bd8817dbf1d7a9950fa6ff62aedff82640
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 39%

---

# Verbindungen – Übersicht

Verbindungen ermöglichen es Customer Journey Analytics-Produktadministratoren, Verbindungen mit verschiedenen AEP-Datenquellen herzustellen, z. B. Ereignis-, Such- und Profildatensätzen. Diese Verbindungen ermöglichen die Integration von Daten aus einer Verbindung zu einer abgeleiteten Datenansicht. Wir haben empfohlen, den Zugriff auf das Connections-Management auf eine zentrale Managementgruppe zu beschränken. Konfigurationen auf Verbindungsebene haben vertragliche Auswirkungen auf die Volumenzuweisungen von Daten, die in Customer Journey Analytics eingehen.
Verbindungen sind die Grundlage von CJA und werden aus AEP-Quelldatensätzen erstellt. Der Zugriff auf Verbindungen bietet außerdem die Möglichkeit, den Connections-Manager anzuzeigen, mit dem Sie die zugrunde liegenden Datensätze, aus denen die Verbindung besteht, anzeigen sowie wichtige Bearbeitungs- und Konfigurationsoptionen vornehmen können.

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
