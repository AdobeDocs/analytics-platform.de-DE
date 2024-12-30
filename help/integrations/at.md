---
title: Reporting zu Zielgruppen
description: Integrieren von Adobe Target mit Customer Journey Analytics
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
source-git-commit: 979564d0249abadd454ce43aba9aeae2c78a44f0
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 41%

---

# Reporting zu Zielgruppen

Mit dem Target-Reporting in Customer Journey Analytics können Sie Adobe Target-Aktivitäten direkt in Customer Journey Analytics messen und Berichte dazu erstellen. Diese Funktionalität ist vergleichbar mit der, die in Adobe Analytics (AA) über Analytics for Target (A4T) ausgeführt wird, jedoch mit der Verbindung zu Adobe Experience Platform (AEP).

Durch das Hinzufügen des Suchdatensatzes der Target-Klassifizierung (der standardmäßig auf Experience Platform verfügbar ist) zu einer Customer Journey Analytics-Verbindung erhalten Anwender jetzt eine angemessene Offenlegung gegenüber Reporting-Tools von Target, der Attribution von Target-Bestellungen und anderen Funktionen. Wenn nur einige kleinere Vorbereitungen und Anpassungen in der Customer Journey Analytics-Datenansicht vorgenommen wurden, können diese Aktivitäten für alle Benutzenden, die Target-Daten direkt an CJA senden möchten, sofort verfügbar gemacht werden.

## Primäre Vorteile

* Marketing-Fachleute können zu jedem Zeitpunkt Customer Journey Analytics-Erfolgsmetriken dynamisch auf Target-Aktivitätsberichte anwenden. Es ist nicht erforderlich, vor Ausführung der Aktivität alles zu spezifizieren.
* Marketing-Fachleute können Customer Journey Analytics-Funktionen wie das Experimentierungs-Panel nutzen, um die Personalisierung ihrer Website weiter zu analysieren.
* Marketing-Fachleute können eine einzige Reporting-Quelle für Adobe Journey Optimizer und Target verwenden. Beide Personalisierungsprodukte können mit Customer Journey Analytics verbunden werden, um eine stärker ganzheitliche Ansicht Ihrer Web-Personalisierung zu erhalten.

## Hinweise und Überlegungen

Nachdem der Zielklassifizierungsereignis-Datensatz zu einer CJA-Verbindung hinzugefügt wurde, müssen einige kleinere Anpassungen in der CJA-Datenansicht vorgenommen werden, sobald diese Komponenten als Dimensionen hinzugefügt wurden, darunter:

* Festlegen der Persistenz, sodass sie der Art des Trackings in Target ähnelt (wenden Sie sich an einen Target-Berater oder an den Kunden, um sicherzustellen, dass die Einstellungen korrekt sind).

* Festlegen der Persistenz auf ALLE , sodass mehrere Target-Aktivitäten gleichzeitig verfolgt und nicht von zukünftigen oder vorherigen Aktivitäten überschrieben werden können.

## Ausführlichere Informationen

Weitere Informationen finden Sie unter [Target-Reporting in Adobe Customer Journey Analytics](https://experienceleague.adobe.com/de/docs/target/using/integrate/cja/target-reporting-in-cja) in der Target-Dokumentation.

Im [Experimentier-Bedienfeld](../analysis-workspace/c-panels/experimentation.md) finden Sie weitere Informationen dazu, wie Analysten verschiedene Varianten von Anwendererlebnissen, Marketing oder Messaging miteinander vergleichen können, um zu ermitteln, welches die beste Lösung für ein bestimmtes Ergebnis ist. Sie können den Anstieg und die Konfidenz eines jeden A/B-Experiments von jeder beliebigen Experimentierplattform aus bewerten – online, offline, aus Adobe-Lösungen wie Target oder Journey Optimizer und sogar aus eigenen, selbst eingebrachten Daten.
