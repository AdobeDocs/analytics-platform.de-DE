---
title: Datensätze für B2B-Suchen transformieren
description: Beschreibt, wie Daten in Datensätze spezifischer B2B-Lookup-Schemas umgewandelt werden
solution: Customer Journey Analytics
feature: Connections
role: Admin
exl-id: 7729c1b9-b3ed-4662-a446-2088389bbd97
source-git-commit: 6e50e9341c2eedd6e4882cc3eb943cbcb8dfc332
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 0%

---

# Datensätze für B2B-Suchen transformieren

Um personenbasierte Suchen nach B2B-Daten (einschließlich Konten, Chancen, Marketinglisten und Kampagnen) zu unterstützen, ist eine Transformation von B2B-Lookup-Datensätzen erforderlich.

Diese Umwandlung ist nur für Datensätze mit Daten für B2B-Lookup-Schemas verfügbar, die auf den folgenden Klassen basieren:

* [Personenbeziehung zwischen XDM-Geschäftskonto](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-account-person-relation)
* [XDM Business Opportunity-Personenbeziehung](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-opportunity-person-relation)
* [XDM Business Marketing List-Mitglieder](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-marketing-list-members)
* [XDM Business Campaign-Mitglieder](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-campaign-members)

So aktivieren Sie die Transformation für einen solchen Datensatz:

![Datensatz umwandeln aktivieren](assets/transform-dataset.gif)

* Stellen Sie sicher, dass Sie die richtige Kennung für **[!UICONTROL Schlüssel]** und **[!UICONTROL Übereinstimmungsschlüssel]**, beispielsweise `personKey.sourceKey`.

* Wählen Sie die Optionen zum Importieren neuer Daten und zur Aufstockung des Datensatzes aus.

* Auswählen **[!UICONTROL Datensatz für B2B-Suchen transformieren]**.

  Mit dieser Option wird der Datensatz so transformiert, dass er für personenbasierte Suchen in B2B-Szenarien verwendet werden kann.


  >[!IMPORTANT]
  >
  >Nach der Aktivierung und beim Speichern der Verbindung ist die Umwandlung unumkehrbar. Sie können die Umwandlungseinstellung für einen Datensatz nach dem Speichern einer Verbindung nicht mehr ändern, außer indem Sie den Datensatz erneut entfernen und zur Verbindung hinzufügen.

So aktivieren Sie die Transformation für einen oder mehrere Datensätze, die bereits Teil einer vorhandenen Verbindung sind:

1. Entfernen Sie die Datensätze aus der Verbindung.
1. Speichern Sie die Verbindung.
1. Fügen Sie die Datensätze zur Verbindung hinzu, während Sie die Transformation für die Datensätze aktivieren

## Hintergrundinformationen

Nicht transformierte Datensätze können für Schemas, die auf den oben genannten vier Schemaklassen basieren, mehrere Zeilen für eine einzelne Personenkennung enthalten. Die personenbasierten Suchen entsprechen nur dem neuesten Vorkommen dieser Personen-ID, wodurch eine ordnungsgemäße, auf der Personen-ID basierende Suche nach Konten, Chancen, Marketinglisten oder Kampagnen verhindert wird.

Durch die Umwandlung wird der Datensatz jeder der vier Schemaklassen geändert (orange in der Abbildung unten), sodass für jede Personenkennung ein (Objekt-)Array für die relevanten Daten (Konten, Chancen, Marketinglisten oder Kampagnen) in den Lookup-Datensätzen erstellt wird (rosa in der Abbildung unten). Diese Umwandlung ermöglicht eine korrekte Funktionsweise von Personen-ID-basierten Suchen.

![B2B-Schemata](./assets/b2b-schemas.svg)
