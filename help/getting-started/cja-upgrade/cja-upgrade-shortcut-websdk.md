---
title: Upgrade-Tastaturbefehl Migrieren einer AppMeasurement- oder Analytics-Erweiterungsimplementierung zur Verwendung der Web-SDK
description: Erfahren Sie mehr über den empfohlenen Pfad beim Upgrade von Adobe Analytics auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 83927cf0-b3b4-42b4-9ca5-0c81c091383f
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 58%

---

# Schnellverfahren zur Aktualisierung: Migrieren der Implementierung einer AppMeasurement- oder Analytics-Erweiterung zur Web SDK-Verwendung {#shortcut-migrate-websdk}

>[!NOTE]
>
>Diese Dokumentation sollte als Teil des Fragebogens zum [Upgrade von Adobe Analytics auf Customer Journey Analytics verwendet werden](https://gigazelle.github.io/cja-ttv/).

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_migrate_aa_to_websdk"
>title="Migrieren der Analytics-Implementierung zur Web SDK-Verwendung"
>abstract="Statt Daten über ein XDM-Objekt zu senden, können Sie alle Variablen im AppMeasurement-Format über das Datenobjekt senden. Mit diesem Schnellverfahren können Sie weiterhin Ihre AppMeasurement-Logik verwenden, um Daten an Platform zu senden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migrate_aa_to_websdk"
>title="Migrieren der Analytics-Implementierung zur Web SDK-Verwendung"
>abstract="Statt Daten über ein XDM-Objekt zu senden, können Sie alle Variablen im AppMeasurement-Format über das Datenobjekt senden. Mit diesem Schnellverfahren können Sie weiterhin Ihre AppMeasurement-Logik verwenden, um Daten an Platform zu senden."

<!-- markdownlint-enable MD034 -->

Beim Upgrade auf Customer Journey Analytics empfiehlt Adobe [eine neue Implementierung des Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). Abhängig von verschiedenen Faktoren, wie z. B. Timeline- und Ressourcenbeschränkungen, sind die empfohlenen Upgrade-Schritte für Ihr Unternehmen möglicherweise nicht praktikabel.

Wenn es sich bei Ihrer Adobe Analytics-Implementierung um AppMeasurement oder die Analytics-Erweiterung handelt, ist eine Aktualisierungsverknüpfung verfügbar, mit der Sie Ihre Adobe Analytics-Implementierung migrieren können, um die Adobe Experience Platform Web SDK zu verwenden, damit Sie Daten an Edge Network und Adobe Analytics senden können, bevor Sie sie an Customer Journey Analytics senden.

## Vor- und Nachteile

Beachten Sie die folgenden Vor- und Nachteile des Upgrade-Tastaturbefehls, um Ihre AppMeasurement- oder Analytics-Erweiterungsimplementierung zur Verwendung der Web-SDK zu migrieren:

| Vorteile | Nachteile |
|----------|---------|
| <ul><li>**Bietet alle Vorteile des Hostings von Daten in Experience Edge Network**: <p>Dazu gehören:</p><ul><li>Reporting und Datenverfügbarkeit sind hochperformant, da Adobe Experience Platform zur Unterstützung von [Anwendungsfällen für die Echtzeit-Personalisierung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=de) entwickelt wurde. </li><li>Sie können die Implementierung für die Adobe Experience Cloud-Datenerfassung zwischen anderen Experience Cloud-Produkten (AJO, RTCDP usw.) konsolidieren.</li><li>Es besteht keine Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar, Ereignis usw.).</li></ul><li>**Nutzt Ihre vorhandene Implementierung**: Dieser Ansatz erfordert zwar einige Implementierungsänderungen, aber keine völlig neue Implementierung. Sie können die vorhandene Datenschicht und den bestehenden Code mit minimal geänderter Implementierungslogik verwenden, ohne dass sich dies auf Ihre vorhandenen Adobe Analytics-Berichte auswirkt.</li><li>**Bietet Flexibilität zum späteren Erstellen eines XDM-Schemas für Ihre Organisation**: Sie können Ihre vorhandene Adobe Analytics-Implementierung zur Nutzung des Web SDK migrieren und überprüfen, ob alles in Adobe Analytics funktioniert. Erstellen Sie dann das XDM-Schema. Diese Flexibilität ermöglicht ein methodischeres und durchdachtes Upgrade auf Customer Journey Analytics.</li></ul> | <ul><li>**Erfordert eine Zuordnung zum Senden von Daten an Platform**: Wenn Ihre Organisation für die Verwendung von Customer Journey Analytics bereit ist, müssen Sie Daten an einen Datensatz in Adobe Experience Platform senden. Diese Aktion erfordert, dass jedes Feld im Datenobjekt ein Eintrag im Datastream-Zuordnungs-Tool ist, das es einem XDM-Schemafeld zuweist. Die Zuordnung muss nur einmal für diesen Workflow durchgeführt werden. Implementierungsänderungen sind nicht erforderlich. Es handelt sich jedoch um einen zusätzlichen Schritt, der beim Senden von Daten in ein XDM-Objekt nicht erforderlich ist.</li><li>**Technische Schulden**: Da dieser Ansatz eine modifizierte Form Ihrer vorhandenen Implementierung nutzt, kann es schwieriger sein, die Implementierungslogik nachzuverfolgen und bei Bedarf zukünftige Änderungen vorzunehmen. </li></ul> |

{style="table-layout:auto"}

## Grundlegende Schritte

Wenn Sie sich entscheiden, den Upgrade-Shortcut zu verwenden, um Ihre AppMeasurement- oder Analytics-Erweiterungsimplementierung zur Verwendung der Web-SDK zu migrieren, wird im [Fragebogen für die Aktualisierung von Adobe Analytics auf Customer Journey Analytics zu den dynamisch generierten Schritten für Ihr Unternehmen ein neuer ](https://gigazelle.github.io/cja-ttv/) hinzugefügt.

Die grundlegenden Schritte für die Migration einer AppMeasurement- oder Analytics-Erweiterungsimplementierung zur Verwendung der Web-SDK sind:

1. Senden von Daten an Platform.

   Wenn Sie bereits Daten mit Ihrer Adobe Analytics-Implementierung an Platform senden, ist dieser Schritt nicht erforderlich. Sie müssen lediglich eine Verbindung zwischen Platform-Datensätzen und Customer Journey Analytics herstellen, wie weiter unten in diesem Prozess beschrieben.

1. (Optional) Erstellen Sie ein XDM-Schema für Ihre Organisation, wenn Sie Zeit dazu haben.

1. (Bedingt) Wenn Sie ein XDM-Schema erstellt haben, verwenden Sie die Datastream-Zuordnung, um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen.
