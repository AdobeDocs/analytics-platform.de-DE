---
title: Verwalten der Customer Journey Analytics-Nutzung
description: Erläutert die Verwaltung der Verwendung von Customer Journey Analytics.
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 37%

---

# Verwalten der Customer Journey Analytics-Nutzung

>[!TIP]
>
>Verwenden Sie die [**[!UICONTROL Usage ]**-](/help/connections/manage-connections.md#usage), um** Nutzung **aufgenommenen und berichtbaren Zeilen über alle Verbindungen in Customer Journey Analytics hinweg anzuzeigen.



Sie können die Verwendung von Customer Journey Analytics in der Benutzeroberfläche [**[!UICONTROL Verbindungen ]**](/help/connections/create-connection.md). In dieser Benutzeroberfläche können Sie auf Verbindungsebene die Datenaufbewahrung in Customer Journey Analytics als rollierendes Fenster in Monaten (1 Monat, 3 Monate, 6 Monate usw.) definieren.

Der Hauptvorteil besteht darin, dass Sie nur Daten speichern oder Berichte dazu erstellen, die anwendbar und nützlich sind, und ältere Daten löschen, die nicht mehr nützlich sind. Dies hilft Ihnen, Ihre vertraglichen Beschränkungen einzuhalten und das Risiko bezüglich Kostendeckung zu reduzieren.

Wenn Sie die Standardeinstellung unverändert, d. h. deaktiviert, lassen, wird die Aufbewahrungsdauer durch die Datenaufbewahrungseinstellung von Adobe Experience Platform ersetzt. Wenn Sie in Experience Platform Daten von einem Zeitraum von 25 Monaten haben, erhalten Customer Journey Analytics durch Aufstockung Daten von einem Zeitraum von 25 Monaten. Wenn Sie in Platform 10 dieser Monate löschen, werden in Customer Journey Analytics die verbleibenden 15 Monate beibehalten.

Die Datenaufbewahrung basiert auf Zeitstempeln und gilt nur für Ereignis-Datensätze und Zusammenfassungsdaten-Datensätze. Für Profil- oder Lookup-Datensätze gibt es keine rollierenden Datenfenstereinstellungen, da keine entsprechenden Zeitstempel vorhanden sind. Wenn Ihre Verbindung Profil- oder Lookup-Datensätze enthält, werden die Daten basierend auf Ihren Datenaufbewahrungseinstellungen für die Ereignis-Datensatz-Zeitstempel in Customer Journey Analytics beibehalten, da sie mit Ereignis-Datensätzen verbunden sind.


>[!MORELIKETHIS]
>
>[Anzeigen der Customer Journey Analytics-Nutzung](/help/connections/manage-connections.md#usage)

