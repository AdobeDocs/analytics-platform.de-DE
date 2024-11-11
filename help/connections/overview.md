---
title: Customer Journey Analytics-Verbindungen – Übersicht
description: Erfahren Sie mehr über Verbindungen in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 2f78905c2a1e94174a52269becc15474baf59f71
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 70%

---

# Verbindungen – Übersicht

Mit Verbindungen können Customer Journey Analytics-Produktadmins Verbindungen zu verschiedenen [!DNL Adobe Experience Platform]-Datenquellen herstellen, z. B. zu Ereignis-, Such- und Profildatensätzen. Diese Verbindungen ermöglichen die Integration von Daten aus einer Verbindung in eine abgeleitete Datenansicht. Verbindungen sind die Grundlage von CJA und werden aus [!DNL Experience Platform]-Quelldatensätzen erstellt. Der Zugriff auf Verbindungen ermöglicht es Ihnen auch, den Verbindungs-Manager anzuzeigen, mit dem die zugrunde liegenden Datensätze, aus denen die Verbindung besteht, angezeigt sowie wichtige Bearbeitungs- und Konfigurationsoptionen vorgenommen werden können.

Unsere Empfehlung war, den Zugriff auf das Verbindungs-Management auf eine zentrale Management-Gruppe zu beschränken. Konfigurationen auf Verbindungsebene haben vertragliche Auswirkungen auf die Volumenzuweisungen von Daten, die in Customer Journey Analytics eingehen.

Im Folgenden finden Sie eine Videoübersicht:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## Erforderliche Berechtigungen

Zum Erstellen einer Customer Journey Analytics-Verbindung benötigen Sie die folgenden Berechtigungen. Weitere Informationen zu Berechtigungen finden Sie in der Dokumentation zu den [Adobe Admin Console](https://helpx.adobe.com/de/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html) - und [Adobe Experience Platform-Berechtigungen](https://experienceleague.adobe.com/de/docs/experience-platform/access-control/home) .

### In Adobe Admin Console:

* Customer Journey Analytics: Produktadministrator
* Adobe Experience Platform: Zum Produktprofil mit dem Namen *AEP-Default-All-Users* hinzugefügt

### In Adobe Experience Platform-Berechtigungen:

* Datenmodellierung: Schemas anzeigen, Schemas verwalten
* Daten-Management: Datensätze anzeigen, Datensätze verwalten
* Datenaufnahme: Quellen verwalten
* Identity Management: Anzeigen von Identitäts-Namespaces
* Sandboxes: Sandboxes, die in verwandten Customer Journey Analytics-Verbindungen verwendet werden

>[!IMPORTANT]
>
>Sie können mehrere [!DNL Experience Platform]-Datensätze zu einer Verbindung zusammenfassen.
