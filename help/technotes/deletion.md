---
title: Auswirkungen des Löschens
description: Machen Sie sich mit den Auswirkungen des Löschens oder Zurücksetzens von Customer Journey Analytics- oder Experience Platform-Objekten vertraut.
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
role: Admin
TQID: https://experienceleague.adobe.com/95ZvIc4JM3aNY2zO6ypn-KmLrIdZ8DZga4vrOcl9Yzs
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
  - id: e4a0bad2-b448-47f1-9fa6-222ebdb3b5b0
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 965
ht-degree: 9%

---

# Auswirkungen des Löschens und Zurücksetzens

Das Löschen oder Zurücksetzen von Customer Journey Analytics- oder Experience Platform-Objekten hat keine Auswirkungen. Diese Auswirkungen werden in diesem Artikel beschrieben.

## Customer Journey Analytics

Beachten Sie die folgenden Auswirkungen, bevor Sie Verbindungen, Datenansichten oder Datensätze in Customer Journey Analytics löschen:

| Aktion | Implikationen |
| --- | --- |
| Löschen einer Verbindung in [!UICONTROL Customer Journey Analytics] | Eine Fehlermeldung weist auf Folgendes hin:<ul><li>Für die gelöschte Verbindung erstellte Datenansichten funktionieren nicht mehr.</li><li> Ebenso funktionieren alle Workspace-Projekte nicht mehr, die von den Datenansichten der gelöschten Verbindung abhängig sind.</li></ul><p>Beachten Sie, dass Sie Customer Journey Analytics-Verbindungen mit folgenden Merkmalen nicht löschen können:</p><ul><li>sind an Adobe Experience Platform-Sandboxes gebunden, für die Sie keine Berechtigungen haben. Selbst wenn Sie Berechtigungen für die auf diesen Verbindungen aufbauenden Datenansichten haben, können Sie die Verbindungen erst löschen, nachdem Sie Berechtigungen für die zugrunde liegenden Adobe Experience Platform-Sandboxes erhalten haben.</li><li>Lassen Sie die folgende Kompatibilitätsoption für eine Datenansicht auswählen, die mit der Verbindung verknüpft ist: **[!UICONTROL Als Standard-Datenansicht in Adobe Journey Optimizer festlegen]**<p>Weitere Informationen zu dieser Konfigurationsoption finden Sie unter [Kompatibilität](/help/data-views/create-dataview.md#compatibility) in [Erstellen oder Bearbeiten einer Datenansicht](/help/data-views/create-dataview.md).</p></li><li>werden in einer Konfiguration für einen der folgenden Dienste verwendet:<ul><li>[Zielgruppenanalyse](/help/connections/audience-analysis/audience-analysis-overview.md): Stellt Zielgruppendaten für Customer Journey Analytics zur eingehenden Analyse bereit</li><li>[Adobe Content Analytics](/help/content-analytics/content-analytics.md): Stellt Daten über die Nutzung von Inhalten und ihre Auswirkungen auf Customer Journey Analytics bereit</li></ul><p>Bevor Sie die Verbindung löschen können, müssen Sie zunächst die Konfiguration löschen oder bearbeiten, die diese Verbindung verwendet.</p></li></ul> |
| Löschen eines Datensatzes in [!UICONTROL Customer Journey Analytics] | Wenn Sie einen Datensatz aus einer Verbindung in Customer Journey Analytics löschen, funktionieren alle Datenansichten und Projekte, die auf diesen Datensatz angewiesen sind, nicht mehr. |
| Löschen einer Datenansicht in [!UICONTROL Customer Journey Analytics] | Wenn Sie eine Datenansicht in Customer Journey Analytics löschen, funktioniert jedes Bedienfeld in einem Workspace-Projekt, das sich auf die Datenansicht stützt, nicht mehr ordnungsgemäß.<p>Beachten Sie, dass Sie Customer Journey Analytics-Datenansichten, die in einer Konfiguration für einen der folgenden Services verwendet werden, nicht löschen können:</p><ul><li>[Zielgruppenanalyse](/help/connections/audience-analysis/audience-analysis-overview.md): Stellt Zielgruppendaten für Customer Journey Analytics zur eingehenden Analyse bereit</li><li>[Adobe Content Analytics](/help/content-analytics/content-analytics.md): Stellt Daten über die Nutzung von Inhalten und ihre Auswirkungen auf Customer Journey Analytics bereit</li></ul><p>Bevor Sie die Datenansicht löschen können, müssen Sie zunächst die Konfiguration löschen oder bearbeiten, die diese Datenansicht verwendet.</p></li></ul> |



## Experience Platform

Beachten Sie die folgenden Auswirkungen, bevor Sie Datensätze oder Batches löschen oder wenn Sie Sandboxes in Experience Platform zurücksetzen oder löschen:

| Aktion | Implikationen |
| --- | --- |
| Datensatz in [!UICONTROL Experience Platform löschen] | Der Datenfluss aus diesem Datensatz in Experience Platform stoppt zu allen Verbindungen, die diesen Datensatz enthalten. Daten aus diesem Datensatz werden automatisch aus den zugehörigen Customer Journey Analytics-Verbindungen gelöscht. |
| Löschen eines Batches aus einem Datensatz in [!UICONTROL Experience Platform] | Wenn ein Batch aus einem [!UICONTROL Adobe Experience Platform]-Datensatz gelöscht wird, wird derselbe Batch aus allen [!UICONTROL Customer Journey Analytics]-Verbindungen entfernt, die diesen spezifischen Batch enthalten. [!UICONTROL Customer Journey Analytics] wird über Batches benachrichtigt, die in [!UICONTROL Adobe Experience Platform] gelöscht wurden. |
| Löschen eines Batches aus [!UICONTROL Experience Platform] **während er aufgenommen wird** in [!UICONTROL Customer Journey Analytics] | Wenn nur ein Batch im Datensatz vorhanden ist, erscheinen keine Daten oder Teildaten aus diesem Batch in [!UICONTROL Customer Journey Analytics]. Die Aufnahme wird zurückgesetzt. Wenn sich beispielsweise im Datensatz fünf Batches befinden und drei von ihnen bereits aufgenommen wurden, als der vierte Batch gelöscht wurde, erscheinen Daten aus diesen drei Batches in [!UICONTROL Customer Journey Analytics]. |
| Lookup-Datensätze in [!UICONTROL Experience Platform &#x200B;] | Das Löschen von Datensätzen ist zwar für andere Quell-Connectoren möglich, das Löschen von [Analytics Classifications Source Connector](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications)-Datensätzen wird jedoch nicht unterstützt. Wenn Sie einen solchen Datensatz versehentlich löschen, wenden Sie sich an die Kundenunterstützung. |
| Löschen oder Zurücksetzen einer Sandbox in Experience Platform | Wenn Sie [eine Experience Platform-Sandbox löschen](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/ui/user-guide#delete-a-sandbox) werden alle Schemata, Datensätze, Batches, Richtlinien und mehr in dieser Sandbox ebenfalls gelöscht. Die Sandbox existiert nicht mehr sowie die Sandbox-Kennung und der Sandbox-Name.<br/>Wenn Sie [eine Experience Platform-Sandbox zurücksetzen](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/ui/user-guide#reset-a-sandbox) werden alle Schemata, Datensätze, Batches, Richtlinien und mehr in dieser Sandbox gelöscht. Während der Name und die Berechtigungen der Sandbox unberührt bleiben, wird die Sandbox-Kennung nach Abschluss des Zurücksetzens geändert.<br/><br/>Customer Journey Analytics verwendet die Sandbox-Kennung und den Sandbox-Namen, um einer Sandbox eine Verbindung zuzuordnen. Das Ergebnis: <ul><li>Verbindungen, die mit der gelöschten oder zurückgesetzten Sandbox verknüpft sind, werden gelöscht.</li><li>Datenansichten (und alle Komponentendefinitionen, z. B. abgeleitete Felder, in der Datenansicht), die auf den gelöschten Verbindungen basieren, werden gelöscht.</li><li>Komponenten, die sich auf die gelöschten Datenansichten stützen, werden gelöscht. Beispielsweise Segmente, berechnete Metriken, Anmerkungen, Warnhinweise, veröffentlichte Zielgruppen und Exporte.</li><li>Bedienfelder in Workspace-Projekten, die auf die gelöschten Datenansichten verweisen, werden unbrauchbar. In diesen Bereichen werden **[!UICONTROL Fehler mit unbekannter Datenansicht]** angezeigt. Entfernen Sie diese Bereiche oder verknüpfen Sie diese Bereiche nach Möglichkeit mit einer vorhandenen Datenansicht.</li><li>Sie sollten keine (historischen) Daten mehr aus der gelöschten Verbindung abfragen, die bereits in Customer Journey Analytics mit dem Abfrage-Service oder Tools, die auf der BI-Erweiterung basieren, verfügbar ist. Schließlich löscht der Adobe-Support oder das Engineering diese Daten aus Customer Journey Analytics.</li></ul>Da das Zurücksetzen oder Löschen einer Sandbox in Experience Platform erhebliche Auswirkungen hat, sollten Sie Folgendes berücksichtigen, bevor Sie eine Sandbox zurücksetzen oder löschen:<ul><li>Listen Sie Ihre Verbindungen auf, um zu verstehen, welche Verbindungen zu welchen Sandboxes gehören.</li><li>Listen Sie Datenansichten auf, um zu verstehen, welche Datenansichten mit welchen Verbindungen verknüpft sind.</li><li>Identifizieren Sie wichtige Workspace-Projekte und verstehen Sie, auf welche Datenansichten diese Projekte in ihren Bedienfeldern verweisen.</li><li>Ermitteln Sie Integrationen mit Tools, die die BI-Erweiterung verwenden, und verstehen Sie, auf welche Datenansichten diese Integrationen angewiesen sind.</li></ul> |
