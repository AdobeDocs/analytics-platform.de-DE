---
title: Reporting zu Zielgruppen
description: Integrieren von Adobe Target mit Customer Journey Analytics
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
TQID: https://experienceleague.adobe.com/7Q8q-e58PrmANht9DpOXuNFImYC48ELhrXPRhBG6gYQ
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 410
ht-degree: 44%

---

# Reporting zu Zielgruppen

Mit dem Target-Reporting in Customer Journey Analytics können Sie Adobe Target-Aktivitäten direkt in Customer Journey Analytics messen und Berichte dazu erstellen. Diese Funktionalität ist vergleichbar mit der, die in Adobe Analytics (AA) über Analytics for Target (A4T) ausgeführt wird, jedoch mit der Konnektivität zu Adobe Experience Platform (AEP).

Durch das Hinzufügen des Suchdatensatzes der Target-Klassifizierung (der standardmäßig in Experience Platform verfügbar ist) zu einer Customer Journey Analytics-Verbindung können Benutzende nun die Reporting-Tools von Target, die Attribution der Zielreihenfolge und andere Funktionen optimal nutzen. Wenn nur einige kleinere Vorbereitungen und Anpassungen in der Customer Journey Analytics-Datenansicht vorgenommen wurden, können diese Aktivitäten für alle Benutzenden, die Target-Daten direkt an CJA senden möchten, sofort verfügbar gemacht werden.

## Primäre Vorteile

* Marketing-Fachleute können zu jedem Zeitpunkt Customer Journey Analytics-Erfolgsmetriken dynamisch auf Target-Aktivitätsberichte anwenden. Es ist nicht erforderlich, vor Ausführung der Aktivität alles zu spezifizieren.
* Marketing-Fachleute können Customer Journey Analytics-Funktionen wie das Experimentierungs-Panel nutzen, um die Personalisierung ihrer Website weiter zu analysieren.
* Marketing-Fachleute können eine einzige Reporting-Quelle für Adobe Journey Optimizer und Target verwenden. Beide Personalisierungsprodukte können mit Customer Journey Analytics verbunden werden, um eine stärker ganzheitliche Ansicht Ihrer Web-Personalisierung zu erhalten.

## Hinweise und Überlegungen

Ihre Target-Aktivität muss [Customer Journey Analytics als Berichtsquelle verwenden](https://experienceleague.adobe.com/de/docs/target/using/integrate/cja/target-reporting-in-cja).

Nachdem der Zielklassifizierungsereignis-Datensatz zu einer Verbindung hinzugefügt wurde, müssen einige kleinere Anpassungen in der Datenansicht vorgenommen werden, sobald diese Komponenten als Dimensionen hinzugefügt wurden, darunter:

* Festlegen der Persistenz, sodass sie der Art des Trackings in Target ähnelt (wenden Sie sich an einen Target-Berater oder an den Kunden, um sicherzustellen, dass die Einstellungen korrekt sind).

* Festlegen der Persistenz auf ALLE , sodass mehrere Target-Aktivitäten gleichzeitig verfolgt und nicht von zukünftigen oder vorherigen Aktivitäten überschrieben werden können.

## Ausführlichere Informationen

Weitere Informationen finden Sie unter [Target-Reporting in Adobe Customer Journey Analytics](https://experienceleague.adobe.com/de/docs/target/using/integrate/cja/target-reporting-in-cja) in der Target-Dokumentation.

Im [Experimentier-Bedienfeld](../analysis-workspace/c-panels/experimentation.md) finden Sie weitere Informationen dazu, wie Analysten verschiedene Varianten von Anwendererlebnissen, Marketing oder Messaging miteinander vergleichen können, um zu ermitteln, welches die beste Lösung für ein bestimmtes Ergebnis ist. Sie können den Anstieg und die Konfidenz eines jeden A/B-Experiments von jeder beliebigen Experimentierplattform aus bewerten – online, offline, aus Adobe-Lösungen wie Target oder Journey Optimizer und sogar aus eigenen, selbst eingebrachten Daten.
