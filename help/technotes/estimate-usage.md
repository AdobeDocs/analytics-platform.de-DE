---
title: Verwalten der Customer Journey Analytics-Nutzung
description: Erläutert die Verwaltung der Verwendung von Customer Journey Analytics.
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
autotag-review: '2026-05-19T09:30:13.855Z'
TQID: 'https://experienceleague.adobe.com/SWjkycY-YwNFMXRXwBypDtTL2ffFn40-Fp88vSxv-74'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
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
source-wordcount: 258
ht-degree: 37%

---

# Verwalten der Customer Journey Analytics-Nutzung

>[!TIP]
>
>Verwenden Sie die [**[!UICONTROL Usage &#x200B;]**-](/help/connections/manage-connections.md#usage), um **&#x200B; Nutzung &#x200B;** aufgenommenen und berichtbaren Zeilen über alle Verbindungen in Customer Journey Analytics hinweg anzuzeigen.



Sie können die Verwendung von Customer Journey Analytics in der Benutzeroberfläche [**[!UICONTROL Verbindungen &#x200B;]**](/help/connections/create-connection.md). In dieser Benutzeroberfläche können Sie auf Verbindungsebene die Datenaufbewahrung in Customer Journey Analytics als rollierendes Fenster in Monaten (1 Monat, 3 Monate, 6 Monate usw.) definieren.

Der Hauptvorteil besteht darin, dass Sie nur Daten speichern oder Berichte dazu erstellen, die anwendbar und nützlich sind, und ältere Daten löschen, die nicht mehr nützlich sind. Dies hilft Ihnen, Ihre vertraglichen Beschränkungen einzuhalten und das Risiko bezüglich Kostendeckung zu reduzieren.

Wenn Sie die Standardeinstellung unverändert, d. h. deaktiviert, lassen, wird die Aufbewahrungsdauer durch die Datenaufbewahrungseinstellung von Adobe Experience Platform ersetzt. Wenn Sie in Experience Platform Daten von einem Zeitraum von 25 Monaten haben, erhalten Customer Journey Analytics durch Aufstockung Daten von einem Zeitraum von 25 Monaten. Wenn Sie in Platform 10 dieser Monate löschen, werden in Customer Journey Analytics die verbleibenden 15 Monate beibehalten.

Die Datenaufbewahrung basiert auf Zeitstempeln und gilt nur für Ereignis-Datensätze und Zusammenfassungsdaten-Datensätze. Für Profil- oder Lookup-Datensätze gibt es keine rollierenden Datenfenstereinstellungen, da keine entsprechenden Zeitstempel vorhanden sind. Wenn Ihre Verbindung Profil- oder Lookup-Datensätze enthält, werden die Daten basierend auf Ihren Datenaufbewahrungseinstellungen für die Ereignis-Datensatz-Zeitstempel in Customer Journey Analytics beibehalten, da sie mit Ereignis-Datensätzen verbunden sind.


>[!MORELIKETHIS]
>
>[Anzeigen der Customer Journey Analytics-Nutzung](/help/connections/manage-connections.md#usage)

