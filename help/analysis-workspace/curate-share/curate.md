---
description: Erfahren Sie, wie Sie Projekte in Analysis Workspace kuratieren. Die Kuratierung beschränkt den Zugriff auf Komponenten, bevor Sie ein Projekt freigeben.
keywords: Analysis Workspace-Kuratierung
title: Kuratieren von Projekten
feature: Curate and Share
exl-id: f9636191-8414-458c-9881-8c03f3d45efb
role: User
source-git-commit: 084c995658a5cf698d253f1c15229f621a8c55d5
workflow-type: ht
source-wordcount: '500'
ht-degree: 100%

---

# Kuratieren von Projekten

Mit der Kuratierung können Sie die Komponenten (Dimensionen, Metriken, Segmente, Datumsbereiche) vor der Freigabe eines Projekts einschränken. Wenn Empfangende das Projekt öffnen, wird ihnen eine begrenzte Anzahl an Komponenten angezeigt, die Sie für sie kuratiert haben. Die Kuratierung ist ein optionaler, aber empfehlenswerter Schritt, bevor Sie ein Projekt freigeben.

>[!NOTE]
> Produktprofile bestimmen als Hauptmechanismen, welche Komponenten ein Anwender sehen kann. Sie werden über die [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/de/docs/core-services/interface/administration/admin-tool-experience-cloud) verwaltet. Kuratierung ist ein sekundäres Segment.

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
