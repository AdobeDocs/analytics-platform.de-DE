---
description: Durch Kuratierung können Sie die Komponenten einschränken, bevor Sie ein Projekt freigeben.
keywords: Analysis Workspace-Kuratierung
title: Kuratieren von Projekten
feature: Curate and Share
exl-id: f9636191-8414-458c-9881-8c03f3d45efb
role: User
source-git-commit: de04792035aa7c235751019ee9f9fe5b74b9b102
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 83%

---

# Kuratieren von Projekten

Mit der Kuratierung können Sie die Komponenten (Dimensionen, Metriken, Filter, Datumsbereiche) vor der Freigabe eines Projekts einschränken. Wenn ein Empfänger das Projekt öffnet, wird ihm eine begrenzte Anzahl von Komponenten angezeigt, die Sie für ihn kuratiert haben. Die Kuratierung ist ein optionaler, aber empfehlenswerter Schritt, bevor Sie ein Projekt freigeben.

>[!NOTE]
> Produktprofile bestimmen als Hauptmechanismen, welche Komponenten ein Anwender sehen kann. Sie werden über die [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=de) verwaltet. Kuratierung ist ein Sekundärfilter.

## Anwenden der Projektkuratierung

1. Klicken Sie auf **[!UICONTROL Freigeben]** > **[!UICONTROL Projektdaten kuratieren]**.
Die im Projekt verwendeten Komponenten werden automatisch hinzugefügt.
1. (Optional) Um weitere Komponenten hinzuzufügen, ziehen Sie die freizugebenden Komponenten aus dem linken Bereich in das Feld [!UICONTROL Komponenten kuratieren] .
1. Klicken Sie auf **[!UICONTROL Fertig]**.

Eine Kuratierung kann auch über das Menü [!UICONTROL Freigeben] angewendet werden, indem Sie auf **[!UICONTROL Kuratieren und freigeben]** klicken. Diese Option kuratiert das Projekt automatisch auf die im Projekt verwendeten Komponenten. Sie können weitere Komponenten hinzufügen, wie oben beschrieben.

![Das Fenster &quot;Komponenten kuratieren&quot;mit den im Projekt verwendeten Komponenten.](assets/curation-field.png)

## Ansicht des kuratierten Projekts

Wenn ein Empfänger ein kuratiertes Projekt öffnet, wird ihm nur der ausgewählte Satz der von Ihnen definierten Komponenten angezeigt:

![Ein freigegebenes kuratiertes Projekt, das die von Ihnen definierten Komponenten anzeigt.](assets/curate-project.png)

## Entfernen der Projektkuratierung

So entfernen Sie die Projektkuratierung und stellen den vollständigen Satz von Komponenten im linken Bereich wieder her:

1. Klicken Sie auf **[!UICONTROL Freigeben]** > **[!UICONTROL Projektdaten kuratieren]**.
1. Klicken Sie auf **[!UICONTROL Kuratierung entfernen]**.
1. Klicken Sie auf **[!UICONTROL Fertig]**.

## Optionen zur Komponentenkuratierung

In einem kuratierten Projekt wird dem Empfänger im linken Bereich die Option für die Komponenten **[!UICONTROL Alle anzeigen]** angezeigt. [!UICONTROL Alle anzeigen] zeigt verschiedene Komponentensätze an, je nach:

* Berechtigungsebene der Person (Admin oder Nicht-Admin)
* Projektrolle (Inhaber/Bearbeiter oder nicht)
* Art der angewendeten Kuratierung (auf Projektebene)

| Kuratierungstyp | Admin hat Einsicht | Projektverantwortlicher ohne Administratorrechte (oder Bearbeitungsrolle) hat Einsicht | Duplizierte Rolle ohne Administratorrechte hat Einsicht |
| --- | --- | --- | --- |
| **Komponenten, die in einer Datenansicht „versteckt“ sind** | Alle für die Berichterstellung verfügbaren Datenansichtskomponenten (für ausgeblendete Komponenten ist das Klicken auf „Alle anzeigen“ erforderlich) | Nicht für die Berichterstellung verfügbar | Nicht für die Berichterstellung verfügbar |
| **Komponenten, die zur Datenansicht hinzugefügt oder daraus entfernt wurden** | Nur Komponenten, die zur Datenansicht hinzugefügt wurden (ausgeblendet oder nicht ausgeblendet). Administratoren können keine Berichte zu Feldern oder Komponenten erstellen, die nicht in der Datenansicht definiert sind. | Nur Komponenten, die zur Datenansicht hinzugefügt wurden, oder Komponenten, für die der Benutzer verantwortlich ist oder die für ihn freigegeben wurden. Ausgeblendete Komponenten sind nicht verfügbar (z. B. Kuratierung der Virtual Report Suite). | Nur Komponenten, die zum DV hinzugefügt wurden, sind nicht ausgeblendet und wurden in die Projektkuratierung aufgenommen. |
| **Kuratierte Komponenten in einem Projekt** | Alle für die Berichterstellung verfügbaren Datenansichtskomponenten (für ausgeblendete Komponenten ist das Klicken auf „Alle anzeigen“ erforderlich) | Alle nicht ausgeblendeten Datenansichtskomponenten (erfordert das Klicken auf „Alle anzeigen“) | Nur kuratierte Komponenten sowie alle Komponenten, für die der Benutzer verantwortlich ist oder die für ihn freigegeben wurden |
| **Kuratiertes Projekt mit einer Datenansicht mit ausgeblendeten Komponenten** | Alle für die Berichterstellung verfügbaren Datenkomponenten (für ausgeblendete und nicht kuratierte Komponenten ist das Klicken auf „Alle anzeigen“ erforderlich) | Alle nicht kuratierten Projektkomponenten, alle nicht ausgeblendeten Datenansichtskomponenten und alle Komponenten, für die der Benutzer verantwortlich ist oder die für ihn freigegeben wurden | Nur kuratierte Komponenten sowie alle Komponenten, für die der Benutzer verantwortlich ist oder die für ihn freigegeben wurden |
