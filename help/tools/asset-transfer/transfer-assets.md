---
title: Übertragen von Assets
description: Erfahren Sie, wie Sie Komponenten von einem Benutzer auf einen anderen übertragen
role: Admin
solution: Customer Journey Analytics
exl-id: c5ed81ea-1d55-4193-9bb1-a2a93ebde91f
source-git-commit: 3e521cb4ef532d57b9f408fc12dcf138f130f059
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 0%

---

# Übertragen von Assets

Mit dem Asset Transfer-Tool können Sie den Besitz von Assets an andere Benutzer übertragen. Assets kann Komponenten wie Projekte, Segmente, Datumsbereiche, berechnete Metriken, Anmerkungen, Warnhinweise und geplante Projekte enthalten.

Assets sind häufig an einen einzelnen Eigentümer gebunden und können in einigen Fällen, z. B. bei Segmenten und berechneten Metriken, nicht einmal von Administratoren bearbeitet oder freigegeben werden. Wenn Benutzer das Unternehmen verlassen oder sich ihre Rolle ändert, kann es erforderlich werden, das Eigentum an diesen Assets auf andere Benutzer zu übertragen, um Kontinuität und angemessenen Zugriff sicherzustellen.

## Zugriffsberechtigungen

Für die Asset-Übertragung ist die Berechtigung eines Produktadministrators für Customer Journey Analytics erforderlich.

## Übertragen von Assets

1. Navigieren Sie in CJA zu **[!UICONTROL Tools]** > **[!UICONTROL Asset-Übertragung]**.

   ![Menüelement „Asset-Übertragung“](/help/tools/asset-transfer/assets/asset-transfer.png)

1. Suchen Sie **[!UICONTROL Dialogfeld]** Benutzer“ nach dem Benutzer, von dem Sie Assets übertragen möchten, und wählen Sie ihn aus.

   >[!IMPORTANT]
   >
   >Es kann nur eine 1:1-Übertragung von einem Benutzer zu einem anderen Benutzer durchgeführt werden. Eins-zu-viele- oder Viele-zu-eins-Übertragungen werden nicht unterstützt.


1. Nachdem Sie einen Benutzer ausgewählt haben, wird die Option Assets übertragen unten auf dem Bildschirm angezeigt.

   ![Menüoption „Assets übertragen“](/help/tools/asset-transfer/assets/after-selection.png)

1. Klicken Sie auf **[!UICONTROL Assets übertragen]**.

1. Wählen Sie **[!UICONTROL Bildschirm „Assets]**&quot; zunächst den Empfänger aus, an den Sie Assets übertragen möchten.

1. Gehen Sie nun im linken Navigationsbereich durch jeden Komponentenordner, um einzelne Komponenten oder alle Assets in einem Ordner zum Übertragen auszuwählen.

   >[!NOTE]
   >
   >Beim Übertragen von Assets von einem Administrator auf einen Nicht-Administrator wird der Empfänger nicht auf einen Administrator aktualisiert.


   >[!NOTE]
   >
   >    Beim Übertragen von Assets, die auf andere Komponenten verweisen (z. B. Projekte, die auf andere Segmente und berechnete Metriken verweisen), werden Komponenten, die nicht dem aktuellen Projektbesitzer gehören, nur für den Empfänger freigegeben. Das Eigentum an allen anderen Komponenten geht auf den Empfänger über.

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

### Mögliche Gründe für den Ausfall der Asset-Übertragung

- Abhängige Services, die Fehler verursachen: Die Asset-Übertragung interagiert für jeden Komponententyp mit einem anderen Service (z. B. Netzwerkprobleme, nachgelagerte Service-Probleme), was zu einem teilweisen oder vollständigen Fehler oder zeitweiligen Fehlern führen kann.

- Fehlende Komponente oder Übertragung durch einen anderen Administrator: Eine Komponente wurde von einem anderen Benutzer gelöscht oder von einem anderen Administrator an eine andere Person übertragen, während ein Asset-Übertragungsvorgang noch in Bearbeitung war.

- API-POST-Text wird nicht korrekt ausgefüllt: Eine Komponente wird möglicherweise nicht im API-POST-Text gesendet, wenn mehrere Komponententypen ausgewählt sind.

- Benutzer existiert nicht: Benutzer wurde während der Übertragung gelöscht oder ist aus einem anderen Grund ungültig. Wenn der Benutzer vor Beginn der Übertragung ungültig ist, erfasst das Tool dies und verarbeitet den Auftrag nicht. Wenn der Benutzer während der Übertragung gelöscht wurde, kann dies zu partiellen Fehlern führen.

- Verbindungs-/Netzwerkfehler: Verbindungs-Devices bei der Übertragung. Alle Batches von Übertragungsaufträgen, die bereits an das Backend übertragen wurden, werden weiterhin verarbeitet, aber der Benutzer sieht die Ergebnismeldung für die Übertragung nicht mit einer Zusammenfassung dessen, was erfolgreich war und was fehlgeschlagen ist.

- Browser-Registerkarte geschlossen Bei sehr großen Übertragungen werden Assets nur von den Netzwerkanfragen übertragen, die vor dem Schließen der Registerkarte bzw. der Seitennavigation erfolgen, wenn die Browser-Registerkarte geschlossen oder die Seite von der Mid-Transfer-Seite weg navigiert wird. Wenn der/die Benutzende zur Seite zurückkehrt, erhält er/sie nicht die Antwortstatusmeldung, die angibt, welche Assets übertragen wurden und welche nicht.

## Übertragen von Assets während des Upgrades von Adobe Analytics auf Customer Journey Analytics

Einer der wichtigsten Anwendungsfälle für die Asset-Übertragung ist das Upgrade von Adobe Analytics auf Customer Journey Analytics.

Mit [ Funktion „Komponentenmigration](https://experienceleague.adobe.com/de/docs/analytics/admin/admin-tools/component-migration/component-migration) in Adobe Analytics können Projekte, für die Administratoren verantwortlich sind, zu anderen Administratoren migriert werden. Alle Komponenten dieser Projekte werden dann in Customer Journey Analytics neu erstellt, und der Empfängeradministrator ist für alle diese Komponenten verantwortlich, unabhängig davon, wer sie erstellt hat.

Mit diesem Asset Transfer Tool können Administratoren anschließend Komponenten ihren rechtmäßigen Besitzern neu zuweisen, unabhängig davon, ob sie Administratoren sind oder nicht.

>[!IMPORTANT]
>
>Sie können zwar Komponenten mit diesem Tool übertragen, aber als Administrator müssen Sie dennoch sicherstellen, dass der Empfänger Zugriff auf die Datenansichten hat, die zum Anzeigen/Verwenden dieser Komponenten erforderlich sind. In der [Admin Console können Sie Berechtigungen anzeigen und zuweisen](https://helpx.adobe.com/de/enterprise/using/admin-console.html).

## In CSV exportieren

Mit **[!UICONTROL Option „In CSV exportieren]** können Administratoren nur eine Liste der in einer CSV-Datei angezeigten Benutzer herunterladen. Sie können keine Liste der übertragenen Assets in eine CSV-Datei exportieren.

## Inaktive Benutzende

Alle zuvor gelöschten Benutzer werden zusammen mit allen verwaisten Komponenten unter einem Eintrag „Inaktive Benutzer“ angezeigt. Diese Komponenten können an einen neuen Empfänger übertragen werden. Diese Funktion wird im Januar verfügbar sein.

![Inaktive Benutzer, die in der Benutzeroberfläche „Assets übertragen“ angezeigt werden](assets/inactive-users.png)

