---
title: Konfigurieren von Customer Journey Analytics
description: Erfahren Sie, wie Sie Customer Journey Analytics-Verbindungen, Datenansichten und Projekte für Experience Platform Data Mirror für Customer Journey Analytics konfigurieren
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: f7687bba-efbe-4a2c-8ad1-cf216554a1e9
source-git-commit: b2a13524760f9d466696534bc8b9691f3b4dfb8a
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 2%

---

# Konfigurieren von Customer Journey Analytics

{{release-limited-testing}}

{{relational-model-based}}

Um die Experience Platform Data Mirror-Funktion für Customer Journey Analytics verwenden zu können, müssen Sie Verbindungen, Datenansichten und Arbeitsbereich-Projekte erstellen oder aktualisieren, um relationale Daten zu verwenden.

## Verbindungen

Fügen Sie Ihrer Verbindung die relationalen Datensätze hinzu, die die Daten aus den Data Warehouse-nativen Lösungen darstellen. Diese Datensätze haben den Typ „Relationaler Datensatz“.

Wenn Sie einen relationalen Datensatz hinzufügen, der gespiegelte Daten aus einer Data Warehouse-nativen Lösung enthält, sind diese Daten normalerweise Ereignisdaten. Stellen Sie sicher, dass Sie die richtigen Einstellungen für den Datensatz auswählen. Wählen Sie beispielsweise den richtigen Datensatztyp, das Feld für Identität und das Feld für Zeitstempel aus.


## Datenansichten

Definieren Sie Felder aus dem relationalen Schema als Komponenten (Metriken und Dimensionen) in Ihrer Datenansicht. Die gespiegelten Datenfelder sind im Unterordner **[!UICONTROL Ad-hoc- und relationale Felder]** des Ordners **[!UICONTROL Ereignisdatensätze]** verfügbar. Verwenden Sie Funktionen wie [abgeleitete Felder](/help/data-views/derived-fields/derived-fields.md) oder [Komponenteneinstellungen](/help/data-views/component-settings/overview.md) zum Ändern der Komponenten, die auf relationalen Feldern basieren.


## Workspace-Projekte

Richten Sie Workspace-Projekte ein, die Metriken und Dimensionen aus Ihren relationalen Daten verwenden. Komponenten, die letztendlich auf den Daten in Ihrer Data Warehouse-nativen Lösung basieren. und werden auf der Grundlage der von Ihnen konfigurierten Datenspiegelungsfunktion aktualisiert.

>[!MORELIKETHIS]
>
>[Data Mirror-Schnellstartanleitung: Spiegeln und Verwenden von relationalen Daten](relational.md)
>
