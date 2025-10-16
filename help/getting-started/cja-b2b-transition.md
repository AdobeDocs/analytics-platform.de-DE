---
title: Übergangsleitfaden
description: Erfahren Sie, wie Sie von Customer Journey Analytics zu Customer Journey Analytics B2B edition wechseln
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: d0e6398b-8080-4e36-b178-0cb91945d0c5
source-git-commit: 3c13ae26a9ef48454467fc21b8faaa9e078c7f9f
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 0%

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

1. Modellieren Ihrer B2B-Daten. Customer Journey Analytics B2B edition geht zumindest von Account-basierten Zeitreihen-Ereignisdaten aus und profitiert von zusätzlichen Profil- oder Lookup-Datensatzdaten. z. B. Kontodaten, Daten zu Einkaufsgruppen, Opportunity-Daten, Daten zu Mitgliedern von Marketing-Listen und mehr.

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
