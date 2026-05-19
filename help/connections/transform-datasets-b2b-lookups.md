---
title: Transformieren von Datensätzen für B2B-Suchen
description: Beschreibt, wie Daten in Datensätzen bestimmter B2B-Lookup-Schemata transformiert werden
solution: Customer Journey Analytics
feature: Connections
role: Admin
exl-id: 7729c1b9-b3ed-4662-a446-2088389bbd97
TQID: https://experienceleague.adobe.com/I7-bKS2jErVibrBHHfItc9oivAy1TJaVtKs7U3pSS78
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: d682e1e729402bff7a3f6e3625402f57deee21ad
workflow-type: tm+mt
source-wordcount: 521
ht-degree: 10%

---

# Transformieren der Datensätze für B2B-Suchvorgänge

Um personenbasierte Suchen nach B2B-Daten (einschließlich Konten, Opportunitys, Marketing-Listen und Kampagnen) zu unterstützen, kann die Transformation von B2B-Lookup-Datensätzen die Datengenauigkeit verbessern.

Diese Umwandlung ist nur für Datensätze mit Daten für B2B-Lookup-Schemas verfügbar, die auf den folgenden Klassen basieren:

* [XDM Business Account Person Relation](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-account-person-relation)
* [XDM Business Opportunity Person Relation](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-opportunity-person-relation)
* [XDM Business Marketing List Members](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-marketing-list-members)
* [XDM Business Campaign Members](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-campaign-members)

>[!NOTE]
>
>Pro ID sind maximal 10.000 Elemente zulässig. Diese Einschränkung bedeutet, dass Sie für jede Personen-ID nur über 10.000 Konten oder 10.000 Opportunitys oder 10.000 Marketing-Listen oder 10.000 Kampagnen verfügen können.

>[!PREREQUISITES]
>
>Damit die Aufnahme ordnungsgemäß funktioniert, müssen Sie überprüfen, ob die B2B-Lookup-Datensätze Daten für die folgenden Felder enthalten (wie in den B2B-Lookup-Schemata definiert):
>
>| Datensatz, der schemakonforme Daten enthält | Mit Daten ausgefülltes Feld |
>|---|---|
>| XDM Business Account Person Relation | `accountPersonID` |
>| XDM Business-Opportunity-Person | `opportunityPersonID` |
>| XDM Business Marketing List | `marketingListMemberID` |
>| XDM Business Campaign Members | `campaign.sourceKey` |
>

So aktivieren Sie die Umwandlung für einen B2B-Lookup-Datensatz:

![Transformations-Datensatz aktivieren](/help/connections/assets/transform.gif)

* Überprüfen Sie für jeden Datensatz die empfohlenen Werte für **[!UICONTROL Schlüssel]** und **[!UICONTROL Übereinstimmungsschlüssel]**. Wenn Sie die Werte von den vorgeschlagenen Werten ändern, wird eine Warnung angezeigt, die Sie auffordert, fortzufahren. Sie müssen Folgendes sicherstellen:

   * Der für „Schlüssel **ausgewählte Wert** auf dem Datentyp Personen-ID .
   * Der Wert, den Sie für **Übereinstimmungsschlüssel** auswählen, wird als primäres Identitätsfeld für den Ereignis-Datensatz definiert.

* Wählen Sie die Optionen für den Import neuer Daten und die Aufstockung des Datensatzes aus.

* Wählen Sie **[!UICONTROL Datensatz für B2B-Suchen umwandeln]** aus.

  Mit dieser Option wird der Datensatz transformiert, sodass er für personenbasierte Suchen in B2B-Szenarien verwendet werden kann.


  >[!IMPORTANT]
  >
  >Nach dem Einschalten und dem Speichern der Verbindung ist die Umwandlung unumkehrbar. Die Konfiguration von Schlüssel, übereinstimmendem Schlüssel und Transform-Datensatz kann nicht geändert werden. Sie können den Datensatz nur entfernen, hinzufügen und dann neu konfigurieren.

So aktivieren Sie die Umwandlung für einen oder mehrere Datensätze, die bereits Teil einer vorhandenen Verbindung sind:

1. Entfernen Sie die Datensätze aus der Verbindung.
1. Speichern Sie die Verbindung.
1. Fügen Sie die Datensätze zur Verbindung hinzu, während Sie die Umwandlung für die Datensätze aktivieren.

## Hintergrundinformationen

Nicht transformierte Datensätze für Schemata, die auf den vier oben genannten Schemaklassen basieren, können mehrere Zeilen für eine einzelne Personenkennung enthalten. Personenbasierte Suchen stimmen nur mit dem neuesten Vorkommen dieser Personenkennung überein, was eine ordnungsgemäße, auf Personen-ID basierende Suche von Konten, Opportunities, Marketing-Listen oder Kampagnen verhindert.

Die Transformation ändert den Datensatz jeder der vier Schemaklassen (orange in der unten stehenden Abbildung), sodass für jede Personenkennung ein (Objekt-)Array für die relevanten Daten (Konten, Opportunitys, Marketing-Listen oder Kampagnen) in den Lookup-Datensätzen erstellt wird (rosa in der unten stehenden Abbildung). Diese Umwandlung ermöglicht ein korrektes Arbeiten der Personen-ID-basierten Suchen.

![B2B-Schemata](./assets/b2b-schemas.png)
