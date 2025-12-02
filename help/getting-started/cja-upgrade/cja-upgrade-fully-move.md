---
title: Beurteilen, wie lange Adobe Analytics nach dem Upgrade auf Customer Journey Analytics benötigt wird
description: Erfahren Sie, wie Sie beurteilen können, wie lange Sie Adobe Analytics nach dem Upgrade auf Customer Journey Analytics benötigen
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 7142ef84-66a6-49eb-938b-b67c9b65bf93
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 100%

---

# Beurteilen, wann Adobe Analytics nach dem Upgrade auf Customer Journey Analytics deaktiviert werden soll {#evaluate-aa-needs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-fully-move"
>title="Vollständiger Wechsel zu Customer Journey Analytics"
>abstract="(Empfohlen) Adobe empfiehlt den vollständigen Übergang von Adobe Analytics zu Customer Journey Analytics. Während der Übergangszeit sollten Sie Adobe Analytics zusammen mit Customer Journey Analytics ausführen, um nebeneinander Datenvergleiche durchzuführen. Wenn Sie mit den Daten zurechtkommen, können Sie Adobe Analytics deaktivieren."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-keep-aa"
>title="Beibehaltung beider Analytics-Produkte"
>abstract="(Nicht empfohlen) Wenn Sie sich hierfür entscheiden, umfasst Ihr Vertrag mit Adobe sowohl Adobe Analytics als auch Customer Journey Analytics. Im Laufe der Zeit kann das für Ihre Organisation teuer werden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-source-connector"
>title="Deaktivieren des Analytics-Quell-Connectors, um Daten ausschließlich aus der Web-SDK zu verwenden"
>abstract="Der Analytics-Quell-Connector wird verwendet, um einen direkten Datenvergleich, historische Daten und Zugriff auf einige Funktionen bereitzustellen, die in Customer Journey Analytics nicht vollständig verfügbar sind. Wenn Sie Adobe Analytics für diese Zwecke nicht mehr benötigen, können Sie den Analytics-Quell-Connector deaktivieren."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Die meisten Organisationen werden Adobe Analytics nach dem Upgrade auf Customer Journey Analytics letztendlich deaktivieren. Dies liegt an den Kosten und der Komplexität für die dauerhafte Nutzung von zwei Analytics-Umgebungen.

Adobe empfiehlt jedoch, die Adobe Analytics-Umgebung nach der Implementierung von Customer Journey Analytics noch eine gewisse Zeit lang in Betrieb zu halten. In den folgenden Abschnitten werden die Gründe dafür sowie der empfohlene Zeitpunkt für die Deaktivierung von Adobe Analytics beschrieben.

## Verwendung von Adobe Analytics während und nach einem Upgrade

Bei der Entscheidung, ob und wann Ihre Organisation Adobe Analytics deaktivieren sollte, sind die folgenden Verwendungszwecke von Adobe Analytics während und nach einem Upgrade auf Customer Journey Analytics zu berücksichtigen:

| Verwendung von Adobe Analytics während und nach dem Upgrade | Erklärung |
|---------|----------|
| Parallelen Datenvergleich durchführen | Adobe empfiehlt, die Adobe Analytics-Umgebung noch eine gewisse Zeit lang in Betrieb zu halten, wenn die neue Customer Journey Analytics-Umgebung bereits ausgeführt wird und Daten erfasst. Auf diese Weise können Sie Ihre Customer Journey Analytics-Daten am besten parallel mit Ihren Adobe Analytics-Daten vergleichen.<p>Deaktivieren Sie Adobe Analytics erst, wenn Sie mit den Daten in Ihrer Customer Journey Analytics-Umgebung zurechtkommen.</p><p>**Hinweis:** Adobe empfiehlt eine neue Implementierung des Web SDK für Ihre Customer Journey Analytics-Umgebung in Verbindung mit dem Analytics-Quell-Connector für historische Daten. [Weitere Informationen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| Historische Daten aus Adobe Analytics beibehalten | Adobe empfiehlt, die Adobe Analytics-Umgebung noch eine gewisse Zeit lang mit dem Analytics-Quell-Connector in Betrieb zu halten, wenn die neue Customer Journey Analytics-Umgebung bereits ausgeführt wird und Daten erfasst. Dies ist die beste Möglichkeit, um historische Adobe Analytics-Daten in Customer Journey Analytics zu importieren.<p>Nachdem Sie mit Ihrer neuen Web SDK-Implementierung genügend historische Daten in Customer Journey Analytics erfasst haben, können Sie den Analytics-Quell-Connector vollständig entfernen. Verfahren Sie auf diese Weise, wenn Sie sich ausschließlich auf die historischen Daten in verlassen können, die Sie mit der neuen Customer Journey Analytics Web SDK-Implementierung erfasst haben.</p><p>**Hinweis:** Adobe empfiehlt eine neue Implementierung des Web SDK für Ihre Customer Journey Analytics-Umgebung in Verbindung mit dem Analytics-Quell-Connector für historische Daten. [Weitere Informationen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| Daten-Feeds oder andere Adobe Analytics-Funktionen verwenden | Einige wenige Funktionen sind in Customer Journey Analytics noch nicht vollständig verfügbar. Wenn Sie Zugriff auf diese Funktionen benötigen, muss Adobe Analytics ggf. zusammen mit Customer Journey Analytics verwendet werden, bis diese Funktionen verfügbar sind. <p>Zu den Funktionen, die in Customer Journey Analytics nicht vollständig verfügbar sind, gehören Daten-Feeds und die Beitragsanalyse. Eine vollständige Liste der Funktionen, die noch nicht verfügbar sind, finden Sie unter [Unterstützung der Customer Journey Analytics-Funktion](/help/getting-started/aa-vs-cja/cja-aa.md).</p> |

## Prozess und Zeitrahmen der Deaktivierung von Adobe Analytics {#disable-adobe-analytics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement-third-pary"
>title="Deaktivieren eines Tag-Management-Drittanbietersystems"
>abstract="Wenn die Web SDK-Daten voll funktionsfähig sind, arbeiten Sie mit Ihrer bzw. Ihrem Tag-Admin zusammen, um die AppMeasurement-Bibliothek aus dem Tag-Management-Drittanbietersystem zu entfernen.<br><br>Wie lange dieser Schritt ungefähr dauert, ist davon abhängig, wie einfach sich AppMeasurement über Ihr Tag-Management-Produkt deaktivieren lässt sowie vom Veröffentlichungszyklus, den Ihre Organisation zur Bereitstellung und Verwaltung von Tagcode verwendet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-tags"
>title="Deaktivieren der Analytics-Erweiterung in Tags"
>abstract="Wenn Web SDK-Daten voll funktionsfähig sind, wenden Sie sich an Ihre Tags-Admins, um die Adobe Analytics-Erweiterung aus der Tag-Eigenschaft zu entfernen. Vergewissern Sie sich zunächst, dass Ihre Benutzerinnen und Benutzer von Adobe Analytics zu Customer Journey Analytics gewechselt haben."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-api"
>title="Deaktivieren der API-Datenerfassung für Adobe Analytics"
>abstract="Wenn Web SDK-Daten voll funktionsfähig sind, entfernen Sie den Adobe Analytics-Code gemeinsam mit dem entsprechenden Entwicklungs-Team aus dem Projekt. Vergewissern Sie sich zunächst, dass Ihre Benutzerinnen und Benutzer von Adobe Analytics zu Customer Journey Analytics gewechselt haben."

<!-- markdownlint-enable MD034 -->

Ihre bestehende Adobe Analytics-Implementierung ist ein wichtiger Bestandteil eines erfolgreichen Upgrades auf Customer Journey Analytics, wie oben unter [Verwendung von Adobe Analytics während und nach einem Upgrade](#uses-of-adobe-analytics-during-and-after-an-upgrade) beschrieben.

Wenn Sie Adobe Analytics für die im obigen Abschnitt beschriebenen Zwecke nicht mehr benötigen, verwenden Sie die folgenden Informationen, um Adobe Analytics zu entfernen:

1. Erfassen Sie keine Daten mehr mit Adobe Analytics.

   Wenn Sie mit den parallelen Vergleichen Ihrer Adobe Analytics-Daten und Ihrer Customer Journey Analytics-Daten zufrieden sind, können Sie die Datenerfassung mit Ihrer Adobe Analytics-Implementierung stoppen. Neue Adobe Analytics-Daten werden nicht mehr über den Analytics-Quell-Connector an Customer Journey Analytics übermittelt.

   Daten, die Sie zuvor in Ihrer Adobe Analytics-Umgebung erfasst haben, sind jedoch weiterhin als historische Daten in Customer Journey Analytics über den Analytics-Quell-Connector verfügbar.

   Dieser Prozess unterscheidet sich je nach der Datenerfassungsmethode, die Sie zur Implementierung von Adobe Analytics verwendet haben:

   +++ AppMeasurement

   [Deaktivieren Sie die AppMeasurement-Datenerfassung](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md).

   +++

   +++ Analytics-Erweiterung (Tags)

   Analytics-Erweiterung in Tags deaktiveren.

   +++

   +++ API

   API-Datenerfassung für Adobe Analytics deaktivieren.

   +++

   +++ Drittanbieter

   Arbeiten Sie mit Ihrer oder Ihrem Tag-Admin zusammen, um die AppMeasurement-Bibliothek aus dem Tag-Management-System eines Drittanbieters zu entfernen.

   +++

1. Adobe Analytics als Dienst aus dem Datenstrom entfernen.

   Wenn die Web-SDK-Daten voll funktionsfähig sind, arbeiten Sie mit Ihrer oder Ihrem Platform-Admin zusammen, um Adobe Analytics als Dienst aus dem Datenstrom zu entfernen.

   Bevor Sie Adobe Analytics als Dienst entfernen, stellen Sie sicher, dass Ihre Analytics-Benutzenden Customer Journey Analytics und nicht Adobe Analytics verwenden.

1. Den Analytics-Quell-Connectors vollständig entfernen.

   Nachdem Sie mit Ihrer neuen Web SDK-Implementierung genügend historische Daten in Customer Journey Analytics erfasst haben, können Sie den Analytics-Quell-Connector vollständig entfernen.

   Gehen Sie so vor, wenn Sie die historischen Daten aus Ihrer Adobe Analytics-Umgebung nicht mehr über den Analytics-Quell-Connector erfassen müssen und sich nur noch auf die historischen Daten verlassen können, die Sie mit der neuen Web-SDK-Implementierung erfasst haben.

{{upgrade-final-step}}

