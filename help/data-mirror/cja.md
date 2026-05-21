---
title: Konfigurieren von Customer Journey Analytics
description: Erfahren Sie, wie Sie Customer Journey Analytics-Verbindungen, Datenansichten und Projekte für Experience Platform Data Mirror für Customer Journey Analytics konfigurieren
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: f7687bba-efbe-4a2c-8ad1-cf216554a1e9
TQID: https://experienceleague.adobe.com/1LArX1cyRWpEY8O9xMwTcgwc0aUTjMrniFiDXtpkCNY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 231
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
