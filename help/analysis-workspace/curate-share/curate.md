---
description: Erfahren Sie, wie Sie Projekte in Analysis Workspace kuratieren. Die Kuratierung beschränkt den Zugriff auf Komponenten, bevor Sie ein Projekt freigeben.
keywords: Analysis Workspace-Kuratierung
title: Kuratieren von Projekten
feature: Curate and Share
exl-id: f9636191-8414-458c-9881-8c03f3d45efb
role: User
TQID: https://experienceleague.adobe.com/FX7KMzyOtrWzD-RUT-iEQZvJslmaes8dej76Jbj79OA
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 0145475e18cfbc3ae3a83e5e3838cdec02b57bda
workflow-type: tm+mt
source-wordcount: 517
ht-degree: 98%

---

# Kuratieren von Projekten

Mit der Kuratierung können Sie die Komponenten (Dimensionen, Metriken, Segmente, Datumsbereiche) vor der Freigabe eines Projekts einschränken. Wenn Empfangende das Projekt öffnen, wird ihnen eine begrenzte Anzahl an Komponenten angezeigt, die Sie für sie kuratiert haben. Die Kuratierung ist ein optionaler, aber empfehlenswerter Schritt, bevor Sie ein Projekt freigeben.

>[!NOTE]
> Produktprofile bestimmen als Hauptmechanismen, welche Komponenten ein Anwender sehen kann. Sie werden über die [CX Enterprise Admin Console](https://experienceleague.adobe.com/de/docs/core-services/interface/administration/admin-tool-experience-cloud) verwaltet. Kuratierung ist ein sekundäres Segment.

## Anwenden der Projektkuratierung

1. Wählen Sie **[!UICONTROL Freigeben]** > **[!UICONTROL Projektdaten kuratieren]** aus.
Die im Projekt verwendeten Komponenten werden automatisch hinzugefügt.
Wenn ein Projekt über mehrere Datenansichten verfügt, wird für jede Datenansicht im Projekt ein kuratiertes Ablageziel angezeigt.
1. (Optional) Um weitere Komponenten hinzuzufügen, ziehen Sie die freizugebenden Komponenten aus dem linken Panel in den Ablagebereich **[!UICONTROL Komponenten kuratieren]** der Datenansicht.
1. Wählen Sie **[!UICONTROL Fertig]** aus.

<!--
Curation can also be applied from the [!UICONTROL Share] menu by selecting **[!UICONTROL Curate and Share]**. This option automatically curates the project to the components in use in the project. You can add additional components following the steps above.
-->

![Das Fenster „Komponenten kuratieren“ mit den im Projekt verwendeten Komponenten.](assets/curation-field.png)

Wenn Empfangende ein kuratiertes Projekt öffnen, werden ihnen nur die von Ihnen definierten kuratierten Komponenten angezeigt:


## Entfernen der Projektkuratierung

So entfernen Sie die Projektkuratierung und stellen den vollständigen Satz der Komponenten im linken Panel wieder her:

1. Wählen Sie **[!UICONTROL Freigeben]** > **[!UICONTROL Projektdaten kuratieren]** aus.
1. Wählen Sie **[!UICONTROL Kuratierung entfernen]** aus.
1. Wählen Sie **[!UICONTROL Fertig]** aus.

## Optionen zur Komponentenkuratierung

In einem kuratierten Projekt wird der Empfängerin bzw. dem Empfänger im linken Panel die Option **[!UICONTROL Alle anzeigen]** für Komponenten angezeigt. [!UICONTROL Alle anzeigen] zeigt verschiedene Komponentensätze an, je nach:

* Berechtigungsebene der Person (Admin oder Nicht-Admin)
* Projektrolle (Inhaber/Bearbeiter oder nicht)
* Art der angewendeten Kuratierung (auf Projektebene)

| Kuratierungstyp | Admin hat Einsicht | Projektverantwortlicher ohne Administratorrechte (oder Bearbeitungsrolle) hat Einsicht | Duplizierte Rolle ohne Administratorrechte hat Einsicht |
| --- | --- | --- | --- |
| **In einer Datenansicht *ausgeblendete* Komponenten** | Alle Datenansichtskomponenten sind für das Reporting verfügbar (zum Anzeigen von ausgeblendeten Komponenten müssen Sie **[!UICONTROL Alle anzeigen]** auswählen) | Nicht für die Berichterstellung verfügbar | Nicht für die Berichterstellung verfügbar |
| **Komponenten, die zur Datenansicht hinzugefügt oder daraus entfernt wurden** | Nur Komponenten, die zur Datenansicht hinzugefügt wurden (ausgeblendet oder nicht ausgeblendet). Admins können keine Berichte zu Feldern oder Komponenten erstellen, die nicht in der Datenansicht definiert sind. | Nur Komponenten, die zur Datenansicht hinzugefügt wurden, oder Komponenten, für die die jeweilige Person verantwortlich ist oder die für sie freigegeben wurden. Ausgeblendete Komponenten sind nicht verfügbar (wie bei der Virtual Report Suite-Kuratierung). | Nur zur Datenansicht hinzugefügte Komponenten sind nicht ausgeblendet und werden bei der Projektkuratierung berücksichtigt. |
| **Kuratierte Komponenten in einem Projekt** | Alle für das Reporting verfügbaren Datenansichtskomponenten (zum Anzeigen von ausgeblendeten Komponenten müssen Sie **[!UICONTROL Alle anzeigen]** auswählen) | Alle nicht ausgeblendeten Datenansichtskomponenten (erfordert das Klicken auf „Alle anzeigen“) | Nur kuratierte Komponenten sowie alle Komponenten, für die der Benutzer verantwortlich ist oder die für ihn freigegeben wurden |
| **Kuratiertes Projekt mit einer Datenansicht mit ausgeblendeten Komponenten** | Alle für das Reporting verfügbaren Datenkomponenten (zum Anzeigen von ausgeblendeten und nicht kuratierten Komponenten müssen Sie **[!UICONTROL Alle anzeigen]** auswählen) | Alle nicht kuratierten Projektkomponenten, alle nicht ausgeblendeten Datenansichtskomponenten und alle Komponenten, für die der Benutzer verantwortlich ist oder die für ihn freigegeben wurden | Nur kuratierte Komponenten sowie alle Komponenten, für die der Benutzer verantwortlich ist oder die für ihn freigegeben wurden |
