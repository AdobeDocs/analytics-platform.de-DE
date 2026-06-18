---
title: Übergangsleitfaden
description: Erfahren Sie, wie Sie von Customer Journey Analytics zu Customer Journey Analytics B2B edition wechseln
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: d0e6398b-8080-4e36-b178-0cb91945d0c5
autotag-review: '2026-05-19T08:06:36.475Z'
TQID: 'https://experienceleague.adobe.com/vkf6272OwRu9B4ZgpiXKhc4J3WAqUAm8r-3iQLUgOKg'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7id: d3f42e9e-bb51-4077-a732-358b801d8b29
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46dbid: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2: id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1id: bfef374d-acfd-4c57-bf74-a2b36053c545id: e1471301-a189-438e-8d48-264a8db508a6
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 9c87ce4fb30c7d1d66ce88174443369ef44a7377
workflow-type: tm+mt
source-wordcount: 623
ht-degree: 3%

---

# Übergangshandbuch

In diesem Handbuch wird beschrieben, wie Sie von Customer Journey Analytics zum B2B edition von Customer Journey Analytics wechseln.

In dem Artikel wird davon ausgegangen, dass Sie Customer Journey Analytics bereits in gewissem Umfang verwenden:

* Sie verfügen über [Verbindungen](/help/connections/overview.md) die Daten in Customer Journey Analytics aufnehmen.
* Sie verfügen über [Datenansichten](/help/data-views/data-views.md) die die Daten aus diesen Verbindungen verwenden.
* Es [ „Projekte](/help/analysis-workspace/home.md) mit Berichten und Visualisierungen, die diese Datenansichten nutzen.

Wenn Sie Customer Journey Analytics noch nicht verwendet haben, lesen Sie die [Schnellstartanleitung für B2B edition](cja-b2b-quick-start-guide.md).

Wenn Sie ein Adobe Analytics-Benutzer sind und Customer Journey Analytics B2B edition verwenden möchten, lesen Sie zunächst die Dokumentation [Upgrade von Adobe Analytics auf Customer Journey Analytics](cja-upgrade/cja-upgrade-recommendations.md).


## Vorhandene Implementierung

Die bestehende Implementierung von Customer Journey Analytics ändert sich überhaupt nicht, sobald Sie für Customer Journey Analytics B2B edition lizenziert und bereitgestellt werden.

Alle vorhandenen Verbindungen werden als [personenbasierte Verbindungen“ ](cja-b2b-concepts-features.md#connections-and-identifiers) und funktionieren weiterhin ohne Aktualisierung. Alles, was auf den Daten dieser personenbasierten Verbindungen beruht, z. B. Datenansichten, Arbeitsbereich-Projekte, Segmente, geplante Exporte, Warnhinweise usw., funktioniert weiterhin wie ursprünglich geplant und beabsichtigt.

>[!IMPORTANT]
>
>Sie können keine vorhandenen personenbasierten Verbindungen in eine kontobasierte Verbindung ändern. Um die Funktionen von B2B edition nutzen zu können, ist eine neue kontobasierte Verbindung erforderlich.
>


## Implementieren von B2B-Funktionen

Um B2B-Funktionen in Ihrer vorhandenen Implementierung zu implementieren, müssen Sie die folgenden Schritte ausführen:

1. Modellieren Ihrer B2B-Daten. Sie können das [Adobe Experience-Datenmodell (XDM) verwenden](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=de) um B2B-Daten zu standardisieren und Schemas für Ihre B2B-Daten zu definieren.<br/>Sie können Ihre Schemata auf den [Standardklassen basieren, die in Real-Time CDP B2B edition bereitgestellt werden](https://experienceleague.adobe.com/de/docs/experience-platform/rtcdp/schemas/b2b) oder Sie können Ihre eigenen benutzerdefinierten Klassen und Schemata verwenden. Die [Anwendungsfälle](/help/use-cases/b2b/b2b-edition/use-cases-overview.md)-Artikel verwenden Real-Time CDP B2B edition-Klassen und -Schemata. Eine Real-Time CDP B2B edition-Lizenz ist jedoch nicht erforderlich, um die Standardklassen und -schemata zu verwenden. <br/>Customer Journey Analytics B2B edition geht von mindestens Account-basierten Zeitreihen-Ereignisdaten aus und profitiert von zusätzlichen Profil- oder Lookup-Datensatzdaten. z. B. Kontodaten, Daten zu Einkaufsgruppen, Opportunity-Daten, Daten zu Mitgliedern von Marketing-Listen und mehr.

   * Definieren Sie, welche Kennung Sie als primäre Kontokennung (Konto-ID) verwenden möchten. Häufig hilft Ihnen ein bestehendes CRM- oder anderes Tool (z. B. Demandbase), diese Kennung zu ermitteln.
   * Identifizieren Sie zusätzliche Kennungen für die anderen B2B-Daten, die Sie verwenden möchten: Kennung des globalen Kontos, Opportunity-Kennung, Einkaufsgruppenkennung und Personenkennung.

1. Vorbereiten Ihrer B2B-Daten. Stellen Sie sicher, dass Sie Kontokennungen für alle Zeitreihen-Ereignisdaten und relevanten Datensatzdaten hinzufügen und erfassen. Stellen Sie auf ähnliche Weise sicher, dass Ihre Zeitreihen-Ereignisdaten und Lookup-Datensätze andere Kennungen für relevante Ereignisse enthalten. Beispiel: Ein Ereignis, das den Wechsel zu einer anderen Verkaufsstufe signalisiert, sollte eine Opportunity-Kennung haben. Diese Kennung sollte Teil der Daten Ihrer Opportunity-Suche sein.

1. [Erstellen Sie eine neue kontobasierte Verbindung](/help/connections/create-connection.md#account-based-connection). Wählen Sie aus, welche optionalen Container Sie einbeziehen möchten, [Datensätze hinzufügen](/help/connections/create-connection.md#add-datasets) und definieren Sie die [Einstellungen für jeden Datensatz](/help/connections/create-connection.md#dataset-settings). Verwenden Sie [Übereinstimmung nach Container](cja-b2b-concepts-features.md#match-by-container) für Lookup-Datensatzdatensätze, wann immer dies möglich ist.

1. [Erstellen Sie Datenansichten](/help/data-views/create-dataview.md) basierend auf Ihrer neuen Verbindung.

   * Stellen Sie sicher, dass Sie alle relevanten Felder aus den aufgenommenen Daten als Metriken oder Dimensionen hinzufügen.
   * Wenden Sie Komponenteneinstellungen (wie Persistenz, Attribution usw.) an, falls erforderlich.
   * Fügen Sie ggf. weitere abgeleitete Felder hinzu.

1. [Erstellen von Workspace-Projekten](/help/analysis-workspace/build-workspace-project/create-projects.md) um Berichte zu erstellen und Einblicke in Ihre B2B-Daten zu erhalten. Verwenden Sie bestimmte B2B-Funktionen wie [Container](cja-b2b-concepts-features.md#containers), um detaillierte Einblicke zu erhalten.

   Sie können B2B-Berichte (personenbasiert) und B2B-Berichte (kontobasiert) und Insights mithilfe mehrerer [Bedienfelder](/help/analysis-workspace/c-panels/panels.md) in einem Arbeitsbereich-Projekt kombinieren.
