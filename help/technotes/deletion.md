---
title: Auswirkungen des Löschens
description: Machen Sie sich mit den Auswirkungen des Löschens oder Zurücksetzens von Customer Journey Analytics- oder Experience Platform-Objekten vertraut.
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: c8b646b7e92663ed9c7e8454a336d25e34415cbe
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 11%

---

# Auswirkungen des Löschens und Zurücksetzens

Das Löschen oder Zurücksetzen von Customer Journey Analytics- oder Experience Platform-Objekten hat keine Auswirkungen. Diese Auswirkungen werden in diesem Artikel beschrieben.

## Customer Journey Analytics

Beachten Sie die folgenden Auswirkungen, bevor Sie Verbindungen, Datenansichten oder Datensätze in Customer Journey Analytics löschen:

| Aktion | Implikationen |
| --- | --- |
| Löschen einer Verbindung in [!UICONTROL Customer Journey Analytics] | Eine Fehlermeldung weist auf Folgendes hin:<ul><li>Für die gelöschte Verbindung erstellte Datenansichten funktionieren nicht mehr.</li><li> Ebenso funktionieren alle Workspace-Projekte nicht mehr, die von den Datenansichten der gelöschten Verbindung abhängig sind.</li></ul>Beachten Sie, dass Sie Customer Journey Analytics-Verbindungen mit folgenden Merkmalen nicht löschen können:<ul><li>sind an Adobe Experience Platform-Sandboxes gebunden, für die Sie keine Berechtigungen haben. Selbst wenn Sie Berechtigungen für die auf diesen Verbindungen aufbauenden Datenansichten haben, können Sie die Verbindungen erst löschen, nachdem Sie Berechtigungen für die zugrunde liegenden Adobe Experience Platform-Sandboxes erhalten haben.</li><li>Lassen Sie die folgende Kompatibilitätsoption für eine Datenansicht auswählen, die mit der Verbindung verknüpft ist: **[!UICONTROL Als Standard-Datenansicht in Adobe Journey Optimizer festlegen]**<p>Weitere Informationen zu dieser Konfigurationsoption finden Sie unter [Kompatibilität](/help/data-views/create-dataview.md#compatibility) in [Datenansicht erstellen oder bearbeiten](/help/data-views/create-dataview.md)</p></li></ul> |
| Löschen eines Datensatzes in [!UICONTROL Customer Journey Analytics] | Wenn Sie einen Datensatz aus einer Verbindung in Customer Journey Analytics löschen, funktionieren alle Datenansichten und Projekte, die auf diesen Datensatz angewiesen sind, nicht mehr. |
| Löschen einer Datenansicht in [!UICONTROL Customer Journey Analytics] | Wenn Sie eine Datenansicht in Customer Journey Analytics löschen, funktioniert jedes Bedienfeld in einem Workspace-Projekt, das sich auf die Datenansicht stützt, nicht mehr ordnungsgemäß. |



## Experience Platform

Beachten Sie die folgenden Auswirkungen, bevor Sie Datensätze oder Batches löschen oder wenn Sie Sandboxes in Experience Platform zurücksetzen oder löschen:

| Aktion | Implikationen |
| --- | --- |
| Datensatz in [!UICONTROL Experience Platform löschen] | Der Datenfluss aus diesem Datensatz in Experience Platform stoppt zu allen Verbindungen, die diesen Datensatz enthalten. Daten aus diesem Datensatz werden automatisch aus den zugehörigen Customer Journey Analytics-Verbindungen gelöscht. |
| Löschen eines Batches aus einem Datensatz in [!UICONTROL Experience Platform] | Wenn ein Batch aus einem [!UICONTROL Adobe Experience Platform]-Datensatz gelöscht wird, wird derselbe Batch aus allen [!UICONTROL Customer Journey Analytics]-Verbindungen entfernt, die diesen spezifischen Batch enthalten. [!UICONTROL Customer Journey Analytics] wird über Batches benachrichtigt, die in [!UICONTROL Adobe Experience Platform] gelöscht wurden. |
| Löschen eines Batches aus [!UICONTROL Experience Platform] **während er aufgenommen wird** in [!UICONTROL Customer Journey Analytics] | Wenn nur ein Batch im Datensatz vorhanden ist, erscheinen keine Daten oder Teildaten aus diesem Batch in [!UICONTROL Customer Journey Analytics]. Die Aufnahme wird zurückgesetzt. Wenn sich beispielsweise im Datensatz fünf Batches befinden und drei von ihnen bereits aufgenommen wurden, als der vierte Batch gelöscht wurde, erscheinen Daten aus diesen drei Batches in [!UICONTROL Customer Journey Analytics]. |
| Lookup-Datensätze in [!UICONTROL Experience Platform &#x200B;] | Das Löschen von Datensätzen ist zwar für andere Quell-Connectoren möglich, das Löschen von [Analytics Classifications Source Connector](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications)-Datensätzen wird jedoch nicht unterstützt. Wenn Sie einen solchen Datensatz versehentlich löschen, wenden Sie sich an die Kundenunterstützung. |
| Löschen oder Zurücksetzen einer Sandbox in Experience Platform | Wenn Sie [eine Experience Platform-Sandbox löschen](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/ui/user-guide#delete-a-sandbox) werden alle Schemata, Datensätze, Batches, Richtlinien und mehr in dieser Sandbox ebenfalls gelöscht. Die Sandbox existiert nicht mehr sowie die Sandbox-Kennung und der Sandbox-Name.<br/>Wenn Sie [eine Experience Platform-Sandbox zurücksetzen](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/ui/user-guide#reset-a-sandbox) werden alle Schemata, Datensätze, Batches, Richtlinien und mehr in dieser Sandbox gelöscht. Während der Name und die Berechtigungen der Sandbox unberührt bleiben, wird die Sandbox-Kennung nach Abschluss des Zurücksetzens geändert.<br/><br/>Customer Journey Analytics verwendet die Sandbox-Kennung und den Sandbox-Namen, um einer Sandbox eine Verbindung zuzuordnen. Das Ergebnis: <ul><li>Verbindungen, die mit der gelöschten oder zurückgesetzten Sandbox verknüpft sind, werden gelöscht.</li><li>Datenansichten (und alle Komponentendefinitionen, z. B. abgeleitete Felder, in der Datenansicht), die auf den gelöschten Verbindungen basieren, werden gelöscht.</li><li>Komponenten, die sich auf die gelöschten Datenansichten stützen, werden gelöscht. Beispielsweise Segmente, berechnete Metriken, Anmerkungen, Warnhinweise, veröffentlichte Zielgruppen und Exporte.</li><li>Bedienfelder in Workspace-Projekten, die auf die gelöschten Datenansichten verweisen, werden unbrauchbar. In diesen Bereichen werden **[!UICONTROL Fehler mit unbekannter Datenansicht]** angezeigt. Entfernen Sie diese Bereiche oder verknüpfen Sie diese Bereiche nach Möglichkeit mit einer vorhandenen Datenansicht.</li><li>Sie sollten keine (historischen) Daten mehr aus der gelöschten Verbindung abfragen, die bereits in Customer Journey Analytics mit dem Abfrage-Service oder Tools, die auf der BI-Erweiterung basieren, verfügbar ist. Schließlich löscht der Adobe-Support oder das Engineering diese Daten aus Customer Journey Analytics.</li></ul>Da das Zurücksetzen oder Löschen einer Sandbox in Experience Platform erhebliche Auswirkungen hat, sollten Sie Folgendes berücksichtigen, bevor Sie eine Sandbox zurücksetzen oder löschen:<ul><li>Listen Sie Ihre Verbindungen auf, um zu verstehen, welche Verbindungen zu welchen Sandboxes gehören.</li><li>Listen Sie Datenansichten auf, um zu verstehen, welche Datenansichten mit welchen Verbindungen verknüpft sind.</li><li>Identifizieren Sie wichtige Workspace-Projekte und verstehen Sie, auf welche Datenansichten diese Projekte in ihren Bedienfeldern verweisen.</li><li>Ermitteln Sie Integrationen mit Tools, die die BI-Erweiterung verwenden, und verstehen Sie, auf welche Datenansichten diese Integrationen angewiesen sind.</li></ul> |
