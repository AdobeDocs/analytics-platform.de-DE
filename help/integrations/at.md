---
title: Target-Reporting in Adobe Customer Journey Analytics
description: Integrieren von Adobe Target mit Customer Journey Analytics
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
source-git-commit: b189776de8cadae3a93c717b6814f2130ab1be43
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 40%

---

# Target-Reporting in Adobe Customer Journey Analytics

Mit der Zielberichterstellung in Customer Journey Analytics können Sie Adobe Target-Aktivitäten direkt im Customer Journey Analytics messen und darüber berichten. Diese Funktion ist mit der in Adobe Analytics (AA) über Analytics for Target (A4T) durchgeführten Ausführung vergleichbar, allerdings mit der Konnektivität zu Adobe Experience Platform (AEP).

Durch das Hinzufügen des (standardmäßig unter Experience Platform verfügbaren) Target Classification-Lookup-Datensatzes zu einer Customer Journey Analytics-Verbindung haben Benutzer jetzt die richtige Exposition gegenüber den Berichterstellungs-Tools von Target, der Zielgruppen-Auftragsattribution und anderen Funktionen. Mit nur geringfügigen Vorbereitungen und Anpassungen innerhalb der Datenansicht der Customer Journey Analytics können diese Aktivitäten sofort für jeden Benutzer verfügbar gemacht werden, der Target-Daten direkt an CJA senden möchte.

## Primäre Vorteile

* Marketing-Fachleute können zu jedem Zeitpunkt Customer Journey Analytics-Erfolgsmetriken dynamisch auf Target-Aktivitätsberichte anwenden. Es ist nicht erforderlich, vor Ausführung der Aktivität alles zu spezifizieren.
* Marketing-Fachleute können Customer Journey Analytics-Funktionen wie das Experimentierungs-Panel nutzen, um die Personalisierung ihrer Website weiter zu analysieren.
* Marketing-Fachleute können eine einzige Reporting-Quelle für Adobe Journey Optimizer und Target verwenden. Beide Personalisierungsprodukte können mit Customer Journey Analytics verbunden werden, um eine stärker ganzheitliche Ansicht Ihrer Web-Personalisierung zu erhalten.

## Hinweise und Überlegungen

Nachdem der Datensatz mit dem Ereignis-Datensatz für die Target-Klassifizierung zu einer CJA-Verbindung hinzugefügt wurde, müssen in der CJA-Datenansicht einige geringfügige Anpassungen vorgenommen werden, sobald diese Komponenten als Dimensionen hinzugefügt wurden, darunter:

* Festlegen der Persistenz, die der Verfolgung in Target ähnelt (wenden Sie sich an einen Target-Berater oder den Kunden, um die richtigen Einstellungen sicherzustellen).

* Setzen der Persistenz auf ALLE , wodurch mehrere Target-Aktivitäten gleichzeitig verfolgt und nicht von künftigen oder früheren Aktivitäten überschrieben werden können.

## Detailliertere Informationen

Weitere Informationen finden Sie unter [Target-Reporting in Adobe Customer Journey Analytics](https://experienceleague.adobe.com/de/docs/target/using/integrate/cja/target-reporting-in-cja) in der Target-Dokumentation.

Im [Experimentier-Bedienfeld](../analysis-workspace/c-panels/experimentation.md) finden Sie weitere Informationen dazu, wie Analysten verschiedene Varianten von Anwendererlebnissen, Marketing oder Messaging miteinander vergleichen können, um zu ermitteln, welches die beste Lösung für ein bestimmtes Ergebnis ist. Sie können den Anstieg und die Konfidenz eines jeden A/B-Experiments von jeder beliebigen Experimentierplattform aus bewerten – online, offline, aus Adobe-Lösungen wie Target oder Journey Optimizer und sogar aus eigenen, selbst eingebrachten Daten.
