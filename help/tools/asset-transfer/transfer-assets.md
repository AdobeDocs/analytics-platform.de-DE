---
title: Übertragen von Assets
description: Erfahren Sie, wie Sie Komponenten von einem Benutzer auf einen anderen übertragen
role: Admin
solution: Customer Journey Analytics
exl-id: c5ed81ea-1d55-4193-9bb1-a2a93ebde91f
source-git-commit: daa07b603caa613ca49b61c2e8e461d558459f57
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 0%

---

# Übertragen von Assets

Mit dem Asset Transfer-Tool können Sie den Besitz von Assets an andere Benutzer übertragen. Assets kann Komponenten wie Projekte, Filter, Datumsbereiche, berechnete Metriken, Anmerkungen, Warnhinweise und geplante Projekte enthalten.

Assets sind häufig an einen einzelnen Eigentümer gebunden und können in einigen Fällen, z. B. bei Filtern und berechneten Metriken, nicht einmal von Administratoren bearbeitet oder freigegeben werden. Wenn Benutzer das Unternehmen verlassen oder sich ihre Rolle ändert, kann es erforderlich werden, das Eigentum an diesen Assets auf andere Benutzer zu übertragen, um Kontinuität und angemessenen Zugriff sicherzustellen.

## Zugriffsberechtigung

Für das Customer Journey Analytics ist die Berechtigung des Produktadministrators für die Asset-Übertragung erforderlich.

## Übertragen von Assets

1. Navigieren Sie in CJA zu **[!UICONTROL Tools]** > **[!UICONTROL Asset-Übertragung]**.

   ![Menüelement „Asset-Übertragung“](/help/tools/asset-transfer/assets/asset-transfer.png)

1. Suchen Sie **[!UICONTROL Dialogfeld]** Benutzer“ nach dem Benutzer, von dem Sie Assets übertragen möchten, und wählen Sie ihn aus.

   >[!IMPORTANT]
   >
   >Es kann nur eine 1:1-Übertragung von einem Benutzer zu einem anderen Benutzer durchgeführt werden. Eins-zu-viele- oder Viele-zu-eins-Übertragungen werden nicht unterstützt.


1. Nachdem Sie einen Benutzer ausgewählt haben, wird die Option Assets übertragen unten auf dem Bildschirm angezeigt.

   ![Menüoption](/help/tools/asset-transfer/assets/after-selection.png)

1. Klicken Sie auf **[!UICONTROL Assets übertragen]**.

1. Wählen Sie **[!UICONTROL Bildschirm „Assets]**&quot; zunächst den Empfänger aus, an den Sie Assets übertragen möchten.

1. Gehen Sie nun im linken Navigationsbereich durch jeden Komponentenordner, um einzelne Komponenten oder alle Assets in einem Ordner zum Übertragen auszuwählen.

   >[!NOTE]
   >
   >Beim Übertragen von Assets von einem Administrator auf einen Nicht-Administrator wird der Empfänger nicht auf einen Administrator aktualisiert.


   >[!NOTE]
   >
   >    Beim Übertragen von Assets, die auf andere Komponenten verweisen (z. B. Projekte, die auf andere Filter und berechnete Metriken verweisen), werden Komponenten, die nicht dem aktuellen Projektbesitzer gehören, nur für den Empfänger freigegeben. Das Eigentum an allen anderen Komponenten geht auf den Empfänger über.

1. Um _alle_ Assets in einem Ordner auszuwählen, aktivieren Sie das Kontrollkästchen neben **[!UICONTROL Name]** oben in der Tabelle.

   ![Zu übertragende Assets auswählen](/help/tools/asset-transfer/assets/select-assets.png)

1. Klicken Sie **[!UICONTROL oben]** auf „Übertragen“, nachdem Sie alle Ihre Auswahlen getroffen haben.

1. Klicken Sie **[!UICONTROL Bestätigen]** wenn die Bestätigungsmeldung angezeigt wird.

   >[!IMPORTANT]
   >
   >Den Bildschirm während der Übertragung nicht schließen, um einen Abbruch des Prozesses zu vermeiden. Dies sorgt für ein reibungsloses Transfererlebnis.

## Übertragungsergebnisse

Es gibt drei mögliche Ergebnisse für eine Übertragung:

- **Übertragung erfolgreich**: &quot;Assets wurde erfolgreich übertragen.“

- **Teilweiser Erfolg**: „Einige Assets wurden erfolgreich übertragen.“

- **Übertragungsfehler**: „Assets konnten nicht übertragen werden. Bitte erneut versuchen.“

## Übertragen von Assets während des Upgrades von Adobe Analytics auf Customer Journey Analytics

Einer der wichtigsten Anwendungsfälle für die Asset-Übertragung ist das Upgrade von Adobe Analytics auf Customer Journey Analytics.

Mit [ Funktion „Komponentenmigration](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/component-migration) in Adobe Analytics können Projekte, für die Administratoren verantwortlich sind, zu anderen Administratoren migriert werden. Alle Komponenten dieser Projekte werden dann im Customer Journey Analytics neu erstellt, und der Empfängeradministrator ist für alle diese Komponenten verantwortlich, unabhängig davon, wer sie erstellt hat.

Mit diesem Asset Transfer Tool können Administratoren anschließend Komponenten ihren rechtmäßigen Besitzern neu zuweisen, unabhängig davon, ob sie Administratoren sind oder nicht.

>[!IMPORTANT]
>
>Sie können zwar Komponenten mit diesem Tool übertragen, aber als Administrator müssen Sie dennoch sicherstellen, dass der Empfänger Zugriff auf die Datenansichten hat, die zum Anzeigen/Verwenden dieser Komponenten erforderlich sind. In der Admin Console [ können Sie Berechtigungen anzeigen und zuweisen](https://helpx.adobe.com/de/enterprise/using/admin-console.html).

## In CSV exportieren

Mit **[!UICONTROL Option „In CSV exportieren]** können Administratoren nur eine Liste der in einer CSV-Datei angezeigten Benutzer herunterladen. Sie können keine Liste der übertragenen Assets in eine CSV-Datei exportieren.

<!---## Unknown users

All previously deleted users appear under one unknown user entry, along with all their orphan components. These components can be transferred to a new recipient. This feature will be available in January.-->
