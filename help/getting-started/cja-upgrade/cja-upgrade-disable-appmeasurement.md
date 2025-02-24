---
title: Hinzufügen des Datensatzes des Analytics-Quell-Connectors zur Verbindung
description: Erfahren Sie, wie Sie den Analytics-Quell-Connector-Datensatz zur Verbindung hinzufügen
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 71b9da74-3597-4536-9e47-f18097dd917b
source-git-commit: 9cfe89aef069d777424eb8a5d9ef8ae03a9d0486
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 43%

---

# Adobe Analytics deaktivieren {#disable-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement"
>title="AppMeasurement-Datenerfassung deaktivieren"
>abstract="Wenn die Web SDK-Daten voll funktionsfähig sind, arbeiten Sie mit Ihrem Entwickler-Team zusammen, um AppMeasurement.js aus Ihrer Website oder Eigenschaft zu entfernen.<br><br>Das Entfernen von AppMeasurement aus einer Website dauert nur wenige Minuten, verlangt Ihrem Engineering-Team allerdings Zeit ab, um den Vorgang abzuschließen. Stellen Sie aber sicher, dass Ihre Analytics-Benutzenden Customer Journey Analytics und nicht Adobe Analytics verwenden. Dieser Ankündigungsprozess, dass alle Benutzenden migriert werden, kann deutlich länger dauern, sofern dies noch nicht geschehen ist."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Befolgen Sie die Schritte auf dieser Seite erst, nachdem Sie alle vorherigen Upgrade-Schritte abgeschlossen haben. Sie können die [empfohlenen Upgrade-Schritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die Upgrade-Schritte ausführen, die für Ihr Unternehmen mit dem Fragebogen [Upgrade von Adobe Analytics auf Customer Journey Analytics dynamisch generiert ](https://gigazelle.github.io/cja-ttv/).
>
>Nachdem Sie die Schritte auf dieser Seite abgeschlossen haben, folgen Sie den empfohlenen Upgrade-Schritten oder den dynamisch generierten Upgrade-Schritten.

Lesen Sie vor dem Deaktivieren von Adobe Analytics die Informationen unter [Evaluieren Sie, wann Adobe Analytics nach dem Upgrade auf Customer Journey Analytics deaktiviert werden soll](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md).

* **Tags:** Deaktivieren der Adobe Analytics-Erweiterung

* **AppMeasurment:** Ersetzen Sie die Bibliothek &quot;AppMeasurement.js“ s=newObject
