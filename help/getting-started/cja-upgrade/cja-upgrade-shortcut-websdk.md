---
title: Aktualisierungskürzel Migrieren einer AppMeasurement- oder Analytics-Erweiterungsimplementierung zur Verwendung des Web SDK
description: Erfahren Sie mehr über den empfohlenen Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 83927cf0-b3b4-42b4-9ca5-0c81c091383f
source-git-commit: daa07b603caa613ca49b61c2e8e461d558459f57
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 56%

---

# Schnellverfahren zur Aktualisierung: Migrieren der Implementierung einer AppMeasurement- oder Analytics-Erweiterung zur Web SDK-Verwendung {#shortcut-migrate-websdk}

>[!NOTE]
>
>Diese Dokumentation sollte im Rahmen des Fragebogens [Adobe Analytics zum Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/) verwendet werden.

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_migrate_aa_to_websdk"
>title="Migrieren der Analytics-Implementierung zur Web SDK-Verwendung"
>abstract="Statt Daten über ein XDM-Objekt zu senden, können Sie alle Variablen im AppMeasurement-Format über das Datenobjekt senden. Mit diesem Schnellverfahren können Sie weiterhin Ihre AppMeasurement-Logik verwenden, um Daten an Platform zu senden."

<!-- markdownlint-enable MD034 -->

Beim Upgrade auf Customer Journey Analytics empfiehlt Adobe [eine neue Implementierung des Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). Je nach verschiedenen Faktoren, wie Timeline- und Ressourcenbeschränkungen, sind die empfohlenen Aktualisierungsschritte jedoch möglicherweise nicht für Ihr Unternehmen praktisch.

Wenn es sich bei Ihrer Adobe Analytics-Implementierung um AppMeasurement oder die Analytics-Erweiterung handelt, ist ein Upgrade-Tastaturbefehl verfügbar, mit dem Sie Ihre Adobe Analytics-Implementierung migrieren können, um das Adobe Experience Platform Web SDK zu verwenden, um mit dem Senden von Daten an Edge Network und Adobe Analytics zu beginnen, bevor sie an Customer Journey Analytics gesendet werden.

## Vorteile und Nachteile

Beachten Sie die folgenden Vorteile und Nachteile des Aktualisierungskürzels, um Ihre AppMeasurement- oder Analytics-Erweiterungsimplementierung zur Verwendung des Web SDK zu migrieren:

| Vorteile | Nachteile |
|----------|---------|
| <ul><li>**Bietet alle Vorteile des Hostings von Daten in Experience Edge Network**: <p>Dazu gehören:</p><ul><li>Reporting und Datenverfügbarkeit sind hochperformant, da Adobe Experience Platform zur Unterstützung von [Anwendungsfällen für die Echtzeit-Personalisierung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=de) entwickelt wurde. </li><li>Sie können die Implementierung für die Adobe Experience Cloud-Datenerfassung zwischen anderen Experience Cloud-Produkten (AJO, RTCDP usw.) konsolidieren.</li><li>Es besteht keine Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar, Ereignis usw.).</li></ul><li>**Nutzt Ihre vorhandene Implementierung**: Dieser Ansatz erfordert zwar einige Implementierungsänderungen, aber keine völlig neue Implementierung. Sie können die vorhandene Datenschicht und den bestehenden Code mit minimal geänderter Implementierungslogik verwenden, ohne dass sich dies auf Ihre vorhandenen Adobe Analytics-Berichte auswirkt.</li><li>**Bietet Flexibilität zum späteren Erstellen eines XDM-Schemas für Ihre Organisation**: Sie können Ihre vorhandene Adobe Analytics-Implementierung zur Nutzung des Web SDK migrieren und überprüfen, ob alles in Adobe Analytics funktioniert. Erstellen Sie dann das XDM-Schema. Diese Flexibilität ermöglicht eine methodischere und sorgfältigere Aktualisierung auf Customer Journey Analytics.</li></ul> | <ul><li>**Erfordert eine Zuordnung zum Senden von Daten an Platform**: Wenn Ihre Organisation für die Verwendung von Customer Journey Analytics bereit ist, müssen Sie Daten an einen Datensatz in Adobe Experience Platform senden. Diese Aktion erfordert, dass jedes Feld im Datenobjekt ein Eintrag im Datastream-Zuordnungs-Tool ist, das es einem XDM-Schemafeld zuweist. Die Zuordnung muss nur einmal für diesen Workflow durchgeführt werden. Implementierungsänderungen sind nicht erforderlich. Es handelt sich jedoch um einen zusätzlichen Schritt, der beim Senden von Daten in ein XDM-Objekt nicht erforderlich ist.</li><li>**Technische Schulden**: Da dieser Ansatz eine modifizierte Form Ihrer vorhandenen Implementierung nutzt, kann es schwieriger sein, die Implementierungslogik nachzuverfolgen und bei Bedarf zukünftige Änderungen vorzunehmen. </li></ul> |

{style="table-layout:auto"}

## Grundlegende Schritte

Wenn Sie den Upgrade-Tastaturbefehl verwenden, um Ihre AppMeasurement- oder Analytics-Erweiterungsimplementierung zur Verwendung des Web SDK zu migrieren, wird den dynamisch generierten Schritten für Ihr Unternehmen im Fragebogen für das Upgrade von [Adobe Analytics auf Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/) ein neuer Schritt hinzugefügt.

Die grundlegenden Schritte für die Migration einer AppMeasurement- oder Analytics-Erweiterungsimplementierung zur Verwendung des Web SDK sind:

1. Senden Sie Daten an Platform.

   Wenn Sie mit Ihrer Adobe Analytics-Implementierung bereits Daten an Platform senden, ist dieser Schritt nicht erforderlich. Sie müssen einfach eine Verbindung zwischen Platform-Datensätzen und Customer Journey Analytics erstellen, wie weiter unten in diesem Vorgang beschrieben.

1. (Optional) Erstellen Sie ein XDM-Schema für Ihre Organisation, wenn Sie Zeit dazu haben.

1. (Bedingt) Wenn Sie ein XDM-Schema erstellt haben, verwenden Sie die Datastream-Zuordnung, um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen.
