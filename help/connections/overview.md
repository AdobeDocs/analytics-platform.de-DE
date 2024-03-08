---
title: Customer Journey Analytics-Verbindungen – Übersicht
description: Erfahren Sie mehr über Verbindungen in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 14cdc7bd8817dbf1d7a9950fa6ff62aedff82640
workflow-type: ht
source-wordcount: '188'
ht-degree: 100%

---

# Verbindungen – Übersicht

Mit Verbindungen können Customer Journey Analytics-Produktadmins Verbindungen zu verschiedenen AEP-Datenquellen herstellen, z. B. zu Ereignis-, Such- und Profildatensätzen. Diese Verbindungen ermöglichen die Integration von Daten aus einer Verbindung in eine abgeleitete Datenansicht. Unsere Empfehlung war, den Zugriff auf das Verbindungs-Management auf eine zentrale Management-Gruppe zu beschränken. Konfigurationen auf Verbindungsebene haben vertragliche Auswirkungen auf die Volumenzuweisungen von Daten, die in Customer Journey Analytics eingehen.
Verbindungen sind die Grundlage von CJA und werden aus AEP-Quelldatensätzen erstellt. Der Zugriff auf Verbindungen bietet außerdem die Möglichkeit, den Verbindungs-Manager anzuzeigen, mit dem die zugrunde liegenden Datensätze, aus denen die Verbindung besteht, angezeigt sowie wichtige Bearbeitungs- und Konfigurationsoptionen vorgenommen werden können.

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
