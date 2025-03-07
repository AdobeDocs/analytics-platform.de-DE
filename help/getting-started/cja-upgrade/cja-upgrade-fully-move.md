---
title: Beurteilen, wie lange Sie Adobe Analytics nach dem Upgrade auf Customer Journey Analytics noch benötigen
description: Erfahren Sie, wie Sie auswerten können, wie lange Sie Adobe Analytics nach dem Upgrade auf Customer Journey Analytics benötigen
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 7142ef84-66a6-49eb-938b-b67c9b65bf93
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 18%

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
>title="Beibehalten beider Analytics-Produkte"
>abstract="(Nicht empfohlen) Wenn Sie sich für diese Option entscheiden, enthält Ihr Vertrag mit Adobe sowohl Adobe Analytics als auch Customer Journey Analytics, was für Ihre Organisation im Laufe der Zeit kostspieliger werden kann."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-source-connector"
>title="Deaktivieren Sie den Analytics-Quell-Connector, um Daten ausschließlich aus der Web-SDK zu verwenden"
>abstract="Der Analytics-Quell-Connector wird verwendet, um einen direkten Datenvergleich, historische Daten und Zugriff auf einige Funktionen bereitzustellen, die in Customer Journey Analytics nicht vollständig verfügbar sind. Wenn Sie Adobe Analytics für diese Zwecke nicht mehr benötigen, können Sie den Analytics-Quell-Connector deaktivieren."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Die meisten Unternehmen werden Adobe Analytics nach dem Upgrade auf Customer Journey Analytics letztendlich deaktivieren. Dies liegt an den Kosten und der Komplexität der Wartung von zwei Analytics-Umgebungen.

Adobe empfiehlt jedoch, die Adobe Analytics-Umgebung nach der Implementierung von Customer Journey Analytics noch einen bestimmten Zeitraum lang auszuführen. In den folgenden Abschnitten werden die Gründe dafür sowie der empfohlene Zeitpunkt für die Deaktivierung von Adobe Analytics beschrieben.

## Verwendung von Adobe Analytics während und nach einem Upgrade

Bei der Entscheidung, ob und wann Ihr Unternehmen Adobe Analytics deaktivieren sollte, sollten Sie die folgenden Verwendungszwecke von Adobe Analytics während und nach einem Upgrade auf Customer Journey Analytics berücksichtigen:

| Verwendung von Adobe Analytics während und nach dem Upgrade | Erklärung |
|---------|----------|
| Paralleler Datenvergleich durchführen | Adobe empfiehlt, die Adobe Analytics-Umgebung noch einen bestimmten Zeitraum lang auszuführen, nachdem die neue Customer Journey Analytics-Umgebung ausgeführt und Daten erfasst wurde. Auf diese Weise können Sie Ihre Customer Journey Analytics-Daten am besten nebeneinander mit Ihren Adobe Analytics-Daten vergleichen.<p>Deaktivieren Sie Adobe Analytics erst, wenn Sie mit den Daten in Ihrer Customer Journey Analytics-Umgebung vertraut sind.</p><p>**Hinweis:** Adobe empfiehlt eine neue Implementierung von Web SDK für Ihre Customer Journey Analytics-Umgebung in Verbindung mit dem Analytics-Quell-Connector für Verlaufsdaten. [Weitere Informationen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| Verlaufsdaten aus Adobe Analytics aufbewahren | Adobe empfiehlt, Ihre Adobe Analytics-Umgebung für einen bestimmten Zeitraum mit dem Analytics-Quell-Connector zu konfigurieren, nachdem Ihre neue Customer Journey Analytics-Umgebung ausgeführt und Daten erfasst wurde. Dies ist die beste Möglichkeit, historische Adobe Analytics-Daten in Customer Journey Analytics zu importieren.<p>Nachdem Sie mit Ihrer neuen Web-SDK-Implementierung genügend historische Daten in Customer Journey Analytics erfasst haben, können Sie den Analytics-Quell-Connector vollständig entfernen. Tun Sie dies, wenn Sie sich ausschließlich auf die historischen Daten in verlassen können, die Sie mit der neuen Customer Journey Analytics Web SDK-Implementierung erfasst haben.</p><p>**Hinweis:** Adobe empfiehlt eine neue Implementierung von Web SDK für Ihre Customer Journey Analytics-Umgebung in Verbindung mit dem Analytics-Quell-Connector für Verlaufsdaten. [Weitere Informationen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| Verwenden von Daten-Feeds oder anderen Adobe Analytics-Funktionen | Einige wenige Funktionen sind in Customer Journey Analytics noch nicht vollständig verfügbar. Wenn Sie Zugriff auf diese Funktionen benötigen, kann es erforderlich sein, Adobe Analytics zusammen mit Customer Journey Analytics zu verwenden, bis diese Funktionen verfügbar sind. <p>Zu den Funktionen, die in Customer Journey Analytics nicht vollständig verfügbar sind, gehören Daten-Feeds und Beitragsanalyse. Eine vollständige Liste der Funktionen, die noch nicht verfügbar sind, finden Sie unter [Customer Journey Analytics-Funktionsunterstützung](/help/getting-started/aa-vs-cja/cja-aa.md).</p> |

## Prozess und Timeline der Deaktivierung von Adobe Analytics {#disable-adobe-analytics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement-third-pary"
>title="Deaktivieren des Tag-Management-Systems eines Drittanbieters"
>abstract="Wenn die Web-SDK-Daten voll funktionsfähig sind, wenden Sie sich an Ihre bzw. Ihren Tag-Admin, um die AppMeasurement-Bibliothek aus dem Tag-Management-System eines Drittanbieters zu entfernen.<br><br>Die geschätzte Dauer für diesen Schritt hängt davon ab, wie einfach sich AppMeasurement über Ihr Tag-Management-Produkt deaktivieren lässt, sowie vom Veröffentlichungszyklus, den Ihre Organisation zur Bereitstellung und Verwaltung von Tag-Code verwendet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-tags"
>title="Deaktivieren der Analytics-Erweiterung in Tags"
>abstract="Wenn Web SDK-Daten voll funktionsfähig sind, wenden Sie sich an Ihren Tags-Administrator, um die Adobe Analytics-Erweiterung aus der Tag-Eigenschaft zu entfernen. Vergewissern Sie sich zunächst, dass Ihre Benutzerinnen und Benutzer von Adobe Analytics zu Customer Journey Analytics gewechselt haben."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-api"
>title="API-Datenerfassung für Adobe Analytics deaktivieren"
>abstract="Wenn Web SDK-Daten voll funktionsfähig sind, entfernen Sie den Adobe Analytics-Code gemeinsam mit dem entsprechenden Entwicklungsteam aus dem Projekt. Vergewissern Sie sich zunächst, dass Ihre Benutzerinnen und Benutzer von Adobe Analytics zu Customer Journey Analytics gewechselt haben."

<!-- markdownlint-enable MD034 -->

Ihre bestehende Adobe Analytics-Implementierung ist ein wichtiger Bestandteil eines erfolgreichen Upgrades auf Customer Journey Analytics, wie im obigen Abschnitt &quot;[ von Adobe Analytics während und nach einem Upgrade“ ](#uses-of-adobe-analytics-during-and-after-an-upgrade).

Wenn Sie Adobe Analytics für die im obigen Abschnitt beschriebenen Zwecke nicht mehr benötigen, verwenden Sie die folgenden Informationen, um Adobe Analytics zu entfernen:

1. Beenden der Datenerfassung mit Adobe Analytics.

   Wenn Sie mit den nebeneinander angezeigten Vergleichen Ihrer Adobe Analytics-Daten und Ihrer Customer Journey Analytics-Daten zufrieden sind, können Sie die Datenerfassung mit Ihrer Adobe Analytics-Implementierung beenden. Neue Adobe Analytics-Daten werden nicht mehr über den Analytics-Quell-Connector an Customer Journey Analytics übermittelt.

   Daten, die Sie zuvor in Ihrer Adobe Analytics-Umgebung erfasst haben, sind jedoch weiterhin als historische Daten in Customer Journey Analytics über den Analytics-Quell-Connector verfügbar.

   Dieser Prozess unterscheidet sich je nach der Datenerfassungsmethode, die Sie zur Implementierung von Adobe Analytics verwendet haben:

+++ AppMeasurement

   [AppMeasurement-Datenerfassung deaktivieren](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md).

+++

+++ Analytics-Erweiterung (Tags)

   Deaktivieren Sie die Analytics-Erweiterung in Tags.

+++

+++ API

   Deaktivieren Sie die API-Datenerfassung.

+++

+++ Drittanbieter

   Arbeiten Sie mit Ihrem Tag-Administrator zusammen, um die AppMeasurement-Bibliothek aus dem Tag-Management-System eines Drittanbieters zu entfernen.

+++

1. Entfernen Sie Adobe Analytics as a Cloud Service aus dem Datenstrom.

   Wenn die Web SDK-Daten voll funktionsfähig sind, wenden Sie sich an Ihren Platform-Administrator, um Adobe Analytics as a Cloud Service aus dem Datenstrom zu entfernen.

   Bevor Sie Adobe Analytics als Service entfernen, stellen Sie sicher, dass Ihre Analytics-Benutzenden Customer Journey Analytics und nicht Adobe Analytics verwenden.

1. Entfernen Sie den Analytics-Quell-Connector vollständig.

   Nachdem Sie mit Ihrer neuen Web-SDK-Implementierung genügend historische Daten in Customer Journey Analytics erfasst haben, können Sie den Analytics-Quell-Connector vollständig entfernen.

   Tun Sie dies, wenn Sie die historischen Daten aus Ihrer Adobe Analytics-Umgebung nicht mehr über den Analytics-Quell-Connector benötigen und sich nur noch auf die historischen Daten verlassen können, die Sie mit der neuen Web SDK-Implementierung erfasst haben.

{{upgrade-final-step}}

