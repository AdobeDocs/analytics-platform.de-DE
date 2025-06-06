---
title: Übertragen von Assets
description: Weitere Informationen zum Übertragen von Komponenten zwischen Benutzenden
role: Admin
solution: Customer Journey Analytics
exl-id: c5ed81ea-1d55-4193-9bb1-a2a93ebde91f
source-git-commit: 3e521cb4ef532d57b9f408fc12dcf138f130f059
workflow-type: ht
source-wordcount: '831'
ht-degree: 100%

---

# Übertragen von Assets

Mit dem Tool „Asset-Übertragung“ können Sie die Eigentümerschaft von Assets auf andere Benutzende übertragen. Zu Assets können Komponenten wie Projekte, Segmente, Datumsbereiche, berechnete Metriken, Anmerkungen, Warnhinweise und geplante Projekte gehören.

Assets sind häufig an eine verantwortliche Person gebunden und können in einigen Fällen, z. B. bei Segmenten und berechneten Metriken, nicht einmal von Admins bearbeitet oder freigegeben werden. Wenn Benutzende die Organisation verlassen oder sich ihre Rolle ändert, kann es erforderlich werden, die Eigentümerschaft an diesen Assets auf andere Benutzende zu übertragen, um Kontinuität und einen angemessenen Zugriff sicherzustellen.

## Berechtigungen

Zur Asset-Übertragung ist eine Admin-Berechtigung für Customer Journey Analytics erforderlich.

## Übertragen von Assets

1. Navigieren Sie in CJA zu **[!UICONTROL Tools]** > **[!UICONTROL Asset-Übertragung]**.

   ![Menüelement „Asset-Übertragung“](/help/tools/asset-transfer/assets/asset-transfer.png)

1. Suchen Sie im Dialogfeld **[!UICONTROL Benutzende]** nach der Person, von der Assets übertragen werden sollen, und wählen Sie sie aus.

   >[!IMPORTANT]
   >
   >Zwischen Benutzenden ist ausschließlich eine 1:1-Übertragung möglich. 1:n- oder n:1-Übertragungen werden nicht unterstützt.


1. Nachdem Sie eine Benutzerin oder einen Benutzer ausgewählt haben, wird unten auf dem Bildschirm die Option „Assets transferieren“ angezeigt.

   ![Menüoption „Assets transferieren“](/help/tools/asset-transfer/assets/after-selection.png)

1. Klicken Sie auf **[!UICONTROL Assets transferieren]**.

1. Wählen Sie auf dem Bildschirm **[!UICONTROL Assets transferieren]** zunächst die empfangende Person für die Asset-Übertragung aus.

1. Gehen Sie nun im linken Navigationsbereich jeden Komponentenordner durch, um einzelne Komponenten oder alle Assets in einem Ordner zum Übertragen auszuwählen.

   >[!NOTE]
   >
   >Beim Übertragen von Assets von Admins auf Nicht-Admins wird die empfangende Person nicht auf Admin-Niveau hochgestuft.


   >[!NOTE]
   >
   >    Beim Übertragen von Assets, die auf andere Komponenten verweisen (z. B. Projekte, die auf andere Segmente und berechnete Metriken verweisen), werden Komponenten, die nicht der für das Projekt verantwortlichen Person gehören, nur für die empfangende Person freigegeben. Die Eigentümerschaft an allen anderen Komponenten wird auf die empfangende Person übertragen.

1. Um _alle_ Assets in einem Ordner auszuwählen, aktivieren Sie oben in der Tabelle das Kontrollkästchen neben **[!UICONTROL Name]**.

   ![Auswählen zu übertragender Assets](/help/tools/asset-transfer/assets/select-assets.png)

1. Klicken Sie oben rechts auf **[!UICONTROL Übertragen]**, nachdem Sie mit Ihrer Auswahl fertig sind.

1. Klicken Sie auf **[!UICONTROL Bestätigen]**, wenn die Bestätigungsmeldung angezeigt wird.

   >[!IMPORTANT]
   >
   >Schließen Sie den Bildschirm während der Übertragung nicht, um einen Prozessabbruch zu vermeiden. Dies sorgt für ein reibungsloses Erlebnis bei der Übertragung.

## Übertragungsergebnisse

Es gibt drei mögliche Ergebnisse einer Übertragung:

- **Übertragung erfolgreich**: „Assets erfolgreich übertragen.“

- **Teilweise erfolgreich**: „Einige Assets wurden erfolgreich übertragen.“

- **Übertragung fehlgeschlagen**: „Assets konnten nicht übertragen werden. Bitte versuchen Sie es erneut.“

### Mögliche Gründe für fehlgeschlagene Asset-Übertragungen

- Fehler durch abhängige Services: Die Asset-Übertragung interagiert bei jedem Komponententyp mit einem anderen Service (z. B. Netzwerkprobleme, nachgelagerte Service-Probleme), was zu einem teilweisen, vollständigen oder zeitweiligen Fehler führen kann.

- Fehlende Komponente oder Übertragung durch andere bzw. anderen Admin: Eine Komponente wurde während eines laufenden Asset-Übertragungsauftrags von einer anderen Person gelöscht oder von einer bzw. einem anderen Admin auf eine andere Person übertragen.

- Keine ordnungsgemäßes Auffüllen des API-POST-Texts: Eine Komponente wird möglicherweise nicht im API-POST-Text gesendet, wenn mehrere Komponententypen ausgewählt sind.

- Die oder der Benutzende existiert nicht: Die oder der Benutzende wurde während der Übertragung gelöscht oder ist aus einem anderen Grund ungültig. Wenn die oder der Benutzende vor Beginn der Übertragung ungültig ist, wird dies vom Tool erfasst und der Auftrag wird nicht verarbeitet. Wenn die oder der Benutzende während der Übertragung gelöscht wurde, kann dies zu teilweisen Fehlern führen.

- Verbindungs-/Netzwerkfehler: Die Verbindung wird während der Übertragung unterbrochen. Alle Batches von Übertragungsaufträgen, die bereits an das Backend übertragen wurden, werden weiterhin verarbeitet, aber die Meldung mit dem Übertragungsergebnis, die der bzw. dem Benutzenden angezeigt wird, enthält keine Zusammenfassung der erfolgreichen und fehlgeschlagenen Vorgänge.

- Schließen der Browser-Registerkarte während der Übertragung: Wenn während äußerst umfangreichen Übertragungen die Browser-Registerkarte geschlossen oder die Seite verlassen wird, werden Assets nur bei den Netzwerkanfragen ordnungsgemäß übertragen, die vor dem Schließen der Registerkarte bzw. vor der Seitennavigation erfolgt sind. Wenn die oder der Benutzende zur Seite zurückkehrt, erhält diese Person keine Antwortstatusmeldung dazu, welche Assets übertragen wurden und welche nicht.

## Übertragen von Assets während des Upgrades von Adobe Analytics auf Customer Journey Analytics

Einer der wichtigsten Anwendungsfälle für die Asset-Übertragung ist das Upgrade von Adobe Analytics auf Customer Journey Analytics.

Mit der Funktion [Komponenten-Migration](https://experienceleague.adobe.com/de/docs/analytics/admin/admin-tools/component-migration/component-migration) in Adobe Analytics können Sie Projekte, für die Admins verantwortlich sind, zu anderen Admins migrieren. Alle Komponenten dieser Projekte werden dann in Customer Journey Analytics neu erstellt, und die bzw. der empfangende Admin ist für alle diese Komponenten verantwortlich, unabhängig davon, wer sie erstellt hat.

Mit diesem Tool „Asset-Übertragung“ können Admins anschließend Komponenten ihren rechtmäßigen Besitzenden neu zuweisen, unabhängig davon, ob sie Admins sind oder nicht.

>[!IMPORTANT]
>
>Sie können mit diesem Tool zwar Komponenten übertragen, aber als Admin müssen Sie dennoch sicherstellen, dass der die Empfängerin bzw. der Empfänger Zugriff auf die Datenansichten hat, die zum Anzeigen/Verwenden dieser Komponenten erforderlich sind. In der [Admin Console](https://helpx.adobe.com/de/enterprise/using/admin-console.html) können Sie Berechtigungen anzeigen und zuweisen.

## Exportieren in CSV

Mit der Option **[!UICONTROL In CSV exportieren]** können Admins nur eine Liste der in einer CSV-Datei angezeigten Benutzenden herunterladen. Sie können keine Liste der übertragenen Assets in eine CSV-Datei exportieren.

## Inaktive Benutzende

Alle zuvor gelöschten Benutzenden werden zusammen mit allen verwaisten Komponenten unter einem Eintrag „Inaktive Benutzende“ angezeigt. Diese Komponenten können an eine neue Empfängerin bzw. einen neuen Empfänger übertragen werden. Diese Funktion wird im Januar verfügbar sein.

![Inaktive Benutzende, die in der Benutzeroberfläche „Assets übertragen“ angezeigt werden](assets/inactive-users.png)

