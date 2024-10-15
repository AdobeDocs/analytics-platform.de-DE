---
title: Übertragen von Assets
description: Erfahren Sie, wie Sie Komponenten von einem Benutzer an einen anderen übertragen.
role: Admin
solution: Customer Journey Analytics
source-git-commit: 9663a24c2430d3822cb83876ea048b6423405215
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 0%

---


# Übertragen von Assets

Mit dem Asset Transfer-Tool können Sie das Eigentum an Assets an andere Benutzer übertragen. Assets kann Komponenten wie Projekte, Filter, Datumsbereiche, berechnete Metriken, Anmerkungen, Warnungen und geplante Projekte enthalten.

Assets sind häufig an einen einzelnen Eigentümer gebunden und können in manchen Fällen, z. B. Filter und berechnete Metriken, selbst von Administratoren nicht bearbeitet oder freigegeben werden. Wenn Benutzer die Organisation verlassen oder ihre Rolle geändert wird, kann es erforderlich werden, das Eigentum an diesen Assets an andere Benutzer zu übertragen, um Kontinuität und angemessenen Zugriff sicherzustellen.

## Zugriffsberechtigung

Für die Asset-Übertragung ist die Produktadministratorberechtigung für die Customer Journey Analytics erforderlich.

## Übertragen von Assets

1. Navigieren Sie in Customer Journey Analytics zu **[!UICONTROL Tools]** > **[!UICONTROL Asset-Übertragung]**.

   ![Menüelement &quot;Asset-Übertragung&quot;](/help/tools/asset-transfer/assets/asset-transfer.png)

1. Suchen Sie im Dialogfeld **[!UICONTROL Benutzer]** nach dem Benutzer, von dem Sie Assets übertragen möchten, und wählen Sie ihn aus.

   >[!IMPORTANT]
   >
   >Sie können nur eine 1:1-Übertragung von einem Benutzer an einen anderen durchführen. Eins-zu-viele- oder Eins-Übertragungen werden nicht unterstützt.


1. Nachdem Sie einen Benutzer ausgewählt haben, wird die Option Assets übertragen unten auf dem Bildschirm angezeigt.

   ![Menüoption](/help/tools/asset-transfer/assets/after-selection.png)

1. Klicken Sie auf **[!UICONTROL Assets übertragen]**.

1. Wählen Sie im Bildschirm **[!UICONTROL Assets übertragen]** zunächst den Empfänger aus, an den Sie Assets übertragen möchten.

1. Navigieren Sie nun in der linken Navigation durch jeden Komponentenordner, um einzelne Komponenten oder alle Assets in einem Ordner auszuwählen, die übertragen werden sollen.

   >[!NOTE]
   >
   >Durch die Übertragung von Assets von einem Administrator auf einen Benutzer ohne Administratorrechte wird der Empfänger nicht auf einen Administrator aktualisiert.


   >[!NOTE]
   >
   >    Bei der Übertragung von Assets, die auf andere Komponenten verweisen (z. B. Projekte, die auf andere Filter und berechnete Metriken verweisen), werden Komponenten, die nicht dem aktuellen Eigentümer des Projekts gehören, nur für den Empfänger freigegeben. Das Eigentum an allen anderen Komponenten wird auf den Empfänger übertragen.

1. Um _alle_ Assets in einem Ordner auszuwählen, aktivieren Sie das Kontrollkästchen neben **[!UICONTROL Name]** oben in der Tabelle.

   ![Assets auswählen, die übertragen werden sollen](/help/tools/asset-transfer/assets/select-assets.png)

1. Klicken Sie oben rechts auf **[!UICONTROL Übertragen]** , nachdem Sie alle Ihre Einstellungen vorgenommen haben.

1. Klicken Sie auf **[!UICONTROL Bestätigen]** , wenn die Bestätigungsmeldung angezeigt wird.

   >[!IMPORTANT]
   >
   >Schließen Sie den Bildschirm nicht während der Übertragung, um eine Abtreibung des Prozesses zu vermeiden. Dadurch wird eine reibungslose Übertragung gewährleistet.

## Übertragungsergebnisse

Es gibt drei mögliche Ergebnisse für eine Übertragung:

- **Transfer success**: &quot;Assets erfolgreich übertragen.&quot;

- **Teilweiser Erfolg**: &quot;Einige Assets wurden erfolgreich übertragen.&quot;

- **Übertragungsfehler**: &quot;Assets konnten nicht übertragen werden. Bitte versuchen Sie es erneut.&quot;

## Übertragen von Assets während der Aktualisierung von Adobe Analytics auf Customer Journey Analytics

Einer der wichtigsten Anwendungsfälle für die Asset-Übertragung ist das Upgrade von Adobe Analytics auf Customer Journey Analytics.

Mit der Funktion [Komponentenmigration](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/component-migration) in Adobe Analytics können Sie Projekte, die sich im Besitz von Administratoren befinden, zu anderen Administratoren migrieren. Alle Komponenten, aus denen diese Projekte bestehen, werden dann in Customer Journey Analytics neu erstellt und der Empfängeradministrator ist für alle diese Komponenten verantwortlich, unabhängig davon, wer sie erstellt hat.

Mit diesem Asset Transfer-Tool können Administratoren Komponenten ihren rechtmäßigen Eigentümern zuweisen, unabhängig davon, ob es sich um Administratoren handelt oder nicht.

>[!IMPORTANT]
>
>Während Sie Komponenten mit diesem Tool übertragen können, müssen Sie als Administrator dennoch sicherstellen, dass der Empfänger Zugriff auf die Datenansichten hat, die zum Anzeigen/Verwenden dieser Komponenten erforderlich sind. Sie können Berechtigungen in der [Admin Console](https://helpx.adobe.com/de/enterprise/using/admin-console.html) anzeigen und zuweisen.

## In CSV exportieren

Mit der Option **[!UICONTROL In CSV exportieren]** können Administratoren nur eine Liste von Benutzern herunterladen, die in einer CSV-Datei angezeigt werden. Sie können keine Liste der übertragenen Assets in eine CSV-Datei exportieren.

<!---## Unknown users

All previously deleted users appear under one unknown user entry, along with all their orphan components. These components can be transferred to a new recipient. This feature will be available in January.-->